# 116：CSS文本效果

在本节课中，我们将学习CSS中一系列用于控制文本样式和布局的属性。这些属性可以帮助我们美化网页中的文字，实现对齐、装饰、间距调整以及阴影效果。

在上一节视频中，我们了解了`box-sizing`属性的工作原理及其如何帮助避免HTML项目中的布局问题。本节中，我们将深入探讨一些与CSS文本相关的属性。

我们已经学习了`font-family`、`font-weight`和`font-style`等属性如何帮助我们装饰HTML文档中的字体。本视频将介绍其他一些文本相关属性，例如`text-align`、`text-decoration`、`text-transform`、`letter-spacing`、`line-height`等。这些属性将帮助我们对齐文本、装饰文本、转换文本大小写，以及在单词和行之间添加间距。

现在，让我们在ST项目中实际操作这些属性。

## 文本对齐：`text-align`

![](img/b0df42051d120e42bfaf854d9da9c744_1.png)

![](img/b0df42051d120e42bfaf854d9da9c744_3.png)

以下是如何使用`text-align`属性来对齐文本。

`text-align`属性有不同的取值。默认值是`left`。

```css
text-align: left; /* 默认值，文本左对齐 */
```

如果我们将值改为`right`，文本将向右对齐。

```css
text-align: right;
```

![](img/b0df42051d120e42bfaf854d9da9c744_5.png)

类似地，如果设置为`center`，文本将居中对齐。

![](img/b0df42051d120e42bfaf854d9da9c744_7.png)

```css
text-align: center;
```

![](img/b0df42051d120e42bfaf854d9da9c744_9.png)

最后，我们还可以使用`justify`值。它会自动调整文本，使其左右两端都对齐。

```css
text-align: justify;
```

![](img/b0df42051d120e42bfaf854d9da9c744_11.png)

当文本左对齐时，文本靠左排列，如果单词在当前行放不下，会自动换行。而使用`justify`时，它会尝试调整整个文本，使其左右两边都对齐。

## 文本装饰：`text-decoration`

![](img/b0df42051d120e42bfaf854d9da9c744_13.png)

接下来，我们看看`text-decoration`属性。它用于为文本添加装饰线。

![](img/b0df42051d120e42bfaf854d9da9c744_14.png)

![](img/b0df42051d120e42bfaf854d9da9c744_15.png)

如果我们设置`text-decoration: overline;`，它会在所有文本上方添加一条线。

```css
text-decoration: overline;
```

![](img/b0df42051d120e42bfaf854d9da9c744_17.png)

如果设置值为`line-through`，文本中间会有一条贯穿线。

```css
text-decoration: line-through;
```

![](img/b0df42051d120e42bfaf854d9da9c744_19.png)

如果设置值为`underline`，文本下方会有一条下划线。

```css
text-decoration: underline;
```

![](img/b0df42051d120e42bfaf854d9da9c744_21.png)

![](img/b0df42051d120e42bfaf854d9da9c744_22.png)

最后，`overline underline`值会在文本的上下方都添加线条。

```css
text-decoration: overline underline;
```

![](img/b0df42051d120e42bfaf854d9da9c744_24.png)

这些是`text-decoration`属性的一些取值及其用例。

## 文本转换：`text-transform`

现在，让我们看看`text-transform`属性，它用于转换文本的大小写。

![](img/b0df42051d120e42bfaf854d9da9c744_26.png)

如果我们设置`text-transform: capitalize;`，每个单词的首字母会变成大写。

```css
text-transform: capitalize;
```

如果设置`text-transform: uppercase;`，整个文本会变成大写。

![](img/b0df42051d120e42bfaf854d9da9c744_28.png)

```css
text-transform: uppercase;
```

类似地，如果设置`text-transform: lowercase;`，整个文本会变成小写。

![](img/b0df42051d120e42bfaf854d9da9c744_30.png)

```css
text-transform: lowercase;
```

![](img/b0df42051d120e42bfaf854d9da9c744_32.png)

这些是`text-transform`属性的一些应用。

## 单词与字母间距：`word-spacing` 与 `letter-spacing`

接下来，我们看看`word-spacing`属性，它用于设置单词之间的间距。

我们可以设置一个值作为单词之间的空间单位。例如，设置`10px`会在每个单词之间产生10像素的间隙。

![](img/b0df42051d120e42bfaf854d9da9c744_34.png)

```css
word-spacing: 10px;
```

我们也可以将其设置为负值，例如`-1px`，这会减少单词间距。如果设置为`-10px`，单词甚至会重叠。

![](img/b0df42051d120e42bfaf854d9da9c744_36.png)

![](img/b0df42051d120e42bfaf854d9da9c744_37.png)

类似地，`letter-spacing`属性用于设置每个字母之间的间距。

![](img/b0df42051d120e42bfaf854d9da9c744_39.png)

```css
letter-spacing: 5px;
```

这会在文本中的每个字母之间产生5像素的间距。

![](img/b0df42051d120e42bfaf854d9da9c744_41.png)

## 行高：`line-height`

![](img/b0df42051d120e42bfaf854d9da9c744_43.png)

现在，让我们看看`line-height`属性，它用于设置文本行之间的高度或间距。

例如，设置`line-height: 10px;`会将行高减小到10像素。

```css
line-height: 10px;
```

如果增加到`200px`，行高会显著增大。

```css
line-height: 200px;
```

这就是`line-height`属性及其在HTML/CSS页面中的用法。

## 文本阴影：`text-shadow`

最后，我们介绍`text-shadow`属性，用于为文本添加阴影效果。

应用文本阴影时，我们需要设置四个值：
1.  水平阴影偏移量
2.  垂直阴影偏移量
3.  模糊半径
4.  阴影颜色

例如：
```css
text-shadow: 2px 2px 5px red;
```
- `2px`：水平阴影偏移量
- `2px`：垂直阴影偏移量
- `5px`：模糊半径
- `red`：阴影颜色

![](img/b0df42051d120e42bfaf854d9da9c744_45.png)

我们可以调整这些值来改变阴影效果。增加水平偏移量会使阴影水平方向更明显；增加垂直偏移量会使阴影垂直方向更明显；增加模糊半径会使阴影边缘更模糊。

本节课中，我们一起学习了CSS中一系列重要的文本相关属性，包括对齐、装饰、大小写转换、间距调整和阴影效果。掌握这些属性将极大地增强你美化网页文本的能力。希望你能理解并在下一个CSS项目中应用它们。

![](img/b0df42051d120e42bfaf854d9da9c744_47.png)

我们下个视频再见。