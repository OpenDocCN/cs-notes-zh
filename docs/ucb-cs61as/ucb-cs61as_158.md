# 序列化器

## 什么是序列化器

我们引入了一个称为序列化器的抽象。这是一个接受另一个过程（称为`proc`）作为其参数的过程。序列化器返回一个新的过程（称为`protected-proc`）。当调用时，`protected-proc`调用`proc`，但只有当同一个序列化器没有被另一个受保护的过程使用时才会调用。`proc`可以有任意数量的参数，而`protected-proc`将接受相同的参数并返回相同的值。

可能会有许多不同的序列化器同时运行，但每个序列化器不能同时执行两个任务。所以如果我们说

```
(define x-protector (make-serializer))
(define y-protector (make-serializer))
(parallel-execute (x-protector (lambda () (set! x (+ x 1))))
                  (y-protector (lambda () (set! y (+ y 1))))) 
```

那么两个任务可以同时运行；它们的机器指令如何交错并不重要。

但如果我们说

```
(parallel-execute (x-protector (lambda () (set! x (+ x 1))))
                  (x-protector (lambda () (set! x (+ x 1))))) 
```

那么，因为我们在两个任务中使用相同的序列化器，序列化器将确保它们不会在时间上重叠。

我们引入了一个新的基本过程，`parallel-execute`。它接受任意数量的参数，每个参数都是一个没有参数的过程，并且并行而不是按顺序调用它们。（这不是 Scheme 的标准部分，而是教科书本节的扩展。）

你可能会想到所有那些(lambda ()...)符号的必要性。由于序列化器不是一个特殊形式，它不能接受表达式作为参数。相反，我们必须给它一个可以调用的过程。

让我们看一下这段代码是如何工作的示例：

```
(define x-protector (make-serializer))
(define protected-increment-x (x-protector (lambda () (set! x (+ x 1)))))
> x
100
> (protected-increment-x)
> x
101 
```

## 实现序列化器

序列化器是一个高级抽象。我们如何让它工作？这是一个**错误的尝试**来实现序列化器：

```
(define (make-serializer)
  (let ((in-use? #f))
    (lambda (proc)
      (define (protected-proc . args)
        (if in-use?
            (begin
             (wait-a-while) ; Never mind how to do that.
             (apply protected-proc args)) ; Try again.
            (begin
             (set! in-use? #t) ; Don't let anyone else in.
             (apply proc args) ; Call the original procedure.
             (set! in-use? #f)))) ; Finished, let others in again.
      protected-proc))) 
```

这有点复杂，所以要集中精力关注重要部分。特别是不要在乎并行性的*调度*方面--我们如何要求这个过程在尝试再次使用序列化器之前等待一段时间。也不要在乎关于`apply`的东西，这只是为了我们可以序列化具有任意数量参数的过程。

需要关注的部分是这个：

```
(if in-use?
    ....... ; wait and try again
    (begin (set! in-use #t)   ; Don't let anyone else in. 
           (apply proc args)  ; Call the original procedure.
           (set! in-use #f))) ; Finished, let others in again. 
```

这段代码的意图是首先检查序列化器是否已经在使用。如果没有，我们通过将`in-use`设置为 true 来声明序列化器，完成我们的工作，然后释放序列化器。

问题在于这一系列事件受到与我们试图保护的过程相同的并行性问题的影响！如果我们检查`in-use`的值，发现它是 false，而正好在那时另一个进程悄悄地抓住了序列化器怎么办？为了使这个工作起作用，我们必须有另一个序列化器来保护这一个，第三个序列化器来保护第二个，依此类推。

*没有简单的方法可以通过竞争进程内的巧妙编程技巧来避免这个问题。* 我们需要在提供并行性的底层机制上获得帮助：硬件和/或操作系统。该底层必须提供*保证原子*操作，我们可以测试`in-use`的旧值并将其更改为新值，而没有其他进程介入的可能性。（事实证明，有一个非常棘手的软件算法可以生成保证原子测试和设置，但实际上，几乎总是有硬件支持并行性。如果你想看到软件解决方案，请在维基百科中查找“Peterson's algorithm”。）

教科书假定存在一个名为`test-and-set!`的过程，具有原子性的保证。尽管在第 312 页上有一个伪实现，但该过程实际上不起作用，原因与我的`make-serializer`的伪实现相同。你需要想象的是，`test-and-set!`是计算机硬件中的一条单指令，类似于我们开始讨论的 Load Word 指令等。（这是一个现实的假设；现代计算机确实提供了一些这样的硬件机制，正是我们现在讨论的原因。）

要理解如何正确实现串行器，你首先需要了解并理解互斥锁（在两个部分中）。
