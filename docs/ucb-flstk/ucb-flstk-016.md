# 016：Turso 数据库演示

在本节课中，我们将学习 Turso 数据库。Turso 是一个基于 LibSQL 的边缘托管分布式数据库。我们将了解其核心概念、工作原理，并通过一个简单的 Node.js 和 Express 应用演示其基本用法。

## 概述：什么是 Turso？

Turso 的定义是：一个基于 LibSQL 的边缘托管分布式数据库。LibSQL 是 SQLite 的一个开源、开放贡献的分支。为了理解这个定义，我们需要逐一拆解其中的术语。

## 边缘计算与数据边缘

上一节我们介绍了 Turso 的基本定义，本节中我们来看看“边缘托管”和“数据边缘”这两个核心概念。

在传统的客户端-服务器应用架构中，用户请求需要经过多个步骤：从用户设备到 Web 服务器，再到数据库，然后返回。这个往返过程的延迟总和，就是用户感知到的网站速度。

**公式：** `往返延迟 = 步骤1 + 步骤2 + 步骤3 + 步骤4`

当用户与服务器距离很远时，延迟会显著增加，尤其是当网络流量需要跨越大洋时。为了解决这个问题，出现了“边缘计算”的概念。

边缘计算是一种分布式计算范式，它将计算和数据存储移动到更靠近数据源（即用户）的位置，从而改善响应时间并节省带宽。

边缘计算主要分为两种：
*   **远边缘：** 指物联网设备、移动设备等，它们可能网络能力有限甚至离线。
*   **近边缘：** 指部署在全球各地的数据中心，提供内容分发网络和边缘函数等服务。

仅仅复制 Web 服务器到边缘还不够，因为数据库查询仍然需要回到中心数据库。为了彻底解决延迟问题，我们需要将数据库也复制到边缘。这就是“数据边缘”的概念。

数据边缘通过将数据库副本放置在靠近查询源（即应用服务器）的位置，实现了最低可能的往返延迟。用户靠近应用服务器，应用服务器靠近数据库，从而最小化了所有环节的延迟。

然而，数据库复制也带来了一些挑战，例如实现难度大、成本较高，以及可能导致数据一致性变弱。Turso 正是为了解决在边缘硬件上运行数据库的挑战而设计的。

## SQL 与 NoSQL 数据库对比

了解了数据边缘的概念后，我们来看看 Turso 所基于的数据库类型。Turso 使用 SQL 数据库，这与课程中学习的 MongoDB 不同。

以下是 SQL 和 NoSQL 数据库的主要区别：

*   **数据模型：**
    *   **SQL：** 使用具有行和列的表格来构建高度结构化的数据。
    *   **NoSQL (如 MongoDB)：** 使用灵活的 JSON 文档存储数据。
*   **查询语言：**
    *   **SQL：** 拥有强大、灵活的标准化查询语言。
    *   **NoSQL：** 查询能力通常较弱，主要通过 API 进行。
*   **可扩展性：**
    *   **SQL：** 传统上难以水平扩展，单表数据量极大时性能可能下降。
    *   **NoSQL：** 通常设计为易于大规模水平扩展。

SQLite 是一个快速、小巧的数据库，它被直接嵌入到应用程序中。它非常适合在资源有限的边缘设备上运行，也是世界上使用最广泛的数据库之一。然而，SQLite 的一个主要限制是它没有内置的服务器模式，无法直接从网络访问。

## LibSQL 与 Turso

为了解决 SQLite 的局限性，ChiselStrike 创建了 LibSQL。LibSQL 是 SQLite 的一个分支，并在此基础上增加了关键功能。

LibSQL 的主要增强包括：
1.  **服务器模式 (SQLD)：** 增加了网络访问能力，可以通过 HTTP 或 WebSocket 进行查询。
2.  **复制功能：** 支持在多个 SQLD 实例之间复制数据，这是实现数据边缘的基础。
3.  **客户端库：** 提供了 JavaScript/TypeScript、Rust、Python 等语言的 SDK。
4.  **Wasm 用户定义函数：** 支持在数据库内运行自定义代码。
5.  **开源与开放贡献：** 社区可以积极参与项目的改进。

Turso 则是在 LibSQL 之上构建的托管服务。它简化了数据库的配置和管理：
*   **自动管理：** 自动配置和管理 SQLD 实例。
*   **命令行工具 (CLI)：** 提供便捷的数据库操作命令。
*   **令牌认证：** 提供基于令牌的客户端认证系统。

用户只需使用 Turso CLI，即可轻松创建数据库和副本，而无需关心底层的 LibSQL 实例。

## 实战演示：构建一个使用 Turso 的 Express 应用

理论部分已经介绍完毕，现在让我们通过一个实际的 Node.js 项目来演示 Turso 的使用。

### 步骤 1：初始化项目与安装依赖

首先，创建一个空目录并初始化 Node.js 项目，然后安装必要的依赖。

```bash
# 初始化项目
npm init -y

# 安装 TypeScript 及相关类型定义
npm install typescript @types/node --save-dev

# 安装 Express 及其类型定义
npm install express
npm install @types/express --save-dev

# 安装 Turso 的客户端库
npm install @libsql/client
```

初始化 TypeScript 配置：
```bash
npx tsc --init
```
在生成的 `tsconfig.json` 中，可以设置 `outDir` 为 `./build`，`rootDir` 为 `./src`。

### 步骤 2：创建 Turso 数据库并获取连接信息

使用 Turso CLI 创建数据库并获取连接所需的 URL 和令牌。

```bash
# 登录 Turso (使用 GitHub 账户)
turso auth login

# 查看可用的部署位置
turso db locations

# 创建数据库（会自动选择离你最近的位置）
turso db create my-demo-db

# 显示数据库信息，获取 URL
turso db show my-demo-db

# 创建访问令牌
turso db tokens create my-demo-db
```

### 步骤 3：编写数据库操作代码

创建 `src/demo.ts` 文件，编写连接数据库和执行查询的代码。

```typescript
import { createClient } from "@libsql/client";

async function main() {
  // 配置客户端，使用从 CLI 获取的 URL 和令牌
  const config = {
    url: "libsql://your-database-url.turso.io",
    authToken: "your-super-secret-auth-token",
  };

  const client = createClient(config);

  try {
    // 执行一个查询
    const rs = await client.execute("SELECT * FROM users");
    console.log(rs);
  } catch (e) {
    console.error(e);
  } finally {
    // 关闭客户端连接
    client.close();
  }
}

![](img/8b2d98c3900020dcd3d68ca84ea0fe19_1.png)

main();
```

### 步骤 4：创建 Express 服务器并集成 Turso

创建 `src/server.ts` 文件，构建一个简单的 API 服务器。

```typescript
import express from "express";
import { createClient } from "@libsql/client";

const app = express();
const port = 3000;

// 配置数据库客户端（应在环境变量中管理敏感信息）
const dbClient = createClient({
  url: process.env.DATABASE_URL!,
  authToken: process.env.DATABASE_AUTH_TOKEN!,
});

// 定义路由：获取所有用户
app.get("/users", async (req, res) => {
  try {
    const rs = await dbClient.execute("SELECT * FROM users");
    res.json(rs);
  } catch (error) {
    console.error(error);
    res.status(500).send("Database error");
  }
});

// 定义路由：添加新用户
app.get("/add-user", async (req, res) => {
  const email = req.query.email;

  // 验证 email 参数
  if (typeof email !== "string") {
    res.status(400).send("Email query parameter is required and must be a string");
    return;
  }

  const userId = `user-${Math.random().toString(36).substr(2, 9)}`; // 生成随机用户ID

  try {
    await dbClient.execute({
      sql: "INSERT INTO users (id, email, coins) VALUES (?, ?, ?)",
      args: [userId, email, 0], // 新用户硬币数为 0
    });
    res.send(`User added with ID: ${userId}`);
  } catch (error) {
    console.error(error);
    res.status(500).send("Failed to add user");
  }
});

app.listen(port, () => {
  console.log(`Server running at http://localhost:${port}`);
});
```

### 步骤 5：创建数据库表

在运行服务器前，需要先创建表。可以使用 Turso Shell：

```bash
# 打开数据库的交互式 Shell
turso db shell my-demo-db
```
在 Shell 中执行 SQL：
```sql
CREATE TABLE users (
    id TEXT PRIMARY KEY,
    email TEXT NOT NULL,
    coins INTEGER DEFAULT 0
);
```

### 步骤 6：运行与测试

编译并运行 TypeScript 代码，然后测试 API。

```bash
# 编译 TypeScript
npx tsc

# 运行服务器（确保已设置环境变量）
DATABASE_URL="your-url" DATABASE_AUTH_TOKEN="your-token" node build/server.js
```

使用 `curl` 或浏览器测试 API 端点：
```bash
# 获取用户列表
curl http://localhost:3000/users

# 添加新用户
curl "http://localhost:3000/add-user?email=newuser@example.com"
```

### 步骤 7：创建数据库副本

为了演示边缘复制，可以为数据库在另一个地理位置创建一个副本。

```bash
# 查看所有可用位置
turso db locations

# 在圣何塞 (SJC) 创建一个副本
turso db replicate my-demo-db sjc

# 再次查看数据库状态，现在应该有一个主实例和一个副本
turso db show my-demo-db
```
创建副本后，应用程序使用的逻辑 URL 会自动将查询路由到离用户最近的数据库实例。

## 总结

![](img/8b2d98c3900020dcd3d68ca84ea0fe19_3.png)

本节课中我们一起学习了 Turso 数据库。我们从其作为基于 LibSQL 的边缘托管分布式数据库的定义开始，深入探讨了“边缘计算”和“数据边缘”的概念，了解了它们如何通过将数据和计算移至用户附近来降低延迟。我们对比了 SQL 和 NoSQL 数据库的特点，并解释了 LibSQL 如何通过为 SQLite 添加服务器模式和复制功能来满足边缘计算的需求。最后，通过一个完整的实战演示，我们一步步创建了一个使用 Turso 的 Node.js 和 Express 应用，包括初始化项目、创建数据库、执行 SQL 操作、构建 API 以及创建数据库副本。Turso 简化了边缘分布式数据库的管理，使开发者能够更轻松地为全球用户构建高性能的应用。