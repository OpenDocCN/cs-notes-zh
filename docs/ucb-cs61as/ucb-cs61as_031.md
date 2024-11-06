# 条件表达式和谓词

## 条件语句复习

我们在第一个实验中使用了`if`和条件语句。在本节中，我们将详细介绍更多细节。

当我们希望函数根据某个特定条件的不同行为时，通常使用`if`或`cond`。请注意，这两个函数在 Racket 中是*特殊形式*；我们不使用通常的“完全评估操作数，然后应用运算符”方法来评估它们。

## `cond`示例

`cond`表达式的一般形式是：

```
(cond  (<test1> <result1>)
       (<test2> <result2>)
       ...
       (<testn> <resultn>)
       (else <default>))  ;; The 'else' case is optional 
```

每个`(<test> <result>)`对称为*子句*。每对的第一部分（`<test>`）是*谓词*—必须评估为 true 或 false 的表达式。

要评估`cond`表达式，首先评估`<test1>`。如果为真，则评估并返回`<result1>`。如果`<test1>`为假，则重复`<test2>`，依此类推，直到没有更多测试。如果遇到`else`，则返回相应的值（“默认值”）。

您可以将`cond`表达式写为一系列“if”语句：

```
(if <test1>
    <result1>
    (if <test2>
        <result2>
        ...
        (if <testn>
            <resultn>
            <default>) ;; Closing parentheses omitted 
```

### 练习

函数`plural`如下接受一个单词并返回其复数形式。例如，`(plural 'carrot)`返回`'carrots`，`(plural 'body)`返回`'bodies`。对于`(plural 'boy)`，它的表现不正确，*应该*返回`'boys`；下面的错误版本却返回`'boies`。

```
(define (plural wd) 
  (if (equal? (last wd) 'y) 
      (word (bl wd) 'ies)
      (word wd 's))) 
```

选择在下面的空白处添加哪行代码，以便`(plural 'boy)`正确运行（即，应返回 boys）。假设`vowel?`如前所定义。

```
(define (plural wd) 
  (if __________________
      (word (bl wd) 'ies)
      (word wd 's))) 
```

## 谓词和样式

谓词是任何返回 true 或 false 的表达式。一些示例包括`(< 3 4)`，`(> 10 -2)`和`(= 'apple 'orange)`。您可以使用`and`，`or`和`not`来形成复合谓词。

这是一个谓词的示例：

```
(define (even? x)
  (= (remainder x 2) 0)) 
```

在定义谓词时，习惯上以问号（`?`）结束过程的名称。

这是另一种定义`even?`的方法：

```
(define (even? x)
  (if (= (remainder x 2) 0)
      #t
      #f)) 
```

尽管此定义等效于上面的原始定义，但它包含冗余。我们建议您避免编写这样的代码。冗余的代码可能会使您的程序更难理解，并且通常被认为是糟糕编程风格的示例。

### 练习

我们定义一个过程，它以三个数字作为参数，并返回两个较大数字的平方和

例如，`(max-sum-squares 1 2 3)`返回`13`，即`4 + 9`

为什么下面的代码不正确？

```
(define (square x) (* x x))

    (define (max-sum-squares a b c) (max (+ (square a) (square b)) (+ (square b) (square c)) (+ (square a) (square c)))) 
```

练习问题：编写一个过程`pigl`，它以一个单词作为参数，并以 pig latin 形式返回该单词。以下是 pig latin 的规则：

如果输入的单词以元音字母开头，则我们在输入后附加“ay”。

如果输入的单词以辅音字母开头，则我们将所有起始辅音字母移至单词末尾��然后在末尾附加“ay”。

以下是一些示例：

```
(pigl 'hello) ; ellohay 
(pigl 'open) ; openay 
(pigl 'scheme) ; emeschay 
```

如果我们的输入没有元音，像`(pigl 'my)`这样会发生什么？确保您的`pigl`检查单词是否没有元音，并直接返回该单词。

```
(pigl my) ; my 
```

在你的 Racket 解释器中使用上面的示例检查你的答案！
