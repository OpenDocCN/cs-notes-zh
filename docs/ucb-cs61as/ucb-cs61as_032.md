# 过程作为黑盒抽象

## 过程作为抽象

到目前为止，我们已经定义了单独执行单个计算的函数（例如`square`，`fib`和`factorial`）。通过组合不同的函数，每个函数处理原始问题的一个子问题，您可以创建一个更复杂的函数。我们将在本节中构建一个此类函数的示例，并探讨“函数作为[抽象](https://edge.edx.org/courses/uc-berkeley/cs61as-1x/SICP/wiki/cs61as-1x/abstraction/)”的概念。

## 扩展示例：最大正方形

查理有大量的方块（而不是条形）巧克力，他想通过将这些方块组织成尽可能大的正方形排列来向朋友展示！所以假设查理有 13 块巧克力。然后最大的正方形排列是 3x3 = 9（左图所示），剩下 4 块。

![chocolate square](img/d4f23e4eb6e1b9f02a069308c23da42f.jpg)

查理想知道“在给定一定数量的巧克力块的情况下，我的正方形的边可以有多大？”我们可以将这个问题表示为一个函数，`(largest-square total guess)`。函数`largest-square`接受两个参数：`total`，表示查理有多少块巧克力（在上面的示例中，`total`为 13），以及`guess`，表示您对最大边长的初始猜测。此函数将输出您的巧克力正方形可以拥有的最大边长（在本例中为 3）。我们将把这个函数分解为子问题，并在本节的其余部分组合所有这些部分。

## 最大正方形：概述

可能看起来奇怪的一件事是多余的参数`guess`。您可以编写一个只使用`total`参数完成相同工作的函数。我们包含了`guess`以增加问题的复杂性。将`guess`视为查理对他认为自己的边可以有多大的估计。在我们的原始示例中，有 13 块巧克力，假设查理认为最大边长为 2：

| guess | leftover | next guess |
| --- | --- | --- |
| 2 | 13-4= 9 | 2+1= 3 |
| 3 | 13-9= 4 | 3+1= 4 |
| 4 | 13-16= -3 | 4+1= 5 |

对于每次对`largest-square`的函数调用，如`(largest-square 13 2)`，我们将检查当前的猜测（在本例中为 2）是否足够好。我们如何检查我们的猜测是否足够好？如果我们的下一个猜测使用的巧克力块多于我们有的可用的数量，则猜测足够好。如果我们可以做出更好的猜测，那么我们将使用下一个猜测并递归调用`largest-square`。

## 最大正方形：骨架代码

根据我们在上一页的直觉，我们可以规范化我们的函数定义。如果您的`guess`足够好，请返回您的`guess`。如果您可以有更好的`guess`，请使用更好的`guess`调用`largest-square`

```
 (define (largest-square total guess)
    (if (good-enough? total guess)
        guess
        (largest-square total (next-guess guess)))) 
```

如果您按原样输入上述定义（没有定义'good-enough?'和'improve-guess'），会发生什么？如果之后您键入（largest-square 13 2），会发生什么？

*"等等，你刚刚定义了一个函数，但它调用了其他尚未定义的函数！我们还没有定义'good-enough?'或'improve-guess'！"*

是的，内部函数的定义是不完整的，但请注意，我们（程序员）可以**理解**函数在做什么！我们已经将找到'largest-square'的问题分解为一些小问题，比如'足够接近吗？'和'改进我们的猜测'。我们可以以不同的方式分解代码，比如每 3 行，每 5 行，但是每个子问题将没有一个*可识别*的任务。将它们分解为一个连贯的、可识别的任务是至关重要的。

这将是我们最后会再次讨论的一个关键思想，但首先让我们完成定义。

## 最大方块：子问题

是时候做必要的工作让函数正常工作了！

```
 (define (largest-square total guess)
    (if (good-enough? total guess)
        guess
        (largest-square total (next-guess guess)))) 
```

问题：

我们想要定义接受两个输入`total`（你拥有的巧克力块的总数）和`guess`（代表你当前的猜测）的函数`good-enough?`。它应该根据下一个整数是否大于`total`来报告`#t`或`#f`

`(good-enough? 13 3)` 应返回 `#t`。下一个猜测是 3+1=4，需要 16 个方块，超过了 13，总数

`(good-enough? 13 2)` 应返回 `#f`。下一个猜测是 2+1=3，需要 9 个方块，仍然低于 13，总数

`(good-enough? 100 11)` 应返回 `#t`。下一个猜测��11+1=12，需要 144 个方块，超过了 100，总数

`(good-enough? 100 10)` 应返回 `#t`。下一个猜测是 10+1=11，需要 121 个方块，超过了 100，总数

`(good-enough? 100 9)` 应返回 `#f`。下一个猜测是 9+1=10，需要 100 个方块，总共是 100

选择应填入空白处的代码：

```
(define (good-enough? total guess))
    ________________________)
```

<ans text="(< total (next-guess guess))" explanation="我们必须对下一个猜测进行平方。"></ans>

接下来，我们定义接受你当前猜测的函数`next-guess`，并返回一个新的数字以供尝试下一个。

`(next-guess 1)` ;;应返回 2

`(next-guess 3)` ;;应返回 4

选择应填入空白处的代码：

```
(define (next-guess guess)
    ________________________)
```

## 函数作为抽象

我们从方形巧克力的例子中可以学到什么？记住，当我们*仅仅*定义`largest-square`时，我们可以理解过程在做什么，而不需要知道`good-enough?`或`next-guess`是如何实现的。我们可以将这些函数视为抽象；我们知道它们会输出什么，但我们不关心**如何**实现。只要它们做正确的事情，我们就满意！

你也可以将这种方法应用到现实生活中。当我们打开电视时，我们从不考虑"哦，电视之所以工作是因为我们将电子射到屏幕上，这些电子由电磁铁引导，这样我们就可以观看东西！"。我们通常更多地考虑"如果我按这个按钮，我就可以看电影"。我们不需要知道电视是如何工作的才能使用它；它的实现对我们来说是抽象的

## 内部定义

我们已经定义了一个相对复杂的过程，它依赖于其他过程。现在我们将看看是否可以改进代码的组织！

请注意，我们对`good-enough?`和`next-guess`的定义非常特定于`largest-square`问题；我们几乎找不到其他可能使用这些函数的函数。此外，当查理想要找到最大的正方形时，他将调用`largest-square`函数，而不会直接操作这两个辅助函数。在这种情况下，最好组织我们的代码，以便只有`largest-square`可以访问这两个辅助函数

如何做到这一点？我们可以在`largest-square`的主体内定义函数如下：

```
(define (largest-square total guess)
    (define (next-guess guess) (+ guess 1))
    (define (good-enough? total guess)
        (< total (square (next-guess guess))))
    (if (good-enough? guess)
        guess
        (largest-square total (next-guess guess))))
```

假设你只定义了上面的过程，当我们调用`(next-guess 4)`时会发生什么？

## 变量的作用域

```
(define (largest-square total guess)
    (define (next-guess guess) (+ guess 1))
    (define (good-enough? total guess)
        (< total (square (next-guess guess))))
    (if (good-enough? guess)
        guess
        (largest-square total (next-guess guess))))
```

之前我们提到`good-enough?`和`next-guess`函数仅在函数`largest-square`内定义。现在这些函数在`largest-square`内部，我们可以将其他多余的部分从函数中取出。请注意，`next-guess`和`good-enough?`接受传递给`larger-square`的相同`total`和`guess`。去除两个辅助函数中的多余参数结果为：

```
(define (largest-square total guess)

        (define (next-guess) (+ guess 1))
        (define (good-enough?)
            (< total (square (next-guess))))
        (if (good-enough?)
            guess
    (largest-square total (next-guess)))) 
```

如何跟踪函数可以访问什么，而不能访问什么？我们将在第 3 单元中花费大量时间来解决这个问题。当一个函数在另一个函数内定义时，内部函数可以访问外部函数的变量和参数。因为`next-guess`是在`largest-square`内定义的，所以`next-guess`可以访问`largest-square`的参数`total`和`guess`。

如果你觉得记忆提示有用，请将外部函数视为父母，将内部函数视为孩子。父母可以借给孩子他们的东西（比如手机），但孩子不会让父母拿走他的玩具。

![](http://4.bp.blogspot.com/-yfy4u4_1Wb4/TxbQrWKytMI/AAAAAAAAIxs/Hi9b9LWDPGY/ s400/cute-baby-playing-handphone-448x336.jpg) ![](http://kidsbesttoys.net/wp- content/images/lamaze-tug-and-play-knot-block-baby-toy-3.jpg)
