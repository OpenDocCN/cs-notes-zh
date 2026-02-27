# 前端编程：3：JavaScript AJAX 🦊 XHR

![](img/7c25ba565f51b6110700362af2d8607c_0.png)

在本节课中，我们将要学习如何使用 JavaScript 进行异步网络通信，核心是掌握 `XMLHttpRequest` (XHR) 对象。我们将了解如何发起请求、处理响应以及应对各种错误情况。

## 概述

上一节我们介绍了 JavaScript 的事件循环，它允许我们执行异步操作。本节中，我们来看看如何利用 `XMLHttpRequest` API 来实现网络请求，这是浏览器内置的、用于发起 HTTP 请求的经典方法。

## 客户端-服务器模型与并发

我们首先讨论了客户端-服务器模型，然后探讨了 JavaScript 的并发模型，特别是事件循环。现在，我们将学习如何将异步网络请求变为现实。

## 认识 XMLHttpRequest

`XMLHttpRequest` 是浏览器内置的 API，用于发起 HTTP 请求。它默认是异步的，这避免了同步执行可能导致的浏览器阻塞问题。

以下是创建一个基本 XHR 请求的流程：

1.  **创建对象**：实例化一个新的 `XMLHttpRequest` 对象。
    ```javascript
    const xhr = new XMLHttpRequest();
    ```
2.  **初始化请求**：使用 `open` 方法指定请求方法和 URL。
    ```javascript
    xhr.open('GET', 'https://api.example.com/data');
    ```
3.  **发送请求**：调用 `send` 方法发起请求。建议将其包裹在 `try...catch` 中，以捕获发送阶段可能抛出的异常。
    ```javascript
    try {
      xhr.send();
    } catch (error) {
      console.error('请求发送失败:', error);
    }
    ```
4.  **处理响应**：通过设置回调函数（如 `onload`）来处理请求完成后的逻辑。在回调中，可以检查状态码（如 `xhr.status === 200`）并获取响应数据（如 `xhr.responseText`）。
    ```javascript
    xhr.onload = function() {
      if (xhr.status === 200) {
        console.log('成功:', xhr.responseText);
      } else {
        console.error('请求出错，状态码:', xhr.status);
      }
    };
    ```

## 实战演示：获取IP地址

让我们通过一个简单的例子来实践。我们将创建一个按钮，点击后通过 XHR 从远程 API 获取并显示用户的 IP 地址。

以下是实现步骤：

1.  创建 `XMLHttpRequest` 对象。
2.  使用 `open` 方法初始化一个 `GET` 请求到 `https://api.ipify.org?format=json`。
3.  设置 `onload` 回调函数，在请求成功（状态码 200）时，解析返回的 JSON 字符串，并更新页面上的文本内容。
4.  将 `send` 调用包裹在 `try...catch` 块中。
5.  为按钮的点击事件绑定上述请求函数。

**核心代码片段：**
```javascript
function getIP() {
  const xhr = new XMLHttpRequest();
  xhr.open('GET', 'https://api.ipify.org?format=json');
  xhr.onload = function() {
    if (xhr.status === 200) {
      const data = JSON.parse(xhr.responseText); // 解析JSON字符串
      document.getElementById('ip-text').textContent = data.ip;
    } else {
      console.error('获取IP失败，状态码:', xhr.status);
    }
  };
  try {
    xhr.send();
  } catch (error) {
    console.error('请求发送异常:', error);
  }
}
```

## 错误处理策略

在网络请求中，错误处理至关重要。我们可以将错误分为两类：预期错误和意外错误。

以下是处理这些错误的方法：

*   **预期错误**：通常通过 HTTP 状态码传达。
    *   `4xx` (如 400, 401, 404)：通常表示客户端请求有问题（如参数错误、资源不存在）。
    *   `5xx` (如 500, 502)：通常表示服务器端出现问题。
    *   处理方式：在 `onload` 回调中检查 `xhr.status`，并根据不同的状态码进行相应处理（如提示用户、重试）。
*   **意外错误**：包括网络断开、请求超时等。
    *   处理方式1：使用 `try...catch` 包裹 `xhr.send()` 来捕获发送阶段的异常。
    *   处理方式2：设置 `onerror` 回调函数来处理请求过程中发生的网络错误。
    *   处理方式3：设置 `ontimeout` 回调来处理请求超时。
    *   最佳策略：对于意外错误，通常采用“指数退避”算法进行重试，即每次重试的等待时间逐渐增加，达到一定次数后最终失败并告知用户。

**示例：设置 `onerror` 回调**
```javascript
xhr.onerror = function() {
  console.error('网络请求过程中发生错误');
};
```

## 避免回调地狱

当多个异步操作依赖前一个操作的结果时，代码容易写成多层嵌套的回调函数，形成所谓的“回调地狱”，这会使代码难以阅读和维护。

以下是避免回调地狱的建议：

*   **扁平化优于嵌套**：尽量避免深度嵌套的回调。
*   **使用命名函数**：对于包含非平凡逻辑的回调，将其定义为独立的命名函数，而不是匿名函数。这提高了代码的可读性和可维护性。
*   **善用箭头函数**：对于简单的单行回调逻辑，可以使用箭头函数使代码更简洁。
*   **遵循软件工程原则**：如单一职责原则（SRP），确保函数只做一件事。

## 总结

本节课中我们一起学习了 `XMLHttpRequest` 的基本用法。我们了解了如何创建请求、发送请求、处理成功响应以及应对各种错误。虽然 XHR 是一个较老的 API，但在许多遗留代码库中仍然存在，理解它非常重要。同时，我们也探讨了如何通过良好的代码组织来避免“回调地狱”。

![](img/7c25ba565f51b6110700362af2d8607c_2.png)

在下一讲中，我们将学习更现代、更优雅的 `fetch` API 以及 `Promise`，它们提供了更强大的异步网络编程能力。