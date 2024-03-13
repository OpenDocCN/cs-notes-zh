# 4\.   算法和数据结构

> 原文：[`introcs.cs.princeton.edu/java/40algorithms`](https://introcs.cs.princeton.edu/java/40algorithms)

## 概述。

在本章中，我们描述并实现了当今计算机上使用的一些最重要的算法和数据结构。（对于更深入的讨论，我们推荐配套教材[《算法，第 4 版》](https://algs4.cs.princeton.edu)。）我们首先考虑了一个衡量和分析程序效率的强大框架。这使我们能够比较算法并准确预测性能。接下来，我们考虑了几种用于经典排序问题的新颖算法。然后，我们构建了最重要的高级数据结构，包括栈、队列和符号表。

+   *4.1 性能*概述了一种科学方法和强大理论，用于理解我们编写的程序的性能和资源消耗。

+   *4.2 排序和搜索*描述了两种经典算法——归并排序和二分查找——以及它们的效率在多个应用中起关键作用的情况。

+   *4.3 栈和队列*介绍了两种密切相关的数据结构，用于操作任意大量的数据集合。

+   *4.4 符号表*考虑了一种存储信息的基本数据结构，称为符号表，以及两种高效的实现方式——哈希表和二叉搜索树。

+   *4.5 小世界现象*提供了一个案例研究，探讨了小世界现象——我们都通过短链条的熟人联系相互联系。

## 本章中的 Java 程序。

以下是本章中的 Java 程序列表。点击程序名称以访问 Java 代码；点击参考号以获取简要描述；阅读教材以获取详细讨论。

> | **参考** | **程序** | **描述** |
> | --- | --- | --- |
> | 4.1.1 | ThreeSum.java | 3 数之和问题 |
> | 4.1.2 | DoublingTest.java | 验证加倍假设 |
> | 4.2.1 | Questions.java | 二分查找（20 个问题） |
> | 4.2.2 | Gaussian.java | 二分查找 |
> | 4.2.3 | BinarySearch.java | 二分查找（在排序数组中） |
> | 4.2.4 | Insertion.java | 插入排序 |
> | 4.2.5 | InsertionTest.java | 插入排序的加倍测试 |
> | 4.2.6 | Merge.java | 归并排序 |
> | 4.2.7 | FrequencyCount.java | 频率统计 |
> | 4.3.1 | ArrayStackOfStrings.java | 字符串栈（数组） |
> | 4.3.2 | LinkedStackOfStrings.java | 字符串栈（链表） |
> | 4.3.3 | ResizingArrayStackOfStrings.java | 字符串栈（调整大小数组） |
> | 4.3.4 | Stack.java | 通用栈 |
> | 4.3.5 | Evaluate.java | 表达式求值 |
> | 4.3.6 | Queue.java | 通用队列 |
> | 4.3.7 | MM1Queue.java | M/M/1 队列模拟 |
> | 4.3.8 | LoadBalance.java | 负载均衡模拟 |
> | 4.4.1 | Lookup.java | 字典查找 |
> | 4.4.2 | Index.java | 索引 |
> | 4.4.3 | HashST.java | 哈希表 |
> | 4.4.4 | BST.java | 二叉搜索树 |
> | 4.4.5 | DeDup.java | 去重过滤器 |
> | 4.5.1 | Graph.java | 图数据类型 |
> | 4.5.2 | IndexGraph.java | 使用图来反转索引 |
> | 4.5.3 | PathFinder.java | 最短路径客户端 |
> | 4.5.4 | PathFinder.java | 最短路径实现 |
> | 4.5.5 | SmallWorld.java | 小世界测试 |
> | 4.5.6 | Performer.java | 表演者-表演者图 |
