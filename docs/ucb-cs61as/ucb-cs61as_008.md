# 作业 0.1

## 作业 0.1 介绍

在这个作业中，你将运用到目前为止学到的知识来解决一些问题。你还将进行一些阅读和自我介绍。

记住：你可以在首页或[截止日期表格](https://docs.google.com/spreadsheets/u/1/d/1JftJo7ko0wx-jxAEF9_QxYXfzHCYqCNqKeRwOU9K65A/edit?usp=sharing)上查看这个作业的截止日期。

## 模板

一个模板文件提供了一个作业任务的基本框架。

如果你在实验室电脑上，将以下命令输入到终端中，将模板复制到当前目录（注意末尾的句点）：

```
 cp ~cs61as/autograder/templates/hw0-1.rkt . 
```

或者你可以在这里下载模板[here](http://inst.eecs.berkeley.edu/~cs61as/templates/hw0-1.rkt)。

### 语言声明

你可能已经注意到第一行说

```
#lang racket 
```

这告诉 Racket 解释器你的文件包含 Racket 代码。这可能看起来多余，但 Racket 解释器也能理解其他 Lisp 家族语言，包括用户定义的语言。

底线是你必须在你写的每个 Racket 文件的顶部包含这行。如果不包含，你会看到这个错误信息：

```
default-load-handler: expected a `module' declaration 
```

## 自动评分程序

**自动评分程序**是一个检查特定作业代码有效性的程序。

如果你在实验室电脑上工作，`grader` 命令将运行自动评分程序；详情请参见下文。如果你在自己的个人电脑上工作，你应该下载[grader.rkt](http://inst.eecs.berkeley.edu/~cs61as/autograder/grader.rkt)和[HW 0-1 tests](http://inst.eecs.berkeley.edu/~cs61as/autograder/tests/hw0-1-tests.rkt)。

## 练习 0

首先，向工作人员介绍一下自己！

在你的作业文件中，回答以下问题：

1.  你叫什么名字？

1.  你的专业是什么？

1.  你是一名老生吗？（也就是，上学期你是否选修了 61AS？）

1.  是什么促使你选修 61AS？

1.  告诉我们一些关于你自己的有趣事情。

现在，看看你能否在 Piazza 上找到一篇名为“Hello World!”的帖子。在那篇帖子上跟进并介绍自己。确保包括：

+   名字

+   专业和年级

+   关于你自己的一个有趣事实

+   你为什么选择这门课程

## 练习 1

这是定义过程的语法：

```
(define ([name of procedure] [variables]) [body of procedure]) 
```

例如，你看到了如何定义一个 `square` 过程：

```
(define (square x) (* x x)) 
```

在定义完后，你可以使用 `square` 过程来找到任何你想要的数字的平方：

```
-> (square 3)
9 
```

使用 `square`，定义一个过程 `sum-of-squares`，它接受两个参数并返回这两个参数的平方和：

```
-> (sum-of-squares 3 4)
25 
```

确保测试你的工作！

写完你的过程后，运行这个练习的自动评分程序，检查你是否正确定义了过程。如果你在实验室电脑上，将以下内容输入到终端中：

```
grader hw0-1 hw0-1.rkt sum-of-squares 
```

如果你在自己的电脑上工作，将以下内容输入到终端中：

```
racket -tm grader.rkt -- hw0-1-tests.rkt hw0-1.rkt sum-of-squares 
```

## 插曲

在我们介绍下一个练习之前，我们需要了解更多的 Racket 特性。参加 0 单元的学生应该将其视为一个预览——我们将在第 0.2 课中更深入地探讨这些特性。

### 单词和句子

我们向您展示了一些有趣的过程，让您可以对单词和句子进行操作：

+   `'` 创建一个单词（例如，`'pi`）或一个句子（例如，`'(good morning)`）。

+   `first` 接受一个单词并返回该单词的第一个字母，或者接受一个句子并返回该句子的第一个单词。

+   `butfirst`（或 `bf`）接受一个单词/句子并返回除了第一个字母/单词之外的所有内容。

将这些过程和概念记在脑后。它们将在以后的练习和课程中再次出现。

### 特殊形式

Racket 有一些控制功能，允许您根据测试选择下一步要执行的操作。这些功能是特殊形式的例子——具有特殊评估规则的过程。我们稍后会在课程中更多地讨论特殊形式。

### `if`

在 Racket 中，`if` 是一个特殊形式，它接受三个参数。`if` 总是评估其第一个参数。如果该参数的值为`true`，则 `if` 评估其第二个参数并返回其值。如果第一个参数的值为`false`，则 `if` 评估其第三个参数并返回该值。

这是正确的 `if` 语法示例：

```
(if (= 5 (+ 2 3))
    'yay!
    (/ 1 0)) 
```

此示例表达式的结果是单词 `'yay!`。因为第一个表达式为真，所以 `if` 的最后一个参数不会被评估，这意味着我们不会得到除以零的错误。

### `cond`

`cond` 是一个特殊形式，它的行为就像 `if`，但有多个选项。每个条件逐一测试，直到有一个求值为`true`。通常在最后使用 `else` 子句来捕获所有先前条件都求值为`false`的情况。

以下是一个示例：

```
(cond ((= 3 1) 'wrong!)
      ((= 3 2) 'still-wrong!)
      (else 'yay)) 
```

在此示例中，前两个条件返回 `false`，因此整体表达式求值为单词 `'yay!`。

用于测试案例的一些好的过程是 `>`、`<` 和 `=`。

### `and`

`and` 检查其所有参数是否都为`true`：

```
-> (and (> 5 3) (< 2 4))
#t
-> (and (> 5 3) (< 2 1))
#f 
```

（注意 `#t` 和 `true` 可以互换使用，`#f` 和 `false` 也一样。）

为什么 `and` 是一个特殊形式？因为它对其参数进行求值，并在可以的情况下尽早停止，只要其中任何一个参数求值为`false`，它就会立即返回`false`。这事实上是很有用的。假设我们有以下内容：

```
(define (divisible? big small)
  (= (remainder big small) 0))
(define (num-divisible-by-4? x)
  (and (number? x) (divisible? x 4))) 
```

然后我们可以这样做：

```
-> (num-divisible-by-4? 16)
#t
-> (num-divisible-by-4? 6) 
#f
-> (num-divisible-by-4? 'aardvark)
#f 
```

注意最后一次调用并没有失败。由于`(number? 'aardvark)`的求值结果是`false`，在评估其第二个参数之前，`and`会返回`#f`。调用`(divisible? 'aardvark 4)`将会导致错误：

```
-> (divisible? 'aardvark 4)
; remainder: contract violation
;   expected: integer?
;   given: 'aardvark
;   argument position: 1st
; [,bt for context] 
```

此消息只是说，由于 `remainder` 过程期望一个整数，但实际传入的是 `'aardvark`，所以报告了一个错误。

关于 `and` 的一个微妙之处：如果其所有参数都求值为`true`，那么它不会简单地返回`#t`，而是返回其最后一个参数的值。

```
-> (and #t (+ 3 5))
8
-> (and (- 2 1) 100)
100 
```

任何不是 `#f` 的都是 `#t`。因此，`100` 是 `true`，`'foo` 是 `true`，等等。

#### `or`

`or` 检查其任一参数是否为`true`。

```
-> (or (> 5 3) (< 2 1))
#t
-> (or (> 5 6) (< 2 1))
#f 
```

为什么 `or` 是一个特殊形式？它对其参数进行求值，并在其中一个参数求值为`true`时立即停止。

```
> (or #f #t (/ 1 0))
#t 
```

关于`or`的一个微妙之处：与`and`一样，如果其任何一个参数求值为`true`，`or`将返回求值表达式的值，而不仅仅是`#t`。

```
-> (or #f (+ 1 2 3))
6
-> (or (* 3 4) (- 2 1))
12 
```

## 练习 2

### 第一部分

花点时间阅读上面的内容，并在解释器中尝试一切。然后，编写一个过程`can-drive`，以一个人的年龄作为参数。如果年龄低于 16 岁，则返回句子`'(Not yet)`。否则，返回句子`'(Good to go)`。确保在解释器中测试您的代码。

完成此练习后，请在终端中键入以下内容，运行自动评分器检查代码是否正确：

```
grader hw0-1 hw0-1.rkt can-drive 
```

或者，在您自己的计算机上：

```
racket -tm grader.rkt -- hw0-1-tests.rkt hw0-1.rkt can-drive 
```

### 第二部分

编写一个过程`fizzbuzz`，接受一个数字并输出`'fizz`，如果数字可被 3 整除，则输出`'buzz`，如果数字可同时被 3 和 5 整除，则输出`'fizzbuzz`，否则输出数字本身。您可能会发现函数`remainder`有用。确保在解释器中测试您的代码。

完成此练习后，请在终端中键入以下内容检查您的解决方案：

```
grader hw0-1 hw0-1.rkt fizzbuzz 
```

或者，在您自己的计算机上：

```
racket -tm grader.rkt -- hw0-1-tests.rkt hw0-1.rkt fizzbuzz 
```

## 练习 3

为什么海象要穿越塞伦盖蒂？

要找到答案，请在 Piazza 上查找标记为“Homework 0-1 Exercise 3 答案”的帖子。

## 练习 4

看看当您将以下代码片段键入解释器时会发生什么：

```
(define (infinite-loop) (infinite-loop))

(if (= 3 6)
  (infinite-loop)
  (/ 4 2)) 
```

现在我们想看看我们是否可以编写一个行为与`if`完全相同的过程。以下是我们的尝试：

```
(define (new-if test then-case else-case)
  (if test
    then-case
    else-case)) 
```

让我们试一试：

```
(new-if (= 3 6)
  (infinite-loop)
  (/ 4 2)) 
```

它不起作用！

这里是另一个示例，它的行为不对：

```
(new-if (= 3 6)
  (/ 1 0)
  (/ 4 2)) 
```

为什么`new-if`的行为不像`if`呢？从这个例子中你能学到什么关于`if`？思考一下并试着弄清楚。预计会再次遇到。

## 推荐阅读

推荐阅读如下：

+   [讲义笔记 1](http://inst.eecs.berkeley.edu/~cs61as/reader/notes.pdf)

+   [SICP 1.1](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-10.html#%25_sec_1.1)

## 手动测试

在运行自动评分器之前，您应该在 Racket 解释器中手动测试您的代码。这很重要，因为自动评分器不总是测试所有可能的情况。

要将单个定义加载到 Racket 中，请从终端启动 Racket 解释器，输入

```
racket 
```

然后从您的文件中复制并粘贴定义到解释器中。

要将整个文件加载到 Racket 中，请使用

```
racket -it hw0-1.rkt 
```

## 运行自动评分器

在提交任何作业之前，您需要进行两项检查：

1.  您的作业*必须*加载到 Racket 解释器中。任何无法加载的提交将不会得到任何学分。

1.  运行自动评分器检查您的答案。如果您无法使作业通过所有自动评分器测试，请不要担心。无论如何，请提交您的作业。请记住，作业是根据努力程度评分的。

要运行自动评分器，请在终端中键入以下内容：

```
grader <assignment name> <file name> 
```

例如，要在这份作业上运行自动评分器，请在终端中键入以下内容：

```
 grader hw0-1 hw0-1.rkt 
```

## 提交你的作业！

对于说明，请参阅此指南。它涵盖了基本的终端命令和作业提交。

如果您在提交过程中遇到任何问题，请不要犹豫向助教求助！
