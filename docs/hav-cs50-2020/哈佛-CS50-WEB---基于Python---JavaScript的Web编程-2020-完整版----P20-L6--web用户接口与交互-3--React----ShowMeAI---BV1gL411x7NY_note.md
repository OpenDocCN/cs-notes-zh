# 哈佛 CS50-WEB ｜ 基于Python / JavaScript的Web编程(2020·完整版) - P20：L6- Web用户接口与交互 3 (React) 🧩

![](img/5d53683b6a69413d33c6e42e94e87297_1.png)

在本节课中，我们将要学习如何使用React框架来构建动态、交互式的Web用户界面。React是一个强大的JavaScript库，它允许我们基于应用程序的状态来声明式地描述UI，并自动处理UI的更新。

## 概述：从命令式到声明式编程

随着网页变得越来越复杂和动态，我们需要大量的JavaScript代码来保持所有元素的同步和更新。为了更高效地创建交互式界面，开发者转向了像React这样的JavaScript库或框架。

React使我们能够设计出能根据底层状态自动更新的用户界面。它的核心思想是**声明式编程**，这与传统的**命令式编程**风格不同。

![](img/5d53683b6a69413d33c6e42e94e87297_3.png)

上一节我们介绍了JavaScript如何直接操作DOM来更新界面，本节中我们来看看React如何通过声明状态来简化这一过程。

### 命令式编程 vs 声明式编程

在命令式编程中，你需要明确地告诉计算机每一步该做什么。例如，更新一个计数器显示：

```javascript
// 命令式编程示例
let h1 = document.querySelector('h1');
let num = parseInt(h1.innerHTML);
num += 1;
h1.innerHTML = num;
```

这段代码明确地获取元素、解析内容、计算新值并更新DOM。

在声明式编程中，你只需描述UI应该是什么样子，而由框架（如React）来处理如何更新到那个状态。在React中，你可能会这样写：

![](img/5d53683b6a69413d33c6e42e94e87297_5.png)

![](img/5d53683b6a69413d33c6e42e94e87297_7.png)

![](img/5d53683b6a69413d33c6e42e94e87297_9.png)

![](img/5d53683b6a69413d33c6e42e94e87297_11.png)

```jsx
// 声明式编程示例 (React JSX)
<h1>{num}</h1>
// 当 num 的值改变时，React会自动更新h1的内容。
```

![](img/5d53683b6a69413d33c6e42e94e87297_13.png)

React允许我们将应用程序分割成多个**组件**，每个组件管理自己的**状态**。当我们操作状态时，React会自动、高效地更新用户界面。

![](img/5d53683b6a69413d33c6e42e94e87297_15.png)

## 开始使用React

要在网页中使用React，最简单的方法是引入三个必要的JavaScript库。

![](img/5d53683b6a69413d33c6e42e94e87297_17.png)

![](img/5d53683b6a69413d33c6e42e94e87297_19.png)

以下是引入React、React DOM和Babel（用于转换JSX代码）的基本HTML结构：

```html
<!DOCTYPE html>
<html>
<head>
    <script src="https://unpkg.com/react@17/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <title>React 应用</title>
</head>
<body>
    <div id="app"></div>
    <script type="text/babel">
        // 我们的React代码将写在这里
    </script>
</body>
</html>
```

*   `React`： 核心库，用于定义组件和逻辑。
*   `ReactDOM`： 用于将React组件渲染到网页的DOM中。
*   `Babel`： 一个转换器，用于将JSX语法转换为浏览器能理解的普通JavaScript。

![](img/5d53683b6a69413d33c6e42e94e87297_21.png)

![](img/5d53683b6a69413d33c6e42e94e87297_23.png)

## 第一个React组件：Hello World

React应用由**组件**构成。组件是用户界面的一部分，可以用JavaScript函数来定义。

![](img/5d53683b6a69413d33c6e42e94e87297_25.png)

让我们创建一个简单的“Hello World”组件：

![](img/5d53683b6a69413d33c6e42e94e87297_27.png)

```jsx
// 定义一个名为 App 的组件
function App() {
    return (
        <div>你好，世界！</div>
    );
}

// 将 App 组件渲染到 id 为 “app” 的 div 中
ReactDOM.render(<App />, document.querySelector(‘#app’));
```

![](img/5d53683b6a69413d33c6e42e94e87297_29.png)

![](img/5d53683b6a69413d33c6e42e94e87297_31.png)

![](img/5d53683b6a69413d33c6e42e94e87297_33.png)

在这个例子中：
1.  我们定义了一个函数 `App`，它是一个React组件。
2.  这个函数返回一些**JSX**（看起来像HTML的代码），描述了组件要渲染的内容。
3.  使用 `ReactDOM.render()` 方法将 `<App />` 组件插入到页面中ID为 `app` 的 `<div>` 里。

![](img/5d53683b6a69413d33c6e42e94e87297_35.png)

JSX允许我们在JavaScript中直接编写类似HTML的结构，并且可以在其中嵌入JavaScript表达式，使用花括号 `{}`。

```jsx
function App() {
    let x = 1;
    let y = 2;
    return (
        <div>{x} + {y} 的值是：{x + y}</div>
    );
}
// 页面上会显示：1 + 2 的值是：3
```

![](img/5d53683b6a69413d33c6e42e94e87297_37.png)

## 组件的复用与Props

![](img/5d53683b6a69413d33c6e42e94e87297_39.png)

组件的强大之处在于可复用性。我们可以创建通用组件，并通过**props**（属性）来定制它们。

以下是如何创建一个可复用的问候组件：

![](img/5d53683b6a69413d33c6e42e94e87297_41.png)

```jsx
// 定义一个接受 props 的 Hello 组件
function Hello(props) {
    return <h1>你好，{props.name}！</h1>;
}

![](img/5d53683b6a69413d33c6e42e94e87297_43.png)

function App() {
    return (
        <div>
            <Hello name="哈利" />
            <Hello name="罗恩" />
            <Hello name="赫敏" />
        </div>
    );
}
// 页面上会渲染三个标题，分别显示“你好，哈利！”、“你好，罗恩！”和“你好，赫敏！”。
```

*   `Hello` 组件接受一个 `props` 参数，其中包含了传递给组件的所有属性。
*   在 `App` 组件中，我们三次使用 `<Hello />` 组件，每次传递不同的 `name` 属性值。
*   这使得同一个组件能根据不同的输入渲染出不同的内容。

## 状态管理：useState Hook

![](img/5d53683b6a69413d33c6e42e94e87297_45.png)

![](img/5d53683b6a69413d33c6e42e94e87297_47.png)

使界面具有交互性的关键是**状态**。状态是组件内部需要跟踪和响应的数据。React 提供了 `useState` 这个 **Hook** 来在函数组件中添加状态。

![](img/5d53683b6a69413d33c6e42e94e87297_49.png)

让我们用状态来构建一个计数器应用：

![](img/5d53683b6a69413d33c6e42e94e87297_51.png)

```jsx
function Counter() {
    // 声明一个状态变量 count，初始值为 0，以及更新它的函数 setCount
    const [count, setCount] = React.useState(0);

    // 定义点击按钮时调用的函数
    function updateCount() {
        setCount(count + 1); // 使用 setCount 更新状态
    }

    return (
        <div>
            <div>当前计数：{count}</div>
            <button onClick={updateCount}>点击计数</button>
        </div>
    );
}

ReactDOM.render(<Counter />, document.querySelector(‘#app’));
```

*   `const [count, setCount] = React.useState(0);` 创建了状态。`count` 是当前值，`setCount` 是用于更新它的函数。
*   在按钮上，我们设置了 `onClick={updateCount}` 事件处理程序。
*   当点击按钮时，`updateCount` 函数调用 `setCount(count + 1)` 来更新状态。
*   **关键点**：当状态 `count` 改变时，React 会自动重新渲染组件，UI 中的 `{count}` 会显示新的值。我们不需要手动操作DOM。

![](img/5d53683b6a69413d33c6e42e94e87297_53.png)

## 综合实践：构建一个加法测验游戏

![](img/5d53683b6a69413d33c6e42e94e87297_55.png)

现在，我们将结合所学知识，构建一个更复杂的应用：一个随机生成加法题目的测验游戏。

### 步骤1：设置基础结构和状态

首先，我们设置游戏所需的状态：两个加数、用户的答案、当前得分以及是否回答错误。

```jsx
function AdditionGame() {
    // 使用一个对象来管理多个状态
    const [state, setState] = React.useState({
        num1: Math.ceil(Math.random() * 10), // 随机数1
        num2: Math.ceil(Math.random() * 10), // 随机数2
        response: “”, // 用户输入的答案
        score: 0,     // 得分
        incorrect: false // 是否回答错误
    });

    // ... 后续UI和逻辑将在这里添加
}
```

![](img/5d53683b6a69413d33c6e42e94e87297_57.png)

![](img/5d53683b6a69413d33c6e42e94e87297_59.png)

### 步骤2：渲染用户界面

![](img/5d53683b6a69413d33c6e42e94e87297_61.png)

根据状态渲染出题目、输入框和得分。

![](img/5d53683b6a69413d33c6e42e94e87297_63.png)

```jsx
return (
    <div>
        {/* 问题部分，如果回答错误则添加 ‘incorrect’ 类 */}
        <div id=“problem” className={state.incorrect ? “incorrect” : “”}>
            {state.num1} + {state.num2}
        </div>
        {/* 答案输入框 */}
        <input
            value={state.response}
            onChange={updateResponse}
            onKeyPress={inputKeyPress}
            autoFocus
        />
        {/* 显示当前得分 */}
        <div>得分：{state.score}</div>
    </div>
);
```

### 步骤3：处理用户输入

![](img/5d53683b6a69413d33c6e42e94e87297_65.png)

我们需要两个函数：一个用于实时更新输入框的内容，另一个用于在按下回车键时检查答案。

![](img/5d53683b6a69413d33c6e42e94e87297_67.png)

```jsx
// 当输入框内容变化时更新 response 状态
function updateResponse(event) {
    setState({
        ...state, // 使用扩展运算符保留其他状态
        response: event.target.value
    });
}

![](img/5d53683b6a69413d33c6e42e94e87297_69.png)

// 当在输入框中按下按键时触发
function inputKeyPress(event) {
    if (event.key === “Enter”) { // 检查是否是回车键
        const answer = parseInt(state.response);
        if (state.num1 + state.num2 === answer) {
            // 回答正确：加分，生成新题目，清空输入，标记为正确
            setState({
                ...state,
                score: state.score + 1,
                num1: Math.ceil(Math.random() * 10),
                num2: Math.ceil(Math.random() * 10),
                response: “”,
                incorrect: false
            });
        } else {
            // 回答错误：扣分，清空输入，标记为错误
            setState({
                ...state,
                score: state.score - 1,
                response: “”,
                incorrect: true
            });
        }
    }
}
```

![](img/5d53683b6a69413d33c6e42e94e87297_71.png)

![](img/5d53683b6a69413d33c6e42e94e87297_73.png)

![](img/5d53683b6a69413d33c6e42e94e87297_75.png)

### 步骤4：添加游戏胜利条件

![](img/5d53683b6a69413d33c6e42e94e87297_77.png)

我们可以通过条件渲染，在得分达到10分时显示胜利画面。

![](img/5d53683b6a69413d33c6e42e94e87297_79.png)

![](img/5d53683b6a69413d33c6e42e94e87297_81.png)

```jsx
// 在 return 之前添加条件判断
if (state.score === 10) {
    return <div id=“winner”>🎉 你赢得了比赛！</div>;
}

![](img/5d53683b6a69413d33c6e42e94e87297_83.png)

// 原来的 return 语句渲染正常的游戏界面
return ( ... );
```

![](img/5d53683b6a69413d33c6e42e94e87297_85.png)

![](img/5d53683b6a69413d33c6e42e94e87297_87.png)

### 步骤5：添加CSS样式

最后，添加一些CSS让游戏看起来更美观。

![](img/5d53683b6a69413d33c6e42e94e87297_89.png)

![](img/5d53683b6a69413d33c6e42e94e87297_91.png)

```html
<style>
    body { text-align: center; font-family: Arial; }
    #problem { font-size: 48px; }
    .incorrect { color: red; }
    #winner { font-size: 72px; color: green; }
    input { font-size: 24px; margin: 10px; }
</style>
```

![](img/5d53683b6a69413d33c6e42e94e87297_93.png)

现在，一个功能完整的加法测验游戏就完成了！用户可以通过它练习加法，得分会随之变化，达到10分即可获胜。

![](img/5d53683b6a69413d33c6e42e94e87297_95.png)

## 总结

![](img/5d53683b6a69413d33c6e42e94e87297_97.png)

本节课中我们一起学习了React框架的核心概念与应用。

![](img/5d53683b6a69413d33c6e42e94e87297_99.png)

![](img/5d53683b6a69413d33c6e42e94e87297_101.png)

我们首先了解了**声明式编程**与命令式编程的区别，React通过让我们描述“UI应该是什么样子”来简化开发。接着，我们学习了如何创建**组件**，这是构建React应用的基石，并通过**props**使组件变得可复用和可配置。

然后，我们深入探讨了**状态管理**，使用 `useState` Hook 来存储和更新组件内部的数据，这是创建交互式应用的关键。最后，我们综合运用这些知识，构建了一个包含状态、事件处理、条件渲染和基础样式的加法测验游戏。

React（以及类似的框架如Vue和Angular）的核心价值在于，它让我们能够专注于应用程序的数据（状态）和业务逻辑，而将复杂的UI同步与更新任务交给框架本身高效处理。这极大地提升了开发动态、数据驱动型Web应用的效率和体验。