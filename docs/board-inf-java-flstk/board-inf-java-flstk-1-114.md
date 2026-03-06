# 114：CSS 图像样式与倒影

在本节课中，我们将学习如何使用 CSS 为图像添加各种样式效果，包括边框、圆角、阴影、滤镜，以及如何创建图像倒影。这些技巧能让网页中的图片更具视觉吸引力。

上一节我们介绍了如何创建图像画廊和使用 CSS 雪碧图。本节中，我们来看看如何对单个图像进行美化和添加特殊效果。

## 图像样式基础

图像是提升网站视觉吸引力的绝佳方式。通过 CSS，你可以为图像应用不同的样式，使其脱颖而出。

![](img/1ef961c43cd771febda14d52c27f1fc9_1.png)

我们可以从多个方面着手美化图像，例如添加边框、设置圆角、添加内边距、应用阴影或使用各种滤镜。接下来，我们将逐一查看这些属性。

以下是一个简单的 HTML 文档，其中包含一张待处理的图片。

![](img/1ef961c43cd771febda14d52c27f1fc9_3.png)

![](img/1ef961c43cd771febda14d52c27f1fc9_5.png)

```html
<img src="dog.jpg" alt="A dog">
```

### 居中与边框

![](img/1ef961c43cd771febda14d52c27f1fc9_7.png)

首先，我们使用 CSS 选择器选中这张图片，并将其在页面中居中显示。

![](img/1ef961c43cd771febda14d52c27f1fc9_9.png)

![](img/1ef961c43cd771febda14d52c27f1fc9_11.png)

```css
img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
```

接着，为图像添加一个边框。

![](img/1ef961c43cd771febda14d52c27f1fc9_13.png)

```css
img {
  display: block;
  margin-left: auto;
  margin-right: auto;
  border: 20px solid black;
}
```

### 圆角与阴影

我们可以使用 `border-radius` 属性将图片的直角变为圆角。

```css
img {
  /* ... 其他样式 ... */
  border-radius: 50%;
}
```

现在，图片变成了圆形。我们还可以尝试制作一个宝丽来（拍立得）相片风格的效果。

![](img/1ef961c43cd771febda14d52c27f1fc9_15.png)

以下是实现宝丽来效果的步骤：

![](img/1ef961c43cd771febda14d52c27f1fc9_17.png)

1.  将图片和描述文字包裹在一个 `div` 容器中。
2.  为容器添加阴影和背景色。
3.  为文字设置居中对齐。

```html
<div class="polaroid">
  <img src="dog.jpg" alt="A dog">
  <p id="text">A dog</p>
</div>
```

![](img/1ef961c43cd771febda14d52c27f1fc9_19.png)

```css
.polaroid {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  width: 500px;
  padding: 10px;
  background-color: white; /* 通常宝丽来相纸是白色的 */
}

![](img/1ef961c43cd771febda14d52c27f1fc9_21.png)

#text {
  text-align: center;
}
```

### 应用滤镜

CSS 滤镜（`filter`）属性可以为图像添加各种视觉效果，如模糊、亮度调整、对比度调整等。

![](img/1ef961c43cd771febda14d52c27f1fc9_23.png)

让我们为图像应用一个模糊滤镜。

![](img/1ef961c43cd771febda14d52c27f1fc9_25.png)

![](img/1ef961c43cd771febda14d52c27f1fc9_27.png)

```css
img {
  /* ... 其他样式 ... */
  filter: blur(4px);
}
```

![](img/1ef961c43cd771febda14d52c27f1fc9_29.png)

我们也可以调整图像的亮度。

```css
img {
  /* ... 其他样式 ... */
  filter: brightness(200%);
}
```

![](img/1ef961c43cd771febda14d52c27f1fc9_31.png)

或者调整对比度。

```css
img {
  /* ... 其他样式 ... */
  filter: contrast(180%);
}
```

类似地，你还可以尝试其他滤镜，如 `hue-rotate`（色相旋转）、`invert`（反色）、`opacity`（透明度）、`saturate`（饱和度）、`sepia`（怀旧色）、`drop-shadow`（投影）、`grayscale`（灰度）等。

![](img/1ef961c43cd771febda14d52c27f1fc9_33.png)

## 图像倒影

![](img/1ef961c43cd771febda14d52c27f1fc9_35.png)

现在，让我们来看看第二个主题：图像倒影。

图像倒影可以创建图像的一个镜像副本，从而产生反射效果。需要注意的是，该属性主要通过 `-webkit-box-reflect` 实现，主要被 Chrome、Safari 和 Opera 浏览器支持，而 Firefox 则不支持。

![](img/1ef961c43cd771febda14d52c27f1fc9_37.png)

要为图像添加倒影，我们可以使用 `-webkit-box-reflect` 属性。

![](img/1ef961c43cd771febda14d52c27f1fc9_39.png)

```css
img {
  -webkit-box-reflect: below;
}
```

![](img/1ef961c43cd771febda14d52c27f1fc9_41.png)

上述代码会在图像下方创建一个倒影。你也可以将方向改为 `right`（右侧）、`left`（左侧）或 `above`（上方，但可能因超出视图而不可见）。

![](img/1ef961c43cd771febda14d52c27f1fc9_43.png)

![](img/1ef961c43cd771febda14d52c27f1fc9_45.png)

本节课中，我们一起学习了如何使用 CSS 为图像添加边框、圆角、阴影和宝丽来效果，探索了多种滤镜的应用，并了解了如何为图像创建倒影效果。这些技能将帮助你显著提升网页中图像的视觉表现力。希望你能在下一个项目中尝试使用它们。我们下节课再见。