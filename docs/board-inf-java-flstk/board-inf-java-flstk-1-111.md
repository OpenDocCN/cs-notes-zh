# 111：CSS导航栏 🧭

在本节课中，我们将学习如何使用CSS创建一个功能完整、样式美观的导航栏。导航栏是网站的关键组成部分，它帮助用户在网站的不同页面或区域间进行导航。

上一节我们介绍了CSS的网格布局，本节中我们来看看如何利用CSS的其他属性来构建一个导航栏。

![](img/e8aed85609827974a0c1683bd7fc2b19_1.png)

## 创建基础HTML结构

首先，我们需要创建导航栏的HTML骨架。导航栏通常由一个无序列表构成，列表项内包含用于跳转的链接。

```html
<ul>
    <li><a class="active" href="#">首页</a></li>
    <li><a href="#">新闻</a></li>
    <li><a href="#">联系</a></li>
    <li><a href="#">关于</a></li>
</ul>
```

## 使用CSS进行基础样式设置

初始的HTML列表看起来并不像导航栏。我们需要使用CSS来改变它的外观。

![](img/e8aed85609827974a0c1683bd7fc2b19_3.png)

![](img/e8aed85609827974a0c1683bd7fc2b19_5.png)

以下是应用于无序列表的样式，用于重置默认样式并设置背景：

```css
ul {
    list-style-type: none; /* 移除列表项前的圆点 */
    margin: 0;
    padding: 0;
    overflow: hidden; /* 防止内容溢出 */
    background-color: #333; /* 设置背景色为深色 */
}
```

![](img/e8aed85609827974a0c1683bd7fc2b19_7.png)

## 排列列表项并设置链接样式

![](img/e8aed85609827974a0c1683bd7fc2b19_9.png)

接下来，我们需要让列表项水平排列，并设置链接的样式，使其看起来像可点击的按钮。

以下是设置列表项和链接样式的代码：

```css
li {
    float: left; /* 使列表项水平排列 */
}

![](img/e8aed85609827974a0c1683bd7fc2b19_11.png)

li a {
    display: block; /* 将链接变为块级元素，方便设置尺寸 */
    color: white; /* 文字颜色 */
    text-align: center; /* 文字居中 */
    padding: 14px 16px; /* 内边距 */
    text-decoration: none; /* 移除下划线 */
}
```

![](img/e8aed85609827974a0c1683bd7fc2b19_13.png)

## 添加交互效果

![](img/e8aed85609827974a0c1683bd7fc2b19_15.png)

一个优秀的导航栏需要有视觉反馈。我们将为当前活动页面和鼠标悬停状态添加特殊样式。

![](img/e8aed85609827974a0c1683bd7fc2b19_17.png)

以下是添加活动状态和悬停效果的样式：

![](img/e8aed85609827974a0c1683bd7fc2b19_19.png)

![](img/e8aed85609827974a0c1683bd7fc2b19_21.png)

```css
/* 活动页面链接的样式 */
.active {
    background-color: #04AA6D; /* 绿色背景 */
    color: white;
}

/* 鼠标悬停时的样式 */
li a:hover {
    background-color: #ddd; /* 浅灰色背景 */
    color: black;
}
```

## 实现固定定位导航栏

![](img/e8aed85609827974a0c1683bd7fc2b19_23.png)

在许多网站中，导航栏会固定在页面顶部，不随页面滚动而移动。我们可以使用 `position: fixed` 属性来实现这个效果。

![](img/e8aed85609827974a0c1683bd7fc2b19_25.png)

![](img/e8aed85609827974a0c1683bd7fc2b19_27.png)

以下是使导航栏固定在顶部的CSS：

![](img/e8aed85609827974a0c1683bd7fc2b19_29.png)

```css
ul {
    position: fixed; /* 固定定位 */
    top: 0; /* 距离顶部为0 */
    width: 100%; /* 宽度占满整个视口 */
}
```

![](img/e8aed85609827974a0c1683bd7fc2b19_31.png)

当导航栏固定后，页面内容可能会被其遮挡。我们需要为页面主体内容添加一个上边距，将其向下推。

![](img/e8aed85609827974a0c1683bd7fc2b19_33.png)

以下是调整页面内容位置的CSS：

![](img/e8aed85609827974a0c1683bd7fc2b19_35.png)

![](img/e8aed85609827974a0c1683bd7fc2b19_37.png)

```css
body {
    margin-top: 50px; /* 根据导航栏高度调整 */
}
```

![](img/e8aed85609827974a0c1683bd7fc2b19_39.png)

## 总结

![](img/e8aed85609827974a0c1683bd7fc2b19_41.png)

![](img/e8aed85609827974a0c1683bd7fc2b19_43.png)

本节课中我们一起学习了如何使用HTML和CSS创建一个完整的导航栏。我们首先构建了基础的HTML列表结构，然后逐步使用CSS设置了列表样式、链接样式、交互效果，并最终实现了固定在页面顶部的导航栏功能。通过组合使用 `float`、`display`、`position` 等属性，我们可以灵活地控制导航栏的布局和外观。