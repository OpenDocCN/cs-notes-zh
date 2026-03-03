# Django for Everybody： 4.1： Autos示例项目详解 🚗

![](img/607c0b39ee9e4dd20c9c2c60affe5347_1.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_3.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_4.png)

在本节课中，我们将详细解析一个名为“Autos”的Django示例项目。这是一个完整的CRUD（创建、读取、更新、删除）应用，我们将通过分析其代码结构来学习Django的核心概念，包括模型、表单、视图、URL配置以及如何使用Django的通用视图来简化开发。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_6.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_8.png)

## 项目概述与运行

首先，让我们了解一下这个Autos项目。这是一个管理汽车品牌（Make）和具体汽车（Auto）信息的应用。它演示了如何建立一对多的关系（一个品牌对应多辆汽车），并实现了完整的增删改查功能，所有操作都受到登录保护。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_10.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_12.png)

运行项目后，访问`/autos`路径，系统会要求你先登录。登录成功后，你可以看到主界面，可以添加品牌、查看品牌列表、添加汽车等。汽车添加表单中有一个下拉菜单，其选项来自品牌表，这正是一对多关系的体现。在列表中，你可以对每条记录进行更新或删除操作。

## 核心文件结构

![](img/607c0b39ee9e4dd20c9c2c60affe5347_14.png)

为了理解这个应用，我们需要分析四个核心文件：`models.py`、`forms.py`、`urls.py`和`views.py`。接下来，我们将逐一进行解析。

### 1. 数据模型 (models.py)

模型文件定义了应用的数据结构。我们有两个模型：`Make`（品牌）和`Auto`（汽车）。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_16.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_18.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_20.png)

**Make模型**非常简单，只有一个`name`字段，并使用了验证器确保名称至少有两个字符。`__str__`方法定义了当打印模型对象时显示的内容。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_22.png)

```python
from django.core.validators import MinLengthValidator
from django.db import models

![](img/607c0b39ee9e4dd20c9c2c60affe5347_24.png)

class Make(models.Model):
    name = models.CharField(
            max_length=200,
            help_text='Enter a make (e.g. Dodge)',
            validators=[MinLengthValidator(2, "Make must be greater than 1 character")]
    )

    def __str__(self):
        return self.name
```

**Auto模型**包含更多字段：昵称、里程、评论，以及一个指向`Make`模型的**外键**（`ForeignKey`）。`on_delete=models.CASCADE`参数意味着当删除一个品牌时，与之关联的所有汽车记录也会被自动删除。

```python
class Auto(models.Model):
    nickname = models.CharField(
            max_length=200,
            validators=[MinLengthValidator(2, "Nickname must be greater than 1 character")]
    )
    mileage = models.PositiveIntegerField()
    comments = models.CharField(max_length=300)
    make = models.ForeignKey('Make', on_delete=models.CASCADE, null=False)

    def __str__(self):
        return self.nickname
```

### 2. 表单 (forms.py)

表单用于在网页上生成输入界面并处理用户提交的数据。这里我们使用了`ModelForm`，它能根据模型自动生成表单字段，极大地简化了代码。

以下是为`Make`模型创建的`ModelForm`。`Meta`类中指定了数据来源的模型和需要包含的字段（这里使用`__all__`表示包含所有字段）。

```python
from django.forms import ModelForm
from .models import Make

class MakeForm(ModelForm):
    class Meta:
        model = Make
        fields = '__all__'
```

![](img/607c0b39ee9e4dd20c9c2c60affe5347_26.png)

### 3. URL路由 (urls.py)

URL配置文件将不同的网址路径映射到对应的视图函数。Autos应用的URL模式清晰地组织了CRUD操作的路由。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_28.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_29.png)

以下是主要的URL模式：
*   `autos/`：列出所有汽车（主视图）。
*   `make/`：列出所有品牌。
*   `make/create/`：创建新品牌。
*   `make/<int:pk>/update/`：更新指定主键（pk）的品牌。
*   `make/<int:pk>/delete/`：删除指定主键的品牌。
*   类似的，还有`auto/create/`， `auto/<int:pk>/update/`， `auto/<int:pk>/delete/`用于汽车的CRUD操作。

每个路径都通过`name`参数被赋予了易于引用的名称。

```python
from django.urls import path
from . import views

![](img/607c0b39ee9e4dd20c9c2c60affe5347_31.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_32.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_34.png)

urlpatterns = [
    path('', views.MainView.as_view(), name='all'),
    path('main/create/', views.AutoCreate.as_view(), name='auto_create'),
    path('main/<int:pk>/update/', views.AutoUpdate.as_view(), name='auto_update'),
    path('main/<int:pk>/delete/', views.AutoDelete.as_view(), name='auto_delete'),
    path('lookup/', views.MakeView.as_view(), name='make_list'),
    path('lookup/create/', views.MakeCreate.as_view(), name='make_create'),
    path('lookup/<int:pk>/update/', views.MakeUpdate.as_view(), name='make_update'),
    path('lookup/<int:pk>/delete/', views.MakeDelete.as_view(), name='make_delete'),
]
```

![](img/607c0b39ee9e4dd20c9c2c60affe5347_36.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_38.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_40.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_41.png)

### 4. 视图逻辑 (views.py) - 基础方式

视图是处理业务逻辑的核心。我们将先看看如何“手动”编写视图来实现CRUD，然后再介绍Django提供的更简洁的“通用视图”。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_43.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_44.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_46.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_48.png)

上一节我们介绍了模型和URL，本节中我们来看看视图如何运作。所有需要登录才能访问的视图都通过`LoginRequiredMixin`进行保护。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_50.png)

**列表视图**：以`MainView`（汽车列表）和`MakeView`（品牌列表）为例。它们从数据库中获取所有对象，传递给模板进行渲染。`get_context_data`方法用于向模板传递额外的上下文数据，比如品牌数量。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_52.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_54.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_56.png)

```python
from django.views import View
from django.shortcuts import render, redirect, get_object_or_404
from django.contrib.auth.mixins import LoginRequiredMixin
from .models import Auto, Make
from .forms import MakeForm

![](img/607c0b39ee9e4dd20c9c2c60affe5347_57.png)

class MainView(LoginRequiredMixin, View):
    def get(self, request):
        make_count = Make.objects.all().count()
        auto_list = Auto.objects.all()
        ctx = {'make_count': make_count, 'auto_list': auto_list}
        return render(request, 'autos/auto_list.html', ctx)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_59.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_61.png)

class MakeView(LoginRequiredMixin, View):
    def get(self, request):
        make_list = Make.objects.all()
        ctx = {'make_list': make_list}
        return render(request, 'autos/make_list.html', ctx)
```

![](img/607c0b39ee9e4dd20c9c2c60affe5347_63.png)

**创建视图**：以`MakeCreate`为例。`GET`请求时，它提供一个空表单；`POST`请求时，它验证表单数据，如果有效则保存到数据库，并重定向到成功页面。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_65.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_66.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_68.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_70.png)

```python
class MakeCreate(LoginRequiredMixin, View):
    template = 'autos/make_form.html'
    success_url = reverse_lazy('autos:all')

    def get(self, request):
        form = MakeForm()
        ctx = {'form': form}
        return render(request, self.template, ctx)

    def post(self, request):
        form = MakeForm(request.POST)
        if not form.is_valid():
            ctx = {'form': form}
            return render(request, self.template, ctx)
        form.save()
        return redirect(self.success_url)
```

**更新视图**：与创建视图类似，但需要先通过主键获取要更新的现有对象。`get_object_or_404`是一个便捷函数：如果对象存在则返回，不存在则直接返回404错误页面。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_72.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_74.png)

```python
class MakeUpdate(LoginRequiredMixin, View):
    model = Make
    success_url = reverse_lazy('autos:all')
    template = 'autos/make_form.html'

    def get(self, request, pk):
        make = get_object_or_404(self.model, pk=pk)
        form = MakeForm(instance=make)
        ctx = {'form': form}
        return render(request, self.template, ctx)

    def post(self, request, pk):
        make = get_object_or_404(self.model, pk=pk)
        form = MakeForm(request.POST, instance=make)
        if not form.is_valid():
            ctx = {'form': form}
            return render(request, self.template, ctx)
        form.save()
        return redirect(self.success_url)
```

![](img/607c0b39ee9e4dd20c9c2c60affe5347_76.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_78.png)

**删除视图**：`GET`请求显示确认删除页面，`POST`请求执行删除操作。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_80.png)

```python
class MakeDelete(LoginRequiredMixin, View):
    model = Make
    success_url = reverse_lazy('autos:all')
    template = 'autos/make_confirm_delete.html'

    def get(self, request, pk):
        make = get_object_or_404(self.model, pk=pk)
        ctx = {'make': make}
        return render(request, self.template, ctx)

    def post(self, request, pk):
        make = get_object_or_404(self.model, pk=pk)
        make.delete()
        return redirect(self.success_url)
```

![](img/607c0b39ee9e4dd20c9c2c60affe5347_82.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_83.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_85.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_87.png)

## 使用Django通用视图进行简化 ✨

上面展示的视图虽然功能完整，但代码中存在大量重复模式。Django提供了基于类的通用视图（Generic Class-Based Views）来封装这些通用模式，让代码变得极其简洁。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_89.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_91.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_93.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_95.png)

以下是使用通用视图重写的`Auto`模型的CRUD操作：

![](img/607c0b39ee9e4dd20c9c2c60affe5347_97.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_99.png)

```python
from django.views.generic.edit import CreateView, UpdateView, DeleteView
from django.urls import reverse_lazy
from .models import Auto

![](img/607c0b39ee9e4dd20c9c2c60affe5347_101.png)

class AutoCreate(LoginRequiredMixin, CreateView):
    model = Auto
    fields = '__all__'
    success_url = reverse_lazy('autos:all')

![](img/607c0b39ee9e4dd20c9c2c60affe5347_103.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_105.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_107.png)

class AutoUpdate(LoginRequiredMixin, UpdateView):
    model = Auto
    fields = '__all__'
    success_url = reverse_lazy('autos:all')

![](img/607c0b39ee9e4dd20c9c2c60affe5347_109.png)

class AutoDelete(LoginRequiredMixin, DeleteView):
    model = Auto
    fields = '__all__'
    success_url = reverse_lazy('autos:all')
```

![](img/607c0b39ee9e4dd20c9c2c60affe5347_111.png)

**代码解析**：
*   `CreateView`、`UpdateView`、`DeleteView`分别对应创建、更新和删除的通用视图。
*   只需指定`model`（操作哪个模型）、`fields`（使用哪些字段，`__all__`表示全部）和`success_url`（操作成功后跳转的地址）。
*   视图会自动处理`GET`和`POST`请求、表单生成、数据验证、对象获取（`get_object_or_404`）、保存和删除等所有逻辑。
*   它们还会根据模型名称自动寻找对应的模板（如`auto_form.html`， `auto_confirm_delete.html`），无需手动指定`template_name`。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_113.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_115.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_117.png)

通过对比可以发现，通用视图将数十行代码浓缩为寥寥几行，且更易于维护。对于`Make`模型的视图，也应该采用同样的方式进行简化，而不是复制冗长的手动代码。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_119.png)

## 模板与登录配置

![](img/607c0b39ee9e4dd20c9c2c60affe5347_121.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_123.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_125.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_127.png)

视图需要模板来呈现页面。通用视图有默认的模板命名约定，例如`<modelname>_form.html`。这些模板接收`form`或`object`等上下文变量。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_129.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_131.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_132.png)

关于登录，项目配置使用了Django内置的认证系统。关键步骤包括：
1.  在`settings.py`中启用`django.contrib.auth`应用。
2.  在项目根`urls.py`中包含认证相关的URL（如`path('accounts/', include('django.contrib.auth.urls'))`）。
3.  在模板目录（如`templates/registration/`）下创建名为`login.html`的登录模板。
4.  在需要登录的视图类中添加`LoginRequiredMixin`。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_134.png)

## 总结与作业建议 🎯

![](img/607c0b39ee9e4dd20c9c2c60affe5347_136.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_138.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_139.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_140.png)

本节课我们一起深入学习了Django的Autos示例项目。我们分析了如何构建一个完整的CRUD应用，涵盖了从模型定义、表单创建、URL配置到视图逻辑的完整流程。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_142.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_144.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_145.png)

核心收获包括：
1.  **模型（Model）**：使用`ForeignKey`建立表间关系，利用`validators`进行数据验证。
2.  **表单（Form）**：使用`ModelForm`快速生成与模型对应的表单。
3.  **视图（View）**：
    *   掌握了手动实现CRUD视图的方法，理解了`get_object_or_404`、表单验证和重定向等关键操作。
    *   **更重要的是**，学会了使用Django的**通用视图**（`CreateView`， `UpdateView`， `DeleteView`）来极大地简化代码，这是Django高效开发的精髓。
4.  **认证**：使用`LoginRequiredMixin`轻松实现视图的登录保护。

![](img/607c0b39ee9e4dd20c9c2c60affe5347_147.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_148.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_149.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_150.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_152.png)

![](img/607c0b39ee9e4dd20c9c2c60affe5347_153.png)

对于你的作业，强烈建议不要直接复制示例中冗长的“手动”视图代码（如`MakeCreate`， `MakeUpdate`）。相反，应该像`AutoCreate`等视图一样，采用基于通用视图的简洁写法。理解并运用这种模式，将使你后续的Django开发事半功倍。请花时间消化视图中的逻辑，特别是通用视图的工作原理，这将是未来所有Django项目的基础。