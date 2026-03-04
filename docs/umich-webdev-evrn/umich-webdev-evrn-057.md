# 057：基本SQL操作 🗄️

![](img/9d699c11935ccd8a7d343c43328daf96_0.png)

![](img/9d699c11935ccd8a7d343c43328daf96_1.png)

在本节课中，我们将学习SQL（结构化查询语言）的基础知识。SQL是用于与数据库服务器通信的语言，它允许我们创建、读取、更新和删除数据。我们将从理解请求-响应周期中SQL的角色开始，然后学习如何通过命令行和图形化工具（如phpMyAdmin）与数据库交互，并最终掌握执行基本CRUD操作的核心SQL命令。

## 请求-响应周期中的SQL

上一节我们介绍了Web应用的基本架构，本节中我们来看看SQL在其中扮演的具体角色。

在典型的Web请求-响应周期中，浏览器向Web服务器发送HTTP请求。服务器可能运行PHP代码，而PHP代码需要与数据库服务器通信。这时，SQL就作为通信语言被发送到数据库服务器。数据库服务器处理SQL指令，找到所需数据，并将其返回给PHP。PHP处理这些数据并生成HTML，最终作为响应发送回浏览器，由浏览器解析并呈现给用户。

![](img/9d699c11935ccd8a7d343c43328daf96_3.png)

对于本讲座，我们的重点是学习在网络中来回流动的SQL语言。通常，浏览器、Web服务器和数据库服务器可能运行在三台独立的机器上，但在开发环境中，它们可以共存于一台机器。

## 数据库服务器与客户端

我们即将使用的数据库服务器软件（如MySQL）功能强大且高度优化。我们从不直接操作其底层数据文件，而是通过发送SQL命令来指挥它工作。这个服务器可以同时处理来自多个客户端的请求。

在开发或生产环境中，开发者通常不直接操作数据库。但为了学习，我们将扮演拥有全部权限的**数据库管理员**角色。

![](img/9d699c11935ccd8a7d343c43328daf96_5.png)

## 设置开发环境

![](img/9d699c11935ccd8a7d343c43328daf96_7.png)

在开始之前，你需要安装一个集成了Web服务器、PHP和MySQL的开发环境，例如XAMPP（Windows）、MAMP（Mac）或LAMP（Linux）。这能为你节省大量配置时间。

## 与数据库交互的两种方式

![](img/9d699c11935ccd8a7d343c43328daf96_9.png)

以下是两种与MySQL数据库服务器交互的主要方式。

### 命令行界面

命令行是与服务器（尤其是Linux服务器）交互的重要技能。虽然本课程不会深入讲解，但了解其基本用法很有帮助。你可以通过终端登录到MySQL服务器并执行命令。

### phpMyAdmin图形界面

对于软件开发，我们更常使用phpMyAdmin这类图形化管理工具。它是一个被广泛用于生产环境数据库管理的Web应用程序，功能强大且实用。我们将主要使用它来学习SQL。

**重要提示**：无论是命令行还是phpMyAdmin，它们都只是**客户端**。它们连接到同一个数据库服务器并发送SQL命令。在一个客户端所做的更改（如删除数据库）会立即反映在另一个客户端上，这演示了多个客户端可以同时与一个数据库服务器交互。

## 创建数据库和表

现在，我们开始使用SQL进行实际操作。首先需要创建一个数据库，然后在其中创建数据表。

### 创建数据库

我们使用 `CREATE DATABASE` 语句来创建一个新数据库。指定字符集（如 `utf8`）是一个好习惯，它能确保数据库支持非拉丁字符（如中文、希腊文）。

```sql
CREATE DATABASE people DEFAULT CHARACTER SET utf8;
```

### 创建表

![](img/9d699c11935ccd8a7d343c43328daf96_11.png)

数据库创建后，我们使用 `CREATE TABLE` 语句在其中创建表。这相当于定义电子表格的列（字段）。我们需要为每个字段指定精确的数据类型和约束。

![](img/9d699c11935ccd8a7d343c43328daf96_13.png)

![](img/9d699c11935ccd8a7d343c43328daf96_14.png)

![](img/9d699c11935ccd8a7d343c43328daf96_15.png)

例如，创建一个 `users` 表，包含 `name` 和 `email` 两个字段，它们都是最大长度为128字符的变长字符串（`VARCHAR`）。

![](img/9d699c11935ccd8a7d343c43328daf96_17.png)

```sql
CREATE TABLE users (
    name VARCHAR(128),
    email VARCHAR(128)
);
```

![](img/9d699c11935ccd8a7d343c43328daf96_19.png)

定义字段长度（如128）是与数据库服务器建立的一种“契约”，它有助于优化存储效率。服务器知道无需为超过此长度的数据预留空间。

![](img/9d699c11935ccd8a7d343c43328daf96_21.png)

### 查看表结构

创建表后，可以使用 `DESCRIBE` 命令查看其结构。

![](img/9d699c11935ccd8a7d343c43328daf96_23.png)

![](img/9d699c11935ccd8a7d343c43328daf96_24.png)

```sql
DESCRIBE users;
```

此命令会列出表中的所有字段及其数据类型、是否允许为空等属性。

## 基本CRUD操作

CRUD代表创建（Create）、读取（Read）、更新（Update）和删除（Delete），这是操作数据的四种基本方式。我们已经完成了“创建”（建表），接下来学习其余三种。

### 插入数据（Create）

![](img/9d699c11935ccd8a7d343c43328daf96_26.png)

使用 `INSERT INTO` 语句向表中添加新行。

![](img/9d699c11935ccd8a7d343c43328daf96_28.png)

![](img/9d699c11935ccd8a7d343c43328daf96_30.png)

```sql
INSERT INTO users (name, email) VALUES ('Chuck', 'csev@umich.edu');
```

可以一次性执行多条插入语句，只需用分号分隔。

![](img/9d699c11935ccd8a7d343c43328daf96_32.png)

### 删除数据（Delete）

![](img/9d699c11935ccd8a7d343c43328daf96_34.png)

![](img/9d699c11935ccd8a7d343c43328daf96_36.png)

使用 `DELETE FROM` 语句从表中删除行。通常需要结合 `WHERE` 子句来指定删除哪些行，否则将删除表中的所有数据。

```sql
DELETE FROM users WHERE email = 'ted@umich.edu';
```

![](img/9d699c11935ccd8a7d343c43328daf96_38.png)

`WHERE` 子句就像一个循环中的 `if` 条件，它让操作只应用于满足条件的记录。

### 更新数据（Update）

使用 `UPDATE` 语句修改表中现有的数据。同样，需要使用 `SET` 指定要更改的列和新值，并用 `WHERE` 子句限定范围。

![](img/9d699c11935ccd8a7d343c43328daf96_40.png)

```sql
UPDATE users SET name = 'Charles' WHERE email = 'csev@umich.edu';
```

### 查询数据（Read）

使用 `SELECT` 语句从表中读取数据，这是最常用的操作。

![](img/9d699c11935ccd8a7d343c43328daf96_42.png)

*   **查询所有列和所有行**：
    ```sql
    SELECT * FROM users;
    ```
    `*` 是通配符，代表所有列。

![](img/9d699c11935ccd8a7d343c43328daf96_44.png)

*   **带条件的查询**：
    ```sql
    SELECT * FROM users WHERE email = 'csev@umich.edu';
    ```

![](img/9d699c11935ccd8a7d343c43328daf96_46.png)

*   **查询不存在的记录**：如果 `WHERE` 条件没有匹配任何行，查询将返回空结果集，这本身并不是错误。

![](img/9d699c11935ccd8a7d343c43328daf96_48.png)

## 高级查询功能

![](img/9d699c11935ccd8a7d343c43328daf96_50.png)

`SELECT` 语句非常灵活，支持许多用于处理和筛选数据的功能。

### 结果排序

![](img/9d699c11935ccd8a7d343c43328daf96_52.png)

使用 `ORDER BY` 子句可以按指定字段对结果进行排序。

```sql
SELECT * FROM users ORDER BY email;
```

### 模糊查询

使用 `LIKE` 操作符和通配符 `%` 进行模式匹配。`%` 代表任意数量的任意字符。

```sql
SELECT * FROM users WHERE name LIKE '%e%';
```
这条语句会查找 `name` 字段中包含字母 ‘e’ 的所有记录。

![](img/9d699c11935ccd8a7d343c43328daf96_54.png)

![](img/9d699c11935ccd8a7d343c43328daf96_56.png)

### 计数

![](img/9d699c11935ccd8a7d343c43328daf96_58.png)

使用 `COUNT()` 函数可以获取匹配的行数，而不返回实际数据。

![](img/9d699c11935ccd8a7d343c43328daf96_60.png)

```sql
SELECT COUNT(*) FROM users;
```
这将返回 `users` 表中的总记录数。

### 限制结果数量

![](img/9d699c11935ccd8a7d343c43328daf96_62.png)

使用 `LIMIT` 子句可以限制返回的行数，常用于分页。

![](img/9d699c11935ccd8a7d343c43328daf96_64.png)

```sql
SELECT * FROM users LIMIT 10;
```

![](img/9d699c11935ccd8a7d343c43328daf96_66.png)

## 总结

![](img/9d699c11935ccd8a7d343c43328daf96_68.png)

本节课中我们一起学习了SQL的基础知识。我们了解了SQL在Web应用架构中的位置，学会了通过命令行和phpMyAdmin与MySQL数据库服务器交互。我们掌握了执行基本CRUD操作的核心SQL语句：
*   **创建**：`CREATE DATABASE`, `CREATE TABLE`, `INSERT INTO`
*   **读取**：`SELECT` （结合 `WHERE`, `ORDER BY`, `LIKE`, `COUNT`, `LIMIT`）
*   **更新**：`UPDATE`
*   **删除**：`DELETE FROM`

![](img/9d699c11935ccd8a7d343c43328daf96_70.png)

这些操作构成了SQL的一半核心内容。它们让你能够在一个数据表内高效地管理数据。在接下来的课程中，我们将探索如何建立多个表之间的关系，并通过连接（JOIN）等操作在这些表之间进行更复杂和强大的数据查询，这才是数据库真正发挥威力的地方。