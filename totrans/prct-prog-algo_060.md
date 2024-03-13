# 1.1 您的第一个程序

> 原文：[`introcs.cs.princeton.edu/python/11hello`](https://introcs.cs.princeton.edu/python/11hello)

在本节中，我们的计划是通过带领您完成运行简单程序所需的基本步骤，将您引入 Python 编程的世界。*Python 系统*（以下简称*Python*）是一组应用程序，与您习惯使用的其他应用程序（如文字处理器、电子邮件程序和网络浏览器）类似。与任何应用程序一样，您需要确保 Python 已正确安装在您的计算机上。您还需要一个文本编辑器和一个终端应用程序。您的第一个任务是按照安装这样一个 Python 编程环境的说明。

您必须安装 Python 3 或 Python 2 编程环境中的一个。

这里是安装 Python 3 编程环境的说明[Windows · Mac OS X · Linux]。我们建议您安装并使用 Python 3 编程环境。

这里是安装 Python 2 编程环境的说明[Windows · Mac OS X · Linux]。我们建议您仅在有充分理由（不属于本书和书站要求的外部原因）时使用 Python 2 编程环境。

* * *

## Python 编程

要在 Python 中编程，您需要：

+   通过将其键入到一个名为，比如`myprogram.py`的文件中来*撰写*一个程序。

+   通过在终端窗口中键入`python myprogram.py`来*运行*（或*执行*）它。

* * *

## 撰写 Python 程序

一个 Python 程序只是存储在具有`.py`扩展名的文件中的一系列字符。要创建一个，您只需使用文本编辑器定义该字符序列。

该程序 helloworld.py 是一个完整 Python 程序的示例。我们在本页重复该程序以便后续描述。行号显示出来是为了方便引用特定行，但它们不是程序的一部分，也不应该出现在您的 helloworld.py 文件中。

```
1  import stdio
2
3  # Write 'Hello, World' to standard output.
4  stdio.writeln('Hello, World')

```

该程序的唯一操作是向终端窗口写入一条消息。一个 Python 程序由语句组成。通常，您将每个语句放在不同的行上。

+   第 1 行包含一个`import`语句。该语句告诉 Python 您打算使用在名为`stdio.py`的文件中定义的`stdio`模块中定义的功能。`stdio.py`文件是我们专门为本书设计的一个文件。它定义了与读取输入和写入输出相关的函数。导入`stdio`模块后，您可以稍后调用该模块中定义的函数。

+   第 2 行是空行。Python 会忽略空行；程序员使用它们来分隔代码的逻辑块。

+   第 3 行包含一个注释，用于记录程序。在 Python 中，注释以'#'字符开始，并延伸到行尾。Python 会忽略注释；它们仅供程序的人类读者阅读。

+   第 4 行是程序的核心。这是一个调用`stdio.writeln()`函数写入一行给定文本的语句。请注意，我们通过写入模块名、后跟一个句点、后跟函数名的方式来调用另一个模块中的函数。

|

### Python 2

本书站的通用语言是 Python 3，因为它是 Python 编程的未来。然而，我们非常小心地确保书站中的代码适用于 Python 2 或 Python 3。例如，在 Python 2 中，helloworld.py 程序可能只是一行`print 'Hello, World'`，但这在 Python 3 中不是有效的程序。为了开发能在两个 Python 版本中都有效的输出代码，我们使用我们的`stdio`模块。每当两种语言之间有显著差异时，我们会在一个类似这样的提示框中提醒 Python 2 用户。|

* * *

## 执行 Python 程序

一旦您编写好程序，您可以运行（或执行）它。为了运行您的程序，Python 编译器将您的 Python 程序转换为更适合在计算机上执行的语言。然后 Python 解释器指导您的计算机按照该语言中表达的指令执行。要运行您的程序，在终端窗口中键入`python`命令，后跟包含 Python 程序的文件名。

```
$ python helloworld.py

```

如果一切顺利，您将看到以下响应：

```
Hello, World

```

目前，您的所有程序都将与 helloworld.py 相同，只是语句序列不同。组成这样的程序的最简单方法是：

+   将 helloworld.py 复制到一个新文件中，文件名为程序名称后跟`.py`。

+   用不同的语句或语句序列替换`stdio.writeln()`的调用。

* * *

## 错误

在学习编程时，很容易混淆编辑、编译和解释程序之间的区别。在学习编程时，您应该将它们分开，以更好地理解不可避免出现的错误的影响。您可以在本节末尾的问答中找到几个错误的示例。

通过仔细检查程序，您可以修复或避免大多数错误。一些错误，称为*编译时错误*，在 Python 编译程序时引发，因为它们阻止编译器进行翻译。Python 报告编译时错误为`SyntaxError`。其他错误，称为*运行时错误*，直到 Python 解释程序时才会引发。例如，如果您在 helloworld.py 中忘记了`import stdio`语句，那么 Python 将在运行时引发`NameError`。

* * *

## 输入和输出

通常，我们希望为我们的程序提供输入，即它们可以处理以产生结果的数据。提供输入数据的最简单方法在 useargument.py 中有所说明。每当您运行该程序时，它都会接受您在程序名称后键入的命令行参数，并将其作为消息的一部分写回终端。

```
$ python useargument.py Alice
Hi, Alice. How are you?
$ python useargument.py Bob
Hi, Bob. How are you?

```

在 useargument.py 中，语句`import sys`告诉 Python 您希望使用`sys`模块中定义的功能。其中一个功能名为`argv`，是一个命令行参数列表（出现在命令行上`python useargument.py`之后，由空格分隔）。第 1.4 节详细描述了列表；目前了解`sys.argv[1]`是您在程序名称后键入的第一个命令行参数，`sys.argv[2]`是您在程序名称后键入的第二个命令行参数，依此类推。

除了`stdio.writeln()`，useargument.py 还调用`stdio.write()`函数。该函数与`stdio.writeln()`类似，但只写入字符串（不是换行符）。

* * *

## 获取更多信息

我们鼓励您在使用本书站时经常访问官方 Python 网站[`www.python.org`](http://www.python.org)。更具体地说：

+   [`docs.python.org/reference/index.htm`](http://docs.python.org/reference/index.html)提供有关 Python 语言的信息。

+   [`docs.python.org/library/index.html`](http://docs.python.org/library/index.html)提供有关 Python 标准库的信息。

+   [`www.python.org/dev/peps/pep-0008/`](http://www.python.org/dev/peps/pep-0008/)提供有关 Python 编程风格的信息。

* * *

## 编程风格

列表中的最后一项值得一些详细说明。关于编程风格...

在编写代码时的首要目标是使其易于理解。易于理解的程序更有��能是正确的，并且在随着时间的推移而进行维护时更有可能保持正确。

程序员使用风格指南使程序更易于理解。正如上面所述，官方 Python 风格指南在页面 [`www.python.org/dev/peps/pep-0008/`](http://www.python.org/dev/peps/pep-0008/) 中给出。我们建议你现在快速阅读一下风格指南，并在以后随着编写 Python 程序的经验增加时偶尔返回查看。

附录 B 补充了官方 Python 风格指南，提供了适合初学计算机编程的建议。我们建议你现在快速阅读一下附录 B，并偶尔返回查看。

* * *

#### 问与答

**Q.** 为什么选择 Python？

**A.** 我们正在研究的程序与其他几种语言中的对应程序非常相似，因此我们选择的语言并不重要。我们使用 Python 是因为它广泛可用，包含一整套现代抽象，并且具有各种��动检查程序错误的功能，因此适合学习编程。Python 正在不断发展，并有许多版本。

**Q.** 我应该使用哪个版本的 Python？

**A.** 我们推荐使用 Python 3，但我们非常小心地确保本书中的代码适用于 Python 2 或 Python 3。所有代码都经过了 Python 2.7 和 3.4 版本的测试（出版时的最新主要版本）。我们使用通用术语 Python 2 指 Python 2.7，Python 3 指 Python 3.4。

**Q.** 我真的必须在书中输入程序以尝试运行它们吗？我相信你已经运行过它们并且它们产生了指定的输出。

**A.** 你应该输入并运行 helloworld.py。如果你还运行 useargument.py，尝试不同的输入并修改它以测试自己的想法，你的理解将大大增强。

**Q.** 当我运行 helloworld.py 时，Python 生成消息

```
ImportError: No module named stdio.

```

那是什么意思？

**A.** 这意味着书站模块 `stdio` 对 Python 不可用。

**Q.** 如何使书站模块 `stdio` 可用于 Python？

**A.** 如果你按照本书网站上的逐步说明安装 Python 编程环境，`stdio` 模块应该已经可用于 Python。

**Q.** Python 对制表符、空格和换行符等空白字符有什么规定？

**A.** 一般来说，Python 认为程序文本中的大多数空白字符是等效的，但有两个重要的例外：*字符串字面值* 和 *缩进*。字符串字面值是单引号内的字符序列，比如 `'Hello, World'`。如果在引号内放入任意数量的空格，你将在字符串字面值中得到完全相同数量的空格。缩进是行首的空白。行首的空格数量在构建 Python 程序结构中起着重要作用，我们将在第 1.3 节中看到。目前你不应该缩进任何代码。

**Q.** 为什么要使用注释？

**A.** 评论是必不可少的，因为它们帮助其他程序员理解你的代码，甚至可以帮助你回顾时理解自己的代码。尽管书中的程序要求我们在书中展示的程序中节制使用注释，但本书网站上的程序被注释得更加现实。

**Q.** 我可以在一行上放置多个语句吗？

**A.** 是的，通过用分号分隔语句。例如，这行代码产生与 helloworld.py 相同的输出：

```
import stdio; stdio.writeln('Hello, World')

```

但许多程序员建议不要这样做，作为一种风格问题。

**Q.** 如果省略括号或拼错单词，比如 `stdio`、`write` 或 `writeln`，会发生什么？

**A.** 这取决于你具体做什么。这些所谓的*语法错误*通常会被编译器捕获。例如，如果你编写一个程序`bad.py`，与 helloworld.py 完全相同，只是省略了第一个左括号，你���得到以下相当有用的消息：

```
% python bad.py
  File "bad.py", line 4
    stdio.write'Hello, World')
                            ^
SyntaxError: invalid syntax

```

从这条消息中，你可能会正确地推测你需要插入一个左括号。但编译器可能无法告诉你确切地犯了哪个错误，所以错误消息可能难以理解。例如，如果你省略了第一个右括号而不是第一个左括号，你会得到以下不太有用的消息，它引用了错误行后面的行：

```
% python bad.py
  File "bad.py", line 5
                                ^
SyntaxError: unexpected EOF while parsing

```

习惯于这种消息的一种方法是故意在一个简单的程序中引入错误，然后看看会发生什么。无论错误消息说什么，你都应该把编译器当作朋友，因为它只是在试图告诉你你的程序有问题。

**Q.** 当我运行`useargument.py`时，我收到一个奇怪的错误消息。请解释一下。

**A.** 最有可能的是，你忘记包含一个命令行参数：

```
% python useargument.py
Hi, Traceback (most recent call last):
  File "useargument.py", line 5, in stdio.write(sys.argv[1])
IndexError: list index out of range 
```

Python 解释器抱怨你运行了程序，但没有像承诺的那样输入命令行参数。在第 1.4 节中，你将更详细地了解列表索引。记住这个错误消息：你可能会再次看到它。即使有经验的程序员偶尔也会忘记输入命令行参数。

**Q.** 我可以使用哪些 Python 模块和函数？

**A.** 许多标准模块都随着任何 Python 安装捆绑在一起。许多其他模块作为扩展模块可供下载和安装。我们专门为本书和书站编写了其他模块（如`stdio`模块）；我们将它们称为*书站模块*。简而言之，有数百个 Python 模块可供你使用，每个模块（通常）定义多个函数。本书只介绍最基本的模块和函数，并且有意以逐步增量的方式（从下一节开始）介绍，以避免用信息压倒你。

* * *

#### 练习

1.  编写一个程序，将`Hello, World`消息写出 10 次。

*解决方案*：参见 tenhellos1.py。

1.  描述如果你在 helloworld.py 中省略以下内容会发生什么：

1.  `import`

1.  `stdio`

1.  `import stdio`

1.  描述如果你在 helloworld.py 中拼错（比如说，省略第二个字母）以下内容会发生什么：

1.  `import`

1.  `stdio`

1.  `write`

1.  `writeln`

1.  描述如果你在 helloworld.py 中省略以下内容会发生什么：

1.  第一个`'`

1.  第二个`'`

1.  `stdio.writeln()`语句

1.  描述如果你尝试用以下每个命令行执行 useargument.py 会发生什么：

1.  `python useargument.py python`

1.  `python useargument.py @!&^%`

1.  `python useargument.py 1234`

1.  `python useargument Bob`

1.  `useargument.py Bob`

1.  `python useargument.py Alice Bob`

1.  修改 useargument.py 编写一个程序，接受三个名字，并按给定顺序的相反顺序写出一个包含这些名字的正确句子，例如，`python usethree.py Alice Bob Carol`写出字符串`'Hi Carol, Bob, and Alice'`。

*解决方案*：参见 usethree.py。

1.  编写一个程序，使用九行星号写出你的姓名首字母，就像下面这样。

    ```
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

    *解决方案*：参见 initials.py。
