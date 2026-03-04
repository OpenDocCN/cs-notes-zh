# 面向所有人的Web应用程序：17：PHP MySQL与PDO代码详解 🧑‍💻

在本节课中，我们将详细学习如何使用PHP的PDO扩展来连接和操作MySQL数据库。我们将从环境准备开始，逐步讲解建立连接、执行查询、处理结果以及优化代码结构。

## 概述

![](img/61c6fbfbca3e8a551df9e832a9bafe67_1.png)

本节教程将引导你完成使用PDO进行数据库操作的全过程。我们将首先设置必要的数据库环境，然后通过多个代码示例，演示如何连接数据库、执行SQL查询、处理返回的数据，以及如何组织代码以提高安全性和可维护性。

---

### 环境准备与数据库设置

![](img/61c6fbfbca3e8a551df9e832a9bafe67_3.png)

上一节概述了课程目标，本节中我们来看看如何为PDO示例准备运行环境。由于操作需要本地数据库支持，你必须下载并配置相关文件。

首先，你需要下载课程提供的 `pdo.zip` 文件，并将其解压到本地Web服务器的根目录（例如 `htdocs`）下，以便通过本地主机（localhost）访问这些文件。

以下是设置数据库的具体步骤：

1.  **创建数据库**：使用SQL命令创建一个名为 `misc` 的数据库。
    ```sql
    CREATE DATABASE misc;
    ```

2.  **创建用户并授权**：创建一个用户 `fred`，密码为 `zap`，并授予其访问 `misc` 数据库的权限。
    ```sql
    CREATE USER 'fred'@'localhost' IDENTIFIED BY 'zap';
    GRANT ALL ON misc.* TO 'fred'@'localhost';
    ```

3.  **创建数据表**：在 `misc` 数据库中创建 `users` 表。
    ```sql
    USE misc;
    CREATE TABLE users (
        user_id INT AUTO_INCREMENT,
        name VARCHAR(128),
        email VARCHAR(128),
        password VARCHAR(128),
        PRIMARY KEY(user_id),
        INDEX(email)
    ) ENGINE=InnoDB DEFAULT CHARSET=utf8;
    ```

4.  **插入测试数据**：向表中插入两条示例用户记录。
    ```sql
    INSERT INTO users (name, email, password) VALUES ('Chuck', 'csev@umich.edu', '123');
    INSERT INTO users (name, email, password) VALUES ('Glenn', 'glenn@umich.edu', '456');
    ```

![](img/61c6fbfbca3e8a551df9e832a9bafe67_5.png)

完成以上步骤后，你的本地数据库中就准备好了可供PDO连接和查询的数据。

---

### 建立PDO数据库连接

环境准备好后，我们现在来看看如何使用PDO建立与MySQL数据库的连接。这是所有数据库操作的第一步。

核心操作是实例化一个PDO对象。其构造函数需要三个主要参数：

![](img/61c6fbfbca3e8a551df9e832a9bafe67_7.png)

![](img/61c6fbfbca3e8a551df9e832a9bafe67_8.png)

*   **数据源名称（DSN）**：一个连接字符串，指定数据库类型、主机地址、端口和数据库名。
*   **用户名**：用于连接数据库的账户名。
*   **密码**：对应用户的密码。

![](img/61c6fbfbca3e8a551df9e832a9bafe67_10.png)

以下代码展示了如何建立连接：

```php
<?php
$pdo = new PDO('mysql:host=localhost;port=3306;dbname=misc',
               'fred',
               'zap');
?>
```

**代码解释**：
*   `mysql:` 指定我们使用MySQL数据库驱动。
*   `host=localhost` 表示数据库服务器位于本机。
*   `port=3306` 是MySQL默认端口（根据你的环境调整，如XAMPP可能是3306）。
*   `dbname=misc` 指定要连接的数据库名称。
*   `'fred'` 和 `'zap'` 是之前创建的用户名和密码。

![](img/61c6fbfbca3e8a551df9e832a9bafe67_12.png)

如果连接信息（如密码）错误，实例化PDO对象时会抛出异常，导致脚本终止。因此，确保这些信息正确是调试的第一步。

---

![](img/61c6fbfbca3e8a551df9e832a9bafe67_14.png)

### 执行查询与遍历结果

![](img/61c6fbfbca3e8a551df9e832a9bafe67_16.png)

成功连接数据库后，本节我们来看看如何执行SQL查询并处理返回的结果集。

使用连接对象的 `query()` 方法可以执行SQL语句。查询结果会返回一个 `PDOStatement` 对象，我们可以通过它来获取数据。

以下是查询并遍历所有用户记录的示例：

```php
<?php
$stmt = $pdo->query("SELECT * FROM users");
while ( $row = $stmt->fetch(PDO::FETCH_ASSOC) ) {
    print_r($row);
}
?>
```

![](img/61c6fbfbca3e8a551df9e832a9bafe67_18.png)

![](img/61c6fbfbca3e8a551df9e832a9bafe67_19.png)

**代码解释**：
1.  `$pdo->query("SELECT * FROM users")` 执行SQL查询，并将结果集赋值给 `$stmt`。
2.  `while ( $row = $stmt->fetch(PDO::FETCH_ASSOC) )` 是一个循环。
    *   `$stmt->fetch(PDO::FETCH_ASSOC)` 方法每次从结果集中取出一行数据。
    *   `PDO::FETCH_ASSOC` 参数指定将行数据作为关联数组返回，数组的键是数据库表的列名（如 `user_id`, `name`）。
    *   当没有更多行可获取时，`fetch()` 返回 `false`，循环结束。
3.  `print_r($row)` 打印出每一行的数据。

![](img/61c6fbfbca3e8a551df9e832a9bafe67_21.png)

运行这段代码，你将看到两个用户的详细信息以数组形式输出。

---

![](img/61c6fbfbca3e8a551df9e832a9bafe67_23.png)

![](img/61c6fbfbca3e8a551df9e832a9bafe67_24.png)

### 将数据渲染为HTML表格

![](img/61c6fbfbca3e8a551df9e832a9bafe67_26.png)

直接打印数组对用户不友好。本节我们学习如何将从数据库获取的数据格式化为美观的HTML页面。

我们可以修改循环体内的代码，用echo语句生成HTML标签，从而将数据嵌入到一个表格中。

![](img/61c6fbfbca3e8a551df9e832a9bafe67_28.png)

```php
<?php
echo '<table border="1">'."\n";
$stmt = $pdo->query("SELECT * FROM users");
while ( $row = $stmt->fetch(PDO::FETCH_ASSOC) ) {
    echo "<tr><td>";
    echo htmlentities($row['user_id']);
    echo "</td><td>";
    echo htmlentities($row['name']);
    echo "</td><td>";
    echo htmlentities($row['email']);
    echo "</td></tr>\n";
}
echo "</table>\n";
?>
```

![](img/61c6fbfbca3e8a551df9e832a9bafe67_29.png)

![](img/61c6fbfbca3e8a551df9e832a9bafe67_30.png)

**代码解释**：
*   在循环中，我们不再使用 `print_r`，而是通过 `echo` 拼接出HTML的 `<tr>`（行）和 `<td>`（单元格）标签。
*   `htmlentities($row['name'])` 函数用于将数据中的特殊字符转换为HTML实体，这是一种重要的安全措施，可以防止跨站脚本（XSS）攻击。
*   最终，这段代码会生成一个包含所有用户数据的HTML表格。

![](img/61c6fbfbca3e8a551df9e832a9bafe67_32.png)

---

![](img/61c6fbfbca3e8a551df9e832a9bafe67_33.png)

![](img/61c6fbfbca3e8a551df9e832a9bafe67_35.png)

### 代码重构与安全优化

将数据库连接信息硬编码在每个PHP文件中是一种糟糕的做法。本节我们来看看如何通过代码重构来提高安全性和可维护性。

![](img/61c6fbfbca3e8a551df9e832a9bafe67_37.png)

最佳实践是将数据库连接代码单独放在一个配置文件中，然后在需要的页面中引入（`require`）它。这样便于统一管理密码，也减少了代码重复。

**1. 创建配置文件 (`pdo.php`)**:

![](img/61c6fbfbca3e8a551df9e832a9bafe67_39.png)

```php
<?php
$pdo = new PDO('mysql:host=localhost;port=3306;dbname=misc',
               'fred',
               'zap');
$pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
?>
```

**代码解释**：
*   `$pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);` 这行代码设置了PDO的错误处理模式。`PDO::ERRMODE_EXCEPTION` 表示当发生错误时，PDO会抛出异常。这比默认的静默模式更有利于调试。

**2. 在主文件中引入配置并查询**:

![](img/61c6fbfbca3e8a551df9e832a9bafe67_41.png)

```php
<?php
require_once "pdo.php"; // 引入数据库连接
$stmt = $pdo->query("SELECT * FROM users");
// ... 后续处理数据的代码
?>
```

![](img/61c6fbfbca3e8a551df9e832a9bafe67_42.png)

通过这种方式，数据库凭证只存在于 `pdo.php` 这一个文件中。如果网站有上百个文件需要数据库连接，你只需修改这一个配置文件即可。即使Web目录被部分访问，数据库密码也不容易泄露。

---

## 总结

本节课中我们一起学习了PHP PDO操作MySQL数据库的核心流程。

我们首先完成了本地数据库环境的搭建，然后深入讲解了**建立PDO连接**的关键代码。接着，我们学习了如何使用 `query()` 方法**执行SQL查询**，并通过 `fetch(PDO::FETCH_ASSOC)` 在循环中**遍历和访问结果集**。之后，我们将数据动态生成**HTML表格**，使结果更直观。最后，我们探讨了通过代码**重构**，将连接配置分离到独立文件的最佳实践，这极大地提升了代码的安全性和可维护性。

![](img/61c6fbfbca3e8a551df9e832a9bafe67_44.png)

![](img/61c6fbfbca3e8a551df9e832a9bafe67_45.png)

记住，成功的PDO操作始于正确的连接参数，而清晰的结构化代码是构建稳健Web应用的基础。