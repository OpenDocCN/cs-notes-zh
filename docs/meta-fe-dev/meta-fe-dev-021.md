# 21：子组件与数据

在本节课中，我们将要学习 React JS 中的数据流。具体来说，我们将了解数据在 React 组件中如何单向流动，以及如何通过 `props` 和 `state` 来展示无状态和有状态组件的使用。

## 概述：什么是单向数据流？

数据流在 React 中是单向的。这意味着数据只能从一个方向流动。

一个自然的问题是：为什么 React 中的单向数据流如此重要？

这种数据流确保了数据通过组件层级结构从上到下地移动。它也确保了变更能够在整个系统中传递。你将在后续课程中更详细地了解这一点。在本视频中，你还会学习如何通过关注数据流来展示无状态和有状态组件的使用。

## 数据流的核心概念

想象数据是金钱，而金钱由你的雇主控制。这笔钱可以被视为 `props`。这笔作为 `props` 的钱传递给你，就变成了你的 `state`。

`props` 总是从你的雇主流向你，而绝不会反向流动。在 React 中，数据通过 `props` 从父组件向下传递到子组件。

子组件不能改变或修改它接收到的 `props`，它只能读取它们并重新渲染。这意味着数据来源于父组件，并仅在子组件中被消费。

然而，如果情况总是如此，那么你在 React 应用中拥有的将只是 DOM 的独立片段，它们作为组件模板，仅用于填充接收到的数据。

虽然这很有效，但几乎没有任何交互性。

## 数据管理的两种方式：Props 与 State

你已经学习了如何使用 `props` 向子组件传递数据。然而，在 React 组件中处理数据还有另一种方式，这种数据被称为 `state`。

React 中的所有数据都可以分为 `props` 数据和 `state` 数据。

*   **`props` 数据**：是组件外部接收并使用的数据，但组件不能改变它。
*   **`state` 数据**：是组件内部的数据，组件可以控制并改变它。

也可以这样理解：

`props` 数据属于渲染该组件的父组件。
`state` 数据属于组件自身。

![](img/bc2cc5b43340f9fd82e3f7aab93ff400_1.png)

为了演示这一点，让我们打开 VS Code 并通过一个例子来实践。

## 实践示例：从父组件 State 到子组件 Props

我已经使用 `create-react-app` 构建了一个新应用。我创建了两个文件：`App.js` 和 `Child.js`。

`App.js` 文件使用类定义（而不是函数）来定义 App 组件。当它被创建时，它会用一个当前日期来初始化其 `state`。

```jsx
// App.js
class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      currentDate: new Date()
    };
  }
  // ... 其他代码
}
```

`render` 函数随后渲染一个名为 `Child` 的组件。`Child` 组件定义了一个名为 `message` 的 `prop`，其值被设置为从组件 `state` 中获取的当前日期，并转换为包含日期、小时、分钟和秒的字符串格式。

```jsx
// App.js 的 render 方法内
render() {
  return (
    <div className="App">
      <Child message={this.state.currentDate.toString()} />
    </div>
  );
}
```

在 `Child.js` 文件中，该组件在一个 `H1` 元素中渲染 `message` 这个 `prop`。

```jsx
// Child.js
function Child(props) {
  return <h1>{props.message}</h1>;
}
```

![](img/bc2cc5b43340f9fd82e3f7aab93ff400_3.png)

现在，当我运行这个应用时，App 组件的 `state` 将其数据向下流动到子组件的 `props` 中，`H1` 元素将显示当前的日期和时间。

## 总结

本节课中我们一起学习了 React JS 中数据如何在子组件间流动。你现在应该已经理解了单向数据流的重要性，即数据通过 `props` 从父组件传递到子组件。同时，你也应该能够通过关注数据流来展示无状态组件（主要依赖 `props`）和有状态组件（拥有并管理自己的 `state`）的使用。记住，`props` 是只读的，属于父组件；而 `state` 是可变的，属于组件自身。