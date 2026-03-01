# 141：直方图编码演示-显示可视化 📊

![](img/2ae307c2302d8b8fa585d373012b32af_0.png)

在本节课中，我们将学习如何使用Python的Matplotlib库创建和美化直方图，以可视化并比较两个不同数据集（匹兹堡和拉斯维加斯的评分数据）的分布情况。我们将从创建一个简单的重叠直方图开始，然后逐步添加标签、图例和标题，最后学习如何创建并排显示的直方图。

---

![](img/2ae307c2302d8b8fa585d373012b32af_2.png)

## 创建基础重叠直方图

![](img/2ae307c2302d8b8fa585d373012b32af_3.png)

首先，我们将在同一个图表中绘制两个直方图，以展示数据的分布。我们将使用 `plt.show()` 方法来显示图表。

![](img/2ae307c2302d8b8fa585d373012b32af_5.png)

以下是创建基础可视化图表的代码：

```python
plt.show()
```

运行上述代码后，我们将看到一个简单的可视化图表。其中，黄色条形代表匹兹堡的数据，红色（或叠加后呈现的橙色）条形代表拉斯维加斯的数据。

![](img/2ae307c2302d8b8fa585d373012b32af_7.png)

---

![](img/2ae307c2302d8b8fa585d373012b32af_9.png)

## 添加图表标签与美化

上一节我们创建了基础图表，本节中我们来看看如何通过添加坐标轴标签、图例和标题来美化它，使图表信息更清晰。

![](img/2ae307c2302d8b8fa585d373012b32af_11.png)

![](img/2ae307c2302d8b8fa585d373012b32af_12.png)

我们将更新代码，添加以下元素：
*   X轴和Y轴的标签。
*   图例，让Matplotlib自动选择最佳位置。
*   一个描述性的标题。

以下是更新后的代码：

![](img/2ae307c2302d8b8fa585d373012b32af_14.png)

![](img/2ae307c2302d8b8fa585d373012b32af_15.png)

```python
plt.xlabel('rating')
plt.ylabel('Number of rating scores')
plt.legend(loc='best')
plt.title('Review Distribution Of Pittsburgh And Las Vegas')
plt.show()
```

![](img/2ae307c2302d8b8fa585d373012b32af_17.png)

运行更新后的代码，我们将看到美化后的可视化图表。黄色条形代表匹兹堡，红色条形代表拉斯维加斯，橙色部分则表示两个数据集重叠的区域。

![](img/2ae307c2302d8b8fa585d373012b32af_19.png)

---

![](img/2ae307c2302d8b8fa585d373012b32af_21.png)

## 创建并排显示的直方图

![](img/2ae307c2302d8b8fa585d373012b32af_23.png)

虽然重叠直方图可以展示数据重叠，但有时并排显示能让对比更清晰。接下来，我们将学习如何创建一个并排显示的直方图。

![](img/2ae307c2302d8b8fa585d373012b32af_25.png)

这次，我们将使用一个 `hist` 函数调用，但传入一个数据列表。以下是实现并排直方图的步骤和代码：

![](img/2ae307c2302d8b8fa585d373012b32af_27.png)

1.  调用 `plt.hist()` 函数。
2.  传入一个包含两个数据序列的列表：`[pit_stars, vegas_stars]`。
3.  设置透明度 `alpha=0.7`。
4.  指定颜色列表 `color=['red', 'blue']`，分别对应匹兹堡和拉斯维加斯。
5.  设置标签列表 `label=['Pittsburgh', 'Las Vegas']`。
6.  将 `bins` 参数设置为 `‘auto’`，让库自动决定分组数量。

以下是完整的代码示例：

```python
plt.hist([pit_stars, vegas_stars], alpha=0.7, color=['red', 'blue'], label=['Pittsburgh', 'Las Vegas'], bins='auto')
plt.xlabel('rating')
plt.ylabel('Number of rating scores')
plt.legend(loc='best')
plt.title('Review Distribution of Pittsburgh and Las Vegas')
plt.show()
```

![](img/2ae307c2302d8b8fa585d373012b32af_29.png)

运行这段代码，我们将得到最终的并排直方图。红色条形代表匹兹堡，蓝色条形代表拉斯维加斯。X轴表示平均评分，Y轴表示每个评分出现的次数。

![](img/2ae307c2302d8b8fa585d373012b32af_31.png)

---

## 总结

![](img/2ae307c2302d8b8fa585d373012b32af_33.png)

![](img/2ae307c2302d8b8fa585d373012b32af_34.png)

本节课中我们一起学习了使用Matplotlib创建直方图进行数据可视化的完整流程。我们从绘制基础的重叠直方图开始，然后学习了如何添加坐标轴标签、图例和标题来增强图表的可读性。最后，我们掌握了创建并排直方图的方法，以便更清晰地对两个数据集进行比较。这些技能是进行数据探索和结果展示的基础。