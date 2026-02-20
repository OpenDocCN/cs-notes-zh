# 哈佛 CS50-WEB ｜ 基于 Python ／ JavaScript 的 Web 编程 (2020·完整版) - P16：L5- JavaScript 编程全解 2 (DOM 操作) 🧩

![](img/0356a82706a80f6f7db9d6650580be5b_1.png)

![](img/0356a82706a80f6f7db9d6650580be5b_3.png)

![](img/0356a82706a80f6f7db9d6650580be5b_5.png)

在本节课中，我们将要学习如何使用 JavaScript 来操作网页的文档对象模型（DOM）。我们将从简单的计数器程序开始，逐步探索如何动态更新页面内容、响应用户事件、修改元素样式，并最终构建一个交互式的待办事项列表应用。通过本课，你将掌握让网页“活”起来的关键技能。

## 从计数器到 DOM 操作 🔢

上一节我们介绍了 JavaScript 的基本语法和函数。本节中我们来看看如何让 JavaScript 与网页内容进行交互。

![](img/0356a82706a80f6f7db9d6650580be5b_7.png)

![](img/0356a82706a80f6f7db9d6650580be5b_9.png)

我们的计数程序实际上正在改进。目前计数器的状态显示一个警报，当我计数时显示一个警报，显示“1”，再次计数时显示“2”。我可以做得更好，不是显示警报，而是以某种方式操作 DOM。

我希望将这个 h1 大标题放在顶部，初始值设为 0。现在当我增加计数器的值时，我将改为使用 `document.querySelector` 找到 h1 元素并更新其 `innerHTML`，将其等于计数器变量的值。

```javascript
document.querySelector('h1').innerHTML = counter;
```

这样，如果我刷新此页面，h1 的初始值就是 0。每次我点击计数，我们将更新该 h1 元素的内容，设置为 1、2、3、4 等等。每次我点击计数按钮，它会增加变量的值，并操作 DOM 进行更改以产生我想在这个实际页面上看到的效果。

![](img/0356a82706a80f6f7db9d6650580be5b_13.png)

## 添加条件逻辑与模板字面量 🧠

我们可以开始添加额外的逻辑。也许我确实偶尔想要一个警报，但不想每次都出现。我可以添加一个条件，比如说如果我只想显示一个警报，每次我计数到 10 的倍数，比如 10、20、30、40、50 等等。

我可以添加一个条件，判断如果计数器对 10 取模，取模运算只会在你除以 10 时得到余数。如果将计数器除以 10，如果余数为 0，这意味着计数器是 10 的倍数。

```javascript
if (counter % 10 === 0) {
    // 显示警报
}
```

为了做到这一点，我真正想做的是在 JavaScript 中将变量插入字符串中。在 Python 中，我们会使用格式化字符串。JavaScript 也做同样的事情，只是语法略有不同。它使用反引号来创建模板字面量。

```javascript
alert(`计数现在是 ${counter}`);
```

这是一个模板字面量，每次我们到达十的倍数时，我们将显示一个警报。这个美元符号和大括号意味着实际上插入 `counter` 变量的值。因此这个模板字面量可以让我们结合变量和字符串，以生成新的字符串。

## 分离 JavaScript 与 HTML 🧹

现在我们可以开始做哪些改进？我们可以做哪些更改来改进设计它的方式？特别是当我们的程序变得更复杂时，我们通常不想将 JavaScript 代码与 HTML 的内容交杂在一起。

这里我们有按钮 `onclick` 等于 `count`，这是函数的名称。尤其是当我们的页面变得更复杂时，如果我们不断维护一点 JavaScript 代码，比如在 HTML 中调用一个函数，这会变得有点烦人。

![](img/0356a82706a80f6f7db9d6650580be5b_15.png)

![](img/0356a82706a80f6f7db9d6650580be5b_17.png)

我们可以开始做到这一点，我可以在 JavaScript 中添加一个事件监听器。

```javascript
document.querySelector('button').onclick = count;
```

这里所说的是 `document.querySelector('button')` 找到页面上的按钮，一旦我找到了那个按钮，我将访问它的 `onclick` 属性并将其设置为 `count` 函数。注意，我实际上并没有调用该函数，只是将 `onclick` 设置为函数本身。这样做的目的是在按钮被点击时，仅在那时才应该运行这个 `count` 函数。

## 处理代码执行时机问题 ⏰

现在我可以尝试通过刷新页面来运行这个程序。我将其刷新，初始值为零，我按下计数，似乎什么也没有发生。每当你在 JavaScript 中遇到问题而未得到想要的行为时，查看 JavaScript 控制台通常是有帮助的。

问题似乎是我正在尝试访问 `null` 的 `onclick` 属性。`null` 在 JavaScript 中表示“没有”，是表示不存在某个对象的方式。那么为什么这个 `document.querySelector('button')` 会返回 `null` 呢？

结果发现如果 `document.querySelector` 无法找到某个元素，它将返回 `null`。这是浏览器工作方式的一点怪癖。浏览器从上到下运行我们的代码，当它到达 `document.querySelector('button')` 这行时，文档的主体尚未加载完成，DOM 的内容尚未加载，结果是我们无法找到这个按钮。

那么我们如何解决这个问题呢？一种策略是将 `<script>` 标签移动到底部，在定义了按钮之后。另一种更常见的方式是添加另一个事件监听器到整个文档上。

```javascript
document.addEventListener('DOMContentLoaded', function() {
    // 在这里为按钮添加事件监听器
    document.querySelector('button').onclick = count;
});
```

`DOMContentLoaded` 事件是在文档对象模型（DOM）页面结构完成加载时触发的事件。现在我们所做的是，等到 DOM 加载完成，等到所有的页面上的内容加载完成后，接着运行这个函数，这个函数将为这个按钮添加事件处理程序。

![](img/0356a82706a80f6f7db9d6650580be5b_27.png)

## 将 JavaScript 移至外部文件 📁

![](img/0356a82706a80f6f7db9d6650580be5b_29.png)

相较于我之前的情况，这是一个改进。但是我代码的其余部分也如此。就像在 CSS 的情况下，我们能够将原本位于页面头部的 CSS 移动到单独的文件中，你也可以对 JavaScript 做同样的事情。

通过将我们的 JavaScript 移动到一个单独的文件中，为此我可以创建一个新文件，称为 `counter.js`，它将包含我 `counter.html` 文件的所有 JavaScript。

在 `counter.html` 中，我使用 `<script src="counter.js"></script>` 来引入 JavaScript 文件。这样，我的 HTML 现在更简单，它只是主体、h1 和按钮，然后我的所有 JavaScript 现在都位于一个单独的文件中。

这让我能够将 HTML 代码和 JavaScript 代码彼此分开。如果我有在多个不同 HTML 页面中使用的常见 JavaScript 代码，多个 HTML 页面都可以包含相同的 JavaScript 源，而不需要重复自己。

## 响应用户输入与表单 📝

既然我们有能力获取 DOM 元素并实际操作它们的内容，我们可以开始让我们的页面变得更加互动，实际上响应用户在页面上的操作，例如填写表单。

假设用户正在填写表单，我们希望我们的代码以某种方式响应他们输入的内容。我将创建一个表单，用户可以在其中输入姓名并提交。

```html
<form>
    <input id="name" placeholder="名称" type="text">
    <input type="submit" value="提交">
</form>
```

在我的 JavaScript 中，当 DOM 加载完成后，我会为表单添加一个提交事件监听器。

```javascript
document.addEventListener('DOMContentLoaded', function() {
    document.querySelector('form').onsubmit = function() {
        const name = document.querySelector('#name').value;
        alert(`Hello, ${name}!`);
        return false; // 阻止表单默认提交行为
    };
});
```

![](img/0356a82706a80f6f7db9d6650580be5b_35.png)

这里我们能够结合事件监听器、函数和查询选择器，既可以读取页面的信息以获取特定 HTML 元素，又可以访问用户输入的内容（`.value` 属性），从而对用户提交表单做出动态响应。

## 动态修改元素样式 🎨

不仅仅是改变元素内的 HTML，我们也可以改变 CSS，改变特定元素的样式属性。让我们看一个例子，创建三个按钮来改变标题的颜色。

![](img/0356a82706a80f6f7db9d6650580be5b_37.png)

```html
<h1 id="hello">你好</h1>
<button id="red">红色</button>
<button id="blue">蓝色</button>
<button id="green">绿色</button>
```

```javascript
document.addEventListener('DOMContentLoaded', function() {
    document.querySelector('#red').onclick = function() {
        document.querySelector('#hello').style.color = 'red';
    };
    document.querySelector('#blue').onclick = function() {
        document.querySelector('#hello').style.color = 'blue';
    };
    document.querySelector('#green').onclick = function() {
        document.querySelector('#hello').style.color = 'green';
    };
});
```

这显示我们可以修改样式，而不仅仅是修改页面内容。但是，这种设计可能并不最佳。每当你发现自己反复编写相同的代码时，通常表明有更好的方法。

![](img/0356a82706a80f6f7db9d6650580be5b_41.png)

![](img/0356a82706a80f6f7db9d6650580be5b_43.png)

## 使用数据属性与循环优化代码 🔄

![](img/0356a82706a80f6f7db9d6650580be5b_45.png)

我们可以为按钮添加数据属性来存储颜色信息，然后使用循环来为所有按钮添加事件监听器。

```html
<button data-color="red">红色</button>
<button data-color="blue">蓝色</button>
<button data-color="green">绿色</button>
```

![](img/0356a82706a80f6f7db9d6650580be5b_49.png)

```javascript
document.addEventListener('DOMContentLoaded', function() {
    document.querySelectorAll('button').forEach(function(button) {
        button.onclick = function() {
            const color = this.dataset.color;
            document.querySelector('#hello').style.color = color;
        };
    });
});
```

`querySelectorAll` 返回一个包含所有匹配元素的节点列表（类似于数组）。`forEach` 方法允许我们为数组中的每个元素运行一个函数。`this` 关键字在事件处理函数中指向接收到事件的元素（即被点击的按钮）。`dataset` 属性允许我们访问元素的数据属性。

## 使用下拉菜单与 `onchange` 事件 📋

![](img/0356a82706a80f6f7db9d6650580be5b_51.png)

![](img/0356a82706a80f6f7db9d6650580be5b_53.png)

我们可以使用下拉菜单代替按钮，并监听 `onchange` 事件。

```html
<select>
    <option value="black">黑色</option>
    <option value="red">红色</option>
    <option value="blue">蓝色</option>
    <option value="green">绿色</option>
</select>
```

![](img/0356a82706a80f6f7db9d6650580be5b_55.png)

```javascript
document.querySelector('select').onchange = function() {
    document.querySelector('#hello').style.color = this.value;
};
```

![](img/0356a82706a80f6f7db9d6650580be5b_57.png)

`this.value` 获取用户在下拉菜单中选择的值。这样，代码比之前更简洁。

## 构建待办事项列表应用 ✅

![](img/0356a82706a80f6f7db9d6650580be5b_59.png)

让我们看看如何使用这些事件来构建一个待办事项列表应用程序。我们将创建一个表单来添加新任务，并动态更新任务列表。

![](img/0356a82706a80f6f7db9d6650580be5b_61.png)

以下是核心的 HTML 结构：

![](img/0356a82706a80f6f7db9d6650580be5b_63.png)

```html
<h1>任务</h1>
<ul id="tasks"></ul>
<form>
    <input id="task" placeholder="新任务" type="text">
    <input id="submit" type="submit" value="添加">
</form>
```

![](img/0356a82706a80f6f7db9d6650580be5b_65.png)

以下是实现添加任务功能的 JavaScript 代码：

![](img/0356a82706a80f6f7db9d6650580be5b_67.png)

```javascript
document.addEventListener('DOMContentLoaded', function() {
    // 默认禁用提交按钮
    document.querySelector('#submit').disabled = true;

    // 监听任务输入框，启用/禁用提交按钮
    document.querySelector('#task').onkeyup = function() {
        if (document.querySelector('#task').value.length > 0) {
            document.querySelector('#submit').disabled = false;
        } else {
            document.querySelector('#submit').disabled = true;
        }
    };

    // 监听表单提交事件
    document.querySelector('form').onsubmit = function() {
        // 获取用户输入的任务
        const task = document.querySelector('#task').value;

        // 创建一个新的列表项元素
        const li = document.createElement('li');
        li.innerHTML = task;

        // 将新任务添加到列表中
        document.querySelector('#tasks').append(li);

        // 清空输入框
        document.querySelector('#task').value = '';

        // 重新禁用提交按钮
        document.querySelector('#submit').disabled = true;

        // 阻止表单默认提交行为
        return false;
    };
});
```

![](img/0356a82706a80f6f7db9d6650580be5b_69.png)

这段代码实现了以下功能：
1.  页面加载时禁用提交按钮。
2.  当用户在任务输入框中键入时，检查输入内容长度，从而启用或禁用提交按钮。
3.  提交表单时，获取输入值，创建一个新的 `<li>` 元素，将其添加到任务列表中，然后清空输入框并重新禁用提交按钮。

![](img/0356a82706a80f6f7db9d6650580be5b_71.png)

## 总结 📚

![](img/0356a82706a80f6f7db9d6650580be5b_73.png)

![](img/0356a82706a80f6f7db9d6650580be5b_75.png)

本节课中我们一起学习了 JavaScript DOM 操作的核心概念。我们从更新元素内容开始，逐步学会了如何响应用户事件（如点击、提交、按键），如何动态修改元素的样式和属性，以及如何创建和添加新的 HTML 元素到页面中。

![](img/0356a82706a80f6f7db9d6650580be5b_77.png)

我们还探讨了优化代码的方法，例如使用数据属性、循环以及将 JavaScript 代码与 HTML 结构分离。最后，我们综合运用这些知识构建了一个交互式的待办事项列表应用。

![](img/0356a82706a80f6f7db9d6650580be5b_79.png)

通过掌握这些技术，你已经能够让静态网页变得动态和交互，这是开发现代 Web 应用的基础。