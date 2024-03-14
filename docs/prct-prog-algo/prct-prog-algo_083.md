# 1\.   基础知识

> 原文：[`algs4.cs.princeton.edu/10fundamentals`](https://algs4.cs.princeton.edu/10fundamentals)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)


## 概述。

本书的目标是研究各种重要和有用的*算法*——解决问题的方法适合计算机实现。算法与*数据结构*——组织数据的方案密切相关。本章介绍了我们研究算法和数据结构所需的基本工具。

+   1.1 编程模型 介绍了我们的*基本编程模型*。我们所有的程序都是使用 Java 编程语言的一个小子集以及一些用于输入和输出的自定义库来实现的。

+   1.2 数据抽象 强调*数据抽象*，我们定义*抽象数据类型*（ADTs）。我们指定一个*应用程序编程接口*（API），然后使用 Java 类机制开发一个实现，供客户端代码使用。

+   1.3 背包、队列和栈 考虑了三种基本的 ADT：*背包*、*队列*和*栈*。我们使用调整大小数组和链表描述 API 和实现。

+   1.4 算法分析 描述了我们分析算法性能的方法。我们方法的基础是*科学方法*：我们提出关于性能的假设，创建数学模型，并进行实验来测试它们。

+   1.5 案例研究：并查集 是一个案例研究，我们考虑解决一个*连接性*问题的解决方案，该问题使用实现经典*并查集*ADT 的算法和数据结构。

## 本章中的 Java 程序。

下面是本章中的 Java 程序列表。点击程序名称以访问 Java 代码；点击参考号以获取简要描述；阅读教材以获取详细讨论。

> | REF | PROGRAM | 描述 / JAVADOC |
> | --- | --- | --- |
> | - | BinarySearch.java | 二分查找 |
> | - | RandomSeq.java | 给定范围内的随机数 |
> | - | Average.java | 一系列数字的平均值 |
> | - | Cat.java | 连接文件 |
> | - | Knuth.java | Knuth 洗牌 |
> | - | Counter.java | 计数器 |
> | - | StaticSETofInts.java | 整数集合 |
> | - | Allowlist.java | 白名单客户端 |
> | - | Vector.java | 欧几里得向量 |
> | - | Date.java | 日期 |
> | - | Transaction.java | 交易 |
> | - | Point2D.java | 点 |
> | - | RectHV.java | 轴对齐矩形 |
> | - | Interval1D.java | 1d 区间 |
> | - | Interval2D.java | 2d 区间 |
> | - | Accumulator.java | 运行平均值和标准差 |
> | 1.1 | ResizingArrayStack.java | LIFO 栈（调整大小数组） |
> | 1.2 | LinkedStack.java | 后进先出栈（链表） |
> | - | Stack.java | 后进先出栈 |
> | - | ResizingArrayQueue.java | 先进先出队列（调整大小数组） |
> | 1.3 | LinkedQueue.java | 先进先出队列（链表） |
> | - | Queue.java | 先进先出队列 |
> | - | ResizingArrayBag.java | 多重集（调整大小数组） |
> | 1.4 | LinkedBag.java | 多重集（链表） |
> | - | Bag.java | 多重集 |
> | - | Stopwatch.java | 计时器（墙上时间） |
> | - | StopwatchCPU.java | 计时器（CPU 时间） |
> | - | LinearRegression.java | 简单线性回归 |
> | - | ThreeSum.java | 暴力三数求和 |
> | - | ThreeSumFast.java | 更快的三数求和 |
> | - | DoublingTest.java | 倍增测试 |
> | - | DoublingRatio.java | 倍增比率 |
> | - | QuickFindUF.java | 快速查找 |
> | - | QuickUnionUF.java | 快速联合 |
> | 1.5 | WeightedQuickUnionUF.java | 加权快速联合 |
> | - | UF.java | 按秩合并并路径减半 |
