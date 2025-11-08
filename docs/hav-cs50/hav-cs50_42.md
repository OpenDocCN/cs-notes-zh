# 第 4 讲

> 原文：[`cs50.harvard.edu/r/notes/4/`](https://cs50.harvard.edu/r/notes/4/)

+   欢迎回来！

+   dplyr

    +   `select`（#select）

    +   `filter`（#filter）

    +   管道操作符

    +   `arrange`（#arrange）

    +   `distinct`（#distinct）

    +   写入数据

    +   `group_by`（#group_by）

    +   `summarize`（#summarize）

    +   `ungroup`（#ungroup）

+   tidyr

    +   整洁数据

    +   标准化

    +   旋转

+   stringr

+   总结

## 欢迎回来！

+   欢迎回到 CS50 的 R 编程入门课程！

+   今天，我们将学习如何整理数据。确实，你可以想象出很多次，表格和数据可能不会是人们希望的样子！

+   *包* 是开发者创建的代码片段，我们可以将其安装并加载到我们的 R 程序中。这些包可以在 R 中提供一些原生不包含的功能。

+   包存储在 R 的 *library* 中。因此，你可以使用 `library` 函数来加载包。

## dplyr

+   [dplyr](https://dplyr.tidyverse.org/) 是 [tidyverse](https://www.tidyverse.org/) 中的一个包，它包含用于操作数据的函数。

+   在 dplyr 中，包含了一个名为 `storms` 的数据集，它包含了来自美国国家海洋和大气管理局 [NOAA](https://www.noaa.gov/) 的风暴数据观测。

+   在加载 dplyr 或 tidyverse 之后，只需在 R 控制台中输入 `storms` 即可加载 `storms` 数据集。

+   当你输入 `storms` 时，注意会显示一个 *tibble*。*tibble* 是 tidyverse 对 R 的数据框的“重新构想”。注意行、行号和各种列是如何包含并标记的。此外，注意 *tibble* 中使用的文本颜色。

### `select`

+   让我们定位数据集中最强的风暴。首先，让我们删除我们不需要的列。考虑以下程序：

    [PRE0]

    注意到 dplyr 中的 `select` 函数允许你确定哪些列将包含在数据框或 tibble 中。`select` 的第一个参数是要操作的（数据框或 tibble）：`storms`。`select` 的第二个参数是要选择的列的向量。然而，在这种情况下，使用了 `!`：一个 `!` 表示后面的列名将被排除。或者，`-` 也有相同的功能。运行此代码将通过删除上述列来简化 tibble。

+   打印出所有这些列有点繁琐！

+   像这样的辅助函数 `contains`、`starts_with` 或 `ends_with` 可以帮助完成这项工作。考虑以下代码：

    [PRE1]

    注意到 `ends_with` 被用来排除所有以 *diameter* 结尾的列。使用的代码更少，但结果与之前相同。

### `filter`

+   另一个有用的函数是 `filter`，它可以用来从数据框中筛选行。

+   考虑以下代码：

    [PRE2]

    注意，只有包含 `status` 列中 `hurricane` 的行被包含在内。

+   注意最新的示例在第一个示例中已经删除了 `dplyr::` 语法。结果是，你不需要命名定义函数的特定包，除非两个或多个包定义了具有相同名称的函数。在这种情况下，你需要通过指定想要使用哪个包的函数来消除歧义。

### 管道操作符

+   在 R 中，*管道操作符* 用 `|>` 表示，允许将数据“管道”到特定的函数中。例如，考虑以下代码：

    [PRE3]

    注意 `storms` 是如何被管道到 `select` 的，隐式地成为 `select` 的第一个参数。然后，注意 `select` 的返回值是如何被管道到 `filter` 的，隐式地成为 `filter` 的第一个参数。当你使用管道操作符时，你可以避免嵌套函数调用，并按顺序编写代码。

### `arrange`

+   现在我们使用 `arrange` 函数来排序我们的行：

    [PRE4]

    注意 `select` 函数的返回值是如何被管道到 `filter` 的，然后 `filter` 的返回值又被管道到 `arrange`。结果数据框中的行按 `wind` 列的值降序排列。

### `distinct`

+   你可能会注意到这个 tibble 包含许多相同风暴的行。因为这个数据包含许多相同风暴的观测，所以这并不奇怪。然而，不是很好奇能够找到只有 *distinct* 飓风吗？

+   `distinct` 函数允许我们在 tibble 中获取独特的项目。

+   Distinct returns distinct rows, finding duplicate rows and returning the first row from the set of duplicates.

+   默认情况下，`distinct` 只在行的所有值与另一行的所有值完全匹配时才将行视为重复。

+   然而，你可以告诉 `distinct` 在确定行是否重复时考虑哪些值。考虑以下利用这一功能的代码：

    [PRE5]

    注意 `distinct` 被告知只查看每个风暴的 `name` 和 `year` 以确定它是否是独特项目。`.keep_all = TRUE` 告诉 `distinct` 仍然返回每行的所有列。

### 写入数据

+   我们可以将数据保存到 CSV 文件中以便以后使用。

+   考虑以下代码：

    [PRE6]

    注意第一个代码块的结果被存储为 `hurricanes`。要将 `hurricanes` 保存为 CSV 文件，`select` 首先选择 3 个特定的列（`year`、`name` 和 `wind`），并将它们写入名为 `hurricanes.csv` 的文件中。

### `group_by`

+   现在我们来找出每年最强大的飓风。

+   考虑以下代码：

    [PRE7]

    注意如何将 `hurricanes.csv` 读取到 `hurricanes` 中。然后，使用 `group_by` 函数将每年所有的飓风分组在一起。对于每个组，使用 `arrange(desc(wind))` 按照风速降序排列。最后，使用 `slice_head` 输出每个组的顶部行。因此，展示了每年最强的风暴。

+   `slice_max` 在变量中选择最大值。考虑一下我们如何在代码中应用这一点：

    [PRE8]

    注意到`hurricanes`是按`year`分组的。然后，使用`slice_max`展示了`wind`的最高值。这样做消除了对`arrange(desc(wind))`的需求。

### `summarize`

+   如果我们想知道每年有多少次飓风？考虑以下代码：

    [PRE9]

    注意到函数`summarize`使用`n`来计算每个组中的行数。

### `ungroup`

+   查看我们的`hurricanes`数据框，你会注意到存在分组。实际上，这些分组是根据`year`进行的。在未来的活动中，你可能会希望取消数据中的分组。因此，考虑以下内容：

    [PRE10]

    注意到`ungroup`命令被用来移除 tibble 的分组。

## tidyr

+   当数据已经很好地组织时，dplyr 非常有用。

+   对于数据尚未很好地组织的情况，又该如何处理？

+   对于这一点，tidyr 包可能很有用！

### 整洁数据

+   根据 tidyverse 的哲学，有三个原则指导我们所说的*整洁数据*。

    [PRE11]

+   在评估数据时，最好查看上述三个原则，看看它们是否被观察到。

### 正常化

+   *正常化*是将数据转换为满足上述原则的过程。

+   正常化也可以指将数据转换为满足上述指南之外更好的设计原则。

+   从课程文件中下载`students.csv`文件并将其放置在你的工作目录中。创建以下新代码：

    [PRE12]

    注意到这段代码加载了一个名为`students.csv`的 CSV 文件，并将这些值存储在`students`中。

+   检查这些数据，你可能看到它们并没有遵循我们之前提到的原则。哪些原则没有被遵循？

### 旋转

+   在`students`数据集中，你可能会注意到有一些行值本应该是列名：“major”和“GPA”。为了清楚起见，这个数据集违反了整洁数据的第二个原则：学生的任何变化方式*都不是*一列。

+   我们可以通过`pivot_wider`将数据集旋转，将这些变量转换为列。`pivot_wider`将一个“更长”的数据集（即具有变量作为行值的数据集）转换为“更宽”的数据集（即将这些变量转换为列）。

+   `pivot_wider`会将`students`数据集从以下内容转换：

    ![转换前的`students`](img/b2abe2d0d26093da0fd1d68a9802293f.png)

    转换为以下内容：

    ![转换后的`students`](img/7ba32632526b205660d8d18e34b724bf.png)

+   但如何操作呢？考虑以下用法：

    [PRE13]

    注意到`pivot_wider`有几个参数，这里进行解释：

    +   第一是要操作的数据集，`students`。

    +   第二个参数，`id_cols`，指定了在转换后的数据集中哪一列应该是唯一的。注意，在`pivot_wider`的转换之前，`student`列中存在重复值。在`pivot_wider`的转换之后，`student`列中存在唯一值。

    +   第三个参数，`names_from`，指定了包含应作为变量（列）的值的列。注意`pivot_wider`转换后，`attribute`列中的值是如何变成列的。

    +   最后，第四个参数，`values_from`，指定了填充新列值的列。

+   由于我们的数据如此整洁，我们可以用数据做更多的事情！

+   考虑以下：

    [PRE14]

    注意这个程序是如何利用`pivot_wider`和 tidyr 来发现学生的平均 GPA。`students`中的`GPA`被转换为数值。然后，使用管道语法来找到 GPA 的平均值。

## stringr

+   我们上面描述的过程在数值本身干净的情况下效果很好。然而，当数值本身不整洁时怎么办呢？

+   `stringr`为我们提供了一种整理字符串的方法。从课程文件中下载`shows.csv`并将其放置在你的工作目录中。考虑以下程序：

    [PRE15]

    注意到节目是如何按`show`分组。然后，计算`votes`的数量。最后，按降序排列`votes`。

+   观察这个程序的结果，你可以看到有多个版本的*《阿凡达：最后的气宗》*。我们可能首先应该解决空白问题。

    [PRE16]

    注意`str_trim`是如何用来移除每条记录的前后空白。然后，`str_squish`用来移除字符之间的额外空白。

+   虽然这一切都非常好，但在大写方面仍然存在一些不一致。我们可以这样解决：

    [PRE17]

    注意`str_to_title`是如何用来强制每个字符串使用标题大小写的。

+   最后，我们可以解决*《阿凡达：最后的气宗》*的拼写变体问题：

    [PRE18]

    注意`str_detect`是如何用来定位`Avatar`实例。每个这些都被转换为`Avatar: The Last Airbender`。

+   虽然这些工具非常有帮助，但考虑你可能需要谨慎行事，不要覆盖正确的条目。例如，有许多名为*《阿凡达》*的电影！我们如何知道投票者不是有意为这些电影投票？

## 总结

在本课中，你学习了如何在 R 中整理数据。具体来说，你学习了三个新的包，它们都是 tidyverse 的一部分：

+   dplyr

+   tidyr

+   stringr

次次见，届时我们将讨论如何可视化我们的数据。
