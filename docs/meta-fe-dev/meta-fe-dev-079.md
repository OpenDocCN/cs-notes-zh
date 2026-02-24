# React JSX 高级模式与测试：P79：37_JSX 和测试模块总结 📚

在本节课中，我们将回顾并总结关于 React JSX 高级模式与测试模块的核心知识。我们将系统梳理从 JSX 基础到组件组合、高级复用模式，再到组件测试的完整学习路径。

你已经完成了 React JSX 高级模式与测试模块的学习。

让我们花几分钟时间来回顾一下到目前为止所学到的内容。

![](img/82bbd898031f1bd6907dfcca54b8d1f0_1.png)

## JSX 深度解析 🧩

![](img/82bbd898031f1bd6907dfcca54b8d1f0_2.png)

你首先深入学习了 JSX。

你了解了组件（Components）和元素（Elements）之间的区别。

![](img/82bbd898031f1bd6907dfcca54b8d1f0_4.png)

![](img/82bbd898031f1bd6907dfcca54b8d1f0_5.png)

你学习了组件是接收数据或属性（props）作为输入，并返回一个元素树作为输出的函数。

```javascript
// 组件示例
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

你还学习了元素只是普通的 JavaScript 对象，它们提供了 DOM 的轻量级表示，并让 React 能够以快速且可预测的方式更新你的用户界面。

![](img/82bbd898031f1bd6907dfcca54b8d1f0_7.png)

```javascript
// React.createElement 创建的元素对象
const element = React.createElement('h1', {className: 'greeting'}, 'Hello, world!');
```

## 组件组合 🧱

![](img/82bbd898031f1bd6907dfcca54b8d1f0_9.png)

接下来，你发现了组件组合的重要性以及 `children` 属性的使用。你被介绍了组件组合的两个主要特性：**容器化（Containment）** 和 **特例化（Specialization）**。

![](img/82bbd898031f1bd6907dfcca54b8d1f0_10.png)

你学习了容器化是一种适用于那些事先不知道其子组件是什么的组件的技术，例如对话框或侧边栏。它使用特殊的 `children` 属性来直接将元素作为其内容传递。

```javascript
// 容器化示例：Dialog 组件
function Dialog(props) {
  return (
    <div className="dialog">
      {props.children}
    </div>
  );
}
```

![](img/82bbd898031f1bd6907dfcca54b8d1f0_12.png)

你也被介绍了特例化，这是一种允许你定义其他组件的特殊用例组件的技术，例如基于一个通用对话框创建一个确认对话框。

![](img/82bbd898031f1bd6907dfcca54b8d1f0_13.png)

```javascript
// 特例化示例：ConfirmationDialog 组件
function ConfirmationDialog(props) {
  return (
    <Dialog>
      <h1>Are you sure?</h1>
      <p>{props.message}</p>
      <button onClick={props.onConfirm}>Yes</button>
      <button onClick={props.onCancel}>No</button>
    </Dialog>
  );
}
```

## 动态操作子元素 ⚙️

然后，你进入了一节关于在 JSX 中动态操作子元素的课程。

在这里，你被介绍了一些新的 React API：`React.cloneElement` 和 `React.Children`。

你学习了 `React.cloneElement` 会克隆并返回一个新元素，允许你直接在 JSX 中操作和转换元素。

```javascript
const newElement = React.cloneElement(oldElement, newProps, ...children);
```

你还学习了 `React.Children.map` 对于子元素操作非常有用，并且当与 `React.cloneElement` 结合使用时，能够为创建灵活的组件提供一个强大的组合模型。

你通过一个实际例子学习了这两个 API，其中实现了一个 `Row` 组件来均匀地分隔其子元素。

![](img/82bbd898031f1bd6907dfcca54b8d1f0_15.png)

![](img/82bbd898031f1bd6907dfcca54b8d1f0_16.png)

## 扩展运算符的应用 🔄

最后，你被介绍了 React 中的扩展运算符。

![](img/82bbd898031f1bd6907dfcca54b8d1f0_18.png)

你学习了扩展运算符在对象中支持两种主要操作：**复制**和**合并**。

```javascript
// 复制对象
const original = { a: 1, b: 2 };
const copy = { ...original };

// 合并对象
const merged = { ...obj1, ...obj2 };
```

![](img/82bbd898031f1bd6907dfcca54b8d1f0_20.png)

![](img/82bbd898031f1bd6907dfcca54b8d1f0_21.png)

然后你看到了 React 如何使用该运算符来展开所有属性，而不是必须手动逐个键入它们。

```javascript
function MyComponent(props) {
  return <ChildComponent {...props} />;
}
```

最后，你看到了一些实际例子，说明了扩展运算符如何允许创建灵活的组件。

## 复用通用行为的高级模式 🧠

接着，你进入了一节关于复用通用行为的高级模式的课程。

该课程首先概述了 React 中的**横切关注点（Cross-Cutting Concerns）**。

你学习了横切关注点指的是与应用程序业务逻辑无关，但在许多地方都需要用到的通用功能，例如错误处理、身份验证或数据获取。

![](img/82bbd898031f1bd6907dfcca54b8d1f0_23.png)

![](img/82bbd898031f1bd6907dfcca54b8d1f0_24.png)

你理解了为什么组件虽然是 React 中代码复用的主要单元，但并不适合封装这类逻辑。

之后，你被介绍了处理横切关注点的两种技术。

你被介绍的第一种技术是**高阶组件（Higher-Order Component， HOC）** 技术，你了解到它为实现横切关注点提供了一个强大的抽象。

```javascript
// HOC 基本结构
const EnhancedComponent = higherOrderComponent(WrappedComponent);
```

你还看到了一个如何使用这种技术来抽象数据获取的示例。

作为关于高阶组件的实践课程的一部分，你学习了高阶组件只是一个接收一个组件并返回一个新组件的函数。

![](img/82bbd898031f1bd6907dfcca54b8d1f0_26.png)

你被介绍了创建高阶组件所需的代码结构，并研究了一个处理屏幕上鼠标指针位置的高阶组件的应用。

![](img/82bbd898031f1bd6907dfcca54b8d1f0_27.png)

然后你学习了第二种处理横切关注点的技术，称为 **Render Props**。

这是一种你添加到组件中的特殊属性，其特点是一个返回 React 元素的函数。

```javascript
<DataProvider render={data => <h1>Hello {data.target}</h1>} />
```

![](img/82bbd898031f1bd6907dfcca54b8d1f0_29.png)

你发现，与高阶组件不同，新的属性是作为函数的参数动态注入的。你通过一个实际例子进行了学习，在该例子中，Render Props 技术被用来抽象从服务器获取数据的功能。

![](img/82bbd898031f1bd6907dfcca54b8d1f0_30.png)

![](img/82bbd898031f1bd6907dfcca54b8d1f0_31.png)

## 使用 React Testing Library 进行组件测试 🧪

该模块以一节关于使用 React Testing Library 进行组件测试的课程结束。

该课程首先全面解释了为什么 React Testing Library 是你测试的推荐工具。

![](img/82bbd898031f1bd6907dfcca54b8d1f0_33.png)

你学习了为了保证你的应用程序按预期工作，一套自动化测试是至关重要的。

你被介绍了测试时的最佳实践，并了解了 React Testing Library 是如何在设计时就考虑了所有这些实践的。

![](img/82bbd898031f1bd6907dfcca54b8d1f0_35.png)

![](img/82bbd898031f1bd6907dfcca54b8d1f0_36.png)

最后，你被介绍了一个使用推荐测试运行器 Jest 和 React Testing Library 的基本测试示例，以说明测试的基本结构。

```javascript
import { render, screen } from '@testing-library/react';
import MyComponent from './MyComponent';

![](img/82bbd898031f1bd6907dfcca54b8d1f0_38.png)

test('renders learn react link', () => {
  render(<MyComponent />);
  const linkElement = screen.getByText(/learn react/i);
  expect(linkElement).toBeInTheDocument();
});
```

关于组件测试的课程以一个真实世界示例中的测试实际应用作为结束。

通过这个例子，你学习了设计良好的测试如何能够捕获代码中的错误，并为你提供修复它们所需的上下文。

你还发现了一个更复杂的应用程序，只需几行代码就可以轻松测试。

然后你被介绍了 React Testing Library 的几个 API，例如用于在全局文档上查询的 `screen`，以及不同的查询类型，例如按文本查询或按角色查询。

最后，你学习了用于你的期望和断言的不同匹配器，例如用于模拟函数的 `toHaveBeenCalled` 和用于元素属性的 `toHaveAttribute`。

## 总结 🎉

本节课中我们一起学习了 React JSX 高级模式与测试模块的核心内容。

![](img/82bbd898031f1bd6907dfcca54b8d1f0_40.png)

我们从 JSX 的本质和组件与元素的区别开始，深入探讨了组件组合的两种主要模式：容器化和特例化。接着，我们学习了如何利用 `React.cloneElement` 和 `React.Children` 动态操作子元素，以及扩展运算符在 React 中的强大应用。

![](img/82bbd898031f1bd6907dfcca54b8d1f0_41.png)

![](img/82bbd898031f1bd6907dfcca54b8d1f0_42.png)

在高级模式部分，我们理解了横切关注点的概念，并掌握了两种复用通用逻辑的强大技术：高阶组件和 Render Props。最后，我们系统学习了如何使用 React Testing Library 和 Jest 为 React 组件编写有效、可维护的测试，包括查询元素、进行断言等关键技能。

![](img/82bbd898031f1bd6907dfcca54b8d1f0_43.png)

![](img/82bbd898031f1bd6907dfcca54b8d1f0_44.png)

恭喜你完成了本模块的学习！现在是时候运用你所学到的一切，去构建一些出色的应用程序了。