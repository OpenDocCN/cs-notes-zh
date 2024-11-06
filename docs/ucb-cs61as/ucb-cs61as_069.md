# calc.rkt

## 概述

在本小节中，我们将玩弄一个用 Racket 编写的计算器程序。

我们的计算器程序将以与 Racket 相同的语法进行算术运算。为什么我们这样做？我们想增加对 Racket 如何评估事物的理解。在下一个实验中，我们将为其添加更多功能，但目前，它只执行算术运算。

您可以从[这里](http://inst.eecs.berkeley.edu/~cs61as/library/calc.rkt)下载该文件。您还可以通过在终端中输入以下内容将其复制到您的课程帐户中：

`cp ~cs61as/lib/calc.rkt .`

注意末尾的'.'。这将把`.rkt`文件复制到当前目录。

## 'READ'函数

在我们深入研究计算器之前，有一个函数我们应该了解：`read`函数。当您调用`(read)`时，它将提示您输入一些��容。

```
> (read)
123
123 
```

在上面的示例中，我们在解释器中输入了`123`。解释器显示的下一个`123`是`read`返回的值。那么它用于什么？试试这个：

```
> (define a (read))
123
a
> a
123 
```

在这里，我们将`a`赋值为您输入的值。因此，当我们再次输入`123`时，我们将该值存储在变量`a`中。尝试下一个更有趣的内容：

```
> (define a (read))
(+ 1 2)
a
> a
(+ 1 2)
> (equal? a '(+ 1 2))
#t 
```

这一次，当解释器询问我们要将什么值放入`a`时，我们输入了`'(+ 1 2)'`。`a`最终的值是`'(+ 1 2)'`而不是 3。下一行测试`a`是否等于带引号的列表`'(+ 1 2)'`。我们可以从中学到什么？**`(read)`接受用户输入作为符号；它们不会被评估。**

有了这个，让我们进入计算器程序！

## Calc：它是如何工作的？

让我们运行程序并了解实际发生了什么。在 Racket 解释器中加载`calc.rkt`（通过输入`(enter! "calc.rkt")`），然后调用函数`(calc)`：

```
> (calc)
calc: 
```

请注意，我们通常的提示符“>”被“calc:”取代。这是一个简单的方法，可以知道您输入的表达式将由`calc.rkt`评估。现在，尝试输入一些算术运算如`(+ 10 20)`，或一些数字如`300`，并进行操作！

它是如何知道如何评估数学运算的？让我们看看`calc`函数的作用。其定义如下：

```
(define (calc)
  (display "calc: ")
  (flush)
  (print (calc-eval (read)))
  (calc)) 
```

第一行说`(display "calc: ")`，告诉解释器在“屏幕”/输出上显示“calc:”。

`flush`告诉解释器显示我们在“屏幕”输出上输入的任何内容（现在可以忽略这一点）。

下一行，`(print (calc-eval (read)))`告诉解释器使用用户输入调用`calc-eval`并打印结果。

最后一行是对`calc`的递归调用，将我们带回开始。这就是**读取-评估-打印-循环（REPL）**：它要求用户输入一些内容，评估它，打印结果，然后循环。

这就是`calc`的全部内容。计算器的魔法发生在`calc-eval`中。

## Calc：数字输入

那么`calc-eval`是做什么的呢？考虑一种情况，我们在`calc`中输入一个数字如下：

```
calc: 42
42 
```

那不是一个非常令人兴奋的结果，但在幕后，许多事情正在互动。因为用户输入为 42，`calc-eval`将被调用为`(print (calc-eval '42))`。（记住`(read)`返回一个带引号的符号。）让我们看看`calc-eval`如何处理这个。它的代码如下。

```
(define (calc-eval exp)
    (cond ((number? exp) exp)
          ((list? exp) 
           (calc-apply (car exp)
                       (map calc-eval (cdr exp))))
          (else (error "Calc: bad expression:" exp)))) 
```

`calc-eval`的主体是一个`cond`，因为形式参数`exp`被调用为 42，第一个条件`(number? exp)`将被满足，`calc-eval`将返回`exp`，即 42。所有数字都被同样对待。这里一个微妙的点是这是基本情况。对于任何算术计算，可以传递的最简单参数都是数字。

## Calc：一个运算符

我们接下来要尝试的表达式是一个单运算符函数调用，如`(+ 1 1)`，`(* 2 3 10)`或`(- 100 50 20 10)`。

```
calc: (* 2 3 10) 
```

这将调用`calc-eval`为`(print (calc-eval '(* 2 3 10)))`。（再次记住`read`将用户输入视为符号。）`calc-eval`如何处理这个？

**测试你的理解**

下面为您复制了`calc-eval`代码：

```
(define (calc-eval exp)
  (cond ((number? exp) exp)
        ((list? exp)
         (calc-apply (car exp)
                     (map calc-eval (cdr exp))))
        (else (error "Calc: bad expression:" exp)))) 
```

当我们调用以下表达式时会发生什么：

```
(calc-eval '(* 2 3 10)) 
```

## Calc-Apply

我们将简单表达式（* 2 3 10）传递给`calc`，作为`(calc-apply '* '(2 3 10))`传递给`calc-apply`。接下来会发生什么？这是`calc-apply`的代码：

```
(define (calc-apply fn args)
  (cond ((eq? fn '+) (accumulate + 0 args))
        ((eq? fn '-) (cond ((null? args) (error "Calc: no args to -"))
                           ((= (length args) 1) (- (car args)))
                           (else (- (car args) (accumulate + 0 (cdr args))))))
        ((eq? fn '*) (accumulate * 1 args))
        ((eq? fn '/) (cond ((null? args) (error "Calc: no args to /"))
                           ((= (length args) 1) (/ (car args)))
                           (else (/ (car args) (accumulate * 1 (cdr args))))))
        (else (error "Calc: bad operator:" fn)))) 
```

注意`calc-apply`中的形式参数`fn`只接受 4 个值：`'+', `'-', `'*', 或`'/`。其他任何值都会导致错误。`Calc-apply`可以描述为"找到函数是什么，然后做正确的事情"。在这种情况下，因为`fn`是`'*'，`calc-apply`将在`args`上调用`accumulate`，即`'(2 3 10)`，并返回`60`。

说服自己，对于`fn`的 4 个可接受参数和任何数字列表`args`，`calc-apply`都会执行正确的计算。

## Calc：嵌套运算符

**测试你的理解**

让我们通过调用更复杂的表达式来测试我们的计算器程序。下面为您复制了`calc-eval`代码：

```
(define (calc-eval exp)
  (cond ((number? exp) exp)
        ((list? exp)
         (calc-apply (car exp)
                     (map calc-eval (cdr exp))))
        (else (error "Calc: bad expression:" exp)))) 
```

当我们调用以下表达式时会发生什么：

```
(calc-eval '(+ 4 5 (* 10 2) 7)) 
```

## 复合表达式

那么我们的计算器程序如何评估复合表达式？它在更简单的表达式上调用`calc-eval`，并递归重复这个过程，直到表达式足够简单（只是数字）以便简单地返回表达式。我们知道`calc-eval`和`calc-apply`适用于数字和具有一个运算符的表达式。其他一切都只是组合。相信递归！

**测试你的理解**

在`calc`中，以下哪个不是可能的调用？

## 要点

在本小节中，您了解了`calc.rkt`，它接受一个算术表达式（操作）作为符号，并像简化的科学计算器一样对其进行评估。
