# 局部状态

## 消息传递

在面向对象编程中让事情发生的方式是“请求”它们为您执行某些操作。我们这样做的方式类似于我们在第 6 课中进行的“消息传递”。在面向对象编程的术语中，我们如何做到这一点？

假设我们有两个对象：**`Matt-Account`**和**`Brian-Account`**，它们是`bank-account`类的实例。它们分别持有**Matt**和**Brian**拥有的金额。（你现在还不能在 Scheme 中输入这些！我们假设之前已经创建了这些对象。）

```
> (ask Matt-Account 'balance)
1000

> (ask Brian-Account 'balance)
10000

> (ask Matt-Account 'deposit 100)
1100

> (ask Brian-Account 'withdraw 200)
9800

> (ask Matt-Account 'balance)
1100

> (ask Brian-Account 'withdraw 200)
9600 
```

## `ask`

我们使用**`ask`**过程告诉对象执行某个动作。在上面的例子中，银行账户对象接受 3 条消息：

+   `balance`

+   `deposit`

+   `withdraw`

对于这 3 条消息，银行账户对象知道需要执行哪些操作。请注意，有些消息需要额外的信息：

+   对于**balance**，它不需要任何额外的参数。它返回账户中的金额。

```
> (ask Matt-Account 'balance)
1000
```

+   对于**deposit**和**withdraw**，我们需要另一个参数来指定我们要存入或取出的金额。

```
> (ask Matt-Account 'deposit 50000)
51000
```

这个比喻是一个对象“知道如何”执行某些任务。这些任务被称为**方法**。

**测试你的理解**

假设我们有一个 Max 的银行账户，并输入以下表达式：

```
(ask max-account 'balance)
1000

(define withdraw 'deposit)
```

从以下表达式返回什么？

```
(ask max-account 'withdraw 100)
```

如果，而不是之前的表达式，我们调用这个表达式：

```
(ask max-account withdraw 100)
```

## 状态

考虑这些调用：

```
> (ask matt-account 'balance)
500

> (ask brian-account 'balance)  
9999  

> (ask matt-account 'deposit 500)
1000

> (ask matt-account 'balance)
1000

> (ask matt-account 'withdraw 200)
800

> (ask matt-account 'balance)
800  

> (ask brian-account 'balance)  
9999 
```

**测试你的理解**

我们多次调用`(ask matt-account 'balance)`，每次返回不同的值。这告诉我们关于面向对象编程的什么？

`matt-account`和`brian-account`都返回每个人拥有多少钱。Matt 对他的账户的操作（对`matt-account`的方法调用）如何影响 Brian 的账户？

## 面向对象编程范式 vs. 函数式编程范式

在第一个问题中，我们看到 Matt 的余额在每次取款和存款时都会发生变化。这对我们来说感觉很自然，因为这就是银行账户的工作方式。但是，根据我们迄今为止使用的函数式编程范式，我们期望相同的调用返回相同的值。

在面向对象编程范式中，对象具有**状态**。也就是说，它们对过去发生的事情有一些了解。在这个例子中，一个银行账户有一个余额，当你存款或取款时，余额会发生变化。

### 局部状态变量

在第二个问题中，我们看到尽管 Matt 有他的'balance'，Brian 有他的'balance'，但它们互不干扰。

在面向对象编程术语中，我们说'balance'是一个**局部状态变量**，或者**实例变量**。实例变量对于不同的实例将具有不同的值。

我们可以在这里与以下定义进行类比

```
(define (square x)
    (* x x)) 
```

和

```
(define (cube x)
    (* x x x)) 
```

两个定义都使用了 x，但它们是独立的。
