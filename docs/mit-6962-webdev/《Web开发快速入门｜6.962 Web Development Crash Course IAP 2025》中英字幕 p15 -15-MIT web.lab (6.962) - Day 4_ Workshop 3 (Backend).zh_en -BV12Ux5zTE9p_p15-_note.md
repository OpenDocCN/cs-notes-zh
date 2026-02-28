# Web开发快速入门：第4天：工作坊3（后端）🚀

![](img/8cf5410479b52f1f6ecd25c125d030b8_1.png)

在本节课中，我们将学习如何为我们的CatBook应用实现后端功能。目前，我们的帖子和评论都存储在React状态中，一旦刷新页面就会消失。我们的目标是让这些数据持久化，即刷新后帖子与评论依然存在。我们将通过将数据存储在后端服务器，并让前端通过发送HTTP请求来获取和提交数据来实现这一点。

![](img/8cf5410479b52f1f6ecd25c125d030b8_3.png)

![](img/8cf5410479b52f1f6ecd25c125d030b8_4.png)

---

![](img/8cf5410479b52f1f6ecd25c125d030b8_6.png)

![](img/8cf5410479b52f1f6ecd25c125d030b8_8.png)

## 移动数据到后端 📦

![](img/8cf5410479b52f1f6ecd25c125d030b8_10.png)

![](img/8cf5410479b52f1f6ecd25c125d030b8_12.png)

上一节我们了解了前后端分离的基本概念。本节中，我们来看看如何将前端的数据移动到后端。

目前，我们的故事（stories）数据硬编码在 `feed.jsx` 文件中。这意味着所有修改都只是本地的，刷新页面就会恢复原样。我们需要将这些数据移动到后端服务器。

以下是需要完成的步骤：
1.  打开 `feed.jsx` 文件，找到名为 `stories` 的数组定义。
2.  复制整个 `stories` 数组的定义代码。
3.  打开 `server.js` 文件。
4.  将复制的 `stories` 数组代码粘贴到 `server.js` 文件顶部，步骤一的注释之前。

现在，故事数据已经存储在服务器端了。

---

## 发送GET请求获取故事 🔍

现在数据在后端，我们需要让前端能够请求这些数据。我们将通过发送一个HTTP GET请求来实现。

我们将使用项目提供的 `utilities.js` 文件中的 `get` 辅助函数来发送请求。这个函数是对JavaScript原生 `fetch` 函数的封装。

在 `feed.jsx` 文件中，我们需要在组件加载时发送GET请求。我们将使用 `useEffect` Hook。请求的端点（URL）将是 `/api/stories`。

以下是实现步骤：
1.  在 `feed.jsx` 的 `useEffect` 函数内，调用 `get('/api/stories')`。
2.  由于 `get` 函数返回一个Promise（代表异步操作），我们使用 `.then()` 方法来处理服务器返回的数据。
3.  在 `.then()` 的回调函数中，我们会收到服务器返回的故事对象数组。
4.  我们希望故事按从早到晚的顺序显示，所以对数组调用 `.reverse()` 方法进行反转。
5.  最后，使用 `setStories` 函数将反转后的数组更新到React状态中。

代码示例如下：
```javascript
useEffect(() => {
  get('/api/stories').then((storyObjects) => {
    const reversedStories = storyObjects.reverse();
    setStories(reversedStories);
  });
}, []);
```

**核心概念**：`get` 函数向指定端点发送HTTP GET请求，并返回一个Promise。我们使用 `.then()` 来等待请求完成并处理响应数据。

---

## 实现GET故事端点 ⚙️

前端已经发送了请求，现在我们需要在后端创建对应的端点来处理这个请求。

我们将在 `server.js` 中创建一个路由。Express框架使用 `app.get()` 方法来定义处理GET请求的端点。

这个端点需要做以下事情：
1.  监听发送到 `/api/stories` 的GET请求。
2.  当请求到达时，将我们之前存储在 `server.js` 中的 `stories` 数组发送回前端。

在Express中，每个路由处理函数接收两个参数：`req`（请求对象）和 `res`（响应对象）。我们使用 `res.send()` 来发送响应。

![](img/8cf5410479b52f1f6ecd25c125d030b8_14.png)

代码示例如下：
```javascript
app.get('/api/stories', (req, res) => {
  res.send(stories);
});
```

![](img/8cf5410479b52f1f6ecd25c125d030b8_16.png)

**核心概念**：在Express中，`app.get(path, handler)` 用于定义GET请求的路由。`handler` 函数使用 `res.send(data)` 向客户端返回数据。

---

![](img/8cf5410479b52f1f6ecd25c125d030b8_18.png)

![](img/8cf5410479b52f1f6ecd25c125d030b8_19.png)

![](img/8cf5410479b52f1f6ecd25c125d030b8_20.png)

![](img/8cf5410479b52f1f6ecd25c125d030b8_22.png)

## 发送POST请求提交新故事 📨

![](img/8cf5410479b52f1f6ecd25c125d030b8_24.png)

现在我们可以获取故事了，但还需要能够发布新故事。这将涉及发送一个HTTP POST请求。

与GET请求类似，我们将使用 `utilities.js` 中的 `post` 辅助函数。POST请求通常用于向服务器提交数据。

在 `feed.jsx` 中，找到 `addNewStory` 函数。这个函数在当前版本中只是将新故事添加到本地状态。我们需要修改它，使其将新故事发送到后端。

实现步骤：
1.  在 `addNewStory` 函数中，调用 `post('/api/story', value)`。这里的 `value` 是包含新故事内容（content）、创建者（creatorName）和ID的对象。
2.  `post` 函数同样返回一个Promise。我们在 `.then()` 回调中处理服务器的响应。
3.  服务器成功保存故事后，会将该故事对象返回给我们作为确认。
4.  在 `.then()` 中，我们将这个返回的新故事对象添加到前端的React状态中，以便立即显示。

代码逻辑如下：
```javascript
const addNewStory = (value) => {
  post('/api/story', value).then((newStory) => {
    setStories([newStory, ...stories]);
  });
};
```

![](img/8cf5410479b52f1f6ecd25c125d030b8_26.png)

![](img/8cf5410479b52f1f6ecd25c125d030b8_28.png)

![](img/8cf5410479b52f1f6ecd25c125d030b8_30.png)

**注意**：将 `setStories` 放在 `.then()` 内部至关重要。这确保了只有在前端确认服务器已成功接收并存储了新故事后，才更新本地界面。如果放在外面，即使服务器失败，用户也会看到帖子已发布的假象。

---

![](img/8cf5410479b52f1f6ecd25c125d030b8_32.png)

![](img/8cf5410479b52f1f6ecd25c125d030b8_33.png)

## 实现POST故事端点 🛠️

![](img/8cf5410479b52f1f6ecd25c125d030b8_35.png)

![](img/8cf5410479b52f1f6ecd25c125d030b8_37.png)

![](img/8cf5410479b52f1f6ecd25c125d030b8_39.png)

现在，我们需要在后端创建端点来接收前端发来的新故事。

![](img/8cf5410479b52f1f6ecd25c125d030b8_41.png)

![](img/8cf5410479b52f1f6ecd25c125d030b8_43.png)

我们将在 `server.js` 中使用 `app.post()` 方法。

这个端点需要：
1.  监听发送到 `/api/story` 的POST请求。
2.  从请求体中获取新故事数据。在Express中，POST请求的数据位于 `req.body` 中。
3.  将这个新故事对象添加到后端的 `stories` 数组中。
4.  将刚添加的故事对象发送回前端，作为操作成功的确认。

![](img/8cf5410479b52f1f6ecd25c125d030b8_45.png)

![](img/8cf5410479b52f1f6ecd25c125d030b8_47.png)

代码示例如下：
```javascript
app.post('/api/story', (req, res) => {
  const newStory = req.body;
  stories.push(newStory);
  res.send(newStory);
});
```

**核心概念**：对于POST请求，客户端发送的数据包含在请求体（body）中。在Express中，我们需要使用 `express.json()` 中间件（通常在 `server.js` 顶部已配置）来解析 `req.body`。

---

## 处理评论：GET请求与查询参数 💬

我们已经为故事实现了完整的流程。现在，我们需要为评论（comments）实现类似的功能，但有一个关键区别：我们需要获取特定故事下的评论。

首先，将硬编码在 `card.jsx` 中的评论数据移动到 `server.js` 中，就像我们之前对故事做的那样。

接下来，在 `card.jsx` 中发送GET请求获取评论。由于我们只需要特定故事的评论，我们需要告诉服务器是哪个故事。我们通过URL的**查询参数（query parameters）**来实现。

例如，要获取父故事ID为 `123` 的评论，请求的URL可能看起来像：`/api/comments?parent=123`。

在 `card.jsx` 中：
1.  我们使用 `get(`/api/comments?parent=${props.storyId}`)` 来发送请求，其中 `props.storyId` 是当前故事组件的ID。
2.  在 `.then()` 回调中，用服务器返回的评论数组更新React状态。

代码示例如下：
```javascript
useEffect(() => {
  get(`/api/comments?parent=${props.storyId}`).then((commentObjs) => {
    setComments(commentObjs);
  });
}, [props.storyId]);
```

---

## 实现GET评论端点 🔎

在后端，我们需要创建 `/api/comments` 端点来处理这个带查询参数的GET请求。

![](img/8cf5410479b52f1f6ecd25c125d030b8_49.png)

在Express中，可以通过 `req.query` 对象访问查询参数。

![](img/8cf5410479b52f1f6ecd25c125d030b8_51.png)

![](img/8cf5410479b52f1f6ecd25c125d030b8_53.png)

这个端点需要：
1.  从 `req.query.parent` 获取前端传递的父故事ID。
2.  从后端的 `comments` 数组中，过滤出所有 `parent` 字段值与这个ID匹配的评论。
3.  将这些过滤后的评论发送回前端。

![](img/8cf5410479b52f1f6ecd25c125d030b8_55.png)

代码示例如下：
```javascript
app.get('/api/comments', (req, res) => {
  const parentId = req.query.parent;
  const filteredComments = comments.filter(comment => comment.parent === parentId);
  res.send(filteredComments);
});
```

![](img/8cf5410479b52f1f6ecd25c125d030b8_57.png)

**核心概念**：GET请求的参数通过URL的查询字符串传递（如 `?key=value`）。在Express后端，使用 `req.query.key` 来获取这些值。

---

## 处理评论：POST请求 📤

最后，我们需要实现发布新评论的功能。

![](img/8cf5410479b52f1f6ecd25c125d030b8_59.png)

在 `card.jsx` 的 `addNewComment` 函数中，我们将发送一个POST请求到 `/api/comment`。请求体（body）中包含新的评论对象。

代码逻辑如下：
```javascript
const addNewComment = (comment) => {
  post('/api/comment', comment).then((newComment) => {
    setComments([...comments, newComment]);
  });
};
```

同样，我们将更新状态的逻辑放在 `.then()` 内部，以确保与服务器状态同步。

---

![](img/8cf5410479b52f1f6ecd25c125d030b8_61.png)

## 实现POST评论端点 ⚡

![](img/8cf5410479b52f1f6ecd25c125d030b8_63.png)

在后端，创建 `/api/comment` 端点来处理新评论的提交。

这个端点与POST故事的端点非常相似：
1.  从 `req.body` 获取评论数据。
2.  将新评论添加到后端的 `comments` 数组中。
3.  将新增的评论对象发送回前端作为响应。

代码示例如下：
```javascript
app.post('/api/comment', (req, res) => {
  const newComment = req.body;
  comments.push(newComment);
  res.send(newComment);
});
```

![](img/8cf5410479b52f1f6ecd25c125d030b8_65.png)

---

## 代码重构：使用路由中间件进行模块化 🧩

现在，我们的 `server.js` 文件包含了所有API端点，随着功能增加，它会变得冗长且难以管理。为了提高代码的组织性和模块化，我们将API相关的路由移到一个单独的文件中。

项目已经创建了一个 `api.js` 文件。我们将：
1.  在 `api.js` 中创建一个Express路由器（`const router = express.Router()`）。
2.  将 `server.js` 中所有以 `app.get` 或 `app.post` 开头的API端点代码移动到 `api.js` 中。
3.  将这些端点中的 `app` 替换为 `router`，并**移除URL路径中的 `/api` 前缀**（例如，`/api/stories` 变成 `/stories`）。
4.  在 `api.js` 文件末尾，导出这个路由器：`module.exports = router`。
5.  在 `server.js` 中，导入这个路由器：`const api = require('./api')`。
6.  在 `server.js` 中，添加一行中间件：`app.use('/api', api)`。这行代码告诉Express：任何以 `/api` 开头的请求，都交由 `api.js` 中的路由器来处理。

**核心概念**：`app.use('/api', router)` 是一个中间件，它将特定路径前缀（`/api`）下的所有请求，转发给指定的路由器（`router`）处理。这有助于按功能模块组织代码。

---

## 总结 🎉

本节课中我们一起学习了如何构建一个完整的后端来支持前端应用。

![](img/8cf5410479b52f1f6ecd25c125d030b8_67.png)

我们完成的主要工作包括：
1.  **数据持久化**：将故事和评论数据从React状态移动到后端服务器。
2.  **HTTP通信**：使用 `get` 和 `post` 函数在前端发送HTTP请求，与后端进行交互。
3.  **后端端点开发**：在Express服务器上创建对应的GET和POST端点，以处理前端的请求，执行数据检索、添加等操作，并返回响应。
4.  **查询参数的使用**：在获取评论时，通过URL查询参数 `?parent=storyId` 来指定请求上下文。
5.  **代码组织**：通过Express的路由器（Router）和中间件（Middleware）将API路由模块化到单独的文件中，使项目结构更清晰。

![](img/8cf5410479b52f1f6ecd25c125d030b8_69.png)

![](img/8cf5410479b52f1f6ecd25c125d030b8_71.png)

现在，你的CatBook应用已经具备了基本的前后端交互能力，帖子与评论在刷新页面后也能得以保留！