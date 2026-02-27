# 025：NodeJS 演示教程 🚀

![](img/9b2334de6b7bce29a33363e7b68f3198_0.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_2.png)

在本节课中，我们将通过两个具体的编程演示，学习如何在 NodeJS 环境中使用 JavaScript。我们将了解如何读取命令行参数、处理日期、使用外部库、读写文件，以及如何创建一个简单的 HTTP 服务器。

上一节我们介绍了课程的整体结构和本周的学习目标，本节中我们来看看具体的 NodeJS 演示。

![](img/9b2334de6b7bce29a33363e7b68f3198_4.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_5.png)

## 演示一：处理日期并输出 JSON 文件

在这个演示中，我们将编写一个 NodeJS 脚本，从命令行读取日期，计算这些日期距今的天数，并将结果以 JSON 格式保存到文件中。

### 步骤 1：设置项目与读取命令行参数

![](img/9b2334de6b7bce29a33363e7b68f3198_7.png)

首先，我们需要创建一个 NodeJS 项目并读取从命令行传入的参数。

![](img/9b2334de6b7bce29a33363e7b68f3198_9.png)

以下是创建项目并读取 `process.argv` 的代码示例：

![](img/9b2334de6b7bce29a33363e7b68f3198_11.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_13.png)

```javascript
// hello.js
const process = require('process');
const argv = process.argv;

![](img/9b2334de6b7bce29a33363e7b68f3198_15.png)

let dates = [];
for (let i = 2; i < argv.length; i++) {
    dates.push(argv[i]);
}
console.log(dates);
```

![](img/9b2334de6b7bce29a33363e7b68f3198_17.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_19.png)

运行脚本时，`process.argv` 的前两个元素是 NodeJS 执行路径和脚本文件路径，因此我们从索引 2 开始读取用户输入的日期。

### 步骤 2：计算日期差

接下来，我们需要计算每个输入日期距离今天的天数。我们将使用一个名为 `date-fns` 的库来简化日期计算。

首先，安装 `date-fns` 库：

```bash
npm install date-fns
```

然后，在脚本中使用它来计算天数差：

![](img/9b2334de6b7bce29a33363e7b68f3198_21.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_23.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_25.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_26.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_28.png)

```javascript
const { differenceInCalendarDays } = require('date-fns');

let dateDaysSincePairs = {};
for (let dateStr of dates) {
    let targetDate = new Date(dateStr);
    let daysBetween = differenceInCalendarDays(new Date(), targetDate);
    dateDaysSincePairs[dateStr] = daysBetween;
}
console.log(dateDaysSincePairs);
```

![](img/9b2334de6b7bce29a33363e7b68f3198_30.png)

这段代码遍历日期数组，为每个日期计算与当前日期的日历天数差，并将结果存储在一个对象中。

![](img/9b2334de6b7bce29a33363e7b68f3198_32.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_34.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_36.png)

### 步骤 3：将结果写入 JSON 文件

最后，我们需要将包含日期和天数差的对象写入一个 JSON 文件。我们将使用 NodeJS 内置的 `fs`（文件系统）模块。

以下是写入文件的代码：

![](img/9b2334de6b7bce29a33363e7b68f3198_38.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_40.png)

```javascript
const fs = require('fs');

![](img/9b2334de6b7bce29a33363e7b68f3198_42.png)

let jsonOutput = JSON.stringify(dateDaysSincePairs);
fs.writeFileSync('dates.json', jsonOutput);
console.log('数据已写入 dates.json 文件。');
```

`JSON.stringify()` 方法将 JavaScript 对象转换为 JSON 字符串，然后 `fs.writeFileSync` 将其同步写入文件。

![](img/9b2334de6b7bce29a33363e7b68f3198_44.png)

上一节我们完成了第一个演示，学会了基本的文件操作和库的使用。本节中我们来看看第二个更复杂的演示：创建一个简单的 HTTP 服务器。

## 演示二：创建简单的 HTTP 服务器

![](img/9b2334de6b7bce29a33363e7b68f3198_46.png)

在这个演示中，我们将使用 Express 框架创建一个 HTTP 服务器。该服务器将提供一个 `/scrape` 路由，用于接收 URL 和 HTML 标签，并返回该标签在指定网页中出现的次数。

![](img/9b2334de6b7bce29a33363e7b68f3198_48.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_50.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_52.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_54.png)

### 步骤 1：设置 Express 服务器

![](img/9b2334de6b7bce29a33363e7b68f3198_56.png)

首先，创建一个新的文件（如 `server.js`）并初始化一个 Express 应用。

![](img/9b2334de6b7bce29a33363e7b68f3198_58.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_60.png)

安装 Express 框架：

![](img/9b2334de6b7bce29a33363e7b68f3198_62.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_64.png)

```bash
npm install express
```

![](img/9b2334de6b7bce29a33363e7b68f3198_66.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_68.png)

创建基本的服务器代码：

![](img/9b2334de6b7bce29a33363e7b68f3198_70.png)

```javascript
// server.js
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => {
    res.send('Hello World!');
});

![](img/9b2334de6b7bce29a33363e7b68f3198_72.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_74.png)

app.listen(port, () => {
    console.log(`服务器运行在 http://localhost:${port}`);
});
```

![](img/9b2334de6b7bce29a33363e7b68f3198_76.png)

运行 `node server.js` 后，访问 `http://localhost:3000` 将会看到 “Hello World!”。

![](img/9b2334de6b7bce29a33363e7b68f3198_78.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_79.png)

### 步骤 2：创建 `/scrape` 路由并获取查询参数

![](img/9b2334de6b7bce29a33363e7b68f3198_81.png)

我们需要创建一个 `/scrape` 路由，它通过 URL 查询参数接收 `url` 和 `tag`。

![](img/9b2334de6b7bce29a33363e7b68f3198_83.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_84.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_86.png)

以下是捕获查询参数的代码：

![](img/9b2334de6b7bce29a33363e7b68f3198_88.png)

```javascript
app.get('/scrape', (req, res) => {
    const url = req.query.url;
    const tag = req.query.tag;
    console.log(`URL: ${url}, Tag: ${tag}`);
    // 暂时返回一个模拟的计数
    res.json({ count: 5 });
});
```

![](img/9b2334de6b7bce29a33363e7b68f3198_90.png)

现在，访问 `http://localhost:3000/scrape?url=https://example.com&tag=div` 将会在服务器终端打印出 URL 和标签，并返回 `{"count":5}`。

![](img/9b2334de6b7bce29a33363e7b68f3198_92.png)

### 步骤 3：获取网页内容并统计标签

![](img/9b2334de6b7bce29a33363e7b68f3198_94.png)

为了真实地统计标签，我们需要获取指定 URL 的网页内容。我们将使用 `sync-request` 库来同步地获取网页 HTML。

![](img/9b2334de6b7bce29a33363e7b68f3198_96.png)

安装 `sync-request` 库：

![](img/9b2334de6b7bce29a33363e7b68f3198_98.png)

```bash
npm install sync-request
```

![](img/9b2334de6b7bce29a33363e7b68f3198_100.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_102.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_104.png)

然后，在路由中获取网页内容并统计标签出现次数：

```javascript
const request = require('sync-request');

app.get('/scrape', (req, res) => {
    const url = req.query.url;
    const tag = req.query.tag.toLowerCase(); // 转换为小写以统一处理

    // 获取网页内容
    const response = request('GET', url);
    const allHtml = response.getBody('utf8').toLowerCase();

    // 简单的统计方法：通过分割字符串来计数
    // 注意：这种方法不完美，仅用于演示
    const count = (allHtml.split(`<${tag}`).length - 1) + (allHtml.split(`<${tag} `).length - 1);

    res.json({ count: count });
});
```

![](img/9b2334de6b7bce29a33363e7b68f3198_106.png)

这段代码获取网页的 HTML 内容，将其转换为小写，然后通过计算特定字符串（如 `<div` 或 `<div `）出现的次数来估算标签数量。请注意，这种方法在遇到复杂或格式不规范的 HTML 时可能不准确，但它演示了基本的思路。

## 总结

![](img/9b2334de6b7bce29a33363e7b68f3198_108.png)

![](img/9b2334de6b7bce29a33363e7b68f3198_110.png)

本节课中我们一起学习了 NodeJS 的两个核心应用演示。

![](img/9b2334de6b7bce29a33363e7b68f3198_112.png)

在第一个演示中，我们：
*   读取了命令行参数。
*   使用 `date-fns` 库进行日期计算。
*   将 JavaScript 对象转换为 JSON 并写入文件。

在第二个演示中，我们：
*   使用 Express 框架创建了一个 HTTP 服务器。
*   定义了路由并处理了查询参数。
*   使用 `sync-request` 库获取了远程网页内容。
*   实现了一个简单（但不完美）的 HTML 标签计数器。

这些练习帮助你熟悉了在终端环境中使用 JavaScript 的基本流程，包括项目初始化、包管理、使用外部库以及处理输入输出。虽然第二个演示中的服务器功能在本次前端课程中不会直接用到，但它有助于你理解 Web 应用前后端交互的基本原理。接下来，请继续学习本周关于 Web JavaScript 的预录课程，为完成作业打下坚实基础。