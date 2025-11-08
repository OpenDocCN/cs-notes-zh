# 第七讲

> 原文：[`cs50.harvard.edu/r/notes/7/`](https://cs50.harvard.edu/r/notes/7/)

+   欢迎！

+   包

+   包结构

+   devtools

+   编写测试

+   编写 R 代码

+   NAMESPACE

+   测试代码

+   编写文档

+   构建包

+   更新包

+   使用和共享包

+   总结

## 欢迎光临！

+   欢迎回到 CS50 的 R 编程入门课程！

+   今天，我们将学习如何打包和分发我们的程序。这样，我们就可以与世界分享它们了！

## 包

+   今天，我们将构建和打包一个名为 `ducksay` 的程序。

+   如果你已经参加过我们的其他 CS50 课程，你可能知道一个名为 `cowsay` 的程序。它接受一些文本并创建一个牛说这些文本的图像。我们将以同样的精神构建 `ducksay`。

+   *包* 是经过编译的源代码，以便可以分发。

## 包结构

+   包应该保存在一个与包同名的文件夹中。

+   我们可以在 R 控制台中输入以下命令来做到这一点：

    ```
    dir.create("ducksay")  setwd("ducksay") 
    ```

    注意这些命令创建了一个名为 `ducksay` 的目录，然后将工作目录设置为 `ducksay`。

+   包通常在主文件夹中有以下结构：

    ```
    DESCRIPTION
    NAMESPACE
    man/
    R/
    tests/ 
    ```

    `DESCRIPTION` 文件将包括对包的描述，包括谁编写了它。`NAMESPACE` 文件将包括我们希望向我们的包用户提供的函数列表。`man` 是一个包含包手册（文档）的文件夹。`R` 包含包的 R 代码。最后，`tests` 包含我们想要运行的所有测试，以确保我们的包按预期行为。

+   我们可以在 R 控制台中输入 `file.create("DESCRIPTION")` 来创建一个 `DESCRIPTION` 文件。现在我们可以打开这个文件并按照以下方式编码：

    ```
    # Demonstrates required components of a DESCRIPTION file  Package:  ducksay  Title:  Duck  Say  Description:  Say  hello  with  a  duck.  Version:  1.0  Authors@R:  person("Carter",  "Zenke",  email  =  "carter@cs50.harvard.edu",  role  =  c("aut",  "cre",  "cph"))  License:  MIT  +  file  LICENSE 
    ```

    注意包的命名和标题。然后，提供描述。包括作者。最后，提供提供此包的许可证。你可以在 `DESCRIPTION` 文件的 [文档](https://cran.r-project.org/doc/manuals/R-exts.html#The-DESCRIPTION-file) 中了解更多关于这些字段的信息。

+   如上 `DESCRIPTION` 文件所示，我们还需要一个 `LICENSE` 文件。我们可以按照以下方式编码：

    ```
    # Demonstrates adding on to a license template  YEAR:  ...  COPYRIGHT  HOLDER:  ducksay  authors 
    ```

    用当前年份填充 `...`。注意许可证和版权所有者的年份是如何命名的。

## devtools

+   一个名为 devtools 的包允许我们更快地创建包。

+   特别是，`devtools` 包提供了创建我们包测试和 R 代码所需文件夹结构的工具。

+   我们可以通过在 R 控制台中输入 `library(devtools)` 来加载 devtools，假设它已经安装。

## 编写测试

+   感谢 devtools 包，我们可以轻松地使用 testthat 为我们编写的包开发测试。

+   然后，我们可以输入 `use_testthat()` 来调用使用 testthat 的能力。我们的 `DESCRIPTION` 文件将自动修改如下：

    ```
    # Demonstrates suggesting a dependency, for testing's sake  Package:  ducksay  Title:  Duck  Say  Description:  Say  hello  with  a  duck.  Version:  1.0  Authors@R:  person("Carter",  "Zenke",  email  =  "carter@cs50.harvard.edu",  role  =  c("aut",  "cre",  "cph"))  License:  MIT  +  file  LICENSE  Suggests:  testthat  (>=  3.0.0)  Config/testthat/edition:  3 
    ```

    注意包会建议应该安装 testthat 版本 3.0.0 或更高版本。这可能会根据您安装的 testthat 版本而有所不同。

+   在由 `use_testthat` 创建的 `tests/testthat` 文件夹内，我们可以创建我们的第一个测试，`test-ducksay.R`，如下所示：

    ```
    # Demonstrates describing behavior of `ducksay`  describe("ducksay()",  {  it("can print to the console with `cat`",  {  expect_output(cat(ducksay()))  })  it("can say hello to the world",  {  expect_match(ducksay(),  "hello, world")  })  }) 
    ```

    注意 `expect_match` 在 `ducksay` 的输出中寻找字符串 `hello, world`。

## 编写 R 代码

+   继续使用 devtools，现在我们可以在 R 控制台中输入以下内容：`use_r("ducksay")`。

+   此命令将创建一个名为 `R` 的文件夹和一个名为 `ducksay.R` 的文件。

+   现在，是时候在我们的程序中提供一些我们将打包的功能了。这个功能应该与我们所编写的测试相匹配。

+   按照以下方式编写 `ducksay.R` 的代码：

    ```
    # Demonstrates defining a function for a package  ducksay  <-  function()  {  paste(  "hello, world",  ">(. )__",  " (____/",  sep  =  "\n"  )  } 
    ```

## `NAMESPACE`

+   如前所述，我们需要在名为 `NAMESPACE` 的文件中提供有关此包最终用户可用的函数的信息。

+   要这样做，您可以在控制台中输入 `file.create("NAMESPACE")`。然后，按照以下方式编辑此文件：

    ```
    # Demonstrates declaring `ducksay` accessible to package end users  export(ducksay) 
    ```

    此文件仅使 `ducksay` 函数对包的最终用户可用。

+   现在，我们可以在 R 控制台中输入 `load_all()` 来加载 `NAMESPACE` 中命名的所有可用函数。

## 测试代码

+   现在，您可以通过运行 `test()` 来测试我们的函数。不应该出现任何错误。

+   此外，在您加载了这个包的函数之后，现在您可以在 RStudio 中使用 `ducksay`。

+   更新我们的测试，让我们测试一下 `ducksay` 中是否出现了鸭子：

    ```
    # Demonstrates checking for duck in output  describe("ducksay()",  {  it("can print to the console with `cat`",  {  expect_output(cat(ducksay()))  })  it("can say hello to the world",  {  expect_match(ducksay(),  "hello, world")  })  it("can say hello with a duck",  {  duck  <-  paste(  ">(. )__",  " (____/",  sep  =  "\n"  )  expect_match(ducksay(),  duck,  fixed  =  TRUE)  })  }) 
    ```

    注意这个测试看起来是否表示了鸭子。此外，注意 `fixed = TRUE`，正如讲座中所述，它防止测试错误地解释鸭子中的一些字符作为称为正则表达式的东西的一部分。现在就足够了，正则表达式不是我们想要的！

## 编写文档

+   现在，我们可以记录如何使用我们的函数。通常，我们可以输入 `?ducksay` 来查看文档。然而，我们还没有创建我们的文档。

+   文档是用一种称为标记语言的类型语言编写的。标记语言提供用于指定文档格式的语法。

+   您可以通过以下方式编写文档：

    ```
    dir.create("man")  file.create("man/ducksay.Rd") 
    ```

    第一个命令创建一个名为 `man` 的文件夹。第二个创建我们的文档文件。

+   按照以下方式修改您的文档文件：

    ```
    # Demonstrates required markup for R documentation files  \name{ducksay}  \alias{ducksay}  \title{Duck  Say}  \description{A  duck  that  says  hello.}  \usage{  ducksay()  }  \value{  A  string  representation  of  a  duck  saying  hello  to  the  world.  }  \examples{  cat(ducksay())  } 
    ```

    注意 `name`、`title`、`description`、`usage` 以及其他部分是如何提供的。您可以通过阅读有关 R 文档文件的[文档](https://cran.r-project.org/doc/manuals/R-exts.html#Writing-R-documentation-files)来了解更多关于这些元素的信息。

+   现在，是时候总结一下并分享我们的包了。

## 构建包

+   一旦一个包的内容准备好打包和分发，可以使用两个命令中的任何一个来启动 *构建*：

    ```
    build
    R CMD build 
    ```

    注意到 `build` 是一个 devtools 函数，可以直接在 R 控制台中运行。`R CMD build` 可以在 R 的计算机终端外运行。

+   运行 `build`，你将在工作目录中看到一个 `.gz` 文件被输出。

## 更新包

+   要更新我们的代码，我们可以打开我们的测试文件并更新测试如下：

    ```
    # Demonstrates ensuring duck repeats given phrase  describe("ducksay()",  {  it("can print to the console with `cat`",  {  expect_output(cat(ducksay()))  })  it("can say hello to the world",  {  expect_match(ducksay(),  "hello, world")  })  it("can say hello with a duck",  {  duck  <-  paste(  ">(. )__",  " (____/",  sep  =  "\n"  )  expect_match(ducksay(),  duck,  fixed  =  TRUE)  })  it("can say any given phrase",  {  expect_match(ducksay("quack!"),  "quack!")  })  }) 
    ```

    注意到添加了一个新的测试，用于查找“quack！”

+   考虑到这个测试，我们现在可以更新我们的源代码，以便输入任何短语，然后鸭子会相应地表达出来：

    ```
    # Demonstrates taking an argument to print  ducksay  <-  function(phrase  =  "hello, world")  {  paste(  phrase,  ">(. )__",  " (____/",  sep  =  "\n"  )  } 
    ```

    注意到提供了一个默认的 `phrase`，“hello, world”。如果提供了另一个 `phrase`，它将说出那个 `phrase`。

+   同样，我们可以更新我们的文档文件如下：

    ```
    # Demonstrates updated markup, including specifying arguments  \name{ducksay}  \alias{ducksay}  \title{Duck  Say}  \description{A  duck  that  says  hello.}  \usage{  ducksay(phrase  =  "hello, world")  }  \arguments{  \item{phrase}{The  phrase  for  the  duck  to  say.}  }  \value{  A  string  representation  of  a  duck  saying  the  given  phrase.  }  \examples{  cat(ducksay())  cat(ducksay("quack!"))  } 
    ```

    注意到 `value` 已更新。此外，`arguments` 也已更新。另一个例子在 `examples` 中提供。

+   我们可以再次运行 `build` 来包含我们的修改。

+   现在我们可以将这个包与其他人共享。

## 使用和共享包

+   现在让我们创建一个名为 `greet.R` 的程序，该程序使用这个包。

+   我们可以通过在 R 控制台中输入 `setwd("..")` 来将工作目录设置在 `ducksay` 之外。这将把我们的工作目录移动到 `ducksay` 之上的一级目录。

+   接下来，我们可以输入 `file.create("greet.R")` 来创建一个新文件。按照以下方式修改此文件：

    ```
    # Demonstrates using custom package  library(ducksay)  name  <-  readline("What's your name? ")  greeting  <-  ducksay(paste("hello,",  name))  cat(greeting) 
    ```

    注意到这个程序加载了 `ducksay`。然后，代码使用这个新的库。

+   虽然这个包在我们的计算机上可以工作，因为我们是在本地开发的这个包，但其他人需要安装这个包。为此，可以使用以下命令之一：

    ```
    install.packages
    R CMD INSTALL 
    ```

    如前几节课所讨论的，顶级命令可以直接在 RStudio 中运行，并且是 R 本身构建的。另一个命令可以在计算机的终端中运行。它也是 R 中构建的。

+   要安装我们的包，我们可以在控制台中运行以下命令：`install.packages("ducksay_1.0.tar.gz")`

+   你可以使用 CRAN、GitHub 甚至电子邮件来共享你的代码。

## 总结

在本课中，你学习了如何在 R 中打包你的程序。具体来说，你学习了以下内容：

+   包

+   包结构

+   devtools

+   编写测试

+   编写 R 代码

+   `NAMESPACE`

+   测试代码

+   编写文档

+   打包包

+   更新包

+   使用和共享包

在本课程中，你学习了关于 R 和 R 编程的许多知识。你学习了如何表示数据、转换数据、应用函数、整理数据、可视化数据、测试程序和打包程序。总的来说，我们希望这些材料对你有所帮助。我们也希望你能将所学应用于世界上的伟大事业。

这就是 CS50 的 R 编程入门。
