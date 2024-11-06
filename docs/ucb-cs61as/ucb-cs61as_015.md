# 特殊形式

## `if`子句

尽管我们在上一课中使用了`if`进行一些练习，这里是特殊形式的一般结构：

```
(if [test]
    [then]
    [else]) 
```

`if`是一个特殊形式，因为它不会评估其参数，除非被使用。以下是一些例子：

```
-> (if #t
       'foo
       'baz)
'foo
-> (if #f
       'foo
       'baz)
'baz
-> (if (= 1 1)
       'foobar
       (/ 1 0))
'foobar 
```

最后一个例子展示了为什么`if`需要是一个特殊形式。由于`(= 1 1)`评估为`#t`，我们永远不会到达 else 情况，`(/ 1 0)`，并成功返回`'foobar`。

## `cond`子句

可以在`if`表达式内部嵌套`if`表达式，就像这样：

```
(define (roman-value letter)
  (if (equal? letter 'i)
      1
      (if (equal? letter 'v)
          5
          (if (equal? letter 'x)
              10
              (if (equal? letter 'l)
                  50
                  (if (equal? letter 'c)
                      100
                      (if (equal? letter 'd)
                          500
                          (if (equal? letter 'm)
                              1000
                              'huh?)))))))) 
```

这对于具有许多子句的条件语句很有用。但是，子句越多，您的代码就会变得越混乱和不可读。嵌套`if`的简写是`cond`子句，它使用不同的语法来完成相同的任务。以下是使用`cond`语句编写的`roman-value`函数：

```
(define (roman-value letter)
  (cond ((equal? letter 'i) 1)
        ((equal? letter 'v) 5)
        ((equal? letter 'x) 10)
        ((equal? letter 'l) 50)
        ((equal? letter 'c) 100)
        ((equal? letter 'd) 500)
        ((equal? letter 'm) 1000)
        (else 'huh?))) 
```

如您所见，`cond`子句允许您指定一系列条件和可能的值。结尾的`else`子句指定了当前述谓词都不为真时要返回的值。

翻译成英语，上面的代码读取为：

+   如果输入字母是"i"，则值为 1。

+   如果输入字母是"v"，则值为 5。

+   ...

+   如果输入字母是"m"，则值为 1000。

+   否则，当上述情况都不为真时，值为`'huh?`。

一个`cond`子句的一般结构如下：

```
(cond ([test1] [then1])
      ([test2] [then2])
      ...
      ([testn] [thenn])
      (else [else])) 
```

## 特殊形式

特殊形式是不遵循正常评估步骤的过程。我们之前学过，表达式中的所有参数在过程应用到其参数之前都会被评估。这对于特殊形式不适用。到目前为止，我们讨论过的谓词和子句中，`if`、`cond`、`or`和`and`都是特殊形式。

**测试您的理解**

下面的表达式目前出错了。重新排列它们的参数，使表达式不会出错并返回正确的值。不要改变任何参数值。

```
(and (/ 1 0) #f #t)
(or #f (/ 1 0) #t)
```

假设我们决定编写自己的`if`过程称为`new-if`并定义如下：

```
(define (new-if test then else)
  (if test 
      then 
      else)) 
```

这应该与`if`完全相同，因为它只是在主体中调用`if`。但是，**由于这是一个复合过程，它不是一个特殊形式**。当我们像这样调用`new-if`时会发生什么？

```
(new-if (= 1 1) 'foo (/ 1 0)) 
```

由于`new-if`不是一个特殊形式，它会在进入主体之前先评估所有的参数。

1.  `(= 1 1)`返回`#t`

1.  `'foo`返回`'foo`

1.  `(/ 1 0)`返回-- 等一下...

由于`(/ 1 0)`出现错误，我们的`new-if`是重新创建`if`特殊形式的失败尝试。

## `if`是可组合的

为了节省时间和代码空间，请记住像`if`和`cond`这样的函数可以在表达式中使用，而不是作为独立的表达式。为了演示这一点，考虑以下简单函数：

```
(define (what-am-i age)
  (if (> age 21)
      '(i am a grownup)
      '(i am a child))) 
```

相反，我们可以这样重写它：

```
(define (what-am-i age)
  (se '(i am a) (if (> age 21)
                    'grownup
                    'child))) 
```

不可否认，似乎没有太大的区别。这是可以理解的，考虑到这是一个简单的函数。当这种技术用于更复杂的函数时，我们通过避免重复节省时间。我们可以看到上面的重写函数只写了一次`'(i am a)`，而原始定义则写了两次。

## 陷阱

`cond`语句的结构有非常严格的括号规则。如果你的代码出错了，很可能是你漏掉了一个括号或者多加了一个括号。因此，在使用`cond`语句时***要注意括号！***

另一个问题是，`and`和`or`不能像英语一样使用。为了澄清，假设我们有一个表达式，试图检查一个参数是否是`'yes`或`'no`：

```
(equal? argument (or 'yes 'no))` 
```

这是错误的。`or`返回第一个不为假的参数，因此在此示例中将返回`'yes`。这个表达式最终被评估为：

```
(equal? argument 'yes) 
```

如果你想要检查参数是`'yes`还是`'no`，你需要做以下操作：

```
(or (equal? argument 'yes) (equal? argument 'no)) 
```

最后，但绝对不是最不重要的，避免冗余代码是至关重要的。简单的代码是聪明的代码，将使复杂的程序更易于阅读和操作。

冗余代码示例：

```
(define (even? number)
  (if (not (odd? number))
      #t
      #f)) 
```

这是糟糕的编码风格。我们可以简化为一行：

```
(define (even? number)
  (not (odd? number))) 
```

**测试你的理解**

**注意：** 这是你的作业中的第 3 个练习。

编写一个名为`indef-article`的过程，它接受一个单词作为唯一参数，并返回一个句子。参见下面的示例，了解`indef-article`应该如何工作。请记住，任何以辅音字母开头的词的不定冠词是"a"，而以元音字母开头的词的不定冠词是"an"。您可以忽略任何边界情况。

```
-> (indef-article 'beetle)
'(a beetle)
-> (indef-article 'apple)
'(an apple)
```
