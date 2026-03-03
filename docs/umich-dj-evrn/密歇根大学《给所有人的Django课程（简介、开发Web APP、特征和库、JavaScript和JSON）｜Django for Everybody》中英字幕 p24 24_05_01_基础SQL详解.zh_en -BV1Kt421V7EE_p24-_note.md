# Django for Everybody：24：基础SQL详解 🗃️

在本节课中，我们将学习SQL的基础知识，包括如何创建表、插入数据、查询、更新和删除数据。我们将使用SQLite数据库进行实际操作，帮助你理解SQL的核心概念和基本操作。

## 概述

![](img/2d1d73e28d58091b47f988aa622337d3_1.png)

SQL（结构化查询语言）是用于管理和操作关系型数据库的标准语言。本节将介绍SQL的基本操作，包括创建表、插入数据、查询数据、更新数据和删除数据。我们将通过实际操作演示这些命令的使用方法。

![](img/2d1d73e28d58091b47f988aa622337d3_3.png)

## 环境准备

![](img/2d1d73e28d58091b47f988aa622337d3_4.png)

首先，我们需要在Linux环境中使用SQLite数据库。SQLite是一个轻量级的数据库，它将所有数据存储在一个文件中，非常适合学习和开发。

```bash
sqlite3 test.sqlite3
```

![](img/2d1d73e28d58091b47f988aa622337d3_6.png)

运行上述命令后，你将进入SQLite的命令行界面。可以输入`.help`查看可用的命令。

![](img/2d1d73e28d58091b47f988aa622337d3_8.png)

## 创建表

在SQL中，我们使用`CREATE TABLE`语句来创建新表。表由列组成，每列都有特定的数据类型。

以下是创建`users`表的SQL语句：

```sql
CREATE TABLE users (
    name TEXT,
    email TEXT
);
```

执行上述命令后，可以使用`.tables`命令查看当前数据库中的所有表。使用`.schema users`命令可以查看`users`表的结构。

![](img/2d1d73e28d58091b47f988aa622337d3_10.png)

![](img/2d1d73e28d58091b47f988aa622337d3_11.png)

## 插入数据

![](img/2d1d73e28d58091b47f988aa622337d3_12.png)

![](img/2d1d73e28d58091b47f988aa622337d3_13.png)

创建表后，我们需要向表中插入数据。使用`INSERT INTO`语句可以向表中添加新记录。

以下是向`users`表插入数据的示例：

![](img/2d1d73e28d58091b47f988aa622337d3_15.png)

```sql
INSERT INTO users (name, email) VALUES ('Kristen', 'kf@u.edu');
```

![](img/2d1d73e28d58091b47f988aa622337d3_17.png)

插入数据后，可以使用`SELECT * FROM users;`查询表中的所有记录。

![](img/2d1d73e28d58091b47f988aa622337d3_18.png)

![](img/2d1d73e28d58091b47f988aa622337d3_20.png)

## 查询数据

查询数据是SQL中最常用的操作之一。使用`SELECT`语句可以从表中检索数据。

以下是查询`users`表中所有记录的示例：

```sql
SELECT * FROM users;
```

![](img/2d1d73e28d58091b47f988aa622337d3_22.png)

如果需要按特定条件查询数据，可以使用`WHERE`子句。例如，查询邮箱为`csev@umich.edu`的记录：

```sql
SELECT * FROM users WHERE email = 'csev@umich.edu';
```

![](img/2d1d73e28d58091b47f988aa622337d3_24.png)

![](img/2d1d73e28d58091b47f988aa622337d3_25.png)

## 更新数据

如果需要修改表中的数据，可以使用`UPDATE`语句。注意，`UPDATE`语句通常需要配合`WHERE`子句使用，以避免更新所有记录。

以下是更新`users`表中特定记录的示例：

![](img/2d1d73e28d58091b47f988aa622337d3_27.png)

```sql
UPDATE users SET name = 'Charles' WHERE email = 'csev@umich.edu';
```

![](img/2d1d73e28d58091b47f988aa622337d3_29.png)

如果不使用`WHERE`子句，`UPDATE`语句将更新表中的所有记录。

![](img/2d1d73e28d58091b47f988aa622337d3_31.png)

## 删除数据

![](img/2d1d73e28d58091b47f988aa622337d3_33.png)

删除数据使用`DELETE`语句。与`UPDATE`类似，`DELETE`语句通常需要配合`WHERE`子句使用，以避免删除所有记录。

以下是删除`users`表中特定记录的示例：

```sql
DELETE FROM users WHERE email = 'ted@umich.edu';
```

![](img/2d1d73e28d58091b47f988aa622337d3_35.png)

![](img/2d1d73e28d58091b47f988aa622337d3_36.png)

如果不使用`WHERE`子句，`DELETE`语句将删除表中的所有记录。

## 排序数据

使用`ORDER BY`子句可以对查询结果进行排序。默认按升序排序，如果需要降序排序，可以添加`DESC`关键字。

以下是按邮箱升序排序的示例：

![](img/2d1d73e28d58091b47f988aa622337d3_38.png)

![](img/2d1d73e28d58091b47f988aa622337d3_39.png)

![](img/2d1d73e28d58091b47f988aa622337d3_40.png)

```sql
SELECT * FROM users ORDER BY email;
```

![](img/2d1d73e28d58091b47f988aa622337d3_41.png)

![](img/2d1d73e28d58091b47f988aa622337d3_42.png)

![](img/2d1d73e28d58091b47f988aa622337d3_43.png)

以下是按姓名降序排序的示例：

```sql
SELECT * FROM users ORDER BY name DESC;
```

![](img/2d1d73e28d58091b47f988aa622337d3_45.png)

## 删除表

如果需要删除整个表，可以使用`DROP TABLE`语句。

以下是删除`users`表的示例：

```sql
DROP TABLE users;
```

执行该命令后，`users`表及其所有数据将被永久删除。

![](img/2d1d73e28d58091b47f988aa622337d3_47.png)

## 总结

![](img/2d1d73e28d58091b47f988aa622337d3_49.png)

本节课我们一起学习了SQL的基础操作，包括创建表、插入数据、查询数据、更新数据和删除数据。通过实际操作，我们掌握了SQL的核心命令及其使用方法。SQL是数据库操作的基础，熟练掌握这些操作对于后续学习Django和Web开发至关重要。希望本节课的内容对你有所帮助！