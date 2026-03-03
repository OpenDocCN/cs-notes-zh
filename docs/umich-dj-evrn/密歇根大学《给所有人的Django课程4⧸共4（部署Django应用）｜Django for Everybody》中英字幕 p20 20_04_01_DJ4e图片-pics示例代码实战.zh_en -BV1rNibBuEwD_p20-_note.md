# Django for Everybody：4：图片处理示例代码实战

在本节课中，我们将学习如何在Django应用中处理图片上传与展示。我们将通过一个CRUD（增删改查）应用示例，详细解析从模型定义、表单处理、视图逻辑到前端展示的完整流程。

![](img/a1805a9eacddcae358ce378cd48505b8_1.png)

![](img/a1805a9eacddcae358ce378cd48505b8_2.png)

## 概述

我们将构建一个允许用户上传、查看、编辑和删除图片的应用。核心在于理解如何将图片的二进制数据存入数据库，并在需要时正确地将其作为HTTP响应流返回给浏览器。这涉及到表单的`multipart/form-data`编码、文件大小验证、模型中的二进制字段处理以及通过视图动态提供图片内容。

---

## 模型定义：存储图片数据

![](img/a1805a9eacddcae358ce378cd48505b8_4.png)

上一节我们介绍了课程目标，本节中我们来看看数据是如何存储的。一切从模型开始，它定义了数据的结构。

在`models.py`中，我们定义了一个`Pic`模型，它包含几个关键字段来存储图片信息：

![](img/a1805a9eacddcae358ce378cd48505b8_6.png)

![](img/a1805a9eacddcae358ce378cd48505b8_7.png)

![](img/a1805a9eacddcae358ce378cd48505b8_8.png)

```python
from django.db import models
from owner.models import Owner

class Pic(models.Model):
    # 图片标题和描述
    title = models.CharField(max_length=200)
    text = models.TextField()
    # 存储图片二进制数据
    picture = models.BinaryField(null=True, blank=True, editable=False)
    # 存储图片的MIME类型，如‘image/png’
    content_type = models.CharField(max_length=256, null=True, blank=True, editable=False)
    # 记录所有者、创建和更新时间
    owner = models.ForeignKey(Owner, on_delete=models.CASCADE)
    created_at = models.DateTimeField(auto_now_add=True)
    updated_at = models.DateTimeField(auto_now=True)
```

**核心概念解释**：
*   **`BinaryField`**：用于在数据库中存储原始二进制数据（BLOB），这里用来存放图片文件的字节。
*   **`content_type`**：这是一个字符串字段，用于记录图片的MIME类型（例如 `image/jpeg`, `image/png`）。当浏览器请求图片时，我们必须通过HTTP响应头正确设置这个类型，浏览器才能正确渲染图片。

**注意**：`picture`和`content_type`字段被设置为`editable=False`，这意味着它们不会在Django默认的Admin后台表单中显示。我们通过自定义`Admin`类来排除它们，因为通过Admin界面直接更新二进制数据比较复杂。

```python
# admin.py
from django.contrib import admin
from .models import Pic

@admin.register(Pic)
class PicAdmin(admin.ModelAdmin):
    exclude = (‘picture‘, ‘content_type‘)
```

---

## 视图逻辑：处理请求与响应

模型定义了数据结构，接下来我们看看视图如何协调表单与模型，处理用户的请求。

我们主要使用基于类的视图，并利用之前创建的`Owner`混合类来自动处理对象的所有者权限。

### 列表与详情视图

以下是用于显示图片列表和详情的视图，它们相对标准：

```python
# views.py
from django.views.generic import ListView, DetailView
from owner.views import OwnerListView, OwnerDetailView
from .models import Pic

class PicListView(OwnerListView):
    model = Pic
    template_name = ‘pics/list.html‘

class PicDetailView(OwnerDetailView):
    model = Pic
    template_name = ‘pics/detail.html‘
```

`OwnerListView`和`OwnerDetailView`为我们处理了根据登录用户过滤列表和检查详情页权限的逻辑。

### 创建图片视图

创建视图（`PicCreateView`）是核心，它需要处理包含文件数据的POST请求。

```python
# views.py
from django.views.generic import CreateView
from django.shortcuts import render, redirect
from .forms import CreateForm

class PicCreateView(CreateView):
    template_name = ‘pics/form.html‘
    form_class = CreateForm

    def get(self, request, *args, **kwargs):
        # 处理GET请求，渲染空表单
        form = self.form_class()
        return render(request, self.template_name, {‘form‘: form})

    def post(self, request, *args, **kwargs):
        # 处理POST请求，表单数据包含在request.POST和request.FILES中
        form = self.form_class(request.POST, request.FILES or None)
        if not form.is_valid():
            # 如果表单验证失败，重新渲染表单并显示错误
            return render(request, self.template_name, {‘form‘: form})
        # 表单有效，进行保存
        pic = form.save(commit=False) # 先不提交到数据库
        pic.owner = self.request.user # 设置所有者
        pic.save() # 保存到数据库
        return redirect(‘pics:all‘) # 重定向到列表页
```

**关键点**：
*   当表单包含文件时，必须使用`enctype="multipart/form-data"`。
*   上传的文件数据不在`request.POST`中，而是在`request.FILES`字典里。
*   `form.save(commit=False)`返回一个尚未保存到数据库的模型实例，允许我们在最终保存前对其进行修改（如设置`owner`字段）。

### 提供图片流的视图

图片本身不是静态文件，而是从数据库读取并通过一个特定的视图动态提供。

```python
# views.py
from django.http import HttpResponse
from django.shortcuts import get_object_or_404
from .models import Pic

def stream_file(request, pk):
    # 根据主键获取图片对象
    pic = get_object_or_404(Pic, id=pk)
    # 构建HTTP响应，设置正确的Content-Type和Content-Length
    response = HttpResponse(pic.picture)
    response[‘Content-Type‘] = pic.content_type
    response[‘Content-Length‘] = len(pic.picture)
    return response
```

这个视图被映射到一个URL（例如`/pics/picture/<int:pk>`），在HTML中，图片标签的`src`属性就指向这个URL。

```html
<img src="{% url ‘pics:picture‘ pic.id %}" alt="{{ pic.title }}">
```

---

## 表单处理：验证与数据清洗

视图是控制器，而表单是连接用户输入（浏览器）和模型（数据库）的桥梁。本节我们深入看看表单如何工作。

表单类`CreateForm`继承自`ModelForm`，但我们需要自定义文件字段和验证逻辑。

```python
# forms.py
from django import forms
from django.core.exceptions import ValidationError
from .models import Pic

class CreateForm(forms.ModelForm):
    # 自定义文件上传字段
    picture = forms.FileField(
        label=‘Select an image to upload‘,
        help_text=‘Max file size: 2 MB‘
    )
    # 文件大小限制（字节）
    max_upload_limit = 2 * 1024 * 1024
    max_upload_limit_text = ‘2 MB‘

    class Meta:
        model = Pic
        fields = [‘title‘, ‘text‘, ‘picture‘] # 包含自定义的picture字段

    def clean(self):
        # 清洗数据，验证文件大小
        cleaned_data = super().clean()
        pic = cleaned_data.get(‘picture‘)
        if pic is None:
            return
        if len(pic) > self.max_upload_limit:
            # 如果文件太大，抛出一个验证错误
            raise ValidationError(f‘File must be < {self.max_upload_limit_text}‘)
        # 将文件数据和MIME类型暂存，供save方法使用
        self.cleaned_data[‘uploaded_file‘] = pic
        self.cleaned_data[‘content_type‘] = pic.content_type

    def save(self, commit=True):
        # 重写save方法，将文件二进制数据存入模型
        instance = super().save(commit=False) # 获取模型实例但不保存

        # 获取清洗阶段暂存的数据
        uploaded_file = self.cleaned_data.get(‘uploaded_file‘, None)
        content_type = self.cleaned_data.get(‘content_type‘, None)

        if uploaded_file is not None:
            # 将二进制数据和MIME类型赋值给模型字段
            instance.picture = uploaded_file.read()
            instance.content_type = content_type

        if commit:
            instance.save() # 如果commit为True，则保存到数据库
        return instance
```

**表单工作流程**：
1.  **初始化**：表单根据`Meta.fields`生成字段，包括自定义的`FileField`。
2.  **验证 (`clean`)**：用户提交后，首先调用父类的`clean`方法进行基础验证（如字段是否必填、长度限制）。然后我们自定义的`clean`方法检查文件大小，并将文件对象和MIME类型暂存到`cleaned_data`中。
3.  **保存 (`save`)**：当视图调用`form.save(commit=False)`时，我们重写的`save`方法会执行。它从`cleaned_data`中取出暂存的文件数据，将其读取为字节并赋值给模型实例的`picture`和`content_type`字段。

---

## 前端交互：表单与图片预览

数据在后端处理完毕，最后我们来看看用户直接交互的前端部分。

### 表单模板与客户端验证

以下是`form.html`模板的关键部分：

```html
<!-- form.html -->
<form method="post" enctype="multipart/form-data">
    {% csrf_token %}
    {{ form|crispy }}
    <button type="submit" class="btn btn-primary">Submit</button>
    <a href="{% url ‘pics:all‘ %}" class="btn btn-secondary">Cancel</a>
</form>

![](img/a1805a9eacddcae358ce378cd48505b8_10.png)

![](img/a1805a9eacddcae358ce378cd48505b8_12.png)

![](img/a1805a9eacddcae358ce378cd48505b8_14.png)

<script>
$(document).ready(function(){
    $(‘#upload-form‘).submit(function(event){
        // 客户端验证文件大小
        var fileInput = $(‘#id_picture‘)[0];
        if (fileInput.files.length > 0) {
            var fileSize = fileInput.files[0].size; // 文件大小，单位字节
            var maxSize = {{ form.max_upload_limit }}; // 从后端传递限制值
            if (fileSize > maxSize) {
                alert(`File must be smaller than {{ form.max_upload_limit_text }}`);
                event.preventDefault(); // 阻止表单提交
                return false;
            }
        }
    });
});
</script>
```

![](img/a1805a9eacddcae358ce378cd48505b8_16.png)

**关键点**：
*   **`enctype="multipart/form-data"`**：表单必须设置此属性才能正确上传文件。
*   **客户端验证**：使用JavaScript在文件上传前检查大小，提供即时反馈，提升用户体验。但**服务器端验证（`clean`方法中）是必须的**，因为客户端验证可以被绕过。

![](img/a1805a9eacddcae358ce378cd48505b8_18.png)

### 图片详情页与点击放大

![](img/a1805a9eacddcae358ce378cd48505b8_20.png)

![](img/a1805a9eacddcae358ce378cd48505b8_22.png)

在`detail.html`中，我们展示图片并实现一个简单的点击放大效果。

![](img/a1805a9eacddcae358ce378cd48505b8_24.png)

```html
<!-- detail.html -->
{% extends ‘base_bootstrap.html‘ %}

![](img/a1805a9eacddcae358ce378cd48505b8_25.png)

{% block content %}
<h1>{{ pic.title }}</h1>
<p>{{ pic.text }}</p>
<!-- 小图，可点击 -->
<img src="{% url ‘pics:picture‘ pic.id %}"
     style="max-width: 200px; float: right;"
     onclick="document.getElementById(‘overlay‘).style.display = ‘block‘"
     alt="{{ pic.title }}">

![](img/a1805a9eacddcae358ce378cd48505b8_27.png)

![](img/a1805a9eacddcae358ce378cd48505b8_29.png)

<!-- 全屏遮罩层，初始隐藏 -->
<div id="overlay" style="position: fixed; display: none; ..." onclick="this.style.display=‘none‘">
    <!-- 大图 -->
    <img src="{% url ‘pics:picture‘ pic.id %}" style="width: 90%; margin-top: 50px; border: 3px solid black;">
</div>
{% endblock %}
```

**实现原理**：
1.  页面上有一个缩略图，其`onclick`事件将`overlay`这个DIV的显示属性改为`block`，使其可见。
2.  `overlay`是一个覆盖全屏的固定定位层，背景是半透明灰色，里面包含一张大图。
3.  给`overlay`层本身也设置`onclick`事件，点击任何位置（包括图片和背景）就将其隐藏（`display: ‘none‘`）。

![](img/a1805a9eacddcae358ce378cd48505b8_31.png)

这是一种利用CSS和少量JavaScript实现模态框效果的简单方法。

![](img/a1805a9eacddcae358ce378cd48505b8_33.png)

---

![](img/a1805a9eacddcae358ce378cd48505b8_35.png)

![](img/a1805a9eacddcae358ce378cd48505b8_37.png)

## 总结

![](img/a1805a9eacddcae358ce378cd48505b8_39.png)

![](img/a1805a9eacddcae358ce378cd48505b8_40.png)

![](img/a1805a9eacddcae358ce378cd48505b8_41.png)

本节课中我们一起学习了在Django应用中集成图片处理功能的完整流程。我们回顾一下关键步骤：

![](img/a1805a9eacddcae358ce378cd48505b8_43.png)

1.  **模型层**：使用`BinaryField`存储图片二进制数据，并用`CharField`记录对应的`content_type`。
2.  **表单层**：创建自定义`ModelForm`，重写`clean()`方法进行服务器端文件验证，并重写`save()`方法将文件数据正确存入模型实例。
3.  **视图层**：
    *   使用基于类的视图处理CRUD操作，注意处理`request.FILES`。
    *   编写一个专门的视图（`stream_file`）从数据库读取二进制数据并设置为HTTP响应，**必须正确设置`Content-Type`响应头**。
4.  **前端层**：
    *   表单必须设置`enctype="multipart/form-data"`。
    *   可以添加JavaScript进行客户端文件大小验证以提升体验。
    *   利用CSS和JavaScript实现简单的图片点击放大预览功能。

![](img/a1805a9eacddcae358ce378cd48505b8_45.png)

![](img/a1805a9eacddcae358ce378cd48505b8_47.png)

通过这个示例，你将掌握在Django中处理文件上传的核心模式，并可将其应用于其他类型的文件处理场景。