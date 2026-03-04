# 面向所有人的Web应用程序：P20：在Windows 10上安装XAMPP 🖥️

![](img/46253f65124e78ae1606a0eb3c4a9214_0.png)

![](img/46253f65124e78ae1606a0eb3c4a9214_2.png)

![](img/46253f65124e78ae1606a0eb3c4a9214_4.png)

在本节课中，我们将学习如何在Windows 10操作系统上安装XAMPP。XAMPP是一个集成了Apache、MySQL、PHP和Perl的免费开源软件包，它是搭建本地Web开发环境的理想工具。我们将从下载开始，逐步完成安装、配置，并运行一个简单的PHP程序来验证安装是否成功。

![](img/46253f65124e78ae1606a0eb3c4a9214_5.png)

![](img/46253f65124e78ae1606a0eb3c4a9214_7.png)

## 下载XAMPP

首先，我们需要从Apache Friends官方网站下载XAMPP的Windows版本。

以下是下载步骤：
1.  访问Apache Friends网站。
2.  找到适用于Windows的XAMPP版本。
3.  点击下载链接，开始下载安装程序。

## 安装XAMPP

下载完成后，我们就可以运行安装程序了。安装程序通常位于系统的“下载”文件夹中。

以下是安装过程中的关键步骤：
1.  运行下载好的安装程序。
2.  在安装向导中，建议**使用默认的安装路径**（通常是 `C:\xampp`）。这可以避免一些潜在的权限问题。
3.  在组件选择界面，对于本课程，我们主要需要Apache（Web服务器）和MySQL（数据库）。可以取消勾选不需要的组件，如Tomcat、Perl和Fake Sendmail。
4.  完成上述设置后，继续安装过程。安装可能需要一些时间。

## 启动XAMPP控制面板

安装完成后，我们不会立即启动控制面板。我们先找到它的位置，以便日后可以方便地启动它。

以下是启动步骤：
1.  打开文件资源管理器，进入XAMPP的安装目录（例如 `C:\xampp`）。
2.  在该目录下，找到名为 `xampp-control.exe` 的文件，这就是控制面板程序。
3.  运行该程序。首次启动时，可能会提示选择语言，并可能出现系统安全对话框，请选择“允许”或“是”。
4.  为了方便，建议右键点击任务栏上的控制面板图标，选择“固定到任务栏”。

## 启动Apache和MySQL服务

在XAMPP控制面板中，我们需要启动两个核心服务。

以下是启动服务的步骤：
1.  在控制面板中，找到Apache模块，点击其右侧的“Start”按钮。启动成功后，其名称旁会显示绿色的“Running”标识，背景变为绿色。
2.  同样地，找到MySQL模块，点击“Start”按钮启动它。
3.  确保两个服务都成功运行，没有出现红色的错误提示。

## 验证安装与配置PHP

![](img/46253f65124e78ae1606a0eb3c4a9214_9.png)

![](img/46253f65124e78ae1606a0eb3c4a9214_11.png)

服务启动后，我们可以通过浏览器访问本地服务器来验证安装。

![](img/46253f65124e78ae1606a0eb3c4a9214_13.png)

以下是验证步骤：
1.  打开浏览器，在地址栏输入 `http://localhost` 或 `http://localhost/dashboard/`。如果看到XAMPP的欢迎面板，说明Apache服务器运行正常。
2.  在欢迎面板上，可以点击“PHPInfo”链接查看详细的PHP配置信息。
3.  在PHP配置中，有一个对开发非常重要的设置叫 `display_errors`。**开发时，此选项应设置为 `On`**，以便在页面上显示错误信息，方便调试；**上线（生产环境）时，则应设置为 `Off`**，以隐藏敏感信息。
4.  在XAMPP中，默认通常已设置为 `On`。如需修改，可以点击控制面板中Apache模块所在行的“Config”按钮，选择“PHP (php.ini)”。在打开的配置文件中，使用 `Ctrl+F` 搜索 `display_errors`，将其值修改为 `On`，保存文件后，**必须重启Apache服务**（先Stop，再Start）才能使更改生效。
5.  返回浏览器，刷新PHPInfo页面，再次搜索 `display_errors`，确认其状态已更新。

![](img/46253f65124e78ae1606a0eb3c4a9214_15.png)

## 创建并运行第一个PHP程序

![](img/46253f65124e78ae1606a0eb3c4a9214_17.png)

现在，我们来创建一个简单的PHP文件，测试整个开发环境是否工作正常。

![](img/46253f65124e78ae1606a0eb3c4a9214_19.png)

以下是创建和测试步骤：
1.  打开你喜欢的文本编辑器（如VS Code、Sublime Text或Notepad++）。课程演示中使用了Atom。
2.  新建一个文件，输入以下混合了HTML和PHP的代码：
    ```php
    <!DOCTYPE html>
    <html>
    <head>
        <title>My First PHP</title>
    </head>
    <body>
        <h1>Hello World from HTML</h1>
        <?php
            echo "<p>Hello World from PHP</p>";
            $x = 5;
            $y = 6;
            $z = $x + $y;
            echo "<p>The sum of $x and $y is: $z</p>";
        ?>
    </body>
    </html>
    ```
3.  保存文件。**关键的一步是：必须将文件保存在XAMPP的 `htdocs` 目录下**，该目录是Apache服务器的默认根目录。路径通常是 `C:\xampp\htdocs\`。
4.  为了管理不同的项目，建议在 `htdocs` 下为每个项目创建一个单独的文件夹。例如，创建一个名为 `first` 的文件夹。
5.  将刚才创建的文件以 `index.php` 为名，保存到 `C:\xampp\htdocs\first\` 目录下。
6.  打开浏览器，访问 `http://localhost/first/index.php`。如果页面正确显示“Hello World from HTML”和PHP计算出的结果“The sum of 5 and 6 is: 11”，则说明你的本地PHP开发环境已完全配置成功。

![](img/46253f65124e78ae1606a0eb3c4a9214_21.png)

---

![](img/46253f65124e78ae1606a0eb3c4a9214_23.png)

本节课中我们一起学习了在Windows 10上搭建PHP本地开发环境的完整流程。我们从下载并安装XAMPP开始，学习了如何启动Apache和MySQL服务，验证了安装并检查了关键的PHP配置（`display_errors`）。最后，我们通过创建并运行一个包含HTML和PHP代码的文件，成功测试了整个环境。现在，你已经拥有了一个功能完备的本地服务器，可以开始进行数据库构建和PHP代码编写等Web开发工作了。