# 107：条件表达式 `cond` 的使用 🧩

在本节课中，我们将学习Racket语言中的 `cond` 结构。`cond` 是处理多条件分支的更好方式，可以替代嵌套的 `if-then-else` 表达式，使代码更清晰、更具可读性。

![](img/a6dd8b7fb0563d0d330b9ac15db0d3f8_1.png)

## 概述

`cond` 可以被视为嵌套 `if-then-else` 表达式的语法糖。它允许我们以更结构化的方式编写多个条件分支。本节将介绍 `cond` 的基本语法、使用场景以及一些重要的风格约定。

## `cond` 的基本语法

`cond` 是一个特殊形式，其基本结构如下：

```racket
(cond
  [test1 result1]
  [test2 result2]
  ...
  [else default-result])
```

每个分支由一对表达式组成：第一个是测试条件，第二个是当该条件为真时要执行的操作。`cond` 会按顺序评估每个测试条件，并执行第一个为真的条件对应的结果表达式。

## 使用 `cond` 重写求和函数

![](img/a6dd8b7fb0563d0d330b9ac15db0d3f8_3.png)

上一节我们介绍了处理嵌套列表的求和函数。本节中，我们来看看如何使用 `cond` 来重写这些函数，使其结构更清晰。

![](img/a6dd8b7fb0563d0d330b9ac15db0d3f8_5.png)

以下是使用 `cond` 重写的 `sum3` 函数，它计算一个可能包含嵌套列表的数字列表的总和：

![](img/a6dd8b7fb0563d0d330b9ac15db0d3f8_6.png)

```racket
(define (sum3 xs)
  (cond
    [(null? xs) 0]
    [(number? (car xs)) (+ (car xs) (sum3 (cdr xs)))]
    [else (+ (sum3 (car xs)) (sum3 (cdr xs)))]))
```

![](img/a6dd8b7fb0563d0d330b9ac15db0d3f8_8.png)

这个 `cond` 表达式清晰地列出了三种情况：
1.  如果列表为空，返回0。
2.  如果列表的第一个元素是数字，则将其与剩余列表的递归和相加。
3.  否则（即第一个元素是列表），则递归计算第一个子列表和剩余列表的和，然后相加。

类似地，我们可以重写 `sum4` 函数，该函数在遇到非列表且非数字的元素时会跳过它：

```racket
(define (sum4 xs)
  (cond
    [(null? xs) 0]
    [(number? (car xs)) (+ (car xs) (sum4 (cdr xs)))]
    [(list? (car xs)) (+ (sum4 (car xs)) (sum4 (cdr xs)))]
    [else (sum4 (cdr xs))]))
```

与 `sum3` 相比，`sum4` 增加了一个显式检查 `(list? (car xs))` 的分支，并在最后的 `else` 分支中跳过无效元素。

![](img/a6dd8b7fb0563d0d330b9ac15db0d3f8_10.png)

![](img/a6dd8b7fb0563d0d330b9ac15db0d3f8_11.png)

## 关于条件测试的重要说明

在Racket中，无论是 `if` 还是 `cond`，其测试表达式的结果都不必须是严格的布尔值 `#t` 或 `#f`。

其语义是：**任何不是 `#f` 的值都被视为真（`#t`）**。只有 `#f` 本身被视为假。

例如：
*   `(if 34 14 15)` 会返回 `14`，因为 `34` 不是 `#f`。
*   `(if '() 14 15)` 会返回 `14`，因为空列表 `'()` 不是 `#f`。
*   `(if #f 14 15)` 才会返回 `15`。

![](img/a6dd8b7fb0563d0d330b9ac15db0d3f8_13.png)

这种特性在动态类型语言中比较常见。虽然有些程序员认为这很方便，但也有人认为这会影响代码清晰度。你可以根据情况决定是否使用。

以下是一个利用此特性的例子，函数 `count-falses` 用于计算一个列表中 `#f` 出现的次数：

```racket
(define (count-falses xs)
  (cond
    [(null? xs) 0]
    [(car xs) (count-falses (cdr xs))] ; 如果(car xs)不是#f，则为真，跳过
    [else (+ 1 (count-falses (cdr xs)))])) ; 否则(car xs)是#f，计数加1
```

在这个函数中，测试 `(car xs)` 利用了“非 `#f` 即真”的规则。如果 `(car xs)` 不是 `#f`，则条件为真，递归处理列表其余部分；如果它是 `#f`，则进入 `else` 分支，计数加1。

## 总结

![](img/a6dd8b7fb0563d0d330b9ac15db0d3f8_15.png)

本节课中我们一起学习了Racket中 `cond` 结构的使用。`cond` 通过提供清晰的多分支结构，改善了嵌套 `if` 表达式的代码风格。我们还了解了Racket条件判断中“非 `#f` 即真”的独特规则。现在，你可以在后续的Racket编程作业中，使用 `cond` 来编写更优雅、更易读的条件判断代码了。