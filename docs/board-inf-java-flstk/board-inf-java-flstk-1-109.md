# 109：CSS Grid 布局（第一部分）📐

在本节课中，我们将要学习 CSS Grid 布局系统的基础知识。CSS Grid 是 CSS 中最强大的布局工具之一，它是一个二维布局系统，允许你使用行和列来创建复杂的布局结构。

## 概述

上一节我们介绍了如何使用 CSS 来样式化表格。本节中，我们来看看 CSS Grid。我们将涵盖 CSS Grid 的基础知识，包括如何设置一个网格、如何定义列、以及如何在网格内放置内容。

![](img/c8074a937b6d1beccddd3c48d591ff3a_1.png)

## 什么是 CSS Grid？

CSS Grid 是一个二维布局系统，允许你使用行和列来创建复杂的布局。与 CSS 中的其他布局工具（如 Flexbox 和浮动）不同，CSS Grid 是专门为创建基于网格的布局而设计的。

![](img/c8074a937b6d1beccddd3c48d591ff3a_3.png)

![](img/c8074a937b6d1beccddd3c48d591ff3a_5.png)

使用 CSS Grid，你可以轻松创建能够适应不同屏幕尺寸和设备的响应式、灵活的布局。你可以将 HTML 元素排列成行和列，从而完全控制每个元素的位置和大小，例如将其布局为页眉、主体内容区、空白区域和侧边栏等有意义的区域。

## 实践 CSS Grid

![](img/c8074a937b6d1beccddd3c48d591ff3a_7.png)

![](img/c8074a937b6d1beccddd3c48d591ff3a_8.png)

让我们在自己的 HTML 文档中实现 CSS Grid。

以下是一个 HTML 文档示例，我们创建了一个网格容器，其中包含多个网格项，并应用了一些基础样式。

![](img/c8074a937b6d1beccddd3c48d591ff3a_10.png)

![](img/c8074a937b6d1beccddd3c48d591ff3a_12.png)

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
  <div class="item">7</div>
  <div class="item">8</div>
</div>
```

![](img/c8074a937b6d1beccddd3c48d591ff3a_14.png)

![](img/c8074a937b6d1beccddd3c48d591ff3a_16.png)

![](img/c8074a937b6d1beccddd3c48d591ff3a_18.png)

```css
.container {
  background-color: blue;
  padding: 20px;
}
.item {
  background-color: lightgray;
  margin-bottom: 10px;
  text-align: center;
  font-size: 24px;
}
```

![](img/c8074a937b6d1beccddd3c48d591ff3a_20.png)

现在，为了对这个容器应用网格布局，我们将使用 `display` 属性，并将其值设置为 `grid`。

![](img/c8074a937b6d1beccddd3c48d591ff3a_21.png)

![](img/c8074a937b6d1beccddd3c48d591ff3a_23.png)

![](img/c8074a937b6d1beccddd3c48d591ff3a_25.png)

```css
.container {
  display: grid;
  /* 其他样式保持不变 */
}
```

![](img/c8074a937b6d1beccddd3c48d591ff3a_27.png)

![](img/c8074a937b6d1beccddd3c48d591ff3a_29.png)

仅仅设置 `display: grid` 并不会立即产生可见的网格效果，因为我们还需要定义网格的结构。

![](img/c8074a937b6d1beccddd3c48d591ff3a_31.png)

![](img/c8074a937b6d1beccddd3c48d591ff3a_32.png)

## 定义网格列

![](img/c8074a937b6d1beccddd3c48d591ff3a_34.png)

![](img/c8074a937b6d1beccddd3c48d591ff3a_36.png)

要定义网格的列，我们使用 `grid-template-columns` 属性。

![](img/c8074a937b6d1beccddd3c48d591ff3a_38.png)

以下是定义列的方法：

![](img/c8074a937b6d1beccddd3c48d591ff3a_40.png)

*   **定义固定宽度列**：`grid-template-columns: 100px;` 会创建一个 100 像素宽的单一列。
*   **定义多列**：`grid-template-columns: 100px 100px;` 会创建两个 100 像素宽的列。
*   **使用 `repeat()` 函数**：当需要多列时，可以使用 `repeat()` 函数简化代码。例如，`grid-template-columns: repeat(4, 100px);` 会创建四个 100 像素宽的列。
*   **使用弹性单位 `fr`**：`fr` 单位代表“分数”，用于创建按比例分配可用空间的列。例如：
    *   `grid-template-columns: 1fr;` 创建一个占据全部可用空间的列。
    *   `grid-template-columns: 1fr 1fr;` 创建两个等宽的列。
    *   `grid-template-columns: 2fr 1fr;` 创建两列，第一列的宽度是第二列的两倍。

## 定义网格行

![](img/c8074a937b6d1beccddd3c48d591ff3a_42.png)

![](img/c8074a937b6d1beccddd3c48d591ff3a_43.png)

定义网格行与定义列类似。

以下是定义行的方法：

*   **使用 `grid-template-rows`**：此属性用于显式定义行的高度。例如，`grid-template-rows: 200px 200px;` 会创建两个 200 像素高的行。
*   **使用 `grid-auto-rows`**：此属性用于定义所有隐式创建的行（即未在 `grid-template-rows` 中定义的行）的高度。例如，`grid-auto-rows: 200px;` 会使所有行的高度为 200 像素。
*   **结合使用**：可以同时使用 `grid-template-rows` 和 `grid-auto-rows`。例如：
    ```css
    .container {
      grid-template-rows: 300px; /* 第一行高 300px */
      grid-auto-rows: 200px;     /* 后续所有行高 200px */
    }
    ```
*   **使用 `minmax()` 函数实现动态行高**：为了让行高根据内容动态调整，可以使用 `minmax(min, max)` 函数。例如，`grid-auto-rows: minmax(100px, auto);` 表示行高最小为 100 像素，最大根据内容自动扩展。

## 设置网格间隙

网格项默认是紧密排列的。我们可以使用以下属性来添加间隙：

![](img/c8074a937b6d1beccddd3c48d591ff3a_45.png)

![](img/c8074a937b6d1beccddd3c48d591ff3a_47.png)

![](img/c8074a937b6d1beccddd3c48d591ff3a_49.png)

*   **列间隙**：使用 `column-gap` 属性。例如，`column-gap: 10px;`。
*   **行间隙**：使用 `row-gap` 属性。例如，`row-gap: 10px;`。
*   **统一间隙**：使用 `gap` 属性可以同时设置行和列的间隙。例如，`gap: 20px;` 会设置行和列的间隙都为 20 像素。

![](img/c8074a937b6d1beccddd3c48d591ff3a_51.png)

![](img/c8074a937b6d1beccddd3c48d591ff3a_53.png)

## 总结

![](img/c8074a937b6d1beccddd3c48d591ff3a_55.png)

本节课中我们一起学习了 CSS Grid 布局的基础部分。我们了解了什么是 CSS Grid，它是一个强大的二维布局工具。我们实践了如何通过 `display: grid` 将一个容器设置为网格，并使用 `grid-template-columns` 和 `grid-template-rows`（或 `grid-auto-rows`）来定义网格的行和列结构。我们还学习了如何使用 `fr` 单位创建弹性布局，使用 `minmax()` 函数让行高自适应内容，以及使用 `gap` 系列属性为网格项之间添加间距。

![](img/c8074a937b6d1beccddd3c48d591ff3a_57.png)

![](img/c8074a937b6d1beccddd3c48d591ff3a_59.png)

掌握这些基础知识后，你已经可以在项目中开始使用 CSS Grid 来创建结构清晰、响应灵活的页面布局了。