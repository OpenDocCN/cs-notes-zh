# Meta后端开发课程：P53：解决方案第2部分：创建菜单项页面 🍽️

在本节课中，我们将学习如何为餐厅网站创建一个动态的菜单项详情页面。我们将从更新数据模型开始，逐步完成视图、模板和URL的配置，最终实现点击菜单列表中的项目即可查看其详细信息的功能。

## 概述
我们将分步完成以下任务：首先更新`Menu`模型并执行数据库迁移；然后在Django管理后台为菜单项添加描述；接着创建用于显示单个菜单项的视图函数和模板；最后配置URL并测试页面功能。

## 更新数据模型与迁移
上一节我们完成了菜单列表的展示，本节中我们来看看如何为每个菜单项添加详情页面。首先，我们需要为菜单项模型添加一个`description`字段。

![](img/31db02f67b04488da4298707949d52e3_1.png)

第一步是打开`models.py`文件，在`Menu`模型中更新`description`属性。

```python
# 在Menu模型中添加description字段
description = models.TextField(max_length=1000, default='')
```

接下来，在终端中运行命令以执行迁移，将模型的更改应用到数据库。

![](img/31db02f67b04488da4298707949d52e3_3.png)

```bash
python manage.py makemigrations
python manage.py migrate
```

![](img/31db02f67b04488da4298707949d52e3_1.png)

## 在Django管理后台更新数据
迁移完成后，使用之前创建的超级用户凭证登录Django管理后台，并根据压缩文件中提供的描述信息更新菜单项。

![](img/31db02f67b04488da4298707949d52e3_3.png)

在Django管理面板中，点击来自`restaurant`应用的`Menu`模型，以显示菜单项列表。

从列表中选择一个特定的项目进行编辑，并使用压缩文件中提供的详细信息更新其`description`字段。

为所有菜单项添加描述后，即可进行下一步。

## 创建视图函数
现在，打开`views.py`文件，创建一个名为`display_menu_item`的视图函数。

该函数必须包含两个参数：`request`和主键`pk`，其中`pk`的默认值设置为`None`。

在函数体内，添加代码以定义视图逻辑。

```python
def display_menu_item(request, pk=None):
    if pk:
        menu_item = Menu.objects.get(pk=pk)
    else:
        menu_item = ''
    return render(request, 'menu_item.html', {'menu_item': menu_item})
```

使用`if`条件检查主键`pk`是否包含值。如果为真，则创建一个变量`menu_item`，并使用`objects.get()`方法根据主键从`Menu`模型中获取对应的菜单项对象。

对于`else`条件，将一个空字符串赋值给变量`menu_item`。

最后，从视图中返回`render`函数，并传递以下参数：`request`对象、模板名称`menu_item.html`，以及一个字典对象。该字典以字符串`'menu_item'`为键，以变量`menu_item`作为其值。

## 配置URL路由
完成视图函数后，打开应用级别的`urls.py`文件，在`urlpatterns`列表中添加`path`函数。

在配置新的菜单项页面路径之前，需要先打开`menu.html`文件，更新代码以添加指向菜单项页面的链接。

选择`href`属性内的完整字符串，将其替换为指向菜单项页面的动态链接的DTL代码。

```django
<!-- 将硬编码的链接替换为动态URL -->
<a href="{% url 'menu_item' pk=item.pk %}">{{ item.name }}</a>
```

请注意，不要移除HTML属性字符串的引号。

## 创建菜单项详情模板
下一步是在名为`Restaurant`的应用内的`templates`文件夹中创建一个名为`menu_item.html`的文件。创建完成后，添加起始代码。

根据注释，使用适当的Django模板语言语法替换匹配的代码。

以下是需要完成的步骤：

首先，添加来自`menu_item`对象的`name`属性。

```django
<h2>{{ menu_item.name }}</h2>
```

接下来，添加来自`menu_item`对象的`description`属性。

```django
<p>{{ menu_item.description }}</p>
```

然后，添加来自`menu_item`对象的`price`属性。

```django
<p>Price: ${{ menu_item.price }}</p>
```

最后，添加代码以显示与菜单项名称一起存储的图片。

```django
<img src="/static/img/{{ menu_item.name }}.jpg" alt="{{ menu_item.name }}">
```

![](img/31db02f67b04488da4298707949d52e3_5.png)

在进行这些添加时，请确保所有更改都包含在段落标签`<p>`内。

## 测试页面功能
现在，保存`menu_item.html`文件，并确保所有其他文件的更改也已保存。

![](img/31db02f67b04488da4298707949d52e3_5.png)

接下来，添加命令以运行开发服务器。

```bash
python manage.py runserver
```

![](img/31db02f67b04488da4298707949d52e3_7.png)

将本地主机URL粘贴到浏览器中，并在末尾添加`/menu`文件路径。按回车键，之前显示的相同页面应该会加载，但这次菜单项名称显示为超链接。

![](img/31db02f67b04488da4298707949d52e3_8.png)

点击“Greek Salad”链接，希腊沙拉的菜单项页面就会出现。

![](img/31db02f67b04488da4298707949d52e3_7.png)
![](img/31db02f67b04488da4298707949d52e3_8.png)

请注意，此页面仅包含数据库中为希腊沙拉存储的信息，并显示其名称、描述、价格和图片。

## 总结
本节课中我们一起学习了如何创建动态的菜单项详情页面。我们首先更新了模型并执行了数据迁移，然后在管理后台填充了数据。接着，我们创建了视图函数来处理单个菜单项的请求，配置了URL路由，并设计了用于展示详情的模板。最后，我们成功测试了从列表页跳转到详情页的完整流程。现在，是时候进入项目的第三部分，开始创建网站的页脚了。