# 前端编程：2.1：🌏 包管理

在本节课中，我们将要学习包管理。这是项目管理和协作开发中的核心概念。我们将了解为什么需要包管理器，如何使用 NPM（Node Package Manager）来安装和管理他人编写的代码库，以及如何确保团队成员之间的开发环境一致。

---

上一节我们介绍了前端开发的基础，本节中我们来看看如何高效地使用和管理外部代码库。

## 为什么需要包管理？

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_1.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_2.png)

在编程时，我们经常需要使用他人编写的代码库。例如，在 C 语言中，你可以使用 `#include <stdio.h>` 来引入标准库。然而，在 JavaScript 中，许多有用的库（如验证日期的库）并非预装在计算机上。我们需要一种方法来下载、安装和管理这些外部代码库，并在多台计算机上保持一致性。

## 初识 NPM

NPM（Node Package Manager）是 Node.js 的包管理器。当你安装 Node.js 时，NPM 也会被一同安装。它主要有两个核心功能：
1.  从互联网上的中央仓库（[npmjs.com](https://wwwnpmjs.com)）下载和管理代码包。
2.  通过配置文件记录项目所依赖的包，确保环境可重现。

以下是两个最常用的命令行工具：
*   `node`：用于执行 JavaScript 代码。
*   `npm`：用于管理 JavaScript 模块。

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_4.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_5.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_7.png)

## 一个具体的例子：安装并使用库

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_9.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_11.png)

假设我们需要一个函数来验证日期是否有效。我们可以使用一个名为 `date-fns` 的流行库。

首先，我们尝试直接使用该库中的 `isValid` 函数：

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_13.png)

```javascript
// dates.js
import { isValid } from 'date-fns';

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_15.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_16.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_18.png)

function dateIsValid(year, month, day) {
  return isValid(new Date(year, month, day));
}

console.log(dateIsValid(2023, 13, 1)); // 月份13是无效的
```

如果直接运行 `node dates.js`，你会遇到一个错误：`Cannot find package 'date-fns'`。这是因为 `date-fns` 库还没有被安装到你的项目中。

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_20.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_22.png)

## 创建并配置 NPM 项目

要安装库，你需要先初始化一个 NPM 项目。这会在当前目录下创建一个 `package.json` 文件，它是项目的“蓝图”或“食谱”。

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_24.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_26.png)

1.  创建一个新文件夹并进入：
    ```bash
    mkdir my-project && cd my-project
    ```
2.  初始化 NPM 项目：
    ```bash
    npm init -y
    ```
    `-y` 参数会使用默认值快速生成 `package.json` 文件。
3.  为了让项目支持 `import` 语法，需要在 `package.json` 中添加一行：
    ```json
    {
      "name": "my-project",
      "version": "1.0.0",
      "type": "module", // 添加这一行
      ...
    }
    ```

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_28.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_30.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_32.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_34.png)

## 安装依赖包

现在，我们可以安装 `date-fns` 库了：

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_36.png)

```bash
npm install date-fns
```

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_38.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_40.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_42.png)

执行这个命令后，会发生以下几件事：
1.  NPM 会从 [npmjs.com](https://wwwnpmjs.com) 下载 `date-fns` 库及其所有代码。
2.  这些代码会被保存在项目根目录下的 `node_modules` 文件夹中。这是存放所有“食材”（即下载的库）的地方。
3.  `package.json` 文件中会自动添加一个 `dependencies` 字段，记录了你所安装的包及其版本。

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_44.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_46.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_47.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_49.png)

```json
{
  "name": "my-project",
  "version": "1.0.0",
  "type": "module",
  "dependencies": {
    "date-fns": "^4.4.2"
  }
}
```

现在再次运行 `node dates.js`，代码就能成功执行并输出结果了。

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_51.png)

## 理解关键文件

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_53.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_55.png)

以下是 NPM 项目中的三个关键文件/文件夹：

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_57.png)

1.  **`package.json`**：项目的“食谱”。它列出了项目的基本信息以及所有依赖项，但不包含实际的代码。这个文件**必须**提交到 Git 等版本控制系统中。
2.  **`node_modules`**：项目的“食材仓库”。所有通过 `npm install` 下载的库的实际代码都存储在这里。这个文件夹通常**不**提交到版本控制系统，因为它体积庞大且可以根据 `package.json` 重新生成。
3.  **`package-lock.json`**：版本的“精确快照”。它由 NPM 自动生成，记录了每个依赖包的确切版本号以及它们之间的依赖关系树。这确保了所有团队成员和部署环境安装完全一致的包版本。这个文件**必须**提交到版本控制系统。

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_59.png)

## 团队协作与依赖管理

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_61.png)

`package.json` 和 `package-lock.json` 的强大之处在于确保了环境的一致性。

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_63.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_65.png)

当你的队友克隆了项目代码后，他们只需要运行一个命令：

```bash
npm install
```

NPM 会读取 `package.json` 和 `package-lock.json`，然后自动下载所有指定版本的依赖包到他们本地的 `node_modules` 文件夹中。这样，所有人的开发环境就完全一致了。

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_67.png)

如果你需要安装新库，使用 `npm install <library-name>`。安装后，记得将更新后的 `package.json` 和 `package-lock.json` 提交到代码仓库。

## 自定义脚本

在 `package.json` 的 `scripts` 字段中，你可以定义一些快捷命令。

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_69.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_71.png)

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_73.png)

例如，添加一个运行日期检查的脚本：

```json
{
  "name": "my-project",
  "version": "1.0.0",
  "type": "module",
  "scripts": {
    "check-date": "node dates.js",
    "start": "node index.js"
  },
  "dependencies": {
    "date-fns": "^4.4.2"
  }
}
```

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_75.png)

然后，你可以通过以下命令来运行这些脚本：

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_77.png)

```bash
npm run check-date
npm run start
# `start` 是一个特殊脚本，可以直接用 `npm start` 运行
```

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_79.png)

这在后续设置项目构建、测试等自动化流程时非常有用。

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_81.png)

---

![](img/a9702cfd27d7d2f4b90bf2efed561a1a_83.png)

本节课中我们一起学习了包管理的基础知识。我们了解了为什么需要 NPM，如何创建项目、安装和管理外部依赖库。最重要的是，我们掌握了通过 `package.json` 和 `package-lock.json` 来保证项目环境可重现的方法，这是现代软件开发中团队协作的基石。下一节，我们将探讨如何利用这些工具来构建更复杂的项目。