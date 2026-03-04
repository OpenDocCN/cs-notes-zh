# 103：Racket列表 🧮

在本节课中，我们将学习Racket语言中的列表。由于Racket列表的工作方式与ML语言中的列表非常相似，特别是我们之前在第1节中使用函数访问列表各部分的方式，因此本节内容会进展得很快。

![](img/cd8d940b1305799b0db01a127b2b766f_1.png)

## 概述

我们将介绍Racket列表的基本操作原语，并通过编写几个简单的函数来加深理解。这些概念与ML语言中的列表操作一脉相承，相信你在学习时会感到熟悉和安心。

## 列表基本操作

Racket列表的操作原语与ML类似，但语法和函数名有所不同。

以下是Racket中用于处理列表的核心函数：

*   **空列表**：使用 `null` 表示。在ML中我们写作 `[]`。
*   **构造列表**：使用 `cons` 函数。它接受一个元素和一个列表，返回一个在原列表头部添加了新元素的新列表。在ML中，我们使用中缀运算符 `::`。
*   **获取头部**：使用 `car` 函数获取列表的第一个元素。
*   **获取尾部**：使用 `cdr` 函数获取列表中除第一个元素外的剩余部分。
*   **判断空列表**：使用 `null?` 函数检查一个列表是否为空。

![](img/cd8d940b1305799b0db01a127b2b766f_3.png)

需要说明的是，`car` 和 `cdr` 这两个函数名的来源是一个历史遗留问题，源于几十年前这种语言最初实现的机器架构。虽然这些名字在今天看来并不直观，但我们已经习惯使用它们。

此外，Racket还提供了 `list` 函数，它可以接受任意数量的参数，并创建一个包含这些参数的列表。这比连续使用多个 `cons` 调用更为方便。

## 编写列表函数示例

![](img/cd8d940b1305799b0db01a127b2b766f_5.png)

![](img/cd8d940b1305799b0db01a127b2b766f_6.png)

![](img/cd8d940b1305799b0db01a127b2b766f_7.png)

![](img/cd8d940b1305799b0db01a127b2b766f_8.png)

![](img/cd8d940b1305799b0db01a127b2b766f_9.png)

![](img/cd8d940b1305799b0db01a127b2b766f_10.png)

上一节我们介绍了列表的基本操作，本节中我们来看看如何利用这些操作来编写实际的函数。

### 示例一：列表求和

![](img/cd8d940b1305799b0db01a127b2b766f_12.png)

![](img/cd8d940b1305799b0db01a127b2b766f_13.png)

首先，我们编写一个函数，用于计算列表中所有数字的总和。

![](img/cd8d940b1305799b0db01a127b2b766f_15.png)

```racket
(define sum
  (lambda (xs)
    (if (null? xs)
        0
        (+ (car xs) (sum (cdr xs))))))
```

![](img/cd8d940b1305799b0db01a127b2b766f_16.png)

这个函数使用递归：如果列表 `xs` 为空，则返回0；否则，将列表的头部 (`car xs`) 与对列表尾部 (`cdr xs`) 递归求和的结果相加。

我们可以测试这个函数，例如计算列表 `(list 3 4 5 6)` 的和，结果应为18。

![](img/cd8d940b1305799b0db01a127b2b766f_18.png)

![](img/cd8d940b1305799b0db01a127b2b766f_19.png)

![](img/cd8d940b1305799b0db01a127b2b766f_20.png)

![](img/cd8d940b1305799b0db01a127b2b766f_21.png)

需要注意的是，Racket是动态类型语言。如果我们错误地将一个字符串传递给 `sum` 函数（例如列表中包含 `"hi"`），程序会在运行时尝试对字符串执行加法操作，从而引发错误。

### 示例二：列表连接

![](img/cd8d940b1305799b0db01a127b2b766f_23.png)

![](img/cd8d940b1305799b0db01a127b2b766f_24.png)

![](img/cd8d940b1305799b0db01a127b2b766f_25.png)

![](img/cd8d940b1305799b0db01a127b2b766f_26.png)

接下来，我们实现一个自己的列表连接函数 `my-append`。Racket本身内置了 `append` 函数，这里我们重新实现它以作练习。

```racket
(define my-append
  (lambda (xs ys)
    (if (null? xs)
        ys
        (cons (car xs) (my-append (cdr xs) ys)))))
```

这个函数同样采用递归：如果第一个列表 `xs` 为空，则直接返回第二个列表 `ys`；否则，将 `xs` 的头部与 `xs` 的尾部同 `ys` 连接的结果再次连接起来。

![](img/cd8d940b1305799b0db01a127b2b766f_28.png)

![](img/cd8d940b1305799b0db01a127b2b766f_29.png)

![](img/cd8d940b1305799b0db01a127b2b766f_30.png)

![](img/cd8d940b1305799b0db01a127b2b766f_31.png)

### 示例三：映射函数

![](img/cd8d940b1305799b0db01a127b2b766f_33.png)

![](img/cd8d940b1305799b0db01a127b2b766f_34.png)

最后，我们实现一个高阶函数 `my-map`，它将一个函数应用到列表的每个元素上。这也是Racket内置的函数。

![](img/cd8d940b1305799b0db01a127b2b766f_35.png)

```racket
(define my-map
  (lambda (f xs)
    (if (null? xs)
        null
        (cons (f (car xs)) (my-map f (cdr xs))))))
```

![](img/cd8d940b1305799b0db01a127b2b766f_37.png)

![](img/cd8d940b1305799b0db01a127b2b766f_38.png)

函数逻辑是：如果列表 `xs` 为空，则返回空列表；否则，将函数 `f` 应用于列表头部 (`car xs`)，并将结果与对列表尾部递归调用 `my-map` 的结果连接起来。

![](img/cd8d940b1305799b0db01a127b2b766f_40.png)

我们可以这样使用它：

![](img/cd8d940b1305799b0db01a127b2b766f_41.png)

![](img/cd8d940b1305799b0db01a127b2b766f_42.png)

```racket
(define fo (my-map (lambda (x) (+ x 1)) (cons 3 (cons 4 (cons 5 null)))))
```

![](img/cd8d940b1305799b0db01a127b2b766f_44.png)

![](img/cd8d940b1305799b0db01a127b2b766f_45.png)

执行后，变量 `fo` 的值将是列表 `'(4 5 6)`。这里我们使用了匿名函数 `(lambda (x) (+ x 1))` 来对每个元素加1。

![](img/cd8d940b1305799b0db01a127b2b766f_46.png)

## 总结

![](img/cd8d940b1305799b0db01a127b2b766f_48.png)

![](img/cd8d940b1305799b0db01a127b2b766f_49.png)

![](img/cd8d940b1305799b0db01a127b2b766f_50.png)

本节课中我们一起学习了Racket中的列表。我们看到，Racket列表的操作方式与ML非常相似，同样方便和强大。我们介绍了列表的基本构造和访问原语（`null`, `cons`, `car`, `cdr`, `null?`），并通过编写 `sum`、`my-append` 和 `my-map` 三个递归函数，实践了如何使用这些原语来处理列表数据。递归在Racket中与在ML中一样，是处理列表问题的核心工具。