# 作业 7

在终端中键入以下内容将模板文件复制到当前目录（注意末尾的句点）：

```
cp ~cs61as/autograder/templates/hw7.scm . 
```

或者你可以从[这里](http://inst.eecs.berkeley.edu/~cs61as/templates/hw7.scm)下载。

## 练习 1

修改模板中给出的 `person` 类，添加一个 `repeat` 方法，用于重复上次说的话。例如：

```
> (define brian (instantiate person 'brian))
brian 

> (ask brian 'repeat)
() 

> (ask brian 'say '(hello))
(hello) 

> (ask brian 'repeat)
(hello) 

> (ask brian 'greet)
(hello my name is brian) 

> (ask brian 'repeat)
(hello my name is brian) 

> (ask brian 'ask '(close the door))
(would you please close the door) 

> (ask brian 'repeat)
(would you please close the door) 
```

## 练习 2

这个练习让你了解 `usual`。

假设我们想定义一个名为 `double-talker` 的类来代表总是说两遍话的人。例如，看看以下对话。

```
> (define mike (instantiate double-talker 'mike))
mike 

> (ask mike 'say '(hello))
(hello hello) 

> (ask mike 'say '(the sky is falling))
(the sky is falling the sky is falling) 
```

考虑以下三个对于 `double-talker` 类的定义：

```
(define-class (double-talker name)
    (parent (person name))
    (method (say stuff) (se (usual 'say stuff) (ask self 'repeat))) ) 

(define-class (double-talker name)
    (parent (person name))
    (method (say stuff) (se stuff stuff)) ) 

(define-class (double-talker name)
    (parent (person name))
    (method (say stuff) (usual 'say (se stuff stuff))) ) 
```

确定这些定义中哪些是按预期工作的。还确定三个版本对哪些消息会有不同的响应。

## 练习 3

对于一个统计项目，你需要计算各种范围内的大量随机数。（回想一下，`(random 10)` 返回 0 到 9 之间的随机数。）此外，你需要跟踪每个范围内计算的随机数数量。你决定使用面向对象编程。`random-generator` 类的对象将接受两个消息：`number` 和 `count`。`number` 消息意味着“给我一个你范围内的随机数”，而 `count` 意味着“你已经请求了多少个数字？”该类有一个实例化参数，指定此对象的随机数范围，因此：

```
(define r10 (instantiate random-generator 10)) 
```

将创建一个对象，使得 `(ask r10 'number)` 将返回 0 到 9 之间的随机数，而 `(ask r10 'count)` 将返回 `r10` 创建的随机数数量。

## 练习 4

定义 `coke-machine` 类。`coke-machine` 的实例化参数是机器中可以容纳的可乐数量和可乐的价格（以分为单位）。例如，

```
(define my-machine (instantiate coke-machine 80 70)) 
```

创建一个可以容纳 80 瓶可乐并以每瓶 70 分的价格出售的机器。`coke-machine` 对象必须接受以下消息：

+   `(ask my-machine 'deposit 25)` 意味着存入 25 分。你可以存入多枚硬币，机器应该记住总额。

+   `(ask my-machine 'coke)` 意味着按下可乐按钮。然后机器会打印出 1) "Not enough money"，2) "Machine empty"，或者 3) 返回找零的金额。错误信息应该使用 `display` 打印（例如，`(display "Machine empty")`）。（成功交易后，机器内不会留下任何钱；即找零不会留在机器内。）

+   `(ask my-machine 'fill 60)` 意味着向机器中添加 60 瓶可乐。

这里是一个例子：

```
> (ask my-machine 'fill 60)
> (ask my-machine 'deposit 25)
> (ask my-machine 'coke)
"Not enough money"

> (ask my-machine 'deposit 25) ;; Now there's 50 cents in there.
> (ask my-machine 'deposit 25) ;; Now there's 75 cents.
> (ask my-machine 'coke)
5 ;; return val is 5 cents change. 
```

你可以假设可乐机有无限的找零，并且最初不含任何可乐。

## 练习 5

我们将使用对象来表示一副牌。你将获得包含标准顺序中的 52 张牌的列表 `ordered-deck`：

```
(define ordered-deck '(AH 2H 3H ... QH KH AS 2S ... QC KC)) 
```

你还得到一个用于打乱列表元素的函数：

```
(define (shuffle deck)
    (if (null? deck)
        '()
        (let ((card (nth (random (length deck)) deck)))
            (cons card (shuffle (remove card deck))) ))) 
```

一个`deck`对象响应两个消息：`deal`和`empty?`。它通过从牌堆中移除顶部的牌来响应`deal`，如果牌堆为空，它通过返回`()`来响应`deal`。它通过返回`#t`或`#f`来响应`empty?`，根据是否所有牌都已发出。为`deck`编写一个类定义。当实例化时，一个`deck`对象应该包含一个洗过的 52 张牌的牌堆。

## 练习 6

我们希望在我们的对象之间促进礼貌。编写一个类`miss-manners`，它以一个对象作为其实例化参数。新的`miss-manners`对象应该只接受一个消息，即`please`。`please`消息的参数应该是，首先，原始对象理解的消息，其次，该消息的参数。**(假设对原始对象的所有消息都需要额外一个参数。)**

这里是一个使用即将推出的冒险游戏项目中的人物类的示例：

```
> (define BH (instantiate person 'Brian BH-office))
BH
> (ask BH 'go 'down)
BRIAN MOVED FROM BH-OFFICE TO SODA
> (define fussy-BH (instantiate miss-manners BH))
> (ask fussy-BH 'go 'east)
ERROR: NO METHOD GO
> (ask fussy-BH 'please 'go 'east)
BRIAN MOVED FROM SODA TO PSL 
```

## 专家专用

如果你想挑战一下，可以做这些。这些*不*计入学分。

### 练习 7

多重继承技术在["面向对象编程 - 上线视图"](http://www-inst.eecs.berkeley.edu/~cs61as/reader/aboveline.pdf)的第 9 和 10 页有描述。该部分讨论了解决继承模式的模糊问题，并特别提到，从第二选择父类直接继承的方法可能比从第一选择祖父类继承的方法更好。

设计一个这样的情况的例子。描述你的例子的继承层次结构，列出每个类提供的方法。还描述为什么在这个例子中，对象从第二选择父类继承一个给定方法而不是从第一选择祖父类继承更为合适。

## 提交你的作业！

有关说明，请参阅此指南。它涵盖了基本的终端命令和作业提交。

如果你在提交作业时遇到任何问题，请不要犹豫向助教求助！
