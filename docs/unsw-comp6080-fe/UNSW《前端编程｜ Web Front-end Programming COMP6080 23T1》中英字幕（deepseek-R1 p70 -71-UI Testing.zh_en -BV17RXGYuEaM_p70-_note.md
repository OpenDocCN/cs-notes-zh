# 前端编程：COMP6080：UI测试入门 🧪

![](img/6e4bae155f2baed27a50327310d6a174_1.png)

在本节课中，我们将学习如何使用Cypress进行端到端（E2E）UI测试。我们将通过一个具体的示例，编写一个“快乐路径”测试，涵盖从导航到主页、成功登录、上传文件到成功退出的完整用户流程。课程内容将基于UNSW COMP6080课程的相关知识进行扩展。

---

## 概述

我们将创建一个模拟的Web应用，并为其编写Cypress测试。测试的主要目标是验证以下核心用户操作序列（即“快乐路径”）能否正确执行：
1.  导航到主页。
2.  成功登录。
3.  成功上传文件。
4.  成功退出。

我们将逐步构建测试代码，并解释每个步骤的作用。

![](img/6e4bae155f2baed27a50327310d6a174_3.png)

---

## 准备演示应用

在深入代码之前，我们首先需要一个用于测试的Web应用。这个演示应用包含以下页面和功能：
*   **主页** (`/`): 包含一个导航栏和一个“登录”按钮。
*   **登录页** (`/login`): 包含一个表单，有`email`和`password`输入框以及一个`submit`提交按钮。
*   **仪表盘页** (`/dashboard`): 登录后显示，包含一个用于上传文件的`input`（`name="your-image"`）和一个“退出”按钮。成功上传图片后，会显示一个图片预览（`img`标签，`name="image-preview"`）。

![](img/6e4bae155f2baed27a50327310d6a174_5.png)

为方便Cypress选择元素，我们已为所有关键交互元素（如按钮、输入框）设置了`name`属性。

---

![](img/6e4bae155f2baed27a50327310d6a174_7.png)

## 安装与配置Cypress

![](img/6e4bae155f2baed27a50327310d6a174_9.png)

首先，我们需要在项目中安装Cypress。如果你的项目尚未安装，可以使用以下命令：

```bash
yarn add cypress
```

安装完成后，为了方便启动Cypress，可以在`package.json`文件的`scripts`部分添加一个快捷命令：

![](img/6e4bae155f2baed27a50327310d6a174_11.png)

![](img/6e4bae155f2baed27a50327310d6a174_12.png)

```json
{
  "scripts": {
    "cypress:open": "cypress open"
  }
}
```

现在，你可以通过运行 `yarn cypress:open` 来启动Cypress测试运行器。

![](img/6e4bae155f2baed27a50327310d6a174_14.png)

当你首次运行此命令时，Cypress会进行初始化配置，并创建 `cypress` 目录及其默认文件结构。

![](img/6e4bae155f2baed27a50327310d6a174_16.png)

在Cypress测试运行器界面中，选择“E2E Testing”并选择一个浏览器（**推荐使用Chrome，因为这是评分时的默认浏览器**）。然后，你可以创建一个新的测试文件，例如将其命名为 `userFlow.cy.js`。

![](img/6e4bae155f2baed27a50327310d6a174_18.png)

---

![](img/6e4bae155f2baed27a50327310d6a174_20.png)

![](img/6e4bae155f2baed27a50327310d6a174_21.png)

## 编写“快乐路径”测试

![](img/6e4bae155f2baed27a50327310d6a174_23.png)

上一节我们配置好了Cypress环境，本节中我们来看看如何编写具体的测试用例。我们将在一个 `describe` 代码块中定义我们的测试套件。

![](img/6e4bae155f2baed27a50327310d6a174_25.png)

以下是完整的测试步骤，我们将逐一拆解：

```javascript
describe('用户流程测试', () => {
  it('应成功完成登录、上传和退出流程', () => {
    // 测试步骤将在这里编写
  });
});
```

![](img/6e4bae155f2baed27a50327310d6a174_27.png)

### 步骤 1: 访问主页并验证URL

![](img/6e4bae155f2baed27a50327310d6a174_29.png)

每个测试开始时，我们首先需要导航到应用的起始URL。

```javascript
cy.visit('http://localhost:3000');
cy.url().should('eq', 'http://localhost:3000/');
```

*   `cy.visit()` 命令用于访问指定的URL。
*   `cy.url().should()` 是一个断言，用于检查当前URL是否与预期一致。

### 步骤 2: 导航到登录页面

接下来，我们需要点击主页上的“登录”按钮，跳转到登录页。

![](img/6e4bae155f2baed27a50327310d6a174_31.png)

![](img/6e4bae155f2baed27a50327310d6a174_33.png)

```javascript
cy.get('button[name="login-button"]').click();
cy.url().should('include', '/login');
```

![](img/6e4bae155f2baed27a50327310d6a174_35.png)

*   `cy.get()` 命令通过CSS选择器（这里使用了属性选择器 `[name="..."]`）来获取DOM元素。
*   `.click()` 命令模拟用户点击操作。
*   我们再次使用 `cy.url().should()` 来断言当前URL包含 `/login` 路径。

![](img/6e4bae155f2baed27a50327310d6a174_37.png)

### 步骤 3: 填写表单并成功登录

现在，我们需要在登录表单中填写信息并提交。

```javascript
cy.get('input[name="email"]').focus().type('example@email.com');
cy.get('input[name="password"]').focus().type('password123');
cy.get('button[name="submit"]').click();
cy.url().should('eq', 'http://localhost:3000/dashboard');
```

*   `.focus()` 命令将焦点置于输入框。
*   `.type()` 命令用于模拟键盘输入，向输入框填入文本。
*   填写完成后，找到提交按钮并点击。
*   断言页面成功跳转至仪表盘 (`/dashboard`)。

![](img/6e4bae155f2baed27a50327310d6a174_39.png)

### 步骤 4: 成功上传文件

![](img/6e4bae155f2baed27a50327310d6a174_41.png)

![](img/6e4bae155f2baed27a50327310d6a174_43.png)

登录后，在仪表盘页面上传一个图片文件。

![](img/6e4bae155f2baed27a50327310d6a174_45.png)

```javascript
cy.get('input[name="your-image"]').selectFile('cypress/assets/cute-cat.jpg');
```

*   `.selectFile()` 是Cypress提供的便捷命令，用于处理文件上传。它接收一个相对于项目根目录的文件路径。

![](img/6e4bae155f2baed27a50327310d6a174_47.png)

**处理异步渲染**：有时，文件上传后，前端需要时间处理并渲染预览图。如果测试立刻断言图片存在，可能会因为渲染未完成而失败。为了解决这个问题，我们需要使用 `cy.wait()` 命令。

```javascript
// 在上传命令后，等待一段时间让UI更新
cy.wait(6000); // 等待6秒
// 然后断言预览图片存在且可见
cy.get('img[name="image-preview"]').should('be.visible');
```

![](img/6e4bae155f2baed27a50327310d6a174_49.png)

*   `cy.wait(6000)` 会使测试暂停6000毫秒（6秒），等待可能的异步操作（如API调用、图片处理）完成。
*   等待之后，我们再断言名为 `image-preview` 的图片元素应该处于可见状态。

### 步骤 5: 成功退出系统

最后，我们点击退出按钮，并验证是否返回主页。

```javascript
cy.get('button[name="logout-button"]').click();
cy.url().should('eq', 'http://localhost:3000/');
```

![](img/6e4bae155f2baed27a50327310d6a174_51.png)

---

## 运行与验证测试

将以上所有步骤组合到 `it` 代码块中，就构成了完整的“快乐路径”测试。在Cypress测试运行器中打开对应的测试文件（如 `userFlow.cy.js`），Cypress将自动执行测试。

你会看到Cypress模拟一个浏览器，逐步执行你的每一个命令：访问页面、点击按钮、输入文本、上传文件。所有断言（`should`）如果通过，测试则显示为绿色；如果有任何一步失败（例如元素未找到、URL不匹配、超时），测试将停止并报告错误。

![](img/6e4bae155f2baed27a50327310d6a174_53.png)

---

## 总结

![](img/6e4bae155f2baed27a50327310d6a174_55.png)

本节课中我们一起学习了如何使用Cypress进行端到端UI测试。我们重点掌握了：

1.  **环境搭建**：安装Cypress并配置测试脚本。
2.  **测试结构**：使用 `describe` 和 `it` 组织测试套件和用例。
3.  **核心命令**：
    *   `cy.visit()` 用于导航。
    *   `cy.get()` 用于选择元素。
    *   `.click()`, `.type()`, `.selectFile()` 用于模拟用户交互。
    *   `.should()` 用于添加断言，验证应用状态。
4.  **处理异步**：使用 `cy.wait()` 命令处理需要等待的UI更新或网络请求，防止测试因超时而失败。
5.  **“快乐路径”测试**：编写了一个完整的流程测试，模拟了用户从访问到退出的关键操作。

![](img/6e4bae155f2baed27a50327310d6a174_57.png)

![](img/6e4bae155f2baed27a50327310d6a174_59.png)

通过为关键HTML元素设置清晰的 `name` 属性，可以让我们更稳定、更易读地编写选择器，这是编写健壮E2E测试的一个良好实践。