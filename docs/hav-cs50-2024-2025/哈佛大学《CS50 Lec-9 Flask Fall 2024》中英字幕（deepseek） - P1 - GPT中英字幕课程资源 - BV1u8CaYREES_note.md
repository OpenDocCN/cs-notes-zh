# CS50：第9讲：Flask Web编程 🚀

![](img/161ff1522ea735662d7ff1bebeb0802c_0.png)

在本节课中，我们将学习如何使用Python的Flask框架进行Web编程。我们将结合之前学过的Python、HTML、CSS、JavaScript和SQL知识，构建动态的Web应用程序。通过本教程，你将学会如何创建路由、处理用户输入、使用模板、管理会话以及连接数据库。

![](img/161ff1522ea735662d7ff1bebeb0802c_2.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_4.png)

---

![](img/161ff1522ea735662d7ff1bebeb0802c_6.png)

## 概述 📋

![](img/161ff1522ea735662d7ff1bebeb0802c_8.png)

本节课我们将探索Web编程的核心概念，特别是使用Flask框架。我们将从静态网页转向动态内容生成，学习如何通过代码处理HTTP请求和响应，以及如何将用户数据持久化存储。

![](img/161ff1522ea735662d7ff1bebeb0802c_10.png)

---

![](img/161ff1522ea735662d7ff1bebeb0802c_12.png)

## 从静态到动态 🌐

![](img/161ff1522ea735662d7ff1bebeb0802c_14.png)

上一节我们介绍了HTTP协议和静态网页服务。本节中，我们来看看如何使用Flask创建动态Web应用程序。

![](img/161ff1522ea735662d7ff1bebeb0802c_16.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_18.png)

### HTTP服务器与Flask

![](img/161ff1522ea735662d7ff1bebeb0802c_20.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_21.png)

之前我们使用`http.server`命令来提供静态内容。它只能将文件内容原样发送给浏览器。从今天开始，我们将使用`flask run`命令启动一个更智能的Web服务器，它可以执行Python代码来动态生成网页。

![](img/161ff1522ea735662d7ff1bebeb0802c_23.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_24.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_25.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_27.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_28.png)

### 创建Flask应用

![](img/161ff1522ea735662d7ff1bebeb0802c_30.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_31.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_32.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_33.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_34.png)

使用Flask时，通常需要两个文件：`app.py`和`requirements.txt`。以下是创建一个简单Web应用的步骤：

![](img/161ff1522ea735662d7ff1bebeb0802c_36.png)

1.  **导入Flask库**：从Flask库中导入必要的组件。
2.  **创建应用实例**：将当前文件转换为一个Web应用。
3.  **定义路由和视图函数**：指定URL路径与处理函数之间的映射。

![](img/161ff1522ea735662d7ff1bebeb0802c_38.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_39.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_40.png)

以下是`app.py`的基本结构：

![](img/161ff1522ea735662d7ff1bebeb0802c_42.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_44.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_45.png)

```python
from flask import Flask

![](img/161ff1522ea735662d7ff1bebeb0802c_47.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_48.png)

app = Flask(__name__)

![](img/161ff1522ea735662d7ff1bebeb0802c_50.png)

@app.route("/")
def index():
    return "Hello, world"
```

![](img/161ff1522ea735662d7ff1bebeb0802c_52.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_54.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_55.png)

### 运行Flask应用

在终端中运行`flask run`命令，Flask将在默认端口5000上启动一个Web服务器。访问`http://localhost:5000`，你将看到“Hello, world”消息。

![](img/161ff1522ea735662d7ff1bebeb0802c_57.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_58.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_60.png)

---

## 处理用户输入 📝

![](img/161ff1522ea735662d7ff1bebeb0802c_62.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_64.png)

上一节我们创建了基本的Flask应用。本节中，我们来看看如何通过URL参数和表单接收用户输入。

![](img/161ff1522ea735662d7ff1bebeb0802c_66.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_68.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_69.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_70.png)

### URL参数

![](img/161ff1522ea735662d7ff1bebeb0802c_72.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_73.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_74.png)

用户可以通过在URL后添加`?key=value`的形式传递参数。例如，`http://example.com/?name=David`。在Flask中，可以使用`request.args`字典来获取这些参数。

![](img/161ff1522ea735662d7ff1bebeb0802c_76.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_77.png)

```python
from flask import request

![](img/161ff1522ea735662d7ff1bebeb0802c_79.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_80.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_82.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_83.png)

@app.route("/")
def index():
    name = request.args.get("name", "world")
    return f"Hello, {name}"
```

![](img/161ff1522ea735662d7ff1bebeb0802c_85.png)

### 表单处理

![](img/161ff1522ea735662d7ff1bebeb0802c_87.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_88.png)

通过HTML表单，用户可以更方便地提交数据。以下是创建一个简单表单的示例：

```html
<form action="/greet" method="post">
    <input type="text" name="name" placeholder="Name">
    <button type="submit">Greet</button>
</form>
```

![](img/161ff1522ea735662d7ff1bebeb0802c_90.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_91.png)

在Flask中，可以使用`request.form`字典获取通过POST方法提交的表单数据。

![](img/161ff1522ea735662d7ff1bebeb0802c_93.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_94.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_95.png)

```python
@app.route("/greet", methods=["POST"])
def greet():
    name = request.form.get("name", "world")
    return f"Hello, {name}"
```

![](img/161ff1522ea735662d7ff1bebeb0802c_97.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_98.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_99.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_101.png)

---

![](img/161ff1522ea735662d7ff1bebeb0802c_103.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_105.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_106.png)

## 使用模板生成HTML 🎨

![](img/161ff1522ea735662d7ff1bebeb0802c_108.png)

上一节我们直接在Python代码中返回HTML字符串。本节中，我们来看看如何使用模板来更好地组织HTML代码。

![](img/161ff1522ea735662d7ff1bebeb0802c_110.png)

### 创建模板

![](img/161ff1522ea735662d7ff1bebeb0802c_112.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_114.png)

Flask使用Jinja2作为模板引擎。模板文件通常放在`templates`文件夹中。例如，创建一个`index.html`模板：

![](img/161ff1522ea735662d7ff1bebeb0802c_116.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_117.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_118.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_120.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Hello</title>
</head>
<body>
    <h1>Hello, {{ name }}</h1>
</body>
</html>
```

![](img/161ff1522ea735662d7ff1bebeb0802c_122.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_123.png)

### 渲染模板

![](img/161ff1522ea735662d7ff1bebeb0802c_124.png)

在Flask中，使用`render_template`函数渲染模板并传递变量：

```python
from flask import render_template

@app.route("/")
def index():
    name = request.args.get("name", "world")
    return render_template("index.html", name=name)
```

![](img/161ff1522ea735662d7ff1bebeb0802c_126.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_128.png)

### 模板继承

![](img/161ff1522ea735662d7ff1bebeb0802c_130.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_131.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_133.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_134.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_135.png)

为了减少代码重复，可以使用模板继承。创建一个基础模板`layout.html`：

![](img/161ff1522ea735662d7ff1bebeb0802c_137.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_138.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>{% block title %}{% endblock %}</title>
</head>
<body>
    {% block body %}{% endblock %}
</body>
</html>
```

![](img/161ff1522ea735662d7ff1bebeb0802c_140.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_142.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_143.png)

在其他模板中继承基础模板：

![](img/161ff1522ea735662d7ff1bebeb0802c_145.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_146.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_147.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_148.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_149.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_150.png)

```html
{% extends "layout.html" %}

![](img/161ff1522ea735662d7ff1bebeb0802c_152.png)

{% block title %}
    Hello
{% endblock %}

![](img/161ff1522ea735662d7ff1bebeb0802c_154.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_155.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_156.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_158.png)

{% block body %}
    <h1>Hello, {{ name }}</h1>
{% endblock %}
```

![](img/161ff1522ea735662d7ff1bebeb0802c_160.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_161.png)

---

![](img/161ff1522ea735662d7ff1bebeb0802c_163.png)

## 数据持久化与数据库 🗄️

![](img/161ff1522ea735662d7ff1bebeb0802c_165.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_166.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_167.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_169.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_171.png)

上一节我们使用会话来临时存储用户数据。本节中，我们来看看如何将数据持久化存储到数据库中。

![](img/161ff1522ea735662d7ff1bebeb0802c_173.png)

### 连接数据库

![](img/161ff1522ea735662d7ff1bebeb0802c_175.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_177.png)

使用SQLite数据库存储用户数据。首先，在`app.py`中导入SQL库并连接数据库：

![](img/161ff1522ea735662d7ff1bebeb0802c_179.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_180.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_182.png)

```python
from cs50 import SQL

db = SQL("sqlite:///froshims.db")
```

![](img/161ff1522ea735662d7ff1bebeb0802c_184.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_185.png)

### 创建表

![](img/161ff1522ea735662d7ff1bebeb0802c_187.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_188.png)

在数据库中创建一个表来存储用户注册信息：

![](img/161ff1522ea735662d7ff1bebeb0802c_190.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_192.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_194.png)

```sql
CREATE TABLE registrants (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT NOT NULL,
    sport TEXT NOT NULL
);
```

![](img/161ff1522ea735662d7ff1bebeb0802c_196.png)

### 插入数据

![](img/161ff1522ea735662d7ff1bebeb0802c_198.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_199.png)

在用户提交表单时，将数据插入数据库：

![](img/161ff1522ea735662d7ff1bebeb0802c_201.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_203.png)

```python
@app.route("/register", methods=["POST"])
def register():
    name = request.form.get("name")
    sport = request.form.get("sport")
    if not name or not sport:
        return render_template("failure.html")
    db.execute("INSERT INTO registrants (name, sport) VALUES (?, ?)", name, sport)
    return render_template("success.html")
```

![](img/161ff1522ea735662d7ff1bebeb0802c_204.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_205.png)

### 查询数据

从数据库中查询数据并在模板中显示：

![](img/161ff1522ea735662d7ff1bebeb0802c_207.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_209.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_210.png)

```python
@app.route("/registrants")
def registrants():
    registrants = db.execute("SELECT * FROM registrants")
    return render_template("registrants.html", registrants=registrants)
```

![](img/161ff1522ea735662d7ff1bebeb0802c_212.png)

在模板中遍历查询结果：

```html
<ul>
    {% for registrant in registrants %}
        <li>{{ registrant.name }} - {{ registrant.sport }}</li>
    {% endfor %}
</ul>
```

![](img/161ff1522ea735662d7ff1bebeb0802c_214.png)

---

## 用户会话与登录 🔐

![](img/161ff1522ea735662d7ff1bebeb0802c_216.png)

上一节我们使用数据库存储数据。本节中，我们来看看如何使用会话来管理用户登录状态。

![](img/161ff1522ea735662d7ff1bebeb0802c_218.png)

### 启用会话

在Flask中启用会话功能：

![](img/161ff1522ea735662d7ff1bebeb0802c_220.png)

```python
from flask_session import Session

![](img/161ff1522ea735662d7ff1bebeb0802c_221.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_222.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_224.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_226.png)

app.config["SESSION_PERMANENT"] = False
app.config["SESSION_TYPE"] = "filesystem"
Session(app)
```

![](img/161ff1522ea735662d7ff1bebeb0802c_228.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_230.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_231.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_232.png)

### 用户登录

创建一个登录表单和处理登录的逻辑：

![](img/161ff1522ea735662d7ff1bebeb0802c_234.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_235.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_236.png)

```python
@app.route("/login", methods=["GET", "POST"])
def login():
    if request.method == "POST":
        session["name"] = request.form.get("name")
        return redirect("/")
    return render_template("login.html")
```

![](img/161ff1522ea735662d7ff1bebeb0802c_238.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_239.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_241.png)

### 用户登出

![](img/161ff1522ea735662d7ff1bebeb0802c_243.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_245.png)

登出时清除会话数据：

```python
@app.route("/logout")
def logout():
    session.clear()
    return redirect("/")
```

![](img/161ff1522ea735662d7ff1bebeb0802c_247.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_248.png)

### 在模板中检查登录状态

![](img/161ff1522ea735662d7ff1bebeb0802c_250.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_251.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_252.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_253.png)

在模板中根据会话数据显示不同内容：

![](img/161ff1522ea735662d7ff1bebeb0802c_255.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_256.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_257.png)

```html
{% if session.name %}
    <p>You are logged in as {{ session.name }}.</p>
    <a href="/logout">Log Out</a>
{% else %}
    <p>You are not logged in.</p>
    <a href="/login">Log In</a>
{% endif %}
```

---

![](img/161ff1522ea735662d7ff1bebeb0802c_259.png)

## 构建API与前端交互 🔄

![](img/161ff1522ea735662d7ff1bebeb0802c_261.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_262.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_264.png)

上一节我们使用模板生成HTML。本节中，我们来看看如何构建API，并通过JavaScript与前端交互。

### 创建API端点

![](img/161ff1522ea735662d7ff1bebeb0802c_266.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_267.png)

在Flask中创建一个返回JSON数据的路由：

![](img/161ff1522ea735662d7ff1bebeb0802c_269.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_271.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_272.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_273.png)

```python
from flask import jsonify

![](img/161ff1522ea735662d7ff1bebeb0802c_275.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_277.png)

@app.route("/search")
def search():
    q = request.args.get("q")
    if q:
        shows = db.execute("SELECT * FROM shows WHERE title LIKE ?", f"%{q}%")
    else:
        shows = []
    return jsonify(shows)
```

### 使用JavaScript调用API

在前端使用JavaScript调用API并动态更新页面：

![](img/161ff1522ea735662d7ff1bebeb0802c_279.png)

```html
<input type="text" id="query" placeholder="Query">
<ul id="results"></ul>

![](img/161ff1522ea735662d7ff1bebeb0802c_281.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_282.png)

<script>
    document.querySelector("#query").addEventListener("input", async function() {
        let query = this.value;
        let response = await fetch(`/search?q=${query}`);
        let shows = await response.json();
        let html = "";
        for (let show of shows) {
            html += `<li>${show.title}</li>`;
        }
        document.querySelector("#results").innerHTML = html;
    });
</script>
```

![](img/161ff1522ea735662d7ff1bebeb0802c_284.png)

---

## 总结 🎓

![](img/161ff1522ea735662d7ff1bebeb0802c_286.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_288.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_289.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_290.png)

![](img/161ff1522ea735662d7ff1bebeb0802c_292.png)

本节课我们一起学习了如何使用Flask框架进行Web编程。我们从创建简单的动态网页开始，逐步学习了处理用户输入、使用模板、连接数据库、管理用户会话以及构建API。通过结合Python、HTML、CSS、JavaScript和SQL，你现在可以构建功能完整的Web应用程序了。希望这些知识能帮助你在未来的项目中大展身手！