# 讲座 1

> 原文：[`cs50.harvard.edu/r/notes/1/`](https://cs50.harvard.edu/r/notes/1/)

+   欢迎！

+   IDE

+   创建您的第一个程序

+   函数

+   错误

+   readline

+   paste

+   文档

+   算术

+   表格

+   向量

+   向量算术

+   外部数据

+   特殊值

+   factor

+   总结

## 欢迎！

+   欢迎来到 CS50 的 R 编程入门课程！

+   *编程* 是一种我们可以向计算机传达指令的方式。

+   有许多 *编程语言* 可以用来编程，包括 *C*、*Python*、*Java*、*R* 等等！

+   我们可以使用 R 来回答有关数据的问题，例如模拟 COVID-19 在游轮上的传播情况。R 也可以用来可视化这些问题的答案。

## IDE

+   *集成开发环境*（IDE）是一个预配置的工具集，可以用来编程。

+   R 有自己的 IDE，称为 *RStudio*，用于专门编写 R 代码。

+   在 RStudio 中，注意 `>` 符号。这表示 R 控制台，我们可以在此处发出命令。

## 创建您的第一个程序

+   您可以通过在 R 控制台中输入 `file.create("hello.R")` 并按键盘上的 `enter` 或 `return` 键来创建您的第一个程序。

+   注意 `hello.R` 以 `.R` 结尾。你可能以前见过其他以 `.jpg` 或 `.gif` 扩展名结尾的文件。`.R` 是 R 使用的特定文件扩展名。

+   当你发出上述命令时，你应该在 R 控制台中看到 `[1] TRUE`。关于这一点，稍后会有更多介绍！

+   在 R 控制台的右侧，您可以访问 *文件资源管理器*。注意 `hello.R` 是在我们的工作目录中创建的——所有文件都将默认保存在此位置。

+   我们可以通过双击它来打开我们的 `hello.R` 文件。

+   *文件编辑器*现在将出现，这是一个我们可以编写多行代码的地方。

+   在文件编辑器中，按照以下方式输入您的第一个程序：

    ```
    print("hello, world") 
    ```

    注意这里出现的所有文本和字符。它们都是必要的。

+   您可以通过点击 *保存* 图标来保存。

+   你可能习惯于通过双击图标来运行程序。在 R 中，我们必须采取不同的方法来运行我们的程序。

+   R 不仅仅是一种编程语言。它还是一个解释器，可以将我们的 *源代码* 转换为计算机可以理解和运行的格式。

+   我们可以通过点击 *运行* 按钮来执行此过程。注意 `hello, world` 现在已经显示出来。做得好！

## 函数

+   *函数* 是一种我们可以运行一系列指令的方式。

+   在您的代码中，`print` 是一个将 `"hello world"` 传递给它的函数。我们传递给函数的内容称为 `参数`。

+   这个函数的副作用是在 R 控制台中显示 `hello, world`。

## 错误

+   *错误* 是代码中无意中出现的错误。

+   按照以下方式修改您的代码：

    ```
    # Demonstrates a bug  prin("hello, world") 
    ```

    注意 `prin` 中缺少的 `t`。

+   运行你的代码，你会注意到产生了错误。

+   *调试*是寻找和消除错误的过程。

## `readline`

+   在 R 中，函数`readline`可以从用户那里读取输入。

+   按照以下方式修改你的代码：

    ```
    readline("What's your name? ")  print("Hello, Carter") 
    ```

    注意如果我们运行此代码，`Carter`将始终出现。

+   我们需要创建一种方法，通过这种方法我们可以读取和使用用户提供的名称。

+   函数不仅仅有参数和副作用，它们还有*返回值*。返回值是由函数提供的。我们可以将返回值存储为*变量*。在 R 中，*变量*也可以称为*对象*，以避免与统计变量混淆——这是一个不同的概念！

+   按照以下方式修改你的代码：

    ```
    name  <-  readline("What's your name? ")  print("Hello, name") 
    ```

    注意名为`name`的变量存储了`readline`的返回值。箭头`<-`表示返回值是从`readline`流向`name`的。这个箭头被称为*赋值运算符*。

+   运行此代码并打开 IDE 右侧的*环境*窗口，你可以看到程序中的变量以及它们存储的内容。

## `paste`

+   尽管如此，运行此代码，注意“name”总是出现。这显然是一个错误！

+   我们可以按照以下方式纠正这个错误：

    ```
    name  <-  readline("What's your name? ")  greeting  <-  paste("Hello, ",  name)  print(greeting) 
    ```

    注意代码的第一行保持不变。注意我们创建了一个名为`greeting`的新变量，并将“Hello, ”和`name`的字符串连接赋值给`greeting`。*字符串*是一组字符。两个单独的字符串通过`paste`函数合并成一个。使用`print`函数打印出结果变量`greeting`。

+   运行此代码，注意环境中出现的新变量。

+   如果你特别留心，仍然有一个错误！在“Hello,”和`name`的值之间存储了两个空格。

## 文档

+   可以通过在 R 控制台中输入`?paste`来访问`paste`的*文档*。相应地，`paste`的文档将出现。阅读此文档，可以了解可以使用`paste`的各种*参数*。

+   与我们当前工作相关的参数之一是`sep`。

+   按照以下方式修改你的代码：

    ```
    name  <-  readline("What's your name? ")  greeting  <-  paste("Hello, ",  name,  sep  =  "")  print(greeting) 
    ```

    注意代码中添加了`sep = ""`。

+   运行此程序，你会看到输出现在按预期工作。

+   恰好程序员经常需要通过将`sep`设置为`""`来省略这些额外的空格。因此，他们发明了`paste0`，它可以不使用任何分隔字符连接字符串。`paste0`可以使用如下：

    ```
    name  <-  readline("What's your name? ")  greeting  <-  paste0("Hello, ",  name)  print(greeting) 
    ```

    注意`paste`变成了`paste0`。

+   你的程序可以进一步简化如下：

    ```
    # Ask user for name  name  <-  readline("What's your name? ")  # Say hello to user  print(paste("Hello,",  name)) 
    ```

    注意`greeting`是通过直接将`paste`的返回值作为`print`的输入值来消除的。

+   最后，当在函数内部嵌套函数，如上所示时，请考虑你和他人阅读代码时可能遇到的进一步挑战。有时，过多的嵌套可能会导致无法理解代码在做什么。这是一个*设计*决策。也就是说，你将经常做出关于代码的决定，以使你的用户和程序员都受益。

+   此外，你可能做出的一个*风格*决策是使用`#`符号添加注释，其中描述代码部分的功能。

## 算术

+   让我们创建一个新的程序，用来统计一些虚构角色的票数。

+   关闭`hello.R`文件。

+   在你的控制台中输入`file.create("count.R")`。

+   按照以下方式创建你的代码：

    ```
    mario  <-  readline("Enter votes for Mario: ")  peach  <-  readline("Enter votes for Peach: ")  bowser  <-  readline("Enter votes for Bowser: ")  total  <-  mario  +  peach  +  bowser  print(paste("Total votes:",  total)) 
    ```

    注意到`readline`的返回值被存储在三个变量中，分别命名为`mario`、`peach`和`bowser`。变量`total`被分配了`mario`、`peach`和`bowser`的总和值。然后，打印出这个总和。

+   R 有很多算术运算符，包括`+`、`-`、`*`、`/`以及其他运算符！

+   运行这段代码，并输入票数，会产生一个错误。

+   正好用户输入被当作字符串处理，而不是数字。查看环境，你会注意到`mario`和其他值的值被引号包围。这些引号表明这些值被存储为字符字符串，而不是数字。这些值需要是数字才能与`+`一起相加。

+   在 R 中，变量可以以不同的模式（有时也称为“类型”）存储。其中一些“存储模式”包括字符、双精度和整数。

+   我们可以按照以下方式将这些变量转换为所需的存储模式：

    ```
    mario  <-  readline("Enter votes for Mario: ")  peach  <-  readline("Enter votes for Peach: ")  bowser  <-  readline("Enter votes for Bowser: ")  mario  <-  as.integer(mario)  peach  <-  as.integer(peach)  bowser  <-  as.integer(bowser)  total  <-  mario  +  peach  +  bowser  print(paste("Total votes:",  total)) 
    ```

    注意到如何通过`as.integer`使用*强制转换*将`mario`和其他值转换为整数。

+   运行这段代码并查看环境，你可以看到这些值现在被存储为没有引号的整数。

+   这个程序可以进一步简化如下：

    ```
    mario  <-  as.integer(readline("Enter votes for Mario: "))  peach  <-  as.integer(readline("Enter votes for Peach: "))  bowser  <-  as.integer(readline("Enter votes for Bowser: "))  total  <-  sum(mario,  peach,  bowser)  print(paste("Total votes:",  total)) 
    ```

    注意到`sum`函数是如何被用来对三个变量的值进行求和的。

+   有没有一种方法可以利用现有的数据源？

## 表格

+   *表格*是我们可以用以组织数据的许多结构之一。

+   *表格*是一组行和列，其中行通常代表存储的某个实体，列代表这些实体的属性。

+   表格可以存储在多种文件格式中。一种常见的格式是逗号分隔值（CSV）文件。

+   在 CSV 文件中，每一行存储在单独的一行上。列由逗号分隔。

+   在我们开始下一个程序之前，在 R 控制台中输入`ls()`以确定环境中所有活动的变量。然后，输入`rm(list = ls())`从环境中移除所有这些值。再次输入`ls()`，你会注意到环境中没有剩余的对象。

+   接下来，输入 `file.create("tabulate.R")` 以创建我们的新程序文件。打开你的文件资源管理器，打开 `tabulate.R` 文件。此外，你应该从本讲座的源代码下载 `votes.csv` 文件并将其拖入你的工作目录。

+   按照以下方式创建你的代码：

    ```
    votes  <-  read.table("votes.csv")  View(votes) 
    ```

    注意代码的第一行是如何从 `votes.csv` 读取表格到 `votes` 变量的。然后，`View` 允许你查看 `votes` 中存储的内容。

+   运行此代码，你现在可以看到 `votes` 对象中存储的单独标签页。然而，这里有一个错误。注意所有数据都被读入了一个列中。看起来 `read.table` 正在从 `csv` 文件中读取数据。但是，似乎还需要一些格式化。

+   按照以下方式修改你的代码：

    ```
    votes  <-  read.table(  "votes.csv",  sep  =  ","  )  View(votes) 
    ```

    注意 `sep` 是如何用于告诉 `read.table` 每个列将根据哪个字符进行分隔的。

+   尽管如此，运行此代码时仍然有错误。我们如何让 `read.table` 识别表格的标题？

+   按照以下方式修改你的代码：

    ```
    votes  <-  read.table(  "votes.csv",  sep  =  ",",  header  =  TRUE  )  View(votes) 
    ```

    注意 `header = TRUE` 参数允许 `read.table` 识别存在标题。

+   运行此文件，表格将按预期显示。

+   程序员创建了一个快捷方式，以便能够更简单地完成此操作。按照以下方式修改你的代码：

    ```
    votes  <-  read.csv("votes.csv")  View(votes) 
    ```

    注意 `read.csv` 如何以前所未有的简单性完成之前代码所做的工作！

+   现在我们已经加载数据，我们如何访问它？按照以下方式修改你的代码：

    ```
    votes  <-  read.csv("votes.csv")  votes[,  1]  votes[,  2]  votes[,  3] 
    ```

    注意如何使用 *方括号表示法* 以 `votes[row, column]` 格式访问值。因此，`votes[, 2]` 将显示 `poll` 列中的数字。

## 向量

+   *向量* 是一个具有相同存储模式的值的列表。

+   考虑到我们的候选人投票数据框（或表格），我们可以通过创建一个新向量来访问特定值。

+   我们可以通过调用每个列的精确名称来简化此程序。

    ```
    votes  <-  read.csv("votes.csv")  colnames(votes)  votes$candidate  votes$poll  votes$mail 
    ```

    注意 `votes$poll` 返回一个包含 `poll` 列中所有值的向量。现在我们可以通过这个新向量访问 `poll` 列的值。

+   运行此代码，注意每个列的值是如何出现的。

+   转到我们关于如何求和这些值的原始问题，按照以下方式修改你的代码：

    ```
    votes  <-  read.csv("votes.csv")  sum(votes$poll[1],  votes$poll[2],  votes$poll[3]) 
    ```

    注意 `sum` 函数是如何用于对 `poll` 表格的前三行中的值进行求和的。

+   然而，此代码不是动态的。它相当不灵活。如果有超过三个候选人怎么办？因此，我们可以简化我们的代码如下，使其更具动态性：

    ```
    votes  <-  read.csv("votes.csv")  sum(votes$poll)  sum(votes$mail) 
    ```

    注意在向量 `votes$poll` 和 `votes$mail` 中找到的值是如何被求和的。

+   如上图所示，使用方括号表示法，我们也可以尝试对 `poll` 和 `mail` 列中的每一行的值进行求和。按照以下方式修改你的代码：

    ```
    votes  <-  read.csv("votes.csv")  votes$poll[1]  +  votes$mail[1]  votes$poll[2]  +  votes$mail[2]  votes$poll[3]  +  votes$mail[3] 
    ```

    注意 `poll` 和 `mail` 的每一行是如何被加在一起的。

+   这是否是 R 提供的最佳方法？

## 向量算术

+   有很多时候我们希望能够将一个向量的行与另一个向量的行相加。我们可以通过向量算术来完成此操作。

+   在使我们的代码更加动态的同一种精神下，我们可以进一步修改我们的代码如下：

    ```
    votes  <-  read.csv("votes.csv")  votes$poll  +  votes$mail 
    ```

    注意向量是如何逐元素相加的。也就是说，第一个向量的第一行加到第二个向量的第一行上，第一个向量的第二行加到第二个向量的第二行上，依此类推。这导致了一个与`poll`和`mail`向量具有相同行数的最终向量。

+   向量算术会产生一个全新的向量。我们可以以各种方式处理这个新向量。

+   自然地，我们可能想要存储我们算术的结果。我们可以通过以下方式修改我们的代码来做到这一点：

    ```
    votes  <-  read.csv("votes.csv")  votes$total  <-  votes$poll  +  votes$mail  write.csv(votes,  "totals.csv") 
    ```

    注意最终的总数被存储在一个名为`votes$total`的新向量中，实际上它是`votes`数据框的新`total`列。然后我们将结果`votes`数据框写入一个名为`totals.csv`的文件。

+   当你查看`csv`文件时，会出现一个问题。注意默认情况下，“行名”是包含在内的。这些可以通过修改以下代码来排除：

    ```
    votes  <-  read.csv("votes.csv")  votes$total  <-  votes$poll  +  votes$mail  write.csv(votes,  "totals.csv",  row.names  =  FALSE) 
    ```

    注意`row.names`被设置为`FALSE`。

## 外部数据

+   今天，我们看到了许多关于如何使用 R 的例子。

+   有许多情况下你可能希望使用别人的数据集。

+   你可以如下访问在线数据源：

    ```
    # Demonstrates reading data from a URL  url  <-  "https://github.com/fivethirtyeight/data/raw/master/non-voters/nonvoters_data.csv"  voters  <-  read.csv(url) 
    ```

    注意`read.csv`是如何从定义的 URL 中提取数据的。

+   看这个数据框，你可以运行`nrow`来获取行数。你可以运行`ncol`来获取列数。

    ```
    # Demonstrates finding number of rows and columns in a large data set  url  <-  "https://github.com/fivethirtyeight/data/raw/master/non-voters/nonvoters_data.csv"  voters  <-  read.csv(url)  nrow(voters)  ncol(voters) 
    ```

    注意`nrow`和`ncol`是如何用来确定这个数据中有多少行和列的。

+   数据集有时会附带一个*代码簿*。代码簿是关于这个数据中包含哪些列的指南。例如，列`Q1`可能代表在研究中向参与者提出的一个特定问题。通过查看这个数据集的代码簿，我们可以知道有一个名为`voter_category`的列，它定义了每个参与者的特定投票行为。

+   你可能想了解在这个列中参与者可能选择的各个选项。这可以通过`unique`函数来完成。

    ```
    # Demonstrates finding unique values in a vector  url  <-  "https://github.com/fivethirtyeight/data/raw/master/non-voters/nonvoters_data.csv"  voters  <-  read.csv(url)  unique(voters$voter_category) 
    ```

    注意`unique`是如何用来确定参与者可能选择的选项的。

## 特殊值

+   对于`Q22`，我们在代码簿中发现这个问题是关于为什么参与者没有注册投票的原因。查看这个数据，我们看到`NA`是呈现的值之一。`NA`在 R 中表示“不可用”的特殊值。

+   R 中的其他特殊值包括`Inf`，`-Inf`，`NaN`和`NULL`。分别表示无限大，负无限大，非数字和空（或无）值。

+   要查看`Q22`的这些可能值，我们可以运行以下代码：

    ```
    # Demonstrates NA  url  <-  "https://github.com/fivethirtyeight/data/raw/master/non-voters/nonvoters_data.csv"  voters  <-  read.csv(url)  voters$Q22  unique(voters$Q22) 
    ```

    注意到`unique`再次被用来发现`Q22`的可能值。

## `factor`

+   `Q21`涉及参与者对未来选举的投票计划。在这个列中，值`1`，`2`和`3`与特定的可能答案相对应。例如，`1`可能代表“是”。

+   在 R 语言中，我们可以使用 `factor` 函数将数字值转换为特定的文本答案。例如，我们可以使用 `factor` 函数将数字 `1` 转换为对应的文本“是”。我们可以通过以下方式修改我们的代码来完成这个操作：

    ```
    # Demonstrates converting a vector to a factor  url  <-  "https://github.com/fivethirtyeight/data/raw/master/non-voters/nonvoters_data.csv"  voters  <-  read.csv(url)  voters$Q21  factor(  voters$Q21  )  factor(  voters$Q21,  labels  =  c("?",  "Yes",  "No",  "Unsure/Undecided")  ) 
    ```

    注意 `factor(voters$Q21)` 将会显示 `Q21` 的具体级别（类别）数据。在代码中出现的后续 `factor` 中，标签被应用于每个级别。例如，`1` 与“是”相关联。

+   在许多情况下，我们可能希望排除某些值。在 `Q21` 中，我们可能希望排除 `-1`，因为这个值代表的含义并不明确。我们可以按照以下方式操作：

    ```
    # Demonstrates excluding values from the levels of a factor  url  <-  "https://github.com/fivethirtyeight/data/raw/master/non-voters/nonvoters_data.csv"  voters  <-  read.csv(url)  voters$Q21  <-  factor(  voters$Q21,  labels  =  c("Yes",  "No",  "Unsure/Undecided"),  exclude  =  c(-1)  ) 
    ```

    注意 `-1` 是如何被排除的。

## 总结

在本课中，你学习了如何在 R 语言中表示数据。具体来说，你学习了……

+   函数

+   错误

+   `readline`

+   `paste`

+   文档

+   算术

+   表格

+   向量

+   向量算术

+   外部数据

+   特殊值

+   `factor`

次次再见，当我们讨论如何转换数据时再见。
