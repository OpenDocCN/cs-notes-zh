# 066：ReactJS 进阶与答疑

在本节课中，我们将学习 ReactJS 的进阶概念，包括状态管理、路由导航以及如何在实际项目中处理常见的开发问题。我们将通过一个问答环节，探讨同学们在完成作业时遇到的具体挑战，并演示如何解决它们。

![](img/a0329e44501b9a4d61bb7af00f2f1afc_1.png)

## 概述

本节课的核心是探讨前端开发中的状态管理和页面路由。我们将从简单的组件状态（`useState`）开始，逐步深入到全局状态管理（如 `useContext`）和持久化存储（如 `localStorage`）。接着，我们将重点介绍如何使用 `react-router-dom` 库来实现单页面应用（SPA）的路由导航，并解决在传递状态（如用户令牌）和页面保护时遇到的常见问题。

## 状态管理概览

在构建前端应用时，管理状态是一个核心概念。状态可以理解为应用在某一时刻的数据快照。根据其作用范围和生命周期，我们可以将状态分为几个层次。

上一节我们介绍了状态的基本概念，本节中我们来看看状态的不同类型及其管理工具。

![](img/a0329e44501b9a4d61bb7af00f2f1afc_3.png)

![](img/a0329e44501b9a4d61bb7af00f2f1afc_5.png)

### 状态类型

以下是前端应用中常见的几种状态类型：

![](img/a0329e44501b9a4d61bb7af00f2f1afc_7.png)

![](img/a0329e44501b9a4d61bb7af00f2f1afc_9.png)

1.  **局部非持久化状态**：使用 `useState` 在组件内部管理。这种状态存在于组件函数的作用域内，页面刷新后即消失。
    ```javascript
    const [count, setCount] = useState(0);
    ```

2.  **全局非持久化状态**：需要在多个组件间共享，但同样不持久化。简单的实现方式包括通过组件树层层传递 `props`，或使用 React 的 `useContext` Hook。

![](img/a0329e44501b9a4d61bb7af00f2f1afc_11.png)

![](img/a0329e44501b9a4d61bb7af00f2f1afc_13.png)

3.  **持久化状态**：需要跨越页面会话保存的数据。在浏览器中，这主要通过 `localStorage` 或 `Cookies` 实现。`localStorage` 是 HTML5 规范引入的（约2008年），比传统的 `Cookies` 使用起来更方便。

![](img/a0329e44501b9a4d61bb7af00f2f1afc_15.png)

![](img/a0329e44501b9a4d61bb7af00f2f1afc_17.png)

![](img/a0329e44501b9a4d61bb7af00f2f1afc_18.png)

![](img/a0329e44501b9a4d61bb7af00f2f1afc_20.png)

![](img/a0329e44501b9a4d61bb7af00f2f1afc_21.png)

4.  **完整的状态管理库**：对于大型工业级应用，通常会使用专门的状态管理库，如 **Redux** 或 **MobX**。这些工具提供了更强大、可预测的状态管理机制。

![](img/a0329e44501b9a4d61bb7af00f2f1afc_23.png)

![](img/a0329e44501b9a4d61bb7af00f2f1afc_25.png)

## 使用 React Router Dom 进行路由

![](img/a0329e44501b9a4d61bb7af00f2f1afc_27.png)

在单页面应用中，路由负责管理不同 URL 对应的视图组件，而无需重新加载整个页面。`react-router-dom` 是 React 生态中最流行的路由库。

![](img/a0329e44501b9a4d61bb7af00f2f1afc_29.png)

上一节我们讨论了状态管理，本节中我们来看看如何管理应用中的不同视图和页面导航。

### 安装与基本设置

首先，需要在项目中安装 `react-router-dom`。
```bash
npm install react-router-dom
```
安装后，你可以在 `package.json` 中看到其版本（例如 v6）。

### 基本路由结构

在应用的顶层（通常是 `App.jsx`），你需要用 `BrowserRouter` 包裹你的应用，并使用 `Routes` 和 `Route` 组件定义路径与组件的映射关系。

```jsx
import { BrowserRouter as Router, Routes, Route } from 'react-router-dom';

function App() {
  return (
    <Router>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/signin" element={<SignIn />} />
        <Route path="/dashboard" element={<Dashboard />} />
      </Routes>
    </Router>
  );
}
```

### 导航与链接

在组件内部，你不能使用传统的 `<a>` 标签进行导航，因为那会导致页面刷新。应该使用 `react-router-dom` 提供的 `Link` 组件或 `useNavigate` Hook。

*   **`Link` 组件**：类似于 `<a>` 标签，但实现的是客户端路由跳转。
    ```jsx
    import { Link } from 'react-router-dom';
    <Link to="/signup">去注册</Link>
    ```
*   **`useNavigate` Hook**：用于在 JavaScript 逻辑中进行编程式导航。
    ```jsx
    import { useNavigate } from 'react-router-dom';
    const navigate = useNavigate();
    // 登录成功后跳转
    navigate('/dashboard');
    ```

### 嵌套路由与布局

对于有共享布局（如导航栏）的页面，可以使用嵌套路由。父路由通过 `<Outlet />` 组件来渲染子路由的内容。

![](img/a0329e44501b9a4d61bb7af00f2f1afc_31.png)

```jsx
// 定义一个布局组件 SiteLayout.jsx
import { Outlet } from 'react-router-dom';
function SiteLayout() {
  return (
    <div>
      <nav>这里是导航栏</nav>
      <main>
        <Outlet /> {/* 子路由内容将在这里渲染 */}
      </main>
    </div>
  );
}

![](img/a0329e44501b9a4d61bb7af00f2f1afc_33.png)

// 在 App.jsx 中配置嵌套路由
<Routes>
  <Route path="/" element={<SiteLayout />}>
    <Route index element={<Home />} /> {/* 路径为 / */}
    <Route path="dashboard" element={<Dashboard />} /> {/* 路径为 /dashboard */}
  </Route>
  <Route path="/signin" element={<SignIn />} /> {/* 独立页面 */}
</Routes>
```

## 实战：认证与路由保护

一个常见的需求是：用户未登录时，访问受保护页面（如仪表盘）应被重定向到登录页；用户已登录时，访问登录/注册页应被重定向到主页。

上一节我们建立了路由结构，本节中我们来看看如何将认证状态与路由逻辑结合起来。

### 全局状态与令牌传递

1.  **在顶层管理令牌**：通常将用户认证令牌（token）存储在应用顶层（如 `App` 组件）的状态中，或使用 `useContext` 使其全局可用。同时，将令牌也保存到 `localStorage` 以实现持久化。
    ```jsx
    const [token, setToken] = useState(localStorage.getItem('token') || null);
    ```

2.  **传递令牌和更新函数**：通过 `props` 或将 `token` 和 `setToken` 放入 `Context`，将它们传递给需要访问令牌或修改令牌的子组件（如 `Dashboard`, `SignIn`）。

### 路由保护逻辑

在包裹所有路由的顶层组件（我们称之为 `Wrapper`）中，可以添加以下逻辑：

1.  **检查登录状态**：在 `useEffect` 中，检查 `localStorage` 或状态中的 `token`。
2.  **条件导航**：使用 `useNavigate` 和 `useLocation` Hooks。
    *   `useLocation` 可以获取当前路径信息。
    *   根据 `token` 是否存在以及当前路径，决定是否重定向用户。

```jsx
import { useEffect, useState } from 'react';
import { useNavigate, useLocation } from 'react-router-dom';

function Wrapper() {
  const [token, setToken] = useState(null);
  const [isLoading, setIsLoading] = useState(true); // 添加加载状态
  const navigate = useNavigate();
  const location = useLocation();

  useEffect(() => {
    const storedToken = localStorage.getItem('token');
    setToken(storedToken);
    setIsLoading(false); // 数据加载完毕
  }, []);

  useEffect(() => {
    if (!isLoading) {
      const publicPaths = ['/signin', '/signup'];
      const isPublicPath = publicPaths.includes(location.pathname);

      if (!token && !isPublicPath) {
        // 未登录且不在公开页面，跳转到登录页
        navigate('/signin');
      } else if (token && isPublicPath) {
        // 已登录但尝试访问登录/注册页，跳转到仪表盘
        navigate('/dashboard');
      }
    }
  }, [token, isLoading, location, navigate]);

  if (isLoading) {
    return <div>Loading...</div>; // 防止在检查完成前渲染受保护内容
  }

  return (
    // ... 渲染 Routes 和其他内容
  );
}
```

![](img/a0329e44501b9a4d61bb7af00f2f1afc_35.png)

### 处理异步令牌获取

由于 `localStorage` 是同步操作，上述示例是可行的。但如果令牌来自一个异步函数（如 API 调用），你需要确保在令牌状态确定之前，应用不会渲染依赖于令牌的路由内容。使用一个 `isLoading` 状态是一种清晰的解决方案。

## 总结

![](img/a0329e44501b9a4d61bb7af00f2f1afc_37.png)

本节课我们一起学习了 React 前端开发的进阶主题。我们回顾了从局部状态到全局状态管理的不同层次，并重点探讨了如何使用 `react-router-dom` v6 构建单页面应用的路由系统。通过一个整合认证状态与路由保护的实战示例，我们演示了如何管理用户令牌、在组件间传递状态、实现编程式导航，以及根据认证状态保护特定路由。记住，在构建复杂交互时，合理规划状态流和组件结构是保持代码清晰和可维护的关键。