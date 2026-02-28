# 018：Catbook调试挑战第二部分解答 🐛

![](img/59b851fc2f436f46308824236ea1995b_0.png)

在本节课中，我们将一起解决Catbook应用中的一系列前端Bug。我们将学习如何识别和修复React组件中的语法错误、路由问题、数据传递失败以及API请求发送错误。通过逐步调试，你将理解如何追踪数据流和修复常见的Web开发问题。

---

![](img/59b851fc2f436f46308824236ea1995b_2.png)

![](img/59b851fc2f436f46308824236ea1995b_4.png)

## 修复JSX语法错误

![](img/59b851fc2f436f46308824236ea1995b_6.png)

上一节我们遇到了一个JSX语法错误。本节中我们来看看如何修复它。

错误信息指出“JSX值应为表达式或引用的JSX文本”。问题出现在`profile.jsx`文件中，具体是在渲染`CatHappiness`组件时。

```jsx
// 错误示例：缺少花括号包裹JavaScript表达式
<CatHappiness catHappiness=catHappiness />
```

在JSX中，当我们需要将JavaScript变量或表达式作为属性值传递给组件时，必须用花括号`{}`将其包裹。`catHappiness`是一个定义在`Profile`组件内部的React状态变量，我们需要将其值传递给`CatHappiness`组件的同名属性。

![](img/59b851fc2f436f46308824236ea1995b_8.png)

![](img/59b851fc2f436f46308824236ea1995b_10.png)

```jsx
// 正确示例：使用花括号包裹JavaScript表达式
<CatHappiness catHappiness={catHappiness} />
```

这样，`catHappiness`状态的值（一个数字，如0, 1, 2, 3）就会被正确地计算并传递给子组件。

![](img/59b851fc2f436f46308824236ea1995b_12.png)

---

## 修复导航栏路由

修复语法错误后，我们发现无法通过导航栏进入个人资料页面。让我们检查导航栏的代码。

![](img/59b851fc2f436f46308824236ea1995b_14.png)

问题在于导航栏中指向个人资料页面的链接没有设置正确的目标路径。

![](img/59b851fc2f436f46308824236ea1995b_16.png)

```jsx
// 错误示例：链接缺少目标路径
<Link>Profile</Link>
```

![](img/59b851fc2f436f46308824236ea1995b_18.png)

`Link`组件需要`to`属性来指定导航目标。主页链接指向`/`，个人资料页链接应指向`/profile`。

```jsx
// 正确示例：指定to属性
<Link to=“/profile”>Profile</Link>
```

点击此链接会将URL更改为`/profile`。然后，在`index.jsx`中定义的路由逻辑会读取当前URL，并决定渲染`Profile`组件。

![](img/59b851fc2f436f46308824236ea1995b_20.png)

---

## 修复动态内容显示

现在我们可以进入个人资料页了，但发现动态内容（如故事正文）无法显示。我们需要追踪数据是如何传递的。

故事数据从`Feed`组件开始，通过`Card`组件，最终到达`SingleStory`组件进行渲染。问题很可能出在数据传递链的某个环节。

检查`Feed.jsx`，我们发现它在渲染`Card`组件时，只传递了`key`、`id`和`creatorName`属性，但没有传递关键的`content`属性。

![](img/59b851fc2f436f46308824236ea1995b_22.png)

```jsx
// 错误示例：未传递content属性
<Card key={story.id} id={story.id} creatorName={story.creatorName} />
```

![](img/59b851fc2f436f46308824236ea1995b_24.png)

`Feed`组件通过`map`函数遍历一个故事对象数组。每个故事对象都包含`content`字段。我们需要将这个字段也传递给`Card`组件。

```jsx
// 正确示例：传递所有必要属性
<Card key={story.id} id={story.id} creatorName={story.creatorName} content={story.content} />
```

这样，`content`数据就会沿着组件树向下传递，最终在`SingleStory`组件中显示出来。

---

## 修复发布新故事功能

接下来，我们发现发布新故事的功能有问题：故事能发布，但内容为空。这表明前端发送的请求体中缺少内容数据。

![](img/59b851fc2f436f46308824236ea1995b_26.png)

我们需要同时检查前端发送请求的代码和后端接收请求的代码。

在前端`Feed.jsx`中，我们找到了`addNewStory`函数，它负责发送POST请求到`/api/story`。但是，查看调用这个函数的地方（在`NewPostInput`组件中），我们发现调用时没有传入任何参数。

```jsx
// 错误示例：调用函数时未传递参数
addNewStory();
```

为了创建一个新故事，我们需要向服务器发送一个包含故事信息（如`id`、`creatorName`、`content`）的对象。`addNewStory`函数应该接收这个对象作为参数。

在`NewPostInput`组件中，用户输入的内容存储在组件的状态`value`中。当用户提交时，我们应该调用`addNewStory`并传入一个包含所有必要信息的新故事对象。

```jsx
// 正确示例：构造故事对象并传递给函数
const newStory = {
  id: id, // 假设id已定义
  creatorName: “anonymousUser”, // 或从状态获取
  content: value // 用户输入的内容
};
addNewStory(newStory);
```

同时，需要确保`Feed.jsx`中的`addNewStory`函数正确地接收这个参数并将其作为请求体发送。

```jsx
const addNewStory = (storyData) => {
  fetch(“/api/story”, {
    method: “POST”,
    headers: { “Content-Type”: “application/json” },
    body: JSON.stringify(storyData) // 将故事对象转换为JSON字符串
  })
  .then(...)
}
```

![](img/59b851fc2f436f46308824236ea1995b_28.png)

---

## 修复发布新评论功能

最后，我们发现发布新评论的功能完全失效。打开浏览器开发者工具的“网络”选项卡，发现点击提交后根本没有POST请求发出。这说明问题出在前端，函数可能没有被正确调用。

我们沿着组件树追踪`addNewComment`函数的传递路径：从`Card`传到`CommentsBlock`，再传到`NewPostInput`组件。

![](img/59b851fc2f436f46308824236ea1995b_30.png)

在`NewPostInput`组件中，我们接收到了一个名为`addNewComment`的属性（prop）。然而，这个组件需要一个名为`onSubmit`的属性来指定提交按钮被点击时的回调函数。当前的代码没有将`addNewComment`函数赋值给`onSubmit`属性。

![](img/59b851fc2f436f46308824236ea1995b_32.png)

```jsx
// 错误示例：NewPostInput组件缺少onSubmit处理函数
<NewPostInput />
```

![](img/59b851fc2f436f46308824236ea1995b_34.png)

我们需要将`addNewComment`函数作为`onSubmit`属性传递给`NewPostInput`组件。

![](img/59b851fc2f436f46308824236ea1995b_36.png)

```jsx
// 正确示例：传递onSubmit处理函数
<NewPostInput onSubmit={addNewComment} />
```

这样，当用户在评论输入框中点击提交时，`NewPostInput`组件内部就会调用我们传入的`addNewComment`函数，从而触发向服务器发送POST请求的流程。

---

## 总结

![](img/59b851fc2f436f46308824236ea1995b_38.png)

本节课中我们一起学习了如何系统性地调试一个React前端应用。我们修复了以下问题：

![](img/59b851fc2f436f46308824236ea1995b_40.png)

![](img/59b851fc2f436f46308824236ea1995b_42.png)

1.  **JSX语法错误**：学会了使用`{}`包裹JavaScript表达式以传递动态值。
2.  **路由链接错误**：修正了导航栏`Link`组件缺失的`to`属性。
3.  **数据传递断裂**：追踪了从`Feed`到`SingleStory`的组件树，补全了缺失的`content`属性传递。
4.  **API请求参数错误**：分析了发布新故事失败的原因，修复了函数调用时缺失参数以及请求体构造的问题。
5.  **事件处理函数未绑定**：发现了评论功能失效是由于`onSubmit`回调函数未正确绑定，并进行了修复。

![](img/59b851fc2f436f46308824236ea1995b_44.png)

调试的关键在于耐心追踪数据流和函数调用链，从错误信息或现象出发，逐层排查可能的原因。恭喜你完成了第二部分调试挑战！