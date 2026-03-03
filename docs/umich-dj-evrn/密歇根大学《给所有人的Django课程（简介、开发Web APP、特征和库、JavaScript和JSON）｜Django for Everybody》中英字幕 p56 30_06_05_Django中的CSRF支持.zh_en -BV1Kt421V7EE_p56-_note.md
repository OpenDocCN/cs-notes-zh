# Django for Everybody： 5.6： Django中的CSRF支持 🛡️

![](img/a8a0f7d99052164338cfe898a6e75d86_1.png)

![](img/a8a0f7d99052164338cfe898a6e75d86_2.png)

在本节课中，我们将学习如何在Django中实现CSRF（跨站请求伪造）保护。我们将了解为什么需要它，如果不处理它会怎样，以及如何通过手动和自动两种方式在表单中正确添加CSRF令牌。

![](img/a8a0f7d99052164338cfe898a6e75d86_4.png)

---

## 概述

上一节我们介绍了CSRF的概念。本节中，我们来看看如何在Django中实际实现它。Django默认启用了CSRF保护，这意味着对于POST请求，我们必须采取一些明确的措施，否则请求会被拒绝。

---

![](img/a8a0f7d99052164338cfe898a6e75d86_6.png)

## 未启用CSRF保护的表单

首先，我们回顾一个之前见过的简单表单视图。当时，我们使用了 `@csrf_exempt` 装饰器来告诉Django不要因为CSRF处理而“炸掉”这个请求。

![](img/a8a0f7d99052164338cfe898a6e75d86_8.png)

![](img/a8a0f7d99052164338cfe898a6e75d86_9.png)

```python
from django.views.decorators.csrf import csrf_exempt

![](img/a8a0f7d99052164338cfe898a6e75d86_11.png)

@csrf_exempt
def my_first_form(request):
    # ... 处理表单的代码
```

这个装饰器的作用是**关闭**该视图的CSRF验证。现在，我们将创建一个没有此装饰器的视图，名为 `fail_form`，来演示如果CSRF保护开启而我们没有处理会发生什么。

当我们访问这个表单，输入一些内容并点击提交时，会收到一个 **403 Forbidden** 错误。在HTTP状态码中，403表示“禁止访问”——服务器理解请求，但拒绝授权。这是因为Django的CSRF中间件检查失败，在请求到达我们的视图代码之前就中止了它。

---

## 手动添加CSRF令牌

![](img/a8a0f7d99052164338cfe898a6e75d86_13.png)

为了让表单正常工作，我们需要在发出的POST请求中包含CSRF令牌。以下是一种手动添加令牌的低级方法：

1.  在HTML表单中，添加一个隐藏的输入字段。
2.  从Django的 `csrf` 模块获取当前请求的令牌。
3.  将这个令牌值填入隐藏字段。

![](img/a8a0f7d99052164338cfe898a6e75d86_15.png)

以下是实现代码：

![](img/a8a0f7d99052164338cfe898a6e75d86_17.png)

```python
from django.middleware.csrf import get_token

![](img/a8a0f7d99052164338cfe898a6e75d86_18.png)

def manual_csrf_form(request):
    # 获取CSRF令牌
    csrf_token = get_token(request)
    
    # 构建包含令牌的HTML表单字符串
    form_html = """
    <form method="post">
        <input type="hidden" name="csrfmiddlewaretoken" value="__TOKEN__">
        <input type="text" name="guess">
        <input type="submit" value="提交">
    </form>
    """
    # 替换占位符为真实的令牌
    form_html = form_html.replace("__TOKEN__", csrf_token)
    return HttpResponse(form_html)
```

当这个页面被渲染时，隐藏字段 `csrfmiddlewaretoken` 会包含一个长而复杂的随机字符串（令牌）。提交表单时，这个令牌会和表单数据（如 `guess=42`）一起发送到服务器。

Django的中间件会在请求到达视图之前验证这个令牌。**只有验证通过，我们的视图函数才会被执行**。因此，在视图内部打印出的POST数据中看到 `csrfmiddlewaretoken`，本身就意味着CSRF检查已经成功。

---

![](img/a8a0f7d99052164338cfe898a6e75d86_20.png)

![](img/a8a0f7d99052164338cfe898a6e75d86_21.png)

## 使用模板标签自动添加CSRF令牌

手动方法虽然有效，但很繁琐。Django提供了更简单的方式——使用模板标签。这是**推荐的做法**。

首先，确保在你的视图渲染模板时使用了 `RequestContext`（使用 `render()` 函数会自动处理这一点）。然后，在模板的表单标签内，使用 `{% csrf_token %}` 标签。

以下是一个示例：

**views.py**
```python
from django.shortcuts import render

![](img/a8a0f7d99052164338cfe898a6e75d86_23.png)

def easy_csrf_form(request):
    return render(request, 'myapp/form_template.html')
```

**form_template.html**
```html
<form method="post">
    {% csrf_token %}
    <input type="text" name="guess">
    <input type="submit" value="提交">
</form>
```

这个 `{% csrf_token %}` 标签会自动生成完整的隐藏输入字段，包括正确的名称和值。作为开发者，你无需关心令牌的具体生成和放置细节。

![](img/a8a0f7d99052164338cfe898a6e75d86_25.png)

![](img/a8a0f7d99052164338cfe898a6e75d86_26.png)

---

## 构建一个带CSRF保护的猜数游戏

现在，我们将应用所学知识，构建一个功能完整的猜数游戏视图。这次我们将使用**基于类的视图**，它可以将GET和POST请求的处理逻辑清晰地分离到不同方法中。

**views.py**
```python
from django.views import View
from django.shortcuts import render

![](img/a8a0f7d99052164338cfe898a6e75d86_28.png)

class GuessingGameView(View):
    
    def get(self, request):
        """处理GET请求，显示空表单"""
        # 渲染模板，初始没有消息
        return render(request, 'game.html', {'message': None})
    
    def post(self, request):
        """处理POST请求，检查猜测结果"""
        # 从POST数据中获取用户的猜测
        user_guess = request.POST.get('guess')
        # 调用函数检查猜测值
        message = self._check_guess(user_guess)
        # 将消息传入上下文并重新渲染页面
        context = {'message': message}
        return render(request, 'game.html', context)
    
    def _check_guess(self, guess):
        """辅助函数：检查猜测值并返回提示信息"""
        secret_number = 42
        try:
            guess_int = int(guess)
            if guess_int < secret_number:
                return "猜低了！"
            elif guess_int > secret_number:
                return "猜高了！"
            else:
                return f"恭喜你！答案是 {secret_number}。"
        except (ValueError, TypeError):
            # 如果输入无法转换为整数
            return f"格式错误：'{guess}' 不是一个有效的数字。"
```

**game.html**
```html
<h1>猜数字游戏</h1>
<form method="post">
    {% csrf_token %}
    <label for="guess">输入你的猜测：</label>
    <input type="text" id="guess" name="guess">
    <input type="submit" value="提交猜测">
</form>

![](img/a8a0f7d99052164338cfe898a6e75d86_30.png)

![](img/a8a0f7d99052164338cfe898a6e75d86_31.png)

{% if message %}
    <p><strong>{{ message }}</strong></p>
{% endif %}
```

### 工作流程解析

![](img/a8a0f7d99052164338cfe898a6e75d86_33.png)

1.  **GET请求**：用户首次访问页面时，触发 `get()` 方法，渲染一个带有空表单和CSRF令牌的页面。
2.  **用户交互**：用户在表单中输入数字（例如42）并点击提交。
3.  **POST请求**：浏览器将表单数据和CSRF令牌一起发送。Django中间件先验证CSRF令牌。
4.  **令牌有效**：验证通过，请求被路由到 `post()` 方法。
5.  **处理逻辑**：`post()` 方法从 `request.POST` 中获取猜测值，调用 `_check_guess` 函数生成提示信息。
6.  **返回响应**：将提示信息放入上下文，重新渲染 `game.html` 模板。此时，因为 `message` 变量有值，页面上会显示出“恭喜你！答案是 42。”

**关键点**：只要我们在模板中正确使用了 `{% csrf_token %}`，CSRF保护就会自动生效。如果令牌缺失或无效，用户会收到403错误，并且我们的 `post()` 方法根本不会被执行。

---

![](img/a8a0f7d99052164338cfe898a6e75d86_35.png)

![](img/a8a0f7d99052164338cfe898a6e75d86_36.png)

![](img/a8a0f7d99052164338cfe898a6e75d86_38.png)

## 总结

本节课中，我们一起学习了Django的CSRF支持：

*   **CSRF保护是默认开启的**，对于POST请求必须处理，否则会导致403错误。
*   **手动添加令牌**涉及使用 `get_token(request)` 获取令牌并嵌入HTML，但这种方法较复杂。
*   **自动添加令牌**是标准做法，只需在表单模板中使用 `{% csrf_token %}` 标签即可。
*   **基于类的视图**（如 `View`）能优雅地分离GET和POST处理逻辑。
*   **验证时机**：CSRF验证发生在请求到达视图函数**之前**。如果视图代码得以执行，就意味着CSRF检查已经通过。

通过构建一个猜数游戏示例，我们实践了如何在一个功能完整的视图中集成CSRF保护、处理用户输入并给出反馈。

![](img/a8a0f7d99052164338cfe898a6e75d86_40.png)

![](img/a8a0f7d99052164338cfe898a6e75d86_41.png)

![](img/a8a0f7d99052164338cfe898a6e75d86_42.png)

---

接下来，我们将讨论一个常见的细节问题：“提交后刷新页面”会带来什么影响，以及如何修复它。