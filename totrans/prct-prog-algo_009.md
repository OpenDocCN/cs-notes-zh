# 2\.   函数

> 原文：[`introcs.cs.princeton.edu/java/20functions`](https://introcs.cs.princeton.edu/java/20functions)

## 概述。

在本章中，我们考虑了一个对控制流具有深远影响的概念，就像条件语句和循环一样重要：*函数*，它允许我们在不同代码段之间来回传递控制。函数很重要，因为它们允许我们在程序中清晰地分离任务，并且提供了一个通用机制，使我们能够重用代码。

+   *2.1 Static Methods* 介绍了 Java 机制（*静态方法*）来实现函数。

+   *2.2 Libraries and Clients* 描述了如何将相关的静态方法分组到库中，以实现模块化编程。

+   *2.3 Recursion* 考虑了一个函数调用*自身*的概念。这种可能性被称为递归。

+   *2.4 Percolation* 提供了一个案例研究，使用蒙特卡洛模拟来研究一种名为渗透的自然模型。

## 本章中的 Java 程序。

下面是本章中的 Java 程序列表。点击程序名称以访问 Java 代码；点击参考号以获取简要描述；阅读教材以获取详细讨论。

> | **REF** | **PROGRAM** | **DESCRIPTION** |
> | --- | --- | --- |
> | 2.1.1 | Harmonic.java | 调和数（重新讨论） |
> | 2.1.2 | Gaussian.java | 高斯函数 |
> | 2.1.3 | Coupon.java | 收集优惠券（重新讨论） |
> | 2.1.4 | PlayThatTuneDeluxe.java | 演奏那首曲子（重新讨论） |
> | 2.2.1 | StdRandom.java | 随机数库 |
> | 2.2.2 | StdArrayIO.java | 数组 I/O 库 |
> | 2.2.3 | IFS.java | 迭代函数系统 |
> | 2.2.4 | StdStats.java | 数据分析库 |
> | 2.2.5 | StdStats.java | 数据分析库 |
> | 2.2.6 | Bernoulli.java | 伯努利试验 |
> | 2.3.1 | Euclid.java | 欧几里德算法 |
> | 2.3.2 | TowersOfHanoi.java | 汉诺塔 |
> | 2.3.3 | Beckett.java | 格雷码 |
> | 2.3.4 | Htree.java | 递归图形 |
> | 2.3.5 | Brownian.java | 布朗桥 |
> | 2.3.6 | LongestCommonSubsequence.java | 最长公共子序列 |
> | 2.4.1 | Percolation.java | 渗透脚手架 |
> | 2.4.2 | VerticalPercolation.java | 垂直渗透 |
> | 2.4.3 | PercolationVisualizer.java | 渗透可视化客户端 |
> | 2.4.4 | PercolationProbability.java | 渗透概率估计 |
> | 2.4.5 | Percolation.java | 渗透检测 |
> | 2.4.6 | PercolationPlot.java | 自适应绘图客户端 |
