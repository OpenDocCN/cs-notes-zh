# Django后端开发：P15：创建请求和响应对象 🚀

在本节课中，我们将要学习Django框架中HTTP请求与响应周期的核心机制。你将了解客户端与服务器如何通过请求和响应对象进行通信，并掌握在Django视图中创建和操作这些对象的基本方法。

## 请求-响应周期概述

上一节我们介绍了Web应用的基本通信模型。本节中我们来看看Django内部如何处理请求-响应周期。

该周期始于用户在浏览器中输入一个URL。此URL被发送到Web服务器，Django随后在其`urls.py`文件中寻找匹配项。一旦找到匹配的URL，它就会被映射到对应的视图函数。在视图文件中，视图函数接收HTTP请求并将其封装为一个`request`对象。视图函数随后定义适当的HTTP响应，并将其作为`HTTP response`对象发回。此响应由Django处理，最终客户端收到HTTP响应。

![](img/2b5e561487af7fe12b5400bde0b457a5_1.png)

## 在代码中探索请求与响应对象

![](img/2b5e561487af7fe12b5400bde0b457a5_1.png)

现在，让我们打开VS Code，探索如何操作Django的请求和响应对象。

首先，打开`views.py`文件并添加必要的导入语句。接着，创建视图。需要记住的是，Django使用`request`和`response`对象在整个系统中传递数据。

HTTP请求和HTTP响应对象的API在Django的`django.http`模块中定义。你需要在视图函数的逻辑中从这个模块导入并使用`HttpRequest`和`HttpResponse`对象。

以下是创建视图函数的步骤：

1.  创建一个名为`home`的视图函数，并将`request`对象传递给它。
2.  检查`urls.py`文件，确保函数名与URL模式列表中的视图函数名称匹配。
3.  回到`views.py`文件，通过输入`request.path`来访问`request`对象中的`path`属性。
4.  将此属性赋值给一个名为`path`的变量。需要注意的是，必须修改格式以便在HTTP响应中返回`path`变量。

下一步是创建带有HTTP响应对象的返回语句。在括号内，传入`path`参数，然后是内容类型，最后是字符集。

```python
from django.http import HttpResponse

def home(request):
    path = request.path
    return HttpResponse(path, content_type='text/plain', charset='utf-8')
```

保存文件并在浏览器中打开本地主机URL。输入URL的确切位置，即`/main/home`。

![](img/2b5e561487af7fe12b5400bde0b457a5_3.png)

请注意，路径显示在浏览器的主窗口中，并且其顺序与你在URL模式列表中按下`main`然后`home`的顺序相同。

![](img/2b5e561487af7fe12b5400bde0b457a5_3.png)

![](img/2b5e561487af7fe12b5400bde0b457a5_5.png)
![](img/2b5e561487af7fe12b5400bde0b457a5_6.png)

如果你在URL模式列表中移除`main`并保存文件，可以通过移除路径中的`main`来配置URL。

![](img/2b5e561487af7fe12b5400bde0b457a5_5.png)

![](img/2b5e561487af7fe12b5400bde0b457a5_8.png)
![](img/2b5e561487af7fe12b5400bde0b457a5_9.png)

![](img/2b5e561487af7fe12b5400bde0b457a5_6.png)

注意路径更新为`/home`。这是因为Django将从应用级别提供的路径拼接到了项目级别的当前路径中。这个例子演示了HTTP响应对象的行为与普通对象类似。

![](img/2b5e561487af7fe12b5400bde0b457a5_8.png)

## 进一步操作响应对象

![](img/2b5e561487af7fe12b5400bde0b457a5_9.png)

为了进一步探索，我们可以创建另一个HTTP响应对象并将其赋值给一个变量。

```python
def home(request):
    response = HttpResponse("This works.")
    return response
```

回到浏览器，刷新页面，注意显示的文本。

![](img/2b5e561487af7fe12b5400bde0b457a5_13.png)

![](img/2b5e561487af7fe12b5400bde0b457a5_11.png)

需要知道的是，这只是一个如何探索HTTP响应对象的示例。在实际场景中，开发者通常不需要修改HTTP响应对象的结构。

![](img/2b5e561487af7fe12b5400bde0b457a5_13.png)

## 返回请求对象的属性

为了让这个例子更深入，你也可以返回HTTP请求对象的属性。例如，你可以创建变量来存储方案（scheme）、方法（method）、地址（address）、用户代理（user agent）和路径信息（path info）。你可能还记得，元标签（metatags）提供了关于请求对象头部（headers）的信息。

要在浏览器窗口中显示HTTP请求对象的属性，你需要将变量渲染到Python的格式化字符串中。回想一下，在Python中执行字符串格式化，可以使用格式化字符串字面值（f-string）。以一个字符`F`（大小写均可）开始字符串，并将其放在引号之前。Python表达式则放在花括号`{}`中。

以下是具体步骤：

1.  在格式化字符串中添加一些HTML标签，并传入你之前创建的变量。
2.  将这个格式化字符串存储在一个名为`message`的变量中。
3.  最后，使用`return`语句返回HTTP响应对象，注意将`message`变量作为第一个参数传递。

```python
def home(request):
    scheme = request.scheme
    method = request.method
    address = request.META['REMOTE_ADDR']
    user_agent = request.META['HTTP_USER_AGENT']
    path_info = request.path_info

    message = f"""
    <p>Scheme: {scheme}</p>
    <p>Method: {method}</p>
    <p>Address: {address}</p>
    <p>User Agent: {user_agent}</p>
    <p>Path Info: {path_info}</p>
    """
    return HttpResponse(message)
```

![](img/2b5e561487af7fe12b5400bde0b457a5_15.png)

现在保存文件。在浏览器中刷新你的URL，注意请求对象的信息显示在浏览器中。

![](img/2b5e561487af7fe12b5400bde0b457a5_17.png)

## 更新请求与响应对象的头部信息

最后需要了解的是，你可以更新HTTP请求和响应对象的头部信息。

![](img/2b5e561487af7fe12b5400bde0b457a5_19.png)

![](img/2b5e561487af7fe12b5400bde0b457a5_15.png)

为此，创建一个HTTP响应对象并将其赋值给一个名为`response`的变量。接着，输入`response.headers`，并使用字典添加一个键为`Age`、值为`20`的项。然后，在格式化字符串中传入这个值。

![](img/2b5e561487af7fe12b5400bde0b457a5_17.png)

```python
def home(request):
    response = HttpResponse()
    response.headers['Age'] = 20
    message = f"Header 'Age' set to: {response.headers['Age']}"
    return HttpResponse(message)
```

返回浏览器并刷新页面。注意响应头的内容显示出来，并且`Age`已作为头部的一部分添加。

![](img/2b5e561487af7fe12b5400bde0b457a5_19.png)

![](img/2b5e561487af7fe12b5400bde0b457a5_21.png)

## 实际应用场景

开发者在处理GET和POST方法时会使用请求和响应对象。

![](img/2b5e561487af7fe12b5400bde0b457a5_21.png)

![](img/2b5e561487af7fe12b5400bde0b457a5_23.png)

![](img/2b5e561487af7fe12b5400bde0b457a5_23.png)

这对于创建表单、操作数据库以及处理Django中其他常见数据结构非常有用。

## 总结

本节课中我们一起学习了如何在Django中使用请求和响应对象。我们了解了请求-响应周期的流程，在代码中创建并操作了`HttpRequest`和`HttpResponse`对象，探索了如何访问请求属性、构建响应内容以及修改响应头。这些知识是构建Django Web应用视图层的基础。