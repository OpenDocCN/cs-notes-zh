# 098：CSS定位详解 🎯

在本节课中，我们将要学习CSS定位。CSS定位允许你控制网页上元素的位置，决定了元素如何被放置在页面上以及如何呈现给用户。

![](img/98aab824d4b448d096a9479cc5acb8dc_1.png)

上一节我们介绍了属性选择器，并在HTML文档中使用了它们。本节中，我们来看看CSS定位的不同类型。

![](img/98aab824d4b448d096a9479cc5acb8dc_3.png)

## 静态定位

![](img/98aab824d4b448d096a9479cc5acb8dc_5.png)

![](img/98aab824d4b448d096a9479cc5acb8dc_7.png)

静态定位是所有HTML元素的默认定位方式。具有静态定位的元素按照文档的正常流进行定位，无法通过CSS移动或重新定位。

以下是如何静态定位一个元素：

![](img/98aab824d4b448d096a9479cc5acb8dc_9.png)

![](img/98aab824d4b448d096a9479cc5acb8dc_11.png)

```css
div {
    position: static;
}
```

![](img/98aab824d4b448d096a9479cc5acb8dc_12.png)

![](img/98aab824d4b448d096a9479cc5acb8dc_14.png)

## 相对定位

![](img/98aab824d4b448d096a9479cc5acb8dc_16.png)

相对定位允许你相对于元素的正常位置进行定位。你可以使用 `top`、`bottom`、`left` 和 `right` 属性分别向上、下、左、右移动元素。

![](img/98aab824d4b448d096a9479cc5acb8dc_18.png)

以下是相对定位的示例：

![](img/98aab824d4b448d096a9479cc5acb8dc_20.png)

![](img/98aab824d4b448d096a9479cc5acb8dc_22.png)

```css
#second {
    position: relative;
    top: 10px;
    left: 20px;
}
```

![](img/98aab824d4b448d096a9479cc5acb8dc_24.png)

## 绝对定位

![](img/98aab824d4b448d096a9479cc5acb8dc_26.png)

![](img/98aab824d4b448d096a9479cc5acb8dc_28.png)

绝对定位允许你相对于其最近的非静态定位的祖先元素进行定位。如果没有这样的祖先元素，则相对于初始包含块（通常是 `<body>` 元素）定位。

![](img/98aab824d4b448d096a9479cc5acb8dc_30.png)

![](img/98aab824d4b448d096a9479cc5acb8dc_32.png)

![](img/98aab824d4b448d096a9479cc5acb8dc_34.png)

以下是绝对定位的示例：

```css
#absolute-element {
    position: absolute;
    top: 50px;
    left: 100px;
}
```

## 固定定位

![](img/98aab824d4b448d096a9479cc5acb8dc_36.png)

固定定位与绝对定位类似，但元素是相对于浏览器窗口的视口定位的。这意味着即使用户滚动页面，元素也会保持在相同的位置。

![](img/98aab824d4b448d096a9479cc5acb8dc_38.png)

![](img/98aab824d4b448d096a9479cc5acb8dc_40.png)

以下是固定定位的示例：

![](img/98aab824d4b448d096a9479cc5acb8dc_42.png)

![](img/98aab824d4b448d096a9479cc5acb8dc_44.png)

```css
#fixed-element {
    position: fixed;
    top: 0;
    left: 0;
}
```

![](img/98aab824d4b448d096a9479cc5acb8dc_46.png)

![](img/98aab824d4b448d096a9479cc5acb8dc_48.png)

## 核心概念总结

![](img/98aab824d4b448d096a9479cc5acb8dc_50.png)

![](img/98aab824d4b448d096a9479cc5acb8dc_52.png)

![](img/98aab824d4b448d096a9479cc5acb8dc_54.png)

![](img/98aab824d4b448d096a9479cc5acb8dc_56.png)

以下是四种主要CSS定位方式的对比：

![](img/98aab824d4b448d096a9479cc5acb8dc_58.png)

*   **静态定位**：默认值，元素处于正常文档流中。
*   **相对定位**：相对于自身正常位置偏移，原空间保留。
*   **绝对定位**：相对于最近的非静态定位祖先元素偏移，脱离文档流。
*   **固定定位**：相对于浏览器视口偏移，脱离文档流，滚动时位置固定。

本节课中我们一起学习了CSS的四种主要定位方式：静态定位、相对定位、绝对定位和固定定位。通过使用这些定位方式，你可以根据设计需求，以最佳方式在网页上定位元素。建议尝试不同的定位方式，看看哪种最适合你的设计。

![](img/98aab824d4b448d096a9479cc5acb8dc_60.png)

![](img/98aab824d4b448d096a9479cc5acb8dc_62.png)

下节课再见。🎼