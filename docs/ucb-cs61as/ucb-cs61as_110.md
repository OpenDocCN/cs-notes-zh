# 可变列表结构

## 改变对

在第 2 单元中，我们使用对作为存储数据的��据结构的基础。我们已经看到我们现在正在进入一个可以改变数据的领域。也会有时候我们想要改变存储在数据结构中的内容。

`(define x (cons 1 2))`

![](img/lab9-1.png)

### `set-car!`

让`x`的`car`代表我摔下楼梯的次数，`cdr`代表我去错洗手间的次数。我刚刚摔了一层楼梯，所以我应该更新`x`的`car`为`2`。我们如何在不创建新对的情况下实现这一点？Scheme 允许我们使用以下函数`set!`来设置某个项目的值：

```
(set-car! x 2) 
```

正如其名称所示，`set-car!`接受一个对和一个值，并将其`car`更改为指向第二个参数指定的值。

![](img/lab9-2.png)

一般形式是

```
(set-car! <pair> <value>) 
```

### `set-cdr!`

正如你所期望的，Scheme 还为我们提供了函数`set-cdr!`，它接受一个对和一个值，并将该对的`cdr`指针更改为指向该值。继续上一个例子，调用

```
(set-cdr! x 3) 
```

将会改变成下面显示的对。

![](img/lab9-3.png)

一般的语法是

```
(set-cdr! <pair> <value>) 
```

## 改变指针

让我们看看`set-car!`和`set-cdr!`如何处理更复杂的列表。我们有以下对：

```
(define x (cons (list a b) (list c d)))
(define y (list e f)) 
```

![](img/e9eca21e818d614542c7d11dc0a02991.jpg)

对`set-car!`和`set-cdr!`的接下来几次调用是独立的，并且将基于这个原始配置。对于接下来的几个问题，强烈建议画出盒指针。

### 示例 1

调用的效果

```
(set-car! x y) 
```

对原始配置进行如下更改将得到以下盒指针图：

![](img/e8df21a04636ad2a014ee759e45a051d.jpg)

这个调用改变了`x`上的 car 指针，它最初指向`(list a b)`，现在指向`y`指向的地方：`(list e f)`。那么带有`a`和`b`的列表会发生什么？实际上对它没有任何影响，但由于它没有被引用的指针，这个列表就不再可达了。

**测试你的理解**

在上面的示例 1 中，`x`会打印什么？

假设我们有来自示例 1 的原始配置，现在我们决定调用以下表达式：

```
(set-car! (car x) 'z)
```

`y`会打印什么？

### 示例 2

从原始配置开始，我们现在调用

```
(define z (cons y (cdr x))) 
```

这给我们以下盒指针图：

![](img/753b11755ec16e689afc20e958891000.jpg)

+   `x`将打印出`((a b) c d)`

+   `y`将打印出`(e f)`

+   `z`将打印出`((e f) c d)`

**测试你的理解**

根据示例 2 中显示的配置，我们现在决定调用

```
(set-cdr! (cdr z) nil)
```

现在`x`会打印什么？

根据示例 2 中显示的配置，我们应该调用什么才能使`z`返回`((e f) b)`？

## 创建新的对

使用`set-car!`和`set-cdr!`修改现有的对。而`cons`和`list`等过程则创建新的对。那么`append`呢？它是否通过更改其中一个列表的`cdr`指针来“合并”两个列表？记住我们一直在使用的`append`的定义：

```
(define (append x y)
  (if (null? x)
      y
      (cons (car x) (append (cdr x) y)))) 
```

`append`通过`cons`连接`x`和`y`的元素形成一个新列表。这告诉我们`append`返回一个新列表。

![](img/lab9-4.png)

**测试你的理解**

当输入到 STk 时，以下代码片段会打印什么？先做一个有根据的猜测，然后在解释器中尝试。 > (define a (list 1 2 3 4 5)) a > (set-cdr! (cdr a) (cdddr a)) okay > a

过程`append!`类似于`append`，但它是一个变异器而不是一个构造器。它通过将它们拼接在一起来附加列表，修改`x`的最后一个对，使其`cdr`现在是`y`。（使用空的`x`调用`append!`是错误的。）例如，

```
(define (append! x y)
    (set-cdr! (last-pair x) y)
    x)
```

`last-pair`过程接受一个列表并返回列表的最后一个对：

```
 (define (last-pair x)
    (if (null? (cdr x))
        x
        (last-pair (cdr x))))
```

现在，让我们看看这段代码：

```
> (define x (list 'a 'b))
x      
> (define y (list 'c 'd))
y
> (define z (append x y))
z     
> z
(a b c d)
```

`(cdr x)`返回什么？在将其放入 STk 之前，请自行尝试。现在，看看以下对`append!`的调用

```
> (define w (append! x y))
w
> w
(a b c d)
```

现在`(cdr x)`返回什么？

## 共享和身份

前面的练习引起了一个重要的警示，即了解何时共享和创建对是重要的。在上面的代码中，`x`和`y`指向相同的对，而`z`则创建了一个具有相同元素的不同对。

![](img/lab9-5.png)

```
(define x (cons 1 2))
(define y x)
(define z (cons 1 2)) 
```

记得`equal?`谓词吗？它可以检查两个对是否包含相同的元素。

`(equal? x y)`、`(equal? x z)`、`(equal? y z)`都返回`#t`，因为它们在相同位置持有相同的元素。是否可能区分`x`和`z`指向不同的结构？是的！Scheme 有`eq?`谓词，它接受 2 个参数并检查这两个参数是否指向同一个对。

```
> (eq? x y)
#t
> (eq? x z)
#f
> (eq? y z)
#f 
```

## 要点

`set-car!`和`set-cdr!`分别改变`car`和`cdr`指针。像`cons`、`list`和`append`这样的过程会创建新的对。知道哪些对在不同列表之间共享对于确定改变一个是否会影响另一个至关重要。绘制框和指针图将非常有帮助。
