# 前端编程：1.1：HTML入门 🐲

在本节课中，我们将学习HTML的基础知识。HTML是构成所有网站结构的基本语言，是网页开发的起点。我们将了解HTML是什么、它的工作原理以及如何使用各种标签来构建网页内容。

![](img/cd248eb9c5afb9a81172ecfcf67a9836_1.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_2.png)

---

## 什么是HTML？🤔

![](img/cd248eb9c5afb9a81172ecfcf67a9836_4.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_6.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_7.png)

HTML代表超文本标记语言。它是构成互联网上任何网站的基本结构。简单来说，HTML是我们用来描述网页内容的语言。它更侧重于结构，而非外观样式。网页的动态效果和视觉样式将由后续学习的CSS和JavaScript来处理。

![](img/cd248eb9c5afb9a81172ecfcf67a9836_9.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_11.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_13.png)

## HTML如何工作？⚙️

![](img/cd248eb9c5afb9a81172ecfcf67a9836_15.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_17.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_19.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_20.png)

与Python或C等需要通过命令行编译或解释的语言不同，HTML的“编译器”就是我们日常使用的**网页浏览器**。浏览器会读取我们编写的HTML代码，并将其渲染成可视化的网页。

这意味着你甚至不需要安装任何特殊软件来运行HTML。只需将代码保存为 `.html` 文件，然后用浏览器打开它即可看到效果。

![](img/cd248eb9c5afb9a81172ecfcf67a9836_22.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_23.png)

**示例：**
```html
<!DOCTYPE html>
<html>
  <head>
    <title>我的第一个网页</title>
  </head>
  <body>
    <p>你好，世界！</p>
  </body>
</html>
```
将上述代码保存为 `page.html` 并用浏览器打开，你就能看到一个简单的网页。

![](img/cd248eb9c5afb9a81172ecfcf67a9836_25.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_26.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_27.png)

在浏览器中，你还可以通过“查看页面源代码”来查看任何网页背后的原始HTML代码。

![](img/cd248eb9c5afb9a81172ecfcf67a9836_29.png)

---

![](img/cd248eb9c5afb9a81172ecfcf67a9836_31.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_33.png)

## 网页的基本结构 🏗️

![](img/cd248eb9c5afb9a81172ecfcf67a9836_35.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_36.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_38.png)

一个标准的HTML文档通常包含以下几个关键部分：

![](img/cd248eb9c5afb9a81172ecfcf67a9836_40.png)

1.  **文档类型声明**：`<!DOCTYPE html>`。这告诉浏览器这是一个HTML5文档。虽然不是强制要求，但遵循最佳实践总是好的。
2.  **`<html>` 标签**：整个网页内容的根容器。
3.  **`<head>` 标签**：包含页面的**元信息**，如标题、字符集、引入的外部文件（CSS、JavaScript）等。这部分内容不会直接显示在页面上。
    *   **`<title>` 标签**：定义浏览器标签页上显示的标题。
4.  **`<body>` 标签**：包含所有会直接显示在网页上的内容，如文本、图片、链接等。

![](img/cd248eb9c5afb9a81172ecfcf67a9836_42.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_44.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_45.png)

**结构示例：**
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>页面标题</title>
  </head>
  <body>
    <!-- 所有可见内容都放在这里 -->
  </body>
</html>
```

![](img/cd248eb9c5afb9a81172ecfcf67a9836_47.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_49.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_50.png)

---

![](img/cd248eb9c5afb9a81172ecfcf67a9836_52.png)

## 常用布局与格式化标签 📐

![](img/cd248eb9c5afb9a81172ecfcf67a9836_54.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_56.png)

上一节我们介绍了网页的基本骨架，本节中我们来看看可以在 `<body>` 标签内使用的各种内容标签。这些标签用于定义内容的结构和基本格式。

![](img/cd248eb9c5afb9a81172ecfcf67a9836_58.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_60.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_61.png)

以下是HTML中一些最常用的布局和格式化标签：

![](img/cd248eb9c5afb9a81172ecfcf67a9836_63.png)

*   **标题**：`<h1>` 到 `<h6>` 标签用于定义标题，`<h1>` 最大，`<h6>` 最小。它们表示内容的结构层级。
    ```html
    <h1>主标题</h1>
    <h2>次级标题</h2>
    <h3>小标题</h3>
    ```
*   **段落**：`<p>` 标签用于定义段落。HTML会忽略普通的换行和空格，使用 `<p>` 标签可以正确地分隔文本块。
    ```html
    <p>这是第一个段落。</p>
    <p>这是第二个段落。</p>
    ```
*   **换行**：`<br>` 是一个**空标签**（没有闭合标签），用于在文本中强制换行。
    ```html
    第一行<br>第二行
    ```
*   **文本格式化**：
    *   `<b>`：**加粗**文本。
    *   `<i>`：*斜体*文本。
    *   `<u>`：<u>下划线</u>文本。
    ```html
    这是<b>加粗</b>，这是<i>斜体</i>，这是<u>下划线</u>的文本。
    ```
*   **列表**：
    *   **无序列表** `<ul>`：项目以圆点等符号开头。
    *   **有序列表** `<ol>`：项目以数字或字母顺序开头。
    *   **列表项** `<li>`：定义列表中的每一项。
    ```html
    <ul>
      <li>苹果</li>
      <li>香蕉</li>
    </ul>
    <ol>
      <li>第一步</li>
      <li>第二步</li>
    </ol>
    ```
*   **通用容器**：
    *   `<div>`：块级容器。默认独占一行，常用于布局和组合其他元素。
    *   `<span>`：行内容器。不会导致换行，常用于对文本的一部分进行样式设置。
    ```html
    <div>这是一个块级区域。</div>
    <div>这是另一个块级区域。</div>
    <p>这是一段<span style="color: red;">红色</span>的文字。</p>
    ```

![](img/cd248eb9c5afb9a81172ecfcf67a9836_65.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_67.png)

---

![](img/cd248eb9c5afb9a81172ecfcf67a9836_69.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_70.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_71.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_73.png)

## 链接与媒体 🔗

![](img/cd248eb9c5afb9a81172ecfcf67a9836_75.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_76.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_77.png)

除了基本的文本和布局，HTML还能轻松地嵌入链接和多媒体内容，让网页变得丰富多彩。

### 链接（锚点标签）

![](img/cd248eb9c5afb9a81172ecfcf67a9836_79.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_80.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_82.png)

`<a>` 标签用于创建超链接，可以链接到其他网页、同一页面的不同部分或文件。

![](img/cd248eb9c5afb9a81172ecfcf67a9836_84.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_86.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_87.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_88.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_90.png)

**核心属性：**
*   `href`：指定链接的目标地址（URL）。
*   `title`：鼠标悬停在链接上时显示的提示文本。
*   `target`：指定如何打开链接。`_blank` 表示在新标签页中打开。

![](img/cd248eb9c5afb9a81172ecfcf67a9836_92.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_94.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_96.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_97.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_98.png)

**示例：**
```html
<a href="https://www.example.com" title="访问示例网站" target="_blank">点击这里</a>
```

### 图像标签

![](img/cd248eb9c5afb9a81172ecfcf67a9836_100.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_102.png)

`<img>` 标签用于在网页中嵌入图像。它也是一个**空标签**。

**核心属性：**
*   `src`：指定图像文件的路径（可以是网络URL或本地文件路径）。
*   `alt`：为图像提供替代文本。如果图像无法加载，将显示此文本。这对可访问性和SEO非常重要。
*   `width` / `height`：设置图像的宽度和高度（单位是像素）。

![](img/cd248eb9c5afb9a81172ecfcf67a9836_104.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_106.png)

**示例：**
```html
<img src="minidog.jpg" alt="一只可爱的小狗" width="400" height="300">
```

![](img/cd248eb9c5afb9a81172ecfcf67a9836_108.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_110.png)

### 高级媒体嵌入

![](img/cd248eb9c5afb9a81172ecfcf67a9836_112.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_113.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_115.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_117.png)

HTML5引入了原生支持多媒体内容的标签。

![](img/cd248eb9c5afb9a81172ecfcf67a9836_119.png)

*   **视频**：`<video>` 标签用于嵌入视频。
    ```html
    <video width="500" controls>
      <source src="meeting.mov" type="video/mp4">
      您的浏览器不支持视频标签。
    </video>
    ```
*   **音频**：`<audio>` 标签用于嵌入音频。
    ```html
    <audio controls>
      <source src="sound.mp3" type="audio/mpeg">
      您的浏览器不支持音频元素。
    </audio>
    ```
*   **内嵌框架**：`<iframe>` 标签用于在当前网页中嵌入另一个网页。
    ```html
    <iframe src="https://www.example.com" width="800" height="600"></iframe>
    ```

![](img/cd248eb9c5afb9a81172ecfcf67a9836_121.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_122.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_124.png)

---

![](img/cd248eb9c5afb9a81172ecfcf67a9836_126.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_127.png)

## 表单：与用户交互 📝

表单是网页与用户交互的核心组件，用于收集用户输入的数据，例如登录框、搜索栏、调查问卷等。

![](img/cd248eb9c5afb9a81172ecfcf67a9836_129.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_131.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_133.png)

`<form>` 标签用于创建一个包含各种输入控件的表单区域。虽然其传统的提交机制（`action`， `method`）在现代前端开发中不常直接使用，但其中的输入元素本身极其重要。

![](img/cd248eb9c5afb9a81172ecfcf67a9836_135.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_136.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_137.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_138.png)

以下是表单中常见的输入元素：

![](img/cd248eb9c5afb9a81172ecfcf67a9836_140.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_142.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_143.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_145.png)

*   **文本输入**：`<input type="text">` 是最基本的单行文本框。
    ```html
    <input type="text" name="username" placeholder="请输入用户名">
    ```
*   **数字输入**：`<input type="number">` 只允许输入数字，并带有调节按钮。
*   **单选按钮**：`<input type="radio">` 用于从一组选项中选择**一项**。通过给同一组的单选按钮设置相同的 `name` 属性来实现互斥。
    ```html
    <input type="radio" id="age1" name="age" value="18-25">
    <label for="age1">18-25</label>
    <input type="radio" id="age2" name="age" value="26-35">
    <label for="age2">26-35</label>
    ```
*   **复选框**：`<input type="checkbox">` 用于从一组选项中选择**多项**。
    ```html
    <input type="checkbox" id="hobby1" name="hobby" value="dancing">
    <label for="hobby1">跳舞</label>
    <input type="checkbox" id="hobby2" name="hobby" value="singing">
    <label for="hobby2">唱歌</label>
    ```
*   **下拉选择框**：`<select>` 和 `<option>` 标签结合创建下拉列表，适用于选项较多的情况。
    ```html
    <select name="city">
      <option value="bj">北京</option>
      <option value="sh" selected>上海</option>
      <option value="gz">广州</option>
    </select>
    ```
*   **多行文本域**：`<textarea>` 用于输入多行文本。
    ```html
    <textarea name="comments" rows="4" cols="50" placeholder="请输入您的意见..."></textarea>
    ```
*   **标签**：`<label>` 标签用于关联文本和表单控件，提高可用性。点击标签文字也能选中对应的控件。使用 `for` 属性指向控件的 `id`。
*   **按钮**：
    *   `<button type="button">点击我</button>`：通用按钮，通常与JavaScript配合使用。
    *   `<input type="submit" value="提交">`：传统的表单提交按钮。

![](img/cd248eb9c5afb9a81172ecfcf67a9836_147.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_149.png)

---

![](img/cd248eb9c5afb9a81172ecfcf67a9836_151.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_153.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_154.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_156.png)

## 总结 🎯

![](img/cd248eb9c5afb9a81172ecfcf67a9836_158.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_160.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_161.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_162.png)

本节课中我们一起学习了HTML的基础知识。我们了解到：

![](img/cd248eb9c5afb9a81172ecfcf67a9836_164.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_165.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_167.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_169.png)

1.  **HTML（超文本标记语言）** 是构建网页内容的**结构性**语言。
2.  **网页浏览器**充当了HTML的“编译器”，将代码渲染成可视化的页面。
3.  一个标准的HTML文档包含 `<!DOCTYPE html>`、`<html>`、`<head>` 和 `<body>` 等基本结构。
4.  我们学习了多种**布局标签**（如 `<h1>`-`<h6>`、`<p>`、`<div>`、`<span>`、列表、表格）来组织内容。
5.  我们掌握了如何使用**链接** (`<a>`)、**图像** (`<img>`) 和**多媒体** (`<video>`、`<audio>`) 标签来丰富页面。
6.  最后，我们探索了**表单** (`<form>`) 及其各种输入控件（文本、单选、复选、下拉框等），这是实现用户交互的基础。

![](img/cd248eb9c5afb9a81172ecfcf67a9836_171.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_172.png)

![](img/cd248eb9c5afb9a81172ecfcf67a9836_174.png)

记住，HTML主要负责网页的**骨架和结构**。在接下来的课程中，我们将学习CSS来为这个骨架添加样式，以及使用JavaScript来让它动起来。