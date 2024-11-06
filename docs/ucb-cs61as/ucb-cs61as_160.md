# 互斥体

## 什么是互斥体？

互斥体是支持两个操作的对象--可以获取互斥体，也可以释放互斥体。一旦获取了互斥体，那么在释放互斥体之前，该互斥体上的任何其他获取操作都不能继续进行。

互斥体是一个可变对象（这里我们将使用一个一元列表，称为单元格），可以保存值 true 或 false。当值为 false 时，互斥体可用于获取。当值为 true 时，互斥体不可用，任何试图获取互斥体的进程都必须等待。

我们的互斥体构造函数`make-mutex`首先将单元格内容初始化为 false。要获取互斥体，我们测试单元格。如果互斥体可用，我们将单元格内容设置为 true 并继续。否则，我们在循环中等待，一遍又一遍地尝试获取，直到发现互斥体可用为止。要释放互斥体，我们将单元格内容设置为 false。

```
(define (make-mutex)
  (let ((cell (list false)))            
    (define (the-mutex m)
      (cond ((eq? m 'acquire)
             (if (test-and-set! cell)
                 (the-mutex 'acquire))) ; retry
            ((eq? m 'release) (clear! cell))))
    the-mutex))
(define (clear! cell)
  (set-car! cell false)) 
```

`Test-and-set!`测试单元格并返回测试结果。此外，如果测试为 false，`test-and-set!`在返回 false 之前将单元格内容设置为 true。这个过程是 Scheme 的原语。它的实现需要硬件支持。

## 使用互斥体

该书在串行化器和原子硬件功能之间使用了一个中间抽象级别，称为互斥体。互斥体和串行化器之间有什么区别？串行化器作为一个抽象，提供了一个受保护的操作，而无需程序员考虑保护的机制。互斥体暴露了事件的顺序。就像之前的不正确实现所说的那样

```
(set! in-use #t)
(apply proc args)
(set! in-use #f) 
```

正确版本使用类似的顺序

```
(mutex ’acquire)
(apply proc args)
(mutex ’release) 
```

顺便说一句，在这些部分的所有版本中都有另一个错误；我们通过忽略返回值的问题简化了讨论。我们希望由 protected-proc 返回的值与原始 proc 返回的值相同，即使对 proc 的调用不是最后一步。因此，正确的实现是

```
(mutex ’acquire)
(let ((result (apply proc args)))
    (mutex ’release)
    result) 
```

就像书中第 311 页的实现一样。

## 使用互斥体实现串行化器

现在我们了解了互斥体以及如何使用它们，相对来说实现串行化器就相对简单了。我们的实现如下。确保你理解它是如何工作的以及为什么！

```
(define (make-serializer)
  (let ((mutex (make-mutex)))
    (lambda (p)
      (define (serialized-p . args)
        (mutex 'acquire)
        (let ((val (apply p args)))
          (mutex 'release)
          val))
      serialized-p))) 
```
