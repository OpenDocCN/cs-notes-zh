# 第 13 课介绍

## 介绍

本周的重要概念是逻辑编程或声明式编程。

这是我们远离以硬件术语表达计算的最大一步。当我们发现流时，我们看到如何以与评估顺序无关的方式表达算法。现在我们将描述一种没有（可见）算法的计算方式！

我们正在使用 A&S 在 Scheme 中实现的逻辑编程语言。因此，表示法类似于 Scheme，即充满了列表。标准逻辑语言如 Prolog 有不同的表示法，但思想是相同的。

## 先决条件

这节课遵循的范式与你之前见过的任何内容都非常不同。因此，没有先决条件！

## 阅读材料

大部分这节课内容取自[这些笔记](http://www-inst.eecs.berkeley.edu/~cs61as/reader/notes.pdf#page=102)和[SICP 4.4.1-4.4.3 节](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-29.html#%_sec_4.4)。

## 逻辑编程

逻辑编程在提供接口给数据库进行信息检索方面表现出色。我们将在本章中使用的查询语言是为了以这种方式使用而设计的。

我们所做的一切只是断言事实：

```
> (load "~cs61as/lib/query.scm")
> (query)

;;; Query input:
(assert! (Brian likes potstickers)) 
```

并询问关于事实的问题：

```
;;; Query input:
(?who likes potstickers)

;;; Query results:
(BRIAN LIKES POTSTICKERS) 
```

尽管断言和查询采用列表形式，看起来有点像 Scheme 程序，但实际上不是！这里没有函数对参数的应用；一个断言只是数据。

尽管出于各种原因，传统上将动词（关系）放在第一位，但这仍然是真实的：

```
(assert! (likes Brian potstickers)) 
```

以后我们将遵循这个惯例，但这样做会更容易陷入认为有一个名为`likes`的函数的陷阱。继续阅读以了解我们如何在这种特殊的语言中编程！
