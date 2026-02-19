# 异常

如果你和我一样，你会经常看到你的程序以错误或异常消息终止。以下是一些异常消息的示例：

```
>>> val a = 3
>>> a / 0
java.lang.ArithmeticException: / by zero
>>> val s = "abc"
>>> s.toInt()
java.lang.NumberFormatException: For input string: "abc"
>>> java.io.File("test.txt").forEachLine { println(it) }
java.io.FileNotFoundException: test.txt (No such file or directory)
>>> val s = Array<Int>(100000000) { 0 }
java.lang.OutOfMemoryError: Java heap space

```

#### 错误和异常

诸如 OutOfMemoryError 之类的错误表示严重的失败，继续程序毫无意义。

然而，其他异常仅仅表示程序中的一个意外或异常条件。例如，程序输入数据中的错误可能会导致异常。这些错误可以被处理：我们说异常被处理或捕获。

例如，NumberFormatException 可能表示用户输入了一个不正确的数字，正确的响应是打印一个错误消息并要求新的输入。

FileNotFoundException 意味着我们尝试打开的文件不存在。根据情况，正确的响应可能是尝试不同的文件名，要求用户提供不同的文件名，或者简单地跳过读取文件。

#### 捕获异常

以下代码要求用户输入一个数字。readString 函数返回一个字符串，因此我们必须使用 toInt()方法将其转换为整数。如果字符串不是一个数字，比如"abc"或"123ab"，那么 toInt()方法会抛出一个异常。我们可以通过将关键部分放在 try 块中，并添加一个 catch 块来处理我们感兴趣的异常来捕获异常（[catch1.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/16-exceptions/catch1.kts)）：

```
import org.otfried.cs109.readString

val str = readString("Enter a number> ")

try {
  val x = str.toInt()
  println("You said: $x")
} 
catch (e: NumberFormatException) {
  println("'$str' is not a number")
}

```

如果 try 块正常执行，则 catch 子句将被跳过。但是，如果在 try 块内的某个地方（包括直接或间接调用的任何方法）抛出异常，则 try 块的执行立即停止，并在第一个与异常匹配的 catch 子句中继续执行。这里，“匹配”意味着异常与 case 中列出的异常类型相同。

catch 块中的代码称为异常处理程序。

在我们上面的示例中，如果字符串 str 不代表一个整数（例如，如果它是"abc"），那么 str.toInt 会抛出 NumberFormatException 异常。try 块被终止（特别是，没有值被赋给 x），并且执行继续在 NumberFormatException 的 catch 子句中。以下是一些示例运行：

```
$ kts catch1.kts
Enter a number> 17
You said: 17
$ kts catch1.kts
Enter a number> abc
'abc' is not a number

```

#### 异常与错误代码

老的编程语言如 C 没有异常，因此所有错误或异常情况都需要通过错误代码来处理。在 C++中，错误代码也仍然广泛使用，例如为了与 C 兼容。

像`str.toInt()`这样简单而优雅的方法在没有异常的情况下是不可能的。我们将不得不返回两个结果：一个布尔值来指示转换是否成功，以及 Int 值本身。

因此，异常使我们能够集中精力于`str.toInt()`的基本含义：它接受一个字符串，并返回一个数字。但是异常的真正威力只在下一节中显现…

#### 深入了解异常

异常的好处是你也可以捕获在 try 块中调用的函数内部抛出的异常。

回到我们的数字转换示例，这里是一个在单独函数中转换字符串的版本（[catch2.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/16-exceptions/catch2.kts)）：

```
fun test(s: String): Int = (s.toDouble() * 100).toInt()

fun show(s: String) {
  try {
    println(test(s))
  }
  catch (e: NumberFormatException) {
    println("Incorrect input")
  }
}

```

函数 test(s)将字符串转换为双精度浮点数，然后将其四舍五入到两位小数并返回整数。

当发生转换错误时，这发生在 test(s)内部，但我们仍然可以在 show(s)函数中捕获这个错误：

```
>>> :load catch2.kts
>>> show("123.456")
12345
>>> show("123a456")
Incorrect input

```

当异常发生时（我们说异常被抛出），正常的执行流程会被中断，然后在最近（最内层，最近的）捕获块继续，其中捕获了这种类型的异常（也就是说，有一个正确类型的异常处理程序）。

让我们更详细地看一下，并考虑以下程序（[except1.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/16-exceptions/except1.kts)）：

```
import org.otfried.cs109.readString

fun f(n: Int) {
  println("Starting f($n) ... ")
  g(n)
  println("Ending f($n) ... ")
}

fun g(n: Int) {
  println("Starting g($n) ... ")
  val m = 100 / n
  println("The result is $m")
  println("Ending g($n) ... ")
}

fun main() {
  while (true) {
    val s = readString("Enter a number> ")
    if (s == "")
      return
    try {
      println("Beginning of try block")
      val n = s.toInt()
      f(n)
      println("End of try block")
    }
    catch (e: NumberFormatException) {
      println("Please enter a number!")
    }
    catch (e: ArithmeticException) {
      println("I can't handle this value!")
    }
  }
}

main()

```

这是一个运行示例：

```
$ kts except1.kts 
Enter a number> 25
Beginning of try block
Starting f(25) ... 
Starting g(25) ... 
The result is 4
Ending g(25) ... 
Ending f(25) ... 
End of try block
Enter a number> 0
Beginning of try block
Starting f(0) ... 
Starting g(0) ... 
I can't handle this value!
Enter a number> abc
Beginning of try block
Please enter a number!
Enter a number>

```

对于输入值"25"，我们看到 try 块的开始和结束以及函数 f 和 g。对于输入值"abc"，toInt 方法抛出异常，因此不调用 f。对于输入值"0"，函数 g 内部的除法抛出 ArithmeticError。正如你所看到的，执行立即在异常处理程序中继续，而不是完成函数 g、f 或 try 块。

#### 抛出异常

到目前为止，我们只捕获了在某些库函数内部抛出的异常。但是你也可以自己抛出异常。例如，假设我们的函数 g(n)应该只处理非负数。如果参数为负数，我们可以通过抛出 IllegalArgumentException 来确保这一点。整个脚本现在看起来像这样（[except2.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/16-exceptions/except2.kts)）：

```
import org.otfried.cs109.readString

fun f(n: Int) {
  println("Starting f($n) ... ")
  g(n)
  println("Ending f($n) ... ")
}

fun g(n: Int) {
  println("Starting g($n) ... ")
  if (n < 0)
    throw IllegalArgumentException()
  println("The value is $n")
  println("Ending g($n) ... ")
}

fun main() {
  while (true) {
    val s = readString("Enter a number> ")
    if (s == "")
      return
    try {
      println("Beginning of try block")
      val n = s.toInt()
      f(n)
      println("End of try block")
    }
    catch (e: NumberFormatException) {
      println("Please enter a number!")
    }
    catch (e: IllegalArgumentException) {
      println("I can't handle this value!")
    }
  }
}

main()

```

请注意，异常是对象，并且像任何其他对象一样通过调用它们的构造函数创建。

再次，我们用不同的输入运行它：

```
$ kts except2.kts 
Enter a number> 25
Beginning of try block
Starting f(25) ... 
Starting g(25) ... 
The value is 25
Ending g(25) ... 
Ending f(25) ... 
End of try block
Enter a number> abc
Beginning of try block
Please enter a number!
Enter a number> -17
Beginning of try block
Starting f(-17) ... 
Starting g(-17) ... 
I can't handle this value!

```

异常通常用于检测输入数据中的错误。

我们可以在程序中适当的位置捕获异常并打印错误消息，或以其他方式处理问题。

当你调试程序时，可能会困惑于某些异常的来源。在这种情况下，使用异常对象的 printStackTrace()方法可能很有用。它会打印出导致异常抛出的方法链。

如果我们将主函数更改如下（[except3.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/16-exceptions/except3.kts)）：

```
fun main() {
  while (true) {
    val s = readString("Enter a number> ")
    if (s == "")
      return
    try {
      println("Beginning of try block")
      val n = s.toInt()
      f(n)
      println("End of try block")
    }
    catch (e: NumberFormatException) {
      println("Please enter a number!")
    }
    catch (e: IllegalArgumentException) {
      e.printStackTrace()
    }
  }
}

```

那么我们可以看到这个过程： 

```
$ kts except3.kts 
Enter a number> 35
Beginning of try block
Starting f(35) ... 
Starting g(35) ... 
The value is 35
Ending g(35) ... 
Ending f(35) ... 
End of try block
Enter a number> -17
Beginning of try block
Starting f(-17) ... 
Starting g(-17) ... 
java.lang.IllegalArgumentException
	at Except3.g(except3.kts:16)
	at Except3.f(except3.kts:9)
	at Except3.main(except3.kts:29)
	at Except3.<init>(except3.kts:41)
        ... many omitted lines ...
Enter a number> abc
Beginning of try block
Please enter a number!
Enter a number> 

```

我们可以看到 IllegalArgumentException 是在函数 g（脚本的第 16 行）中抛出的，该函数被函数 f 调用，后者又被主函数调用。

#### 断言

断言是在程序执行过程中测试的条件。如果条件为真，则不会发生任何特殊情况。但是，如果条件为假，则会抛出 AssertionError 异常。该语句：

```
assert(condition)

```

如果条件为假，则抛出 AssertionError。

您还可以在断言中包含一条消息。

断言的目的是检测程序中的错误。（与上面使用异常的目的相比，异常的目的是检测输入数据中的错误。）

考虑以下代码：

```
  ... code A computing string s ...
  assert(s.nonEmpty(), "s is empty!")
  ... code B using string s ...

```

如果代码 A 正确，则由 A 计算得到的字符串 s 不能是空的。我们通过断言验证这一点确实是真的，即 s 不为空。

此断言的目的是保护代码 B。如果没有断言，可能会发生以下情况：代码 A 中存在错误，因此 s 为空。这会导致代码 B 中发生一些奇怪的崩溃，因此我们开始调试代码 B。有了断言，立即清楚问题出在代码 A。

因此，断言的目的是保护代码片段免受彼此的影响，并隔离问题。

#### Require

require(condition) 语句是断言的一种特殊形式。它的工作方式与 assert 完全相同，但如果条件为假，则会抛出 IllegalArgumentException。

当您需要一个断言来测试方法的参数是否正确时很有用：在这种情况下，您应该使用 require(condition) 而不是 assert(condition)。

require 的目的是保护您的函数免受使用非法参数调用的影响。如果没有它，您可能会花很长时间尝试调试函数，而实际上问题是由于给函数传递的参数值不正确引起的。

#### 读取和写入文件

在读取或写入文件时，很多问题可能会出现。文件可能不存在，我们可能没有写入权限，硬盘可能已满，或者有人可能弹出我们正在读取的光盘。这意味着任何进行文件输入/输出的严肃代码都需要考虑捕获异常。

以下简单的脚本会打印文本文件中的所有行以及每行的长度。如果文件不存在或者您没有读取文件的权限，将会抛出异常。您可以捕获异常，打印错误消息，并继续执行，而不是让程序崩溃（[read1.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/16-exceptions/read1.kts)）：

```
val fd = java.io.File("project.txt")

try {
  fd.forEachLine {
    println("${it.length} $it")
  }
} 
catch (e: java.io.FileNotFoundException) {
  println("Project file does not exist!")
}
catch (e: java.io.IOException) {
  println("Error reading project file!")
}

```

如果 forEachLine 方法无法打开文件，则会抛出 FileNotFoundException。循环不会被执行；执行直接跳转到打印消息给用户的异常处理程序。

FileNotFoundException 是 IOException 的一种特殊情况，因此异常符合两个 catch 子句。但是，只有一个 catch 子句会被执行 - 第一个匹配的子句。如果第一个不存在，则会执行第二个 catch 子句。

可能发生的情况是我们可以打开文件，但是`forAllLines`方法仍然抛出异常（例如，因为磁盘故障）。这通常会生成某种类型的`IOException`。这将导致第二个捕获子句执行。异常处理程序通常用于从错误中恢复并清理类似打开文件的松散端。

注意，并非每个可能发生的异常都需要一个捕获子句。你可以捕获一些异常，让其他异常传播。
