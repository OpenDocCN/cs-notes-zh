# Web开发快速入门：2.3：React组件生命周期与Hooks 🧬

![](img/51598ece4900c0b029304f4fb6dc1a61_1.png)

在本节课中，我们将要学习React组件的生命周期，以及如何使用`useEffect`这个重要的Hook。理解这些概念对于构建动态、响应式的Web应用至关重要。

## 组件拆分原则回顾

![](img/51598ece4900c0b029304f4fb6dc1a61_3.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_5.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_6.png)

上一节我们介绍了组件的基础概念，本节中我们来看看如何合理地拆分组件。将大型组件拆分为更小的组件主要有三个原因：

![](img/51598ece4900c0b029304f4fb6dc1a61_8.png)

以下是拆分组件的三个主要动机：
1.  **代码可读性与维护性**：当一个组件的代码过长、难以阅读时，将其拆分有助于在大型代码库中协作和追踪变更。
2.  **功能分离**：当UI的不同部分承担不同的功能职责时（例如，导航栏和帖子内容），应将它们拆分为独立的组件。
3.  **单一职责**：如果一个组件处理了过多不同的任务，为了代码清晰，应将其拆分为多个各司其职的组件。

![](img/51598ece4900c0b029304f4fb6dc1a61_10.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_12.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_14.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_15.png)

最终，如何设计组件树取决于开发者自身，这需要通过实践和参考优秀代码来积累经验。

![](img/51598ece4900c0b029304f4fb6dc1a61_17.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_19.png)

## State与Props的核心概念

State和Props是React中数据流动的基石。

![](img/51598ece4900c0b029304f4fb6dc1a61_21.png)

*   **State（状态）**：由组件自身维护的一块“记忆”数据，在多次渲染间持续存在。它是可变的，只能通过调用`useState`返回的setter函数来更新。State使我们能够控制应用显示的内容并存储数据。
    *   **创建State**：`const [value, setValue] = useState(initialValue);`
*   **Props（属性）**：从父组件传递给子组件的数据，类似于函数的参数。它们是**只读的**，只有当父组件的状态更新并重新传递给子组件时，子组件的Props才会改变。

![](img/51598ece4900c0b029304f4fb6dc1a61_23.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_25.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_27.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_29.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_30.png)

在更新数组或对象类型的State时，我们通常使用扩展运算符（`...`）来创建一个新的引用，而不是直接修改原State。

![](img/51598ece4900c0b029304f4fb6dc1a61_32.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_34.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_36.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_37.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_39.png)

## 状态提升（Lifting State Up）

![](img/51598ece4900c0b029304f4fb6dc1a61_41.png)

当多个子组件需要共享或同步状态时，一个常见的设计模式是“状态提升”。

![](img/51598ece4900c0b029304f4fb6dc1a61_43.png)

考虑一个包含标签页（Tabs）和内容面板（Tweet Panel）的Feed组件。如果每个组件内部都有自己的状态（如`selectedTab`和`contentType`），那么切换标签页时，内容面板无法自动感知。

![](img/51598ece4900c0b029304f4fb6dc1a61_45.png)

**解决方案**：将相关的状态（`selectedTab`）提升到它们共同的父组件（Feed）中。然后，父组件通过Props将状态值和更新状态的函数传递给子组件。

![](img/51598ece4900c0b029304f4fb6dc1a61_47.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_49.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_51.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_52.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_53.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_54.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_55.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_56.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_58.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_60.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_62.png)

**核心原则**：如果多个子组件需要交互或共享状态，应将该状态提升到它们最近的共同祖先组件中。子组件之间无法直接共享状态，必须通过父组件传递。

## 组件生命周期详解

![](img/51598ece4900c0b029304f4fb6dc1a61_64.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_66.png)

一个React组件的生命周期包含三个阶段：挂载（Mounting）、更新（Updating）和卸载（Unmounting）。每个阶段都伴随着“触发（Trigger） -> 渲染（Render） -> 提交（Commit）”的流程。

![](img/51598ece4900c0b029304f4fb6dc1a61_68.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_70.png)

1.  **挂载（Mounting）**：组件首次被创建并插入DOM中。
    *   **触发**：组件首次渲染。
    *   **渲染**：执行组件函数内的所有JavaScript逻辑（`useState`, `useEffect`等），并计算返回的JSX。
    *   **提交**：React将计算出的JSX更新到浏览器的真实DOM中，用户此时可以看到UI。

![](img/51598ece4900c0b029304f4fb6dc1a61_72.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_74.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_76.png)

2.  **更新（Updating）**：组件因状态或Props改变而重新渲染。
    *   **触发**：组件的State改变，或其接收的Props改变，或其祖先组件重新渲染。
    *   **渲染与提交**：与挂载阶段类似，重新执行组件函数并更新DOM。React会通过“虚拟DOM对比（Diffing）”高效地只更新发生变化的部分。

3.  **卸载（Unmounting）**：组件从DOM中被移除。

![](img/51598ece4900c0b029304f4fb6dc1a61_78.png)

**常见触发条件**：
*   组件**自身State**改变。
*   组件接收的**Props**改变。
*   组件的**祖先组件**重新渲染（会导致所有后代组件重新渲染，后续会学习优化方法）。

![](img/51598ece4900c0b029304f4fb6dc1a61_80.png)

## 深入useEffect Hook

`useState`用于管理状态并触发重新渲染，但有时我们需要在状态变化后执行一些“副作用”操作，例如数据获取、订阅或手动修改DOM。这时就需要`useEffect`。

**基本语法**：`useEffect(callbackFunction, [dependencyArray])`

`useEffect`根据依赖数组的不同，有三种主要使用方式：

以下是`useEffect`的三种常见用法：
1.  **在每次渲染后执行**：`useEffect(() => { console.log('Rendered!'); });` （无依赖数组）
2.  **仅在挂载时执行一次**：`useEffect(() => { console.log('Mounted!'); }, []);` （空依赖数组）
3.  **在特定依赖变化后执行**：`useEffect(() => { console.log('Value changed:', value); }, [value]);` （包含依赖的数组）

**清理函数（Cleanup）**：如果`useEffect`的回调函数返回一个函数，那么这个返回的函数会在组件**卸载前**或**依赖项变化导致该`useEffect`重新执行前**被调用，用于清理资源（如取消订阅、清除定时器）。
```javascript
useEffect(() => {
  const timer = setInterval(() => { /* ... */ }, 1000);
  // 清理函数
  return () => clearInterval(timer);
}, []);
```

## 常见JSX模式

在编写组件时，我们经常用到以下两种模式：

*   **条件渲染（Conditional Rendering）**：使用三元运算符根据条件决定渲染内容。
    ```javascript
    return (
      <div>
        {isLoading ? <Spinner /> : <Content data={data} />}
      </div>
    );
    ```

![](img/51598ece4900c0b029304f4fb6dc1a61_82.png)

*   **列表渲染（List Rendering）**：使用`map`函数将数据数组渲染为JSX元素数组。为每个元素提供一个稳定的`key`属性有助于React优化渲染性能。
    ```javascript
    return (
      <ul>
        {items.map((item) => (
          <li key={item.id}>{item.name}</li>
        ))}
      </ul>
    );
    ```

![](img/51598ece4900c0b029304f4fb6dc1a61_84.png)

## 实战：创建一个计时器

![](img/51598ece4900c0b029304f4fb6dc1a61_86.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_87.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_89.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_90.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_92.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_94.png)

让我们综合运用所学知识，创建一个简单的计时器组件。

1.  **创建状态**：使用`useState`来存储当前时间。
    ```javascript
    const [time, setTime] = useState(0);
    ```
2.  **使用副作用更新状态**：使用`useEffect`在组件挂载后，每秒更新一次时间。
    ```javascript
    useEffect(() => {
      const intervalId = setInterval(() => {
        setTime(prevTime => prevTime + 1); // 使用函数式更新确保拿到最新值
      }, 1000);
      // 清理函数：在组件卸载时清除定时器
      return () => clearInterval(intervalId);
    }, []); // 空依赖数组，确保effect只运行一次
    ```
3.  **渲染状态**：在JSX中显示时间。
    ```javascript
    return <div>Time: {time} seconds</div>;
    ```

这个例子完整展示了State管理、生命周期（挂载、更新、卸载）以及`useEffect`（包含清理函数）的协同工作。

![](img/51598ece4900c0b029304f4fb6dc1a61_96.png)

![](img/51598ece4900c0b029304f4fb6dc1a61_97.png)

---

![](img/51598ece4900c0b029304f4fb6dc1a61_99.png)

本节课中我们一起学习了React组件的完整生命周期（挂载、更新、卸载），深入理解了`useEffect` Hook的用法及其在管理副作用中的核心作用，并掌握了状态提升、条件渲染和列表渲染等关键开发模式。这些概念是构建复杂、交互式React应用的坚实基础。