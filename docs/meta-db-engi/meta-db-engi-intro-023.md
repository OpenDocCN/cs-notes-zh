# 23：更新数据 📝

在本节课中，我们将学习如何使用 SQL 的 `UPDATE` 语句来修改数据库表中已有的数据。我们将通过具体的例子，演示如何更新单个学生的信息，以及如何批量更新多个学生的记录。

---

## 概述

`UPDATE` 语句是 SQL 中用于修改表中现有记录的核心命令。通过结合 `SET` 子句指定要更改的列和新值，并使用 `WHERE` 子句精确选择要更新的行，我们可以灵活地管理数据。

---

## 更新单个学生的记录

上一节我们介绍了 `UPDATE` 语句的基本概念。本节中，我们来看看如何更新表中特定学生的信息。

假设我们有一个名为 `StudentTable` 的表，包含以下字段：`Id`、`FirstName`、`LastName`、`HomeAddress`、`CollegeAddress`、`ContactNumber` 和 `Department`。

现在，我们需要更新 `Id` 为 3 的学生的家庭住址和联系电话。

以下是执行此操作的 SQL 语法步骤：

1.  使用 `UPDATE` 子句，后跟要更新的表名。
2.  使用 `SET` 子句，指定要更新的列及其新值。
3.  使用 `WHERE` 子句，精确指定要更新的记录。

对应的 SQL 代码如下：

```sql
UPDATE StudentTable
SET HomeAddress = '123 New Street',
    ContactNumber = '555-0123'
WHERE Id = 3;
```

执行此语句后，数据库会返回确认消息。检查表格，可以看到 `Id` 为 3 的学生的 `HomeAddress` 和 `ContactNumber` 字段已更新为新值。

---

## 批量更新多个学生的记录

学会了更新单条记录后，我们进一步探讨如何批量更新满足特定条件的多条记录。

例如，假设学校的工程系已将课程迁至校园内的新地点“Harper Building”。我们需要为所有工程系的学生更新 `CollegeAddress` 字段。

以下是批量更新的 SQL 语法：

```sql
UPDATE StudentTable
SET CollegeAddress = 'Harper Building'
WHERE Department = 'Engineering';
```

此语句会将 `Department` 列为 ‘Engineering’ 的所有学生的 `CollegeAddress` 更新为 ‘Harper Building’。

---

## 同时更新多个字段

`UPDATE` 语句的强大之处在于，它可以一次性更新多个列。

例如，如果我们想同时更新工程系学生的学院地址和家庭地址，可以在 `SET` 子句中添加多个“列-值”对。

以下是更新多个字段的语法示例：

```sql
UPDATE StudentTable
SET CollegeAddress = 'Harper Building',
    HomeAddress = '456 Maple Ave'
WHERE Department = 'Engineering';
```

在这个例子中，我们用一个 `UPDATE` 语句更新了两列数据。

**关键点**：在 `SET` 子句中，多个“列=值”配对之间必须用逗号分隔。

---

## 总结

![](img/45e85f7fb0571ae4bb7cbf5f09015183_1.png)

本节课中我们一起学习了 SQL `UPDATE` 语句的用法。
*   我们掌握了如何使用 `UPDATE ... SET ... WHERE ...` 语法来更新表中的特定记录。
*   我们实践了更新单个学生信息的方法。
*   我们学习了如何通过 `WHERE` 子句筛选条件，来批量更新多个学生的记录。
*   最后，我们了解了如何在一个语句中同时更新多个字段的值。

![](img/45e85f7fb0571ae4bb7cbf5f09015183_3.png)

正确使用 `UPDATE` 语句是管理和维护数据库数据准确性的关键技能。