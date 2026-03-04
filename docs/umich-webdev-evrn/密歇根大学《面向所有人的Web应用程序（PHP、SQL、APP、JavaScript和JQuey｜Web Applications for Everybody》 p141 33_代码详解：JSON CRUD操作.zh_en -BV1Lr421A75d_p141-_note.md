# 面向所有人的Web应用程序：第33章：JSON CRUD操作详解 🧩

![](img/4111cd997d6ccf7c84f350ce6a8749ea_1.png)

在本节课中，我们将继续探讨jQuery与JSON的结合使用，并对一个基础的CRUD（创建、读取、更新、删除）应用程序进行一个小修改。我们将学习如何利用JSON来动态获取和展示数据，从而理解服务器端渲染与客户端渲染的区别。

## 概述

![](img/4111cd997d6ccf7c84f350ce6a8749ea_3.png)

我们将分析一个混合了PHP、JavaScript和jQuery的CRUD应用示例。该应用的核心变化在于，它不再由PHP直接生成完整的HTML表格，而是先由PHP后端提供JSON格式的数据，再由前端的jQuery通过AJAX请求获取这些数据，并动态地构建和填充表格。

![](img/4111cd997d6ccf7c84f350ce6a8749ea_5.png)

![](img/4111cd997d6ccf7c84f350ce6a8749ea_6.png)

## 代码演变：从服务器端渲染到客户端渲染

上一节我们回顾了传统的服务器端渲染方式。本节中我们来看看如何将其改造为使用JSON进行数据交互的客户端渲染模式。

### 传统的服务器端渲染方式

在最初的版本（`index_old.php`）中，所有HTML内容都在服务器端由PHP生成。

```php
// 示例：传统的PHP循环生成表格行
$stmt = $pdo->query('SELECT title, plays, rating, id FROM tracks');
while ($row = $stmt->fetch(PDO::FETCH_ASSOC)) {
    echo '<tr>';
    echo '<td>' . htmlentities($row['title']) . '</td>';
    echo '<td>' . htmlentities($row['plays']) . '</td>';
    echo '<td>' . htmlentities($row['rating']) . '</td>';
    // ... 编辑和删除按钮
    echo '</tr>';
}
```

这种方式下，浏览器接收到的响应已经是一个完整的、填充好数据的HTML页面。

### 新的客户端渲染方式

![](img/4111cd997d6ccf7c84f350ce6a8749ea_8.png)

在新的版本（`index.php`）中，我们采用了不同的策略。页面初始加载时，表格体（`<tbody>`）是空的。

![](img/4111cd997d6ccf7c84f350ce6a8749ea_10.png)

```html
<table border="1">
    <tbody id="track-table-body">
        <!-- 初始为空，将由JavaScript填充 -->
    </tbody>
</table>
```

数据填充的逻辑转移到了JavaScript中。

![](img/4111cd997d6ccf7c84f350ce6a8749ea_12.png)

![](img/4111cd997d6ccf7c84f350ce6a8749ea_13.png)

以下是实现动态数据加载的核心步骤：

![](img/4111cd997d6ccf7c84f350ce6a8749ea_14.png)

![](img/4111cd997d6ccf7c84f350ce6a8749ea_15.png)

1.  **发起AJAX请求**：使用jQuery的`$.getJSON()`方法从`get_json.php`获取数据。
2.  **处理JSON响应**：成功获取数据后，执行回调函数。数据（`data`）是一个由对象组成的数组。
3.  **动态构建DOM**：遍历数据数组，为每条记录拼接出对应的HTML表格行字符串。
4.  **插入到页面**：使用jQuery的`.append()`方法将生成的HTML插入到空的`<tbody>`中。

```javascript
$(document).ready(function() {
    $.getJSON('get_json.php', function(data) {
        var tbody = $('#track-table-body');
        tbody.empty(); // 清空现有内容
        if (data.length === 0) {
            tbody.append('<tr><td colspan="4">No entries found.</td></tr>');
        } else {
            $.each(data, function(index, row) {
                // 对数据进行HTML转义，防止注入攻击
                var title = $('<div>').text(row.title).html();
                var plays = $('<div>').text(row.plays).html();
                var rating = $('<div>').text(row.rating).html();
                var id = row.id;

                // 构建表格行HTML
                var html = '<tr>' +
                    '<td>' + title + '</td>' +
                    '<td>' + plays + '</td>' +
                    '<td>' + rating + '</td>' +
                    '<td><a href="edit.php?id=' + id + '">Edit</a></td>' +
                    '<td><a href="delete.php?id=' + id + '" onclick="return confirm(\'Are you sure?\');">Delete</a></td>' +
                    '</tr>';
                tbody.append(html);
            });
        }
    }).fail(function(jqxhr, textStatus, error) {
        console.error("Error fetching JSON: ", textStatus, error);
    });
});
```

### 后端数据接口 (`get_json.php`)

后端的任务变得非常纯粹：查询数据库，并将结果编码为JSON格式输出。

![](img/4111cd997d6ccf7c84f350ce6a8749ea_17.png)

```php
<?php
require_once 'pdo.php'; // 数据库连接

![](img/4111cd997d6ccf7c84f350ce6a8749ea_19.png)

![](img/4111cd997d6ccf7c84f350ce6a8749ea_21.png)

header('Content-Type: application/json'); // 设置正确的响应头

$stmt = $pdo->query('SELECT title, plays, rating, id FROM tracks');
$rows = $stmt->fetchAll(PDO::FETCH_ASSOC); // 获取所有行作为关联数组

![](img/4111cd997d6ccf7c84f350ce6a8749ea_23.png)

echo json_encode($rows); // 编码并输出JSON
?>
```

## 两种方式的对比与选择

通过查看页面源代码，我们可以清晰地看到两种方式的区别：
*   **服务器端渲染**：源代码中包含完整的、已填充数据的HTML表格。
*   **客户端渲染（JSON）**：源代码中的表格体是空的，数据是在页面加载后由JavaScript动态添加的。

![](img/4111cd997d6ccf7c84f350ce6a8749ea_25.png)

![](img/4111cd997d6ccf7c84f350ce6a8749ea_27.png)

以下是两种技术路径的简单对比：

| 特性 | 服务器端渲染 (PHP直接输出) | 客户端渲染 (JSON + jQuery) |
| :--- | :--- | :--- |
| **首次加载速度** | 可能更快，因HTML已就绪 | 可能稍慢，需等待JS下载、执行和数据请求 |
| **前后端分离** | 耦合较紧 | 更清晰，后端专注API，前端负责展示 |
| **动态更新** | 需整页刷新 | 可局部更新，用户体验更流畅 |
| **SEO友好度** | 友好，内容直接存在于HTML中 | 需额外处理（如服务端渲染）才能被搜索引擎抓取 |
| **适用场景** | 内容型网站、管理后台初始页 | 单页应用(SPA)、高度交互的Web应用 |

没有绝对意义上的“更好”的技术，只有“更合适”的技术。选择取决于你的具体需求：
*   如果需要简单的页面和良好的SEO，服务器端渲染是可靠的选择。
*   如果需要构建像实时聊天、动态仪表盘这样交互复杂的应用，采用JSON进行客户端渲染则更具优势。

## 总结

![](img/4111cd997d6ccf7c84f350ce6a8749ea_29.png)

本节课中我们一起学习了如何将JSON集成到CRUD应用程序中。我们分析了从传统的服务器端PHP渲染到使用jQuery进行客户端动态渲染的演变过程。关键在于理解：
1.  后端角色转变为提供纯净数据（JSON）的API。
2.  前端角色转变为消费这些数据并负责构建用户界面。
3.  这种分离使得前后端开发可以更独立，并能创建出响应更迅速、用户体验更佳的现代Web应用程序。

![](img/4111cd997d6ccf7c84f350ce6a8749ea_31.png)

掌握这两种模式，能帮助你在不同的项目需求中做出恰当的技术选型。