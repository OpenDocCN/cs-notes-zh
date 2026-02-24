# 后端开发（Django）：P45：将模型对象映射到模板 📋

在本节课中，我们将学习如何将Django模型对象传递给模板，并利用模板语言动态地展示数据库中的数据。这是创建动态网页内容的核心步骤。

Django广受欢迎的原因之一，是它允许开发者快速创建动态网站内容。只需几个步骤，你就能从数据库中取出数据，编写一些逻辑，然后在浏览器中将其展示给最终用户。

之前你已经学习了如何通过传递给模板的对象，在网页上展示动态数据。本节中，我们将通过向模板传递一个模型对象，为“小柠檬”餐厅创建一个动态菜单。我们还将探索如何使用Django模板语言的for循环来遍历对象并展示其内容。

## 准备工作：模型回顾

上一节我们介绍了模型的基本概念。现在，我们来看看之前创建的`Menu`模型。

在`models.py`文件中，我们创建了一个名为`Menu`的模型，它包含`name`和`price`两个属性。注意，`name`被设置为字符字段（`CharField`），而`price`被设置为整数字段（`IntegerField`）。我们还创建了一个`__str__`方法，该方法会使用`name`属性为对象渲染一个字符串。

![](img/9550cc4eb70bafba1e8dd194583656a5_1.png)

```python
from django.db import models

class Menu(models.Model):
    name = models.CharField(max_length=200)
    price = models.IntegerField()

    def __str__(self):
        return self.name
```

这个方法有助于在Django管理后台进行可视化和识别。在浏览器中打开Django管理后台，可以看到这个模型包含了诸如“鹰嘴豆泥”、“沙拉三明治”等菜单项的数据。

![](img/9550cc4eb70bafba1e8dd194583656a5_3.png)

## 创建视图函数

准备工作就绪后，接下来我们创建视图函数。

在`views.py`文件中，我创建了另一个名为`menu`的视图函数。与之前的视频类似，我传入了`request`对象，但这里需要采取几个不同的步骤。

![](img/9550cc4eb70bafba1e8dd194583656a5_5.png)

以下是创建视图的步骤：

1.  首先，从`models.py`文件中导入`Menu`模型。
2.  接下来，在函数内部，我需要创建一个包含`Menu`模型内所有值的对象。为此，我使用`Menu.objects.all()`方法，并将其赋值给一个名为`new_menu`的变量。
3.  第三步是创建一个字典。使用你之前学过的类似逻辑，在花括号内，我创建一个名为`‘menu’`的键，其值就是变量`new_menu`。这个字典被赋值给另一个变量`new_menu_dict`。
4.  最后一步是返回一个`render`函数，它接收三个参数：`request`对象、模板文件名和刚才创建的字典。

以下是完整的视图函数代码：

```python
from django.shortcuts import render
from .models import Menu  # 从当前目录的models模块导入Menu类

def menu(request):
    # 获取Menu模型中的所有对象
    new_menu = Menu.objects.all()
    # 创建上下文字典，将查询集传递给模板
    new_menu_dict = {‘menu‘: new_menu}
    # 渲染模板并返回响应
    return render(request, ‘menuCard.html‘, new_menu_dict)
```

屏幕上代码较多，因此我将之前创建的视图函数注释掉。这也能确保不会因两个函数中的某些名称相似而引起正则表达式冲突。

保存文件后，我需要检查`urls.py`文件中的URL映射。

注意，`path`函数内的URL被设置为`‘menu/‘`作为资源定位地址。视图函数`menu`被指定为要调用的函数。

```python
from django.urls import path
from . import views

urlpatterns = [
    path(‘menu/‘, views.menu, name=‘menu‘),
]
```

## 创建模板文件

最后一部分，我需要创建一个与`render`函数中键入的名称相同的HTML文件：`menuCard.html`。

在模板文件中，我将访问从字典传递过来的`‘menu‘`键。

首先，我直接尝试在模板中显示`menu`变量：

![](img/9550cc4eb70bafba1e8dd194583656a5_7.png)

```html
{{ menu }}
```

保存所有文件后，我打开浏览器，导航到URL `‘/menu/‘` 并按回车。

注意，网页上显示的是一个查询集对象。我希望页面只显示对象中的具体项目，因此需要修改代码。

## 使用模板语言动态展示数据

![](img/9550cc4eb70bafba1e8dd194583656a5_9.png)

回到HTML文件，我需要使用Django模板语言配合条件语句和循环。

以下是修改模板的步骤：

1.  我首先添加一个`if`条件语句，检查`menu`中是否有项目。
2.  如果条件为真，我使用一个`for`循环来遍历`menu`中的项目。
3.  在循环体内，我使用`{{ item.name }}`和`{{ item.price }}`来显示每个项目的名称和价格。
4.  我需要确保使用`{% endfor %}`来结束`for`循环。
5.  最后，我添加一个`else`条件，如果`menu`对象为空，则显示一些文本。
6.  使用`{% endif %}`结束`if`条件。

修改后的模板代码如下：

```html
<!DOCTYPE html>
<html>
<body>
    {% if menu %}
        {% for item in menu %}
            {{ item.name }} : {{ item.price }}
        {% endfor %}
    {% else %}
        <p>No items to display.</p>
    {% endif %}
</body>
</html>
```

![](img/9550cc4eb70bafba1e8dd194583656a5_11.png)

代码看起来没问题。我保存文件并刷新浏览器中的网页。现在，只有对象的名称和价格被动态显示出来。

理解这一点很重要：这些数据是从数据库中获取，并使用模型存储在模型对象中的。然后我遍历该对象以显示每个项目的名称和价格值。

## 优化显示格式

代码已经可以工作，但我可以通过最后一步来进一步优化：用HTML段落标签包裹动态输出的内容。

![](img/9550cc4eb70bafba1e8dd194583656a5_13.png)

```html
<!DOCTYPE html>
<html>
<body>
    {% if menu %}
        {% for item in menu %}
            <p>{{ item.name }} : ${{ item.price }}</p>
        {% endfor %}
    {% else %}
        <p>No items to display.</p>
    {% endif %}
</body>
</html>
```

![](img/9550cc4eb70bafba1e8dd194583656a5_15.png)

如果我保存文件并刷新网页，会注意到现在每个项目都显示在新的一行上。

## 测试动态更新

最后，为了演示这个动态网页，让我使用Django管理后台向数据库添加另一个项目。

我添加一个名为“Baklava”、价格为10的项目。保存该项目后，我切换到菜单页面并刷新。

注意，内容会自动更新，并显示新添加的项目。

![](img/9550cc4eb70bafba1e8dd194583656a5_17.png)

## 总结 🎯

![](img/9550cc4eb70bafba1e8dd194583656a5_19.png)

本节课中，我们一起学习了如何通过从视图向模板传递模型对象来创建动态菜单。你还探索了如何使用Django模板语言的`for`循环来遍历对象并显示其内容。这个过程涵盖了从数据库获取数据、在视图中处理、最后在模板中动态渲染的完整流程，是Django Web开发的基础。