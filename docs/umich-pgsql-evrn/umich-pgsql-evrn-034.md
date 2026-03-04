# 034：GROUP BY分组查询演示 🗂️

在本节课中，我们将要学习 `GROUP BY` 子句的工作原理。`GROUP BY` 与 `DISTINCT` 相关，两者本质上都是先创建一个记录集，然后对其进行后处理。`DISTINCT` 的作用很简单，就是去除重复行。而 `GROUP BY` 则更进一步，它允许我们对分组后的数据进行聚合计算。

## 概述

我们将使用 PostgreSQL 内置的 `pg_timezone_names` 虚拟表来演示 `GROUP BY` 的用法。这张表包含了时区名称、缩写、与 UTC 的偏移量以及是否使用夏令时等信息。

## 从 DISTINCT 到 GROUP BY

![](img/69d134343a5b54d0d26b6ede57a23c69_1.png)

上一节我们介绍了 `DISTINCT`，本节我们来看看 `GROUP BY`。首先，让我们查看一下 `pg_timezone_names` 表中有多少行数据。

```sql
SELECT COUNT(*) FROM pg_timezone_names;
```

![](img/69d134343a5b54d0d26b6ede57a23c69_3.png)

执行上述查询，我们会得到 591 行数据。

![](img/69d134343a5b54d0d26b6ede57a23c69_5.png)

接下来，我们使用 `DISTINCT` 查看 `is_dst` 字段的唯一值。`is_dst` 表示是否使用夏令时。

```sql
SELECT DISTINCT is_dst FROM pg_timezone_names;
```

![](img/69d134343a5b54d0d26b6ede57a23c69_7.png)

查询结果只有两行：`false` 和 `true`。如果不使用 `DISTINCT`，直接查询前 20 行，我们会看到大量的垂直重复数据。

![](img/69d134343a5b54d0d26b6ede57a23c69_9.png)

```sql
SELECT is_dst FROM pg_timezone_names LIMIT 20;
```

`DISTINCT` 的作用就是“挤压”掉这些垂直重复的行。如果我们同时选择多个字段，`DISTINCT` 则会基于所有选定字段的组合来判断唯一性。

## GROUP BY 的核心概念

`GROUP BY` 的核心思想与 `DISTINCT` 类似，但它不仅仅是去除重复，还能对每个分组进行聚合计算。

以下是一个基础示例，它统计了 `is_dst` 字段中 `true` 和 `false` 各自的数量：

```sql
SELECT is_dst, COUNT(is_dst) FROM pg_timezone_names GROUP BY is_dst;
```

这条语句的工作原理是：首先将所有行按照 `is_dst` 的唯一值进行分组（类似于 `DISTINCT`），然后对每个分组中的行进行计数，最后将分组和计数结果返回给我们。理解这个基础示例至关重要。

## 使用 WHERE 和 HAVING 子句

我们可以对分组查询应用 `WHERE` 和 `HAVING` 子句来进行过滤。

`WHERE` 子句在分组**之前**过滤记录。例如，以下查询只统计 `is_dst` 为 `true` 的记录：

```sql
SELECT is_dst, COUNT(is_dst) FROM pg_timezone_names WHERE is_dst = true GROUP BY is_dst;
```

有时，我们可能希望基于聚合计算的结果（如计数）进行过滤。这时就需要使用 `HAVING` 子句，它在分组**之后**对结果进行过滤。

![](img/69d134343a5b54d0d26b6ede57a23c69_11.png)

以下是 `HAVING` 子句的使用示例，它找出出现次数超过 10 次的时区缩写：

```sql
SELECT abbrev, COUNT(abbrev) FROM pg_timezone_names GROUP BY abbrev HAVING COUNT(abbrev) > 10;
```

需要注意的是，`HAVING` 子句中引用的必须是出现在 `SELECT` 列表中的聚合列。

![](img/69d134343a5b54d0d26b6ede57a23c69_13.png)

![](img/69d134343a5b54d0d26b6ede57a23c69_14.png)

为了更清晰地查看结果，我们可以对查询结果进行排序：

```sql
SELECT abbrev, COUNT(abbrev) FROM pg_timezone_names GROUP BY abbrev HAVING COUNT(abbrev) > 10 ORDER BY COUNT(abbrev) DESC;
```

执行后，我们可以看到按出现次数降序排列的、使用超过 10 次的时区缩写列表。

![](img/69d134343a5b54d0d26b6ede57a23c69_16.png)

## 总结

本节课我们一起学习了 `GROUP BY` 分组查询。我们了解到 `GROUP BY` 可以将数据分组并对每个组进行聚合计算（如计数）。我们还学习了如何使用 `WHERE` 子句在分组前过滤数据，以及如何使用 `HAVING` 子句在分组后基于聚合结果进行过滤。掌握这些概念对于进行复杂的数据汇总和分析至关重要。在接下来的课程中，我们将探讨子查询的相关内容。