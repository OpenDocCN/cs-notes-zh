# 3\.   面向对象编程

> 原文：[`introcs.cs.princeton.edu/java/30oop`](https://introcs.cs.princeton.edu/java/30oop)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)


## 概述。

在面向对象编程中，我们编写 Java 代码来创建新的数据类型，指定值和操作以操作这些值。这个想法源自于对（软件中）现实世界实体的建模，如电子、人、建筑物或太阳系，并很容易扩展到对抽象实体的建模，如位、数字、程序或操作系统。

+   *3.1 使用数据类型* 描述了如何使用现有的引用数据类型，用于文本处理和图像处理。

+   *3.2 创建数据类型* 描述了如何使用 Java 的类机制创建用户定义的数据类型。

+   *3.3 设计数据类型* 考虑了设计数据类型的重要技术，强调 API、封装、不可变性和契约式设计。

+   *3.4 案例研究：N-Body 模拟* 展示了一个模拟*n*粒子运动的案例研究，受牛顿引力定律的影响。

## 本章中的 Java 程序。

以下是本章节中的 Java 程序列表。点击程序名称以访问 Java 代码；点击参考编号以获取简要描述；阅读教材以获取详细讨论。

> | **参考** | **程序** | **描述** |
> | --- | --- | --- |
> | 3.1.1 | PotentialGene.java | 识别潜在基因 |
> | 3.1.2 | AlbersSquares.java | 阿���伯斯方块 |
> | 3.1.3 | Luminance.java | 亮度库 |
> | 3.1.4 | Grayscale.java | 将颜色转换为灰度 |
> | 3.1.5 | Scale.java | 图像缩放 |
> | 3.1.6 | Fade.java | 渐变效果 |
> | 3.1.7 | Cat.java | 文件连接 |
> | 3.1.8 | StockQuote.java | 股票报价抓取 |
> | 3.1.9 | Split.java | 文件分割 |
> | 3.2.1 | Charge.java | 带电粒子数据类型 |
> | 3.2.2 | Stopwatch.java | 计时器数据类型 |
> | 3.2.3 | Histogram.java | 直方图数据类型 |
> | 3.2.4 | Turtle.java | 海龟图形数据类型 |
> | 3.2.5 | Spiral.java | 黄金螺线 |
> | 3.2.6 | Complex.java | 复数数据类型 |
> | 3.2.7 | Mandelbrot.java | 曼德勃罗集 |
> | 3.2.8 | StockAccount.java | 股票账户数据类型 |
> | 3.3.1 | Complex.java") | 复数数据类型（重新审视） |
> | 3.3.2 | Counter.java | 计数器数据类型 |
> | 3.3.3 | Vector.java | 空间向量数据类型 |
> | 3.3.4 | Sketch.java | 文档草图数据类型 |
> | 3.3.5 | CompareDocuments.java | 相似度检测 |
> | 3.4.1 | Body.java | 万有引力体数据类型 |
> | 3.4.2 | Universe.java | n 体模拟 |
