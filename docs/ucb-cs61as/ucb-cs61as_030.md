# 过程应用的替换模型

## 应用复合过程

到目前为止，我们已经看到了 Racket 如何分解和评估诸如：

`(+ 1 2)`

`(+ 3 4 (* 2 5))`

通过以下步骤：

1.  评估过程

1.  评估参数

1.  将过程应用于参数。

我们在第 3 步中有些含糊。如何确切地“应用”过程？对于像`+`、`-`、`quote`、`or`、`and`、`not`这样的原始函数，我们可以假设它们内置于解释器中。我们更感兴趣的是更复杂的东西：如何应用复合（即用户定义的）过程？由于我们可以定义任意多个复合过程，它们不能全部内置于解释器中。需要有一种共同的逐步方式来应用复合过程。一种思考这个问题的方法是替换模型，我们将在本小节中探讨。

## 替换模型

要使用替换模型应用复合过程，您需要用相应参数的值替换主体中的每个形式参数，并正常评估它。这实际上意味着什么？通过一个例子更容易理解：

考虑第一个实验室中的`sum-of-squares`过程，可以定义如下：

```
(define (sum-of-squares x y)  
     (+ (square x) (square y))) ;; This line is the 'body' of the procedure
     (define (square x) (* x x)) 
```

替换模型如何处理`(sum-of-squares 3 4)`？

1.  我们有一个形式参数 x，用参数 3 调用，另一个形式参数 y，用参数 4 调用。

1.  我们在主体中用 3 和 4 分别替换 x 和 y 的每个出现

1.  然后主体变为`(+ (square 3) (square 4))`

1.  使用 square 的定义，这简化为`(+ (* 3 3) (* 4 4))。`

1.  应用两个乘法得到`(+ 9 16)`

1.  应用加法得到`25`的结果

步骤 1 和 2 是替换模型最关键的部分：找到传递给函数的值，并用相应值替换主体中的每个变量。

## 形式参数的名称

到目前为止，您可能已经注意到形式参数的名称是任意的。例如，以下所有内容都是等效的：

`(define (square x) (* x x))`

`(define (square apple) (* apple apple))`

`(define (square magikarp) (* magikarp magikarp))`

替换模型处理这三个等效，尽管最好选择一个易于理解的名称（在这种情况下，第一个定义是理想的）。主要问题是在主体内保持一致。例如，以下内容可能会导致错误：

`(define (square x) (* apple apple))`

![立方体形状的苹果](http://foundersgrp.files.wordpress.com/2011/01/apple-cube.jpg)

当我们使用上述定义的 Substitution Model 与`(square 4)`时，你会注意到事情并没有得到正确定义。过程`square`接受一个参数，这里是 4。在函数体内我们需要找到`apple`的值并执行`(* apple apple)`。`apple`的值是多少？我们不知道！我们只知道`x`是多少！

## Substitution Model & Racket

Racket 是否实际使用 Substitution Model 来应用复合过程？并非完全如此。我们使用 Substitution Model 来帮助我们思考过程应用。Racket 做了稍微复杂一点的事情，我们将在第 3 和第 4 单元中探讨。后来，我们会发现 Substitution Model 无法解释 Racket 中的一些函数。这个模型将作为我们将构建的框架。

## Applicative Order vs Normal Order

我们通过评估运算符、评估操作数，然后应用运算符的方法只是一种可能的评估规则。我们一直在使用的排序被称为“Applicative Order”。另一种评估方法是在需要值之前不评估操作数。这种方法被称为“Normal Order”。我们可以从以下示例中看到这两者之间的区别：

`(square (+ 3 2))`

请注意，square 的输入是(`+ 3 2)。

+   Applicative Order:

`(square (+ 3 2))`

`(square 5)`

`(* 5 5)`

`25`

在 Applicative Order 中，你会在进入 square 的函数体`(* x x)`之前评估参数`x`。当你评估`(+ 3 2)`时，你得到`5`，这就是你传递给 square 的值。所以`x`绑定到`5`。

+   Normal Order:

`(square (+ 3 2))`

`(* (+ 3 2) (+ 3 2))`

`(* 5 5)`

`25`

在 Normal Order 中，你不会评估`(+ 3 2)`直到绝对需要。所以在这种情况下，`(square x)`中的`x`绑定到`(+ 3 2)`。

请注意，在 Normal Order 中，由于你不评估`x`，即`(+ 3 2)`，直到需要它时，你需要评估两次。另一方面，在 Applicative Order 中，由于你在应用过程之前评估操作数`x`，你只评估`(+ 3 2)`一次。

考虑以下代码片段：

```
(define (double_first a b) (+ a a))

(double_first (+ 1 1) (+ 2 2)) 
```

在 Applicative Order 中，(+ 1 1)被评估了多少次？

<ans text="2" explanation="再试一次！" u00026gtu0003bu0003c="" ans=""></ans>
