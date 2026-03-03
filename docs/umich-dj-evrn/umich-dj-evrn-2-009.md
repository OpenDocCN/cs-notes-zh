# Django for Everybody：4.9：Bootstrap导航菜单实战教程 🧭

![](img/cfb146335d3ed3fc5a988a44b5a69503_1.png)

## 概述
在本节课中，我们将学习如何在Django应用中集成一个功能完整的Bootstrap导航菜单。这个菜单将包含页面链接、下拉菜单、用户登录状态显示以及Gravatar头像等功能。我们将重点讲解如何通过模板继承复用菜单，以及如何根据当前页面动态高亮菜单项。

---

## 菜单结构与模板继承

上一节我们介绍了Bootstrap的基础布局。本节中我们来看看如何构建一个可复用的导航菜单。

我们采用多层模板继承的方式来组织代码：
1.  **`base_bootstrap.html`**： 提供基础的Bootstrap页面框架。
2.  **`base_menu.html`**： 继承自 `base_bootstrap.html`，并专门定义导航栏区域（`block nav_bar`）。
3.  具体的页面模板（如 `main_menu.html`）： 继承自 `base_menu.html`，只需关注页面主体内容（`block content`）。

这种结构类似于面向对象编程中的继承，让我们可以逐层定制和扩展功能。`base_menu.html` 的关键作用是重写了 `base_bootstrap.html` 中的 `nav_bar` 块。



## 构建导航菜单

以下是构建Bootstrap导航菜单的核心步骤，主要代码位于 `base_menu.html` 中。

### 1. 菜单基础框架
我们首先按照Bootstrap官方文档的指导，构建导航栏的基本HTML结构，包括品牌标识、响应式折叠按钮等。

```html
<nav class="navbar navbar-expand-md navbar-dark bg-dark">
    <a class="navbar-brand" href="/">Brand</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarCollapse">
        <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarCollapse">
        <!-- 左侧菜单和右侧菜单将放在这里 -->
    </div>
</nav>
```

### 2. 动态高亮当前页面
一个常见的需求是让用户知道当前位于哪个页面。我们通过对比当前请求的路径与菜单项链接来实现高亮。

在Django模板中，我们可以使用 `{% url %}` 标签生成链接，并用 `request.path` 获取当前路径。

```html
<ul class="navbar-nav mr-auto">
    {% url ‘menu:main‘ as xyz %}
    <li class="nav-item {% if request.path == xyz %}active{% endif %}">
        <a class="nav-link" href="{% url ‘menu:main‘ %}">主页</a>
    </li>
    {% url ‘menu:page1‘ as xyz %}
    <li class="nav-item {% if request.path == xyz %}active{% endif %}">
        <a class="nav-link" href="{% url ‘menu:page1‘ %}">页面一</a>
    </li>
</ul>
```
**代码解释**：
*   `{% url ‘menu:main‘ as xyz %}`： 将名为 `‘menu:main‘` 的URL路径计算结果存入变量 `xyz`。
*   `{% if request.path == xyz %}active{% endif %}`： 如果当前请求路径 `request.path` 等于菜单项链接，则为该 `<li>` 标签添加 `active` 类。Bootstrap 的 `active` 类会改变菜单项的背景色，实现高亮效果。

### 3. 处理用户登录状态
导航栏右侧通常显示用户相关的信息。我们需要根据用户是否登录来显示不同的内容。

```html
<ul class="navbar-nav ml-auto">
    {% if user.is_authenticated %}
        <!-- 用户已登录：显示下拉菜单，包含Gravatar和登出链接 -->
        <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="#" id="userMenu" data-toggle="dropdown">
                <img src="{{ user|gravatar:60 }}" class="rounded-circle" style="width: 30px; height: 30px;">
            </a>
            <div class="dropdown-menu">
                <a class="dropdown-item" href="{% url ‘logout‘ %}?next={{ request.path }}">登出</a>
            </div>
        </li>
    {% else %}
        <!-- 用户未登录：显示登录链接 -->
        <li class="nav-item">
            <a class="nav-link" href="{% url ‘login‘ %}?next={{ request.path }}">登录</a>
        </li>
    {% endif %}
</ul>
```
**代码解释**：
*   `{% if user.is_authenticated %}`： 判断当前用户是否已通过认证（登录）。
*   **已登录状态**：显示一个下拉菜单，其中包含用户头像（通过Gravatar显示）和“登出”链接。`?next={{ request.path }}` 参数确保用户登出或登录后能返回当前页面。
*   **未登录状态**：显示一个“登录”链接。



## 集成Gravatar头像

Gravatar是一项全球公认的头像服务。我们可以通过用户的邮箱地址获取其Gravatar头像。

### 1. 在模板中使用Gravatar
在模板中，我们使用自定义的模板过滤器 `gravatar` 来生成头像URL。

```html
<img src="{{ user|gravatar:60 }}" class="rounded-circle">
```
这行代码会将 `user` 对象（通常是 `request.user`）的邮箱地址处理后，生成一个边长为60像素的Gravatar头像URL。

### 2. 创建自定义模板过滤器
我们需要在Django应用中创建一个自定义的模板标签来生成Gravatar URL。

在 `yourapp/templatetags/app_tags.py` 文件中：

```python
import hashlib
from django import template

register = template.Library()

@register.filter
def gravatar(user, size=60):
    # 获取用户邮箱，处理并生成MD5哈希
    email = user.email.strip().lower().encode(‘utf-8‘)
    email_hash = hashlib.md5(email).hexdigest()
    # 构建Gravatar URL
    gravatar_url = f"https://www.gravatar.com/avatar/{email_hash}?s={size}&d=identicon"
    return gravatar_url
```
**原理**：
1.  获取用户邮箱，去除空格并转为小写。
2.  使用MD5算法对邮箱进行**单向哈希**。这能保护用户邮箱隐私，因为无法从哈希值反推出原始邮箱。
3.  将哈希值插入到Gravatar的标准URL格式中，并指定尺寸参数 `s`。

![](img/cfb146335d3ed3fc5a988a44b5a69503_3.png)

![](img/cfb146335d3ed3fc5a988a44b5a69503_5.png)

### 3. 在模板中加载标签
在使用自定义过滤器的模板顶部，需要先加载它。

```html
{% load app_tags %}
```

---

## 总结
本节课中我们一起学习了如何为Django应用创建一个专业、动态的Bootstrap导航菜单。

我们掌握了以下核心技能：
*   利用Django的**模板继承机制**（`extends` 和 `block`）来复用菜单代码，保持项目结构清晰。
*   通过比较 `request.path` 与菜单URL，实现**当前页面高亮**（`active` 类）。
*   根据 `user.is_authenticated` 条件判断，在菜单中**动态切换登录/登出状态**的显示。
*   创建并使用**自定义模板过滤器**（`gravatar`），集成Gravatar全球头像服务，并理解了其通过MD5哈希保护用户隐私的原理。

![](img/cfb146335d3ed3fc5a988a44b5a69503_7.png)

这个菜单组件是Web应用的通用基础模块。你可以直接使用课程提供的示例代码，并根据需要修改菜单项链接和品牌信息，快速应用到自己的项目中。