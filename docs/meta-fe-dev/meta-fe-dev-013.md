# Meta前端开发课程：P13：嵌入JSX表达式 🧩

在本节课中，我们将学习JSX的一个核心特性：嵌入表达式。我们将了解JSX如何允许开发者在HTML代码中直接使用JavaScript变量、函数调用和表达式，从而动态地构建React元素。

---

## JSX基础回顾

上一节我们介绍了JSX是JavaScript的语法扩展，它允许开发者在React组件代码中编写HTML。本节中，我们来看看JSX如何将HTML代码自动转换为React元素。

一个基本的JSX示例如下，它会在网页上输出“Hello world”文本：

```jsx
const result = <p>Hello world</p>;
```

这段代码将一个包含短语“Hello world”的段落HTML元素，赋值给名为`result`的常量变量。当此JSX代码执行时，`result`变量将包含一个可以插入到网页中的React元素。这是JSX的关键特性之一：**自动从HTML代码构建React元素**。

---

## 嵌入表达式

![](img/c3ce7792f7c3515f58a1ff2ceb3bf975_1.png)

现在，让我们探索JSX的另一个重要特性：**嵌入表达式**。

![](img/c3ce7792f7c3515f58a1ff2ceb3bf975_3.png)

嵌入表达式允许开发者将JavaScript变量的值插入到最终React元素的HTML中。表达式被包裹在花括号`{}`中。

以下是嵌入表达式的几种常见用法：

### 1. 嵌入变量值

你可以直接在JSX中输出一个变量的值。

```jsx
const name = 'John';
const greeting = <p>Hello, {name}</p>;
```

### 2. 嵌入函数调用

嵌入表达式也可以嵌入函数的输出结果。假设你需要以特定格式输出人名，可以创建一个格式化函数，然后在JSX的花括号内调用它。

```jsx
function formatName(firstName, lastName) {
  return firstName + ' ' + lastName;
}

const user = { firstName: 'Jane', lastName: 'Doe' };
const element = <h1>Hello, {formatName(user.firstName, user.lastName)}!</h1>;
```

与之前的例子一样，函数为JavaScript变量生成的值将被输出到HTML中。

![](img/c3ce7792f7c3515f58a1ff2ceb3bf975_5.png)

![](img/c3ce7792f7c3515f58a1ff2ceb3bf975_6.png)

### 3. 在HTML属性中使用表达式

![](img/c3ce7792f7c3515f58a1ff2ceb3bf975_7.png)

表达式同样可以用于HTML属性。这在需要动态插入内容时非常有用，例如插入个人资料图片的地址。

以下是具体步骤：
首先，将图片地址存储在一个名为`url`的变量中。图片将使用`<img>`元素显示，因此你需要将`url`变量嵌入到`src`属性中。

```jsx
const url = 'https://example.com/profile.jpg';
const profileImg = <img src={url} alt="Profile" />;
```

请注意，属性值不需要双引号，因为JSX会自动处理这些。

![](img/c3ce7792f7c3515f58a1ff2ceb3bf975_9.png)

---

## 总结

本节课中，我们一起学习了JSX嵌入表达式的强大功能。我们了解到，通过使用花括号`{}`，可以在JSX中：

*   直接插入**JavaScript变量**的值。
*   执行并插入**函数调用**的结果。
*   动态设置**HTML元素的属性**（如`src`）。

这只是JSX作为一种高效输出包含JavaScript变量内容的HTML元素方式的其中一个例子。随着学习的深入，你将会遇到更多应用场景。掌握嵌入表达式是编写动态、交互式React组件的基础。