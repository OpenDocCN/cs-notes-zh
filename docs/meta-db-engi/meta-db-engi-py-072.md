# Python 72：使用Python客户端连接MySQL数据库 🐍🔌

在本节课中，我们将学习如何使用Python客户端连接MySQL数据库。我们将了解如何导入必要的库、建立连接，并理解连接过程中的关键参数。

---

## 概述

基于Python的应用程序需要能够与MySQL数据库通信以执行数据库操作。这意味着需要在Python和MySQL之间建立连接。例如，Little Lemon餐厅需要在其依赖Python的网站和MySQL数据库之间建立连接，以便客户可以查看菜单和预订时段等数据。

## 导入MySQL连接器

首先，您需要熟悉MySQL Python Connector API软件包。这个API促进了Python和MySQL之间的连接。但在使用之前，您需要将其导入到Python程序中。

要导入连接器API，请键入`import`命令，后跟其名称`mysql.connector`，然后选择运行。

然而，每次需要使用API时都输入`mysql.connector`可能很繁琐。因此，我们可以创建一个别名。您可以为`mysql.connector`创建一个名为`connector`的别名。然后，您可以使用这个简写来提高编码效率。

要创建别名，您可以再次键入`import mysql.connector`或使用现有代码，但这次在语句中包含`as connector`。`as`关键字指示Python在未来的所有代码中使用`connector`这个别名来识别`import mysql.connector`。

现在，每次需要使用MySQL Python连接器API时，您只需键入其别名`connector`。但请确保您已首先安装了连接器API，否则会遇到“模块未找到”的错误。

您已成功导入了连接器API（也称为包或软件）。现在，您可以使用访问运算符（点号`.`）开始使用其模块和功能。

## 建立数据库连接

例如，您可以帮Little Lemon使用连接器在其基于Python的网站和MySQL数据库之间建立连接。

首先，创建一个变量来访问连接器模块中的连接功能。将其命名为`connection`，并为其分配值`connector.connect`。

接下来，在一对括号内向`connect`模块传递关键参数。这些参数是数据库用户名和密码，因为只有授权用户才能访问数据库。在这个例子中，用户是`Mario`，密码是`cuisine`。

默认情况下，连接是在Python和安装在您机器本地的数据库之间建立的。这个数据库被称为“本地主机”（Localhost）。它也可以通过其IP地址`127.0.0.1`访问。

在本课程的后续阶段，您将了解更多关于本地主机和其他参数的信息。现在，您应该能够在Python和MySQL之间创建连接了。

以下是建立连接的核心代码：

```python
import mysql.connector as connector

connection = connector.connect(
    user="Mario",
    password="cuisine"
)
```

## 总结

本节课中，我们一起学习了如何为Python程序导入MySQL连接器API，以及如何使用用户名和密码参数在Python和MySQL数据库之间建立基本连接。这是进行后续所有数据库操作的第一步。

---

![](img/6d09288f2b0ad744bdbe60f87973b1e1_1.png)

![](img/6d09288f2b0ad744bdbe60f87973b1e1_1.png)

![](img/6d09288f2b0ad744bdbe60f87973b1e1_2.png)

![](img/6d09288f2b0ad744bdbe60f87973b1e1_2.png)