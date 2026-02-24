# React 开发教程：第 24 章：使用 useRef 访问底层 DOM 🔍

在本节课中，我们将学习如何使用 React 的 `useRef` Hook 来访问和操作底层的 DOM 元素。我们将通过一个具体的例子——创建一个点击按钮后自动聚焦到输入框的功能——来演示其核心用法。

---

## 概述

假设“小柠檬”餐厅的店主希望为库存搜索功能添加一个特性：点击按钮后，光标能自动聚焦到搜索输入框。在本节中，我们将在一个独立的应用中编写代码来实现这一特定需求，以便专注于 `useRef` Hook 的功能。

## 初始应用设置

首先，我们有一个使用 Create React App (CRA) 构建的示例应用。为了更清晰地展示 `useRef` 的用法，我对初始代码进行了一些调整。

初始应用仅包含一个返回语句，其中有一个 `Fragment`，内部是一个显示“使用 useRef 访问底层 DOM”的 `H1` 标题。

![](img/b74e5929c6ba0c1e4cc1a046cff3805d_1.png)

```jsx
import React from 'react';

function App() {
  return (
    <>
      <h1>使用 useRef 访问底层 DOM</h1>
    </>
  );
}

export default App;
```

## 添加输入框和按钮

为了演示 `useRef` 如何用于访问 DOM，我们将用它来将光标聚焦到一个输入框。因此，我们首先需要添加一个输入框和一个按钮。

```jsx
function App() {
  return (
    <>
      <h1>使用 useRef 访问底层 DOM</h1>
      <input type="text" />
      <button>聚焦输入框</button>
    </>
  );
}
```

## 实现点击处理函数

现在，我们为按钮添加一个 `onClick` 事件处理属性。我们需要定义 `focusInput` 函数来处理按钮点击。

```jsx
function App() {
  const focusInput = () => {
    // 这里将实现聚焦逻辑
  };

  return (
    <>
      <h1>使用 useRef 访问底层 DOM</h1>
      <input type="text" />
      <button onClick={focusInput}>聚焦输入框</button>
    </>
  );
}
```

## 引入 useRef Hook

为了访问输入框的 DOM 节点，我们需要使用 `useRef` Hook。`useRef` 返回一个可变的 ref 对象，其 `.current` 属性被初始化为传入的参数（这里为 `null`）。

```jsx
import React, { useRef } from 'react';

function App() {
  const formInputRef = useRef(null);

  const focusInput = () => {
    // 聚焦逻辑将在这里使用 formInputRef
  };

  return (
    <>
      <h1>使用 useRef 访问底层 DOM</h1>
      <input type="text" ref={formInputRef} />
      <button onClick={focusInput}>聚焦输入框</button>
    </>
  );
}
```

## 连接 Ref 与 DOM 节点

我们将 `formInputRef` 作为 `ref` 属性的值传递给 `input` 元素。React 在创建该输入框的 DOM 节点并渲染到屏幕上后，会将该 DOM 节点赋值给 `formInputRef.current` 属性。

## 实现聚焦逻辑

现在，我们可以在 `focusInput` 函数中访问这个 DOM 节点。输入框的 DOM 节点有一个 `.focus()` 方法，可以使其获得焦点。

```jsx
const focusInput = () => {
  formInputRef.current.focus();
};
```

**代码解释：**
*   `formInputRef.current` 指向 `<input>` 的 DOM 节点。
*   `.focus()` 是该 DOM 节点自带的方法，用于将焦点设置到该元素上。

这样，用户无需手动点击或按 Tab 键切换到输入框，点击按钮即可直接开始输入。

## 测试功能

保存所有更改，在浏览器中查看运行中的应用。点击输入框外部，然后点击“聚焦输入框”按钮。可以看到光标成功跳转到了输入框内，功能正常工作。

## 核心概念总结

*   **`useRef` Hook**： 用于创建一个可变的 ref 对象，其 `.current` 属性可以持有任何值。
*   **访问 DOM**： 将 ref 对象通过 `ref` 属性附加到 JSX 元素时，React 会将对应的 DOM 节点赋值给其 `.current` 属性。
*   **操作 DOM**： 通过 `refObject.current` 可以访问该 DOM 节点，并调用其原生方法（如 `.focus()`）或读取/修改其属性。

![](img/b74e5929c6ba0c1e4cc1a046cff3805d_3.png)

![](img/b74e5929c6ba0c1e4cc1a046cff3805d_4.png)

## 本节总结

![](img/b74e5929c6ba0c1e4cc1a046cff3805d_5.png)

在本节课中，我们一起学习了如何使用 `useRef` Hook 来“钩入”DOM，并基于手头的任务（例如聚焦输入框）来操作特定 DOM 节点的属性。`useRef` 是连接 React 声明式世界与命令式 DOM 操作的重要桥梁。