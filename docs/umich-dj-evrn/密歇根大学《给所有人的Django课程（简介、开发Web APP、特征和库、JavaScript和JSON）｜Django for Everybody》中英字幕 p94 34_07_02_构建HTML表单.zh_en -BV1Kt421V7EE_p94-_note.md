# Django for Everybody：34.07.02：构建HTML表单 📝

![](img/5f3e0d670c733093870d4db1c2d1a9e7_1.png)

在本节课中，我们将学习如何在HTML中构建表单。表单是Web应用与用户交互的核心组件，用于收集和提交数据。我们将介绍几种常见的HTML表单元素及其工作原理，包括文本输入、密码框、单选按钮、复选框、下拉选择框、文本域以及提交按钮。此外，我们还会简要了解HTML5引入的一些新输入类型。

---

![](img/5f3e0d670c733093870d4db1c2d1a9e7_3.png)

## 基本表单元素

上一节我们介绍了表单的基本概念，本节中我们来看看几种最常用的HTML表单输入类型。

### 文本输入框

文本输入框是最基础的表单元素，用于收集单行文本信息。其HTML代码结构如下：

```html
<input type="text" name="account" id="account">
```

*   **`type="text"`**：定义输入类型为文本。
*   **`name="account"`**：这是关键属性。当表单提交时，服务器会收到一个键值对，键就是这里的`name`值。例如，如果用户输入“Beth”并提交，服务器收到的数据将是 `account=Beth`。
*   **`id="account"`**：主要用于将`<label>`标签与此输入框关联起来，以提升可访问性。对于表单数据的提交，`id`属性不是必需的。

![](img/5f3e0d670c733093870d4db1c2d1a9e7_5.png)

### 密码输入框

密码输入框在视觉上会将输入内容隐藏（通常显示为星号或圆点），但其数据提交方式与文本输入框完全相同。

```html
<input type="password" name="pass" id="passwd">
```

*   **`type="password"**：定义输入类型为密码。
*   重要提示：密码框仅在用户界面中隐藏输入内容。**当表单数据提交到服务器时，密码是以明文形式传输的**，除非应用了额外的加密措施（如HTTPS）。

### 隐藏输入框

![](img/5f3e0d670c733093870d4db1c2d1a9e7_7.png)

隐藏输入框在页面上不可见，但它的值会随表单一起提交。常用于传递一些不需要用户填写但服务器需要知道的数据。

```html
<input type="hidden" name="user_id" value="12345">
```

---

## 选择类表单元素

在了解了基本的文本输入后，我们来看看用于提供选项的表单元素。

### 单选按钮

单选按钮用于在多个选项中**只能选择一项**的场景。所有属于同一组的单选按钮必须拥有相同的`name`属性值。

![](img/5f3e0d670c733093870d4db1c2d1a9e7_9.png)

```html
<input type="radio" name="when" value="AM"> AM
<input type="radio" name="when" value="PM"> PM
```

以下是关于单选按钮的关键点：
*   当用户点击其中一个选项时，同组（`name`相同）的其他选项会自动取消选中。
*   提交表单时，服务器会收到 `when=选中的value值`（例如 `when=PM`）。
*   这些按钮可以分散在页面的任何位置，只要`name`相同，它们就属于同一组。

### 复选框

复选框允许用户从多个选项中进行**多项选择**。每个复选框都是一个独立的实体，通常拥有不同的`name`。

```html
<input type="checkbox" name="class1" value="E"> English
<input type="checkbox" name="class2" value="S539"> S539
<input type="checkbox" name="class3"> Math
```

以下是关于复选框的关键点：
*   每个复选框是否被选中是独立的。
*   提交表单时，**只有被选中的复选框**的`name`和`value`会作为数据发送给服务器。
*   如果未指定`value`属性（如上面的“Math”），默认提交的值为 `on`。
*   用户可以选中任意多个、一个或不选中任何复选框。

### 下拉选择框

![](img/5f3e0d670c733093870d4db1c2d1a9e7_11.png)

![](img/5f3e0d670c733093870d4db1c2d1a9e7_12.png)

下拉选择框（`<select>`）为用户提供了一个选项列表，通常用于节省空间，用户只能从中选择一项。

```html
<select name="soda">
    <option value="0">Coke</option>
    <option value="1">Pepsi</option>
    <option value="2">Mountain Dew</option>
</select>
```

以下是关于下拉选择框的关键点：
*   `name`属性定义在`<select>`标签上。
*   每个`<option>`标签的`value`属性是提交给服务器的值，而标签内的文本（如“Coke”）是显示给用户看的。
*   可以使用`selected`属性来预设默认选项：`<option value="peanuts" selected>Peanuts</option>`。如果不设置，默认选中第一项。

---

![](img/5f3e0d670c733093870d4db1c2d1a9e7_14.png)

## 文本域与按钮

除了上述元素，表单中还需要处理大段文本和用户提交动作。

### 文本域

当需要用户输入多行、大段文本（如评论、博客文章）时，应使用`<textarea>`标签。

```html
<textarea name="feedback" rows="4" cols="50">默认文本...</textarea>
```

*   **`name`**：定义提交时的键名。
*   **`rows`和`cols`**：定义文本域的初始高度（行数）和宽度（列数）。
*   用户可以在此区域内自由输入，包括换行符和空格，所有内容都会作为字符串提交。

### 提交按钮

提交按钮用于触发表单数据的发送。

![](img/5f3e0d670c733093870d4db1c2d1a9e7_16.png)

```html
<input type="submit" name="submit_btn" value="提交表单">
```

*   `value`属性的值会显示在按钮的文本上。
*   当按钮被点击时，表单中所有具有`name`属性的元素数据会被收集并发送到`<form>`标签`action`属性指定的地址。
*   在多语言环境中，按钮文本可能需要翻译，因此服务器端逻辑通常通过检查`name`（如`submit_btn`）是否存在来判断是否提交，而不是依赖`value`的文本内容。

### 其他按钮与简单交互

![](img/5f3e0d670c733093870d4db1c2d1a9e7_18.png)

有时表单中需要“取消”或“返回”按钮。这可以通过一个普通按钮结合简单的JavaScript来实现。

```html
<input type="button" value="取消" onclick="location.href='/home'; return false;">
```

*   **`type="button"**：定义一个普通按钮，点击它不会自动提交表单。
*   **`onclick`**：定义了点击按钮时执行的JavaScript代码。
*   **`location.href='/home'`**：将浏览器导航到 `/home` 这个URL。
*   **`return false;`**：阻止按钮可能触发的任何默认表单提交行为。

---

## HTML5新增输入类型

传统的输入类型已经服务了二十多年。HTML5引入了一系列新的输入类型，它们能在支持它们的浏览器中提供更好的用户体验（如内置验证和专用输入界面），并在旧浏览器中优雅地降级为普通文本输入框。

以下是几个HTML5输入类型的例子：

*   **颜色选择器**：`<input type="color" name="favcolor">`
    *   会弹出系统或浏览器提供的颜色选择器，提交的值是十六进制颜色码（如 `#ff0000`）。
*   **日期选择器**：`<input type="date" name="birthday">`
    *   会弹出日期选择控件，方便用户选择日期。
*   **邮箱验证**：`<input type="email" name="usermail">`
    *   浏览器会进行简单的格式验证（检查是否包含“@”符号等），如果格式无效，在提交时会阻止表单并提示用户。
*   **数字与范围**：`<input type="number" name="quantity" min="1" max="5">`
    *   用于输入数字，并可配合`min`和`max`属性限制范围。浏览器会验证输入值是否在指定范围内。
*   **URL验证**：`<input type="url" name="homepage">`
    *   浏览器会验证输入内容是否符合URL格式。

**核心优势与注意事项**：
1.  **内置验证**：对于`email`、`number`（配合`min`/`max`）、`url`等类型，浏览器会在用户提交表单前进行初步验证。如果验证失败，表单不会被提交，用户会立即得到反馈。
2.  **优雅降级**：在不支持HTML5新特性的旧浏览器中，这些输入框会显示为普通的文本输入框（`type="text"`），功能依然可用。
3.  **服务器端验证仍需进行**：**切记，浏览器端的验证是为了提升用户体验，绝不能替代服务器端的数据验证。** 恶意用户或旧浏览器仍然可能提交无效数据，因此必须在服务器端对所有接收到的数据再次进行严格的检查和清理。

---

## 总结

本节课中我们一起学习了构建HTML表单的基础知识。我们介绍了多种核心的表单元素：用于输入文本的`text`、`password`和`textarea`；用于单项选择的`radio`按钮和`select`下拉框；用于多项选择的`checkbox`；以及触发提交的`submit`按钮。我们还了解了如何使用`button`类型结合JavaScript实现其他交互。最后，我们预览了HTML5带来的一些更智能的输入类型（如`date`、`email`、`number`），它们能提供更好的输入体验和初步的客户端验证。

![](img/5f3e0d670c733093870d4db1c2d1a9e7_20.png)

记住，这只是HTML表单世界的开端。在实际开发中，你还需要深入学习如何设置表单的`action`和`method`属性，如何处理提交的数据，以及如何结合CSS和JavaScript来创建更美观、交互性更强的表单。