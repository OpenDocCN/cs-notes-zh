# 106：CSS box-sizing 属性详解 📦

在本节课中，我们将要学习 CSS 的 `box-sizing` 属性。这个属性控制着元素宽度和高度的计算方式，对于精确布局至关重要。

上一节我们介绍了 CSS 盒模型及其如何影响网页上 HTML 元素的布局和尺寸。本节中，我们来看看 `box-sizing` 属性及其不同的取值。

`box-sizing` 属性允许你控制元素宽度和高度的计算方式，决定是否将内边距和边框包含在计算内。它主要有两个值：`content-box` 和 `border-box`。

`box-sizing` 的默认值是 `content-box`。这意味着元素的宽度和高度仅基于其内容区域计算。如果你为元素添加内边距或边框，元素的总尺寸会增加，这可能导致布局问题。

另一方面，`border-box` 值在计算宽度和高度时，会将内边距和边框包含在内。这意味着，如果你将一个元素的宽度设为 200 像素，并添加 10 像素的内边距和 1 像素的边框，元素的总宽度将保持为 200 像素。

以下是两种计算方式的公式对比：

![](img/e8b133bb1b3251ec9ae13d0c3a92f7ef_1.png)

*   **`content-box` (默认)**
    `元素总宽度 = width + padding-left + padding-right + border-left + border-right`

*   **`border-box`**
    `元素总宽度 = width` (已包含 padding 和 border)

![](img/e8b133bb1b3251ec9ae13d0c3a92f7ef_3.png)

现在，让我们通过一个 HTML 文档示例来看看它的实际效果。

![](img/e8b133bb1b3251ec9ae13d0c3a92f7ef_5.png)

![](img/e8b133bb1b3251ec9ae13d0c3a92f7ef_7.png)

以下是一个演示 `box-sizing` 如何工作的示例步骤。

![](img/e8b133bb1b3251ec9ae13d0c3a92f7ef_9.png)

首先，我们创建一个 HTML 文档，其中包含一个主 `div` 容器和两个内部的 `div` 元素。

```html
<div id="main">
  <div class="box box1">Box 1</div>
  <div class="box box2">Box 2</div>
</div>
```

![](img/e8b133bb1b3251ec9ae13d0c3a92f7ef_11.png)

接着，我们为这些元素添加一些基础样式。

![](img/e8b133bb1b3251ec9ae13d0c3a92f7ef_13.png)

![](img/e8b133bb1b3251ec9ae13d0c3a92f7ef_15.png)

```css
#main {
  width: 500px;
  border: 10px solid black;
}

.box {
  width: 100%; /* 默认继承父容器宽度 */
  background-color: lightblue;
  margin-bottom: 10px;
}
```

此时，两个内部 `div` 会填满主容器的宽度。现在，我们为第一个盒子添加内边距。

![](img/e8b133bb1b3251ec9ae13d0c3a92f7ef_17.png)

![](img/e8b133bb1b3251ec9ae13d0c3a92f7ef_19.png)

```css
.box1 {
  padding: 20px;
}
```

![](img/e8b133bb1b3251ec9ae13d0c3a92f7ef_21.png)

你会发现，第一个盒子超出了主容器的黑色边框。这是因为在默认的 `content-box` 模式下，`width: 100%` 仅指内容宽度为 500px，加上左右各 20px 的内边距后，总宽度变成了 540px。

![](img/e8b133bb1b3251ec9ae13d0c3a92f7ef_23.png)

为了解决这个问题，我们使用 `box-sizing` 属性。

![](img/e8b133bb1b3251ec9ae13d0c3a92f7ef_25.png)

```css
.box1 {
  padding: 20px;
  box-sizing: border-box; /* 将 padding 和 border 包含在 width 计算内 */
}
```

应用 `border-box` 后，第一个盒子自动调整，其总宽度（内容+内边距）被限制在主容器设定的 500px 宽度内。即使我们再添加边框，它也会被包含在总宽度内。

![](img/e8b133bb1b3251ec9ae13d0c3a92f7ef_27.png)

```css
.box1 {
  padding: 20px;
  border: 5px solid red;
  box-sizing: border-box;
}
```

而第二个盒子保持 `content-box` 的默认行为。如果你将其 `box-sizing` 也改为 `content-box`，它会表现出和最初未设置时一样的向外扩张的行为。

![](img/e8b133bb1b3251ec9ae13d0c3a92f7ef_29.png)

本节课中我们一起学习了 CSS `box-sizing` 属性的核心概念和用法。我们了解到 `content-box` 是默认值，计算尺寸时不包含内边距和边框；而 `border-box` 则将这些部分包含在设定的宽度和高度内，使得布局控制更加直观和稳定。在实际开发中，使用 `border-box` 通常能避免许多意外的布局问题。