# 流是延迟的列表

## 流构造器和选择器

表面上，流只是具有不同名称的列表，用于操作它们的过程不同。它们有一个构造器 `cons-stream`，和两个选择器，`stream-car` 和 `stream-cdr`，满足以下约束：

+   `(stream-car (cons-stream x y))` 返回 `x`

+   `(stream-cdr (cons-stream x y))` 返回 `y`

为了在使用流时构造流，我们将安排流的 cdr 在被 `stream-cdr` 过程访问时评估，而不是在流构造时评估。

作为数据抽象，流与列表相同。区别在于元素评估的时间。对于普通列表，`car` 和 `cdr` 在构造时都会被评估。对于流而言，cdr 在选择时才会被评估。

我们对流的实现将基于一个称为 `delay` 的特殊形式。评估 `(delay [exp])` 不会评估表达式 [exp]，而是返回一个所谓的延迟对象，我们可以将其视为在将来某个时间评估 [exp] 的“承诺”。作为 `delay` 的伴随，有一个名为 `force` 的过程，它以延迟对象作为参数执行评估 -- 实际上，强制延迟实现其承诺。我们将在下面看到如何实现 `delay` 和 `force`，但首先让我们使用它们来构建流。

`cons-stream` 是这样一个特殊形式，使得 `(cons-stream [a] [b])` 等价于 `(cons [a] (delay [b]))`。

这意味着我们将使用对 `car` 和延迟的 `cdr` 进行成对构造。这些将是我们的 `stream-car` 和 `stream-cdr` 过程：

```
(define (stream-car stream) (car stream))

(define (stream-cdr stream) (force (cdr stream))) 
```

注意 `cons-stream` 是一个特殊形式。如果不是的话，调用 `(cons-stream a b)` 将会评估 `b`，这意味着 `b` 将不会延迟。

## `the-empty-stream`

有一个可区分的对象，`the-empty-stream`，它不能是任何 `cons-stream` 操作的结果，并且可以用谓词 `stream-null?` 来识别。

## 列表程序的流类比

我们可以制作和使用流，就像我们可以制作和使用列表一样，以表示按顺序排列的聚合数据。特别是，我们可以构建 `list-ref`、`map`、`for-each` 等的流类比。

### `stream-ref`

```
(define (stream-ref s n)
  (if (= n 0)
      (stream-car s)
      (stream-ref (stream-cdr s) (- n 1)))) 
```

如果我们定义 x 为

```
(define x (cons-stream 0 (cons-stream 1 (cons-stream 2 the-empty-stream)))) 
```

那么 `(stream-ref x 0)` 返回 0，`(stream-ref x 2)` 返回 2。（注意 n 从 0 开始计数）

### `stream-map`

```
(define (stream-map proc s)
  (if (stream-null? s)
      the-empty-stream
      (cons-stream (proc (stream-car s))
                   (stream-map proc (stream-cdr s))))) 
```

如果 x 与上面相同，那么 `(stream-map square x)` 将返回一个包含 `(0 1 4)` 的流

### `stream-for-each`

```
(define (stream-for-each proc s)
  (if (stream-null? s)
      'done
      (begin (proc (stream-car s))
             (stream-for-each proc (stream-cdr s))))) 
```

`stream-for-each` 用于查看流很有用。以下可能有助于检查发生了什么：

```
(define (display-stream s)
  (stream-for-each display-line s))

(define (display-line x)
  (newline)
  (display x)) 
```

## 使用流进行计算

让我们再次看一下我们之前看到的第二个素数计算，用流的术语重新表述：

```
(stream-car
 (stream-cdr
  (stream-filter prime?
                 (stream-enumerate-interval 10000 1000000)))) 
```

所以我们首先用参数 10,000 和 1,000,000 调用 `stream-enumerate-interval`。这将创建一个从 10,000 到 1,000,000 的数字流。

```
(define (stream-enumerate-interval low high)
  (if (> low high)
      the-empty-stream
      (cons-stream
       low
       (stream-enumerate-interval (+ low 1) high)))) 
```

返回的结果是 `(cons 10000 (delay (stream-enumerate-interval 10001 1000000)))` 这是一个流，表示为一个对，其 `car` 是 10,000，`cdr` 是一个承诺，如果有必要，将枚举更多的区间。现在我们使用 `stream-filter` 进行过滤

```
(define (stream-filter pred stream)
  (cond ((stream-null? stream) the-empty-stream)
        ((pred (stream-car stream))
         (cons-stream (stream-car stream)
                      (stream-filter pred
                                     (stream-cdr stream))))
        (else (stream-filter pred (stream-cdr stream))))) 
```

`stream-filter` 测试流的 `stream-car`（对偶的 car，即 10,000）。由于这不是素数，`stream-filter` 检查其输入流的 `stream-cdr`。对 `stream-cdr` 的调用强制评估延迟的 `stream-enumerate-interval`，现在返回

```
(cons 10001
      (delay (stream-enumerate-interval 10002 1000000))) 
```

`stream-filter` 现在查看这个流的 `stream-car`，10,001，看到这也不是素数，强制另一个 `stream-cdr`，依此类推，直到 `stream-enumerate-interval` 产生素数 10,007，然后根据其定义，`stream-filter` 返回

```
(cons-stream (stream-car stream)
             (stream-filter pred (stream-cdr stream))) 
```

就是

```
(cons 10007
      (delay
        (stream-filter
         prime?
         (cons 10008
               (delay
                 (stream-enumerate-interval 10009
                                            1000000)))))) 
```

现在将此结果传递给我们原始表达式中的 `stream-cdr`。这强制了延迟的 `stream-filter`，进而保持强制延迟的 `stream-enumerate-interval`，直到找到下一个素数，即 10,009。最后，传递给我们原始表达式中的 `stream-car` 的结果是

```
(cons 10009
      (delay
        (stream-filter
         prime?
         (cons 10010
               (delay
                 (stream-enumerate-interval 10011
                                            1000000)))))) 
```

`Stream-car` 返回 10,009，并且计算完成。只有测试了必要数量的整数以找到第二个素数，并且只枚举了必要的区间来提供素数筛选器。

## 实现 `delay` 和 `force`

尽管 `delay` 和 `force` 可能看起来像神秘的操作，但它们的实现实际上非常简单。`delay` 必须封装一个表达式，以便以后按需评估，我们可以简单地将表达式视为过程的主体来实现这一点。`delay` 可以是一个特殊形式，如下

```
 (delay [exp]) 
```

是语法糖，等同于

```
 (lambda () [exp]) 
```

`force` 简单地调用由 `delay` 生成的过程（无参数），因此我们可以将 `force` 实现为一个过程：

```
 (define (force delayed-object)
  (delayed-object)) 
```

再次注意 `delay` 作为特殊形式的重要性。如果不是，那么当我们调用 `(delay b)` 时，`b` 将在我们评估主体之前被评估。

这种实现足以使 `delay` 和 `force` 正常工作，但我们可以包含一个重要的优化。在许多应用程序中，我们最终会多次强制相同的延迟对象。这可能导致涉及流的递归程序严重低效。解决方案是构建延迟对象，以便第一次强制它们时，它们存储计算的值。后续的强制将简单地返回存储的值，而不重复计算。换句话说，我们将 `delay` 实现为一个特殊用途的记忆化过程。实现这一点的一种方法是使用以下过程，该过程以一个过程（无参数）作为参数，并返回该过程的记忆化版本。第一次运行记忆化过程时，它保存计算结果。在后续的评估中，它只是返回结果。

```
(define (memo-proc proc)
  (let ((already-run? false) (result false))
    (lambda ()
      (if (not already-run?)
          (begin (set! result (proc))
                 (set! already-run? true)
                 result)
          result)))) 
```

`Delay` 然后被定义为（delay [exp]）等同于

```
(memo-proc (lambda () [exp])) 
```

而`force`保持不变

## 收获

在本节中，你学到了：

1.  流是什么样的

1.  流的一些有用应用

1.  如何实现`delay`和`force`

## 接下来呢？

让我们继续下一小节，学习无限列表！
