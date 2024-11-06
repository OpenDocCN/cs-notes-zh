# 集合的高阶方法

在处理集合（如数组或列表）时，我们经常使用 for 循环对集合的所有元素执行某些操作：

```
>>> val C = listOf("Introduction to Programming",
...                "Programming Practice",
...                "Data Structures",
...                "Programming Principles",
...                "Algorithms",
...                "Programming Languages")
>>> C
[Introduction to Programming, Programming Practice, Data Structures, Programming Principles, Algorithms, Programming Languages]
>>> for (e in C)
...   println(e)
Introduction to Programming
Programming Practice
Data Structures
Programming Principles
Algorithms
Programming Languages

```

此循环的有趣部分是打印语句。现代编程语言使得可以编写集中在这部分而不是循环上的代码。

我们可以使用集合的 forEach 方法而不是编写 for 循环。这是一个高阶方法，即它将函数对象作为其参数。

上面的循环改为：

```
>>> C.forEach { s: String -> println(s) }
Introduction to Programming
Programming Practice
Data Structures
Programming Principles
Algorithms
Programming Languages

```

正如我们在前一节中学到的，这可以简化一些，因为 Scala 编译器知道 forEach 的参数必须是类型为（String）-> Unit 的函数对象。因此，我们可以省略参数的类型。

```
>>> C.forEach { s -> println(s) }
Introduction to Programming
Programming Practice
Data Structures
Programming Principles
Algorithms
Programming Languages

```

此外，只有一个参数，因此我们可以用魔术参数名 it 替换它。

```

>>> C.forEach { println(it) }
Introduction to Programming
Programming Practice
Data Structures
Programming Principles
Algorithms
Programming Languages

```

这里是另一个示例，我们使用 forEach 来计算集合元素的总和：

```
>>> val l = listOf(15, 39, 22, 98, 37, 19, 5)
>>> l
[15, 39, 22, 98, 37, 19, 5]
>>> var sum = 0
>>> l.forEach { sum += it }
>>> sum
235

```

再次使用了我们用于函数字面值 x：Int -> sum += x 的快捷语法。

#### 任何，所有，计数和查找

经常需要遍历集合的元素以确定以下属性之一：

+   集合是否包含具有某种属性的元素？

+   所有元素都具有该属性吗？

+   有多少元素具有该属性？

+   找到具有该属性的元素。

这可以很好地使用高阶方法 any，all，count 和 find 来完成。它们都需要将元素映射到布尔值的函数对象。

以下是一些示例：

```
>>> val C = listOf("Introduction to Programming",
...                "Programming Practice",
...                "Data Structures",
...                "Programming Principles",
...                "Algorithms",
...                "Programming Languages")
>>> C.count { "Programming" in it }
4
>>> C.count { "Programming" !in it }
2
>>> C.all { " " in it }
false
>>> C.any { " " !in it }
true
>>> C.any { "Algo" in it }
true
>>> C.all { "A" in it.toUpperCase() }
true
>>> C.find { " " !in it }
Algorithms

```

#### 过滤集合

我们经常希望从集合中挑选出满足特定条件的所有元素组成的子集。高阶方法 filter 和 filterNot 可以做到这一点。同样，它们的参数是将元素映射到布尔值的函数对象。

这里有一些基本示例，使用上面的列表：

```
>>> C.filter { " " in it }
[Introduction to Programming, Programming Practice, Data Structures, Programming Principles, Programming Languages]
>>> C.filterNot { " " in it }
[Algorithms]

```

请注意，filterNot 与 filter 执行相同的操作，但颠倒了条件的意义。

这里有一些使用我们的 113809 个英语单词文件的有趣过滤器：

```
>>> val words = java.io.File("words.txt").useLines { it.toSet() }
>>> words.filter { "issis" in it }
[missis, missises, narcissism, narcissisms, narcissist, narcissists]
>>> words.filter { it.length > 20 }
[counterdemonstrations, hyperaggressivenesses, microminiaturizations]
>>> words.filterNot { "a" in it || "e" in it || "o" in it || "u" in it || "i" in it }
[by, byrl, byrls, bys, crwth, crwths, cry, crypt, crypts, cwm, cwms,
 cyst, cysts, dry, dryly, drys, fly, flyby, flybys, flysch, fry,
 ghyll, ghylls, glycyl, glycyls, glyph, glyphs, gym, gyms, gyp, gyps,
 gypsy, hymn, hymns, hyp, hyps, lymph, lymphs, lynch, lynx, my,
 myrrh, myrrhs, myth, myths, nth, nymph, nymphs, phpht, pht, ply,
 pry, psst, psych, psychs, pygmy, pyx, rhythm, rhythms, rynd, rynds,
 sh, shh, shy, shyly, sky, sly, slyly, spry, spryly, spy, sty, stymy,
 sylph, sylphs, sylphy, syn, sync, synch, synchs, syncs, syzygy, thy,
 thymy, try, tryst, trysts, tsk, tsks, tsktsk, tsktsks, typp, typps,
 typy, why, whys, wry, wryly, wych, wynd, wynds, wynn, wynns, xylyl,
 xylyls, xyst, xysts]

```

过滤是埃拉托斯特尼筛法的本质，因此很自然地我们可以使用 filter 来简洁地编写它（[primes.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/40-lambda/primes.kts)）：

```
val n = args[0].toInt()
val sqrtn = Math.sqrt(n.toDouble()).toInt()

var s = (2 .. n).toList()

while (true) {
  val k = s.first()
  if (k > sqrtn)
     break
  print("$k ")
  s = s.filter { it % k != 0 }
}

println(s.joinToString(separator=" "))

```

#### 转换集合

另一个常见的操作是通过某种方式转换现有集合的每个元素来创建新集合。

这可以使用高阶函数 map 来完成。它的参数是将集合的元素映射到其转换值的函数对象。新集合可以具有相同或不同的类型：

```
>>> C
[Introduction to Programming, Programming Practice, Data Structures, Programming Principles, Algorithms, Programming Languages]
>>> C.map { it.length }
[27, 20, 15, 22, 10, 21]
>>> C.map { it.toUpperCase() }
[INTRODUCTION TO PROGRAMMING, PROGRAMMING PRACTICE, DATA STRUCTURES,
  PROGRAMMING PRINCIPLES, ALGORITHMS, PROGRAMMING LANGUAGES] 
>>> C.map { it + " " + it }
[Introduction to Programming Introduction to Programming, Programming
  Practice Programming Practice, Data Structures Data Structures,
  Programming Principles Programming Principles, Algorithms
  Algorithms, Programming Languages Programming Languages] 

```

#### 对集合进行排序

我们已经看到，可以使用其 sorted 方法对列表进行排序。这总是使用元素类型的自然排序来对元素进行排序。

如果我们想要使用不同的排序方式进行排序，我们可以使用高阶方法 sortedWith（返回一个新列表）或 sortWith（对给定的可变列表进行排序）。它们接受一个 java.util.Comparator 对象作为参数，用于处理列表元素之间的比较。

我们可以从将两个元素\(a\)和\(b\)映射到一个 Int 的函数对象中创建一个 Comparator 对象。如果元素\(a\)应该在所需的排序顺序中出现在元素\(b\)之前，则函数应返回负整数，如果\(a\)应该在\(b\)之后出现，则返回正整数，如果在排序顺序中认为\(a\)和\(b\)相等，则返回零。

这里是一个例子：

```
>>> val words = java.io.File("words.txt").useLines { it.toSet() }
>>> words.sortedWith(java.util.Comparator { a: String, b: String -> b.length - a.length }).take(10)
[counterdemonstrations, hyperaggressivenesses, microminiaturizations,
  counterdemonstration, counterdemonstrators, hypersensitivenesses,
  microminiaturization, representativenesses, anticonservationist,
  comprehensivenesses] 

```

它按照单词列表中元素的长度降序排列（然后我们只显示前 10 个元素）。

请注意，每个可比较类型已经有一个 compareTo(a, b)方法，如果\(a > b\)，则返回正整数，如果\(a < b\)，则返回负整数，如果\(a = b\)，则返回零：

```
>>> 17.compareTo(19)
-1
>>> 17.compareTo(13)
1
>>> 17.compareTo(17)
0
>>> "CS109".compareTo("Otfried")
-12

```

当构建我们自己的 Comparator 对象时，我们可以利用这一点，例如像这样：

```
>>> words.sortedWith(java.util.Comparator<String> { a, b -> -a.length.compareTo(b.length) }).take(10)
[counterdemonstrations, hyperaggressivenesses, microminiaturizations,
  counterdemonstration, counterdemonstrators, hypersensitivenesses,
  microminiaturization, representativenesses, anticonservationist,
  comprehensivenesses] 

```

实际上，我们甚至可以更简单地做到这一点：有 sortedBy 和 sortBy 方法，它们接受一个将列表元素映射到另一个可比较类型 R 的函数对象。然后按照 R 上的顺序对列表进行排序：

```
>>> words.sortedBy { -it.length }.take(10)
[counterdemonstrations, hyperaggressivenesses, microminiaturizations,
  counterdemonstration, counterdemonstrators, hypersensitivenesses,
  microminiaturization, representativenesses, anticonservationist,
  comprehensivenesses] 

```

我们已经按照它们的负长度对单词进行了排序，因此最长的单词排在第一位。如果您觉得否定有点不合逻辑，您可以像这样写：

```
>>> words.sortedByDescending { it.length }.take(10)
[counterdemonstrations, hyperaggressivenesses, microminiaturizations,
  counterdemonstration, counterdemonstrators, hypersensitivenesses,
  microminiaturization, representativenesses, anticonservationist,
  comprehensivenesses] 

```

实际上，这个更长，但可能更容易理解。

#### 更多高阶方法

Kotlin 集合有许多更高阶的方法。以下是一些示例：

findLast 找到满足给定属性的列表中的最后一个元素（请记住 find 会找到第一个元素）：

```
>>> val l = listOf(13, 7, 2, 19, 20, 1, 17, 35, 9)
>>> l.find { it > 15 }
19
>>> l.findLast { it > 15 }
35

```

retainAll 类似于 filter，但它修改了 MutableList 本身，丢弃所有不满足属性的元素（而 filter 总是返回一个新列表）：

```
>>> val l = mutableListOf(13, 7, 2, 19, 20, 1, 17, 35, 9)
>>> l.filter { it > 15 }
[19, 20, 17, 35]
>>> l
[13, 7, 2, 19, 20, 1, 17, 35, 9]
>>> l.retainAll { it > 15 }
true
>>> l
[19, 20, 17, 35]

```

takeWhile 和 takeLastWhile 返回一个新列表，其中包含满足属性的给定列表的元素的开头（或结尾）。类似地，dropWhile 和 dropLastWhile 返回剩余的元素：

```
>>> val l = listOf(13, 7, 2, 19, 20, 1, 17, 35, 9)
>>> l.takeWhile { it > 5 }
[13, 7]
>>> l.dropWhile { it > 5 }
[2, 19, 20, 1, 17, 35, 9]
>>> l.takeLastWhile { it > 5 }
[17, 35, 9]
>>> l.dropLastWhile { it > 5 }
[13, 7, 2, 19, 20, 1]

```

groupBy 是一个有用的操作：它将一个函数对象应用于集合的每个元素，以获得该元素的“键”。然后返回一个将这些键映射到原始元素列表的映射：

```
>>> val l = listOf(13, 7, 2, 19, 20, 1, 17, 35, 9)
>>> l.groupBy { it % 3 }
{1=[13, 7, 19, 1], 2=[2, 20, 17, 35], 0=[9]}
>>> val m = words.groupBy { it.length }
>>> m[20]
[counterdemonstration, counterdemonstrators, hypersensitivenesses, microminiaturization, representativenesses]
>>> m[21]
[counterdemonstrations, hyperaggressivenesses, microminiaturizations]
>>> m[22]
null

```

flatMap 是一个非常强大的操作：它将给定的函数对象应用于集合的每个元素。函数对象的结果应该是一个列表（或集合，或数组）。flatMap 的结果是将所有这些列表按照原始列表的顺序组合成一个列表。

fold 和 reduce 或其他一些强大的操作略微超出了本节的范围。稍后再了解它们！
