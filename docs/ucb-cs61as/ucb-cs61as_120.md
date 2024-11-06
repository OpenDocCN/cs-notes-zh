# 示例 - 交错流

## 追加流

假设你有两个流，你想将一个与另一个合并，类似于列表的`append`。用`append`，我们将一个列表的开头连接到另一个列表的结尾。等效的流定义将是这样的：

```
(define (stream-append s1 s2)
  (if (stream-null? s1)
      s2
      (cons-stream (stream-car s1) 
                   (stream-append (stream-cdr s1) s2)))) 
```

但等等！流可以是*无限*长的！如果我们调用`(stream-append s1 s2)`而`s1`是一个无限流，我们将永远无法访问`s2`的任何元素。

## 交错流

另一种方法是**交错**这两个流：

```
(define ones (cons-stream 1 ones)) ; (1 1 1 1 ...)
(define twos (cons-stream 2 twos)) ; (2 2 2 2 ...)

(define one-two (interleave ones twos)) ; (1 2 1 2 ...) 
```

通过交错两个流，我们可以确保我们将使用来自两个流的元素。我们可以这样定义`interleave`：

```
(define (interleave s1 s2) 
  (if (stream-null? s1)
      s2
      (cons-stream (stream-car s1)
                   (interleave s2 (stream-cdr s1))))) 
```
