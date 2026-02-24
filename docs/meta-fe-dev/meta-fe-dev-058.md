# 58：使用 useState 钩子构建目标追踪应用 🎯

在本节课中，我们将学习如何使用 React 的 `useState` 钩子来构建一个简单的目标追踪应用。我们将通过一个“小柠檬餐厅”的业务目标管理示例，理解如何在组件中声明、读取和更新状态。

![](img/852151f16378a2b3e697d5f6ec1b34eb_1.png)

想象一下，在小柠檬餐厅的早期阶段，餐厅还只存在于纸面上。店主希望有一个应用来追踪餐厅业务的发展和所有相关目标的达成情况。让我们探索如何使用 React 的 `useState` 钩子在组件中构建并更新状态，以满足这些需求。

![](img/852151f16378a2b3e697d5f6ec1b34eb_1.png)

当代码编译完成后，屏幕上会显示完整的应用。我们得到一个标题为“我的小柠檬目标”的页面，以及一个包含两个输入框的简单表单：`goal` 和 `by`。第一个输入框让店主输入他们的目标，第二个输入框让他们输入达成该目标的时间框架。

代码本身由三个独立的组件构成：
*   `GoalForm` 组件：通过表单捕获新目标。
*   `ListOfGoals` 组件：遍历所有已添加的目标，并将它们显示为一个无序列表。
*   `App` 组件：将上述两个组件组合在一起，渲染它们，并通过 `props` 传递它们需要使用的函数。

![](img/852151f16378a2b3e697d5f6ec1b34eb_3.png)
![](img/852151f16378a2b3e697d5f6ec1b34eb_4.png)

![](img/852151f16378a2b3e697d5f6ec1b34eb_3.png)

![](img/852151f16378a2b3e697d5f6ec1b34eb_4.png)

让我们深入探索这些组件。

## 分析 GoalForm 组件

第一个组件是 `GoalForm` 组件，它在函数体中接收 `props` 对象。

在 `GoalForm` 函数体内，我首先声明了一个状态变量 `formData`，它通过解构调用 `useState` 钩子得到。我将这个 `formData` 变量初始化为一个包含两个属性的对象：`goal` 和 `by`，它们的值都设置为空字符串。

```javascript
const [formData, setFormData] = useState({ goal: '', by: '' });
```

接下来，我声明了两个函数：`changeHandler` 和 `submitHandler`。

首先是 `changeHandler` 函数，它接受一个参数 `e`。这个 `e` 参数是一个现成的事件对象。换句话说，我不需要在我的 `changeHandler` 中传递这个对象，它是由 React 之外的机制提供的。即使在普通的 JavaScript 中，每当事件被触发时，也会创建一个包含许多与该事件相关数据的事件对象。然后，我可以通过简单地为其分配一个自定义名称（例如 `e`、`evt` 或 `event`）来使用这个事件对象。这里我使用字母 `e` 来保持代码简洁。

在 `changeHandler` 函数体内，我通过调用之前从 `useState` 钩子解构出来的状态设置函数 `setFormData` 来更新 `formData` 变量的状态。

`setFormData` 函数接收 `formData` 变量前一个值的浅拷贝（即前面使用了扩展运算符的 `formData` 变量）。

```javascript
const changeHandler = (e) => {
    setFormData({ ...formData, [e.target.name]: e.target.value });
};
```

请记住，你不应该直接操作 `formData` 变量，这就是我制作副本的原因。这是因为 React 优化其虚拟 DOM 的方式。保持状态不可变使得能够更高效、更具成本效益地比较虚拟 DOM 的先前版本和更新后的版本。

然后，我通过添加这段代码来更新这个新的 `formData` 对象副本：它读取 `e.target.name` 并使用方括号表示法，然后将此属性的值设置为事件对象实例中 `e.target.value` 属性内的任何内容（该事件对象是在该特定事件触发时构建的）。

之所以使用方括号表示法有效，是因为它允许我动态地设置 `e.target.name` 的值。换句话说，如果用户在 `name` 属性设置为 `goal` 的输入框中键入，它允许我将其设置为 `goal`；如果用户在 `name` 属性设置为 `by` 的输入框中键入，则将其设置为 `by`。

其次，我声明了一个 `submitHandler` 函数，它也接受 `event` 参数。

`GoalForm` 组件接收名为 `onAdd` 的 prop，我将 `addGoal` 函数作为 prop 值传递给它。但这不仅仅是任何函数，它实际上是在 App 组件内部第 43 行声明的函数。

这个 `addGoal` 函数接受一个目标条目，并更新保存在 App 函数内部的 `allGoals` 状态变量的值。它通过将这个目标条目添加到 App 组件的 `allGoals` 状态变量中保存和跟踪的先前目标列表中来做到这一点。

任何状态变量的更新都必须通过之前解构的状态更新函数进行。对于 App 组件，状态更新函数是 `setAllGoals` 函数。这就是为什么我在 `addGoal` 函数内部调用这个状态更新函数。

为了使一切正常工作，我还需要将 `addGoal` 函数定义传递给 App 组件返回语句中的 `GoalForm` JSX 元素。这就是为什么 `addGoal` 函数现在可以作为名为 `onAdd` 的 prop 在 `GoalForm` 函数内部使用，也是为什么我现在可以在第 10 行开始的 `submitHandler` 函数内部使用它。

因此，一旦在这里第 12 行调用 `props.onAdd` 函数，我就会回到 `GoalForm` 函数声明中。它接收 `formData` 变量，这会触发 App 组件中 `allGoals` 状态变量的更新，如前所述。

但现在我仍然需要处理表单显示用户输入的值的问题。我需要将 `formData` 状态变量重置为空字符串，既重置 `formData` 状态对象的 `goal` 属性，也重置其 `by` 属性。

```javascript
const submitHandler = (e) => {
    e.preventDefault();
    props.onAdd(formData);
    setFormData({ goal: '', by: '' });
};
```

现在，我来到了 `GoalForm` 函数的返回语句。在这里，我希望你关注 `form` 元素，它的 `onSubmit` 事件处理属性被设置为 `submitHandler` 函数。

第一个和第二个输入框都遵循相同的结构，具有 `type`、`name`、`placeholder`、`value` 和 `onChange` 属性，这些属性连接到了前面描述的功能。

## 分析 ListOfGoals 组件

接下来看 `ListOfGoals` 组件，该组件从其父组件 App 接收 `allGoals` 状态变量作为 prop。

这样做的目的是映射 `allGoals` 对象数组，其中每个对象都包含描述单个目标的两个属性，如前所述。通过映射 `allGoals` 对象数组，我现在输出这个无序列表，为每个单独的目标提供一个列表项条目。

## 总结

在本节课中，我们一起学习了在 React 组件中使用 `useState` 钩子，包括如何声明、读取和更新状态。通过编码实现一个 React 目标应用，你应该对在组件内使用 `useState` 钩子有了更深入的了解。

![](img/852151f16378a2b3e697d5f6ec1b34eb_6.png)

![](img/852151f16378a2b3e697d5f6ec1b34eb_6.png)