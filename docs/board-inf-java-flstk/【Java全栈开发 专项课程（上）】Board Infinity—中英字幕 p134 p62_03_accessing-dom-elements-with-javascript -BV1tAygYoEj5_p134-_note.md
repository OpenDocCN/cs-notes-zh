# JavaScript DOM 操作：03：使用 JavaScript 访问 DOM 元素 🎯

在本节课中，我们将学习如何使用 JavaScript 访问网页中的 DOM 元素。这是实现动态网页交互的基础。

![](img/b5779175e54c42655c527eafc9757041_1.png)

## 概述

上一节我们介绍了 DOM 的概念。本节中，我们来看看如何通过 JavaScript 代码来访问和选取 DOM 树中的特定元素。掌握这些方法是操作网页内容的第一步。

![](img/b5779175e54c42655c527eafc9757041_3.png)

![](img/b5779175e54c42655c527eafc9757041_5.png)

## 访问 DOM 元素的方法

以下是 JavaScript 中几种常用的 DOM 选择器。

![](img/b5779175e54c42655c527eafc9757041_7.png)

### 1. 通过 ID 获取元素

![](img/b5779175e54c42655c527eafc9757041_9.png)

`document.getElementById()` 方法返回拥有指定 ID 的第一个元素。由于 ID 在 HTML 中应是唯一的，此方法通常返回单个元素。

![](img/b5779175e54c42655c527eafc9757041_11.png)

**代码示例：**
```javascript
let element = document.getElementById('hello');
console.log(element);
```
在 HTML 中，你需要有一个 ID 为 `hello` 的元素，例如 `<div id="hello">Hello World</div>`。执行上述代码后，控制台将输出这个 `<div>` 元素。

### 2. 通过类名获取元素

`document.getElementsByClassName()` 方法返回一个包含所有指定类名的元素的集合（HTMLCollection）。请注意方法名中的 `Elements` 是复数形式。

![](img/b5779175e54c42655c527eafc9757041_13.png)

![](img/b5779175e54c42655c527eafc9757041_14.png)

**代码示例：**
```javascript
let items = document.getElementsByClassName('green');
console.log(items);
```
此代码会选取所有 `class` 属性包含 `green` 的元素。即使只有一个元素匹配，返回的也是一个集合。

![](img/b5779175e54c42655c527eafc9757041_16.png)

### 3. 通过标签名获取元素

`document.getElementsByTagName()` 方法返回一个包含所有指定标签名的元素的集合。

![](img/b5779175e54c42655c527eafc9757041_18.png)

![](img/b5779175e54c42655c527eafc9757041_20.png)

**代码示例：**
```javascript
let listItems = document.getElementsByTagName('li');
console.log(listItems);
```
这段代码会选取文档中所有的 `<li>` 列表项元素。

![](img/b5779175e54c42655c527eafc9757041_22.png)

### 4. 使用 CSS 选择器获取单个元素

![](img/b5779175e54c42655c527eafc9757041_24.png)

`document.querySelector()` 方法返回文档中匹配指定 CSS 选择器的**第一个**元素。它非常强大，可以使用任何有效的 CSS 选择器。

**代码示例：**
```javascript
let firstGreenItem = document.querySelector('.green');
console.log(firstGreenItem);
```
即使有多个元素拥有 `green` 类，此方法也只会返回第一个匹配的元素。

![](img/b5779175e54c42655c527eafc9757041_26.png)

### 5. 使用 CSS 选择器获取所有元素

![](img/b5779175e54c42655c527eafc9757041_28.png)

![](img/b5779175e54c42655c527eafc9757041_29.png)

`document.querySelectorAll()` 方法返回一个包含文档中匹配指定 CSS 选择器的所有元素的 NodeList。

**代码示例：**
```javascript
let allGreenItems = document.querySelectorAll('.green');
console.log(allGreenItems);
```
与 `querySelector` 不同，此方法会返回所有匹配的元素。

## 总结

![](img/b5779175e54c42655c527eafc9757041_31.png)

本节课中我们一起学习了访问 DOM 元素的五种核心方法。我们了解到，DOM 是一个代表网页 HTML 元素的树状结构。JavaScript 提供了 `getElementById`、`getElementsByClassName`、`getElementsByTagName`、`querySelector` 和 `querySelectorAll` 等方法来选取这些元素。一旦获得对元素的引用，你就可以修改其属性、内容、样式，或者创建新元素，从而构建出能够响应用户输入并实时更新的动态交互网页。在接下来的视频中，我们将学习如何使用 JavaScript 来操作 DOM。