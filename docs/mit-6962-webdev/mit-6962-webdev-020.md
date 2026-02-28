# 020：调试Catbook第四部分答案

![](img/69a8e0c16000cb8a698c13e705325e15_0.png)

![](img/69a8e0c16000cb8a698c13e705325e15_2.png)

在本节课中，我们将一起解决Catbook项目的第四个调试挑战。我们将定位并修复导致页面白屏、评论显示错误以及新故事发布后前端不更新的问题。

## 概述与问题重现

![](img/69a8e0c16000cb8a698c13e705325e15_4.png)

![](img/69a8e0c16000cb8a698c13e705325e15_6.png)

上一节我们完成了代码的拉取和服务器重启。现在，让我们访问Catbook页面，看看具体出现了什么问题。



![](img/69a8e0c16000cb8a698c13e705325e15_8.png)

![](img/69a8e0c16000cb8a698c13e705325e15_0.png)

页面显示为白屏。一个实用的调试技巧是：每当遇到白屏，首先应打开浏览器的JavaScript控制台，那里通常会有更详细的错误信息。



控制台显示错误：`Uncaught SyntaxError: The requested module ‘./NewPostInput’ does not provide an export named ‘default’`。这个错误与组件的导出和导入有关，并且指向了`Feed`和`NewPostInput`组件。

## 修复导出/导入语法错误

让我们先检查`NewPostInput.jsx`文件，看看它是如何导出的。



![](img/69a8e0c16000cb8a698c13e705325e15_4.png)

在`NewPostInput.jsx`中，我们定义了`NewStory`和`NewComment`两个组件，并使用以下方式导出：
```javascript
export { NewComment, NewStory };
```
注意，这里使用的是**命名导出**，而不是`export default`。

接下来，我们看看在`Feed.jsx`中是如何导入`NewStory`的。



![](img/69a8e0c16000cb8a698c13e705325e15_10.png)

![](img/69a8e0c16000cb8a698c13e705325e15_10.png)

问题找到了！在`Feed.jsx`中，导入语句缺少了花括号 `{}`。对于命名导出的模块，导入时必须使用花括号指定具体的导出名称。

**修复方法：**
将 `import NewStory from ‘./NewPostInput’;` 修改为：
```javascript
import { NewStory } from ‘./NewPostInput’;
```

![](img/69a8e0c16000cb8a698c13e705325e15_12.png)

![](img/69a8e0c16000cb8a698c13e705325e15_14.png)

保存更改后，页面错误更新为：`The requested module ‘./Feed’ does not provide an export named ‘default’`。这说明`Feed`组件本身的导出也有问题。

## 修复Feed组件的导出

这个错误可能出现在`Feed.jsx`的导出部分，或者`index.jsx`的导入部分。我们同时打开这两个文件进行检查。



![](img/69a8e0c16000cb8a698c13e705325e15_14.png)

在`index.jsx`中，导入语句是 `import Feed from ‘./Feed’;`，这表示它期望导入`Feed.jsx`的默认导出。
然而，在`Feed.jsx`文件的底部，我们并没有任何导出语句。

![](img/69a8e0c16000cb8a698c13e705325e15_16.png)

**修复方法：**
在`Feed.jsx`文件底部添加默认导出：
```javascript
export default Feed;
```

保存后，页面成功加载，但出现了新问题：所有评论都显示在每一条故事下面，而不是只显示在对应的父故事下。

## 修复评论过滤逻辑

![](img/69a8e0c16000cb8a698c13e705325e15_18.png)

所有评论都重复显示，这通常是后端API过滤逻辑出了问题。我们打开浏览器开发者工具的“网络”选项卡，查看获取评论的请求。



![](img/69a8e0c16000cb8a698c13e705325e15_20.png)

![](img/69a8e0c16000cb8a698c13e705325e15_16.png)

请求URL是 `/api/comments?parentId=3`，这看起来是正确的。服务器也返回了三条评论。问题可能出在服务器没有正确根据`parentId`进行过滤。

打开服务器端的`api.js`文件，查看处理`/api/comments` GET请求的代码。



![](img/69a8e0c16000cb8a698c13e705325e15_22.png)

![](img/69a8e0c16000cb8a698c13e705325e15_24.png)

代码中，我们试图根据`req.query.parentStory`来过滤评论。为了调试，我们在服务器终端打印相关值：
```javascript
console.log(‘comment.parentStory:’, comments[0].parentStory);
console.log(‘req.query.parentStory:’, req.query.parentStory);
```

![](img/69a8e0c16000cb8a698c13e705325e15_26.png)

刷新页面后，终端两个值都打印为`undefined`。这说明：
1.  评论对象中没有`parentStory`字段，正确的字段名是`parent`。
2.  查询参数中也没有`parentStory`，正确的参数名是`parentId`。

**修复方法：**
将代码中的`parentStory`全部更正为正确的字段名。
1.  将 `comment.parentStory` 改为 `comment.parent`。
2.  将 `req.query.parentStory` 改为 `req.query.parentId`。

修改后，评论显示恢复正常，每条故事下只显示属于自己的评论。

![](img/69a8e0c16000cb8a698c13e705325e15_28.png)

## 修复发布新故事后前端不更新的问题

![](img/69a8e0c16000cb8a698c13e705325e15_30.png)

现在测试发布新故事功能。提交后，新故事没有立即出现在页面上，但刷新页面后会显示。这说明后端成功保存了数据，但前端没有用返回的数据更新状态。

![](img/69a8e0c16000cb8a698c13e705325e15_32.png)

首先，我们检查后端`api.js`中处理`/api/story` POST请求的代码。



![](img/69a8e0c16000cb8a698c13e705325e15_34.png)

![](img/69a8e0c16000cb8a698c13e705325e15_28.png)

代码将新故事加入了数组，但没有通过`res.send()`将其返回给前端。根据RESTful API设计，创建资源后通常将新创建的对象返回。

![](img/69a8e0c16000cb8a698c13e705325e15_36.png)

**修复方法：**
在添加故事到数组后，发送新故事作为响应：
```javascript
res.send(newStory);
```

但这还不够。我们还需要修改前端，使其在收到服务器响应后更新本地状态。打开`Feed.jsx`，找到`addNewStory`方法。



![](img/69a8e0c16000cb8a698c13e705325e15_36.png)

当前，`addNewStory`方法只发送了POST请求，但没有处理响应。我们需要在Promise的`.then()`回调中，使用服务器返回的新故事来更新React的状态。

**修复方法：**
修改`addNewStory`方法，在收到响应后更新`stories`状态：
```javascript
addNewStory = (value) => {
    fetch(‘/api/story’, {
        method: ‘POST’,
        headers: {
            ‘Content-Type’: ‘application/json’,
        },
        body: JSON.stringify(value),
    })
    .then((response) => response.json())
    .then((storyResponse) => {
        // 将新故事添加到现有故事列表的前面
        this.setStories([storyResponse, …this.state.stories]);
    });
}
```
这里，`setStories`用于更新状态，将新故事（`storyResponse`）放在原有故事数组（`…this.state.stories`）的最前面。

## 总结

![](img/69a8e0c16000cb8a698c13e705325e15_38.png)

本节课中，我们一起学习了如何系统性地调试一个React全栈应用。我们解决了三个主要问题：
1.  **组件导入/导出错误**：修复了因错误使用命名导出和默认导出而导致的语法错误。
2.  **后端API逻辑错误**：修正了字段名不匹配导致的评论过滤失效问题。
3.  **前端状态更新缺失**：补充了发布新故事后，前端根据服务器响应更新本地状态的逻辑。

![](img/69a8e0c16000cb8a698c13e705325e15_40.png)

调试的关键在于耐心和有条理：从错误信息出发，利用浏览器控制台和网络工具，定位问题出现在前端还是后端，然后逐层检查相关代码。希望这次调试过程能帮助你更好地理解模块导出和状态管理的概念。