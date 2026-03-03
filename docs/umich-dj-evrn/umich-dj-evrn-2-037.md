# Django for Everybody：4.7：JSON与Fetch API详解 🚀

![](img/0a2da5b3a9bab334b6c99c11bfda74a1_1.png)

在本节课中，我们将学习如何在Django应用中处理JSON数据，并使用JavaScript的Fetch API从客户端异步获取这些数据。我们将探讨JSON的基本概念、如何在Django视图中返回JSON响应，以及使用Promise和Async/Await两种模式编写健壮的Fetch请求。

---

## 概述 📋

JSON（JavaScript Object Notation）是一种轻量级的数据交换格式，其语法与JavaScript对象和Python字典高度相似。这使得它在Web开发中，尤其是在前后端分离的架构中，成为理想的数据传输格式。Fetch API是现代浏览器提供的用于发起网络请求的强大接口。本节课我们将结合两者，学习如何从Django后端获取JSON数据并在前端进行处理。

---

## JSON基础：语法与本质 🔍

![](img/0a2da5b3a9bab334b6c99c11bfda74a1_3.png)

JSON的本质是一种数据格式语法。它并非只能从服务器动态获取，其基础语法可以直接在JavaScript中定义。

上一节我们概述了课程目标，本节中我们来看看JSON的基本语法。

以下是一个在JavaScript中直接定义对象的例子：
```javascript
const who = {
    "first": "Chuck",
    "last": "Severance",
    "email": "csev@umich.edu"
};
console.log(who);
```
这段代码创建了一个名为 `who` 的JavaScript对象常量并打印它。其语法是：花括号 `{}` 包裹，内部是一系列 `"键": 值` 对。值可以是字符串、数字、布尔值、数组，甚至是嵌套的对象。

JSON的巧妙之处在于，**我们可以将这种完全相同的语法通过网络进行发送和接收**。这使得数据序列化和反序列化变得非常直观。

![](img/0a2da5b3a9bab334b6c99c11bfda74a1_5.png)

---

![](img/0a2da5b3a9bab334b6c99c11bfda74a1_7.png)

## Django视图：返回JSON响应 🐍

理解了JSON的语法后，我们来看看如何在Django后端生成并返回JSON数据。

Django提供了便捷的工具来创建JSON响应。与返回HTML的普通视图不同，我们需要返回一个明确标明内容类型为JSON的响应。

以下是Django视图返回JSON的示例代码：
```python
from django.http import JsonResponse
import time

def json_fun(request):
    time.sleep(2)  # 模拟延迟，便于观察
    data = {
        'first': 'Chuck',
        'last': 'Severance',
        'email': 'csev@umich.edu'
    }
    return JsonResponse(data)
```
在这段代码中：
1.  我们使用 `JsonResponse` 类。
2.  向其传递一个Python字典 `data`。
3.  `JsonResponse` 会自动将字典序列化为JSON字符串，并正确设置HTTP响应头（如 `Content-Type: application/json`）。

![](img/0a2da5b3a9bab334b6c99c11bfda74a1_9.png)

当我们访问这个视图的URL时，浏览器开发者工具的“网络”(Network)选项卡会显示，响应头是 `application/json`，响应体就是序列化后的JSON文本。浏览器通常会友好地解析并格式化显示这些数据。

**一个关键优势是：Python字典的语法与JavaScript对象（JSON）的语法几乎完全相同**，这使得数据转换非常自然。

---

![](img/0a2da5b3a9bab334b6c99c11bfda74a1_11.png)

![](img/0a2da5b3a9bab334b6c99c11bfda74a1_13.png)

## 使用Fetch API：Promise模式 ⚡

现在我们已经能从服务器获取JSON了，接下来学习如何在浏览器中使用Fetch API来异步获取这些数据。

Fetch API支持两种主要的编码风格：Promise链式调用和Async/Await。首先，我们来看Promise模式。

Promise模式通过 `.then()` 和 `.catch()` 方法链式处理异步操作。以下是使用Promise模式发起Fetch请求的示例结构：
```javascript
fetch(url)
  .then(response => response.json()) // 将响应解析为JSON
  .then(data => {
    console.log('成功获取数据:', data);
    // 在此处处理数据，例如更新UI
  })
  .catch(error => {
    console.error('请求过程中发生错误:', error);
    // 在此处处理错误，例如显示错误信息
  });
```
这段代码的工作流程是：
1.  `fetch(url)` 启动一个异步请求，并返回一个Promise。
2.  第一个 `.then()` 在请求完成、收到响应后执行，它尝试将响应体解析为JSON（这又是一个返回Promise的操作）。
3.  第二个 `.then()` 在JSON解析成功后执行，接收解析出的 `data` 对象，供我们使用。
4.  `.catch()` 会捕获链中任何阶段发生的错误。

![](img/0a2da5b3a9bab334b6c99c11bfda74a1_15.png)

![](img/0a2da5b3a9bab334b6c99c11bfda74a1_16.png)

![](img/0a2da5b3a9bab334b6c99c11bfda74a1_17.png)

在实际开发中，我们需要处理各种潜在错误，例如：
*   **URL语法错误**：`fetch` 调用本身会立即失败。
*   **404 Not Found**：服务器返回了响应，但状态码不是成功的2xx系列。
*   **200 OK但内容非JSON**：服务器返回了HTML或其他内容，导致 `response.json()` 解析失败。

![](img/0a2da5b3a9bab334b6c99c11bfda74a1_19.png)

![](img/0a2da5b3a9bab334b6c99c11bfda74a1_20.png)

Promise模式代码紧凑，适合处理大多数简单的异步场景。

![](img/0a2da5b3a9bab334b6c99c11bfda74a1_22.png)

---

## 使用Fetch API：Async/Await模式 🧵

![](img/0a2da5b3a9bab334b6c99c11bfda74a1_24.png)

除了Promise链，Async/Await提供了另一种更接近同步代码风格的异步处理方式。

Async/Await基于Promise，但允许我们以更线性的方式编写代码。以下是使用Async/Await重写的Fetch示例：
```javascript
async function loadData(url) {
  try {
    const response = await fetch(url); // 等待fetch完成
    if (!response.ok) { // 检查HTTP状态码是否成功
      throw new Error(`HTTP错误! 状态码: ${response.status}`);
    }
    const data = await response.json(); // 等待JSON解析完成
    console.log('成功获取数据:', data);
    // 在此处处理数据
    return data;
  } catch (error) {
    console.error('无法加载数据:', error);
    // 在此处处理错误
  }
}
```
这段代码的关键点：
1.  函数使用 `async` 关键字声明，表示其内部包含异步操作。
2.  `await` 关键字可以“暂停”异步函数的执行，直到后面的Promise完成。**这并非真正的线程阻塞，而是语法糖，它让引擎将代码分割，在Promise解决后继续执行**。
3.  `try...catch` 块可以集中处理所有异步和同步错误。
4.  我们可以更精细地控制流程，例如在获取响应后、解析JSON前，检查 `response.ok` 或 `response.status`，从而区分“404错误”和“返回了非JSON内容”等不同情况。

Async/Await模式代码结构更清晰，错误处理更集中，尤其在处理复杂异步逻辑时能提供更好的控制力。

---

## 总结 🎯

本节课中我们一起学习了：
1.  **JSON的本质**：一种与JavaScript对象和Python字典语法相似的数据交换格式。
2.  **Django返回JSON**：使用 `JsonResponse` 可以轻松将Python字典序列化为JSON并返回给前端。
3.  **Fetch API的两种模式**：
    *   **Promise模式**：通过 `.then().catch()` 链式调用，代码简洁，适用于大多数场景。
    *   **Async/Await模式**：使用 `async/await` 关键字，让异步代码看起来像同步代码，流程控制更清晰，错误处理更直接。

![](img/0a2da5b3a9bab334b6c99c11bfda74a1_26.png)

![](img/0a2da5b3a9bab334b6c99c11bfda74a1_28.png)

![](img/0a2da5b3a9bab334b6c99c11bfda74a1_29.png)

两种Fetch编码风格各有优势。Promise链更为简洁和函数式；而Async/Await则更易于阅读和调试，尤其适合复杂的异步逻辑。你可以根据项目需求和个人偏好进行选择。掌握这两种方法将使你能够高效地构建与现代Django后端交互的动态Web前端。