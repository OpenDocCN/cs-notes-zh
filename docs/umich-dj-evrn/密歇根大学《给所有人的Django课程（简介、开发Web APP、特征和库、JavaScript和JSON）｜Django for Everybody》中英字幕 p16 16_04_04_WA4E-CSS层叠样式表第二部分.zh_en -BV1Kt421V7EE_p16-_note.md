# Django for Everybody：16：CSS层叠样式表第二部分

## 概述

![](img/44eaf2d459d7a251a65e8ca550eeecc7_1.png)

在本节课中，我们将学习如何在HTML中使用CSS，具体探讨将CSS规则应用到HTML不同部分的三种基本方法。我们还将了解`<span>`和`<div>`这两个没有默认样式的特殊标签，以及如何使用ID和类选择器来精确地选择和控制页面元素。

## CSS与HTML的结合方式

上一节我们介绍了CSS的基本语法，本节中我们来看看如何将CSS规则应用到HTML文档中。主要有三种方法。

### 1. 内联样式

最简单但最少用的方法是使用内联样式。你可以在任何HTML标签上使用`style`属性，并在其中直接写入CSS规则。

**示例代码：**
```html
<p style="border-style: solid; border-color: red; border-width: 5px; font-family: monospace;">
  这是一个带有红色边框和等宽字体的段落。
</p>
<body style="font-family: Arial, sans-serif;">
  ...
</body>
```

在这个例子中，`<p>`标签被设置为红色实线边框和等宽字体，而`<body>`标签则设置了Arial字体。由于`<p>`标签的样式声明更“接近”元素本身，所以它的`font-family`设置会覆盖`<body>`的全局设置。这体现了“层叠”的核心概念：**距离目标元素越近的样式声明，优先级越高**（除非使用了`!important`规则，我们稍后会讨论）。

![](img/44eaf2d459d7a251a65e8ca550eeecc7_3.png)

![](img/44eaf2d459d7a251a65e8ca550eeecc7_4.png)

### 2. 内部样式表

另一种方法是将CSS规则放在HTML文档的`<head>`区域内的`<style>`标签中。

**示例代码：**
```html
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      font-family: Arial, sans-serif;
    }
    h1 {
      color: blue;
    }
    p {
      border-style: solid;
      border-color: red;
      border-width: 5px;
    }
    a {
      color: green;
      text-decoration: none;
      background-color: lightgray;
    }
  </style>
</head>
<body>
  <!-- 页面内容 -->
</body>
</html>
```

这样，所有`<body>`内的元素都会继承Arial字体，所有`<h1>`标题会变成蓝色，所有`<p>`段落会有红色边框，所有`<a>`链接会变成绿色无下划线且背景为浅灰色。这种方法适用于单个页面，但当网站有多个页面时，维护起来会很麻烦。

### 3. 外部样式表

最常用、最推荐的方法是将CSS规则写入一个单独的文件（`.css`文件），然后在HTML中通过`<link>`标签引入。

![](img/44eaf2d459d7a251a65e8ca550eeecc7_6.png)

![](img/44eaf2d459d7a251a65e8ca550eeecc7_7.png)

**HTML文件 (`index.html`)：**
```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="rules.css">
</head>
<body>
  <!-- 页面内容 -->
</body>
</html>
```

**CSS文件 (`rules.css`)：**
```css
body {
  font-family: Arial, sans-serif;
}
h1 {
  color: blue;
}
p {
  border-style: solid;
  border-color: red;
  border-width: 5px;
}
a {
  color: green;
  text-decoration: none;
  background-color: lightgray;
}
```

浏览器会单独请求`rules.css`文件，并将其中的规则应用到HTML文档中。这种方法便于在多页面间共享和复用样式，也利于维护。

### 三种方式的优先级与协作

通常，最佳实践是：
1.  **主要样式放在外部样式表**中。
2.  对于某个页面特有的微调，使用**内部样式表**（`<style>`标签）。
3.  对于极个别元素的特殊样式，使用**内联样式**。

![](img/44eaf2d459d7a251a65e8ca550eeecc7_9.png)

![](img/44eaf2d459d7a251a65e8ca550eeecc7_10.png)

![](img/44eaf2d459d7a251a65e8ca550eeecc7_12.png)

它们的优先级遵循“层叠”原则：**内联样式 > 内部样式表 > 外部样式表**（同样，距离元素越近优先级越高）。你可以通过这种组合方式，灵活地控制整个网站的外观。

## 无默认样式的标签：`<span>` 与 `<div>`

随着CSS的普及，开发者需要一些“干净”的标签作为画布，以便完全通过CSS来控制样式，而不受HTML标签历史默认样式的影响。这就是`<span>`和`<div>`的用途。

以下是它们的关键区别：
*   **`<span>`**：是一个**行内元素**，本身没有任何默认样式（如边距、边框）。它用于对一小段行内文本进行样式化或分组。
*   **`<div>`**：是一个**块级元素**，本身同样没有任何默认样式。它用于定义文档中的分区或节，是页面布局的基石。

**示例代码：**
```html
<p style="border: 1px solid green;">这是一个有默认边距的段落。</p>
<div style="border: 1px solid blue;">这是一个没有边距的div块。</div>
<span style="color: green;">这是一段被span包裹的绿色文字。</span>
<div style="border: 1px solid orange;">
  <div style="border: 1px solid red;">这是一个嵌套在橙色div内的红色div。</div>
</div>
```

`<p>`标签本身有默认的边距（margin）和内边距（padding），使其看起来更美观。而`<div>`和`<span>`则从零开始，你需要通过CSS为其添加所有样式，包括布局、边距、颜色等。这使得它们成为构建复杂页面布局的理想选择。

## 精确选择：ID 与 类选择器

我们经常需要更精确地选择特定元素来应用样式，而不是针对所有同类标签。这时就需要使用ID和类选择器。

![](img/44eaf2d459d7a251a65e8ca550eeecc7_14.png)

### ID 选择器

ID属性在单个HTML文档中应该是**唯一**的。它用于标识页面中一个特定的、唯一的元素（如页头、主内容区）。

**CSS中使用 `#` 来指定ID选择器。**

**示例代码：**
```html
<style>
  #first {
    background-color: lightblue;
    padding: 10px;
  }
</style>
<div id="first">这个div拥有唯一的ID“first”。</div>
```

### 类选择器

![](img/44eaf2d459d7a251a65e8ca550eeecc7_16.png)

类属性可以在单个HTML文档中用于**多个**元素。它用于标识一组具有相同样式的元素。

**CSS中使用 `.` 来指定类选择器。**

**示例代码：**
```html
<style>
  .highlight {
    background-color: yellow;
  }
  .center {
    text-align: center;
  }
</style>
<p class="highlight">这个段落被高亮。</p>
<p class="highlight center">这个段落同时被高亮和居中。</p>
```

### 组合与层级选择

你可以组合使用这些选择器，实现更精细的控制。

以下是几种高级选择器用法：
*   **多个类**：一个元素可以拥有多个类（如 `class=“shout loud”`），它将同时应用这两个类定义的所有样式。
*   **后代选择器**：可以选择特定元素内部的元素。

![](img/44eaf2d459d7a251a65e8ca550eeecc7_18.png)

**示例代码：**
```html
<style>
  /* 选择类为“shout”的元素 */
  .shout {
    text-transform: uppercase; /* 文字转为大写 */
  }
  /* 选择类为“loud”的元素 */
  .loud {
    color: red;
  }
  /* 选择ID为“third”的元素内部的所有<p>标签 */
  #third p {
    background-color: lightyellow;
  }
</style>

<p class=“shout loud”>这段文字既是红色又是大写。</p>

<div id=“third”>
  <p>这个段落背景是浅黄色。</p>
  <p>这个段落背景也是浅黄色。</p>
</div>
<p>这个段落不受影响，背景不是浅黄色。</p>
```

使用后代选择器（如 `#third p`）可以避免给内部每个`<p>`标签都单独添加类名，使代码更简洁。

## 总结

本节课中我们一起学习了：
1.  将CSS融入HTML的三种方式：**内联样式**、**内部样式表**和**外部样式表**，理解了它们之间的**优先级（层叠）**关系。
2.  认识了两个没有默认样式的关键HTML标签：行内元素 **`<span>`** 和块级元素 **`<div>`**，它们是现代网页布局的基础。
3.  掌握了如何使用 **ID选择器 (`#id`)** 和 **类选择器 (`.class`)** 来精确选择页面元素，并了解了**后代选择器**等高级用法，从而能够更高效、更有针对性地控制页面样式。

![](img/44eaf2d459d7a251a65e8ca550eeecc7_20.png)

下一节，我们将探讨如何使用CSS来设置图片、颜色和字体等具体样式属性。