# 第 2 课介绍

## 介绍

> "我 lambda Racket"

本周我们将学习一个新的特殊形式，`lambda`，它可以创建过程！确保你学会它，因为它将在本课程的其余部分中广泛使用。

## 先决条件和预期内容

**先决条件：** 在进行本课程之前需要完成第 1 课。你应该熟悉函数、过程和调用过程等概念。

**预期内容：** 在本课程中，我们将：

+   解释 lambda 和高阶函数

+   学习 Racket 中的一个基本概念，或者任何其他面向函数的编程语言 -- 使用其他函数来操作函数。

## 阅读材料

本课程的相关阅读如下：

+   [SICP 1.3 - 使用高阶过程进行抽象](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-12.html)

+   [讲座笔记](http://inst.eecs.berkeley.edu/~cs61as/reader/notes.pdf#page=9)

## 预览

我们在第 1 课中学习了如何创建、修改和调用过程。每个过程都有一个名称、它的参数和一个主体，我们在其中告诉函数如何处理它的参数。

例如，这是一个过程 `cube`，它接受一个参数 `x` 并返回 `x` 的立方：

```
(define (cube x)  
   (* x x x)) 
```

我们`定义`了一个过程，它的名称是 `cube`，参数是 `x`，主体是 `(* x x x)`。你现在应该能够看出，主体将三个 `x` 相乘并返回 `x` 的立方。

`cube` 是一个过程，或者抽象，我们可以像盒子一样处理并传递，就像任何其他数字或符号一样。它有一个*值*，我们可以给它一个*名称*。

现在我们想想，像上面那样定义 `cube` 并不比像这样定义 `var` 差太远：

```
(define var 10) 
```

![立方体](https://dl.dropboxusercontent.com/u/16963685/cs61as-edx/cube_diagram.png)

在盒子 `var` 中，我们放置了 `10`。在盒子 `(cube x)` 中，我们放置了 `(* x x x)`。在一个盒子中，我们放置一个数字，而在另一个中，我们放置一个表达式。相当相似，对吧？如果我们不是将原始值或表达式放入盒子中，而是将一个**函数**放入其中呢？难以想象！

它可能看起来像这样：

```
(define f [some function]) 
```

`[一些函数]` 是我们将放置 lambda 的地方。继续阅读以了解更多！