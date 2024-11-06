# 第 12 课介绍

## 介绍

此时，你（原则上）知道如何在 Scheme 中构建一个 Scheme 解释器。现在我们看到如何使元循环求值器更加高效，以及改变元循环求值器如何改变语言的解释方式，以及这带来的好处。特别是，我们形成了两个新的求值器。第一个求值器将程序的语法分析（分析程序要做什么）与执行（实际执行程序要做的事情）分开，以提高效率。第二个求值器将解释器从应用序改为正则序。

## 先决条件和期望

你应该对第 11 课中的元循环求值器非常熟悉。本课程在 MCE 的思想和代码基础上进行了大量构建。

## 阅读材料

以下是本课程的相关阅读材料：

+   [SICP 4.1.7 将语法分析与执行分离](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-26.html#%_sec_4.1.7)

+   [SICP 4.2 惰性求值](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-27.html#%_sec_4.2)

+   [讲座笔记](http://www-inst.eecs.berkeley.edu/~cs61as/reader/notes.pdf#page=93)（跳过非确定性求值器。）

+   [Therac 论文](http://www-inst.eecs.berkeley.edu/~cs61as/reader/Therac-25.pdf)

当你准备好了，继续下一节！
