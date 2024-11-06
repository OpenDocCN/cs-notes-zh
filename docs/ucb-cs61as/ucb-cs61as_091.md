# 本地状态变量

## 预览

让我们快速浏览一下我们将在本节中讨论的内容：

![](img/3153baea361d35852ff06442458a01c2.jpg)

```
(define (make-account balance) 
  (define (withdraw amount) 
    (set! balance (- balance amount)) balance) 
  (define (deposit amount) 
    (set! balance (+ balance amount)) balance) 
  (define (dispatch msg) 
    (cond 
      ((eq? msg 'withdraw) withdraw) 
      ((eq? msg 'deposit) deposit) ) ) 
  dispatch) 
```

你觉得呢？你对这个函数有什么想法吗？

## 提款

让我们从银行账户中取钱。我们将使用一个名为`withdraw`的过程来实现这一点，该过程以要提取的金额作为参数。如果账户中有足够的钱来容纳提款，则`withdraw`应返回提款后剩余的余额。否则，`withdraw`应返回消息`"余额不足"`。例如，如果我们账户中有$100，我们应该使用`withdraw`获得以下响应序列：

```
(withdraw 25)
75
(withdraw 25)
50
(withdraw 60)
"Insufficient funds"
(withdraw 15)
35 
```

注意到表达式`(withdraw 25)`，被评估两次，产生不同的值。

*等等，但我以为特定的带有相同参数的函数调用会返回相同的值！*

到目前为止，它一直是这样，但这是一个过程的新行为类型。我们所有的过程都可以看作是通过垂直线测试的函数。对过程的调用计算应用于给定参数的函数的值，并且对具有相同参数的同一过程的两次调用总是产生相同的结果。但在这种情况下，每次交易后都需要改变余额。否则，我们都会变得富有！

要实现`withdraw`，我们可以使用一个变量`balance`来表示账户中的余额，并将`withdraw`定义为一个访问余额的过程。提款过程检查余额是否至少与请求的金额一样多。如果是，`withdraw`将余额减少金额并返回余额的新值。否则，`withdraw`返回`余额不足`的消息。这里是`balance`和`withdraw`的定义：

```
(define balance 100)

(define (withdraw amount)
  (if (>= balance amount)
      (begin (set! balance (- balance amount))
             balance)
      "Insufficient funds")) 
```

通过表达式来减少余额

```
(set! balance (- balance amount)) 
```

这使用了`set!`特殊形式，其语法为

```
(set! [name] [new-value]) 
```

这里`[name]`是一个符号，`[new-value]`是任何表达式。`Set!`改变`[name]`，使其值为通过评估`[new-value]`获得的结果。在这种情况下，我们正在更改余额，使其新值为从余额的先前值中减去金额的结果。

`Withdraw`还使用`begin`特殊形式，在 if 测试为真的情况下导致两个表达式被评估：首先减少`balance`，然后返回`balance`的值。一般来说，评估表达式

```
(begin [exp1] [exp2] ... [expk]) 
```

导致表达式`[exp1]`到`[expk]`按顺序求值，并将最终表达式`[expk]`的值作为整个`begin`形式的值返回。

在你的 STk 解释器上使用`withdraw`、`set!`和`begin`进行玩耍！

## 有些不对劲...

在我们继续之前，再次检查`withdraw`和`balance`是如何定义的：

```
(define balance 100)

(define (withdraw amount)
  (if (>= balance amount)
      (begin (set! balance (- balance amount))
             balance)
      "Insufficient funds")) 
```

你看到可能会引起问题的地方了吗？

## 检测到问题

问题出在变量`balance`上。如上所述，`balance`是在全局环境中定义的名称，并且可以被任何过程自由访问以进行检查或修改。如果我们能够使`balance`在`withdraw`内部，那将更好，这样`withdraw`将是唯一可以直接访问`balance`的过程，而任何其他过程只能间接访问`balance`（通过调用`withdraw`）。这将更准确地模拟`balance`是`withdraw`使用的**局部状态变量**，用于跟踪账户状态的概念。

我们可以通过以下方式将`balance`变为`withdraw`内部：

```
(define new-withdraw
  (let ((balance 100))
    (lambda (amount)
      (if (>= balance amount)
          (begin (set! balance (- balance amount))
                 balance)
          "Insufficient funds")))) 
```

我们在这里所做的是使用`let`来建立一个具有局部变量`balance`的环境，其初始值为 100。在这个局部环境中，我们使用`lambda`创建一个以`amount`为参数并像我们先前的`withdraw`过程一样运行的过程。这个过程——作为评估`let`表达式的结果返回——是`new-withdraw`，它的行为与`withdraw`完全相同，但其变量`balance`不可被任何其他过程访问。

```
> (new-withdraw 10)
90
> (new-withdraw 30)
60 
```

在 STk 解释器上尝试使用`new-withdraw`，确保你理解它是如何工作的。

## `make-account`

这里是 SICP 中`make-account`过程的简化版本：

```
(define (make-account balance) 
  (define (withdraw amount) 
    (set! balance (- balance amount)) balance) 
  (define (deposit amount) 
    (set! balance (+ balance amount)) balance) 
  (define (dispatch msg) 
    (cond ((eq? msg 'withdraw) withdraw) 
          ((eq? msg 'deposit) deposit) ) ) 
  dispatch) 
```

现在，让我们尝试使用局部状态变量重写这个。填写下面代码中的空白，使结果与上面的`make-account`过程完全相同。也就是说，它响应相同的消息并产生相同的返回值。两个过程之间的区别在于上面的`make-account`内部被下面的`let`语句包围，并且`make-account`的参数名称不同。

```
(define (make-account init-amount) 
  (let (______________________) 
    (define (withdraw amount) 
      (set! balance (- balance amount)) balance) 
    (define (deposit amount) 
      (set! balance (+ balance amount)) balance) 
    (define (dispatch msg) 
      (cond ((eq? msg 'withdraw) withdraw) 
            ((eq? msg 'deposit) deposit) ) ) 
    dispatch) ) 
```

现在，修改`make-account`的任一版本，使其在给定消息`balance`时返回当前账户余额，并在给定消息`init-balance`时返回账户最初创建时的金额。例如，

```
> (define acc (make-account 100)) 
acc 
> (acc 'balance) 
100 
```

进行另一个修改，使得在给定消息 transactions（任何存款或取款）时，它返回自账户开户以来所做的所有交易的列表。例如：

```
> (define acc (make-account 100)) 
acc 
> ((acc 'withdraw) 50) 
50 
> ((acc 'deposit) 10) 
60
> (acc 'balance)
60
> (acc 'transactions) 
((deposit 10) (withdraw 50)) 
```

在查看下面的整个解决方案之前，在 STk 解释器中尝试你的定义，并确保你理解`make-account`的整个代码。

这是我们的解决方案：

```
(define (make-account init-amount) 
  (let ((balance init-amount)
        (transactions '())) 
    (define (withdraw amount) 
      (set! balance (- balance amount))
      (set! transactions (cons (list 'withdraw amount) transactions)) 
      balance) 
    (define (deposit amount) 
      (set! balance (+ balance amount))
      (set! transactions (cons (list 'deposit amount) transactions)) 
      balance) 
    (define (dispatch msg) 
      (cond ((eq? msg 'withdraw) withdraw) 
            ((eq? msg 'deposit) deposit)
            ((eq? msg 'balance) balance)
            ((eq? msg 'transactions) transactions) ) ) 
    dispatch) ) 
```

## 评估的替换模型

鉴于这个定义：

```
(define (plus1 var) 
  (set! var (+ var 1)) 
  var) 
```

遵循[替换模型](http://berkeley-cs61as.github.io/textbook/the-substitution-model-for-procedure-application.html)来找到计算结果

```
(plus1 5) 
```

即，展示将`var`替换为`5`后在`plus1`主体中得到的表达式，然后计算结果的值。

现在，在 STk 解释器中尝试一下。你得到了相同的答案吗？为什么？

引入赋值带来了相当大的代价。此时，你可能意识到我们不能再使用替换模型进行评估，因为它会产生错误的值。问题在于，替换最终基于我们语言中的符号本质上是值的名称这一概念。但是一旦我们引入`set!`和变量的值可以改变的概念，一个变量就不再仅仅是一个名称。现在一个变量在某种程度上指向一个可以存储值的位置，而存储在这个位置的值可以改变。

*那么我如何评估这些过程呢？*

新的评估模型在下一小节等着你。

## 要点

在本节中，你学到了：

1.  如何实现局部状态变量

1.  赋值的代价

1.  如何使用`set!`和`begin`

## 接下来是什么？

让我们去下一小节，学习关于新的评估模型！
