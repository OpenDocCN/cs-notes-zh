# PostgreSQL for Everybody：4：SELECT DISTINCT 语句演示 🚗

在本节中，我们将学习如何使用 `SELECT DISTINCT` 和 `SELECT DISTINCT ON` 语句来消除查询结果中的重复行。我们将通过创建一个包含重复数据的示例表，并演示不同形式的 `DISTINCT` 如何工作。

## 概述

![](img/d6e19964e48ccc864d21b970b9e80950_1.png)

`SELECT DISTINCT` 是 SQL 中用于从查询结果中移除重复行的关键字。它基于所选列的组合来判断重复。`SELECT DISTINCT ON` 则提供了更精细的控制，允许我们指定在哪个（或哪些）列上进行去重，并配合 `ORDER BY` 来决定保留哪一行。

## 创建示例数据

首先，我们创建一个名为 `racing` 的表，并插入一些包含重复制造商和型号的数据，以便演示。

```sql
CREATE TABLE racing (
    make VARCHAR(50),
    model VARCHAR(50),
    year INT,
    price DECIMAL(10, 2)
);

INSERT INTO racing (make, model, year, price) VALUES
('Dodge', 'Neon', 1995, 10000),
('Dodge', 'Neon', 1998, 12000),
('Dodge', 'Neon', 1999, 13000),
('Ford', 'Focus', 2000, 15000),
('Ford', 'Focus', 2001, 16000),
('Subaru', 'Impreza', 2002, 20000),
('Mazda', 'Miata', 2001, 18000),
('Mazda', 'Miata', 2002, 19000);
```

## 使用 SELECT DISTINCT

上一节我们创建了包含重复数据的表。本节中，我们来看看如何使用基本的 `SELECT DISTINCT`。

最基本的 `SELECT DISTINCT` 形式作用于所有选定的列，它确保最终结果集中的每一行都是唯一的。

执行一个简单的查询，查看 `make` 列：

```sql
SELECT make FROM racing;
```

你会发现结果中有很多重复项，例如 Dodge 出现了多次。

要消除这些重复，只需在 `SELECT` 后添加 `DISTINCT` 关键字：

![](img/d6e19964e48ccc864d21b970b9e80950_3.png)

```sql
SELECT DISTINCT make FROM racing;
```

![](img/d6e19964e48ccc864d21b970b9e80950_5.png)

这条语句的意思是：“不要向我显示相同的行两次”。数据库引擎在处理查询时，会检查每一行，如果该行已经存在于结果集中，就不会再次添加。

你也可以在多个列上使用 `DISTINCT`。以下是基于 `make` 和 `model` 组合进行去重的示例：

```sql
SELECT DISTINCT make, model FROM racing;
```

此时，数据库判断重复的依据是 `make` 和 `model` 这两列值的组合。只有组合完全相同的行才会被去重。

## 使用 SELECT DISTINCT ON

基本的 `DISTINCT` 适用于整个行。但有时我们只想在特定的一列上消除重复，同时还能看到其他列的信息。这时就需要 `SELECT DISTINCT ON`。

![](img/d6e19964e48ccc864d21b970b9e80950_7.png)

![](img/d6e19964e48ccc864d21b970b9e80950_8.png)

`SELECT DISTINCT ON` 允许我们指定一个或一组列，仅在这些列上消除重复值。对于被消除的重复组，数据库会返回**第一行**（除非使用 `ORDER BY` 指定顺序）。

以下是一个示例，我们希望在 `model` 列上消除重复，但同时查看 `make` 和 `year`：

```sql
SELECT DISTINCT ON (model) make, model, year FROM racing;
```

这条查询会为每个唯一的 `model` 返回一行。但问题来了：对于有多个年份的 Dodge Neon，数据库会返回哪一年的记录呢？

默认情况下，返回的是查询过程中**最先遇到**的那一行，这个顺序可能是不确定的。为了可控地选择保留哪一行，我们必须结合 `ORDER BY` 子句。

## 结合 ORDER BY 使用

为了让 `SELECT DISTINCT ON` 的行为可预测，我们需要使用 `ORDER BY` 来明确指定行的排序顺序。去重操作将保留每个重复组中排序后的第一行。

首先，我们看看如果不使用 `DISTINCT ON`，只是按年份降序排列所有数据：

```sql
SELECT make, model, year FROM racing ORDER BY year DESC;
```

现在，我们在此基础上添加 `DISTINCT ON (model)`。我们希望为每个型号只保留最新（年份最大）的那条记录：

```sql
SELECT DISTINCT ON (model) make, model, year
FROM racing
ORDER BY model, year DESC;
```

让我们分解一下这个查询：
1.  `ORDER BY model, year DESC`：首先按 `model` 排序，然后在每个 `model` 组内按 `year` 降序排列。
2.  `DISTINCT ON (model)`：对于每个唯一的 `model`，只保留排序后的第一行（即年份最大的那一行）。

执行后，对于 “Dodge Neon”，我们将只看到 1999 年的记录，因为它在组内按年份降序排在第一。

同理，如果我们想为每个型号保留最早年份的记录，可以按年份升序排列：

```sql
SELECT DISTINCT ON (model) make, model, year
FROM racing
ORDER BY model, year ASC;
```

## 常见用法总结

在实际应用中，`SELECT DISTINCT`（不带 `ON`）更为常用。它通常用于快速查看某一列或某几列的唯一值列表。

例如，查看表中所有不重复的年份：

```sql
SELECT DISTINCT year FROM racing;
```

或者，查看所有不重复的制造商和型号组合：

```sql
SELECT DISTINCT make, model FROM racing;
```

`SELECT DISTINCT ON` 是一个更高级、更特定的功能，在需要基于某列去重但同时需要获取组内“第一条”相关记录的详细信息时非常有用。

## 总结

![](img/d6e19964e48ccc864d21b970b9e80950_10.png)

![](img/d6e19964e48ccc864d21b970b9e80950_11.png)

本节课中我们一起学习了 `SELECT DISTINCT` 语句的核心用法。
*   **`SELECT DISTINCT`**：用于从结果集中移除所有列值都完全相同的重复行。
*   **`SELECT DISTINCT ON (column)`**：用于基于指定列消除重复，并可通过 `ORDER BY` 子句控制每个重复组中保留哪一行。
理解这些语句能帮助你在查询数据时有效地整理和简化结果，尤其是在处理包含大量重复信息的数据集时。