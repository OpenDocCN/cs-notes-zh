# 34：使用嵌入式资源 🖼️

在本节课中，我们将学习在 React 应用中显示图像的三种不同方法。你将掌握如何通过 `import` 语句、`require` 函数以及直接使用网络图片 URL 来嵌入和使用图像资源。

## 概述

为了演示如何在 React 应用中处理嵌入式资源，我创建了一个名为 “embedded assets” 的基础应用。在应用的 `src` 文件夹中，我添加了一个 `assets` 文件夹，其中又包含一个 `images` 文件夹，里面存放了一张名为 “Central Park” 的 JPEG 图片。

![](img/ad7b69a57c5f8e389f5dea5a7dd1c4c5_1.png)

![](img/ad7b69a57c5f8e389f5dea5a7dd1c4c5_1.png)

现在，让我们打开 `App.js` 文件来查看应用组件的初始代码。代码中包含了一些描述当前任务的文本，即展示三张带有样式的图片。接下来，我将逐一演示三种导入图片的方法。

## 方法一：使用 `import` 语句

第一种方法是使用 `import` 语句。这种方法允许你为导入的图片设置一个变量名。

要导入 “Central Park” 图片文件，我需要输入 `import` 关键字，然后提供图片的相对路径。在我的例子中，文件位于 `assets/images` 文件夹内。

```javascript
import rooftops from ‘./assets/images/CentralPark.jpg‘;
```

导入后，我将在代码中渲染一个 `<img>` 标签。我使用 `height` 属性将图片高度限制为 200 像素，并将 `src` 属性设置为变量 `rooftops`，它包含了图片文件的路径。最后，遵循最佳实践，我添加了一个 `alt` 属性来描述图片内容。

```javascript
<img height={200} src={rooftops} alt=“Central Park rooftops view” />
```

![](img/ad7b69a57c5f8e389f5dea5a7dd1c4c5_3.png)

保存文件后，可以看到图片已成功在浏览器中显示。这就是使用 `import` 语句导入图片的第一种方法。

## 方法二：使用 `require` 函数

![](img/ad7b69a57c5f8e389f5dea5a7dd1c4c5_3.png)

上一节我们介绍了使用 `import` 语句，本节中我们来看看第二种方法：使用 `require` 函数。

同样，我先创建一个 `<img>` 标签，并将高度限制为 200 像素。但这次，我将 `src` 属性设置为 `require()` 函数调用的结果。我需要将图片的相对路径作为字符串传递给这个函数。

```javascript
<img height={200} src={require(‘./assets/images/CentralPark.jpg‘)} alt=“Central Park view from require” />
```

保存代码后，第二张图片也成功显示。请注意，使用这种方法时，我不需要在文件顶部预先导入图片，只需在 `src` 属性中直接调用 `require` 并传入路径字符串即可。

## 方法三：使用网络图片 URL

前面两种方法都用于加载本地图片文件，现在我们来学习第三种方法：加载托管在互联网上的图片。

这次，我想展示一个来自图片托管网站的随机图片。首先，我创建一个变量来存储这个图片的 URL。

```javascript
const randomImageUrl = ‘https://images.unsplash.com/photo-...‘;
```

然后，我可以在 `return` 语句中添加第三个 `<img>` 元素，并将 `src` 属性设置为上面定义的变量 `randomImageUrl`。

```javascript
<img height={200} src={randomImageUrl} alt=“Random image from the web” />
```

![](img/ad7b69a57c5f8e389f5dea5a7dd1c4c5_5.png)

## 总结

本节课中，我们一起学习了在 React 组件中使用图像资源的三种不同方式：
1.  使用 **`import` 语句**预先导入本地图片。
2.  使用 **`require()` 函数**在需要时动态引入本地图片路径。
3.  直接使用 **网络图片的 URL** 来加载远程资源。

![](img/ad7b69a57c5f8e389f5dea5a7dd1c4c5_5.png)

每种方法都有其适用场景，你可以根据项目需求灵活选择。