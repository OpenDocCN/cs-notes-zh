# 继承

## 介绍

您可以想象，随着我们的程序在 OOP 中变得越来越大，您将定义更多的对象和类。一些类将具有类似的特征。例如，您可能有一个`box`类，一个`safety-deposit-box`类和一个`locked-box`类。它们都需要了解类似的方法，比如向其中添加项目和从中移除项目。为每个类似的箱类重复编码将是多余的。我们想要的是定义一个通用类（如`box`类），它知道通用方法，比如`open`，然后让更具体的类（如`safe-deposit-box`类）从通用`box`类**继承**。

## 父母和子女

假设我们想创建一个`checking-account`类。支票账户与常规银行账户相同，只是您还可以在人与人之间提取支票。但是每次写支票时都要收取十美分的费用。

```
> (define Hal-Account (instantiate checking-account 1000))
Hal-Account
> (ask Hal-Account 'balance)
1000
> (ask Hal-Account 'deposit 100)
1100
> (ask Hal-Account 'withdraw 50)
1050
> (ask Hal-Account 'write-check 30)
1019.9 
```

实现`checking-account`的一种方法是复制我们为`account`类编写的所有代码，但如果我们需要更改我们的`account`，那么我们需要记得更改我们的`checking-account`。

在面向对象编程中，一个类是另一个类的专业化是非常常见的：新类将拥有旧类的所有方法，以及一些额外的方法，就像在这个银行账户示例中一样。为了描述这种情况，我们使用对象类族的比喻。原始类是父类，专业化版本是子类。我们说子类继承了父类的方法。（有时也使用子类和父类来表示子类和父类。）

## 父母

这是我们如何创建账户类的子类：

```
(define-class (checking-account init-balance)
    **(parent (account init-balance))**
    (method (write-check amount)
        (ask self 'withdraw (+ amount 0.10)) ))
```

这个示例介绍了`define-class`中的父类。在这种情况下，父类是`account`类。请注意，因为`account`类需要一个实例化变量，我们也需要提供该参数（因此为`(account init-balance)`）。

每当我们向`checking-account`对象发送消息时，对应的方法从哪里来？如果该名称的方法在`checking-account`类中定义，它将被使用；否则，OOP 系统将在父账户类中查找方法。如果父类没有该方法，我们将查看父类的父类，依此类推。

**检验你的理解**

这些问题跟随我们上面的`account`和`checking-account`类定义。

```
(define sam (instantiate checking-account 500))
```

这些中的哪一个将返回错误？

## 'self'关键字

`write-check`应该做什么？它应该将账户余额减少指定金额和额外费用。我们已经知道如何减少余额，那就是`withdraw`方法！要从另一个方法的主体中调用我们已经定义的方法，我们使用**self**，因此为`(ask self 'withdraw (+ amount 0.10))`。每个对象都有一个本地状态变量`self`，其值是对象本身。

## 范围

在某个类中定义的方法只能访问同一类中定义的局部状态变量。例如，在`checking-account`类中定义的方法不能引用在`account`类中定义的`balance`变量；同样，`account`类中的方法也不能引用`init-balance`变量。

这个规则对应于通常的 Scheme 规则关于变量作用域的规定：每个变量只在定义它的块内有效。（顺便说一句，并非每个面向对象的编程实现都是这样的。）

**测试你的理解**

类很棒！它们使对象有序。继承很棒！它们使类有序。要注意子类具有哪些状态以及哪些状态被更新。

```
>(define nick (instantiate checking-account 500))
>(ask nick 'init-balance)
500
>(ask nick 'balance)
500
>(ask nick 'deposit 50)
550
```

以下表达式返回什么？

```
(ask nick 'balance)
```

以下表达式返回什么？

```
(ask nick 'init-balance)
```

假设我们现在有以下代码片段：

```
(define-class (checking-account init-balance)
    (parent (account init-balance)) 
    (method (write-check amount)
        (ask self 'withdraw (+ amount 0.10)) )
    (method (show-balance) balance)  )

(define jeffrey (instantiate checking-account 500))
```

我们在类中添加了一个新方法，show-balance。那么（ask jeffrey 'show-balance）会返回什么？

## 要点

本小节的几个要点：

+   有些类将是另一个类的更“专业化”或“具体化”版本。在这些情况下，我们希望将特定类作为“父”类的“子”类。

+   子类继承父类的所有方法。

+   要跟踪哪个变量实际上在你的类中作用域。

## 接下来是什么？

我们将学习一个类可以拥有哪些类型的变量。
