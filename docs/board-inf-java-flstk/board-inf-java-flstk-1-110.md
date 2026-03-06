# 110：CSS Grid布局（第二部分）📐

![](img/b7661b9822339ca85c09f75cd2ac9611_0.png)

![](img/b7661b9822339ca85c09f75cd2ac9611_2.png)

在本节课中，我们将继续深入学习CSS Grid布局。上一节我们介绍了如何使用`grid-template-columns`和`grid-template-rows`来定义网格的列与行。本节中，我们将探索另一种强大的布局方式：**网格模板区域**，并学习如何精确控制网格项的位置与对齐方式。

![](img/b7661b9822339ca85c09f75cd2ac9611_4.png)

## 概述：网格模板区域

![](img/b7661b9822339ca85c09f75cd2ac9611_6.png)

![](img/b7661b9822339ca85c09f75cd2ac9611_8.png)

`grid-template-areas`属性允许我们通过为网格区域命名来直观地定义布局结构。这是一种声明式的布局方法。

以下是定义网格模板区域的步骤：

![](img/b7661b9822339ca85c09f75cd2ac9611_10.png)

![](img/b7661b9822339ca85c09f75cd2ac9611_12.png)

1.  在网格容器中，使用`grid-template-areas`属性定义区域布局。
2.  为每个网格项分配一个`grid-area`名称，使其填充对应的区域。

![](img/b7661b9822339ca85c09f75cd2ac9611_14.png)

![](img/b7661b9822339ca85c09f75cd2ac9611_16.png)

例如，我们可以这样定义一个包含页眉、侧边栏和内容区的布局：
```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr;
  grid-template-rows: auto 1fr;
  grid-template-areas:
    "header header"
    "sidebar content";
}

.item1 { grid-area: header; }
.item2 { grid-area: sidebar; }
.item3 { grid-area: content; }
```
通过这种方式，我们可以清晰地看到页眉横跨两列，侧边栏和内容区分别占据第二行的两列。

![](img/b7661b9822339ca85c09f75cd2ac9611_18.png)

![](img/b7661b9822339ca85c09f75cd2ac9611_20.png)

## 精确控制网格项位置

![](img/b7661b9822339ca85c09f75cd2ac9611_22.png)

除了使用命名区域，我们还可以通过指定网格线的起始和结束位置来精确控制网格项的尺寸和位置。

![](img/b7661b9822339ca85c09f75cd2ac9611_24.png)

以下是相关的CSS属性：

*   `grid-column-start`: 定义网格项从哪条垂直网格线开始。
*   `grid-column-end`: 定义网格项到哪条垂直网格线结束。
*   `grid-row-start`: 定义网格项从哪条水平网格线开始。
*   `grid-row-end`: 定义网格项到哪条水平网格线结束。

![](img/b7661b9822339ca85c09f75cd2ac9611_26.png)

这些属性可以简写为：
*   `grid-column: <start-line> / <end-line>;`
*   `grid-row: <start-line> / <end-line>;`

![](img/b7661b9822339ca85c09f75cd2ac9611_28.png)

**重要提示**：网格线编号从1开始，并且包括每条列/行之间的隐性格线。例如，一个3列的网格有4条垂直网格线。

我们也可以使用`span`关键字来指定网格项跨越的轨道数量，这通常更为直观：
```css
.item {
  /* 从第1条网格线开始，跨越3列 */
  grid-column: 1 / span 3;
  /* 从第2条网格线开始，跨越2行 */
  grid-row: 2 / span 2;
}
```

## 网格内容的对齐

CSS Grid提供了强大的属性来控制网格容器内所有网格项的对齐方式。

![](img/b7661b9822339ca85c09f75cd2ac9611_30.png)

以下是控制对齐的核心属性：

![](img/b7661b9822339ca85c09f75cd2ac9611_32.png)

*   **水平对齐**：使用`justify-content`属性。其常用值包括：
    *   `start`: 将网格项对齐到容器的起始边缘（左对齐）。
    *   `end`: 将网格项对齐到容器的结束边缘（右对齐）。
    *   `center`: 将网格项在容器内水平居中。
    *   `space-between`: 在网格项之间均匀分配空间，首尾项紧贴容器边缘。
    *   `space-around`: 在每个网格项周围分配相等的空间。
    *   `space-evenly`: 在网格项之间以及项与容器边缘之间分配相等的空间。

![](img/b7661b9822339ca85c09f75cd2ac9611_34.png)

![](img/b7661b9822339ca85c09f75cd2ac9611_36.png)

*   **垂直对齐**：使用`align-content`属性。其取值与`justify-content`相同，但作用于垂直方向。
    *   `start`: 顶部对齐。
    *   `end`: 底部对齐。
    *   `center`: 垂直居中。
    *   `space-between`、`space-around`、`space-evenly`: 在垂直方向上均匀分配空间。

![](img/b7661b9822339ca85c09f75cd2ac9611_38.png)

例如，要使网格内容在容器内完全居中：
```css
.container {
  display: grid;
  height: 100vh; /* 使容器有足够高度以观察垂直对齐效果 */
  justify-content: center; /* 水平居中 */
  align-content: center;   /* 垂直居中 */
}
```

![](img/b7661b9822339ca85c09f75cd2ac9611_40.png)

![](img/b7661b9822339ca85c09f75cd2ac9611_42.png)

![](img/b7661b9822339ca85c09f75cd2ac9611_44.png)

![](img/b7661b9822339ca85c09f75cd2ac9611_46.png)

## 总结

![](img/b7661b9822339ca85c09f75cd2ac9611_48.png)

![](img/b7661b9822339ca85c09f75cd2ac9611_50.png)

本节课中我们一起学习了CSS Grid布局的进阶技巧。我们掌握了如何使用`grid-template-areas`进行直观的布局规划，以及如何通过`grid-column`和`grid-row`属性（结合网格线编号或`span`关键字）来精确定位网格项。最后，我们探讨了`justify-content`和`align-content`属性，它们能帮助我们在网格容器内轻松实现各种复杂的对齐需求。结合这些强大的工具，你可以创建出既灵活又响应迅速的网页布局。