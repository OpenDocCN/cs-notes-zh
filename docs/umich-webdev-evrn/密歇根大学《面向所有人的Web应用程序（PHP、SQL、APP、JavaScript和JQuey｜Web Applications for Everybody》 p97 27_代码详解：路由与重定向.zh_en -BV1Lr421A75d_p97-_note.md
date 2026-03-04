# 面向所有人的Web应用程序：第27讲：代码详解：路由与重定向 🧭

在本节课中，我们将学习Web开发中的一个核心概念：重定向。我们将通过一个简单的PHP示例，详细解析重定向的工作原理及其在路由中的应用。

![](img/ee4d01eb065a62180dbcffb109b07e7a_1.png)

![](img/ee4d01eb065a62180dbcffb109b07e7a_2.png)

## 概述

重定向是Web服务器告知浏览器“您请求的资源已移至新位置”的一种方式。它通过HTTP响应头实现，是构建动态Web应用和实现页面跳转的关键技术。

![](img/ee4d01eb065a62180dbcffb109b07e7a_4.png)

## 什么是重定向？

当您访问一个网址时，服务器会返回一个HTTP状态码。状态码`200`表示请求成功。而状态码`302`则表示“已找到”，但资源位于其他位置。服务器会通过一个名为`Location`的HTTP头部，告诉浏览器应该前往的新地址。

![](img/ee4d01eb065a62180dbcffb109b07e7a_6.png)

例如，访问`doctorchuck.com`（无连字符）时，服务器会返回一个`302`状态码和`Location: doctor-chuck.com`的头部，浏览器便会自动跳转到带连字符的网址。您会观察到浏览器地址栏中的URL发生了变化。

## 在PHP中实现重定向

![](img/ee4d01eb065a62180dbcffb109b07e7a_8.png)

![](img/ee4d01eb065a62180dbcffb109b07e7a_9.png)

在PHP中，我们可以使用`header()`函数来设置HTTP响应头。`echo`或`print`用于向响应的主体部分输出内容，而`header()`则用于在主体内容之前发送HTTP头部信息。

以下是实现重定向的核心代码：
```php
header("Location: new_page.php");
exit; // 确保重定向后停止执行后续代码
```

## 示例代码详解

![](img/ee4d01eb065a62180dbcffb109b07e7a_11.png)

我们来看一个具体的示例。该示例包含一个表单，根据提交的数字将用户重定向到不同的页面。

以下是示例代码的主要逻辑：
```php
if ($_POST[‘value’] == 1) {
    header(“Location: redirect1.php”);
    return;
} elseif ($_POST[‘value’] == 2) {
    header(“Location: redirect2.php?param=123”);
    return;
} elseif ($_POST[‘value’] == 3) {
    header(“Location: https://www.doctor-chuck.com”);
    return;
}
```

### 代码执行流程分析

让我们逐步分析不同输入下的执行流程：

**输入数字1：**
*   表单将数据`POST`到`redirect1.php`。
*   服务器处理请求，发现`value`等于1。
*   服务器返回`302 Found`状态码和`Location: redirect1.php`头部。
*   浏览器立即向`redirect1.php`发起一个新的`GET`请求，页面刷新。

![](img/ee4d01eb065a62180dbcffb109b07e7a_13.png)

**输入数字2：**
*   表单同样将数据`POST`到`redirect1.php`。
*   服务器处理请求，发现`value`等于2。
*   服务器返回`302 Found`状态码和`Location: redirect2.php?param=123`头部。
*   浏览器立即向`redirect2.php?param=123`发起一个新的`GET`请求，页面跳转至新地址。

**输入数字3：**
*   表单将数据`POST`到`redirect1.php`。
*   服务器处理请求，发现`value`等于3。
*   服务器返回`302 Found`状态码和`Location: https://www.doctor-chuck.com`头部。
*   浏览器立即向`https://www.doctor-chuck.com`发起一个新的`GET`请求，最终加载外部网站的全部内容（包括HTML、CSS、图片等）。

通过浏览器的开发者工具“网络”（Network）面板，可以清晰地观察到每次`POST`请求后，紧随其后的`302`响应和新的`GET`请求。

![](img/ee4d01eb065a62180dbcffb109b07e7a_15.png)

![](img/ee4d01eb065a62180dbcffb109b07e7a_16.png)

## 总结

![](img/ee4d01eb065a62180dbcffb109b07e7a_18.png)

本节课我们一起学习了Web应用中的重定向机制。我们了解到重定向通过HTTP的`302`状态码和`Location`头部实现，是控制用户流和实现页面路由的基础。在PHP中，使用`header(“Location: url”)`函数可以方便地发起重定向。掌握这一技术，对于构建具有良好用户体验和逻辑流程的Web应用程序至关重要。