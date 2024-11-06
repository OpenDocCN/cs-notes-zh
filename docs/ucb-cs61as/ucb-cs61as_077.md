# 作业 6

在终端键入以下命令将模板文件复制到当前目录（注意末尾的句点）：

```
cp ~cs61as/autograder/templates/hw6.rkt . 
```

或者你可以在[这里](http://inst.eecs.berkeley.edu/~cs61as/templates/hw6.rkt)下载模板。

## 自动评分程序

要在计算机上运行自动评分程序，请在此处下载测试文件：[here](http://inst.eecs.berkeley.edu/~cs61as/autograder/tests/hw6-tests.rkt)。按照之前课程的说明操作。

## 练习 0

**练习 0 包括来自课程的问题。强烈建议完成。这不计入学分。**

从文件中加载 racket-1 解释器

`~cs61as/lib/racket1.rkt`

要启动解释器，请键入`(racket-1)`。通过评估一些表达式来熟悉它。记住：你有所有 Racket 的算术和列表操作原语；你有 lambda 但没有高阶函数；你没有定义。要停止 racket-1 解释器并返回 Racket，只需评估一个非法表达式，例如`()`。

0a. 详细跟踪一个简单的过程调用，例如

`((lambda (x) (+ x 3)) 5)`

在 racket-1 中处理。

0b. 尝试发明高阶过程；由于你没有定义，你将不得不使用 Y 组合子技巧，就像这样：

```
Racket-1:
((lambda (f n)  ; this lambda is defining MAP 
    ((lambda (map) (map map f n)) 
    (lambda (map f n) 
        (if (null? n) 
            '() 
            (cons (f (car n)) (map map f (cdr n))) )) )) ;end of lambda defining MAP 
first              ; the argument f for MAP
'(the rain in spain)) ; the argument n for MAP

(t r i s) 
```

0c. 由于 racket-1 中自动可用所有 Racket 原语，你可能认为可以使用 Racket 的原始 map 函数。尝试这些示例：

```
Racket-1: 
(map first '(the rain in spain))`

Racket-1: 
(map (lambda (x) (first x)) '(the rain in spain)) 
```

解释结果。

0d. 修改解释器以添加 and 特殊形式。测试你的工作。确保一旦计算出 false 值，你的 and 会返回 #f 而不再评估任何其他参数。

## 练习 1

完成以下内容：

阿贝尔森与苏斯曼，练习 [2.74, 2.75, 2.76](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-17.html#%25_thm_2.74)，[2.77, 2.79, 2.80](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-18.html#%25_thm_2.77)，[2.81, 2.83](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-18.html#%25_thm_2.81)

注意：其中一些是思考练习；你不需要实际运行任何 Scheme 程序！（有些不要求你编写过程；其他要求修改不在线上的程序。）

## 练习 2

为 `racket-1` 编写一个 `map` 原语（称为 `map-1`，以便你和 Racket 不会混淆哪个是哪个），它对所有映射过程都能正确工作。

## 练习 3

修改 `racket-1` 解释器以添加 `let` 特殊形式。提示：像过程调用一样，`let` 将必须使用 `substitute` 替换某些变量为它们的值。不要忘记评估提供这些值的表达式！

## 练习 4

[SICP 练习 2.62](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-16.html#%25_thm_2.62)

这会有所帮助：[SICP 2.3.3](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-16.html#%_sec_2.3.3)

## 练习 5

文件`~cs61as/lib/bst.scm`包含了 SICP 2.3.3 中的二叉搜索树过程。使用 adjoin-set，构建[第 156 页上显示的树](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-16.html#%_fig_2.16)。

## 专家专用：练习 6

**如果你愿意的话可以做这个。这不计入学分。**

处理类型问题的另一种方法是类型推断。例如，如果一个过程包括表达式`(+ n k)`，则可以推断`n`和`k`具有数值。类似地，表达式`(f a b)`表明 f 的值是一个过程。编写一个名为 inferred-types 的过程，给定一个 Scheme 过程的定义作为参数，返回有关过程参数的信息列表。信息列表应该对应每个参数一个元素；每个元素应该是一个包含参数名称和推断参数类型的两个元素列表。可能的类型：

```
? (the type can't be inferred)

procedure (the parameter appeared as the first word in an unquoted expression or as the first argument of map or every)

number (the parameter appeared as an argument of +, -, max, or min)

list (the parameter appeared as an argument of append or as the second argument of map or member)

sentence-or-word (the parameter appeared as an argument of first, butfirst, sentence, or member?, or as the second argument of every)

x (conflicting types were inferred) 
```

对于这个问题，你应该假设要检查的过程体中不包含任何`if`或`cond`的出现，尽管它可能包含任意嵌套和引用的表达式。（一个更雄心勃勃的推断过程既会检查更全面的一组过程，还可以推断条件，比如“非空列表”。）以下是你的推断过程应该返回的示例。

```
(inferred-types
    '(define (foo a b c d e f)
        (f (append (a b) c '(b c))
           (+ 5 d)
           (sentence (first e) f)) ) ) 
```

应该返回

```
((a procedure) (b ?) (c list) (d number)
 (e sentence-or-word) (f x)) 
```

如果你真的雄心勃勃，你可以维护一个推断参数类型的数据库，并在你正在检查的过程被另一个过程调用时使用它！

## 提交你的作业！

有关说明，请参阅此指南。它涵盖了基本的终端命令和作业提交。

如果你在提交作业时遇到任何问题，请不要犹豫向助教求助！
