# 022：第5讲 - 数据库集成 🗄️

![](img/27fc632f2042799173055ebe2e50dfca_1.png)

在本节课中，我们将学习如何将MongoDB数据库连接到你的Cat App后端。我们将创建数据模型，并修改API端点，以实现用户信息、故事信息和评论信息在数据库中的存储与检索。

---

![](img/27fc632f2042799173055ebe2e50dfca_3.png)

## 连接应用与数据库 🔌

![](img/27fc632f2042799173055ebe2e50dfca_5.png)

![](img/27fc632f2042799173055ebe2e50dfca_7.png)

上一节我们介绍了数据库的基本概念，本节中我们来看看如何将你的应用连接到MongoDB实例。

![](img/27fc632f2042799173055ebe2e50dfca_9.png)

首先，你需要获取你的MongoDB连接字符串。这个字符串通常以 `mongodb+srv://` 开头。请将其复制并粘贴到 `server.js` 文件中的相应位置。

**代码示例：**
```javascript
// 在 server.js 文件中
const MONGO_CONNECTION_URL = process.env.MONGO_URL; // 请在此处替换为你的连接字符串
```

完成此步骤后，运行 `npm install` 和 `npm start`。如果连接成功，你将在终端看到“Server running on port 3000 and connected to MongoDB”的消息。

---

## 创建数据模型 📐

现在我们已经建立了数据库连接，接下来需要定义数据的结构。我们将为“故事”和“评论”创建Mongoose模型。

在MongoDB中，我们使用**模式（Schema）**来定义文档的结构，并使用**模型（Model）**作为构建文档的构造函数。

以下是创建“故事”模型的步骤，你需要对“评论”模型进行类似操作。

**步骤列表：**
1.  在 `models/story.js` 文件中，导入 `mongoose`。
2.  使用 `new mongoose.Schema()` 定义一个模式，指定 `creatorName` 和 `content` 字段及其类型（例如 `String`）。
3.  使用 `mongoose.model()` 基于该模式创建一个模型。
4.  使用 `module.exports` 导出该模型。

**代码示例（story.js）：**
```javascript
const mongoose = require('mongoose');

const storySchema = new mongoose.Schema({
  creatorName: String,
  content: String
});

const Story = mongoose.model('Story', storySchema);
module.exports = Story;
```

对于“评论”模型，你还需要添加一个 `parent` 字段，用于关联其所属的故事。

---

## 修改API端点以使用数据库 🔄

我们已成功创建了数据模型，本节我们将修改后端API，使其能够与数据库进行交互。

首先，需要在 `api.js` 中导入我们刚刚创建的模型。

**代码示例：**
```javascript
const Story = require('./models/story');
const Comment = require('./models/comment');
```

### 处理GET请求

对于获取所有故事的端点（`GET /stories`），我们将使用模型的 `.find()` 方法从数据库中检索所有文档。

![](img/27fc632f2042799173055ebe2e50dfca_11.png)

![](img/27fc632f2042799173055ebe2e50dfca_12.png)

**代码示例：**
```javascript
router.get('/stories', (req, res) => {
  Story.find()
    .then(stories => {
      res.send(stories);
    })
    .catch(error => {
      // 处理错误
    });
});
```

对于获取特定故事评论的端点（`GET /comments`），我们需要根据查询参数 `parent`（即故事ID）来过滤评论。

**代码示例：**
```javascript
router.get('/comments', (req, res) => {
  Comment.find({ parent: req.query.parent })
    .then(comments => {
      res.send(comments);
    })
    .catch(error => {
      // 处理错误
    });
});
```

### 处理POST请求

对于创建新故事的端点（`POST /story`），我们需要从请求体（`req.body`）中获取数据，创建一个新的模型实例，然后使用 `.save()` 方法将其存入数据库。

**代码示例：**
```javascript
router.post('/story', (req, res) => {
  const newStory = new Story({
    creatorName: '你的名字', // 可以动态设置
    content: req.body.content
  });
  newStory.save()
    .then(() => {
      res.send({ message: 'Story created!' });
    })
    .catch(error => {
      // 处理错误
    });
});
```

创建新评论的端点（`POST /comment`）逻辑类似，但需要额外保存 `parent` 字段。

**代码示例：**
```javascript
router.post('/comment', (req, res) => {
  const newComment = new Comment({
    parent: req.body.parent,
    content: req.body.content
  });
  newComment.save()
    .then(() => {
      res.send({ message: 'Comment created!' });
    })
    .catch(error => {
      // 处理错误
    });
});
```

完成这些修改后，你的前端应用就可以通过API将数据持久化到MongoDB中，并在需要时从数据库获取数据。

---

## 测试与验证 ✅

修改完成后，请务必进行测试。
1.  运行你的前端（`npm run dev`）和后端（`npm start`）服务器。
2.  尝试在应用中发布新的故事和评论。
3.  登录你的MongoDB Atlas集群，在对应的数据库集合中，检查是否出现了新创建的“故事”和“评论”文档。这是验证数据是否成功存入数据库的好方法。

---

## 总结 📝

本节课中我们一起学习了数据库集成的核心步骤：
1.  **连接数据库**：将MongoDB连接字符串配置到后端应用中。
2.  **定义数据模型**：使用Mongoose模式与模型为“故事”和“评论”定义数据结构。
3.  **集成后端API**：修改GET和POST端点，使用模型方法与数据库进行交互，实现数据的创建与查询。

![](img/27fc632f2042799173055ebe2e50dfca_14.png)

现在，你的Cat App已经具备了数据持久化能力，所有用户生成的内容都将安全地存储在云端数据库中。