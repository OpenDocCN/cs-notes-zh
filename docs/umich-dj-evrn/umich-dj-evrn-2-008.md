# 008：我的文章（myarts）示例代码实战

![](img/be22e7f381c283e91cf00876c37f4d57_0.png)

![](img/be22e7f381c283e91cf00876c37f4d57_2.png)

![](img/be22e7f381c283e91cf00876c37f4d57_3.png)

在本教程中，我们将通过“我的文章”示例，深入探讨Django中“数据行所有权”的核心概念。我们将学习如何构建一个应用，让用户只能查看和编辑自己创建的文章。

![](img/be22e7f381c283e91cf00876c37f4d57_5.png)

![](img/be22e7f381c283e91cf00876c37f4d57_7.png)

![](img/be22e7f381c283e91cf00876c37f4d57_9.png)

## 概述

![](img/be22e7f381c283e91cf00876c37f4d57_10.png)

![](img/be22e7f381c283e91cf00876c37f4d57_12.png)

![](img/be22e7f381c283e91cf00876c37f4d57_13.png)

![](img/be22e7f381c283e91cf00876c37f4d57_15.png)

“我的文章”示例的核心是“数据行所有权”。这意味着数据库中的每一行数据（例如一篇文章）都归属于一个特定的用户。我们将学习如何：
1.  在模型中建立用户与数据行之间的关联。
2.  在视图和模板中，根据当前登录用户来过滤和显示数据。
3.  保护数据，确保用户只能操作属于自己的内容。

![](img/be22e7f381c283e91cf00876c37f4d57_16.png)

![](img/be22e7f381c283e91cf00876c37f4d57_17.png)

![](img/be22e7f381c283e91cf00876c37f4d57_19.png)

![](img/be22e7f381c283e91cf00876c37f4d57_21.png)

![](img/be22e7f381c283e91cf00876c37f4d57_22.png)

![](img/be22e7f381c283e91cf00876c37f4d57_23.png)

## 模型与数据所有权

![](img/be22e7f381c283e91cf00876c37f4d57_25.png)

上一节我们介绍了核心概念，本节中我们来看看如何在实际的模型中实现数据所有权。

![](img/be22e7f381c283e91cf00876c37f4d57_27.png)

在Django中，我们使用**外键**来建立模型之间的关联。对于“我的文章”应用，我们需要在`Article`模型中添加一个指向Django内置`User`模型的外键字段，名为`owner`。

![](img/be22e7f381c283e91cf00876c37f4d57_29.png)

```python
# models.py
from django.db import models
from django.conf import settings

![](img/be22e7f381c283e91cf00876c37f4d57_31.png)

![](img/be22e7f381c283e91cf00876c37f4d57_33.png)

class Article(models.Model):
    title = models.CharField(max_length=200)
    text = models.TextField()
    owner = models.ForeignKey(settings.AUTH_USER_MODEL, on_delete=models.CASCADE)
    created_at = models.DateTimeField(auto_now_add=True)
    updated_at = models.DateTimeField(auto_now=True)
```

**关键点解析**：
*   `settings.AUTH_USER_MODEL`：这是一个字符串，指向项目中使用的用户模型。这比直接导入`User`模型更灵活。
*   `on_delete=models.CASCADE`：这表示如果关联的用户被删除，那么属于该用户的所有文章也会被自动删除。
*   `owner`字段的值是一个整数，对应`auth_user`表中用户的**主键**。

![](img/be22e7f381c283e91cf00876c37f4d57_35.png)

![](img/be22e7f381c283e91cf00876c37f4d57_36.png)

![](img/be22e7f381c283e91cf00876c37f4d57_37.png)

![](img/be22e7f381c283e91cf00876c37f4d57_38.png)

在数据库层面，`myarts_article`表中会有一个`owner_id`列，其值就是`auth_user`表中用户的ID。这样，我们就建立了文章与用户之间的归属关系。

![](img/be22e7f381c283e91cf00876c37f4d57_40.png)

![](img/be22e7f381c283e91cf00876c37f4d57_42.png)

![](img/be22e7f381c283e91cf00876c37f4d57_44.png)

## 视图与URL配置

![](img/be22e7f381c283e91cf00876c37f4d57_46.png)

![](img/be22e7f381c283e91cf00876c37f4d57_47.png)

![](img/be22e7f381c283e91cf00876c37f4d57_49.png)

理解了模型结构后，我们来看看如何通过视图来控制数据的访问。

视图的配置非常简洁，因为我们使用了可重用的“所有者视图”。以下是`urls.py`和`views.py`的关键部分：

```python
# urls.py
from django.urls import path
from . import views

urlpatterns = [
    path('', views.ArticleListView.as_view(), name='all'),
    path('article/<int:pk>', views.ArticleDetailView.as_view(), name='article_detail'),
    path('article/create', views.ArticleCreateView.as_view(success_url=reverse_lazy('myarts:all')), name='article_create'),
    path('article/<int:pk>/update', views.ArticleUpdateView.as_view(), name='article_update'),
    path('article/<int:pk>/delete', views.ArticleDeleteView.as_view(success_url=reverse_lazy('myarts:all')), name='article_delete'),
]
```

```python
# views.py
from django.views import generic
from .models import Article
from .owner import OwnerListView, OwnerDetailView, OwnerCreateView, OwnerUpdateView, OwnerDeleteView

![](img/be22e7f381c283e91cf00876c37f4d57_51.png)

class ArticleListView(OwnerListView):
    model = Article

![](img/be22e7f381c283e91cf00876c37f4d57_53.png)

class ArticleDetailView(OwnerDetailView):
    model = Article

class ArticleCreateView(OwnerCreateView):
    model = Article
    fields = ['title', 'text'] # 注意：这里不包含‘owner’字段

![](img/be22e7f381c283e91cf00876c37f4d57_55.png)

![](img/be22e7f381c283e91cf00876c37f4d57_57.png)

class ArticleUpdateView(OwnerUpdateView):
    model = Article
    fields = ['title', 'text'] # 注意：这里不包含‘owner’字段

![](img/be22e7f381c283e91cf00876c37f4d57_59.png)

![](img/be22e7f381c283e91cf00876c37f4d57_61.png)

![](img/be22e7f381c283e91cf00876c37f4d57_63.png)

class ArticleDeleteView(OwnerDeleteView):
    model = Article
```

![](img/be22e7f381c283e91cf00876c37f4d57_65.png)

**视图解析**：
*   我们的视图类（如`ArticleListView`）继承自自定义的`OwnerListView`等类，而不是Django原生的`generic.ListView`。
*   在`ArticleCreateView`和`ArticleUpdateView`中，`fields`列表**明确排除了`owner`字段**。这是因为我们不想让用户在表单中手动选择文章的所有者，这个值将由后台逻辑自动设置。
*   `success_url`参数可以在URL配置中指定，这使得视图代码更加简洁。

![](img/be22e7f381c283e91cf00876c37f4d57_67.png)

![](img/be22e7f381c283e91cf00876c37f4d57_68.png)

![](img/be22e7f381c283e91cf00876c37f4d57_69.png)

这种设计的美妙之处在于，所有关于“所有权”的复杂逻辑都被封装在了`owner.py`的基类视图中，我们的业务视图变得非常清晰和简单。

## 模板中的权限控制

在用户界面中，我们需要根据所有权来显示或隐藏编辑和删除按钮。这主要在列表模板中实现。

![](img/be22e7f381c283e91cf00876c37f4d57_71.png)

以下是模板中控制按钮显示的逻辑：

![](img/be22e7f381c283e91cf00876c37f4d57_73.png)

```html
<!-- article_list.html -->
{% for article in article_list %}
  <li>
    {{ article.title }}
    {% if article.owner == user %}
      (<a href="{% url 'myarts:article_update' article.id %}">Edit</a> |
      <a href="{% url 'myarts:article_delete' article.id %}">Delete</a>)
    {% endif %}
  </li>
{% endfor %}
```

**模板逻辑解析**：
*   `article.owner`：这是当前文章对象`owner`字段的值，即创建该文章的用户ID。
*   `user`：这是Django模板上下文自动提供的变量，代表当前登录的用户对象。
*   `{% if article.owner == user %}`：这个条件判断检查当前文章的所有者是否就是当前登录的用户。如果成立，则显示编辑和删除链接。

![](img/be22e7f381c283e91cf00876c37f4d57_75.png)

**重要提示**：这仅仅是**用户体验优化**，而非安全措施。恶意用户仍然可以通过猜测或构造URL（如`/article/4/update/`）来尝试访问不属于自己的内容。真正的安全保护必须在视图层实现，我们接下来就会看到。

![](img/be22e7f381c283e91cf00876c37f4d57_77.png)

## 核心：所有者视图（owner.py）

所有权的魔法都发生在自定义的`owner.py`文件中。这里定义了所有视图基类，它们处理了自动设置所有者和权限验证的核心逻辑。

![](img/be22e7f381c283e91cf00876c37f4d57_79.png)

![](img/be22e7f381c283e91cf00876c37f4d57_81.png)

### 创建视图（OwnerCreateView）

当用户创建新文章时，我们需要自动将当前登录用户设置为文章的所有者。

```python
# owner.py
from django.contrib.auth.mixins import LoginRequiredMixin
from django.views.generic import CreateView

![](img/be22e7f381c283e91cf00876c37f4d57_83.png)

![](img/be22e7f381c283e91cf00876c37f4d57_85.png)

![](img/be22e7f381c283e91cf00876c37f4d57_87.png)

class OwnerCreateView(LoginRequiredMixin, CreateView):
    def form_valid(self, form):
        # 在保存到数据库之前，临时将表单数据存入对象
        object = form.save(commit=False)
        # 将当前登录用户设置为对象的所有者
        object.owner = self.request.user
        # 现在将对象（包含owner信息）保存到数据库
        object.save()
        # 调用父类的form_valid方法完成后续操作（如重定向）
        return super().form_valid(form)
```

![](img/be22e7f381c283e91cf00876c37f4d57_89.png)

![](img/be22e7f381c283e91cf00876c37f4d57_91.png)

![](img/be22e7f381c283e91cf00876c37f4d57_93.png)

![](img/be22e7f381c283e91cf00876c37f4d57_94.png)

![](img/be22e7f381c283e91cf00876c37f4d57_96.png)

**代码解析**：
1.  `LoginRequiredMixin`：确保只有登录用户才能访问创建页面。
2.  `form_valid(self, form)`：这是一个在表单验证通过后、数据保存前被调用的方法。我们覆盖它来插入自定义逻辑。
3.  `form.save(commit=False)`：这行代码告诉Django：“根据表单数据创建一个模型对象，但先不要保存到数据库”。这样我们就获得了这个对象的一个临时实例。
4.  `object.owner = self.request.user`：将当前请求的用户（`self.request.user`）赋值给对象的`owner`属性。
5.  `object.save()`：现在，将包含了正确`owner`信息的对象保存到数据库。
6.  `super().form_valid(form)`：最后，调用父类（`CreateView`）的`form_valid`方法，它通常会处理重定向到成功页面等操作。

![](img/be22e7f381c283e91cf00876c37f4d57_98.png)

![](img/be22e7f381c283e91cf00876c37f4d57_100.png)

![](img/be22e7f381c283e91cf00876c37f4d57_102.png)

### 更新与删除视图（OwnerUpdateView, OwnerDeleteView）

![](img/be22e7f381c283e91cf00876c37f4d57_104.png)

![](img/be22e7f381c283e91cf00876c37f4d57_105.png)

对于更新和删除操作，核心保护机制是重写`get_queryset`方法，确保用户只能操作属于自己的数据。

![](img/be22e7f381c283e91cf00876c37f4d57_107.png)

![](img/be22e7f381c283e91cf00876c37f4d57_109.png)

```python
# owner.py
from django.views.generic import UpdateView, DeleteView

![](img/be22e7f381c283e91cf00876c37f4d57_111.png)

![](img/be22e7f381c283e91cf00876c37f4d57_112.png)

class OwnerUpdateView(LoginRequiredMixin, UpdateView):
    def get_queryset(self):
        # 首先获取默认的查询集（根据URL中的pk查找对象）
        qs = super().get_queryset()
        # 在此基础上，增加一个过滤器：只返回owner是当前用户的对象
        return qs.filter(owner=self.request.user)

class OwnerDeleteView(LoginRequiredMixin, DeleteView):
    def get_queryset(self):
        qs = super().get_queryset()
        return qs.filter(owner=self.request.user)
```

![](img/be22e7f381c283e91cf00876c37f4d57_114.png)

![](img/be22e7f381c283e91cf00876c37f4d57_115.png)

**代码解析**：
1.  `get_queryset(self)`：这个方法返回一个查询集（QuerySet），视图用它来查找要操作的对象。
2.  `super().get_queryset()`：调用父类方法，获得基础的查询集（例如，查找`id`为特定值的文章）。
3.  `.filter(owner=self.request.user)`：这是关键步骤。我们在基础查询上增加一个过滤条件，要求`owner`字段必须等于当前登录的用户。
4.  **安全效果**：如果用户尝试更新或删除一个不属于自己的文章（例如ID为4的文章属于用户2，而当前用户是用户1），那么经过过滤的查询集将找不到任何记录。Django会因此抛出一个`Http 404`（页面未找到）错误，从而阻止了未授权操作。这个检查在**加载数据**和**提交更新**时都会执行，提供了双重保护。

![](img/be22e7f381c283e91cf00876c37f4d57_117.png)

![](img/be22e7f381c283e91cf00876c37f4d57_119.png)

![](img/be22e7f381c283e91cf00876c37f4d57_121.png)

## 总结

![](img/be22e7f381c283e91cf00876c37f4d57_123.png)

![](img/be22e7f381c283e91cf00876c37f4d57_124.png)

本节课中我们一起学习了如何在Django中实现“数据行所有权”。我们通过以下步骤构建了一个安全的、用户专属的内容管理系统：

![](img/be22e7f381c283e91cf00876c37f4d57_126.png)

![](img/be22e7f381c283e91cf00876c37f4d57_127.png)

1.  **模型设计**：在`Article`模型中添加`owner`外键字段，关联到用户模型。
2.  **视图封装**：创建了可重用的`OwnerCreateView`、`OwnerUpdateView`和`OwnerDeleteView`等基类视图，将所有权逻辑（自动设置所有者、权限过滤）封装其中。
3.  **业务视图**：我们的业务视图（如`ArticleCreateView`）只需继承这些所有者视图并配置`model`和`fields`，代码非常简洁。
4.  **模板优化**：在模板中使用`{% if article.owner == user %}`来根据所有权显示或隐藏操作按钮，改善用户体验。
5.  **安全核心**：认识到模板中的隐藏仅是前端优化，真正的安全依赖于视图层`get_queryset`方法中的权限过滤，它确保了用户只能访问和修改属于自己的数据。

![](img/be22e7f381c283e91cf00876c37f4d57_129.png)

![](img/be22e7f381c283e91cf00876c37f4d57_131.png)

这种基于面向对象编程的封装模式非常强大且优雅。一旦编写好`owner.py`，你就可以在项目的任何需要所有权功能的模型中复用这些视图，只需让对应的视图类继承它们即可，极大地提高了代码的复用性和可维护性。