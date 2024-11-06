# 标记数据

## 标记数据简介

在我们创建通用操作符之前，我们首先必须能够跟踪数据类型。为什么呢？

回想一下第 4 课，我们实现了有理数。我们决定将有理数存储为一对，其中`car`保存分子，`cdr`保存分母。与此同时，我们的敌人，本·比特迪德尔，实现了复数。他也将这些数字表示为一对：`car`保存实部，`cdr`保存虚部。

![](img/tagged_data_1.gif) ![](img/tagged_data_2.gif)

现在，给定一个`car`是 3 且`cdr`是 4 的对，我们如何知道给定的数据表示有理数[mathjaxinline]\frac{3}{4}[/mathjaxinline]还是复数[mathjaxinline]3+4i[/mathjaxinline]？我们得到的原始数据可以以任何方式解释，所以我们无法确定！实际上，这对可能既不是这两者，实际上可能代表某种其他数据类型。这就是为什么我们需要一种将数据与其特定类型关联的系统。

（顺便说一句：此时，你可能会对本感到生气——他为什么要使用与我们相同的表示方式？！但是，他真的没有错。即使他使用了不同的内部表示，我们也*不能*使用此区别来检查数据的类型：我们将突破数据抽象屏障！）

解决方案是使用**标记数据**：每个数据片段都携带关于其类型的信息。我们可以通过给所有数据附加标记来实现这一点。为了做到这一点，我们需要一个构造函数来标记我们的数据（`attach-tag`），并选择器来从标记数据片段中获取标记和数据（`type-tag`和`contents`）。

下面是处理标记数据的可能实现。

```
(define (attach-tag tag data)
  (cons tag data))

(define (type-tag tagged-data)
  (if (pair? tagged-data)
      (car tagged-data)
      (error "Not tagged data")))

(define (contents tagged-data)
  (if (pair? tagged-data)
      (cdr tagged-data)
      (error "Not tagged data"))) 
```

你能想出另一组构造函数和选择器来使用不同的内部表示实现数据标记吗？

## 为有理数和复数标记

现在我们已经实现了标记数据，我们可以修复我们的有理数和复数数据类型的实现。我们的旧代码看起来像这样：

```
(define (make-rational numer denom)
  (cons num denom))

(define (make-complex real imag)
  (cons real imag)) 
```

但现在我们可以这样做：

```
(define (make-rational numer denom)
  (attach-tag 'rational (cons num denom)))

(define (make-complex real imag)
  (attach-tag 'complex (cons real imag))) 
```

请注意，我们完全可以用`attach-tag`替换函数`cons`，代码仍然可以正常工作。但这违反了我们创建的数据抽象屏障！

然后，我们可以使用`contents`编写选择器。例如，对于有理数：

```
(define (numer n)
  (car (contents n)))

(define (denom n)
  (cdr (contents n))) 
```

## 为标记数据编写过程

我们的目标是编写一个通用的加法过程。它应该适用于有理数和复数。

第一步是编写特定于输入数据类型的加法过程。使用我们在上一节刚刚编写的构造函数和选择器，这应该相当简单。

尝试以下操作：

1.  编写 `add-rational`，它接受两个有理数，并返回一个等于两个输入之和的有理数。记得通过使用适当的构造函数和选择器来尊重数据抽象。

1.  编写`add-complex`，它接受两个复数，并返回等于两个输入之和的复数。请记住 mathjaxinline + (c+di) = (a+c)+(b+d)i[/mathjaxinline]。

1.  假设我们已经编写了一个过程`add-rational-complex`，它按顺序接受有理数和复数，并正确地将它们相加。

1.  现在编写一个名为`add-numbers`的通用加法操作，它接受两个数字，每个数字可以是有理数或复数。我们应该依靠标记将我们的数据指向上面的正确过程。

在下面检查你的答案。

### 解决方案

你的`add-rational`应该是这样的：

```
(define (add-rational x y)
  (make-rational (+ (* (numer x) (denom y))
                    (* (numer y) (denom x)))
                 (* (denom x) (denom y)))) 
```

你的`add-complex`应该是类似的。请注意，由于`make-rational`、`numer`和`denom`创建的抽象屏障，我们不必担心标记。

现在是`add-numbers`：

```
(define (add-numbers num1 num2)
  (cond ((and (equal? (type-tag num1) 'rational)
              (equal? (type-tag num2) 'rational))
         (add-rational num1 num2))
        ((and (equal? (type-tag num1) 'complex)
              (equal? (type-tag num2) 'complex))
         (add-complex num1 num2))
        ((and (equal? (type-tag num1) 'rational)
              (equal? (type-tag num2) 'complex))
         (add-rational-complex num1 num2))
        (else
         (add-rational-complex num2 num1)))) 
```

太棒了！我们现在可以使用一个通用过程来添加数字了！

### 反思

让我们思考一下我们学到了什么：

1.  我们甚至不需要知道标记是如何实现的就能编写这个`add-numbers`！这是因为我们正确地*抽象了*这些细节。所以我们只需使用选择器`type-tag`来告诉我们正在处理的数据类型。

1.  如果我们想要将另一种类型的数字添加到我们的系统中，我们将不得不更改我们通用函数的定义，添加大量的额外条件来处理新的数据类型。在我们的情况下，修改将很简单，但这在较大的系统中不起作用。换句话说，我们的系统缺乏*可扩展性*。

尽管`add-numbers`的例子有点牵强，但实际上有许多系统确实使用了带标记的数据。事实上，Racket 解释器使用标记的数据来评估你的代码！

## 带标记数据的弱点

正如我们上面所暗示的，带标记的数据系统有几个关键弱点。

其中一个弱点是，每种数据类型都必须被识别并手动纳入每个通用过程中。例如，假设我们想要将新类型的数字纳入我们的系统。我们需要用一个类型来标识这个新的表示，然后编辑所有通用过程（`add-numbers、multiply-numbers、divide-numbers`等）以检查新类型并执行相应的操作。

另一个弱点是，即使单独设计了各个表示和相应的过程，我们也必须保证整个系统中没有两个过程具有相同的名称。这就是我们创建了新过程`add-numbers`的原因，它调用了`add-rational`、`add-complex`和`add-rational-complex`。

这两个弱点的根本问题是，实现通用接口的技术不具备可扩展性——实现通用程序的人必须每次添加新的表示或类型时修改这些程序。此外，最初编写有理数系统和复数系统的人现在必须修改他们的代码以避免名称冲突。在这些情况下，必须对代码进行的更改是直接的，但仍然必须进行，这是不便和错误的根源。
