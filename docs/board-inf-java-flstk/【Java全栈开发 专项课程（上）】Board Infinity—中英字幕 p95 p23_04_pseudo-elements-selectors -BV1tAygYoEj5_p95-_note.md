# CSS 选择器：第23章：伪元素选择器 🎨

## 概述
在本节课中，我们将要学习 CSS 伪元素选择器。我们将了解什么是伪元素，它与伪类有何不同，并学习如何使用 `::before`、`::after`、`::first-line` 和 `::first-letter` 等伪元素来为网页元素的特定部分添加样式。

![](img/e9b208b583f68a5bca1e498728a153ac_1.png)

![](img/e9b208b583f68a5bca1e498728a153ac_3.png)

---

## 伪元素简介
上一节我们介绍了伪类选择器及其在 HTML 中的应用。本节中我们来看看伪元素选择器。

伪元素用于设置元素**特定部分**的样式，例如段落的第一个字母或第一行文本。伪元素通过**双冒号** `::` 来表示。

其基本语法为：
```css
selector::pseudo-element {
  property: value;
}
```

---

## `::before` 伪元素
`::before` 伪元素允许你在元素内容**之前**插入内容。这对于添加装饰性元素（如图标或线条）非常有用。

![](img/e9b208b583f68a5bca1e498728a153ac_5.png)

![](img/e9b208b583f68a5bca1e498728a153ac_6.png)

![](img/e9b208b583f68a5bca1e498728a153ac_7.png)

以下是 `::before` 伪元素的一个应用示例。假设我们有一个段落标签，内容为“Active”。

![](img/e9b208b583f68a5bca1e498728a153ac_9.png)

```html
<p>Active</p>
```

我们可以通过 CSS 在其前面添加一个绿色圆点：

![](img/e9b208b583f68a5bca1e498728a153ac_11.png)

```css
p::before {
  content: ''; /* 内容为空，用于创建纯样式元素 */
  display: inline-block;
  width: 20px;
  height: 20px;
  background-color: green;
  border: none;
  border-radius: 50px;
}
```

![](img/e9b208b583f68a5bca1e498728a153ac_13.png)

![](img/e9b208b583f68a5bca1e498728a153ac_15.png)

![](img/e9b208b583f68a5bca1e498728a153ac_16.png)

**代码解释**：
*   `content: '';`：这是 `::before` 和 `::after` 伪元素的必需属性。即使内容为空，也需要声明。
*   `display: inline-block;`：使伪元素以行内块级元素显示，可以设置宽高。
*   `width` 和 `height`：定义了圆点的大小。
*   `background-color`：设置圆点的颜色。
*   `border-radius: 50px;`：将方形变为圆形。

应用后，你会在“Active”文本前看到一个绿色圆点。这个圆点实际上是插入在 `<p>` 标签内部，位于其内容之前。

![](img/e9b208b583f68a5bca1e498728a153ac_18.png)

![](img/e9b208b583f68a5bca1e498728a153ac_20.png)

---

## `::after` 伪元素
顾名思义，`::after` 伪元素用于在元素内容**之后**插入内容。

我们继续在上一个段落的基础上，使用 `::after` 添加一个“新消息”提示：

```css
p::after {
  content: 'New Message'; /* 插入文本内容 */
  background-color: gray;
  color: black;
  opacity: 0.5;
  margin-left: 10px;
  padding: 2px;
}
```

**效果**：在“Active”文本后面，会出现一个半透明的灰色背景，上面写着“New Message”的标签。这模拟了聊天应用中常见的未读消息提示效果。

![](img/e9b208b583f68a5bca1e498728a153ac_22.png)

![](img/e9b208b583f68a5bca1e498728a153ac_24.png)

---

![](img/e9b208b583f68a5bca1e498728a153ac_26.png)

![](img/e9b208b583f68a5bca1e498728a153ac_28.png)

## `::first-line` 与 `::first-letter` 伪元素
除了插入内容，伪元素还可以用于修饰元素内已有的内容。

### `::first-line` 伪元素
`::first-line` 用于设置元素内**第一行文本**的样式。

假设我们有一个长段落：
```html
<p id="chat">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
```

![](img/e9b208b583f68a5bca1e498728a153ac_30.png)

![](img/e9b208b583f68a5bca1e498728a153ac_32.png)

我们可以用以下 CSS 高亮其第一行：
```css
#chat::first-line {
  background-color: yellow;
}
```
应用后，无论浏览器窗口如何调整，只有该段落的第一行文本会显示黄色背景。

![](img/e9b208b583f68a5bca1e498728a153ac_34.png)

![](img/e9b208b583f68a5bca1e498728a153ac_36.png)

### `::first-letter` 伪元素
`::first-letter` 用于设置元素内**第一个字母**的样式。

使用同一个段落，我们可以这样设置：
```css
#chat::first-letter {
  font-size: 2em;
  font-weight: bold;
  color: red;
}
```
应用后，段落的第一个字母“L”会变得更大、更粗且为红色，常用于创建首字下沉效果。

![](img/e9b208b583f68a5bca1e498728a153ac_38.png)

![](img/e9b208b583f68a5bca1e498728a153ac_40.png)

---

![](img/e9b208b583f68a5bca1e498728a153ac_42.png)

![](img/e9b208b583f68a5bca1e498728a153ac_44.png)

## 重要注意事项
需要记住的关键点是：伪元素**并不会**在页面文档对象模型（DOM）中实际添加新的 HTML 内容，它们只是通过 CSS 修改了现有内容的**视觉呈现**。

---

## 总结
本节课中我们一起学习了 CSS 伪元素选择器。
*   伪元素用于样式化元素内容的特定部分，使用双冒号 `::` 表示。
*   `::before` 和 `::after` 允许在元素内容的前后插入装饰性内容。
*   `::first-line` 和 `::first-letter` 用于修饰元素内已有的第一行或第一个字符。
*   伪元素通过 CSS 改变视觉表现，而不改变 HTML 结构。

![](img/e9b208b583f68a5bca1e498728a153ac_46.png)

![](img/e9b208b583f68a5bca1e498728a153ac_48.png)

希望你能在下一个项目中运用这些强大的样式工具。我们下个视频再见！