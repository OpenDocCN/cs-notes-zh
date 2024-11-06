# 作业 9

## 模板

在终端上键入以下命令将模板文件复制到当前目录（注意末尾的句点）：

```
cp ~cs61as/autograder/templates/hw9.scm . 
```

或者您可以在此处下载模板[here](http://inst.eecs.berkeley.edu/~cs61as/templates/hw9.scm)。

## 练习 1

假设已提供以下定义。

```
(define x (cons 1 3))
(define y 2) 
```

一位 CS 61AS 学生打算将`x`的值更改为一个`car`等于`1`且`cdr`等于`2`的对，他输入表达式`(set! (cdr x) y)`而不是`(set-cdr! x y)`，结果出现错误。请解释原因。

## 练习 2

**a)** 在下面的空白处为两个`set-cdr!`操作提供参数，以产生对`list1`和`list2`的指定效果。不要创建任何新对；只重新排列现有对的指针。

```
> (define list1 (list (list 'a) 'b))
list1 

> (define list2 (list (list 'x) 'y))
list2 

> (set-cdr! ________ ________)
okay 

> (set-cdr! ________ ________)
okay 

> list1
((a x b) b) 

> list2
((x b) y) 
```

**b)** 在填写上述代码中的空白并对`list1`和`list2`产生指定效果后，绘制一个解释表达式`(set-car! (cdr list1) (cadr list2))`求值效果的框和指针图。

## 练习 3

完成阿贝尔森和苏斯曼的[3.13 和 3.14 练习](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-22.html#%_thm_3.13)。

## 练习 4

在阿贝尔森和苏斯曼的[3.16, 3.17](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-22.html#%_thm_3.16)、[3.21](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-22.html#%_thm_3.21)、[3.25 和 3.27](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-22.html#%_thm_3.25)中完成练习。

**注意：** 您不需要为练习 3.27 绘制环境图；使用`trace`过程提供所请求的解释。将表过程`lookup`和`insert!`视为原始；即不要跟踪它们调用的过程。此外，假设这些过程在常数时间内工作。我们对`memo-fib`被调用的次数感兴趣。

## 练习 5

编写`vector-append`，它接受两个向量作为参数，并返回一个包含两个参数元素的新向量，类似于列表的`append`。

**不要将列表用作中间值。（也就是说，任何时候都不要将向量转换为列表！）**

## 练习 6

编写`vector-filter`，它接受一个谓词函数和一个向量作为参数，并返回一个仅包含谓词返回`true`的参数向量元素的新向量。新向量应该正好足够容纳所选元素。将您的程序的运行时间与此版本进行比较：

```
(define (vector-filter pred vec)
    (list->vector (filter pred (vector->list vec)))) 
```

**不要将列表用作中间值。（也就是说，任何时候都不要将向量转换为列表！）**

## 练习 7

对向量进行排序：

**a)** 编写`bubble-sort!`，它接受一个数字向量并重新排列为递增顺序。（你将修改参数向量；不要创建新的。）使用以下算法进行定义：1\. 遍历数组，一次查看两个相邻的元素，从元素 0 开始。如果较早的元素大于较晚的元素，则交换它们。然后查看下一个重叠的对（0 和 1，然后 1 和 2，依此类推）。2\. 递归地`bubble-sort`除了最后一个元素之外的所有元素（现在是最大的元素）。3\. 当只有一个元素需要排序时停止。

**b)** 证明这个算法确实对向量进行了排序。**提示：证明第 2 步中的括号声明。**

**c)** 这个算法的运行时间增长顺序是多少？

**不要使用列表作为中间值。（也就是说，任何时候都不要将向量转换为列表！）**

## 专家级额外练习：练习 8

**如果你愿意的话可以做这个。这不计入学分。**

Abelson & Sussman，练习[3.19](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-22.html#%_thm_3.19)和[3.23](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-22.html#%_thm_3.23)。

练习 3.19 尤为具有挑战性，所以如果你解决了它，那就太棒了。你需要查看一些你可能在本节中跳过的其他练习。练习 3.23 稍微容易一些，但要注意Θ(1)运行时间要求。

## 专家级额外练习：练习 9

**如果你愿意的话可以做这个。这不计入学分。**

编写过程`cxr-name`。它的参数将是由`cars`和`cdrs`组合而成的函数。它应返回该函数的适当名称：

```
> (cxr-name (lambda (x) (cadr (cddar (cadar x)))))
CADDDAADAR 
```

## 提交你的作业！

有关说明，请参阅此指南。它涵盖了基本的终端命令和作业提交。

如果提交时遇到任何问题，请不要犹豫向助教求助！
