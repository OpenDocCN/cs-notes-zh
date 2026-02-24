# 24：创建模型 🏗️

在本节课中，我们将学习如何在Django项目中创建数据模型。模型是Django应用的核心，它定义了数据的结构和行为，并直接映射到数据库中的表。

## 概述

![](img/922f3625d0731615b849d40294ff7969_1.png)

上一节我们介绍了Django模型的基本概念。本节中，我们将通过一个具体的例子，一步步学习如何在`models.py`文件中创建模型，如何通过Django Shell与模型交互，以及如何对数据进行基本的增删改查操作。

## 创建模型类

要构建一个模型，需要在`models.py`文件中编写代码。假设我正在为“小柠檬餐厅”构建一个菜单系统。

首先，我创建一个名为`Menu`的类，并让它继承自`models.Model`。

```python
from django.db import models

class Menu(models.Model):
```

## 定义模型字段

在类内部，我将创建三个变量作为模型的属性。每个属性都需要指定一个字段类型。

以下是需要定义的字段：
*   `name`: 菜品名称。
*   `cuisine`: 菜系。
*   `price`: 价格。

我为`name`变量分配一个`models.CharField`字段，它用于存储中小型字符串。我可以传入`max_length`参数并设置一个值，例如100。

```python
    name = models.CharField(max_length=100)
```

对`cuisine`变量重复相同的过程。

对于`price`，我使用`models.IntegerField`字段来存储整数值。注意，这里我不需要传递任何参数。

```python
    cuisine = models.CharField(max_length=100)
    price = models.IntegerField()
```

至此，模型所需的代码就编写完成了。

## 注册应用与数据迁移

现在让我尝试访问这个模型。在终端中，我输入命令`python manage.py shell`并按回车。

我进入了Django的命令行工具。需要知道的是，我不能直接在shell中访问`Menu`类。首先，我必须从`menu_app`文件夹内的`models.py`文件中导入它。

我使用Python的导入命令：`from menu_app.models import Menu`，然后按回车。注意，我收到了一个错误。

这是因为我没有在`settings.py`文件的`INSTALLED_APPS`列表中添加这个应用。所以，我现在打开那个文件，将应用添加到已安装应用列表中。

```python
INSTALLED_APPS = [
    ...
    'menu_app',
]
```

添加应用后，我需要执行一个叫做“迁移”的操作。暂时不用过于担心这一步，你将在后续课程中详细了解迁移。现在只需知道，这是在Django中操作模型必须运行的命令。

我运行命令：`python manage.py makemigrations`。注意，它为`Menu`模型创建了一个迁移文件。如果你查看这个Python文件，可以看到Django内部已经使用内置的SQLite数据库创建了`menu`表的列结构。

为了完成这一步，我运行另一个迁移命令：`python manage.py migrate`。

## 使用Django Shell操作数据

现在，我准备回到shell中操作我创建的`Menu`模型。让我先清空终端，再次运行`python manage.py shell`。

进入shell后，我再次导入`Menu`类。这次没有出现错误。

我现在可以运行命令`Menu.objects.all()`，它会返回数据库中的所有条目。由于我还没有任何数据，所以返回一个空的查询集。

我将直接使用命令向数据库中添加一个条目：`m = Menu.objects.create(name='Pasta', cuisine='Italian', price=10)`。注意，我将这个条目赋值给了一个对象`m`，这样我就可以对这个对象进行操作，例如更新或保存。我按回车，然后保存这个对象。

现在，如果我再次运行命令来返回数据库中的所有条目，会注意到有一个条目在数据库中。

让我快速添加另一个条目，然后再次查看数据库条目。注意，现在有两个对象，但显示的信息不够直观，只显示了菜单对象一和二的名称。

## 自定义模型显示

Django提供了一种使用“自定义方法”来改变显示方式。例如，我可以使用一个内置的自定义方法`__str__`来定制字符串表示。

我在`Menu`类中添加以下方法：
```python
    def __str__(self):
        return self.name + ': ' + self.cuisine
```

`__str__`是一个“魔法方法”，用于返回对象的字符串表示。保存文件后，我必须退出shell并重新进入。

再次进入shell后，我可以像在Python文件中一样编写代码。我再次导入`Menu`类，并运行显示所有条目的命令。注意，现在细节按照我定义的`__str__`自定义函数打印出来了。

类似地，我可以创建自己的自定义函数以供使用。

## 更新数据条目

既然我已经演示了如何创建数据库表和添加条目，现在让我演示如何更新条目。

假设我想访问一个条目并更新它。我可以使用`get`方法并传入主键值`2`，它指向“Taco”这个条目。然后，我可以将其赋值给我创建的一个名为`p`的对象。

```python
p = Menu.objects.get(pk=2)
```

现在，我可以像在常规Python代码中一样访问这个对象内的属性。我输入`p.cuisine = 'Mexican'`来更新条目。我保存这个更改。

这次当我显示所有条目时，会注意到数值已经更新。

## 总结

![](img/922f3625d0731615b849d40294ff7969_3.png)

本节课中，我们一起学习了在`models.py`文件中创建Django模型的全过程。我们定义了模型类及其字段，通过迁移命令将模型同步到数据库，并使用Django Shell进行了数据的创建、查询和更新操作。我们还了解了如何通过`__str__`方法自定义模型对象的显示方式。虽然也可以通过Django管理后台来查看和更新数据库，但理解代码在内部如何工作同样重要。本视频只是为你展示了如何使用模型的一个例子，你将在后续课程中学习更多关于迁移、管理界面以及使用Django和Python代码可以添加的其他功能。