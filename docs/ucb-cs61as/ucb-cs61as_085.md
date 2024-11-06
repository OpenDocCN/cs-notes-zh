# 初始化和默认

## 初始化

浏览`penguin`类：

```
(define-class (penguin name)
    (class-vars (all-penguin nil)
                (favorite-food 'tuna))
    (instance-vars (hunger 50)
                   (weight 350))
    (method (eat)
        (set! hunger (- hunger 1))
        (set! weight (+ weight 5))
        (se 'That favorite-food '(was delicious!))))

> (define jack (instantiate penguin 'jack))

> (ask jack 'eat)
(that tuna was delicious!)

> (ask jack 'hunger)
49

> (ask jack 'weight)
355 
```

企鹅有 2 个实例变量：它的`hunger`和`weight`。企鹅类有 2 个类变量：它的最爱食物是`tuna`，以及`all-penguin`，它是一个包含所有已创建企鹅名称的列表。当前，`all-penguin`从不更新。在某些情况下，比如这种情况，我们希望我们的对象在创建时执行某个特定的操作。我们可以使用**`initialize`**子句来实现这一点。

![图片](http://wikimotive.com/wp-content/uploads/sites/2/2013/05/Cute-Penguin- Wallpaper-2013.jpg)

## 在实例化后

一旦企鹅对象被实例化，我们希望它：

1.  说出他的名字并且

1.  将自己添加到`all-penguin`列表中。这是我们如何使用初始化子句来做到的：

```
(define-class (penguin name)
    (class-vars (all-penguin nil)
                (favorite-food tuna))
    (instance-vars (hunger 50)
                   (weight 350))
    **(initialize (print (se '(hi my name is) name))
                (set! all-penguin (cons name all-penguin)))**
    (method (eat)
        (set! hunger (- hunger 1))
        (set! weight (+ weight 5))
        (se 'That favorite-food '(was delicious!))))

> (define jack (instantiate penguin 'jack))
(hi my name is jack)

> (define jennie (instantiate penguin 'jennie))
(hi my name is jennie)

> (ask penguin 'all-penguin)
(jennie jack)

> (ask jack 'all-penguin)
(jennie jack)
```

## 默认方法

所以，这是迄今为止我们对企鹅类的定义：

```
(define-class (penguin name)
    (class-vars (all-penguin nil)
                (favorite-food 'tuna))
    (instance-vars (hunger 50)
                   (weight 350))
    (initialize (print (se '(hi my name is) name))
                (set! all-penguin (cons name all-penguin)))
    (method (eat)
        (set! hunger (- hunger 1))
        (set! weight (+ weight 5))
        (se 'That favorite-food '(was delicious!)))) 
```

让我们假设我们调用了以下方法：

```
> (define jack (instantiate penguin 'jack))
(hi my name is jack)

> (ask jack 'favorite-food)
tuna

> (ask jack 'eat)
(That tuna was delicious!)

> (ask jack 'back-flip)
*** Error: No method back-flip in class penguin 
```

看起来`jack`不知道如何进行`back-flip`。目前我们的企鹅只知道一小部分消息，但作为企鹅类的设计者，我们不希望它们对每条其他消息都抛出错误。相反，如果一个企鹅看到它不理解的消息，我们希望它吃东西。我们可以使用**default-method**子句来实现这一点。看看我们企鹅类的添加：

```
(define-class (penguin name)
    (class-vars (all-penguin nil)
                (favorite-food 'tuna))
    (instance-vars (hunger 50)
                   (weight 350))
    (initialize (print (se '(hi my name is) name))
                (set! all-penguin (cons name all-penguin)))
    (method (eat)
        (set! hunger (- hunger 1))
        (set! weight (+ weight 5))
        (se 'That favorite-food '(was delicious!)))
    **(default-method
        (print (se '(I dont know how to) message '(I will eat instead)))
        (ask self 'eat)))**
```

现在我们调用这些方法：

```
> (define jack (instantiate penguin 'jack))
(hi my name is jack)

> (ask jack 'back-flip)
(I dont know how to back-flip I will eat instead)
(that tuna was delicious!)

> (ask jack 'weight)
355

> (ask jack 'fly)
(I don't know how to fly I will eat instead)
(that tuna was delicious!)

> (ask jack 'weight)
360 
```

![图片](img/e939e754b584aa6534cb464fcf312b2b.jpg)

## 消息和参数

注意，在上面的 default-method 中，我们使用消息来找出我们传递给对象的消息是什么。类似地，我们也可以使用 args 来找出其他参数被传递为列表的情况。

例如，如果我们调用

```
(ask jack 'do-math 1 2 5 10) 
```

然后，变量`message`将指向`'do-math`，而变量`args`将指向`(1 2 5 10)`。
