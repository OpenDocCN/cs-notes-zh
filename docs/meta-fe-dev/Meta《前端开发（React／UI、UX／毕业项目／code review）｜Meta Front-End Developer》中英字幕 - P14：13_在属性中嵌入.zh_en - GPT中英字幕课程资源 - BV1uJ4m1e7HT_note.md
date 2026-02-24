# Meta前端开发课程：P14：在属性中嵌入JS表达式 🖼️

在本节课中，我们将学习如何在React应用的HTML属性中嵌入JavaScript表达式。具体来说，我们将通过一个向应用添加并渲染图像的实例，演示如何操作`<img>`标签的`src`属性。

## 概述

我们将从一个简单的React应用开始，它目前只渲染一个标题。我们的目标是导入一张图片，并将其作为一个组件的属性进行渲染。这个过程涉及导入资源、创建组件以及在JSX属性中使用JavaScript表达式。

## 项目初始状态

首先，我们位于新项目的`App.js`文件中。初始的`App`组件仅返回一个包含“Hello World”文本的`<h1>`标题。

```jsx
function App() {
  return <h1>Hello World</h1>;
}
```

![](img/bb3d49563098c48ae4114f75a71efe6f_1.png)

## 准备图像资源

![](img/bb3d49563098c48ae4114f75a71efe6f_2.png)

![](img/bb3d49563098c48ae4114f75a71efe6f_3.png)

我已经从Coursera的GitHub账户（通过公开的GitHub API获取）复制了一张头像图片，并将其粘贴到项目`src`文件夹的根目录下，命名为`avatar.png`。

为了在组件中使用这张图片，我需要先将其导入。

## 导入图像

在`App.js`文件中，使用`import`语句导入图像资源。

```jsx
import avatar from './avatar.png';
```

## 创建Logo组件

接下来，我在`App.js`文件中添加一个名为`Logo`的新函数。虽然`Logo`本质上是一个独立的组件，但为了本示例的简洁性，我将代码保存在`App`组件内部，而非单独的文件中。

`Logo`函数接受一个`props`对象作为参数。在函数内部，我声明了一个`userPic`常量，并为其分配一个JSX元素。

以下是`Logo`组件的代码：

```jsx
function Logo(props) {
  const userPic = <img src={avatar} alt="User Avatar" />;
  return userPic;
}
```

在这个`<img>`元素中，我将导入的`avatar.png`图像作为`src`属性的值进行传递。

## 渲染Logo组件

现在，回到`App`组件中，我通过在`return`语句中添加`<Logo />`元素来渲染`Logo`组件。

更新后的`App`组件代码如下：

```jsx
function App() {
  return (
    <div>
      <h1>Hello World</h1>
      <Logo />
    </div>
  );
}
```

## 结果预览

在浏览器中预览我的应用。效果很好，它同时显示了标题文本和图像。

需要记住的是，如果继续构建包含更多组件的应用，最佳实践是将`Logo`组件提取到它自己的文件中，然后在需要时导入并渲染它。

![](img/bb3d49563098c48ae4114f75a71efe6f_5.png)

## 总结

![](img/bb3d49563098c48ae4114f75a71efe6f_6.png)

本节课我们一起完成了一个完整的演示，展示了如何在属性中嵌入JSX表达式。在这个案例中，我们操作的是HTML图像标签的`src`属性。我们学习了导入本地资源、在组件内封装逻辑以及最终在应用中渲染组件的基本流程。