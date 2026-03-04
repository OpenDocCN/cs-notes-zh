# 121：使用 define-syntax 定义 Racket 宏 🧩

![](img/26765173691d36979a273bb4b4d17667_1.png)

在本节课中，我们将学习如何在 Racket 中定义自己的宏。我们将通过三个具体的例子，逐步讲解 `define-syntax` 和 `syntax-rules` 的使用方法，并理解宏与函数的区别。

## 概述 📋

宏是一种强大的元编程工具，它允许我们在代码被求值之前，根据自定义的语法规则对其进行转换。与函数不同，宏的参数不会被立即求值，这使得宏能够实现函数无法完成的任务，例如延迟求值或创建新的控制结构。我们将通过定义三个宏来掌握其基本用法。

## 定义第一个宏：`my-if` 🔄

首先，我们定义一个名为 `my-if` 的宏，其语法类似于 Racket 内置的 `if`，但要求使用 `then` 和 `else` 关键字。用户将能够这样编写代码：`(my-if e1 then e2 else e3)`。

以下是定义 `my-if` 宏的代码：

```racket
(define-syntax my-if
  (syntax-rules (then else)
    [(my-if e1 then e2 else e3)
     (if e1 e2 e3)]))
```

**代码解析：**
*   `define-syntax` 用于定义宏，而不是变量或函数。
*   `my-if` 是宏的名称。
*   `syntax-rules` 后面跟着一个列表 `(then else)`，这列出了宏中除了宏名 `my-if` 之外的特殊关键字。
*   方括号 `[...]` 内定义了一个转换规则。它匹配形如 `(my-if e1 then e2 else e3)` 的语法模式，并将其转换为 `(if e1 e2 e3)`。这里的 `e1`, `e2`, `e3` 是模式变量，代表任意表达式。

**使用示例：**
```racket
(my-if true then (+ 3 4) else 72) ; 展开为 (if true (+ 3 4) 72)，结果为 7
```
如果用户忘记写 `then` 或 `else`，Racket 会报错，因为提供的语法不匹配宏定义的任何规则。

上一节我们介绍了如何定义一个简单的条件判断宏。接下来，我们看一个更简单的例子，它用于“注释掉”代码。

## 定义第二个宏：`comment-out` 🗑️

`comment-out` 宏的目的是完全忽略第一个表达式，只求值第二个表达式。例如，`(comment-out (car null) (+ 3 4))` 应该只计算 `(+ 3 4)` 并返回 7，而不会触发 `(car null)` 的错误。

以下是 `comment-out` 宏的定义：

```racket
(define-syntax comment-out
  (syntax-rules ()
    [(comment-out e1 e2)
     e2]))
```

**代码解析：**
*   这个宏没有额外的关键字，因此 `syntax-rules` 后的列表是空的 `()`。
*   规则匹配 `(comment-out e1 e2)` 模式，并直接将其替换为第二个表达式 `e2`。注意，`e2` 外面没有括号，这意味着它直接是表达式本身，而不是一个函数调用。

**使用示例：**
```racket
(comment-out (car null) (+ 3 4)) ; 展开为 (+ 3 4)，结果为 7。 (car null) 被安全地丢弃。
```

![](img/26765173691d36979a273bb4b4d17667_3.png)

我们已经看到了两个在语法层面进行替换的宏。现在，让我们探讨一个更强大的应用：重新实现延迟求值。

## 定义第三个宏：`my-delay` ⏳

在之前学习“承诺”（promises）时，我们使用函数实现了 `my-delay` 和 `my-force` 来模拟惰性求值。`my-delay` 函数接收一个无参函数（thunk），并返回一个包含该 thunk 的特定数据结构。

然而，使用函数时，调用者必须显式地创建一个 thunk：`(my-delay (lambda () e))`。我们可以定义一个宏，让调用者只需写 `(my-delay e)`，宏会自动将其包装在 thunk 中。

![](img/26765173691d36979a273bb4b4d17667_5.png)

以下是 `my-delay` 宏的定义：

```racket
(define-syntax my-delay
  (syntax-rules ()
    [(my-delay e)
     (mcons #f (lambda () e))]))
```

**代码解析：**
*   宏匹配 `(my-delay e)`。
*   它将其展开为 `(mcons #f (lambda () e))`。这里，表达式 `e` 被放入一个 `(lambda () ...)` 中，从而延迟了它的求值。
*   **关键点**：这**无法**用函数实现。因为 Racket 的函数在调用前总会先对所有参数进行求值。如果 `my-delay` 是函数，那么 `e` 在传入时就会被计算，失去了延迟的意义。宏在语法扩展阶段就将 `e` 放入了 thunk，因此解决了这个问题。

**注意**：定义了此宏后，调用方式从 `(my-delay (lambda () e))` 变为 `(my-delay e)`。如果程序员错误地写了前者，将会产生一个“双重 thunk”，导致需要调用两次才能得到结果。

那么，`my-force` 也应该定义为宏吗？

![](img/26765173691d36979a273bb4b4d17667_7.png)

## 为什么 `my-force` 应该保持为函数 ❌

`my-force` 的功能是：接收一个 promise（即 `my-delay` 返回的 `mcons`），检查其是否已被求值，若未求值则强制执行其中的 thunk 并缓存结果。

![](img/26765173691d36979a273bb4b4d17667_9.png)

我们可以尝试将其定义为宏：

```racket
; 版本一：有问题的宏
(define-syntax my-force
  (syntax-rules ()
    [(my-force e)
     (if (mcar e)
         (mcdr e)
         (begin (set-mcar! e #t)
                (set-mcdr! e ((mcdr e)))
                (mcdr e)))]))
```

**问题**：如果调用是 `(my-force (begin (print “hi”) p))`，那么 `(begin (print “hi”) p)` 这个表达式会在宏展开时，被复制到上述 `if` 语句的多个位置（`e` 出现的地方），导致副作用（打印 “hi”）发生多次，这违背了“表达式只应求值一次”的原则。

我们可以修复这个问题，引入一个局部变量来保存求值结果：

![](img/26765173691d36979a273bb4b4d17667_11.png)

```racket
; 版本二：修复多次求值的宏
(define-syntax my-force
  (syntax-rules ()
    [(my-force e)
     (let ([x e]) ; 先对 e 求值一次，结果绑定到 x
       (if (mcar x)
           (mcdr x)
           (begin (set-mcar! x #t)
                  (set-mcdr! x ((mcdr x)))
                  (mcdr x))))]))
```

这个版本行为正确了。但是，**这并没有带来任何额外的好处**。它的行为和对应的函数实现完全一样。既然函数已经能完美、清晰地表达这个逻辑，就没有必要使用更复杂、更容易出错的宏来实现。因此，`my-force` 应保持为函数。

## 总结 🎯

![](img/26765173691d36979a273bb4b4d17667_13.png)

![](img/26765173691d36979a273bb4b4d17667_14.png)

本节课我们一起学习了 Racket 宏的基础知识：
1.  我们使用 `define-syntax` 和 `syntax-rules` 来定义宏。
2.  宏在语法层面进行模式匹配和替换，其参数不会预先求值。
3.  我们通过 `my-if`、`comment-out` 和 `my-delay` 三个例子实践了宏的定义。
4.  我们认识到宏虽然强大，但需要谨慎设计，特别是要注意表达式可能被求值的次数（如第一个有问题的 `my-force` 宏所示）。
5.  判断是否使用宏的一个重要原则是：如果函数能够实现相同的语义，通常应优先使用函数，因为其行为更易于推理。

![](img/26765173691d36979a273bb4b4d17667_16.png)

宏是创造领域特定语言和强大抽象的工具，但同时也要求程序员对求值顺序有清晰的理解。在接下来的课程中，我们将继续深入探讨宏的更多细节和注意事项。