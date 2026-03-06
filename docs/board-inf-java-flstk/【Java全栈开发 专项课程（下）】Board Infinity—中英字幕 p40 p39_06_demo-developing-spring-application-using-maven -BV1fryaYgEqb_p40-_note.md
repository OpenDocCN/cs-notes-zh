# Java全栈开发：40：使用Maven开发Spring应用教程 🚀

![](img/a8960663a2f7570f822ae1f699f75b04_0.png)

在本节课中，我们将学习如何在Eclipse中使用Maven创建一个Spring应用，并演示如何构建一个基础的Web项目。整个过程将涵盖从项目初始化、配置调整到最终在服务器上运行的完整步骤。

## 概述 📋

上一节我们介绍了Maven的基本概念。本节中，我们来看看如何实际运用Maven在Eclipse中搭建一个Spring Web应用项目。我们将创建一个Maven项目，配置其POM文件，并最终在Tomcat服务器上成功运行。

![](img/a8960663a2f7570f822ae1f699f75b04_2.png)

## 准备工作

首先，如果之前的项目正在Tomcat服务器上运行，需要先清理Tomcat的工作目录。在Eclipse中，右键点击服务器，选择“Clean Tomcat Work Directory”。这将停止任何与Tomcat相关的进程。

## 创建Maven项目

接下来，我们开始创建新的Maven项目。

在Eclipse中，点击 **File** -> **New** -> **Other...**，然后在搜索框中输入“Maven Project”并选择它。

创建Maven项目时，有两种主要选项：
*   **简单项目**：这是一个核心Java项目。选择此项后，系统不会询问项目模板，只会要求进行Maven配置。
*   **使用原型（Archetype）的项目**：如果不选择“简单项目”，点击“Next”后，系统会要求你选择一个项目原型（Archetype）。原型是预定义的项目模板。

对于Web应用，我们需要选择Web应用原型。

以下是创建步骤：
1.  在过滤框中输入“webapp”或“Apache”来搜索原型。以“Apache Maven”开头的原型会被筛选出来。
2.  从列表中选择 **`maven-archetype-webapp`**。Spring框架项目通常也需要Web应用集成。如果只想创建核心Maven项目，可以选择 **`maven-archetype-quickstart`**。
3.  点击“Next”。

## 配置项目

现在需要配置项目的基本信息。

*   **Group Id**：这本质上是项目的基础包名。
*   **Artifact Id**：这是项目的名称，例如可以命名为“MavenWebProject”或“SpringProject”。

填写完毕后，点击“Next”。Maven会根据所选的原型生成项目的基本骨架，这个过程可能需要一点时间。

项目生成成功后，你可以在项目目录中看到 `pom.xml` 文件。

## 调整项目配置

生成的项目可能需要一些调整才能正常工作。

首先，检查 `pom.xml` 文件。默认的Java编译器版本可能是1.7。建议将其至少修改为1.8。在 `pom.xml` 中找到 `<properties>` 部分，修改 `<maven.compiler.source>` 和 `<maven.compiler.target>` 的值。

修改后，右键点击项目，选择 **Maven** -> **Update Project...**。在弹出的窗口中，勾选“Force Update of Snapshots/Releases”，然后点击“OK”。更新完成后，项目的Java标准版就会变为1.8。

接下来，需要配置项目的目标运行时服务器。右键点击项目，选择 **Properties**。在属性窗口中，找到 **Targeted Runtimes**。在这里，选择你的Tomcat服务器版本（例如Tomcat 9.0）。这一步是必须的，它指明了Web应用将在哪个服务器上运行。

在项目的 `src/main/webapp` 文件夹下，已经存在一个 `index.jsp` 文件，其中包含基础的“Hello World”代码。至此，项目的基础结构已准备就绪。

## 构建与运行项目

现在，我们来构建并运行这个Maven Web项目。

首先，构建项目。右键点击项目，选择 **Run As** -> **Maven build...**。在“Goals”输入框中，输入 `clean install`，然后点击“Run”。这将清理并编译项目。控制台输出显示“BUILD SUCCESS”即表示构建成功且没有错误。

构建成功后，即可在服务器上运行。右键点击项目，选择 **Run As** -> **Run on Server**。选择配置好的Tomcat服务器，并确保要运行的是我们刚创建的Maven项目（可能需要从列表中移除其他动态Web项目）。点击“Finish”，服务器将启动。

项目运行后，默认会在Eclipse内置浏览器中打开 `index.jsp` 页面，显示“Hello World”。

![](img/a8960663a2f7570f822ae1f699f75b04_4.png)

![](img/a8960663a2f7570f822ae1f699f75b04_5.png)

## 额外配置与查看

你可以配置在外部浏览器中打开应用。在Eclipse的 **Window** -> **Web Browser** 菜单中选择“External Web Browser”并应用设置。这样下次运行时就会使用系统默认的外部浏览器。

此外，一个重要的文件是 `pom.xml`。在这个文件中，你可以管理项目的所有依赖。默认情况下，JUnit依赖已被添加。你可以通过访问 [Maven中央仓库网站](https://mvnrepository.com/) 查找其他依赖，并将其坐标（groupId, artifactId, version）添加到 `pom.xml` 的 `<dependencies>` 部分。通过这种方式，你可以轻松管理项目所需的所有库。

## 总结 🎯

![](img/a8960663a2f7570f822ae1f699f75b04_7.png)

![](img/a8960663a2f7570f822ae1f699f75b04_8.png)

![](img/a8960663a2f7570f822ae1f699f75b04_9.png)

本节课中，我们一起学习了在Eclipse中使用Maven创建和运行Spring Web应用的全过程。我们完成了从创建Maven项目、选择Web应用原型、配置POM文件和目标运行时，到最终使用 `clean install` 命令构建项目并在Tomcat服务器上成功运行的步骤。掌握这些是进行Java企业级开发的基础。