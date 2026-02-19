# 编译程序

我们用 Kotlin、Java、C++ 或 C 等高级编程语言编写程序。编译器将源代码转换为对象代码（机器代码）。

对于 C 和 C++，习惯上编译为本机机器代码。它可以直接由处理器执行。本机机器代码对于不同的处理器、操作系统有所不同，并且可能依赖于库版本。因此，为 Windows 编译的程序无法在 Mac OS 上运行，为 iOS 编译的程序无法在 Windows 上运行，并且为 Mac OS 10.9 编译的程序可能无法在 Mac OS 10.10 上运行。

Java 和 Kotlin 通常被翻译为 JVM（Java 虚拟机）的对象代码。计算机上需要一个 Java 运行时环境来执行程序。完全相同的对象代码可以在任何系统上工作。JVM 在服务器上被广泛使用。

到目前为止，我们已经将我们的程序编写为 Kotlin 脚本。脚本适用于快速编程任务。每次运行脚本时，它都会被重新编译，然后执行。

对于较大的程序，最好编写一个应用程序。它可以由许多单独的源文件组成，这些文件可以单独编译（因此您只需编译您已更改的源文件）。一旦编译完成，应用程序启动速度比脚本快得多。

#### 编译

让我们从一个小例子开始。我们创建一个源文件 [point.kt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/48-compiling/point.kt)（注意文件扩展名 kt，与我们用于脚本的扩展名 kts 不同）：

```
data class Point(val x: Int, val y: Int) {
  override fun toString(): String = 
    "[%d,%d]".format(x,y)
}

```

我已经创建了一个只包含此文件的新目录：

```
$ dir
point.kt

```

我现在将使用 Kotlin 编译器 ktc 编译 point.kt：

```
$ ktc point.kt
$ dir classes
Point.class

```

正如您所见，classes 子目录中创建了一个新文件，即 Point.class。扩展名为 class 的文件正好包含 JVM 的一个类定义。

现在我们可以从交互模式（或脚本）中使用这个类：

```
$ ktc
Welcome to Kotlin version 1.0.1-2 (JRE 1.7.0_95-b00)
Type :help for help, :quit for quit
>>> val p = Point(7, 13)
>>> p
[7,13]

```

请注意，在这个交互式会话中，我没有定义 Point 类。Kotlin 会自动找到它：当它看到当前未定义的 Point 时，它会寻找名为 Point 的类或对象的定义。因此，它会在其类路径上检查所有目录，以查找具有名称 Point.class 的文件。由于我使用 -cp 选项将子目录 classes 添加到类路径中，Kotlin 会在那里找到该文件并从该文件加载类定义。请注意，源文件 point.kt 不会被使用——我们可以删除它，仍然可以使用 Point.class 中的 Point 类。

#### 什么可以被编译

当你编写脚本时，可以在文件中放置任意的 Kotlin 命令。例如，这个文件 [hello.kt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/48-compiling/hello.kt) 作为脚本完全没有问题：

```
// This cannot be compiled

println("Hello World")

```

但是，它无法被编译：

```
$ ktc hello.kt
hello.kt:3:1: error: expecting a top level declaration

```

正如编译器已经告诉我们的那样，源文件只能包含顶级声明。这包括使用 fun 定义的函数定义、使用 class 定义的类定义以及使用 val 和 var 定义的全局变量的定义。

#### 应用

这引出了一个问题：如果我们只允许放置声明，那么我们如何运行程序中的任何代码？答案可以追溯到 1970 年代初期：一个应用程序通过一个名为 main 的特殊函数启动。它必须接受一个类型为 Array<String> 的参数，该参数将在程序启动时接收命令行参数。

所以下面的源文件可以被编译 [hello-app.kt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/48-compiling/hello-app.kt)：

```
fun main(args: Array<String>) {
  println("Hello World")
}

```

我们对其进行编译：

```
$ ktc hello-app.kt 
$ dir classes
Hello_appKt.class  META-INF

```

请注意，已经为类 Hello_appKt 创建了一个类文件（还有一个名为 META_INF 的新子目录，其中包含编译器的信息——我们完全可以忽略这一点）。

要运行我们的程序，我们需要"运行类" Hello_appKt：

```
$ kt Hello_appKt
Hello World

```

请记住，要运行程序，您需要提供类名，而不是源文件名。（事实上，根本不需要源文件来运行程序！）

这是一个完整应用程序的小例子：[number-game.kt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/48-compiling/number-game.kt)：

```
import org.otfried.cs109.readString

var secret = 0

val random = java.util.Random()

fun answerGuess(guess: Int) {
  if (guess == secret)
    println("You got it")
  else if (guess > secret)
    println("Too big")
  else if (guess < secret)
    println("Too small")
}

fun main(args: Array<String>) {
  secret = random.nextInt(100)
  var guess = -1
  while (guess != secret) {
    guess = readString("Guess my number> ").toInt()
    answerGuess(guess)
  }
}

```

我们可以编译并运行程序：

```
$ ktc number-game.kt 
$ dir classes
META-INF  Number_gameKt.class
$ kt Number_gameKt
Guess my number> 17
Too small
Guess my number> 68
Too big
Guess my number> 43
Too big
Guess my number> 32
Too big
Guess my number> 25
Too big
Guess my number> 20
Too big
Guess my number> 19
You got it

```

再次注意，要运行程序，你必须提供类名 Number_gameKt（这是 Kotlin 根据源文件 number-game.kt 自动创建的）。

#### 多个源文件

一个更大的应用程序将由几个源文件组成，定义了许多函数和类。至少一个源文件必须定义一个返回 Unit 的函数 main(args: Array<String>)。这个函数是程序的起点。程序是通过表示包含主函数的源文件的类启动的。

编译这样一个应用程序的最简单方法是一次编译所有文件：

```
$ ktc *.kt

```

然而，当程序变得更大时，只重新编译已更改或依赖已更改部分是有意义的。实现这一点的最简单方法是使用构建工具，如 gradle 或 maven，或者集成开发环境（IDE）如 [IntelliJ](https://www.jetbrains.com/idea/download/index.html)（由与 Kotlin 创建者相同的公司制作，因此对 Kotlin 的支持最佳）。 这个 [教程](https://kotlinlang.org/docs/tutorials/getting-started.html) 将帮助您入门。

#### 为分发编译

想象一下，你写了一个不错的程序，想要把它送给朋友或者发布到你的网站上。显然，你不希望他们为了运行你的程序而必须安装 Kotlin 编译器。所以你必须将你的程序打包成这样一种形式，只需 JVM 安装（大多数计算机已经有了）即可。

我们需要做两件事：首先，不再创建大量的类文件，我们将它们全部打包成一个 jar 文件。其次，我们将 Kotlin 库添加到这个包中，这样它就可以在没有安装 Kotlin 的情况下运行：

```
$ kotlinc -d number-game.jar -include-runtime number-game.kt 

```

编译器将创建一个新文件 number-game.jar。您可以直接在 Java 虚拟机上运行它：

```
$ java -jar number-game.jar 
Guess my number> 17
Too big
Guess my number> 13
Too big
Guess my number> 4
Too big
Guess my number> 1
Too small
Guess my number> 2
You got it

```

这将在任何已安装 JVM 的计算机上运行。如果您的程序具有图形用户界面，您可能也可以通过单击 jar 文件来启动它。
