# Python和Java编程入门1-2：34：直方图编码演示-设置Pyplot选项 📊

![](img/44e83494faed04c25a21c58cdc45afd7_0.png)

![](img/44e83494faed04c25a21c58cdc45afd7_2.png)

在本节课中，我们将学习如何使用Matplotlib的Pyplot库创建和自定义直方图。我们将通过一个具体的例子，为两个不同城市（匹兹堡和拉斯维加斯）的餐厅星级评分数据绘制直方图，并学习如何设置透明度、颜色、标签等选项，使图表更具可读性和表现力。

---

![](img/44e83494faed04c25a21c58cdc45afd7_4.png)

上一节我们介绍了数据可视化的基本概念，本节中我们来看看如何使用Pyplot库的具体函数来绘制直方图。

![](img/44e83494faed04c25a21c58cdc45afd7_6.png)

首先，我们需要为匹兹堡的星级评分数据创建一个直方图。Pyplot库在创建可视化图表时提供了多种配置选项，我们将使用其中一些基础的选项。

![](img/44e83494faed04c25a21c58cdc45afd7_7.png)

![](img/44e83494faed04c25a21c58cdc45afd7_8.png)

以下是使用Pyplot库绘制直方图的基本代码结构：

![](img/44e83494faed04c25a21c58cdc45afd7_10.png)

```python
plt.hist(data, alpha=0.3, color='yellow', label='Pittsburgh', bins='auto')
```

![](img/44e83494faed04c25a21c58cdc45afd7_12.png)

让我们详细解析这段代码中的参数：
*   **`data`**：这是要绘制直方图的数据集，在本例中是匹兹堡的星级评分数据 `pit_stars`。
*   **`alpha=0.3`**：这个参数设置直方图中柱子的透明度。值在0（完全透明）到1（完全不透明）之间，`0.3`表示70%的透明度。
*   **`color='yellow'`**：这个参数设置直方图中柱子的填充颜色。
*   **`label='Pittsburgh'`**：这个参数为这个直方图数据系列设置一个标签，该标签将用于图例。
*   **`bins='auto'`**：这个参数设置X轴的分箱（即分组）规则。`‘auto’` 表示让库自动决定最合适的分箱数量和宽度。

![](img/44e83494faed04c25a21c58cdc45afd7_14.png)

![](img/44e83494faed04c25a21c58cdc45afd7_16.png)

---

现在，让我们在同一个图表上添加拉斯维加斯的星级评分数据。这将把拉斯维加斯的数据与匹兹堡的数据叠加显示，便于对比。

![](img/44e83494faed04c25a21c58cdc45afd7_18.png)

![](img/44e83494faed04c25a21c58cdc45afd7_19.png)

![](img/44e83494faed04c25a21c58cdc45afd7_21.png)

以下是添加第二个直方图的代码：

```python
plt.hist(data, alpha=0.3, color='red', label='Las Vegas', bins='auto')
```

![](img/44e83494faed04c25a21c58cdc45afd7_23.png)

![](img/44e83494faed04c25a21c58cdc45afd7_25.png)

在这段代码中，我们使用了相同的 `alpha` 和 `bins` 参数以保证样式一致，但将数据源更改为拉斯维加斯的评分数据 `vegas_stars`，颜色改为红色，标签改为“Las Vegas”。

---

![](img/44e83494faed04c25a21c58cdc45afd7_27.png)

![](img/44e83494faed04c25a21c58cdc45afd7_28.png)

本节课中我们一起学习了如何使用Matplotlib的Pyplot库绘制叠加直方图。我们掌握了 `plt.hist()` 函数的关键参数，包括如何指定数据源、设置柱子的透明度和颜色、添加数据标签以及控制分箱方式。通过将两个城市的数据绘制在同一张图上，我们可以直观地比较它们的星级评分分布。