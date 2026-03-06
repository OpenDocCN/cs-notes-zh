# JavaScript DOM 操作：P141：使用 JavaScript 创建与移除 DOM 元素

在本节课中，我们将详细学习如何使用 JavaScript 动态地创建和移除网页中的 DOM 元素。这是 Web 开发中动态修改页面内容的一项基础技术。

![](img/2f1ecfc343912d36e28a0cdeb7cc02cb_1.png)

JavaScript 提供了多种方法来创建和操作 DOM 元素，包括 `createElement`、`appendChild`、`append`、`remove` 和 `removeChild` 等。

![](img/2f1ecfc343912d36e28a0cdeb7cc02cb_3.png)

上一节我们介绍了 DOM 的基本概念，本节中我们来看看如何通过代码实践这些操作。

## 实践示例：动态食物列表

让我们通过一个具体的例子来理解。首先，我们准备一个基础的 HTML 模板。

![](img/2f1ecfc343912d36e28a0cdeb7cc02cb_5.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>DOM 操作示例</title>
</head>
<body>
    <h1>我最喜欢的食物</h1>
    <ul id="foodList">
        <li>Pizza</li>
        <li>Sushi</li>
    </ul>
    <button id="addButton">添加 Tacos</button>
    <button id="removeButton">移除 Sushi</button>
    <script src="script.js"></script>
</body>
</html>
```

![](img/2f1ecfc343912d36e28a0cdeb7cc02cb_7.png)

接下来，我们编写 JavaScript 代码来实现动态添加和移除列表项的功能。

以下是实现此功能的核心步骤：

1.  **选择 DOM 元素**：使用 `querySelector` 方法获取页面上的按钮和列表。
2.  **添加事件监听器**：为“添加”和“移除”按钮绑定点击事件。
3.  **创建新元素**：在点击“添加”按钮时，使用 `createElement` 和 `createTextNode` 方法创建一个新的列表项。
4.  **将元素加入 DOM**：使用 `appendChild` 方法将新创建的元素添加到列表中。
5.  **从 DOM 中移除元素**：在点击“移除”按钮时，使用 `removeChild` 方法将指定的列表项从 DOM 中删除。

```javascript
// 1. 选择 DOM 元素
const addButton = document.querySelector('#addButton');
const removeButton = document.querySelector('#removeButton');
const foodList = document.querySelector('#foodList');

// 2. 为“添加”按钮添加事件监听器
addButton.addEventListener('click', function() {
    // 3. 创建新的列表项元素和文本节点
    const newListItem = document.createElement('li');
    const newListItemText = document.createTextNode('Tacos');

    // 4. 将文本节点附加到列表项元素
    newListItem.appendChild(newListItemText);

    // 5. 将新的列表项添加到食物列表中
    foodList.appendChild(newListItem);
});

// 6. 为“移除”按钮添加事件监听器
removeButton.addEventListener('click', function() {
    // 7. 选择要移除的列表项（第二个li，即Sushi）
    const sushiItem = document.querySelector('#foodList li:nth-child(2)');

    // 8. 检查元素是否存在，然后从DOM中移除
    if (sushiItem) {
        foodList.removeChild(sushiItem);
    }
});
```

![](img/2f1ecfc343912d36e28a0cdeb7cc02cb_9.png)

![](img/2f1ecfc343912d36e28a0cdeb7cc02cb_10.png)

运行上述代码后，页面将显示一个包含“Pizza”和“Sushi”的列表，以及两个按钮。点击“添加 Tacos”按钮，列表末尾会新增一个“Tacos”项。点击“移除 Sushi”按钮，列表中的“Sushi”项将被删除。

## 核心方法总结

![](img/2f1ecfc343912d36e28a0cdeb7cc02cb_12.png)

在本示例中，我们使用了几个关键的 DOM 操作方法：

![](img/2f1ecfc343912d36e28a0cdeb7cc02cb_13.png)

*   **`document.createElement(tagName)`**：创建一个指定标签名的 HTML 元素。
*   **`document.createTextNode(text)`**：创建一个包含指定文本的文本节点。
*   **`parentElement.appendChild(childElement)`**：将一个节点附加到指定父节点的子节点列表末尾。
*   **`parentElement.removeChild(childElement)`**：从 DOM 中移除父节点下的一个指定子节点。
*   **`document.querySelector(selector)`**：返回文档中与指定选择器匹配的第一个元素。

![](img/2f1ecfc343912d36e28a0cdeb7cc02cb_15.png)

事件监听器使用 `querySelector` 方法访问相应的 DOM 元素，然后使用 `appendChild` 或 `removeChild` 方法来创建或移除元素。

![](img/2f1ecfc343912d36e28a0cdeb7cc02cb_17.png)

## 课程总结

本节课中我们一起学习了如何使用 JavaScript 创建和移除 DOM 元素。在 Web 开发中，这是一项用于动态修改网页内容的基础技术。通过使用 `createElement`、`appendChild`、`removeChild` 等方法，开发者可以创建动态且响应式的网页，为用户提供丰富而吸引人的体验。

![](img/2f1ecfc343912d36e28a0cdeb7cc02cb_19.png)

在下一节视频中，我们将学习如何使用 Ajax 动态加载内容。