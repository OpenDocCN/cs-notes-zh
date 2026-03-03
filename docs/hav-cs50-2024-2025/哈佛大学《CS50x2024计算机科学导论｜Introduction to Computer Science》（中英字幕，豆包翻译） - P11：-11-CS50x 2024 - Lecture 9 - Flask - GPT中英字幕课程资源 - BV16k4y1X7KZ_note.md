# CS50x 2024：第9讲：Flask 🚀

![](img/9e2f9fda28bc5aece4246768d8d754a6_0.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_1.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_2.png)

在本节课中，我们将学习如何使用Flask框架构建动态Web应用程序。我们将从静态网站过渡到能够处理用户输入、与数据库交互并提供个性化内容的交互式应用。

---

## 概述 📋

![](img/9e2f9fda28bc5aece4246768d8d754a6_4.png)

到目前为止，我们一直使用HTTP服务器来提供静态内容，例如预先编写好的HTML、CSS和JavaScript文件。然而，现代Web应用程序（如Gmail或Google搜索）是动态的：它们根据用户输入实时生成内容，通常涉及数据库查询。在本节中，我们将介绍Flask，一个用于Python的轻量级Web框架，它使我们能够轻松创建此类动态应用程序。

![](img/9e2f9fda28bc5aece4246768d8d754a6_6.png)

我们将从创建一个简单的“Hello, World”应用开始，逐步构建更复杂的功能，如表单处理、数据验证、会话管理和与SQL数据库的集成。

---

## 从静态到动态 🌐

上一节我们介绍了静态网站。本节中，我们来看看如何使网站变得动态。

### URL、路径与路由

回顾一下，URL可以包含路径和查询参数。例如：
*   `https://example.com/` - 默认路径。
*   `https://example.com/folder/file.html` - 映射到服务器文件系统。
*   `https://www.google.com/search?q=cats` - 包含输入参数（`q=cats`）的路径。

![](img/9e2f9fda28bc5aece4246768d8d754a6_8.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_9.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_10.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_12.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_13.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_14.png)

在动态Web应用中，路径（Path）通常被称为路由（Route）。我们不再需要URL严格对应服务器上的物理文件。相反，我们可以用代码定义路由，并决定每个路由触发什么操作。

### 引入Flask框架

![](img/9e2f9fda28bc5aece4246768d8d754a6_16.png)

Flask是一个Python的“微框架”，它提供了一套工具和约定，简化了Web应用的开发。与功能更全但更复杂的Django等框架相比，Flask更轻量，适合快速构建小型到中型的应用。

使用Flask时，我们不再运行`http-server`，而是运行`flask run`来启动我们的应用服务器。

![](img/9e2f9fda28bc5aece4246768d8d754a6_18.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_19.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_20.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_22.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_23.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_24.png)

---

![](img/9e2f9fda28bc5aece4246768d8d754a6_26.png)

## 创建第一个Flask应用 🛠️

![](img/9e2f9fda28bc5aece4246768d8d754a6_28.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_30.png)

让我们从创建一个最简单的“Hello, World”应用开始，但我们将以动态的方式实现它。

![](img/9e2f9fda28bc5aece4246768d8d754a6_32.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_33.png)

### 项目结构

Flask应用通常遵循一个约定的文件结构：
*   `app.py`：主应用文件，包含核心逻辑。
*   `templates/` 目录：存放HTML模板文件。
*   `requirements.txt`：列出项目依赖的Python库。
*   `static/` 目录：存放静态文件（如图片、CSS、JavaScript）。

![](img/9e2f9fda28bc5aece4246768d8d754a6_35.png)

以下是创建项目的基本步骤：

![](img/9e2f9fda28bc5aece4246768d8d754a6_37.png)

1.  **创建项目文件夹和文件**：
    ```bash
    mkdir hello
    cd hello
    touch app.py
    mkdir templates
    ```

2.  **创建HTML模板** (`templates/index.html`)：
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Hello</title>
    </head>
    <body>
        <h1>Hello, World!</h1>
    </body>
    </html>
    ```

![](img/9e2f9fda28bc5aece4246768d8d754a6_39.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_40.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_41.png)

3.  **编写Flask应用** (`app.py`)：
    ```python
    from flask import Flask, render_template

    app = Flask(__name__)

    @app.route("/")
    def index():
        return render_template("index.html")
    ```

4.  **运行应用**：
    ```bash
    flask run
    ```
    访问终端输出的URL（通常是 `http://127.0.0.1:5000`），你将看到“Hello, World!”页面。

**代码解释**：
*   `from flask import Flask, render_template`：导入Flask核心类和用于渲染模板的函数。
*   `app = Flask(__name__)`：创建Flask应用实例。`__name__`是一个特殊变量，代表当前模块的名称。
*   `@app.route("/")`：这是一个装饰器，它将下面的函数与Web应用的根路径（`/`）绑定。当用户访问根URL时，将调用`index`函数。
*   `def index():`：定义处理根路由的函数。
*   `return render_template("index.html")`：该函数返回`templates`目录下`index.html`文件的内容。

---

![](img/9e2f9fda28bc5aece4246768d8d754a6_43.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_44.png)

## 处理用户输入 📝

![](img/9e2f9fda28bc5aece4246768d8d754a6_46.png)

上一节我们创建了一个基本的Flask应用。本节中，我们来看看如何接收并处理用户通过URL传递的参数，使我们的问候语个性化。

![](img/9e2f9fda28bc5aece4246768d8d754a6_48.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_50.png)

### 通过URL参数获取输入

![](img/9e2f9fda28bc5aece4246768d8d754a6_52.png)

我们可以修改应用，使其从URL的查询字符串中读取一个`name`参数。

![](img/9e2f9fda28bc5aece4246768d8d754a6_54.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_56.png)

1.  **修改模板** (`templates/index.html`)，添加一个占位符：
    ```html
    <body>
        <h1>Hello, {{ placeholder }}!</h1>
    </body>
    ```
    这里的双花括号 `{{ ... }}` 是Jinja2模板引擎的语法，用于插入变量。

![](img/9e2f9fda28bc5aece4246768d8d754a6_58.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_59.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_61.png)

2.  **修改应用逻辑** (`app.py`)，从请求中获取参数并传递给模板：
    ```python
    from flask import Flask, render_template, request

    app = Flask(__name__)

    @app.route("/")
    def index():
        # 从URL查询参数中获取‘name’的值，如果不存在则默认为‘world’
        name = request.args.get("name", "world")
        # 将变量‘name’的值传递给模板，在模板中它被称为‘placeholder’
        return render_template("index.html", placeholder=name)
    ```

![](img/9e2f9fda28bc5aece4246768d8d754a6_63.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_64.png)

3.  **测试**：
    *   访问 `http://127.0.0.1:5000/` 会显示 “Hello, world!”。
    *   访问 `http://127.0.0.1:5000/?name=David` 会显示 “Hello, David!”。

![](img/9e2f9fda28bc5aece4246768d8d754a6_66.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_68.png)

**代码解释**：
*   `from flask import request`：导入`request`对象，它封装了客户端发来的HTTP请求的所有信息。
*   `request.args`：这是一个类似字典的对象，包含了URL查询字符串中的所有参数（即`?`后面的部分）。
*   `.get("name", "world")`：安全地从`args`字典中获取键为`"name"`的值。如果键不存在，则返回默认值`"world"`。这避免了因缺少参数而导致的错误。
*   `render_template("index.html", placeholder=name)`：调用`render_template`函数时，可以传递任意数量的关键字参数。这些参数会成为模板中的变量。这里我们将Python变量`name`的值传递给了模板变量`placeholder`。

![](img/9e2f9fda28bc5aece4246768d8d754a6_70.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_71.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_72.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_73.png)

### 使用表单改进用户体验

![](img/9e2f9fda28bc5aece4246768d8d754a6_75.png)

让用户手动修改URL并不友好。更常见的做法是使用HTML表单。

![](img/9e2f9fda28bc5aece4246768d8d754a6_77.png)

1.  **创建表单模板** (`templates/form.html`)：
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Greet Form</title>
    </head>
    <body>
        <form action="/greet" method="get">
            <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
            <button type="submit">Greet</button>
        </form>
    </body>
    </html>
    ```

![](img/9e2f9fda28bc5aece4246768d8d754a6_79.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_80.png)

2.  **创建结果显示模板** (`templates/greet.html`)：
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Greeting</title>
    </head>
    <body>
        <h1>Hello, {{ name }}!</h1>
    </body>
    </html>
    ```

3.  **更新应用逻辑** (`app.py`)，处理两个路由：
    ```python
    from flask import Flask, render_template, request

    app = Flask(__name__)

    @app.route("/")
    def index():
        # 显示表单页面
        return render_template("form.html")

    @app.route("/greet")
    def greet():
        # 处理表单提交，获取名字并显示问候语
        name = request.args.get("name", "world")
        return render_template("greet.html", name=name)
    ```

**代码解释**：
*   `<form action="/greet" method="get">`：表单的`action`属性指定了数据提交的目标URL（`/greet`路由）。`method="get"`意味着表单数据会附加在URL的查询字符串中发送。
*   当用户访问根路径`/`时，`index`函数返回表单页面。
*   当用户填写表单并点击提交后，浏览器会向`/greet?name=输入的值`发送请求。`greet`函数从`request.args`中获取`name`参数，并将其传递给`greet.html`模板进行渲染。

---

## 使用模板继承优化设计 🧩

![](img/9e2f9fda28bc5aece4246768d8d754a6_82.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_83.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_85.png)

上一节我们创建了多个HTML文件，但它们有大量重复的代码（如`<html>`, `<head>`, `<body>`标签）。本节中，我们来看看如何使用Jinja2的模板继承功能来消除这种重复，使代码更易于维护。

![](img/9e2f9fda28bc5aece4246768d8d754a6_87.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_88.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_89.png)

### 创建基础布局模板

![](img/9e2f9fda28bc5aece4246768d8d754a6_91.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_92.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_93.png)

首先，创建一个包含通用结构的基础模板 `templates/layout.html`：

![](img/9e2f9fda28bc5aece4246768d8d754a6_95.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_97.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_98.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{% block title %}My App{% endblock %}</title>
</head>
<body>
    {% block body %}
    {% endblock %}
</body>
</html>
```

![](img/9e2f9fda28bc5aece4246768d8d754a6_100.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_101.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_103.png)

**代码解释**：
*   `{% block body %}` 和 `{% endblock %}`：定义了一个名为`body`的“块”（block）。子模板可以覆盖这个块，插入自己独特的内容。`title`块同理。

![](img/9e2f9fda28bc5aece4246768d8d754a6_105.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_107.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_108.png)

### 创建继承布局的子模板

然后，修改 `templates/form.html` 和 `templates/greet.html`，让它们继承自 `layout.html`：

![](img/9e2f9fda28bc5aece4246768d8d754a6_110.png)

**`templates/form.html`**:
```html
{% extends "layout.html" %}

![](img/9e2f9fda28bc5aece4246768d8d754a6_112.png)

{% block title %}
    Greet Form
{% endblock %}

{% block body %}
    <form action="/greet" method="get">
        <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
        <button type="submit">Greet</button>
    </form>
{% endblock %}
```

![](img/9e2f9fda28bc5aece4246768d8d754a6_114.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_115.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_116.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_118.png)

**`templates/greet.html`**:
```html
{% extends "layout.html" %}

![](img/9e2f9fda28bc5aece4246768d8d754a6_120.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_121.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_122.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_123.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_124.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_126.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_127.png)

{% block title %}
    Greeting
{% endblock %}

![](img/9e2f9fda28bc5aece4246768d8d754a6_129.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_130.png)

{% block body %}
    <h1>Hello, {{ name }}!</h1>
{% endblock %}
```

![](img/9e2f9fda28bc5aece4246768d8d754a6_132.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_133.png)

**代码解释**：
*   `{% extends "layout.html" %}`：声明此模板继承自`layout.html`。
*   `{% block title %}...{% endblock %}` 和 `{% block body %}...{% endblock %}`：用自定义的内容填充（或覆盖）父模板中定义的相应块。

![](img/9e2f9fda28bc5aece4246768d8d754a6_135.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_137.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_138.png)

这样，所有页面的共同结构只需在`layout.html`中定义一次。如果需要修改网站标题或添加全局CSS，只需改动这一个文件。

![](img/9e2f9fda28bc5aece4246768d8d754a6_140.png)

---

![](img/9e2f9fda28bc5aece4246768d8d754a6_142.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_143.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_144.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_146.png)

## 使用POST方法增强隐私与安全 🔒

![](img/9e2f9fda28bc5aece4246768d8d754a6_148.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_149.png)

上一节我们使用GET方法提交表单，数据会显示在URL中。本节中，我们来看看当处理敏感信息（如密码）时，如何使用POST方法来提高隐私性。

### 将表单方法改为POST

1.  **修改表单模板** (`templates/form.html`)：
    ```html
    <form action="/greet" method="post">
        <!-- 输入字段不变 -->
        <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
        <button type="submit">Greet</button>
    </form>
    ```

![](img/9e2f9fda28bc5aece4246768d8d754a6_151.png)

2.  **更新应用逻辑** (`app.py`)，使其支持POST请求并从一个路由处理两种方法：
    ```python
    from flask import Flask, render_template, request

    app = Flask(__name__)

    @app.route("/", methods=["GET", "POST"])
    def index():
        if request.method == "POST":
            # 处理表单提交（POST请求）
            # 注意：POST表单数据在 request.form 中，而不是 request.args
            name = request.form.get("name", "world")
            return render_template("greet.html", name=name)
        else:
            # 显示表单页面（GET请求）
            return render_template("form.html")
    ```

![](img/9e2f9fda28bc5aece4246768d8d754a6_153.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_154.png)

**代码解释**：
*   `methods=["GET", "POST"]`：通过`@app.route`装饰器的`methods`参数，明确指定该路由同时接受GET和POST请求。
*   `request.method`：检查当前请求是GET还是POST。
*   `request.form`：当表单使用`method="post"`提交时，数据不会出现在URL中，而是存储在HTTP请求的正文里。在Flask中，可以通过`request.form`（也是一个类似字典的对象）来访问这些数据。
*   逻辑流程：用户首次访问`/`（GET请求）时，看到表单。填写表单并提交后，浏览器发送POST请求到同一个URL`/`。`index`函数检测到是POST请求，便从`request.form`中提取数据并渲染结果页面。

![](img/9e2f9fda28bc5aece4246768d8d754a6_156.png)

**重要安全原则**：永远不要信任用户输入。无论是来自`request.args`还是`request.form`，所有用户提供的数据都必须进行验证和清理，以防止安全漏洞（如SQL注入或跨站脚本攻击）。

---

## 构建一个完整的应用：新生运动会注册 🏀

![](img/9e2f9fda28bc5aece4246768d8d754a6_158.png)

现在，让我们综合运用所学知识，构建一个更复杂的模拟应用：一个新生运动会（Frosh IMs）在线注册系统。

![](img/9e2f9fda28bc5aece4246768d8d754a6_159.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_161.png)

### 功能规划
1.  显示一个注册表单，包含姓名和运动项目下拉菜单。
2.  在服务器端验证用户输入。
3.  将成功的注册信息存储起来（先使用内存，后改用数据库）。
4.  显示所有已注册人员的列表。
5.  允许注销（删除注册）。

![](img/9e2f9fda28bc5aece4246768d8d754a6_163.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_164.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_166.png)

### 版本1：基础表单与内存存储

![](img/9e2f9fda28bc5aece4246768d8d754a6_167.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_168.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_170.png)

以下是实现的核心步骤和代码片段：

![](img/9e2f9fda28bc5aece4246768d8d754a6_172.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_173.png)

1.  **定义运动项目列表和应用结构** (`app.py`)：
    ```python
    from flask import Flask, render_template, request, redirect

    app = Flask(__name__)

    # 全局变量（在内存中）存储注册信息。注意：服务器重启会丢失数据！
    SPORTS = ["Basketball", "Soccer", "Ultimate Frisbee"]
    registrants = {}

    @app.route("/")
    def index():
        return render_template("index.html", sports=SPORTS)

    @app.route("/register", methods=["POST"])
    def register():
        # 1. 验证输入
        name = request.form.get("name")
        sport = request.form.get("sport")

        if not name or sport not in SPORTS:
            # 验证失败，返回错误页面
            return render_template("failure.html")

        # 2. 存储注册信息（在内存字典中）
        registrants[name] = sport

        # 3. 重定向到注册者列表页面
        return redirect("/registrants")

    @app.route("/registrants")
    def show_registrants():
        return render_template("registrants.html", registrants=registrants)
    ```

2.  **创建注册表单模板** (`templates/index.html`)，使用Jinja2循环动态生成运动项目选项：
    ```html
    {% extends "layout.html" %}
    {% block body %}
        <h1>Register</h1>
        <form action="/register" method="post">
            <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
            <select name="sport">
                <option disabled selected>Sport</option>
                {% for sport in sports %}
                    <option value="{{ sport }}">{{ sport }}</option>
                {% endfor %}
            </select>
            <button type="submit">Register</button>
        </form>
    {% endblock %}
    ```

3.  **创建注册者列表模板** (`templates/registrants.html`)：
    ```html
    {% extends "layout.html" %}
    {% block body %}
        <h1>Registrants</h1>
        <table>
            <thead>
                <tr><th>Name</th><th>Sport</th></tr>
            </thead>
            <tbody>
                {% for name, sport in registrants.items() %}
                    <tr><td>{{ name }}</td><td>{{ sport }}</td></tr>
                {% endfor %}
            </tbody>
        </table>
    {% endblock %}
    ```

**关键点**：
*   **服务器端验证**：在`register`函数中，我们检查`name`是否提供，以及`sport`是否在我们预定义的`SPORTS`列表中。这至关重要，因为用户可能通过浏览器开发者工具篡改表单，提交无效数据。**永远不要只依赖客户端的验证**。
*   **重定向**：注册成功后，使用`redirect("/registrants")`将用户引导至列表页面。这是一种“Post/Redirect/Get”模式，可以防止用户刷新页面时重复提交表单。

### 版本2：集成SQL数据库持久化存储

内存存储不可靠。让我们使用SQLite数据库来永久保存数据。

1.  **数据库模式** (`froshims.db`)：
    ```sql
    CREATE TABLE registrants (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        name TEXT NOT NULL,
        sport TEXT NOT NULL
    );
    ```

2.  **更新应用逻辑** (`app.py`)，使用CS50 SQL库进行数据库操作：
    ```python
    from flask import Flask, render_template, request, redirect
    from cs50 import SQL

    app = Flask(__name__)
    db = SQL("sqlite:///froshims.db")
    SPORTS = ["Basketball", "Soccer", "Ultimate Frisbee"]

    @app.route("/")
    def index():
        return render_template("index.html", sports=SPORTS)

    @app.route("/register", methods=["POST"])
    def register():
        name = request.form.get("name")
        sport = request.form.get("sport")

        if not name or sport not in SPORTS:
            return render_template("failure.html")

        # 将数据插入数据库
        db.execute("INSERT INTO registrants (name, sport) VALUES(?, ?)", name, sport)

        return redirect("/registrants")

    @app.route("/registrants")
    def show_registrants():
        # 从数据库查询所有注册者
        registrants = db.execute("SELECT * FROM registrants")
        return render_template("registrants.html", registrants=registrants)

    @app.route("/deregister", methods=["POST"])
    def deregister():
        # 根据唯一ID删除注册者
        id = request.form.get("id")
        if id:
            db.execute("DELETE FROM registrants WHERE id = ?", id)
        return redirect("/registrants")
    ```

3.  **更新注册者列表模板** (`templates/registrants.html`)，为每条记录添加一个注销按钮：
    ```html
    <tbody>
        {% for registrant in registrants %}
            <tr>
                <td>{{ registrant.name }}</td>
                <td>{{ registrant.sport }}</td>
                <td>
                    <form action="/deregister" method="post">
                        <!-- 隐藏字段，传递要删除的记录的唯一ID -->
                        <input name="id" type="hidden" value="{{ registrant.id }}">
                        <button type="submit">Deregister</button>
                    </form>
                </td>
            </tr>
        {% endfor %}
    </tbody>
    ```

![](img/9e2f9fda28bc5aece4246768d8d754a6_175.png)

**代码解释**：
*   `from cs50 import SQL` 和 `db = SQL("sqlite:///froshims.db")`：初始化数据库连接。
*   `db.execute("INSERT ... VALUES(?, ?)", name, sport)`：使用参数化查询插入数据。`?`是占位符，库会自动用`name`和`sport`变量的值安全地替换它们。**这可以防止SQL注入攻击**。
*   `registrants = db.execute("SELECT * FROM registrants")`：执行查询，返回一个列表，列表中的每个元素都是一个字典，代表一行记录。字典的键是列名。
*   在模板中，使用`{{ registrant.id }}`、`{{ registrant.name }}`等来访问每一行的不同列。
*   注销功能通过一个包含隐藏字段`<input name="id" value="{{ registrant.id }}">`的小表单实现。当点击“Deregister”按钮时，该记录的唯一`id`会被发送到服务器，用于执行精确的`DELETE`操作。

![](img/9e2f9fda28bc5aece4246768d8d754a6_177.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_178.png)

这个例子展示了典型的**MVC（模型-视图-控制器）** 模式：
*   **模型 (Model)**：数据库 (`froshims.db`) 和与之交互的逻辑（在`app.py`的SQL语句中）。
*   **视图 (View)**：HTML模板文件 (`templates/` 目录下的文件)。
*   **控制器 (Controller)**：`app.py` 中的Flask路由函数，它处理请求，协调模型和视图。

![](img/9e2f9fda28bc5aece4246768d8d754a6_180.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_182.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_184.png)

---

![](img/9e2f9fda28bc5aece4246768d8d754a6_186.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_187.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_189.png)

## 实现用户会话与状态管理 🍪

![](img/9e2f9fda28bc5aece4246768d8d754a6_191.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_192.png)

Web本身是无状态的，这意味着服务器默认不会记住之前的请求来自谁。为了实现登录、购物车等功能，我们需要一种机制来维持“状态”或“会话”。

![](img/9e2f9fda28bc5aece4246768d8d754a6_194.png)

### Cookie的工作原理

![](img/9e2f9fda28bc5aece4246768d8d754a6_196.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_197.png)

服务器可以通过在HTTP响应头中设置`Set-Cookie`来要求浏览器存储一小段信息（一个“Cookie”）。浏览器之后向同一服务器发出的每个请求，都会自动在请求头中包含这个`Cookie`。这就像进入游乐场时在手背上盖个章，之后再进入时出示手章即可，无需再次购票。

### 使用Flask-Session管理会话

Flask提供了`session`对象，它像一个字典，可以安全地存储用户特定的数据（如用户名、购物车物品）。Flask在后台使用Cookie来实现这一点，但为我们处理了所有复杂细节。

![](img/9e2f9fda28bc5aece4246768d8d754a6_199.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_201.png)

1.  **配置和使用会话** (`app.py`):
    ```python
    from flask import Flask, render_template, request, redirect, session
    from flask_session import Session

    app = Flask(__name__)

    # 配置会话
    app.config["SESSION_PERMANENT"] = False
    app.config["SESSION_TYPE"] = "filesystem"
    Session(app)

    @app.route("/")
    def index():
        # 从会话中获取用户名，如果不存在则为None
        name = session.get("name")
        return render_template("index.html", name=name)

    @app.route("/login", methods=["GET", "POST"])
    def login():
        if request.method == "POST":
            # 将用户名存入会话
            session["name"] = request.form.get("name")
            return redirect("/")
        else:
            return render_template("login.html")

    @app.route("/logout")
    def logout():
        # 清除会话中的所有数据
        session.clear()
        return redirect("/")
    ```

2.  **创建登录模板** (`templates/login.html`):
    ```html
    {% extends "layout.html" %}
    {% block body %}
        <form action="/login" method="post">
            <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
            <button type="submit">Log In</button>
        </form>
    {% endblock %}
    ```

3.  **更新首页模板** (`templates/index.html`)，根据登录状态显示不同内容：
    ```html
    {% extends "layout.html" %}
    {% block body %}
        {% if name %}
            <h1>You are logged in as {{ name }}.</h1>
            <a href="/logout">Log Out</a>
        {% else %}
            <h1>You are not logged in.</h1>
            <a href="/login">Log In</a>
        {% endif %}
    {% endblock %}
    ```

![](img/9e2f9fda28bc5aece4246768d8d754a6_203.png)

**代码解释**：
*   `session` 对象的行为就像一个Python字典。存储在其中的数据与当前访问者的浏览器唯一关联。
*   `session["name"] = ...`：存储数据。
*   `session.get("name")`：获取数据。
*   `session.clear()`：删除所有会话数据，实现登出。
*   当用户A登录时，`session["name"]` 对用户A的浏览器是“David”。当用户B访问时，`session["name"]` 对用户B的浏览器初始为`None`，他们是完全独立的。

![](img/9e2f9fda28bc5aece4246768d8d754a6_205.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_207.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_208.png)

---

![](img/9e2f9fda28bc5aece4246768d8d754a6_209.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_211.png)

## 构建异步Web应用与API 🌉

![](img/9e2f9fda28bc5aece4246768d8d754a6_213.png)

现代Web应用追求更流畅的用户体验，比如在输入时实时显示搜索建议，而无需重新加载整个页面。这通常通过异步JavaScript（Ajax）和API来实现。

![](img/9e2f9fda28bc5aece4246768d8d754a6_215.png)

### 实现实时搜索建议

![](img/9e2f9fda28bc5aece4246768d8d754a6_217.png)

1.  **后端API端点** (`app.py`):
    ```python
    from flask import Flask, render_template, request, jsonify
    from cs50 import SQL

    app = Flask(__name__)
    db = SQL("sqlite:///shows.db")

    @app.route("/")
    def index():
        return render_template("index.html")

    @app.route("/search")
    def search():
        q = request.args.get("q", "")
        # 使用LIKE进行模糊查询，%是通配符
        shows = db.execute("SELECT * FROM shows WHERE title LIKE ?", f"%{q}%")
        # 将Python列表直接转换为JSON格式返回
        return jsonify(shows)
    ```

![](img/9e2f9fda28bc5aece4246768d8d754a6_219.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_221.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_222.png)

2.  **前端页面与JavaScript** (`templates/index.html`):
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Search</title>
    </head>
    <body>
        <input autocomplete="off" autofocus placeholder="Query" type="search" id="q">
        <ul id="results"></ul>

        <script>
            let input = document.querySelector('#q');
            let results = document.querySelector('#results');

            input.addEventListener('input', async function() {
                // 获取输入框的值
                let query = this.value;
                // 使用fetch API异步向/search端点发送请求
                let response = await fetch(`/search?q=${query}`);
                // 解析返回的JSON数据
                let shows = await response.json();

                // 清空之前的列表
                results.innerHTML = '';
                // 动态创建新的列表项
                for (let show of shows) {
                    let li = document.createElement('li');
                    li.textContent = `${show.title} (${show.year})`;
                    results.appendChild(li);
                }
            });
        </script>
    </body>
    </html>
    ```

![](img/9e2f9fda28bc5aece4246768d8d754a6_223.png)

**代码解释**：
*   **API端点**：`/search`路由不再返回完整的HTML页面，而是返回`jsonify(shows)`，即一个JSON格式的数据。JSON是一种轻量级的数据交换格式，易于被JavaScript解析。
*   **前端JavaScript**:
    *   `fetch(/search?q=${query})`：向我们的API端点发送异步HTTP GET请求。
    *   `await response.json()`：将服务器返回的JSON字符串解析为JavaScript对象。
    *   随后，JavaScript动态更新页面上的`<ul>`元素，插入新的`<li>`项，而无需刷新整个页面。
*   **用户体验**：用户在输入框中每键入一个字符，都会触发一次搜索请求并即时更新下方的建议列表，体验非常流畅。

![](img/9e2f9fda28bc5aece4246768d8d754a6_225.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_226.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_227.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_229.png)

---

![](img/9e2f9fda28bc5aece4246768d8d754a6_231.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_232.png)

## 总结 🎓

本节课中我们一起学习了如何使用Flask框架构建动态Web应用程序。我们从创建一个简单的“Hello, World”应用出发，逐步掌握了以下核心概念：

![](img/9e2f9fda28bc5aece4246768d8d754a6_234.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_235.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_236.png)

1.  **Flask基础**：设置项目结构，创建路由，渲染模板。
2.  **处理用户输入**：通过`request.args`和`request.form`获取GET和POST请求中的数据，并进行安全验证。
3.  **模板引擎Jinja2**：使用变量插值`{{ }}`、控制结构`{% if %}`, `{% for %}`和模板继承`{% extends %}`来构建动态且可维护的HTML。
4.  **数据持久化**：将内存中的数据存储迁移到SQLite数据库，使用参数化查询防止SQL注入，实现了数据的增删改查。
5.  **状态管理**：利用Flask-Session和Cookie实现了用户登录/注销和会话状态保持。
6.  **现代Web交互**：通过异步JavaScript（Ajax）和JSON API，实现了无需刷新页面的实时搜索功能，提升了用户体验。

![](img/9e2f9fda28bc5aece4246768d8d754a6_238.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_239.png)

![](img/9e2f9fda28bc5aece4246768d8d754a6_241.png)

通过这些技术，你现在已经具备了构建复杂、交互式、数据驱动的Web应用程序的基本能力。这些原理是当今大多数网站（如Google、Amazon、社交媒体）运行的基础。在最终项目中，你可以运用这些知识，创造出属于自己的功能完整的Web应用。