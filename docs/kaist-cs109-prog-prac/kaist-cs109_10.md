# 集合

集合是用于存储元素集合的数据类型。集合中没有顺序，并且所有元素必须是不同的（因此不能在集合中有多个相同元素的副本）。换句话说，集合是 Kotlin 中集合数学概念的实现。

集合在许多问题中自然而然地出现：拼写正确的单词形成一个集合。质数形成一个集合。

当然，我们可以简单地使用列表（或数组）来存储形成集合的项目集合。但这不是自然的，通常也不高效：列表是一个索引序列，其中元素具有排序，同一个元素可能出现多次，并且只能通过逐个查看所有元素来搜索元素。

幸运的是，Kotlin 使用的 Java 标准库为我们提供了一个非常好的集合数据类型。更准确地说，集合是一个参数化数据类型，因此有 Set<Int>、Set<String> 等。

让我们创建一些集合：

```
>>> val s = setOf(2, 3, 5, 7, 9)
>>> s
[2, 3, 5, 7, 9]
>>> val w = setOf("CS109", "is", "wonderful")
>>> w
[CS109, is, wonderful]
>>> val e = emptySet<String>()
>>> e
[]

```

请注意，对于空集，您必须指示元素的类型，因为 Kotlin 无法从元素本身推断出类型。您还可以通过使用它们的 toSet() 方法将其他集合（列表、数组、范围）转换为集合。

请记住，您写入元素的顺序并不重要，一个元素不能出现多次：

```
>>> val s2 = setOf(9, 9, 5, 7, 3, 5, 3, 2)
>>> s == s2
true
>>> val w2 = setOf("wonderful", "is", "CS109")
>>> w == w2
true

```

+ 和 - 运算符可用于向集合添加元素，并从集合中移除元素。结果是一个新的集合。可以添加已经在集合中的元素，也可以移除不在集合中的元素。

```
>>> s + 11
[2, 3, 5, 7, 9, 11]
>>> s - 7
[2, 3, 5, 9]
>>> s - 6
[2, 3, 5, 7, 9]
>>> s + 7
[2, 3, 5, 7, 9]
>>> s + 7 == s
true

```

集合的标准数学操作——并集、交集、差集和包含关系——可以（大多数情况下）使用集合方法实现：

+   \(|s|\) 是 s.size

+   \(s \cup t\) 是 s + t

+   \(s \setminus t\) 是 s - t

+   \(x \in s\)? 是 s.contains(x) 或 x in s

+   \(s \subseteq t\)? 是 t.containsAll(s)

+   \(s \cap t\) 没有方法，但可以实现为 s.filter { it in t }。

以下是一些例子：

```
>>> val a = (1 .. 10).toSet()
>>> a
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
>>> val b = (1 .. 10 step 2).toSet()
>>> b
[1, 3, 5, 7, 9]
>>> val c = (1 .. 5).toSet()
>>> c
[1, 2, 3, 4, 5]
>>> a.containsAll(b)
true
>>> b.containsAll(a)
false
>>> a.containsAll(c)
true
>>> a - b
[2, 4, 6, 8, 10]
>>> b + c
[1, 3, 5, 7, 9, 2, 4]
>>> b.filter { it in c }
[1, 3, 5]

```

集合支持许多其他操作，其中一些您已经从列表中熟悉，例如：

+   s.size 是集合的大小；

+   s.isEmpty() 与 s.size == 0 相同；

+   s.isNotEmpty() 与 s.size != 0 相同；

+   s.max()、s.min()、s.sum() 返回集合中元素的最大值、最小值和总和；

+   s.sorted() 返回一个 s 中元素按排序顺序排列的列表；

+   s.joinToString() 返回一个将 s 的所有元素连接在一起的字符串（具有与列表相同的选项）；

+   s.toList() 和 s.toMutableList() 返回与集合相同的元素的（可变）列表。

作为使用集合的第一个示例，这里是一个简单的拼写检查器。它使用了包含 113809 个英语单词的文件 words.txt，每行一个单词。

我们读取文件并立即将其转换为集合。然后我们允许用户从终端输入单词。我们检查单词是否在拼写正确的单词集合中，并报告这一点（[spell.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/13-sets/spell.kts)）。

```
import org.otfried.cs109.readString

val fname = "words.txt"

val words = java.io.File("words.txt").useLines { it.toSet() }

while (true) {
  val w = readString("Enter a word> ").trim()
  if (w == "")
    break
  if (w in words) 
    println("$w is a word")
  else
    println("Error: $w is not a word")
}

```

这里是一个示例运行：

```
$ kts spell.kts
Enter a word> lovely
lovely is a word
Enter a word> lovly
Error: lovly is not a word
Enter a word> wierd
Error: wierd is not a word
Enter a word> weird
weird is a word
Enter a word> supercede
Error: supercede is not a word
Enter a word> supersede
supersede is a word
Enter a word> 

```

你也可以使用集合来衡量两个文本之间的相似性（例如对网络文档进行分类）。考虑每个文本的单词集合，并比较它们的并集大小与交集大小。

#### 可变集合

我们上面看到的所有集合都是不可变的：没有办法改变集合的内容。集合操作如并集和交集实际上会返回一个新的集合对象。

有时使用可变集合更有效或更方便（但请记住这些更危险）。Java 标准库提供了一个可变集合数据类型，在 Kotlin 中称为 MutableSet。我们使用 add 添加元素，并使用 remove 删除元素：

```
>>> val s = mutableSetOf(1, 2, 3, 4)
>>> s
[1, 2, 3, 4]
>>> s.add(9)
true
>>> s
[1, 2, 3, 4, 9]
>>> s.add(13)
true
>>> s
[1, 2, 3, 4, 9, 13]
>>> s.remove(2)
true
>>> s
[1, 3, 4, 9, 13]
>>> s.remove(12)
false
>>> s
[1, 3, 4, 9, 13]

```

集合的一个经典应用是埃拉托斯特尼筛法来计算质数。这里是一个实现（[sieve.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/13-sets/sieve.kts)）：

```
fun sieve(n: Int): Set<Int> {
  var s = (2 .. n).toMutableSet()
  val sqrtn = Math.sqrt(n.toDouble()).toInt()
  for (i in 2 .. sqrtn) {
    if (i in s) {
      var k = i * i
      while (k <= n) {
      	s.remove(k)
	k += i
      }
    }
  }
  return s
}

val num = if (args.size == 1) args[0].toInt() else 1000

val primes = sieve(num)

for (i in primes)
  print("$i ")

println()

```

运行的输出：

```
$ kts sieve.kts 500
2 3 5 7 11 13 17 19 23 29 31 37 41 43 47 53 59 61 67 71 73 79 83 89 97
101 103 107 109 113 127 131 137 139 149 151 157 163 167 173 179 181
191 193 197 199 211 223 227 229 233 239 241 251 257 263 269 271 277
281 283 293 307 311 313 317 331 337 347 349 353 359 367 373 379 383
389 397 401 409 419 421 431 433 439 443 449 457 461 463 467 479 487
491 499

```

集合还有许多其他应用。例如，在迷宫中找路时，你可以将已经看到的位置存储在一个集合中。同样地，在实现电脑游戏时，你可以将已经评估过的游戏位置存储在一个集合中。
