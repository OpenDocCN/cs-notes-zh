# 作业 8

## 模板

在终端上键入以下命令，将模板文件复制到当前目录：

```
cp ~cs61as/autograder/templates/hw8.scm . 
```

或者您可以在[这里](http://inst.eecs.berkeley.edu/~cs61as/templates/hw8.scm)下载。

## 练习

完成以下内容：

+   [SICP 3.3, 3.4](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-20.html#%_thm_3.3)

+   [SICP 3.7, 3.8](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-20.html#%_thm_3.7)

+   [SICP 3.10](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-21.html#%25_thm_3.10)

+   [SICP 3.11](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-21.html#%25_thm_3.11)

**注意：** 对于练习 3.3 和 3.4，您应该创建一个名为`make-password-account`而不是`make-account`的函数。

## 专家级额外内容

**如果您愿意，请执行此操作。这不计入学分。**

环境模型的目的是表示变量的作用域；当您在程序中看到一个`x`时，它指的是哪个变量`x`？解决这个问题的另一种方法是重命名所有局部变量，以便永远不会有两个同名变量。编写一个名为`unique-rename`的过程，它以一个`(quoted)` lambda 表达式作为参数，并返回一个将变量重命名为唯一的等效 lambda 表达式：

```
> (unique-rename '(lambda (x) (lambda (y) (x (lambda (x) (y x))))))
(lambda (g1) (lambda (g2) (g1 (lambda (g3) (g2 g3))))) 
```

请注意，原始表达式中有两个名为`x`的变量，在返回的表达式中，从名称中清楚地知道哪个是哪个。您将需要一个修改后的计数器对象来生成唯一的名称。

您可以假设没有`quote`、`let`或`define`表达式，因此每个符号都是一个变量引用，变量只能通过`lambda`创建。

描述如何使用`unique-rename`来允许仅有一个`(global)`帧的 Scheme 程序的评估。

## 提交您的作业！

有关说明，请参阅此指南。它涵盖了基本的终端命令和作业提交。

如果您在提交作业时遇到任何问题，请不要犹豫向助教求助！
