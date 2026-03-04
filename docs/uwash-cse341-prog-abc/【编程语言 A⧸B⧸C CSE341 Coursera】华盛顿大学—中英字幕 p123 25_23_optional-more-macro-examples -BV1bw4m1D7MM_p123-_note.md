# 编程语言 A/B/C CSE341：25：更多宏示例 🧩

![](img/90b9a8d569dde3a2ec454e3cded20c1b_1.png)

在本节课中，我们将通过几个更复杂的宏示例来结束对宏的学习。这些示例将展示一些新特性，并将我们之前见过的概念组合起来。我们将学习如何创建接受多个参数、具有多个匹配分支，甚至能够递归调用自身的宏。

---

![](img/90b9a8d569dde3a2ec454e3cded20c1b_3.png)

## 循环宏示例 🔄

![](img/90b9a8d569dde3a2ec454e3cded20c1b_5.png)

上一节我们介绍了宏的基本概念，本节中我们来看看一个自定义的循环宏 `for`。这个宏的目的是展示如何处理多个参数，并控制其中哪些需要被重新求值，哪些不需要。

以下是 `for` 宏的使用示例：
```racket
(for 7 11 do (print "hi"))
```
这段代码会打印五次 “hi”，因为 `11 - 7 = 5`。我们也可以在参数位置使用任意表达式。

![](img/90b9a8d569dde3a2ec454e3cded20c1b_7.png)

假设我们有三个函数：
```racket
(define (f x) (print "A") x)
(define (g x) (print "B") x)
(define (h x) (print "C") x)
```
现在执行：
```racket
(for (f 7) (g 11) do (h 9))
```
它会按顺序打印一次 “A”、一次 “B” 和五次 “C”。这是用户期望的 `for` 循环行为。

![](img/90b9a8d569dde3a2ec454e3cded20c1b_8.png)

为了实现正确的求值顺序和次数，我们需要在定义宏时格外小心。`for` 宏的展开形式如下：
```racket
(define-syntax for
  (syntax-rules (do)
    ((for low high do body)
     (let ((l low)
           (h high))
       (letrec ((loop (lambda (i)
                        (if (< i h)
                            (begin
                              body
                              (loop (+ i 1)))
                            #f))))
         (loop l))))))
```
这个宏的核心思想是：
1.  使用 `let` 表达式按顺序对 `low` 和 `high` 求值一次，并将结果绑定到变量 `l` 和 `h` 上，避免重复求值。
2.  定义一个递归辅助函数 `loop`，在循环中执行 `body` 部分，执行次数为 `high - low`。

如果起始值大于结束值，例如 `(for 11 7 do (print “hi”))`，循环体将一次也不执行，这也是符合预期的行为。

![](img/90b9a8d569dde3a2ec454e3cded20c1b_10.png)

---

![](img/90b9a8d569dde3a2ec454e3cded20c1b_11.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_12.png)

## 多分支宏示例 🧱

![](img/90b9a8d569dde3a2ec454e3cded20c1b_14.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_15.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_16.png)

接下来，我们看一个名为 `let2` 的宏，它是 `let` 的一个变体。这个示例将展示如何让一个宏拥有多个匹配分支（即多个 `syntax-rules` 情况）。

![](img/90b9a8d569dde3a2ec454e3cded20c1b_18.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_19.png)

`let2` 的用法是减少定义变量时所需的括号。比较一下：
*   标准 `let`: `(let ((x 1) (y 2)) (+ x y))`
*   使用 `let2`: `(let2 x 1 y 2 (+ x y))`

`let2` 也支持定义更少或零个变量：
```racket
(let2 x 1 (+ x 5)) ; 定义一个变量
(let2 3)           ; 定义零个变量，直接返回3
```

![](img/90b9a8d569dde3a2ec454e3cded20c1b_21.png)

`let2` 宏的定义如下，它包含了三个不同的匹配分支：
```racket
(define-syntax let2
  (syntax-rules ()
    ; 情况1：零个绑定
    ((let2 () body) body)
    ; 情况2：一个绑定
    ((let2 (var1 val1) body)
     (let ((var1 val1)) body))
    ; 情况3：两个绑定
    ((let2 (var1 val1) (var2 val2) body)
     (let ((var1 val1))
       (let ((var2 val2))
         body)))))
```
每个分支匹配不同数量的参数，并将其展开为对应的标准 `let` 表达式。

如果用户错误地使用了宏，例如提供了三个绑定 `(let2 x 1 y 2 z 3 (+ x y z))`，由于没有匹配的分支，Racket 会报告一个“语法错误：`let2` 匹配失败”的信息。

![](img/90b9a8d569dde3a2ec454e3cded20c1b_23.png)

一个有趣的情况是，如果用户提供了格式错误的参数，例如 `(let2 3 4 5 (+ 3 4))`。这个输入**能**匹配第三个分支（它被解析为 `var1=3, val1=4, var2=5, val2=(+ 3 4)`），但在展开后，会产生一个无效的 `let` 表达式 `(let ((3 4)) …)`。此时，错误信息将是关于 `let` 的语法错误（例如“期望一个标识符，但得到 3”），而不是关于 `let2` 的。这是使用宏时的一个常见问题：错误可能发生在展开后的代码中。

![](img/90b9a8d569dde3a2ec454e3cded20c1b_25.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_26.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_28.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_29.png)

---

## 递归宏示例 ♾️

![](img/90b9a8d569dde3a2ec454e3cded20c1b_31.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_33.png)

最后，我们来看一个最复杂的例子：递归宏。我们将实现一个自己的 `let*`（假设 Racket 本身没有提供）。

递归宏允许宏在其展开式中调用自身。我们定义的宏叫 `my-let*`。

`my-let*` 的用法应与标准 `let*` 一致：
```racket
(my-let* ((x 1) (y (+ x 1))) (+ x y)) ; 应返回 3
```

其定义如下：
```racket
(define-syntax my-let*
  (syntax-rules ()
    ; 基本情况：绑定列表为空
    ((my-let* () body) body)
    ; 递归情况：至少有一个绑定
    ((my-let* ((var0 val0) . rest) body)
     (let ((var0 val0))
       (my-let* rest body)))))
```
这个宏有两个分支：
1.  **基本情况**：当绑定列表为空时，直接执行 `body`。
2.  **递归情况**：使用模式 `((var0 val0) . rest)` 匹配第一个绑定和剩余绑定列表（`…` 是 Racket 宏中用于匹配“一个或多个”的特殊语法）。展开时，它创建一个 `let` 绑定第一个变量，然后在它的主体中**递归调用** `my-let*` 来处理剩余的绑定。

![](img/90b9a8d569dde3a2ec454e3cded20c1b_35.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_37.png)

通过这种递归展开，我们就能用基本的 `let` 构造出 `let*` 的语义。

需要注意的是，递归宏非常强大，但如果编写不当（例如形成无限递归展开），程序在运行前就会在宏展开阶段失败。因此必须谨慎使用。

![](img/90b9a8d569dde3a2ec454e3cded20c1b_39.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_40.png)

---

## 总结 📝

本节课中我们一起学习了三个高级宏的示例：
1.  **`for` 循环宏**：演示了如何控制多个参数的求值顺序和次数，确保用户代码按预期执行。
2.  **`let2` 多分支宏**：展示了如何为一个宏定义多个 `syntax-rules` 分支，以处理不同数量的参数，并讨论了宏使用错误时可能出现的错误信息问题。
3.  **`my-let*` 递归宏**：介绍了最强大的递归宏概念，通过宏自身调用自身，实现了 `let*` 的功能，体现了宏在扩展语言语法方面的强大能力。

![](img/90b9a8d569dde3a2ec454e3cded20c1b_42.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_44.png)

通过这些例子，我们看到了宏如何能够创造新的控制结构、简化语法，并在编译时生成复杂的代码。这标志着我们对 Racket 宏系统的探索告一段落。