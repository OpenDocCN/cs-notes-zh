# 哈佛CS50-WEB ｜ 基于Python／JavaScript的Web编程（2020·完整版） - P11：L3-Django网络编程3（表单与session） 📝

在本节课中，我们将学习如何使用Django处理表单、实现模板继承、管理URL命名空间，以及利用会话（session）为不同用户存储独立的数据。我们将构建一个简单的任务管理应用，通过实践来掌握这些核心概念。

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_1.png)

## 概述

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_3.png)

我们将创建一个包含两个页面的任务管理应用：一个页面用于显示任务列表，另一个页面用于添加新任务。我们将学习如何避免代码重复、安全地处理表单提交，并为每个用户维护独立的任务列表。

## 创建添加任务页面

上一节我们介绍了如何显示任务列表，本节中我们来看看如何创建一个新页面来添加任务。

我们首先需要创建一个新的视图函数 `add` 来渲染添加任务的页面。这个函数将负责显示一个表单。

```python
# views.py
def add(request):
    return render(request, "tasks/add.html")
```

为了让这个视图能够被访问，我们需要在 `urls.py` 文件中为其配置一个URL路径。

```python
# urls.py
from django.urls import path
from . import views

urlpatterns = [
    path("", views.index, name="index"),
    path("add/", views.add, name="add"),  # 新增的添加任务路径
]
```

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_7.png)

现在，当用户访问 `/tasks/add` 时，将会调用 `add` 视图并渲染 `add.html` 模板。

接下来，我们创建 `templates/tasks/add.html` 文件。这个页面的主体将包含一个表单，而不是任务列表。

```html
<!-- add.html -->
<!DOCTYPE html>
<html>
<head>
    <title>Tasks</title>
</head>
<body>
    <h1>Add Task</h1>
    <form>
        <input type="text" name="task">
        <input type="submit" value="Add">
    </form>
</body>
</html>
```

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_9.png)

这个表单目前还没有任何功能，提交后不会产生任何效果。

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_11.png)

## 使用模板继承避免重复

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_13.png)

我们注意到 `add.html` 和 `index.html` 的页面结构（如 `<head>`、`<title>`）非常相似。复制粘贴代码不是最佳实践，Django的模板继承功能可以解决这个问题。

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_15.png)

我们创建一个基础模板 `layout.html`，它包含页面的通用结构，并定义一个可以被子模板填充的“块”。

```html
<!-- layout.html -->
<!DOCTYPE html>
<html>
<head>
    <title>Tasks</title>
</head>
<body>
    {% block body %}
    {% endblock %}
</body>
</html>
```

然后，我们修改 `index.html` 和 `add.html`，让它们继承自 `layout.html`，并只填充 `body` 块中的内容。

```html
<!-- index.html -->
{% extends "tasks/layout.html" %}

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_17.png)

{% block body %}
    <h1>Tasks</h1>
    <ul>
        {% for task in tasks %}
            <li>{{ task }}</li>
        {% endfor %}
    </ul>
{% endblock %}
```

```html
<!-- add.html -->
{% extends "tasks/layout.html" %}

{% block body %}
    <h1>Add Task</h1>
    <form>
        <input type="text" name="task">
        <input type="submit" value="Add">
    </form>
{% endblock %}
```

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_21.png)

这样，公共的HTML结构只定义一次，易于维护和修改。

## 在页面间添加链接并解决命名空间冲突

为了在页面间导航，我们可以在模板中添加链接。但是，直接硬编码URL（如 `href="/tasks/add"`）不是好方法，因为一旦URL改变，就需要修改多处代码。

Django允许我们通过URL的名称（`name`）来动态生成链接。我们在 `urls.py` 中已经为路径定义了名称（`name="index"`, `name="add"`）。

在模板中，我们使用 `{% url %}` 标签来生成链接。

```html
<!-- 在 index.html 中添加链接 -->
<a href="{% url 'add' %}">Add a New Task</a>

<!-- 在 add.html 中添加链接 -->
<a href="{% url 'index' %}">View Tasks</a>
```

然而，如果多个应用中有同名的URL（例如，新年应用也有一个叫 `index` 的URL），就会产生命名空间冲突。Django可能无法确定我们想链接到哪个 `index`。

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_27.png)

为了解决这个问题，我们在应用的 `urls.py` 中为 `urlpatterns` 添加一个 `app_name`。

```python
# tasks/urls.py
app_name = "tasks"
urlpatterns = [...]
```

然后，在模板中引用URL时，需要包含应用命名空间。

```html
<!-- 修改后的链接 -->
<a href="{% url 'tasks:index' %}">View Tasks</a>
<a href="{% url 'tasks:add' %}">Add a New Task</a>
```

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_29.png)

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_31.png)

## 处理表单提交（POST请求与CSRF保护）

现在，我们需要让添加任务的表单真正起作用。我们将表单的 `action` 指向添加任务的URL，并将方法设置为 `POST`。`POST` 方法通常用于提交会改变服务器状态的数据。

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_33.png)

```html
<!-- add.html 中的表单 -->
<form action="{% url 'tasks:add' %}" method="post">
    <input type="text" name="task">
    <input type="submit" value="Add">
</form>
```

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_35.png)

如果我们此时提交表单，会得到一个 **403 Forbidden** 错误，提示“CSRF verification failed”。这是Django的一项安全特性，用于防止跨站请求伪造攻击。

为了让表单通过验证，我们需要在表单内部添加一个CSRF令牌。

```html
<form action="{% url 'tasks:add' %}" method="post">
    {% csrf_token %}
    <input type="text" name="task">
    <input type="submit" value="Add">
</form>
```

`{% csrf_token %}` 标签会被Django替换为一个隐藏的输入字段，包含一个唯一的令牌。服务器会验证这个令牌，确保请求来自我们自己的网站。

## 使用Django表单类简化开发

手动编写HTML表单字段是可行的，但当表单复杂时，使用Django的 `forms` 模块会更高效。它可以帮助我们自动生成HTML、进行数据验证和清理。

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_37.png)

首先，在 `views.py` 中创建一个表单类。

```python
# views.py
from django import forms

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_39.png)

class NewTaskForm(forms.Form):
    task = forms.CharField(label="New Task")
    # 可以轻松添加更多字段，例如：
    # priority = forms.IntegerField(label="Priority", min_value=1, max_value=10)
```

然后，在 `add` 视图中，将这个表单的实例传递给模板。

```python
def add(request):
    return render(request, "tasks/add.html", {
        "form": NewTaskForm()
    })
```

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_41.png)

最后，在 `add.html` 模板中，使用 `{{ form }}` 来渲染整个表单。

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_43.png)

```html
<form action="{% url 'tasks:add' %}" method="post">
    {% csrf_token %}
    {{ form }}
    <input type="submit" value="Add">
</form>
```

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_45.png)

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_47.png)

Django会自动生成带有标签和输入框的HTML，并可以添加客户端验证（如检查数字范围）。

## 在视图中处理GET和POST请求

一个表单页面通常需要处理两种请求：
1.  **GET请求**：用户首次访问页面，获取空表单。
2.  **POST请求**：用户提交表单数据。

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_49.png)

我们需要修改 `add` 视图来区分这两种情况并处理提交的数据。

```python
# views.py
from django.shortcuts import render, redirect
from django.urls import reverse

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_51.png)

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_53.png)

def add(request):
    # 检查请求方法是否为 POST（表单提交）
    if request.method == "POST":
        # 用提交的数据填充表单实例
        form = NewTaskForm(request.POST)
        # 检查表单数据是否有效
        if form.is_valid():
            # 获取清理后的数据
            task = form.cleaned_data["task"]
            # TODO: 将任务保存到列表
            # 成功后重定向到任务列表页
            return redirect(reverse("tasks:index"))
        else:
            # 如果表单无效，将带有错误信息的表单返回给用户
            return render(request, "tasks/add.html", {"form": form})
    # 如果是 GET 请求，显示一个空表单
    return render(request, "tasks/add.html", {"form": NewTaskForm()})
```

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_55.png)

## 使用会话（Session）存储用户特定数据

目前，我们将任务存储在一个全局变量 `tasks = []` 中。这意味着所有访问网站的用户都共享同一个任务列表，这显然不是我们想要的。

我们需要为每个用户维护独立的任务列表。Django的**会话（Session）** 功能可以实现这一点。会话就像一个字典，可以为每个访问者存储特定的数据。

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_57.png)

首先，我们需要运行迁移命令来创建Django用于存储会话数据的数据库表。

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_59.png)

```bash
python manage.py migrate
```

然后，我们修改视图，将任务列表存储在 `request.session` 中，而不是全局变量里。

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_61.png)

```python
# views.py
def index(request):
    # 检查会话中是否已有“tasks”键，如果没有，则初始化一个空列表
    if "tasks" not in request.session:
        request.session["tasks"] = []
    return render(request, "tasks/index.html", {
        "tasks": request.session["tasks"]
    })

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_63.png)

def add(request):
    if request.method == "POST":
        form = NewTaskForm(request.POST)
        if form.is_valid():
            task = form.cleaned_data["task"]
            # 将新任务添加到当前会话的任务列表中
            request.session["tasks"] += [task]
            # 重定向前，确保保存会话（Django 默认会保存）
            return redirect(reverse("tasks:index"))
        else:
            return render(request, "tasks/add.html", {"form": form})
    return render(request, "tasks/add.html", {"form": NewTaskForm()})
```

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_65.png)

现在，不同浏览器或隐身窗口访问网站，会拥有各自独立的会话和任务列表。

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_67.png)

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_69.png)

我们还可以改进 `index.html`，当任务列表为空时显示友好的提示。

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_71.png)

```html
<!-- index.html -->
{% block body %}
    <h1>Tasks</h1>
    <ul>
        {% for task in tasks %}
            <li>{{ task }}</li>
        {% empty %}
            <li>No tasks yet.</li>
        {% endfor %}
    </ul>
    <a href="{% url 'tasks:add' %}">Add a New Task</a>
{% endblock %}
```

## 总结

![](img/6acd1d7a2f7273f2e4fdae2de65f83ed_75.png)

本节课中我们一起学习了Django Web编程的几个核心概念：

1.  **创建多页面应用**：通过定义新的视图和URL配置来添加功能页面。
2.  **模板继承**：使用 `{% extends %}` 和 `{% block %}` 来消除HTML代码重复，提升可维护性。
3.  **URL命名与命名空间**：使用 `name` 参数为URL命名，并通过 `app_name` 和 `{% url 'app:name' %}` 解决命名冲突，实现动态、解耦的链接生成。
4.  **表单处理**：
    *   使用 `POST` 方法提交表单。
    *   添加 `{% csrf_token %}` 以防止跨站请求伪造攻击。
    *   利用Django的 `forms.Form` 类简化表单创建、渲染和验证。
    *   在视图中区分处理 `GET` 和 `POST` 请求，使用 `form.is_valid()` 和 `form.cleaned_data` 处理提交的数据。
5.  **会话（Session）**：使用 `request.session`（一个类字典对象）为每个用户存储独立的数据，实现了多用户环境下数据的隔离，这是构建交互式Web应用的基础。

通过这些技术，我们构建了一个具有基本功能的多用户任务管理应用，它能够安全地接收用户输入并持久化用户特定的数据。这为学习更复杂的数据库操作和Django模型打下了坚实的基础。