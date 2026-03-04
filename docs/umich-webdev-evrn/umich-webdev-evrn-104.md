# 104：PHP中的CRUD代码详解 🧑‍💻

![](img/664e0683bfe1607ce851355c9f9c5d96_1.png)

在本节课中，我们将详细解析一个PHP的CRUD（增删改查）应用程序。这个应用将数据库操作功能拆分到独立的文件中，并遵循了良好的代码组织实践。我们将从概述开始，逐步分析每个核心文件（`index.php`, `add.php`, `delete.php`, `edit.php`）的功能和代码逻辑。

![](img/664e0683bfe1607ce851355c9f9c5d96_3.png)

## 概述

我们分析的CRUD应用程序实现了对用户数据的基本操作：创建(Create)、读取(Read)、更新(Update)和删除(Delete)。与之前将多个功能混合在单个文件（如`user3.php`）中的做法不同，本应用采用了更清晰的结构，将每个核心操作分离到独立的文件中。这遵循了MVC（模型-视图-控制器）模式的思路，使代码更易于维护和理解。

应用程序的运行依赖于一个名为`misc`的数据库。你需要下载代码并在本地配置好数据库连接才能运行它。数据库的SQL设置说明可以在项目文件夹中找到。

![](img/664e0683bfe1607ce851355c9f9c5d96_5.png)

## 主页面：列表与导航 (`index.php`)

上一节我们介绍了应用的整体结构，本节中我们来看看应用的主入口文件`index.php`。这个文件主要负责显示用户列表并提供导航链接。

`index.php`的模型部分非常简单，它只包含数据库连接和会话启动代码。其核心是视图部分，即生成用户列表的HTML表格。

![](img/664e0683bfe1607ce851355c9f9c5d96_7.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_8.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_9.png)

以下是生成表格和操作链接的关键代码逻辑：

![](img/664e0683bfe1607ce851355c9f9c5d96_11.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_12.png)

```php
// 从数据库获取所有用户数据
$stmt = $pdo->query('SELECT name, email, password, user_id FROM users');
echo '<table border="1">'."\n";
while ($row = $stmt->fetch(PDO::FETCH_ASSOC)) {
    echo "<tr><td>";
    echo htmlentities($row['name']);
    echo "</td><td>";
    echo htmlentities($row['email']);
    echo "</td><td>";
    echo htmlentities($row['password']);
    echo "</td><td>";
    // 编辑链接：通过GET参数传递用户ID
    echo('<a href="edit.php?user_id='.$row['user_id'].'">Edit</a> / ');
    // 删除链接
    echo('<a href="delete.php?user_id='.$row['user_id'].'">Delete</a>');
    echo("</td></tr>\n");
}
```

该文件还实现了“闪现消息”模式，用于在页面重定向后显示一次性的成功或错误提示。其原理是利用`$_SESSION`超全局变量临时存储消息，在页面显示后立即清除。

![](img/664e0683bfe1607ce851355c9f9c5d96_14.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_15.png)

## 创建用户功能 (`add.php`)

![](img/664e0683bfe1607ce851355c9f9c5d96_17.png)

在了解了如何展示数据后，本节我们来看看如何创建新数据。`add.php`文件负责处理新用户的添加。它包含一个表单用于输入用户信息，并包含数据验证逻辑。

![](img/664e0683bfe1607ce851355c9f9c5d96_19.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_21.png)

该文件的结构遵循典型的“控制器”模式：首先处理POST请求（模型/控制器逻辑），然后渲染HTML表单（视图逻辑）。

![](img/664e0683bfe1607ce851355c9f9c5d96_23.png)

以下是处理表单提交和数据验证的核心代码：

![](img/664e0683bfe1607ce851355c9f9c5d96_25.png)

```php
// 检查是否通过POST请求提交了必要的数据
if (isset($_POST['name']) && isset($_POST['email']) && isset($_POST['password'])) {
    // 数据验证1: 检查姓名和密码是否为空
    if (strlen($_POST['name']) < 1 || strlen($_POST['password']) < 1) {
        $_SESSION['error'] = 'Missing data';
        header("Location: add.php");
        return;
    }
    // 数据验证2: 检查邮箱格式是否包含@符号
    if (strpos($_POST['email'], '@') === false) {
        $_SESSION['error'] = 'Bad data';
        header("Location: add.php");
        return;
    }
    // 数据验证通过，执行插入操作
    $sql = "INSERT INTO users (name, email, password) VALUES (:name, :email, :password)";
    $stmt = $pdo->prepare($sql);
    $stmt->execute(array(
        ':name' => $_POST['name'],
        ':email' => $_POST['email'],
        ':password' => $_POST['password']));
    // 设置成功消息并重定向回主页
    $_SESSION['success'] = 'Record Added';
    header('Location: index.php');
    return;
}
```

这种模式被称为“保护式编程”或“提前返回”，即在验证失败时立即终止脚本执行并重定向，避免执行后续可能出错的代码。

![](img/664e0683bfe1607ce851355c9f9c5d96_27.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_28.png)

## 删除用户功能 (`delete.php`)

![](img/664e0683bfe1607ce851355c9f9c5d96_30.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_31.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_33.png)

现在我们已经学会了如何添加数据，接下来看看如何安全地删除数据。`delete.php`文件处理用户的删除操作。为了安全，它包含一个确认页面，并且严格验证传入的用户ID。

删除流程分为两步：
1.  **GET请求**：显示一个确认页面，询问用户是否确定要删除。
2.  **POST请求**：实际执行删除数据库记录的操作。

![](img/664e0683bfe1607ce851355c9f9c5d96_35.png)

以下是该文件的关键步骤：

![](img/664e0683bfe1607ce851355c9f9c5d96_37.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_38.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_39.png)

首先，验证通过链接传递过来的用户ID是否存在且有效。

```php
// 第一步：验证GET参数中的user_id
if (!isset($_GET['user_id'])) {
    $_SESSION['error'] = 'Missing user_id';
    header('Location: index.php');
    return;
}
// 第二步：检查该ID在数据库中是否存在对应的用户
$stmt = $pdo->prepare("SELECT name FROM users WHERE user_id = :xyz");
$stmt->execute(array(":xyz" => $_GET['user_id']));
$row = $stmt->fetch(PDO::FETCH_ASSOC);
if ($row === false) {
    $_SESSION['error'] = 'Bad value for user_id';
    header('Location: index.php');
    return;
}
```

![](img/664e0683bfe1607ce851355c9f9c5d96_41.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_42.png)

如果验证通过，则显示确认页面。注意，这里使用`htmlentities()`函数对用户名进行转义，以防止跨站脚本（XSS）攻击。

![](img/664e0683bfe1607ce851355c9f9c5d96_44.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_45.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_46.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_47.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_48.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_50.png)

```php
// 显示确认删除的视图部分
$n = htmlentities($row['name']);
echo "<p>Confirm: Deleting ".$n."</p>\n";
echo('<form method="post"><input type="hidden" ');
echo('name="user_id" value="'.$_GET['user_id'].'">'."\n");
echo('<input type="submit" value="Delete" name="delete">');
echo('<a href="index.php">Cancel</a>');
echo("\n</form>\n");
```

最后，处理用户确认删除的POST请求。

![](img/664e0683bfe1607ce851355c9f9c5d96_52.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_53.png)

```php
// 第三步：处理确认删除的POST请求
if (isset($_POST['delete']) && isset($_POST['user_id'])) {
    $sql = "DELETE FROM users WHERE user_id = :zip";
    $stmt = $pdo->prepare($sql);
    $stmt->execute(array(':zip' => $_POST['user_id']));
    $_SESSION['success'] = 'Record deleted';
    header('Location: index.php');
    return;
}
```

![](img/664e0683bfe1607ce851355c9f9c5d96_55.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_56.png)

## 更新用户功能 (`edit.php`)

最后，我们来学习如何更新现有数据。`edit.php`文件结合了“读取”和“更新”的功能。它首先根据`user_id`获取并显示用户的当前信息，然后允许用户修改并提交更新。

该文件同样遵循“保护式编程”原则，并使用了预处理语句来防止SQL注入攻击。

![](img/664e0683bfe1607ce851355c9f9c5d96_58.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_59.png)

文件首先验证并获取要编辑的用户信息：

![](img/664e0683bfe1607ce851355c9f9c5d96_61.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_62.png)

```php
// 获取要编辑的用户原始数据
$stmt = $pdo->prepare("SELECT * FROM users WHERE user_id = :xyz");
$stmt->execute(array(":xyz" => $_GET['user_id']));
$row = $stmt->fetch(PDO::FETCH_ASSOC);
if ($row === false) {
    $_SESSION['error'] = 'Bad value for user_id';
    header('Location: index.php');
    return;
}
// 将数据存入变量，并用htmlentities转义以供安全输出
$n = htmlentities($row['name']);
$e = htmlentities($row['email']);
$p = htmlentities($row['password']);
$user_id = $row['user_id'];
```

![](img/664e0683bfe1607ce851355c9f9c5d96_64.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_65.png)

然后，在表单中预填充这些值：

![](img/664e0683bfe1607ce851355c9f9c5d96_67.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_68.png)

```html
<!-- 编辑表单视图部分 -->
<form method="post">
<p>Name: <input type="text" name="name" value="<?= $n ?>"></p>
<p>Email: <input type="text" name="email" value="<?= $e ?>"></p>
<p>Password: <input type="text" name="password" value="<?= $p ?>"></p>
<input type="hidden" name="user_id" value="<?= $user_id ?>">
<p><input type="submit" value="Update"/>
<a href="index.php">Cancel</a></p>
</form>
```

最后，处理表单提交，执行更新操作：

![](img/664e0683bfe1607ce851355c9f9c5d96_70.png)

```php
// 处理更新数据的POST请求
if (isset($_POST['name']) && isset($_POST['email']) && isset($_POST['password']) && isset($_POST['user_id'])) {
    // ... (数据验证逻辑与add.php类似) ...
    // 执行更新
    $sql = "UPDATE users SET name = :name, email = :email, password = :password WHERE user_id = :user_id";
    $stmt = $pdo->prepare($sql);
    $stmt->execute(array(
        ':name' => $_POST['name'],
        ':email' => $_POST['email'],
        ':password' => $_POST['password'],
        ':user_id' => $_POST['user_id']));
    $_SESSION['success'] = 'Record updated';
    header('Location: index.php');
    return;
}
```

## 总结

![](img/664e0683bfe1607ce851355c9f9c5d96_72.png)

本节课中我们一起学习了如何构建一个结构清晰的PHP CRUD应用程序。我们分析了四个核心文件：
*   `index.php`：负责读取和列表显示数据，并提供操作导航。
*   `add.php`：负责创建新数据，包含完整的数据验证和插入逻辑。
*   `delete.php`：负责删除数据，采用两步确认流程以保证操作安全。
*   `edit.php`：负责更新数据，结合了读取原始数据和写入更新数据的功能。

![](img/664e0683bfe1607ce851355c9f9c5d96_74.png)

![](img/664e0683bfe1607ce851355c9f9c5d96_76.png)

整个应用的核心实践包括：
1.  **代码分离**：将不同功能拆分到独立文件，提高可维护性。
2.  **POST-Redirect-GET (PRG) 模式**：防止表单重复提交，并提供清晰的用户反馈。
3.  **闪现消息**：利用会话在重定向间传递一次性状态信息。
4.  **数据验证与保护式编程**：在执行任何操作前严格检查输入数据的有效性和完整性。
5.  **安全防护**：使用预处理语句（`prepare` / `execute`）防止SQL注入，使用`htmlentities()`防止XSS攻击。

![](img/664e0683bfe1607ce851355c9f9c5d96_78.png)

这个CRUD应用虽然功能基础，但它展示了构建安全、健壮Web应用程序的最佳实践和代码组织模式，为开发更复杂的应用打下了坚实的基础。