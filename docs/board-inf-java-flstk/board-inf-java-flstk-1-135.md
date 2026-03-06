# 135：使用 JavaScript 操作 DOM 元素 🛠️

在本节课中，我们将学习如何使用 JavaScript 来操作网页上的 DOM 元素。上一节我们介绍了如何访问 DOM 元素，本节中我们来看看如何动态地修改它们。

## 概述

使用 JavaScript 操作 DOM，意味着可以在不重新加载整个页面的情况下，动态地修改网页上的元素。例如，一个网页上有一个按钮和一个段落元素，你可以使用 JavaScript 在按钮被点击时，改变段落内的文本，而无需刷新页面。

要实现这一点，首先需要使用 DOM 选择器选中你想要修改的元素。DOM 选择器是一种允许你选择网页上一个或一组元素的方法。我们在之前的视频中已经介绍了几种不同的 DOM 选择器。

一旦选中了目标元素，你就可以访问并修改它的属性。属性是元素的可变特征，例如其文本内容、属性和样式。

![](img/e3d62bedadbc423dac23fd386405a16d_1.png)

## 实践操作

![](img/e3d62bedadbc423dac23fd386405a16d_3.png)

现在，让我们通过一些例子来具体看看如何操作。

![](img/e3d62bedadbc423dac23fd386405a16d_5.png)

### 访问文档属性

![](img/e3d62bedadbc423dac23fd386405a16d_7.png)

首先，我们可以访问 `document` 对象的各种属性。以下是一些基本示例：

```javascript
// 获取并打印当前页面的域名
console.log(document.domain);

![](img/e3d62bedadbc423dac23fd386405a16d_9.png)

// 获取并打印当前页面的完整 URL
console.log(document.URL);

![](img/e3d62bedadbc423dac23fd386405a16d_11.png)

// 获取并修改页面标题
document.title = "DOM 操作";
console.log(document.title);

![](img/e3d62bedadbc423dac23fd386405a16d_13.png)

// 获取整个文档的 body 元素
console.log(document.body);

![](img/e3d62bedadbc423dac23fd386405a16d_15.png)

![](img/e3d62bedadbc423dac23fd386405a16d_17.png)

// 获取整个文档的 head 元素
console.log(document.head);
```

执行上述代码，你可以在浏览器的开发者工具控制台中看到相应的输出，例如域名、URL 以及修改后的页面标题。

![](img/e3d62bedadbc423dac23fd386405a16d_19.png)

### 向页面添加文本

![](img/e3d62bedadbc423dac23fd386405a16d_21.png)

![](img/e3d62bedadbc423dac23fd386405a16d_23.png)

要向页面添加文本，你需要先选中一个元素，然后使用相应的方法。以下是向 `body` 添加文本的步骤：

![](img/e3d62bedadbc423dac23fd386405a16d_24.png)

![](img/e3d62bedadbc423dac23fd386405a16d_26.png)

1.  选中 `body` 元素。
2.  使用 `append` 或 `appendChild` 方法添加内容。

![](img/e3d62bedadbc423dac23fd386405a16d_28.png)

```javascript
// 1. 选中 body 元素
const body = document.body;

![](img/e3d62bedadbc423dac23fd386405a16d_30.png)

// 2. 向 body 追加文本
body.append("Hello");
```

![](img/e3d62bedadbc423dac23fd386405a16d_32.png)

执行后，单词 “Hello” 会出现在网页上。

### 创建并添加新元素

![](img/e3d62bedadbc423dac23fd386405a16d_34.png)

除了添加文本，我们还可以创建全新的 HTML 元素并将其添加到文档中。以下是创建一个 `<div>` 元素并添加文本的步骤：

```javascript
// 1. 创建一个新的 div 元素
const div = document.createElement('div');

![](img/e3d62bedadbc423dac23fd386405a16d_36.png)

// 2. 为这个 div 元素设置文本内容
div.innerText = "这是一个用 JavaScript 创建的 div";

// 3. 将这个 div 元素添加到 body 中
body.appendChild(div);
```

![](img/e3d62bedadbc423dac23fd386405a16d_38.png)

执行上述代码后，页面上会出现一个包含指定文本的新 `<div>` 元素。

### 从页面中移除元素

![](img/e3d62bedadbc423dac23fd386405a16d_40.png)

同样，我们也可以移除已存在的元素。以下是两种移除元素的方法：

![](img/e3d62bedadbc423dac23fd386405a16d_42.png)

**方法一：通过父元素移除**
```javascript
// 假设 ‘div’ 是要移除的元素，且 ‘body’ 是其父元素
body.removeChild(div);
```

![](img/e3d62bedadbc423dac23fd386405a16d_44.png)

**方法二：元素自行移除**
```javascript
// 直接调用元素自身的 remove 方法
div.remove();
```

![](img/e3d62bedadbc423dac23fd386405a16d_46.png)

两种方法都可以成功将指定的 `<div>` 元素从页面中删除。

## 核心方法总结

![](img/e3d62bedadbc423dac23fd386405a16d_48.png)

在本节实践中，我们使用了以下几个核心方法：
*   **`document.createElement(tagName)`**：用于创建一个新的指定类型的 HTML 元素。
*   **`element.innerText`**：用于获取或设置元素的文本内容。
*   **`parentElement.appendChild(childElement)`**：将一个元素节点添加到指定父节点的子节点列表末尾。
*   **`parentElement.removeChild(childElement)`**：从父元素中移除一个指定的子元素。
*   **`element.remove()`**：将元素自身从它所属的 DOM 树中移除。

## 总结

![](img/e3d62bedadbc423dac23fd386405a16d_50.png)

本节课中我们一起学习了如何使用 JavaScript 操作 DOM 元素。通过 DOM 选择器选中元素后，我们可以修改其文本内容、创建并添加新元素，或者移除现有元素。这些操作使得网页能够实现动态、交互式的用户体验，而无需重新加载。在下一节视频中，我们将进一步学习如何使用 JavaScript 修改元素的样式和属性。