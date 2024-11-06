# 作业 10

## 模板

你可以通过在终端中键入复制此作业��模板：

```
cp ~cs61as/autograder/templates/hw10.scm . 
```

你也可以通过点击[这里](http://inst.eecs.berkeley.edu/~cs61as/templates/hw10.scm)下载它。

## 练习 1

阅读[SICP 3.5.1](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-24.html#%_sec_3.5.1)，然后回答以下问题：

1.  `(delay (+ 1 27))`的值的类型是什么？

1.  `(force (delay (+ 1 27)))`的值的类型是什么？

## 练习 2

评估此表达式会产生错误：

```
(stream-cdr (stream-cdr (cons-stream 1 '(2 3)))) 
```

解释原因。

## 练习 3

考虑以下内容：

```
(define (enumerate-interval low high) 
  (if (> low high) 
      '() 
      (cons low (enumerate-interval (+ low 1) high)) ) )

(define (stream-enumerate-interval low high) 
  (if (> low high) 
      the-empty-stream 
      (cons-stream low (stream-enumerate-interval (+ low 1) high)) ) ) 
```

以下两个表达式之间有什么区别？

```
(delay (enumerate-interval 1 3))
(stream-enumerate-interval 1 3) 
```

## 练习 4

数论中一个未解决的问题涉及以下算法，用于创建一系列正整数[mathjaxinline]s_1, s_2, \ldots[/mathjaxinline]，其中[mathjaxinline]s_1[/mathjaxinline]是某个正整数，对于所有[mathjaxinline]n > 1[/mathjaxinline]，

+   如果[mathjaxinline]s_n[/mathjaxinline]是奇数，则[mathjaxinline]s_{n+1} = 3s_n+1[/mathjaxinline]；

+   如果[mathjaxinline]s_n[/mathjaxinline]是偶数，则[mathjaxinline]s_{n+1} = s_n \div 2[/mathjaxinline]。

无论选择什么起始值[mathjaxinline]s_1[/mathjaxinline]，该序列（称为*hailstone 序列*）似乎总是以重复的值 1、4、2、1、4、2、1...结束。然而，目前尚不清楚是否总是这种情况。

1.  编写一个过程`num-seq`，给定一个正整数`n`作为参数，返回`n`的 hailstone 序列。例如，`(num-seq 7)`应返回表示序列 7, 22, 11, 34, 17, 52, 26, 13, 40, 20, 10, 5, 16, 8, 4, 2, 1, 4, 2, 1, ...的流。

1.  编写一个过程`seq-length`，给定由`num-seq`生成的流作为参数，返回出现在序列中直到第一个 1 的值的数量。例如，`(seq-length (num-seq 7))`应返回 17。你应该假设序列中的某处有一个 1。

## 练习 5

又到了作业时间——SICP！

完成以下内容：[3.50, 3.51, 3.52](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-24.html#%_thm_3.50)，[3.53, 3.54, 3.55, 3.56](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-24.html#%_thm_3.53)，[3.64](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-24.html#%25_thm_3.64)，[3.66, 3.68](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-24.html#%25_thm_3.66)。

## 练习 6

编写并测试两个操作非负真分数的函数。

第一个函数`fract-stream`将以两个非负整数的列表作为其参数，分子和分母，其中分子小于分母。它将返回一个表示分数十进制扩展的无限流的十进制数字。

第二个函数`approximation`将接受两个参数：一个分数流和一个非负整数 numdigits。它将返回一个包含十进制扩展的前 numdigits 位数的列表（而不是流）。

一些指导方针：

+   `(fract-stream '(1 7))` 应返回代表小数的流

+   1/7 的展开式是 0.142857142857142857...

+   `(stream-car (fract-stream '(1 7)))` 应返回 `1`。

+   `(stream-car (stream-cdr (stream-cdr (fract-stream '(1 7)))))` 应返回

+   `2`。

+   `(approximation (fract-stream '(1 7)) 4)` 应返回 `(1 4 2 8)`。

+   `(approximation (fract-stream '(1 2)) 4)` 应返回 `(5 0 0 0)`。

## 提交您的作业！

指南请参见此指南。它涵盖了基本的终端命令和作业提交。

如果您在提交作业时遇到任何问题，请不要犹豫向助教求助！
