# React 条件渲染教程：P32：31_单视图条件更新 🎬

在本节课中，我们将学习如何在 React 中根据特定条件来渲染不同的内容。我们将重点介绍两种核心方法：`if` 语句和三元运算符，并通过一个动态显示工作日问候和早餐提醒的小应用来实践。

![](img/d6ff4de32a607e1df57a0ffeb620bb97_1.png)

---

## 项目目标与初始化 🎯

上一节我们介绍了条件渲染的概念，本节中我们来看看如何具体实现。本应用的目标是：利用本地计算机的时间，根据不同的返回值，在同一个 `return` 语句中输出各种动态消息，所有内容都包裹在一个 `div` 元素内。

具体来说，我们将编写一个应用，为工作日显示特定消息。如果是上午，还会询问用户是否吃过早餐。

首先，我使用 Create React App 来构建一个初始的 React 应用。我将通过这个定制化的启动应用中的代码，来演示一些条件渲染的实践。

## 核心逻辑：变量声明与条件判断 ⚙️

以下是应用组件的核心代码逻辑。我们首先声明几个变量来获取和处理时间信息。

```javascript
// 获取当前时间
const time = new Date();

// 获取当前是星期几（长格式，如“Monday”）
const day = time.toLocaleString('en-US', { weekday: 'long' });

// 判断当前是否为上午（6点至12点之间）
const morning = time.getHours() >= 6 && time.getHours() <= 12;

// 声明一个变量用于存储动态消息，初始不赋值
let dayMessage;
```

接下来，我们使用 `if` 语句来根据 `day` 变量的值，为 `dayMessage` 变量赋予不同的字符串内容。

```javascript
// 根据星期几生成不同的消息
if (day.toLowerCase() === 'monday') {
  dayMessage = 'Happy Monday.';
} else if (day.toLowerCase() === 'tuesday') {
  dayMessage = 'Tuesday, four days to go.';
} else if (day.toLowerCase() === 'wednesday') {
  dayMessage = 'Halfway there.';
} else if (day.toLowerCase() === 'thursday') {
  dayMessage = 'Thursday is the new Friday.';
} else if (day.toLowerCase() === 'friday') {
  dayMessage = 'Weekend is coming!';
} else {
  // 对于周末或其他情况
  dayMessage = 'Stay calm and keep having fun.';
}
```

## 在 JSX 中进行条件渲染 ✨

现在，我们进入 `return` 语句部分。在这里，我们将之前定义的变量和条件逻辑整合到 JSX 中，实现最终渲染。

在 `return` 语句中，我们有一个主标题 `h1`，用于显示 `dayMessage` 变量的内容。此外，我们使用**三元运算符**来条件性地评估 `morning` 变量。

```javascript
return (
  <div>
    <h1>{dayMessage}</h1>
    {
      morning ? <h2>Have you had breakfast yet?</h2> : ''
    }
  </div>
);
```

**三元运算符**的语法结构如下：
`条件 ? 条件为真时渲染的内容 : 条件为假时渲染的内容`

在这个例子中，如果 `morning` 为 `true`，则渲染一个包含“Have you had breakfast yet?”的 `h2` 元素；如果为 `false`，则渲染一个空字符串。

## 运行结果与动态验证 📱

![](img/d6ff4de32a607e1df57a0ffeb620bb97_3.png)

运行上述代码，输出结果会根据当前时间和星期几动态变化。

例如，在星期一上午，你可能会看到：
```
Happy Monday.
Have you had breakfast yet?
```

如果将代码中判断上午的时间上限从 `12` 改为 `19` 并保存，那么在下午时段，“Have you had breakfast yet?”这条消息将不再显示。这证明了我们的条件渲染逻辑是有效的。

## 关键要点总结 📝

本节课中我们一起学习了 React 中条件渲染的两种主要方法：
1.  使用 **`if` 语句** 在渲染逻辑之外进行复杂的条件判断和变量赋值。
2.  使用 **三元运算符** 在 JSX 内部简洁地进行内联条件渲染。

![](img/d6ff4de32a607e1df57a0ffeb620bb97_5.png)

通过结合这两种方法，我们可以构建出能够根据状态（如时间）动态显示不同内容的 React 组件，这大大增强了用户界面的交互性和灵活性。