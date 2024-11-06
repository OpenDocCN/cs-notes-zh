# 无限流

## 介绍

我们已经看到如何支持操作流的幻觉，将其视为完整序列，而实际上我们只计算所需的流量。我们可以利用这种技术有效地将序列表示为流，即使序列非常长。但更重要的是，我们可以使用流来表示无限长的序列。例如，假设我们定义如下：

```
(define (integers-starting-from n)
  (cons-stream n (integers-starting-from (+ n 1))))

(define integers (integers-starting-from 1)) 
```

然后`integers`表示所有正整数的流。更具体地说，`integers`的`stream-car`为 1，`integers`的`stream-cdr`是一个等价于`(integers-starting-from 2)`的承诺。

使用`integers`，我们可以定义其他无限流，例如不能被 7 整除的整数流：

```
(define (divisible? x y)
  (= (remainder x y) 0))
(define no-sevens
  (stream-filter (lambda (x) (not (divisible? x 7)))
                 integers)) 
```

然后，我们可以通过访问此流的元素来找到不能被 7 整除的整数：

```
-> (stream-ref no-sevens 100)
117 
```

## 流程

到目前为止，我们一直在定义流的方式与我们定义列表的方式非常相似。现在我们将采取更“流式”的方法。

我们可以利用延迟评估来隐式定义流。例如，我们可以这样定义一个全为 1 的无限流：

```
(define ones (cons-stream 1 ones)) 
```

这与递归过程的定义方式非常相似：`ones`是一个`car`为`1`且`cdr`为评估`ones`的承诺的对。评估`cdr`再次给我们一个`1`和评估`ones`的承诺，依此类推。

我们还可以定义一个流程`add-streams`，它产生两个流的逐元素和：

```
(define (add-streams s1 s2)
  (stream-map + s1 s2) 
```

例如，`(add-streams ones ones)`将产生一个全为 2 的流。

我们可以重新定义然后隐式定义`integers`：

```
(define integers (cons-stream 1 (add-streams ones integers))) 
```

这定义了`integers`为一个流，其`stream-car`为 1，其`stream-cdr`为`ones`和`integers`的和。因此，`integers`的第二个元素是`integers`的第一个元素加 1，或者 2；`integers`的第三个元素是`integers`的第二个元素加 1，或者 3；依此类推。这个定义之所以有效，是因为在任何时刻，已经生成了足够多的整数流，以便我们可以将其反馈到定义中，以生成下一个整数。

## 关于`stream-map`

请注意，在上面的示例中，我们使用两个流调用了`stream-map`。之前，我们只使用一个流调用了 stream-map：

```
-> (define x (cons-stream 1 (cons-stream 2 (cons-stram 3 the-empty-stream))))
-> (stream-map square x)
(1 #[stream with car 4]) 
```

你可以使用`stream-map`与任意数量的流，只要你提供的过程具有相应数量的参数：

```
-> (stream-map + x x)
(2 #[stream with car 4]) 
```

当然，`stream-map`的实际定义略有不同，但现在不用担心。

我们还可以以相同的方式定义斐波那契数列：

```
(define fibs
  (cons-stream 0
               (cons-stream 1
                            (add-streams (stream-cdr fibs) fibs)))) 
```

这个定义表示`fibs`是以 0 和 1 开头的流，使得流的其余部分可以通过将`fibs`与自身向右移动一个位置相加来生成。

我们还可以使用`scale-stream`定义另一个流操作。它接受两个参数——一个整数流和一个整数，并将流中的所有元素乘以该整数：

```
(define (scale-stream strm factor)
  (stream-map (lambda (x) (* x factor)) strm)) 
```

现在我们可以这样定义所有 2 的幂的流：

```
(define doubles (cons-stream 1 (scale-stream doubles 2))) 
```

现在我们可以以不同的、隐式的方式定义素数的无限流:

```
(define primes
  (cons-stream 2
               (stream-filter prime?
                              (integers-starting-from 3)))) 
```

这可能看起来相当简单——我们从第一个素数 2 开始，然后我们通过`cons-stream`将其余的素数与之连接起来。然而，`prime?`的定义方式使得这个问题变得有点微妙。

我们通过查看一个数是否被小于√(n)的任何一个素数（而不仅仅是任何整数！）整除来检查一个数是否是素数:

```
(define (prime? n)
  (define (iter ps)
    (cond ((> (square (stream-car ps)) n) #t)
          ((divisible? n (stream-car ps)) #f)
          (else (iter (stream-cdr ps)))))
  (iter primes)) 
```

这是一个递归定义（就像你在树中看到的那样！）因为`primes`是根据`prime?`谓词定义的，而`prime?`谓词本身使用了`primes`流。这个过程之所以有效是因为，在任何时刻，已经生成了足够多的`primes`流来测试我们需要检查的下一个数的素数性。也就是说，对于我们测试素数性的每个`n`，要么`n`不是素数（在这种情况下，已经生成了一个可以整除它的素数），要么`n`是素数（在这种情况下，已经生成了一个素数——即小于`n`的素数——它大于√(`n`))

## 要点

在本节中，您学到了:

1.  无限流是什么！

1.  我们可以用它们做一些很酷的东西
