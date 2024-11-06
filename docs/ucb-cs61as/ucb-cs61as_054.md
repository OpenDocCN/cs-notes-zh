# 列表运算符和 HOFs

## 列表运算符

Racket 为列表提供了有用的原始过程：

### `list-ref`

`list-ref`接受一个列表和一个数字`n`作为参数，并返回列表的第`n`个项目。列表的第一个元素被索引为`0`，意味着它是列表的第`0`个元素。这是`list-ref`的定义方式：

```
(define (list-ref lst n)
  (if (= n 0)
      (car lst)
      (list-ref (cdr lst) (- n 1)))) 
```

这里是一个演示它如何工作的示例：

```
-> (define squares (list 1 4 9 16 25))
squares
-> (list-ref squares 3)
16 
```

### `null?`

`null?`接受一个列表作为参数，如果列表为空则返回`#t`。否则，返回`#f`：

```
(null? (list 1 3))
#f

(null? '())
#t 
```

### `length`

`length`接受一个列表作为参数，并返回列表中的项目数。这是`length`的定义方式：

```
(define (length items)
  (if (null? items)
      0
      (+ 1 (length (cdr items))))) 
```

这里是一个例子：

```
-> (define odds (list 1 3 5 7))
odds
-> (length odds)
4 
```

## 高阶函数与列表

从现在开始，我们将主要使用列表和对，而不是句子。这很好，因为这意味着我们将能够更仔细地查看 Racket 如何表示数据。但是，这也意味着我们之前用句子定义的许多重要的高阶函数现在必须重新编写以适用于对。

### `every` vs. `map`

回想一下 HOF `every`，它接受一个函数和一个句子，并返回一个应用到句子的每个元素的句子。使用对的等价物称为`map`，它接受一个函数和一个*列表*，并返回一个将函数*映射*到列表中每个元素的列表。`map`是一个递归定义的函数，你可以在这里看到：

```
(define (map proc items)
  (if (null? items)
      null
      (cons (proc (car items))
            (map proc (cdr items))))) 
```

对于列表的过程`null?`类似于句子的过程`empty?`，检查给定的参数是否为空列表。这里有一些对`map`的例子：

```
-> (map square (list 1 2 3 4 5))
(1 4 9 16 25)
-> (map car (list (cons 1 2) (cons 3 4) (cons 5 6)))
(1 3 5) 
```

### `keep` vs. `filter`

我们在作业 2 中的`filtered-accumulate`问题中已经快速看到了`filter`，所以你应该已经对 HOF `filter`应该做什么有一些想法。`filter`接受两个参数，一个谓词和一个列表，并返回仅满足谓词的元素的列表。看一下正式定义：

```
(define (filter pred lst)
  (cond ((null? lst) null)
        ((pred (car lst))
          (cons (car lst) (filter pred (cdr lst))))
        (else (filter pred (cdr lst))))) 
```

这里有一些例子：

```
-> (filter odd? '(1 2 3 4 5))
(1 3 5)
-> (filter (lambda (x) (> x 2)) '(1 2 3 4 5))
(3 4 5) 
```

### `accumulate`

最后，有一个用于句子的过程`accumulate`。这个过程接受两个参数的函数，一个基本情况值和一个值的句子，并使用这个操作连续地组合列表中的值，并以基本情况值结束/开始。有两个等效的`accumulate`用于列表：`foldl`和`foldr`。两者都接受两个值的函数，一个基本情况值和一个列表。

`fold-left`从列表中的最后一个（最右边）元素开始，并递归地连续应用函数，直到达到列表的第一个元素。因此，它向左*折叠*。例如，这是评估对`foldl`调用的步骤：

```
-> (foldl cons '() '(1 2 3 4))
... (cons 4 (cons 3 (cons 2 (cons 1 '()))))
(4 3 2 1) 
```

这是另一个例子：

```
-> (define combiner (lambda (x y) (cons (add1 x) y)))
combiner
(foldl combiner '() '(1 2 3 4))
... (combiner 4 (combiner 3 (combiner 2 (combiner 1 '()))))
... (5 . (4 . (3 . (2 . ()))))
(5 4 3 2) 
```

另一方面，`fold-right`从列表中的第一个（最左边）元素开始，并递归地连续应用函数，直到达到列表的最后一个元素。因此，它向右*折叠*。举个例子：

```
-> (foldr cons '() '(1 2 3 4))
... (cons 1 (cons 2 (cons 3 (cons 4 '()))))
(1 2 3 4)

-> (foldr + 0 '(1 2 3 4))
... (+ 1 (+ 2 (+ 3 (+ 4 0))))
10 
```

现在我们有两个版本的`accumulate`，其中`foldl`和`foldr`的值仅在它们被调用时与组合函数的顺序有关时才会有所不同。

## 高阶函数总结

为了使过渡更容易，这里有一个表格，展示了一些句子操作及其在列表中的等价操作。

| 句子 | 列表 |
| --- | --- |
| `se/sentence` | `cons/list/append` |
| `first` | `car` |
| `bf/butfirst` | `cdr` |
| `last` | 没有对应项 |
| `bl/butlast` | 没有对应项 |
| `count` | `length` |
| `item`（从一开始索引） | `list-ref`（从零开始索引） |
| `every` | `map` |
| `keep` | `filter` |
| `accumulate` | `foldl/foldr` |
