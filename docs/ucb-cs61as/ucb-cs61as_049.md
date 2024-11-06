# 作业 3

## 模板

在终端输入以下命令将模板文件复制到当前目录（注意末尾的句点）：

```
cp ~cs61as/autograder/templates/hw3.rkt . 
```

或者你可以在[这里](http://inst.eecs.berkeley.edu/~cs61as/templates/hw3.rkt)下载模板。

## 自动评分程序

如果你在实验室计算机上工作，`grader` 命令将运行自动评分程序。如果你在自己的个人机器上工作，你应该下载[grader.rkt](http://inst.eecs.berkeley.edu/~cs61as/autograder/grader.rkt)和[HW 3 tests](http://inst.eecs.berkeley.edu/~cs61as/autograder/tests/hw3-tests.rkt)。

## 练习 1: 快速指数不变量

这是之前课程中的`fast-expt`过程：

```
(define (even? n)
  (= (remainder n 2) 0))

(define (fast-expt b n)
  (cond ((= n 0) 1)
        ((even? n) (square (fast-expt b (/ n 2))))
        (else (* b (fast-expt b (- n 1))))))
```

设计一个过程，演变出一个使用连续平方的迭代求幂过程，并使用对数数量的步骤，就像`fast-expt`一样。

（提示：利用观察到的事实(*b*^(*n*/2))² = (*b*²)^(*n*/2)，保持，连同指数*n*和基数*b*，一个额外的状态变量*a*，并定义状态转换，使得乘积*a b^n*从一个状态到另一个状态保持不变。在过程开始时*a*被取为 1，答案由过程结束时的*a*的值给出。一般来说，定义一个在状态之间保持不变的不变量数量是思考设计迭代算法的强大方式。）

## 练习 2: 黄金比例（可选）

阅读 SICP 中关于[查找函数的不动点](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-12.html#%_sec_Temp_106)的子章节，并完成[练习 1.35](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-12.html#%25_thm_1.35)。

## 练习 3: `cont-frac`

### 第 1 部分

无限*连分数*是一个形式为：

[mathjax]f=\frac{N_1}{D_1+\frac{N_2}{D_2+\frac{N_3}{D_3+\cdots}}}[/mathjax]

举例来说，可以证明

[mathjax]\frac{1}{\phi}=\frac{1}{1+\frac{1}{1+\frac{1}{1+\cdots}}}[/mathjax]

其中[mathjaxinline]\phi=\frac{1+\sqrt{5}}{2}[/mathjaxinline]是黄金比例。近似无限连分数的一种方法是在给定项数后截断展开。这种截断——所谓的*[mathjaxinline]k[/mathjaxinline]项有限连分数*——具有以下形式：

[mathjax]\frac{N_1}{D_1+\frac{N_2}{\ddots+\frac{N_k}{D_k}}}[/mathjax]

假设`n`和`d`是一个参数（项索引[mathjaxinline]i[/mathjaxinline]）的过程，返回连分数的第[mathjaxinline]i[/mathjaxinline]项的[mathjaxinline]N[/mathjaxinline]和[mathjaxinline]D[/mathjaxinline]。定义一个过程`cont-frac`，使得评估`(cont-frac n d k)`计算[mathjaxinline]k[/mathjaxinline]项有限连分数的值。通过近似[mathjaxinline]\frac{1}{\phi}[/mathjaxinline]来检查你的过程

```
(cont-frac (lambda (i) 1.0)
           (lambda (i) 1.0)
           k) 
```

对于连续的`k`值。为了获得精确到小数点后 4 位的近似值，你需要将`k`设定为多大？

### 第 2 部分

如果你的`cont-frac`过程生成了一个递归过程，请写一个生成迭代过程的过程。如果它生成了一个迭代过程，请写一个生成递归过程的过程。

### 第 3 部分

1737 年，瑞士数学家莱昂哈德·欧拉表明

[mathjax] e - 2=\frac{N_1}{D_1+\frac{N_2}{D_2+\frac{N_3}{D_3+\cdots}}} [/mathjax]

对于参数

[mathjax] \begin{cases} N_i = 1\\ D_i = 1,2,1,1,4,1,1,6,1,1,8,\cdots \end{cases} [/mathjax]

其中[mathjaxinline]e[/mathjaxinline]是自然对数的底。编写一个程序，使用你的`cont-frac`过程来近似[mathjaxinline]e[/mathjaxinline]，使用欧拉展开。

## 练习 4：`next-perf`

*完美数*被定义为等于所有小于自身的因子之和的数。例如，第一个完美数是 6，因为它的因子是 1、2、3 和 6，而 1+2+3=6。第二个完美数是 28，因为 1+2+4+7+14=28。第三个完美数是多少？

编写一个过程`(next-perf n)`，从`n`开始测试连续整数，直到找到一个完美数。然后你可以评估`(next-perf 29)`来解决问题。注意，你的过程应该能够处理任何非负整数输入。

提示：你会需要一个`sum-of-factors`子过程。

注意：如果在系统负载繁重时运行此程序，可能需要半小时来计算答案！尝试跟踪辅助过程，确保你的程序正常运行，或者从计算`(next-perf 1)`开始，看看是否得到 6。

## 练习 5：交换基本情况

这是本课程中较早时的`count-change`程序的定义：

```
 (define (count-change amount)
  (cc amount `(50 25 10 5 1)))
```

(define (cc amount kinds-of-coins) (cond [(= amount 0) 1] [(or (< amount 0) (empty? kinds-of-coins)) 0] [else (+ (cc amount (bf kinds-of-coins)) (cc (- amount (first kinds-of-coins)) kinds-of-coins))] ))

解释在`cc`过程中交换基本情况检查顺序的影响。

也就是说，完全描述原始`cc`过程将返回不同值或行为不同于下面给出的`cc`过程编码的参数集，并解释返回值的差异。

```
(define (cc amount kinds-of-coins)
  (cond
    [(or (< amount 0) (empty? kinds-of-coins)) 0]
    [(= amount 0) 1]
    [else ... ] ) ) ; as in the original version
```

## 练习 6：求幂的不变量

这是本课程中较早时的迭代求幂过程：

```
(define (expt b n)
  (expt-iter b n 1))

(define (expt-iter b counter product)
  (if (= counter 0)
      product
      (expt-iter b
                (- counter 1)
                (* b product))))
```

给出一个代数公式，将迭代求幂过程的参数`b`、`n`、`counter`和`product`的值联系起来。

(我们要找的答案是“`b`、`n`和`counter`乘以`product`的和总是等于 37”。)

## 提交你的作业！

有关说明，请参见此指南。它涵盖了基本的终端命令和作业提交。

如果你在提交作业时遇到任何问题，请不要犹豫向助教求助！
