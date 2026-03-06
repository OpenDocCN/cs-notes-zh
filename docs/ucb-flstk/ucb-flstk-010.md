# 010：Node.js 与服务器基础 🚀

![](img/7d6c21f07be064be8e2b53d1455dcb32_1.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_3.png)

在本节课中，我们将要学习 Node.js 的基础知识，了解它如何让 JavaScript 在浏览器之外运行，并亲手构建一个简单的 Web 服务器。通过实践，你将理解客户端与服务器交互的基本原理。

## 什么是 Node.js？🤔

上一节我们介绍了课程概述，本节中我们来看看 Node.js 是什么。

Node.js 本质上是一个 JavaScript 运行时环境。你之前可能熟悉的 JavaScript 只能在网页浏览器中运行，而像 Python 或 Java 这样的语言则可以在计算机上直接运行程序。Node.js 的出现使得我们能够使用 JavaScript 编写服务器端程序。

你可以通过访问其官网下载并安装 Node.js。如果你一直在使用 React 进行开发，那么你的电脑里很可能已经安装了 Node.js，因为它通常是 React 开发环境的依赖项。

![](img/7d6c21f07be064be8e2b53d1455dcb32_5.png)

你可以通过在终端中运行 `node` 命令来检查是否已安装。

## 认识 NPM 📦

Node.js 带来了一个强大的工具：NPM（Node Package Manager）。它类似于 Python 的 pip，是一个包管理器，允许你轻松安装和管理第三方代码库（包）。此外，NPM 还能帮助你初始化并管理整个项目环境，我们稍后会看到这一点。

![](img/7d6c21f07be064be8e2b53d1455dcb32_7.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_9.png)

## Node.js 的能力与限制 ⚡

![](img/7d6c21f07be064be8e2b53d1455dcb32_10.png)

Node.js 的强大之处在于它提供了浏览器所不具备的访问系统资源的能力。

在浏览器中，JavaScript 的访问受到严格限制。你无法直接访问文件系统，不能自由地进行网络请求，也无法启动一个 Web 服务器。而使用 Node.js，你可以像使用 Python 一样，在本地计算机上执行这些操作。

然而，Node.js 环境也缺少浏览器环境中的一些特定对象。例如，你不能再使用 `document.getElementById` 这样的 DOM 操作方法，因为 Node.js 运行时没有“文档”（document）这个概念，它只是一个纯 JavaScript 的执行环境。

## 构建你的第一个服务器 🛠️

理解了 Node.js 的基本概念后，本节我们将动手构建一个 Web 服务器。

服务器是一台持续运行、等待连接的计算机。当你访问一个网站时，你的浏览器会向托管该网站的服务器发送请求，服务器则返回构成网站的 HTML、CSS 和 JavaScript 文件。

服务器的妙处在于，它不仅可以提供静态网页，还能处理动态请求。例如，一个登录表单在提交时，会向同一个服务器发送另一个请求，服务器可以验证用户名和密码，并返回登录结果。服务器是“有状态”的，它可以记住信息。

现在，请打开你的代码编辑器（如 VS Code）并创建一个新项目。

![](img/7d6c21f07be064be8e2b53d1455dcb32_12.png)

以下是需要完成的步骤：
1.  在项目中创建一个新的 JavaScript 文件，例如 `server.js`。
2.  打开编辑器内的终端。

![](img/7d6c21f07be064be8e2b53d1455dcb32_14.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_16.png)

## 运行简单的 Node.js 脚本 ▶️

![](img/7d6c21f07be064be8e2b53d1455dcb32_18.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_20.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_22.png)

我们将从一个简单的脚本开始，验证 Node.js 环境。

![](img/7d6c21f07be064be8e2b53d1455dcb32_24.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_26.png)

在你的 `server.js` 文件中，输入以下代码：
```javascript
console.log(42);
```
保存文件后，在终端中运行命令：
```bash
node server.js
```
终端应该会输出数字 `42`。这表明你的 Node.js 环境工作正常。

![](img/7d6c21f07be064be8e2b53d1455dcb32_28.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_30.png)

## 使用 Express 框架创建服务器 🌐

![](img/7d6c21f07be064be8e2b53d1455dcb32_32.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_34.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_36.png)

直接使用原生 Node.js 创建服务器比较复杂，因此我们使用一个流行的框架——Express。

![](img/7d6c21f07be064be8e2b53d1455dcb32_38.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_39.png)

首先，我们需要初始化一个 NPM 项目并安装 Express。在项目根目录的终端中，依次运行以下命令：
```bash
npm init -y
npm install express cors
```
`npm init -y` 会快速创建一个 `package.json` 文件来管理项目依赖。`npm install` 命令则用于安装 `express` 框架和 `cors` 中间件（用于处理跨域请求）。

![](img/7d6c21f07be064be8e2b53d1455dcb32_41.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_43.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_45.png)

接下来，在 `server.js` 文件中，用以下代码替换之前的内容：
```javascript
// 导入所需的模块
const express = require('express');
const cors = require('cors');

![](img/7d6c21f07be064be8e2b53d1455dcb32_47.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_49.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_50.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_52.png)

// 创建一个 Express 应用实例
const app = express();

// 使用 cors 中间件，允许跨域请求
app.use(cors());

// 定义一个路由处理器：当访问根路径（‘/’）时，返回 “Hello World”
app.get('/', (req, res) => {
  res.send('Hello World');
});

![](img/7d6c21f07be064be8e2b53d1455dcb32_54.png)

// 让服务器在 3042 端口上开始监听网络请求
app.listen(3042, () => {
  console.log('Server listening on port 3042');
});
```
这段代码创建了一个基本的服务器。它监听本机（`localhost`）的 `3042` 端口。当你在浏览器中访问 `http://localhost:3042` 时，服务器会处理对根路径 `/` 的 `GET` 请求，并返回文本 “Hello World”。

![](img/7d6c21f07be064be8e2b53d1455dcb32_56.png)

保存文件，并在终端中运行 `node server.js` 来启动服务器。然后打开浏览器访问上述地址，你应该能看到 “Hello World”。

## 理解服务器状态 🧠

为了展示服务器可以“记住”信息，我们来修改一下代码。

将 `server.js` 中的路由处理器修改如下：
```javascript
let counter = 1; // 在服务器内存中定义一个计数器变量

app.get('/', (req, res) => {
  res.send(`Incremental value: ${counter}`); // 每次请求返回当前计数值
  counter++; // 处理完请求后，计数器加1
});
```
重启服务器（在终端按 `Ctrl+C` 停止，再运行 `node server.js`）并刷新浏览器。每次刷新页面，看到的数字都会递增。即使你关闭浏览器标签页再重新打开，计数器依然会继续累加，因为 `counter` 变量一直保存在运行着的服务器内存中。这演示了服务器如何维护状态。

![](img/7d6c21f07be064be8e2b53d1455dcb32_58.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_60.png)

## 从客户端连接服务器 🔗

![](img/7d6c21f07be064be8e2b53d1455dcb32_62.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_64.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_66.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_68.png)

服务器已经就绪，现在我们来创建一个简单的 HTML 客户端页面与之交互。

![](img/7d6c21f07be064be8e2b53d1455dcb32_70.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_72.png)

在项目中创建一个新文件，命名为 `client.html`，并填入以下内容：
```html
<!DOCTYPE html>
<html>
<head>
    <title>Client</title>
</head>
<body>
    <h1 id="display">Initial Text</h1>
    <button onclick="getStuff()">Get Stuff</button>

    <script>
        async function getStuff() {
            // 向我们的服务器发起请求
            const response = await fetch('http://localhost:3042/');
            // 等待并获取响应的文本内容
            const text = await response.text();
            // 将获取到的文本显示在页面的 h1 元素中
            document.getElementById('display').innerText = text;
        }
    </script>
</body>
</html>
```
直接双击在浏览器中打开这个 `client.html` 文件（注意，它不是通过我们的 Node.js 服务器提供的）。点击 “Get Stuff” 按钮，页面会向 `localhost:3042` 上的服务器发送请求，并将服务器返回的递增数字显示出来。

![](img/7d6c21f07be064be8e2b53d1455dcb32_74.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_76.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_78.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_80.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_82.png)

这个例子清晰地展示了客户端与服务器的分离：`client.html` 是运行在浏览器中的客户端，它主动向另一个独立运行的程序（我们的 Node.js 服务器）发起请求并获取数据。

![](img/7d6c21f07be064be8e2b53d1455dcb32_84.png)

## 关于 CORS 和 Fetch API 的补充说明 🔐

你可能注意到，我们的服务器代码中使用了 `app.use(cors())`。这是为了启用 CORS（跨源资源共享），允许像 `client.html` 这样来自不同“源”（协议、域名、端口）的网页向我们的服务器发起请求。出于安全原因，浏览器默认禁止这类跨域请求。

![](img/7d6c21f07be064be8e2b53d1455dcb32_86.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_88.png)

我们客户端使用的 `fetch()` 函数是现代浏览器提供的用于发起网络请求的 API。它返回一个 Promise 对象，这使得我们可以用 `async/await` 语法优雅地处理异步操作（即需要等待服务器响应的操作）。

![](img/7d6c21f07be064be8e2b53d1455dcb32_90.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_92.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_93.png)

## 总结 📚

![](img/7d6c21f07be064be8e2b53d1455dcb32_95.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_97.png)

![](img/7d6c21f07be064be8e2b53d1455dcb32_99.png)

本节课中我们一起学习了 Node.js 的核心概念与实践。我们了解到 Node.js 使得 JavaScript 能够用于服务器端编程，并通过 NPM 管理项目依赖。我们使用 Express 框架快速构建了一个 Web 服务器，该服务器能够监听请求、返回响应，并且利用内存维护状态（如计数器）。最后，我们创建了一个独立的 HTML 客户端页面，通过 Fetch API 与自建的服务器进行通信，直观地演示了前后端分离的交互模式。这为理解现代 Web 应用如何工作奠定了坚实的基础。