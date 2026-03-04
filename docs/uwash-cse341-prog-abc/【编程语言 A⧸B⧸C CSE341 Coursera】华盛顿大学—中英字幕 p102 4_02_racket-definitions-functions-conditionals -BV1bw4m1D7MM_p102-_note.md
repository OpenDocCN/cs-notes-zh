# Racket基础：1：定义、函数与条件语句 🚀

在本节课中，我们将学习Racket编程语言的基础知识，包括如何定义变量、编写函数以及使用条件语句。这些概念与我们在ML语言中学过的内容相似，但语法有所不同。我们将通过编写代码来逐步掌握它们。

## 变量定义

![](img/b2359fcaa144d5860558aaccfb7a8fa3_1.png)

首先，我们来看如何在Racket中定义变量。定义变量的语法是使用`define`关键字，后跟变量名和一个表达式。这类似于ML中的`val x = 3`。

![](img/b2359fcaa144d5860558aaccfb7a8fa3_2.png)

以下是定义变量的示例：
```racket
(define x 3)
```

定义变量后，我们可以在其他定义中使用它。例如，我们可以定义变量`y`，其值为`x`加2的结果。在Racket中，函数调用需要将函数名放在括号内，后跟参数。

以下是使用变量`x`定义变量`y`的示例：
```racket
(define y (+ x 2))
```

这里，`+`是一个函数，我们调用它并传入`x`和`2`作为参数。函数调用的通用语法是：`(函数名 参数1 参数2 ...)`。

## 函数定义

接下来，我们学习如何定义自己的函数。我们将编写几个计算立方值的函数版本。

第一个版本使用`lambda`关键字来定义匿名函数。`lambda`后跟参数列表和函数体。

以下是使用`lambda`定义立方函数的示例：
```racket
(define cube1
  (lambda (x)
    (* x x x)))
```

![](img/b2359fcaa144d5860558aaccfb7a8fa3_4.png)

在这个例子中，`cube1`被绑定到一个匿名函数，该函数接受一个参数`x`，并返回`x * x * x`的结果。

然而，Racket中的乘法函数`*`可以接受任意数量的参数。因此，我们可以简化函数体。

以下是简化后的立方函数定义：
```racket
(define cube2
  (lambda (x)
    (* x x x)))
```

![](img/b2359fcaa144d5860558aaccfb7a8fa3_6.png)

此外，Racket提供了定义函数的语法糖，允许我们省略`lambda`关键字，直接使用`define`后跟参数列表和函数体。

以下是使用语法糖定义立方函数的示例：
```racket
(define (cube3 x)
  (* x x x))
```

![](img/b2359fcaa144d5860558aaccfb7a8fa3_8.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_9.png)

这三种方式定义的函数在功能上是完全相同的。

## 递归函数

与ML不同，在Racket中定义递归函数不需要额外的关键字。我们可以直接使用`lambda`或语法糖来编写递归函数。

现在，让我们编写一个计算幂的函数。我们将以两种方式实现。

![](img/b2359fcaa144d5860558aaccfb7a8fa3_11.png)

第一种方式使用`if`条件语句。`if`语句的语法是`(if 测试表达式 真分支 假分支)`。

![](img/b2359fcaa144d5860558aaccfb7a8fa3_13.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_15.png)

以下是计算幂的递归函数定义：
```racket
(define (power1 x y)
  (if (= y 0)
      1
      (* x (power1 x (- y 1)))))
```

![](img/b2359fcaa144d5860558aaccfb7a8fa3_17.png)

在这个函数中，如果`y`等于0，返回1；否则，返回`x`乘以`power1`递归调用的结果，其中`y`减1。

我们可以测试这个函数：
```racket
(power1 3 2) ; 返回 9
(power1 3 0) ; 返回 1
```

![](img/b2359fcaa144d5860558aaccfb7a8fa3_19.png)

## 柯里化函数

柯里化是一种将多参数函数转换为一系列单参数函数的技术。在Racket中，虽然内置支持多参数函数，但我们仍然可以实现柯里化。

以下是柯里化版本的幂函数定义：
```racket
(define (power2 x)
  (lambda (y)
    (power1 x y)))
```

![](img/b2359fcaa144d5860558aaccfb7a8fa3_21.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_22.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_23.png)

这里，`power2`是一个接受参数`x`的函数，它返回另一个接受参数`y`的函数，该函数调用`power1`计算`x`的`y`次幂。

使用柯里化函数时，我们需要分别调用每个函数：
```racket
((power2 4) 2) ; 返回 16
```

![](img/b2359fcaa144d5860558aaccfb7a8fa3_25.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_27.png)

首先调用`(power2 4)`返回一个函数，然后调用该函数并传入`2`，最终得到结果16。

![](img/b2359fcaa144d5860558aaccfb7a8fa3_28.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_30.png)

## 函数调用语法

![](img/b2359fcaa144d5860558aaccfb7a8fa3_31.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_33.png)

在Racket中，函数调用的语法始终是`(函数表达式 参数1 参数2 ...)`。其中，函数表达式可以是一个变量名，也可以是其他求值为函数的表达式。

例如：
```racket
(define add +)
(add 2 3) ; 返回 5
```

这里，`add`被绑定到`+`函数，因此调用`(add 2 3)`等价于调用`(+ 2 3)`。

![](img/b2359fcaa144d5860558aaccfb7a8fa3_35.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_36.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_37.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_38.png)

需要注意的是，如果表达式是`if`、`define`或`lambda`等关键字，它们不是函数调用，而是Racket中的特殊构造。

## 总结

![](img/b2359fcaa144d5860558aaccfb7a8fa3_40.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_41.png)

![](img/b2359fcaa144d5860558aaccfb7a8fa3_42.png)

本节课中，我们一起学习了Racket的基础知识。我们掌握了如何定义变量、编写函数以及使用条件语句。通过示例代码，我们了解了Racket的语法特点，如函数调用的括号规则和递归函数的实现方式。此外，我们还简要介绍了柯里化函数的概念及其在Racket中的应用。这些基础知识将为我们后续学习更复杂的Racket概念打下坚实的基础。