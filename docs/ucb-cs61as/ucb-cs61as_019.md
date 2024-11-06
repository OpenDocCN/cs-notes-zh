# 什么是递归

**递归**是一种编写解决某些类型问题的过程的方法。这些问题的解决方案取决于相同问题的较小实例的解决方案。通常情况下，递归让我们一遍又一遍地重复相同的过程。看起来有点像这样：

![](http://caseelse.net/wp-content/uploads/2008/05/recursionagain.jpg)

递归过程的特殊之处在于，为了调用该过程，我们需要让该过程调用自身，这将不得不调用自身，这将--让我们去看一个例子。

## 例子：阶乘

在数学中，非负整数[mathjaxinline]n[/mathjaxinline]的阶乘，用[mathjaxinline]n![/mathjaxinline]表示，是小于或等于 n 的所有正整数的乘积。例如，[mathjaxinline]3! = 3 * 2 * 1[/mathjaxinline]。此外，根据定义，[mathjaxinline]0! = 1[/mathjaxinline]。

我们如何在 Racket 中编写`factorial`过程？这是一个挑战，因为我们想要相乘的数字取决于我们想要找到阶乘的数字，*参数*。

因此，我们将使用递归。让我们将其分为两种可能情况：

+   如果[mathjaxinline]n ≥ 1[/mathjaxinline]，那么[mathjaxinline]n! = n * (n-1)![/mathjaxinline]

+   如果[mathjaxinline]n = 0[/mathjaxinline]，那么[mathjaxinline]n! = 1[/mathjaxinline]

递归在很大程度上依赖于*条件语句*。如果我们已经完成，返回某个值。否则，继续递归。对于阶乘的例子，我们递归直到达到[mathjaxinline]n = 0[/mathjaxinline]，然后返回 1。我们可以利用这一点来编写`factorial`。看看下面的 Racket 解决方案中的`factorial`，看看你能否理解。也在解释器中尝试一下！如果你目前不理解代码，没关系。我们将在下一小节中更明确地讨论递归。

```
(define (factorial n)
  (if (= n 0)
      1
      (* n (factorial (- n 1))))) 
```

## 要点

这是我们在本小节中涵盖的内容：

1.  什么是递归？

1.  如何使用递归定义阶乘？

继续下一小节了解递归的工作原理。
