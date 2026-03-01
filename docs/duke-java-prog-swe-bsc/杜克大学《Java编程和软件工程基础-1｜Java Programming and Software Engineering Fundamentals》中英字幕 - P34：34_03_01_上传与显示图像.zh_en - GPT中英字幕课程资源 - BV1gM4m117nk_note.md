# Java编程和软件工程基础：P34：上传与显示图像 📤🖼️

![](img/c23209ebfc002bd1851e006728e41cfb_0.png)

在本节课中，我们将学习几个核心概念，这些概念将允许你上传图像文件并在HTML画布中显示它们。

随着我们朝着为绿屏算法创建交互式网页的目标迈进，我们需要一些新的编程概念和JavaScript工具。通过这些新概念和工具，你将能够创建更多网页，从一个非常简单的页面逐步过渡到更复杂、更具创意的绿屏和迷你项目页面。

我们将从一个原型开始，这是一个我们想要实现的网页模型，但更易于理解。我们需要一种新型的输入元素来上传图像文件，但在这个第一个原型中，我们将从一个简单的想法开始，以便我们可以专注于概念，而不是新HTML元素的细节。

一个更简单的输入类型是文本输入，它将显示一个文本框，就像你在这里看到的那样，允许用户输入文本。我们将用这个原型来测试和理解处理这个以及任何其他HTML元素的JavaScript概念。

然后，我们将把输入类型改为文件，并介绍上传图像文件并在HTML画布中显示它所需的概念。

让我们看看这个原型，以理解网页和JavaScript。

## 理解原型

HTML文本输入元素允许用户输入任何文本。正如你在这个简单页面中看到的，用户输入了“Lion.jpg”并即将点击按钮。

这里我们将使用一个按钮来处理事件。当用户按下回车键时处理文本是可能的，但我们将使用按钮，因为它们更常见。像往常一样，当用户点击按钮生成事件时，我们将编写JavaScript来处理该事件。这里使用`onclick`事件处理程序。

以下是处理用户输入内容的JavaScript代码：

```javascript
function handleUpload() {
    var textInput = document.getElementById('textInput');
    var userText = textInput.value;
    alert("你输入的文件名是: " + userText);
}
```

我们使用熟悉的JavaScript来访问文本输入元素的值，并在警告框中显示该结果。因此，当用户点击“上传”时，警告框会弹出。

请记住，这是一个文本输入的例子。输入元素不关心我们是否输入了文件名。我们本可以输入任何文本。当我们把输入类型改为文件时，我们将确保获得的值代表一个实际的文件，不过，正如我们很快将看到的，我们需要做一些工作来确保该文件是一个图像。

## 从文本到文件上传

上一节我们介绍了使用文本输入的原型，本节中我们来看看如何将其扩展为允许用户选择图像文件、上传并显示的网页。

我们将用一个类型为`file`的单一输入，替换原来的文本输入和按钮输入。我们将从用户选择并上传的文件创建一个图像。这将是一个来自Duke Learn to Program库的简单图像，你之前已经使用过。

通过扩展我们在原型中看到的功能，你将创建这个网页。从熟悉的东西开始有助于理解新概念，在本例中，是文件输入和一个JavaScript代码库。从熟悉的东西开始也有助于调试，因为我们从一个正常工作的网页和JavaScript开始。

让我们看看HTML和JavaScript如何结合，允许你上传和显示图像。

## 文件输入HTML元素

以下是用于指定输入元素的HTML代码，该元素允许用户选择文件并将其上传到网站。

```html
<input type="file" id="fileInput" multiple="false" accept="image/*" onchange="uploadImage()">
```

你将使用`file`而不是`button`或`color`作为输入的类型。

你将确保用户只上传一个文件，而不是多个，通过使用`multiple`属性并将其设置为`false`，表示不能选择多个文件。

你将只允许用户选择图像文件，例如，不允许选择文本文件或音频文件。你通过为`accept`属性指定一个值来实现这一点。该值是`image/*`，如上所示，`*`表示所有图像类型，而不仅仅是JPEG。

像往常一样，你将提供一个`id`，以便可以在你的JavaScript代码中找到这个元素。

你将使用`onchange`作为事件处理程序。当用户通过点击输入元素上显示的按钮选择文件时，会触发此事件。

请注意，你不需要添加按钮元素；它已包含在文件输入类型中。

## 处理上传的JavaScript

当用户点击“选择文件”时，会出现一个文件选择器（这个只允许图像文件；你的可能看起来不同，因为不同的浏览器处理此限制的方式不同）。一旦选择了图像“Lion.jpg”，文件输入的内容就会改变。这会触发`onchange`事件处理程序。

那么，让我们看看`upload`函数应该是什么样子，以实现将图像显示在我们的画布元素中的目标。

```javascript
function uploadImage() {
    // 1. 获取画布和文件输入元素
    var canvas = document.getElementById('myCanvas');
    var fileInput = document.getElementById('fileInput');

    // 2. 从文件输入创建SimpleImage对象
    var image = new SimpleImage(fileInput);

    // 3. 将图像绘制到画布上
    image.drawTo(canvas);
}
```

`upload`函数通过HTML中指定的ID获取画布元素和文件输入元素。

然后，你将从HTML文件输入本身创建一个简单的图像变量。

等等，`SimpleImage`不是标准的JavaScript。它是为本课程创建的JavaScript代码库，托管在dukelearntoprogram.com。当你使用我们的自定义JavaScript环境时，代码会自动包含。但对于你创建的网页，你需要指定这个库的来源。

## 引入SimpleImage库

让我们看看在CodePen中如何操作。在CodePen页面的编辑视图中，JavaScript的源代码放在HTML面板中，而不是JavaScript面板中，包含在带有`src`（源）属性的开放和闭合的`<script>`标签内。

```html
<script src="https://www.dukelearntoprogram.com/course1/common/js/image/SimpleImage.js"></script>
```

你可以看到URL的最后一部分是`simpleimage.js`，因为这是我们希望页面能够使用的库。在CodePen之外，你也会使用`<script>`标签。这是从我们的Duke Learn to Program站点包含simpleimage.js库的代码。

现在我们知道了如何告诉网页在哪里找到我们的JavaScript代码，让我们完成将图像放入画布的过程。

我们刚刚从文件输入HTML元素创建了一个新的`SimpleImage`。

最后一步是使用`drawTo`方法，这是包含在SimpleImage库中的一个方法。我们将调用`image.drawTo()`并使用画布元素作为参数，以指示应将SimpleImage绘制到我们选择的特定画布上。

一如既往，你不应该试图记住所有这些方法，你可以随时查阅文档，比如来自dukelearntoprogram.com的这个文档。

## 总结

本节课中我们一起学习了如何创建一个允许用户上传并显示图像的网页。

我们从一个简单的文本输入原型开始，理解了事件处理的基本流程。然后，我们引入了HTML的`<input type="file">`元素，它内置了文件选择功能。通过设置`accept="image/*"`属性，我们限制了用户只能选择图像文件。

在JavaScript部分，我们学习了如何使用`onchange`事件来响应用户的文件选择操作。最关键的一步是使用`SimpleImage`这个专为课程设计的库，它能方便地从文件输入创建图像对象，并通过`drawTo(canvas)`方法将图像绘制到指定的HTML画布上。

最后，我们还了解了如何在网页的HTML头部通过`<script>`标签引入外部的JavaScript库（如SimpleImage.js），这是扩展网页功能的重要方式。

掌握了这些概念，你现在可以创建允许用户上传图像的网页了，这是实现更复杂图像处理应用（如绿屏算法）的基础。