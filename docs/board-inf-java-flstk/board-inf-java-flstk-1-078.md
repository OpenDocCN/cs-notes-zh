# 078：表单与输入标签 📝

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_1.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_3.png)

在本节课中，我们将要学习HTML中用于收集用户数据的核心元素：表单（`<form>`）和输入标签（`<input>`）。我们将了解如何创建表单，探索不同类型的输入控件，并学习如何通过属性来增强它们的功能。

上一节我们介绍了HTML的格式化标签，本节中我们来看看如何与用户进行交互。

## 表单标签（`<form>`）

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_5.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_7.png)

HTML中的表单用于从用户那里收集数据并将其发送到服务器。`<form>`标签是网页上表单的容器，内部可以包含输入字段、按钮和下拉菜单等元素。

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_9.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_11.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_13.png)

要使用`<form>`标签，需要指定`action`和`method`属性：
*   `action`：决定表单数据将被发送到哪个URL。
*   `method`：指定数据如何通过请求从客户端发送到服务器（通常是`GET`或`POST`）。

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_15.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_17.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_19.png)

以下是创建表单标签的基本结构：

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_21.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_23.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_25.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_27.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_29.png)

```html
<form action="/submit-data" method="POST">
  <!-- 各种输入控件将放在这里 -->
</form>
```

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_31.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_33.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_35.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_37.png)

## 输入标签（`<input>`）

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_39.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_41.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_43.png)

`<input>`标签是一个自闭合标签，用于创建各种类型的交互式表单控件。它拥有多个属性，如`type`、`name`、`value`、`placeholder`等，我们将在本节中学习它们。

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_45.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_47.png)

以下是HTML中一些最常见的输入类型：

*   **文本 (`type="text"`)**: 创建可接受文本输入的表单字段。
    ```html
    <input type="text">
    ```
*   **邮箱 (`type="email"`)**: 创建专门用于接收邮箱地址的输入字段。
*   **数字 (`type="number"`)**: 创建仅允许输入数字的字段。
    ```html
    <input type="number">
    ```
*   **密码 (`type="password"`)**: 创建用于输入密码的字段，输入内容会被掩码（显示为圆点或星号）以保护隐私。
    ```html
    <input type="password">
    ```
*   **日期 (`type="date"`)**: 提供一个日期选择器，让用户选择日期。
    ```html
    <input type="date">
    ```
*   **文件 (`type="file"`)**: 允许用户选择并上传文件。
*   **隐藏 (`type="hidden"`)**: 创建一个对用户不可见的输入字段，用于在表单中传递不需要用户填写的数据。
*   **提交 (`type="submit"`)**: 创建一个提交按钮，用于将表单数据发送到服务器。
    ```html
    <input type="submit" value="提交">
    ```
*   **单选按钮 (`type="radio"`)**: 创建单选按钮，用于让用户从多个选项中选择一项。
    ```html
    <input type="radio" id="minor" name="age">
    <label for="minor">您是未成年人吗？</label>
    ```
*   **复选框 (`type="checkbox"`)**: 创建复选框，允许用户选择多个选项。
    ```html
    <input type="checkbox" id="terms">
    <label for="terms">您接受条款和条件吗？</label>
    ```

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_49.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_51.png)

为了使表单布局更清晰，可以使用`<br>`（换行）标签将元素放置到新的一行。

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_53.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_55.png)

## 输入标签的常用属性

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_57.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_59.png)

输入标签的属性为其提供了额外的功能和约束。以下是几个关键属性：

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_61.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_63.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_65.png)

*   **`value`**: 设置输入控件的默认值。
    ```html
    <input type="text" value="初始值">
    ```
*   **`placeholder`**: 在输入字段中显示提示文本（占位符），描述期望的输入内容。当用户开始输入时，提示文本会消失。
    ```html
    <input type="text" placeholder="请输入您的姓名">
    ```
*   **`readonly`**: 使输入字段变为只读，用户可以看到其值但无法编辑。
    ```html
    <input type="text" value="只读文本" readonly>
    ```
*   **`required`**: 指定在提交表单之前必须填写此输入字段，确保收集到必要的数据。
*   **`name`**: 用于在表单提交时标识输入控件，这对服务器端处理表单数据至关重要。
    ```html
    <input type="text" name="username">
    ```
*   **`max` / `min`**: 对于`type="number"`的输入，设置允许输入的最大值和最小值。
    ```html
    <input type="number" min="5" max="10">
    ```

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_67.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_68.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_69.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_71.png)

## 其他表单元素：下拉列表 (`<select>`)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_73.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_74.png)

除了`<input>`，表单中还可以使用`<select>`标签来创建下拉列表。它内部包含多个`<option>`标签来定义各个选项。

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_76.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_78.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_80.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_82.png)

```html
<select>
  <option value="red">红色</option>
  <option value="blue">蓝色</option>
  <option value="green">绿色</option>
</select>
```

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_84.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_86.png)

---

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_88.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_90.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_92.png)

![](img/d686dfd5b6b74eeba954ae3b025dc2fd_94.png)

本节课中我们一起学习了HTML表单的基础知识。我们了解了如何用`<form>`标签创建表单，探索了多种`<input>`类型（如文本、密码、日期、单选按钮等）及其关键属性（如`placeholder`、`required`、`name`），还简单介绍了`<select>`下拉列表。建议你在自己的项目中尝试使用这些元素来构建交互式表单。