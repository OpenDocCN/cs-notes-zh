# 概述 - 数据抽象

## 什么是数据抽象？

回想第 1 课 - 你还记得[过程作为黑盒抽象](http://berkeley-cs61as.github.io/textbook/procedures-as-black-box-abstractions.html)吗？你不需要知道用作[高阶函数](http://berkeley-cs61as.github.io/textbook/hofs-procedures-as-arguments.html)参数的过程是如何实现的，只要它们能工作！这使我们能够创建通用的，“可定制”的函数，使我们的代码简洁，可读性强，*灵活*。

复合数据的类似概念称为**数据抽象**，它是一种方法论，使我们能够将复合数据对象的使用方式与如何从更基本的数据对象构造它的细节隔离开来。换句话说，你不需要知道汽车的发动机是如何工作的才能开车。

数据抽象的基本思想是结构化使用复合数据对象的程序，使其操作“抽象数据”。也就是说，我们的程序应该以一种不对数据存储或提取方式做任何假设的方式使用数据。因此，数据表示的方式是“具体的”，并且独立于使用它的程序。

专业程序员编写的程序和项目通常对不懂编程的公众开放。如果一个科技公司用 Python 编写了一个很酷的程序，他们不会期望他们的客户知道他们如何编写程序，甚至如何理解 Python，才能使用他们的产品。那么这些程序员如何让非程序员人群使用他们的作品呢？抽象。这就是编程的全部意义。

我们系统中这两部分之间的接口将是一组过程，称为**构造函数**和**选择器**：

+   **构造函数** 创建存储我们数据的对象。

+   **选择器（selector(s)）** 从构造函数创建的对象中提取您将使用的数据。

构造函数创建的对象称为**抽象数据类型（ADT）**。

## 例子：有理数

为了说明这种技术，让我们考虑如何设计一个用于操作有理数的接口。

有理数是可以表示为两个整数的商或分数（*p/q*）的任何数，其中*q*不为零。例如，3/4 是一个有理数，分母为 4，分子为 3，而π是一个无理数。

尽管 Racket 语言已经在其字典中容纳了分数，让我们尝试通过创建自己的抽象数据类型来表示它。在我们开始制作构造函数和选择器之前，让我们先看看我们需要的信息。

完整表示有理数所需的最小数据是分子和分母。因此，我们可以任意选择存储这两个数字的方式。这里我们选择将其存储在一个*对*中：

```
(define (make-rational numer denom)
  (if (= 0 denom)
      (error "Divisor cannot be 0!")
      (cons numer denom))) 
```

这就是我们的构造函数！它只是一个过程，当用适当的参数调用时，通过将其存储在一对中来“创建”一个有理数。当然，`(3 . 4)`看起来并不*像*一个分数，但这正是我们的选择器存在的原因。我们如何*提取*我们的抽象数据类型中的分子和分母？看一看：

```
(define (numerator rat)
  (car rat))

(define (denominator rat)
  (cdr rat)) 
```

第一个选择器`numerator`接受一个有理数作为其参数，并通过调用`car`来返回其分子。第二个选择器通过调用`cdr`来返回分母。现在，我们的抽象数据类型实现已经完成了！我们可以创建一个有理数并提取其数据，就像这样：

```
-> (define x (make-rational 3 4))
x
-> (numerator x)
3
-> (denominator x)
4 
```

你是否注意到，在上面的调用中，没有任何内容透露了*有理数*是如何表示的？你已经*抽象*出了表示数据的方法，并留下了一个几乎任何人都可以使用的干净接口。

抽象数据类型的构造函数和选择器是相辅相成的。这个有理数实现的选择器对于不同的有理数实现是不起作用的。我们可以使用列表、句子、小数等。抽象的美妙之处在于我们*不知道*。

**测试您的理解**

考虑在平面中表示线段的问题。每个线段表示为一对点：一个起点和一个终点。

点被表示为一对坐标：

```
(define (make-point x y) (cons x y))
(define (x-coord point) (car point))
(define (y-coord point) (cdr point))
```

定义一个构造函数称为`make-segment`和选择器称为`start-segment`和`end-segment`，以点的形式定义线段的表示。您可以选择任何您希望存储数据的方法。

## 使用 ADT 的过程

为了扩展我们的有理数 ADT，让我们编写一些尊重我们实现抽象的过程。一个有用的过程是`print-rat`，它实际上让我们看到一个有理数的“外观”，给定其抽象表示。

```
-> (define (print-rat rat)
    (word (numerator rat) '/ (denominator rat)))
-> (define x (make-rational 3 4))
x
-> (print-rat x)
3/4 
```

这样我们就可以假装我们的有理数实际上不是一对。:)

如果我们不能对有理数进行数学运算，那有理数有什么用呢？在这里，我们为我们的 ADT 定义了一些简单的算术过程：

```
(define (add-rat rat1 rat2)
  (make-rational (+ (* (numerator rat1) (denominator rat2))
                    (* (numerator rat2) (denominator rat1)))
                 (* (denominator rat1) (denominator rat2))))

(define (sub-rat rat1 rat2)
  (make-rational (- (* (numerator rat1) (denominator rat2))
                    (* (numerator rat2) (denominator rat1)))
                 (* (denominator rat1) (denominator rat2)))))

(define (mul-rat rat1 rat2)
  (make-rational (* (numerator rat1) (numerator rat2))
                 (* (denominator rat1) (denominator rat2))))

(define (div-rat rat1 rat2)
  (make-rational (* (numerator rat1) (denominator rat2))
                 (* (denominator rat1) (numerator rat2)))))

(define (equal-rat? rat1 rat2)
  (= (* (numerator rat1) (denominator rat2))
     (* (numerator rat2) (denominator rat1)))) 
```

注意这些过程*尊重*抽象。在我们的代码中，我们从不调用`cons`来创建一个有理数，也不调用`car`/`cdr`来选择分子或分母。不这样做被称为**数据抽象违反**，但我们可以在后面的部分讨论这个问题。现在，让我们继续进行更大更好的示例！

**测试您的理解**

使用上面的线段实现，定义一个名为`segment-length`的过程，该过程接受一个线段并返回其长度。
