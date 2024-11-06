# 作业 2

## 模板

在终端上输入以下命令将模板文件复制到当前目录（注意末尾的句点）：

```
cp ~cs61as/autograder/templates/hw2.rkt . 
```

或者您可以在[这里](http://inst.eecs.berkeley.edu/~cs61as/templates/hw2.rkt)下载模板。

## 自动评分器

如果您在实验室计算机上工作，`grader`命令将运行自动评分器��如果您在自己的个人计算机上工作，您应该下载[grader.rkt](http://inst.eecs.berkeley.edu/~cs61as/autograder/grader.rkt)和[HW 2 tests](http://inst.eecs.berkeley.edu/~cs61as/autograder/tests/hw2-tests.rkt)。 

## 练习 1

编写一个过程`substitute`，它接受三个参数：一个句子，一个旧单词和一个新单词。它应返回句子的副本，但是将每个旧单词的出现替换为新单词。

```
-> (substitute '(she loves you yeah yeah yeah) 'yeah 'maybe)
(she loves you maybe maybe maybe) 
```

## 练习 2

将以下内容输入到 Racket 中，并注意结果。看看你能否在让 Racket 进行计算之前预测结果。

```
(lambda (x) (+ x 3)) 
```

```
((lambda (x) (+ x 3)) 7) 
```

`make-adder`是一个返回另一个函数的函数。

```
(define (make-adder num)
  (lambda (x) (+ x num)))
((make-adder 3) 7) 
```

```
(define plus3 (make-adder 3))
(plus3 7) 
```

```
(define (square x) (* x x))
(square 5) 
```

```
(define sq (lambda (x) (* x x)))
(sq 5) 
```

```
(define (try f) (f 3 5))
(try +)
(try word) 
```

## 练习 3

考虑一个函数`g`，对于表达式

`((g) 1)`

在评估时返回值为`3`。

确定`g`有多少个参数。用一个词描述`g`返回的值的类型。

## 练习 4

对于以下每个表达式，为了使表达式的评估成功且不会引起错误，`f`必须是什么？对于每个表达式，给出一个`f`的定义，使得评估表达式不会引起错误，并说明根据你的定义，表达式的值是什么。明确地说，对于第一个，定义`f1`，对于第二个，定义`f2`，依此类推。

1.  `f1`

1.  `(f2)`

1.  `(f3 3)`

1.  `((f4))`

1.  `(((f5)) 3)`

## 练习 5

找出以下表达式的值，其中`add1`是一个将其参数加一的原始过程，`t`定义如练习 5 中所示：

```
(define (t f)
  (lambda (x) (f (f (f x)))) ) 
```

在计算机上尝试这些之前先解决它们。

1.  `((t add1) 0)`

1.  `((t (t add1)) 0)`

1.  `(((t t) add1) 0)`

## 练习 6

找出以下表达式的值，其中`t`的定义如练习 5 中所示，`s`定义如下：

```
(define (s x)
  (+ 1 x)) 
```

在计算机上尝试这些之前先解决它们

1.  `((t s) 0)`

1.  `((t (t s)) 0)`

1.  `(((t t) s) 0)`

## 练习 7

编写并测试`make-tester`过程。给定一个单词`w`作为其参数，`make-tester`返回一个带有一个参数`x`的过程，如果`x`等于`w`则返回`true`，否则返回`false`。

```
-> ((make-tester 'hal) 'hal)
#t
-> ((make-tester 'hal) 'cs61a)
#f
-> (define sicp-author-and-astronomer? (make-tester 'gerry))
-> (sicp-author-and-astronomer? 'hal)
#f
-> (sicp-author-and-astronomer? 'gerry)
#t 
```

## 练习 8

完成 SICP 练习[1.31a](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-12.html#%25_thm_1.31)，[1.32a](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-12.html#%25_thm_1.32)，[1.33](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-12.html#%25_thm_1.33)，[1.40](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-12.html#%25_thm_1.40)，[1.41](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-12.html#%25_thm_1.41)和[1.43](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-12.html#%25_thm_1.43)。对于其中一些问题，您需要阅读 SICP 文本的部分。

一些额外的指导方针：

+   对于 1.31a，你应该基于文本中较早的`sum`函数构建你的`product`函数。它应该接受四个参数（`term`、`a`、`next`和`b`）。找到`sum`函数并弄清楚每个参数的作用。

+   对于 1.31a，估算π的函数应该被称为`estimate-pi`（参见模板）。它不应接受任何参数，并且应使用给定公式的至少 100 个项来估算π。

+   对于 1.33，谓词应该是`filtered-accumulate`的最后一个参数（参见模板）。

+   对于 1.33，你应该定义函数`sum-sq-prime`和`prod-of-some-numbers`（参见模板）。

+   对于 1.40，不用担心学习牛顿法。只需完成`cubic`，它接受三个参数（`a`、`b`和`c`）并返回另一个过程。该过程应接受一个输入`x`，并在`x`处计算问题中显示的三次方程。

+   对于 1.43，将你的过程命名为`my-repeated`而不是`repeated`（参见模板）。

## 练习 9

上周你写了一个名为`squares`的过程，它会将其参数句子中的每个数字平方，并看到了`pigl-sent`，它会将其参数句子中的每个单词进行`pigl`处理。将这种模式概括为创建一个名为`my-every`的高阶过程，该过程将作为参数给定的任意过程应用于参数句子中的每个单词。

```
-> (my-every square '(1 2 3 4))
(1 4 9 16)
-> (my-every first '(nowhere man))
(n m) 
```

## 练习 10

使用高阶函数，我们的`simply-scheme`库提供了上一练习中的`every`函数和我们课程中展示的`keep`函数的自己版本。在尝试在计算机上运行之前，通过解决这些示例来熟悉它们：

1.  `(every (lambda (letter) (word letter letter)) 'purple)`

1.  `(every (lambda (n) (if (even? n) (word n n) n)) '(781 5 76 909 24))`

1.  `(keep even? '(781 5 76 909 24))`

1.  `(keep (lambda (letter) (member? letter 'aeiou)) 'bookkeeper)`

1.  `(keep (lambda (letter) (member? letter 'aeiou)) 'syzygy)`

1.  `(keep (lambda (letter) (member? letter 'aeiou)) '(purple syzygy))`

1.  `(keep (lambda (wd) (member? 'e wd)) '(purple syzygy))`

## 提交你的作业！

有关说明，请参阅此指南。它涵盖了基本的终端命令和作业提交。

如果在提交作业时遇到任何问题，请不要犹豫向助教寻求帮助！
