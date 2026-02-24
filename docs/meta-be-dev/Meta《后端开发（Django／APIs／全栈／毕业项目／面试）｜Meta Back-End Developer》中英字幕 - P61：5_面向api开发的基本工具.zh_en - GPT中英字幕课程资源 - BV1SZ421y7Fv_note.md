# 后端开发：5：面向API开发的基本工具 🛠️

在本节课中，我们将学习如何利用几种命令行和图形界面工具来高效地测试与调试API。掌握这些工具将帮助您更快地开发并提升开发能力。

## 概述

作为一名开发者，若想高效工作，就需要合适的工具。例如，一个智能的代码编辑器可以帮助您更快地开发。本节视频将介绍几种可用于测试API的命令行和图形界面工具，并演示如何在Insomnia中进行实际测试。这些工具都是跨平台的，可在Windows、Mac OS和Linux上使用。在本课程中，您将频繁使用其中一些工具（如Insomnia），因此现在了解它们非常重要。

## 命令行工具：cURL

首先介绍的是cURL，这是一个广为人知的工具，允许开发者从命令行发起HTTP调用。它适用于所有主流操作系统，但没有图形界面。

要使用cURL，只需在Windows中打开PowerShell，或在Linux/Mac中打开终端，输入`curl`并回车即可。

cURL可以轻松发送HTTP GET请求。例如，只需在`curl`命令后加上API的URI。以下命令会向Postman Echo服务（一个用于显示请求头和请求体的服务）发送一个HTTP GET请求，这对于测试API调用非常有用。

```bash
curl https://postman-echo.com/get
```

对于POST请求，操作略有不同。这次需要使用`-d`参数添加请求体，并使用`-X`参数指定HTTP方法为POST。

```bash
curl -X POST -d "key=value" https://postman-echo.com/post
```

## 图形界面工具：Postman

接下来是Postman，它提供了跨平台的桌面工具和一个网页版本，拥有先进的图形界面，使得API的测试和调试变得简单。Postman是一个强大的API开发工具，使用它可以减少在API细节上的纠缠，从而将更多时间用于构建完美的API。您可以访问其官网和附加资源以获取更多信息。

![](img/abc12e625b496785e1a49b97ae196ddc_1.png)

## 图形界面工具：Insomnia Rest Client

另一个重要工具是Insomnia Rest Client，这是一个功能强大的REST API客户端，用于存储、组织和执行REST API请求。Insomnia是免费的、跨平台的，并且拥有非常用户友好的界面。您可以从本课末尾附加资源中提供的链接下载并安装适合您操作系统的Insomnia。请注意，Insomnia目前只有桌面版本。

在本课程的其余部分，您将使用Insomnia来测试和与您构建的API进行交互。下面我们来看看如何使用它。

![](img/abc12e625b496785e1a49b97ae196ddc_3.png)

![](img/abc12e625b496785e1a49b97ae196ddc_4.png)

### 开始使用Insomnia

Insomnia是测试API的绝佳工具。所有请求都将保存在一个“请求集合”中。要开始使用，请点击右上角的“创建”按钮，然后选择“请求集合”。为其命名（例如“第一个集合”），然后点击“创建”。

现在，您进入了一个空的集合。要创建第一个API请求，请点击左侧边栏的加号图标，然后选择“HTTP请求”。在Mac上也可以按`Command + N`，在Windows和Linux上按`Ctrl + N`。

您可以双击默认的请求名称“New Request”，将其更改为更具个人特色的名称，例如“第一个请求”。

在中间区域顶部显示“GET”的地方，点击并选择您的请求将要使用的HTTP方法类型。目前先保持为GET。在旁边的文本框中，写入您的API URL，例如：`https://httpbin.org/get?project=LittleLemon`。

HTTPBin.org是一个免费服务，允许您试验不同类型的HTTP方法。当您调用这些API时，它会将您发送的内容回显出来。

现在，点击右侧的“发送”按钮，您将看到HTTPBin返回了您发送的相同查询参数，在您的例子中就是`project=LittleLemon`。

### 创建POST请求

这次，让我们尝试创建一个新的HTTP POST请求。为此，点击左侧边栏的加号图标，选择“HTTP请求”。请求创建后，双击其名称并赋予一个新名称，例如“第二个请求”。

现在点击HTTP方法下拉菜单，选择“POST”。这次在URL字段中添加：`https://httpbin.org/post`。

您已经知道，HTTP POST请求接受表单数据或JSON数据作为参数。在Insomnia中，您可以轻松地为POST请求输入数据：点击“Body”选项卡，然后选择“Form URL Encoded”或“JSON”。

在这个参数窗口中，您可以以一种易于使用和组织的方式列出所有参数。在左侧写入参数名，在右侧写入值。在参数字段中写入`project`，值写为`Little Lemon`。

现在，点击“发送”按钮以显示输出。您可以创建任意数量的请求，并随时返回进行测试。

## 总结

![](img/abc12e625b496785e1a49b97ae196ddc_6.png)

![](img/abc12e625b496785e1a49b97ae196ddc_7.png)

![](img/abc12e625b496785e1a49b97ae196ddc_8.png)

在本节课中，我们一起学习了cURL、Postman和Insomnia等出色的工具，您可以使用它们来创建和测试您的API。掌握这些工具是成为一名高效后端开发者的重要一步。