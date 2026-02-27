# 008：CSS布局基础

![](img/09a1cfcc5feeccb105f8c2571acc9c57_1.png)

在本节课中，我们将学习CSS布局的核心概念，包括盒模型、元素的显示类型以及几种传统的页面布局方法。掌握这些基础知识是构建复杂网页结构的第一步。

## 盒模型 📦

![](img/09a1cfcc5feeccb105f8c2571acc9c57_3.png)

上一节我们介绍了CSS的基本格式化，本节中我们来看看网页布局的基石——盒模型。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_5.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_7.png)

网页上的每个`<div>`元素（以及许多其他元素）都遵循盒模型。盒模型是一个简单的概念：每个元素都被视为一个矩形盒子，这个盒子由内到外依次是**内容**、**内边距**、**边框**和**外边距**。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_9.png)

*   **内容**：元素的实际内容，如文本或图片，具有宽度和高度。
*   **内边距**：内容与边框之间的透明区域。
*   **边框**：围绕在内边距外部的边界线。
*   **外边距**：边框外部的透明区域，用于分隔其他元素。

我们可以通过CSS来设置这些属性。例如，创建一个名为`.box`的`<div>`：

![](img/09a1cfcc5feeccb105f8c2571acc9c57_11.png)

```css
.box {
  width: 200px;
  height: 200px;
  background-color: blue;
  color: white;
  border: 1px solid yellow;
  padding: 10px;
  margin: 20px;
}
```

![](img/09a1cfcc5feeccb105f8c2571acc9c57_13.png)

*   `width`和`height`定义了内容区域的尺寸。
*   `background-color`会覆盖内容和内边距区域，但不会覆盖外边距。
*   `border`在元素周围创建可见的边界。
*   `padding`在内容和边框之间增加空间。
*   `margin`在元素外部创建空间，用于与其他元素隔开。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_14.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_15.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_17.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_19.png)

内边距和外边距的主要区别在于：内边距是元素内部空间，背景色会覆盖它；外边距是元素外部空间，用于控制元素与其他元素的距离。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_21.png)

## 块级与行内元素 🧱

![](img/09a1cfcc5feeccb105f8c2571acc9c57_23.png)

理解了盒模型后，我们需要知道并非所有元素都以相同方式参与布局。这主要取决于元素的`display`属性。

`<div>`默认是一个**块级元素**。块级元素的行为特点是：
*   总是从新的一行开始。
*   默认会占据其父容器100%的宽度（即使设置了固定宽度，剩余空间也会被外边距自动填充）。

`<span>`默认是一个**行内元素**。行内元素的行为特点是：
*   不会从新行开始，会与其他行内元素并排显示。
*   对`width`和`height`属性不敏感，其尺寸由内容决定。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_25.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_27.png)

我们可以通过CSS的`display`属性来改变元素的默认行为：
*   `display: block;`：将元素变为块级元素（如将`<span>`变为块级）。
*   `display: inline;`：将元素变为行内元素（如将`<div>`变为行内）。
*   `display: inline-block;`：一种混合模式。元素像行内元素一样并排显示，但同时可以设置`width`和`height`，非常实用。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_29.png)

此外，`display`还有两个特殊值用于控制元素可见性：
*   `display: none;`：完全从页面布局中移除元素，就像它不存在一样。
*   `visibility: hidden;`：元素仍占据布局空间，只是不可见。相比之下，`display: none;`更常用。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_31.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_33.png)

## 传统布局方法：浮动 🎈

![](img/09a1cfcc5feeccb105f8c2571acc9c57_35.png)

现在我们已经掌握了布局的基本组件，本节中我们来看看几种传统的页面布局方法。首先是**浮动**。

`float`属性是一个较老的布局技术，现在已不推荐广泛使用，但在某些特定场景或旧代码中仍可能遇到。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_37.png)

`float`属性允许你将一个元素向左或向右移动，使其脱离正常的文档流，并允许后续的**行内内容**（如文本）环绕它。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_39.png)

```css
.floater {
  width: 50px;
  height: 50px;
  background-color: purple;
  float: left;
  margin: 10px;
}
```

浮动元素的怪异行为在于：它只会影响后面的行内内容（使其环绕），但不会影响后面的块级元素。为了清除浮动对后续块级元素的影响，可以使用`clear`属性：
```css
.cleared-box {
  clear: both; /* 也可以是 left 或 right */
}
```

![](img/09a1cfcc5feeccb105f8c2571acc9c57_41.png)

浮动在过去常被用来创建多栏布局，例如一个侧边栏加一个主内容区。但这种方法计算复杂且不灵活，现代布局技术已提供了更好的解决方案。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_42.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_44.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_45.png)

## 传统布局方法：定位 🎯

![](img/09a1cfcc5feeccb105f8c2571acc9c57_47.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_49.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_51.png)

另一种更强大且至今仍有用的布局技术是**定位**。`position`属性有四个主要值：`static`、`relative`、`absolute`和`fixed`。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_53.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_54.png)

*   **`static`**：默认值。元素处于正常的文档流中。
*   **`relative`**：元素先被放置在正常文档流中，然后可以使用`top`、`right`、`bottom`、`left`属性相对于其**原始位置**进行偏移。
    ```css
    .relative-box {
      position: relative;
      top: 10px;
      left: 20px;
    }
    ```
*   **`absolute`**：元素被移出正常文档流。其位置相对于**最近的、非`static`定位的祖先元素**进行偏移。如果没有这样的祖先，则相对于整个文档（`<body>`）。
    ```css
    .parent {
      position: relative; /* 为绝对定位的子元素提供参照 */
    }
    .absolute-box {
      position: absolute;
      bottom: 10px;
      right: 10px;
    }
    ```
    `position: absolute;`非常实用，常用于创建对话框、图标角标或精确放置在特定位置的元素。
*   **`fixed`**：元素被移出正常文档流，但其位置是相对于**浏览器视口**固定的。即使页面滚动，它也会停留在屏幕的同一位置。常用于导航栏、悬浮按钮或弹窗。
    ```css
    .fixed-popup {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%); /* 一种居中技巧 */
      width: 300px;
      background: black;
      color: white;
    }
    ```

## 其他布局相关技巧 🛠️

最后，我们补充几个与布局密切相关的实用CSS技巧。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_56.png)

**居中一个块级元素**：这是一个非常常见的需求。可以通过将左右外边距设置为`auto`来实现。
```css
.centered-div {
  width: 300px;
  margin: 0 auto; /* 上下外边距为0，左右自动平均分配 */
}
```

**处理内容溢出**：当元素内容超出其指定大小时，`overflow`属性决定了如何处理。
```css
.overflow-box {
  height: 100px;
  overflow: hidden; /* 隐藏超出的内容 */
  /* overflow: scroll; 添加滚动条 */
  /* overflow: auto; 仅在需要时添加滚动条 */
}
```

![](img/09a1cfcc5feeccb105f8c2571acc9c57_58.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_60.png)

*   `visible`：默认值，内容会渲染到盒子外面。
*   `hidden`：超出的内容被裁剪，不可见。
*   `scroll`：始终显示滚动条。
*   `auto`：由浏览器决定，仅在内容溢出时显示滚动条。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_62.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_64.png)

---

![](img/09a1cfcc5feeccb105f8c2571acc9c57_66.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_68.png)

![](img/09a1cfcc5feeccb105f8c2571acc9c57_70.png)

本节课中我们一起学习了CSS布局的基础知识。我们从**盒模型**开始，理解了每个元素的构成。然后探讨了**块级与行内元素**的根本区别。接着，我们介绍了两种传统布局方法：略显过时但需了解的**浮动**，以及依然强大实用的**定位**（`relative`、`absolute`、`fixed`）。最后，我们学习了一些实用技巧，如**元素居中**和**处理溢出内容**。

![](img/09a1cfcc5feeccb105f8c2571acc9c57_72.png)

布局是CSS中最具挑战性的部分之一，需要不断练习和积累。当遇到困难时，多参考在线示例和文档是非常有效的方法。在接下来的课程中，我们将学习更现代的布局工具，如Flexbox和Grid。