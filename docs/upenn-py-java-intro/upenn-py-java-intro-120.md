# 120：代码练习-连接数据 📊

在本节课中，我们将要学习如何使用Pandas库来连接（或合并）多个数据表。我们将从一个包含Yelp商家数据的Excel文件开始，然后分别加载城市和州的信息工作表，最后通过“连接”操作将这些信息整合到一个统一的数据集中。

---

![](img/442bb02998a1786261ff63d4f22a0baa_1.png)

## 准备与数据加载

在开始连接数据之前，我们需要导入必要的库并加载数据。

![](img/442bb02998a1786261ff63d4f22a0baa_3.png)

![](img/442bb02998a1786261ff63d4f22a0baa_4.png)

首先，导入Pandas库，并为其设置一个简短的别名 `pd`。

```python
import pandas as pd
```

接下来，使用 `pd.ExcelFile` 方法加载包含多个工作表的Excel文件。我们将文件命名为 `Yelp.xlsx`，它位于与当前Jupyter笔记本文件相同的目录中。

```python
xls = pd.ExcelFile('Yelp.xlsx')
```

![](img/442bb02998a1786261ff63d4f22a0baa_6.png)

`xls` 变量现在是一个代表整个Excel文件的对象。要访问其中的特定工作表，我们使用 `parse` 方法。首先，我们解析名为 `Yelp data` 的工作表，并将其存储在一个名为 `df` 的DataFrame中。

```python
df = xls.parse('Yelp data')
```

为了确认数据已正确加载，我们可以使用 `head()` 方法查看前五行数据。

```python
df.head()
```

![](img/442bb02998a1786261ff63d4f22a0baa_8.png)

---

## 连接城市数据

![](img/442bb02998a1786261ff63d4f22a0baa_10.png)

上一节我们加载了主要的Yelp商家数据。本节中，我们来看看如何将城市信息连接到这个主数据集上。

首先，我们需要从同一个Excel文件中加载城市信息。使用 `parse` 方法解析名为 `cities` 的工作表，并将其存储在 `df_cities` 变量中。

```python
df_cities = xls.parse('cities')
```

同样，我们可以查看这个新DataFrame的前几行，以了解其结构。

```python
df_cities.head()
```

可以看到，`df_cities` 包含两列：`ID` 和 `city`。

现在，我们使用Pandas的 `merge` 函数来连接数据。以下是执行连接的关键参数：
*   `left`: 左侧的DataFrame（主数据集 `df`）。
*   `right`: 右侧的DataFrame（城市数据集 `df_cities`）。
*   `how`: 连接类型，这里使用 `'inner'` 表示内连接。
*   `left_on`: 左侧DataFrame中用于匹配的列名（`city ID`）。
*   `right_on`: 右侧DataFrame中用于匹配的列名（`ID`）。

```python
df = pd.merge(left=df, right=df_cities, how='inner', left_on='city ID', right_on='ID')
```

执行后，新的 `df` 包含了来自 `df_cities` 的 `city` 信息。再次使用 `df.head()` 查看，可以确认城市名称已成功添加。

![](img/442bb02998a1786261ff63d4f22a0baa_12.png)

---

## 连接州数据

我们已经成功地将城市信息合并到了数据集中。接下来，我们将以同样的方式添加州的信息。

首先，从Excel文件中加载州信息工作表。

```python
df_states = xls.parse('states')
df_states.head()
```

`df_states` 工作表包含 `ID` 和 `state` 两列。

现在，我们再次使用 `merge` 函数。这次，将主数据集 `df` 与州数据集 `df_states` 进行连接。连接键是 `df` 中的 `state ID` 列和 `df_states` 中的 `ID` 列。

```python
df = pd.merge(left=df, right=df_states, how='inner', left_on='state ID', right_on='ID')
```

连接完成后，我们可以检查数据形状，确认列数增加了。

![](img/442bb02998a1786261ff63d4f22a0baa_14.png)

```python
df.shape
```

![](img/442bb02998a1786261ff63d4f22a0baa_15.png)

使用 `df.head()` 查看数据，可以看到 `state` 列也已成功添加。

---

![](img/442bb02998a1786261ff63d4f22a0baa_17.png)

## 查看与清理数据

现在，我们已经拥有了一个包含商家名称、城市和州信息的完整数据集。让我们来查看一下具体内容，并做一些清理工作。

首先，创建一个我们感兴趣的列名列表，然后使用这个列表从DataFrame中选取数据。

```python
atts = ['name', 'city', 'state']
df[atts].head(100)
```

这段代码将显示前100家商家的名称、所在城市和州。

在查看结果时，你可能会注意到数据中多出了一些多余的列，例如 `ID_x` 和 `ID_y`。这些是连接操作后产生的重复列。以下是删除它们的方法：

```python
del df['ID_x']
del df['ID_y']
```

![](img/442bb02998a1786261ff63d4f22a0baa_19.png)

删除后，再次查看数据，这些多余的列就消失了。现在，数据集中只保留了原始的 `city ID` 和 `state ID` 列，以及我们通过连接添加的 `city` 和 `state` 信息列。

---

![](img/442bb02998a1786261ff63d4f22a0baa_21.png)

## 总结

本节课中我们一起学习了如何使用Pandas进行数据连接操作。我们主要完成了以下步骤：
1.  **导入库与加载数据**：使用 `pd.ExcelFile` 和 `parse` 方法加载Excel文件中的多个工作表。
2.  **执行连接**：使用 `pd.merge()` 函数，通过指定连接键（`left_on`, `right_on`）和连接方式（`how='inner'`），将城市和州的信息表连接到主数据集。
3.  **查看与清理**：选取特定列查看结果，并使用 `del` 关键字删除连接后产生的重复列。

![](img/442bb02998a1786261ff63d4f22a0baa_23.png)

通过这个练习，你掌握了将分散在不同表格中的相关信息整合到一个统一视图中的基本方法，这是数据分析中一项非常实用的技能。