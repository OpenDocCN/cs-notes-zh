# Python 71：安装与设置

在本节课中，我们将学习如何为数据库工程任务安装和配置Python环境，并建立Python与MySQL数据库之间的连接。我们将从下载Python开始，逐步设置开发环境，并安装必要的库来实现数据库交互。

---

![](img/dba673520e1b2c47ef1823093b04f72f_1.png)

## 下载与安装Python

首先，你需要从Python官方网站下载最新版本的Python。请遵循网站上的安装说明进行操作。

安装完成后，你需要验证Python是否正确安装。打开命令提示符，输入以下命令来检查你机器上运行的Python版本：

```bash
python --version
```

如果Python安装正确，控制台将显示类似 `Python 3.x.x` 的信息，这表明你正在运行Python 3。请确保版本号与Python官网上的最新版本匹配。如果看到“Python not found”的提示，请检查你的安装步骤或参考Python官网的相关文档。

---

## 选择与设置集成开发环境

上一节我们介绍了如何安装Python，本节中我们来看看如何设置一个编写和运行代码的环境。你需要选择一个IDE（集成开发环境）。本课程使用Jupyter IDE来演示Python代码，因此建议你也使用Jupyter环境。

![](img/dba673520e1b2c47ef1823093b04f72f_3.png)

以下是安装Jupyter的步骤：

1.  打开命令提示符。
2.  输入以下命令来安装Jupyter：
    ```bash
    python -m pip install jupyter
    ```
3.  安装完成后，输入以下命令来启动Jupyter Notebook：
    ```bash
    python -m notebook
    ```

此命令将在你的默认浏览器中打开一个新的Jupyter Notebook实例。

---

![](img/dba673520e1b2c47ef1823093b04f72f_5.png)

![](img/dba673520e1b2c47ef1823093b04f72f_6.png)

## 配置工作环境

现在，你可以在Jupyter中设置你的工作环境。

1.  在Jupyter主界面，点击“New”按钮。
2.  选择“Folder”来创建一个新文件夹。这将生成一个名为“Untitled Folder”的文件夹。
3.  将这个新文件夹重命名为 `mysql_python_course_content`，然后点击进入。
4.  在这个文件夹内，再次点击“New”按钮。
5.  选择“Python 3 (ipykernel)”选项。这将打开一个新的浏览器标签页，你可以在其中输入和运行Python代码。

---

![](img/dba673520e1b2c47ef1823093b04f72f_8.png)

## 安装MySQL连接器

![](img/dba673520e1b2c47ef1823093b04f72f_10.png)

为了在Python和MySQL数据库之间建立连接，我们需要使用一个专门的Python库，名为 `mysql-connector-python`。这个库是一个API，提供了许多用于操作MySQL的实用功能。

`mysql-connector-python` 需要使用Python自带的包管理工具 `pip` 进行单独安装。

以下是安装步骤：

1.  在你刚刚创建的Jupyter Notebook代码单元格中，输入以下命令：
    ```bash
    !pip install mysql-connector-python
    ```
2.  按下 `Shift + Enter` 或点击“Run”按钮来执行代码。

代码执行后，控制台将输出安装过程的信息。如果安装成功，你将看到一系列库被成功安装的提示。这意味着Python现在可以访问这些库的所有功能。

---

## 导入MySQL连接器库

安装完成后，你需要在Python代码中导入这个库才能使用它。在Python中，使用 `import` 语句来导入库。

在你的Jupyter Notebook的新单元格中，输入以下代码：

```python
import mysql.connector as connector
```

这段代码的含义如下：
*   `import`：告诉Python你想要导入并使用一个库。
*   `mysql.connector`：`mysql` 是 `pip` 安装的主包，`.connector` 是使用点运算符访问的该包下的子模块。
*   `as connector`：这是一种使用别名的重命名方法。它将 `mysql.connector` 简化为 `connector`，方便后续代码调用。在Python开发中使用别名是常见做法，最好使用其他开发者熟悉的通用别名。

运行这段代码。如果控制台没有输出任何错误信息，则表明 `mysql-connector-python` 已成功导入，你现在可以与你的MySQL数据库进行通信了。

---

## 总结

![](img/dba673520e1b2c47ef1823093b04f72f_12.png)

![](img/dba673520e1b2c47ef1823093b04f72f_13.png)

本节课中我们一起学习了为数据库工程配置Python环境的完整流程。我们首先下载并安装了Python，然后设置了Jupyter开发环境。接着，我们使用 `pip` 安装了关键的 `mysql-connector-python` 库，并最终在代码中成功导入该库，为后续连接和操作MySQL数据库做好了准备。现在，你的Python环境已经准备就绪，可以开始进行数据库操作了。