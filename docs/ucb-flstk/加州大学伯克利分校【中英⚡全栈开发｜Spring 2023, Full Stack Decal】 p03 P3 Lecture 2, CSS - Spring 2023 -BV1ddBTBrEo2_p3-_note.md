# 全栈开发：P3：CSS基础入门 🎨

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_0.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_2.png)

在本节课中，我们将要学习CSS的基础知识。CSS是层叠样式表的缩写，它负责网页的视觉表现，就像给HTML搭建的“骨架”房子进行装修和粉刷。没有CSS，网页将只有结构和内容，看起来会非常简陋。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_4.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_6.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_8.png)

---

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_10.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_12.png)

## 什么是CSS？

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_14.png)

上一节我们提到了CSS的作用。本节中我们来看看它的具体定义。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_16.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_17.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_18.png)

CSS是一种样式表语言，用于描述HTML文档的呈现方式。它控制着网页的布局、颜色、字体等视觉样式。你可以把它想象成网页的“设计师”。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_20.png)

一个没有加载CSS的网站（例如Facebook）看起来会非常糟糕，而加载了CSS后，页面会变得美观。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_22.png)

在HTML中，每个标签都可以拥有属性。例如，一个`<div>`标签可以有一个`class`属性，其值是一个字符串。这个`class`属性在CSS中会非常重要。

---

## 应用CSS的三种方式

现在，让我们看看如何将CSS应用到HTML元素上。主要有三种方法。

### 1. 内联样式

内联样式是直接将CSS规则写在HTML元素的`style`属性中。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_24.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_26.png)

```html
<h1 style="color: red; font-weight: bold;">这是一个标题</h1>
```

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_28.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_30.png)

在上面的代码中，`style`属性告诉浏览器这个`<h1>`元素需要应用CSS规则。规则写在属性值里，其语法是`属性名: 属性值;`，多个规则用分号隔开。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_32.png)

这种方式虽然直接，但会让HTML代码变得混乱，不利于维护。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_34.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_35.png)

### 2. 内部样式表

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_37.png)

内部样式表是将CSS规则集中写在HTML文档的`<style>`标签内。

```html
<style>
    .paragraph-one {
        color: red;
        font-weight: bold;
    }
</style>
<p class="paragraph-one">这是一个段落。</p>
```

这种方式比内联样式更整洁。我们通过给段落元素一个`class="paragraph-one"`，然后在`<style>`标签内使用选择器`.paragraph-one`来为所有具有该类的元素统一设置样式。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_39.png)

### 3. 外部样式表

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_41.png)

这是最推荐的方式，它将CSS代码完全分离到一个独立的`.css`文件中，然后在HTML中通过`<link>`标签引入。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_43.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_45.png)

**style.css 文件：**
```css
.important-paragraph {
    color: blue;
    font-weight: bold;
}
```

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_47.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_49.png)

**index.html 文件：**
```html
<head>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <p class="important-paragraph">这是一个重要的段落。</p>
</body>
```

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_51.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_53.png)

这种方式实现了内容与样式的彻底分离，使得代码结构清晰，易于管理和复用。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_55.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_57.png)

---

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_59.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_60.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_62.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_64.png)

## CSS选择器

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_66.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_68.png)

上一节我们学会了如何引入CSS。本节中我们来看看如何精确地选中想要样式化的元素，这需要通过**选择器**来实现。

选择器用于指定我们要样式化的HTML元素。以下是一些核心选择器：

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_70.png)

*   **元素选择器**：直接使用HTML标签名。
    ```css
    h1 { color: red; } /* 选中所有<h1>标签 */
    ```
*   **类选择器**：以一个点`.`开头，后跟类名。用于选中具有特定`class`属性的元素。
    ```css
    .important { color: blue; } /* 选中所有 class="important" 的元素 */
    ```
*   **ID选择器**：以一个井号`#`开头，后跟ID名。用于选中具有特定`id`属性的**唯一**元素。
    ```css
    #main-title { font-size: 50px; } /* 选中 id="main-title" 的元素 */
    ```

**核心概念**：
*   `class`（类）可以被多个元素共享。
*   `id`（标识符）在同一个HTML文档中应该是唯一的。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_72.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_73.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_75.png)

一个元素可以同时拥有多个类，用空格分隔：
```html
<p class="important silly">这个段落有两个类。</p>
```
你可以用组合选择器来选中它：
```css
.important.silly { text-decoration: underline; } /* 选中同时具有这两个类的元素 */
```

---

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_77.png)

## 更复杂的选择器

除了基本选择器，CSS还支持更复杂的关系选择器，用于描述元素之间的层级关系。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_79.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_80.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_82.png)

以下是几种常见的关系选择器：

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_84.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_86.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_88.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_90.png)

*   **后代选择器（空格）**：选中某个元素内部的所有特定后代元素。
    ```css
    .silly-paragraph .cool-paragraph { opacity: 0.5; }
    /* 选中所有在 class="silly-paragraph" 的元素内部的 class="cool-paragraph" 的元素 */
    ```
*   **子元素选择器（`>`）**：仅选中某个元素的直接子元素。
    ```css
    .silly-paragraph > .cool-paragraph { background-color: red; }
    /* 仅选中作为 .silly-paragraph 直接子元素的 .cool-paragraph */
    ```
*   **通用选择器（`*`）**：选中页面上的所有元素。
    ```css
    * { margin: 0; } /* 重置所有元素的外边距 */
    ```

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_92.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_94.png)

---

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_96.png)

## 常用的CSS属性

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_98.png)

现在我们已经知道如何选中元素了，接下来看看可以用哪些属性来改变它们的外观。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_100.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_101.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_103.png)

以下是一些最常用和基础的CSS属性：

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_105.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_107.png)

*   **颜色与背景**
    *   `color`: 设置文本颜色。值可以是颜色名（如`red`）、十六进制码（如`#ff0000`）、RGB值（如`rgb(255, 0, 0)`）或RGBA值（如`rgba(255, 0, 0, 0.5)`，最后一个参数是透明度）。
    *   `background-color`: 设置元素的背景颜色。
    *   `background-image`: 设置元素的背景图片。
    *   `opacity`: 设置元素的不透明度（0为完全透明，1为完全不透明）。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_109.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_111.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_113.png)

*   **文本与字体**
    *   `font-size`: 设置字体大小（如`16px`, `2rem`）。
    *   `font-family`: 设置字体族（如`Arial`, `"Microsoft YaHei"`）。
    *   `font-weight`: 设置字体粗细（如`normal`, `bold`）。
    *   `text-align`: 设置文本对齐方式（如`left`, `center`, `right`）。
    *   `text-decoration`: 设置文本装饰（如`underline`, `line-through`）。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_115.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_116.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_117.png)

*   **尺寸与边框**
    *   `width` / `height`: 设置元素的宽度和高度。单位可以是`px`（像素）、`%`（相对于父元素的百分比）、`vw`/`vh`（相对于视口宽度/高度的百分比）。
    *   `border`: 设置边框。是`border-width`、`border-style`、`border-color`的简写属性。例如：`border: 2px solid black;`。
    *   `border-radius`: 设置边框圆角（如`10px`）。
    *   `box-shadow`: 为元素添加阴影（如`box-shadow: 5px 5px 10px grey;`）。

---

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_119.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_121.png)

## 盒模型

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_123.png)

理解CSS的**盒模型**是进行网页布局的基石。每个HTML元素都被视为一个矩形的“盒子”，这个盒子由内到外由四部分组成：

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_125.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_127.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_128.png)

1.  **内容**：显示文本、图像等的实际区域，由`width`和`height`定义。
2.  **内边距**：内容与边框之间的透明区域，由`padding`控制。
3.  **边框**：围绕内边距和内容的线，由`border`控制。
4.  **外边距**：盒子与其他盒子之间的透明间隔区域，由`margin`控制。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_130.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_131.png)

**公式**：一个元素在页面上占据的总宽度 = `margin-left` + `border-left` + `padding-left` + `width` + `padding-right` + `border-right` + `margin-right`。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_133.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_134.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_135.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_137.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_139.png)

默认情况下，`width`和`height`只定义**内容区**的大小。添加`padding`和`border`会使元素的实际占用空间变大。这有时会导致布局计算困难。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_141.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_143.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_144.png)

为了解决这个问题，我们可以使用`box-sizing`属性：
```css
* {
    box-sizing: border-box;
}
```
当设置为`border-box`时，元素的`width`和`height`属性将包含**内容、内边距和边框**的总和。这意味着，如果你设置`width: 200px;`和`padding: 20px;`，内容区会自动调整以确保总宽度仍是200px。这极大地简化了布局工作，是推荐的实践。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_146.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_147.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_149.png)

---

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_150.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_152.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_154.png)

## 开发者工具

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_156.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_157.png)

在开发过程中，浏览器内置的**开发者工具**是你的得力助手。你可以通过右键点击页面元素并选择“检查”来打开它。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_159.png)

开发者工具允许你：
*   **实时查看和修改HTML/CSS**：你可以看到页面的结构，并直接修改样式，效果会立即在页面上呈现（仅在你的浏览器中）。
*   **调试布局**：可以直观地查看每个元素的盒模型（内容、内边距、边框、外边距），帮助你理解为什么元素会以某种方式排列。
*   **测试响应式设计**：可以模拟不同设备的屏幕尺寸。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_161.png)

---

## 其他要点与最佳实践

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_163.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_165.png)

*   **注释**：在CSS中，你可以使用`/* 注释内容 */`来添加注释，解释代码的作用。
*   **样式优先级（层叠）**：当多条规则作用于同一个元素时，CSS会根据**特异性**和**顺序**来决定最终应用的样式。通常，更具体的选择器（如ID选择器）会覆盖更通用的选择器（如元素选择器）。后定义的规则会覆盖先定义的规则（在特异性相同的情况下）。
*   **重置默认样式**：不同浏览器对HTML元素有默认的CSS样式（例如，`<body>`有默认的`margin`）。为了确保跨浏览器的一致性，通常会在项目开始使用一个“CSS重置”样式表来清除这些默认样式。
    ```css
    body { margin: 0; }
    ```

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_167.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_169.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_171.png)

---

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_173.png)

本节课中我们一起学习了CSS的基础知识。我们从CSS是什么开始，介绍了三种应用CSS的方法（内联、内部、外部），深入探讨了如何使用各种选择器来精确选中元素。然后，我们学习了一系列常用的CSS属性来改变元素的外观，并理解了网页布局的核心——盒模型。最后，我们了解了如何使用开发者工具进行调试，以及一些CSS的最佳实践。

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_175.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_177.png)

![](img/03d3b4df569bb49325d9fa75ee8a2ef2_179.png)

掌握这些基础知识是构建美观、结构清晰的网页的第一步。在接下来的课程中，我们将学习更复杂的CSS布局技术。