# Django for Everybody：4：修改文档对象模型(DOM)的JavaScript技术

在本节课中，我们将学习如何使用JavaScript动态地修改网页的文档对象模型（DOM）。我们将从简单的元素内容修改开始，逐步深入到创建新元素、将其添加到DOM中，以及通过JavaScript控制CSS样式来实现元素的显示与隐藏。

## 从控制台日志到DOM修改

上一节我们介绍了如何在浏览器控制台中查看JavaScript的运行情况。本节中，我们来看看如何实际修改文档对象模型（DOM）。

回忆一下之前使用调试器修改DOM的例子。我们修改了DOM，如果修改的内容在窗口中可见，那么变化会立即呈现。本质上，我们在一端运行JavaScript，用户界面（UI）就会随之改变，这个过程几乎是瞬间完成的。当然，如果代码运行时间过长，变化可能会延迟，因为浏览器需要先完成JavaScript代码的执行，然后才能重新显示页面。

![](img/5b287a3cedf2ed8f1d3ae0536f312b14_1.png)

![](img/5b287a3cedf2ed8f1d3ae0536f312b14_2.png)

![](img/5b287a3cedf2ed8f1d3ae0536f312b14_3.png)

我们可以手动进行这些修改，但更好的方式是通过事件来触发修改。为了触发修改，我们需要能够获取DOM的特定部分，或者说查询文档对象模型。

## 通过事件触发DOM修改

![](img/5b287a3cedf2ed8f1d3ae0536f312b14_5.png)

让我们回顾一个使用事件处理函数的例子。以下代码展示了我们可以在JavaScript中定义一个函数，并通过`onclick`方法在点击事件发生后调用该函数。请注意，引号的使用很重要。

![](img/5b287a3cedf2ed8f1d3ae0536f312b14_7.png)

```html
<button onclick="myFunction()">点击我</button>
```

`onclick`属性是一个字符串，它只在点击的那一刻被解析，然后`myFunction`函数在那一刻被调用。

现在，让我们在`onclick`方法中做一些更有趣的事情。

## 修改现有元素的内容

以下是一个更具体的例子。页面的顶部是一个带有ID的H1标签，我们设置其`id="fun"`。ID在整个文档中必须是唯一的，这与CSS规则一致。DOM元素拥有属性和方法，其中之一就是`innerHTML`。

```html
<h1 id="fun">原始标题</h1>
<button onclick="changeHeader()">改变标题</button>

![](img/5b287a3cedf2ed8f1d3ae0536f312b14_9.png)

![](img/5b287a3cedf2ed8f1d3ae0536f312b14_10.png)

<script>
function changeHeader() {
    document.getElementById('fun').innerHTML = '一个很酷的标题';
    console.log('标题已被点击并更改');
}
</script>
```

![](img/5b287a3cedf2ed8f1d3ae0536f312b14_12.png)

在这段代码中，我们简单地将`innerHTML`属性赋值为“一个很酷的标题”。这就是你看到变化的基本方式——我们正在改变元素。

这个过程的一个重要部分是函数会结束。函数执行完毕后，控制权交还给浏览器。浏览器检测到DOM发生了变化，然后重新显示页面。如果我们函数的最后一行做了某些疯狂的操作，没有将线程交还给浏览器，页面可能会出错。但在这里，我们只是修改DOM然后返回。

这段代码运行得非常快，眨眼之间就完成了。其中没有任何缓慢的操作，一切发生得都很快。浏览器得以迅速重新显示内容。因此，当你点击按钮时，你会看到标题立即变成了“一个很酷的标题”。

我也可以读取`innerHTML`然后追加内容，但在这个例子中，我们直接替换了它。一旦函数执行完毕，浏览器就会接管并重新显示更新后的内容。

## 向DOM中添加新元素

到目前为止，我们所做的都是找到标签、修改它，然后放回去。现在，让我们尝试向DOM中添加全新的元素。这是一个稍微复杂一点的操作。

![](img/5b287a3cedf2ed8f1d3ae0536f312b14_14.png)

以下是实现此功能的源代码。我们有一个按钮（锚点标签），它调用`add`函数。页面上还有一个`<ul>`标签，其`id="zap"`，里面最初有一个列表项`<li>`。

```html
<ul id="zap">
    <li>第一个项目</li>
</ul>
<button onclick="add()">添加项目</button>

<script>
let counter = 1; // 全局变量

![](img/5b287a3cedf2ed8f1d3ae0536f312b14_16.png)

function add() {
    // 创建一个新的LI元素
    const newItem = document.createElement('li');
    // 设置其类名和内容
    newItem.className = 'new';
    newItem.innerHTML = '项目编号 ' + counter;

    // 找到UL元素，并将新的LI添加为其子元素
    document.getElementById('zap').appendChild(newItem);

    counter++; // 计数器加一
}
</script>
```

![](img/5b287a3cedf2ed8f1d3ae0536f312b14_18.png)

首先，我们创建一个全局变量`counter`并初始化为1。在`add`函数中，我们使用`document.createElement('li')`创建一个新的`<li>`元素。然后，我们可以设置它的属性，比如`className`和`innerHTML`。这里，我们将`innerHTML`设置为“项目编号”加上当前的计数器值。

接着，我们通过`document.getElementById('zap')`找到`<ul>`标签，并使用`appendChild`方法将新创建的`<li>`元素添加为其子元素。每次点击按钮，`counter`都会增加1，并且会添加一个新的列表项。

初始状态是“第一个项目”。点击按钮几次后，它会动态地添加“项目编号 1”、“项目编号 2”等项目。这样，我们就可以从JavaScript中操作DOM的许多方面，包括改变CSS，从而改变元素的外观。

![](img/5b287a3cedf2ed8f1d3ae0536f312b14_20.png)

![](img/5b287a3cedf2ed8f1d3ae0536f312b14_21.png)

## 通过JavaScript控制CSS样式

在这个例子中，我们有一个标题标签，其`id="fun"`，这同样是我们在JavaScript中获取它的方式。我们还有两个按钮，`id`分别为`poof`（隐藏）和`show`（显示），按钮文字也是“隐藏”和“显示”。

我们将使用`addEventListener`来绑定事件。虽然也可以使用`onclick`，但这里我想让大家习惯一种做法：通常在文档加载的最后阶段，集中添加所有的事件监听器。这样，HTML先被显示，然后再附加交互行为。

```html
<h1 id="fun">可隐藏的标题</h1>
<button id="show">显示</button>
<button id="poof">隐藏</button>

![](img/5b287a3cedf2ed8f1d3ae0536f312b14_23.png)

<script>
// 为“显示”按钮添加点击事件监听器
document.getElementById('show').addEventListener('click', function() {
    document.getElementById('fun').style.display = 'block';
});

// 为“隐藏”按钮添加点击事件监听器（使用箭头函数）
document.getElementById('poof').addEventListener('click', (event) => {
    document.getElementById('fun').style.display = 'none';
});
</script>
```

![](img/5b287a3cedf2ed8f1d3ae0536f312b14_25.png)

在脚本中，我们首先获取`show`按钮元素，然后为其添加一个事件监听器。我们监听`click`事件，第二个参数是一个函数（这里是一个匿名函数）。这个函数只有一行代码：获取`id="fun"`的元素，并通过`.style.display`将其CSS的`display`属性设置为`'block'`（显示）。

对于`poof`（隐藏）按钮，我们也添加一个点击事件监听器。这里使用了稍有不同的语法——箭头函数（`=>`）。这是现代JavaScript中更简洁的语法。箭头函数`(event) => { ... }`定义了一个匿名函数，它接收一个`event`参数（浏览器在调用时会传入事件对象），但在本例中我们并未使用它。函数体将标题的`display`样式设置为`'none'`，使其消失。

运行这段代码，点击“隐藏”，标题会消失；点击“显示”，标题会重新出现。这只是一个如何通过JavaScript修改CSS的简单示例。

![](img/5b287a3cedf2ed8f1d3ae0536f312b14_27.png)

## 总结

![](img/5b287a3cedf2ed8f1d3ae0536f312b14_29.png)

本节课中，我们一起学习了使用JavaScript动态操作DOM的核心技术。我们从修改现有元素的`innerHTML`开始，然后学习了如何创建全新的DOM元素（`createElement`）并将其添加到文档中（`appendChild`）。最后，我们探索了如何通过JavaScript直接操作元素的`style`属性来控制CSS，从而实现如显示/隐藏这样的动态视觉效果。这些技术是构建交互式网页应用的基础。