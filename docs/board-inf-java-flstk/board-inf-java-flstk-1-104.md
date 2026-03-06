# 104：CSS背景颜色 🎨

在本节课中，我们将要学习CSS中的`background-color`属性。我们将探讨如何为网页设置背景颜色，以及使用不同颜色表示方法（如颜色名称、RGB、RGBA和十六进制）来丰富你的设计。

上一节我们介绍了CSS的`color`属性，本节中我们来看看如何设置元素的背景颜色。作为网页开发者，为网站选择合适的背景色对于创造引人入胜的用户体验至关重要。背景色为整个页面定下基调，并极大地影响网站的可读性和整体美观度。

## 设置背景颜色

在CSS中，我们使用`background-color`属性来设置元素的背景颜色。其基本语法如下：

```css
selector {
  background-color: value;
}
```

![](img/4d2b4b4837ec6aae890315ddd154465e_1.png)

![](img/4d2b4b4837ec6aae890315ddd154465e_3.png)

以下是几种常用的颜色值指定方法。

![](img/4d2b4b4837ec6aae890315ddd154465e_5.png)

### 1. 使用颜色名称

CSS预定义了一系列颜色名称，例如`red`、`blue`、`coral`等。这种方法简单直接，但可选颜色有限。

![](img/4d2b4b4837ec6aae890315ddd154465e_7.png)

![](img/4d2b4b4837ec6aae890315ddd154465e_9.png)

```css
body {
  background-color: coral;
}
```

### 2. 使用RGB值

RGB颜色模型通过混合红（Red）、绿（Green）、蓝（Blue）三种光的分量来定义颜色。每个分量的取值范围是0到255。

```css
body {
  background-color: rgb(100, 149, 237);
}
```

![](img/4d2b4b4837ec6aae890315ddd154465e_11.png)

![](img/4d2b4b4837ec6aae890315ddd154465e_13.png)

### 3. 使用RGBA值

![](img/4d2b4b4837ec6aae890315ddd154465e_15.png)

RGBA在RGB的基础上增加了一个Alpha通道，用于控制颜色的不透明度。Alpha值的范围是0.0（完全透明）到1.0（完全不透明）。

![](img/4d2b4b4837ec6aae890315ddd154465e_17.png)

```css
body {
  background-color: rgba(100, 149, 237, 0.4); /* 40%不透明度 */
}
```

![](img/4d2b4b4837ec6aae890315ddd154465e_19.png)

![](img/4d2b4b4837ec6aae890315ddd154465e_21.png)

### 4. 使用十六进制值

十六进制颜色代码以`#`开头，后跟六位数字或字母，每两位分别代表红、绿、蓝的分量。

```css
body {
  background-color: #ffffff; /* 白色 */
  background-color: #6495ed; /* 与 rgb(100, 149, 237) 相同 */
}
```

![](img/4d2b4b4837ec6aae890315ddd154465e_23.png)

## 实践与应用

选择互补的颜色并使用对比度来提升可读性非常重要。浅色背景搭配深色文字通常具有良好的可读性，反之亦然。你可以尝试不同的颜色组合，找到最适合你网站主题和风格的方案。

本节课中我们一起学习了CSS的`background-color`属性。我们掌握了使用颜色名称、RGB、RGBA和十六进制代码来设置背景色的方法，并了解了透明度控制。请花时间尝试不同的颜色，利用对比度提升可读性，从而创建视觉上突出且能吸引用户的网站。

![](img/4d2b4b4837ec6aae890315ddd154465e_25.png)

我们下个视频再见。🎼