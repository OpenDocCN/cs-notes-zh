# 后端开发（Django/APIs/全栈/毕业项目/面试）：P20：在视图中处理错误 🛠️

在本节课中，我们将学习如何在Django视图中处理错误，并探索如何使用`HttpResponseNotFound`类创建一个自定义的404错误页面。

## 概述

浏览网页时，偶尔输入URL或点击链接后，发现找不到目标页面是很常见的。Django在无法匹配URL时会显示一个默认的“页面未找到”错误页，其中包含一些面向开发者的技术信息。然而，通常不希望最终用户看到这类信息。本节将演示如何创建自定义的错误视图，以提供更友好的用户体验。

## 默认错误页面与调试模式

上一节我们介绍了Django的基本视图处理。本节中我们来看看如何处理错误。首先，让我们了解Django的默认行为。

![](img/18875dd42af2ab1757b9f334b5f58084_1.png)

当Django无法匹配请求的URL时，它会显示一个默认的404错误页面。在开发阶段，Django的调试模式（`DEBUG = True`）默认开启，此页面会显示详细的错误信息，例如请求方法和URL。

以下是启动开发服务器的命令：
```bash
python3 manage.py runserver
```

![](img/18875dd42af2ab1757b9f334b5f58084_3.png)

在浏览器中打开本地服务器地址（如`http://localhost:8000`），如果访问一个不存在的URL（例如`/home`），你将看到默认的错误页面。页面会提示：“你看到此错误是因为在Django设置文件中`DEBUG = True`。将其改为`False`，Django将显示标准404页面。”

## 关闭调试模式

调试是处理代码中错误的过程。为了在生产环境中隐藏技术细节，需要关闭调试模式。

![](img/18875dd42af2ab1757b9f334b5f58084_5.png)

要进行此更改，请打开项目下的`settings.py`文件，找到`DEBUG`设置并将其值改为`False`。
```python
# settings.py
DEBUG = False
```

此外，必须在`ALLOWED_HOSTS`设置中添加值。在本例中，添加星号（`*`）以包含所有可能的主机。
```python
# settings.py
ALLOWED_HOSTS = ['*']
```

![](img/18875dd42af2ab1757b9f334b5f58084_7.png)

保存文件并刷新浏览器中的网页。现在，你会看到一个不同的页面，显示“未找到，请求的资源在服务器上不存在”，这是一个更简洁的标准404页面。

## 创建自定义404错误视图

虽然标准页面更简洁，但我们通常希望创建一个与网站品牌一致的自定义错误页面。接下来，我们将创建一个自定义的404错误处理视图。

![](img/18875dd42af2ab1757b9f334b5f58084_9.png)

以下是创建自定义404页面的步骤：

1.  **在项目层级创建视图文件**：首先，在项目目录下创建一个名为`views.py`的新文件（如果不存在）。
2.  **配置URL**：打开项目级的`urls.py`文件，进行必要的导入并添加URL模式。
3.  **指定错误处理器**：在`urlpatterns`列表**之外**，添加一个变量来指定404错误的处理函数。

让我们看看具体的代码实现。首先，在项目的`urls.py`文件中进行配置：
```python
# myproject/urls.py
from django.urls import path
from . import views  # 导入项目级的views模块

# 定义URL模式
urlpatterns = [
    # ... 你的其他URL模式 ...
]

# 在urlpatterns之外指定错误处理器
handler404 = views.handler404
```

接下来，在项目级的`views.py`文件中创建处理函数：
```python
# myproject/views.py
from django.http import HttpResponse

![](img/18875dd42af2ab1757b9f334b5f58084_11.png)

def handler404(request, exception):
    return HttpResponse("404错误：页面未找到")
```

保存文件并返回浏览器，刷新之前显示404错误的页面。现在，页面上将显示我们自定义的消息“404错误：页面未找到”。如果你修改URL为其他随机值，消息保持不变，这是因为`handler404`会处理所有URL配置文件中未找到的页面。

![](img/18875dd42af2ab1757b9f334b5f58084_13.png)

但是，如果你访问一个在URL配置中明确定义了视图的地址，该视图仍会正常渲染。

## 使用HttpResponseNotFound类

![](img/18875dd42af2ab1757b9f334b5f58084_15.png)

![](img/18875dd42af2ab1757b9f334b5f58084_16.png)

同样地，就像代码中使用了`HttpResponse`对象，你也可以使用`HttpResponseNotFound`。Django中的不同类代表不同的HTTP状态码，`HttpResponseNotFound`类就代表状态码404（页面未找到）。

修改`views.py`中函数的返回语句：
```python
# myproject/views.py
from django.http import HttpResponseNotFound

def handler404(request, exception):
    return HttpResponseNotFound("404错误：页面未找到")
```

![](img/18875dd42af2ab1757b9f334b5f58084_18.png)

保存文件并刷新浏览器。虽然页面上没有可见的变化，但客户端在内部收到了404状态消息。你可以通过浏览器的开发者工具进行验证：右键点击页面，选择“检查”，转到“网络”标签页，然后访问一个不存在的地址（如`/home`）。刷新页面后，在“网络”标签中点击该请求，你会看到状态为“404 Not Found”。

## 最佳实践：设计友好的错误页面

![](img/18875dd42af2ab1757b9f334b5f58084_20.png)

通常，开发者会修改返回的字符串，添加一些HTML元素，如标题和返回首页的按钮，以创建更友好、更具引导性的页面。

![](img/18875dd42af2ab1757b9f334b5f58084_22.png)

以下是一个改进的示例：
```python
# myproject/views.py
from django.http import HttpResponseNotFound

![](img/18875dd42af2ab1757b9f334b5f58084_24.png)

def handler404(request, exception):
    html_content = """
    <!DOCTYPE html>
    <html>
    <head><title>页面未找到</title></head>
    <body>
        <h1>404 - 页面不存在</h1>
        <p>抱歉，您寻找的页面已丢失在数字海洋中。</p>
        <a href="/"><button>返回首页</button></a>
    </body>
    </html>
    """
    return HttpResponseNotFound(html_content)
```

通常认为，最佳实践是创建一个易于理解、与网站品牌保持一致并能引导用户返回首页的自定义错误页面。

![](img/18875dd42af2ab1757b9f334b5f58084_26.png)

## 总结

本节课中我们一起学习了如何使用Django处理视图中的错误。我们探索了如何通过将设置中的`DEBUG`改为`False`来切换错误页面显示模式，并详细演示了如何利用`handler404`和`HttpResponseNotFound`类来创建自定义的404错误页面，从而为网站用户提供更佳体验。