# Django for Everybody：04：Django 模型与数据库

## 概述

在本节课中，我们将学习Django框架中一个核心概念：**模型**。模型是Django用于与数据库交互的工具，它允许我们使用Python代码来定义数据结构，而无需直接编写复杂的SQL语句。我们将了解如何创建模型、进行数据库迁移以及使用Django的管理界面来操作数据。

上一节我们介绍了Django项目的基本结构和视图，本节中我们来看看如何定义和管理应用程序的数据。

## 什么是Django模型？

Django模型是一个Python类，它继承自`django.db.models.Model`。这个类中的每一个属性都代表数据库表中的一个字段。Django会根据这个模型类自动在数据库中创建对应的数据表。

**核心概念公式**：
`一个Django模型类 = 一张数据库表`

**示例代码**：
```python
from django.db import models

class Book(models.Model):
    title = models.CharField(max_length=200)
    author = models.CharField(max_length=100)
    published_date = models.DateField()
```
在上面的代码中，我们定义了一个`Book`模型，它对应数据库中的一张表。这张表将拥有`title`、`author`和`published_date`三个字段。

## 创建模型并进行迁移

定义好模型后，我们需要告诉Django去创建对应的数据库表。这个过程分为两步：生成迁移文件和执行迁移。

以下是创建并应用模型迁移的步骤：

1.  **生成迁移文件**：Django会检测你对模型所做的更改（例如新建或修改了一个模型类），并生成一个描述这些更改的Python脚本。
    ```bash
    python manage.py makemigrations
    ```

2.  **执行迁移**：Django会读取迁移文件，并将其中的指令应用到数据库中，从而创建或修改表结构。
    ```bash
    python manage.py migrate
    ```

执行完这两条命令后，你的模型所对应的数据表就已在数据库中准备就绪了。

## 使用Django管理界面

Django提供了一个强大的内置管理界面（Admin Site），允许开发者无需编写额外代码就能对模型数据进行增、删、改、查操作。

要使用管理界面，你需要完成以下步骤：

1.  **创建超级用户**：首先，你需要创建一个可以登录管理后台的账户。
    ```bash
    python manage.py createsuperuser
    ```
    按照提示输入用户名、邮箱和密码。

2.  **注册模型**：在应用的`admin.py`文件中，注册你定义的模型，这样它才会在管理界面中显示。
    ```python
    # 在 yourapp/admin.py 中
    from django.contrib import admin
    from .models import Book

    admin.site.register(Book)
    ```

3.  **访问管理界面**：运行开发服务器后，在浏览器中访问 `http://127.0.0.1:8000/admin/`，使用你创建的超级用户账号登录。你就能看到`Book`模型，并可以对其进行管理操作。

## 总结

本节课中我们一起学习了Django模型的基础知识。我们了解到模型是连接Python代码与数据库的桥梁，通过定义模型类可以自动生成数据库表。我们学会了使用`makemigrations`和`migrate`命令来同步数据库结构，并且探索了如何使用Django内置的管理界面来方便地管理数据。掌握模型是构建Django Web应用数据层的基石。