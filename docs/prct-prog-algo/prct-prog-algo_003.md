# 1.1   您的第一个 Java 程序：   Hello World

> 原文：[`introcs.cs.princeton.edu/java/11hello`](https://introcs.cs.princeton.edu/java/11hello)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)


在本节中，我们的计划是通过带领您完成三个基本步骤来进入 Java 编程的世界，以便让一个简单的程序运行起来。与任何应用程序一样，您需要确保 Java 已正确安装在您的计算机上。您还需要一个编辑器和一个终端应用程序。以下是三种流行家用操作系统的系统特定说明。[Mac OS X · Windows · Linux]

## 在 Java 中编程。

我们将 Java 编程过程分为三个步骤：

1.  *通过在文本编辑器中键入程序并将其保存为名为`MyProgram.java`的文件来创建*程序。

1.  *通过在终端窗口中键入"`javac MyProgram.java`"来编译*它。

1.  *执行*（或*运行*）它，通过在终端窗口中键入"`java MyProgram`"。

第一步创建程序；第二步将其翻译为更适合机器执行的语言（并将结果放在名为`MyProgram.class`的文件中）；第三步实际运行程序。

+   *创建 Java 程序。* 程序只是一系列字符，就像句子、段落或诗歌一样。要创建一个程序，我们只需要像为电子邮件一样使用文本编辑器定义该字符序列。HelloWorld.java 是一个示例程序。将这些字符键入您的文本编辑器并将其保存到名为`HelloWorld.java`的文件中。

    ```java
    public class HelloWorld {
       public static void main(String[] args) {
          // Prints "Hello, World" in the terminal window.
          System.out.println("Hello, World");
       }
    }

    ```

+   *编译 Java 程序。* *编译器*是一个应用程序，它将程序从 Java 语言翻译为更适合在计算机上执行的语言。它以扩展名为`.java`的文本文件（您的程序）作为输入，并生成一个扩展名为`.class`的文件（计算机语言版本）。要编译`HelloWorld.java`，请在终端中键入下面的粗体文本。（我们使用`%`符号来表示命令提示符，但根据您的系统可能会有所不同。）

    ```java
    % javac HelloWorld.java

    ```

    如果您正确输入了程序，您不应该看到任何错误消息。否则，请返回并确保��按照上面显示的方式输入程序。

+   *执行（或运行）Java 程序。* 一旦编译程序，您就可以执行它。这是令人兴奋的部分，计算机遵循您的指示。要运行`HelloWorld`程序，请在终端窗口中键入以下内容：

    ```java
    % java HelloWorld

    ```

    如果一切顺利，您应该看到以下响应

    ```java
    Hello, World

    ```

+   *理解 Java 程序。* 具有`System.out.println()`的关键行在终端窗口中打印文本“Hello, World”。当我们开始编写更复杂的程序时，我们将讨论`public`、`class`、`main`、`String[]`、`args`、`System.out`等的含义。

+   *创建自己的 Java 程序。* 目前，我们所有的程序都将像`HelloWorld.java`一样，只是`main()`中的语句顺序不同。编写这样的程序最简单的方法是：

    +   将`HelloWorld.java`复制到一个新文件中，文件名是程序名称后跟`.java`。

    +   在所有地方用程序名称替换`HelloWorld`。

    +   用一系列语句替换打印语句。

## 错误。

大多数错误都可以通过仔细检查我们创建的程序来轻松修复，就像我们在输入电子邮件消息时修复拼写和语法错误一样。

+   *编译时错误。* 这些错误在编译程序时被系统捕获，因为它们阻止编译器进行翻译（因此会发出尝试解释原因的错误消息）。

+   *运行时错误。* 这些错误在执行程序时被系统捕获，因为程序尝试执行无效操作（例如，除以零）。

+   *逻辑错误。* 这些错误（希望）在执行程序时由程序员捕获，因为程序产生了错误答案。错误是程序员的噩梦。它们可能很微妙，很难找到。

你将学到的最基本的技能之一是识别错误；接下来的一个技能将是在编码时足够小心，以避免许多错误。

## 输入和输出。

通常，我们希望为我们的程序提供*输入*：它们可以处理以产生结果的数据。提供输入数据的最简单方法在 UseArgument.java 中有所说明。每当执行此程序时，它都会读取您在程序名称后键入的命令行参数，并将其作为消息的一部分打印回终端。

```java
% javac UseArgument.java
% java UseArgument Alice
Hi, Alice. How are you?
% java UseArgument Bob
Hi, Bob. How are you?

```

#### 练习

1.  编写一个程序 TenHelloWorlds.java，打印"`Hello, World`"十次。

1.  修改 UseArgument.java 以创建一个程序 UseThree.java，接受三个名字并打印出一个以给定顺序相反的名字构成的正确句子，例如，"`java UseThree Alice Bob Carol`"给出"`Hi Carol, Bob, and Alice.`"。

#### 网页练习

1.  编写一个程序 HelloWorldMultilingual.java，在尽可能多的人类语言中打印“Hello World!”。

1.  编写一个程序 Initials.java，使用九行星号打印您的缩写，就像下面的例子一样。

    ```java
    **        ***    **********      **             *             **
    **      ***      **        **     **           ***           **
    **    ***        **         **     **         ** **         **
    **  ***          **          **     **       **   **       **
    *****            **          **      **     **     **     **
    **  ***          **          **       **   **       **   **
    **    ***        **         **         ** **         ** **
    **      ***      **        **           ***           ***
    **        ***    **********              *             *

    ```

1.  描述如果在 HelloWorld.java 中省略

    1.  `main`

    1.  `String`

    1.  `HelloWorld`

    1.  `System.out`

    1.  `println`

1.  描述如果在 HelloWorld.java 中省略

    1.  `;`

    1.  第一个`"`

    1.  第二个`"`

    1.  第一个`{`

    1.  第二个`{`

    1.  第一个`}`

    1.  第二个`}`

1.  描述如果在 HelloWorld.java 中拼写错误（比如，省略第二个字母）

    1.  `main`

    1.  `String`

    1.  `HelloWorld`

    1.  `System.out`

    1.  `println`

1.  我输入了以下程序。它编译正常，但当我执行它时，我得到错误`java.lang.NoSuchMethodError: main`。我做错了什么？

    ```java
    public class Hello {
       public static void main() {
          System.out.println("Doesn't execute");   
       }
    }

    ```

    *答案*：你忘记了`String[] args`。这是必需的。
