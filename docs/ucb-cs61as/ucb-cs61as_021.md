# 常见的递归模式

## “Every”模式

这里是一个将句子中的每个数字平方的过程：

```
(define (square-sent sent)
  (if (empty? sent) `
      '()
      (se (square (first sent))
          (square-sent (bf sent))))) 
```

这里是一个将句子中的每个单词翻译为 Pig Latin 的过程：

```
(define (pigl-sent sent)
  (if (empty? sent)
      '()
      (se (pigl (first sent))
          (pigl-sent (bf sent))))) 
```

这里的模式非常清晰。我们的递归情况将对句子的`第一个`进行一些简单的操作，比如将其`平方`或`pigl`，然后将其与对句子的`butfirst`进行递归调用的结果结合起来。

**检验你的理解**

**注意：** 这是你的作业中的第 5 题。

编写一个名为`initials`的过程，该过程以句子作为参数，并返回句子中每个单词的首字母组成的句子。例如：

```
-> (initials '(if i needed someone))
'(i i n s)
```

## “保留”模式

在“every”模式中，我们收集将单词或句子的每个元素转换为其他内容的结果。这次我们将考虑一种不同类型的问题：选择一些元素并过滤掉其他元素。

首先，这里是一个从句子中选择三个字母单词的过程：

```
-> (define (keep-three-letter-words sent)
     (cond ((empty? sent) '())
           ((= (count (first sent)) 3)
             (se (first sent) (keep-three-letter-words (bf sent))))
           (else
             (keep-three-letter-words (bf sent)))))

-> (keep-three-letter-words '(one two three four five six seven))
'(one two six) 
```

接下来，这里是一个从单词中选择元音字母的过程：

```
-> (define (keep-vowels wd)
     (cond ((empty? wd) "")
           ((vowel? (first wd))
             (word (first wd) (keep-vowels (bf wd))))
           (else
             (keep-vowels (bf wd)))))

-> (keep-vowels 'napoleon)
'aoeo 
```

让我们看看“every”模式和“keep”模式之间的区别。首先，“keep”过程有三种情况，而不像大多数“every”过程那样只有两种情况。在“every”模式中，我们只需区分基本情况和递归情况。在“keep”模式中，仍然有一个基本情况，但有两个递归情况：我们必须决定是否保留返回值中的第一个可用元素。当我们保留一个元素时，我们保留元素本身，而不是元素的某个函数。

**检验你的理解**

编写一个名为`numbers`的过程，该过程以句子作为参数，并返回另一个只包含句子中数字的句子。您可能会发现`number?`谓词有用。

```
-> (numbers '(76 trombones and 110 cornets))
'(76 110)
```

## “累积”模式

这里有两个遵循“累积”模式的函数的递归过程，它将参数的所有元素组合成一个单一结果：

```
-> (define (addup nums)
     (if (empty? nums)
         0
         (+ (first nums)
            (addup (bf nums)))))
-> (addup '(8 3 6 1 10))
28

-> (define (scrunch-words sent)
     (if (empty? sent)
         "" ; This is an empty word
         (word (first sent)
               (scrunch-words (bf sent)))))
-> (scrunch-words '(ack now ledge able))
'acknowledgeable 
```

模式是什么？我们使用一些组合器（`+`或`word`）将我们正在处理的单词与递归调用的结果连接起来。基本情况测试空参数，但基本情况的返回值必须是组合器函数的单位元素。

**检验你的理解**

在这个小节中，我们通过各种函数作为递归的示例。以下哪些函数符合累积模式？选择所有符合条件的。

```
(define (pigl wd)
  (if (pl-done? wd)
      (word wd 'ay)
      (pigl (word (bf wd) (first wd)))))

(define (count-ums sent)
  (cond ((empty? sent) 0)
        ((um? (first sent)) (+ 1 (count-ums (bf sent))))
        (else (count-ums (bf sent)))))

(define (fib n)
  (cond ((= n 0) 0)
        ((= n 1) 1)
        (else (+ (fib (- n 1)) (fib (- n 2))))))
```
