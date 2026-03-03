# 045：搜索功能与视图配置模式实战

![](img/c5006f2674aa806614f90e6a73a1b8ef_0.png)

![](img/c5006f2674aa806614f90e6a73a1b8ef_2.png)

在本节课中，我们将学习如何为Django应用添加搜索功能，并探索一种直接在URL配置文件中定义视图的新模式。我们将通过分析一个名为“Well”的示例应用来理解这些概念。

## 概述

“Well”应用是之前“My Arts”应用的一个变体，核心区别在于它增加了一个搜索框。用户可以通过搜索框查找包含特定关键词的文章。本节课将重点解析如何实现基于GET请求的搜索功能，以及如何通过`urls.py`文件更简洁地配置通用视图。

## 搜索功能的实现原理

上一节我们介绍了CRUD操作，本节中我们来看看如何实现一个不刷新页面的搜索功能。其核心在于使用GET请求来传递搜索参数。

当用户在搜索框中输入内容并提交时，表单会发起一个GET请求（因为表单没有指定`method="post"`）。搜索关键词会作为查询参数附加在URL之后，例如：`/well?search=yada`。

![](img/c5006f2674aa806614f90e6a73a1b8ef_4.png)

![](img/c5006f2674aa806614f90e6a73a1b8ef_5.png)

这种设计使得搜索结果是**幂等**的。这意味着相同的搜索URL总会返回符合该搜索条件的逻辑结果（即使底层数据发生了变化），并且这个URL可以被收藏或分享。

### 视图中的搜索逻辑

在`PostListView`中，我们需要处理带有和不带有搜索参数的GET请求。

![](img/c5006f2674aa806614f90e6a73a1b8ef_7.png)

以下是处理搜索的核心代码逻辑：

```python
def get(self, request):
    # 从GET请求中获取名为‘search’的参数，如果不存在则返回False
    search = request.GET.get('search', False)
    if search:
        # 如果存在搜索词，则构建一个查询集，查找标题或正文中包含该词的文章
        from django.db.models import Q
        query = Q(title__contains=search) | Q(text__contains=search)
        objects = Post.objects.filter(query).select_related('owner').order_by('-updated_at')[:10]
    else:
        # 如果没有搜索词，则获取全部文章
        objects = Post.objects.all().select_related('owner').order_by('-updated_at')[:10]

    # 对文章列表进行后续处理（如格式化时间）
    for obj in objects:
        obj.natural_updated = naturaltime(obj.updated_at)

    context = {'post_list': objects, 'search': search}
    return render(request, self.template_name, context)
```

**代码解释**：
1.  `request.GET.get('search', False)` 用于安全地获取URL中的查询参数。
2.  当`search`参数存在时，我们使用Django的`Q`对象来构建一个复杂的查询条件，它允许我们使用逻辑或（`|`）来组合多个过滤条件（例如：标题包含关键词 **或** 正文包含关键词）。
3.  `select_related('owner')` 是一个性能优化方法，它会在查询文章的同时，通过单次SQL查询获取关联的`owner`（用户）信息，避免后续逐个访问时产生额外的数据库查询（即“N+1查询问题”）。
4.  `naturaltime` 是一个方便的模板过滤器，用于将日期时间转换为“3小时前”这样的友好格式。

### 模板中的搜索表单

在列表页的模板中，我们需要一个表单来发起搜索请求，并显示当前的搜索词。

以下是模板中搜索表单部分的关键代码：

```html
<form>
    <input type="text" name="search" placeholder="Search term..." value="{{ search|default_if_none:'' }}">
    <button type="submit"><i class="fas fa-search"></i></button>
    {% if search %}
        <a href="{% url 'well:all' %}"><i class="fas fa-undo"></i></a>
    {% endif %}
</form>
```

**代码解释**：
1.  表单默认使用GET方法提交，目标URL是当前页面。
2.  `value="{{ search|default_if_none:'' }}"` 确保在提交搜索后，搜索框内会回显刚才输入的关键词。
3.  如果当前处于搜索状态（`search`变量为真），则会显示一个撤销图标（🔙），点击后会跳转回没有搜索参数的列表页URL。

## 在URL配置中定义视图的新模式

之前，我们通常在`views.py`中为每个功能创建视图类。对于简单的增删改查视图，有一种更简洁的模式：直接在项目的`urls.py`中配置Django的通用视图。

以下是`urls.py`中直接配置通用视图的示例：

```python
from django.urls import path
from myarts.owner import OwnerListView, OwnerDetailView, OwnerCreateView, OwnerUpdateView, OwnerDeleteView
from . import models

app_name = 'well'

urlpatterns = [
    path('', PostListView.as_view(), name='all'), # 自定义的列表视图，包含搜索
    path('post/<int:pk>', OwnerDetailView.as_view(model=models.Post, template_name='well/detail.html'), name='post_detail'),
    path('post/create', OwnerCreateView.as_view(model=models.Post, template_name='well/form.html', fields=['title', 'text'], success_url=reverse_lazy('well:all')), name='post_create'),
    path('post/<int:pk>/update', OwnerUpdateView.as_view(model=models.Post, template_name='well/form.html', fields=['title', 'text'], success_url=reverse_lazy('well:all')), name='post_update'),
    path('post/<int:pk>/delete', OwnerDeleteView.as_view(model=models.Post, template_name='well/delete.html', success_url=reverse_lazy('well:all')), name='post_delete'),
]
```

**模式优点**：
1.  **减少代码文件**：无需在`views.py`中为简单的CRUD操作编写几乎相同的视图类。
2.  **集中配置**：URL模式与视图的关键参数（如关联的模型、使用的模板、表单字段、成功后的跳转地址）定义在同一个地方，一目了然。
3.  **易于维护**：当需要重命名应用或调整基础行为时，修改点更集中。这里通过`app_name`变量和字符串拼接（如`‘well/detail.html’`）来管理模板路径，使得应用更易于复用。

**注意事项**：
这种模式适用于直接使用通用视图且无需额外自定义逻辑的场景。对于像`PostListView`这样需要复杂自定义逻辑（如搜索）的视图，仍然需要在`views.py`中编写自定义类。

## 总结

本节课中我们一起学习了两个核心内容：
1.  **实现搜索功能**：我们了解了如何通过GET请求和查询参数实现幂等的搜索，如何在视图中使用`Q`对象进行复杂查询，以及如何在模板中渲染搜索表单和状态。
2.  **视图配置新模式**：我们探索了一种直接在`urls.py`中配置通用视图类（如`OwnerCreateView`）的高效模式，这可以简化标准CRUD操作的代码结构，使项目更加清晰。

![](img/c5006f2674aa806614f90e6a73a1b8ef_9.png)

![](img/c5006f2674aa806614f90e6a73a1b8ef_11.png)

通过“Well”这个示例，你将掌握如何为你的Django应用添加实用的搜索特性，并学会根据场景选择最简洁的视图定义方式。