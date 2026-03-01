# Python数据可视化：第37章：散点图编码演示 - 比较不同维度的数据点

在本节课中，我们将学习如何使用Python的Pandas和Matplotlib库，通过散点图来可视化并比较不同类别业务的数据。具体来说，我们将分析三个不同行业（医疗健康、快餐、早餐与早午餐）的商家，比较它们的评论数量和星级评分。

我们将使用散点图来展示这些数据，因为散点图非常适合用于观察两个连续变量之间的关系，并能通过颜色或标记区分不同的数据组。

## 数据准备与类别筛选

首先，我们需要从数据集中筛选出三个特定类别的业务数据。假设我们有一个包含所有业务信息的数据框，我们需要为每个感兴趣的类别创建单独的数据子集。

以下是创建这些新数据框的步骤：

![](img/d1a9ae20927ea319ab1a6817513c611d_0.png)

1.  确定原始数据框中用于标识业务类别的列名（例如 `'category'`）。
2.  使用条件筛选，为“医疗健康”、“快餐”以及“早餐与早午餐”这三个类别分别创建新的数据框。

对应的Python代码可能如下所示：
```python
import pandas as pd

# 假设 df 是包含所有业务数据的原始DataFrame
# 筛选医疗健康类别的业务
health_df = df[df['category'] == 'Health and Medical']
# 筛选快餐类别的业务
fastfood_df = df[df['category'] == 'Fast Food']
# 筛选早餐与早午餐类别的业务
breakfast_df = df[df['category'] == 'Breakfast and Brunch']
```
通过以上代码，我们得到了三个独立的数据框，每个都只包含对应类别的商家数据，为后续的可视化做好了准备。

## 创建与定制散点图

在分离出所需类别的数据后，下一步是使用Matplotlib创建散点图。我们将把“评论数量”放在X轴，把“星级评分”放在Y轴，并用不同的颜色或标记来区分三个类别。

以下是绘制散点图的关键步骤：

*   **初始化图表**：使用 `plt.figure()` 创建一个新的图形窗口，并可使用 `figsize` 参数设置其大小。
*   **绘制散点**：对每个类别的数据框，分别调用 `plt.scatter()` 函数。我们需要指定X轴数据（评论数量）、Y轴数据（星级评分）、以及用于区分类别的颜色（`color`）或标记样式（`marker`）。
*   **添加图例**：为每个 `plt.scatter()` 调用设置一个 `label` 参数，然后使用 `plt.legend()` 来显示图例，以便读者能分辨哪个点集代表哪个类别。
*   **添加标签与标题**：使用 `plt.xlabel()`, `plt.ylabel()` 和 `plt.title()` 为图表添加清晰的轴标签和标题。
*   **显示图表**：最后，使用 `plt.show()` 将绘制好的图表展示出来。

一个基础的绘图代码结构如下：
```python
import matplotlib.pyplot as plt

plt.figure(figsize=(10, 6))

plt.scatter(health_df['review_count'], health_df['stars'], color='blue', label='Health and Medical', alpha=0.6)
plt.scatter(fastfood_df['review_count'], fastfood_df['stars'], color='red', label='Fast Food', alpha=0.6)
plt.scatter(breakfast_df['review_count'], breakfast_df['stars'], color='green', label='Breakfast and Brunch', alpha=0.6)

plt.xlabel('Review Count')
plt.ylabel('Star Rating')
plt.title('Business Review Count vs. Star Rating by Category')
plt.legend()
plt.grid(True, linestyle='--', alpha=0.5)
plt.show()
```
在这段代码中，`alpha` 参数用于设置点的透明度，有助于在点重叠时更好地观察分布密度；`grid` 函数则添加了网格线，使读数更加方便。

## 图表解读与分析

绘制出散点图后，我们可以直观地进行比较分析。观察图表时，可以关注以下几个方面：

![](img/d1a9ae20927ea319ab1a6817513c611d_2.png)

*   **整体分布**：观察点主要集中在哪个评论数量和星级评分区间。例如，是否大部分商家的评论数都少于500条？
*   **类别间差异**：比较不同颜色的点群。快餐店的评分是否普遍集中在某个范围？早餐店的评论数量是更多还是更少？
*   **相关性趋势**：是否存在某种趋势？例如，评论数量越多的商家，其星级评分是倾向于更高还是更低？这种趋势在不同类别间是否一致？
*   **异常点**：注意那些远离主要点群的孤立点。这些可能是评论数极高但评分很低，或评分极高但评论数很少的特殊商家。

通过这样的可视化分析，我们能够快速获得对数据集的直观理解，并发现潜在的模式或问题，这比单纯查看数字表格要有效得多。

本节课中，我们一起学习了如何使用Pandas进行数据筛选，以及如何利用Matplotlib绘制多系列散点图来比较不同维度（此处为不同业务类别）的数据点。散点图是探索两个变量间关系的强大工具，结合颜色区分，可以高效地在单一图表中呈现多组数据的对比情况。掌握这一技能，将有助于你在数据分析项目中更深入地挖掘数据洞察。