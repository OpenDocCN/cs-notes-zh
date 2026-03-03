# 076：Cookie与会话

![](img/9adafa944b3e0d9ce049e62f18116dd1_1.png)

在本节课中，我们将学习Web开发中的两个核心概念：Cookie和会话。我们将首先了解Cookie的工作原理，它是浏览器端的概念，然后探讨会话，这是服务器端的概念。理解这两者的区别和联系对于构建需要用户状态管理的Web应用至关重要。

![](img/9adafa944b3e0d9ce049e62f18116dd1_3.png)

![](img/9adafa944b3e0d9ce049e62f18116dd1_4.png)

## Cookie：浏览器端的标记

上一节我们介绍了课程概述，本节中我们来看看Cookie。Cookie是服务器存储在用户浏览器中的一小段数据。它的主要目的是让服务器能够识别和区分来自不同浏览器的请求。当Web服务器处理来自互联网上成千上万个浏览器的请求时，它需要一种方法来“标记”每个浏览器，以便知道正在与谁通信。

Cookie与登录没有直接关系。它的作用是在每个浏览器上留下一个标记，并在每次请求时将这个标记返回给服务器。通常，当服务器首次收到一个没有标记的浏览器请求时，它会生成一个唯一的标识符（通常是一个随机数）并通过响应头发送给浏览器，这个过程称为“设置Cookie”。

![](img/9adafa944b3e0d9ce049e62f18116dd1_6.png)

以下是关于Cookie的几个关键点：
*   **作用域与安全性**：Cookie与特定的网站（域名）关联。一个网站只能读写自己设置的Cookie，不能访问其他网站的Cookie，这确保了基本的安全性。
*   **有效期**：Cookie可以设置有效期。有两种主要类型：
    *   **持久性Cookie**：设置一个固定的过期时间（例如1000秒后或某个具体日期）。浏览器会将其保存到磁盘，即使关闭浏览器，在有效期内再次访问网站时也会发送该Cookie。
    *   **会话Cookie**：不设置过期时间，其生命周期与浏览器会话一致。当用户关闭所有浏览器标签页和浏览器窗口时，此类Cookie会被清除。

## 实际操作：查看和设置Cookie

![](img/9adafa944b3e0d9ce049e62f18116dd1_8.png)

![](img/9adafa944b3e0d9ce049e62f18116dd1_9.png)

理解了Cookie的基本概念后，让我们通过实际操作来加深理解。我们可以在浏览器的开发者工具中查看当前网站的Cookie。

以下是在Django视图中处理Cookie的示例代码：

![](img/9adafa944b3e0d9ce049e62f18116dd1_11.png)

```python
def cookie_demo(request):
    # 打印请求中携带的所有Cookie（字典形式）
    print(request.COOKIES)

    # 创建一个HTTP响应
    response = HttpResponse("C is for cookie and it's good enough for me")

    # 设置一个会话Cookie（关闭浏览器后失效）
    response.set_cookie('zap', 42)

    # 设置一个持久性Cookie，1000秒后过期
    response.set_cookie('sakaicar', 42, max_age=1000)

    return response
```

代码执行流程如下：
1.  当浏览器首次访问该视图且未携带Cookie时，`request.COOKIES` 是一个空字典。
2.  视图函数创建一个响应对象，并通过 `response.set_cookie()` 方法设置两个Cookie。
3.  服务器在响应头中发送 `Set-Cookie` 指令。
4.  浏览器接收到响应后，会将Cookie存储起来。
5.  此后，浏览器向同一网站发起的每一次请求，都会在请求头中自动携带这些Cookie。此时在视图函数中，`request.COOKIES` 字典将包含键值对 `{'zap': '42', 'sakaicar': '42'}`。

![](img/9adafa944b3e0d9ce049e62f18116dd1_13.png)

![](img/9adafa944b3e0d9ce049e62f18116dd1_14.png)

## 会话：服务器端的状态管理

我们已经了解了Cookie如何在浏览器端存储标记。本节中我们来看看会话，它利用这个标记在服务器端存储更多用户相关的数据。

![](img/9adafa944b3e0d9ce049e62f18116dd1_16.png)

![](img/9adafa944b3e0d9ce049e62f18116dd1_17.png)

会话是存储在服务器上的数据，用于在同一个用户的不同请求之间保持状态。Cookie最常见的用途之一就是为会话提供支持：服务器将唯一的会话ID（通常是一个长的随机字符串）存储在浏览器的Cookie中。当浏览器发送请求时，会附带这个会话ID Cookie，服务器通过这个ID找到对应的会话数据。

在Django中，会话的使用非常简便。`request.session` 对象就像一个字典，你可以用它来存储和读取当前会话的数据。

```python
# 在会话中存储数据
request.session['favorite_color'] = 'blue'

# 从会话中读取数据
favorite_color = request.session.get('favorite_color', 'unknown')
```

Django会自动处理会话ID Cookie的创建、发送和验证。开发者只需关心 `request.session` 中的数据即可，无需直接操作底层的Cookie。

![](img/9adafa944b3e0d9ce049e62f18116dd1_19.png)

## 总结

![](img/9adafa944b3e0d9ce049e62f18116dd1_21.png)

本节课中我们一起学习了Cookie和会话。
*   **Cookie** 是服务器设置在浏览器的小型数据片段，主要用于标识浏览器。它可以是临时的（会话Cookie），也可以是长期的（持久Cookie）。
*   **会话** 是服务器端的概念，用于存储用户在一次访问过程中的状态信息。它依赖于Cookie（通常是存储会话ID的Cookie）来关联浏览器与服务器上对应的数据。

![](img/9adafa944b3e0d9ce049e62f18116dd1_23.png)

理解Cookie作为浏览器标记的机制，以及会话如何利用这个标记在服务器端管理用户状态，是构建交互式Web应用的基础。在接下来的学习中，你将看到如何运用会话来实现用户登录、购物车等功能。