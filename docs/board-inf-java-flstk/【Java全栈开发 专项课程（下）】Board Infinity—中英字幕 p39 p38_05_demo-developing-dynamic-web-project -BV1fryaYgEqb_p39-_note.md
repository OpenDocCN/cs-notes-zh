# Java全栈开发：专项课程（下）：39：创建动态Web项目教程 🚀

![](img/1ce94dbc3866a60a8e77bc43db24bf6f_0.png)

在本节课中，我们将学习如何在Eclipse集成开发环境中创建一个动态Web项目。我们将从环境准备开始，逐步完成项目创建、服务器配置，并最终运行一个简单的网页。

---

## 概述

![](img/1ce94dbc3866a60a8e77bc43db24bf6f_2.png)

创建动态Web项目是Java Web开发的第一步。这个过程涉及在Eclipse中设置项目结构，并将其部署到Apache Tomcat应用服务器上运行。本节教程将引导你完成所有必要步骤。

## 环境准备

在开始之前，请确保你的计算机上已安装以下软件：
*   **JDK** (Java开发工具包)
*   **Eclipse IDE** (用于Java EE开发者的版本更佳)
*   **Apache Tomcat** (应用服务器)

上一节我们介绍了课程背景，本节中我们来看看具体的创建步骤。Apache Tomcat是运行Java Web应用常用的服务器，几乎所有的Java Web应用都会部署到类似的应用服务器上。

## 创建动态Web项目

以下是创建新动态Web项目的步骤。

1.  打开Eclipse，点击菜单栏的 **File** (文件)。
2.  选择 **New** (新建) -> **Other...** (其他...)。在弹出的窗口中，展开 **Web** 文件夹。
3.  选择 **Dynamic Web Project** (动态Web项目)，然后点击 **Next** (下一步)。

![](img/1ce94dbc3866a60a8e77bc43db24bf6f_0.png)

## 配置项目参数

在项目配置页面，你需要设置几个关键参数。

1.  在 **Project name** (项目名称) 字段中，为你的项目命名，例如 `DynamicWebProjectDemo`。
2.  **Target runtime** (目标运行时) 需要指定为Apache Tomcat。如果下拉列表中没有可选项，请点击 **New Runtime...** (新建运行时...)。
3.  在弹出的窗口中选择你安装的Tomcat版本（例如 Apache Tomcat v9.0），点击 **Next**。
4.  点击 **Browse...** (浏览...)，找到并选择你电脑上Tomcat的安装目录（例如 `C:\Program Files\Apache Software Foundation\Tomcat 9.0`），然后点击 **Finish** (完成)。

## 完成项目创建

设置好运行时后，返回项目创建向导。

1.  **Dynamic web module version** (动态Web模块版本) 可以选择最新的（如4.0），这对创建JSP页面没有影响。
2.  连续点击 **Next** (下一步)，直到看到 **Finish** (完成) 按钮，然后点击它。
3.  项目创建成功后，你可以在Eclipse的 **Project Explorer** (项目资源管理器) 视图中看到它。

## 创建Web页面

项目创建完成后，需要添加一个网页文件。

1.  在项目结构中，导航到 `src/main/webapp` 目录。这是存放Web应用文件（如HTML、JSP）的标准位置。
2.  右键点击 `webapp` 文件夹，选择 **New** -> **HTML File** (HTML文件)。
3.  将文件命名为 `index.html`。
4.  在打开的编辑器中，编写简单的HTML代码，例如：
    ```html
    <!DOCTYPE html>
    <html>
    <head><title>My Page</title></head>
    <body>
        <h1>Hello World!</h1>
    </body>
    </html>
    ```
5.  保存文件 (`Ctrl + S`)。

## 配置并启动服务器

要让项目运行起来，需要在Eclipse中配置Tomcat服务器。

1.  转到 **Window** (窗口) -> **Show View** (显示视图) -> **Servers** (服务器)。如果“Servers”视图未显示，可以通过 **Other...** 在搜索框中找到它。
2.  在“Servers”视图底部，点击 **“No servers are available. Click this link to create a new server...”** (没有可用服务器。点击此链接创建新服务器...)。
3.  选择你之前配置的Apache Tomcat版本，点击 **Next**。
4.  在下一个界面，将左侧你刚创建的项目移动到右侧的“Configured” (已配置) 列表中，点击 **Finish**。

## 运行与测试项目

服务器配置好后，就可以运行项目了。

1.  在“Servers”视图中，右键点击你刚添加的Tomcat服务器，选择 **Start** (启动)。控制台会显示服务器启动日志。
2.  服务器启动后，右键点击你的项目（例如 `DynamicWebProjectDemo`），选择 **Run As** (运行方式) -> **Run on Server** (在服务器上运行)。
3.  选择已启动的服务器，点击 **Finish**。Eclipse内置的浏览器会打开并显示你的 `index.html` 页面，你应该能看到“Hello World!”字样。

![](img/1ce94dbc3866a60a8e77bc43db24bf6f_4.png)

## （可选）配置外部浏览器

默认情况下，Eclipse使用内置浏览器。你可以将其改为系统默认的外部浏览器（如Chrome）。

1.  点击 **Window** (窗口) -> **Preferences** (首选项)。
2.  在左侧导航栏中，展开 **General** (常规) -> **Web Browser** (Web浏览器)。
3.  在右侧选择 **Use external web browser** (使用外部Web浏览器)，并从列表中选择你喜欢的浏览器（如Chrome）。
4.  点击 **Apply and Close** (应用并关闭)。
5.  下次运行项目时，页面将在你选择的外部浏览器中打开。

如果更改后未生效，可以尝试重启Eclipse，或者直接从浏览器访问服务器地址（通常是 `http://localhost:8080/你的项目名/`）。

## 总结

![](img/1ce94dbc3866a60a8e77bc43db24bf6f_4.png)

本节课中我们一起学习了在Eclipse中创建和运行动态Web项目的完整流程。关键步骤包括：创建项目、配置Tomcat运行时、添加Web内容、配置服务器以及运行测试。你现在已经拥有了一个基础的Java Web开发环境，可以在此基础上进一步学习Servlet、JSP等更高级的Web技术。

![](img/1ce94dbc3866a60a8e77bc43db24bf6f_6.png)

请继续关注后续课程，以了解更多关于Web应用开发环境的知识。下次见！

![](img/1ce94dbc3866a60a8e77bc43db24bf6f_6.png)

![](img/1ce94dbc3866a60a8e77bc43db24bf6f_7.png)

![](img/1ce94dbc3866a60a8e77bc43db24bf6f_9.png)

![](img/1ce94dbc3866a60a8e77bc43db24bf6f_9.png)