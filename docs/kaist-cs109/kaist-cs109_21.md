# 读取和写入文本文件

#### 读取文本文件

读取文本文件最简单的方法是使用 File 的 readText 方法：它简单地将整个文件作为一个字符串返回：

```
>>> java.io.File("text.txt").readText()
When I started programming, there were no graphical displays. 
All computer input and output was done using text.

```

如果你想将每行读取为一个 List<String>，每行一个元素，你可以使用 readLines()方法：

```
>>> val fname = "words.txt"
>>> val list = java.io.File(fname).readLines()
>>> list.take(10)
[aa, aah, aahed, aahing, aahs, aal, aalii, aaliis, aals, aardvark]

```

如果你想将行存储在一个集合中，或者如果你想进行一些额外的过滤或处理，以下方法更有效率：

```
>>> val words = java.io.File(fname).useLines { it.toSet() }
>>> words.take(10)
[aa, aah, aahed, aahing, aahs, aal, aalii, aaliis, aals, aardvark]
>>> val some = java.io.File(fname).useLines { it.filter { it.length > 10}.map {it.toUpperCase() }.toList() }
>>> some.take(10)
[ABANDONMENT, ABANDONMENTS, ABBREVIATED, ABBREVIATES, ABBREVIATING,
 ABBREVIATION, ABBREVIATIONS, ABDICATIONS, ABDOMINALLY,
 ABERRATIONS]

```

如果你需要对文件的每一行进行更复杂的处理，File 类的 forEachLine 方法很方便。它接受一个函数对象作为参数，该函数对象接受一个字符串参数。该方法依次为文件的每一行调用此函数对象：

```
>>> java.io.File(fname).forEachLine { print(it); print(' ') }
aa aah aahed aahing aahs aal aalii aaliis aals aardvark aardvarks
aardwolf aardwolves aas aasvogel aasvogels aba abaca abacas abaci
aback abacus abacuses abaft abaka abakas abalone abalones abamp
abampere abamperes abamps abandon abandoned ...

```

注意魔术名 it 的使用，代表每行的内容。

如果你需要做一些更复杂的事情，可能需要重置文件的读取到文件的开头，跳过文件的部分内容等等，使用 BufferedReader 是方便的（[readfile1.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/94-files/readfile1.kts)）：

```
fun readFile(fname: String) {
  val reader = java.io.File(fname).bufferedReader()
  var line = reader.readLine()
  while (line != null) {
    println(line)
    line = reader.readLine()
  }
  reader.close()
}

```

注意 readLine 返回一个 String?，当你完成时必须关闭读取器。

通过将读取代码包装在 use 块中，关闭读取器会自动进行（即使我们从函数中提前返回或抛出异常）（[readfile2.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/94-files/readfile2.kts)）：

```
fun readFile(fname: String) {
  val reader = java.io.File(fname).bufferedReader()
  reader.use {
    reader ->
      var line = reader.readLine()
      while (line != null) {
        println(line)
        line = reader.readLine()
      }
  }
}

```

#### 写入文本文件

要写入文本文件，请创建 PrintWriter。它支持 print 和 println 方法，其工作方式就像打印到终端一样。不要忘记关闭 PrintWriter，否则你的文件会不完整：（[writefile1.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/94-files/writefile1.kts)）：

```
val out = java.io.File("test.txt").printWriter()

for (i in 1 .. 10)
  out.println("$i: ${i * i}")

out.close()

```

同样，我们可以通过使用 use 来使关闭文件自动化：（[writefile2.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/94-files/writefile2.kts)）：

```
java.io.File("test.txt").printWriter().use {
  out ->
    for (i in 1 .. 10)
      out.println("$i: ${i * i}")
}

```
