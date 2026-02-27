# 前端编程：09：CSS Flexbox 布局指南 🧩

在本节课中，我们将要学习 CSS Flexbox 布局。Flexbox 是一种现代的网页布局方式，旨在创建响应式、动态的网页结构，它能轻松处理不同尺寸的屏幕和内容变化。

![](img/79ffb9d111098a77d034f7280ff0842f_1.png)

![](img/79ffb9d111098a77d034f7280ff0842f_2.png)

## 为什么需要 Flexbox？

![](img/79ffb9d111098a77d034f7280ff0842f_4.png)

在传统布局中，若要将多个元素（例如三个盒子）水平排列并均匀分布，可能会遇到困难。例如，使用 `display: inline-block` 并设置 `width: 33%` 时，元素间的空白和边距会导致布局错乱，无法精确计算总宽度。

Flexbox 正是为了解决这类布局难题而设计的。它通过一个容器（父元素）来管理其内部项目（子元素）的排列方式，使得创建复杂的响应式布局变得非常简单。

## Flexbox 的核心概念

Flexbox 布局主要涉及两个部分：**容器**（Container）和**项目**（Items）。所有 Flexbox 属性都应用于这两者之一。

![](img/79ffb9d111098a77d034f7280ff0842f_6.png)

### 1. 创建 Flex 容器

要使用 Flexbox，首先需要将一个元素设置为 Flex 容器。这是通过给该元素的 CSS 添加 `display: flex;` 属性来实现的。

![](img/79ffb9d111098a77d034f7280ff0842f_8.png)

![](img/79ffb9d111098a77d034f7280ff0842f_9.png)

```css
.container {
  display: flex;
}
```

![](img/79ffb9d111098a77d034f7280ff0842f_11.png)

![](img/79ffb9d111098a77d034f7280ff0842f_12.png)

![](img/79ffb9d111098a77d034f7280ff0842f_14.png)

一旦容器被设置为 `flex`，其直接子元素就会自动成为 Flex 项目，并按照 Flexbox 的规则进行排列。

### 2. 控制排列方向：`flex-direction`

![](img/79ffb9d111098a77d034f7280ff0842f_16.png)

![](img/79ffb9d111098a77d034f7280ff0842f_17.png)

`flex-direction` 属性定义了 Flex 项目在容器内的排列方向（主轴方向）。它是一个应用于容器的属性。

![](img/79ffb9d111098a77d034f7280ff0842f_19.png)

![](img/79ffb9d111098a77d034f7280ff0842f_20.png)

![](img/79ffb9d111098a77d034f7280ff0842f_22.png)

以下是 `flex-direction` 的主要取值：
*   `row`（默认值）：项目从左到右水平排列。
*   `row-reverse`：项目从右到左水平排列。
*   `column`：项目从上到下垂直排列。
*   `column-reverse`：项目从下到上垂直排列。

![](img/79ffb9d111098a77d034f7280ff0842f_24.png)

通过改变 `flex-direction`，你可以轻松地重新排列内容的流向。

![](img/79ffb9d111098a77d034f7280ff0842f_26.png)

![](img/79ffb9d111098a77d034f7280ff0842f_27.png)

![](img/79ffb9d111098a77d034f7280ff0842f_29.png)

### 3. 主轴对齐：`justify-content`

`justify-content` 属性定义了 Flex 项目在**主轴**（由 `flex-direction` 定义的方向）上的对齐方式。它也是一个容器属性。

![](img/79ffb9d111098a77d034f7280ff0842f_31.png)

![](img/79ffb9d111098a77d034f7280ff0842f_32.png)

![](img/79ffb9d111098a77d034f7280ff0842f_33.png)

以下是 `justify-content` 的常用取值：
*   `flex-start`（默认）：项目向主轴起点对齐。
*   `flex-end`：项目向主轴终点对齐。
*   `center`：项目在主轴居中对齐。
*   `space-between`：项目均匀分布，第一个在起点，最后一个在终点，项目间间隔相等。
*   `space-around`：项目均匀分布，每个项目两侧的间隔相等，项目之间的间隔是项目与边框间隔的两倍。
*   `space-evenly`：项目均匀分布，所有间隔（项目之间、项目与边框）完全相等。

这个属性让你可以精细控制项目在水平（或垂直）方向上的分布。

![](img/79ffb9d111098a77d034f7280ff0842f_35.png)

![](img/79ffb9d111098a77d034f7280ff0842f_36.png)

### 4. 交叉轴对齐：`align-items`

![](img/79ffb9d111098a77d034f7280ff0842f_37.png)

`align-items` 属性定义了 Flex 项目在**交叉轴**（与主轴垂直的方向）上的对齐方式。它同样应用于容器。

![](img/79ffb9d111098a77d034f7280ff0842f_39.png)

以下是 `align-items` 的常用取值：
*   `stretch`（默认）：如果项目未设置高度，它将拉伸以填满容器高度。
*   `flex-start`：项目向交叉轴起点对齐（顶部）。
*   `flex-end`：项目向交叉轴终点对齐（底部）。
*   `center`：项目在交叉轴居中对齐。
*   `baseline`：项目按它们的基线对齐。

![](img/79ffb9d111098a77d034f7280ff0842f_41.png)

为了让 `align-items` 生效，通常需要为容器设置一个明确的高度。

![](img/79ffb9d111098a77d034f7280ff0842f_43.png)

### 5. 处理溢出：`flex-wrap`

![](img/79ffb9d111098a77d034f7280ff0842f_45.png)

默认情况下，所有 Flex 项目都会尝试排在一行（或一列）上。`flex-wrap` 属性定义了当一行（列）空间不足时，项目是否换行以及如何换行。

![](img/79ffb9d111098a77d034f7280ff0842f_47.png)

![](img/79ffb9d111098a77d034f7280ff0842f_48.png)

![](img/79ffb9d111098a77d034f7280ff0842f_49.png)

以下是 `flex-wrap` 的取值：
*   `nowrap`（默认）：不换行。
*   `wrap`：当空间不足时，项目换行到下一行（列）。
*   `wrap-reverse`：换行，但顺序相反。

![](img/79ffb9d111098a77d034f7280ff0842f_51.png)

![](img/79ffb9d111098a77d034f7280ff0842f_53.png)

![](img/79ffb9d111098a77d034f7280ff0842f_55.png)

当使用 `flex-wrap: wrap;` 后，你可以使用 `align-content` 属性来控制多行/多列在交叉轴上的对齐方式，其取值与 `justify-content` 类似。

![](img/79ffb9d111098a77d034f7280ff0842f_57.png)

## 项目（子元素）的属性

![](img/79ffb9d111098a77d034f7280ff0842f_59.png)

除了容器属性，Flex 项目本身也有一些重要属性。

![](img/79ffb9d111098a77d034f7280ff0842f_61.png)

### 1. 分配剩余空间：`flex`

![](img/79ffb9d111098a77d034f7280ff0842f_63.png)

`flex` 属性是 `flex-grow`、`flex-shrink` 和 `flex-basis` 的简写。它定义了项目如何分配容器中的剩余空间。

![](img/79ffb9d111098a77d034f7280ff0842f_65.png)

![](img/79ffb9d111098a77d034f7280ff0842f_66.png)

一个最常见的用法是 `flex: 1;`。这表示该项目会“增长”以填充可用空间。如果所有项目都设置为 `flex: 1;`，它们将等分空间。如果一个项目设置为 `flex: 2;`，而其他为 `flex: 1;`，那么前者占据的空间将是后者的两倍。

你也可以为某个项目设置固定宽度（如 `width: 50px;`），Flexbox 会智能地处理，让固定尺寸的项目保持大小，而其他具有 `flex` 属性的项目按比例分配剩余空间。

### 2. 调整顺序：`order`

`order` 属性可以改变 Flex 项目的显示顺序，而无需修改 HTML 结构。默认值为 0。数值越小，排列越靠前。

## 实践与学习资源

Flexbox 功能强大但选项较多，最佳学习方式是动手实践。你可以通过修改在线编辑器的代码来观察不同属性的效果。

此外，推荐两个优秀的学习资源：
1.  **CSS-Tricks 的 Flexbox 指南**：这是一个非常全面的属性参考网站，清晰地列出了容器和项目的所有属性。
2.  **Flexbox Froggy 游戏**：一个互动式学习游戏，通过解决谜题来掌握 Flexbox 的各种属性，寓教于乐。

![](img/79ffb9d111098a77d034f7280ff0842f_68.png)

![](img/79ffb9d111098a77d034f7280ff0842f_69.png)

## 总结

![](img/79ffb9d111098a77d034f7280ff0842f_71.png)

![](img/79ffb9d111098a77d034f7280ff0842f_72.png)

![](img/79ffb9d111098a77d034f7280ff0842f_74.png)

本节课我们一起学习了 CSS Flexbox 布局的核心知识。我们了解到 Flexbox 通过 `display: flex` 创建一个容器，并通过 `flex-direction`、`justify-content`、`align-items` 等容器属性来控制项目的排列、对齐与分布。同时，项目自身的 `flex` 和 `order` 属性提供了更精细的空间分配和顺序控制能力。

![](img/79ffb9d111098a77d034f7280ff0842f_76.png)

![](img/79ffb9d111098a77d034f7280ff0842f_78.png)

Flexbox 是构建现代、响应式网页布局的基石工具。虽然初学时有较多概念，但通过不断练习和查阅文档，你将能熟练运用它来创建各种复杂的页面结构。