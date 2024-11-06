# Mapreduce

### Mapreduce 简介

在本节中，我们将重新访问第 2 单元的高阶函数（`map`和`accumulate`）并将其与并行性结合起来，从而使我们能够高效地处理大量数据。

### Mapreduce 背景

Google 的工程师们注意到他们的大部分计算可以分解为对数据的某个函数的`map`，然后是之后的`accumulate`（也称为`reduce`，因此得名）。结果是一个名为`mapreduce`的库过程，它接受两个函数作为参数；一个充当`mapper`，另一个充当`reducer`。它接受大量数据，将它们分成较小的部分，将`mapper`应用于较小的数据，并使用`reducer`组合结果。Mapreduce 处理与并行性有关的一切，我们只需提供这两个函数。

尽管这可能*看起来*像`mapreduce`正在做的事情，但这**不是**`mapreduce`：

```
(define (mapreduce mapper reducer base-case data)
    (accumulate reducer base-case (map mapper data))) 
```

为什么不是 mapreduce 呢？因为它没有处理数据的划分，应用映射器并行性以及在减少之前对它们进行排序。不过，它做对的是，想要使用 mapreduce 的人只需要传递四个参数：`mapper, reducer, base-case`和我们要处理的`data`给`mapreduce`函数。

如果您感兴趣，[这里](http://static.googleusercontent.com/media/research.google.com/en/us/archive/mapreduce-osdi04.pdf)是由提出 mapreduce 的 Google 员工撰写的一篇论文。这不是必需的，但它非常易读和有趣。[旧的讲义](http://inst.eecs.berkeley.edu/~cs61as/reader/notes.pdf#page=24)也有很好的解释，如果您觉得不理解 mapreduce，应该阅读这些内容。

### Mapreduce 的分解

![](img/mapreduce.jpg)

1.  将`mapper`映射到较小的数据（并行完成）。这涉及选择我们要处理的输入部分并为每个结果“附加”一个键

1.  根据它们的键将结果排序到“桶”中

1.  每个“桶”都传递给一个`reducer`来累积值

我们将在后续部分更详细地查看这些步骤。

在本课程中，我们将使用搜索文本文件并查找单词频率的示例。

这将作为我们的测试文件：

```
>(define song1   '( ((please please me) i saw her standing there)
            ((please please me) misery)
            ((please please me) please please me)))

>(define song2   '( ((with the beatles) it wont be long)
            ((with the beatles) all ive got to do)
            ((with the beatles) all my loving)))

>(define song3   '( ((a hard days night) a hard days night)
            ((a hard days night) i should have known better)
            ((a hard days night) if i fell)))

>(define all-songs (append song1 song2 song3))
( ((please please me) i saw her standing there)
  ((please please me) misery)
  ((please please me) please please me)
  ((with the beatles) it wont be long)
  ((with the beatles) all i have got to do)
  ((with the beatles) all my loving)
  ((a hard days night) a hard days night)
  ((a hard days night) i should have known better)
  ((a hard days night) if i fell) ) 
```

请注意，每一行都带有它们的标题。我们建议将此标签打开在某个地方，以便您知道我们的输入是什么样子的。

您可以在此处获取我们的 mapreduce 实现的数据和其他函数这里。请注意，此实现不涉及并行性。

### 映射器

![](img/mapreduce_mapper.jpg)

```
(map mapper data) 
```

+   **输入**：（较小的）键-值对

+   **输出**：键-值对列表

`映射器`是一个接受数据（作为键值对）并返回**键值对列表**的函数。键值对列表与我们在第 9 课中玩过的关联列表（也称为 a-lists）相同。键用于跟踪数据的来源；这对于并行化很重要。请注意，输入的键不一定与映射器输出的键相同。这将是我们的键值对的 ADT：

```
 (define make-kv-pair cons)
    (define kv-key car)
    (define kv-value cdr) 
```

如果我们查看样本输入的第一项，结果如下：

```
 >(kv-key '((please please me) i saw her standing there))
 (please please me)
 >(kv-value '((please please me) i saw her standing there))
 (i saw her standing there) 
```

为什么我们输出键值对列表而不是单个键值对？以下是一些原因：

+   **无键值**：有时我们的数据中可能没有我们感兴趣的键。例如，想象一种情况，你想要统计一个单词中元音字母的数量，然后遇到了单词'fly'。在这种情况下，我们将返回空列表。

+   **多个键值**：有时我们的数据对应于我们想要生成的 2 个或更多个键。这适用于我们的歌词示例（如下所示）

### 扩展示例：单词计数

这是我们示例中映射器的定义。

```
>(define (mapper input-kv-pair)
    (map (lambda (wd) (make-kv-pair wd 1)) (kv-value input-kv-pair)))

>(mapper '((please please me) i saw her standing there))
((i . 1) (saw . 1) (her . 1) (standing . 1) (there . 1)) 

>(mapper '((please please me) please please me))
((please . 1) (please . 1) (me . 1)) 
```

我们的映射器做什么？它接受一个键值对（其键是歌曲标题，其值是歌曲中的一行）。对于行中的每个单词，将该单词用作新键，并将其与值 1 配对。请注意，即使单词在行中出现两次，比如'(please please me)'，它也会输出'(please . 1)'两次而不是'(please . 2)'。这没问题，因为这里我们只是从 1 开始计数。我们稍后将它们相加。

### 按桶排序

![](img/mapreduce_sort.jpg)

在我们实际进入`减少器`之前，有一个中间步骤对键进行排序，并将相同的键分组在一起。幸运的是，我们可以利用抽象化，并使用函数`**按桶排序**`将它们排序到'桶'中。具有相同键的键值对被分组到同一个'桶'下。这是调用上一步映射器的结果：

```
>(map mapper all-songs)
( ((i . 1) (saw . 1) (her . 1) (standing . 1) (there . 1))  
  ((misery . 1))  
  ((please . 1) (please . 1) (me . 1))  
  ((it . 1) (wont . 1) (be . 1) (long . 1))   
  ((all . 1) (i . 1) (have . 1) (got . 1) (to . 1) (do . 1))  
  ((all . 1) (my . 1) (loving . 1))   
  ((a . 1) (hard . 1) (days . 1) (night . 1))   
  ((i . 1) (should . 1) (have . 1) (known . 1) (better . 1))  
  ((if . 1) (i . 1) (fell . 1)) ) 
```

调用按桶排序的结果如下：

```
>(sort-into-buckets (map mapper all-songs))

'( ((i . 1) (i . 1) (i . 1) (i . 1))
   ((saw . 1))
   ((her . 1))
   ((standing . 1))
   . . .
   ((all . 1) (all . 1))
   ((have . 1) (have . 1))
   . . . 
   ((if . 1))  
   ((fell . 1)) ) 
```

为了保持简洁，结果的某些部分被省略了。请注意这里的键和值是如何组织的。结果是一个桶列表，其中一个桶是具有相同键的键值对列表。`((i . 1) (i . 1) (i . 1) (i . 1))`是一个桶的示例，其中每个键值对具有键'i'。

### 减少器

![](img/mapreduce_reduce.jpg)

+   **输入**：两个“值”

+   **输出**：一个值

`减少器`接受两个值（没有键），并输出一个单个值。

### 扩展示例：单词计数

这是我们减少器的定义

```
(define (reducer num other-num)
    (+ num other-num)) 
```

### 减少一个桶

请注意，我们的减少器接受两个值，而我们之前步骤的结果（按桶排序）是一个桶列表（其中一个桶是一个键值对列表）。让我们看看如何使用我们的`减少器`将其减少到单个键值对。让我们使用我们的第一个键值对列表：

```
((i . 1) (i . 1) (i . 1) (i. 1) (i . 1)) 
```

`> (accumulate reducer 0 (map kv-value '((i . 1) (i . 1) (i . 1) (i . 1) (i . 1))))`

这简化为：

`> (accumulate reducer 0 '(1 1 1 1 1))`

`5`

在调用 accumulate 之前，我们必须通过使用 map 从 kv- 对列表中获取值。请注意，调用 accumulate 的结果是与键相关联的单个值（在本例中为 'i' 的 5）。因为我们最终的结果需要是一个 kv- 对，所以最终我们必须返回 `(i . 5)`。表达式变为：

```
(make-kv-pair (kv-key '(i . 1))
              (accumulate reducer 0 (map kv-value '((i . 1) (i . 1)  
                                    (i . 1) (i . 1) (i . 1))))) 
```

我们可以将上面的表达式推广到除了 '((i . 1) (i . 1) (i . 1) (i . 1) (i . 1))' 之外的任何其他“桶”。

```
(define (reduce-bucket reducer base-value bucket)
    (make-kv-pair   (kv-key (car bucket))
            (accumulate reducer base-value (map kv-value bucket)))) 
```

### 减少一个桶的列表

上面的 `reduce-bucket` 过程减少一个桶。我们从上一步的结果 `(sort-into-buckets (map mapper data))` 是一个桶的列表。要减少一个桶的列表，我们可以再次使用 map。我们将定义函数 `group-reduce` 来实现这一点。

```
(define (groupreduce reducer base-case buckets)
    (map (lambda (bucket) (reduce-bucket reducer base-case bucket))  
             buckets)) 
```

如果我们使用到目前为止的内容，它会计算为以下内容：

```
>(groupreduce reducer 0 (sort-into-buckets (map mapper all-songs)))
( (i . 4) (saw . 1) (her . 1)
  . . .
  (misery . 1) (please . 2) (me . 1)
  . . .
  (all . 2) (have . 2)) 
```

为了简洁起见，某些值被省略。最终的结果再次是一个 kv- 对的列表：键是单词，值是这些单词在我们的数据中出现的次数。我们刚刚使用 mapreduce 构建了数据中单词计数！

这是我们的 mapreduce 的最终（手势模糊，近似）定义：

```
(define (mapreduce mapper reducer base-case data)
    (groupreduce reducer base-case (sort-into-buckets (map mapper data)))) 
```

为什么不是实际的 mapreduce？实际的方法将涉及并行地映射和减少我们的 kv- 对，并且我们必须考虑并发问题。上面的定义捕捉了我们关注的主要部分。

### 练习 Mapreduce

编写一个 mapreduce 函数就是定义您的映射器和减少器。我们有一系列不同的场景，希望您定义相应的映射器、减少器，并最终调用 mapreduce。

记住：

+   您的映射器的输入是一个键值对，输出是一个键值对的**列表**。

+   您的减少器的输入是两个值，输出是一个值

### 链接 Mapreduce

如前所述，由于 mapreduce 的输入是一个键值对列表，输出也是一个键值对列表，因此可以将 mapreduce 链接在一起。它看起来像这样：`(mapreduce some-mapper some-reducer some-base-case (mapreduce another-mapper another-reducer another-base-case actual-input))`。请注意，第一个 mapreduce 的键和值可能与第二个 mapreduce 的完全不同。

### 最常见的单词

让我们写另一个 mapreduce 函数（我们还没有链接）。这次，我们的输入的键是 'words'，值是数字，表示它们在文档中出现的次数。我们希望输出是一个仅有一个键值对的列表，就像输入一样，我们的键是一个单词，值是一个数字，表示遇到的最高数字。

注意：我们的解决方案并不理想，有点牵强。它没有充分利用 mapreduce 提供的并行性。

```
>(define x (list (make-kv-pair her 1) (make-kv-pair i 4) (make-kv-pair saw 1))
>(most-frequent x) ; i appears the most
((i . 4)) 
```

### 现在我们开始链接

我们上面的函数是有效的，如果我们传递键为单词，值为数字的对。在现实生活中，我们可能无法直接访问每个单词的单词计数；我们必须从原始文档中处理它。

编写函数`real-most-frequent`，接受一个键值对列表，其中键是文件名，而值是来自该文件的行（就像我们所有歌曲示例一样）。我们的输出再次是一个**单一**键值对列表。你可能想要重用我们在本课程中已经定义的任何函数。

```
>(real-most-frequent all-songs)
((i . 4)) 
```

读者不包含 MapReduce 练习。如果你想获得更多练习，Lesson 14 讨论中有 MapReduce 问题。
