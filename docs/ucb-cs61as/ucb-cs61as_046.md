# 空间

## 递归过程

要开始探索过程如何使用空间，请考虑以下过程：

```
(define (factorial n)
  (if (= n 0)
      1
      (* n (factorial (- n 1))))) 
```

如果我们手动评估`(factorial 5)`，写出每一步，我们会得到以下结果：

```
start with  (factorial 5)
replaced by (* 5 (factorial 4))
replaced by (* 5 (* 4 (factorial 3)))
replaced by (* 5 (* 4 (* 3 (factorial 2))))
replaced by (* 5 (* 4 (* 3 (* 2 (factorial 1)))))
replaced by (* 5 (* 4 (* 3 (* 2 (* 1 (factorial 0))))))
replaced by (* 5 (* 4 (* 3 (* 2 (* 1 1)))))
replaced by (* 5 (* 4 (* 3 (* 2 1))))
replaced by (* 5 (* 4 (* 3 2)))
replaced by (* 5 (* 4 6))
replaced by (* 5 24)
replaced by 120 
```

每一行描述了计算的一个新步骤——我们需要在那个时间步骤记住什么以便继续评估。这里是关键观察：如果我们选择一个足够大的输入，比如 10000，那么在某个步骤，我们将无法将整行记在脑中。

计算机以相同的方式评估过程调用。每个函数调用都存储在计算机的工作内存中——这是一个用于存储中间、不完整计算的地方。这个空间是有限的，可能会溢出。需要记住的重要一点是，这个问题只会在非常大的输入上发生。这个"工作内存"被称为"调用堆栈"。当程序使用完这个空间时，就会发生"堆栈溢出"。

## 迭代过程

有没有一种方法可以修复阶乘，使其在大输入时不会使计算机耗尽空间？考虑以下内容：

```
(define (factorial n)
  (fact-iter 1 1 n))

(define (fact-iter product counter max-count)
  (if (> counter max-count)
      product
      (fact-iter (* counter product)
                 (+ counter 1)
                 max-count))) 
```

测试你的理解。为什么我们必须说`(> counter max-count)`？如果我们执行`(fact-iter 1 1 3)`会发生什么？现在如果我们用上面的代码来绘制`(factorial 5)`，我们会得到以下结果：

```
start with  (factorial 5)
replaced by (fact-iter 1 1 5)
replaced by (fact-iter 1 2 5)
replaced by (fact-iter 2 3 5)
replaced by (fact-iter 6 4 5)
replaced by (fact-iter 24 5 5)
replaced by (fact-iter 120 6 5)
replaced by 120 
```

在这种情况下，我们在评估过程中需要保留的不完整计算量在每一步都没有增长。相反，我们通过参数传递*计算的不完整答案*，这样可以节省空间。换句话说，计算的完整状态保存在递归调用的参数中——调用`(fact-iter 2 3 5)`会产生与调用`(fact-iter 1 1 5)`相同的结果，而调用`(factorial 3)`会产生与调用`(factorial 5)`不同的结果。

注意，这个迭代过程仍然使用递归，但这与说它是一个递归过程是不同的。

## 比较迭代和递归过程

将这些函数并排看，我们可以确定这两个过程之间的关系。

| 递归 | 迭代 |
| --- | --- |

|

```
(define (factorial n)
  (if (= n 0)
      1
      (* n (factorial (- n 1))))) 
```

|

```
(define (factorial n)
  (fact-iter 1 1 n))

(define (fact-iter product counter 
                   max-count)
  (if (> counter max-count)
      product
      (fact-iter (* counter product)
                 (+ counter 1)
                 max-count))) 
```

|

对于这两个过程的重要观察：

+   递归版本中作为基本情况返回的值充当迭代版本中`product`的起始点（1）。注意，调用迭代`(factorial 1)`会导致在`fact-iter`中触发基本情况，并返回 1。

+   在递归版本中，`*`过程在递归调用之外被调用。在迭代版本中，所有参数在（或在）递归调用之前被转换。也就是说，`(* counter product)`首先发生，然后进行递归调用。**这就是迭代版本更节省空间的关键所在。**

+   作为一个推论，这意味着递归调用是在过程调用中被"最后"评估的表达式（与乘法相反）。

+   因为迭代版本需要跟踪更多的参数，它需要一个辅助过程，递归实际上发生在那里。这在迭代过程中经常发生。

## 尾递归和编写尾递归过程

在正式术语中，迭代`factorial`更加节省空间，因为 Racket 解释器实现了[尾递归消除](https://en.wikipedia.org/wiki/Tail_call)。在其他编程语言和其他未经过尾递归优化的解释器中，递归和迭代版本在运行时使用相同的空间。那么我们为什么要关心呢？

+   引入这些主题使我们更深入地理解递归、求值和编程语言，为其他主题提供了坚实的背景

+   这是一个练习思考资源使用和权衡的机会，这对软件工程和计算机科学通常很重要。

要编写*尾递归*过程，以下是一些建议。

+   弄清楚是否需要保留额外的参数来跟踪计算状态，以及是否需要辅助过程。几乎总是需要某种参数来跟踪"到目前为止的答案"。在`factorial`中，这是`product`。

+   实际上，作为一个一般规则，过程的递归版本会尝试使其参数逐渐变小，而迭代版本则会构建一个结果。因此，在编写迭代过程时，考虑一下需要的起始值以便"构建"你的答案。在`factorial`中，这是 1、1 和`n`，在`(fact-iter 1 1 n)`中。

+   确保递归调用发生在"最后一刻"。实际上，这意味着在进行递归调用之前处理参数（相加、相减、相乘、`butfirst`等）。

## 练习

以下问题是为了帮助你理解。你不会被评分。你可以向工作人员核对你的答案。

+   迭代`factorial`在`fact-iter`中跟踪三件事。那些事情是什么？我们能否再次重写`factorial`以便只跟踪两件事？

+   如果我们使用迭代版本，调用`factorial`会不会导致空间耗尽？

## 进一步阅读

[SICP 1.2.1 - 线性递归和迭代](https://mitpress.mit.edu/sicp/full-text/book/book-Z-H-11.html#%_sec_1.2.1)
