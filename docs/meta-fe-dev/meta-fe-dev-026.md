# 26：React 状态管理

在本节课中，我们将要学习如何管理跨多个组件层级的状态。你将理解如何使用 Context API 来更高效地管理状态，并学会使用 `useContext` 和 `useReducer` 这两个钩子进行基本的状态管理。

## 概述：从 Props 到 Context

到目前为止，你可能已经学会了通过使用 **props** 在父组件和子组件之间传递状态的方法。

但是，你是否想过，对于拥有多层组件的更复杂应用，这些方法是否依然适用？

幸运的是，有一些工具可以帮助你做到这一点。通过本视频的学习，你将理解 Context API 如何用于跨多个组件层级更高效地管理状态。

## 为什么需要 Context API？

通过 props 传递状态有助于管理状态，但这就像乘坐公交车，需要在到达终点前经过每一站。

相比之下，使用 Context API 就像瞬间传送到目的地。它是一种绕过在多层组件中冗余传递数据的方式。

记住，API 代表 **应用程序编程接口**。API 提供了一组预定义的方式，让你可以与某些代码进行交互。

因此，Context API 提供了一种在 React 中处理上下文的简化方法。

## 理解 Context API 的核心概念

要设置 Context API，你需要添加一段代码作为你的 **Context Provider**，这也是状态将被存储的地方。

![](img/3ca7ab954781ab3d8e35b50d9b53ae6e_1.png)

当一个组件需要使用状态时，它就成为一个 **Context Consumer**。

**核心代码结构示例：**
```javascript
// 1. 创建 Context
const MyContext = React.createContext();

// 2. 创建 Provider 组件
function MyProvider({ children }) {
  const [state, setState] = useState(initialState);
  return (
    <MyContext.Provider value={{ state, setState }}>
      {children}
    </MyContext.Provider>
  );
}

// 3. 在 Consumer 组件中使用
function MyComponent() {
  const { state } = useContext(MyContext);
  return <div>{state}</div>;
}
```

## 实践：一个使用 Context 的简单应用

现在，让我们分析一个利用 Context API 来控制状态的简单应用。

在我的 `App.js` 文件中，我使用了一些代码作为起始设置。你可以在附加资源中找到这个文件，如果你想用它来练习使用 Context API。

在 App 组件中，我有 `MealsProvider` 和 `MealsList` 的导入语句。

`MealsProvider` 提供上下文状态数据，并将其传递给 App 组件内它所包裹的所有组件。目前，它包裹了两个组件：`MealsList` 组件和 `Counter` 组件，它们位于 return 语句的 div 标签之间。

`MealsProvider` 组件借助 Context API 来组织并持有所有状态。

首先，我使用 `React.createContext()` 函数设置了 `MealsContext` 变量。

接着，我声明了 `today‘sMeals` 数组，其中包含几个保存为字符串的食物项。

然后，我将 `MealsProvider` 编码为一个接受 `children` 值的 ES6 函数。这个 `children` 值包含了当 `MealsProvider` 组件在 App 组件内部渲染时，将被包裹进该组件的一切内容。

`children` 值被包裹在 `<MealsContext.Provider>` JSX 元素中并从 `MealsProvider` 返回。

`<MealsContext.Provider>` JSX 元素带有 `value` 属性，这个属性被赋值为 `meals` 对象，也就是我之前用 `useState` 变量设置的值。

在文件底部导出 `MealsProvider` 组件之前，我还将 `useMealsListContext` 变量设置为 `React.useContext()` 调用，并将 `MealsContext` 作为其唯一参数传入。这使得我可以更容易地从 `useMealsListContext` 变量中解构出 `meals` 对象。

最后，在 `MealsList` 组件中，我通过从 `MealsProvider` 文件导入 `useMealsListContext` 来访问上下文数据。

## 深入分析 MealsList 组件

让我们更详细地分解这个组件的工作原理。

首先，我从 `useMealsListContext` 调用返回的对象中解构出 `meals` 属性。原始对象有一个名为 `meals` 的属性，它保存着一个包含三个餐食字符串的数组。

一旦我从该对象中解构出 `meals` 属性，剩下的就是保存在 `meals` 变量中的三个字符串的数组。这允许我对 `meals` 值进行映射，为 `meals` 数组的每个成员渲染一个 `<h2>` 元素。

这段代码可能比你遇到的大多数代码都要复杂。如果你需要时间来理解它是如何工作的，请不要担心。只需记住重要的一点：这个设置为你使用 Context API 提供了一个很好的起点。

## 查看 Counter 组件

最后，让我们检查一下 `Counter` 组件。

请注意，它获取上下文数据的方式与 `MealsList` 组件相同。这就是拥有一个集中式状态存储的用处。它允许我直接从任何需要状态的组件中获取状态，而无需进行 **prop drilling** 或 **状态提升**。

## 引入 useReducer Hook

接下来，让我向你展示 `useReducer` Hook 是如何工作的。让我们继续学习 `useReducer` Hook。

你可以把它看作是一个功能更强大的 `useState`。`useState` Hook 从一个初始状态开始，而 `useReducer` 除了初始状态外，还会接收一个 **reducer 函数**。

让我用一个代码示例来说明。

假设我有一个 React 应用，代表我钱包里的金额。初始状态是值 100，而“接一个新客户”这个动作会增加这个值，“给车加油”这个动作会减少它。

我应用了一个 **reducer 函数**，它接收 `state` 和 `action`。

与在 `useState` Hook 中使用 `setState` 不同，我使用 `useReducer` Hook 的 `dispatch` 方法。`dispatch` 方法接受一个对象字面量，该对象有一个 `type` 属性，设置为与 `reducer` 函数内部定义的行为相匹配的 `action.type`。

现在，当我在浏览器中与这个应用交互时，我可以通过点击“接一个新客户”按钮来增加金额值，或者通过点击“给车加油”按钮来减少它。

**核心代码示例：**
```javascript
// Reducer 函数
function walletReducer(state, action) {
  switch (action.type) {
    case ‘ADD_CUSTOMER‘:
      return state + 10; // 假设接客户赚10元
    case ‘REFUEL‘:
      return state - 20; // 假设加油花20元
    default:
      return state;
  }
}

// 在组件中使用
function WalletApp() {
  const [money, dispatch] = useReducer(walletReducer, 100);
  return (
    <div>
      <p>钱包余额：{money}</p>
      <button onClick={() => dispatch({ type: ‘ADD_CUSTOMER‘ })}>
        接一个新客户
      </button>
      <button onClick={() => dispatch({ type: ‘REFUEL‘ })}>
        给车加油
      </button>
    </div>
  );
}
```

## 总结

在本节课中，我们一起学习了 `useContext` 和 `useReducer` 这两个 Hook 如何用于跨多个组件层级更高效地管理状态。

*   **Context API** 提供了一种在组件树中共享数据的直接方式，避免了逐层传递 props 的繁琐。
*   **`useContext`** Hook 允许函数式组件订阅 React 上下文，从而轻松访问全局或共享状态。
*   **`useReducer`** Hook 则为管理更复杂的状态逻辑提供了方案，它通过一个纯函数（reducer）来根据不同的动作（action）更新状态。

![](img/3ca7ab954781ab3d8e35b50d9b53ae6e_3.png)

通过结合使用这些工具，你可以构建出状态管理更清晰、组件间通信更高效的 React 应用程序。