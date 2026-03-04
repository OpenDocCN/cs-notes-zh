# 面向所有人的Web应用程序：24：Cookie与会话详解 🍪

![](img/76fe488013308c3fa4386d3837af72ca_1.png)

![](img/76fe488013308c3fa4386d3837af72ca_2.png)

在本节课中，我们将学习Web开发中的两个核心概念：Cookie和会话。我们将通过具体的PHP代码示例，了解它们如何工作、有何区别以及如何在实践中使用它们。

![](img/76fe488013308c3fa4386d3837af72ca_4.png)

## 概述

Cookie和会话是Web应用程序中用于在无状态的HTTP协议上维持状态的关键技术。Cookie是存储在用户浏览器中的小段数据，而会话则利用Cookie在服务器端存储用户数据。理解它们的工作原理对于构建需要用户登录、购物车等功能的动态网站至关重要。

## Cookie详解

Cookie是存储在用户浏览器中的键值对数据。服务器可以通过响应头将Cookie发送给浏览器，浏览器会在后续的请求中自动将其发送回服务器。

### Cookie的工作原理

![](img/76fe488013308c3fa4386d3837af72ca_6.png)

![](img/76fe488013308c3fa4386d3837af72ca_7.png)

以下是设置和读取Cookie的基本PHP代码：

```php
if (!isset($_COOKIE['zap'])) {
    setcookie('zap', 42, time() + 3600);
}
```

![](img/76fe488013308c3fa4386d3837af72ca_9.png)

![](img/76fe488013308c3fa4386d3837af72ca_10.png)

*   `setcookie()` 函数用于设置Cookie。它接收三个主要参数：Cookie的名称（键）、值以及过期时间。
*   `$_COOKIE` 是一个PHP超全局数组，包含了浏览器在本次请求中发送过来的所有Cookie。
*   代码逻辑是：如果名为 `zap` 的Cookie不存在，就将其值设置为 `42`，并设定一小时后过期。

当用户首次访问页面时，服务器检测到 `$_COOKIE[‘zap’]` 未设置，于是通过 `setcookie` 函数在HTTP响应头中添加 `Set-Cookie: zap=42` 指令。浏览器收到后，会将该Cookie保存起来。

![](img/76fe488013308c3fa4386d3837af72ca_12.png)

![](img/76fe488013308c3fa4386d3837af72ca_14.png)

在后续的请求中，浏览器会自动在请求头中包含 `Cookie: zap=42`。PHP引擎会解析这个请求头，并将数据填充到 `$_COOKIE` 超全局数组中。因此，当代码再次执行时，`isset($_COOKIE[‘zap’])` 条件为真，就不会再次设置相同的Cookie。

![](img/76fe488013308c3fa4386d3837af72ca_15.png)

![](img/76fe488013308c3fa4386d3837af72ca_17.png)

用户可以在浏览器的开发者工具中查看、修改或删除Cookie。这意味着Cookie数据并不完全安全，可以被用户操控。

![](img/76fe488013308c3fa4386d3837af72ca_18.png)

## 会话详解

![](img/76fe488013308c3fa4386d3837af72ca_20.png)

![](img/76fe488013308c3fa4386d3837af72ca_22.png)

会话（Session）提供了一种在服务器端存储用户数据的方法，它通常借助一个Cookie来追踪用户。

![](img/76fe488013308c3fa4386d3837af72ca_24.png)

### 会话的工作原理

![](img/76fe488013308c3fa4386d3837af72ca_26.png)

![](img/76fe488013308c3fa4386d3837af72ca_27.png)

要使用PHP会话，首先需要调用 `session_start()` 函数。

```php
session_start();
```

当 `session_start()` 被调用时，PHP会执行以下操作：
1.  检查请求中是否包含会话ID（通常通过一个名为 `PHPSESSID` 的Cookie）。
2.  如果没有，则生成一个唯一、随机的会话ID，并通过 `Set-Cookie` 响应头将其发送给浏览器。
3.  初始化 `$_SESSION` 超全局数组。这个数组的数据**存储在服务器上**（例如服务器的临时文件或数据库中），而不是浏览器中。

![](img/76fe488013308c3fa4386d3837af72ca_29.png)

![](img/76fe488013308c3fa4386d3837af72ca_30.png)

![](img/76fe488013308c3fa4386d3837af72ca_31.png)

### 会话数据操作

![](img/76fe488013308c3fa4386d3837af72ca_33.png)

![](img/76fe488013308c3fa4386d3837af72ca_35.png)

会话数据通过 `$_SESSION` 数组进行读写。以下是一个计数器示例：

```php
session_start();
if (!isset($_SESSION[‘pizza’])) {
    echo(“Session is empty\n”);
    $_SESSION[‘pizza’] = 0;
} elseif ($_SESSION[‘pizza’] < 3) {
    $_SESSION[‘pizza’] ++;
    echo(“Added one\n”);
} else {
    session_destroy();
    echo(“Session Destroyed\n”);
}
print_r($_SESSION);
```

![](img/76fe488013308c3fa4386d3837af72ca_37.png)

![](img/76fe488013308c3fa4386d3837af72ca_39.png)

代码执行流程如下：
1.  **首次访问**：`$_SESSION[‘pizza’]` 未设置，将其初始化为 `0`。
2.  **后续访问（值小于3）**：每次访问，`pizza` 的值增加1。
3.  **当值达到3**：调用 `session_destroy()` 函数。这会清空服务器上与该会话ID关联的所有数据（即 `$_SESSION` 数组），但**不会删除浏览器中的会话ID Cookie**。下次访问时，由于会话ID依然存在，会开启一个新的空会话。

![](img/76fe488013308c3fa4386d3837af72ca_41.png)

会话数据实际存储在服务器的特定目录（可通过 `session.save_path` 配置项查看）中，以文件形式保存，内容经过序列化处理。这保证了数据的私密性，用户无法直接查看或修改。

![](img/76fe488013308c3fa4386d3837af72ca_43.png)

## Cookie与会话的关系与区别

![](img/76fe488013308c3fa4386d3837af72ca_45.png)

![](img/76fe488013308c3fa4386d3837af72ca_46.png)

![](img/76fe488013308c3fa4386d3837af72ca_47.png)

上一节我们介绍了会话在服务器端存储数据的机制，现在我们来总结一下它与Cookie的关系和核心区别。

![](img/76fe488013308c3fa4386d3837af72ca_48.png)

![](img/76fe488013308c3fa4386d3837af72ca_50.png)

虽然会话依赖于Cookie来传递会话ID，但它们是不同的概念：
*   **存储位置**：Cookie数据存储在**客户端（浏览器）**，会话数据存储在**服务器端**。
*   **安全性**：会话更安全，因为敏感数据不在客户端存储和传输。Cookie中的数据可能被用户查看或修改。
*   **容量限制**：单个Cookie大小通常有限制（如4KB），而会话可以存储更多数据，仅受服务器配置限制。
*   **生命周期**：Cookie可通过设置过期时间长期存在，而会话通常在浏览器关闭后失效（会话ID Cookie过期），或通过 `session_destroy()` 手动销毁。

## 总结

本节课中我们一起学习了Web开发中维持用户状态的两种关键技术。
我们了解到，**Cookie**是存储在浏览器中的键值对，用于在请求间携带少量信息，可通过 `setcookie()` 设置，通过 `$_COOKIE` 读取。
而**会话**则是一种更强大的机制，它利用Cookie传递一个会话ID，从而在服务器端安全地存储用户相关的数据，通过 `session_start()` 启动，通过 `$_SESSION` 数组进行操作。

![](img/76fe488013308c3fa4386d3837af72ca_52.png)

![](img/76fe488013308c3fa4386d3837af72ca_54.png)

理解Cookie和会话的区别与联系，是构建交互式Web应用程序的重要基础。