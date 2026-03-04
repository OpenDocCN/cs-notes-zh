# 密歇根大学《面向所有人的Web应用程序》：第31章：JSON聊天应用教程 🗨️

![](img/1f7c24c3ce878cdb9e898de02a1d7337_0.png)

![](img/1f7c24c3ce878cdb9e898de02a1d7337_1.png)

在本节课中，我们将学习如何整合PHP、JavaScript和JSON技术，构建一个简单的异步聊天应用。我们将看到如何将数据模型保留在服务器端，而将视图和控制逻辑更多地迁移到浏览器中。

## 概述

我们将构建一个聊天应用，它能够异步地从服务器拉取并显示新消息，类似于Facebook等社交平台的消息更新机制。应用的核心数据模型将存储在PHP会话（Session）中，前端则使用JavaScript和jQuery通过AJAX定期获取并更新聊天内容。

## 服务器端模型与逻辑

首先，我们来看服务器端的代码。在`index.php`文件中，我们使用会话来管理聊天数据。

如果接收到重置请求，我们会清空会话中的聊天记录。我们的数据模型不是一个独立的数据库，而是一个存储在PHP会话中的聊天消息数组。

处理表单提交的逻辑如下：当用户发送一条消息时，我们首先初始化聊天数组（如果尚未存在），然后将新消息（包含文本和发送时间戳）添加到数组中。最后，我们重定向回页面自身以防止表单重复提交。

```php
// 示例：在会话中存储聊天数组
$_SESSION['chats'] = array();
array_push($_SESSION['chats'], array($message, date('Y-m-d H:i:s')));
```

这是一种非常简单的“数据库”实现，键`chats`下存储的只是一个数组。

## 前端视图结构

![](img/1f7c24c3ce878cdb9e898de02a1d7337_3.png)

![](img/1f7c24c3ce878cdb9e898de02a1d7337_4.png)

接下来是视图部分，即用户看到的HTML界面。

我们有一个表单，包含一个用于输入消息的文本框、一个“发送”按钮和一个“重置”按钮。表单的处理逻辑对应上面服务器端的代码。

在表单下方，我们有一个`<div>`元素，其ID为`chatcontent`，用于动态加载和显示聊天记录。初始时，这个`div`内会显示一个加载动画（spinner），表示正在获取数据。这是一种常见模式：先显示一个加载指示器，然后在数据成功获取后将其清除并填充实际内容。

```html
<div id="chatcontent">
    <img src="spinner.gif" alt="Loading...">
</div>
```

![](img/1f7c24c3ce878cdb9e898de02a1d7337_6.png)

![](img/1f7c24c3ce878cdb9e898de02a1d7337_7.png)

## 浏览器端的应用逻辑

现在，我们进入应用的核心——运行在浏览器中的JavaScript控制器代码。

我们定义了一个名为`updateMessages`的函数。这个函数使用jQuery的`$.getJSON`方法向`chatlist.php`发起AJAX请求，以获取最新的聊天记录。

```javascript
function updateMessages() {
    $.getJSON('chatlist.php', function(rows) {
        console.log('JSON received', rows);
        // ... 处理数据的代码
    });
}
```

服务器端`chatlist.php`的代码很简单：它启动会话，读取`$_SESSION['chats']`数组，然后使用`json_encode`函数将其编码为JSON格式输出。我们在其中添加了`sleep(5)`来模拟网络延迟，以便更清楚地看到加载效果。

```php
// chatlist.php 示例
session_start();
sleep(5);
header('Content-Type: application/json');
echo json_encode($_SESSION['chats']);
```

## 处理数据并更新视图

当AJAX请求成功返回后，我们在`success`回调函数中处理数据。

首先，我们清空`#chatcontent`这个`div`。然后，我们遍历从服务器返回的`rows`数组。这个数组的每个元素本身也是一个包含两个元素的数组：第一个是消息文本，第二个是发送日期。

我们使用一个`for`循环，为每条消息创建一个段落（`<p>`）元素，并将其追加到`#chatcontent`中。

```javascript
$('#chatcontent').empty(); // 清空现有内容
for (var i = 0; i < rows.length; i++) {
    var entry = rows[i];
    $('#chatcontent').append('<p>' + entry[0] + '    ' + entry[1] + '</p>');
}
```

## 实现定时轮询

为了让聊天内容自动更新，我们需要定期调用`updateMessages`函数。这里不能使用简单的同步循环，因为会阻塞浏览器。我们采用异步模式：在每次成功获取数据后，设置一个定时器，在4秒后再次执行自身。

```javascript
// 在 updateMessages 函数的 success 回调末尾
setTimeout(updateMessages, 4000);
```

这个模式确保了即使某次请求失败，也不会无限地每4秒重试（因为只有在成功后才设置下一次定时器）。

![](img/1f7c24c3ce878cdb9e898de02a1d7337_9.png)

## 启动应用

最后，我们需要在页面加载完成后启动整个流程。我们使用jQuery的`$(document).ready()`方法。

在其中，我们首先进行一个AJAX全局设置`$.ajaxSetup({cache: false})`。这非常重要，因为它可以阻止浏览器缓存`GET`请求的响应。如果没有这个设置，浏览器可能会直接返回旧的JSON数据，而不是每次都向服务器请求最新消息。其原理是在请求URL后自动添加一个随时间变化的参数。

然后，我们调用一次`updateMessages()`函数来加载初始聊天记录，并启动定时轮询的链条。

```javascript
$(document).ready(function(){
    $.ajaxSetup({cache: false});
    updateMessages();
});
```

![](img/1f7c24c3ce878cdb9e898de02a1d7337_11.png)

## 异步编程模式的重要性

这种“启动一个操作，然后定义操作完成后的回调函数”的模式，是JavaScript异步编程的核心。它允许浏览器同时处理多个任务（如更新聊天、响应用户点击、显示通知等），而不会因为等待某个操作（如网络请求）而冻结界面。虽然初学者需要时间适应，但它是一种非常强大且必要的编程范式。

![](img/1f7c24c3ce878cdb9e898de02a1d7337_13.png)

## 总结

本节课中，我们一起学习了一个完整的JSON聊天应用的构建过程。

我们首先在服务器端用PHP会话实现了一个简单的数据模型。然后，我们创建了前端视图，包括表单和用于显示消息的容器。接着，我们编写了浏览器端的JavaScript控制器，它使用AJAX从服务器异步获取JSON格式的聊天数据，并动态更新DOM以显示这些消息。最后，我们通过`setTimeout`实现了定时轮询，使聊天内容能够自动更新，并讨论了禁用缓存和异步编程模式的重要性。

![](img/1f7c24c3ce878cdb9e898de02a1d7337_15.png)

通过这个例子，你可以看到，利用JSON作为数据交换格式，配合前端的jQuery AJAX和后端的PHP，我们可以用相对较少的代码实现强大的、交互式的Web应用功能。随着学习的深入，你会发现越来越多的逻辑被移到浏览器端执行，而服务器端则更专注于数据模型和核心业务规则。