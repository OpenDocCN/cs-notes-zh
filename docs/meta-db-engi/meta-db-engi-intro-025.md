# 25：模块小结 - CRUD操作 📊

在本节课中，我们将回顾整个模块的核心内容，即数据库的CRUD操作。我们将总结如何创建、读取、更新和删除数据，并回顾SQL数据类型等关键概念。通过本小结，你将巩固已学技能，为成为数据库工程师打下坚实基础。

## 模块内容回顾

本模块中，你学习了如何在数据库中进行创建、读取、更新和删除数据。你还研究了不同的SQL数据类型，例如数值型、字符串型和默认值。

现在，我们来回顾你学到的关键主题和掌握的技能。

## SQL数据类型介绍

模块开始时，我们介绍了SQL数据类型。

完成第一课后，你现在能够识别和理解数值数据类型，以便将数据以数字形式存储在数据库中，在数据库中使用数值数据类型，并区分整数和小数数据类型，从而存储不同大小的数值，包括正数和负数。

![](img/25c5c916be3b2d2c6264223ed026ef6f_1.png)

以下是数值数据类型的核心概念：

![](img/25c5c916be3b2d2c6264223ed026ef6f_2.png)

![](img/25c5c916be3b2d2c6264223ed026ef6f_3.png)

![](img/25c5c916be3b2d2c6264223ed026ef6f_4.png)

*   **整数类型**：用于存储没有小数部分的数字，例如 `INT`。
*   **小数类型**：用于存储包含小数部分的数字，例如 `DECIMAL(10, 2)`。

---

在探索了数值数据类型之后，我们接着研究了字符串数据类型。

![](img/25c5c916be3b2d2c6264223ed026ef6f_6.png)

在研究过程中，你学会了如何识别和理解数据库中的字符串数据类型。

以下是字符串数据类型的核心概念：

![](img/25c5c916be3b2d2c6264223ed026ef6f_8.png)

*   **固定长度字符串**：使用 `CHAR(n)` 定义，始终占用 `n` 个字符的空间。
*   **可变长度字符串**：使用 `VARCHAR(n)` 定义，最多占用 `n` 个字符的空间，实际占用空间根据数据长度变化。

---

本课学习的最后一个概念是默认值。

![](img/25c5c916be3b2d2c6264223ed026ef6f_10.png)

现在你已经完成了关于默认值的课程，你能够演示对数据库中约束概念的理解（使用SQL语法），并识别用于在表中设置默认值的默认约束。

![](img/25c5c916be3b2d2c6264223ed026ef6f_11.png)

![](img/25c5c916be3b2d2c6264223ed026ef6f_12.png)

默认值的核心语法是：
```sql
CREATE TABLE table_name (
    column_name data_type DEFAULT default_value
);
```

---

作为本课的一部分，你还完成了一系列专注于SQL数据类型的练习。

成功完成这些练习后，你现在能够展示使用数值数据类型、字符串数据类型和默认值的能力，并概述如何为你的数据选择正确的数据类型。

![](img/25c5c916be3b2d2c6264223ed026ef6f_14.png)

![](img/25c5c916be3b2d2c6264223ed026ef6f_15.png)

## 创建和读取数据

![](img/25c5c916be3b2d2c6264223ed026ef6f_16.png)

完成SQL数据类型的学习后，我们接着探索了在数据库中创建和读取数据的主题。

现在你已经完成了这一课，你能够创建数据库和表，修改数据库表结构，以及删除数据库。

![](img/25c5c916be3b2d2c6264223ed026ef6f_18.png)

创建数据库和表的核心命令如下：
```sql
CREATE DATABASE db_name;
CREATE TABLE table_name (...);
ALTER TABLE table_name ...;
DROP DATABASE db_name;
```

---

![](img/25c5c916be3b2d2c6264223ed026ef6f_20.png)

你还可以演示如何使用SQL语法在数据库中创建表，使用SQL的`ALTER TABLE`语句修改表结构，以及使用SQL的`INSERT`语句向表中插入或添加数据。

插入数据的核心语法是：
```sql
INSERT INTO table_name (column1, column2) VALUES (value1, value2);
```

![](img/25c5c916be3b2d2c6264223ed026ef6f_22.png)

---

![](img/25c5c916be3b2d2c6264223ed026ef6f_23.png)

![](img/25c5c916be3b2d2c6264223ed026ef6f_24.png)

除了这些新技能，你还学会了如何使用SQL的`SELECT`语句从表中检索数据，以及如何使用`INSERT INTO ... SELECT`语句将一个或多个表中的查询数据插入到另一个目标表中。

数据检索与插入的核心语法：
```sql
SELECT * FROM table_name;
INSERT INTO target_table SELECT * FROM source_table;
```

---

![](img/25c5c916be3b2d2c6264223ed026ef6f_26.png)

![](img/25c5c916be3b2d2c6264223ed026ef6f_27.png)

你也有机会通过一系列练习来展示这些新技能。

在这些练习中，你证明了你有能力创建数据库和表，然后向表中填充数据，并使用`SELECT`和`INSERT INTO ... SELECT`语句管理表中的数据。

## 更新和删除数据

接着，我们进入了最后一课，探索如何更新和删除数据。

![](img/25c5c916be3b2d2c6264223ed026ef6f_29.png)

![](img/25c5c916be3b2d2c6264223ed026ef6f_30.png)

完成本课后，你现在能够演示对SQL`UPDATE`语句的了解，并利用`UPDATE`语句更新记录的单字段和多字段值。

更新数据的核心语法是：
```sql
UPDATE table_name SET column1 = value1 WHERE condition;
```

---

最后，你还通过完成一个从表中删除记录的练习，证明了你在这些新技能方面的能力。

删除数据的核心语法是：
```sql
DELETE FROM table_name WHERE condition;
```

![](img/25c5c916be3b2d2c6264223ed026ef6f_32.png)

![](img/25c5c916be3b2d2c6264223ed026ef6f_33.png)

---

![](img/25c5c916be3b2d2c6264223ed026ef6f_34.png)

## 总结 🎯

本节课中，我们一起学习了数据库的核心CRUD操作。你现在已经熟悉了创建、读取、更新和删除操作，并且熟练掌握了SQL数据类型的使用。

你正在成为一名数据库工程师的道路上稳步前进。