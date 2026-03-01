# 127：更新与创建数据

![](img/2613bea855278c9214e6f913b47b7ae1_0.png)

在本节课中，我们将要学习如何在数据框中创建新的列，以及如何利用这些新列进行数据查询。这是数据处理中非常实用且基础的操作。

## 创建新列 🆕

![](img/2613bea855278c9214e6f913b47b7ae1_2.png)

在数据框中创建新列非常简单。你只需要为新列指定一个唯一的名称，并为其赋值即可。

例如，你可以使用以下语法来创建一个新列：
```python
my_df['new_column'] = some_value
```

![](img/2613bea855278c9214e6f913b47b7ae1_4.png)

## 组合现有列 🔗

上一节我们介绍了如何创建简单的新列，本节中我们来看看如何通过组合现有列来创建更复杂的新列。

![](img/2613bea855278c9214e6f913b47b7ae1_6.png)

![](img/2613bea855278c9214e6f913b47b7ae1_7.png)

以下是一个具体的例子：添加一个名为 `categories` 的新列，该列将 `category0` 和 `category1` 的值组合成一个用逗号分隔的列表。

```python
my_df['categories'] = my_df['category0'] + ', ' + my_df['category1']
```

![](img/2613bea855278c9214e6f913b47b7ae1_9.png)

这段代码将 `category0` 的字符串值与 `category1` 的字符串值连接起来，并用逗号分隔它们。

## 利用新列进行查询 🔍

![](img/2613bea855278c9214e6f913b47b7ae1_11.png)

现在我们已经创建了一个组合后的 `categories` 列，我们可以基于这个单一的列来查找业务数据。

以下是查找披萨餐厅的示例，通过检查 `categories` 列是否包含字符串 “pizza” 来实现：

![](img/2613bea855278c9214e6f913b47b7ae1_13.png)

```python
pizza_restaurants = my_df[my_df['categories'].str.contains('pizza')]
```

![](img/2613bea855278c9214e6f913b47b7ae1_14.png)

本节课中我们一起学习了如何在数据框中创建新列，包括直接赋值和组合现有列，并利用新列进行数据筛选。这些是进行有效数据分析和处理的基础技能。