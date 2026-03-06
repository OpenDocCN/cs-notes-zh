# 113：CSS图片画廊与精灵图 🖼️

![](img/db3a4797f4281335f95deab317bc2ea9_1.png)

## 概述
在本节课中，我们将学习如何使用CSS创建图片画廊和精灵图。图片画廊能有效展示多张图片，而精灵图技术则能优化网页性能。

## CSS图片画廊
上一节我们介绍了如何使用CSS创建下拉按钮。本节中，我们来看看如何创建一个图片画廊。

图片画廊是排列成网格或行的图片集合。它是展示图片并为浏览者提供便捷浏览方式的好方法。在CSS中，我们可以使用`float`属性并设置图片的宽度和高度来创建画廊，也可以使用其他CSS属性实现。

以下是创建一个基础图片画廊的步骤：

1.  **HTML结构**：首先，创建一个主容器`<div>`，并为其设置一个类名（例如`my-gallery`）。在这个容器内，为每张图片创建单独的`<div>`或直接使用`<img>`标签。

    ```html
    <div class="my-gallery">
        <img src="dog1.jpg" alt="Dog 1">
        <img src="dog2.jpg" alt="Dog 2">
        <img src="dog3.jpg" alt="Dog 3">
    </div>
    ```

2.  **CSS样式**：使用CSS Grid布局来排列图片。为画廊容器设置`display: grid`，并定义列数。同时，可以添加间隙使布局更美观。

    ```css
    .my-gallery {
        display: grid;
        /* 创建3列，每列等宽 */
        grid-template-columns: repeat(3, 1fr);
        /* 设置图片之间的间隙为10像素 */
        grid-gap: 10px;
    }
    ```

![](img/db3a4797f4281335f95deab317bc2ea9_3.png)

3.  **图片样式**：控制图片本身的尺寸，使其适应网格布局。通常将宽度设为100%，高度设为自动。

    ```css
    .my-gallery img {
        width: 100%;
        height: auto;
    }
    ```

应用这些样式后，图片将整齐地排列在一个三列的网格中。你可以通过调整`grid-template-columns`的值来改变列数。

![](img/db3a4797f4281335f95deab317bc2ea9_5.png)

## CSS精灵图
了解了图片画廊的创建后，我们接下来探讨一种优化技术：CSS精灵图。

精灵图是一种用于减少网页HTTP请求次数的技术。它将多个小图标或图片合并到一张大图中，然后使用CSS背景定位来显示所需的特定部分。

以下是使用精灵图的步骤：

1.  **创建合并图像**：首先，需要使用图像编辑软件（如Photoshop）或在线工具，将所有小图标合并到一张图片中。例如，一张图里可能包含主页图标、左箭头和右箭头图标。

2.  **HTML结构**：在HTML中，为每个需要显示图标的地方创建一个元素（如`<div>`或`<span>`）。由于实际图像将通过CSS背景引入，`src`属性可以放置一个透明的占位图。

    ```html
    <div id="home"></div>
    <div id="back"></div>
    ```

![](img/db3a4797f4281335f95deab317bc2ea9_7.png)

![](img/db3a4797f4281335f95deab317bc2ea9_9.png)

3.  **CSS背景定位**：为每个元素设置相同的背景图像（即合并后的精灵图），然后通过`background-position`属性调整位置，以显示正确的图标部分。同时需要精确设置元素的宽度和高度，以匹配目标图标的大小。

    ```css
    #home {
        width: 46px;
        height: 44px;
        background: url(‘sprites.gif’) 0 0;
    }
    #back {
        width: 43px;
        height: 44px;
        background: url(‘sprites.gif’) -91px 0;
    }
    ```
    在`#back`的样式中，`background-position: -91px 0;`意味着将背景图像向左移动91像素，从而显示出左箭头图标。

![](img/db3a4797f4281335f95deab317bc2ea9_11.png)

![](img/db3a4797f4281335f95deab317bc2ea9_12.png)

![](img/db3a4797f4281335f95deab317bc2ea9_14.png)

![](img/db3a4797f4281335f95deab317bc2ea9_16.png)

通过这种方式，浏览器只需加载一张合并后的图片，而不是多个单独的小图片，从而显著提升了页面加载性能。

![](img/db3a4797f4281335f95deab317bc2ea9_18.png)

![](img/db3a4797f4281335f95deab317bc2ea9_20.png)

## 总结
本节课中我们一起学习了两个实用的CSS技巧。我们首先学习了如何利用CSS Grid布局创建整洁的图片画廊。接着，我们探讨了CSS精灵图技术，它通过合并图片和背景定位来减少HTTP请求，优化网站性能。掌握这些技能将有助于你构建更美观、更高效的网页。