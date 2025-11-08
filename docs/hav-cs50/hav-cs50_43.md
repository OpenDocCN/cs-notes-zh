# 第五讲

> 原文：[`cs50.harvard.edu/r/notes/5/`](https://cs50.harvard.edu/r/notes/5/)

+   欢迎！

+   ggplot2

+   规模

+   标签

+   填充

+   主题

+   保存你的图表

+   点

+   随时间可视化

+   总结

## 欢迎！

+   欢迎回到 CS50 的 R 编程入门课程！

+   今天，我们将学习如何可视化数据。一个好的可视化可以帮助我们以全新的方式解释和理解数据。

## ggplot2

+   `ggplot` 中的 `plot` 意味着我们将要 *绘制* 我们的数据。

+   `ggplot` 中的 `gg` 指的是一种 *图形语法*，其中图形的各个组件可以组合在一起来可视化数据。

+   组成图形语法有很多组件，首先是 *数据*。

+   另一个组件是 *几何形状*。这些是图表的各种图形表示选项。这包括柱状图、点和线条。

+   最后，*美学映射* 是数据与我们的图表视觉特征之间的关系。例如，在一个图表中，一个水平的 `x` 轴可能代表每个候选人。然后，一个垂直的 `y` 轴可能与每个候选人的投票数相关联。正是通过数据与几何形状之间的这种关系，我们能够可视化和理解图表的美学映射。你可能想象过在某个时候，展示给你的是设计不佳的图表：当映射不正确时，数据更难以解释和理解。

+   下载讲座的源文件，并在 R 控制台中运行 `library("tidyverse")`，以便将 `tidyverse` 载入内存。然后，创建以下可视化：

    ```
    # Create a blank visualization  votes  <-  read.csv("votes.csv")  ggplot() 
    ```

    注意到 `votes.csv` 被加载到 `votes` 中。当运行 `ggplot` 时，目前还没有任何可视化。

+   我们可以这样向 `ggplot` 提供输入：

    ```
    # Supply data  votes  <-  read.csv("votes.csv")  ggplot(votes) 
    ```

    注意到 `votes` 被提供给 `ggplot`，但仍然没有可视化。

+   我们需要告诉 `ggplot` 我们想要什么类型的图表：

    ```
    # Add first geometry  votes  <-  read.csv("votes.csv")  ggplot(votes)  +  geom_col() 
    ```

    注意到 `geom_col` 指定数据应该使用柱状几何形状进行可视化。然而，在这个阶段，将会出现错误。错误表明我们需要指定美学映射。

+   注意，`+` 操作符也有新的含义：使用 `+` 操作符在图表的基础层上添加一个图层。

+   要指定美学映射，我们可以如下定义：

    ```
    # Add x and y aesthetics  votes  <-  read.csv("votes.csv")  ggplot(votes,  aes(x  =  candidate,  y  =  votes))  +  geom_col() 
    ```

    注意到各种由 `aes` 指定的美学映射是如何在括号内定义的。例如，`x = candidate` 和 `y = votes` 都是美学映射。现在，`ggplot` 知道哪些数据映射到我们图表的哪些美学特征。

+   运行上述代码，我们的第一个可视化终于出现了！

## 规模

+   注意到 `ggplot` 决定 `votes` 轴的值范围从 `0` 到 `200`。如果我们想提供更多的空间，以便我们可以可视化到 `250`，该怎么办？让我们来学习一下 **规模**。

+   刻度可以是 *连续的*，范围从一个数字到另一个数字，或者 *离散的*，这意味着分类。

+   连续刻度有 *限制*。例如，`votes` 中提供的数据范围从 `0` 到 `200`。因此，我们可以按如下方式修改这些限制：

    ```
    # Adjust y scale  votes  <-  read.csv("votes.csv")  ggplot(votes,  aes(x  =  candidate,  y  =  votes))  +  geom_col()  +  scale_y_continuous(limits  =  c(0,  250)) 
    ```

    注意 `y` 的刻度是如何通过 `scale_y_continuous` 修改为从 `0` 到 `250` 的。这同样是通过带有 `+` 操作符的新层提供的。

## 标签

+   此外，还可以向图表添加标签。考虑以下示例：

    ```
    # Add labels  votes  <-  read.csv("votes.csv")  ggplot(votes,  aes(x  =  candidate,  y  =  votes))  +  geom_col()  +  scale_y_continuous(limits  =  c(0,  250))  +  labs(  x  =  "Candidate",  y  =  "Votes",  title  =  "Election Results"  ) 
    ```

    注意 `x`、`y` 和 `title` 提供了标签。这些是通过 `+` 操作符添加的新层。

## 填充

+   填充颜色也可以根据 `候选人` 名称进行更改。考虑以下示例：

    ```
    # Add fill aesthetic mapping for geom_col  votes  <-  read.csv("votes.csv")  ggplot(votes,  aes(x  =  candidate,  y  =  votes))  +  geom_col(aes(fill  =  candidate))  +  scale_y_continuous(limits  =  c(0,  250))  +  labs(  x  =  "Candidate",  y  =  "Votes",  title  =  "Election Results"  ) 
    ```

    注意 `fill` 是通过 `aes` 函数依赖于 `candidate` 的。

+   我们可能希望调整 `fill` 颜色以适应色盲。我们可以这样做：

    ```
    # Use viridis scale to design for color blindness  votes  <-  read.csv("votes.csv")  ggplot(votes,  aes(x  =  candidate,  y  =  votes))  +  geom_col(aes(fill  =  candidate))  +  scale_fill_viridis_d("Candidate")  +  scale_y_continuous(limits  =  c(0,  250))  +  labs(  x  =  "Candidate",  y  =  "Votes",  title  =  "Election Results"  ) 
    ```

    注意 `viridis` 规模是通过 `scale_fill_viridis_d` 函数提供的。

## 主题

+   也可以修改 `ggplot` 使用的主题。你可以这样做：

    ```
    # Adjust ggplot theme  votes  <-  read.csv("votes.csv")  ggplot(votes,  aes(x  =  candidate,  y  =  votes))  +  geom_col(aes(fill  =  candidate))  +  scale_fill_viridis_d("Candidate")  +  scale_y_continuous(limits  =  c(0,  250))  +  labs(  x  =  "Candidate",  y  =  "Votes",  title  =  "Election Results"  )  +  theme_classic() 
    ```

    注意 `theme_classic` 被提供。ggplot2 [提供几个主题](https://ggplot2.tidyverse.org/reference/ggtheme.html)。

## 保存您的图表

+   最后，可以保存图表。

    ```
    # Save file  votes  <-  read.csv("votes.csv")  p  <-  ggplot(votes,  aes(x  =  candidate,  y  =  votes))  +  geom_col(aes(fill  =  candidate))  +  scale_fill_viridis_d("Candidate")  +  scale_y_continuous(limits  =  c(0,  250))  +  labs(  x  =  "Candidate",  y  =  "Votes",  title  =  "Election Results"  )  +  theme_classic()  ggsave(  "votes.png",  plot  =  p,  width  =  1200,  height  =  900,  units  =  "px"  ) 
    ```

    注意整个图表被指定为 `p`。然后，使用 `ggsave`，指定文件名、图表（在这种情况下，`p`）、高度、宽度和单位。

+   通过执行此代码，你已经保存了你的第一个图表。恭喜！

## 点

+   现在，让我们看看一种名为 `点` 的新几何类型。

+   想象一下，糖果的价格百分位数和糖的百分位数是如何表示的。

+   你可以想象 `sugar` 百分位数可以映射到 `y` 轴，而 `price` 百分位数可以标注在 `x` 轴上。

+   这可以通过以下代码形式实现：

    ```
    # Introduce geom_point  load("candy.RData")  ggplot(  candy,  aes(x  =  price_percentile,  y  =  sugar_percentile)  )  +  geom_point() 
    ```

    注意数据 `candy` 是如何提供给 `ggplot` 函数的。然后，使用 `aes` 函数设置美学映射。例如，`price_percentile` 被分配给 `x` 轴。最后，运行 `geom_point` 函数。

+   运行此代码会在图表中表示点。

+   标签可以按如下方式添加：

    ```
    # Add labels and theme  load("candy.RData")  ggplot(  candy,  aes(x  =  price_percentile,  y  =  sugar_percentile)  )  +  geom_point()  +  labs(  x  =  "Price",  y  =  "Sugar",  title  =  "Price and Sugar"  )  +  theme_classic() 
    ```

    注意 `x`、`y` 和 `title` 的 `labs`（标签）是如何提供的。还有一个主题被命名。

+   现在，许多点重叠。可以使用 `jitter` 来帮助可视化重叠的点：

    ```
    # Introduce geom_jitter  ggplot(  candy,  aes(x  =  price_percentile,  y  =  sugar_percentile)  )  +  geom_jitter()  +  labs(  x  =  "Price",  y  =  "Sugar",  title  =  "Price and Sugar"  )  +  theme_classic() 
    ```

    注意 `geom_point` 是如何被 `geom_jitter` 替换的。这允许可视化重叠的点。

+   我们可以向我们的点添加颜色美学：

    ```
    # Introduce size and color aesthetic  ggplot(  candy,  aes(x  =  price_percentile,  y  =  sugar_percentile)  )  +  geom_jitter(  color  =  "darkorchid",  size  =  2  )  +  labs(  x  =  "Price",  y  =  "Sugar",  title  =  "Price and Sugar"  )  +  theme_classic() 
    ```

    注意所有点都被改变为一种颜色。

+   此外，我们还可以更改我们点的尺寸和形状：

    ```
    # Introduce point shape and fill color  ggplot(  candy,  aes(x  =  price_percentile,  y  =  sugar_percentile)  )  +  geom_jitter(  color  =  "darkorchid",  fill  =  "orchid",  shape  =  21,  size  =  2  )  +  labs(  x  =  "Price",  y  =  "Sugar",  title  =  "Price and Sugar"  )  +  theme_classic() 
    ```

    注意 `shape` 和 `size` 是如何改变的。你可以参考 [文档](https://ggplot2.tidyverse.org/articles/ggplot2-specs.html#sec:shape-spec) 来了解哪些数字对应哪些形状。

## 随时间可视化

+   你可以想象数据是如何随时间表示的。

+   例如，考虑如何表示飓风安妮塔的数据随时间的变化。

+   我们可以像以前一样用点来绘制：

    ```
    # Visualize with geom_point  load("anita.RData")  ggplot(anita,  aes(x  =  timestamp,  y  =  wind))  +  geom_point() 
    ```

    注意 `timestamp` 和风速是如何随时间放置在点上的。

+   虽然这种可视化很有用，但通过显示风速是否增加或减少的线条来展示可能会更有用。每个点都可以通过以下方式用线条连接：

    ```
    # Introduce geom_line  load("anita.RData")  ggplot(anita,  aes(x  =  timestamp,  y  =  wind))  +  geom_line() 
    ```

    注意 `geom_line` 被用作一个新图层。

+   结果是一系列在每次时间戳处改变方向的线条。如果我们能结合 `point` 和 `line` 会怎样？嗯，确实可以！

    ```
    # Combine geom_line and geom_point  load("anita.RData")  ggplot(anita,  aes(x  =  timestamp,  y  =  wind))  +  geom_line()  +  geom_point(color  =  "deepskyblue4") 
    ```

    注意如何通过 `geom_line` 添加带有线条的图层。然后，使用 `deepskyblue4` 添加 `geom_point` 作为图层。

+   美学可以通过多种方式修改：

    ```
    # Experiment with geom_line and geom_point aesthetics  load("anita.RData")  ggplot(anita,  aes(x  =  timestamp,  y  =  wind))  +  geom_line(  linetype  =  1,  linewidth  =  0.5  )  +  geom_point(  color  =  "deepskyblue4",  size  =  2  ) 
    ```

    注意如何修改 `linetype` 和 `linewidth`。然后，改变点的 `size`。你可以参考 [文档](https://ggplot2.tidyverse.org/reference/aes_linetype_size_shape.html#linetype) 了解更多关于各种线型的信息。

+   就像我们今天之前的图表一样，我们可以添加标签和主题：

    ```
    # Add labels and adjust theme  load("anita.RData")  ggplot(anita,  aes(x  =  timestamp,  y  =  wind))  +  geom_line(  linetype  =  1,  linewidth  =  0.5  )  +  geom_point(  color  =  "deepskyblue4",  size  =  2  )  +  labs(  y  =  "Wind Speed (Knots)",  x  =  "Date",  title  =  "Hurricane Anita"  )  +  theme_classic() 
    ```

    注意 `labs` 如何允许我们为 `y`、`x` 和标题指定标签。然后，启用 `theme_classic`。

+   作为最后的点缀，我们还可以添加一条水平线来划分飓风状态。飓风安妮塔何时成为飓风？

    ```
    # Add horizontal line to demarcate hurricane status  load("anita.RData")  ggplot(anita,  aes(x  =  timestamp,  y  =  wind))  +  geom_line(  linetype  =  1,  linewidth  =  0.5  )  +  geom_point(  color  =  "deepskyblue4",  size  =  2  )  +  geom_hline(  linetype  =  3,  yintercept  =  64  )  +  labs(  y  =  "Wind Speed (Knots)",  x  =  "Date",  title  =  "Hurricane Anita"  )  +  theme_classic() 
    ```

    注意如何添加一个新图层来显示 `yintercept = 64` 处的线条，以指定任何 64 或更高的值都被认为是飓风。`linetype` 被指定为 `3` 或点划线。

## 总结

在本课中，你学习了如何在 R 中可视化数据。具体来说，你学习了以下内容：

+   ggplot2

+   标度

+   标签

+   填充

+   主题

+   点

+   随时间可视化

欢迎下次我们讨论如何测试我们的程序。
