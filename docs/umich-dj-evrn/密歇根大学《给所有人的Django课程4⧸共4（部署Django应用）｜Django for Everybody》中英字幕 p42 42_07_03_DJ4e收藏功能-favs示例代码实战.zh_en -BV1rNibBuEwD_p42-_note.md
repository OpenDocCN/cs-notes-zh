# Django for Everybody：4.7：收藏功能（Favs）示例代码实战 🚀

![](img/93f7b6f482b038f42d521918ac98ff02_1.png)

![](img/93f7b6f482b038f42d521918ac98ff02_2.png)

![](img/93f7b6f482b038f42d521918ac98ff02_3.png)

在本节课中，我们将学习如何实现一个“收藏”功能。这个功能演示了Django中的“多对多”关系，并引入了Ajax技术，以实现无需刷新整个页面的动态交互。我们将从模型设计开始，逐步讲解视图、模板和JavaScript代码，最终构建一个允许用户点击星标来收藏项目的完整应用。

## 模型设计 🗂️

上一节我们介绍了项目的基本结构，本节中我们来看看核心的数据模型是如何设计的。

模型定义了数据的结构。在这个收藏功能中，我们有两个核心模型：`Thing`（物品）和`Fav`（收藏记录）。

![](img/93f7b6f482b038f42d521918ac98ff02_5.png)

![](img/93f7b6f482b038f42d521918ac98ff02_6.png)

![](img/93f7b6f482b038f42d521918ac98ff02_8.png)

*   `Thing` 模型代表一个可以被收藏的物品。它包含标题、描述等字段，并通过一个`owner`外键关联到用户，以确定谁拥有（可以编辑/删除）这个物品。
*   `Fav` 模型是连接用户和物品的中间表，它建立了“多对多”关系。一个用户可以收藏多个物品，一个物品也可以被多个用户收藏。

![](img/93f7b6f482b038f42d521918ac98ff02_10.png)

![](img/93f7b6f482b038f42d521918ac98ff02_12.png)

以下是核心的模型代码：

![](img/93f7b6f482b038f42d521918ac98ff02_14.png)

![](img/93f7b6f482b038f42d521918ac98ff02_15.png)

```python
# favs/models.py
from django.db import models
from django.contrib.auth.models import User

![](img/93f7b6f482b038f42d521918ac98ff02_17.png)

class Thing(models.Model):
    title = models.CharField(max_length=200)
    text = models.TextField()
    # 物品所有者，用于权限控制
    owner = models.ForeignKey(User, on_delete=models.CASCADE)
    created_at = models.DateTimeField(auto_now_add=True)
    updated_at = models.DateTimeField(auto_now=True)

    def __str__(self):
        return self.title

class Fav(models.Model):
    # 关联被收藏的物品
    thing = models.ForeignKey(Thing, on_delete=models.CASCADE)
    # 关联执行收藏的用户
    user = models.ForeignKey(User, on_delete=models.CASCADE)
    created_at = models.DateTimeField(auto_now_add=True)

    class Meta:
        # 确保同一个用户不能重复收藏同一个物品
        unique_together = ('thing', 'user')

    def __str__(self):
        return f'{self.user.username} likes {self.thing.title}'
```

**关键点解析：**
*   `Fav.thing` 和 `Fav.user` 是两个外键，分别指向 `Thing` 和 `User` 模型。
*   `on_delete=models.CASCADE` 表示当关联的 `Thing` 或 `User` 被删除时，对应的 `Fav` 记录也会被自动删除。
*   `unique_together = (‘thing‘, ’user‘)` 是 `Meta` 类中的一个约束，它确保数据库中不会出现 `(用户A, 物品X)` 这样的重复组合，即一个用户只能收藏某个物品一次。

![](img/93f7b6f482b038f42d521918ac98ff02_19.png)

## URL配置与视图概览 🔗

![](img/93f7b6f482b038f42d521918ac98ff02_21.png)

![](img/93f7b6f482b038f42d521918ac98ff02_22.png)

![](img/93f7b6f482b038f42d521918ac98ff02_24.png)

![](img/93f7b6f482b038f42d521918ac98ff02_25.png)

定义好数据如何存储后，我们需要定义用户如何访问这些功能。这通过URL配置和视图来完成。

![](img/93f7b6f482b038f42d521918ac98ff02_27.png)

![](img/93f7b6f482b038f42d521918ac98ff02_29.png)

URL配置将特定的网页地址映射到处理该请求的视图函数。以下是本项目的主要URL模式：

```python
# favs/urls.py
from django.urls import path
from . import views

![](img/93f7b6f482b038f42d521918ac98ff02_31.png)

![](img/93f7b6f482b038f42d521918ac98ff02_32.png)

urlpatterns = [
    path(‘’, views.ThingListView.as_view(), name=‘thing_list’),
    path(‘thing/<int:pk>’, views.ThingDetailView.as_view(), name=‘thing_detail’),
    path(‘thing/create/’, views.ThingCreateView.as_view(), name=‘thing_create’),
    path(‘thing/<int:pk>/update/’, views.ThingUpdateView.as_view(), name=‘thing_update’),
    path(‘thing/<int:pk>/delete/’, views.ThingDeleteView.as_view(), name=‘thing_delete’),
    # 收藏功能相关的URL
    path(‘thing/<int:pk>/favorite/’, views.AddFavoriteView.as_view(), name=‘thing_favorite’),
    path(‘thing/<int:pk>/unfavorite/’, views.DeleteFavoriteView.as_view(), name=‘thing_unfavorite’),
]
```

**视图分类：**
*   **标准CRUD视图**：`ThingListView`, `ThingDetailView`, `ThingCreateView`, `ThingUpdateView`, `ThingDeleteView`。这些视图处理物品的列表展示、详情查看、创建、更新和删除，与之前课程中的示例类似，并通过`Owner`混合类（Mixin）来确保用户只能操作自己拥有的物品。
*   **收藏功能视图**：`AddFavoriteView` 和 `DeleteFavoriteView`。这是本节课的新内容，它们专门处理通过Ajax发送的收藏与取消收藏请求。

接下来，我们将深入最复杂的部分——列表视图，它需要为前端提供初始的收藏状态数据。

## 列表视图：传递收藏状态 📋

列表视图（`ThingListView`）不仅要列出所有物品，还需要告诉前端模板当前登录用户已经收藏了哪些物品，以便正确显示“已收藏”或“未收藏”的星标。

以下是`ThingListView`中处理此逻辑的关键部分：

```python
# favs/views.py
class ThingListView(OwnerListView):
    model = Thing
    template_name = ‘favs/thing_list.html’

    def get(self, request):
        # 调用父类方法获取物品列表
        thing_list = Thing.objects.all()
        favorites = [] # 初始化收藏ID列表
        if request.user.is_authenticated:
            # 获取当前用户所有收藏记录的物品ID
            # 使用列表推导式将QuerySet转换为纯ID列表，如 [4, 7]
            favorites = list(request.user.fav_set.values_list(‘thing_id’, flat=True))
            print(favorites) # 调试用，可在控制台查看
        ctx = {‘thing_list’: thing_list, ‘favorites’: favorites}
        return render(request, self.template_name, ctx)
```

![](img/93f7b6f482b038f42d521918ac98ff02_34.png)

![](img/93f7b6f482b038f42d521918ac98ff02_35.png)

**代码逻辑：**
1.  `request.user.fav_set`：利用Django的反向查询关系，获取当前用户的所有`Fav`记录。
2.  `.values_list(‘thing_id‘, flat=True)`：从这些记录中只提取出`thing_id`字段，形成一个ID值列表。
3.  将这个ID列表（`favorites`）传递给模板上下文（`ctx`）。

![](img/93f7b6f482b038f42d521918ac98ff02_37.png)

![](img/93f7b6f482b038f42d521918ac98ff02_38.png)

这样，在模板中，我们就可以通过检查当前遍历的物品ID是否在`favorites`列表中，来决定显示哪一颗星标。

![](img/93f7b6f482b038f42d521918ac98ff02_40.png)

![](img/93f7b6f482b038f42d521918ac98ff02_42.png)

![](img/93f7b6f482b038f42d521918ac98ff02_43.png)

![](img/93f7b6f482b038f42d521918ac98ff02_45.png)

## 前端模板：动态显示星标 ⭐

![](img/93f7b6f482b038f42d521918ac98ff02_46.png)

![](img/93f7b6f482b038f42d521918ac98ff02_47.png)

![](img/93f7b6f482b038f42d521918ac98ff02_49.png)

视图准备好了数据，现在需要在网页上显示出来。模板负责生成HTML，并利用传递过来的`favorites`列表控制星标的显示状态。

![](img/93f7b6f482b038f42d521918ac98ff02_51.png)

以下是模板中渲染每个物品及其收藏星标的核心代码：

![](img/93f7b6f482b038f42d521918ac98ff02_53.png)

```html
<!-- favs/templates/favs/thing_list.html -->
{% for thing in thing_list %}
  <div>
    <span>{{ thing.title }}</span>
    {% if user.is_authenticated %}
      <!-- 两颗重叠的星标，通过样式控制只显示一颗 -->
      <!-- 空心星：点击后执行收藏 -->
      <a href=“#”
         onclick=“favPost(‘{% url ‘thing_unfavorite’ thing.id %}‘, {{ thing.id }}); return false;”
         id=“favorite_star_{{thing.id}}”
         {% if thing.id in favorites %}style=“display: none;”{% endif %}>
        ☆ <!-- 空心星符号 -->
      </a>
      <!-- 实心星：点击后取消收藏 -->
      <a href=“#”
         onclick=“favPost(‘{% url ‘thing_favorite’ thing.id %}‘, {{ thing.id }}); return false;”
         id=“unfavorite_star_{{thing.id}}”
         {% if not thing.id in favorites %}style=“display: none;”{% endif %}>
        ★ <!-- 实心星符号 -->
      </a>
    {% endif %}
  </div>
{% endfor %}
```

**模板逻辑：**
*   循环遍历所有物品（`thing_list`）。
*   如果用户已登录（`user.is_authenticated`），则显示星标区域。
*   **两颗星标**：实际上渲染了两个链接（`<a>`标签），一个代表“未收藏”（☆），一个代表“已收藏”（★）。它们通过CSS的`display: none;`样式来控制只显示其中一个。
*   **条件判断**：`{% if thing.id in favorites %}` 用来判断当前物品是否已被收藏。如果已收藏，就隐藏空心星（☆），显示实心星（★）；反之则隐藏实心星，显示空心星。
*   **`onclick`事件**：点击星标时，会调用JavaScript函数`favPost`，并传入对应的URL（用于收藏或取消收藏）和物品ID。

![](img/93f7b6f482b038f42d521918ac98ff02_55.png)

这种“两颗星切换显示”的方式是实现UI状态变化的一种简洁方法。接下来，我们看看点击事件背后的JavaScript如何工作。

## JavaScript：处理Ajax请求与UI更新 🛠️

![](img/93f7b6f482b038f42d521918ac98ff02_57.png)

当用户点击星标时，我们不希望整个页面刷新，而是只向服务器发送一个轻量级的请求，并在收到响应后局部更新星标显示。这通过JavaScript（使用Fetch API）实现，即Ajax技术。

以下是处理收藏/取消收藏的JavaScript函数：

```javascript
// 静态文件中的JavaScript或模板内嵌的<script>
function favPost(url, thing_id) {
    console.log(‘Requesting to favorite/unfavorite‘);
    // 使用Fetch API向服务器发送POST请求
    fetch(url, {
        method: ‘POST‘,
        headers: {
            ‘Content-Type’: ‘application/x-www-form-urlencoded; charset=UTF-8‘,
        },
        // 请求体为空，因为操作由URL本身定义
    })
    .then(response => {
        console.log(‘Favorite/Unfavorite operation finished‘);
        // 请求完成后，切换两颗星标的显示状态
        const star = document.getElementById(`favorite_star_${thing_id}`);
        const unstar = document.getElementById(`unfavorite_star_${thing_id}`);
        // 切换显示/隐藏
        if (star.style.display === ‘none‘) {
            star.style.display = ‘inline‘;
            unstar.style.display = ‘none‘;
        } else {
            star.style.display = ‘none‘;
            unstar.style.display = ‘inline‘;
        }
    })
    .catch(error => console.error(‘Error:‘, error));
}
```

**JavaScript逻辑：**
1.  `fetch(url, {method: ‘POST‘, …})`：向传入的URL（由模板生成，如`/thing/4/favorite/`）发送一个HTTP POST请求。
2.  `.then(response => {…})`：这是一个Promise回调。当服务器响应返回后，执行其中的代码。这实现了异步处理，不会阻塞页面。
3.  **UI更新**：在回调函数中，通过`document.getElementById`获取到当前物品对应的两颗星标元素，然后翻转它们的显示状态（将显示的隐藏，隐藏的显示）。这样就实现了点击后星标外观的即时变化。

至此，前端的交互流程已经完成。最后，我们需要看看服务器端如何响应这个Ajax POST请求。

## 后端视图：处理收藏与取消收藏 ✅

前端发送的Ajax请求最终由Django视图处理。`AddFavoriteView`和`DeleteFavoriteView`负责在数据库中创建或删除`Fav`记录。

由于这是一个简单的API端点，并且为了避免跨站请求伪造（CSRF）保护的复杂性（在Ajax中需要额外处理），示例中使用了`@csrf_exempt`装饰器。在实际生产环境中，需要根据安全要求谨慎处理。

以下是处理“添加收藏”的视图：

![](img/93f7b6f482b038f42d521918ac98ff02_59.png)

![](img/93f7b6f482b038f42d521918ac98ff02_60.png)

![](img/93f7b6f482b038f42d521918ac98ff02_61.png)

![](img/93f7b6f482b038f42d521918ac98ff02_62.png)

```python
# favs/views.py
from django.views.decorators.csrf import csrf_exempt
from django.utils.decorators import method_decorator
from django.contrib.auth.mixins import LoginRequiredMixin
from django.http import HttpResponse
from django.shortcuts import get_object_or_404

![](img/93f7b6f482b038f42d521918ac98ff02_64.png)

![](img/93f7b6f482b038f42d521918ac98ff02_65.png)

@method_decorator(csrf_exempt, name=‘dispatch‘)
class AddFavoriteView(LoginRequiredMixin, View):
    def post(self, request, pk):
        # 1. 获取要收藏的物品
        thing = get_object_or_404(Thing, id=pk)
        # 2. 创建Fav对象（建立用户与物品的关联）
        fav = Fav(thing=thing, user=request.user)
        try:
            fav.save() # 尝试保存
        except IntegrityError:
            # 如果已经收藏过（违反unique_together约束），则忽略
            pass
        # 3. 返回一个空的成功响应（前端不处理具体内容，只根据状态码判断）
        return HttpResponse()
```

![](img/93f7b6f482b038f42d521918ac98ff02_67.png)

以下是处理“取消收藏”的视图：

![](img/93f7b6f482b038f42d521918ac98ff02_69.png)

![](img/93f7b6f482b038f42d521918ac98ff02_71.png)

![](img/93f7b6f482b038f42d521918ac98ff02_73.png)

```python
# favs/views.py
@method_decorator(csrf_exempt, name=‘dispatch‘)
class DeleteFavoriteView(LoginRequiredMixin, View):
    def post(self, request, pk):
        # 1. 获取要取消收藏的物品
        thing = get_object_or_404(Thing, id=pk)
        # 2. 查找并删除对应的收藏记录
        try:
            fav = Fav.objects.get(user=request.user, thing=thing)
            fav.delete()
        except Fav.DoesNotExist:
            # 如果记录不存在（可能已被删除），则忽略
            pass
        # 3. 返回一个空的成功响应
        return HttpResponse()
```

![](img/93f7b6f482b038f42d521918ac98ff02_75.png)

**视图逻辑：**
*   `LoginRequiredMixin`：确保只有登录用户才能访问。
*   `get_object_or_404(Thing, id=pk)`：根据URL中的主键`pk`获取物品对象，如果不存在则返回404错误。
*   **添加收藏**：尝试创建新的`Fav`对象并保存。使用`try...except IntegrityError`来捕获可能因重复收藏（违反`unique_together`）而引发的异常，并优雅地忽略它。
*   **取消收藏**：尝试查找当前用户和指定物品对应的`Fav`记录，如果找到则删除。
*   `return HttpResponse()`：两个视图都返回一个空的HTTP响应，状态码默认为200（成功）。前端JavaScript的Fetch API接收到成功的响应后，就会触发更新UI的回调函数。

## 总结 📝

![](img/93f7b6f482b038f42d521918ac98ff02_77.png)

本节课中我们一起学习了如何在Django应用中实现一个完整的收藏功能。我们回顾一下关键步骤：

![](img/93f7b6f482b038f42d521918ac98ff02_79.png)

![](img/93f7b6f482b038f42d521918ac98ff02_81.png)

1.  **模型设计**：使用`Fav`作为中间模型，通过`ForeignKey`建立`User`和`Thing`之间的多对多关系，并用`unique_together`确保数据唯一性。
2.  **URL与视图**：配置了处理收藏（`favorite/`）和取消收藏（`unfavorite/`）的URL，并创建了对应的视图类来处理POST请求。
3.  **列表视图增强**：在`ThingListView`中查询当前用户的收藏列表，并将物品ID列表传递给模板。
4.  **模板逻辑**：在模板中使用条件判断，根据物品是否在收藏列表中，来显示不同的星标（☆或★），并绑定调用JavaScript的点击事件。
5.  **Ajax交互**：编写JavaScript函数`favPost`，使用Fetch API向服务器发送异步POST请求，并在请求成功后切换星标的显示状态，实现无刷新交互。
6.  **后端处理**：视图接收Ajax请求，在数据库中创建或删除`Fav`记录，并返回简单的成功响应。

![](img/93f7b6f482b038f42d521918ac98ff02_83.png)

![](img/93f7b6f482b038f42d521918ac98ff02_84.png)

这个示例综合运用了Django的模型关系、基于类的视图、模板系统以及前端的Ajax技术，是一个典型的现代Web交互功能实现案例。