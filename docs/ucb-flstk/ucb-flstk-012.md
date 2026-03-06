# 012：后端开发（二）🚀

![](img/18f8b419755349cc15567673482ae2ee_0.png)

在本节课中，我们将学习如何使用 Express 框架和 MongoDB 数据库构建后端服务。我们将重点创建一个用户认证系统，包括用户注册、登录以及使用 JSON Web Token (JWT) 进行安全验证。

---

## 课程回顾

上一节我们介绍了 HTTP 协议、REST API 架构以及如何使用 Postman 测试 API 端点。HTTP 是一种允许不同计算机在互联网上通信的协议。客户端发起 HTTP 请求，服务器则包含信息并返回响应。REST 是 API 的一种架构风格，而 API 是允许两个应用程序相互通信的接口。Postman 是一个用于测试 HTTP 请求和 API 端点的工具。

简单来说，当你在浏览器中访问一个网页时，你的计算机会向一个 API 发送请求。API 处理该请求，可能会从服务器上的数据库收集必要信息，然后将数据打包，以响应的形式发送回你的浏览器。

---

## Express 框架介绍

Express 是一个基于 Node.js 的后端 Web 应用框架。它专为构建 Web 应用程序和 API 而设计，与前端常用的 Axios 不同，Express 主要用于后端开发。

以下是一个简单的 Express 服务器代码示例：

```javascript
const express = require('express');
const app = express();

![](img/18f8b419755349cc15567673482ae2ee_2.png)

app.get('/', (req, res) => {
  res.json({ message: 'API 正在运行' });
});

app.listen(4000, () => {
  console.log(`服务器已在端口 4000 启动`);
});
```

在这段代码中，我们首先创建了一个 Express 应用对象，然后定义了一个处理根路径 (`/`) GET 请求的路由，最后让服务器监听 4000 端口。

要使用 Express，你需要先通过 `npm install express` 命令安装它。

![](img/18f8b419755349cc15567673482ae2ee_4.png)

![](img/18f8b419755349cc15567673482ae2ee_5.png)

---

## 数据库基础

数据库是结构化信息或数据的组织集合，通常以电子形式存储在计算机系统中。主要有两种类型的数据库：

![](img/18f8b419755349cc15567673482ae2ee_7.png)

1.  **SQL 数据库**：如 PostgreSQL 和 Microsoft SQL Server。你可以将其想象成 Google Sheets 表格，每一行数据对应一条记录，不同的列对应不同的数据类别。
2.  **NoSQL 数据库**：如 MongoDB 和 DynamoDB。这类数据库不使用表格，而是通过定义“模式”来规定数据的结构。数据以对象的形式存储，每个对象可以包含多个字段。

本节课我们将主要使用 **MongoDB**，它是一种学习曲线相对平缓的 NoSQL 数据库。

在 MongoDB 中，数据以集合的形式组织，集合中的每个文档都是一个 JSON 对象。例如，一个存储 Airbnb 房源的数据库，每个文档（对象）都包含 `name`、`description`、`price` 等字段。

---

![](img/18f8b419755349cc15567673482ae2ee_9.png)

![](img/18f8b419755349cc15567673482ae2ee_11.png)

## 项目搭建与依赖安装

![](img/18f8b419755349cc15567673482ae2ee_13.png)

![](img/18f8b419755349cc15567673482ae2ee_14.png)

现在，让我们开始动手搭建项目。首先，创建一个新目录并初始化 Node.js 项目：

```bash
mkdir mongo-practice
cd mongo-practice
npm init -y
```

接着，安装项目所需的依赖包：

```bash
npm install --save express cors mongoose bcryptjs jsonwebtoken express-validator nodemon dotenv
```

![](img/18f8b419755349cc15567673482ae2ee_16.png)

以下是各个依赖包的作用：
*   `express`: 后端 Web 应用框架。
*   `cors`: 处理跨域资源共享。
*   `mongoose`: 用于连接和操作 MongoDB 数据库的 ODM 库。
*   `bcryptjs`: 用于加密用户密码。
*   `jsonwebtoken`: 用于生成和验证 JSON Web Token，实现用户认证。
*   `express-validator`: 用于验证输入数据。
*   `nodemon`: 开发工具，监视文件变化并自动重启服务器。
*   `dotenv`: 用于加载环境变量。

![](img/18f8b419755349cc15567673482ae2ee_18.png)

---

## 创建 Express 服务器

创建一个 `index.js` 文件作为应用的入口点：

```javascript
const express = require('express');
const bodyParser = require('body-parser');

const app = express();
const PORT = 4000;

// 中间件：解析 JSON 格式的请求体
app.use(bodyParser.json());

// 基础路由，用于测试
app.get('/', (req, res) => {
  res.json({ message: 'API 正在运行' });
});

// 启动服务器
app.listen(PORT, () => {
  console.log(`服务器已在端口 ${PORT} 启动`);
});
```

使用 `npx nodemon index.js` 命令启动服务器，然后在 Postman 中访问 `http://localhost:4000/`，你应该会收到 `{“message”: “API 正在运行”}` 的响应。

---

## 连接 MongoDB 数据库

为了连接 MongoDB，我们需要配置数据库连接。首先，在 MongoDB Atlas（云服务）或本地创建一个数据库，并获取连接字符串。

创建一个 `config/db.js` 文件：

```javascript
const mongoose = require('mongoose');
const mongoURI = ‘你的MongoDB连接字符串/test’; // 请替换为你的实际连接字符串

const initiateMongoServer = async () => {
  try {
    await mongoose.connect(mongoURI, {
      useNewUrlParser: true,
      useUnifiedTopology: true,
    });
    console.log(‘已连接到数据库’);
  } catch (e) {
    console.log(e);
    throw e;
  }
};

module.exports = initiateMongoServer;
```

在 `index.js` 中引入并调用此函数：

```javascript
const initiateMongoServer = require(‘./config/db’);
initiateMongoServer();
```

---

## 定义数据模型（Schema）

在 MongoDB 中，我们使用模式来定义数据的结构。创建一个 `models/User.js` 文件来定义用户模型：

```javascript
const mongoose = require(‘mongoose’);

const UserSchema = new mongoose.Schema({
  username: {
    type: String,
    required: true,
  },
  email: {
    type: String,
    required: true,
  },
  password: {
    type: String,
    required: true,
  },
  createdAt: {
    type: Date,
    default: Date.now,
  },
});

module.exports = mongoose.model(‘User’, UserSchema);
```

![](img/18f8b419755349cc15567673482ae2ee_20.png)

这个模式规定，每个用户文档必须有 `username`、`email` 和 `password` 字段，并且都是字符串类型。`createdAt` 字段会自动设置为创建文档的日期。

![](img/18f8b419755349cc15567673482ae2ee_22.png)

---

## 实现用户注册功能

我们将使用路由来组织 API 端点。创建一个 `routes/user.js` 文件来处理用户相关的请求。

首先，实现用户注册 (`/signup`) 端点：

```javascript
const express = require(‘express’);
const router = express.Router();
const User = require(‘../models/User’);
const bcrypt = require(‘bcryptjs’);
const jwt = require(‘jsonwebtoken’);

![](img/18f8b419755349cc15567673482ae2ee_24.png)

// 用户注册
router.post(‘/signup’, async (req, res) => {
  const { username, email, password } = req.body;

  try {
    // 1. 检查用户是否已存在
    let user = await User.findOne({ email });
    if (user) {
      return res.status(400).json({ msg: ‘用户已存在’ });
    }

    // 2. 创建新用户对象
    user = new User({
      username,
      email,
      password,
    });

    // 3. 加密密码
    const salt = await bcrypt.genSalt(10);
    user.password = await bcrypt.hash(password, salt);

    // 4. 保存用户到数据库
    await user.save();

    // 5. 创建并返回 JWT
    const payload = {
      user: {
        id: user.id,
      },
    };

    jwt.sign(
      payload,
      ‘randomString’, // 应使用更安全的密钥，并从环境变量读取
      { expiresIn: 10000 },
      (err, token) => {
        if (err) throw err;
        res.status(200).json({ token });
      }
    );
  } catch (err) {
    console.error(err.message);
    res.status(500).send(‘保存用户时出错’);
  }
});

module.exports = router;
```

![](img/18f8b419755349cc15567673482ae2ee_26.png)

![](img/18f8b419755349cc15567673482ae2ee_28.png)

在 `index.js` 中挂载这个路由：

![](img/18f8b419755349cc15567673482ae2ee_30.png)

![](img/18f8b419755349cc15567673482ae2ee_31.png)

![](img/18f8b419755349cc15567673482ae2ee_32.png)

![](img/18f8b419755349cc15567673482ae2ee_34.png)

```javascript
const userRoutes = require(‘./routes/user’);
app.use(‘/user’, userRoutes);
```

![](img/18f8b419755349cc15567673482ae2ee_36.png)

现在，你可以使用 Postman 向 `http://localhost:4000/user/signup` 发送一个 POST 请求，请求体为 JSON 格式（例如 `{“username”: “test”, “email”: “test@example.com”, “password”: “123456”}`），来测试注册功能。成功后，你会收到一个 JWT 令牌。

![](img/18f8b419755349cc15567673482ae2ee_38.png)

![](img/18f8b419755349cc15567673482ae2ee_40.png)

![](img/18f8b419755349cc15567673482ae2ee_42.png)

---

![](img/18f8b419755349cc15567673482ae2ee_44.png)

![](img/18f8b419755349cc15567673482ae2ee_45.png)

![](img/18f8b419755349cc15567673482ae2ee_47.png)

![](img/18f8b419755349cc15567673482ae2ee_48.png)

## 实现用户登录功能

![](img/18f8b419755349cc15567673482ae2ee_49.png)

![](img/18f8b419755349cc15567673482ae2ee_50.png)

接下来，在 `routes/user.js` 中添加用户登录 (`/login`) 端点：

```javascript
// 用户登录
router.post(‘/login’, async (req, res) => {
  const { email, password } = req.body;

  try {
    // 1. 检查用户是否存在
    let user = await User.findOne({ email });
    if (!user) {
      return res.status(400).json({ msg: ‘用户不存在，请先注册’ });
    }

    // 2. 验证密码
    const isMatch = await bcrypt.compare(password, user.password);
    if (!isMatch) {
      return res.status(400).json({ msg: ‘密码错误’ });
    }

    // 3. 创建并返回 JWT
    const payload = {
      user: {
        id: user.id,
      },
    };

    jwt.sign(
      payload,
      ‘randomString’,
      { expiresIn: 3600 },
      (err, token) => {
        if (err) throw err;
        res.json({ token });
      }
    );
  } catch (err) {
    console.error(err.message);
    res.status(500).send(‘服务器错误’);
  }
});
```

使用 Postman 向 `http://localhost:4000/user/login` 发送包含邮箱和密码的 POST 请求，验证登录功能。

![](img/18f8b419755349cc15567673482ae2ee_52.png)

---

## 使用中间件保护路由

中间件是一种函数，它可以访问请求对象 (`req`)、响应对象 (`res`) 和下一个中间件函数 (`next`)。它的主要作用是在请求到达最终路由处理器之前，执行一些检查或操作。

我们将创建一个中间件来验证 JWT。创建 `middleware/auth.js` 文件：

```javascript
const jwt = require(‘jsonwebtoken’);

![](img/18f8b419755349cc15567673482ae2ee_54.png)

![](img/18f8b419755349cc15567673482ae2ee_56.png)

module.exports = function (req, res, next) {
  // 从请求头中获取 token
  const token = req.header(‘x-auth-token’);

  // 检查 token 是否存在
  if (!token) {
    return res.status(401).json({ msg: ‘无令牌，授权被拒绝’ });
  }

  try {
    // 验证 token
    const decoded = jwt.verify(token, ‘randomString’);
    req.user = decoded.user; // 将解码后的用户信息添加到请求对象中
    next(); // 继续执行下一个中间件或路由处理器
  } catch (err) {
    res.status(401).json({ msg: ‘令牌无效’ });
  }
};
```

![](img/18f8b419755349cc15567673482ae2ee_58.png)

现在，我们可以创建一个受保护的路由，只有提供有效 JWT 的用户才能访问。在 `routes/user.js` 中添加：

![](img/18f8b419755349cc15567673482ae2ee_60.png)

```javascript
const auth = require(‘../middleware/auth’);

// 获取当前用户信息 (受保护路由)
router.get(‘/me’, auth, async (req, res) => {
  try {
    // 中间件已将用户ID添加到 req.user
    const user = await User.findById(req.user.id).select(‘-password’); // 查询用户但不返回密码字段
    res.json(user);
  } catch (err) {
    console.error(err.message);
    res.status(500).send(‘获取用户信息时出错’);
  }
});
```

要测试这个端点，你需要：
1.  先通过登录或注册获取一个 JWT 令牌。
2.  在 Postman 中，向 `http://localhost:4000/user/me` 发送 GET 请求。
3.  在请求的 “Headers” 选项卡中，添加一个键为 `x-auth-token`，值为你的 JWT 令牌的请求头。

如果令牌有效，你将收到当前用户的详细信息（不包括密码）。

---

## 总结

本节课我们一起学习了后端开发的核心概念与实践。我们回顾了 HTTP 和 REST API 的基础知识，然后深入使用 **Express** 框架搭建了服务器。我们介绍了 **MongoDB** 这种 NoSQL 数据库，并通过 **Mongoose** 库与之进行交互。

本节课的重点是构建了一个完整的用户认证系统：
1.  我们定义了用户数据模型（Schema）。
2.  实现了用户**注册**功能，包括密码加密（使用 `bcryptjs`）和将用户保存至数据库。
3.  实现了用户**登录**功能，验证用户凭证并返回一个 **JSON Web Token (JWT)**。
4.  创建了**认证中间件**，用于在后续请求中验证 JWT 的有效性。
5.  实现了一个**受保护的路由** (`/me`)，只有携带有效 JWT 的请求才能访问，并返回用户信息。

![](img/18f8b419755349cc15567673482ae2ee_62.png)

![](img/18f8b419755349cc15567673482ae2ee_63.png)

通过这个流程，我们模拟了现代 Web 应用中常见的认证与授权机制。在开发过程中，使用 **Postman** 测试 API 端点，以及利用 **nodemon** 实现开发热重载，都是提高效率的重要实践。