# 三种本地状态变量

## 概述

到目前为止，我们看到的唯一本地状态变量是实例化变量。在本小节中，我们将看到另外两种类型：实例变量和类变量。

## 实例变量

回想一下`checking-account`类：

```
(define-class (checking-account init-balance)
    (parent (account init-balance))
    (method (write-check amount)
        (ask self 'withdraw (+ amount 0.10)) )) 
```

每当我们写支票时，我们都会向账户收取额外的 10 美分。所有`checking-accounts`都以 10 美分的费用开始，但现在我们希望能够在进行过程中更改费用。一种方法是将`check-fee`作为一个实例化变量添加。

```
(define-class (checking-account init-balance check-fee)
    (parent (account init-balance))
    (method (write-check amount)
        (ask self 'withdraw (+ amount check-fee)) )
    (method (set-fee! fee)
        (set! check-fee fee)) ))

(define lily (instantiate checking-account 1000 0.10))
(define ted (instantiate checking-account 1000 0.10))
(define barney (instantiate checking-account 9999 0.10)) 
```

但这种格式稍微冗余，因为我们必须每次指定`check-fee`，即使我们总是希望它从 10 美分开始。我们将引入一个新的子句，**instance-vars**，解决我们的问题。

```
(define-class (checking-account init-balance)
    (parent (account init-balance))
    **(instance-vars (check-fee 0.10))**
    (method (write-check amount)
        (ask self 'withdraw (+ amount check-fee)))
    (method (set-fee! fee)
        (set! check-fee fee)) )
```

## 实例变量 vs. 实例化变量

实例化变量也是实例变量；也就是说，每个实例都有它们的私有值。唯一的区别在于表示法以及何时设置初始值。对于实例化变量，你在调用实例化时给出一个值，但对于其他实例变量，你在类定义中给出值。

## 类变量

第三种本地状态变量是类变量。与实例变量的情况不同，类变量对于整个类只有一个值。类的每个实例共享这个值。例如，假设我们想要有一个所有在同一项目上工作的`worker`类。也就是说，每当他们中的任何一个工作时，完成的工作总量都会增加。另一方面，每个工人在工作时都会单独感到饥饿。因此，类有一个共同的`work-done`变量，每个实例有一个单独的`hunger`变量。

```
(define-class (worker)
    (instance-vars (hunger 0))
    (class-vars (work-done 0))
    (method (work)
        (set! hunger (+ hunger 1))
        (set! work-done (+ work-done 1))
        'whistle-while-you-work ))  

> (define brian (instantiate worker))
brian
> (define matt (instantiate worker))
matt
> (ask matt 'work)
whistle-while-you-work
> (ask matt 'work)
whistle-while-you-work
> (ask matt 'hunger)
2
> (ask matt 'work-done)
2
> (ask brian 'work)
whistle-while-you-work
> (ask brian 'hunger)
1
> (ask brian 'work-done)
3
> (ask worker 'work-done)
3 
```

正如你所看到的，要求任何`worker`对象工作会增加`work-done`变量。相反，每个工人都有自己的`hunger`实例变量，所以当 Brian 工作时，Matt 不会感到饥饿。你可以询问任何实例类变量的值，或者你可以询问类本身。这是通常规则的一个例外，即消息必须发送给实例，而不是类。

**测试你的理解**

我们将设计一个“Dog”类。对于以下每一项，决定它们应该是狗类的“子类”、“父类”、“实例变量”、“类变量”还是“方法”。

（例如，如果我们问“cat?”，你认为猫应该是狗的父类，请输入“parent”）

关于狗类，“name”是一个：

关于狗类，“age”是一个：

关于狗类，“wag-tail”是一个：

关于狗类，“Animal”是一个：

## 总结

有三种本地状态变量：实例化、实例和类。

+   当你使用`instantiate`创建对象时，会指定一个实例化变量。

+   实例变量是每个对象都有的变量，彼此独立；改变一个的值不会影响其他的。

+   一个类变量是一个被该类的所有对象共享的变量；改变类变量的值，该类的每个对象都会注意到这个变化。
