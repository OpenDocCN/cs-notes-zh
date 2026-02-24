# 后端开发（Django）：P13：创建视图和视图逻辑 🧱

在本节课中，我们将要学习如何创建视图函数，这些函数能够返回文本和HTML标记。我们还将学习如何将这些函数映射到特定的URL，以便最终用户能在网页浏览器中看到它们。

![](img/12b4984fa6d6b6f1f248fab190a97fe6_1.png)

---

## 概述

视图是Django应用的核心组件之一，它负责处理用户的请求并返回响应。简单来说，视图就是一个Python函数，它接收一个Web请求，并返回一个Web响应。响应可以是纯文本、HTML页面、JSON数据等。

上一节我们介绍了Django项目和应用的基本结构，本节中我们来看看如何编写具体的视图函数，并让它们通过URL在浏览器中显示出来。

---

## 创建返回文本的视图

首先，我们需要在应用的 `views.py` 文件中创建一个视图函数。这个函数将返回一个简单的“Hello World”文本。

以下是创建此视图的步骤：

1.  打开应用目录下的 `views.py` 文件。
2.  从 `django.http` 模块导入 `HttpResponse` 类。这个类允许我们与服务器进行通信。
3.  定义一个名为 `say_hello` 的函数，它返回一个包含“Hello World”文本的 `HttpResponse` 对象。

对应的代码如下：

```python
# 在 views.py 文件中
from django.http import HttpResponse

def say_hello(request):
    return HttpResponse("Hello World")
```

**核心概念**：`HttpResponse` 对象是Django中用于向客户端（浏览器）返回内容的基本方式。其基本公式为：**`HttpResponse(content=文本或HTML内容)`**。

---

![](img/12b4984fa6d6b6f1f248fab190a97fe6_3.png)

## 将视图映射到URL

仅仅创建视图函数是不够的，Django并不知道当用户访问哪个地址时应该执行这个函数。因此，我们需要在URL配置文件中建立URL与视图函数之间的映射。

以下是配置URL的步骤：

![](img/12b4984fa6d6b6f1f248fab190a97fe6_5.png)

1.  打开项目目录下的 `urls.py` 文件。
2.  从你的应用模块中导入 `views`。
3.  在 `urlpatterns` 列表中添加一个 `path()`，将特定的URL路径（例如 `‘sayhello/’`）与刚才创建的 `say_hello` 视图函数关联起来。

对应的代码如下：

```python
# 在项目 urls.py 文件中
from django.urls import path
from your_app_name import views # 请将 your_app_name 替换为你的实际应用名

![](img/12b4984fa6d6b6f1f248fab190a97fe6_7.png)

urlpatterns = [
    path('sayhello/', views.say_hello, name='say_hello'),
]
```

**核心概念**：`path()` 函数用于定义URL模式。其基本语法为：**`path(‘路由/’, 视图函数, name=‘路由名称’)`**。当用户访问 `基础URL/sayhello/` 时，Django就会调用 `views.say_hello` 函数并返回其结果。

配置完成后，运行开发服务器（`python manage.py runserver`），在浏览器中访问 `http://127.0.0.1:8000/sayhello/`，你就能看到“Hello World”的页面了。

![](img/12b4984fa6d6b6f1f248fab190a97fe6_9.png)

---

## 创建更多视图函数

掌握了基本方法后，我们可以创建更多功能不同的视图。每个视图函数都需要在 `views.py` 中定义，并在 `urls.py` 中配置对应的路径。

以下是几个视图函数的示例：

1.  **返回欢迎信息**：创建一个返回“Welcome to Little Lemon”的视图。

    ```python
    def homepage(request):
        return HttpResponse("Welcome to Little Lemon")
    ```

    然后在 `urlpatterns` 中添加：`path(‘homepage/’, views.homepage, name=‘homepage’)`。

![](img/12b4984fa6d6b6f1f248fab190a97fe6_11.png)

![](img/12b4984fa6d6b6f1f248fab190a97fe6_12.png)

2.  **集成Python功能**：创建一个显示当前年份的视图，这需要用到Python的 `datetime` 模块。

    ```python
    import datetime

    def display_date(request):
        date_joined = datetime.datetime.now().year
        return HttpResponse(date_joined)
    ```

    对应的URL配置为：`path(‘displaydate/’, views.display_date, name=‘display_date’)`。

3.  **返回HTML内容**：视图不仅可以返回纯文本，还可以返回带有HTML标记和简单样式的富文本内容。

    ```python
    def menu(request):
        html_content = “””
        <h1 style=‘color: blue;’>Little Lemon</h1>
        <p>Welcome to our restaurant’s menu page.</p>
        “””
        return HttpResponse(html_content)
    ```

    对应的URL配置为：`path(‘menu/’, views.menu, name=‘menu’)`。

访问 `http://127.0.0.1:8000/menu/`，你将看到一个带有蓝色标题和段落的简单网页。

---

![](img/12b4984fa6d6b6f1f248fab190a97fe6_14.png)

## 总结

![](img/12b4984fa6d6b6f1f248fab190a97fe6_16.png)

本节课中我们一起学习了Django视图创建与URL映射的核心流程。

我们首先学习了如何编写一个基础的视图函数，使用 `HttpResponse` 对象返回文本内容。接着，我们掌握了关键的一步：如何在项目的 `urls.py` 文件中使用 `path()` 函数，将特定的URL路径与我们编写的视图函数关联起来，从而使浏览器能够访问到这些内容。

最后，我们通过多个实例进行了实践，包括返回静态文本、集成Python代码动态生成内容，以及返回带有HTML标记和简单样式的响应。虽然目前返回的内容还比较基础，但这为后续学习使用模板（Templates）来构建完整的网页打下了坚实的基础。

![](img/12b4984fa6d6b6f1f248fab190a97fe6_18.png)

记住这个核心流程：**编写视图（views.py） -> 配置URL（urls.py） -> 运行服务器访问**。祝你接下来的开发之旅顺利！🚀