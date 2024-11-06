# 运行评估器

## 运行评估器

让我们看看 Scheme 如何运行评估器。到目前为止，我们已经学习了如何使用`mc-eval`和`mc-apply`评估 Scheme 表达式。那么评估器程序是如何运行的呢？

我们的评估器程序的作用是将所有表达式简化为原始过程的应用。因此，我们运行评估器所需的全部就是创建一个机制，使用底层 Scheme 系统进行原始过程的应用。

每个原始过程名称都必须有一个绑定，这样当`mc-eval`评估原始应用的操作数时，它将找到一个对象传递给`mc-apply`。因此，我们设置一个全局环境，将唯一对象与我们将要评估的表达式中可能出现的原始过程名称相关联（例如，我们将`+`绑定到具有相同名称的底层 Scheme 过程）。全局环境还包括`true`和`false`符号的绑定，以便它们可以用作要评估的表达式中的变量。

```
(define (setup-environment)
  (let ((initial-env
         (extend-environment (primitive-procedure-names)
                             (primitive-procedure-objects)
                             the-empty-environment)))
    (define-variable! 'true true initial-env)
    (define-variable! 'false false initial-env)
    initial-env))
(define the-global-environment (setup-environment)) 
```

为了方便运行元循环评估器，我们提供了一个**驱动循环**，模拟底层 Scheme 系统的读取-评估-打印循环（或 REPL）。它打印一个**提示**，读取一个输入表达式，在全局环境中评估这个表达式，并打印结果。我们在每个打印的结果前加上一个**输出提示**，以区分表达式的值和可能打印的其他输出。

```
(define input-prompt ";;; M-Eval input:")
(define output-prompt ";;; M-Eval value:")
(define (driver-loop)
  (prompt-for-input input-prompt)
  (let ((input (read)))
    (let ((output (mc-eval input the-global-environment)))
      (announce-output output-prompt)
      (user-print output)))
  (driver-loop))
(define (prompt-for-input string)
  (newline) (newline) (display string) (newline))

(define (announce-output string)
  (newline) (display string) (newline)) 
```

我们使用一个特殊的打印过程`user-print`，以避免打印复合过程的环境部分，这可能是一个非常长的列表（甚至可能包含循环）。

```
(define (user-print object)
  (if (compound-procedure? object)
      (display (list 'compound-procedure
                     (procedure-parameters object)
                     (procedure-body object)
                     '(procedure-env>))
      (display object))) 
```

现在我们只需要初始化全局环境并启动驱动循环就可以运行评估器。以下是一个示例交互：

```
(define the-global-environment (setup-environment))
(driver-loop)
;;; M-Eval input:
(define (append x y)
  (if (null? x)
      y
      (cons (car x)
            (append (cdr x) y))))
;;; M-Eval value:
ok
;;; M-Eval input:
(append '(a b c) '(d e f))
;;; M-Eval value:
(a b c d e f) 
```

*等等，我还是不明白。我们如何用 Scheme 编写的评估器来评估 Scheme 代码？*

这是因为 Scheme 足够强大，可以处理程序作为数据，并让我们构建既是分层又是循环的数据结构。我在下一节给你一个类比。

## 数据作为程序

要理解用 Scheme 编写的解释器解释 Scheme 表达式，可以将程序视为抽象机器的描述。例如，您可以将计算阶乘的程序视为：

```
(define (factorial n)
  (if (= n 1)
      1
      (* (factorial (- n 1)) n))) 
```

描述了一个包含递减、乘法和相等测试部分的机器，还有一个两位置开关和另一个阶乘机器。（阶乘机器是无限的，因为它内部包含另一个阶乘机器 -- 递归！）因此，这台机器看起来像这样：

![](img/e573237fc15c3c41936fac8959325d54.jpg)

像`阶乘`一样，评估器是一个非常特殊的机器，它以其他机器的描述作为输入，然后配置自身以模拟给定的机器。例如，如果我们给评估器阶乘的定义，评估器将模拟它并能够计算阶乘。

![](img/747dece8f01e6a003704c21c47f7d1e5.jpg)

所以我们的评估器只是一个模仿所有其他机器的通用机器！

如果你想了解更多关于这些机器的信息，请询问第 5 单元。

## 要点

在这一小节中，你学会了评估器的工作原理。

## 接下来是什么？

去做你的家庭作业！你也应该开始进行第 4 个项目，你将学习 Python 编程语言。
