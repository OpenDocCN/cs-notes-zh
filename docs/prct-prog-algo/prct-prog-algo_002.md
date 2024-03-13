# 1\.   编程元素

> 原文：[`introcs.cs.princeton.edu/java/10elements`](https://introcs.cs.princeton.edu/java/10elements)

## 概述。

本章中我们的目标是说服您，编写计算机程序比编写段落或文章等文本要容易。在本章中，我们将带您了解这些基本知识，帮助您开始使用 Java 进行编程，并学习各种有趣的程序。

+   *1.1 编程元素* 指导您如何在系统上创建、编译和执行 Java 程序。

+   *1.2 数据的内置类型* 描述了 Java 用于操作字符串、整数、实数和布尔值的内置数据类型。

+   *1.3 条件和循环* 介绍了 Java 的控制流结构，包括`if-else`语句、`while`循环和`for`循环。

+   *1.4 数组* 考虑了一种称为数组的数据结构，用于组织大量数据。

+   *1.5 输入和输出* 扩展了输入和输出抽象（命令行参数和标准输出）的集合，包括标准输入、标准绘图和标准音频。

+   *1.6 随机网络冲浪者* 提供了一个案例研究，模拟了使用马尔可夫链的网络冲浪者的行为。

## 本章中的 Java 程序。

下面是本章中的 Java 程序列表。单击程序名称以访问 Java 代码；单击参考编号以获取简要描述；阅读教材以获取详细讨论。

> | **参考** | **程序** | **描述** |
> | --- | --- | --- |
> | 1.1.1 | HelloWorld.java | Hello, World |
> | 1.1.2 | UseArgument.java | 使用命令行参数 |
> | 1.2.1 | Ruler.java | 字符串连接示例 |
> | 1.2.2 | IntOps.java | 整数乘法和除法 |
> | 1.2.3 | Quadratic.java | 二次方程公式 |
> | 1.2.4 | LeapYear.java | 闰年 |
> | 1.2.5 | RandomInt.java | 强制转换以获得随机整数 |
> | 1.3.1 | Flip.java | 抛硬币 |
> | 1.3.2 | TenHellos.java | 你的第一个 while 循环 |
> | 1.3.3 | PowersOfTwo.java | 计算 2 的幂 |
> | 1.3.4 | DivisorPattern.java | 你的第一个嵌套循环 |
> | 1.3.5 | HarmonicNumber.java | 调和数 |
> | 1.3.6 | Sqrt.java | 牛顿法 |
> | 1.3.7 | Binary.java | 转换为二进制 |
> | 1.3.8 | Gambler.java | 赌徒破产模拟 |
> | 1.3.9 | Factors.java | 整数因子分解 |
> | 1.4.1 | Sample.java | 无重复抽样 |
> | 1.4.2 | CouponCollector.java | 收集优惠券模拟 |
> | 1.4.3 | PrimeSieve.java | 埃拉托斯特尼筛法 |
> | 1.4.4 | SelfAvoidingWalk.java | 避免自我随机漫步 |
> | 1.5.1 | RandomSeq.java | 生成随机序列 |
> | 1.5.2 | TwentyQuestions.java | 交互式用户输入 |
> | 1.5.3 | Average.java | 对一系列数字进行平均 |
> | 1.5.4 | RangeFilter.java | 一个简单的过滤器 |
> | 1.5.5 | PlotFilter.java | 标准输入到绘图过滤器 |
> | 1.5.6 | BouncingBall.java | 弹跳球 |
> | 1.5.7 | PlayThatTune.java | 数字信号处理 |
> | 1.6.1 | Transition.java | 计算转移矩阵 |
> | 1.6.2 | RandomSurfer.java | 模拟随机冲浪者 |
> | 1.6.3 | Markov.java | 混合马尔可夫链 |
