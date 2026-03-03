# 021：论坛（Forums）示例代码实战 🧑‍💻

![](img/cdeb6312c6e58fb659b31ff94575e1ce_1.png)

在本节课中，我们将一起学习并分析一个Django论坛应用的示例代码。这个示例的核心是演示如何使用“多对多”关系，并再次实践“所有者”模式。我们将从模型设计开始，逐步深入到视图、模板和表单的处理逻辑，理解如何构建一个允许用户创建论坛帖子并发表评论的系统。

## 概述

![](img/cdeb6312c6e58fb659b31ff94575e1ce_3.png)

我们将要分析的代码实现了一个简单的论坛功能。主要特性包括：
*   用户可以创建、编辑、删除自己的论坛帖子。
*   所有用户（包括未登录用户）可以查看帖子及其评论。
*   登录用户可以对任何帖子发表评论。
*   用户只能删除自己发表的评论。
*   通过“所有者”模式控制编辑和删除权限。

这个应用涉及三个核心模型：`User`（Django内置）、`Forum`（论坛帖子）和`Comment`（评论）。`Forum`和`Comment`都与`User`模型存在“一对多”关系，而`Forum`和`User`之间通过`Comment`模型构成了一个“多对多”关系。

## 模型设计：理解数据关系

上一节我们概述了应用的功能，本节中我们来看看支撑这些功能的数据模型是如何设计的。理解模型之间的关系是理解整个应用逻辑的基础。

核心模型定义在 `models.py` 文件中，主要有两个：`Forum` 和 `Comment`。

**1. Forum 模型**
`Forum` 模型代表一个论坛帖子。除了“多对多”字段，它的结构与我们之前构建的CRUD应用非常相似。

![](img/cdeb6312c6e58fb659b31ff94575e1ce_5.png)

```python
class Forum(models.Model):
    title = models.CharField(max_length=200)
    text = models.TextField()
    owner = models.ForeignKey(settings.AUTH_USER_MODEL, on_delete=models.CASCADE)
    created_at = models.DateTimeField(auto_now_add=True)
    updated_at = models.DateTimeField(auto_now=True)
    comments = models.ManyToManyField(settings.AUTH_USER_MODEL,
        through='Comment', related_name='forum_comments')
```
*   `owner` 字段是一个指向 `User` 模型的外键，建立了“一个用户拥有多个论坛帖子”的“一对多”关系。
*   `comments` 字段是一个 `ManyToManyField`，它通过 `Comment` 模型与 `User` 模型关联。`related_name='forum_comments'` 非常重要，它会在 `User` 模型实例上创建一个名为 `forum_comments` 的反向查询管理器，用于获取该用户的所有评论。即使我们不立即使用它，明确命名也可以避免未来可能出现的名称冲突。

**2. Comment 模型**
`Comment` 模型作为连接表（或称为联结表、关联表），它存储了具体的评论内容，并包含两个外键。

```python
class Comment(models.Model):
    text = models.TextField()
    forum = models.ForeignKey(Forum, on_delete=models.CASCADE)
    owner = models.ForeignKey(settings.AUTH_USER_MODEL, on_delete=models.CASCADE)
    updated_at = models.DateTimeField(auto_now=True)
```
*   `forum` 和 `owner` 是两个外键，分别指向 `Forum` 和 `User` 模型。
*   `text` 字段存储评论内容。我们将评论数据直接建模在这个连接模型中，这是一种常见且便捷的做法。

**数据关系图解**
这三个模型的关系可以可视化如下：
```
User 表 (1) --<拥有>-- (多) Comment 表 (多) --<属于>-- (1) Forum 表
```
*   一个 `User` 可以拥有多个 `Forum`（通过 `Forum.owner`）。
*   一个 `User` 可以拥有多个 `Comment`（通过 `Comment.owner`）。
*   一个 `Forum` 可以拥有多个 `Comment`（通过 `Comment.forum`）。
*   因此，`Forum` 和 `User` 通过 `Comment` 表形成了“多对多”的关系：一个论坛可以有多个用户（通过他们的评论），一个用户也可以参与多个论坛（通过发表评论）。

## 视图逻辑：处理请求与响应

理解了数据模型后，我们来看看视图（`views.py`）如何操作这些模型来处理用户请求。大部分视图基于我们之前熟悉的CRUD模式构建，但论坛详情页和评论创建视图有一些值得关注的细节。

以下是几个关键视图的解析：

**1. ForumDetailView（论坛详情视图）**
这个视图负责显示一个特定的论坛帖子及其所有评论。它继承自 `OwnerDetailView`。

```python
class ForumDetailView(OwnerDetailView):
    model = Forum
    template_name = "forums/forum_detail.html"

    def get(self, request, pk):
        forum = get_object_or_404(Forum, id=pk)
        comments = Comment.objects.filter(forum=forum).order_by('-updated_at')
        comment_form = CommentForm()
        context = { 'forum': forum, 'comments': comments, 'comment_form': comment_form }
        return render(request, self.template_name, context)
```
*   它通过 `pk`（主键）获取对应的 `Forum` 对象。
*   然后，它过滤出所有 `forum` 字段等于当前论坛对象的 `Comment` 对象，并按更新时间倒序排列。
*   同时，它创建了一个空的 `CommentForm` 实例，用于在页面上渲染评论输入框。
*   最后，它将论坛对象、评论列表和评论表单一起传递给模板进行渲染。

**2. comment_create_view（评论创建视图）**
当用户在详情页提交评论表单时，会触发这个视图。

```python
@login_required
def comment_create_view(request, pk):
    forum = get_object_or_404(Forum, id=pk)
    if request.method == 'POST':
        comment = Comment(text=request.POST['comment'], owner=request.user, forum=forum)
        comment.save()
        return redirect(reverse('forums:forum_detail', args=[pk]))
```
*   它首先通过 `pk` 获取要评论的 `Forum` 对象。
*   在 `POST` 请求中，它创建一个新的 `Comment` 对象。**关键步骤在于同时为这个评论对象设置两个外键**：`owner=request.user`（当前登录用户）和 `forum=forum`（当前论坛帖子）。
*   调用 `comment.save()` 将这个包含关联关系的评论对象存入数据库。
*   最后，它重定向回论坛详情页（`forums:forum_detail`），并使用 `args=[pk]` 传递论坛的主键，以显示刚添加的评论。这是一个典型的“Post-Redirect-Get”模式，避免了重复提交。

**3. CommentDeleteView（评论删除视图）**
这个视图处理评论的删除，它继承自 `OwnerDeleteView`。

```python
class CommentDeleteView(OwnerDeleteView):
    model = Comment
    template_name = "forums/comment_delete.html"

    def get_success_url(self):
        forum_id = self.object.forum.id
        return reverse('forums:forum_detail', kwargs={'pk': forum_id})
```
*   大部分删除逻辑（如权限检查、确认页面渲染）都由父类 `OwnerDeleteView` 处理。
*   我们需要重写 `get_success_url` 方法。因为删除评论后，我们不应该停留在评论页面，而应该返回到该评论所属的论坛详情页。
*   `self.object` 指向当前正在被删除的 `Comment` 对象（即使在数据库删除后，内存中仍有其副本）。通过 `self.object.forum.id` 可以获取到其所属论坛的ID，然后用它来生成正确的重定向URL。

## 模板与表单：构建用户界面

视图处理了业务逻辑，接下来我们看看模板（`templates/`）和表单（`forms.py`）如何共同构建用户界面。论坛详情页（`forum_detail.html`）是交互最复杂的部分。

**1. 评论表单**
我们使用一个简单的Django表单来生成评论输入框，这让我们能方便地使用Crispy Forms等库来美化样式。

```python
# forms.py
class CommentForm(forms.Form):
    comment = forms.CharField(widget=forms.Textarea(attrs={'rows': 3}), label='')
```
在详情页模板中，我们这样渲染它：
```html
{% if user.is_authenticated %}
    <form action="{% url 'forums:comment_create' forum.id %}" method="post">
        {% csrf_token %}
        {{ comment_form|crispy }}
        <input type="submit" value="提交评论">
        <a href="{% url 'forums:all' %}">所有论坛</a>
    </form>
{% endif %}
```
*   表单的 `action` 指向 `forums:comment_create` 视图，并传递当前论坛的 `id`。
*   使用 `{% if user.is_authenticated %}` 确保只有登录用户能看到评论表单。

**2. 显示评论列表**
在表单下方，我们遍历从视图传递来的 `comments` 列表，显示所有评论。

```html
{% for comment in comments %}
    <p>{{ comment.text }}</p>
    <p>由 {{ comment.owner }} 于 {{ comment.updated_at|naturaltime }} 发布</p>
    {% if user == comment.owner %}
        <a href="{% url 'forums:comment_delete' comment.id %}">
            <i class="fas fa-trash"></i> <!-- 删除图标 -->
        </a>
    {% endif %}
{% endfor %}
```
*   循环输出每条评论的文本、所有者和发布时间（使用 `naturaltime` 过滤器显示为“刚刚”、“2分钟前”等友好格式）。
*   使用条件判断 `{% if user == comment.owner %}`，只有当当前登录用户是这条评论的所有者时，才显示删除图标。删除图标的链接指向 `forums:comment_delete` 视图，并传递评论的 `id`。

**3. 删除确认页面**
当用户点击删除图标时，会跳转到 `comment_delete.html` 这个确认页面。这个模板通常继承自一个基础模板，并包含一个简单的确认表单。

![](img/cdeb6312c6e58fb659b31ff94575e1ce_7.png)

```html
<form method="post">
    {% csrf_token %}
    <p>你确定要删除这条评论吗？</p>
    <input type="submit" value="确认删除">
    <a href="{% url 'forums:forum_detail' object.forum.id %}">取消</a>
</form>
```
*   表单提交后，会调用 `CommentDeleteView` 的 `post` 方法执行删除。
*   “取消”链接使用 `object.forum.id` 返回到评论所属的论坛详情页。

## URL配置与路由

最后，我们快速浏览一下 `urls.py` 文件，看看请求是如何被路由到对应视图的。配置方式与我们之前构建的CRUD应用类似。

```python
app_name = 'forums'
urlpatterns = [
    path('', ForumListView.as_view(), name='all'),
    path('forum/<int:pk>', ForumDetailView.as_view(), name='forum_detail'),
    path('forum/create', ForumCreateView.as_view(), name='forum_create'),
    path('forum/<int:pk>/update', ForumUpdateView.as_view(), name='forum_update'),
    path('forum/<int:pk>/delete', ForumDeleteView.as_view(), name='forum_delete'),
    path('forum/<int:pk>/comment', comment_create_view, name='comment_create'),
    path('comment/<int:pk>/delete', CommentDeleteView.as_view(), name='comment_delete'),
]
```
*   为 `Forum` 和 `Comment` 模型定义了完整的CRUD路由。
*   注意评论创建路由 `forum/<int:pk>/comment`，它接收论坛的 `pk`，并将其传递给 `comment_create_view` 函数视图。
*   评论删除路由 `comment/<int:pk>/delete` 接收评论自身的 `pk`，并将其传递给 `CommentDeleteView` 类视图。

## 总结

本节课中我们一起学习并拆解了一个Django论坛应用的示例代码。我们重点探讨了：

1.  **模型设计**：如何使用 `ManyToManyField` 并通过一个中间模型（`Comment`）来建立“多对多”关系，以及如何在中间模型中存储额外数据（如评论内容）。
2.  **视图逻辑**：如何编写视图来创建关联对象（特别是同时设置多个外键），以及如何重写类视图的方法（如 `get_success_url`）来实现自定义的重定向行为。
3.  **模板交互**：如何在模板中根据用户身份和对象所有权动态显示内容（如编辑/删除按钮），以及如何实现“Post-Redirect-Get”模式来提升用户体验。
4.  **权限控制**：再次实践了“所有者”模式，确保用户只能修改或删除自己创建的内容。

![](img/cdeb6312c6e58fb659b31ff94575e1ce_9.png)

![](img/cdeb6312c6e58fb659b31ff94575e1ce_11.png)

![](img/cdeb6312c6e58fb659b31ff94575e1ce_12.png)

这个示例将我们之前学到的许多Django概念（模型关系、CRUD操作、基于所有者的权限、表单处理、模板标签等）组合成了一个更复杂的实际应用。理解这个例子有助于你开始构建涉及复杂数据关系的Django项目。