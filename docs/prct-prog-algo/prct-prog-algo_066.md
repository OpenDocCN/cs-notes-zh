# 2\. 函数和模块

> 原文：[`introcs.cs.princeton.edu/python/20functions`](https://introcs.cs.princeton.edu/python/20functions)

在本章中，我们考虑了一个对控制流程具有深远影响的概念，就像条件语句和循环一样重要：*函数*，它允许我们在不同代码段之间传递控制。函数很重要，因为它们允许我们在程序中清晰地分离任务，并且因为它们提供了一个通用机制，使我们能够重用代码。

+   *2.1 定义函数* 描述了如何在 Python 中创建自己的函数。

+   *2.2 模块和客户端* 描述了如何将相关函数分组到模块中以实现模块化编程。

+   *2.3 递归* 考虑了一个函数调用*自身*的概念。这种可能性被称为递归。

+   *2.4 案例研究：渗透* 提供了一个案例研究，使用蒙特卡洛模拟来研究一种名为渗透的自然模型。

## 本章中的 Python 程序

以下是本章中使用的 Python 程序和数据文件列表。

> | **参考** | **程序** | **描述** | **数据** |
> | --- | --- | --- | --- |
> | 2.1.1 | harmonicf.py | 调和数（重新讨论） | – |
> | 2.1.2 | gauss.py | 高斯函数 | – |
> | 2.1.3 | coupon.py | 优惠券收集器（重新讨论） | – |
> | 2.1.4 | playthattunedeluxe.py | 演奏那首曲子（重新讨论） | elise.txt  ascale.txt  stairwaytoheaven.txt  entertainer.txt  firstcut.txt  freebird.txt  looney.txt   |
> | 2.2.1 | gaussian.py | 高斯函数模块 | – |
> | 2.2.2 | gaussiantable.py | 示例高斯客户端 | – |
> | 2.2.3 | sierpinski.py | 谢尔宾斯基三角形 | – |
> | 2.2.4 | ifs.py | 迭代函数系统 | sierpinski.txt  barnsley.txt  coral.txt  culcita.txt  cyclosorus.txt  dragon.txt  fishbone.txt  floor.txt  koch.txt  spiral.txt  swirl.txt  tree.txt  zigzag.txt   |
> | 2.2.5 | bernoulli.py | 伯努利试验 | – |
> | 2.3.1 | euclid.py | 欧几里德算法 | – |
> | 2.3.2 | towersofhanoi.py | 汉诺塔 | – |
> | 2.3.3 | beckett.py | 格雷码 | – |
> | 2.3.4 | htree.py | 递归图形 | – |
> | 2.3.5 | brownian.py | 布朗桥 | – |
> | 2.4.1 | percolationv.py | 垂直渗流检测 | test5.txt  test8.txt   |
> | 2.4.2 | percolationio.py | 渗流支持函数 | – |
> | 2.4.3 | visualizev.py | 垂直渗流可视化客户端 | – |
> | 2.4.4 | estimatev.py | 垂直渗流概率估计 | – |
> | 2.4.5 | percolation.py | 渗流检测 | test5.txt  test8.txt   |
> | 2.4.6 | visualize.py | 渗流可视化客户端 | – |
> | 2.4.7 | estimate.py | 渗流概率估计 | – |
