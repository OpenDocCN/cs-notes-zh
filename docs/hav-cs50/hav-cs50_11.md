# 第九讲

> 原文：[`cs50.harvard.edu/x/notes/9/`](https://cs50.harvard.edu/x/notes/9/)

+   欢迎！

+   http-server

+   Flask

+   表单

+   模板

+   请求方法

+   Frosh IMs

+   Flask 和 SQL

+   Cookies 和 Session

+   购物车

+   显示

+   APIs

+   JSON

+   总结

## 欢迎光临！

+   在之前的几周中，你已经学习了多种编程语言、技术和策略。

+   事实上，这门课程远不止是 *C 语言课程* 或 *Python 课程*，而更多的是一门 *编程课程*，这样你就可以继续追随未来的趋势。

+   在过去的几周中，你已经学习了 *如何学习* 编程。

+   今天，我们将从 HTML 和 CSS 转向结合 HTML、CSS、SQL、Python 和 JavaScript，以便你可以创建自己的 Web 应用程序。

+   你可以考虑使用这周学到的技能来创建你的最终项目。

## http-server

+   到目前为止，你所看到的 HTML 都是预先编写和静态的。

+   在过去，当你访问一个页面时，浏览器会下载一个 HTML 页面，你能够查看它。这些被认为是 *静态* 页面，因为在 HTML 中编程的内容正是用户看到的和下载到他们互联网浏览器中的内容。

+   动态页面指的是 Python 和类似语言创建 HTML 的即时能力。因此，你可以拥有由代码根据用户输入或行为在服务器端生成的 Web 页面。

+   你过去使用 `http-server` 来提供你的网页服务。今天，我们将利用一个新的服务器，它可以解析出网址并根据提供的 URL 执行操作。

+   此外，上周，你看到了以下这样的 URL：

    ```
    https://www.example.com/folder/file.html 
    ```

    注意到 `file.html` 是位于 `example.com` 的 `folder` 文件夹中的一个 HTML 文件。

## Flask

+   这周，我们介绍了与 *路由*（如 `https://www.example.com/route?key=value`）交互的能力，其中特定的功能可以通过 URL 中提供的键和值在服务器上生成。

+   *Flask* 是一个第三方库，它允许你使用 Flask 框架或微框架在 Python 中托管 Web 应用程序。

+   你可以在终端窗口中执行 `flask run` 来运行 Flask，在 [cs50.dev](https://cs50.dev)。

+   要这样做，你需要一个名为 `app.py` 的文件和另一个名为 `requirements.txt` 的文件。`app.py` 包含代码，告诉 Flask 如何运行你的 Web 应用程序。`requirements.txt` 包含了运行 Flask 应用程序所需的库列表。

+   这里是 `requirements.txt` 的一个示例：

    ```
    Flask 
    ```

    注意到在这个文件中只有 `Flask` 出现。这是因为 Flask 是运行 Flask 应用程序所必需的。

+   这里是一个非常简单的 `app.py` Flask 应用程序：

    ```
    # Says hello to world by returning a string of text 
    from flask import Flask, render_template, request

    app = Flask(__name__)

    @app.route("/")
    def index():
        return "hello, world" 
    ```

    注意到 `/` 路由简单地返回文本 `hello, world`。

+   我们还可以创建实现 HTML 的代码：

    ```
    # Says hello to world by returning a string of HTML 
    from flask import Flask, render_template, request

    app = Flask(__name__)

    @app.route("/")
    def index():
        return '<!DOCTYPE html><html lang="en"><head><title>hello</title></head><body>hello, world</body></html>' 
    ```

    注意到它不是返回简单的文本，而是提供了 HTML。

+   改进我们的应用程序，我们还可以通过创建一个名为 `templates` 的文件夹并创建一个包含以下代码的 `index.html` 文件来根据模板提供 HTML：

    ```
    <!DOCTYPE html>

    <html lang="en">

        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>hello</title>
        </head>

        <body>
            hello, {{ name }}
        </body>

    </html> 
    ```

    注意双大括号 `{{ name }}`，它是为我们 Flask 服务器稍后提供的某个内容的占位符。

+   然后，在 `templates` 文件夹所在的同一文件夹中，创建一个名为 `app.py` 的文件，并添加以下代码：

    ```
    # Uses request.args.get 
    from flask import Flask, render_template, request

    app = Flask(__name__)

    @app.route("/")
    def index():
        name = request.args.get("name", "world")
        return render_template("index.html", name=name) 
    ```

    注意，这段代码将 `app` 定义为 Flask 应用程序。然后，它定义了 `app` 的 `/` 路由，返回包含 `name` 参数的 `index.html` 内容。默认情况下，`request.args.get` 函数将查找用户提供的 `name`。如果没有提供名称，它将默认为 `world`。"@app.route" 通常被称为装饰器。

+   您可以通过在终端窗口中输入 `flask run` 来运行这个网络应用程序。如果 Flask 没有运行，请确保上述每个文件中的语法都正确。此外，如果 Flask 无法运行，请确保您的文件组织如下：

    ```
    /templates
        index.html
    app.py
    requirements.txt 
    ```

+   一旦运行起来，您将被提示点击一个链接。一旦您导航到该网页，请尝试在浏览器 URL 栏的基本 URL 中添加 `?name=[Your Name]`。

## 表单

+   在改进我们的程序时，我们知道大多数用户不会在地址栏中输入参数。相反，程序员依赖于用户在网页上填写表单。因此，我们可以按如下方式修改 `index.html`：

    ```
    <!DOCTYPE html>

    <html lang="en">

        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>hello</title>
        </head>

        <body>
            <form action="/greet" method="get">
                <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
                <button type="submit">Greet</button>
            </form>
        </body>

    </html> 
    ```

    注意现在创建了一个表单，它接受用户的姓名，并将其传递给名为 `/greet` 的路由。"autocomplete" 已关闭。此外，包含文本 `name` 的 `placeholder` 也被包含在内。此外，注意 `meta` 标签是如何被用来使网页响应式的。

+   此外，我们还可以按如下方式修改 `app.py`：

    ```
    # Adds a form, second route 
    from flask import Flask, render_template, request

    app = Flask(__name__)

    @app.route("/")
    def index():
        return render_template("index.html")

    @app.route("/greet")
    def greet():
        return render_template("greet.html", name=request.args.get("name", "world")) 
    ```

    注意默认路径将显示一个表单，让用户输入他们的姓名。`/greet` 路由将 `name` 传递到该网页。

+   为了完成这个实现，您需要在 `templates` 文件夹中创建一个名为 `greet.html` 的模板，如下所示：

    ```
    <!DOCTYPE html>

    <html lang="en">

        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>hello</title>
        </head>

        <body>
            hello, {{ name }}
        </body>

    </html> 
    ```

    注意，现在这个路由将向用户显示问候语，然后是他们的名字。

## 模板

+   我们的网页 `index.html` 和 `greet.html` 有很多相同的数据。如果允许主体内容独特，但复制相同的布局从页面到页面，岂不是很好？

+   首先，创建一个新的模板 `layout.html` 并编写如下代码：

    ```
    <!DOCTYPE html>

    <html lang="en">

        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>hello</title>
        </head>

        <body>
            {% block body %}{% endblock %}
        </body>

    </html> 
    ```

    注意到 `{% block body %}{% endblock %}` 允许从其他 HTML 文件中插入其他代码。

+   然后，按如下方式修改您的 `index.html`：

    ```
    {% extends "layout.html" %}

    {% block body %}

        <form action="/greet" method="get">
            <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
            <button type="submit">Greet</button>
        </form>

    {% endblock %} 
    ```

    注意到 `{% extends "layout.html" %}` 这行代码告诉服务器从哪里获取此页面的布局。然后，`{% block body %}{% endblock %}` 告诉要插入 `layout.html` 的代码。

+   最后，按如下方式修改 `greet.html`：

    ```
    {% extends "layout.html" %}

    {% block body %}
        hello, {{ name }}
    {% endblock %} 
    ```

    注意这段代码更短、更紧凑。

## 请求方法

+   您可以想象一些场景，在这些场景中不能安全地使用 `get`，因为用户名和密码会出现在 URL 中。

+   我们可以通过修改`app.py`来利用`post`方法帮助解决这个问题：

    ```
    # Switches to POST 
    from flask import Flask, render_template, request

    app = Flask(__name__)

    @app.route("/")
    def index():
        return render_template("index.html")

    @app.route("/greet", methods=["POST"])
    def greet():
        return render_template("greet.html", name=request.form.get("name", "world")) 
    ```

    注意到在`/greet`路由中添加了`POST`，并且我们使用`request.form.get`而不是`request.args.get`。

+   这告诉服务器深入查看虚拟信封，不要在 URL 中暴露`post`中的项目。

+   尽管如此，我们可以通过使用单个路由来同时处理`get`和`post`来进一步改进此代码。为此，修改`app.py`如下：

    ```
    # Uses a single route 
    from flask import Flask, render_template, request

    app = Flask(__name__)

    @app.route("/", methods=["GET", "POST"])
    def index():
        if request.method == "POST":
            return render_template("greet.html", name=request.form.get("name", "world"))
        return render_template("index.html") 
    ```

    注意到`get`和`post`都是在单个路由中完成的。然而，`request.method`被用来根据用户请求的路由类型正确路由。

+   因此，你可以按照以下方式修改你的`index.html`：

    ```
    {% extends "layout.html" %}

    {% block body %}

        <form action="/" method="post">
            <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
            <button type="submit">Greet</button>
        </form>

    {% endblock %} 
    ```

    注意到表单的`action`已被更改。

+   尽管如此，此代码中仍然存在一个错误。根据我们的新实现，当有人在没有输入名称的情况下填写表单时，会显示没有名称的`Hello,`。我们可以通过以下方式编辑`app.py`来改进我们的代码：

    ```
    # Moves default value to template 
    from flask import Flask, render_template, request

    app = Flask(__name__)

    @app.route("/", methods=["GET", "POST"])
    def index():
        if request.method == "POST":
            return render_template("greet.html", name=request.form.get("name"))
        return render_template("index.html") 
    ```

    注意到`name=request.form.get("name"))`已被更改。

+   最后，按照以下方式修改`greet.html`：

    ```
    {% extends "layout.html" %}

    {% block body %}

        hello,
        {% if name -%}
            {{ name }}
        {%- else -%}
            world
        {%- endif %}

    {% endblock %} 
    ```

    注意到`hello, {{ name }}`是如何改变以允许在没有识别到名称时输出默认值。

+   由于我们已经更改了许多文件，你可能希望将你的最终代码与[我们的最终代码](https://cdn.cs50.net/2024/fall/lectures/9/src9/hello10/)进行比较。

## Frosh IMs

+   Frosh IMs 或*froshims*是一个允许学生注册校内体育活动的网络应用程序。

+   关闭所有与`hello`相关的窗口，并在终端窗口中输入`mkdir froshims`创建一个文件夹。然后，输入`cd froshims`浏览到这个文件夹。在此文件夹内，通过输入`mkdir templates`创建一个名为`templates`的目录。

+   接下来，在`froshims`文件夹中，输入`code requirements.txt`并编写如下代码：

    ```
    Flask 
    ```

    如前所述，运行 Flask 应用程序需要 Flask。

+   最后，输入`code app.py`并编写如下代码：

    ```
    # Implements a registration form using a select menu, validating sport server-side 
    from flask import Flask, render_template, request

    app = Flask(__name__)

    SPORTS = [
        "Basketball",
        "Soccer",
        "Ultimate Frisbee"
    ]

    @app.route("/")
    def index():
        return render_template("index.html", sports=SPORTS)

    @app.route("/register", methods=["POST"])
    def register():

        # Validate submission
        if not request.form.get("name") or request.form.get("sport") not in SPORTS:
            return render_template("failure.html")

        # Confirm registration
        return render_template("success.html") 
    ```

    注意到提供了一个`failure`选项，如果`name`或`sport`字段填写不正确，将向用户显示错误信息。

+   接下来，通过输入`code templates/index.html`在`templates`文件夹中创建一个名为`index.html`的文件，并编写如下代码：

    ```
    {% extends "layout.html" %}

    {% block body %}
        <h1>Register</h1>
        <form action="/register" method="post">
            <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
            <select name="sport">
                <option disabled selected value="">Sport</option>
                {% for sport in sports %}
                    <option value="{{ sport }}">{{ sport }}</option>
                {% endfor %}
            </select>
            <button type="submit">Register</button>
        </form>
    {% endblock %} 
    ```

+   接下来，通过输入`code templates/layout.html`创建一个名为`layout.html`的文件，并编写如下代码：

    ```
    <!DOCTYPE html>

    <html lang="en">

        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>froshims</title>
        </head>

        <body>
            {% block body %}{% endblock %}
        </body>

    </html> 
    ```

+   第四，在`templates`目录下创建一个名为`success.html`的文件，如下所示：

    ```
    {% extends "layout.html" %}

    {% block body %}
        You are registered!
    {% endblock %} 
    ```

+   最后，在`templates`目录下创建一个名为`failure.html`的文件，如下所示：

    ```
    {% extends "layout.html" %}

    {% block body %}
        You are not registered!
    {% endblock %} 
    ```

+   执行`flask run`并检查此阶段的程序。

+   你可以想象我们如何使用单选按钮查看各种注册选项。我们可以通过以下方式改进`index.html`：

    ```
    {% extends "layout.html" %}

    {% block body %}
        <h1>Register</h1>
        <form action="/register" method="post">
            <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
            {% for sport in sports %}
                <input name="sport" type="radio" value="{{ sport }}"> {{ sport }}
            {% endfor %}
            <button type="submit">Register</button>
        </form>
    {% endblock %} 
    ```

    注意到`type`已被更改为`radio`。

+   再次执行`flask run`，你可以看到界面现在已更改。

+   你可以想象我们如何接受许多不同注册者的注册。我们可以通过以下方式改进`app.py`：

    ```
    # Implements a registration form, storing registrants in a dictionary, with error messages 
    from flask import Flask, redirect, render_template, request

    app = Flask(__name__)

    REGISTRANTS = {}

    SPORTS = [
        "Basketball",
        "Soccer",
        "Ultimate Frisbee"
    ]

    @app.route("/")
    def index():
        return render_template("index.html", sports=SPORTS)

    @app.route("/register", methods=["POST"])
    def register():

        # Validate name
        name = request.form.get("name")
        if not name:
            return render_template("error.html", message="Missing name")

        # Validate sport
        sport = request.form.get("sport")
        if not sport:
            return render_template("error.html", message="Missing sport")
        if sport not in SPORTS:
            return render_template("error.html", message="Invalid sport")

        # Remember registrant
        REGISTRANTS[name] = sport

        # Confirm registration
        return redirect("/registrants")

    @app.route("/registrants")
    def registrants():
        return render_template("registrants.html", registrants=REGISTRANTS) 
    ```

    注意到使用了一个名为 `REGISTRANTS` 的字典来记录 `REGISTRANTS[name]` 选定的 `sport`。同时，注意 `registrants=REGISTRANTS` 将字典传递给此模板。

+   此外，我们可以实现 `error.html`：

    ```
    {% extends "layout.html" %}

    {% block body %}
        <h1>Error</h1>
        <p>{{ message }}</p>
        <img alt="Grumpy Cat" src="/static/cat.jpg">
    {% endblock %} 
    ```

+   此外，创建一个新的模板，名为 `registrants.html`，如下所示：

    ```
    {% extends "layout.html" %}

    {% block body %}
        <h1>Registrants</h1>
        <table>
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Sport</th>
                </tr>
            </thead>
            <tbody>
                {% for name in registrants %}
                    <tr>
                        <td>{{ name }}</td>
                        <td>{{ registrants[name] }}</td>
                    </tr>
                {% endfor %}
            </tbody>
        </table>
    {% endblock %} 
    ```

    注意到 `{% for name in registrants %}...{% endfor %}` 会遍历每个注册者。能够在动态网页上迭代是非常强大的功能！

+   最后，在 `app.py` 所在的同一文件夹中创建一个名为 `static` 的文件夹。在那里，上传以下文件：一个 [猫](https://cdn.cs50.net/2024/fall/lectures/9/src9/froshims4/static/cat.jpg) 的文件。

+   执行 `flask run` 并与该应用程序互动。

+   现在你已经拥有了一个网络应用程序！然而，存在一些安全漏洞！因为所有内容都在客户端，攻击者可以更改 HTML 并**黑客**网站。此外，如果服务器关闭，这些数据将不会持久化。我们是否有办法让数据在服务器重启时也能持久化？

## Flask 和 SQL

+   正如我们所见，Python 可以与 SQL 数据库交互，我们可以结合 Flask、Python 和 SQL 的力量来创建一个数据将持久化的网络应用程序！

+   要实现这一点，你需要采取多个步骤。

+   首先，将以下 [SQL 数据库](https://cdn.cs50.net/2024/fall/lectures/9/src9/froshims4/froshims.db)下载到你的 `froshims` 文件夹中。

+   在终端中执行 `sqlite3 froshims.db` 并输入 `.schema` 以查看数据库文件的内容。进一步输入 `SELECT * FROM registrants;` 以了解内容。你会注意到文件中目前没有任何注册信息。

+   接下来，按如下方式修改 `requirements.txt`：

    ```
    cs50
    Flask 
    ```

+   按如下方式修改 `index.html`：

    ```
    {% extends "layout.html" %}

    {% block body %}
        <h1>Register</h1>
        <form action="/register" method="post">
            <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
            {% for sport in sports %}
                <input name="sport" type="checkbox" value="{{ sport }}"> {{ sport }}
            {% endfor %}
            <button type="submit">Register</button>
        </form>
    {% endblock %} 
    ```

+   按如下方式修改 `layout.html`：

    ```
    <!DOCTYPE html>

    <html lang="en">

        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>froshims</title>
        </head>

        <body>
            {% block body %}{% endblock %}
        </body>

    </html> 
    ```

+   确保 `error.html` 显示如下：

    ```
    {% extends "layout.html" %}

    {% block body %}
        <h1>Error</h1>
        <p>{{ message }}</p>
        <img alt="Grumpy Cat" src="/static/cat.jpg">
    {% endblock %} 
    ```

+   修改 `registrants.html` 以如下所示：

    ```
    {% extends "layout.html" %}

    {% block body %}
        <h1>Registrants</h1>
        <table>
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Sport</th>
                    <th></th>
                </tr>
            </thead>
            <tbody>
                {% for registrant in registrants %}
                    <tr>
                        <td>{{ registrant.name }}</td>
                        <td>{{ registrant.sport }}</td>
                        <td>
                            <form action="/deregister" method="post">
                                <input name="id" type="hidden" value="{{ registrant.id }}">
                                <button type="submit">Deregister</button>
                            </form>
                        </td>
                    </tr>
                {% endfor %}
            </tbody>
        </table>
    {% endblock %} 
    ```

    注意到包含了一个隐藏值 `registrant.id`，这样就可以在 `app.py` 中稍后使用这个 `id`。

+   最后，按如下方式修改 `app.py`：

    ```
    # Implements a registration form, storing registrants in a SQLite database, with support for deregistration 
    from cs50 import SQL
    from flask import Flask, redirect, render_template, request

    app = Flask(__name__)

    db = SQL("sqlite:///froshims.db")

    SPORTS = [
        "Basketball",
        "Soccer",
        "Ultimate Frisbee"
    ]

    @app.route("/")
    def index():
        return render_template("index.html", sports=SPORTS)

    @app.route("/deregister", methods=["POST"])
    def deregister():

        # Forget registrant
        id = request.form.get("id")
        if id:
            db.execute("DELETE FROM registrants WHERE id = ?", id)
        return redirect("/registrants")

    @app.route("/register", methods=["POST"])
    def register():

        # Validate name
        name = request.form.get("name")
        if not name:
            return render_template("error.html", message="Missing name")

        # Validate sports
        sports = request.form.getlist("sport")
        if not sports:
            return render_template("error.html", message="Missing sport")
        for sport in sports:
            if sport not in SPORTS:
                return render_template("error.html", message="Invalid sport")

        # Remember registrant
        for sport in sports:
            db.execute("INSERT INTO registrants (name, sport) VALUES(?, ?)", name, sport)

        # Confirm registration
        return redirect("/registrants")

    @app.route("/registrants")
    def registrants():
        registrants = db.execute("SELECT * FROM registrants")
        return render_template("registrants.html", registrants=registrants) 
    ```

    注意到使用了 `cs50` 库。包含了一个用于 `register` 的 `post` 方法的路由。这个路由将获取注册表单中的姓名和运动项目，并执行一个 SQL 查询将 `name` 和 `sport` 添加到 `registrants` 表中。`deregister` 路由将执行一个 SQL 查询，获取用户的 `id` 并利用这些信息注销该个人。

+   你可以执行 `flask run` 并检查结果。

+   如果你想下载我们的 `froshims` 实现，你可以[在这里](https://cdn.cs50.net/2024/fall/lectures/9/src9/froshims5/)下载。

+   你可以在[Flask 文档](https://flask.palletsprojects.com)中了解更多关于 Flask 的信息。

## Cookies 和 Session

+   `app.py` 被视为**控制器**。**视图**被认为是用户所看到的内容。**模型**是数据存储和操作的方式。三者合称为 *MVC*（模型，视图，控制器）。

+   虽然之前的 `froshims` 实现从管理角度来看很有用，其中后台管理员可以向数据库添加和删除个人，但可以想象这段代码在公共服务器上实现并不安全。

+   首先，不良分子可能会通过点击注销按钮代表其他用户做出决定——实际上是从服务器删除他们记录的答案。

+   像谷歌这样的网络服务使用登录凭证来确保用户只能访问正确的数据。

+   实际上，我们可以使用 *cookies* 来实现这一点。Cookies 是存储在您计算机上的小文件，这样您的计算机就可以与服务器通信，并有效地表示，“我是一个已经登录的授权用户。” 这种通过 cookie 的授权称为 *会话*。

+   Cookies 可以按照以下方式存储：

    ```
    GET / HTTP/2
    Host: accounts.google.com
    Cookie: session=value 
    ```

    在这里，一个 `session` id 被存储，并带有特定的 `value`，表示该会话。

+   以最简单的方式，我们可以通过创建一个名为 `login` 的文件夹，然后添加以下文件来实现这一点。

+   首先，创建一个名为 `requirements.txt` 的文件，其内容如下：

    ```
    Flask
    Flask-Session 
    ```

    注意，除了`Flask`，我们还包含了`Flask-Session`，这是支持登录会话所必需的。

+   第二，在 `templates` 文件夹中创建一个名为 `layout.html` 的文件，其内容如下：

    ```
    <!DOCTYPE html>

    <html lang="en">

        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>login</title>
        </head>

        <body>
            {% block body %}{% endblock %}
        </body>

    </html> 
    ```

    注意这提供了一个非常简单的布局，包括标题和正文。

+   第三，在`templates`文件夹中创建一个名为`index.html`的文件，其内容如下：

    ```
    {% extends "layout.html" %}

    {% block body %}

        {% if name -%}
            You are logged in as {{ name }}. <a href="/logout">Log out</a>.
        {%- else -%}
            You are not logged in. <a href="/login">Log in</a>.
        {%- endif %}

    {% endblock %} 
    ```

    注意这个文件会检查 `session["name"]` 是否存在（在下面的 `app.py` 中进一步阐述）。如果存在，它将显示欢迎信息。如果不存在，它将建议您浏览到登录页面。

+   第四，创建一个名为 `login.html` 的文件，并添加以下代码：

    ```
    {% extends "layout.html" %}

    {% block body %}

        <form action="/login" method="post">
            <input autocomplete="off" autofocus name="name" placeholder="Name" type="text">
            <button type="submit">Log In</button>
        </form>

    {% endblock %} 
    ```

    注意这是基本登录页面的布局。

+   最后，创建一个名为 `app.py` 的文件，并编写以下代码：

    ```
    from flask import Flask, redirect, render_template, request, session
    from flask_session import Session

    # Configure app app = Flask(__name__)

    # Configure session app.config["SESSION_PERMANENT"] = False
    app.config["SESSION_TYPE"] = "filesystem"
    Session(app)

    @app.route("/")
    def index():
        return render_template("index.html", name=session.get("name"))

    @app.route("/login", methods=["GET", "POST"])
    def login():
        if request.method == "POST":
            session["name"] = request.form.get("name")
            return redirect("/")
        return render_template("login.html")

    @app.route("/logout")
    def logout():
        session.clear()
        return redirect("/") 
    ```

    注意文件顶部的修改后的 *导入*，包括 `session`，这将允许您支持会话。最重要的是，注意 `session["name"]` 在 `login` 和 `logout` 路由中的使用。`login` 路由会将提供的登录名分配给 `session["name"]`。然而，在 `logout` 路由中，注销是通过清除 `session` 的值来实现的。

+   `session` 抽象允许您确保只有特定用户可以访问我们应用程序中的特定数据和功能。它允许您确保没有人代表另一个用户行事，无论是好是坏！

+   如果您愿意，您可以下载[我们的实现](https://cdn.cs50.net/2024/fall/lectures/9/src9/login/)。

+   你可以在[Flask 文档](https://flask.palletsprojects.com/en/stable/api/#flask.session)中了解更多关于会话的信息。

## 购物车

+   接下来，我们将通过一个最终示例来展示如何利用 Flask 的会话启用功能。

+   我们检查了 `app.py` 中的 `store` 代码。以下代码被展示：

    ```
    from cs50 import SQL
    from flask import Flask, redirect, render_template, request, session
    from flask_session import Session

    # Configure app app = Flask(__name__)

    # Connect to database db = SQL("sqlite:///store.db")

    # Configure session app.config["SESSION_PERMANENT"] = False
    app.config["SESSION_TYPE"] = "filesystem"
    Session(app)

    @app.route("/")
    def index():
        books = db.execute("SELECT * FROM books")
        return render_template("books.html", books=books)

    @app.route("/cart", methods=["GET", "POST"])
    def cart():

        # Ensure cart exists
        if "cart" not in session:
            session["cart"] = []

        # POST
        if request.method == "POST":
            book_id = request.form.get("id")
            if book_id:
                session["cart"].append(book_id)
            return redirect("/cart")

        # GET
        books = db.execute("SELECT * FROM books WHERE id IN (?)", session["cart"])
        return render_template("cart.html", books=books) 
    ```

    注意到`cart`是通过列表实现的。可以使用`books.html`中的`Add to Cart`按钮向此列表添加项目。点击此类按钮时，将调用`post`方法，其中将项目`id`附加到`cart`上。在查看购物车时，调用`get`方法，执行 SQL 以显示购物车中的书籍列表。

+   我们还看到了`books.html`的内容：

    ```
    {% extends "layout.html" %}

    {% block body %}

        <h1>Books</h1>
        {% for book in books %}
            <h2>{{ book["title"] }}</h2>
            <form action="/cart" method="post">
                <input name="id" type="hidden" value="{{ book['id'] }}">
                <button type="submit">Add to Cart</button>
            </form>
        {% endfor %}

    {% endblock %} 
    ```

    注意到这是如何通过`for book in books`为每本书创建`Add to Cart`功能的。

+   你可以在[源代码](https://cdn.cs50.net/2024/fall/lectures/9/src9/store/)中查看驱动此`flask`实现的其余文件。

## 显示

+   我们在`app.py`中查看了一个名为`shows`的预设计程序：

    ```
    # Searches for shows using LIKE 
    from cs50 import SQL
    from flask import Flask, render_template, request

    app = Flask(__name__)

    db = SQL("sqlite:///shows.db")

    @app.route("/")
    def index():
        return render_template("index.html")

    @app.route("/search")
    def search():
        shows = db.execute("SELECT * FROM shows WHERE title LIKE ?", "%" + request.args.get("q") + "%")
        return render_template("search.html", shows=shows) 
    ```

    注意到`search`路由允许通过一种方式来搜索`show`。此搜索查找与用户提供的标题`LIKE`匹配的标题。

+   我们还检查了`index.html`：

    ```
    <!DOCTYPE html>

    <html lang="en">

        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>shows</title>
        </head>

        <body>

            <input autocomplete="off" autofocus placeholder="Query" type="text">

            <ul></ul>

            <script>
                let input = document.querySelector('input');
                input.addEventListener('input', async function() {
                    let response = await fetch('/search?q=' + input.value);
                    let shows = await response.json();
                    let html = '';
                    for (let id in shows) {
                        let title = shows[id].title.replace('<', '&lt;').replace('&', '&amp;');
                        html += '<li>' + title + '</li>';
                    }
                    document.querySelector('ul').innerHTML = html;
                });
            </script>

        </body>

    </html> 
    ```

    注意到 JavaScript `script`创建了一个自动完成的实现，其中匹配`input`的标题会被显示出来。

+   你可以在[源代码](https://cdn.cs50.net/2024/fall/lectures/9/src9/shows3/)中查看此实现的其他文件。

## API

+   *应用程序程序接口*或*API*是一系列规范，允许你与另一个服务进行交互。例如，我们可以利用 IMDB 的 API 来与其数据库进行交互。我们甚至可以集成用于处理从服务器下载的特定类型数据的 API。

+   在对`shows`进行改进的同时，查看`app.py`的改进，我们看到了以下内容：

    ```
    # Searches for shows using Ajax 
    from cs50 import SQL
    from flask import Flask, render_template, request

    app = Flask(__name__)

    db = SQL("sqlite:///shows.db")

    @app.route("/")
    def index():
        return render_template("index.html")

    @app.route("/search")
    def search():
        q = request.args.get("q")
        if q:
            shows = db.execute("SELECT * FROM shows WHERE title LIKE ? LIMIT 50", "%" + q + "%")
        else:
            shows = []
        return render_template("search.html", shows=shows) 
    ```

    注意到`search`路由执行了一个 SQL 查询。

+   查看`search.html`，你会注意到它非常简单：

    ```
    {% for show in shows %}
        <li>{{ show["title"] }}</li>
    {% endfor %} 
    ```

    注意到它提供了一个项目符号列表。

+   最后，查看`index.html`，注意到*AJAX*代码被用来驱动搜索：

    ```
    <!DOCTYPE html>

    <html lang="en">

        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>shows</title>
        </head>

        <body>

            <input autocomplete="off" autofocus placeholder="Query" type="search">

            <ul></ul>

            <script>
                let input = document.querySelector('input');
                input.addEventListener('input', async function() {
                    let response = await fetch('/search?q=' + input.value);
                    let shows = await response.text();
                    document.querySelector('ul').innerHTML = shows;
                });
            </script>

        </body>

    </html> 
    ```

    注意到使用事件监听器动态查询服务器以提供与提供的标题匹配的列表。这将定位 HTML 中的`ul`标签并相应地修改网页以包含匹配的列表。

+   你可以在[AJAX 文档](https://api.jquery.com/category/ajax/)中了解更多信息。

## JSON

+   *JavaScript 对象表示法*或*JSON*是一个包含键和值的字典文本文件。这是一种原始且对计算机友好的方式来获取大量数据。

+   JSON 是从服务器获取数据的一种非常有用的方式。

+   你可以在我们共同检查的`index.html`中看到这一操作：

    ```
    <!DOCTYPE html>

    <html lang="en">

        <head>
            <meta name="viewport" content="initial-scale=1, width=device-width">
            <title>shows</title>
        </head>

        <body>

            <input autocomplete="off" autofocus placeholder="Query" type="text">

            <ul></ul>

            <script>
                let input = document.querySelector('input');
                input.addEventListener('input', async function() {
                    let response = await fetch('/search?q=' + input.value);
                    let shows = await response.json();
                    let html = '';
                    for (let id in shows) {
                        let title = shows[id].title.replace('<', '&lt;').replace('&', '&amp;');
                        html += '<li>' + title + '</li>';
                    }
                    document.querySelector('ul').innerHTML = html;
                });
            </script>

        </body>

    </html> 
    ```

    虽然上述内容可能有些晦涩，但它为你提供了一个起点，让你可以自己研究 JSON，看看它如何在你的网络应用程序中实现。

+   此外，我们还检查了`app.py`以了解如何获取 JSON 响应：

    ```
    # Searches for shows using Ajax with JSON 
    from cs50 import SQL
    from flask import Flask, jsonify, render_template, request

    app = Flask(__name__)

    db = SQL("sqlite:///shows.db")

    @app.route("/")
    def index():
        return render_template("index.html")

    @app.route("/search")
    def search():
        q = request.args.get("q")
        if q:
            shows = db.execute("SELECT * FROM shows WHERE title LIKE ? LIMIT 50", "%" + q + "%")
        else:
            shows = []
        return jsonify(shows) 
    ```

    注意到`jsonify`是如何被用来将结果转换为当代网络应用可接受的易读格式的。

+   你可以在[JSON 文档](https://www.json.org/json-en.html)中了解更多信息。

+   总结来说，你现在可以使用 Python、Flask、HTML 和 SQL 来完成自己的网络应用程序。

## 总结

在本节课中，你学习了如何利用 Python、SQL 和 Flask 来创建 Web 应用程序。具体来说，我们讨论了……

+   Flask

+   表单

+   模板

+   请求方法

+   Flask 和 SQL

+   Cookie 和会话

+   API

+   JSON

下次再见，我们将在这里举行本学期的最后一堂课，地点是[Sanders Theatre](https://websites.harvard.edu/memhall/home-2/buildings/sanders-theatre/)！
