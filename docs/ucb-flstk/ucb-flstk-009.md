# 009：React进阶与路由

![](img/41f17d119df49d05258f0dda5bfd36de_0.png)

在本节课中，我们将深入学习React的核心概念，包括两个重要的Hook：`useEffect`，以及如何为React应用添加多页面功能（路由）。我们还将介绍如何通过`Axios`库与后端API进行通信以获取数据。

上一讲我们介绍了React的基础，包括组件、状态和属性。本节中我们来看看更高级的Hook和如何构建多页面应用。

## 🪝 深入理解 `useEffect` Hook

`useEffect` 是一个用于处理组件“副作用”的Hook。副作用指的是那些与渲染结果无关的操作，例如数据获取、订阅或手动修改DOM。

其基本语法是一个接受两个参数的函数：
```javascript
useEffect(() => {
  // 副作用逻辑在这里执行
}, [dependencies]);
```
*   第一个参数是一个函数，包含要执行的副作用代码。
*   第二个参数是一个依赖项数组，用于控制副作用执行的时机。

### 依赖项数组的作用

以下是依赖项数组不同情况的说明：

*   **不提供依赖项数组**：副作用函数在**每次**组件渲染后都会执行。
*   **提供空数组 `[]`**：副作用函数仅在组件**首次渲染**后执行一次。
*   **提供非空数组 `[dep1, dep2]`**：副作用函数在**首次渲染后**以及**依赖项的值发生变化时**执行。

**示例**：假设我们有一个计数器和一个提示框状态。我们希望仅在提示框状态改变时弹出提示。
```javascript
const [count, setCount] = useState(0);
const [alert, setAlert] = useState(‘初始值’);

useEffect(() => {
  alert(‘alert状态改变了！’);
}, [alert]); // 仅当alert变量变化时执行
```
点击计数器按钮不会触发`useEffect`，因为`count`不在依赖项中。只有调用`setAlert`改变`alert`值时，才会弹出提示。

`useEffect` 在数据获取场景中非常有用。你可以将存储数据的状态变量放入依赖项，这样当数据更新后，组件会自动重新渲染以展示新数据。

## 🧭 React Router 实现客户端路由

目前我们构建的都是单页面应用。路由使我们能够为应用添加多个“页面”，并根据URL显示不同的内容。

### 核心概念

*   **客户端路由**：与传统的`<a>`标签（会触发整个页面刷新）不同，React Router 实现了客户端路由。它只更新页面中需要变化的部分，提供更流畅的用户体验。
*   **`<Router>`**： 需要用 `<BrowserRouter>` 包裹整个应用的根组件，为应用提供路由上下文。
*   **`<Switch>` 与 `<Route>`**： `<Switch>` 组件用于包裹一组 `<Route>`。`<Route>` 定义了路径和对应渲染的组件。
*   **`<Link>`**： 用于导航的特殊组件，替代 `<a>` 标签。它不会导致页面完全重新加载。

### 使用步骤

以下是实现路由的基本步骤：

1.  **安装库**： 使用React Router v5（本课程版本）。
    ```bash
    npm install react-router-dom@5
    ```
2.  **包裹应用**： 在入口文件（如`index.js`）中用 `<BrowserRouter>` 包裹 `<App>` 组件。
3.  **定义路由结构**： 在组件中使用 `<Switch>` 和 `<Route>`。
    ```javascript
    import { Switch, Route } from ‘react-router-dom’;

    function App() {
      return (
        <div>
          <nav>{/* 导航栏 */}</nav>
          <Switch>
            <Route exact path=“/” component={HomePage} />
            <Route path=“/about” component={AboutPage} />
          </Switch>
        </div>
      );
    }
    ```
4.  **使用 `<Link>` 导航**：
    ```javascript
    import { Link } from ‘react-router-dom’;
    <Link to=“/about”>关于我们</Link>
    ```

## 🔄 使用 Axios 获取API数据

为了在React应用中显示动态内容，我们需要从后端服务器获取数据。`Axios` 是一个基于Promise的HTTP客户端，非常适合此任务。

### 结合 `useEffect` 与 `Axios`

数据获取通常是一个副作用，因此应在 `useEffect` 中执行。将依赖项数组设为空数组 `[]` 可以确保只在组件挂载时获取一次数据，避免不必要的网络请求。

**示例：获取GitHub用户信息**

```javascript
import React, { useState, useEffect } from ‘react’;
import axios from ‘axios’;

function GitHubInfo() {
  const [userData, setUserData] = useState(null);

  useEffect(() => {
    const fetchData = async () => {
      try {
        const response = await axios.get(‘https://api.github.com/users/你的用户名‘);
        setUserData(response.data); // 将获取的数据存入状态
      } catch (error) {
        console.error(‘获取数据失败:‘, error);
      }
    };

    fetchData();
  }, []); // 空依赖数组确保只获取一次

  return (
    <div>
      {userData ? (
        <p>GitHub 粉丝数: {userData.followers}</p>
      ) : (
        <p>加载中...</p> // 处理数据加载前的状态
      )}
    </div>
  );
}
```
**关键点说明**：
*   **异步操作**： `axios.get` 返回一个Promise，我们使用 `async/await` 语法等待其完成。
*   **状态管理**： 将获取的数据（`response.data`）通过 `setUserData` 存入状态。
*   **条件渲染**： 在数据加载完成前（`userData` 为 `null`），显示“加载中…”提示，防止访问未定义的数据。

---

![](img/41f17d119df49d05258f0dda5bfd36de_2.png)

![](img/41f17d119df49d05258f0dda5bfd36de_4.png)

本节课中我们一起学习了React的`useEffect` Hook，它用于管理副作用逻辑；了解了如何使用React Router v5为单页面应用添加多页面路由功能；最后，我们掌握了通过`Axios`库在`useEffect`中异步获取后端API数据并渲染到页面的完整流程。这些是构建动态、交互式现代Web应用的核心技能。