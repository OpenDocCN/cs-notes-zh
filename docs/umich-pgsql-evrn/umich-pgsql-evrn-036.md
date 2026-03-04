# 036：子查询应用演示 🧩

![](img/aa7df3be9aadc3ad98ae613883ddbaa1_1.png)

## 概述
在本节课中，我们将要学习SQL中一个强大且实用的技术——子查询。子查询允许我们将一个查询的结果作为另一个查询的输入，这对于数据操作和分析非常有用。我们将通过具体的例子来理解其工作原理和应用场景。

![](img/aa7df3be9aadc3ad98ae613883ddbaa1_3.png)

![](img/aa7df3be9aadc3ad98ae613883ddbaa1_4.png)

## 子查询的基本概念
子查询的核心思想是：将一个查询的结果作为另一个查询的输入。这意味着PostgreSQL会先执行内部的查询，获取其结果，然后再执行外部的查询。虽然在高性能的在线系统中，人们可能因为效率问题而不喜欢使用子查询，但在数据操作和一次性分析任务中，它是一个非常有价值的工具。

## 简单子查询示例
上一节我们介绍了子查询的基本概念，本节中我们来看看一个具体的例子。

![](img/aa7df3be9aadc3ad98ae613883ddbaa1_6.png)

假设我们想查找特定账户（例如邮箱为 `edit@study.com` 的账户）发表的所有评论内容。我们首先需要知道该账户的ID，然后根据这个ID去查找评论。

以下是实现此目标的步骤：
1.  首先，我们查询账户表以获取该邮箱对应的账户ID：
    ```sql
    SELECT id FROM account WHERE email = 'edit@study.com';
    ```
    这个查询会返回一个数字（例如 `1`）。

2.  接着，我们使用这个ID来查询评论表：
    ```sql
    SELECT content FROM comment WHERE account_id = 1;
    ```

子查询允许我们将这两个步骤合并为一个查询。我们将第一个查询（获取ID）放在括号内，作为第二个查询中 `WHERE` 条件的一部分。

```sql
SELECT content FROM comment WHERE account_id = (SELECT id FROM account WHERE email = 'edit@study.com');
```

执行时，PostgreSQL会先运行内部的 `SELECT` 语句获取ID，然后运行外部的 `SELECT` 语句获取评论内容。这就是最简单的子查询形式。

## 在FROM子句中使用子查询
除了在 `WHERE` 子句中使用，子查询还可以作为“虚拟表”在 `FROM` 子句中使用。这为我们提供了更大的灵活性。

![](img/aa7df3be9aadc3ad98ae613883ddbaa1_8.png)

![](img/aa7df3be9aadc3ad98ae613883ddbaa1_10.png)

让我们回顾一个使用 `HAVING` 子句的例子。`HAVING` 子句在 `GROUP BY` 分组之后对结果进行过滤。但有时，我们可以通过子查询来达到类似的效果。

![](img/aa7df3be9aadc3ad98ae613883ddbaa1_12.png)

以下是一个生成分组计数结果的查询：
```sql
SELECT post_id, COUNT(*) AS ct FROM comment GROUP BY post_id;
```
这个查询会返回一个包含 `post_id` 和对应评论数量 `ct` 的结果集。

现在，我们可以将这个查询本身作为一个“表”，放在外部查询的 `FROM` 子句中，并为其指定一个别名（例如 `zap`）。

![](img/aa7df3be9aadc3ad98ae613883ddbaa1_14.png)

```sql
SELECT * FROM (
    SELECT post_id, COUNT(*) AS ct FROM comment GROUP BY post_id
) AS zap;
```
此时，`zap` 就是一个临时的虚拟表，它拥有 `post_id` 和 `ct` 两列。我们可以像查询普通表一样，对这个虚拟表应用 `WHERE`、`ORDER BY` 等子句。

![](img/aa7df3be9aadc3ad98ae613883ddbaa1_16.png)

例如，我们只想查看评论数量超过30条的记录，并按数量降序排列：

![](img/aa7df3be9aadc3ad98ae613883ddbaa1_18.png)

![](img/aa7df3be9aadc3ad98ae613883ddbaa1_20.png)

```sql
SELECT * FROM (
    SELECT post_id, COUNT(*) AS ct FROM comment GROUP BY post_id
) AS zap
WHERE zap.ct > 30
ORDER BY zap.ct DESC;
```
在这个例子中，内部查询负责分组和计数，外部查询负责对计数结果进行过滤和排序。这种将复杂查询分解为多个逻辑步骤的方法，使得SQL语句更易于构建和理解。

![](img/aa7df3be9aadc3ad98ae613883ddbaa1_22.png)

![](img/aa7df3be9aadc3ad98ae613883ddbaa1_23.png)

## 子查询的优缺点与适用场景
子查询是一个非常强大的工具，但它也存在一个关键的“优化边界”问题。外部查询必须等待内部查询完全执行完毕并生成所有结果后，才能开始工作。如果内部查询的结果集非常大，数据库可能需要将其写入磁盘，然后外部查询再从中读取，这可能会影响性能。

![](img/aa7df3be9aadc3ad98ae613883ddbaa1_25.png)

因此，在需要处理高并发、低延迟的在线事务处理系统中，数据库优化师通常会尽量避免使用子查询。

然而，在数据分析、数据挖掘或一次性数据处理的场景下，我们执行的查询可能只需要运行零点几秒，并且只运行一次。在这种情况下，子查询的简洁性和强大功能使其成为一个不可或缺的工具。它可以帮助我们清晰地表达复杂的逻辑，而不必过分担心其对瞬时性能的微小影响。

![](img/aa7df3be9aadc3ad98ae613883ddbaa1_27.png)

## 总结
本节课中我们一起学习了SQL子查询的应用。我们了解了子查询如何将一个查询的结果嵌入到另一个查询中，并探索了其在 `WHERE` 子句和 `FROM` 子句中的两种主要用法。我们认识到，虽然子查询在需要极致性能的在线系统中可能不是最佳选择，但对于数据分析和即席查询任务来说，它是一个极其强大和实用的技术。掌握子查询，能让你更灵活、更高效地操作和探索数据。