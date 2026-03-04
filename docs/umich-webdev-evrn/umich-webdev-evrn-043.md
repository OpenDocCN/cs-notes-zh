# 043：HTML输入类型详解 🧩

在本节课中，我们将详细讲解HTML表单中各种输入类型的工作原理和代码实现。我们将逐一分析文本、密码、单选按钮、复选框、下拉菜单、文本域、多选列表以及提交按钮等元素，并了解它们如何与服务器进行数据交互。

---

## 文本与密码输入

上一节我们介绍了表单的基本结构，本节中我们来看看最基础的文本输入类型。

**文本输入** (`<input type="text">`) 是最常见的表单字段，用于接收用户输入的单行文本。为了保持代码的语义化，我们通常使用 `<label>` 标签与之关联。

**密码输入** (`<input type="password">`) 在视觉上与文本输入类似，但用户输入的内容会被隐藏（通常显示为圆点或星号）。需要注意的是，密码字段仅在输入时提供视觉保护。当表单通过HTTP POST方法提交时，密码会以**明文形式**在网络中传输。因此，它主要用于防止他人从旁窥视（“肩窥”），而非提供真正的加密安全。

以下是这两种输入类型的代码示例：
```html
<label for="nickname">Nickname:</label>
<input type="text" id="nickname" name="nickname">

<label for="secret">Password:</label>
<input type="password" id="secret" name="secret">
```

---

## 单选按钮与复选框

接下来，我们探讨允许用户进行选择的输入类型：单选按钮和复选框。

**单选按钮** (`<input type="radio">`) 允许用户从一组选项中选择**唯一**的答案。它的工作原理类似于汽车收音机的选台器。通过为同一组的所有单选按钮设置相同的 `name` 属性，浏览器会确保它们中只有一个能被选中。`value` 属性定义了选中该项后要发送到服务器的值。`checked` 属性可以设置默认选中的项。

**复选框** (`<input type="checkbox">`) 则允许用户进行**多项**独立选择。每个复选框通常拥有独立的 `name` 和 `value`。如果未指定 `value`，则默认提交字符串 `"on"`。在服务器端，我们通常检查该 `name` 是否存在于 `$_POST` 数组中，来判断复选框是否被选中，而不是直接依赖其 `value` 值。

以下是这两种输入类型的代码示例：
```html
<!-- 单选按钮 -->
<input type="radio" id="am" name="when" value="AM">
<label for="am">AM</label>
<input type="radio" id="pm" name="when" value="PM" checked>
<label for="pm">PM</label>

<!-- 复选框 -->
<input type="checkbox" id="class1" name="class1" checked>
<label for="class1">Class I</label>
<input type="checkbox" id="class2" name="class2" checked>
<label for="class2">Class II</label>
```

![](img/39fed7f85ac1accb5bef0955b96fa136_1.png)

---

![](img/39fed7f85ac1accb5bef0955b96fa136_3.png)

## 下拉选择菜单

现在，我们来看两种允许用户从列表中选择的表单控件：标准下拉菜单和带默认值的下拉菜单。

**下拉菜单** (`<select>`) 通过 `<option>` 子元素提供一系列选项。当用户提交表单时，所选 `<option>` 的 `value` 属性值会作为该字段的数据发送到服务器。

以下是下拉菜单的代码示例：
```html
<label for="soda">Soda:</label>
<select id="soda" name="soda">
    <option value="1">Coke</option>
    <option value="2">Pepsi</option>
    <option value="3">Mountain Dew</option>
</select>

<label for="snack">Snack:</label>
<select id="snack" name="snack">
    <option value="nuts">Peanuts</option>
    <option value="chips" selected>Chips</option>
    <option value="cookie">Cookies</option>
</select>
```
在第一个例子中，用户选择“Mountain Dew”会提交 `soda=3`。在第二个例子中，我们使用 `selected` 属性预先选中了“Chips”，因此默认会提交 `snack=chips`。

---

## 文本域与多选列表

表单中还有两种用于处理多行文本和多项复杂选择的控件。

**文本域** (`<textarea>`) 用于接收用户输入的多行文本。与 `<input>` 不同，它的默认值直接写在开始和结束标签之间，可以包含空格和换行符。提交后，所有内容会作为一个完整的字符串发送到服务器。**重要提示**：由于用户可以在此输入任何内容（包括HTML和JavaScript代码），如果不对其进行过滤就直接输出到网页，可能导致跨站脚本（XSS）攻击，因此必须谨慎处理。

**多选列表** (`<select multiple>`) 是下拉菜单的变体，允许用户通过按住 `Ctrl`（Windows/Linux）或 `Command`（Mac）键选择多个选项。提交时，它会将一个数组发送到服务器。然而，这种交互方式对用户不够友好，在实际应用中应谨慎使用。

以下是这两种控件的代码示例：
```html
<!-- 文本域 -->
<label for="about">About:</label>
<textarea id="about" name="about">Blah blah blank...</textarea>

<!-- 多选列表 -->
<label for="topping">Topping:</label>
<select id="topping" name="topping[]" multiple>
    <option value="cheese">Cheese</option>
    <option value="ham">Ham</option>
</select>
```

---

![](img/39fed7f85ac1accb5bef0955b96fa136_5.png)

## 提交按钮与小技巧

最后，我们来了解表单的提交机制以及一个实用的小技巧。

**提交按钮** (`<input type="submit">`) 用于发送表单数据。它的 `value` 属性有两个作用：一是作为按钮上显示的文本，二是作为提交时发送的数据。在有多语言需求的应用程序中，按钮文本可能会被翻译，因此更常见的做法是为不同的按钮设置不同的 `name`，然后在服务器端检查哪个 `name` 存在于 `$_POST` 数据中，以此判断哪个按钮被点击。

此外，我们还可以创建一个**不提交表单的按钮**。通过将 `type` 设置为 `button` 并添加 `onclick` 的JavaScript事件，可以让按钮执行跳转链接等操作，而不触发表单提交。这在实现“取消”或“返回”功能时非常有用。

以下是按钮的代码示例：
```html
<!-- 提交按钮 -->
<input type="submit" name="do_post" value="Submit">

![](img/39fed7f85ac1accb5bef0955b96fa136_7.png)

<!-- 作为链接的按钮（不提交表单） -->
<input type="button" value="Cancel" onclick="location.href='https://example.com'; return false;">
```

---

![](img/39fed7f85ac1accb5bef0955b96fa136_9.png)

本节课中我们一起学习了HTML表单中多种输入类型的详细用法，包括文本、密码、单选、复选、下拉选择、文本域和多选列表。我们还探讨了提交按钮的工作方式以及如何创建一个不提交表单的导航按钮。理解这些基础元素的特性和数据提交机制，是构建交互式Web应用程序的重要第一步。