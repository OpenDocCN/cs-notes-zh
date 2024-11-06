# StringBuilder

我们经常希望从小片段构建一个大字符串。例如，考虑列表和集合的 joinToString 方法。让我们为列表实现一个简单版本（[join1.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/18-stringbuilder/join1.kts)）：

```
fun join(l: List<Int>): String {
  var s = ""
  for (e in l) {
    if (s.isEmpty())
      s = e.toString()
    else
      s = s + ", " + e.toString()
  }
  return s
}

```

这是可行的，可以从这个测试中看出：

```
>>> :load join1.kts
>>> val s = (1..10).toList()
>>> join(s)
1, 2, 3, 4, 5, 6, 7, 8, 9, 10

```

但是，请记住字符串对象是不可变的。当将另一个数字添加到当前字符串 s 时，必须创建一个全新的字符串，并且所有字符都从旧字符串复制到新字符串中。当列表长度很大时，这可能是一个缓慢的操作。让我们编写一些代码来测量我们的函数 join 的运行时间（[join2.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/18-stringbuilder/join2.kts)）：

```
import java.lang.System.currentTimeMillis

fun join(l: List<Int>): String {
  var s = ""
  for (e in l) {
    if (s.isEmpty())
      s = e.toString()
    else
      s = s + ", " + e.toString()
  }
  return s
}

val n = args[0].toInt()
val a = (1 .. n).toList()

val t0 = currentTimeMillis()
val s = join(a)
val t1 = currentTimeMillis()

println("Creating a string with ${a.size} integers took ${t1 - t0} milliseconds")

```

输出是

```
$ kts join2.kts 100
Creating a string with 100 integers took 1 milliseconds
$ kts join2.kts 1000
Creating a string with 1000 integers took 3 milliseconds
$ kts join2.kts 10000
Creating a string with 10000 integers took 529 milliseconds
$ kts join2.kts 20000
Creating a string with 20000 integers took 1728 milliseconds
$ kts join2.kts 40000
Creating a string with 40000 integers took 6680 milliseconds
$ kts join2.kts 80000
Creating a string with 80000 integers took 27939 milliseconds

```

注意代码如何变得越来越慢：将元素数量翻倍会导致运行时大约增加四倍。

要解决这个问题，我们需要一个可变字符串类型：一个我们可以在末尾添加更多字符而不必复制所有内容的对象。Java 库提供了数据类型 StringBuilder，它本质上是一个可变的字符串。一旦字符串完全构建完成，我们可以通过调用它的 toString()方法将其转换为普通字符串。

这是新的 join 函数（[join3.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/18-stringbuilder/join3.kts)）：

```
fun join(l: List<Int>): String {
  var s = StringBuilder()
  for (e in l) {
    if (s.isEmpty())
      s.append(e.toString())
    else {
      s.append(", ")
      s.append(e.toString())
    }
  }
  return s.toString()
}

```

而且这样要快得多：

```
$ kts join3.kts 80000
Creating a string with 80000 integers took 35 milliseconds
$ kts join3.kts 1000000
Creating a string with 1000000 integers took 113 milliseconds

```

请注意，即使是一百万个数字现在也不是问题。

StringBuilder 对象支持大多数字符串方法，并且具有一些其他方法，可以将它们转换为可变字符串：

+   s.append(ch)附加字符 ch;

+   s.append(t)附加字符串 t;

+   s.append(n)附加数字 n 的字符串表示形式（可以是任何数字类型，如 Int、Double、Long 等）;

+   s.append(x)附加任何对象的字符串表示形式（通过调用它们的 toString()方法）;

+   s.delete(i, j)从索引 i（包括）到 j（不包括）删除字符;

+   s.insert(i, t)在索引 i 处插入字符串 t;

+   s.toString()以普通的、不可变的字符串形式返回内容。
