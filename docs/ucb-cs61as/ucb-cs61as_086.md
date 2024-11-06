# 明确使用父类的方法

## 调用父类

我们的企鹅类有点拥挤！为了整理一下，让我们为它创建一个名为`emperor-penguin`的子类。它可以做所有`penguin`能做的事情，只是当它吃东西时，一个`emperor-penguin`在吃东西之前会说`'(bon apetit)`。以下定义是否有效？

```
(define-class (emperor-penguin name)
    (parent (penguin name))
    (method (eat)
        (print '(bon apetit!))
        (ask self 'eat))) 
```

![](img/d3fe4a1bf85482f335cb863a18bbe15c.jpg)

**测试你的理解**

让我们将`napoleon`定义如下：

```
(define napoleon (instantiate emperor-penguin 'napoleon))
```

当我们调用`(ask napoleon 'eat)`时会发生什么？

## 通常

调用父类方法的正确方式是使用**usual**关键字。

```
(define-class (emperor-penguin name)
    (parent (penguin name))
    (method (eat)
        (print '(bon apetit!))
        **(usual 'eat)))**
```

**usual**接受一个或多个参数，第一个是消息，其他的是消息需要的任何参数。然后将这个消息和必要的参数传递给父类。这样，一个`emperor-penguin`对象将引用`penguin`的`eat`方法。

调用通常就像是使用`(ask self ...)`一样，只是参数相同，只有在祖先类（父类、祖父类等）中定义的方法才能被使用。在没有父类的类中调用通常是错误的。

## 命名直觉

你可能会觉得`usual`是这个函数的一个有趣的名字。这是名字背后的想法：我们将子类视为特殊化。也就是说，父类代表一些广泛的事物类别，而子类是一个特殊化的版本。（想想支票账户与`accounts`的关系。）子对象几乎以与其父类相同的方式执行所有操作。子类有一些特殊的方式来处理一些消息，与通常方式（父类的方式）不同。但子类可以明确决定以通常（类似父类）的方式执行某些操作，而不是以自己的特殊方式。
