# 消息传递

## 什么是消息传递？

在传统风格中，运算符被表示为知道不同类型的函数；类型本身只是数据。在数据导向编程中，运算符和类型都是数据，并且有一个通用的 operate 函数来完成工作。我们还可以颠倒传统的风格，将类型表示为函数，将操作仅表示为数据。

实际上，不仅类型是函数，而且单个数据本身也是函数。也就是说，有一个函数（如下所示的`make-circle`），表示圆形类型，当你调用该函数时，它会返回一个代表你给定的特定圆形的函数作为其参数。每个圆形都是一个对象，表示它的函数是一个分发过程，它以一个消息作为其参数，该消息说明要执行哪个操作。

下面是`make-square`和`make-circle`的新定义。

```
(define (make-square side)
    (lambda (message)
        (cond ((eq? message 'area)
               (* side side))
              ((eq? message 'perimeter)
               (* 4 side))
              (else (error "Unknown message")))))

(define (make-circle radius)
    (lambda (message)
        (cond ((eq? message 'area)
               (* pi radius radius))
              ((eq? message 'perimeter)
               (* 2 pi radius))
              (else (error "Unknown message")))))

(define square5 (make-square 5))

(define circle3 (make-circle 3)) 
```

## 为什么消息传递很重要？

消息传递可能看起来是处理这个形状问题的过于复杂的方式，但我们将在下一课中看到，它是创建面向对象编程的关键思想之一。当与我们下周将学习的局部状态的概念相结合时，消息传递变得更加强大。

我们似乎放弃了带标记的数据；每种形状类型只是一些函数，很难确定给定函数代表哪种类型的形状。如果需要，我们可以通过添加每个对象都理解的`type`消息来将消息传递与带标记的数据结合起来。

```
(define (make-square side)
    (lambda (message)
        (cond ((eq? message 'area)
               (* side side))
              ((eq? message 'perimeter)
               (* 4 side))
              ((EQ? MESSAGE 'TYPE) 'SQUARE)
               (else (error "Unknown message"))))) 
```
