# CS50x 2024：第8讲：HTML， CSS， JavaScript 🌐

![](img/e2286cf0b31bc83edb13a8b2f669b689_0.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_1.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_2.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_4.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_6.png)

## 概述
在本节课中，我们将要学习互联网的工作原理，并在此基础上开始构建软件。我们将介绍三种不同的语言：HTML、CSS和JavaScript。其中，HTML和CSS是用于呈现内容的标记语言，而JavaScript是一种编程语言，常用于浏览器中创建交互式界面。

---

## 互联网如何工作 🌍

上一节我们介绍了课程的整体目标，本节中我们来看看互联网的基础工作原理。

互联网的核心是路由器，这些服务器的目的是将信息从A点路由到B点。数据通常不会直接从A点发送到B点，而是会经过多个中间路由器。

### 数据包与协议
数据在互联网上以“数据包”的形式传输，类似于现实世界中的信封。互联网使用的主要协议是TCP/IP。

*   **IP（互联网协议）**：负责为网络上的每台设备分配一个唯一的地址，即IP地址。IP地址的格式通常是`数字.数字.数字.数字`（例如`192.168.1.1`），每个数字在0到255之间，总共32位（4字节），理论上最多可以有约42.9亿个地址。由于设备数量激增，世界正在向IPv6（128位地址）过渡。
*   **TCP（传输控制协议）**：在IP的基础上工作，提供两项关键功能：
    1.  **保证交付**：通过为数据包添加序列号（例如“1/2”、“2/2”），接收方可以检测丢失的数据包并请求重发。
    2.  **多路复用**：通过使用端口号，让一台计算机可以同时处理多种服务（如电子邮件、网页、视频会议）。常见的端口号有80（HTTP）和443（HTTPS）。

### DNS与DHCP
人们通常使用域名（如`harvard.edu`）访问网站，但计算机需要使用IP地址。DNS（域名系统）服务器的作用就是将域名转换为IP地址。

此外，当设备连接到网络时，它需要知道自己的IP地址、默认路由器和DNS服务器。DHCP（动态主机配置协议）服务器会自动为设备分配这些配置信息，使整个过程无需手动设置。

---

## 万维网与HTTP 🌐

![](img/e2286cf0b31bc83edb13a8b2f669b689_8.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_9.png)

上一节我们了解了互联网的底层传输机制，本节中我们来看看构建在其上的最流行的应用——万维网（Web）及其协议HTTP。

![](img/e2286cf0b31bc83edb13a8b2f669b689_11.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_13.png)

### URL的组成部分
一个完整的URL包含多个部分，例如：`https://www.example.com/path/to/file.html`
*   `https://`：方案或协议，表示使用安全的HTTP。
*   `www.example.com`：完全限定域名，其中`www`是主机名，`example.com`是域名，`.com`是顶级域。
*   `/path/to/file.html`：路径，指向服务器上的特定文件或目录。

![](img/e2286cf0b31bc83edb13a8b2f669b689_15.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_16.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_18.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_20.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_22.png)

### HTTP请求与响应
Web遵循客户端-服务器模型。浏览器（客户端）向服务器发送请求，服务器返回响应。这通过HTTP协议标准化。

![](img/e2286cf0b31bc83edb13a8b2f669b689_24.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_26.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_27.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_29.png)

**HTTP请求**（从浏览器到服务器）可能如下所示：
```
GET / HTTP/2
Host: www.harvard.edu
...
```
*   `GET`是请求方法（动词），表示获取信息。另一个常见方法是`POST`，用于向服务器提交数据。
*   `/`是请求的路径（根目录）。
*   `HTTP/2`是协议版本。
*   `Host`是HTTP头部，指定请求的域名。

![](img/e2286cf0b31bc83edb13a8b2f669b689_31.png)

**HTTP响应**（从服务器到浏览器）可能如下所示：
```
HTTP/2 200 OK
Content-Type: text/html
...
```
*   `200`是状态码，表示“成功”。其他常见状态码包括：
    *   `301`：永久移动（重定向）
    *   `404`：未找到
    *   `500`：服务器内部错误

![](img/e2286cf0b31bc83edb13a8b2f669b689_33.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_34.png)

---

## HTML：构建网页结构 🏗️

![](img/e2286cf0b31bc83edb13a8b2f669b689_36.png)

上一节我们了解了浏览器和服务器如何通信，本节中我们来看看如何使用HTML来定义网页的内容和结构。

![](img/e2286cf0b31bc83edb13a8b2f669b689_38.png)

HTML（超文本标记语言）不是编程语言，而是一种标记语言，用于描述网页的结构。它主要由**标签**和**属性**构成。

![](img/e2286cf0b31bc83edb13a8b2f669b689_40.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_42.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_43.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_45.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_46.png)

### 基本HTML文档结构
一个最简单的HTML文档如下所示：

![](img/e2286cf0b31bc83edb13a8b2f669b689_48.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_49.png)

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>hello, title</title>
    </head>
    <body>
        hello, body
    </body>
</html>
```

![](img/e2286cf0b31bc83edb13a8b2f669b689_51.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_52.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_53.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_55.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_56.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_57.png)

*   `<!DOCTYPE html>`：文档类型声明，表示使用HTML5。
*   `<html>`：根元素，`lang="en"`是一个属性，表示页面主要语言为英语。
*   `<head>`：头部，包含页面的元信息，如标题。
*   `<title>`：定义浏览器标签页上显示的标题。
*   `<body>`：主体，包含页面的所有可见内容。

![](img/e2286cf0b31bc83edb13a8b2f669b689_59.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_60.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_62.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_63.png)

HTML元素通常由开始标签（如`<p>`）、内容和结束标签（如`</p>`）组成。它们可以嵌套，形成一种树状结构（文档对象模型，DOM）。

![](img/e2286cf0b31bc83edb13a8b2f669b689_65.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_66.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_68.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_70.png)

### 常用HTML标签
以下是创建网页时常用的一些标签：

![](img/e2286cf0b31bc83edb13a8b2f669b689_72.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_73.png)

*   **段落**：`<p>`标签定义段落。浏览器会忽略HTML源代码中的多余空白（包括换行和多个空格），只显示一个空格。
*   **标题**：`<h1>`到`<h6>`标签定义标题，`<h1>`最大，`<h6>`最小。
*   **列表**：
    *   无序列表（项目符号）使用`<ul>`和`<li>`标签。
    *   有序列表（数字编号）使用`<ol>`和`<li>`标签。
*   **表格**：使用`<table>`、`<tr>`（行）和`<td>`（单元格）标签。
*   **图像**：使用`<img>`标签，并通过`src`属性指定图片路径，`alt`属性提供替代文本。
*   **视频**：使用`<video>`标签，可以包含`controls`属性来显示播放控件。
*   **链接**：使用`<a>`（锚点）标签，通过`href`属性指定目标URL。
*   **表单**：使用`<form>`标签创建用户输入区域。`<input>`标签用于创建输入框，`type`属性可以指定为`text`、`search`、`email`等。`action`属性指定表单提交的URL，`method`属性指定提交方法（GET或POST）。
*   **语义化标签**：如`<header>`、`<main>`、`<footer>`、`<nav>`等，能更好地描述内容区域，有助于可访问性和搜索引擎优化。
*   **元标签**：`<meta>`标签位于`<head>`中，提供关于页面的元数据，例如设置移动设备友好的视口，或定义在社交媒体上分享时的预览信息。

![](img/e2286cf0b31bc83edb13a8b2f669b689_75.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_76.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_77.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_78.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_79.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_80.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_82.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_83.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_85.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_86.png)

### 表单与用户输入
表单可以通过URL的查询字符串传递用户输入，格式为`?key=value&key2=value2`。例如，Google搜索“cats”的URL是`https://www.google.com/search?q=cats`。

![](img/e2286cf0b31bc83edb13a8b2f669b689_88.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_89.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_90.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_91.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_93.png)

可以使用`pattern`属性和正则表达式在客户端验证输入（例如，只允许`.edu`邮箱）。但**客户端验证并不安全**，因为用户可以通过浏览器开发者工具修改HTML和JavaScript。真正的验证必须在服务器端进行。

![](img/e2286cf0b31bc83edb13a8b2f669b689_95.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_96.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_97.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_99.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_100.png)

可以使用W3C的验证器（`validator.w3.org`）来检查HTML代码的语法正确性。

![](img/e2286cf0b31bc83edb13a8b2f669b689_102.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_103.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_104.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_105.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_107.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_108.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_109.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_111.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_112.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_113.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_114.png)

---

![](img/e2286cf0b31bc83edb13a8b2f669b689_116.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_117.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_118.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_119.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_120.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_122.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_123.png)

## CSS：为网页添加样式 🎨

![](img/e2286cf0b31bc83edb13a8b2f669b689_125.png)

上一节我们使用HTML构建了网页的骨架，本节中我们来看看如何使用CSS来美化网页，控制其外观和布局。

![](img/e2286cf0b31bc83edb13a8b2f669b689_127.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_129.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_130.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_132.png)

CSS（层叠样式表）用于描述HTML元素在屏幕上的呈现样式。它同样使用**属性**和**值**，但语法是`属性: 值;`。

![](img/e2286cf0b31bc83edb13a8b2f669b689_134.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_136.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_138.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_139.png)

### 应用CSS的三种方式
1.  **内联样式**：直接在HTML标签的`style`属性中编写CSS。
    ```html
    <p style="font-size: large; text-align: center;">Hello</p>
    ```
2.  **内部样式表**：在HTML文档的`<head>`部分使用`<style>`标签包含CSS规则。
    ```html
    <head>
        <style>
            p {
                font-size: large;
                text-align: center;
            }
        </style>
    </head>
    ```
3.  **外部样式表**：将CSS规则写在一个独立的`.css`文件中，然后在HTML中通过`<link>`标签引入。这是最推荐的方式，因为它实现了样式与内容的分离，便于维护和复用。
    ```html
    <head>
        <link href="styles.css" rel="stylesheet">
    </head>
    ```

![](img/e2286cf0b31bc83edb13a8b2f669b689_141.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_142.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_143.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_144.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_145.png)

### CSS选择器
CSS通过“选择器”来指定哪些元素应用样式。

![](img/e2286cf0b31bc83edb13a8b2f669b689_147.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_148.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_150.png)

*   **元素选择器**：直接使用标签名。
    ```css
    p { color: blue; }
    ```
*   **类选择器**：使用点号（`.`）后跟类名。HTML元素通过`class`属性指定类名。
    ```css
    .centered { text-align: center; }
    ```
    ```html
    <div class="centered">This is centered.</div>
    ```
*   **ID选择器**：使用井号（`#`）后跟ID名。HTML元素通过`id`属性指定ID（应在页面内唯一）。
    ```css
    #special { font-weight: bold; }
    ```
    ```html
    <p id="special">This is bold.</p>
    ```
*   **伪类选择器**：用于定义元素的特殊状态，如悬停。
    ```css
    a:hover { text-decoration: underline; }
    ```

![](img/e2286cf0b31bc83edb13a8b2f669b689_152.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_153.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_155.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_156.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_157.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_158.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_160.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_161.png)

### 层叠与继承
CSS规则可以“层叠”和“继承”。子元素会继承父元素的某些样式（如`color`, `font-family`），除非被子元素自己的规则覆盖。样式也可以从多个来源（浏览器默认、作者样式、用户样式）合并，并遵循 specificity（特异性）和顺序规则来决定最终应用的样式。

![](img/e2286cf0b31bc83edb13a8b2f669b689_163.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_165.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_166.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_167.png)

### 使用CSS框架
为了快速创建美观、专业的界面，可以使用第三方CSS框架，如Bootstrap。这些框架提供了一系列预定义的CSS类，开发者只需为HTML元素添加相应的类名，即可获得复杂的样式效果，而无需从头编写大量CSS代码。

![](img/e2286cf0b31bc83edb13a8b2f669b689_169.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_170.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_172.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_173.png)

---

![](img/e2286cf0b31bc83edb13a8b2f669b689_175.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_176.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_177.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_178.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_180.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_181.png)

## JavaScript：实现网页交互 🤖

![](img/e2286cf0b31bc83edb13a8b2f669b689_183.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_184.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_186.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_187.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_188.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_189.png)

上一节我们使用CSS美化了网页的静态外观，本节中我们来看看如何使用JavaScript为网页添加动态行为和交互功能。

![](img/e2286cf0b31bc83edb13a8b2f669b689_191.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_192.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_193.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_195.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_197.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_198.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_199.png)

JavaScript是一种真正的编程语言，可以在浏览器中运行，用于操作HTML和CSS，响应用户事件。

![](img/e2286cf0b31bc83edb13a8b2f669b689_201.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_202.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_204.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_205.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_206.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_207.png)

### 在HTML中引入JavaScript
1.  **内联事件处理程序**：直接在HTML标签的事件属性（如`onsubmit`、`onclick`）中编写少量JavaScript代码（不推荐，混合了结构与行为）。
    ```html
    <form onsubmit="greet(); return false;">
    ```
2.  **内部脚本**：在HTML文档中使用`<script>`标签包含JavaScript代码。
    ```html
    <script>
        function greet() {
            alert('Hello!');
        }
    </script>
    ```
3.  **外部脚本**：将JavaScript代码写在一个独立的`.js`文件中，然后通过`<script src="...">`标签引入（推荐方式）。
    ```html
    <script src="script.js"></script>
    ```

![](img/e2286cf0b31bc83edb13a8b2f669b689_209.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_211.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_212.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_214.png)

### 基本JavaScript概念
*   **变量**：使用`let`或`const`关键字声明变量。
    ```javascript
    let message = "Hello";
    const PI = 3.14;
    ```
*   **函数**：使用`function`关键字定义函数。
    ```javascript
    function greet(name) {
        alert('Hello, ' + name);
    }
    ```
*   **DOM操作**：JavaScript可以通过DOM API访问和修改HTML文档。
    *   `document.querySelector(‘#id‘)`：选择具有特定ID的第一个元素。
    *   `element.innerHTML`：获取或设置元素的HTML内容。
    *   `element.style.property`：获取或设置元素的CSS样式（注意：CSS属性名如`background-color`在JS中要改为驼峰命名`backgroundColor`）。
*   **事件处理**：可以为元素添加事件监听器，以响应用户操作（如点击、按键、提交表单）。
    ```javascript
    document.querySelector('button').addEventListener('click', function() {
        alert('Button clicked!');
    });
    ```
*   **定时器**：`setInterval(function, milliseconds)`函数可以每隔指定毫秒数重复执行一个函数。

![](img/e2286cf0b31bc83edb13a8b2f669b689_216.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_217.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_219.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_221.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_222.png)

### 示例：动态修改页面
JavaScript的强大之处在于可以动态地创建、修改和删除页面元素，无需重新加载页面。例如，可以实现自动补全搜索框、实时更新内容、创建单页应用等复杂交互。

![](img/e2286cf0b31bc83edb13a8b2f669b689_224.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_226.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_227.png)

**重要安全提示**：如前所述，客户端（浏览器中）的JavaScript代码可以被用户查看和修改。因此，任何涉及安全、数据验证或敏感逻辑的操作都必须在服务器端进行。

![](img/e2286cf0b31bc83edb13a8b2f669b689_229.png)

---

![](img/e2286cf0b31bc83edb13a8b2f669b689_231.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_232.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_233.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_235.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_236.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_238.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_239.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_240.png)

## 总结 🎯

本节课中我们一起学习了构建现代Web应用的基础三大件：

![](img/e2286cf0b31bc83edb13a8b2f669b689_242.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_243.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_245.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_247.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_248.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_250.png)

1.  **HTML**：用于定义网页的内容和结构。
2.  **CSS**：用于控制网页的视觉表现和布局。
3.  **JavaScript**：用于实现网页的交互逻辑和动态行为。

![](img/e2286cf0b31bc83edb13a8b2f669b689_252.png)

![](img/e2286cf0b31bc83edb13a8b2f669b689_254.png)

我们还了解了互联网和Web的基本工作原理，包括TCP/IP、HTTP协议、客户端-服务器模型等。掌握了这些基础知识，你就具备了创建功能性和交互式网页的能力。在接下来的课程中，我们将学习如何将这些前端技术与后端服务器逻辑（使用Python等语言）结合起来，构建完整的Web应用程序。