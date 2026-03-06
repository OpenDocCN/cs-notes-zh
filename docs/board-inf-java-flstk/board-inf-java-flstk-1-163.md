# 163：模板驱动表单入门教程 🚀

## 概述
在本节课中，我们将学习 Angular 中的模板驱动表单。这是一种通过 HTML 模板中的指令来创建和管理表单的简单方法。我们将通过一个具体示例，逐步了解如何构建一个包含基本验证和提交功能的表单。

---

## 模板驱动表单简介
上一节我们介绍了 Angular 表单的基本概念。本节中，我们来看看模板驱动表单的具体实现方式。

模板驱动表单提供了一种声明式的方法来处理表单。它依赖于 HTML 模板中的指令来创建和管理表单控件。

以下是创建模板驱动表单的主要步骤：

### 第一步：导入必要模块
首先，需要在模块中导入 `FormsModule`。这个模块提供了模板驱动表单所需的核心指令。

```typescript
// 在 AppModule 中
import { FormsModule } from '@angular/forms';

@NgModule({
  imports: [
    FormsModule // 导入 FormsModule
  ]
})
```

### 第二步：在模板中创建表单结构
接下来，在组件的 HTML 模板中构建表单。使用 `<form>` 元素包裹所有表单控件，并使用 `ngModel` 等指令将控件绑定到组件属性。

![](img/8230b0349837d5bfa0526eb880621bca_1.png)

### 第三步：添加表单验证
可以为表单控件添加验证规则。可以使用 HTML 原生属性（如 `required`、`minlength`）或 Angular 指令来定义验证。

### 第四步：处理表单提交
将表单的 `ngSubmit` 事件绑定到组件中的一个方法，以处理表单提交逻辑。

### 第五步：访问表单数据和验证状态
通过 `ngModel` 指令，可以在组件中访问和操作表单数据，以及检查控件的验证状态。

---

## 实战示例：创建一个用户信息表单
现在，让我们通过一个具体示例来实践上述步骤。我们将创建一个包含“姓名”和“邮箱”字段的简单表单。

### 1. 准备项目与模块
确保已在项目的根模块（通常是 `AppModule`）中正确导入了 `FormsModule`。

### 2. 编写 HTML 模板
在组件的 HTML 文件中，我们构建表单结构。

```html
<form (ngSubmit)="submitForm()">
  <!-- 姓名字段 -->
  <label for="name">姓名</label>
  <input type="text" id="name" name="name" [(ngModel)]="user.name" required>

  <!-- 邮箱字段 -->
  <label for="email">邮箱</label>
  <input type="email" id="email" name="email" [(ngModel)]="user.email" required>

  <!-- 提交按钮 -->
  <button type="submit">提交</button>
</form>
```

![](img/8230b0349837d5bfa0526eb880621bca_3.png)

**代码解释：**
*   `(ngSubmit)=“submitForm()”`：将表单的提交事件绑定到组件的 `submitForm` 方法。
*   `[(ngModel)]=“user.name”`：使用“双向数据绑定”将输入框的值与组件中的 `user.name` 属性同步。
*   `required`：HTML5 属性，表示该字段为必填项。

### 3. 编写组件逻辑
在组件的 TypeScript 文件中，定义数据模型和处理提交的方法。

![](img/8230b0349837d5bfa0526eb880621bca_5.png)

```typescript
import { Component } from '@angular/core';

![](img/8230b0349837d5bfa0526eb880621bca_7.png)

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  // 定义用户对象，用于绑定表单数据
  user = {
    name: '',
    email: ''
  };

  // 处理表单提交的方法
  submitForm() {
    console.log('表单已提交', this.user);
    // 这里可以添加将数据发送到服务器的逻辑
  }
}
```

### 4. 运行与测试
保存所有文件后，应用将自动重新加载。在浏览器中：
1.  你会看到一个包含两个输入框和一个按钮的表单。
2.  尝试不填写任何内容直接点击“提交”，浏览器会阻止提交并提示必填字段。
3.  填写“姓名”（如：John）和“邮箱”（如：john@email.com）后点击“提交”。
4.  打开浏览器的开发者工具（Console 标签页），你将看到打印出的消息：“表单已提交”以及包含输入数据的 `user` 对象。

![](img/8230b0349837d5bfa0526eb880621bca_9.png)

---

![](img/8230b0349837d5bfa0526eb880621bca_11.png)

## 核心概念总结
*   **`FormsModule`**：必须导入此模块才能使用模板驱动表单功能。
*   **`ngModel` 指令**：实现表单控件与组件属性之间的**双向数据绑定**。语法为 `[(ngModel)]=“propertyName”`。
*   **`ngSubmit` 事件**：用于捕获表单提交事件，并触发组件中指定的处理方法。
*   **模板驱动表单的特点**：逻辑主要写在 HTML 模板中，适合**结构简单、验证逻辑不复杂**的表单场景。

---

## 总结
本节课中，我们一起学习了 Angular 模板驱动表单的创建过程。我们从导入 `FormsModule` 开始，然后在模板中使用 `form`、`input` 标签及 `ngModel`、`ngSubmit` 等指令构建了一个具有基本验证功能的表单，最后在组件中定义了数据模型和处理提交的方法。模板驱动表单以其直观、声明式的方式，为构建简单表单提供了极大的便利。

![](img/8230b0349837d5bfa0526eb880621bca_13.png)

在下一节视频中，我们将了解另一种更强大、更适合复杂场景的表单处理方式——响应式表单。