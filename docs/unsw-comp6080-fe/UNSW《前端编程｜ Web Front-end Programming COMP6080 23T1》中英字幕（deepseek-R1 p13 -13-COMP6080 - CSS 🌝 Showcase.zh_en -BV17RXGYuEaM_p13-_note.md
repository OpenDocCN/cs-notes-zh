# 前端编程：第8讲：CSS 展示 🌟

![](img/f713760584cc547ade363f1d05c18986_1.png)

![](img/f713760584cc547ade363f1d05c18986_3.png)

在本节课中，我们将探索一系列有趣且富有创意的CSS技术。这些内容旨在激发灵感，不会在考试中涉及。我们将学习如何创建背景图案、CSS艺术、动画、遮罩与裁剪、3D CSS效果，以及如何将CSS与SVG结合，最后还会了解自定义CSS的Houdini API。

## 背景与图案 🎨

上一节我们介绍了课程概述，本节中我们来看看如何使用CSS创建背景和图案。CSS的`background`属性功能强大，远不止设置单一颜色。

以下是几种创建渐变背景的方法：

*   **线性渐变**：使用`linear-gradient()`函数。可以指定方向（如`to right`）或角度（如`135deg`），并定义颜色变化。例如：
    ```css
    background: linear-gradient(to right, green, pink);
    background: linear-gradient(135deg, green, pink);
    ```
*   **径向渐变**：使用`radial-gradient()`函数。颜色从中心点向外辐射。可以指定形状（`circle`或`ellipse`）和中心位置。例如：
    ```css
    background: radial-gradient(circle at 20px 80px, green 0% 20%, pink 20% 60%, green 60%);
    ```
*   **重复渐变**：使用`repeating-linear-gradient()`和`repeating-radial-gradient()`可以创建条纹或同心圆等重复图案。通过设置相同的色标位置可以实现硬切边效果。
*   **多重背景**：可以在一个元素上叠加多个背景图像（包括渐变）。列表中的第一个背景会绘制在最上层。
*   **圆锥渐变**：使用`conic-gradient()`围绕中心点进行颜色渐变。结合`repeating-conic-gradient()`可以创建饼图切片或雷达图效果。
*   **像素级图案**：通过为每个“像素”设置一个微小的`linear-gradient`作为背景，理论上可以用单个`<div>`元素拼出任何图片。网站 [singlediv.com](https://singlediv.com) 展示了这种技术的惊人潜力。
*   **资源推荐**：网站 [CSS3 Patterns](https://projects.verou.me/css3patterns/) 提供了大量可直接复用的高级CSS背景图案代码。

## CSS艺术 🖼️

CSS艺术是指仅使用HTML和CSS来绘制图像或复杂图形。这通常需要组合大量元素，并巧妙运用多种CSS属性。

以下是创建CSS艺术的关键技术：

![](img/f713760584cc547ade363f1d05c18986_5.png)

![](img/f713760584cc547ade363f1d05c18986_7.png)

*   **形状组合**：使用多个`<div>`元素，并通过`border-radius`、`linear-gradient`和`radial-gradient`来创建基本形状（如圆形、椭圆）和阴影，模拟3D效果。
*   **变换**：使用`transform`属性（如`rotate`、`translate`、`scale`）来精确调整和组合这些形状。
*   **资源推荐**：网站 [cssart.com](https://cssart.com) 汇集了许多令人惊叹的CSS艺术作品，例如“VW Bug”。
*   **球体生成器示例**：通过JavaScript动态计算并应用一系列渐变的`radial-gradient`，可以模拟出具有立体感的球体。核心是创建一个从中心点（通常偏移一点以模拟光源）向外颜色逐渐变暗的径向渐变列表。

## 遮罩与裁剪 ✂️

本节我们将学习如何控制元素的可见区域，即遮罩与裁剪。这允许我们创造出非矩形的显示效果。

以下是几种遮罩与裁剪的方法：

*   **文字遮罩**：使用`background-clip: text`属性可以让背景（如图片）只在文字形状内显示。需要将文字颜色设为`transparent`。
*   **路径裁剪**：使用`clip-path`属性可以按照指定形状裁剪元素。
    *   `circle()`：裁剪为圆形。
    *   `polygon()`：裁剪为多边形，通过一系列坐标点定义。
    *   `path()`：使用SVG路径语法进行更复杂、包含曲线的裁剪（目前主要Firefox支持）。
*   **图像遮罩**：使用`mask-image`属性，通过一张灰度图片来定义元素的透明度（黑色为不透明，白色为透明）。这可以实现渐变擦除等高级过渡效果。
*   **CSS滤镜**：使用`filter`属性可以为元素添加视觉效果，如`blur()`模糊、`brightness()`调整亮度、`hue-rotate()`改变色相等。
*   **实践案例**：一个波浪形遮罩动画的原型，结合了`clip-path`动态裁剪和`filter`颜色过滤，创造出流动的视觉特效。

## CSS动画 🎬

CSS动画能让界面元素动起来，增加交互的趣味性。我们已经了解了基础动画，这里看一些创意应用。

以下是两个创意动画技巧：

![](img/f713760584cc547ade363f1d05c18986_9.png)

![](img/f713760584cc547ade363f1d05c18986_11.png)

*   **背景位置动画**：对复杂的多重背景（如图案）应用`background-position`动画，可以创造出平移、滚动的视觉效果。单元素动画艺术作品常使用此技术。
*   **溢出隐藏技巧**：将动画元素（如移动的波浪SVG）放置在一个设置了`overflow: hidden`的容器中，可以只显示容器范围内的部分，从而制造出元素“进入”或“离开”视口的错觉。常用于创建无限循环的背景或特殊转场。

## 结合SVG的CSS 🖍️

SVG（可缩放矢量图形）本身是XML格式，其元素也可以使用CSS进行样式化和动画。

![](img/f713760584cc547ade363f1d05c18986_13.png)

![](img/f713760584cc547ade363f1d05c18986_15.png)

![](img/f713760584cc547ade363f1d05c18986_17.png)

以下是两种结合SVG的CSS动画技术：

![](img/f713760584cc547ade363f1d05c18986_19.png)

![](img/f713760584cc547ade363f1d05c18986_20.png)

*   **描边动画**：利用SVG路径的`stroke-dasharray`（虚线样式）和`stroke-dashoffset`（虚线偏移）属性。通过动画将`stroke-dashoffset`从路径总长变化到0，可以模拟出画笔绘制路径的过程。
*   **路径变形动画**：对SVG `<path>`元素的`d`（路径数据）属性应用CSS过渡或动画，可以实现从一个形状平滑变形到另一个形状的效果。注意，两个路径需要有相同数量的命令和点才能流畅过渡。

## 3D CSS 🧊

![](img/f713760584cc547ade363f1d05c18986_22.png)

![](img/f713760584cc547ade363f1d05c18986_23.png)

![](img/f713760584cc547ade363f1d05c18986_25.png)

通过CSS的3D变换功能，我们可以让元素在三维空间中旋转和移动。

![](img/f713760584cc547ade363f1d05c18986_27.png)

以下是关于3D CSS的介绍：

![](img/f713760584cc547ade363f1d05c18986_29.png)

*   **核心属性**：主要使用`transform`属性的3D函数，如`rotateX()`、`rotateY()`、`rotateZ()`、`translate3d()`，并配合`perspective`设置透视点来创造深度感。
*   **创意作品**：许多艺术家创作了令人印象深刻的纯CSS 3D作品，如可旋转的房屋、复杂的3D场景等。
*   **动手实践**：可以尝试修改提供的“等距立方体”示例代码，通过JavaScript动态添加更多立方体、改变其位置、大小和颜色，来构建自己的3D世界（如3D图表或简单游戏）。

![](img/f713760584cc547ade363f1d05c18986_31.png)

![](img/f713760584cc547ade363f1d05c18986_33.png)

## 自定义CSS与Houdini 🪄

当现有CSS属性无法满足特定设计需求时（例如，想要一个双色波浪下划线），我们可以借助CSS Houdini API来自定义绘制逻辑。

以下是使用CSS Painting API的基本步骤：

1.  **注册绘制工作**：在单独的JavaScript文件中，使用`registerPaint`注册一个自定义绘制器，并实现`paint`方法。在该方法中，可以使用类似Canvas的API进行绘制。
2.  **使用自定义属性**：在CSS中，通过`background-image: paint(自定义绘制器名称)`来调用。可以定义并使用自定义CSS属性（如`--underline-color-1`）来传递参数给绘制器。
3.  **动画支持**：由于自定义属性可以被CSS动画系统插值，因此只需对自定义属性（如`--wave-time`）应用关键帧动画，就能让自定义绘制效果动起来。

![](img/f713760584cc547ade363f1d05c18986_35.png)

**注意**：Houdini API较新，浏览器支持度不一（如Painting API主要支持Chrome/Edge），使用时需检查兼容性。

## 总结 📚

![](img/f713760584cc547ade363f1d05c18986_37.png)

![](img/f713760584cc547ade363f1d05c18986_39.png)

![](img/f713760584cc547ade363f1d05c18986_41.png)

本节课我们一起探索了CSS在创意表达方面的多种可能性。我们学习了如何制作复杂的背景图案、用CSS绘制艺术图形、实现遮罩裁剪效果、创作CSS和SVG动画、构建3D场景，甚至通过Houdini API扩展CSS本身的功能。希望这些内容能激发你的灵感，鼓励你在未来的项目中尝试更多有趣、独特的CSS技术。