# 前端编程：COMP6080：Week 5 - 作业3演示 🚀

在本节课中，我们将学习如何完成作业3。作业3要求我们创建一个交互式网页，该网页能够根据用户输入动态生成内容。我们将通过一个具体的演示来理解如何实现这一目标。

![](img/19a916dab9b86403ca44cf2d7894d7ac_0.png)

上一节我们介绍了作业3的基本要求，本节中我们来看看如何具体实现一个动态生成列表的功能。

![](img/19a916dab9b86403ca44cf2d7894d7ac_1.png)

## 核心概念：动态生成列表

![](img/19a916dab9b86403ca44cf2d7894d7ac_2.png)

动态生成列表的核心在于使用JavaScript来操作DOM（文档对象模型）。我们将根据用户输入的数据，在网页上创建并显示相应的列表项。

![](img/19a916dab9b86403ca44cf2d7894d7ac_3.png)

以下是实现动态生成列表的关键步骤：

![](img/19a916dab9b86403ca44cf2d7894d7ac_4.png)

1.  **获取用户输入**：我们需要从HTML输入框中获取用户输入的值。
2.  **创建列表项**：根据输入的值，使用JavaScript创建一个新的列表项元素（`<li>`）。
3.  **将列表项添加到列表**：将新创建的列表项添加到HTML中已存在的无序列表（`<ul>`）中。
4.  **清空输入框**：在添加完成后，清空输入框以便用户输入下一个项目。

![](img/19a916dab9b86403ca44cf2d7894d7ac_5.png)

## 代码实现

![](img/19a916dab9b86403ca44cf2d7894d7ac_6.png)

让我们通过代码来具体实现上述步骤。首先，我们需要一个基本的HTML结构。

![](img/19a916dab9b86403ca44cf2d7894d7ac_7.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>动态列表生成器</title>
</head>
<body>
    <h1>我的待办事项列表</h1>
    <input type="text" id="itemInput" placeholder="输入一个新项目...">
    <button id="addButton">添加</button>
    <ul id="itemList"></ul>

    <script src="script.js"></script>
</body>
</html>
```

![](img/19a916dab9b86403ca44cf2d7894d7ac_8.png)

接下来，我们编写JavaScript代码（`script.js`）来实现交互逻辑。

![](img/19a916dab9b86403ca44cf2d7894d7ac_9.png)

```javascript
// 获取页面上的元素
const inputElement = document.getElementById('itemInput');
const buttonElement = document.getElementById('addButton');
const listElement = document.getElementById('itemList');

![](img/19a916dab9b86403ca44cf2d7894d7ac_10.png)

// 为按钮添加点击事件监听器
buttonElement.addEventListener('click', function() {
    // 步骤1：获取用户输入
    const newItemText = inputElement.value.trim();

    // 检查输入是否为空
    if (newItemText === '') {
        alert('请输入内容！');
        return; // 如果为空，则停止执行
    }

    // 步骤2：创建新的列表项元素
    const newListItem = document.createElement('li');
    // 将用户输入的文字设置为列表项的文本内容
    newListItem.textContent = newItemText;

    // 步骤3：将新列表项添加到无序列表中
    listElement.appendChild(newListItem);

    // 步骤4：清空输入框
    inputElement.value = '';
});
```

![](img/19a916dab9b86403ca44cf2d7894d7ac_11.png)

## 功能扩展：添加删除功能

![](img/19a916dab9b86403ca44cf2d7894d7ac_12.png)

一个完整的待办事项列表通常还需要删除功能。我们可以为每个列表项添加一个删除按钮。

![](img/19a916dab9b86403ca44cf2d7894d7ac_13.png)

以下是修改后的JavaScript代码，为每个新增的列表项添加删除按钮：

![](img/19a916dab9b86403ca44cf2d7894d7ac_14.png)

```javascript
buttonElement.addEventListener('click', function() {
    const newItemText = inputElement.value.trim();

    if (newItemText === '') {
        alert('请输入内容！');
        return;
    }

    const newListItem = document.createElement('li');
    newListItem.textContent = newItemText;

    // 创建删除按钮
    const deleteButton = document.createElement('button');
    deleteButton.textContent = '删除';
    // 为删除按钮添加点击事件
    deleteButton.addEventListener('click', function() {
        // 当点击删除按钮时，从列表中移除其父元素（即<li>）
        listElement.removeChild(newListItem);
    });

    // 将删除按钮添加到列表项中
    newListItem.appendChild(deleteButton);

    // 将列表项添加到列表
    listElement.appendChild(newListItem);

    inputElement.value = '';
});
```

![](img/19a916dab9b86403ca44cf2d7894d7ac_15.png)

## 总结

![](img/19a916dab9b86403ca44cf2d7894d7ac_16.png)

本节课中我们一起学习了如何构建一个动态生成列表的交互式网页。我们掌握了以下关键点：

![](img/19a916dab9b86403ca44cf2d7894d7ac_17.png)

*   使用`document.getElementById`获取DOM元素。
*   使用`addEventListener`为元素绑定事件（如点击事件）。
*   使用`document.createElement`动态创建新的HTML元素。
*   使用`appendChild`将新元素插入到DOM树中。
*   使用`removeChild`从DOM树中移除元素。

![](img/19a916dab9b86403ca44cf2d7894d7ac_18.png)

通过组合这些基本的DOM操作方法，我们可以创建出丰富多样的前端交互效果。理解这些原理是完成作业3以及未来更复杂前端开发任务的基础。