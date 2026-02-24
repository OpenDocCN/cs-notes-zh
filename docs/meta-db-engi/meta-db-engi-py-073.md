# Python 73：使用Python在MySQL数据库中创建数据库和表 🗄️

在本节课中，我们将学习如何通过Python程序连接到MySQL数据库，并执行创建新数据库和数据表的操作。这是构建数据驱动应用程序的基础步骤。

![](img/1f31fc6ecfd27eb35f7eb62a8e0fed85_1.png)

---

上一节我们介绍了如何建立Python与MySQL的连接。本节中，我们来看看在连接建立后，如何具体执行创建数据库和表的操作。

## 创建游标对象

与MySQL数据库建立连接后，需要通过一个“游标”对象来执行SQL命令。游标可以理解为指向数据库中特定位置的指针，它允许应用程序执行查询并获取结果。

创建游标对象的代码如下：
```python
cursor = connection.cursor()
```

## 创建新数据库

以下是创建名为“LittleLemon”数据库的步骤。

首先，将SQL语句编写为Python字符串，并存储在一个变量中。使用三引号可以方便地将长SQL语句写成多行，提高可读性。

```python
create_database_query = """
CREATE DATABASE LittleLemon;
"""
```

接着，使用游标对象的`execute()`方法来执行这个SQL语句。

```python
cursor.execute(create_database_query)
```

## 选择使用的数据库

数据库创建成功后，需要明确指定后续操作在此数据库中进行。

以下是选择使用“LittleLemon”数据库的代码：

```python
use_database_query = "USE LittleLemon;"
cursor.execute(use_database_query)
```

## 在数据库中创建表

现在数据库已准备就绪，下一步是在其中创建存储数据的表。

我们将创建一个名为`MenuItems`的表，用于存储菜单项信息。该表包含以下列：
*   `ItemID`: 主键，整数类型，自动递增。
*   `Name`: 菜品名称，可变字符类型，最大长度200。
*   `Type`: 菜品类型（如菜系），可变字符类型，最大长度100。
*   `Price`: 价格，整数类型。

创建该表的SQL语句和Python代码如下：

```python
create_menu_item_table = """
CREATE TABLE MenuItems (
    ItemID INT AUTO_INCREMENT,
    Name VARCHAR(200),
    Type VARCHAR(100),
    Price INT,
    PRIMARY KEY (ItemID)
);
"""
cursor.execute(create_menu_item_table)
```

使用相同的方法，您可以创建数据库所需的任何其他表，只需修改相应的SQL查询语句即可。

---

![](img/1f31fc6ecfd27eb35f7eb62a8e0fed85_3.png)

![](img/1f31fc6ecfd27eb35f7eb62a8e0fed85_4.png)

本节课中我们一起学习了使用Python操作MySQL数据库的核心流程。我们首先通过连接对象创建了游标，然后依次执行了创建数据库、选择数据库以及创建数据表的SQL命令。掌握这些步骤是进行后续数据插入、查询和更新等操作的基础。