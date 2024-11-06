# 布尔值和谓词

## 布尔值：真和假

**布尔值**在形式上被定义为只有两个可能值的二进制变量：“真”和“假”。 在表达*条件*或根据测试结果选择操作的指令时，这些非常有用。 一个逻辑的例子是：如果我们缺少牛奶，那么去商店。 否则，加牛奶到我们的谷物中并享用。

为了测试我们是否缺少牛奶，我们需要使用布尔值。 Racket 中的“真”用`#t`或`true`表示，而“假”用`#f`或`false`表示。

```
-> (= 1 1)
#t

-> (= 1 2)
#f

> (if #t
    '(the condition was true)
    '(the condition was false))
(the condition was true)

> (if #f
    '(the condition was true)
    '(the condition was false))
(the condition was false)

> (if (= 1 1)
    '(the condition was true)
    '(the condition was false))
(the condition was true) 
```

## 谓词

当调用时返回`true`或`false`的函数称为**谓词**。 例如，`even?`是一个用于测试一个数字是否为偶数的谓词。

```
-> (even? 2)
#t
-> (even? 3)
#f 
```

谓词永远不会返回除`#t`或`#f`之外的值。 下面是 Racket 中一些有用的预定义谓词列表。 这个列表并不全面，您肯定会在未来的课程中发现更多的谓词。

### 数学运算符

Racket 具有您需要比较数值的标准数学运算符：

+   `<` 如果第一个参数小于第二个参数，则返回`#t`。

+   `>` 如果第一个参数大于第二个参数，则返回`#t`。

+   `=` 如果两个参数相等，则返回`#t`。

+   `<=` 如果第一个参数小于或等于第二个参数，则返回`#t`。

+   `>=` 如果第一个参数大于或等于第二个参数，则返回`#t`。

**警告：** 这些谓词仅适用于**数字**。 使用这些谓词来比较单词、句子或任何其他类型的值将产生错误。

```
-> (= (+ 3 3) 6)
#t
-> (= 'foo 'foo)
; =: contract violation
;   expected: number?
;   given: 'foo
;   argument position: 1st
; [,bt for context] 
```

### `member?`

`member?`，当给定一个字母和一个单词时，如果单词包含该字母，则返回`#t`，否则返回`#f`。 当`member?`给定一个单词和一个句子时，如果句子包含该单词，则返回`#t`，否则返回`#f`。

```
-> (member? 'a 'aeiou)
#t
-> (member? 'b 'aeiou)
#f

-> (member? 'foo '(foo bar baz))
#t
-> (member? 'foobar '(foo bar baz))
#f 
```

### `empty?`

谓词`empty?`接受任意类型的一个参数，并在参数为空单词`""`或空句子`'()`时返回`#t`，否则返回`#f`。

```
-> (empty? "")
#t
-> (empty? 'foo)
#f

-> (empty? '())
#t
-> (empty? '(foo bar baz))
#f

-> (empty? 3)
#f 
```

### `equal?`

`equal?` 接受两个任意类型的参数，并在它们相同时返回`#t`，否则返回`#f`。

```
-> (equal? (+ 1 1) 2)
#t
-> (equal? 3 1)
#f

-> (equal? 'foo 'foo)
#t
-> (equal? '(foo bar baz) '(foo bar baz))
#t

-> (equal? + +)
#t 
```

### 类型检查器

Racket 还提供了检查值是否属于特定类型的谓词：

+   `number?` 检查一个值是否为数字。

+   `word?` 检查一个值是否为单词。

+   `sentence?` 检查一个值是否为句子。

+   `boolean?` 检查一个值是否为布尔值。

### 作为谓词的复合过程

您绝对可以创建自己的谓词，因为它们实际上是过程。 例如：

```
(define (vowel? letter)
  (member? letter 'aeiou)) 
```

`vowel?` 检查其参数字母是否是元音字母。

**测试你的理解**

**注意：** 这是你的作业中的第 2 题。

编写一个名为`teen?`的谓词，它以一个数字作为参数，并在数字介于 13 和 19 之间（包括 13 和 19）时返回`#t`。

## 除了假之外的一切都是真

在评估表达式是真还是假时，重要的是要记住，除非是假，否则任何东西都被视为真。这意味着所有数字、单词、句子和过程都是真的，甚至包括 `""`、`'()` 和 `0`。以下是一些令人费解的例子：

```
-> (false? "") ;; is "" false?
#f ;; no, it is not
-> (false? '())
#f
-> (false? 0)
#f
-> (false? false?) ;; is the procedure false? false?
#f ;; no, the procedure itself is not false 
```

## 逻辑运算符

我们也可以在 Racket 中使用逻辑运算。

### `and`

`and` 是一个谓词，接受任意数量的任何类型的参数。如果所有参数都不是假的，它将返回最后一个元素，否则返回 `#f`。例如：

```
-> (and 1 2 3)
3
-> (and (= 1 1) (member? 'a 'aeiou))
#t
-> (and (number? 'hi) 2 3)
#f 
```

### `or`

`or` 是一个谓词，接受任意数量的任何类型的参数。它返回第一个真元素，否则返回 `#f`。例如：

```
-> (or (even? 4) (= 1 1))
#t
-> (or 1 #f 2)
1
-> (or (even? 1) #f (number? 'foo))
#f 
```

### `not`

`not` 接受任何类型的单个参数，简单地否定它所接受的参数。例如：

```
-> (not #f)
#t
-> (not #t)
#f
-> (not 3)
#f
-> (not (and (and 3 3) (or #f #f)))
#t 
```

### `nand`

`nand` 等同于 `(not (and ...`。例如：

```
-> (nand #f #t)
...(not (and #f #t))
...(not #f)
#t 
```

### `nor`

`nor` 就是你猜到的，等同于 `(not (or ...`。例如：

```
-> (nor #f #t)
...(not (or #f #t))
...(not #t)
#f 
```

### `xor`

`xor` 接受任何类型的两个参数，如果恰好一个（不多不少）参数不是 `#f`，则返回该参数。否则，返回 `#f`。

```
-> (xor 11 #f)
11
-> (xor #f 11)
11
-> (xor 11 22)
#f
-> (xor #f #f)
#f 
```
