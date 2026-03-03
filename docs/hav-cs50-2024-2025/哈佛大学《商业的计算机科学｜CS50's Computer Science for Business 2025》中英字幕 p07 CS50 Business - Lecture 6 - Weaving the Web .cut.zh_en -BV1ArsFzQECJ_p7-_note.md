# 哈佛大学《商业的计算机科学》：第6讲：编织网络 🌐

## 概述
在本节课中，我们将学习构成万维网（Web）基础的三种核心技术：HTML、CSS 和 JavaScript。我们将了解如何使用 HTML 来构建网页的结构，使用 CSS 来美化其样式，以及使用 JavaScript 来增加交互性。即使你从未编写过代码，也能理解这些技术如何协同工作，创造出我们每天使用的网站和应用。

![](img/b24c2807aef11fc612696c6543042792_1.png)

---

![](img/b24c2807aef11fc612696c6543042792_3.png)

![](img/b24c2807aef11fc612696c6543042792_4.png)

## HTML：网页的骨架 🏗️

上一节我们介绍了互联网的基础设施，本节中我们来看看在互联网之上传输的具体数据格式——HTML。

### 什么是 HTML？
HTML（超文本标记语言）不是一种编程语言，而是一种标记语言。它用于结构化网页内容并添加元数据，例如格式化信息或语义信息，以便浏览器（最终是人类）理解他们正在查看的内容。

![](img/b24c2807aef11fc612696c6543042792_6.png)

![](img/b24c2807aef11fc612696c6543042792_8.png)

HTML 主要包含两种语法特性：**标签**和**属性**。

### 最简单的 HTML 页面
以下是一个最简单的 HTML5 页面示例：

![](img/b24c2807aef11fc612696c6543042792_10.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Hello, title</title>
</head>
<body>
    Hello, body
</body>
</html>
```

![](img/b24c2807aef11fc612696c6543042792_12.png)

![](img/b24c2807aef11fc612696c6543042792_14.png)

![](img/b24c2807aef11fc612696c6543042792_16.png)

*   `<!DOCTYPE html>`：文档类型声明，告诉浏览器这是 HTML5 文档。
*   `<html lang="en">`：HTML 根元素的开始标签，`lang="en"` 属性表示页面语言为英语。
*   `<head>`：页面头部，包含元信息，如标题。
*   `<title>`：页面标题，显示在浏览器标签页上。
*   `<body>`：页面主体，包含用户可见的主要内容。
*   每个开始标签（如 `<title>`）通常对应一个结束标签（如 `</title>`），用 `/` 表示结束。

![](img/b24c2807aef11fc612696c6543042792_17.png)

![](img/b24c2807aef11fc612696c6543042792_18.png)

![](img/b24c2807aef11fc612696c6543042792_20.png)

![](img/b24c2807aef11fc612696c6543042792_21.png)

![](img/b24c2807aef11fc612696c6543042792_22.png)

### 文档对象模型（DOM）
浏览器接收到 HTML 后，会在内存中将其解析成一个树状结构，称为**文档对象模型**。上面的 HTML 对应的 DOM 树如下：

![](img/b24c2807aef11fc612696c6543042792_24.png)

![](img/b24c2807aef11fc612696c6543042792_25.png)

```
        Document
           |
        <html>
        /    \
    <head>   <body>
      |         |
   <title>   "Hello, body"
      |
"Hello, title"
```

![](img/b24c2807aef11fc612696c6543042792_27.png)

![](img/b24c2807aef11fc612696c6543042792_29.png)

这种结构使得 JavaScript 可以方便地访问和操作页面元素。

![](img/b24c2807aef11fc612696c6543042792_31.png)

![](img/b24c2807aef11fc612696c6543042792_32.png)

---

![](img/b24c2807aef11fc612696c6543042792_34.png)

![](img/b24c2807aef11fc612696c6543042792_36.png)

![](img/b24c2807aef11fc612696c6543042792_38.png)

![](img/b24c2807aef11fc612696c6543042792_39.png)

![](img/b24c2807aef11fc612696c6543042792_40.png)

## 创建并查看你的第一个网页 🚀

![](img/b24c2807aef11fc612696c6543042792_42.png)

![](img/b24c2807aef11fc612696c6543042792_43.png)

![](img/b24c2807aef11fc612696c6543042792_44.png)

现在，让我们动手创建一个 HTML 文件并在浏览器中查看它。

![](img/b24c2807aef11fc612696c6543042792_46.png)

![](img/b24c2807aef11fc612696c6543042792_48.png)

![](img/b24c2807aef11fc612696c6543042792_49.png)

### 步骤
1.  **创建文件**：使用文本编辑器（如 VS Code）创建一个新文件，命名为 `hello.html`。
2.  **编写代码**：将上面的简单 HTML 代码复制到文件中并保存。
3.  **运行本地服务器**：为了在浏览器中查看，你可以在文件所在目录运行一个简单的 HTTP 服务器。例如，在终端中运行：
    ```bash
    python3 -m http.server 8080
    ```
4.  **在浏览器中访问**：打开浏览器，输入地址 `http://localhost:8080/hello.html`，你就能看到你的第一个网页了。

![](img/b24c2807aef11fc612696c6543042792_50.png)

![](img/b24c2807aef11fc612696c6543042792_52.png)

![](img/b24c2807aef11fc612696c6543042792_53.png)

![](img/b24c2807aef11fc612696c6543042792_55.png)

---

![](img/b24c2807aef11fc612696c6543042792_56.png)

![](img/b24c2807aef11fc612696c6543042792_58.png)

## 更多 HTML 标签示例 📝

![](img/b24c2807aef11fc612696c6543042792_60.png)

![](img/b24c2807aef11fc612696c6543042792_62.png)

![](img/b24c2807aef11fc612696c6543042792_63.png)

以下是 HTML 中一些常用标签的示例，用于构建更丰富的页面内容。

![](img/b24c2807aef11fc612696c6543042792_65.png)

![](img/b24c2807aef11fc612696c6543042792_67.png)

![](img/b24c2807aef11fc612696c6543042792_68.png)

### 段落与标题
使用 `<p>` 标签定义段落，使用 `<h1>` 到 `<h6>` 标签定义不同级别的标题。

![](img/b24c2807aef11fc612696c6543042792_70.png)

![](img/b24c2807aef11fc612696c6543042792_71.png)

![](img/b24c2807aef11fc612696c6543042792_72.png)

![](img/b24c2807aef11fc612696c6543042792_73.png)

```html
<h1>主标题</h1>
<p>这是一个段落。</p>
<h2>次级标题</h2>
<p>这是另一个段落。</p>
```

![](img/b24c2807aef11fc612696c6543042792_75.png)

![](img/b24c2807aef11fc612696c6543042792_76.png)

![](img/b24c2807aef11fc612696c6543042792_78.png)

![](img/b24c2807aef11fc612696c6543042792_79.png)

### 列表
以下是创建无序列表和有序列表的方法。

![](img/b24c2807aef11fc612696c6543042792_81.png)

*   **无序列表**（项目符号）：
    ```html
    <ul>
        <li>项目一</li>
        <li>项目二</li>
        <li>项目三</li>
    </ul>
    ```
*   **有序列表**（数字编号）：
    ```html
    <ol>
        <li>第一步</li>
        <li>第二步</li>
        <li>第三步</li>
    </ol>
    ```

![](img/b24c2807aef11fc612696c6543042792_83.png)

![](img/b24c2807aef11fc612696c6543042792_84.png)

![](img/b24c2807aef11fc612696c6543042792_85.png)

![](img/b24c2807aef11fc612696c6543042792_87.png)

![](img/b24c2807aef11fc612696c6543042792_89.png)

![](img/b24c2807aef11fc612696c6543042792_90.png)

![](img/b24c2807aef11fc612696c6543042792_91.png)

![](img/b24c2807aef11fc612696c6543042792_92.png)

### 表格
使用 `<table>`、`<tr>`（行）、`<th>`（表头单元格）、`<td>`（数据单元格）标签来创建表格。

![](img/b24c2807aef11fc612696c6543042792_94.png)

![](img/b24c2807aef11fc612696c6543042792_96.png)

![](img/b24c2807aef11fc612696c6543042792_97.png)

```html
<table>
    <thead>
        <tr>
            <th>姓名</th>
            <th>电话</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>张三</td>
            <td>123-456-7890</td>
        </tr>
        <tr>
            <td>李四</td>
            <td>098-765-4321</td>
        </tr>
    </tbody>
</table>
```

![](img/b24c2807aef11fc612696c6543042792_99.png)

![](img/b24c2807aef11fc612696c6543042792_101.png)

![](img/b24c2807aef11fc612696c6543042792_103.png)

### 图像与媒体
*   **图像**：使用 `<img>` 标签，它是空元素，无需闭合标签。
    ```html
    <img src="bridge.png" alt="一座桥的图片">
    ```
    *   `src` 属性指定图片来源。
    *   `alt` 属性提供替代文本，用于可访问性和图片无法加载时。
*   **视频**：使用 `<video>` 标签。
    ```html
    <video controls muted>
        <source src="video.mp4" type="video/mp4">
    </video>
    ```
    *   `controls` 属性添加播放控件。
    *   `muted` 属性默认静音。

![](img/b24c2807aef11fc612696c6543042792_105.png)

![](img/b24c2807aef11fc612696c6543042792_107.png)

![](img/b24c2807aef11fc612696c6543042792_108.png)

### 超链接
使用 `<a>`（锚点）标签创建链接。

![](img/b24c2807aef11fc612696c6543042792_110.png)

![](img/b24c2807aef11fc612696c6543042792_111.png)

```html
<a href="https://www.harvard.edu">访问哈佛大学</a>
```
`href` 属性指定链接的目标地址。**注意**：用户看到的文本（“访问哈佛大学”）可能与实际跳转的地址不同，这是网络钓鱼攻击的常见手段，需要警惕。

![](img/b24c2807aef11fc612696c6543042792_113.png)

![](img/b24c2807aef11fc612696c6543042792_114.png)

![](img/b24c2807aef11fc612696c6543042792_116.png)

![](img/b24c2807aef11fc612696c6543042792_117.png)

![](img/b24c2807aef11fc612696c6543042792_118.png)

### 表单
表单用于收集用户输入。以下是一个模仿 Google 搜索前端的简单表单：

![](img/b24c2807aef11fc612696c6543042792_120.png)

![](img/b24c2807aef11fc612696c6543042792_121.png)

![](img/b24c2807aef11fc612696c6543042792_122.png)

![](img/b24c2807aef11fc612696c6543042792_123.png)

![](img/b24c2807aef11fc612696c6543042792_125.png)

![](img/b24c2807aef11fc612696c6543042792_126.png)

![](img/b24c2807aef11fc612696c6543042792_127.png)

![](img/b24c2807aef11fc612696c6543042792_128.png)

![](img/b24c2807aef11fc612696c6543042792_129.png)

![](img/b24c2807aef11fc612696c6543042792_131.png)

```html
<form action="https://www.google.com/search" method="get">
    <input type="search" name="q" placeholder="输入搜索词">
    <input type="submit" value="Google 搜索">
</form>
```
*   `action` 属性指定表单数据提交到的地址。
*   `method="get"` 表示通过 URL 传递数据（例如 `?q=cats`）。
*   `name="q"` 是 Google 定义的查询参数名。
*   `type="search"` 会提供更好的搜索框体验（如清除按钮）。

![](img/b24c2807aef11fc612696c6543042792_133.png)

![](img/b24c2807aef11fc612696c6543042792_134.png)

### 输入验证
HTML5 提供了内置的客户端输入验证。

![](img/b24c2807aef11fc612696c6543042792_136.png)

![](img/b24c2807aef11fc612696c6543042792_137.png)

![](img/b24c2807aef11fc612696c6543042792_138.png)

*   **使用 `type` 属性**：
    ```html
    <input type="email" required>
    ```
*   **使用 `pattern` 属性和正则表达式**：
    ```html
    <input type="text" pattern="\d{3}-\d{3}-\d{4}" placeholder="123-456-7890">
    ```
    *   `\d` 匹配数字。
    *   `{3}` 表示匹配前一个字符 3 次。
    *   这个模式匹配美国电话号码格式。

![](img/b24c2807aef11fc612696c6543042792_140.png)

![](img/b24c2807aef11fc612696c6543042792_141.png)

![](img/b24c2807aef11fc612696c6543042792_142.png)

![](img/b24c2807aef11fc612696c6543042792_143.png)

![](img/b24c2807aef11fc612696c6543042792_145.png)

![](img/b24c2807aef11fc612696c6543042792_147.png)

**重要提示**：客户端验证**仅用于改善用户体验**，容易被绕过（用户可通过浏览器开发者工具修改 HTML）。**真正的安全验证必须在服务器端进行。**

![](img/b24c2807aef11fc612696c6543042792_149.png)

![](img/b24c2807aef11fc612696c6543042792_150.png)

![](img/b24c2807aef11fc612696c6543042792_151.png)

![](img/b24c2807aef11fc612696c6543042792_152.png)

![](img/b24c2807aef11fc612696c6543042792_154.png)

---

![](img/b24c2807aef11fc612696c6543042792_156.png)

![](img/b24c2807aef11fc612696c6543042792_157.png)

![](img/b24c2807aef11fc612696c6543042792_159.png)

![](img/b24c2807aef11fc612696c6543042792_160.png)

![](img/b24c2807aef11fc612696c6543042792_162.png)

![](img/b24c2807aef11fc612696c6543042792_164.png)

## CSS：为网页添加样式 🎨

![](img/b24c2807aef11fc612696c6543042792_166.png)

![](img/b24c2807aef11fc612696c6543042792_167.png)

![](img/b24c2807aef11fc612696c6543042792_168.png)

![](img/b24c2807aef11fc612696c6543042792_170.png)

上一节我们使用 HTML 构建了网页的结构，本节中我们来看看如何使用 CSS 来美化这些结构。

![](img/b24c2807aef11fc612696c6543042792_172.png)

![](img/b24c2807aef11fc612696c6543042792_173.png)

![](img/b24c2807aef11fc612696c6543042792_174.png)

![](img/b24c2807aef11fc612696c6543042792_175.png)

![](img/b24c2807aef11fc612696c6543042792_177.png)

![](img/b24c2807aef11fc612696c6543042792_179.png)

![](img/b24c2807aef11fc612696c6543042792_180.png)

![](img/b24c2807aef11fc612696c6543042792_182.png)

### 什么是 CSS？
CSS（层叠样式表）用于描述 HTML 元素在屏幕上的呈现样式，如颜色、字体、间距和布局。它同样使用**属性-值**对。

![](img/b24c2807aef11fc612696c6543042792_184.png)

![](img/b24c2807aef11fc612696c6543042792_186.png)

### 应用 CSS 的三种方式
1.  **内联样式**：直接在 HTML 标签的 `style` 属性中编写。
    ```html
    <p style="color: red; text-align: center;">这是一个红色居中的段落。</p>
    ```
2.  **内部样式表**：在 HTML 文件的 `<head>` 部分使用 `<style>` 标签。
    ```html
    <head>
        <style>
            p {
                color: blue;
                font-size: 18px;
            }
        </style>
    </head>
    ```
3.  **外部样式表**（推荐）：将 CSS 规则写入单独的 `.css` 文件，然后在 HTML 中链接。
    *   `styles.css` 文件：
        ```css
        body {
            background-color: lightgray;
        }
        h1 {
            color: navy;
        }
        ```
    *   在 HTML 中链接：
        ```html
        <head>
            <link rel="stylesheet" href="styles.css">
        </head>
        ```
    这种方式利于代码分离和团队协作。

![](img/b24c2807aef11fc612696c6543042792_188.png)

![](img/b24c2807aef11fc612696c6543042792_190.png)

![](img/b24c2807aef11fc612696c6543042792_191.png)

### CSS 选择器
选择器用于指定哪些 HTML 元素应用样式规则。

![](img/b24c2807aef11fc612696c6543042792_193.png)

![](img/b24c2807aef11fc612696c6543042792_194.png)

![](img/b24c2807aef11fc612696c6543042792_196.png)

![](img/b24c2807aef11fc612696c6543042792_197.png)

*   **元素选择器**：按标签名选择。
    ```css
    p { color: green; }
    ```
*   **类选择器**（最常用）：按 `class` 属性选择。类名以 `.` 开头。
    ```css
    .center { text-align: center; }
    .large { font-size: 24px; }
    ```
    ```html
    <p class="center large">这个段落既居中又大号。</p>
    ```
*   **ID 选择器**：按 `id` 属性选择。ID 名以 `#` 开头。一个 ID 在页面中应唯一。
    ```css
    #header { background-color: yellow; }
    ```
    ```html
    <div id="header">页眉</div>
    ```

![](img/b24c2807aef11fc612696c6543042792_199.png)

![](img/b24c2807aef11fc612696c6543042792_201.png)

![](img/b24c2807aef11fc612696c6543042792_202.png)

![](img/b24c2807aef11fc612696c6543042792_203.png)

![](img/b24c2807aef11fc612696c6543042792_204.png)

### 层叠与继承
*   **层叠**：当多条规则应用于同一元素时，会根据**特异性**和**顺序**决定最终样式。
*   **继承**：某些属性（如 `color`, `font-family`）会从父元素继承到子元素。

![](img/b24c2807aef11fc612696c6543042792_206.png)

![](img/b24c2807aef11fc612696c6543042792_207.png)

![](img/b24c2807aef11fc612696c6543042792_209.png)

### 使用 CSS 框架
CSS 框架（如 **Bootstrap**）提供了预定义的样式类和组件，能极大加快开发并保证一致性。只需通过 `<link>` 引入其 CSS 文件，然后使用其定义的类名即可。

![](img/b24c2807aef11fc612696c6543042792_211.png)

![](img/b24c2807aef11fc612696c6543042792_213.png)

![](img/b24c2807aef11fc612696c6543042792_214.png)

![](img/b24c2807aef11fc612696c6543042792_216.png)

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet">
<table class="table table-striped">
  <!-- 表格内容 -->
</table>
```

![](img/b24c2807aef11fc612696c6543042792_218.png)

![](img/b24c2807aef11fc612696c6543042792_219.png)

![](img/b24c2807aef11fc612696c6543042792_220.png)

![](img/b24c2807aef11fc612696c6543042792_222.png)

![](img/b24c2807aef11fc612696c6543042792_223.png)

---

![](img/b24c2807aef11fc612696c6543042792_225.png)

![](img/b24c2807aef11fc612696c6543042792_226.png)

![](img/b24c2807aef11fc612696c6543042792_227.png)

![](img/b24c2807aef11fc612696c6543042792_228.png)

![](img/b24c2807aef11fc612696c6543042792_229.png)

![](img/b24c2807aef11fc612696c6543042792_231.png)

![](img/b24c2807aef11fc612696c6543042792_232.png)

## JavaScript：让网页动起来 ⚡

![](img/b24c2807aef11fc612696c6543042792_234.png)

![](img/b24c2807aef11fc612696c6543042792_235.png)

![](img/b24c2807aef11fc612696c6543042792_236.png)

![](img/b24c2807aef11fc612696c6543042792_237.png)

![](img/b24c2807aef11fc612696c6543042792_239.png)

![](img/b24c2807aef11fc612696c6543042792_241.png)

上一节我们使用 CSS 美化了网页的外观，本节中我们来看看如何使用 JavaScript 为网页添加交互逻辑。

![](img/b24c2807aef11fc612696c6543042792_243.png)

![](img/b24c2807aef11fc612696c6543042792_244.png)

![](img/b24c2807aef11fc612696c6543042792_245.png)

### 什么是 JavaScript？
JavaScript 是一种真正的**编程语言**，运行在浏览器中。它可以动态地读取和修改 HTML（DOM）与 CSS，响应用户操作，实现复杂的交互功能。

![](img/b24c2807aef11fc612696c6543042792_247.png)

![](img/b24c2807aef11fc612696c6543042792_248.png)

### 如何在 HTML 中使用 JavaScript？
1.  **内联事件处理器**（不推荐用于复杂逻辑）：
    ```html
    <button onclick="alert('Hello!')">点击我</button>
    ```
2.  **内部脚本**：使用 `<script>` 标签。
    ```html
    <script>
        function greet() {
            let name = document.querySelector('#name').value;
            alert('Hello, ' + name);
        }
    </script>
    <input type="text" id="name">
    <button onclick="greet()">打招呼</button>
    ```
3.  **外部脚本**（推荐）：将代码写入单独的 `.js` 文件，然后引入。
    ```html
    <head>
        <script src="script.js"></script>
    </head>
    ```

![](img/b24c2807aef11fc612696c6543042792_250.png)

### 操作 DOM
JavaScript 的核心能力之一是操作文档对象模型。

![](img/b24c2807aef11fc612696c6543042792_252.png)

![](img/b24c2807aef11fc612696c6543042792_254.png)

![](img/b24c2807aef11fc612696c6543042792_256.png)

![](img/b24c2807aef11fc612696c6543042792_257.png)

*   **选择元素**：
    ```javascript
    let myElement = document.querySelector('#myId'); // 通过 ID 选择
    let myElements = document.querySelectorAll('.myClass'); // 通过类选择所有
    ```
*   **修改内容与样式**：
    ```javascript
    myElement.innerHTML = '<strong>新内容</strong>'; // 修改 HTML 内容
    myElement.textContent = '新文本'; // 只修改文本
    myElement.style.color = 'red'; // 修改样式 (注意：JS 中用驼峰命名，如 backgroundColor)
    ```
*   **添加/移除元素**：
    ```javascript
    let newPara = document.createElement('p');
    newPara.textContent = '我是新段落！';
    document.body.appendChild(newPara);
    ```

![](img/b24c2807aef11fc612696c6543042792_259.png)

### 事件处理
JavaScript 采用**事件驱动**编程模型。你可以让代码“监听”特定事件（如点击、按键、鼠标移动），并在事件发生时执行函数。

![](img/b24c2807aef11fc612696c6543042792_261.png)

![](img/b24c2807aef11fc612696c6543042792_262.png)

![](img/b24c2807aef11fc612696c6543042792_263.png)

![](img/b24c2807aef11fc612696c6543042792_264.png)

![](img/b24c2807aef11fc612696c6543042792_266.png)

![](img/b24c2807aef11fc612696c6543042792_267.png)

```javascript
// 选择按钮
let myButton = document.querySelector('#myButton');

![](img/b24c2807aef11fc612696c6543042792_269.png)

![](img/b24c2807aef11fc612696c6543042792_270.png)

![](img/b24c2807aef11fc612696c6543042792_271.png)

![](img/b24c2807aef11fc612696c6543042792_273.png)

// 为按钮添加点击事件监听器
myButton.addEventListener('click', function(event) {
    // 阻止按钮的默认行为（如表单提交）
    event.preventDefault();
    // 执行你的代码
    console.log('按钮被点击了！');
    document.body.style.backgroundColor = 'lightblue';
});

![](img/b24c2807aef11fc612696c6543042792_275.png)

![](img/b24c2807aef11fc612696c6543042792_277.png)

![](img/b24c2807aef11fc612696c6543042792_279.png)

![](img/b24c2807aef11fc612696c6543042792_281.png)

// 监听键盘事件
document.addEventListener('keyup', function(event) {
    console.log(`你松开了键：${event.key}`);
});
```

![](img/b24c2807aef11fc612696c6543042792_283.png)

![](img/b24c2807aef11fc612696c6543042792_284.png)

![](img/b24c2807aef11fc612696c6543042792_286.png)

### 一个综合示例：动态背景色
以下代码展示了如何结合 HTML、CSS 和 JavaScript 创建一个交互式页面。

![](img/b24c2807aef11fc612696c6543042792_288.png)

![](img/b24c2807aef11fc612696c6543042792_289.png)

![](img/b24c2807aef11fc612696c6543042792_291.png)

![](img/b24c2807aef11fc612696c6543042792_292.png)

![](img/b24c2807aef11fc612696c6543042792_293.png)

![](img/b24c2807aef11fc612696c6543042792_295.png)

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        body { transition: background-color 0.5s; }
    </style>
</head>
<body>
    <button id="redBtn">红色</button>
    <button id="greenBtn">绿色</button>
    <button id="blueBtn">蓝色</button>

    <script>
        // 选择 body 元素
        let body = document.querySelector('body');

        // 为每个按钮添加点击事件
        document.querySelector('#redBtn').addEventListener('click', function() {
            body.style.backgroundColor = 'red';
        });
        document.querySelector('#greenBtn').addEventListener('click', function() {
            body.style.backgroundColor = 'green';
        });
        document.querySelector('#blueBtn').addEventListener('click', function() {
            body.style.backgroundColor = 'blue';
        });
    </script>
</body>
</html>
```

![](img/b24c2807aef11fc612696c6543042792_297.png)

![](img/b24c2807aef11fc612696c6543042792_298.png)

![](img/b24c2807aef11fc612696c6543042792_299.png)

![](img/b24c2807aef11fc612696c6543042792_301.png)

![](img/b24c2807aef11fc612696c6543042792_303.png)

![](img/b24c2807aef11fc612696c6543042792_304.png)

---

![](img/b24c2807aef11fc612696c6543042792_306.png)

![](img/b24c2807aef11fc612696c6543042792_307.png)

![](img/b24c2807aef11fc612696c6543042792_309.png)

![](img/b24c2807aef11fc612696c6543042792_310.png)

![](img/b24c2807aef11fc612696c6543042792_311.png)

![](img/b24c2807aef11fc612696c6543042792_312.png)

## 总结 🎓

![](img/b24c2807aef11fc612696c6543042792_313.png)

![](img/b24c2807aef11fc612696c6543042792_315.png)

![](img/b24c2807aef11fc612696c6543042792_317.png)

![](img/b24c2807aef11fc612696c6543042792_318.png)

![](img/b24c2807aef11fc612696c6543042792_319.png)

![](img/b24c2807aef11fc612696c6543042792_320.png)

![](img/b24c2807aef11fc612696c6543042792_321.png)

![](img/b24c2807aef11fc612696c6543042792_323.png)

本节课中我们一起学习了构建现代万维网的三大核心技术：

![](img/b24c2807aef11fc612696c6543042792_325.png)

![](img/b24c2807aef11fc612696c6543042792_327.png)

![](img/b24c2807aef11fc612696c6543042792_329.png)

![](img/b24c2807aef11fc612696c6543042792_330.png)

![](img/b24c2807aef11fc612696c6543042792_331.png)

1.  **HTML**：作为网页的**骨架**，它使用标签和属性来定义内容的结构和语义（如标题、段落、列表、链接、表单）。
2.  **CSS**：作为网页的**皮肤**，它使用选择器和属性-值对来控制内容的视觉表现（如颜色、字体、布局），实现了内容与样式的分离。
3.  **JavaScript**：作为网页的**肌肉**，它是一种编程语言，能够操作 DOM 和 CSS，响应用户事件，为网页注入**交互性**和动态行为。

![](img/b24c2807aef11fc612696c6543042792_333.png)

![](img/b24c2807aef11fc612696c6543042792_334.png)

![](img/b24c2807aef11fc612696c6543042792_336.png)

![](img/b24c2807aef11fc612696c6543042792_337.png)

![](img/b24c2807aef11fc612696c6543042792_339.png)

![](img/b24c2807aef11fc612696c6543042792_340.png)

![](img/b24c2807aef11fc612696c6543042792_342.png)

这三种语言各司其职，又紧密协作：HTML 提供结构，CSS 负责表现，JavaScript 控制行为。理解它们之间的关系，是理解当今网站和许多移动应用如何工作的关键。虽然我们只触及了这些技术的表面，但已经掌握了足以开始探索和创建简单网页的核心概念。