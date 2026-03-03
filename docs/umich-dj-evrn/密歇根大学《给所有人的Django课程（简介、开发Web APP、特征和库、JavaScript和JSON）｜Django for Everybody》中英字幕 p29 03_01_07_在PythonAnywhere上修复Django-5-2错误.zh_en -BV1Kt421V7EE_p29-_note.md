# Django for Everybody：P29：在PythonAnywhere上修复Django应用错误

![](img/6736b609a9e0297d38f4ed9a9030adb7_0.png)

![](img/6736b609a9e0297d38f4ed9a9030adb7_1.png)

在本节课中，我们将学习如何在PythonAnywhere平台上诊断和修复Django应用中的两种常见错误：启动失败和运行时错误。我们将通过具体的步骤和示例，帮助你理解如何定位问题并快速解决。

## 概述

当你在PythonAnywhere上运行Django应用时，可能会遇到两种基本错误。第一种是**启动失败**，即应用无法启动，你会在访问应用时看到“出了点问题”的提示。第二种是**运行时错误**，即应用可以启动，但在处理请求时出现问题，你会看到一个带有错误追踪信息的黄色页面。本节将指导你如何系统地排查和修复这些问题。

## 启动失败：应用无法启动

上一节我们介绍了两种错误类型。本节中我们来看看第一种：启动失败。当你修改代码后点击“重新加载”按钮，然后访问应用时看到“出了点问题”的提示，这通常意味着应用启动失败。PythonAnywhere无法启动你的应用，因为它存在致命错误。

### 理解启动过程

当你在PythonAnywhere上点击“重新加载”按钮时，会发生一系列操作。系统会进入你的源代码目录，设置虚拟环境，并运行一个配置文件（类似于在本地运行 `python manage.py runserver` 命令）。这个过程会加载你的 `settings.py`、`urls.py` 以及 `settings.py` 中列出的所有应用。如果在加载这些文件的任何阶段出现错误，应用就会启动失败。

### 诊断步骤：使用 `python manage.py check`

要诊断启动失败，最有效的方法是使用Django的检查命令。以下是具体步骤：

1.  在PythonAnywhere控制面板中，进入“Consoles”标签页。
2.  创建一个新的“Bash Console”。
3.  在Bash控制台中，首先确认你处于正确的虚拟环境中。你可以通过运行 `python --version` 来检查。
4.  使用 `pwd` 命令确认当前目录，然后切换到你的Django项目目录。通常命令是：
    ```bash
    cd ~/django_projects/mysite
    ```
5.  运行Django的检查命令：
    ```bash
    python manage.py check
    ```

这个命令会模拟应用启动过程，加载所有设置、URL配置和应用。如果存在导致启动失败的语法错误或导入错误，它会在这里显示出来。

### 示例：修复导入错误

![](img/6736b609a9e0297d38f4ed9a9030adb7_3.png)

假设 `python manage.py check` 命令输出了一个错误追踪信息，指出在 `polls/views.py` 的第1行有一个 `ModuleNotFoundError: No module named 'jango'` 错误。

1.  根据错误信息，定位到有问题的文件：`polls/views.py`。
2.  打开该文件，发现第1行代码是：
    ```python
    from jango.http import HttpResponse
    ```
    这里 `jango` 拼写错误，应该是 `django`。
3.  将其修正为：
    ```python
    from django.http import HttpResponse
    ```
4.  保存文件。
5.  再次在Bash控制台中运行 `python manage.py check`。如果命令成功执行且没有输出错误，说明问题已解决。
6.  最后，返回PythonAnywhere的“Web”标签页，点击“Reload”按钮重新加载你的Web应用。
7.  刷新你的应用页面，它现在应该可以正常访问了。

![](img/6736b609a9e0297d38f4ed9a9030adb7_5.png)

![](img/6736b609a9e0297d38f4ed9a9030adb7_6.png)

**关键提示**：在修复后先运行 `check` 命令进行验证，是一个好习惯。这比直接重新加载应用更快，并且能确保没有遗留其他错误。

![](img/6736b609a9e0297d38f4ed9a9030adb7_8.png)

![](img/6736b609a9e0297d38f4ed9a9030adb7_9.png)

![](img/6736b609a9e0297d38f4ed9a9030adb7_11.png)

### 备用方案：查看错误日志

![](img/6736b609a9e0297d38f4ed9a9030adb7_13.png)

如果 `python manage.py check` 没有发现问题，但应用仍然无法启动，你可以查看PythonAnywhere的错误日志。

![](img/6736b609a9e0297d38f4ed9a9030adb7_15.png)

1.  在“Web”应用配置页面，找到“Error log”的链接并点击。
2.  日志文件会按时间顺序记录所有错误。你需要滚动到**底部**查看最近的错误。
3.  日志中的错误信息通常与 `python manage.py check` 的输出类似，但可能更冗长。仔细阅读，定位根本原因。

## 运行时错误：黄色追踪页面

上一节我们解决了应用无法启动的问题。本节中我们来看看第二种情况：运行时错误。当应用成功启动，但在处理某个特定请求时发生错误，你就会看到一个黄色的调试页面，其中包含了详细的错误追踪信息。

### 理解黄色追踪页面

这个页面意味着你的应用已经通过了所有启动检查，`settings.py`、`urls.py` 等文件都已成功加载。错误发生在执行你的业务逻辑代码时（例如，在 `views.py` 中处理一个视图函数）。

黄色页面的顶部通常会有一个简短的错误摘要，下方则是详细的“Traceback”（追踪信息），它展示了错误发生时的完整函数调用栈。

### 诊断与修复步骤

以下是修复运行时错误的通用步骤：

1.  **阅读错误摘要**：首先看黄色页面顶部的错误描述，它通常直接指出了问题所在，例如 `NameError: name ‘HttpsResponse’ is not defined`。
2.  **查看追踪信息**：向下滚动，在追踪信息中寻找属于你自己项目的文件（如 `polls/views.py`）。错误最后指向的那几行，通常就是问题的根源。
3.  **定位并编辑代码**：根据错误信息指出的文件和行号（例如 `polls/views.py, line 6`），打开对应的文件进行修改。
4.  **利用编辑器提示**：PythonAnywhere的在线编辑器会用黄色三角形标记出它检测到的代码问题（如未定义的变量、未使用的导入）。这是一个很好的辅助调试工具。
5.  **保存并重新加载**：修复代码后保存文件。然后，返回“Web”标签页点击“Reload”按钮，或者直接刷新你的应用页面来测试是否修复成功。

### 示例：修复未定义变量错误

假设你在访问投票详情页时看到了黄色页面，错误信息显示 `NameError at /polls/1/`，并指出在 `polls/views.py` 的第6行，变量 `HttpsResponse` 未定义。

1.  打开 `polls/views.py` 文件。
2.  找到第6行，发现代码是：
    ```python
    return HttpsResponse(“Hello, world.”)
    ```
    这里 `HttpsResponse` 拼写错误，应该是 `HttpResponse`（注意大小写）。
3.  同时，编辑器可能在代码旁显示黄色三角形，提示“Undefined variable ‘HttpsResponse’”。
4.  将其修正为：
    ```python
    return HttpResponse(“Hello, world.”)
    ```
5.  保存文件后，编辑器中的黄色警告会消失。
6.  刷新你的应用页面，错误应该已经解决，页面可以正常显示。

## 总结

本节课中我们一起学习了在PythonAnywhere上调试Django应用的两种核心方法。

*   对于**启动失败**（“出了点问题”），核心工具是使用Bash控制台运行 `python manage.py check` 命令。它能快速定位导致应用无法加载的语法或导入错误。
*   对于**运行时错误**（黄色追踪页面），关键在于仔细阅读错误信息，在追踪栈中找到自己项目文件的错误行，并进行修正。编辑器的实时语法检查也能提供很大帮助。

![](img/6736b609a9e0297d38f4ed9a9030adb7_17.png)

![](img/6736b609a9e0297d38f4ed9a9030adb7_18.png)

![](img/6736b609a9e0297d38f4ed9a9030adb7_19.png)

![](img/6736b609a9e0297d38f4ed9a9030adb7_20.png)

记住调试的通用流程：重现错误 -> 阅读错误信息 -> 定位问题代码 -> 修复 -> 验证。通过不断练习，你会越来越熟练地处理这些开发中常见的问题。