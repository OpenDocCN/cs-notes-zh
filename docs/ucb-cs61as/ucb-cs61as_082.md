# 类

要在面向对象编程中创建对象，您需要**实例化**一个类。`matt-account`和`brian-account`是“account”**类**的一部分。

```
> (define Matt-Account (instantiate account 1000))
Matt-Account

> (define Brian-Account (instantiate account 10000))
Brian-Account 
```

`instantiate`函数以其第一个参数作为类，并返回该类的新对象。`instantiate`可能需要根据特定类的不同而需要额外的参数：在这个例子中，创建账户时必须指定账户的初始余额。

## 定义一个类

面向对象程序中的大部分代码都是各种类的定义。一个类可以被视为某种对象的蓝图：“这种类型的对象应该能做什么？每个对象应该知道什么变量？”下面是账户类的定义。我们现在只实现一个方法，以后会添加更多内容。关于这段代码有很多要说的，我们会逐一解释。

```
(define-class (account balance) ;; define a class called account
    (method (deposit amount) 
        ;; objects of this class will have one method called deposit
        (set! balance (+ amount balance))
        balance)
        ;; deposit sets the balance the the current value plus the deposit amount and then returns the new balance
        ) 
```

## `define-class`

有一个新的特殊形式，`define-class`。`define-class`的语法类似于`define`的语法。在你期望看到你正在定义的过程的名称的地方，是你正在定义的类的名称。在过程的参数位置，是类的初始化变量：这些是必须作为额外参数给出的本地状态变量的初始值。在下面的例子中，初始化变量“balance”设置为 1000。

```
(define Matt-Account (instantiate account 1000)) 
```

类的主体由任意数量的子句组成；在这个例子中只有一种类型的子句，即方法子句，但我们以后会学习其他类型的子句。

## 方法

定义方法的语法也被选择为类似于定义过程的语法。方法的“名称”实际上是用于访问方法的消息。当我们说`(ask matt-account 'deposit 50)`时，实质上是说“在`matt-account`中，找到名称为'deposit 的方法，并用参数 50 调用该方法”。换句话说，`matt-account`将调用`(deposit 50)`。

有了我们现在的类定义，我们实际上可以执行`(ask matt-account 'balance)`。有些人可能会说：“但我们还没有为余额定义任何方法！”这是真的，但上面的代码仍然有效。对于类中的每个局部状态变量，都会自动定义一个同名的方法。这些方法没有参数，它们只返回该名称变量的当前值。因为我们在实例化`matt-account`时有状态变量`balance`，所以我们免费获得了同名的方法'balance。这是我们可以创建`state`的一种方式；我们将看到稍后的另一种方法。

## SET!

在`deposit`的主体中，我们引入了一个新的过程，`set!`。这个过程改变了状态变量的值。它的第一个参数是未求值的；它是你希望改变值的变量的名称。第二个参数是已求值的；这个表达式的值成为变量的新值。`set!`改变了变量的值，但不返回任何东西。

```
> (define a 3)
a

> a
3

> (set! a (+ 2 4))
okay ; What Scheme prints when nothing is returned

> a
6

> (set! a (+ a a))
okay  

> a  
12 
```

"set!"中的"!"是 Scheme 中用于改变某些东西的函数的约定（就像以"?"结尾的过程返回#t 或#f 的约定一样）。

**测试你的理解**

这看起来很像 define，但意义略有不同。Define 创建一个新变量，而 set!更改现有变量的值。看一下下面的代码：

```
(define a 10)
(define (change x)
  (define a 20)
  x)
(change 30)
```

现在`a`的值是多少？

相反，我们决定执行以下代码片段：

```
(define a 10)
(define (change x)
  (set! a 20)
  x)
(change 30)
```

现在`a`的值是多少？

如果我们尝试`set!`一个未定义的变量会发生什么？

```
(set! c 10)
```

在 STk 解释器上试一试。

## 定义'Withdraw'方法

我们定义了`deposit`方法，现在让我们看看如何定义`withdraw`方法。请注意，这些方法在类定义中出现的顺序并不重要。

```
(define-class (account balance)
    (method (deposit amount)
        (set! balance (+ amount balance))
        balance)  

    (method (withdraw amount)
        (if (< balance amount)
            "Insufficient Fund"
            (begin 
              (set! balance (- balance amount))
              balance))) 
```

再次，`withdraw`是一个接受一个参数`amount`的方法。如果`balance`中没有足够的钱，则返回"资金不足"。否则，减少`balance`的值并返回剩余的`balance`。我们正在使用一个新的特殊形式，`begin`。它实际上是做什么？

## 我应该从哪里开始？

想象一下，如果我们**不**使用`begin`特殊形式。你认为会发生什么？

```
(if (< balance amount)
    "Insufficient Fund"
    (set! balance (- balance amount))
    balance) 
```

`if`只接受 3 个参数：一个条件，然后情况，和否则情况。如果我们不使用`begin`，我们将有**四**个参数，解释器会抛出错误。到目前为止，在每个过程中，我们只评估一个表达式，以提供该过程的返回值。然而，一个过程仍然只能返回一个值。现在，有时我们想要评估一个表达式的执行而不是返回值，例如改变一个变量的值。对`begin`的调用表明`(set! amount (- amount balance))`和`balance`一起形成 if 的单个参数。

在下一节中，我们将讨论一个类如何从另一个类继承属性。
