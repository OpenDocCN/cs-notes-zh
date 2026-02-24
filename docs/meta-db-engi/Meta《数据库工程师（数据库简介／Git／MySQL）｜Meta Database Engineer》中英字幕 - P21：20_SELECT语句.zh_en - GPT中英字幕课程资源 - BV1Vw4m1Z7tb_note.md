# 数据库工程师：P21：SELECT语句 🗃️

在本节课中，我们将学习如何使用SQL中的`SELECT`语句从数据库表中查询数据。`SELECT`语句是SQL中最基础且最常用的命令之一，它允许你检索表中的特定列、所有列，甚至执行计算。

## 基本语法

上一节我们介绍了`SELECT`语句的重要性，本节中我们来看看它的基本语法结构。一个基础的SQL `SELECT`语句由以下部分组成：

```sql
SELECT column_name FROM table_name;
```

*   `SELECT` 是用于检索数据的关键字。
*   `column_name` 是你需要查询的数据所在的列名。
*   `FROM` 是指定数据来源表的关键字。
*   `table_name` 是你要查询的表的名称。
*   分号 `;` 通常用于标记SQL语句的结束。

## 查询单列数据

理解了基本语法后，让我们通过一个具体例子来看看如何从表中查询一列数据。假设我们有一个名为 `Players` 的足球俱乐部球员表，其中包含 `ID`、`name`、`age`、`level` 等列。

![](img/0e6d7f43f44e0d3bc924df13976a56e5_1.png)

如果我们只需要获取所有球员的姓名，可以使用以下语句：

```sql
SELECT name FROM Players;
```

![](img/0e6d7f43f44e0d3bc924df13976a56e5_3.png)

![](img/0e6d7f43f44e0d3bc924df13976a56e5_4.png)

执行此查询后，将返回一个结果集，其中单独列出 `Players` 表中 `name` 列的所有值，每个姓名占据一行。

## 查询多列数据

有时，我们需要从表中获取不止一列的信息。例如，我们想同时查看每位球员的姓名和技能等级。

![](img/0e6d7f43f44e0d3bc924df13976a56e5_6.png)

以下是实现此目标的方法：

```sql
SELECT name, level FROM Players;
```

请注意，在 `SELECT` 关键字后列出多个列名时，必须用逗号 `,` 将它们分隔开，这样SQL才能识别它们是不同的列。执行此查询将返回来自 `name` 和 `level` 两列的数据。

![](img/0e6d7f43f44e0d3bc924df13976a56e5_8.png)

## 查询所有列数据

如果需要检索表中的所有数据，也有两种方法可以实现。

![](img/0e6d7f43f44e0d3bc924df13976a56e5_10.png)

第一种方法是列出所有列名：

```sql
SELECT ID, name, age, level FROM Players;
```

![](img/0e6d7f43f44e0d3bc924df13976a56e5_12.png)

同样，每个列名之间需要用逗号分隔。

![](img/0e6d7f43f44e0d3bc924df13976a56e5_14.png)

![](img/0e6d7f43f44e0d3bc924df13976a56e5_16.png)

第二种方法是使用星号 `*` 作为通配符，这是一种快捷方式：

```sql
SELECT * FROM Players;
```

![](img/0e6d7f43f44e0d3bc924df13976a56e5_18.png)

使用 `SELECT *` 会返回指定表中所有列的所有数据，其结果与显式列出所有列名相同。

![](img/0e6d7f43f44e0d3bc924df13976a56e5_20.png)

---

本节课中我们一起学习了SQL `SELECT` 语句的核心用法。你现在已经掌握了如何从数据库表中查询单列、多列以及所有列的数据。下次当你需要从数据库中检索信息时，就可以根据需求选择合适的方法了。