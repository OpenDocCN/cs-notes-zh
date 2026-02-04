# 最小生成树

> 原文：[`courses.physics.illinois.edu/cs225/sp2019/notes/mst/`](https://courses.physics.illinois.edu/cs225/sp2019/notes/mst/)

返回笔记 by Jenny Chen

## 定义

图 *G* 的 **生成树** 是包含 *G* 中所有节点的连通无环子图。加权图 *G* 的 **最小生成树** (MST) 是 *G* 的一个生成树，其边的权重和最小。

![图片](img/55afea685ffb9f237404e832d8affdea.png)

图 *G*

![图片](img/78ae44c96162cc305184b0f7808d06b2.png)

橙色高亮的子图是 *G* 的一个生成树

![图片](img/377099aae31f041ba445caa25c31c991.png)

紫色高亮的子图是加权 *G* 的最小生成树

## 寻找图的最小生成树

寻找图的最小生成树有多种方法。最直观且原始的方法是尝试 *G* 的所有可能的子图，找到那些是生成树的，然后找到权重最小的那个。这将需要指数时间。有一些算法可以更快地完成这个任务。

### Kruskal 算法

Kruskal 算法的高级思想是通过插入边来构建生成树。在插入边时有两个限制：

1.  为了保持树的最小权重，我们按从低权重到高权重的顺序插入边。

1.  为了保持树的无环性，我们添加的边不能引入环。

为了满足第一个条件，我们按权重升序排序边并按此顺序插入。为了满足第二个条件，我们必须跟踪已经属于同一个连通分量（小树）的节点。想象一下我们的算法进行到一半。由于我们纯粹根据权重选择边，可能会有多个不连通的小树。例如，我们的图可能看起来像这样。

![图片](img/db28128760cd6cca94b26518991518c3.png)

在这个阶段 `a`、`b` 和 `c` 形成一个小树，同样 `f` 和 `e` 也形成一个小树。插入边 `bc` 会引入一个环。

我们可以使用不相交集合来跟踪哪些节点属于哪个分量。当我们插入一条边时，我们将两个节点所属的两个集合合并。从概念上讲，这是在两个小树之间添加一条边并将它们合并成一个大树。如果我们即将插入的边连接的两个节点属于同一个集合，那么我们不能插入这条边，因为这会引入一个环。

![Kruskal 的演示图像 0](img/36e7e997a34329c018b6521bc311412a.png)![Kruskal 的演示图像 1](img/b6d47a5077c5d4d66f450ec6a94e3bab.png)![Kruskal 的演示图像 2](img/ca85742dc8e193db2abd1eb6d082fb97.png)![Kruskal 的演示图像 3](img/27ff1d5880ace26eec86918cbc1e7c71.png)![Kruskal 的演示图像 4](img/aa7c455ed276e3edbaaee4c2420f7c81.png)![Kruskal 的演示图像 5](img/209aa4972b0c38bee6ba8b058c615e9e.png)![Kruskal 的演示图像 6](img/f82520ab075b8e518bc658ae2051d43d.png)上一页 下一页

Kruskal 算法的逐步示例。

这是 Kruskal 算法的伪代码。

```c
1\. Sort the edges in increasing order of weights
   (You can do this with a heap, or simply sort them in an array)
2\. Initialize a separate disjoint set for each vertex
3\. for each edge uv in sorted order:
4\.   if u and v are in different sets:
5\.     add uv to solution
6\.     union the sets that u and v belong to 
```

使用堆或排序数组执行此算法的运行时间都是，这主要由边的排序决定。

### Prim 算法

另一个能够高效找到最小生成树的算法是 Prim 算法。Prim 算法的思想是通过添加“出边”中的最小权重边来扩展树。这些“出边”是连接我们树中的一端节点和不在我们树中的一端节点的边。

![](img/b6c967f71db2d993b2f51638b4e78bad.png)

在这个例子中，我们的当前树用深蓝色着色。浅蓝色边是“出边”。

在 Prim 算法的开始，我们在图中选择一个任意节点作为“起始树”。然后，对于我们树的“出边”，我们选择具有最小权重的边并将其添加到我们的树中。这一步通过添加一个节点来扩展我们的树。我们继续以这种方式添加边，直到我们的树包含图中的所有节点。

![Kruskal 的演示图像 1](img/1bc4fd4eb505404ead37bbf954143a70.png)![Kruskal 的演示图像 2](img/31999d006baf4c8e9f5bbc78bc3417f8.png)![Kruskal 的演示图像 3](img/62d7d0bd29182f1613c51e190e1b8dd7.png)![Kruskal 的演示图像 4](img/e3e50d73db727c0ea46523b8363faa11.png)![Kruskal 的演示图像 5](img/d1d7f89961b419326a896fe53079f7ce.png)![Kruskal 的演示图像 6](img/a1c0b24111386bd64d170a487dc5511e.png)![Kruskal 的演示图像 7](img/8d6eab9ea02344be298ee71e5872faec.png)上一页 下一页

Prim 算法的高级思想的一个逐步示例。深蓝色边和节点是当前树。浅蓝色边是我们树的“出边”。浅紫色边是树内的边。

但我们在代码中如何选择最小的“出边”呢？我们可以从不同的角度思考。我们不是从边中选择，而是可以从树的直接邻居节点中选择。我们可以给每个节点分配一个最小的权重，以将其添加到我们的树中，然后选择具有最小此类值的节点。对于不是我们直接邻居的节点，分配无穷大，这样它们就不会被考虑。我们可以使用堆这种数据结构来有效地选择具有最小权重的节点。

![](img/69d6db590c87c4ae93eab5f9afafd627.png)

在这个例子中，我们的当前树用深紫色着色。直接邻居用浅橙色着色。注意，节点`g`的权重是 6 而不是 9，因为 6 是`g`和我们的树之间的较小权重边。

下一个问题是我们如何随着算法的进行更新每个节点上的权重？注意，当我们向我们的树中添加一个新节点时，唯一会改变权重的节点是新添加节点的邻居。因此，每次我们添加一个节点，我们就更新这个节点的邻居的权重。

![克鲁斯卡尔演示图像 1](img/3ba7e9514ed314741bd744c50206c4dd.png)![克鲁斯卡尔演示图像 2](img/1c728a4f7968337d4da1a3c4c769ba10.png)![克鲁斯卡尔演示图像 3](img/ec82daafec10be6b309a0b1567e3a93f.png)![克鲁斯卡尔演示图像 4](img/49ab0da936018edb4809bd7fb8821360.png)![克鲁斯卡尔演示图像 5](img/f8f984adce5a23a8e93065264cc72289.png)![克鲁斯卡尔演示图像 6](img/eeb6bc56509c27e4ad1265a525f8c223.png)![克鲁斯卡尔演示图像 7](img/e606dbb757f486b87a3a1990e464e17d.png)上一页 下一页

一个以节点`c`开始的 Prim 算法逐步实现示例。

这里是 Prim 算法的伪代码。

```c
1\. Create a heap and insert all vertices into the it with the weight infinity.
2\. Choose an arbitrary node and set its weight to 0.
3\. while the heap is not empty:
4\.   remove the node with minimum weight from the heap, call it v
5\.   add the edge that connects v and its predecessor to the solution
6\.   for each neighbor u of v:
7\.     if the weight of edge uv is less than the weight of u:
8\.       update the weight of u to be weight of uv
9\.       update u's predecessor to v 
```

使用二叉堆（本课程所教授的那种）运行此算法的时间复杂度是。然而，如果我们使用[斐波那契堆](https://brilliant.org/wiki/fibonacci-heap/)，它可以以时间复杂度降低其元素的优先级。如果使用斐波那契堆，此算法的时间复杂度为。

#### 为什么这些算法有效？

尽管克鲁斯卡尔和 Prim 算法都直观合理，但它们在每一步都做出了最优的**局部**选择。这意味着它们在任何时候都没有将整个图作为一个整体来考虑。如果你对“为什么它们有效？”感到好奇，请选修 CS 374 课程以了解详情。
