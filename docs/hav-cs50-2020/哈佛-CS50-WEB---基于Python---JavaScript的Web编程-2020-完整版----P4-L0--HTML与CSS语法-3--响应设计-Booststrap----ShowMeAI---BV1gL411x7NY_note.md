# 哈佛 CS50-WEB 4：L0- HTML与CSS语法 3 (响应设计，Bootstrap) 📱

![](img/d15ab487c4bc1743a9156bbc67f2189c_1.png)

在本节课中，我们将要学习如何让网页在不同尺寸的设备上都能良好显示，即响应式设计。我们将探讨实现响应式设计的多种方法，包括视口设置、媒体查询、Flexbox、Grid布局，并介绍如何使用Bootstrap库来快速构建美观且响应式的界面。最后，我们将学习Sass，一个强大的CSS扩展语言，它能帮助我们更高效、更结构化地编写样式代码。

## 响应式设计与视口 🌐

上一节我们介绍了如何使用CSS精确控制网页样式。本节中，我们来看看如何确保网页在各种设备上都能良好显示，这就是响应式设计。

响应式设计的关键在于确保我们的网页，无论用户如何查看，看起来都很好。如今，人们不仅用电脑，也常用手机或平板电脑查看网页。因此，以响应式的方式设计网页非常重要。

我们将探讨多种在网页中实现响应式设计的方法，首先从讨论视口开始。

视口是用户实际可以看到的屏幕的视觉部分，也就是整个网页区域中向用户显示内容的部分。

![](img/d15ab487c4bc1743a9156bbc67f2189c_3.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_5.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_7.png)

当你将网页转换到移动屏幕时会发生什么呢？许多移动设备默认情况下会将其视口视为与电脑屏幕相同的宽度，因为并非所有网页都针对移动设备优化。为了确保在移动设备上可以看到所有内容，许多手机会将网页缩小以适应移动屏幕，但这通常不是我们理想的效果。

![](img/d15ab487c4bc1743a9156bbc67f2189c_9.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_11.png)

我们希望页面能够适应不同尺寸的屏幕，让标题、图像和文本等元素能适当调整以填满整个屏幕。

我们可以做的一件简单事情是在HTML的`<head>`部分添加一行代码来控制视口：

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

![](img/d15ab487c4bc1743a9156bbc67f2189c_13.png)

这行代码提供了元数据，表示将视口宽度设置为设备的宽度。默认情况下，许多手机会使用比设备实际宽度更宽的视口。通过指定视口仅为设备宽度，页面在移动设备上看起来会好得多。

## 使用媒体查询 📏

除了添加视口代码，我们还可以对页面进行其他更改以使其在不同屏幕上看起来更好，其中一项重要技术是媒体查询。

媒体查询主要用于根据渲染页面的设备或屏幕大小来控制页面的显示方式。

![](img/d15ab487c4bc1743a9156bbc67f2189c_15.png)

以下是使用媒体查询的一个简单例子，它根据屏幕宽度改变页面背景色：

![](img/d15ab487c4bc1743a9156bbc67f2189c_17.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Example</title>
    <style>
        /* 如果屏幕宽度大于等于600像素 */
        @media (min-width: 600px) {
            body {
                background-color: red;
            }
        }
        /* 如果屏幕宽度小于等于599像素 */
        @media (max-width: 599px) {
            body {
                background-color: blue;
            }
        }
    </style>
</head>
<body>
    <h1>Welcome to my webpage</h1>
</body>
</html>
```

![](img/d15ab487c4bc1743a9156bbc67f2189c_19.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_21.png)

在这个例子中，当屏幕宽度大于等于600像素时，背景为红色；当屏幕宽度小于等于599像素时，背景变为蓝色。

我们能够使用媒体查询来微调页面在各种设备上的显示。你不仅可以控制背景颜色，还可以控制任何CSS属性，例如间距、填充，甚至可以使用`display`属性在小屏幕上隐藏某些元素。

媒体查询还可以检查设备是处于竖屏还是横屏模式，或者用户是否在尝试打印页面内容。

## 使用Flexbox进行布局 🔄

![](img/d15ab487c4bc1743a9156bbc67f2189c_23.png)

上一节我们介绍了如何使用媒体查询响应屏幕尺寸。本节中，我们来看看Flexbox，这是一个强大的CSS布局工具，特别适用于在响应式设计中排列多个元素。

![](img/d15ab487c4bc1743a9156bbc67f2189c_25.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_27.png)

如果我们有多个元素需要同时显示在同一页面上，并且不希望它们溢出，Flexbox非常有用。

![](img/d15ab487c4bc1743a9156bbc67f2189c_29.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_31.png)

想象在电脑显示器上显示六个元素，当转到移动屏幕时，如果它们都缩小到几乎不可见，效果可能不好。另一种方法是保持元素大小不变，但这会导致需要滚动。更好的方案是让元素能够自动换行。

![](img/d15ab487c4bc1743a9156bbc67f2189c_33.png)

Flexbox可以轻松实现这种换行效果。以下是一个使用Flexbox的例子：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flexbox Example</title>
    <style>
        #container {
            display: flex;
            flex-wrap: wrap;
        }
        #container div {
            background-color: green;
            font-size: 20px;
            margin: 20px;
            padding: 20px;
            width: 200px;
        }
    </style>
</head>
<body>
    <div id="container">
        <div>Sample text one</div>
        <div>Sample text two</div>
        <div>Sample text three</div>
        <div>Sample text four</div>
        <div>Sample text five</div>
        <div>Sample text six</div>
        <!-- 可以添加更多div -->
    </div>
</body>
</html>
```

在这个例子中，`#container`被设置为`display: flex`，并且`flex-wrap: wrap`允许子元素在容器宽度不足时自动换行。当页面缩小时，元素会移动到新行，从而适应不同尺寸的屏幕。

![](img/d15ab487c4bc1743a9156bbc67f2189c_35.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_37.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_39.png)

## 使用Grid进行布局 🗂️

![](img/d15ab487c4bc1743a9156bbc67f2189c_41.png)

除了Flexbox，CSS还提供了Grid布局，适用于需要在特定网格中排列元素的情况。

![](img/d15ab487c4bc1743a9156bbc67f2189c_43.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_45.png)

Grid布局允许你定义列和行的具体大小。以下是一个使用CSS Grid的例子：

![](img/d15ab487c4bc1743a9156bbc67f2189c_47.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grid Example</title>
    <style>
        #grid {
            background-color: green;
            display: grid;
            grid-gap: 20px 10px; /* 行间距 10px，列间距 20px */
            grid-template-columns: 200px 200px auto;
            padding: 20px;
        }
        .grid-item {
            background-color: white;
            font-size: 20px;
            padding: 20px;
            text-align: center;
        }
    </style>
</head>
<body>
    <div id="grid">
        <div class="grid-item">1</div>
        <div class="grid-item">2</div>
        <div class="grid-item">3</div>
        <div class="grid-item">4</div>
        <div class="grid-item">5</div>
        <div class="grid-item">6</div>
        <!-- 可以添加更多项目 -->
    </div>
</body>
</html>
```

![](img/d15ab487c4bc1743a9156bbc67f2189c_49.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_51.png)

这里，`#grid`被设置为`display: grid`。`grid-template-columns: 200px 200px auto;` 定义了三列：前两列固定为200像素宽，第三列自动调整以填充剩余空间。当屏幕尺寸变化时，第三列的宽度会动态变化。

## 使用Bootstrap库 🚀

![](img/d15ab487c4bc1743a9156bbc67f2189c_53.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_55.png)

上一节我们学习了如何使用原生CSS工具实现响应式布局。本节中，我们来看看Bootstrap，这是一个非常流行的CSS库，它提供了大量预定义的样式和组件，能帮助我们快速构建美观且响应式的网页，而无需从头编写所有样式。

![](img/d15ab487c4bc1743a9156bbc67f2189c_57.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_59.png)

要使用Bootstrap，只需在HTML文件的`<head>`部分添加其CSS链接：

![](img/d15ab487c4bc1743a9156bbc67f2189c_61.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_63.png)

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet">
```

![](img/d15ab487c4bc1743a9156bbc67f2189c_65.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_67.png)

添加后，Bootstrap会为页面应用一套默认样式，例如自定义字体。然后，你可以使用Bootstrap提供的类来快速添加样式化组件。

以下是使用Bootstrap警报组件的例子：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet">
    <title>Bootstrap Alert</title>
</head>
<body>
    <div class="alert alert-primary" role="alert">
        A simple primary alert!
    </div>
    <div class="alert alert-success" role="alert">
        A simple success alert!
    </div>
    <div class="alert alert-danger" role="alert">
        A simple danger alert!
    </div>
</body>
</html>
```

![](img/d15ab487c4bc1743a9156bbc67f2189c_69.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_71.png)

通过更改`alert-*`类（如`primary`、`success`、`danger`），可以快速改变警报的颜色和样式。

Bootstrap还包含一个强大的网格系统，用于创建响应式布局。它将每行分为12个等宽的单位列。

以下是Bootstrap网格列的一个基础示例：

![](img/d15ab487c4bc1743a9156bbc67f2189c_73.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_75.png)

```html
<div class="container">
    <div class="row">
        <div class="col-3">Column 1</div>
        <div class="col-3">Column 2</div>
        <div class="col-3">Column 3</div>
        <div class="col-3">Column 4</div>
    </div>
</div>
```

![](img/d15ab487c4bc1743a9156bbc67f2189c_77.png)

每个`.col-3`的div占用3个单位，一行4个正好占满12个单位。当屏幕缩小时，这些列会自动调整宽度。

你还可以指定不同屏幕尺寸下的列宽。例如，`.col-lg-3`表示在大屏幕上占3个单位，`.col-sm-6`表示在小屏幕上占6个单位。这样，元素可以根据屏幕大小自动换行排列。

## 使用Sass增强CSS ✨

上一节我们介绍了如何使用库来简化开发。本节中，我们来看看Sass，它是CSS的一个强大扩展，能帮助我们更高效、更结构化地编写样式代码，减少重复。

随着CSS代码量增长，可能会出现大量重复。Sass通过引入变量、嵌套和继承等功能来解决这个问题。

![](img/d15ab487c4bc1743a9156bbc67f2189c_79.png)

首先，Sass允许我们使用变量。在纯CSS中，如果一种颜色在多个地方使用，更改时需要修改多处。Sass的变量功能可以消除这种重复。

![](img/d15ab487c4bc1743a9156bbc67f2189c_81.png)

Sass文件使用`.scss`扩展名。以下是一个使用Sass变量的例子：

![](img/d15ab487c4bc1743a9156bbc67f2189c_83.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_85.png)

**variables.scss**
```scss
$color: red; // 定义变量

ul {
    font-size: 14px;
    color: $color; // 使用变量
}

![](img/d15ab487c4bc1743a9156bbc67f2189c_87.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_89.png)

ol {
    font-size: 18px;
    color: $color; // 使用变量
}
```

浏览器无法直接理解Sass，需要先将Sass编译成标准的CSS。可以使用命令行工具`sass`进行编译：

![](img/d15ab487c4bc1743a9156bbc67f2189c_91.png)

```bash
sass variables.scss variables.css
```

![](img/d15ab487c4bc1743a9156bbc67f2189c_93.png)

编译后生成的`variables.css`文件就可以像普通CSS一样链接到HTML中。如果需要修改变量值，只需在`.scss`文件中更改一处，然后重新编译即可。

![](img/d15ab487c4bc1743a9156bbc67f2189c_95.png)

为了方便，可以使用`--watch`参数让Sass自动监控文件变化并重新编译：

![](img/d15ab487c4bc1743a9156bbc67f2189c_97.png)

```bash
sass --watch variables.scss variables.css
```

![](img/d15ab487c4bc1743a9156bbc67f2189c_99.png)

其次，Sass允许选择器嵌套，这能让结构更清晰。例如，你想样式化所有在`div`内部的段落：

![](img/d15ab487c4bc1743a9156bbc67f2189c_101.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_103.png)

**nested.scss**
```scss
div {
    font-size: 18px;
    p {
        color: blue;
    }
    ul {
        color: green;
    }
}
```

这会被编译为：
```css
div { font-size: 18px; }
div p { color: blue; }
div ul { color: green; }
```

![](img/d15ab487c4bc1743a9156bbc67f2189c_105.png)

最后，Sass支持继承，这有助于减少通用样式的重复。例如，多种类型的消息框有共同的样式，但背景色不同：

**inheritance.scss**
```scss
%message {
    font-family: sans-serif;
    font-size: 18px;
    border: 1px solid black;
    padding: 20px;
    margin: 20px;
}

.success {
    @extend %message;
    background-color: green;
}

![](img/d15ab487c4bc1743a9156bbc67f2189c_107.png)

.warning {
    @extend %message;
    background-color: orange;
}

![](img/d15ab487c4bc1743a9156bbc67f2189c_109.png)

![](img/d15ab487c4bc1743a9156bbc67f2189c_111.png)

.error {
    @extend %message;
    background-color: red;
}
```

![](img/d15ab487c4bc1743a9156bbc67f2189c_113.png)

通过`@extend`，`.success`、`.warning`和`.error`类都继承了`%message`占位符的所有样式，并各自添加了独特的背景色。

![](img/d15ab487c4bc1743a9156bbc67f2189c_115.png)

## 总结 📝

![](img/d15ab487c4bc1743a9156bbc67f2189c_117.png)

本节课中我们一起学习了网页响应式设计与CSS高级工具。

我们首先了解了响应式设计的重要性，并学习了如何通过设置视口来为移动设备优化网页。

接着，我们探讨了使用媒体查询来根据屏幕尺寸应用不同的CSS样式。

然后，我们介绍了两种强大的CSS布局模型：Flexbox和Grid，它们能帮助我们轻松创建适应不同屏幕的复杂布局。

![](img/d15ab487c4bc1743a9156bbc67f2189c_119.png)

之后，我们认识了Bootstrap库，它提供了大量预构建的响应式组件和网格系统，能极大提高前端开发效率。

最后，我们学习了Sass，这是一个CSS预处理器，它通过变量、嵌套和继承等功能，让我们能够编写更简洁、更易维护的样式代码。

![](img/d15ab487c4bc1743a9156bbc67f2189c_121.png)

通过这些工具和技术，我们可以确保自己构建的网页在任何设备上都能提供良好的用户体验。接下来，我们将学习如何将这些静态网页技术与Python、JavaScript等动态语言结合，构建功能丰富的Web应用。