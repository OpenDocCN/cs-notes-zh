# 2\.   排序

> 原文：[`algs4.cs.princeton.edu/20sorting`](https://algs4.cs.princeton.edu/20sorting)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)


## 概述。

排序是重新排列一系列对象的过程，使它们按照某种逻辑顺序排列。排序在商业数据处理和现代科学计算中起着重要作用。在交易处理、组合优化、天体物理学、分子动力学、语言学、基因组学、天气预测等领域都有广泛的应用。

在本章中，我们考虑了几种经典的排序方法以及一个称为优先队列的基本数据类型的高效实现。我们讨论了比较排序算法的理论基础，并以对排序和优先队列算法的应用进行调查来结束本章。

+   *2.1 Elementary Sorts*介绍了选择排序、插入排序和希尔排序。

+   *2.2 Mergesort*描述了归并排序，这是一种能够保证在线性对数时间内运行的排序算法。

+   *2.3 Quicksort*描述了快速排序，它比其他任何排序算法都被广泛使用。

+   *2.4 Priority Queues*介绍了优先队列数据类型以及使用二叉堆的高效实现。它还介绍了堆排序。

+   *2.5 Applications*描述了排序的应用，包括使用替代排序、选择、系统排序和稳定性。

## 本章的 Java 程序。

以下是本章中的 Java 程序列表。点击程序名称以访问 Java 代码；点击参考号以获取简要描述；阅读教材以获取全面讨论。

> | REF | PROGRAM | DESCRIPTION / JAVADOC |
> | --- | --- | --- |
> | 2.1 | Insertion.java | 插入排序 |
> | - | InsertionX.java | 插入排序（优化版） |
> | - | BinaryInsertion.java | 二分插入排序 |
> | 2.2 | Selection.java | 选择排序 |
> | 2.3 | Shell.java | 希尔排序 |
> | 2.4 | Merge.java | 自顶向下的归并排序 |
> | - | MergeBU.java | 自底向上的归并排序 |
> | - | MergeX.java | 优化的归并排序 |
> | - | Inversions.java | 逆序对数量 |
> | 2.5 | Quick.java | 快速排序 |
> | - | Quick3way.java | 三向切分的快速排序 |
> | - | QuickX.java | 优化的双向快速排序 |
> | - | QuickBentleyMcIlroy.java | 优化的三向快速排序 |
> | - | TopM.java | 优先队列客户端 |
> | 2.6 | MaxPQ.java | 最大堆优先队列 |
> | - | MinPQ.java | 最小堆优先队列 |
> | - | IndexMinPQ.java | 索引最小堆优先队列 |
> | - | IndexMaxPQ.java | 索引最大堆优先队列 |
> | - | Multiway.java | 多路归并 |
> | 2.7 | Heap.java | 堆排序 |

## 排序演示。

以下是一些有趣的排序演示。

+   [排序算法动画](http://www.sorting-algorithms.com)，作者 David Martin。

+   [排序算法的声音和可视化](http://panthema.net/2013/sound-of-sorting/)，作者 Timo Bingmann。

+   [快速排序的声音](https://www.youtube.com/watch?v=m1PS8IR6Td0)。

+   机器人可视化展示[快速排序](https://www.youtube.com/watch?v=aXXWXz5rF64)和[归并排序](https://www.youtube.com/watch?v=es2T6KY45cA)。

+   [Carlo Zapponi 的排序可视化](http://sorting.at)，使用逆序计数作为进度的衡量标准。
