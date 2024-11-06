# 作业 13

对于涉及编写查询或规则的所有问题，请测试您的解决方案。

运行查询系统并加载示例数据：

```
> (load "~cs61as/lib/query.scm")
> (initialize-data-base microshaft-data-base)
> (query-driver-loop) 
```

您现在处于查询系统的解释器中。

要添加一个断言：

```
(assert! (foo bar)) 
```

要添加一条规则：

```
(assert! (rule (foo) (bar))) 
```

其他任何内容都是一个查询。

## 练习 1

Abelson & Sussman，练习[4.56](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-29.html#%_thm_4.56)，[4.57, 4.58](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-29.html#%_thm_4.57)和[4.65](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-29.html#%_thm_4.65)。

## 练习 2：专家级别的额外练习

**如果你想的话可以这样做。这不计入学分。**

在本节的前面，我们描述了允许推断出单向反向关系的规则，即，

```
;;; Query input:
 (forward-reverse (a b c) ?what) 

;;; Query results:
 (FORWARD-REVERSE (A B C) (C B A)) 

;;; Query input:
 (forward-reverse ?what (a b c)) 

;;; Query results:
 ... infinite loop 
```

或者

```
;;; Query input:
 (backward-reverse ?what (a b c)) 

;;; Query results:
 (BACKWARD-REVERSE (C B A) (A B C)) 

;;; Query input:
 (backward-reverse (a b c) ?what) 

;;; Query results:
 ... infinite loop 
```

定义规则，使得可以推断出双向的反向关系，从而产生以下对话：

```
;;; Query input:
 (reverse ?what (a b c)) 

;;; Query results:
 (REVERSE (C B A) (A B C)) 

;;; Query input:
 (reverse (a b c) ?what) 

;;; Query results:
 (REVERSE (A B C) (C B A)) 
```

## 提交您的作业！

查看此指南获取说明。它涵盖了基本的终端命令和作业提交。

如果你在提交作业时遇到任何问题，请毋需犹豫地向助教求助！
