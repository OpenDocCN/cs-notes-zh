# 全栈开发：第十三讲：React 3 演示

在本节课中，我们将学习 React 中的状态管理，特别是如何使用 `useState` Hook 来创建和管理组件内部的状态。我们将通过一个简单的计数器应用来演示其核心概念和用法。

上一讲我们介绍了 React 组件的基础结构，本节中我们来看看如何让组件“记住”并响应用户交互。

## 状态与 `useState` Hook

在 React 中，**状态** 指的是组件内部可以随时间变化的数据。当状态改变时，React 会自动重新渲染组件以反映最新的数据。我们使用 `useState` Hook 来为函数组件添加状态。

`useState` 是一个函数，它接收一个参数作为状态的初始值，并返回一个包含两个元素的数组：
1.  当前的状态值。
2.  一个用于更新该状态的函数。

其基本语法可以用以下代码描述：

```javascript
const [state, setState] = useState(initialState);
```

## 构建一个计数器应用

让我们通过构建一个计数器来实践 `useState` 的用法。这个计数器将显示一个数字，并提供两个按钮来增加或减少这个数字。

### 步骤一：导入 `useState`

首先，我们需要从 `react` 库中导入 `useState` Hook。

![](img/7a9e564249570305ada245e8f13151fd_0.png)

```javascript
import React, { useState } from 'react';
```

### 步骤二：初始化状态

在函数组件内部，我们调用 `useState` 来声明一个状态变量。这里我们将计数器的初始值设为 0。

```javascript
function Counter() {
  const [count, setCount] = useState(0);
  // ... 其他代码
}
```

现在，变量 `count` 存储着当前计数值（初始为0），而 `setCount` 函数用于更新 `count` 的值。

![](img/7a9e564249570305ada245e8f13151fd_1.png)

### 步骤三：在 JSX 中显示状态

我们可以在组件的 JSX 中直接使用 `count` 变量来显示当前计数值。

```javascript
return (
  <div>
    <p>当前计数：{count}</p>
  </div>
);
```

### 步骤四：更新状态

为了改变状态，我们需要调用状态更新函数 `setCount`。重要的是，**我们永远不应该直接修改 `count` 变量**（例如 `count = count + 1`），而必须使用 `setCount` 函数。

![](img/7a9e564249570305ada245e8f13151fd_2.png)

以下是定义增加和减少计数功能的代码：

```javascript
const increment = () => {
  setCount(count + 1);
};

const decrement = () => {
  setCount(count - 1);
};
```

### 步骤五：绑定事件到按钮

最后，我们将这两个函数绑定到按钮的 `onClick` 事件上。

![](img/7a9e564249570305ada245e8f13151fd_3.png)

```javascript
return (
  <div>
    <p>当前计数：{count}</p>
    <button onClick={increment}>增加</button>
    <button onClick={decrement}>减少</button>
  </div>
);
```

当用户点击“增加”按钮时，`increment` 函数会被调用，它通过 `setCount(count + 1)` 将 `count` 状态更新为当前值加1，从而触发组件重新渲染。

## 完整组件代码

将以上所有步骤组合起来，我们就得到了一个完整的计数器组件：

```javascript
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  const increment = () => {
    setCount(count + 1);
  };

  const decrement = () => {
    setCount(count - 1);
  };

  return (
    <div>
      <p>当前计数：{count}</p>
      <button onClick={increment}>增加</button>
      <button onClick={decrement}>减少</button>
    </div>
  );
}

![](img/7a9e564249570305ada245e8f13151fd_4.png)

export default Counter;
```

## 核心概念回顾

本节课中我们一起学习了 React 状态管理的核心：

1.  **状态**：组件内部可变的私有数据。
2.  **`useState` Hook**：用于在函数组件中添加状态。它返回状态变量和对应的更新函数。
3.  **状态更新**：必须通过 `useState` 提供的更新函数（如 `setCount`）来修改状态，直接修改变量不会触发重新渲染。
4.  **数据驱动视图**：状态改变后，React 会自动重新计算组件的 JSX 并更新 DOM，使得界面与数据保持同步。

通过这个计数器示例，你掌握了使用 `useState` 管理组件状态的基本模式，这是构建交互式 React 应用的基石。