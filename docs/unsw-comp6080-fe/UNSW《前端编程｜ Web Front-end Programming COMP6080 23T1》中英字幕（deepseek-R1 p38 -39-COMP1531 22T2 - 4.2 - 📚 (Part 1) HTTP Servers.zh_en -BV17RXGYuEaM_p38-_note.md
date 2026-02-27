# COMP1531：4.2：🌐 HTTP服务器（第一部分）

![](img/5235cb1364d5cbf0d954368cf2cfbc52_1.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_3.png)

在本节课中，我们将要学习网络、互联网、万维网（Web）以及HTTP服务器的基本概念。这是COMP1531课程中一个非常重要的主题，我们将通过构建自己的Web服务器来理解其工作原理。本节课是第一部分，主要介绍背景知识和一个简单的Express服务器示例。

---

## 概述：网络、互联网与万维网

在深入探讨Web服务器之前，我们需要理解几个核心概念：网络、互联网和万维网。它们是层层递进的关系。

**网络** 是一个广义概念，指一组能够相互通信的互联计算机。例如，你家里的所有设备通过路由器连接，就构成了一个家庭网络。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_5.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_6.png)

**互联网** 是一个全球性的基础设施，用于连接世界各地的计算机，使它们能够相互通信。它是一个巨大的网络。

**万维网** 是运行在互联网之上的一个系统，由通过URL链接的文档和资源组成，主要通过HTTP协议访问。我们日常使用的网站、YouTube、GitLab等都是万维网的一部分。

简单来说：**网络**包含**互联网**，而**互联网**又承载着**万维网**。我们即将学习的Web服务器，就运行在万维网上。

---

## 网络协议：沟通的规则

当计算机通过网络通信时，它们需要遵循特定的结构或规则，以确保彼此能够理解。这就像打电话时有固定的开场白和结束语一样。

这些规则被称为 **网络协议**。不同的通信类型使用不同的协议。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_8.png)

*   **SSH**：用于安全地远程连接另一台计算机（如连接VLab）。
*   **SMTP/IMAP**：用于发送和接收电子邮件。
*   **HTTP**：**超文本传输协议**，是**万维网的专用协议**。当你在浏览器中访问网站时，使用的就是HTTP协议。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_10.png)

在本课程中，我们将重点学习 **HTTP协议**。

---

## Web服务器基础模型

![](img/5235cb1364d5cbf0d954368cf2cfbc52_12.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_14.png)

万维网最初的设计非常简单，就像一个在线图书馆。其基本工作模型如下：

![](img/5235cb1364d5cbf0d954368cf2cfbc52_16.png)

1.  你（**客户端**）使用**Web浏览器**（如Chrome）。
2.  浏览器向**Web服务器**发送一个HTTP**请求**，例如“我想要`index.html`这个资源”。
3.  Web服务器收到请求后进行一些处理。
4.  服务器向你的浏览器返回一个HTTP**响应**，其中包含你请求的资源（如HTML文档）。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_18.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_20.png)

这个过程与在餐厅点餐类似：你是顾客（客户端），向服务员（服务器）提出请求，服务员处理后为你提供食物（响应）。

在本课程中，我们的重点是**构建自己的Web服务器**。

---

## 引入Express：一个Node.js Web服务器库

![](img/5235cb1364d5cbf0d954368cf2cfbc52_22.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_23.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_25.png)

我们将使用一个名为 **Express** 的Node.js库来构建HTTP服务器。它是一个NPM模块，使用起来非常直接。

以下是一个最基本的Express服务器代码示例。我们将逐行分析：

![](img/5235cb1364d5cbf0d954368cf2cfbc52_27.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_28.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_30.png)

```javascript
import express from 'express';

![](img/5235cb1364d5cbf0d954368cf2cfbc52_32.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_34.png)

const app = express();
const port = 3000;
app.use(express.json());

![](img/5235cb1364d5cbf0d954368cf2cfbc52_36.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_38.png)

app.get('/', (req, res) => {
    res.send('Hello World');
});

app.listen(port, () => {
    console.log(`Example app listening on port ${port}`);
});
```

**代码解析：**

![](img/5235cb1364d5cbf0d954368cf2cfbc52_40.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_41.png)

1.  `import express from 'express';`
    *   导入Express库。
2.  `const app = express();`
    *   创建一个Express应用实例。这类似于你之前使用`prompt-sync`库时创建的对象。
3.  `const port = 3000;`
    *   定义一个端口号。**端口**的概念稍后会详细解释。
4.  `app.use(express.json());`
    *   这是Express的一个配置项，用于解析JSON格式的请求数据。目前可以暂时忽略其具体含义，但需要包含这行代码。
5.  `app.get('/', (req, res) => { ... });`
    *   这是定义服务器**路由**和**行为**的核心部分。
    *   `app.get` 表示监听对特定URL路径的**GET**请求。
    *   `'/'` 是URL路径，这里代表网站的根目录（例如 `http://localhost:3000/`）。
    *   `(req, res) => { ... }` 是一个回调函数（匿名函数），当有请求到达该路径时被调用。
    *   `req` 对象包含请求的详细信息（如参数、头部）。
    *   `res` 对象用于构建和发送响应。这里我们使用 `res.send('Hello World')` 来返回文本“Hello World”。
6.  `app.listen(port, ...);`
    *   这行代码**启动服务器**。它让服务器开始监听指定端口（这里是3000），等待客户端连接。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_43.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_45.png)

---

## 运行服务器并理解关键概念

![](img/5235cb1364d5cbf0d954368cf2cfbc52_47.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_49.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_51.png)

当你运行上述代码时，服务器并不会像普通脚本一样执行完就退出。它会**持续运行**，就像一个在岗待命的服务员，循环等待客户的请求，直到你手动终止它（例如按 `Ctrl+C`）。

服务器运行后，你可以在浏览器中访问 `http://localhost:3000` 来测试它。这里引出了两个新概念：

*   **`localhost`**：这是一个特殊的主机名，指代**你当前正在使用的计算机本身**。它对应的IP地址通常是 `127.0.0.1`。在开发阶段，我们通常在本地计算机上运行和测试服务器。
*   **端口**：你可以将端口理解为计算机上的一个**“服务窗口”**。一台计算机可以同时运行多个网络服务（如Web服务器、数据库、邮件服务器），每个服务监听一个不同的端口号，就像一家商店有多个接待窗口一样。端口号范围很大，开发中常用 `3000`、`8080` 等。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_53.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_54.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_55.png)

**重要提示：开发环境的隔离性**
当你在VLab或自己的开发机上运行这个Express服务器时，它**仅运行在该台具体的计算机上**，并没有自动发布到公共互联网。因此：
*   只有连接到**同一台计算机**（例如，同一个VLab服务器实例，如 `vx8`）的其他用户，才能通过 `localhost:端口号` 访问你的服务器。
*   你在家用电脑的浏览器里输入 `localhost:3000`，访问的是你自己电脑上的服务，**无法**访问到运行在VLab上的服务器。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_57.png)

---

## 端口冲突与解决方案

![](img/5235cb1364d5cbf0d954368cf2cfbc52_59.png)

由于端口是计算机上的共享资源，可能会发生**端口冲突**。例如，如果你在VLab的 `vx8` 机器上运行服务器在端口 `2022`，而另一位同学也登录到 `vx8` 并试图在同一个端口 `2022` 上启动他的服务器，他就会收到“地址已被占用”的错误。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_60.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_62.png)

**解决方法很简单：更改端口号。** 只需将代码中的 `const port = 2022;` 改为另一个未被占用的数字（例如 `3022`、`4000`）即可。在开发中，这是一个常见且容易解决的问题。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_64.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_65.png)

---

![](img/5235cb1364d5cbf0d954368cf2cfbc52_67.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_69.png)

## 扩展服务器：定义多个路由

![](img/5235cb1364d5cbf0d954368cf2cfbc52_71.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_73.png)

Express的强大之处在于可以轻松定义多个路由来处理不同的URL请求。以下是如何扩展我们的服务器：

```javascript
app.get('/', (req, res) => {
    res.send('Hello World');
});

![](img/5235cb1364d5cbf0d954368cf2cfbc52_75.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_76.png)

app.get('/1', (req, res) => {
    res.send('1');
});

![](img/5235cb1364d5cbf0d954368cf2cfbc52_78.png)

app.get('/1/2', (req, res) => {
    res.send('2');
});

![](img/5235cb1364d5cbf0d954368cf2cfbc52_80.png)

app.get('/oh/my/god/why/is/this/url/so/long', (req, res) => {
    res.send('You found the long URL!');
});
```

![](img/5235cb1364d5cbf0d954368cf2cfbc52_82.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_84.png)

现在，你的服务器可以响应四个不同的URL路径：
*   `http://localhost:3000/` -> 返回 “Hello World”
*   `http://localhost:3000/1` -> 返回 “1”
*   `http://localhost:3000/1/2` -> 返回 “2”
*   `http://localhost:3000/oh/my/god/why/is/this/url/so/long` -> 返回 “You found the long URL!”

![](img/5235cb1364d5cbf0d954368cf2cfbc52_86.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_88.png)

这展示了如何根据不同的URL路径提供不同的内容，这是构建Web应用API的基础。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_90.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_92.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_94.png)

---

![](img/5235cb1364d5cbf0d954368cf2cfbc52_96.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_98.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_99.png)

## 总结

本节课我们一起学习了以下核心内容：

![](img/5235cb1364d5cbf0d954368cf2cfbc52_101.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_102.png)

![](img/5235cb1364d5cbf0d954368cf2cfbc52_104.png)

1.  **概念区分**：理解了**网络**、**互联网**和**万维网**之间的关系。
2.  **网络协议**：知道了HTTP协议是万维网的专用通信协议。
3.  **Web服务器模型**：掌握了客户端-服务器请求-响应的基本交互模型。
4.  **Express入门**：使用Node.js的Express库创建了一个最简单的HTTP服务器。
5.  **关键术语**：明白了 **`localhost`**（本地主机）和 **端口** 的含义及其在开发中的作用。
6.  **路由定义**：学会了如何使用 `app.get()` 为不同的URL路径定义处理逻辑。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_106.png)

简而言之，一个Web服务器就是一个运行在特定计算机、监听特定端口的程序，它接收HTTP请求，并根据请求的URL等信息返回HTTP响应。Express让我们能够用JavaScript轻松地编写这样的程序。

![](img/5235cb1364d5cbf0d954368cf2cfbc52_108.png)

在下一节课中，我们将深入探讨如何构建更复杂的API、处理不同类型的HTTP请求（如POST、PUT、DELETE），并开始将它们与完整的软件项目结合起来。