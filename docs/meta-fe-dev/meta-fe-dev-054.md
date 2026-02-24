# 54：什么是上下文，为什么使用它 🧩

在本节课中，我们将要学习 React 中的一个重要概念——上下文（Context）。我们将探讨什么是上下文，为什么需要它，以及如何在实际项目中应用它来解决组件间数据传递的难题。

---

## 概述：数据传递的挑战

在典型的 React 应用中，数据通过属性（props）以自上而下的方式从父组件传递到子组件。

然而，应用中可能存在某些数据，需要被许多不同的组件所使用。在这些场景下，仅使用 React 提供的 props 来向下传递数据并不总是高效。

因此，本节视频将介绍一种替代的数据传递方式，称为“上下文”。你将学习它的定义、引入的原因，并通过实例进行探索。

---

## 为什么需要上下文？🌍

想象一下，Little Lemon 食品订购应用提供了一个浅色或深色主题，用于改变所有元素的背景和文本颜色。

或者是一些通用偏好设置，例如根据访问者的地理位置确定特定的区域设置，这些信息需要被多个组件知晓。

这些数据有什么共同点呢？它们代表了整个应用的**全局状态**。

随着应用规模的增长，构成应用的组件树也会变得庞大。如前所述，props 是 React 提供的向下传递数据的方式，但在此场景下，它可能变得繁琐。因为你必须显式地将数据穿过树的每一层，其中可能包含许多并不真正需要该数据、仅仅充当代理的中间组件。

这个问题通常被称为 **“属性钻取”（prop drilling）问题**。顾名思义，父组件必须将属性一直“钻取”到需要消费它们的子组件。

---

## React 的解决方案：上下文 API

React 解决此问题的方法是引入了**上下文应用程序编程接口（Context API）**。

![](img/0b10f7932db757dcea8fcf01afe6c550_1.png)

上下文提供了一种替代方式，可以在组件树中传递数据，而无需在每一层手动传递 props。当你需要共享可被视为 React 组件树全局状态的数据时，它是合适的工具。

**核心概念公式：**
`Context = 跨组件树的全局数据共享机制`

---

## 实践探索：创建一个上下文

让我们花些时间通过实际操作来研究上下文 API。在这个演示中，我将使用之前通过 Create React App 创建的一个简单应用。

![](img/0b10f7932db757dcea8fcf01afe6c550_3.png)

它代表了一个简单的博客平台，Little Lemon 用它向订阅者发布创新的食谱。它包含一个标题栏，其中有标题和显示在右上角的当前已认证用户。其余部分由页面组件渲染，该组件本身包含用户的博客条目，每个条目都有标题、内容和作者姓名。

请注意，有两个组件需要知道已认证的用户：标题栏内的“已登录用户”组件和页面组件。因为已认证用户属于需要在多个组件间共享的全局数据性质。这是一个清晰的例子，表明上下文是完成这项工作的完美工具。

以下是创建和使用上下文的步骤：

### 第一步：创建上下文对象

首先，需要从 React 导入 `createContext` 函数。这个函数会返回一个新的上下文对象。

```javascript
import { createContext } from 'react';
export const UserContext = createContext(undefined); // 默认值设为 undefined
```

![](img/0b10f7932db757dcea8fcf01afe6c550_5.png)

### 第二步：创建提供者组件

接下来，需要创建一个提供者（Provider）组件。提供者组件允许消费组件订阅上下文的变化。

```javascript
export function UserProvider({ children }) {
  const [user, setUser] = useState(null); // 假设这是认证用户状态

  return (
    <UserContext.Provider value={user}>
      {children}
    </UserContext.Provider>
  );
}
```

`UserContext.Provider` 组件接受一个 `value` 属性，这个值将被传递给该提供者后代的所有消费组件。

### 第三步：包装应用

为了让整个应用感知到这个上下文，需要用提供者组件包装整个应用。

```javascript
// 在应用的根组件（如 App.js）中
import { UserProvider } from './context/UserContext';

function App() {
  return (
    <UserProvider>
      {/* 应用的其他组件 */}
    </UserProvider>
  );
}
```

### 第四步：在组件中消费上下文

最后一步，在需要显示用户名的地方消费用户上下文，即在“已登录用户”组件和页面组件中。

为了方便使用，可以创建一个自定义钩子来包装 `useContext` 钩子。

```javascript
// 自定义钩子
import { useContext } from 'react';
import { UserContext } from './UserContext';

export function useUser() {
  return useContext(UserContext);
}
```

然后在组件中使用这个钩子：

```javascript
// 在需要用户信息的组件中
import { useUser } from './context/UserContext';

function LoggedInUser() {
  const user = useUser(); // 消费上下文
  return <div>User: {user?.name}</div>;
}
```

应用现在成功显示了已认证用户的名称。

---

![](img/0b10f7932db757dcea8fcf01afe6c550_7.png)

## 总结与最佳实践 📝

![](img/0b10f7932db757dcea8fcf01afe6c550_9.png)

本节课中，我们一起学习了 React 上下文的概念、其引入的原因以及如何通过一个实际示例来使用它。

你了解了上下文是用于解决跨组件树共享全局状态数据（如用户主题、区域设置、认证信息）的有效工具，它能避免繁琐的属性钻取问题。

**核心要点总结：**
*   **问题**：跨多层级组件传递相同数据导致“属性钻取”。
*   **解决方案**：使用 React **Context API**。
*   **关键步骤**：`createContext` -> `Provider` -> `useContext`。
*   **适用场景**：真正的**全局状态**共享。

但请记住，尽管上下文对于管理全局状态非常有用，仍然建议你尽可能坚持使用 props 和组件自身状态（state）。这样，你的应用数据流将更容易追踪和理解。上下文应谨慎使用，主要用于那些在组件树中许多不同层级都需要访问的数据。