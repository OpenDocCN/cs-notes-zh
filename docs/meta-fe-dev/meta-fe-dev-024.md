# 24：观察状态 🧐

在本节课中，我们将要学习React中状态（State）的核心概念，理解为何使用状态，并掌握如何使用`useState`钩子来观察和更新组件的状态。

## 概述

React中使用状态是为了处理应用程序中可能变化的数据。状态是React中一个强大的工具，开发者用它来管理应用程序内部可能改变的数据。需要记住，状态数据是组件内部的。这使得组件能够根据状态数据的变化重新渲染，并向用户展示最新的更新。

## 使用useState钩子更新组件

上一节我们介绍了状态的基本概念，本节中我们来看看如何使用之前遇到的`useState`钩子来更新组件。

`useState`钩子允许组件定义和追踪状态。它通过两个参数实现此功能：第一个参数用于访问状态，第二个参数是一个用于更新状态的函数。

例如，你可以使用`date`变量来访问日期状态，然后使用`setDate`函数来更新该状态。

![](img/48aabbbe323142c558b1af1026113ff9_1.png)

```javascript
const [date, setDate] = useState();
```

为了帮助你理解`useState`钩子的实用性，接下来我们将探索一个示例，演示如何使用它来观察和操纵组件的状态。

## 示例：观察与操纵状态

![](img/48aabbbe323142c558b1af1026113ff9_3.png)

让我们观察一个为名为“Little Lemon”的地中海餐厅制作的应用程序。它有一个子组件`Header`，该组件接收一个包含`props`的对象。

```javascript
function Header(props) {
  return <h1>{props.message}</h1>;
}
```

该组件在返回并渲染为H1元素之前，会访问`message`属性。

在父组件`App.js`中，我导入了`Heading`组件，并将`word`设置为一个状态变量，其初始值为字符串“eat”。（目前，我忽略“eat”字符串后的注释。）

在return语句中，我将`Heading`组件包裹在一个单独的div中。我传递了`message`属性，其值为`word`加上用双引号括起来的“at Little Lemon”，所有这些都包裹在一对花括号中。

```javascript
function App() {
  const [word, setWord] = useState('eat');
  return (
    <div>
      <Heading message={word + " at Little Lemon"} />
    </div>
  );
}
```

你已经知道，一对花括号表示一个JSX表达式，这意味着花括号内的所有代码都将作为常规JavaScript进行计算。JavaScript引擎获取单词“eat”并将其与“at Little Lemon”连接起来。因此，在浏览器窗口中，我得到“eat at Little Lemon”。

## 通过事件更新状态

如果我想将`word`状态变量的值更新为其他内容，例如“drink”，我可以直接使用`setWord`函数来实现。然而，当我保存更改并运行代码时，应用程序无法工作。这是因为不能直接从你的状态中调用状态设置函数。

相反，我需要基于一个事件（如点击）来更新它。😊

因此，我添加了另一个名为`button`的元素，并设置`onClick`属性等于`handleClick`。

我现在定义另一个名为`handleClick`的函数。在`handleClick`函数定义内部，我调用`setWord('drink')`。我保存所有文件并等待应用程序编译。

```javascript
function App() {
  const [word, setWord] = useState('eat');

  function handleClick() {
    setWord('drink');
  }

  return (
    <div>
      <Heading message={word + " at Little Lemon"} />
      <button onClick={handleClick}>点击这里</button>
    </div>
  );
}
```

现在，当我点击“点击这里”按钮时，我得到“drink at Little Lemon”。

## 关键要点

以下是观察和更新状态的核心要点：

*   要观察和更新状态，你可以使用状态钩子提供的这些状态设置函数和状态变量。
*   但你必须确保在JSX语法中使用事件处理属性，或者使用你将在以后学到的其他方法。

## 总结

本节课中我们一起学习了React中状态变化的基础知识，包括如何应用`useState`语法来观察和操纵组件中的状态。做得好。