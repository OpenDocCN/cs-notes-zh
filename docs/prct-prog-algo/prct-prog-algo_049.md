# 9\.   科学计算

> 原文：[`introcs.cs.princeton.edu/java/90scientific`](https://introcs.cs.princeton.edu/java/90scientific)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)


本章节正在大力施工中。

科学和工程中许多重要且具有挑战性的问题需要大量的计算资源来模拟和仿真自然现象。一些示例问题包括：人类基因组计划、计算流体动力学、海洋环流、等离子体动力学、车辆碰撞模拟、建筑漫游、全球气候模拟、金融建模、地震勘测、分子动力学模拟、蛋白质折叠、电子设计、核武器模拟、制药设计和自然语言处理。这些重大挑战性问题具有广泛的科学、社会、经济和政治影响。

高效的计算机算法也在现代技术中发挥着核心作用，并丰富了我们的日常生活。例如网页搜索引擎、DVD 播放器、手机、JPEG 图像、MP3 音频文件和 DivX 视频文件。

科学计算涵盖了一个庞大的知识领域，在过去半个世纪里建立在高斯、牛顿、欧拉等人的工作之上。在本章中，我们将概述在我们的计算基础设施中发挥关键作用的一些最重要的算法。设计稳健和高效的科学算法是一项非常不平凡的任务。我们的目标是让您了解所涉及的内容，并确保您在编写科学代码时意识到您所做决策的后果。本书不旨在成为全面参考（请参阅《Java 数值计算法》、《Golub 和 Van Loan 的矩阵计算》）。我们也不包括数学证明来证明我们的算法。

[计算机模拟方法简介](http://sip.clarku.edu/3e/) 由 Gould, Tobochnik 和 Christian 撰写。

[数值计算法](http://library.lanl.gov/numerical/bookcpdf.html)。

[Colt](http://dsd.lbl.gov/~hoschek/colt/) 提供了一组用于在 Java 中进行高性能科学和技术计算的开源库。由 CERN 提供。速度高达优化后的 Fortran 的 90%。它包含了用于离线和在线数据分析、线性代数、多维数组、统计学、直方图、蒙特卡洛模拟、并行和并发编程的高效数据结构和算法。
