# 115：CSS表单样式设计 🎨

![](img/e673f49c73b6fd6a64bcc9c6da074bc1_0.png)

在本节课中，我们将学习如何使用CSS来设计和美化HTML表单。表单是网页与用户交互的关键组件，良好的样式设计能提升用户体验。我们将从创建一个基础表单开始，逐步应用CSS样式，使其外观更加美观和专业。

上一节我们介绍了如何使用CSS处理图片，本节中我们来看看如何将CSS应用于表单元素。

## 创建基础HTML表单结构

首先，我们需要创建一个包含基本输入字段的HTML表单。以下是表单的HTML结构代码：

```html
<div>
    <form>
        <label for="fname">First Name</label>
        <input type="text" id="fname" name="firstname" placeholder="Your name..">

        <label for="lname">Last Name</label>
        <input type="text" id="lname" name="lastname" placeholder="Your last name..">

        <label for="country">Country</label>
        <select id="country" name="country">
            <option value="aus">Australia</option>
            <option value="can">Canada</option>
            <option value="usa">USA</option>
        </select>

        <input type="submit" value="Submit">
    </form>
</div>
```

此代码创建了一个包含姓名输入框、国家下拉菜单和提交按钮的简单表单。

## 为输入框和下拉菜单添加样式

接下来，我们将使用CSS为文本输入框和下拉菜单添加统一的样式。目标是让它们具有一致的宽度、内边距和边框。

以下是应用于输入框和下拉菜单的CSS规则：

```css
input[type=text], select {
    width: 100%;
    padding: 12px 20px;
    margin: 8px 0;
    display: inline-block;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
}
```

**代码解释**：
*   `width: 100%;` 使元素宽度占满其容器。
*   `padding: 12px 20px;` 设置元素内部的内容与边框之间的上下间距为12像素，左右间距为20像素。
*   `margin: 8px 0;` 设置元素外部的上下边距为8像素，左右边距为0。
*   `border: 1px solid #ccc;` 定义一个1像素宽、灰色的实线边框。
*   `border-radius: 4px;` 为边框添加4像素的圆角。
*   `box-sizing: border-box;` 确保元素的宽度和高度包含内边距和边框，防止布局错乱。

## 设计提交按钮样式

提交按钮是表单交互的终点，需要设计得醒目且友好。我们将改变其背景色、文字颜色，并添加鼠标悬停效果。

以下是提交按钮的基础样式和悬停效果样式：

```css
/* 基础样式 */
input[type=submit] {
    width: 100%;
    background-color: #4CAF50;
    color: white;
    padding: 14px 20px;
    margin: 8px 0;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

/* 悬停效果 */
input[type=submit]:hover {
    background-color: #45a049;
}
```

**代码解释**：
*   `background-color` 和 `color` 分别设置按钮的背景色和文字颜色。
*   `border: none;` 移除了浏览器为按钮添加的默认边框。
*   `cursor: pointer;` 将鼠标指针在按钮上时变为手形，提示用户此处可点击。
*   `:hover` 是一个伪类选择器，用于定义当用户鼠标悬停在元素上时的样式。

## 美化表单容器

最后，为了让整个表单区域看起来更完整，我们可以为包裹表单的`<div>`容器添加一些样式，例如背景色、内边距和圆角。

以下是表单容器的CSS样式：

![](img/e673f49c73b6fd6a64bcc9c6da074bc1_2.png)

![](img/e673f49c73b6fd6a64bcc9c6da074bc1_4.png)

```css
div {
    border-radius: 5px;
    background-color: #f2f2f2;
    padding: 20px;
}
```

应用以上所有样式后，我们的表单将从朴素的默认样式转变为具有现代感的、风格统一的设计。

![](img/e673f49c73b6fd6a64bcc9c6da074bc1_6.png)

![](img/e673f49c73b6fd6a64bcc9c6da074bc1_8.png)

本节课中我们一起学习了如何使用CSS来美化HTML表单。我们掌握了为文本输入框、下拉菜单设置统一样式的方法，设计了醒目且具有交互反馈的提交按钮，并通过美化表单容器使整个表单区域更加协调。这些技能是前端开发中构建用户友好界面的基础。