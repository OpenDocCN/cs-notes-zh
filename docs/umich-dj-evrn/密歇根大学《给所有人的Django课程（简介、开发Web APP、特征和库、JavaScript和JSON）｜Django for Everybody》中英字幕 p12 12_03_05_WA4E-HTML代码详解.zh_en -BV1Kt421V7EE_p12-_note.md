# Django for Everybody：12：HTML代码详解 🧑‍💻

![](img/a11a028d71b34f17dcaea3ade8516f08_1.png)

在本节课中，我们将通过分析示例代码来深入了解HTML。我们将探讨文档对象模型与源代码的区别，并逐一解析常见的HTML元素和结构。

![](img/a11a028d71b34f17dcaea3ade8516f08_2.png)

## 概述

![](img/a11a028d71b34f17dcaea3ade8516f08_4.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_5.png)

我们将通过一个示例HTML文件，学习如何查看源代码和文档对象模型，理解它们之间的差异，并探索段落、链接、列表、特殊字符、图像和表格等基本HTML元素的用法。

![](img/a11a028d71b34f17dcaea3ade8516f08_7.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_8.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_9.png)

---

## 文档对象模型与源代码 🔍

![](img/a11a028d71b34f17dcaea3ade8516f08_11.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_12.png)

上一节我们介绍了课程目标，本节中我们来看看HTML代码的两个重要视图：源代码和文档对象模型。

![](img/a11a028d71b34f17dcaea3ade8516f08_14.png)

源代码是服务器发送给浏览器的原始文件内容。你可以通过浏览器的“查看页面源代码”功能看到它。

文档对象模型是浏览器解析源代码后生成的结构化表示。它更“整洁”，并且可以通过开发者工具动态修改。在开发者工具的“元素”面板中看到的就是DOM。

![](img/a11a028d71b34f17dcaea3ade8516f08_16.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_18.png)

**核心概念**：
*   **源代码**：原始的、静态的HTML文件。
    ```html
    <p>这是一个未闭合的段落</p>
    ```
*   **文档对象模型**：浏览器解析后生成的、可交互的树状结构。
    ```javascript
    // DOM可以通过JavaScript动态修改
    document.querySelector('p').textContent = '修改后的内容';
    ```

![](img/a11a028d71b34f17dcaea3ade8516f08_20.png)

两者关键区别在于：**源代码是固定不变的，而DOM可以被JavaScript动态改变**。

---

![](img/a11a028d71b34f17dcaea3ade8516f08_22.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_24.png)

## 基础文档结构 📄

![](img/a11a028d71b34f17dcaea3ade8516f08_26.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_27.png)

以下是HTML文档的基本骨架。

![](img/a11a028d71b34f17dcaea3ade8516f08_28.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_29.png)

```html
<!DOCTYPE html>
<html>
<head>
    <title>页面标题</title>
</head>
<body>
    <!-- 页面内容在这里 -->
</body>
</html>
```

![](img/a11a028d71b34f17dcaea3ade8516f08_31.png)

在示例中，`<head>`标签包含元信息，`<body>`标签包含所有可见内容。浏览器会忽略HTML中多余的空格和换行，渲染时将它们压缩。

![](img/a11a028d71b34f17dcaea3ade8516f08_33.png)

---

![](img/a11a028d71b34f17dcaea3ade8516f08_35.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_36.png)

## 文本与段落标签

![](img/a11a028d71b34f17dcaea3ade8516f08_37.png)

现在，我们来学习如何组织文本内容。

![](img/a11a028d71b34f17dcaea3ade8516f08_39.png)

以下是常用的文本级标签：
*   `<p>`：定义段落。浏览器会自动在段落前后添加一些边距。
*   `<strong>`：加粗文本，表示重要性。
*   `<em>`：倾斜文本，表示强调。
*   `<a>`：定义超链接。`href`属性指定链接地址，标签之间的文本是可点击的。
*   `<pre>`：预格式化文本。它会保留源代码中的所有空格和换行，并使用等宽字体显示，常用于展示代码。

![](img/a11a028d71b34f17dcaea3ade8516f08_41.png)

**注意**：`<a>`标签的`href`属性可以使用相对路径（如`list.htm`）或绝对路径（如`https://www.example.com`）。浏览器会将相对路径转换为完整的绝对URL。

![](img/a11a028d71b34f17dcaea3ade8516f08_43.png)

---

![](img/a11a028d71b34f17dcaea3ade8516f08_45.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_46.png)

## 列表与导航 🧭

列表是组织一系列项目的有效方式。在示例中，一个无序列表`<ul>`被用作导航菜单。

![](img/a11a028d71b34f17dcaea3ade8516f08_48.png)

以下是列表的结构解析：
*   整个列表由`<ul>`开始，`</ul>`结束。
*   列表中的每一项都由`<li>`标签包裹。
*   可以在`<li>`标签内部使用`<p>`标签来增加项目之间的间距。

![](img/a11a028d71b34f17dcaea3ade8516f08_50.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_51.png)

这个结构清晰地展示了如何用HTML创建层次化的导航链接。

---

## 特殊字符

![](img/a11a028d71b34f17dcaea3ade8516f08_53.png)

在HTML中，某些字符具有特殊含义，必须使用实体引用来表示。

![](img/a11a028d71b34f17dcaea3ade8516f08_55.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_57.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_58.png)

以下是必须转义的核心字符及其代码：
*   小于号 `<`：`&lt;`
*   大于号 `>`：`&gt;`
*   和号 `&`：`&amp;`

![](img/a11a028d71b34f17dcaea3ade8516f08_60.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_62.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_64.png)

此外，还可以使用实体引用显示各种符号，例如：
*   黑桃 ♠：`&spades;`
*   红心 ♥：`&hearts;`
*   方块 ♦：`&diams;`

![](img/a11a028d71b34f17dcaea3ade8516f08_65.png)

浏览器内置了这些字符的显示支持。

![](img/a11a028d71b34f17dcaea3ade8516f08_67.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_68.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_70.png)

---

## 链接与图像 🌐

![](img/a11a028d71b34f17dcaea3ade8516f08_72.png)

链接和图像是网页最基本的媒体元素。

关于链接的更多细节：
*   `<a>`标签的`target="_blank"`属性可以让链接在新标签页中打开。
*   链接的样式会随状态改变（例如，访问过的链接通常会变成紫色）。

![](img/a11a028d71b34f17dcaea3ade8516f08_74.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_76.png)

图像通过`<img>`标签嵌入。
*   `src`属性指定图像文件的路径（可以是相对或绝对路径）。
*   图像默认像一个大字符一样嵌入在文本流中。
*   可以将`<img>`标签放在`<a>`标签内部，从而创建一个可点击的图片链接。

![](img/a11a028d71b34f17dcaea3ade8516f08_78.png)

---

## 表格 📊

![](img/a11a028d71b34f17dcaea3ade8516f08_80.png)

表格用于展示行列数据，不应再用于整个页面的布局。

![](img/a11a028d71b34f17dcaea3ade8516f08_82.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_83.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_84.png)

一个基本的表格结构如下：
```html
<table>
    <thead>
        <tr><th>标题1</th><th>标题2</th></tr>
    </thead>
    <tbody>
        <tr><td>数据A</td><td>数据B</td></tr>
    </tbody>
</table>
```

即使源代码中遗漏了`<tbody>`标签，浏览器在构建DOM时也会自动补全，以确保结构的正确性。这再次体现了DOM是经过浏览器“修复”和标准化后的版本。

![](img/a11a028d71b34f17dcaea3ade8516f08_86.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_87.png)

---

## 容错性与错误HTML ⚠️

![](img/a11a028d71b34f17dcaea3ade8516f08_89.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_90.png)

HTML规范具有很强的容错性。浏览器会尝试修复一些常见的代码错误。

![](img/a11a028d71b34f17dcaea3ade8516f08_92.png)

浏览器会自动修正的错误包括：
*   标签名大小写不统一（会统一转为小写）。
*   某些标签未正确闭合（会尝试自动闭合）。
*   属性值缺少引号（会尝试补全）。

![](img/a11a028d71b34f17dcaea3ade8516f08_94.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_95.png)

**重要提示**：尽管浏览器会修复错误，但编写符合标准的HTML至关重要。依赖浏览器的纠错可能导致不可预测的渲染结果，尤其是在复杂的页面或不同的浏览器中。始终使用验证工具检查你的代码。

![](img/a11a028d71b34f17dcaea3ade8516f08_97.png)

---

![](img/a11a028d71b34f17dcaea3ade8516f08_99.png)

![](img/a11a028d71b34f17dcaea3ade8516f08_101.png)

## 总结

![](img/a11a028d71b34f17dcaea3ade8516f08_103.png)

本节课中我们一起学习了HTML的核心实践。
我们区分了**源代码**和**文档对象模型**，理解了DOM是动态且可变的。
我们练习了使用段落、强调、链接、列表、特殊字符、图像和表格等基本元素来构建内容。
我们还了解到浏览器会尝试修复有瑕疵的HTML代码，但开发者仍应致力于编写清晰、标准的代码。

![](img/a11a028d71b34f17dcaea3ade8516f08_105.png)

通过操作示例代码，你现在应该对HTML如何工作以及如何在浏览器中检查和调试它有了更直观的认识。