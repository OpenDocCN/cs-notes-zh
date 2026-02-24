# React 前端开发：模块总结：React 钩子与自定义钩子 🎯

在本模块中，我们深入学习了 React 钩子和自定义钩子。我们探讨了许多重要的概念和实际应用，这些知识将帮助你在后续课程中更好地进行前端开发。现在，让我们来回顾一下你所学到的关键知识和技能。

## 第一课：useState 钩子

上一节我们介绍了模块概述，本节中我们来看看第一个核心钩子：`useState`。它用于在 React 函数组件中管理状态。

你学习了如何使用 `useState` 钩子进行数组解构，以及如何通过状态更新函数来更新状态。我们还探讨了如何响应用户事件（如按钮点击）来改变状态。通过一个详细的演示，你掌握了在组件内声明、读取和更新状态的方法。

**核心概念代码示例：**
```javascript
const [state, setState] = useState(initialState);
```

完成本课学习后，你现在应该能更好地在 React 中处理组件状态了。

## 第二课：useEffect 钩子与副作用

在掌握了状态管理后，本节我们将关注另一个重要概念：副作用，以及与之相关的 `useEffect` 钩子。

你了解到副作用会使函数变得“不纯”，这些不纯函数会执行诸如调用 `console.log`、`fetch` 或浏览器的地理位置功能等操作。除了理论学习，你还通过实践演示学习了如何在函数组件中使用 `useEffect` 钩子来执行副作用，以及如何使用依赖数组来控制 `useEffect` 函数的执行时机。

需要记住的是，依赖数组决定了 `useEffect` 钩子何时被调用。

**核心概念公式：**
`useEffect(effectFunction, dependencyArray)`

## 第三课：钩子规则与数据获取

在学习了两个核心钩子后，本节我们将了解使用钩子时必须遵守的规则，以及如何从网络获取数据。

首先，你学习了 React 中钩子的使用规则并理解了它们。这些规则是：
*   只能在 React 组件函数中调用钩子。
*   必须在 React 组件函数的顶层调用钩子。
*   可以在一个组件内调用多个状态钩子或副作用钩子。
*   应保证多次钩子调用的顺序一致。

![](img/c77bf2176c6aa3c273d03af75a02e75a_1.png)

以下是关于 `fetch` 函数的内容。你学习了 JavaScript 中被称为“异步 JavaScript”的职责委托机制。`fetch` 函数本身看起来是 JavaScript 的一部分，但实际上它是从 JavaScript 调用浏览器 API 的一种方式。这引出了使用状态和副作用钩子获取数据的课程。你通过一个演示，学习了如何使用 `fetch` API 在 React 中从网络获取数据。

**核心概念代码示例：**
```javascript
fetch(url)
  .then(response => response.json())
  .then(data => setState(data));
```

完成本课后，你应该更深入地理解了如果开发者不遵守 React 钩子规则会发生什么，并且能够描述在 JavaScript 和 React 中是如何获取数据的。

![](img/c77bf2176c6aa3c273d03af75a02e75a_3.png)

## 第四课：useReducer 钩子与自定义钩子

在掌握了基础钩子之后，本节我们将探索更高级的状态管理钩子 `useReducer`，并学习创建自定义钩子。

你学习了 `useReducer` 钩子，它与 `useState` 的不同之处在于，除了初始状态外，它还需要一个 `reducer` 函数。你了解到在 `useState` 效率低下的情况下可以使用 `useReducer`，例如当你拥有复杂的状态逻辑时，并学习了如何在代码中实现 `useReducer` 钩子。

**核心概念代码示例：**
```javascript
const [state, dispatch] = useReducer(reducer, initialState);
```

此外，你还接触了 `refs` 的概念，了解了它们如何用于超越虚拟 DOM 并访问底层 DOM 元素及其他应用。你也有机会探索如何编写自己的自定义钩子。

![](img/c77bf2176c6aa3c273d03af75a02e75a_5.png)

**核心概念代码示例：**
```javascript
function useCustomHook() {
  // 钩子逻辑
  return value;
}
```

完成本课后，你应该能够使用 `useReducer` 钩子来跟踪状态，并在你的 React 应用中创建自己的自定义钩子。

![](img/c77bf2176c6aa3c273d03af75a02e75a_7.png)

## 总结与展望 🚀

在本节课中，我们一起学习了 React 钩子的核心知识。你取得了出色的进展，现在对使用钩子已经有了扎实的掌握。

接下来，是时候深入探讨 JSX 了，我期待在下一个模块中继续指导你。