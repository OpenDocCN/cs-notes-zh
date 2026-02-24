# 12：创建视图并映射到URL 🚀

在本节课中，我们将要学习Django中URL配置的核心概念，了解如何将特定的URL地址映射到对应的视图函数，从而在用户访问网站时返回正确的网页内容。我们将从创建视图函数开始，逐步配置项目级和应用级的URL，最终实现一个简单的网页响应。

---

大多数网站都是Web应用程序。当你在浏览器中输入一个URL地址，或者从搜索引擎点击一个网站链接时，通常会返回一个主页。这个主页是在仅发送了包含域名的URL请求时返回的。

之前的学习中，你已经了解到，为了接受HTTP请求并返回HTTP响应，你需要在`views.py`文件中创建一个视图函数。这个视图函数随后会被映射到一个URL上。当向该URL发起请求时，视图函数就会被调用。

在本视频中，你将学习Django中的URL配置，以及如何用它来将URL映射到视图。你将探索`urls.py`这个URL配置文件，并了解为什么它在项目级别和应用级别都存在。最后，你将学习如何使用`include()`函数来引用应用级别的`urls.py`文件，从而为你创建的应用设计URL。

在Django中，视图函数所使用的URL配置是在`urls.py`文件中创建和更新的。Django默认会在项目级别创建一个`urls.py`文件。但此外，最佳实践是在每个应用级别也创建一个`urls.py`文件。这样，一个应用的所有相关URL可以集中管理。然而，项目也需要知道每个应用内部使用了哪些URL。

例如，在Django中，当用户请求一个URL时，这个请求首先由项目级别的`urls.py`文件处理。Django会寻找名为`urlpatterns`的变量。但是，包含URL映射逻辑的代码位于应用级别。因此，你需要一种方法来告诉Django也去检查应用级别的`urls.py`文件。你可以通过使用`include()`函数来实现这一点。

在项目级别的`urls.py`文件中，你在`urlpatterns`列表内创建一个新的`path()`。然后，在`path()`函数内部，你将应用级别`urls.py`文件的引用作为`view`参数传入。这使得项目级别能够访问应用级别的URL。通过使用`include()`函数，项目级别的`urls.py`可以继承应用级别的URL配置。稍后，当你处理包含字符串形式URL的路由时，你将更详细地探索这种继承的概念。

---

现在，让我们打开VS Code，开始编写URL配置的代码。

首先，创建一个项目，并在项目内创建一个名为`myapp`的应用。为了确保Django应用正在运行，请在终端运行命令`python3 manage.py runserver`来启动开发服务器。现在，选择URL将Django部署到你的本地主机。

请注意，网页会显示一个“安装成功”的消息。让我们先关闭这个网页并停止服务器。

![](img/3aedd0dffb17ca146754e5692fb34ca5_1.png)

第一步是打开`views.py`文件来创建一个视图。使用导入语句，输入`from django.http import HttpResponse`。接下来，创建一个名为`home`的函数，并将`request`对象作为参数传入。然后，返回一个包含字符串的`HttpResponse`。

让我们以小柠檬餐厅的主页为例。字符串中的消息是：“Welcome to the Little Lemon restaurant.” 我们的目标是当用户打开本地主机的URL时显示这条消息。

以下是创建视图的步骤：
1.  从`django.http`模块导入`HttpResponse`类。
2.  定义一个名为`home`的视图函数，它接受一个`request`参数。
3.  在函数体内，使用`return`语句返回一个`HttpResponse`对象，其内容为欢迎字符串。

![](img/3aedd0dffb17ca146754e5692fb34ca5_3.png)

代码示例如下：
```python
from django.http import HttpResponse

![](img/3aedd0dffb17ca146754e5692fb34ca5_5.png)

def home(request):
    return HttpResponse("Welcome to the Little Lemon restaurant.")
```

---

让我们探索显示这条消息的后续步骤。

第一步是在`myapp`应用内创建一个名为`urls.py`的文件。请记住，这是应用级别的`urls.py`文件，项目级别也存在一个同名的文件。

在`urls.py`文件中，你需要从`django.urls`导入`path`函数。这允许你在`urlpatterns`列表中使用`path`函数。正是在`path`函数内部，你将URL映射到其相关的视图函数。

下一步是创建一个名为`urlpatterns`的序列。在方括号内，你添加`path`函数，并在括号内传入一个空字符串，后跟视图函数的位置和名称。因为`urls.py`文件和`views.py`文件位于同一个文件夹，你只需要提供视图函数所在文件的名称（不带`.py`扩展名），然后是一个点号和视图函数的名称。

请注意，VS Code在代码中高亮了`views`这个词。这意味着为了使用`views.py`文件，必须导入它。因此，输入`from . import views`并保存文件。重要的是要记住在这个`path`函数末尾添加一个逗号，以匹配Django执行的解析。

现在，再次保存文件。好的，代码几乎完成了。最后一步是在项目级别设置URL配置。这是因为项目文件不知道视图函数在哪里。

以下是配置应用级URL的步骤：
1.  在应用目录下创建`urls.py`文件。
2.  从`django.urls`导入`path`。
3.  从当前目录导入`views`模块。
4.  定义`urlpatterns`列表，使用`path()`函数将空路径`''`映射到`views.home`视图。

代码示例如下：
```python
from django.urls import path
from . import views

urlpatterns = [
    path('', views.home),
]
```

---

为了设置此配置，请打开项目的`urls.py`文件。在`path`关键字旁边，输入逗号，然后输入`include`以导入`include`函数。接下来，在`urlpatterns`列表内，添加另一个`path`函数。在括号内传入一个空字符串作为第一个参数。对于第二个参数，使用`include()`函数来传入应用的`urls.py`文件位置。再次记住，不要添加`.py`扩展名。

保存文件并在浏览器中打开本地主机的URL。

成功！消息“Welcome to the Little Lemon restaurant.” 显示出来了。

![](img/3aedd0dffb17ca146754e5692fb34ca5_7.png)

![](img/3aedd0dffb17ca146754e5692fb34ca5_9.png)

---

在本节课中，我们一起学习了Django中的URL配置，以及如何用它来将项目级别的URL映射到应用级别的视图。你掌握了创建视图函数、配置应用级和项目级`urls.py`文件，并使用`include()`函数连接它们的关键步骤。通过实践，你成功地在浏览器中显示了自定义的欢迎页面，这是构建Django Web应用的重要基础。