# 给所有人的Django课程：P18：CSS代码详解第一部分 🎨

![](img/c9c6b8fde670dc006d36d88d35a33eca_1.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_2.png)

在本节课中，我们将学习层叠样式表（CSS）的基础知识。我们将了解如何将样式应用于HTML元素，探索CSS的“层叠”特性，并学习如何使用选择器、类（class）和ID来精确控制网页的外观。

---

![](img/c9c6b8fde670dc006d36d88d35a33eca_4.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_5.png)

## CSS简介与基本语法

![](img/c9c6b8fde670dc006d36d88d35a33eca_7.png)

层叠样式表（CSS）用于控制网页的视觉呈现。CSS可以通过多种方式应用到HTML元素上。

![](img/c9c6b8fde670dc006d36d88d35a33eca_9.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_10.png)

以下是应用CSS的几种基本方式：
*   **内联样式**：直接在HTML标签的`style`属性中定义样式。例如：`<p style="color: blue;">`。
*   **内部样式表**：在HTML文档的`<head>`部分使用`<style>`标签定义样式规则。
*   **外部样式表**：将样式规则写入独立的`.css`文件，然后在HTML中通过`<link>`标签引入。

![](img/c9c6b8fde670dc006d36d88d35a33eca_12.png)

一个CSS规则由**选择器**和**声明块**组成。声明块包含一个或多个用分号分隔的**属性-值**对。其基本语法如下：
```css
选择器 {
    属性1: 值1;
    属性2: 值2;
}
```
例如，`color: blue;` 中，`color`是属性，`blue`是值。

![](img/c9c6b8fde670dc006d36d88d35a33eca_14.png)

---

![](img/c9c6b8fde670dc006d36d88d35a33eca_16.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_17.png)

## 理解“层叠”与开发者工具

上一节我们介绍了CSS的基本语法，本节中我们来看看CSS的核心特性——“层叠”。CSS的“C”代表“Cascading”（层叠），这意味着样式可以来自多个来源，并且有明确的优先级规则。

![](img/c9c6b8fde670dc006d36d88d35a33eca_19.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_20.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_21.png)

我们可以使用浏览器的开发者工具来直观地查看和理解这些规则。在工具中选中一个元素，可以看到应用到它身上的所有CSS规则，并了解它们的来源（用户代理样式表、作者样式表、内联样式等）和优先级。

“层叠”的规则是：**越具体、越靠近元素的样式，优先级越高**。例如，内联样式（直接写在标签上的`style`）的优先级高于在`<style>`标签或外部样式表中定义的样式。

![](img/c9c6b8fde670dc006d36d88d35a33eca_23.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_24.png)

---

## 常用CSS属性示例

了解了层叠原理后，让我们通过一些具体的属性来实践如何改变元素的外观。

以下是一些常用的CSS属性及其效果：
*   **`color`**：设置文本颜色，如 `color: blue;`。
*   **`font-family`**：设置字体。可以指定一个字体栈，浏览器会依次尝试。例如 `font-family: Arial, sans-serif;` 表示优先使用Arial字体，如果不可用则使用任何无衬线字体。
*   **`border`**：为元素添加边框。这是一个简写属性，可以同时设置边框的样式、颜色和宽度。例如 `border: 5px solid red;` 会创建一个5像素宽的红色实线边框。在调试布局时，临时给元素加边框是查看其占据空间的常用技巧。
*   **`margin`** 和 **`padding`**：控制元素的外边距和内边距。`margin-top: 1em;` 会在元素上方增加一个字符高度的空间。`em`是一个相对单位，表示当前字体尺寸的倍数，在响应式设计中非常有用。

![](img/c9c6b8fde670dc006d36d88d35a33eca_26.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_27.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_28.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_29.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_30.png)

---

![](img/c9c6b8fde670dc006d36d88d35a33eca_32.png)

## 使用选择器应用样式

![](img/c9c6b8fde670dc006d36d88d35a33eca_34.png)

上一节我们直接在元素上写样式，但给每个标签都添加内联样式是不现实的。本节中我们来看看如何使用选择器来批量应用样式规则。

![](img/c9c6b8fde670dc006d36d88d35a33eca_36.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_37.png)

我们可以在`<style>`标签或外部CSS文件中编写规则。选择器用于“选中”我们想要样式化的HTML元素。

![](img/c9c6b8fde670dc006d36d88d35a33eca_39.png)

以下是几种基本选择器的用法：
*   **元素选择器**：直接使用HTML标签名。例如，`p { ... }` 会选中页面中所有的`<p>`段落标签。
*   **ID选择器**：使用`#`号加上元素的`id`属性值。ID在页面中应该是唯一的。例如，`#first { ... }` 会选中 `id="first"` 的那个元素。
*   **类选择器**：使用`.`号加上元素的`class`属性值。类可以被多个元素共享。例如，`.shout { ... }` 会选中所有 `class="shout"` 的元素。

![](img/c9c6b8fde670dc006d36d88d35a33eca_41.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_42.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_44.png)

一个元素可以拥有多个类，用空格分隔，如 `class="shout more-space"`，这样它会同时应用`.shout`和`.more-space`两个类的样式。

![](img/c9c6b8fde670dc006d36d88d35a33eca_46.png)

---

## 组织代码：外部样式表

![](img/c9c6b8fde670dc006d36d88d35a33eca_48.png)

当样式规则越来越多，或者网站有多个页面时，将CSS代码写在每个HTML文件里会变得难以维护。本节中我们来看看如何将样式提取到外部文件中。

![](img/c9c6b8fde670dc006d36d88d35a33eca_50.png)

我们创建一个独立的文件，例如 `style.css`，将所有的CSS规则放入其中。然后在HTML文件的`<head>`部分，通过一行代码引入它：
```html
<link rel="stylesheet" href="style.css">
```
这样做的好处是：
1.  **代码复用**：多个HTML页面可以共享同一个CSS文件，保持网站风格一致。
2.  **结构清晰**：实现了内容（HTML）与表现（CSS）的分离，便于管理和维护。
3.  **提高性能**：浏览器可以缓存CSS文件，加速后续页面的加载。

---

![](img/c9c6b8fde670dc006d36d88d35a33eca_52.png)

## 结构标签：`<div>` 与 `<span>`

![](img/c9c6b8fde670dc006d36d88d35a33eca_54.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_55.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_56.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_57.png)

为了更灵活地应用样式，我们经常需要给HTML内容添加“钩子”。本节中我们来看看两个没有默认样式的通用容器标签：`<div>`和`<span>`。

![](img/c9c6b8fde670dc006d36d88d35a33eca_59.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_61.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_63.png)

它们的主要区别和用途如下：
*   **`<div>` 标签**：是一个块级元素，用于组合其他元素，本身不带有任何默认样式（如段落那样的外边距）。它常用于布局和作为CSS样式化的容器。
*   **`<span>` 标签**：是一个行内元素，用于对文本的一部分进行组合或样式化，同样没有默认样式。

![](img/c9c6b8fde670dc006d36d88d35a33eca_65.png)

通过为`<div>`和`<span>`添加`class`或`id`属性，我们可以精确地对文档中的特定部分应用复杂的CSS样式。

![](img/c9c6b8fde670dc006d36d88d35a33eca_67.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_68.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_70.png)

---

![](img/c9c6b8fde670dc006d36d88d35a33eca_72.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_74.png)

## 组合与层级选择器

![](img/c9c6b8fde670dc006d36d88d35a33eca_76.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_78.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_80.png)

仅仅使用基本的类选择器有时还不够精确。本节中我们来看看如何组合选择器，以选中更特定的元素。

我们可以通过空格来组合选择器，表示层级关系。例如：
*   `#third p { background-color: yellow; }`
这条规则的意思是：**选中`id`为`third`的元素内部的所有`<p>`段落标签**，并将它们的背景色设为黄色。它不会影响`#third`外部的段落，也不会影响`#third`内部的其他非`<p>`元素。这种层级选择器让我们能进行非常精细的样式控制。

![](img/c9c6b8fde670dc006d36d88d35a33eca_82.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_83.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_85.png)

---

## 实战：构建一个简单的导航栏

![](img/c9c6b8fde670dc006d36d88d35a33eca_87.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_88.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_89.png)

最后，让我们运用所学知识来构建一个简单的导航栏。良好的实践是先用语义化的HTML描述结构，再用CSS添加样式。

首先，我们使用HTML5的`<nav>`标签来定义导航区域，并使用列表`<ul>`和`<li>`来组织链接。这为屏幕阅读器等辅助技术提供了清晰的语义。
```html
<nav>
    <ul>
        <li><a class="back" href="#">上一页</a></li>
        <li><a class="forward" href="#">下一页</a></li>
    </ul>
</nav>
```
此时，它只是一个简单的垂直链接列表。在下一个教程中，我们将通过CSS将其美化成一个水平的导航栏，并添加颜色、悬停效果等。

![](img/c9c6b8fde670dc006d36d88d35a33eca_91.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_92.png)

---

![](img/c9c6b8fde670dc006d36d88d35a33eca_94.png)

![](img/c9c6b8fde670dc006d36d88d35a33eca_95.png)

本节课中我们一起学习了CSS的基础。我们理解了CSS的层叠原理，学会了使用元素、类和ID选择器来应用样式，掌握了如何通过外部样式表组织代码，并认识了`<div>`和`<span>`这两个重要的结构标签。最后，我们还开始了导航栏的HTML结构搭建。在接下来的课程中，我们将深入CSS布局和更复杂的选择器。