# 下线面向对象编程

## 下线

![](img/c3229d7fec712b3fbb256433b56ae890.jpg)

利用你新学到的环境知识，理解面向对象编程将会更加容易！我们称之为“below-the-line”，因为我们实现了面向对象编程的功能，而没有使用任何特殊的过程（比如 `define-class`）。

## 消息传递

让我们看一下以下代码：

```
(define (make-rectangular x y)
  (define (dispatch m)
    (cond ((eq? m 'real-part) x)
          ((eq? m 'imag-part) y)
          ((eq? m 'magnitude)
           (sqrt (+ (square x) (square y))))
          ((eq? m 'angle) (atan y x))
          (else
            (error "Unknown op -- MAKE-RECTANGULAR" m))))
  dispatch) 
```

在这个例子中，复数对象由一个分派过程表示。该过程以消息作为其参数，并将数字作为其结果返回。然而，`dispatch` 可以返回一个过程而不是一个数字，并且允许额外的参数传递给我们称之为响应消息的方法。

用户说

```
((acc 'withdraw) 100) 
```

评估这个表达式需要一个两步过程：

1.  调用分派过程（命名为 acc）并将消息 withdraw 作为其参数。

1.  `dispatch` 过程返回 `withdraw` 方法过程，然后第二个过程以 100 作为其参数被调用以执行实际工作。

一个对象的所有活动都来自于调用其方法过程；对象本身的唯一工作是在收到消息时返回正确的过程。

任何使用消息传递模型的面向对象编程系统都必须有一种下线机制，用于将方法与消息关联起来。在 Scheme 中，由于其一级过程，使用 `dispatch` 过程作为关联机制非常自然。在其他一些语言中，对象可能被表示为消息-方法对的数组。如果我们将对象视为抽象数据类型，使用对象的程序不应该知道我们恰好将对象表示为过程。调用方法的两步符号违反了这种抽象屏障。为了解决这个问题，我们发明了 ask 过程：

```
(define (ask object message . args)
  (let ((method (object message))) ; Step 1: invoke dispatch procedure
    (if (method? method)
        (apply method args)        ; Step 2: invoke the method
        (error "No method" message (cadr method))))) 
```

`ask` 执行的基本步骤与文本中使用的显式符号相同。首先，它使用消息作为参数调用分派过程（即对象本身）。这应该返回一个方法（另一个过程）。第二步是使用提供给 `ask` 的任何额外参数调用该方法过程。`ask` 的主体看起来比之前的版本复杂，但其中大部分与错误检查有关：如果对象无法识别我们发送的消息怎么办？这些细节并不是很重要。`ask` 使用了 Scheme 中我们之前未讨论过的两个特性：

在 `ask` 的形式参数列表中使用的点符号表示它接受任意数量的参数。前两个与形式参数对象和消息相关联；所有剩余的参数（零个或多个）都被放在一个列表中，并与形式参数 args 相关联。

过程`apply`接受一个过程和一组参数，并将该过程应用于这些参数。我们之所以在这里需要它，是因为我们事先不知道方法将会接收多少个参数；如果我们写成（方法 参数），我们将为方法提供一个参数，即一个列表。

在我们的面向对象编程系统中，通常将消息发送给实例，但也可以将一些消息发送给类，即检查类变量的消息。当您向类发送消息时，就像向实例发送消息一样，您会收到一个方法。这就是为什么我们可以同时向实例和类使用 ask。 （当您要求它创建一个新实例时，面向对象编程系统本身也会向类发送一个实例化消息。）因此，类和每个实例都由一个分派过程表示。类定义的整体结构看起来像这样：

```
(define (class-dispatch-procedure class-message)
  (cond ((eq? class-message 'some-var-name) (lambda () (get-the-value)))
         (...)
        ((eq? class-message 'instantiate)
         (lambda (instantiation-var ...)
           (define (instance-dispatch-procedure instance-message)
             (cond ((eq? instance-message 'foo) (lambda ...))
                    (...)
                   (else (error "No method in instance")) ))
             instance-dispatch-procedure))
        (else (error "No method in class")) )) 
```

（请注意，这并不是一个类真正的样子。在这个简化版本中，我们省略了许多细节。这里唯一关键的一点是有两个分派过程，一个在另一个内部。）在每个过程中，都有一个包含每个允许的消息的`cond`。每个子句的结果表达式是一个定义相应方法的`lambda`表达式。

## 本地状态（再次）

在前一小节中，您学会了如何为过程提供一个本地状态变量：在另一个建立变量的过程内定义该过程。因此，它可以被写成以下示例：

```
(define new-withdraw
  (let ((balance 100))
    (lambda (amount)
      (if (>= balance amount)
          (begin (set! balance (- balance amount)) balance)
          "Insufficient funds")))) 
```

在面向对象编程系统中，有三种类型的本地状态变量：类变量、实例变量和实例化变量。虽然实例化变量只是上面实例变量的一种特殊类型，但它们的实现方式不同。这里是另一种简化的类定义视图，这次省略了所有消息传递的内容，专注于变量：

```
(define class-dispatch-procedure
  (LET ((CLASS-VAR1 VAL1)
        (CLASS-VAR2 VAL2) ...)
    (lambda (class-message)
      (cond ((eq? class-message 'class-var1) (lambda () class-var1))
            ...
            ((eq? class-message 'instantiate)
             (lambda (INSTANTIATION-VARIABLE1 ...)
               (LET ((INSTANCE-VAR1 VAL1)
                     (INSTANCE-VAR2 VAL2) ...)
                (define (instance-dispatch-procedure instance-message)
                 ...)
                instance-dispatch-procedure))))))) 
```

类变量的作用域包括类分派过程、实例分派过程以及这些方法中的所有内容。实例变量的作用域不包括其方法中的类分派过程。每次调用类`instantiate`方法都会产生一组新的实例变量，就像书中每个新的银行账户都有自己的本地状态变量一样。

为什么类变量和实例变量使用`let`来实现，而实例化变量不是？原因在于类和实例变量由类定义本身给出它们的（初始）值。这就是`let`的作用：它建立了名称和值之间的关联。然而，实例化变量直到创建类的每个特定实例时才会获得值，因此我们将这些变量实现为将被调用以创建实例的`lambda`的形式参数。

## 继承和委托

继承是子类对象可以使用父类方法的机制。理想情况下，所有这些方法都应该成为子类的一部分；父类的过程定义将被“复制到”子类的 Scheme 实现中。我们的 OOP 系统的实际实现，尽管目的相同，但使用了一种稍微不同的技术，称为委托。每个对象的分发过程只包含其自身类的方法条目，而不包括其父类的方法。但每个对象在一个实例变量中有一个其父类的对象。为了更容易谈论所有这些对象和类，让我们看一个之前看过的例子：

```
(define-class (checking-account init-balance)
  (parent (account init-balance))
  (method (write-check amount)
    (ask self 'withdraw (+ amount 0.10)) )) 
```

让我们创建该类的一个实例：

```
(define Gerry-account (instantiate checking-account 20000)) 
```

那么名为`Gerry-account`的对象将具有一个名为`my-account`的实例变量，其值是账户类的一个实例。（变量“my-whatever”是由`define-class`自动创建的。）

这个父实例有什么好处呢？如果`Gerry-account`的分发过程无法识别某个消息，那么它将到达`cond`的`else`子句。在没有父类的对象中，该子句将生成一个错误消息。但如果对象有一个父类，`else`子句将把消息传递给父类的分发过程：

```
(define (make-checking-account-instance init-balance)
  (LET ((MY-ACCOUNT (INSTANTIATE ACCOUNT INIT-BALANCE)))
    (lambda (message)
      (cond ((eq? message 'write-check) (lambda (amount) ...))
            ((eq? message 'init-balance) (lambda () init-balance))
            (ELSE (MY-ACCOUNT MESSAGE)) )))) 
```

（当然，这是一个极为简化的图景。我们省略了类分发过程等其他细节。在实现中并没有一个名为`make-checking-account-instance`的过程；这个过程实际上是类的实例化方法，正如我们之前解释的那样。）

当我们向`Gerry-account`发送一个`write-check`消息时，它会以我们谈论的直接方式处理。但当我们向`Gerry-account`发送一个存款消息时，我们到达`cond`的`else`子句，消息被委托给父账户对象。该对象（即其分发过程）返回一个方法，而`Gerry-account`也返回该方法。

关键的理解是为什么`else`子句没有说

```
(else (ask my-parent message)) 
```

`Gerry-account`分发过程以消息作为其参数，并以方法作为其结果。你会记得，`Ask`执行一个两步过程，首先获取方法，然后调用该方法。在分发过程中，我们只想获取方法，而不是调用它。（在某处，有一个等待`Gerry-account`分发过程返回方法的`ask`调用，然后`ask`将调用该方法。）

委托技术存在一个缺点。当我们要求`Gerry-account`存入一些钱时，`deposit`方法只能访问`account`类的本地状态变量，而不能访问`checking-account`类的状态变量。同样，`write-check`方法也无法访问账户本地状态变量如`balance`。你可以看到为什么会出现这种限制：每个方法都是在一个类过程的范围内定义的过程，Scheme 的词法作用域规则限制了每个方法只能访问其范围包含的变量。继承和委托之间的技术区别在于基于继承的面向对象编程系统没有这种限制。我们可以通过使用请求另一个类（子类请求父类，反之亦然）返回（或修改）其变量的消息来绕过这种限制。`write-check`方法中的`(ask self 'withdraw ...)`就是一个例子。

## 花里胡哨

到目前为止所展示的简化 Scheme 实现隐藏了实际面向对象编程系统中的几个复杂之处。到目前为止，我们解释的确实是实现中最重要的部分，你不应该让接下来的细节让你对核心思想感到困惑。我们对这些事情给出了相当简要的解释，省略了令人讨厌的细节。

一个复杂之处在于多重继承。与将未知消息委托给一个父类不同，我们必须尝试多个父类。真正的`else`子句调用一个名为`get-method`的过程，该过程接受任意数量的对象（即分派过程）作为参数，除了消息之外。`Get-method`依次尝试在每个对象中找到一个方法；只有当所有父类都未提供方法时，它才会给出错误消息。（每个父类都将有一个"my-whatever"变量。）

影响`else`子句的另一个复杂之处是类定义中可能使用`default-method`的情况。如果使用了这个可选特性，`default-method`子句的主体将成为对象的`else`子句的一部分。

当一个实例被创建时，`instantiate`过程会向其发送一个`initialize`消息。每个调度过程都自动有一个对应的方法。如果在`define-class`中使用`initialize`子句，则方法包括该代码。但即使没有`initialize`子句，OOP 系统也有一些自己的初始化任务要执行。特别是，初始化必须为 self 变量提供一个值。每个`initialize`方法都以所需的 self 值作为参数。如果没有涉及父级或子级，则`self`只是对象自己的调度过程的另一个名称。但是，如果一个实例是某个子实例的`my-whatever`，那么`self`应该表示该子实例。解决方案是，子类的`initialize`方法使用子类自己的 self 作为参数调用父类的`initialize`方法。（子类如何获得自己的 self 参数？这是由`instantiate`过程提供的。）

最后，`usual`涉及一些复杂情况。每个对象都有一个`send-usual-to-parent`方法，它基本上复制了`ask`过程的工作，但它只在父级中查找方法，就像`else`子句所做的那样。调用`usual`会导致调用此方法。

## 计数器示例

现在让我们实现一个简单的计数器。每次调用`counter`时，它会增加自己的局部变量和所有计数器的全局变量。以下是我们计数器类的代码：

```
(define make-counter
    (let ((glob 0))
        (lambda ()
            (let ((loc 0))
                (lambda ()
                    (set! loc (+ loc 1))
                    (set! glob (+ glob 1))
                    (list loc glob)))))) 
```

它的工作方式如下：

```
> (define counter1 (make-counter))
counter1

> (define counter2 (make-counter))
counter2

> (counter1)
(1 1)

> (counter1)
(2 2)

> (counter2)
(1 3)

> (counter1)
(3 4) 
```

类变量`glob`是在包围外部 lambda 创建的环境中创建的，该 lambda 表示整个类。实例变量`loc`是在类 lambda 内部的环境中创建的，但在表示类的实例的第二个 lambda 之外。

**检验你的理解**

上面的示例展示了环境如何支持 OOP 中的状态变量，但简化了实例不是消息传递调度过程的事实。简而言之，这不是非常现实。

目前，我们调用计数器而没有参数，并返回该计数器的局部和全局变量的列表。更改此类以使计数器具有两种方法，要么是'local'或'global'。这两种方法中的每一种都接受正好一个参数：增加计数器的数字。你的代码应该像这样工作：

```
> (define counter1 (make-counter))
counter1
> (define counter2 (make-counter))
counter2

> ((counter1 'global) 5)
5
> ((counter2 'global) 3)
8
> ((counter1 'local) 2)
2
```
