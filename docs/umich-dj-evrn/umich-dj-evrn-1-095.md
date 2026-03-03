# 095：表单的GET、POST与HTTP方法 🚀

## 概述

在本节课中，我们将学习HTML表单如何与服务器通信。我们将重点介绍两种基本的HTTP方法：GET和POST。理解这两种方法的区别对于构建安全、有效的Web应用程序至关重要。

![](img/ca62901dfc081b8f9fbfe3cae767c02e_1.png)

![](img/ca62901dfc081b8f9fbfe3cae767c02e_2.png)

![](img/ca62901dfc081b8f9fbfe3cae767c02e_3.png)

表单是我们在浏览器中创建填空区域的方式。其核心思想是绘制一些字段和位置供用户输入，然后通过某种方式将数据发送到服务器。我们将探讨多种收集数据并将其发送到服务器的方法。

## GET与POST方法

![](img/ca62901dfc081b8f9fbfe3cae767c02e_5.png)

上一节我们提到了表单的基本概念。本节中，我们来看看与服务器通信表单数据的两种基本方式。

我们之前使用锚点标签（`<a>`）所做的一切都是GET请求。这意味着你将获取一个文档并显示它。你可以在URL末尾添加参数，例如 `?guess=42`。然而，我们真正要介绍并详细讨论的是POST数据的概念。在表单中，你实际上可以进行GET或POST操作。

以下是两种方法的简要对比：

*   **GET请求**：数据作为URL的一部分发送（例如 `?key1=value1&key2=value2`）。
*   **POST请求**：数据在HTTP请求的消息体内发送，不会显示在URL中。

## 代码示例：数据转储工具

![](img/ca62901dfc081b8f9fbfe3cae767c02e_7.png)

![](img/ca62901dfc081b8f9fbfe3cae767c02e_8.png)

为了清晰地展示数据，我们将使用一个简单的工具函数。GET数据、POST数据，甚至Cookie数据都以类似字典的键值对形式传入。以下代码定义了一个 `dump_data` 函数，用于安全地格式化并输出这些数据。

```python
from django.utils.html import escape

def dump_data(label, data_dict):
    """
    安全地转储并格式化字典数据，用于显示。
    """
    output = f"<p><b>{label}:</b></p>"
    if data_dict:
        for key, value in data_dict.items():
            output += f"<p>{escape(str(key))} = {escape(str(value))}</p>"
    else:
        output += "<p>(no data)</p>"
    return output
```

这个函数遍历字典的所有项，调用 `HTML escape` 以防止跨站脚本注入攻击，然后将键和值打印出来，并包裹在段落标签中。这样我们就可以在多个示例中复用这段代码来展示数据。

## 使用GET方法的表单

现在，让我们看一个使用GET方法的简单表单示例。这个视图函数会打印一个表单，并在提交后检索表单数据。

```python
from django.http import HttpResponse
from django.views.decorators.csrf import csrf_exempt

@csrf_exempt  # 暂时禁用CSRF保护以简化示例
def getform(request):
    html = """
    <html>
    <body>
        <form>
            <label>请输入你的猜测：</label>
            <input type="text" name="guess" size="40" />
            <input type="submit" value="提交" />
        </form>
    </body>
    </html>
    """
    response = html
    if request.GET:
        response += dump_data("GET 数据", request.GET)
    return HttpResponse(response)
```

这个表单包含一个文本输入框（`name="guess"`）和一个提交按钮。当用户在框中输入“42”并点击提交按钮时，会发生以下情况：

![](img/ca62901dfc081b8f9fbfe3cae767c02e_10.png)

1.  浏览器会自动在原始URL的末尾追加 `?guess=42`。
2.  它发起一个新的GET请求，URL包含这个参数。
3.  Django框架会解析这个请求，并将 `guess=42` 这个键值对放入 `request.GET` 字典中。
4.  我们的 `dump_data` 函数将其显示出来。

## 使用POST方法的表单

![](img/ca62901dfc081b8f9fbfe3cae767c02e_12.png)

接下来，我们看看使用POST方法的相同表单。关键区别在于 `<form>` 标签的 `method` 属性。

```python
@csrf_exempt  # 暂时禁用CSRF保护以简化示例
def postform(request):
    html = """
    <html>
    <body>
        <form method="post">
            <label>请输入你的猜测：</label>
            <input type="text" name="guess" size="40" />
            <input type="submit" value="提交" />
        </form>
    </body>
    </html>
    """
    response = html
    if request.method == 'POST':
        response += dump_data("POST 数据", request.POST)
    return HttpResponse(response)
```

这个表单与GET表单几乎完全相同，只是我们将 `method="post"` 添加到了 `<form>` 标签中。这告诉浏览器使用POST技术（而非GET技术）将数据发送到服务器。

提交表单后，你会注意到：
*   **URL中没有出现 `?guess=42`** 这样的参数。
*   数据通过HTTP连接以不同的方式传输，位于所有请求头信息之后。
*   在服务器端，我们通过检查 `request.method` 来判断是否为POST请求，并通过 `request.POST` 字典来访问提交的数据，我们仍然能获取到 `guess` 关键字及其值“42”。

## GET与POST的工作原理对比

为了更清晰地理解，以下是两种方法工作原理的对比：

![](img/ca62901dfc081b8f9fbfe3cae767c02e_14.png)

**GET请求过程：**
1.  浏览器将表单数据（如 `guess=42`）**追加到目标URL的末尾**。
2.  发起一个到该新URL的GET请求。
3.  Django接收请求，解析URL中的参数，并将其存入 `request.GET`。

![](img/ca62901dfc081b8f9fbfe3cae767c02e_15.png)

**POST请求过程：**
1.  浏览器将表单数据放入HTTP请求的**消息体（body）**中。
2.  发起一个到表单指定URL的POST请求（URL本身不变）。
3.  请求头中包含 `Content-Type: application/x-www-form-urlencoded` 等信息，告诉服务器如何解析消息体。
4.  Django接收请求，从消息体中解析参数，并将其存入 `request.POST`。

POST数据中如果包含特殊字符也需要编码，但我们现在暂时忽略这个细节。重要的是理解，在POST请求中看不到URL参数，是因为数据是作为HTTP连接的一部分传输的。

## 如何选择GET还是POST？

你可能会问，这有区别吗？是的，区别很重要。

以下是选择GET或POST的一些基本规则：

*   **POST应用于创建或修改数据**。任何会改变系统状态的操作（插入、更新、删除）都应使用POST。
*   **GET适用于读取或搜索**。获取信息、查询数据时应使用GET。它**绝不应该**用于插入、修改或删除数据。

这样规定有几个原因：
1.  **网络爬虫（Web Spiders）**：爬虫会跟踪网页上的GET请求链接来收集信息。如果你的应用错误地将删除操作设计为GET请求，爬虫可能会意外地“点击”所有删除链接，导致数据被清空。而爬虫通常不会自动提交POST请求，因为它们假设POST可能会改变服务器状态。
2.  **幂等性（Idempotent）**：GET请求应该是幂等的，即多次执行相同的GET请求应该产生相同的效果（或返回相同语义的结果）。例如，访问 `?page=1` 应该总是返回第一页的内容。这使得GET请求可以被收藏、缓存和重复访问。
3.  **数据长度限制**：GET请求通过URL传递数据，而URL长度存在限制（通常约2000字符，因浏览器和服务器而异）。POST请求通过消息体传输数据，可以处理更大量的数据，特别是上传文件（如图片）时必须使用POST。
4.  **URL美观与安全**：POST不会将参数暴露在URL中，这使得URL更简洁，并且不会在浏览器历史记录或服务器日志中明文留下敏感数据（如密码）。

## 总结

本节课中，我们一起学习了HTML表单中GET与POST两种HTTP方法的核心知识。

我们了解到，GET方法将数据附加在URL中进行发送，适用于安全的、幂等的读取操作；而POST方法将数据放在请求体内发送，适用于会改变服务器状态的创建、更新或删除操作，并能处理更大量的数据。正确选择GET或POST是构建安全、可靠且符合Web标准的应用程序的基础。

![](img/ca62901dfc081b8f9fbfe3cae767c02e_17.png)

下一节，我们将快速回顾HTML表单中可以使用哪些不同类型的输入标签（`<input>`）。