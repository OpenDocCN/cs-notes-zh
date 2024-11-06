# 使用 Lambda 构建过程

看一下下面对`sum-doubles`的定义，它接受两个数字`a`和`b`，并返回`a`和`b`之间所有数字的总和加倍。

```
(define (sum-doubles a b)
    (define (double x) (* 2 x))
    (if (> a b)
        0
        (+ (double a) (sum-doubles (+ a 1) b)))) 
```

由于`double`函数并没有为我们预先定义，我们不得不在我们的`sum-doubles`定义内部自己定义它。

但这样做太浪费了！在我们的`sum-doubles`定义之外，我们将永远无法使用那个`double`函数。有没有一种快速、简单的方法可以在不先定义、然后应用命名函数的情况下创建用户定义的函数？

## Lambda：匿名函数

实际上，是的。让我们介绍**lambda**函数，也被称为匿名函数。这些神秘的函数将是我们将在未来课程中讨论的重要角色。

lambda 的一般形式如下：

```
(lambda (<param1> <param2> ... <paramn>) <body>) 
```

让我们来解剖一下。在括号内，我们有三个主要部分：

+   一个**标签**，`lambda`，告诉 Racket 这是一个 lambda 函数，

+   一个**参数列表**（可以有很多个），

+   和**主体**—在参数列表之后的任何内容。

例如，过程`double`可以定义为以下 lambda 函数：

```
(lambda (x) (* 2 x)) 
```

换句话说，

```
(define double (lambda (x) (* 2 x))) 
```

相当于：

```
(define (double x) (* 2 x)) 
```

在描述 lambda 时，你会称其为“返回[主体]的[参数]函数”。例如，“`double`是返回`(* 2 x)`的`x`函数。”

## 调用 Lambda

正如我们可以调用使用`define`创建的过程一样，我们也可以调用 lambda 函数。调用 lambda 的一般形式如下：

`((lambda (<param1> <param2> ... <paramn>) <body>) <arg1> <arg2> ... <argn>)`

因此，如果我们想要将`(double 5)`作为匿名函数调用，替换模型会给我们这个结果：

```
-> ((lambda (x) (* 2 x)) 5)
-> ((lambda (x) (* 2 5)) 5)
-> (* 2 5)
10 
```

这里发生了什么？当我们调用 lambda 函数时，第一个参数对应于第一个参数，第二个参数对应于第二个参数，...，第 n 个参数对应于第 n 个参数。然后，在主体中，每个参数的每次出现都会被相应的参数替换。

让我们用一个示例表达式来说明这一点：

```
-> ((lambda (x y z) (+ x y x z)) 1 2 3) 
```

在 lambda 的主体中，我们用`1`替换每个`x`的出现。我们用`2`替换每个`y`。每次看到`z`时，我们用`3`替换它。

```
-> ((lambda (x y z) (+ x y x z)) 1 2 3)
-> ((lambda (x y z) (+ 1 2 1 3)) 1 2 3)
-> (+ 1 2 1 3)
7 
```

现在，我们可以将`sum-doubles`重写为：

```
(define (sum-doubles a b)
    (if (> a b)
        0
        (+ ((lambda (x) (* 2 x)) a) (sum-doubles (+ a 1) b)))) 
```

**注意：**创建`lambda`返回的值是一个过程，就像使用`define`调用创建的过程一样。

在 Racket 解释器中尝试这些表达式：

```
(lambda (x) (+ x 3))  
((lambda (x) (+ x 3)) 7)  
(define add3 (lambda (x) (+ x 3)))  
(add3 7)

(define (square x) (* x x))   
(square 5)   
(define sq (lambda (x) (* x x)))   
(sq 5)   
((lambda (x y) (+ (* 2 x) (* 5 y))) (* 100 100) (* 5 2)) 
```
