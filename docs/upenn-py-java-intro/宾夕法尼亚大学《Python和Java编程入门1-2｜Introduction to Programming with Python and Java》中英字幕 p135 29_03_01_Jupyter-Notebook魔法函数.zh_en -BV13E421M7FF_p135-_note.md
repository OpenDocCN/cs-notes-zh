# Python与Java编程入门1-2：第29章：Jupyter Notebook魔法函数

在本节课中，我们将学习Jupyter Notebook中一个非常实用的功能——魔法函数。这些特殊的命令以百分号`%`开头，能够帮助我们更高效地执行一些元操作或增强Notebook的功能。

![](img/7e7164031376a020aeaba49f4182a1ec_0.png)

## 什么是魔法函数？

上一节我们介绍了Jupyter Notebook的基本操作。本节中，我们来看看Jupyter Notebook内置的“魔法函数”。魔法函数是Jupyter Notebook特有的功能，它们以`%`或`%%`符号开头，用于执行一些常规Python代码无法直接完成的便捷操作，例如测量代码运行时间、加载外部库的特定模式，或者进行系统级操作。

## 一个实用的魔法函数示例：`%pylab inline`

一个常用且重要的魔法函数是`%pylab inline`。它的主要作用是同时导入NumPy和Matplotlib库，并设置图表在Notebook内直接显示，而不是弹出单独的窗口。

以下是使用`%pylab inline`的步骤和效果：

1.  **在单独的代码单元格中运行**：为了确保环境正确配置，这个魔法命令通常需要在Notebook的第一个代码单元格中执行。
2.  **执行命令**：在单元格中输入`%pylab inline`并运行。
3.  **效果**：运行后，Notebook会自动导入`numpy`和`matplotlib.pyplot`等科学计算和绘图库，并配置好内嵌绘图模式。

运行此命令后，你就可以直接在后续的单元格中使用如`plot()`等函数进行绘图，并且图表会直接显示在代码输出区域。

![](img/7e7164031376a020aeaba49f4182a1ec_2.png)

```python
%pylab inline
# 运行后，即可直接使用numpy和matplotlib
x = linspace(0, 10, 100)
y = sin(x)
plot(x, y)
```

![](img/7e7164031376a020aeaba49f4182a1ec_3.png)

本节课中我们一起学习了Jupyter Notebook的魔法函数，重点介绍了`%pylab inline`这个用于配置科学计算和可视化环境的实用命令。掌握魔法函数能显著提升你在Notebook中编程和数据分析的效率。