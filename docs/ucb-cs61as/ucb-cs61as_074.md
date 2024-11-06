# 数据导向编程

## 什么是数据导向编程？

**你必须加载并运行以下文件才能完成本节内容。不用担心其中定义了什么。**

```
cp ~cs61as/lib/data_directed_programming.rkt . 
```

数据导向编程是一种通过进一步模块化数据类型来增加代码灵活性的方法。我们不是使用`cond`子句在函数内部控制有关数据类型和运算符（过程）的信息，而是将这些信息记录在一个我们可以添加和检索的数据结构中。你被赋予了这样做的工具：`put`来设置数据结构和`get`来检查它。直观地说，我们只是向一个类似表的数据结构中添加条目。

```
 > (get 'foo 'baz)
    #f
    > (put 'foo 'baz 'hello)
    > (get 'foo 'baz)
    hello 
```

在上面的代码中，我们尝试检索具有键`'foo`和`'baz`的条目。因为该条目不存在（我们还没有`put`它！），我们得到了`#f`。下一行将一个条目放入具有键`'foo`和`'baz`的表中。在最后一行，我们检索我们刚刚放入的信息。

一旦你把东西放进表里，它就会一直在那里。（这是我们从函数式编程中第一次分离出来的部分，我们允许你进行赋值。但我们的意图是在计算开始时设置表，然后将其视为常量信息，而不是可变的东西。）暂时我们把`put`和`get`当作原语；我们会在第三单元中看到如何构建它们。

要理解所有这些与数据导向编程的关系，首先观察到我们有一些操作，我们希望能够对各种类型的数据应用。根据输入数据的类型，我们调用不同的过程来执行相同的基本操作。例如，添加两个有理数使用不同的过程，与添加两个复数不同。我们基本上正在处理一个二维表，该表包含一个轴上的可能操作和另一个轴上的可能类型。请注意，可能的类型实际上可能是类型列表，如果过程需要多个参数的话。

使用这种范式，向系统添加一个新类型不需要更改任何现有的过程；我们只需要向表中添加新条目。

## 一个新的示例系统

如上一节所述，我们表的“键”必须是类型列表，如果我们想继续使用我们的算术示例。现在我们不打算处理这个不必要的复杂性，我们将切换到一个更友好的示例，这应该稍微容易些。但是，所有的大想法都完全相同。

我们的数据类型将是正方形和圆；我们的操作将是面积和周长。为了进行比较（和复习），这些操作的标记数据版本将被编写为：

```
(define pi 3.141592654)

;;this is the tagged-data version where types are processed by the generic procedure being called
(define (make-square side)
    (attach-tag 'square side))

;;this is the tagged-data version where types are processed by the generic procedure being called
(define (make-circle radius)
    (attach-tag 'circle radius))

;;this is the tagged-data version where types are processed by the generic procedure being called
(define (area shape)
    (cond ((eq? (type-tag shape) 'square)
           (* (contents shape) (contents shape)))
          ((eq? (type-tag shape) 'circle)
           (* pi (contents shape) (contents shape)))
          (else (error "Unknown shape -- AREA"))))

;;this is the tagged-data version where types are processed by the generic procedure being called
(define (perimeter shape)
    (cond ((eq? (type-tag shape) 'square)
           (* 4 (contents shape)))
          ((eq? (type-tag shape) 'circle)
           (* 2 pi (contents shape)))
          (else (error "Unknown shape -- PERIMETER")))) 
```

你应该能完全理解上面的代码！我们将在本课程的其余部分中始终使用这个以正方形和圆为例的示例。

## “put”一切都放在一起

使用页面顶部介绍的数据结构，现在系统可以处理任意数量的类型，而无需更改现有代码！以下是新代码的样子（构造函数保持不变）：

```
;;this is the data-directed version where types and operations 
;;are handled by a data structure that stores the information
(put 'square 'area (lambda (s) (* s s)))
(put 'circle 'area (lambda (r) (* pi r r)))
(put 'square 'perimeter (lambda (s) (* 4 s)))
(put 'circle 'perimeter (lambda (r) (* 2 pi r))) 
```

请注意，表格中每个单元格的条目都是一个函数，而不是一个符号。现在我们可以重新定义通用操作符（“通用”是因为它们适用于任何类型）：

```
;;this is the data-directed version where types and operations 
;;are handled by a data structure that stores the information    
(define (area shape-obj)
    (operate 'area shape-obj))

(define (perimeter shape-obj)
    (operate 'perimeter shape-obj))

(define (operate op obj)
    (let ((proc (get (type-tag obj) op)))
      (if proc
          (proc (contents obj))
          (error "Unknown operator for type")))) 
```

魔法发生在`operate`过程中。给定一个操作和一些数据，它会查找应用于该数据的正确过程。如果存在条目（这意味着我们知道如何处理该操作），那么我们只需应用该过程。否则，我们会抛出错误。

## 数据导向编程的澄清

不要认为数据导向编程只是指操作符和类型名称的二维表！DDP 是一个非常通用、伟大的想法。它意味着将系统的细节放入数据中，而不是放入程序中，这样你就可以编写通用程序，而不是非常具体的程序。

从前，每当一家公司获得一台计算机时，他们都必须雇佣一群程序员为他们编写诸如工资单程序之类的东西。他们不能只是使用别人的程序，因为细节会有所不同，例如，员工编号中有多少位数字。如今，你可以使用通用业务软件包，每家公司都可以根据自己的特定目的“调整”程序，使用数据文件。

另一个展示数据导向编程通用性的例子是编译器。过去，如果你想发明一种新的编程语言，你必须从头开始编写一个编译器。但现在我们有形式化符号来表达语言的语法。（请参阅课程阅读器背面的 Scheme 报告第 7.1 节，第 38 页。）一个程序可以读取这些形式化描述，并编译任何语言。
