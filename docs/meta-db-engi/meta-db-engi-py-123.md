# 123：创建数据库客户端 🛠️

在本节课中，我们将学习如何为Little Lemon餐厅创建一个数据库客户端。我们将通过Python应用程序与MySQL数据库进行交互。具体任务包括：检查Python版本、安装合适的集成开发环境（IDE），以及将Python连接到Little Lemon的MySQL数据库。

![](img/11b17e63f2eda7f4c07ff407dd23b340_1.png)

---

## 检查Python版本 🐍

首先，我们需要确认您的计算机上安装的Python版本。这是确保后续步骤兼容性的基础。

打开命令提示符，输入以下命令来检查Python版本：

```bash
python --version
```

如果Python已正确安装，控制台将显示类似 `Python 3.x.x` 的信息。这表明您正在运行Python 3版本。请确保显示的版本号与Python官方网站（python.org）上的最新版本相匹配。

如果您看到“Python 不是内部或外部命令”的提示，则需要重新检查Python的安装，或参考Python官网的相关文档进行配置。

---

![](img/11b17e63f2eda7f4c07ff407dd23b340_3.png)

![](img/11b17e63f2eda7f4c07ff407dd23b340_4.png)

![](img/11b17e63f2eda7f4c07ff407dd23b340_5.png)

## 安装集成开发环境（IDE） 💻

![](img/11b17e63f2eda7f4c07ff407dd23b340_6.png)

![](img/11b17e63f2eda7f4c07ff407dd23b340_7.png)

![](img/11b17e63f2eda7f4c07ff407dd23b340_8.png)

上一节我们确认了Python环境，本节中我们来看看如何安装一个合适的IDE来编写和运行代码。IDE是用于显示和编辑代码的软件。

![](img/11b17e63f2eda7f4c07ff407dd23b340_9.png)

![](img/11b17e63f2eda7f4c07ff407dd23b340_10.png)

在本课程中，我们将使用Jupyter IDE来演示Python代码。要安装Jupyter，请在您的Python环境中输入以下命令：

```bash
python -m pip install jupyter
```

然后，按照Jupyter的安装流程进行操作。安装完成后，输入 `jupyter notebook` 命令，这将在您的默认浏览器中打开一个新的Jupyter笔记本实例，供您使用。

---

## 连接Python到MySQL数据库 🔌

现在我们已经准备好了Python和IDE，下一步是将Python连接到MySQL数据库。为此，我们需要使用一个专为MySQL设计的Python库，名为 **mysql-connector-python**。这个库是一个API，提供了许多操作MySQL的实用功能。

`mysql-connector-python` 库需要通过Python的包管理工具 `pip` 单独安装。`pip` 通常随Python软件一同安装。

首先，在Jupyter中创建一个新的笔记本实例，并将其命名为 `configuring_mysql_connector`。

![](img/11b17e63f2eda7f4c07ff407dd23b340_12.png)

![](img/11b17e63f2eda7f4c07ff407dd23b340_13.png)

以下是安装该库的步骤：

![](img/11b17e63f2eda7f4c07ff407dd23b340_14.png)

![](img/11b17e63f2eda7f4c07ff407dd23b340_15.png)

1.  在Jupyter笔记本的一个单元格中，输入以下命令来调用pip并安装连接器：

    ```python
    !pip install mysql-connector-python
    ```

    请注意，库的名称中 `python` 的 ‘p’ 是小写。

![](img/11b17e63f2eda7f4c07ff407dd23b340_16.png)

![](img/11b17e63f2eda7f4c07ff407dd23b340_17.png)

![](img/11b17e63f2eda7f4c07ff407dd23b340_18.png)

2.  按下 `Shift + Enter` 或点击“运行”按钮来执行这行代码。

![](img/11b17e63f2eda7f4c07ff407dd23b340_19.png)

![](img/11b17e63f2eda7f4c07ff407dd23b340_20.png)

![](img/11b17e63f2eda7f4c07ff407dd23b340_21.png)

---

## 验证环境配置 ✅

最后一步是检查您的环境是否已正确配置。我们将尝试导入刚刚安装的库。

![](img/11b17e63f2eda7f4c07ff407dd23b340_23.png)

在Jupyter的新单元格中，输入以下代码：

![](img/11b17e63f2eda7f4c07ff407dd23b340_24.png)

![](img/11b17e63f2eda7f4c07ff407dd23b340_25.png)

```python
import mysql.connector as connector
```

然后运行该单元格。如果单元格没有输出任何错误信息，则表明 `mysql.connector` 库已成功导入。这意味着您的Python环境现在已经准备好与MySQL数据库进行交互了。

---

## 总结 📝

![](img/11b17e63f2eda7f4c07ff407dd23b340_27.png)

本节课中我们一起学习了为Little Lemon创建数据库客户端的基础准备工作。我们完成了三个核心任务：检查并确认了Python 3的运行环境；安装并启动了Jupyter IDE作为开发工具；最后，使用 `pip` 安装了 `mysql-connector-python` 库，并成功验证了Python与MySQL的连接能力。

![](img/11b17e63f2eda7f4c07ff407dd23b340_28.png)

![](img/11b17e63f2eda7f4c07ff407dd23b340_29.png)

如果您对本节课的任何部分需要更多指导，可以回顾之前课程中的具体学习材料。