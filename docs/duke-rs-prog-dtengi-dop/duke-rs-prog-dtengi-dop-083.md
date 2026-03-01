# 083：83_04_04_BigQuery提示工程 🚀

![](img/07fa1d1f02c8dff04313ff4da149f75d_0.png)

在本节课中，我们将学习如何将提示工程应用于BigQuery平台。我们将通过一个具体的例子，展示如何利用大型语言模型（如ChatGPT）来理解、修改和增强SQL查询，从而更高效地进行数据分析和处理。

## 概述

提示工程是一种与大型语言模型交互的技术，通过精心设计的指令（提示）来引导模型生成所需的代码或解释。本节我们将探索如何将这一技术应用于Google BigQuery，以简化SQL查询的编写和优化过程。

## 开始使用提示工程

上一节我们介绍了提示工程的基本概念。本节中，我们来看看如何在Open AI的平台上开始实践。

在Open AI的界面中，我们可以开始进行提示工程。这里的核心思想是，通过查看各种示例，我们可以找到多种从大型语言模型中获取代码的方法。以“SQL翻译”为例，这是一个很好的起点。我们可以打开一个“Playground”，提交提示，并尝试获得一些SQL答案。这个过程就是通过提示程序来获取代码，并进行反复调整。

## 在BigQuery中应用提示工程

![](img/07fa1d1f02c8dff04313ff4da149f75d_2.png)

那么，我们如何在像BigQuery这样的平台上实际应用提示工程呢？让我们通过一个实例来探索。

首先，我们查看一些数据。这里展示的是Google Cloud的搜索趋势数据。在Google Trends数据集中，我们可以看到诸如“top rising terms”等项目。如果我们想查看其中一个查询，可以打开它并开始操作。

但如果我们不完全清楚如何格式化查询或使其更完善呢？一个简单的方法是将查询语句复制到ChatGPT中寻求帮助。

![](img/07fa1d1f02c8dff04313ff4da149f75d_4.png)

以下是请求解释查询的示例：

```sql
-- 原始查询示例
SELECT term, score
FROM `bigquery-public-data.google_trends.international_top_terms`
WHERE refresh_date = DATE('2023-04-17')
ORDER BY score DESC
LIMIT 100;
```

![](img/07fa1d1f02c8dff04313ff4da149f75d_6.png)

我们可以向ChatGPT提出请求：“请为我解释这个Google BigQuery查询。”模型会返回解释，说明这个查询旨在从特定日期范围的Google Trends数据集中提取前100个上升最快的搜索词。这是开始构建查询时理解现有代码的好方法。

## 修改和优化查询

理解了基础查询后，我们可能想对其进行修改。例如，我们可能只想获取前10个结果，而不是100个。

我们可以向ChatGPT提供原始代码，并给出新的指令：“请修改此查询，只获取前10个结果。”

![](img/07fa1d1f02c8dff04313ff4da149f75d_8.png)

模型可能会返回修改后的代码：

```sql
SELECT term, score
FROM `bigquery-public-data.google_trends.international_top_terms`
WHERE refresh_date = DATE('2023-04-17')
ORDER BY score DESC
LIMIT 10; -- 修改为仅获取前10个结果
```

![](img/07fa1d1f02c8dff04313ff4da149f75d_10.png)

我们将修改后的代码粘贴回BigQuery并运行，就能成功获得前10个结果。

## 实现更复杂的转换

![](img/07fa1d1f02c8dff04313ff4da149f75d_12.png)

接下来，我们可以尝试更复杂的转换。例如，我们希望所有结果都以大写形式显示。

我们可以继续向ChatGPT提出请求：“现在我需要所有结果都显示为大写字母。”

![](img/07fa1d1f02c8dff04313ff4da149f75d_14.png)

模型可能会建议使用`UPPER()`函数：

```sql
SELECT UPPER(term) AS term, score -- 使用UPPER函数将术语转换为大写
FROM `bigquery-public-data.google_trends.international_top_terms`
WHERE refresh_date = DATE('2023-04-17')
ORDER BY score DESC
LIMIT 10;
```

再次将代码粘贴到BigQuery中运行，结果确实全部变成了大写。

![](img/07fa1d1f02c8dff04313ff4da149f75d_16.png)

我们还可以进行其他调整，例如将结果中的空格替换为下划线。

提出请求：“现在将所有空格替换为下划线。”

模型可能会建议使用`REPLACE()`函数：

![](img/07fa1d1f02c8dff04313ff4da149f75d_18.png)

```sql
SELECT REPLACE(UPPER(term), ' ', '_') AS term, score -- 将大写后的术语中的空格替换为下划线
FROM `bigquery-public-data.google_trends.international_top_terms`
WHERE refresh_date = DATE('2023-04-17')
ORDER BY score DESC
LIMIT 10;
```

![](img/07fa1d1f02c8dff04313ff4da149f75d_20.png)

## 逐步增加查询复杂度

![](img/07fa1d1f02c8dff04313ff4da149f75d_22.png)

在提示工程中，采用渐进式的方法逐步增加需求是获取理想结果的最佳策略之一。

观察查询，我们发现数据中还有“country_code”和“country_name”字段。我们可以要求将这些信息也加入查询结果中。

![](img/07fa1d1f02c8dff04313ff4da149f75d_24.png)

提出请求：“请在查询中添加国家代码和国家名称。”

模型会相应修改`SELECT`子句和`GROUP BY`子句：

```sql
SELECT
  country_code,
  country_name,
  REPLACE(UPPER(term), ' ', '_') AS term,
  score
FROM `bigquery-public-data.google_trends.international_top_terms`
WHERE refresh_date = DATE('2023-04-17')
GROUP BY country_code, country_name, term, score
ORDER BY score DESC
LIMIT 10;
```

![](img/07fa1d1f02c8dff04313ff4da149f75d_26.png)

## 构建最终复杂查询

最后，我们可以尝试构建一个更复杂的查询。例如，将结果扩展到前50条，并新增一列来统计每个国家出现的搜索词数量。

提出一个综合请求：“现在将查询扩展到返回50个结果，并添加一个我们自己生成的列，用于统计每个国家的结果出现次数，并将其包含在输出中。”

模型可能会生成如下查询：

```sql
SELECT
  country_code,
  country_name,
  REPLACE(UPPER(term), ' ', '_') AS term,
  score,
  COUNT(*) OVER (PARTITION BY country_name) AS country_occurrence_count -- 使用窗口函数统计每个国家的出现次数
FROM `bigquery-public-data.google_trends.international_top_terms`
WHERE refresh_date = DATE('2023-04-17')
ORDER BY score DESC
LIMIT 50;
```

![](img/07fa1d1f02c8dff04313ff4da149f75d_28.png)

![](img/07fa1d1f02c8dff04313ff4da149f75d_29.png)

运行这个查询，我们成功获得了前50个结果，并且包含了每个国家搜索词的出现次数统计。

## 总结

本节课中，我们一起学习了如何将提示工程应用于BigQuery。我们通过实例演示了如何：
1.  使用大型语言模型解释现有的SQL查询。
2.  通过自然语言指令修改和优化查询（如限制结果数量、转换文本格式）。
3.  以渐进的方式增加查询的复杂度，逐步添加所需字段和计算列。
4.  最终构建一个包含数据统计的复杂查询。

![](img/07fa1d1f02c8dff04313ff4da149f75d_31.png)

![](img/07fa1d1f02c8dff04313ff4da149f75d_32.png)

这种方法极大地提升了使用BigQuery等数据平台进行探索和开发的效率，就像有一位数据库专家随时在身边提供帮助。通过有效的提示工程，我们可以为未来的机器学习模型训练或其他数据分析任务快速准备好所需的数据视图。