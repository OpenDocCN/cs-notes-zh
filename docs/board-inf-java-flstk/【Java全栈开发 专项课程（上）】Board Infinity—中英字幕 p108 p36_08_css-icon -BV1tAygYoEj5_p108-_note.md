# Java全栈开发 专项课程（上）：P36_08：CSS图标 🎨

在本节课中，我们将要学习如何在网页中使用CSS图标。图标能够使网页更加生动、直观，并提升用户体验。

上一节我们介绍了CSS中与文本相关的样式属性，如文本装饰、文本转换和文本阴影等。本节中，我们来看看如何为网页添加图标。

## 概述

CSS本身没有提供内置的图标功能。为了在HTML网页中使用图标，我们需要借助第三方图标库，例如Font Awesome、Bootstrap Icons、Google Icons或W3.CSS Icons。使用这些库需要先将它们导入到项目中，然后即可使用它们提供的丰富图标资源。

## 导入图标库

首先，我们从一个空白的HTML页面开始。当前页面仅移除了默认的边距和内边距。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Icons</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
    </style>
</head>
<body>

![](img/f4785bf6339fa295b0a2c862c9a95cab_1.png)

</body>
</html>
```

为了添加图标，我们需要导入第三方库。以W3.CSS图标库为例，以下是导入步骤。

![](img/f4785bf6339fa295b0a2c862c9a95cab_3.png)

我们需要在HTML文档的`<head>`部分添加两个链接来导入该库。

```html
<link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
```

添加后，我们的HTML文档结构如下。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Icons</title>
    <link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
        }
    </style>
</head>
<body>

![](img/f4785bf6339fa295b0a2c862c9a95cab_5.png)

</body>
</html>
```

## 使用图标

![](img/f4785bf6339fa295b0a2c862c9a95cab_7.png)

导入库之后，就可以在页面中使用图标了。图标通常通过`<i>`标签并添加特定的CSS类来呈现。

![](img/f4785bf6339fa295b0a2c862c9a95cab_9.png)

例如，要添加一个“主页”图标，可以在`<body>`标签内插入以下代码。

```html
<i class="fa fa-home"></i>
```

保存并刷新页面，你将看到一个主页图标显示出来。

## 自定义图标样式

我们可以为图标添加自定义样式，例如改变其大小和颜色。这可以通过内联样式或内部样式表来实现。

首先，尝试使用内联样式。

![](img/f4785bf6339fa295b0a2c862c9a95cab_11.png)

```html
<i class="fa fa-home" style="font-size: 50px; color: blue;"></i>
```

![](img/f4785bf6339fa295b0a2c862c9a95cab_13.png)

然而，你可能会发现图标大小没有改变。这是因为图标库自带的CSS类优先级更高，覆盖了我们的内联样式。

为了强制应用我们的样式，需要使用CSS的`!important`规则。以下是使用内部样式表的示例。

在`<style>`标签内添加以下规则。

```css
i {
    font-size: 50px !important;
    color: blue !important;
}
```

![](img/f4785bf6339fa295b0a2c862c9a95cab_15.png)

现在保存并刷新页面，图标的大小和颜色都已按照我们的设定改变了。

## 探索更多图标

W3.CSS图标库提供了丰富的图标选择。要查看所有可用的图标，可以访问其官方文档。在那里，你可以找到图标的名称和对应的CSS类，然后根据需求在项目中使用。

![](img/f4785bf6339fa295b0a2c862c9a95cab_17.png)

除了W3.CSS，还有其他流行的图标库可供选择，例如Font Awesome、Google Material Icons和Bootstrap Icons。它们的导入和使用方式类似，通常都是通过链接引入CSS文件，然后使用特定的类名。

以下是使用不同图标库的通用步骤。

![](img/f4785bf6339fa295b0a2c862c9a95cab_19.png)

1.  在图标库官网找到CDN链接或下载指令。
2.  将链接添加到HTML文档的`<head>`部分。
3.  在需要图标的地方使用`<i>`或`<span>`标签，并添加库指定的CSS类名。

## 总结

![](img/f4785bf6339fa295b0a2c862c9a95cab_21.png)

本节课中我们一起学习了如何在网页中使用CSS图标。我们了解到CSS本身不提供图标，需要借助第三方图标库。我们以W3.CSS为例，演示了如何导入图标库、在页面中插入图标以及如何通过`!important`规则自定义图标的样式。掌握这些知识后，你就可以在未来的项目中灵活运用各种图标来增强界面的视觉效果和交互性了。