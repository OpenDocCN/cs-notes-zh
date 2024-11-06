# 作业 4

## 模板

在终端中键入以下内容，将模板文件复制到当前目录（注意末尾的句点）：

```
cp ~cs61as/autograder/templates/hw4.rkt . 
```

或者你可以在这里下载模板[here](http://inst.eecs.berkeley.edu/~cs61as/templates/hw4.rkt)。

## 自动评分程序

如果你在实验室计算机上工作，`grader`命令将运行自动评分程序。如果你在自己的个人机器上工作，你应该下载[grader.rkt](http://inst.eecs.berkeley.edu/~cs61as/autograder/grader.rkt)和[HW 4 tests](http://inst.eecs.berkeley.edu/~cs61as/autograder/tests/hw4-tests.rkt)。

## 热身

尝试预测以下表达式将返回什么结果，然后用 Racket 解释器检查你的答案：

+   `(define x (cons 4 5))`

+   `(car x)`

+   `(cdr x)`

+   `(define y (cons 'hello 'goodbye))`

+   `(define z (cons x y))`

+   `(car (cdr z))`

+   `(cdr (cdr z))`

+   `(cdr (car z))`

+   `(car (cons 8 3))`

+   `(car z)`

+   `(car 3)`

## 练习 1

前几个练习涉及到[SICP 2.1.4](https://mitpress.mit.edu/sicp/full-text/book/book-Z-H-14.html#%_sec_2.1.4)。有关区间算术的详细信息，请参阅文本。

### SICP 2.7

艾莉莎的程序不完整，因为她没有指定区间抽象的实现。这是区间构造函数的定义：

```
(define (make-interval a b) (cons a b)) 
```

定义选择器`upper-bound`和`lower-bound`以完成实现。

### SICP 2.8

使用类似于艾莉莎的推理，描述如何计算两个区间的差。定义一个相应的减法过程，称为`sub-interval`。

### SICP 2.10

专家系统程序员本·比特迪德尔（Ben Bitdiddle）看着艾莉莎的代码，并评论说不清楚什么意思是通过跨越零的区间进行除法。修改艾莉莎的代码以检查这种情况，并在发生时发出错误信号。

**注意：** 跨越零意味着一个边界<=零，另一个边界>=零！

### SICP 2.12

定义一个构造函数`make-center-percent`，它接受一个中心和一个百分比容差，并生成所需的区间。你还必须定义一个选择器`percent`，为给定区间产生百分比容差。`center`选择器与上面显示的相同。

### SICP 2.17

定义一个过程`last-pair`，返回只包含给定（非空）列表的最后一个元素的列表：

```
-> (last-pair (list 23 72 149 34))
(34) 
```

### SICP 2.20

过程`+`、`*`和`list`接受任意数量的参数。定义这样的过程的一种方法是使用带有**点尾符号**的`define`。在过程定义中，最后一个参数名之前有一个点的参数列表表示，当调用过程时，初始参数（如果有）将像往常一样具有初始参数的值，但最后一个参数的值将是任何剩余参数的列表。例如，给定定义

```
(define (f x y . z) <body>) 
```

过程`f`可以接受两个或更多个参数。如果我们评估

```
(f 1 2 3 4 5 6) 
```

然后在`f`的主体中，`x`将是`1`，`y`将是`2`，`z`将是列表`'(3 4 5 6)`。鉴于定义

```
(define (g . w) <body>) 
```

过程`g`可以不带参数或带一个或多个参数调用。如果我们评估

```
(g 1 2 3 4 5 6) 
```

然后在`g`的主体中，`w`将是列表`'(1 2 3 4 5 6)`。

使用这种表示法编写一个过程`same-parity`，它接受一个或多个整数，并返回与第一个参数具有相同奇偶性的所有参数的列表。例如，

```
-> (same-parity 1 2 3 4 5 6 7)
(1 3 5 7)

-> (same-parity 2 3 4 5 6 7)
(2 4 6) 
```

### SICP 2.22

路易斯·里森尼试图重写练习 2.21 的第一个`square-list`过程，以便演变出一个迭代过程：

```
(define (square-list items)
  (define (iter things answer)
    (if (null? things)
        answer
        (iter (cdr things) 
              (cons (square (car things))
                    answer))))
  (iter items nil)) 
```

不幸的是，以这种方式定义`square-list`会产生与所需顺序相反的答案列表。为什么？

然后路易斯尝试通过交换`cons`的参数来修复他的错误：

```
(define (square-list items)
  (define (iter things answer)
    (if (null? things)
        answer
        (iter (cdr things)
              (cons answer
                    (square (car things))))))
  (iter items nil)) 
```

这也不起作用。请解释。

## 练习 2

编写一个过程`my-substitute`，它接受三个参数：一个列表，一个旧单词和一个新单词。它应返回列表的副本，但是将每个旧单词的出现替换为新单词，即使在子列表中也是如此。例如：

```
-> (my-substitute '((lead guitar) (bass guitar) (rhythm guitar) drums)
                  'guitar
                  'axe)
((lead axe) (bass axe) (rhythm axe) drums) 
```

你可能会发现过程`list?`很有用：

```
-> (list? (list 1 2 3))
#t
-> (list? 'apple)
#f
-> (list? 4)
#f 
```

## 练习 3

现在编写`my-substitute2`，它接受一个列表，一个旧单词列表和一个新单词列表；最后两个列表应该具有相同的长度。它应返回第一个参数的副本，但将出现在第二个参数中的每个单词替换为第三个参数中对应的单词：

```
-> (my-substitute2 '((4 calling birds) (3 french hens) (2 turtle doves))
                   '(1 2 3 4)
                   '(one two three four))
((four calling birds) (three french hens) (two turtle doves)) 
```

## 专家专用

如果你想挑战自己，可以尝试这些。这些*不*计入学分。

### 练习 4

编写过程`cxr-function`，其参数是以 c 开头，以 r 结尾，并在中间有一串字母 a 和/或 d 的单词，例如`cdddadaadar`。它应返回相应的函数。

### 练习 5

[SICP Ex. 2.6](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-14.html#%_thm_2.4)。除了加法，还要发明非负整数的乘法和指数运算。如果你真的很热情，看看能否发明减法。（记住，这个游戏的规则是你只有 lambda 作为起点。）阅读`~cs61as/lib/church-hint`以获取一些建议。

### 练习 6

[SICP Ex. 2.18](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-15.html#%_thm_2.18)；这需要一些思考，你应确保做对，但不要为此卡壳一个小时。注意：你的解决方案应该颠倒列表，而不是句子！也就是说，你应该使用`cons`、`car`和`cdr`，而不是`first`、`sentence`等。

## 提交你的作业！

有关说明，请参阅此指南。它涵盖了基本的终端命令和作业提交。

如果你在提交作业时遇到任何问题，请不要犹豫向助教求助！
