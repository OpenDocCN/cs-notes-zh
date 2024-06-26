# 4.4   最短路径

> 原文：[`algs4.cs.princeton.edu/44sp`](https://algs4.cs.princeton.edu/44sp)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)


## 最短路径。

加权有向图是一个有向图，其中我们为每条边关联权重或成本。从顶点 s 到顶点 t 的*最短路径*是从 s 到 t 的有向路径，具有没有更低权重的其他路径的属性。![最短路径](img/c9fd258b9b7a2ffcb98efba84aecb15f.png)

## 属性。

我们总结了几个重要的属性和假设。

+   *路径是有方向的。* 最短路径必须遵守其边的方向。

+   *权重不一定是距离。* 几何直觉可能有所帮助，但边的权重可能代表时间或成本。

+   *并非所有顶点都需要可达。* 如果 t 从 s 不可达，则根本没有路径，因此从 s 到 t 的最短路径也不存在。

+   *负权重引入了复杂性。* 目前，我们假设边的权重是正数（或零）。

+   *最短路径通常是简单的。* 我们的算法忽略形成循环的零权重边，因此它们找到的最短路径没有循环。

+   *最短路径不一定是唯一的。* 从一个顶点到另一个顶点可能有多条最低权重的路径；我们满足于找到其中任何一条。

+   *并行边和自环可能存在。* 在文本中，我们假设不存在并行边，并使用符号 v->w 来表示从 v 到 w 的边，但我们的代码可以轻松处理它们。

## 加权有向图数据类型。

我们使用以下 API 表示加权边：![加权有向边的 API](img/b1f77b9849da61ad97bff9c0b8aab7e8.png)

`from()`和`to()`方法对于访问边的顶点很有用。DirectedEdge.java 实现了这个 API。

我们使用以下 API 表示加权有向图：

![用于加权图](img/4236d6807f411808c24225d8e6b29d89.png)

EdgeWeightedDigraph.java 使用邻接表表示实现了该 API。

![加权有向图表示](img/a329bb0074af43f005bb5a202ed09660.png)

## 最短路径 API。

我们使用以下 API 计算加权有向图的最短路径：![SP 实现的 API](img/4d3ce1ced09aa91dcd4d7bad3bace51f.png)

我们准备了一些测试数据：

+   tinyEWD.txt 包含 8 个顶点和 15 条边

+   mediumEWD.txt 包含 250 个顶点和 2,546 条边

+   1000EWG.txt 包含 1,000 个顶点和 16,866 条边

+   10000EWG.txt 包含 10,000 个顶点和 123,462 条边

+   largeEWG.txt 包含一百万个顶点和 15,172,126 条边。

## 单源最短路径的数据结构。

给定一个加权有向图和一个指定的顶点 s，*最短路径树*（SPT）是一个子图，包含 s 和所有从 s 可达的顶点，形成以 s 为根的有向树，使得每条树路径都是图中的最短路径。

我们用两个顶点索引数组表示最短路径：

+   *最短路径树上的边*：`edgeTo[v]`是从 s 到 v 的最短路径上的最后一条边。

+   *到源的距离*：`distTo[v]`是从 s 到 v 的最短路径的长度。

![最短路径树](img/f3e30b34dd784170d84f6cbd51cae3c0.png)

## 松弛。

我们的最短路径实现基于一种称为*松弛*的操作。我们将`distTo[s]`初始化为 0，对于所有其他顶点 v，将`distTo[v]`初始化为无穷大。

+   *边松弛。* 对边 v->w 进行松弛意味着测试从 s 到 w 的已知最佳路径是否是从 s 到 v，然后沿着从 v 到 w 的边，如果是，则更新我们的数据结构。

    ```java
    private void relax(DirectedEdge e) {
        int v = e.from(), w = e.to();
        if (distTo[w] > distTo[v] + e.weight()) {
            distTo[w] = distTo[v] + e.weight();
            edgeTo[w] = e;
        }
    }

    ```

    ![边松弛](img/c6b74f72869ca238f32028f7b25b7f9d.png)

+   *顶点松弛。* 我们所有的实现实际上都会松弛从给定顶点指向的所有边。

    ```java
    private void relax(EdgeWeightedDigraph G, int v) {
        for (DirectedEdge e : G.adj(v)) {
            int w = e.to();
            if (distTo[w] > distTo[v] + e.weight()) {
                distTo[w] = distTo[v] + e.weight();
                edgeTo[w] = e;
            }
        }
    }

    ```

## 迪杰斯特拉算法。

戴克斯特拉算法将`dist[s]`初始化为 0，将所有其他`distTo[]`条目初始化为正无穷。然后，它重复地放松并将具有最低`distTo[]`值的非树顶点添加到树中，继续直到所有顶点都在树上或没有非树顶点具有有限的`distTo[]`值。

DijkstraSP.java 是戴克斯特拉算法的高效实现。它使用 IndexMinPQ.java 作为优先队列。

## 命题。

戴克斯特拉算法使用额外空间与 V 成正比，时间与 E log V 成正比（在最坏情况下）解决了带非负权重的带权有向图中的单源最短路径问题。

## 无环带权有向图。

我们使用术语*带权有向无环图*来指代无环带权有向图。

+   *带权有向无环图中的单源最短路径问题*。我们现在考虑一种用于查找最短路径的算法，对于带权有向无环图而言，它比戴克斯特拉算法更简单且更快。

    +   它在线性时间内解决了单源问题。

    +   它处理负边权重。

    +   它解决了相关问题，如查找最长路径。

    该算法将顶点放松与拓扑排序结合起来。我们将`distTo[s]`初始化为 0，将所有其他`distTo[]`值初始化为无穷大，然后按照*拓扑顺序*放松顶点。AcyclicSP.java 是这种方法的实现。它依赖于这个版本的 Topological.java，扩展以支持带权有向图。

+   *带权有向无环图中的单源最长路径问题*。我���可以通过将`distTo[]`值初始化为负无穷大并在`relax()`中改变不等式的意义来解决带权有向无环图中的单源最长路径问题。AcyclicLP.java 实现了这种方法。

+   *关键路径法*。我们考虑并行的有前置约束的作业调度问题：给定一组指定持续时间的作业，其中有前置约束规定某些作业必须在某些其他作业开始之前完成，我们如何在相同数量的处理器上安排这些作业，以便它们在最短的时间内完成，同时仍然遵守约束条件？![作业调度问题](img/77a2a5e9a681f66322db190852974ffe.png)![作业调度解决方案](img/a3984ec355bb6681c7e9df6ffe021007.png)

    通过将问题制定为带权有向无环图中的最长路径问题，可以解决此问题：创建一个带权有向无环图，其中包含一个源 s，一个汇 t，以及每个作业的两个顶点（一个起始顶点和一个结束顶点）。对于每个作业，从其起始顶点到其结束顶点添加一条权重等于其持续时间的边。对于每个前置约束 v->w，从对应于 v 的结束顶点到对应于 w 的开始顶点添加一条零权重边。还从源到每个作业的起始顶点和从每个作业的结束顶点到汇添加零权重边。

    ![作业调度问题简化为最长路径](img/983f1d16dc523fe0e36509b80b1c135b.png)

    现在，根据从源到达的最长路径的长度安排每个作业的时间。

    ![作业调度问题关键路径](img/1a9ad0173d95fc74e4895aec07706077.png)

    CPM.java 是关键路径法的实现。

## 命题。

通过按拓扑顺序放松顶点，我们可以在时间复杂度为 E + V 的情况下解决带权有向无环图的单源最短路径和最长路径问题。

## 一般带权有向图中的最短路径。

如果(i)所有权重为非负或(ii)没有循环，则可以解决最短路径问题。

+   *负循环*。*负循环*是一个总权重为负的有向循环。如果存在负循环，则最短路径的概念是没有意义的。![带有负循环的加权有向图](img/1ddeec2a4571899ee4984f8e825d77aa.png)

    因此，我们考虑没有负循环的加权有向图。

+   *贝尔曼-福特算法*。将`distTo[s]`初始化为 0，将所有其他`distTo[]`值初始化为无穷大。然后，以任意顺序考虑有向图的边，并放松所有边。进行 V 次这样的遍历。

    ```java
    for (int pass = 0; pass < G.V(); pass++)
       for (int v = 0; v < G.V(); v++)
          for (DirectedEdge e : G.adj(v))
              relax(e);

    ```

    我们不详细考虑这个版本，因为它*总是*放松 V E 条边。

+   *基于队列的贝尔曼-福特算法*。可能导致`distTo[]`变化的唯一边是那些离开上一轮中`distTo[]`值发生变化的顶点的边。为了跟踪这样的顶点，我们使用一个 FIFO 队列。BellmanFordSP.java 通过维护两个额外的数据结构来实现这种方法：

    +   一个要放松的顶点队列

    +   一个顶点索引的布尔数组`onQ[]`，指示哪些顶点在队列上，以避免重复

+   *负循环检测*。在许多应用中，我们的目标是检查并提取负循环。因此，我们向 API 添加以下方法：![负循环检测的 API](img/cfd7f360a9766f394952b3b95a9be85a.png)

    当且仅当在所有边的第 V 次遍历后队列非空时，从源可达负循环。此外，我们`edgeTo[]`数组中的边子图必须包含一个负循环。因此，为了实现`negativeCycle()`，BellmanFordSP.java 从`edgeTo[]`中的边构建一个加权有向图，并在该图中查找循环。为了找到循环，它使用 EdgeWeightedDirectedCycle.java，这是第 4.3 节中 DirectedCycle.java 的一个版本，适用于加权有向图。我们通过仅在每次第 V 次边放松后执行此检查来分摊此检查的成本。

+   *套汇检测*。考虑一个基于商品交易的金融交易市场。rates.txt 中的表显示了货币之间的转换率。文件的第一行是货币 V 的数量；然后文件每行给出货币的名称，然后是转换为其他货币的汇率。*套汇机会*是一个有向循环，使得交换率的乘积大于 1。例如，我们的表格显示，1000 美元可以购买 1000.00 × .741 = 741 欧元，然后我们可以用我们的欧元购买 741 × 1.366 = 1,012.206 加拿大元，最后，我们可以用我们的加拿大元购买 1,012.206 × .995 = 1,007.14497 美元，获得 7.14497 美元的利润！

    | ![汇率](img/ef7ed3932b44809c134885251055b1c9.png) |             | ![套汇机会](img/cae0c4738e269685e9e1c0ed762d4d50.png) |
    | --- | --- | --- |

    为了将套汇问题制定为负循环检测问题，将每个权重替换为其*对数*的负值。通过这种改变，在原问题中通过乘以边权重来计算路径权重对应于在转换后的问题中将它们相加。Arbitrage.java 通过解决相应的负循环检测问题来识别货币兑换网络中的套汇机会。

### 命题。

在加权有向图中，从 s 到 v 存在最短路径当且仅当从 s 到 v 存在至少一条有向路径，并且从 s 到 v 的任何有向路径上的顶点都不在负循环上。

### 命题。

贝尔曼-福特算法解决了给定源 s 的单源最短路径问题（或找到从 s 可达的负循环）对于具有 V 个顶点和 E 条边的任意加权有向图，在最坏情况下，时间复杂度为 E V，额外空间复杂度为 V。

#### 问与答

**Q.** Dijkstra 算法能处理负权重吗？

**A.** 是和否。有两种已知的最短路径算法称为*Dijkstra 算法*，取决于一个顶点是否可以多次入队到优先队列。当权重为非负时，这两个版本是相同的（因为没有顶点会多次入队）。DijkstraSP.java 中实现的版本（允许一个顶点多次入队）在存在负边权（但没有负环）时是正确的，但其最坏情况下的运行时间是指数级的。（我们注意到 DijkstraSP.java 如果边权重为负数，则会抛出异常，以便程序员不会对这种指数级行为感到惊讶。）如果我们修改 DijkstraSP.java 以使一个顶点不能多次入队（例如，使用`marked[]`数组标记那些已经被松弛的顶点），那么算法保证在*E* log *V*时间内运行，但当存在负权边时可能产生错误结果。

#### 练习

1.  真或假。将每个边权重增加一个常数不会改变单源最短路径问题的解决方案。

    *解决方案。* 假。

1.  为 EdgeWeightedDigraph.java 提供`toString()`的实现。

1.  使用第 1.4 节的内存成本模型确定 EdgeWeightedDigraph.java 用于表示具有*V*个顶点和*E*条边的图所使用的内存量。

    *解决方案。* 56 + 40V + 72E。MemoryOfEdgeWeightedDigraph.java 根据经验计算，假设没有缓存`Integer`值 - Java 通常缓存-128 到 127 的整数。

1.  从第 4.2 节中的`DirectedCycle`和`Topological`类中使用本节的`EdgeweightedDigraph`和`DirectedEdge`API，从而实现 EdgeWeightedDirectedCycle.java 和 Topological.java。

1.  假设我们通过为`EdgeWeightedGraph`中的每个`Edge`创建两个`DirectedEdge`对象（分别在每个方向上）来将`EdgeWeightedGraph`转换为`EdgeWeightedDigraph`，然后使用贝尔曼-福特算法。解释为什么这种方法会失败得惊人。

    *解决方案：* 即使带权图不包含负权重环，这可能会引入负成本循环。

1.  如果在贝尔曼-福特算法的同一遍历中允许一个顶点被多次入队会发生什么？

    *答案：* 算法的运行时间可能呈指数增长。例如，考虑所有边权重均为-1 的完全带权有向图会发生什么。

#### 创意问题

1.  **有向无环图中的最长路径。** 开发一个实现 AcyclicLP.java 的程序，可以解决带权有向无环图中的最长路径问题。

1.  **线上的所有对最短路径。** 给定一个加权线图（无向连通图，所有顶点的度为 2，除了两个端点的度为 1），设计一个算法，在线性时间内预处理图，并能在常数时间内返回任意两个顶点之间最短路径的距离。

    *部分解决方案。* 找到一个度为 1 的顶点 s，并运行广度优先（或深度优先）搜索以找到其余顶点出现的顺序。然后，计算从 s 到每个顶点 v 的最短路径长度，称为`dist[v]`。顶点 v 和 w 之间的最短路径是|`dist[v] - dist[w]`|。

1.  **单调最短路径。** 给定一个带权有向图，找到从 s 到每个其他顶点的*单调*最短路径。如果路径上每条边的权重要么严格递增要么严格递减，则路径是单调的。

    *部分解决方案：* 按升序松弛边并找到最佳路径；然后按降序松弛边并找到最佳路径。

1.  **Dijkstra 算法的懒惰实现。** 开发一个实现 LazyDijkstraSP.java 的 Dijkstra 算法的懒惰版本，该版本在文本中有描述。

1.  **Bellman-Ford 队列永不为空。** 证明如果在基于队列的 Bellman-Ford 算法中从源可达到一个负循环，那么队列永远不会为空。

    *解决方案*：考虑一个负循环，并假设对于循环 W 上的所有边，`distTo[w] <= distTo[v] + length(v, w)`。对循环上的所有边进行这个不等式求和意味着循环的长度是非负的。

1.  **Bellman-Ford 负循环检测。** 证明如果在通用 Bellman-Ford 算法的第 V 次遍历中有任何边被松弛，那么`edgeTo[]`数组中就有一个有向循环，并且任何这样的循环都是负循环。

    *解决方案*：待定。

#### 网络练习

1.  **最优子结构性质。** 证明从 v 到 w 的最短路径上的每个子路径也是两个端点之间的最短路径。

1.  **唯一最短路径树。** 假设从 s 到每个其他顶点都有唯一的最短路径。证明 SPT 是唯一的。

1.  **没有负循环。** 证明如果通用算法终止，则从 s 可达的地方没有负循环。提示：在终止时，从 s 可达的所有边都满足`distTo[w] <= distTo[v] + e.weight()`。将这个不等式对沿循环的所有边相加。

1.  **前驱图。** 真或假。在没有负循环的边权重有向图中执行 Bellman-Ford 时，遵循`edgeTo[]`数组总是会回到 s 的路径。对 Dijkstra 算法重复这个问题。

1.  **Yen 对 Bellman-Ford 的改进。** [[参考](http://11011110.livejournal.com/215330.html)] 将边分为两个 DAGs A 和 B：A 由从较低索引顶点到较高索引顶点的边组成；B 由从较高索引顶点到较低索引顶点的边组��。在 Bellman-Ford 的一个阶段中遍历所有边时，首先按顶点编号的升序（A 的拓扑顺序）遍历 A 中的边，然后按顶点编号的降序（B 的拓扑顺序）遍历 B 中的边。在遍历 A 中的边时，SPT 中从具有正确`distTo[]`值的顶点开始并且仅使用 A 中的边的任何路径都会得到正确的`distTo[]`值；B 也是如此。所需的遍历次数是路径上 A-B 交替的最大次数，最多为(V+1)/2。因此，所需的遍历次数最多为(V+1)/2，而不是 V。

1.  **替换路径。** 给定具有非负权重和源 s 以及汇 t 的边权重有向图，设计一个算法，找到从 s 到 t 的最短路径，该路径不使用每条边 e。你的算法的增长顺序应为 E V log V。

1.  **道路网络数据集。**

    +   来自[DIMACS 挑战](http://www.dis.uniroma1.it/~challenge9/download.shtml)。这里是[每个州的所有道路](http://www.dis.uniroma1.it/~challenge9/data/tiger/)。

    +   rome99.txt 是罗马的有向道路网络的大部分数据，来自[DIMACS 挑战](http://www.dis.uniroma1.it/~challenge9/download.shtml)。该图包含 3353 个顶点和 8870 条边。顶点对应道路交叉口，边对应道路或道路段。边的权重是以米为单位的距离。

    +   NYC.txt 是纽约市的无向道路网络。该图包含 264346 个顶点和 733846 条边。它是连通的，包含平行边，但没有自环。边的权重是旅行时间，且严格为正。

1.  **互联网路由。** [OSPF（开放最短路径优先）](http://en.wikipedia.org/wiki/Open_shortest_path_first)是互联网路由中广泛使用的协议，使用了迪杰斯特拉算法。[RIP（路由信息协议）](http://en.wikipedia.org/wiki/Routing_Information_Protocol)是另一种基于贝尔曼-福特算法的路由协议。

1.  **具有跳过一条边的最短路径。** 给定具有非负权重的边权重有向图，设计一个 E log V 算法，用于找到从 s 到 t 的最短路径，其中您可以将任意一条边的权重更改为 0。

    *解决方案。* 计算从 s 到每个其他顶点的最短路径；计算从每个顶点到 t 的最短路径。对于每条边 e = (v, w)，计算从 s 到 v 的最短路径长度和从 w 到 t 的最短路径长度的和。最小的这样的和提供了最短的这样的路径。

1.  **无向图中的最短路径。** 编写一个程序 DijkstraUndirectedSP.java，使用迪杰斯特拉算法解决非负权重的无向图中的单源最短路径问题。

1.  **弗洛伊德-沃舍尔算法。** FloydWarshall.java 实现了弗洛伊德-沃舍尔算法，用于全对最短路径问题。其时间复杂度与 V³ 成正比，空间复杂度与 V² 成正比。它使用了 AdjMatrixEdgeWeightedDigraph.java。

1.  **随机贝尔曼-福特算法。** [[参考资料](http://11011110.livejournal.com/215330.html)] 假设我们在 Yen 算法中均匀随机选择顶点顺序（其中 A 包含所有从排列中较低顶点到较高顶点的边）。证明预期的通过次数最多为(V+1)/3。

1.  **苏尔巴勒算法。** 给定具有非负边权重和两个特殊顶点 s 和 t 的有向图，找到从 s 到 t 的两条边不相交的路径，使得这两条路径的权重之和最小。

    *解决方案。* 这可以通过巧妙地应用迪杰斯特拉算法来实现，即[苏尔巴勒算法](https://en.wikipedia.org/wiki/Suurballe%27s_algorithm)。
