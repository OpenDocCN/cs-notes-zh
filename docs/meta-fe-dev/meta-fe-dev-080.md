# 80：38_高级React课程回顾 📚

在本节课中，我们将一起回顾整个高级React课程的核心内容。我们将梳理从项目初始化到高级概念的所有关键知识点，帮助你巩固所学，为接下来的综合评估做好准备。

## 概述

本课程涵盖了React的高级主题，包括组件渲染、状态管理、Hooks、JSX深入以及测试。通过回顾，我们将串联起各个模块的知识点，构建完整的知识体系。

## 模块一：组件与数据管理

在开篇模块中，你首先对课程有了整体了解。在第一课中，你学习了如何设置VS Code项目，并掌握了如何高效利用课程内容以确保达成学习目标。

### 列表渲染与表单

接着，你进入了下一课，学习如何在React中渲染列表。在这一课中，你掌握了如何转换和渲染列表组件，创建基础列表组件，并理解了React列表组件中**键（Keys）** 的重要性。

在随后的课程中，你深入探索了React中的表单。首先，你学习了**受控组件**与**非受控组件**的区别。接着，你发现了如何在React中创建受控表单组件，并通过创建自己的注册表单来测试所学技能。

以下是受控组件的基本代码结构示例：
```jsx
function ControlledForm() {
  const [value, setValue] = useState('');
  const handleChange = (event) => setValue(event.target.value);
  return <input type="text" value={value} onChange={handleChange} />;
}
```

### React Context

在模块一的最后一课，你学习了React Context。你探索了Props和State，以及它们与Context的关系。你也学习了Context如何触发重新渲染，并应用这些知识创建了一个**明暗主题切换器**。

## 模块二：深入Hooks

接下来，你开始了第二个模块的学习，该模块涵盖了React中所有常见的Hooks以及如何构建自定义Hooks。

### Hooks基础

在本模块的第一课，你开始了Hooks的学习。你学习了如何实现**useState** Hook来处理复杂数据，并应用这些知识来管理组件内部的状态。你也了解了副作用和**useEffect** Hook。

### Hooks规则与数据获取

![](img/bf4be23a3d5bcb9b9fe83cf114f47b89_1.png)

在下一课中，你继续学习了Hooks的规则以及如何使用Hooks获取数据。你发现了Hooks的基本规则，以及如何在你的解决方案中有效地使用它们。

![](img/bf4be23a3d5bcb9b9fe83cf114f47b89_2.png)

你还深入了解了如何使用Hooks获取数据，并在一个实践练习中测试了你的数据获取技能。

### 高级Hooks

在本模块的最后一课，你通过高级Hooks提升了知识和技能。你学习了**useReducer** Hook的好处，它与useState的区别，以及如何使用**useRef**访问底层DOM。

接着，你构建了自己的自定义Hook：**usePrevious**。

![](img/bf4be23a3d5bcb9b9fe83cf114f47b89_4.png)

以下是自定义Hook `usePrevious` 的一个简单实现示例：
```jsx
function usePrevious(value) {
  const ref = useRef();
  useEffect(() => {
    ref.current = value;
  });
  return ref.current;
}
```

## 模块三：JSX深入与测试

![](img/bf4be23a3d5bcb9b9fe83cf114f47b89_6.png)

在第三个模块中，你更详细地探索了JSX以及如何测试你的解决方案。

### JSX深度解析

在第一课中，你深入研究了JSX。你对JSX组件和元素有了更详细的概述。

接着，你探索了使用`children`进行组件组合的两个关键特性：**容器化（Containment）** 和**特例化（Specialization）**，以及如何在JSX中动态操作子元素。在构建一个单选按钮组组件时，你有机会应用新技能，并了解了JSX中的**扩展属性（Spread Attributes）**。

### 行为复用

在下一课中，你专注于行为复用。你学习了React中的**横切关注点（Cross-Cutting Concerns）**，探索了**高阶组件（HOC）** 及其如何被高效使用。你也学习了一个特定的HOC模式，称为**Render Props**，并使用Render Props在一个解决方案中实现了滚动位置跟踪。

### 集成测试

在本模块的最后一课，你被介绍了使用React Testing Library进行集成测试。你发现了Jest和React Testing Library，为一个表单编写了测试场景，并了解了**持续集成（CI）**。

## 总结

![](img/bf4be23a3d5bcb9b9fe83cf114f47b89_8.png)

本节课中，我们一起回顾了整个高级React课程的核心旅程。我们从项目搭建和基础组件渲染开始，逐步深入到状态管理、高级Hooks、JSX的灵活运用以及应用测试。每个模块都构建在前一个模块的基础上，旨在让你能够构建更健壮、可维护的React应用。

你已经到达本课程回顾的终点，现在是时候在综合分级评估中尝试运用你所学的知识了。祝你成功！🚀