# 3\. 面向对象编程

> 原文：[`introcs.cs.princeton.edu/python/30oop`](https://introcs.cs.princeton.edu/python/30oop)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)


在*面向对象编程*中，我们将一个大型且可能复杂的程序分解为一组相互作用的元素或*对象*。这个想法源自于对（软件中）建模现实世界实体的概念，如电子、人、建筑物或太阳系，并很容易扩展到对抽象实体的建模，如位、数字、颜色、图像或程序。

如第 1.2 节所讨论的，数据类型是一组值和一组在这些值上定义的操作。在 Python 中，许多数据类型（如`int`和`float`）的值和操作是预定义的。在面向对象编程中，我们组合代码来定义新的数据类型。

这种定义新数据类型并操作持有数据类型值的对象的能力也被称为*数据抽象*，并引导我们进入一种自然扩展了第二章基础的函数抽象风格的模块化编程风格。数据类型允许我们隔离数据以及函数。

+   *3.1 数据类型* 描述了如何使用现有数据类型，用于文本处理和图像处理。

+   *3.2 创建数据类型*描述了如何使用 Python 的类机制创建用户定义的数据类型。

+   *3.3 设计数据类型*考虑了设计数据类型的重要技术，强调 API、封装、不可变性和按合同设计。

+   *3.4 案例研究：N 体��拟*提供了一个模拟 n 个粒子运动的案例研究，受牛顿引力定律的影响。

## 本章中的 Python 程序

下面是本章中使用的 Python 程序和数据文件列表。

> | **参考** | **程序** | **描述** | **数据** |
> | --- | --- | --- | --- |
> | 3.1.1 | potentialgene.py | 潜在基因识别 | – |
> | 3.1.2 | chargeclient.py | 带电粒子客户端 | – |
> | 3.1.3 | alberssquares.py | 阿尔伯斯方块 | – |
> | 3.1.4 | luminance.py | 亮度库 | – |
> | 3.1.5 | grayscale.py | 将颜色转换为灰度 | mandrill.jpg  mandrill.png  darwin.jpg  darwin.png   |
> | 3.1.6 | scale.py | 图像缩放 | mandrill.jpg  mandrill.png  darwin.jpg  darwin.png   |
> | 3.1.7 | fade.py | 渐变效果 | mandrill.jpg  mandrill.png  darwin.jpg  darwin.png   |
> | 3.1.8 | potential.py | 可视化电势 | charges.txt   |
> | 3.1.9 | cat.py | 连接文件 | in1.txt  in2.txt   |
> | 3.1.10 | stockquote.py | 股票报价的屏幕抓取 | – |
> | 3.1.11 | split.py | 文件分割 | djia.csv   |
> | 3.2.1 | charge.py | 带电粒子数据类型 | – |
> | 3.2.2 | stopwatch.py | 秒表数据类型 | – |
> | 3.2.3 | histogram.py | 直方图数据类型 | – |
> | 3.2.4 | turtle.py | 海龟图形数据类型 | – |
> | 3.2.5 | koch.py | 科赫曲线 | – |
> | 3.2.6 | spiral.py | 黄金螺旋 | – |
> | 3.2.7 | drunk.py | 醉汉乌龟 | – |
> | 3.2.8 | drunks.py | 醉汉乌龟们 | – |
> | 3.2.9 | complex.py | 复数数据类型 | – |
> | 3.2.10 | mandelbrot.py | 曼德勃罗集 | – |
> | 3.2.11 | stockaccount.py | 股票账户数据类型 | turing.txt   |
> | 3.3.1 | complexpolar.py | 复数（再探讨） | – |
> | 3.3.2 | counter.py | 计数器数据类型 | – |
> | 3.3.3 | vector.py | 空间向量数据类型 | – |
> | 3.3.4 | sketch.py | 素描数据类型 | genome20.txt   |
> | 3.3.5 | comparedocuments.py | 相似性检测 | documents.txt  constitution.txt  tomsawyer.txt  huckfinn.txt  prejudice.txt  djia.csv  amazon.html  actg.txt   |
> | 3.4.1 | body.py | 引力体数据类型 | – |
> | 3.4.2 | universe.py | n 体模拟 | 2body.txt  3body.txt  4body.txt  2bodytiny.txt   |
