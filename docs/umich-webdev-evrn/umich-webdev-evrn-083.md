# 083：在PHP中执行SQL查询

![](img/658ef70728af55a6398f8e410f93fb18_0.png)

![](img/658ef70728af55a6398f8e410f93fb18_1.png)

在本节课中，我们将学习如何从PHP代码内部连接到MySQL数据库，并执行SQL查询来读取和插入数据。我们将从建立数据库连接开始，然后学习如何执行`SELECT`和`INSERT`语句，并将数据库中的数据格式化为HTML输出。

![](img/658ef70728af55a6398f8e410f93fb18_3.png)

## 概述：建立数据库与连接

上一节我们介绍了SQL的基础知识。本节中，我们来看看如何从PHP程序内部与数据库进行交互。首先，我们需要创建一个数据库、一个用户账户，并建立PHP到数据库的连接。

### 创建数据库和用户

在开始编写PHP代码之前，必须在MySQL服务器上设置好数据库。这通常通过命令行或phpMyAdmin等工具完成。

以下是创建数据库和用户账户的SQL命令示例：

```sql
CREATE DATABASE misc;
GRANT ALL ON misc.* TO 'fred'@'localhost' IDENTIFIED BY 'zap';
GRANT ALL ON misc.* TO 'fred'@'127.0.0.1' IDENTIFIED BY 'zap';
```

**核心概念解释**：
*   `CREATE DATABASE misc;`：创建一个名为`misc`的新数据库。
*   `GRANT ALL ...`：授予用户`fred`从特定主机（`localhost`或`127.0.0.1`）连接到`misc`数据库的所有权限，并设置密码为`zap`。
*   限制连接源（如`localhost`）是一种安全措施，它像一个防火墙，只允许来自同一台计算机内部的连接访问数据库，阻止外部网络的直接访问。

### 理解数据库连接

数据库服务器运行在计算机的特定网络端口上。MySQL的默认端口是3306。在PHP中，我们需要提供主机地址、端口号、数据库名、用户名和密码来建立连接。

对于运行MAMP的Mac用户，MySQL端口通常是8889。因此，连接信息会因开发环境而异。

## 在PHP中建立数据库连接

现在，我们进入PHP部分，学习如何用代码建立到MySQL的连接。

![](img/658ef70728af55a6398f8e410f93fb18_5.png)

### 使用PDO进行连接

![](img/658ef70728af55a6398f8e410f93fb18_6.png)

PHP Data Objects (PDO) 提供了一个统一的接口来连接和操作多种数据库。以下是建立连接的基本代码：

![](img/658ef70728af55a6398f8e410f93fb18_8.png)

```php
$pdo = new PDO('mysql:host=localhost;port=8889;dbname=misc',
               'fred', 'zap');
```

![](img/658ef70728af55a6398f8e410f93fb18_10.png)

**代码解析**：
*   `new PDO(...)`：创建一个新的PDO对象，即数据库连接。
*   `mysql:host=localhost;port=8889;dbname=misc`：这是数据源名称(DSN)，指定了数据库类型(`mysql`)、主机(`localhost`)、端口(`8889`)和数据库名(`misc`)。
*   `'fred', 'zap'`：连接所用的用户名和密码。

如果连接信息（如密码、端口）错误，这行代码将产生错误并终止脚本。正确配置连接通常是初学阶段最具挑战性的一步。

### 设置错误模式

为了在开发过程中更容易地调试错误，建议将PDO的错误模式设置为“异常模式”。这样，当SQL执行出错时，PDO会抛出异常，而不是静默失败。

```php
$pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
```

## 执行SELECT查询并读取数据

成功建立连接后，我们就可以执行SQL查询了。首先从读取数据开始。

![](img/658ef70728af55a6398f8e410f93fb18_12.png)

![](img/658ef70728af55a6398f8e410f93fb18_13.png)

### 发送查询并获取结果

以下代码演示了如何执行一个`SELECT`查询并遍历所有返回的结果行：

```php
$stmt = $pdo->query("SELECT * FROM users");
while ( $row = $stmt->fetch(PDO::FETCH_ASSOC) ) {
    print_r($row);
}
```

**代码解析**：
1.  `$pdo->query("SELECT * FROM users")`：通过连接对象`$pdo`的`query`方法，向数据库发送一个SQL查询字符串。返回的结果是一个PDOStatement对象，我们将其存储在`$stmt`变量中。
2.  `$stmt->fetch(PDO::FETCH_ASSOC)`：从结果集中获取下一行数据。`PDO::FETCH_ASSOC`参数指定以关联数组的形式返回数据，数组的键是数据库的列名（如`user_id`, `name`）。
3.  `while`循环会持续执行，直到`fetch`方法没有更多数据可返回（返回`false`）为止。
4.  `print_r($row)`：打印出每一行的数组内容。

![](img/658ef70728af55a6398f8e410f93fb18_15.png)

![](img/658ef70728af55a6398f8e410f93fb18_16.png)

![](img/658ef70728af55a6398f8e410f93fb18_17.png)

![](img/658ef70728af55a6398f8e410f93fb18_18.png)

### 将数据格式化为HTML输出

通常，我们不会直接打印原始数据，而是将其格式化为美观的HTML呈现给用户。

以下是如何将查询结果转换为一个HTML表格的示例：

```php
echo "<table border='1'>\n";
$stmt = $pdo->query("SELECT name, email FROM users");
while ( $row = $stmt->fetch(PDO::FETCH_ASSOC) ) {
    echo "<tr><td>";
    echo htmlentities($row['name']);
    echo "</td><td>";
    echo htmlentities($row['email']);
    echo "</td></tr>\n";
}
echo "</table>\n";
```

**代码解析**：
*   首先输出HTML表格的开始标签。
*   执行一个更具体的查询，只选择`name`和`email`列。
*   在循环中，为每一行数据输出HTML表格行(`<tr>`)和单元格(`<td>`)。
*   `htmlentities()`函数用于将数据中的特殊字符转换为HTML实体，这是一种重要的安全措施，可以防止跨站脚本(XSS)攻击。
*   最后输出表格的结束标签。

这个过程本质上是将数据库中的数据转换并格式化为HTML代码。

## 代码组织：分离连接配置

在一个拥有多个PHP脚本的网站中，每个脚本都需要数据库连接。为了避免在多个文件中重复编写连接代码，最佳实践是将连接配置放在一个单独的文件中，然后在其他文件中引入它。

### 创建独立的连接文件

创建一个名为`pdo.php`的文件，内容如下：

```php
<?php
$pdo = new PDO('mysql:host=localhost;port=8889;dbname=misc',
               'fred', 'zap');
$pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
?>
```

### 在其他脚本中引入连接

在需要使用数据库的脚本中，使用`require_once`语句引入这个连接文件：

```php
<?php
require_once "pdo.php";
// 现在可以直接使用 $pdo 变量来执行查询
$stmt = $pdo->query("SELECT * FROM users");
...
?>
```

![](img/658ef70728af55a6398f8e410f93fb18_20.png)

这种方法使代码更易于维护。如果需要修改数据库密码或主机名，只需更新`pdo.php`一个文件即可。

![](img/658ef70728af55a6398f8e410f93fb18_22.png)

## 执行INSERT查询

除了读取数据，我们同样需要通过PHP向数据库插入新数据。

### 使用PDO执行INSERT

执行`INSERT`、`UPDATE`、`DELETE`等不返回数据行的操作，通常使用`exec`方法或预处理语句。一个简单的插入示例如下：

```php
$pdo->exec("INSERT INTO users (name, email, password)
            VALUES ('John', 'john@example.com', 'secret')");
```

**注意**：直接将变量值拼接进SQL字符串（如上例）在实践中非常危险，容易导致SQL注入攻击。在生产环境中，**必须使用预处理语句（Prepared Statements）**来安全地处理用户输入的数据。我们将在后续课程中详细讲解预处理语句。

## 总结

本节课中我们一起学习了PHP与MySQL数据库交互的核心步骤：
1.  **建立连接**：使用PDO对象，并提供正确的主机、端口、数据库名、用户名和密码。
2.  **执行查询**：使用`query()`方法执行`SELECT`查询，使用`exec()`方法执行`INSERT`等操作（注意安全风险）。
3.  **处理结果**：使用`fetch(PDO::FETCH_ASSOC)`在循环中遍历`SELECT`查询返回的数据行，并以关联数组形式访问每一列。
4.  **格式化输出**：将获取到的数据库数据嵌入到HTML代码中，生成用户可见的网页内容。
5.  **组织代码**：将数据库连接配置分离到独立文件中，通过`require_once`引入，提高代码的可维护性。

![](img/658ef70728af55a6398f8e410f93fb18_24.png)

![](img/658ef70728af55a6398f8e410f93fb18_26.png)

掌握这些基础是构建动态Web应用的关键。下一节，我们将深入探讨如何使用更安全的预处理语句来执行SQL命令。