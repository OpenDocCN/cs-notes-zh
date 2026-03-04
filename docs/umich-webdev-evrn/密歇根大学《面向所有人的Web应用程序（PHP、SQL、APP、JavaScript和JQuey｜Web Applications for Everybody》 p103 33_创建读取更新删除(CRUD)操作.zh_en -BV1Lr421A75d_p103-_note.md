# 面向所有人的Web应用程序：第33讲：创建读取更新删除(CRUD)操作 🛠️

![](img/782befdaf5e37b3291ea18610247b509_0.png)

![](img/782befdaf5e37b3291ea18610247b509_1.png)

![](img/782befdaf5e37b3291ea18610247b509_3.png)

![](img/782befdaf5e37b3291ea18610247b509_5.png)

在本节课中，我们将整合之前所学的PHP、SQL、重定向等技术，构建一个经典的CRUD（创建、读取、更新、删除）应用程序。我们将重构代码，将其拆分为多个职责单一的文件，并实现完整的POST重定向和闪存消息机制。

![](img/782befdaf5e37b3291ea18610247b509_7.png)

---

![](img/782befdaf5e37b3291ea18610247b509_9.png)

## 概述 📋

![](img/782befdaf5e37b3291ea18610247b509_11.png)

到目前为止，我们已经学习了PHP、SQL、重定向等知识。现在，我们将把这些知识整合起来，构建一个标准的CRUD应用程序。这个应用程序将围绕一个数据库表，实现数据的创建、读取、更新和删除功能。我们将重构现有代码，将其拆分为多个文件，并确保使用正确的POST重定向和闪存消息模式。

---

![](img/782befdaf5e37b3291ea18610247b509_13.png)

## 应用程序架构 🏗️

![](img/782befdaf5e37b3291ea18610247b509_15.png)

上一节我们介绍了构建CRUD应用的目标，本节中我们来看看具体的文件结构。我们将创建4到5个文件，并将它们放在一个名为`crud`的文件夹中。

以下是主要文件及其功能：
*   **`index.php`**：主页面，显示所有记录的列表。
*   **`add.php`**：用于添加新记录的页面。
*   **`delete.php`**：用于删除记录的页面。
*   **`edit.php`**：用于编辑现有记录的页面。
*   **`pdo.php`**：用于建立数据库连接的公共文件。

`index.php`是应用程序的起点。它将显示数据列表，并为每条记录提供“编辑”和“删除”链接。这些链接是锚点标签（`<a href="...">`），而不是表单，点击后会导航到新的页面。

---

![](img/782befdaf5e37b3291ea18610247b509_17.png)

## 主列表页面 (`index.php`) 📄

![](img/782befdaf5e37b3291ea18610247b509_19.png)

现在，让我们深入看看`index.php`文件是如何工作的。它首先包含`pdo.php`来建立数据库连接，并启动会话。然后，它会检查并显示可能存在的闪存消息。

以下是处理闪存消息的核心代码：
```php
if ( isset($_SESSION['error']) ) {
    echo '<p style="color:red">'.$_SESSION['error']."</p>\n";
    unset($_SESSION['error']);
}
if ( isset($_SESSION['success']) ) {
    echo '<p style="color:green">'.$_SESSION['success']."</p>\n";
    unset($_SESSION['success']);
}
```
这些消息并非首次访问页面时显示，而是在从`add.php`、`delete.php`或`edit.php`重定向回来时，由这些页面设置的。

接着，视图部分会查询数据库并输出一个表格。在表格的“操作”列中，我们为每条记录创建编辑和删除链接，并通过URL参数（GET参数）传递该记录的主键（`user_id`）。

![](img/782befdaf5e37b3291ea18610247b509_21.png)

例如，生成的链接可能如下所示：
*   `edit.php?user_id=1`
*   `delete.php?user_id=1`

这样，目标页面就知道要操作哪条记录了。

![](img/782befdaf5e37b3291ea18610247b509_23.png)

![](img/782befdaf5e37b3291ea18610247b509_24.png)

![](img/782befdaf5e37b3291ea18610247b509_26.png)

---

## 添加记录功能 (`add.php`) ➕

了解了主页面后，我们来看看如何添加新记录。当点击“Add New”链接时，会进入`add.php`。这个文件遵循模型-视图-控制器（MVC）模式，控制器逻辑在上方，视图在下方。

视图部分是一个简单的表单，包含姓名、邮箱、密码字段以及“添加”和“取消”按钮。当用户提交表单时，数据通过POST方法发送到服务器端的控制器逻辑。

控制器逻辑执行以下步骤：
1.  检查POST数据。
2.  使用预处理语句执行SQL插入操作，以防止SQL注入攻击。
    ```php
    $stmt = $pdo->prepare('INSERT INTO users (name, email, password) VALUES (:name, :email, :password)');
    $stmt->execute(array(
        ':name' => $_POST['name'],
        ':email' => $_POST['email'],
        ':password' => $_POST['password']));
    ```
3.  在会话中设置成功消息：`$_SESSION[‘success’] = ‘Record added’;`。
4.  使用`header(‘Location: index.php’)`重定向回`index.php`。

![](img/782befdaf5e37b3291ea18610247b509_28.png)

**重要提示**：在重定向之前输出任何内容（如调试语句）会导致错误，因为HTTP头部已经发送。调试信息应写入日志文件。

![](img/782befdaf5e37b3291ea18610247b509_30.png)

![](img/782befdaf5e37b3291ea18610247b509_31.png)

整个流程是：点击添加 -> 填写表单 -> POST提交 -> 插入数据库 -> 设置闪存消息并重定向 -> 主页面显示成功消息。

![](img/782befdaf5e37b3291ea18610247b509_33.png)

---

![](img/782befdaf5e37b3291ea18610247b509_35.png)

## 删除记录功能 (`delete.php`) 🗑️

![](img/782befdaf5e37b3291ea18610247b509_37.png)

接下来，我们看看删除功能是如何实现的。从主页面点击删除链接会进入`delete.php?user_id=X`，这是一个GET请求。

![](img/782befdaf5e37b3291ea18610247b509_39.png)

该页面的逻辑如下：
1.  **首次GET请求（确认页面）**：
    *   根据传入的`user_id`执行SELECT查询，验证ID是否有效并获取用户名。
    *   如果未找到记录（例如ID无效），则在会话中设置错误闪存消息并重定向回主页。
    *   如果找到记录，则进入视图部分，显示确认删除的表单，其中包含一个隐藏字段`<input type=”hidden” name=”user_id” value=”…”>`，用于再次传递用户ID。

![](img/782befdaf5e37b3291ea18610247b509_41.png)

2.  **提交表单后的POST请求（执行删除）**：
    *   检查POST数据，确认删除操作。
    *   使用预处理语句执行DELETE操作。
        ```php
        $stmt = $pdo->prepare('DELETE FROM users WHERE user_id = :uid');
        $stmt->execute(array(':uid' => $_POST['user_id']));
        ```
    *   在会话中设置成功消息并重定向回`index.php`。

这种“先GET显示确认，再POST执行操作”的模式，是防止意外删除的良好实践。

![](img/782befdaf5e37b3291ea18610247b509_43.png)

---

![](img/782befdaf5e37b3291ea18610247b509_45.png)

## 编辑记录功能 (`edit.php`) ✏️

![](img/782befdaf5e37b3291ea18610247b509_46.png)

![](img/782befdaf5e37b3291ea18610247b509_48.png)

最后，我们来实现之前缺失的编辑功能。`edit.php`的工作流程与添加和删除有相似之处，也有其特点。

当点击主页的编辑链接时，进入`edit.php?user_id=X`（GET请求）。页面逻辑首先根据`user_id`查询数据库，获取该记录的旧数据。如果ID无效，则设置错误并重定向。

获取到旧数据后，进入视图部分。视图是一个表单，其字段（姓名、邮箱、密码）的`value`属性中预先填充了旧数据。**关键点**：这些从数据库取出的数据在输出到HTML前，必须使用`htmlentities()`函数进行转义，以防止跨站脚本（XSS）攻击。同时，表单中包含一个隐藏字段来保存`user_id`。

![](img/782befdaf5e37b3291ea18610247b509_50.png)

当用户修改数据并提交表单时，发生POST请求。控制器逻辑执行UPDATE语句：
```php
$stmt = $pdo->prepare('UPDATE users SET name = :name, email = :email, password = :password WHERE user_id = :uid');
$stmt->execute(array(
    ':name' => $_POST['name'],
    ':email' => $_POST['email'],
    ':password' => $_POST['password'],
    ':uid' => $_POST['user_id']));
```
更新成功后，设置成功闪存消息并重定向回主页。

![](img/782befdaf5e37b3291ea18610247b509_52.png)

**安全提醒**：无论是INSERT、UPDATE还是DELETE，只要SQL语句涉及用户输入，就必须使用预处理语句（`prepare` / `execute`）来防止SQL注入攻击。

---

## 数据安全与转义策略 🔒

在CRUD操作中，正确处理用户数据至关重要，这里总结一下核心策略：

![](img/782befdaf5e37b3291ea18610247b509_54.png)

*   **SQL注入防护**：永远使用预处理语句（Prepared Statements）来构建SQL查询。不要直接拼接用户输入到SQL字符串中。
    *   **正确做法**：`$stmt = $pdo->prepare(‘SQL语句 :placeholder’); $stmt->execute(array(‘:placeholder’ => $user_input));`
*   **XSS跨站脚本防护**：当将数据从数据库输出到HTML页面时，必须使用`htmlentities()`函数进行转义。
    *   **策略**：数据**存入**数据库时保持原始状态（不转义）。数据**从数据库取出**并**输出到HTML**时进行转义（`htmlentities`）。这样避免双重转义，也确保了安全。

---

## 总结 🎯

![](img/782befdaf5e37b3291ea18610247b509_56.png)

本节课中，我们一起构建了一个完整的单表CRUD应用程序。我们学习了如何将应用拆分为`index.php`（读取）、`add.php`（创建）、`edit.php`（更新）和`delete.php`（删除）等多个文件，并通过URL参数在页面间传递信息。

我们深入实践了POST重定向GET（PRG）模式，利用会话闪存消息在重定向后向用户传递操作反馈。更重要的是，我们贯穿始终地应用了关键安全实践：使用预处理语句防御SQL注入，以及在输出时使用`htmlentities`防御XSS攻击。

![](img/782befdaf5e37b3291ea18610247b509_58.png)

理解这个基础的CRUD模式至关重要，它是构建更复杂Web应用程序的基石。后续学习AJAX、jQuery或其他技术时，你会发现它们常常是围绕这个核心模式进行的扩展和优化。