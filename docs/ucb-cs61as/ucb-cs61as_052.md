# 第 4 课介绍

## 数据抽象和序列

还记得在第 0.1 课中关于抽象的所有花里胡哨的说法，以及在第 2 课中使用高阶函数预览抽象吗？在这节课中，你将终于尝试创建一些非常有趣的抽象数据类型。你将会学到，在编程时，控制复杂性和分层抽象将会使你拥有干净、专业的代码。

## 先决条件和预期内容

**先决条件：**学习计算机科学是渐进的。确保你了解所有先前的课程，特别是第 1 和第 2 课。

**预期内容：**编程可以用以下三个（非常非常通用的）类别概括：

+   存储数据

+   提取数据

+   操纵数据

在第 2 课中，我们学习了**过程抽象**。换句话说，我们学会了如何使用抽象创建通用的、“可定制的”过程。这属于上述第三类别，数据操作。例如，我们有一个数字列表 - 我们的*数据* - 我们想要*操作*它以找到所有平方的和。我们使用我们抽象的过程*sum*对此进行了泛化。如果你不记得这个，我们建议你花一点时间[回顾](http://berkeley-cs61as.github.io/textbook/hofs-procedures-as-arguments.html)。

本课程是关于**数据抽象**的，属于前两个类别。我们将首先介绍用于存储数据的数据结构（对和列表），展示如何提取和操作它们（`map`），然后最终教你如何创建自己的抽象数据类型。

加油。

## 读物

以下是本课程的相关阅读材料：

+   [SICP 2 介绍](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-13.html)

+   [SICP 2.1](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-14.html#%25_sec_2.1)

+   [SICP 2.2.1](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-15.html#%25_sec_2.2.1)

+   [讲座笔记](http://inst.eecs.berkeley.edu/~cs61as/reader/notes.pdf#page=18)（忽略关于 MapReduce 的部分 -- 这与 map 不同！）
