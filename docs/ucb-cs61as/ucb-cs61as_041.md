# 应用高阶函数

**注意：** 这一部分比课程的其他部分更加密集。如果你在这一部分遇到困难，不要担心——这比我们期望你掌握的大部分内容都要高级。

在这里，我们将使用到目前为止学到的工具来探索两个应用示例：`fixed-point`和`iterate`。

## `fixed-point`

我们首先尝试表达函数的**不动点**的计算。如果一个数字`x`满足方程`f(x) = x`，则称其为函数`f`的不动点。

一个找到某些函数`f`的不动点的算法是，我们从一个初始猜测开始，然后重复应用`f`，直到连续的值非常接近。

```
x  
(f x)  
(f (f x))  
... 
```

利用这个想法，我们将制作一个过程`fixed-point`，它将一直应用一个函数，直到我们找到两个连续值的差小于某个预定的`tolerance`。看看我们下面对`fixed-point`的定义：

```
(define tolerance 0.00001)

(define (fixed-point f first-guess)
    (define (close-enough? v1 v2)
        (< (abs (- v1 v2)) tolerance))
    (define (try guess)
       (let ((next (f guess)))
          (if (close-enough? guess next)
              next
              (try next))))
    (try first-guess)) 
```

例如，我们可以使用这种方法来近似余弦函数的不动点，从 1 作为初始近似开始：

```
-> (fixed-point cos 1.0)
0.7390822985224024 
```

为了展示用`fixed-point`抽象函数的强大之处，我们将开发一种只需 3 行 Racket 代码就能计算平方根的方法！

计算某个数字`x`的平方根需要找到一个`y`，使得`y² = x`。将这个方程转化为等价形式`y = x / y`，你会看到我们正在寻找函数`(lambda (y) (/ x y))`的不动点。在代码中：

```
(define (sqrt x)
    (fixed-point (lambda (y) (/ x y))
    1.0)) 
```

如果你碰巧有一个解释器，你会发现这��起作用。要了解原因，请看，比如，`(sqrt 4)`的连续猜测值：

```
1
4/1 = 4
4/4 = 1
4/1 = 4
... 
```

它只是不断地振荡！如果你仔细想想，它对我们放入的任何数字都会这样做（除了 0 或 1）。

因此，我们不再通过`1`来改变猜测值，而是通过稍微小一点。为了做到这一点，我们将下一个猜测值与当前猜测值平均。也就是说，在`y`之后的下一个猜测值是`(1/2)(y + x/y)`，而不是`x/y`。

制作这样一个猜测序列的过程就是简单地寻找`y = (1/2)(y + x/y)`的不动点的过程：

```
(define (sqrt x)
    (fixed-point (lambda (y) (* 0.5 (+ y (/ x y))))
    1.0)) 
```

通过这种修改，平方根过程可以工作。这种平均连续逼近解的方法，SICP 作者称之为`average damping`，通常有助于固定点搜索的收敛。

因此，让我们继续我们的抽象狂热，并将平均阻尼技术也抽象化：

```
(define (average-damp f)  
     (lambda (y) (* 0.5 (+ y (f y))))) 
```

现在，一个新的`sqrt`：

```
(define (sqrt x)  
  (fixed-point (average-damp (lambda (y) (/ x y)))  
               1.0)) 
```

非常清晰，对吧？

注意：

`y = (1/2)(y + x/y)`是方程`y = x / y`的一个简单转换；为了推导它，将`y`添加到方程的两边，然后除以`2`。

你可能已经注意到，我们已经有效地推导出了用于计算平方根的牛顿法。但是...还有很多其他方法！如果你感兴趣，这里有一个[很酷的链接](http://en.wikipedia.org/wiki/Methods_of_computing_square_roots)。

## `iterate`

现在我们将用另一个高阶函数结束这节课。

这将允许我们编写`fixed-point`和`largest-square`（来自第 1 课）。

你会问，为什么？因为它们都属于**迭代改进**的一般形式。也就是说，你从一个值开始，并不断改进它直到足够好为止。

注意这里有 3 件事情需要抽象出来：

1.  起始值

1.  用于改进的函数

1.  用于测试是否足够好的函数

所以，有了这些，我们知道了我们的参数以及它应该做什么，那么让我们来写吧！

```
(define (iterate start improve good-enough?)  
   (if (good-enough? start)  
       start  
       (iterate (improve start) improve good-enough?))) 
```

现在，我将用`iterate`来表达`largest-square`：

```
(define (largest-square total guess)  
    (iterate guess   
             (lambda (x) (+ x 1))  
             (lambda (x) (< total (square (+ x 1))))  
      )) 
```

我们的抽象狂热（大部分）到此为止，但要保持警惕。抽象是让程序员编写复杂但可读性强的系统的关键。

不要错过一个好的抽象机会。
