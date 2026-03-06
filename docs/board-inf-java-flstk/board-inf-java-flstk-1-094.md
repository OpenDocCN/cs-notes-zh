# 094：伪类选择器（第二部分）🎯

## 概述

在本节课中，我们将继续学习CSS伪类选择器。上一节我们介绍了 `:hover`、`:active`、`:visited`、`:focus` 等常见伪类选择器。本节中，我们将深入探讨基于元素位置进行选择的伪类选择器，特别是 `:nth-child()`、`:first-child` 和 `:last-child`。

---

![](img/b78f33dcd09148cbf735204a8977dd50_1.png)

## 使用 `:nth-child()` 伪类选择器

`:nth-child()` 伪类选择器用于根据元素在其父元素中的位置来选择元素。这可以用来为每隔一个的元素设置样式，或者基于特定位置选择元素。

以下是 `:nth-child()` 的基本语法：
```css
selector:nth-child(expression) {
  /* 样式规则 */
}
```

让我们通过一个HTML示例来看看如何使用它。假设我们有以下包含多个段落的文档：

![](img/b78f33dcd09148cbf735204a8977dd50_3.png)

![](img/b78f33dcd09148cbf735204a8977dd50_5.png)

```html
<p>1</p>
<p>2</p>
<p>3</p>
<p>4</p>
<p>5</p>
<p>6</p>
<p>7</p>
<p>8</p>
```

现在，我们使用 `:nth-child()` 为这些段落标签应用样式。

![](img/b78f33dcd09148cbf735204a8977dd50_7.png)

### 选择特定位置的元素

如果我们想只对第一个段落应用样式，可以这样写：
```css
p:nth-child(1) {
  background-color: red;
}
```
这样，只有标有“1”的段落背景会变成红色。

![](img/b78f33dcd09148cbf735204a8977dd50_9.png)

同理，选择第五个段落：
```css
p:nth-child(5) {
  background-color: red;
}
```

### 选择偶数或奇数位置的元素

![](img/b78f33dcd09148cbf735204a8977dd50_11.png)

`:nth-child()` 的强大之处在于可以使用公式。

为所有偶数位置的元素设置样式：
```css
p:nth-child(2n) {
  background-color: red;
}
```
参数 `2n` 表示选择所有第 2、4、6、8... 个元素。

为所有奇数位置的元素设置样式：
```css
p:nth-child(2n+1) {
  background-color: red;
}
```
参数 `2n+1` 表示选择所有第 1、3、5、7... 个元素。

### 使用更复杂的公式

我们还可以使用更复杂的表达式。例如：
```css
p:nth-child(2n+3) {
  background-color: red;
}
```
这个公式会选择第 3、5、7... 个元素。因为当 `n=0` 时，是第3个元素；`n=1` 时，是第5个元素，依此类推。

![](img/b78f33dcd09148cbf735204a8977dd50_13.png)

![](img/b78f33dcd09148cbf735204a8977dd50_15.png)

### 使用关键字

![](img/b78f33dcd09148cbf735204a8977dd50_17.png)

`:nth-child()` 也接受 `odd`（奇数）和 `even`（偶数）关键字，使代码更易读。

![](img/b78f33dcd09148cbf735204a8977dd50_19.png)

选择所有奇数元素：
```css
p:nth-child(odd) {
  background-color: red;
}
```

选择所有偶数元素：
```css
p:nth-child(even) {
  background-color: red;
}
```

![](img/b78f33dcd09148cbf735204a8977dd50_21.png)

### 选择间隔元素

我们还可以每隔几个元素选择一次。例如，每隔两个元素选择第三个：
```css
p:nth-child(3n) {
  background-color: red;
}
```
这会对第 3、6、9... 个元素应用样式。

![](img/b78f33dcd09148cbf735204a8977dd50_23.png)

---

## 使用 `:first-child` 伪类选择器

![](img/b78f33dcd09148cbf735204a8977dd50_25.png)

在了解了 `:nth-child()` 之后，我们来看看 `:first-child`。这个选择器用于选择父元素下的第一个子元素，可以用来将第一个元素的样式设置得与其他元素不同。

其语法很简单：
```css
selector:first-child {
  /* 样式规则 */
}
```

让我们在之前的HTML上应用它。注释掉之前的 `:nth-child` 样式，添加：
```css
p:first-child {
  background-color: yellow;
}
```
你会发现，所有 `<p>` 标签中的第一个子元素（即标有“1”的段落）背景变成了黄色。

![](img/b78f33dcd09148cbf735204a8977dd50_27.png)

### 理解作用域

![](img/b78f33dcd09148cbf735204a8977dd50_29.png)

`:first-child` 的选择是基于其父元素上下文（作用域）的。考虑以下HTML结构：
```html
<p>1</p>
<p>2</p>
<p>3</p>
<p>4</p>
<div>
  <p>5</p>
  <p>6</p>
  <p>7</p>
  <p>8</p>
</div>
```
再次应用 `p:first-child { background-color: yellow; }`。

现在，标有“1”和“5”的段落背景都变成了黄色。这是因为：
*   在整个文档中，第一个 `<p>` 是“1”。
*   在 `<div>` 这个新的父元素作用域内，第一个 `<p>` 子元素是“5”。

---

![](img/b78f33dcd09148cbf735204a8977dd50_31.png)

## 使用 `:last-child` 伪类选择器

![](img/b78f33dcd09148cbf735204a8977dd50_33.png)

与 `:first-child` 相对应的是 `:last-child` 选择器，它用于选择父元素下的最后一个子元素。

语法如下：
```css
selector:last-child {
  /* 样式规则 */
}
```

让我们在上面的HTML示例中添加这个样式：
```css
p:last-child {
  background-color: red;
}
```
现在，你会发现最后一个 `<p>` 标签（在示例中是“8”）的背景变成了红色。它选择了所有 `<p>` 标签中作为其父元素最后一个子元素的那一个。

![](img/b78f33dcd09148cbf735204a8977dd50_35.png)

---

![](img/b78f33dcd09148cbf735204a8977dd50_37.png)

## 总结

![](img/b78f33dcd09148cbf735204a8977dd50_39.png)

本节课我们一起学习了三种基于位置的CSS伪类选择器：
1.  **`:nth-child(expression)`**：通过数字、公式（如 `2n+1`）或关键字（`odd`， `even`）选择特定位置或模式的子元素。
2.  **`:first-child`**：选择父元素下的第一个子元素。
3.  **`:last-child`**：选择父元素下的最后一个子元素。

![](img/b78f33dcd09148cbf735204a8977dd50_41.png)

这些选择器能让你更精准、更高效地控制页面元素的样式，尤其是在处理列表、表格或任何重复性内容时。希望你能在下一个项目中灵活运用它们。