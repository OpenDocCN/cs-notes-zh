# 编程语言 A/B/C CSE341 Coursera：26：不使用结构体在 Racket 中进行数据类型编程 🧩

在本节课中，我们将学习如何在 Racket 这种动态类型语言中，不使用类似 ML 中的数据类型绑定，来实现类似的功能。我们将探索两种主要方法：处理混合类型列表，以及使用列表和符号来构建递归数据结构。

## 处理混合类型列表

在 ML 中，列表的所有元素必须是同一类型。为了处理混合类型，我们需要定义新的数据类型。然而，在 Racket 中，我们可以直接混合不同类型的数据，并使用内置谓词（如 `number?` 和 `string?`）来检查值的类型。

以下是实现一个函数 `funny-sum` 的示例，该函数对列表中的数字求和，对字符串则取其长度：

```racket
(define (funny-sum xs)
  (cond
    [(null? xs) 0]
    [(number? (car xs)) (+ (car xs) (funny-sum (cdr xs)))]
    [(string? (car xs)) (+ (string-length (car xs)) (funny-sum (cdr xs)))]))
```

这个函数直接利用了 Racket 的动态类型特性，无需预先定义任何新的数据类型。

![](img/1d4d0bf014fcb12571e1a45960f7a801_1.png)

## 构建递归数据结构

上一节我们介绍了如何处理简单的混合类型。本节中，我们来看看如何为更复杂的递归数据结构（如算术表达式树）编写解释器。

在 ML 中，我们会定义一个数据类型来表示表达式，并编写一个求值函数。在 Racket 中，我们可以使用列表来模拟这种结构。列表的第一个元素将作为一个“标签”，用来标识表达式的类型。

首先，我们需要一些辅助函数来“构造”表达式：

```racket
; 构造一个常量表达式
(define (constant i) (list 'constant i))

; 构造一个取负表达式
(define (negate e) (list 'negate e))

; 构造一个加法表达式
(define (add e1 e2) (list 'add e1 e2))

![](img/1d4d0bf014fcb12571e1a45960f7a801_3.png)

; 构造一个乘法表达式
(define (multiply e1 e2) (list 'multiply e1 e2))
```

接下来，我们需要辅助函数来“检查”和“提取”表达式：

```racket
; 检查是否为常量表达式
(define (constant? e) (eq? (car e) 'constant))

; 检查是否为取负表达式
(define (negate? e) (eq? (car e) 'negate))

; 检查是否为加法表达式
(define (add? e) (eq? (car e) 'add))

; 检查是否为乘法表达式
(define (multiply? e) (eq? (car e) 'multiply))

; 从常量表达式中提取整数值
(define (constant-int e) (car (cdr e)))

; 从取负表达式中提取子表达式
(define (negate-e e) (car (cdr e)))

; 从加法表达式中提取第一个子表达式
(define (add-e1 e) (car (cdr e)))

; 从加法表达式中提取第二个子表达式
(define (add-e2 e) (car (cdr (cdr e))))

; 从乘法表达式中提取第一个子表达式
(define (multiply-e1 e) (car (cdr e)))

; 从乘法表达式中提取第二个子表达式
(define (multiply-e2 e) (car (cdr (cdr e))))
```

现在，我们可以使用这些辅助函数来编写我们的解释器 `eval-exp`。这个函数遵循一个优雅的模式：递归求值子表达式，获取底层数据，执行操作，然后构造一个新的表达式作为结果。

```racket
(define (eval-exp e)
  (cond
    [(constant? e) e] ; 基础情况：直接返回常量表达式
    [(negate? e)
     (let ([v (eval-exp (negate-e e))]) ; 递归求值子表达式
       (constant (- (constant-int v))))] ; 取负并包装成常量
    [(add? e)
     (let ([v1 (constant-int (eval-exp (add-e1 e)))] ; 求值第一个子表达式
           [v2 (constant-int (eval-exp (add-e2 e)))]) ; 求值第二个子表达式
       (constant (+ v1 v2)))] ; 相加并包装
    [(multiply? e)
     (let ([v1 (constant-int (eval-exp (multiply-e1 e)))]
           [v2 (constant-int (eval-exp (multiply-e2 e)))])
       (constant (* v1 v2)))]))
```

## 关于符号的说明

在代码中，我们使用了**符号**（Symbol），例如 `'constant`。符号类似于字符串，但比较速度更快（使用 `eq?`）。我们也可以使用字符串（如 `"constant"`）来实现，但使用符号是 Racket 中的常见做法。

## 总结

本节课中我们一起学习了在 Racket 中不使用正式数据类型绑定的编程方法。
*   对于混合类型数据，我们可以直接利用动态类型和内置类型谓词。
*   对于递归数据结构，我们可以使用列表和符号来模拟数据类型的构造、检查和提取操作。
*   通过定义清晰的辅助函数，我们可以编写出结构清晰、易于理解的代码，其递归逻辑与 ML 中的模式匹配版本相对应。

![](img/1d4d0bf014fcb12571e1a45960f7a801_5.png)

这种方法的核心在于，我们手动管理了数据的“标签”和结构，而将类型检查的责任从编译时转移到了运行时和程序员自身。