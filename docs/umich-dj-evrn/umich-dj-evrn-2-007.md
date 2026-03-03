# 007：Crispy表单实战演练 🎨

![](img/8c1e740bb129330042c5480311d819bc_1.png)

在本节课程中，我们将学习如何使用Crispy Forms库来美化Django应用中的表单。我们将看到，无需修改视图逻辑或表单定义，仅通过调整模板和配置，就能将默认的简单表单转换为具有现代样式的精美表单。

## 概述

Django内置的表单渲染功能可以自动生成HTML，但样式通常比较基础。Crispy Forms是一个第三方库，它允许我们使用流行的前端框架（如Bootstrap）的样式来渲染表单，从而显著提升表单的外观和用户体验，而无需手动编写大量HTML和CSS。

上一节我们介绍了Django内置的表单渲染方式，本节中我们来看看如何使用Crispy Forms库来替代它。

## 内置表单渲染与Crispy表单对比

在Django中，我们创建一个表单对象，并将其传递给模板。在模板中，我们可以使用类似 `{{ form.as_table }}` 的语法来渲染表单。这会生成一个包含所有表单字段的HTML表格。

**代码示例（内置渲染）:**
```html
<table>
    {{ form.as_table }}
</table>
```

![](img/8c1e740bb129330042c5480311d819bc_3.png)

这种方法生成的HTML结构简单，但缺乏现代、美观的样式。

![](img/8c1e740bb129330042c5480311d819bc_5.png)

Crispy Forms库则提供了另一种渲染方式。它接收相同的表单对象，但输出的是应用了Bootstrap样式的、更美观的HTML代码。表单会拥有圆角边框、高亮效果、清晰的标签和必填字段标识（星号）。

![](img/8c1e740bb129330042c5480311d819bc_6.png)

**代码示例（Crispy渲染）:**
```html
{% load crispy_forms_tags %}
{% crispy form %}
```

关键点在于，我们**没有改变**视图（`views.py`）中创建和传递表单对象的逻辑，也没有改变表单类（`forms.py`）本身的定义。我们仅仅改变了模板中渲染这个对象的方式。

## 配置Crispy Forms

要使Crispy Forms正常工作，需要进行一些安装和配置。以下是必要的步骤：

首先，需要在Python虚拟环境中安装Crispy Forms及其Bootstrap适配器。

**安装命令:**
```bash
pip install django-crispy-forms
pip install crispy-bootstrap5
```

接下来，需要在Django项目的设置文件 `settings.py` 中进行配置。

**配置 `settings.py`:**
1.  将 `crispy_forms` 和 `crispy_bootstrap5` 添加到 `INSTALLED_APPS` 列表中。
2.  设置 `CRISPY_ALLOWED_TEMPLATE_PACKS` 和 `CRISPY_TEMPLATE_PACK` 变量，指定使用Bootstrap 5。

![](img/8c1e740bb129330042c5480311d819bc_8.png)

![](img/8c1e740bb129330042c5480311d819bc_10.png)

**代码示例:**
```python
# settings.py
INSTALLED_APPS = [
    ...
    'crispy_forms',
    'crispy_bootstrap5',
    ...
]

CRISPY_ALLOWED_TEMPLATE_PACKS = "bootstrap5"
CRISPY_TEMPLATE_PACK = "bootstrap5"
```

![](img/8c1e740bb129330042c5480311d819bc_12.png)

## 在模板中使用Crispy Forms

配置完成后，在模板中使用Crispy Forms非常简单。主要涉及两个模板标签。

以下是使用Crispy Forms渲染表单的模板示例：

![](img/8c1e740bb129330042c5480311d819bc_14.png)

**代码示例:**
```html
<!-- awesome_template.html -->
{% load crispy_forms_tags %}
<!DOCTYPE html>
<html>
<head>
    <title>Awesome Form</title>
    <!-- 确保引入了Bootstrap的CSS -->
    <link href="path/to/bootstrap.css" rel="stylesheet">
</head>
<body>
    <form method="post">
        {% csrf_token %}
        <!-- 核心变化：使用crispy过滤器渲染表单 -->
        {% crispy form %}
        <!-- 提交按钮通常也会被crispy样式化 -->
        <input type="submit" value="Submit">
    </form>
</body>
</html>
```

![](img/8c1e740bb129330042c5480311d819bc_16.png)

**代码解释:**
1.  `{% load crispy_forms_tags %}`：这行代码必须放在模板顶部，它加载了Crispy Forms的模板标签库，使其提供的 `crispy` 过滤器可用。
2.  `{% crispy form %}`：这是核心步骤。`form` 是视图传递过来的表单对象。`|` 是过滤器管道符，`crispy` 是过滤器名称。这行代码将表单对象交给Crispy Forms库进行渲染，生成带有Bootstrap样式的HTML。

![](img/8c1e740bb129330042c5480311d819bc_18.png)

## 核心优势：面向对象设计的灵活性

![](img/8c1e740bb129330042c5480311d819bc_20.png)

![](img/8c1e740bb129330042c5480311d819bc_21.png)

![](img/8c1e740bb129330042c5480311d819bc_22.png)

这个练习展示了Django面向对象设计的一个强大优势。表单被定义为一个明确的对象（继承自 `forms.Form`）。视图负责处理这个对象的逻辑，而模板负责决定如何“显示”这个对象。

Django内置了 `as_table`、`as_p` 等方法来完成显示工作。Crispy Forms库则提供了一个替代的“显示器”。由于表单对象的结构是标准的，我们可以轻松地切换不同的渲染方式，而无需重写业务逻辑。这体现了“关注点分离”的原则，也是使用框架和库来提高开发效率的典范。

![](img/8c1e740bb129330042c5480311d819bc_24.png)

## 总结

![](img/8c1e740bb129330042c5480311d819bc_25.png)

![](img/8c1e740bb129330042c5480311d819bc_26.png)

![](img/8c1e740bb129330042c5480311d819bc_27.png)

![](img/8c1e740bb129330042c5480311d819bc_29.png)

本节课中我们一起学习了如何使用Crispy Forms库来美化Django表单。我们了解到，只需安装库、更新配置，并在模板中使用 `{% crispy form %}` 过滤器，就能将普通的表单转换为具有专业Bootstrap样式的精美表单。整个过程无需改动视图和表单模型的核心代码，充分体现了Django框架的灵活性和可扩展性。通过利用像Crispy Forms这样的优秀第三方库，我们可以更专注于应用的功能开发，同时轻松获得良好的用户界面。