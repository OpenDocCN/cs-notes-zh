# 132：表单与jQuery代码详解

![](img/a1749bc708e6e0e7ea5ae65349683c54_1.png)

在本节课中，我们将学习一个结合了表单、PHP会话、Ajax和jQuery的异步聊天应用。我们将详细解析其代码结构和工作原理，理解如何在不刷新页面的情况下实现多窗口间的实时通信。

## 概述

我们将要分析的应用程序是一个简单的异步聊天室。它允许用户在多个浏览器窗口或标签页中发送消息，并利用Ajax和定时器自动更新所有窗口中的聊天内容，而无需手动刷新页面。这个应用巧妙地结合了PHP处理表单提交和会话管理，以及JavaScript/jQuery处理前端的异步数据获取和DOM更新。

## 代码结构与工作原理

![](img/a1749bc708e6e0e7ea5ae65349683c54_3.png)

上一节我们介绍了应用的基本功能，本节中我们来看看其背后的代码是如何组织的。

整个应用的核心逻辑分布在两个PHP文件中：`index.php`（主页面）和`chatlist.php`（数据接口）。

### 1. 表单处理与PHP会话

![](img/a1749bc708e6e0e7ea5ae65349683c54_5.png)

首先，我们来看`index.php`中处理表单提交和会话的部分。其核心是标准的请求-响应周期。

![](img/a1749bc708e6e0e7ea5ae65349683c54_7.png)

当用户提交表单（发送消息或重置聊天）时，页面会向自身（`index.php`）发起POST请求。服务器端的PHP代码会检查请求参数，并更新存储在`$_SESSION`中的聊天数据数组。

以下是处理逻辑的伪代码描述：

```php
// 检查是否为重置操作
if (isset($_POST[‘reset’])) {
    // 清空会话中的聊天数组
    $_SESSION[‘chats’] = array();
    // 重定向回自身，使用GET请求刷新页面
    header(“Location: index.php”);
}
// 检查是否有新消息
elseif (isset($_POST[‘message’]) && strlen($_POST[‘message’]) > 0) {
    // 如果会话中没有聊天数组，则初始化一个空数组
    if (!isset($_SESSION[‘chats’])) {
        $_SESSION[‘chats’] = array();
    }
    // 将新消息和当前时间戳作为子数组，添加到聊天数组中
    $_SESSION[‘chats’][] = array($_POST[‘message’], date(DATE_RFC2822));
    // 重定向回自身，使用GET请求刷新页面
    header(“Location: index.php”);
}
```

**核心概念**：聊天数据被存储为一个PHP会话（`$_SESSION`）中的二维数组。每个子数组包含两个元素：消息内容（`[0]`）和日期时间（`[1]`）。使用`header(“Location: …”)`进行重定向是一种防止表单重复提交的常见模式（Post/Redirect/Get）。

### 2. 前端页面与jQuery

处理完POST请求后，`index.php`会输出HTML页面。这个页面包含了聊天表单、一个用于显示消息的`<div>`，以及关键的JavaScript/jQuery代码。

以下是页面的关键部分：

```html
<!-- 聊天表单，提交到自身 -->
<form method=“post”>
    <input type=“text” name=“message” size=“60”/>
    <input type=“submit” value=“Chat”/>
    <input type=“submit” name=“reset” value=“Reset”/>
</form>

<!-- 显示聊天内容的区域，初始时包含一个加载动画 -->
<div id=“chatcontent”>
    <img src=“spinner.gif” alt=“Loading…”/>
</div>
```

在页面底部，引入了jQuery库，并定义了一个名为`updateMessages`的JavaScript函数。

```javascript
function updateMessages() {
    console.log(‘*’);
    // 发起Ajax请求获取最新的聊天列表
    $.ajax({
        url: ‘chatlist.php’,
        cache: false, // 禁止缓存，确保每次获取新数据
        dataType: ‘json’, // 期望返回JSON格式数据
        success: function(data) { // 请求成功后的回调函数
            console.log(data);
            // 清空聊天显示区域
            $(‘#chatcontent’).empty();
            // 遍历返回的JSON数据（一个数组）
            for (var i = 0; i < data.length; i++) {
                // data[i][0] 是消息， data[i][1] 是日期
                var msg = data[i][0];
                var date = data[i][1];
                // 为每条消息创建一个新的段落并添加到显示区域
                $(‘#chatcontent’).append(‘<p>’ + date + ‘: ‘ + msg + ‘</p>’);
            }
            // 设置一个4秒后的定时器，再次调用自己，实现轮询
            setTimeout(updateMessages, 4000);
        }
    });
}
// 页面加载完成后，立即调用一次该函数以获取初始数据
$(document).ready(function() {
    updateMessages();
});
```

**核心概念**：
*   **`$.ajax`**：jQuery的Ajax方法，用于向服务器（`chatlist.php`）发起异步HTTP请求。
*   **`cache: false`**：通过添加一个基于时间戳的查询参数，强制浏览器跳过缓存，每次都从服务器获取新数据。
*   **`dataType: ‘json’`**：告诉jQuery将服务器响应解析为JSON对象。
*   **`success` 回调函数**：请求成功且数据解析完成后执行的函数。在这里，它用新数据更新DOM。
*   **`setTimeout`**：一个原生JavaScript函数，用于在指定的毫秒数后执行一段代码。这里它创建了一个每4秒轮询一次的循环。
*   **DOM操作**：`$(‘#chatcontent’).empty()`清空元素内容，`.append()`向元素内添加新的HTML内容。

### 3. JSON数据接口 (`chatlist.php`)

`updateMessages`函数请求的`chatlist.php`文件是一个纯数据接口。它不返回HTML，而是返回JSON格式的聊天数据。

以下是`chatlist.php`的代码：

```php
<?php
session_start(); // 启动会话，以访问$_SESSION
// 设置正确的HTTP头部，声明内容类型为JSON
header(‘Content-Type: application/json; charset=utf-8’);
// 模拟网络延迟，便于演示（实际应用应移除）
sleep(5);
// 检查会话中是否有聊天数据，没有则初始化为空数组
if (!isset($_SESSION[‘chats’])) {
    $_SESSION[‘chats’] = array();
}
// 使用json_encode将PHP数组转换为JSON字符串并输出
echo json_encode($_SESSION[‘chats’]);
?>
```

![](img/a1749bc708e6e0e7ea5ae65349683c54_9.png)

**核心概念**：
*   **`header(‘Content-Type: application/json’)`**：这是至关重要的HTTP头部。它告诉浏览器（以及jQuery）返回的内容是JSON格式，而不是默认的HTML。这是API设计的良好实践。
*   **`json_encode()`**：PHP内置函数，将PHP变量（如数组、对象）转换为JSON格式的字符串。
*   **`sleep(5)`**：此处仅用于演示，人为制造5秒延迟，让我们能在开发者工具中清晰地观察到请求和更新的过程。

## 应用流程总结

现在，让我们将以上所有部分串联起来，回顾整个应用的工作流程：

1.  **初始加载**：用户访问`index.php`。页面加载jQuery，并立即执行`updateMessages()`函数。
2.  **首次数据获取**：`updateMessages()`向`chatlist.php`发起Ajax请求。由于`sleep(5)`，请求会等待5秒。
3.  **显示加载状态**：在等待响应期间，`#chatcontent` div中显示着`spinner.gif`（加载动画）。
4.  **接收并渲染数据**：5秒后，Ajax请求收到`chatlist.php`返回的JSON数据。`success`回调函数被触发：
    *   清空`#chatcontent` div（移除加载动画）。
    *   使用`for`循环遍历JSON数组。
    *   为每条消息生成一个`<p>`标签，并将其追加到`#chatcontent` div中。
5.  **建立轮询循环**：渲染完成后，`setTimeout(updateMessages, 4000)`被调用，设定在4秒后再次执行`updateMessages`函数，从而开始下一次数据获取。这就建立了一个每4秒轮询一次的循环。
6.  **用户交互**：
    *   **发送消息**：用户在表单中输入文本并点击“Chat”。表单以POST方式提交到`index.php`。PHP代码将消息和日期存入`$_SESSION[‘chats’]`数组，然后重定向。页面刷新，重复步骤1。此时，轮询函数会在几秒后获取到包含新消息的列表并更新所有打开的窗口。
    *   **重置聊天**：用户点击“Reset”。表单提交一个`reset`参数。PHP代码清空`$_SESSION[‘chats’]`数组并重定向。随后的轮询会获取到空数组并清空聊天显示区域。

![](img/a1749bc708e6e0e7ea5ae65349683c54_11.png)

## 关键点与学习总结

本节课中我们一起学习了如何构建一个简单的异步Web应用。让我们总结一下其中的关键技术和设计模式：

*   **前后端分离（雏形）**：`index.php`负责呈现视图和处理表单动作，`chatlist.php`作为纯数据API（返回JSON），这是现代前后端分离架构的简单体现。
*   **Ajax与轮询**：使用jQuery的`$.ajax`进行异步通信，结合`setTimeout`实现定时轮询，是早期实现“实时”更新的典型方法（现代更常用WebSocket）。
*   **无刷新DOM更新**：通过JavaScript/jQuery操作DOM（`empty()`, `append()`），可以在不重新加载整个页面的情况下更新部分内容，提升用户体验。
*   **会话状态管理**：使用PHP的`$_SESSION`在服务器端维持聊天记录的状态，避免了使用数据库的复杂性。
*   **正确的HTTP头部**：在API端点（`chatlist.php`）设置`Content-Type: application/json`是至关重要的，它确保了数据能被正确解析。

![](img/a1749bc708e6e0e7ea5ae65349683c54_13.png)

通过这个案例，你可以看到如何将PHP、JavaScript、jQuery和Ajax技术组合起来，创建一个具有动态交互功能的Web应用程序。虽然这是一个基础示例，但它涵盖了构建更复杂交互式应用的核心思想。