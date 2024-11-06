# 表示队列

## 队列数据结构

使用`set-car!`和`set-cdr!`允许我们创建一种以前无法有效实现的数据结构：队列。**队列**是一种序列，在其中项目从一端（称为队列的后端）插入，从另一端（前端）删除。因为项目总是按照插入的顺序被移除，所以有时称队列为 FIFO（先进先出）。

![](http://3.bp.blogspot.com/_w9XO9zBePXE/SKFjlee6K-I/AAAAAAAAAdk/iRjNgU62cmM/ s1600/royston_queue.jpg)

## 队列实例

假设我们有函数`make-queue`，它返回一个新队列，`insert-queue!`，它向队列添加一个新元素，以及`delete-queue!`，它从队列中删除一个元素（我们将很快实现它们！）。让我们来看看队列的机制。

| 操作 | 结果队列 |
| --- | --- |
| `(define q (make-queue))` |  |
| `(insert-queue! q 'a)` | `a` |
| `(insert-queue! q 'b)` | `a b` |
| `(delete-queue! q)` | b |
| `(insert-queue! q 'c)` | b c |
| `(insert-queue! q 'd)` | `b c d` |
| `(delete-queue! q)` | `c d` |

在数据抽象方面，我们可以将队列视为以下一组操作定义的：

+   一个构造函数：`(make-queue)`返回一个空队列（不包含任何项目的队列）。

+   两个选择器：

    +   `(empty-queue? <_queue_>)`测试队列是否为空。

    +   `(front-queue <_queue_>)`返回队列前端的对象，如果队列为空，则发出错误信号。**它不修改队列。**

+   两个改变者：

    +   `(insert-queue! <_queue_> <_item_>)`将项目插入到队列的后端，并将修改后的队列作为其值返回。

    +   `(delete-queue! <_queue_>)`删除队列前端的项目，并将修改后的队列作为其值返回，如果在删除之前队列为空，则发出错误信号。

## 作为列表的队列

因为队列是一系列项目的列表，我们可以用普通列表来表示它。队列的前端将是列表的`car`，插入新元素将相当于在末尾添加新对。删除项目只是`cdr`。为什么我们不采用这种实现？问题在于运行时间。要将项目添加到列表的末尾，我们必须经过一系列的`cdr`。如果列表真的很长，我们将花费很长时间找到最后一对。这样做的运行时间为`Θ(n)`，其中`n`是列表的长度。

列表允许我们在常数时间内访问第一个项目，但当需要找到最后一对时，它需要很长时间。我们可以通过存储和更新指向最后一对的指针来解决这个问题。

![](img/44b4d2bc1275d24e3d1a3098b9325efb.jpg)

查看上面的队列，我们可以看到我们存储了两个指针：一个指向列表的前端，一个指向后端。如果我们尝试向队列添加一个新项目，`'d`，则结构将更改为以下内容：

![](img/ac70f6a07a551383054f2350a1c1b210.jpg)

当我们想要找到`q`的最后一对时，我们可以按照`(cdr q)`指针。

## 实现

要定义队列操作，我们使用以下过程，这些过程使我们能够选择和修改队列的前端和后端指针： 

```
(define (front-ptr queue)
    (car queue))
(define (rear-ptr queue)
    (cdr queue))
(define (set-front-ptr! queue item)
    (set-car! queue item))
(define (set-rear-ptr! queue item)
    (set-cdr! queue item)) 
```

现在我们可以实现实际的队列操作。如果其前端指针是空列表，则我们将考虑队列为空：

```
(define (empty-queue? queue)
    (null? (front-ptr queue))) 
```

`make-queue`构造函数返回一个初始为空队列的对，其`car`和`cdr`都是空列表：

```
(define (make-queue)
    (cons '() '())) 
```

要选择队列前端的项目，我们返回由前端指针指示的对的`car`：

```
(define (front-queue queue)
    (if (empty-queue? queue)
        (error "FRONT called with an empty queue" queue)
        (car (front-ptr queue)))) 
```

## 添加到队列

我们将遵循之前概述的一般算法：

1.  `cons`一个包含新项的新对

1.  如果队列为空，我们将其`front-ptr`和`rear-ptr`设置为这个新对

1.  如果队列不为空，我们找到最后一对，将其`cdr`更改为新生成的对，并更新`rear-ptr`。

    (define (insert-queue! queue item) (let ((new-pair (cons item '()))) (cond ((empty-queue? queue) (set-front-ptr! queue new-pair) (set-rear-ptr! queue new-pair) queue) (else (set-cdr! (rear-ptr queue) new-pair) (set-rear-ptr! queue new-pair) queue))))

## 从队列中删除

要从队列中删除，我们可以简单地将`front-ptr`更改为指向下一个对。

```
(define (delete-queue! queue)
  (cond ((empty-queue? queue)
         (error "DELETE! called with an empty queue" queue))
        (else
         (set-front-ptr! queue (cdr (front-ptr queue)))
         queue))) 
```

![](img/ac70f6a07a551383054f2350a1c1b210.jpg)

如果从上面的队列开始我们决定删除第一个项目，更改只会发生在`front-ptr`指向的位置：

![](img/368ec8b3e335f9a139ebbaf028b67d33.jpg)

## 收获

`set-car!`和`set-cdr!`允许我们更有效地实现一个新的数据结构（队列），而不仅仅是`cons`、`car`和`cdr`所能构建的。
