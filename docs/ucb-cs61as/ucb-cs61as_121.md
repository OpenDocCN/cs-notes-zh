# 示例 - 无限对流

假设我们想要生成一个包含整数对[i, j]的无限流，其中 i≤j 且 i + j 是素数。如果`int-pairs`是所有整数对的流，我们的流是：

```
(stream-filter (lambda (pair)
                 (prime? (+ (car pair) (cadr pair))))
               int-pairs) 
```

现在我们只需要定义`int-pairs`。我们该如何做呢？让我们假设我们有两个等同于`integers`的流[S]和[T]。现在让我们想象一下[S]和[T]的整数对数组（或矩阵，如果你想这样考虑的话）：

![](img/69a4180dd536dcfa0479b74fc01cd99f.jpg)

整数对的流是对角线上方的所有内容：

![](img/bbfd42bec6190b3c92380777ded52152.jpg)

让我们称一般的整数对流为`(pairs s t)`，并将其视为由三部分组成：对[S0, T0]，第一行中其余的对，以及剩余的对。

![](img/57c83d75e5f1c2494e71bd4ade2fdb90.jpg)

这个分解中的第三部分（不在第一行的对）是由`(stream-cdr s)`和`(stream-cdr t)`形成的对（递归）。还要注意第二部分（第一行的其余部分）是：

```
(stream-map (lambda (x) (list (stream-car s) x))
            (stream-cdr t))1 
```

那么我们的整数对流就是：

```
(define (pairs s t)
  (cons-stream (list (stream-car s) (stream-car t))
               (combine (stream-map (lambda (x) (list (stream-car s) x))
                                                  (stream-cdr t))
                                      (pairs (stream-cdr s) (stream-cdr t))))) 
```

现在我们只需要使用某种`combine`函数将这些流组合在一起。我们知道追加不起作用，让我们使用`interleave`代替！我们的对流变成了：

```
(define (pairs s t)
  (cons-stream (list (stream-car s) (stream-car t))
               (interleave (stream-map (lambda (x) (list (stream-car s) x))
                                       (stream-cdr t))
               (pairs (stream-cdr s) (stream-cdr t))))) 
```
