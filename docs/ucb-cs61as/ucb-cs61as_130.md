# 作业 11

## 练习 0。

一些热身问题来检查你的理解：

+   列出在元循环求值器中调用`mc-eval`的所有过程。

+   列出在元循环求值器中调用`mc-apply`的所有过程。

+   解释为什么`make-procedure`不调用`mc-eval`。

## 作业 11 说明

一些学生抱怨本周的作业非常耗时。

因此，我们有些不情愿地将一些练习标记为可选；如果你真的时间紧迫，可以跳过这些。但如果你能完成所有练习，效果会更好！

可选练习后面有*。

## 模板

你可以通过在终端中输入以下内容来复制此作业的模板：

```
 cp ~cs61as/autograder/templates/hw11.scm . 
```

或者，你可以在[这里](http://inst.eecs.berkeley.edu/~cs61as/templates/hw11.scm)下载。

## 练习 1。

Abelson & Sussman，练习[4.3, 4.6, 4.7*, 4.10*](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-26.html#%_thm_4.3)，[4.11*, 4.13](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-26.html#%_thm_4.11)，[4.14](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-26.html#%_thm_4.14)，以及[4.15](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-26.html#%_thm_4.15)。

## 练习 4。

Abelson & Sussman，练习[4.1](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-26.html#%_thm_4.1)，[4.2, 4.4, 和 4.5](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-26.html#%_thm_4.2)。

## 练习 2*。

修改元循环求值器以允许对过程的参数进行类型检查。这个功能应该如何工作呢？当定义一个新过程时，形式参数可以是一个符号，如常规情况，或者是一个包含两个元素的列表。在这种情况下，第二个元素是一个符号���即形式参数的名称。第一个元素是一个表达式，其值是一个谓词函数，该参数必须满足。如果参数有效，该函数应返回`#t`。例如，这里是一个具有经过类型检查的参数 num 和 list 的过程 foo：

```
> (define (foo (integer? num) ((lambda (x) (not (null? x))) lst))
    (list-ref lst num))
> (foo 3 '(a b c d e))
d
> (foo 3.5 `(a b c d e))
Error: wrong argument type -- 3.5
> (foo 2 '())
Error: wrong argument type -- () 
```

在这个例子中，我们定义了一个名为`foo`的过程，它有两个形式参数，名为`num`和`list`。当调用`foo`时，求值器将检查第一个实际参数是否为整数，第二个实际参数是否不为空。其值为所需谓词函数的表达式应相对于`foo`的定义环境进行求值。（提示：考虑 extend-environment。）

## 更多挑战问题

如果你对本节感兴趣，这里还有一些可选练习。这些练习不计入学分。

+   Abelson & Sussman，练习[4.16 - 4.21](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-26.html#%_thm_4.16)。

## 提交你的作业！

有关说明，请参阅此指南。它涵盖了基本的终端命令和作业提交。

如果你在提交过程中遇到任何问题，请毫不犹豫地向助教求助！
