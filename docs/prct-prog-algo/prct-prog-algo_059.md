# 1\. 编程元素

> 原文：[`introcs.cs.princeton.edu/python/10elements`](https://introcs.cs.princeton.edu/python/10elements)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)


本章的目标是说服您，编写计算机程序比写段文字（如段落或文章）更容易。写散文很困难：我们在学校花了很多年学习如何做到这一点。相比之下，只需几个基本构件就足以让我们进入一个世界，在这个世界中，我们可以利用计算机帮助我们解决各种各样的迷人问题，否则这些问题将无法解决。在本章中，我们将带领您了解这些基本构件，让您开始使用 Python 进行编程，并研究各种有趣的程序。

+   *1.1 你的第一个程序* 指导您如何在系统上编写和执行 Python 程序。

+   *1.2 内置数据类型* 描述了 Python 的内置数据类型，用于操作字符串、整数、实数和布尔值。

+   *1.3 条件和循环* 介绍了 Python 中用于控制流的结构，包括`if`、`while`和`for`语句。

+   *1.4 数组* 讨论了一种称为数组的数据结构，用于组织大量数据。

+   *1.5 输入和输出* 将输入和输出抽象的范围（从命令行输入和标准输出）扩展到包括标准输入、标准绘图和标准音频。

+   *1.6 案例研究：随机网页浏览者* 展示了一个案例研究，模拟了使用马尔可夫链的网页浏览���的行为。

## 本章中的 Python 程序

以下是本章中使用的 Python 程序和数据文件列表。

> | **参考** | **程序** | **描述** | **数据** |
> | --- | --- | --- | --- |
> | 1.1.1 | helloworld.py | 你好，世界 | – |
> | 1.1.2 | useargument.py | 使用命令行参数 | – |
> | 1.2.1 | ruler.py | 字符串连接示例 | – |
> | 1.2.2 | intops.py | 整数运算符 | – |
> | 1.2.3 | floatops.py | 浮点数运算符 | – |
> | 1.2.4 | quadratic.py | 二次方程 | – |
> | 1.2.5 | leapyear.py | 闰年 | – |
> | 1.3.1 | flip.py | 抛硬币 | – |
> | 1.3.2 | tenhellos.py | 你的第一个循环 | – |
> | 1.3.3 | powersoftwo.py | 计算二的幂 | – |
> | 1.3.4 | divisorpattern.py | 你的第一个嵌套循环 | – |
> | 1.3.5 | harmonic.py | 调和数 | – |
> | 1.3.6 | sqrt.py | 牛顿法 | – |
> | 1.3.7 | binary.py | 转换为二进制 | – |
> | 1.3.8 | gambler.py | 赌徒破产模拟 | – |
> | 1.3.9 | factors.py | 整数因子分解 | – |
> | 1.4.1 | sample.py | 无重复抽样 | – |
> | 1.4.2 | couponcollector.py | 优惠券收集器模拟 | – |
> | 1.4.3 | primesieve.py | 埃拉托斯特尼筛法 | – |
> | 1.4.4 | selfavoid.py | 避免自我随机漫步 | – |
> | 1.5.1 | randomseq.py | 生成随机序列 | – |
> | 1.5.2 | twentyquestions.py | 交互式用户输入 | – |
> | 1.5.3 | average.py | 对一系列数字求平均值 | – |
> | 1.5.4 | rangefilter.py | 一个简单的过滤器 | – |
> | 1.5.5 | plotfilter.py | 标准输入绘制滤波器 | usa.txt   |
> | 1.5.6 | bouncingball.py | 弹跳球 | – |
> | 1.5.7 | playthattune.py | 数字信号处理 | elise.txt  ascale.txt  stairwaytoheaven.txt  entertainer.txt  firstcut.txt  freebird.txt  looney.txt   |
> | 1.6.1 | transition.py | 计算转移矩阵 | small.txt  medium.txt   |
> | 1.6.2 | randomsurfer.py | 模拟随机冲浪者 | – |
> | 1.6.3 | markov.py | 混合马尔可夫链 | – |
