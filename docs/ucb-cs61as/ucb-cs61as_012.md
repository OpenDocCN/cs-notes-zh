# 单词和句子

## 介绍

当我们想到函数时，我们自动假设与数学和数字有关。实际上，在 Racket 和任何其他函数式编程语言中，我们可以有函数来操作非数值的值。

### 单词

假设你定义了一个名为`square`的过程：

```
(define (square x) (* x x)) 
```

但是以后想要访问实际单词`'square`而不是过程，我们只需输入`'square`（单引号后跟单词 square）即可获得**文字单词**。请注意，如果你只是处理一个单词，你不需要在表达式周围加上括号。

### 句子

**句子**只是用括号分组的单词集合。要创建一个句子，你需要在括号外面加上一个引号，就像这样`'(hi hey hello)`。尝试通过写一两个单词和句子来练习一下。

**测试你的理解**

在 Racket 解释器中尝试以下每一个。

```
'61AS
```

```
'(I love 61AS!)
```

```
('I 'love '61AS!)
```

## `quote`

你在上面的部分看到的`'`实际上是一个名为`quote`的函数的缩写。这意味着：

+   `'x`等同于`(quote x)`

+   `'(hi hey hello)`等同于`(quote (hi hey hello))`

`quote`与大多数其他过程不同，因为它不评估其参数。表现出这种行为的函数是**特殊形式**。你现在不需要理解特殊形式；我们将在后面的小节中更深入地讨论这个主题。现在，知道`quote`是一个接受一个参数并将其作为单词或句子返回的函数就足够了。看下面的例子：

```
-> (define x 4)
x
-> x
4
-> (quote x)
x
-> 'x
x 
```

由于`quote`经常被使用，它被赋予了缩写`'`，一个单引号。请记住，尽管在缩写形式中可能是这样，但`quote`只是一个函数，可以像其他函数一样在 Racket 中调用。

## 单词和句子选择器

在处理单词和句子时，拥有能够操作它们的过程会很有帮助。这些过程本身很简单。正确地组合它们以完成目标将是困难的部分。现在，这里是一些你可以用来从单词或句子中选择数据的过程列表。

### `first`

`first`接受一个单词并返回单词的第一个字母，或接受一个句子并返回句子的第一个单词。

```
-> (first 'hello)
'h
-> (first '(hi hey hello))
'hi 
```

### `last`

`last`接受一个单词并返回单词的最后一个字母，或接受一个句子并返回句子的最后一个单词。

```
-> (last 'hello)
'o
-> (last '(hi hey hello))
'hello 
```

### `butfirst`或`bf`

`butfirst`或其缩写版本`bf`接受一个单词并返回除了第一个字母之外的所有字母，或接受一个句子并返回除了第一个单词之外的所有单词。

```
-> (butfirst 'hello)
'ello
-> (bf 'hello)
'ello
-> (butfirst '(hi hey hello))
'(hey hello)
-> (bf '(hi hey hello))
'(hey hello) 
```

### `butlast`或`bl`

`butlast`或其缩写版本`bl`接受一个单词并返回除了最后一个字母之外的所有字母，或接受一个句子并返回除了最后一个单词之外的所有单词。

```
-> (butlast 'hello)
'hell
-> (bl 'hello)
'hell
-> (butlast '(hi hey hello))
'(hi hey)
-> (bl '(hi hey hello))
'(hi hey) 
```

### `item`

`item`接受一个数字`n`和一个单词，并返回单词中的第`n`个字母。或者，它接受一个数字`n`和一个句子，并返回句子中的第`n`个单词。

```
-> (item 2 'hello)
'e
-> (item 2 '(hi hey hello))
'hey 
```

**检验你的理解**

尝试猜测 Racket 将对以下表达式输出什么，然后用 Racket 解释器检查你的答案。

```
(first '(foo foo))
```

```
(bf '(foo foo))
```

```
(equal? (first '(foo foo)) (bf '(foo foo)))
```

`equal?` 是一个检查两个元素是否相同的函数。

## 单词和句子构造器

现在我们已经学会了如何拆分单词或句子，让我们学习如何将它们组合在一起。

### `word`

`word` 接受任意数量的单词作为参数，将它们连接成一个大单词。

```
-> (word 'play 'ground)
'playground
-> (word 'fo 'o 'b 'ar)
'foobar
-> (word 'cs '61 'as)
'cs61as 
```

### `sentence` 或 `se`

`sentence`，或其缩写版本 `se`，接受任意数量的单词或句子作为参数，并创建一个包含所有参数的句子。

```
-> (sentence 'I 'love 'cs '61as!)
'(I love cs 61as!)
-> (se 'foo 'bar)
'(foo bar)
-> (se 'foo '(foo bar) 'bar)
'(foo foo bar bar) 
```

### 空单词

还有一个空单词，你可以将其与其他单词组合在一起，使用时不会产生任何效果。这由 `""` 表示。

```
-> (word 'foo "")
'foo
-> (word "" 'foo)
'foo
-> (word "" "")
"" 
```

### 空句子

还有一个空句子，你可以将其与其他句子组合在一起，使用时不会产生任何效果。这由 `'()` 表示。

```
-> (se 'hi 'there '())
(hi there)
-> (se '() 'hi 'there)
(hi there)
-> (se 'hi '() 'there)
(hi there)
-> (se '() '() '())
'() 
```

目前可能不清楚为什么需要这些空单词和句子。现在记住它们，当我们学习 Lesson 0-3 中的递归时，它们将非常有用。

**检验你的理解**

**注意：** 这是你的作业中的练习 1。

让我们构建一些处理单词和句子的函数。我们将为你定义 `second` 过程 - 这个过程返回单词中的第二个字母，或句子中的第二个单词。

```
(define (second item)
    (first (bf item)))
```

1.  编写一个名为 `first-two` 的过程，它以单词作为参数，返回一个包含参数的前两个字母的两个字母单词。

1.  编写一个名为 `two-first` 的过程，它接受两个单词作为参数，返回一个包含这两个参数的首字母的两个字母单词。

1.  现在编写一个名为 `two-first-sent` 的过程，它接受一个由两个单词组成的句子作为参数，返回一个包含这两个单词的首字母的两个字母单词。

## 陷阱

基本上，在处理单词和句子时，你可以使用的唯一标点符号是 `!` 和 `?`。你已经看到引号 `'` 在 Racket 中有特殊含义。句号和逗号也有特殊含义，因此你也不能使用它们。

正如你在早前的练习中看到的，单词和包含一个单词的句子之间有区别。例如，人们经常错误地认为两个单词的句子的 `butfirst`，比如 `(计算机科学)` 是 `'科学`。实际上，它是一个包含一个单词的句子：`(科学)`。证明单词和一个单词句子之间的区别的另一种方法是通过对���们进行 `count`：

```
-> (bf '(computer science))
'(science)  

-> (count (bf '(computer science)))  
1 ;; because there is ONE word in the sentence.

-> (first (bf '(computer science)))
'science

> (count (first (bf '(computer science))))  
7 ;; because there are SEVEN letters in the word 'science 
```

## 要点

+   我们可以使用 `word` 和 `sentence` 分别构建单词和句子。

+   我们也可以使用引号来构建单词和句子。

+   我们可以使用 `first`、`butfirst`、`last` 和 `butlast` 等过程来检索单词或句子的部分。
