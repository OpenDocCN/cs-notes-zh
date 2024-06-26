# 6.5   归约

> 原文：[`algs4.cs.princeton.edu/65reductions`](https://algs4.cs.princeton.edu/65reductions)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)

本章节正在建设中。

## 归约。

在计算机科学中，归约或模拟是一个强大的概念.... 将问题 X 转化为一个更简单的问题 Y 的问题解决框架，以便根据 Y 的解推导出原始问题 X 的解。

Eric Alander - “归约提供了一种抽象。如果 A 高效地归约到 B，且 B 高效地归约到 A，那么 A 和 B 在某种意义上是等价的：它们是观察同一问题的两种不同方式。我们不再有无限多的计算问题，而是留下了更少数量的等价问题类。没有什么能让计算社区为这一惊人的洞察做好准备，即人们真正想要解决的计算问题只有几个。根据资源限制将自然计算问题划分为有意义的组别。”

## 上界。

+   3-共线到排序。

+   凸包到排序（Graham 扫描）。

+   中位数到排序。

+   二分图匹配到最大流。BipartiteMatchingToMaxflow.java 通过将问题归约为最大流，在二分图中计算最大基数匹配。在最坏情况下，每次增广都会增加匹配的基数。Hopcroft-Karp 算法将运行时间改进为 E sqrt(V)。

+   LP 标准形式：标准形式线性规划是 { max cx : Ax <= b, x ≥ 0 }。展示如何将一般线性规划（带有 ≤、≥ 和 = 约束）归约为标准形式。

+   最大流到线性规划。

+   分配问题到线性规划。

+   PERT 到 有向无环图的拓扑排序。

+   USTCONN（无向图中的 s-t 连通性）到 STCONN（有向图中的无向 s-t 连通性）。

+   无向图上的最短路径到有向图上的最短路径。

+   欧几里得最小生成树到 Delauney 三角剖分。

+   LP 可行性归约为 LP。（使用二分搜索。需要限制有界 LP 的值。）

+   二人零和博弈到 LP。TwoPersonZeroSumGame.java

+   LP 可归约为二人零和博弈。（Bradley, Hax, 和 Magnanti 的练习 26）

## 下界。

+   元素唯一性到排序。

+   2D 最近点对问题到 2D 欧几里得最小生成树。

+   凸包到 Voronoi / Delauney 三角剖分。

+   3-SUM 到 3-共线。

+   练习：3-SUM 到 4-SUM。

+   练习：3-SUM 到 3-SUMplus

+   练习：3-共线到 3-共点。

+   3-SAT 到 独立集。

+   独立集到整数线性规划。

+   *元素唯一性。* 给定 N 个来自全序宇宙的元素 x[1], ..., x[n]，是否存在一对 i ≠ j，使得 x[i] = x[j]？在比较树模型和代数决策树模型中有 Theta(N log N) 的下界。通过排序可以轻松达到 O(N log N)。

    *解决方案 1*（比较树模型）：给定 N 个不同的值。让 ai 成为第 i 小的元素。在任何基于比较的算法中，我们必须比较 a[i] 和 a[i-1]；否则算法无法区分 a[i-1] < a[i] 和 a[i-1] = a[i] 的情况。考虑 N 个元素的两种不同排列。存在一个元素 a[i]，在第一个排列中 a[i-1] 在 a[i] 之前，但在第二个排列中 a[i-1] 在 a[i] 之后。由于每个基于比较的算法必须比较 a[i] 和 a[i-1]，算法在这两个排列上运行不同。因此，至少有 N! 个叶子节点。[参考链接](http://dimacs.rutgers.edu/~gkindler/ds02c/ex5_ans.ps)

    *解法 2*（比较树模型）：假设元素都是不同的且 a_1 < a_2 < ... < a_N。任何正确的元素唯一性算法必须对每个 i < N 比较 a_i 和 a_i+1。如果不这样做，那么如果我们将 a_i+1 更改为 a_i，算法将产生相同的输出（但这将从无重复更改为有重复的答案）。算法使用的比较集合形成一个 DAG。找到总顺序（线性时间）并得到排序顺序。因此，该算法可用于对不同元素进行排序，且排序下界适用。

    *备注*：这些论点适用于比较树模型的计算，但不适用于线性决策树或代数决策树模型的计算。这里有一个更一般的论点（由 Jeff Erickson 提供）：考虑所有可能输入的空间 R^n。正输入的集合有 n！个连通分量，每个排列一个。另一方面，可以到达线性决策树中任何叶子的输入子集是凸的，因此是连通的。因此，任何确定唯一性的线性决策树至少有 n！个叶子。线性决策树的结果是由 Dobkin 和 Lipton 在[On the complexity of computations under varying sets of primitives.](http://dx.doi.org/10.1016/0022-0000(79)90054-0)中得出的。代数决策树的结果是由 Ben-Or 在[Lower bounds for algebraic computation trees.](http://doi.acm.org/10.1145/800061.808735)中得出的。整数输入的特殊情况的结果更微妙：参见 Lubiw 和 Racs 的*整数元素唯一性问题的下界*。

+   *3-SUM*。

+   *3-SAT*。

## 线性规划。

将线性方程组推广到不等式。

[讲座幻灯片](http://www.cs.princeton.edu/~wayne/teaching/lp-simplex.pdf)

### 单纯形算法。

由 George Dantzig 于 1948 年发明。根据 Dongarra 和 Sullivan 的说法，单纯形算法是 20 世纪对科学和工程影响最大的十大算法之一。广义的高斯消元以处理不等式。程序 LinearProgramming.java 是一个基本实现。它解决{ max cx : Ax <= b, x >= 0 }假设 b >= 0。因此 x = 0 是一个基本可行解（我们不需要担心单纯形的第一阶段）。

*线性规划的基本定理*。形式为（P）的每个 LP 都具有以下三个属性：（i）如果它没有最优解，则它要么是不可行的，要么是无界的（ii）如果它有一个可行解，则它有一个基本可行解（iii）如果它有一个最优解，则它有一个基本最优解。

*强对偶定理*。形式为（P）的每个 LP 都有一个对偶（D）{ min by : y A >= c : y >= 0 }。p1 + p2 + ... + pM = 1 -> x1 + x2 + ... + xm = 1/V。

如果（P）有���且可行，则（D）也有界且可行。此外，它们具有相同的最优值。单纯形算法同时解决这两个问题。

*显著特性*。实践中，单纯形算法通常在最多 2(m+n)个主元中终止。n = 总变量（原始+松弛），m = 方程。

*陷阱*。退化，循环。

## 分配问题。

形式化为 LP。依赖于 *Birchoff-von Neumann 定理*：分配问题 LP 的所有极端点都是 {0, 1}。AssignmentProblemToLP.java 将分配问题（最大权重完美匹配）简化为线性规划。EasyAssignmentProblemToLP.java 将所有内容放在主函数中，不提取对偶解。Hungarian.java 实现了匈牙利算法；在最坏情况下，运行时间的增长数量级为 N⁴。 --> AssignmentProblem.java 实现了连续最短路径算法；在最坏情况下，运行时间的增长数量级为 N³ log N。AssignmentProblemDense.java 实现了连续最短路径算法；在最坏情况下，运行时间的增长数量级为 N³。

### 二人零和博弈。

简化为 LP。可以假设收益矩阵严格为正（对每个条目添加一个常数会使游戏的价值增加 M，但不会改变解）。（P）min { x1 + ... + xm, : x >= 0, M^t x >= 1} 和（D）max { y1 + ... + yn, : y >= 0, My <= 1}。将解向量 x* 和 y* 标准化，以获得行玩家（最小化）和列玩家（最大化）的最佳策略；标准化常数是游戏的价值。

技巧。替换变量：xi = pi / V；最大化 V -> 最小化 1/V；[博弈论，第 6-7 页](http://www.scribd.com/doc/30906572/Game-THeory)

程序 ZeroSumGame.java 实现了这种方法。

注意：通过适当的变量更改，任何 LP 都可以转化为这种形式。

**极小极大定理。**（冯·诺伊曼）。对于每个有限的二人零和博弈，存在一个值 V 和每个玩家的混合策略，使得（i）给定行玩家的策略，列玩家的最佳可能收益是 V，以及（ii）给定列玩家的策略，行玩家的最佳可能收益是 -V。

## 线性规划求解器。

+   LinearProgramming.java 是单纯形算法的简化版本。假设 b >= 0，因此 x = 0 是一个起始的基本可行解。TwoPhaseSimplex.java 是两阶段单纯形算法的简化版本，它消除了假设 b >= 0。

+   [OR-Objects](http://opsresearch.com/OR-Objects/) 包含一个 Java 线性规划求解器。LPDemo.java 演示了如何使用 or124.jar 解决线性规划问题。

+   [QSopt](http://www2.isye.gatech.edu/~wcook/qsopt/software/java.htm) 是由大卫·阿普尔盖特、威廉·库克、Sanjeeb Dash 和 Monika Mevenkamp 创造的 Java 线性规划求解器。可以免费用于研究或教育目的。QSoptSolver.java 解决了 LP 格式的线性规划问题，例如 beer.lp。

+   [Matlab](http://www.mathworks.com/products/matlab/) 包含优化工具箱中的线性规划求解器。

    ```java
    [wayne:tombstone] ~> matlab
                                          < M A T L A B (R) >
                                Copyright 1984-2009 The MathWorks, Inc.
                              Version 7.9.0.529 (R2009b) 64-bit (glnxa64)
                                            August 12, 2009
    >> A = [5 15; 4 4; 35 20];
    >> b = [480; 160; 1190];
    >> c = [13; 23];

    >> lb = [0; 0];
    >> ub = [inf; inf];
    >> x = linprog(-c, A, b, [], [], lb, ub)
    x =
        12.0000
        28.0000

    ```

+   [CPLEX](http://www-01.ibm.com/software/integration/optimization/cplex-optimizer/) 是用于线性规划、混合整数规划和二次规划的高性能数学规划求解器。支持与 C、C++、Java、Python、Matlab 和 Microsoft Excel 的接口。也可通过建模系统（包括 AIMMS、AMPL、GAMS 和 MPL）访问。

+   [AMPL](http://www.ampl.com/) 是数学规划的建模语言。文件 beer.mod 和 beer.dat 指定了酿酒厂问题的模型和数据。

    ```java
    [wayne:tombstone] ~> ampl
    ILOG AMPL 9.100
    AMPL Version 20021038 (SunOS 5.8)

    ampl: model beer.mod;

    ampl: data beer.dat;

    ampl: solve;
    ILOG CPLEX 9.100 
    CPLEX 9.1.0: optimal solution; objective 800
    2 dual simplex iterations (1 in phase I)

    ampl: display x;
    x [*] :=  ale 12  beer 28  ;

    ampl: display constraints.dual;
    x [*] :=  corn 1  hops 2  malt 0  ;

    ```

+   Microsoft Excel 在 Windows 上有一个基本的求解器插件，但在 Mac 上不再可用。

#### 问答

**Q.** 无向最短路径与带负权重的有向最短路径？

**A.** 需要更聪明的简化来避免负循环（通过非二部匹配）。

#### 练习

1.  *最大公约数和最小公倍数.* 将最小公倍数简化为最大公约数。

1.  *表 k-和.* 给定一个 k 行 N 列的整数表，是否有 k 个数相加为 0，每个数来自 k 行中的一个？

1.  **硬币不同。** 给定 N 枚硬币和一个天平，确定这些硬币是否都有不同的重量。证明解决该问题的任何算法的复杂度至少为 N log N。*提示*：你可以使用这样一个事实，即给定 N 个实数，元素的不同性在线性决策树模型中至少需要 N log N 次比较（在这个模型中，你可以对 N 个元素的任意线性组合进行比较，例如，x1 + 2x2 < x3）。

1.  **集合相等。** 给定两个集合 S 和 T，S 是否等于 T？给出一个 O(N log N)的算法和一个匹配的下界。

1.  **集合子集。** 给定两个集合 S 和 T，S 是否是 T 的子集？给出一个 O(N log N)的算法和一个匹配的下界。

1.  **集合不相交。** 给定两个集合 S 和 T，S 与 T 的交集是否为空集？给出一个 O(N log N)的算法和一个匹配的下界。（由于 S 和 T 是集合，因此两者中没有重复元素。）

    *解决方案。* 要获得 O(N log N)的上界，对 S 和 T 中的元素的并集进行排序，并检查重复项。

1.  **集合不相交。** 给定两个按升序排列的集合 S 和 T，S 与 T 的交集是否为空集？证明一个 Omega(N log N)的下界或给出一个 O(N)的算法。

1.  **合并两个列表的下界。** 展示任何基于比较的合并两个大小为 N 的列表的算法在最坏情况下至少需要 2N-1 次比较。*解决方案*：即使所有元素都不同，下界也成立。如果第 i 个和第(i+1)个最小的元素在不同的列表中，则它们必须进行比较。

1.  **二分查找的下界。** 需要 log(N+1)次比较。*解决方案*：即使所有元素都不同，下界也成立……

1.  **欧几里得 TSP 和 MST 下界。** 对于欧几里得 TSP 或欧几里得 MST，给出一个 Omega(N log N)的下界（需要代数决策树来理解，因为你希望允许一个合理的算法来计算距离）。*解决方案*：在一条线上选择 N 个点。最优路径必须按升序访问这些点。

1.  **模式的下界。** 模式的 Theta(N log N)下界。*解决方案*：可以通过找到模式并检查是否超过一个来解决元素不同性问题。

1.  **最接近对的下界。** 最接近对的 Theta(N log N)下界。*解决方案*：如果有一个次线性对数算法，可以通过找到最接近对并检查它们是否相等来在次线性对数时间内解决元素不同性问题。

1.  **最小和次小元素。** 描述如何使用最多 N + log N 次比较找到最小和次小元素。*解决方案*：将元素分成一对一对，并比较每对中的两个元素。使用每对中的 N/2 个获胜者进行递归。经过 N-1 次比较后，我们得到最小元素。请注意，每个元素最多与 log N 个其他元素进行比较。特别是，最小元素最多与 log N 个其他元素进行比较，其中一个必须是次小元素。如果你跟踪所有的比较，你可以记住涉及最小元素的 log N 次比较，并进行比较。

1.  **计数逆序对。** 证明 Theta(N log N)的下界。这是一个尚未解决的研究问题。

1.  **螺母和螺栓。** 证明快速排序部分的螺母和螺栓问题的 Theta(N log N)下界。[已知匹配的最坏情况上界为 O(N log N)，但这是非常复杂的。]

1.  **存在符号表。** 假设你有一个支持插入和存在操作的基于比较的算法，每次操作都只需要 O(1)次比较。解释为什么在这种计算模型中这是不可能的。*解决方案*：为了在 O(N)时间内解决元素不同性问题，对于每个 N 个元素，检查它是否已经在数据结构中（如果是，则这是一个重复项）；如果不是，则插入它。

1.  使用整数规划模型一个形如 x ≤ y 的约束（Ax = b，x >= 0，x 为整数）。

1.  使用整数规划模型一个形如 x = {0 或 1}的约束。

1.  使用整数规划模型一个形如 x = {1 或 2 或 4}的约束。

1.  **Tait 着色。** 使用 IP 模拟 3 边着色立方图。

1.  为患者分配器官捐赠者。

1.  **二部顶点覆盖。** 减少到最大流。

1.  **传递闭包和传递闭包。** 将[传递闭包](http://en.wikipedia.org/wiki/Transitive_reduction)减少到传递闭包，反之亦然（当运行时间仅作为顶点数 V 的函数时）。也可减少到布尔矩阵乘法。

1.  **3SUM'。** 给定三组整数 A、B 和 C，总大小为 n，是否存在 A 中的 a，B 中的 b 和 C 中的 c，使得 a + b = c？证明 3SUM 线性时间减少到 3SUM'，反之亦然。

    *解决方案。* 要显示 3SUM 减少到 3SUM'，设置 A = S，B = S，C = -S。

    要显示 3SUM'减少到 3SUM，假设所有整数都是正数（如果不是，则将 k 添加到 A 和 B 中的每个元素，将 2K 添加到 C 中的每个元素）。设置 m = 2 max(A, B, C)。对于 A 中的每个元素 a，在 S 中放置 a + m。对于 B 中的每个元素 b，在 S 中放置 b。对于 C 中的每个元素，在 S 中放置-c -m。

1.  **不等式满足等式。** 给定线性不等式系统*A* *x* ≤ *b*，设计一个线性规划来确定在任何可行解*x*中哪些不等式必须满足等式。

1.  **等式约束。** 使用两个<=约束模拟线性规划等式约束。

1.  **无限制变量。** 使用两个非负变量 y 和 z 来模拟线性规划无限制变量 x。

1.  **无界 LP。** 如果（P）是无界的，则存在一个矢量 d >= 0，使得 Ad <= 0 且 cd > 0。首先解释为什么如果存在这样的矢量 d，则问题是无界的。接下来，修改单纯形算法，在 LP 无界时报告这样的矢量。*答案*：根据假设 b >= 0 且 x = 0 是可行的。因此，对于任何正常数α，αd 都是可行的，并且具有目标值αcd。通过检查最小比率规则是否失败，可以识别矢量 d。在这种情况下，列 q 中的条目为非正（Ad <= 0），并且目标函数系数为正（cd > 0）。

1.  **减少成本。** 修改单纯形算法以报告减少的成本（影子价格）。给出经济解释。

1.  **丹齐格的最陡边规则。** 修改单纯形算法，使其始终选择最正的目标函数系数。

1.  **循环。** 给出一个导致单纯形算法（使用最陡边规则）循环的病态线性规划输入。

1.  **瓶颈分配问题。** 给定 N 个男人和 N 个女人。每个人有 M 个属性。每个人指定异性的一组理想属性。找到一个完美匹配，其中最不幸的人与指定属性最少的伴侣匹配。将此问题减少到分配问题。

    *解决方案。* 创建一个边权重图，其中边的权重是两个人中满足的可取属性的最小数量。目标是最大化分配中最小权重边的权重。解决此问题的一种方法是使用二分查找（消除所有权重小于给定阈值的边）并解决结果的二部完美匹配问题。

1.  **中国邮递员问题。** 给定一个强连通的有向图 G，找到一个最短长度的有向循环，该循环至少经过每条边一次。（事实证明，最佳循环将最多访问每条边两次。）如果每个顶点都是*平衡*的，则图是欧拉图：其度等于其出度。将不平衡的顶点分为两组：L = 出度小于入度的顶点，R = 出度大于入度的顶点。通过在 L 中的一个顶点到 R 中的一个顶点添加一个有向路径，我们改善了平衡性。在 (L, R) 上形成一个加权二部图，其中从 v 到 w 的边的权重是 G 中从 v 到 w 的最短路径的长度。找到一个最小权重匹配，并将这些边添加到 G 中使其成为欧拉图。然后，找到一个循环。这被称为 Edmonds-Johnson（1973）算法。（类似的算法适用于无向图，但需要在非二部图中找到一个最小权重完美匹配。）
