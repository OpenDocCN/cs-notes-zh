# Django for Everybody：05_02_02：Django数据模型 🗄️

![](img/0d752d16c37a1be222fb33c5777caf09_1.png)

![](img/0d752d16c37a1be222fb33c5777caf09_3.png)

![](img/0d752d16c37a1be222fb33c5777caf09_4.png)

![](img/0d752d16c37a1be222fb33c5777caf09_5.png)

![](img/0d752d16c37a1be222fb33c5777caf09_6.png)

在本节课中，我们将要学习Django数据模型。数据模型是Django应用与数据库交互的核心，它使用一种称为“对象关系映射”的技术，让我们可以用Python对象来操作数据库，而无需编写复杂的SQL语句。

![](img/0d752d16c37a1be222fb33c5777caf09_8.png)

## 回顾SQL

![](img/0d752d16c37a1be222fb33c5777caf09_10.png)

在之前的课程中，我们介绍了SQL（结构化查询语言）。SQL是与数据库通信的标准方式，它允许我们在一定程度上跨不同数据库进行移植。

![](img/0d752d16c37a1be222fb33c5777caf09_12.png)

以下是一些基本的SQL命令示例：
```sql
CREATE TABLE Users (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name VARCHAR(128),
    email VARCHAR(128)
);
```
我们可以运行这些命令来创建表、查询数据等。然而，SQL也存在一些问题。不同数据库（如PostgreSQL、MySQL）在某些高级功能（如外键、分页查询）的实现上存在差异。学习SQL的基础部分相对容易，但要精通所有数据库的高级特性则非常困难。

## 对象关系映射器的出现

为了解决SQL的复杂性和数据库差异性问题，出现了对象关系映射器。ORM在物理数据库层和SQL抽象层之上，又构建了一层抽象。

![](img/0d752d16c37a1be222fb33c5777caf09_14.png)

在Django中，我们通过创建Python类来定义数据模型。这个类会映射到数据库中的一张表。ORM的优势在于：
*   **简化开发**：约80%的常见数据库操作，使用ORM比直接写SQL更简单。
*   **数据库可移植性**：ORM代码知道如何处理SQLite、PostgreSQL和MySQL等不同数据库的差异。你可以在开发时使用SQLite，部署时切换到MySQL，而无需修改核心代码。
*   **聚焦业务逻辑**：开发者可以更专注于数据结构和业务逻辑，而非数据库语法。

![](img/0d752d16c37a1be222fb33c5777caf09_16.png)

## 定义Django模型

在Django中，我们在应用的 `models.py` 文件中定义模型。

我们通过继承 `django.db.models.Model` 类来创建模型。这个基类为我们提供了大量现成的功能。在类内部，我们定义属性，这些属性对应数据库表中的列。

![](img/0d752d16c37a1be222fb33c5777caf09_18.png)

以下是一个定义 `User` 模型的例子，它等同于之前用SQL创建的 `Users` 表：
```python
from django.db import models

class User(models.Model):
    name = models.CharField(max_length=128)
    email = models.CharField(max_length=128)
```
*   `User` 类名对应数据库表名（Django通常会做一些命名转换，例如可能变成 `appname_user`）。
*   `name` 和 `email` 是模型字段，分别对应表中的列。
*   `models.CharField` 表示这是一个字符字段，`max_length` 参数定义了最大长度。

![](img/0d752d16c37a1be222fb33c5777caf09_20.png)

## 迁移：同步模型与数据库

定义模型后，我们需要将其同步到数据库，这个过程称为“迁移”。

迁移分为两步：
1.  **生成迁移文件**：在项目根目录下运行 `python manage.py makemigrations`。此命令会读取 `models.py` 中的变更，并生成一个包含具体SQL操作的Python脚本文件（如 `0001_initial.py`）。
2.  **应用迁移**：运行 `python manage.py migrate`。此命令会执行迁移文件中定义的SQL操作，在数据库中实际创建或修改表结构。

![](img/0d752d16c37a1be222fb33c5777caf09_22.png)

迁移机制非常强大，它允许你在开发环境调试好数据库结构后，将同样的变更安全地应用到生产环境，即使生产环境使用的是不同的数据库。

在开发中，Django默认会创建一个 `db.sqlite3` 文件作为数据库。如果你把数据库弄乱了，可以删除这个文件，然后重新运行 `migrate` 命令来重建。

## 使用Django Shell操作数据

![](img/0d752d16c37a1be222fb33c5777caf09_24.png)

Django提供了一个增强的Python Shell，预加载了项目环境，方便我们测试模型操作。

要启动它，请在项目根目录运行：
```bash
python manage.py shell
```

![](img/0d752d16c37a1be222fb33c5777caf09_26.png)

在Shell中，我们可以进行数据的增删改查操作。以下是核心的CRUD操作示例：

**创建数据**
```python
from myapp.models import User # 从你的应用导入模型

![](img/0d752d16c37a1be222fb33c5777caf09_28.png)

u = User(name='Kristen', email='k@example.com') # 在内存中创建对象
u.save() # 将对象保存到数据库，执行INSERT操作
print(u.id) # 保存后，数据库会自动分配一个id
```

![](img/0d752d16c37a1be222fb33c5777caf09_30.png)

**查询数据**
以下是查询数据的基本方法。
*   `User.objects.all()`：获取所有用户对象（对应 `SELECT *`）。
*   `User.objects.filter(email='k@example.com')`：根据条件过滤（对应 `WHERE` 子句）。
*   `User.objects.filter(email='k@example.com').values()`：执行查询并获取结果字典。

**更新数据**
```python
User.objects.filter(email='k@example.com').update(name='NewName')
```

![](img/0d752d16c37a1be222fb33c5777caf09_32.png)

**删除数据**
```python
User.objects.filter(email='k@example.com').delete()
```

## 模型字段类型

Django提供了丰富的字段类型，它们不仅定义了数据库中的列类型，还常常包含额外的验证逻辑。

![](img/0d752d16c37a1be222fb33c5777caf09_34.png)

例如，`models.EmailField` 是一个邮箱字段。数据库本身可能没有专门的“邮箱”类型，但Django的ORM层会确保输入的数据符合邮箱地址格式。其他常用字段还包括 `IntegerField`、`DateField`、`TextField` 等。

在后续课程中，我们还会学习用于表间关联的字段，如 `ForeignKey`（外键）、`ManyToManyField`（多对多关系）等。

![](img/0d752d16c37a1be222fb33c5777caf09_36.png)

## 模型在Django架构中的位置

理解模型在整体架构中的位置非常重要。

一个典型的Django请求流程如下：
1.  用户通过浏览器发起请求。
2.  URL配置（`urls.py`）将请求路由到对应的视图函数（`views.py`）。
3.  视图函数是处理业务逻辑的核心。**它通过模型（`models.py`）与数据库进行交互**。
4.  视图函数使用模板和表单来生成最终的HTML响应，返回给浏览器。

![](img/0d752d16c37a1be222fb33c5777caf09_38.png)

此外，Django强大的内置管理后台（admin site）也是通过读取 `models.py` 和 `admin.py` 的配置，自动生成界面来管理模型数据的。

## 总结

![](img/0d752d16c37a1be222fb33c5777caf09_40.png)

本节课中我们一起学习了Django数据模型的核心概念。

我们了解到，Django模型是其对象关系映射器的实现。它允许我们使用Python类来定义数据库结构，并通过这些类的实例来操作数据，这比直接编写SQL更加直观和高效。模型带来了数据库可移植性，并提供了强大的迁移工具来管理数据库结构的演变。同时，模型还是Django自动生成管理后台和表单的基础。

虽然ORM能处理大部分场景，但了解底层的SQL知识仍然非常重要，因为在处理一些非常复杂的查询时，直接使用SQL可能更合适。然而，对于典型的Web应用开发，Django模型将是你最得力的工具之一。