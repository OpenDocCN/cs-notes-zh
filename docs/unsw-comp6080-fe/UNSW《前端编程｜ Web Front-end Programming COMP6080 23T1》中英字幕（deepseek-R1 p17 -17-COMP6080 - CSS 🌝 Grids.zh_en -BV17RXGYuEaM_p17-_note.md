# 前端编程：17：CSS Grids 🌐

在本节课中，我们将学习CSS Grid布局。这是一种强大的布局工具，特别适合创建由直线分隔的、结构化的网页布局。我们将从基本概念开始，逐步学习如何创建网格、定义行列以及使用网格区域来构建复杂的页面结构。

## 概述

CSS Grid是Flexbox布局的延伸，专门用于创建二维网格布局。它非常适合那些可以用一系列直线清晰分隔内容的页面结构。本节课我们将学习其核心概念和基本用法。

![](img/bd16047f6531faa5c0f5c1a866116282_1.png)

![](img/bd16047f6531faa5c0f5c1a866116282_2.png)

## 网格的基本概念与应用场景

上一节我们介绍了CSS Grid的概述，本节中我们来看看它的具体应用场景。

![](img/bd16047f6531faa5c0f5c1a866116282_4.png)

CSS Grid适用于结构可以用直线清晰分隔的布局。例如，一个典型的网页布局，如头部、侧边栏、主内容和页脚，就非常适合使用网格。

CSS Grid不适用于元素位置完全杂乱无章的结构。对于那种情况，Flexbox可能是更好的选择。

![](img/bd16047f6531faa5c0f5c1a866116282_6.png)

![](img/bd16047f6531faa5c0f5c1a866116282_7.png)

历史上，网页上的网格布局是通过HTML表格（`<table>`）构建的。表格在样式设计上能力有限，且其元素并非为灵活的动态布局而设计。表格应保留用于展示真正的表格数据。

## 创建第一个网格：井字棋游戏

了解了应用场景后，我们来动手创建第一个网格。

首先，需要一个容器元素，并为其设置 `display: grid` 属性。这会将容器内的所有项目定义为网格项目。

```css
.container {
  display: grid;
}
```

接下来，我们需要定义网格的列和行。例如，要创建一个3x3的井字棋棋盘：

```css
.container {
  display: grid;
  grid-template-columns: 50px 50px 50px;
  grid-template-rows: 50px 50px 50px;
}
```

![](img/bd16047f6531faa5c0f5c1a866116282_9.png)

![](img/bd16047f6531faa5c0f5c1a866116282_10.png)

现在，网格已经定义好了，但还看不到内容。我们需要在容器内添加项目。对于井字棋，我们添加9个`<div>`元素。

```html
<div class="container">
  <div>X</div>
  <div>O</div>
  <div>X</div>
  <!-- ... 总共9个div -->
</div>
```

这样，一个简单的井字棋游戏布局就完成了。使用CSS Grid创建这种结构比使用Flexbox更快捷，因为它是为此类网格结构量身定制的。

## 使用fr单位和构建页面布局

![](img/bd16047f6531faa5c0f5c1a866116282_12.png)

我们创建了一个固定像素尺寸的网格。现在，让我们看看如何使用更灵活的单位，并构建一个更实用的网页布局。

![](img/bd16047f6531faa5c0f5c1a866116282_14.png)

CSS Grid引入了一个名为`fr`（fraction，分数）的单位。它类似于Flexbox中的`flex`属性，用于分配剩余空间。例如，`grid-template-columns: 1fr 1fr 1fr;`会创建三个等宽的列。

让我们用网格来构建一个典型的网页布局：头部、侧边栏、主内容和页脚。

首先，我们使用`grid-template-areas`属性来定义网格区域。这允许我们为网格的每个单元格命名。

```css
.container {
  display: grid;
  grid-template-areas:
    "header header header"
    "sidebar main main"
    "footer footer footer";
  grid-template-rows: 1fr 3fr 1fr; /* 中间行更大 */
  grid-template-columns: 100px 1fr; /* 侧边栏固定宽度，主内容自适应 */
}
```

然后，我们为每个区域创建对应的类，并使用`grid-area`属性将它们映射到上面定义的区域名。

```css
.header { grid-area: header; background: red; }
.sidebar { grid-area: sidebar; background: green; }
.main { grid-area: main; background: blue; }
.footer { grid-area: footer; background: orange; }
```

最后，在HTML中使用这些类：

```html
<div class="container">
  <div class="header">Header</div>
  <div class="sidebar">Sidebar</div>
  <div class="main">Main Content</div>
  <div class="footer">Footer</div>
</div>
```

![](img/bd16047f6531faa5c0f5c1a866116282_16.png)

![](img/bd16047f6531faa5c0f5c1a866116282_17.png)

通过这种方式，我们可以轻松地创建出结构清晰的页面布局，而无需使用浮动（float）或绝对定位（absolute positioning）。

![](img/bd16047f6531faa5c0f5c1a866116282_19.png)

![](img/bd16047f6531faa5c0f5c1a866116282_20.png)

![](img/bd16047f6531faa5c0f5c1a866116282_21.png)

## 网格间隙与项目对齐

我们已经构建了页面布局，现在来看看如何调整网格项目之间的间距和对齐方式。

与Flexbox类似，CSS Grid的属性也分为**容器属性**和**项目属性**。

![](img/bd16047f6531faa5c0f5c1a866116282_23.png)

以下是控制网格间隙（Gap）的属性：
*   `row-gap`: 设置行与行之间的间隙。
*   `column-gap`: 设置列与列之间的间隙。
*   `gap`: 是`row-gap`和`column-gap`的简写属性。例如，`gap: 10px;`会同时设置行和列的间隙为10像素。

![](img/bd16047f6531faa5c0f5c1a866116282_24.png)

![](img/bd16047f6531faa5c0f5c1a866116282_25.png)

![](img/bd16047f6531faa5c0f5c1a866116282_26.png)

![](img/bd16047f6531faa5c0f5c1a866116282_27.png)

![](img/bd16047f6531faa5c0f5c1a866116282_28.png)

![](img/bd16047f6531faa5c0f5c1a866116282_29.png)

以下是控制网格内项目对齐的属性（作用于容器）：
*   `justify-items`: 控制所有网格项目在水平方向（沿行轴）的对齐方式（如`start`, `center`, `end`, `stretch`）。
*   `align-items`: 控制所有网格项目在垂直方向（沿列轴）的对齐方式。
*   `place-items`: 是`align-items`和`justify-items`的简写。

![](img/bd16047f6531faa5c0f5c1a866116282_31.png)

![](img/bd16047f6531faa5c0f5c1a866116282_32.png)

例如，设置`justify-items: center;`会使所有网格项目在其各自的网格单元格内水平居中。

![](img/bd16047f6531faa5c0f5c1a866116282_34.png)

![](img/bd16047f6531faa5c0f5c1a866116282_35.png)

## 总结

本节课中我们一起学习了CSS Grid布局的核心知识。

![](img/bd16047f6531faa5c0f5c1a866116282_37.png)

我们了解到CSS Grid是创建二维网格布局的强大工具，尤其适合结构规整的页面。我们学习了如何通过`display: grid`启动网格，使用`grid-template-columns`和`grid-template-rows`定义行列，以及利用`fr`单位创建弹性布局。

更重要的是，我们掌握了使用`grid-template-areas`和`grid-area`来直观地构建复杂页面布局（如包含头部、侧边栏、主内容和页脚的布局）的方法。最后，我们还简要介绍了如何通过`gap`属性设置间隙，以及使用`justify-items`和`align-items`来控制项目对齐。

![](img/bd16047f6531faa5c0f5c1a866116282_39.png)

CSS Grid提供了一种高效、直观的方式来构建响应式网页结构，当你的设计可以被清晰的网格线描述时，它就是最佳选择。