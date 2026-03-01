# 055：在笔记本中探索预期寿命数据 📊

![](img/a44f4455fb62ff90500f130082df26aa_0.png)

在本节课中，我们将学习如何在Google Colab笔记本中进行探索性数据分析。我们将使用一个关于全球预期寿命的数据集，通过一系列步骤来加载、查看、筛选和分析数据，以发现有趣的模式和见解。

---

## 概述

探索性数据分析是数据科学工作流程中的关键第一步。其目的是熟悉数据、检查数据质量并初步发现趋势或异常。本节我们将使用Python的Pandas库在Colab笔记本中完成这一过程。

上一节我们介绍了数据分析的环境，本节中我们来看看如何具体操作。

---

## 连接运行时与加载库

首先，我们需要在Google Colab中设置运行环境。Colab笔记本的一个优点是它提供了专业级的计算资源。

以下是连接运行时并加载必要库的步骤：

1.  点击“运行时”菜单，选择“更改运行时类型”。
2.  根据需求选择硬件加速器（如GPU、TPU）或提升内存（RAM）。
3.  连接成功后，即可运行代码单元格。

现在，我们可以加载数据分析的核心库——Pandas。

```python
import pandas as pd
```

---

## 加载与初步查看数据

数据加载是分析的基础。我们将加载一个关于全球预期寿命的数据集。

运行以下代码来加载数据并查看其前几行：

```python
# 假设数据文件名为‘life_expectancy.csv’
df = pd.read_csv('life_expectancy.csv')
df.head()
```

初步查看时，数据可能显得杂乱，包含从1960年开始的多个国家和年份。我们需要进一步深入查看其结构和列信息。

---

## 理解数据结构

为了理解我们正在处理的数据，需要查看数据的列名和整体信息。

以下是查看数据结构的步骤：

1.  使用 `df.columns` 查看所有列名。
2.  使用 `df.info()` 获取数据概览，包括行数、列数和数据类型。

查看列名后，我们可能发现数据包含“国家名称”、“国家代码”、“指标名称”、“指标代码”以及多个年份的列（如“2020”）。

---

## 筛选与排序数据

为了聚焦分析，我们通常需要筛选和排序数据。例如，我们可能只关心2020年的最新数据，并想看看预期寿命最高和最低的国家。

以下是筛选和排序2020年数据的步骤：

```python
# 选择我们关心的列：国家名称和2020年数据
df_2020 = df[['Country Name', '2020']]

# 按2020年预期寿命升序排序，并查看前25名
top_25 = df_2020.sort_values(by='2020', ascending=False).head(25)
print(top_25)
```

执行后，我们可以看到2020年预期寿命最高的25个国家和地区，例如中国香港、日本、韩国等。

---

## 计算描述性统计

描述性统计能帮助我们快速把握数据的集中趋势和分布情况。

我们可以计算数据的中位数、均值等统计量：

```python
# 计算各年份数据的中位数
median_by_year = df.iloc[:, 4:].median() # 假设从第5列开始是年份数据
print(median_by_year)
```

通过观察不同年份的中位数，我们可以发现全球预期寿命随时间推移呈现上升趋势。

如果数据中存在缺失值，我们可以使用 `df.dropna()` 将其删除。

---

## 深入分析特定维度

数据可能包含细分维度，例如区分性别。我们可以专门分析女性的预期寿命数据。

以下是分析女性预期寿命的步骤：

1.  筛选出指标名称包含“女性”的数据行。
2.  对其进行排序和描述性统计。

```python
# 假设‘Indicator Name’列中包含‘female’关键词
df_female = df[df['Indicator Name'].str.contains('female', case=False, na=False)]
top_female = df_female.sort_values(by='2020', ascending=False).head(10)
print(top_female)
print(df_female['2020'].describe())
```

分析结果显示，日本、西班牙、瑞士等国的女性预期寿命名列前茅。

---

## 案例研究：聚焦特定国家或群体

我们可以将分析聚焦于特定国家或国家集团，例如G20国家，以进行对比。

以下是分析G20国家预期寿命的步骤：

1.  定义一个G20国家列表。
2.  从数据中筛选出这些国家的数据。
3.  进行排序和比较。

```python
g20_countries = [‘Argentina‘, ‘Australia‘, ‘Brazil‘, ‘Canada‘, ‘China‘, ...] # 完整G20列表
df_g20 = df[df[‘Country Name‘].isin(g20_countries)]
df_g20_sorted = df_g20.sort_values(by=‘2020‘, ascending=False)
print(df_g20_sorted[[‘Country Name‘, ‘2020‘]])
```

通过对比可以发现，在G20国家中，美国的预期寿命排名相对靠后，接近巴西、沙特阿拉伯等国，这与其实力地位形成对比，是一个值得深入研究的现象。

---

## 寻找相似模式与可视化

我们还可以寻找与目标国家（如美国）预期寿命相似的其他国家，以提供更多背景信息。

以下是寻找相似国家的步骤：

```python
# 定义目标值（例如美国的预期寿命）
us_life_exp = df.loc[df[‘Country Name‘] == ‘United States‘, ‘2020‘].values[0]

# 计算所有国家与美国的差值，并找出差值最小的5个国家
df[‘difference‘] = abs(df[‘2020‘] - us_life_exp)
similar_countries = df.nsmallest(6, ‘difference‘) # 包含美国自己
print(similar_countries[[‘Country Name‘, ‘2020‘]])
```

最后，可视化能直观展示分析结果。我们可以使用Seaborn库绘制图表。

```python
import seaborn as sns
import matplotlib.pyplot as plt

plt.figure(figsize=(12, 8))
sns.barplot(x=‘2020‘, y=‘Country Name‘, data=top_25)
plt.title(‘Top 25 Countries by Life Expectancy (2020)‘)
plt.xlabel(‘Life Expectancy‘)
plt.show()
```

图表清晰显示，许多现代化国家的预期寿命集中在85-88岁之间，而美国则明显偏低，这突出了进一步调查的必要性。

---

## 总结

![](img/a44f4455fb62ff90500f130082df26aa_2.png)

本节课中我们一起学习了在Google Colab笔记本中进行探索性数据分析的全过程。我们从连接运行时和加载数据开始，逐步进行了数据查看、筛选排序、统计计算、维度深入分析以及最终的可视化。通过这些步骤，我们不仅熟悉了数据集，还发现了“美国预期寿命相对较低”这样一个值得深入探讨的洞察。你可以将这些技术应用于你自己的数据探索任务中。