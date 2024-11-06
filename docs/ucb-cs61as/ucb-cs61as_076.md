# Racket-1

## 入门指南

通过在终端中输入以下内容，将 Racket-1 解释器的源代码复制到当前目录：

```
cp ~cs61as/lib/racket1.rkt . 
```

或者，你可以在此处下载代码 [here](http://inst.eecs.berkeley.edu/~cs61as/library/racket1.rkt)。

要启动 Racket-1，在 Racket 中输入以下内容：

```
;; Load Racket-1 file
(require "racket1.rkt")

;; Start interpreter
(racket-1) 
```

熟悉 Racket-1，通过评估一些表达式来了解它。尝试输入常规的 Racket 表达式，看看会发生什么！

你可能会注意到，在 Racket-1 中，你不能做到在正常的 Racket 中可以做的一切：

+   你有所有用于算术和列表操作的 Racket 原语。

+   你有`lambda`，但没有高阶函数。

+   你没有`define`。

要停止 Racket-1 解释器并返回 Racket，只需评估一个非法表达式，如`()`。

## 解释器是什么？

为了在计算机上运行程序，计算机中的某些东西必须理解代码的意图，执行必要的计算，然后返回结果。这个东西充当了程序员思想和计算机硬件之间的中介。其中一种中介是**解释器**。

`racket` 是 Racket 的解释器。它将 Racket 源代码转换为计算机指令，然后告诉计算机执行它们。它具有读取输入和显示输出的功能。

Racket-1 也是一个解释器。它适用于 Racket 的纯函数子集。Racket-1 是用 Racket 编写的这个事实很有趣但并不重要。我们也可以用其他语言（比如 Python）编写 Racket-1，但对我们作为用户真正重要的是解释器*做*什么，而不是它的源代码是什么样子。

我们将在接下来的几堂课中更多地讨论解释器。现在，让我们讨论一下 Racket-1 的工作原理。

## Racket-1 是如何工作的？

**racket-1**

racket-1 遵循以下规则：

要评估一个组合：

1.  评估组合的子表达式

1.  将最左边子表达式（运算符）的值应用于其他子表达式（操作数）的值。要将复合过程应用于参数，用每个形式参数替换对应的参数来评估过程的主体。

(SICP: [1.1.3](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-10.html#%_sec_1.1.3)，[1.1.5](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-10.html#%_sec_1.1.5))

示例：

```
Racket> ((lambda (x) (* x x)) (- 2 (* 4 3)))
100 
```

这里发生了什么？根据规则，手动逐步评估。

**读-求值-打印循环**

解释器需要一个循环，允许它执行它所做的所有事情。每次键入命令时，racket-1 解析和执行您的输入，返回输出，然后等待另一个命令。这称为读取-求值-打印循环（REPL）。

这就是全部的 racket-1：

```
(define (racket-1)
    (newline)
    (display "Racket-1: ")
    (flush-output)
    (print (eval-1 (read)))
    (newline)
    (racket-1)
) 
```

前三行简单地打印提示符“Racket-1: ”。第四行是重要的一行。在这里，输入被读取、解析并发送到 eval-1 进行评估。在 eval-1 处理执行代码后，打印其结果。最后，racket-1 调用自身重新启动该过程，显示另一个“Racket-1: ”并接受另一个命令。

**Eval-1**

Eval-1 负责返回作为 exp 传递的任何计算的结果。它由一个 cond 组成，其中包含它可以解释和计算的每个子句。请注意，特殊形式是在 Eval-1 中捕获和处理的。

```
(define (eval-1 exp)
  (cond ((constant? exp) exp)
        ((symbol? exp) (eval exp))      ; use underlying Racket's EVAL
        ((quote-exp? exp) (cadr exp))
        ((if-exp? exp)
         (if (eval-1 (cadr exp))
             (eval-1 (caddr exp))
             (eval-1 (cadddr exp))))
        ((lambda-exp? exp) exp)
        ((pair? exp) (apply-1 (eval-1 (car exp))      ; eval the operator
                              (map eval-1 (cdr exp))))
        (else (error "bad expr: " exp)))) 
```

**Apply-1**

当需要将一个过程应用于其参数时，eval-1 会调用 apply-1。Apply-1 处理两种情况：

1.  racket-1 原语。在这个上下文中，原语是指非用户定义的过程。所有 Racket 过程都是 racket-1 原语。

1.  Lambda 函数，或用户定义的过程。

```
(define (apply-1 proc args)
  (cond [(procedure? proc)      ; use underlying Racket's APPLY
          (apply proc args)]
        [(lambda-exp? proc)
          (eval-1 (substitute (caddr proc)   ; the body
                              (cadr proc)    ; the formal parameters
                              args           ; the actual arguments
                              '()))]         ; bound-vars
        [else (error "bad proc: " proc)])) 
```

**互递归（在 racket-1 中）**

![eval](img/eval.png)

## 与 Racket-1 练习

好吧，即使你刚刚完成盯着代码看了一会儿，你可能还没有完全理解其中的所有内容。让我们通过一些练习来更好地了解这个程序。

1.  手动详细跟踪 racket-1 如何处理以下过程调用：

    ```
     ((lambda (x) (+ x 3)) 5) 
    ```

特别是，逐步跟踪 racket-1 必须调用的所有函数来评估此表达式。

1.  尝试发明高阶过程；由于没有 define，你将不得不使用 Y-组合器技巧，就像这样：

    ```
    Racket-1: 
    ((lambda (f n)  ; this lambda is defining MAP 
        ((lambda (map) (map map f n)) 
        (lambda (map f n) 
            (if (null? n) 
                '() 
                (cons (f (car n)) (map map f (cdr n))) )) )) ;end of lambda defining MAP 
    first              ; the argument f for MAP
    '(the rain in spain)) ; the argument n for MAP

    (t r i s) 
    ```

1.  由于所有的 Racket 原语在 racket-1 中都是自动可用的，你可能会认为你可以使用 Racket 的原始 map 函数。尝试这些例子：

    ```
    Racket-1: 
    (map first '(the rain in spain)) 
    Racket-1: 
    (map (lambda (x) (first x)) '(the rain in spain)) 
    ```

解释结果。

1.  修改解释器以添加 `and` 特殊形式。测试你的工作。确保一旦计算出一个 false 值，你的 `and` 就会返回 `#f`，而不会继续评估任何其他参数。
