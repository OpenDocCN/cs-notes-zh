# 序列作为常规接口

## 序列作为抽象

让我们更深入地探讨抽象的概念。使用抽象的一个主要好处是帮助我们清理代码并增加可读性。我们为序列编写的一些函数可以使用高阶函数进行泛化和抽象。这个想法可以通过以下步骤总结：

+   在我们的代码中找到一个重复的模式

+   使用 HOF 抽象化模式中的每个元素

+   重新定义我们的代码使用抽象

这里有两个示例函数，将有助于演示这个想法。

`sum-odd-squares` 接受一个包含数字的树，并将树中每个**奇数**元素的平方相加：

```
(define (sum-odd-squares tree)
  (cond ((null? tree) 0)  
        ((not (pair? tree))
         (if (odd? tree) (square tree) 0))
        (else (+ (sum-odd-squares (car tree))
                 (sum-odd-squares (cdr tree)))))) 
```

`even-fibs` 接受一个数字 `n`，并返回包括 `n` 在内的偶数斐波那契数的列表：

```
(define (even-fibs n)
  (define (next k)
    (if (> k n)
        nil
        (let ((f (fib k)))
          (if (even? f)
              (cons f (next (+ k 1)))
              (next (+ k 1))))))
  (next 0)) 
```

乍一看这两个函数，我们可能会说“这两个函数没有任何共同之处！”当然，这两个函数看起来完全不同，但它们确实共享相同的逻辑：

![](img/2be0131620e5880b328720c924f164fb.jpg)

我们想法的第一步是在我们的代码中找到一个重复的模式。从我们在之前课程中描述递归的方式，你可能会通过基本情况和递归调用来剖析 `sum-odd-squares` 和 `even-fibs`。现在，让我们从不同的角度看看每个函数的作用：

`sum-odd-squares`：

+   **枚举**树的叶子节点

+   **过滤**掉具有偶数数据的节点，仅留下奇数值节点

+   **映射**函数 `square` 到剩余的每个节点，最后

+   **累积**结果通过将它们相加，从 0 开始。

`even-fibs`：

+   **枚举**从 0 到 `n` 的整数

+   **映射**函数 `fib` 到每个整数

+   **过滤**掉奇数，仅留下偶数斐波那契数，最后

+   **累积**使用 `cons`，从空列表开始。

我们在这里看到了什么模式？起初看起来非常不同的两个函数现在可以总结为四个主要部分：枚举、过滤、累积和计算。这很棒，因为现在我们可以使用 HOF 来抽象化我们的代码。这将引导我们进入我们抽象化想法的第二步。但在那之前，让我们来看看一些 HOF。

## 映射

我们在第 4 课中讨论了 `map` HOF。您可能希望[返回](http://localhost:8000/textbook/representing-sequences.html#sub3)快速复习一下。

## 过滤

`filter` 接受两个参数，`predicate` 和 `sequence`，并返回仅满足 `predicate` 的元素的序列。

```
(define (filter predicate sequence)
  (cond ((null? sequence) nil)
        ((predicate (car sequence))
         (cons (car sequence)
               (filter predicate (cdr sequence))))
        (else (filter predicate (cdr sequence))))) 
```

**测试您的理解**

以下表达式返回什么？

```
(filter (lambda (x) (= (remainder x 2) 0)) (list 0 1 2 3 4 5)) 
```

```
(filter equal? '(bongo celia momo laval laburrita bongo)) 
```

## 累积

`accumulate` 接受一个操作 `op`，一个起始值 `initial` 和一个 `sequence`。从 `initial` 开始，`accumulate` 使用 `op` 将 `sequence` 中的所有值组合成一个值。以下是一些示例：

```
> (accumulate + 0 '(1 2 3 4 5))
15
> (accumulate append null '((1 2) (3 4) (5 6)))
(1 2 3 4 5 6) 
```

这是我们如何定义 `accumulate`：

```
(define (accumulate op initial sequence)
  (if (null? sequence)
      initial
      (op (car sequence)
          (accumulate op initial (cdr sequence))))) 
```

这个 HOF 的工作原理可能有点令人困惑，所以让我们明确写出评估步骤：

考虑表达式：

`(accumulate + 0 (list 1 2 3 4 5))`

递归步骤将按以下方式进行：

`(+ 1 (accumulate + 0 (list 2 3 4 5)))`

`(+ 1 (+ 2 (accumulate + 0 (list 3 4 5))))`

`(+ 1 (+ 2 (+ 3 (accumulate + 0 (list 4 5)))))`

`(+ 1 (+ 2 (+ 3 (+ 4 (accumulate + 0 (list 5))))))`

`(+ 1 (+ 2 (+ 3 (+ 4 (+ 5 (accumulate + 0 (list)))))))`

`(+ 1 (+ 2 (+ 3 (+ 4 (+ 5 0)))))`

`(+ 1 (+ 2 (+ 3 (+ 4 5))))`

`(+ 1 (+ 2 (+ 3 9)))`

`(+ 1 (+ 2 12))`

`(+ 1 14)`

`15`

## 枚举

`enumerate`做什么？`enumerate`制作一个元素的序列/列表。我们对`filter`、`map`和`accumulate`的定义是为序列设计的，但请记住，我们的一个函数`sum-odd-squares`是在树上调用的。我们可以通过只有不同的`enumerate`函数来区分它们，而不是制作几个版本的累加、映射和筛选。

## 列举列表

枚举将在给定下限和上限范围内返回一个列表。

+   `(enumerate-interval 0 5)` 返回`(0 1 2 3 4 5)`

+   `(enumerate-interval 10 13)` 返回`(10 11 12 13)`

您可以定义枚举（用于列表）如下：

```
(define (enumerate-interval low high)
  (if (> low high)
      nil
      (cons low (enumerate-interval (+ low 1) high)))) 
```

## 枚举树

对于我们树形版本的枚举，我们需要一个接受树的函数，并返回一个包含所有叶子的列表，以便与我们的其他高阶函数兼容。

```
(define (enumerate-tree tree)
  (cond ((null? tree) nil)
        ((not (pair? tree)) (list tree))
        (else (append (enumerate-tree (car tree))
                      (enumerate-tree (cdr tree)))))) 
```

## 将所有内容整合在一起

在这里，我们达到了我们抽象概念的最后一步。通过我们定义的所有辅助函数，我们可以定义一个更模块化、可读性更强、更紧凑的`sum-odd-squares`和`even-fibs`的版本：

```
(define (sum-odd-squares tree)
  (accumulate +
              0
              (map square
                   (filter odd?
                           (enumerate-tree tree))))) 
```

我们在这里做了什么？我们找到树中的所有叶子（**枚举**），保留所有奇数（**筛选**），对剩下的所有内容进行平方（**映射**），然后将结果相加（**累加**）。

类似地，我们可以如下定义`even-fibs`：

```
(define (even-fibs n)
  (accumulate cons
              nil
              (filter even?
                      (map fib
                           (enumerate-interval 0 n))))) 
```

这次发生了什么？我们从 0 到`n`制作一个列表（**枚举**），为它们找到斐波那契数（**映射**），保留所有偶数（**筛选**），然后将它们放在一起成为一个列表（**累加**）。

## 要点

序列为使用不同组合的`map`、`filter`、`accumulate`和`enumerate`提供了强大的抽象基础。即使函数看起来具有不同结构，就像我们在这里使用的示例一样，我们可能能够使用类似的过程信号来分解它们。
