# 作业 1

## 模板

在终端输入以下命令，将模板文件复制到当前目录（注意末尾的句点）：

```
cp ~cs61as/autograder/templates/hw1.rkt . 
```

或者你可以在[这里](http://inst.eecs.berkeley.edu/~cs61as/templates/hw1.rkt)下载模板。

**如果你在这份作业上遇到困难，请查阅[Lesson 0.3](https://berkeley-cs61as.github.io/textbook/how-recursion-works.html)详细解释递归。**

## 自动评分程序

如果你在实验室计算机上工作，`grader`命令将运行自动评分程序。如果你在自己的个人机器上工作，你应该下载[grader.rkt](http://inst.eecs.berkeley.edu/~cs61as/autograder/grader.rkt)和[HW 1 tests](http://inst.eecs.berkeley.edu/~cs61as/autograder/tests/hw1-tests.rkt)。

## 练习 1

编写一个名为`dupls-removed`的过程，给定一个句子作为输入，返回从句子中删除重复单词后的结果。这个问题使用[递归](https://berkeley-cs61as.github.io/textbook/how-recursion-works.html)。

```
;; This should output (c a d e b)
(dupls-removed '(a b c a e d e b)) 
```

```
;; This should output (a b c)
(dupls-removed '(a b c)) ;; 
```

```
;; This should output (b a) 
(dupls-removed '(a a a a b a a)) 
```

作为提醒，你可以在实验室计算机上运行自动评分程序：

```
grader hw1 hw1.rkt dupls-removed 
```

或者在你自己的机器上：

```
racket -tm grader.rkt -- hw1-tests.rkt hw1.rkt dupls-removed 
```

## 练习 2

编写一个名为`count-word`的过程，以一个句子和一个单词作为参数，并输出句子中输入单词的出现次数。

```
;; This should output 2
(count-word '(i really really like 61as) 'really) 
```

```
;; This should output 0
(count-word '(i lambda racket) 'love) 
```

## 练习 3

解释如果在`pigl`过程中使用`new-if`（来自 Lab 0）而不是`if`会发生什么。

这是之前实验室中`pigl`的定义

```
(define (pigl wd)
  (if (pl-done? wd)
      (word wd 'ay)
      (pigl (word (bf wd) (first wd)))))

(define (pl-done? wd)
  (vowel? (first wd)))

(define (vowel? letter)
  (member? letter '(a e i o u))) 
```

## 练习 4

编写一个名为`squares`的过程，以一串数字作为参数，并返回这些数字的平方组成的句子。

```
;; This should output (1 4 9)
(squares '(1 2 3)) 
```

## 练习 5

编写一个名为`switch`的过程，以一个句子作为参数，并返回一个句子，其中每个`I`或`me`的实例都被替换为`you`，而每个`you`在句子开头以外的实例都被替换为`me`（句子中唯一应大写的词是`I`）。

```
;; This should output (I told you that you should wake me up)
(switch '(you told me that I should wake you up)) 
```

提示：考虑编写一个处理问题一般情况的辅助函数——也就是说，你的辅助函数不必担心“除了在句子开头”这部分。然后使用该辅助函数编写`switch`，并在`switch`的主体中处理特殊情况。

## 练习 6

编写一个名为`ordered?`的谓词，以一串数字作为参数，并在数字按升序排列时返回`#t`，否则返回`#f`。

```
(ordered? '(1 2 3)) ; #t 
```

```
(ordered? '(2 1 3)) ; #f 
```

```
(ordered? '(2)) ; #t 
```

## 练习 7

编写一个名为`ends-e`的过程，以一个句子作为参数，并返回一个只包含以字母 E 结尾的单词的句子。

```
;; This should output (please the above the blue)
(ends-e '(please put the salami above the blue elephant)) 
```

## 练习 8

大多数 Lisp 版本提供了像我们见过的`and`和`or`过程。原则上，这些可以是普通过程，但某些 Lisp 版本将它们作为特殊形式。

假设，例如，我们评估`(or (= x 0) (= y 0) (= z 0))`。如果`or`是一个普通过程，那么在调用 or 之前，所有三个参数表达式都将被评估。但是如果变量`x`的值为 0，我们知道整个表达式必须为真，而不管`y`和`z`的值如何。一个 Lisp 解释器，其中`or`是一个特殊形式，可以逐个评估参数，直到找到一个为真的参数或者用完所有参数。

设计一个测试，告诉你 Racket 的`and`和`or`是特殊形式还是普通函数。这是一个有点棘手的问题，但它会让你更深入地思考评估过程。为什么对于解释器来说，将`or`视为特殊形式并逐个评估其参数可能是有利的？你能想到为什么将`or`视为普通函数可能是有利的吗？

## 提交你的作业

**如果你在提交时遇到问题，请在 Piazza 上提问或联系助教。**

**提交前：** 确保你的文件在 Racket 中加载。你可以通过在 Racket 中输入`(enter! "hw1.rkt")`来验证，其中“hw1.rkt”是你的作业文件的名称。如果作业在 Racket 中无法加载，你将不会得到任何学分。

要提交你的作业，你需要在任何实验室计算机上登录。如果你想从家里提交，你必须远程连接到实验室计算机。稍后会详细介绍。

现在，在左侧点击“终端”图标。终端是一个终端仿真器，一种通过文本命令直接与计算机交互的方法。它有点像你整个计算机的“解释器”。你可以用 xterm 做一些有用的事情，比如导航和操作文件系统（类似于 Windows 资源管理器），提交作业（就像我们现在正在做的），以及启动 Racket 解释器（通过`racket`）！

让我们提交一个作业。这需要以下步骤：

1.  为作业创建一个文件夹（可选，但强烈建议，我们将看到原因）

1.  在那个文件夹中完成作业（或者如果你已经完成了作业，将文件移动到那个文件夹中）

1.  运行`submit`命令

1.  检查作业是否正确提交

我们将提交一个名为“units”的作业，这将告诉工作人员你要做多少单元。

### 创建一个文件夹

在终端中输入：

```
mkdir units 
```

这告诉计算机创建一个名为`units`的目录（文件夹）。你可以通过运行`ls`来双重检查它是否存在（还可以看到当前目录中还有什么）。

现在我们需要导航到那个文件夹，所以我们会执行：

```
cd units 
```

### 完成作业

为了完成这个任务，你必须创建一个名为`units`的文件（在名为`units`的目录中）。在那个文件中，写下你计划做哪些单元。例如，如果你要做 0、1、2 和 3 单元，你会写下

```
0 1 2 3 
```

请**不要**包含任何额外的空格或空行！

### 提交

创建完文件后，你可以通过以下方式提交作业

```
submit units 
```

这告诉计算机你想提交作业“units”。按照出现的任何指示操作。

### 检查你的提交

以下命令允许你查看你提交作业的时间：

```
glookup -t 
```

现在就是这些。你可能会对在家连接以便处理所有这些事情感兴趣。有关详细信息，请查看顶部的资源链接！
