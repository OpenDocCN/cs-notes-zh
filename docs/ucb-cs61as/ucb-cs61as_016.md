# 作业 0.2

## 模板

在终端上键入以下命令，将模板文件复制到当前目录（注意末尾的句点）：

```
cp ~cs61as/autograder/templates/hw0-2.rkt . 
```

或者您可以在此处下载模板文件[here](http://inst.eecs.berkeley.edu/~cs61as/templates/hw0-2.rkt)。

## 自动评分程序

如果您在实验室计算机上工作，`grader`命令将运行自动评分程序。如果您在自己的个人计算机上工作，您应该下载[grader.rkt](http://inst.eecs.berkeley.edu/~cs61as/autograder/grader.rkt)和[hw0-2-tests](http://inst.eecs.berkeley.edu/~cs61as/autograder/tests/hw0-2-tests.rkt)。

## 练习 0

表达式`(+ 8 2)`的值为`10`。它是由三个原子组成的复合表达式。对于这个问题，写出另外五个值也为`10`的 Racket 表达式：

1.  一个原子

1.  由三个原子组成的另一个复合表达式

1.  由四个原子组成的复合表达式

1.  由一个原子和两个复合子表达式组成的复合表达式

1.  任何其他类型的表达��

## 练习 1

让我们构建一些处理单词和句子的函数。我们将给出上一个实验室的第二个过程。您可能还会发现 word 函数有用。

1.  编写一个过程`first-two`，接受一个单词作为参数，返回一个包含该参数前两个字母的两个字母单词。

1.  编写一个过程`two-first`，接受两个单词作为参数，返回一个包含这两个参数首字母的两个字母单词。

1.  现在编写一个过程`two-first-sent`，接受一个两个单词的句子作为参数，返回一个包含这两个单词首字母的两个字母单词。

```
-> (first-two 'ambulatory)
'am
-> (two-first 'brian 'epstein)
'be
-> (two-first-sent '(brian epstein))
'be 
```

## 练习 2

编写一个谓词`teen?`，如果其参数在 13 到 19 之间（包括 13 和 19），则返回`#t`。

```
-> (teen? 19)
#t
-> (teen? (/ 39 2))
#f 
```

## 练习 3

编写一个过程`indef-article`，接受一个单词作为唯一参数，并返回一个句子。请参考下面的示例，了解`indef-article`应该如何工作。请记住，以辅音字母开头的任何单词的不定冠词是"a"，以元音字母开头的任何单词的不定冠词是"an"。您可以忽略任何边缘情况。

```
-> (indef-article 'beetle)
'(a beetle)
-> (indef-article 'apple)
'(an apple) 
```

## 练习 4

编写一个过程`insert-and`，接受一个项目的句子，并返回一个在语法正确位置插入`and`的新句子。

```
-> (insert-and '(john bill wayne fred joey))
'(john bill wayne fred and joey) 
```

## 练习 5

编写一个过程`query`，通过交换前两个单词并在最后一个单词末尾添加问号，将一个陈述句转换为疑问句。您可以忽略任何边缘情况。

```
-> (query '(you are experienced))
'(are you experienced?)
-> (query '(i should have known better))
'(should i have known better?)
-> (query '(you were there))
'(were you there?) 
```

## 练习 6

编写一个过程`european-time`，将美国 AM/PM 制式时间转换为欧洲 24 小时制式时间。同时，编写`american-time`，实现相反的功能。

```
-> (european-time '(8 am))
8
-> (european-time '(4 pm))
16
-> (european-time '(12 am))
0

-> (american-time 21)
'(9 pm)
-> (american-time 12)
'(12 pm) 
```

## 练习 7

编写一个过程`describe-time`，接受秒数作为参数，并返回该时间量的更有用描述。假设一年有 365.25 天。您只需要考虑一天内的时间段。

```
-> (describe-time 45)
'(45 seconds)

-> (describe-time 930)
'(15.5 minutes) 
```

### 注意

您可能会注意到 Racket 对整数除法的处理有点奇怪：

```
-> (/ 1 2)
1/2 
```

你可以通过在一个或多个参数中使用小数点来强制 Racket 返回带有小数点的数字（也称为*浮点数*）：

```
-> (/ 1.0 2)
0.5 
```

## 练习 8

以下程序无法正常工作。为什么？请修复它并解释原因。

```
(define (superlative adjective word)
  (se (word adjective 'est) word)) 
```

这就是`superlative`应该如何工作的：

```
-> (superlative 'dumb 'exercise)
'(dumbest exercise) 
```

## 提交你的作业！

欲了解说明，请参阅此指南。它涵盖了基本的终端命令和作业提交。

如果在提交过程中遇到任何问题，请毫不犹豫地向助教求助！
