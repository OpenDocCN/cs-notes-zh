# 005：JavaScript 基础入门 🚀

![](img/d144928d9b7cd4c460af009d89439950_0.png)

在本节课中，我们将要学习JavaScript的基础知识。JavaScript是前端开发的三大核心技术之一，它让网页从静态的文档变为可以交互的动态应用。我们将从如何在HTML中引入JavaScript开始，逐步学习变量、数据类型、函数、对象等核心概念。

---

## 如何在网页中运行JavaScript？

上一节我们介绍了JavaScript的作用，本节中我们来看看如何在网页中运行它。

与CSS类似，JavaScript可以通过两种方式嵌入到HTML中。

**1. 内联方式：使用 `<script>` 标签**

![](img/d144928d9b7cd4c460af009d89439950_2.png)

你可以直接在HTML文件中使用 `<script>` 标签来编写JavaScript代码。

```html
<!DOCTYPE html>
<html>
<head>
    <title>我的网页</title>
</head>
<body>
    <h1>你好，世界！</h1>
    <script>
        // 这里是JavaScript代码
        console.log("这段代码在控制台运行");
    </script>
</body>
</html>
```

**2. 外部文件方式：使用 `src` 属性**

![](img/d144928d9b7cd4c460af009d89439950_4.png)

![](img/d144928d9b7cd4c460af009d89439950_6.png)

你也可以将JavaScript代码写在一个独立的 `.js` 文件中，然后在HTML中引用它。这有助于保持代码的整洁和可维护性。

```html
<!DOCTYPE html>
<html>
<head>
    <title>我的网页</title>
</head>
<body>
    <h1>你好，世界！</h1>
    <script src="myscript.js"></script>
</body>
</html>
```

![](img/d144928d9b7cd4c460af009d89439950_8.png)

**注意**：`<script>` 标签的位置很重要。如果脚本需要操作页面上的元素（例如，修改 `<body>` 的内容），通常需要将 `<script>` 标签放在 `<body>` 标签的末尾，或者使用 `defer` 等属性，以确保在DOM元素加载完成后再执行脚本。

---

## 变量与常量

现在我们知道如何运行JavaScript了，接下来学习如何存储数据。在JavaScript中，我们使用变量和常量。

声明变量有三种方式：`let`、`const` 和 `var`。

*   **`let`**：用于声明一个**可以重新赋值**的变量。这是现代JavaScript中的推荐用法。
*   **`const`**：用于声明一个**常量**，其值在声明后**不能被重新赋值**。
*   **`var`**：是旧的声明方式，现在已不推荐使用。它与 `let` 在作用域上有细微差别。

以下是声明变量的示例：

```javascript
let myVariable = 10; // 可以改变
myVariable = 20; // 正确

const myConstant = 42; // 不可以改变
// myConstant = 50; // 错误！会报错

var oldVariable = "过时了"; // 避免使用
```

**命名约定**：变量名通常使用**驼峰命名法**，例如 `myVariableName`。

---

## 数据类型与运算符

变量可以存储不同类型的数据。JavaScript是一种“动态类型”语言，这意味着你不需要提前声明变量的类型。

以下是主要的数据类型：

*   **数字**：整数或小数，例如 `42`， `3.14`。
*   **字符串**：文本，用单引号 `‘’` 或双引号 `“”` 包裹，例如 `‘Hello’`。
*   **布尔值**：`true` 或 `false`。
*   **对象**：用于存储键值对的集合，我们稍后会详细讲解。
*   **数组**：用于存储有序的元素列表，我们稍后会详细讲解。
*   **Undefined**：表示变量已声明但未赋值。
*   **Null**：表示一个空值。

JavaScript可以自动在不同类型之间转换，这有时很方便，但有时也会导致意想不到的结果。

```javascript
let myNumber = 42;
let myString = “答案是：” + myNumber; // JavaScript 将数字转换为字符串并拼接
console.log(myString); // 输出：“答案是：42”

let result = “5” - 3; // JavaScript 将字符串“5”转换为数字5
console.log(result); // 输出：2
```

**比较运算符**：比较两个值时，建议使用**严格相等** `===` 和**严格不相等** `!==`。它们会同时比较值和数据类型。

```javascript
console.log(5 == “5”); // true (宽松相等，只比较值)
console.log(5 === “5”); // false (严格相等，比较值和类型)
```

---

## 控制流：条件与循环

有了数据和变量，我们就可以让程序做决策和重复任务了。控制流语句和Python非常相似。

**条件语句 (if...else)**

使用 `if`、`else if` 和 `else` 来根据条件执行不同的代码块。代码块用花括号 `{}` 包裹。

```javascript
let score = 85;

if (score >= 90) {
    console.log(“优秀！”);
} else if (score >= 60) {
    console.log(“及格！”);
} else {
    console.log(“不及格！”);
}
```

**循环语句 (for, while)**

`for` 循环和 `while` 循环用于重复执行代码。

```javascript
// for 循环
for (let i = 0; i < 5; i++) {
    console.log(“循环次数：” + i);
}

![](img/d144928d9b7cd4c460af009d89439950_10.png)

// while 循环
let count = 0;
while (count < 3) {
    console.log(“计数：” + count);
    count++; // count = count + 1 的简写
}
```

![](img/d144928d9b7cd4c460af009d89439950_12.png)

---

## 函数

函数是一段可重复使用的代码块。在JavaScript中，定义函数有几种方式。

![](img/d144928d9b7cd4c460af009d89439950_14.png)

**1. 函数声明**

使用 `function` 关键字。

![](img/d144928d9b7cd4c460af009d89439950_16.png)

```javascript
function greet(name) {
    return “你好， ” + name + “!”;
}
let message = greet(“小明”);
console.log(message); // 输出：“你好， 小明！”
```

**2. 函数表达式 (包括箭头函数)**

你可以将函数赋值给一个变量。箭头函数 `=>` 是更简洁的写法。

```javascript
// 函数表达式
const greet = function(name) {
    return “你好， ” + name + “!”;
};

// 箭头函数 (更简洁)
const greetArrow = (name) => {
    return “你好， ” + name + “!”;
};

// 如果函数体只有一行返回语句，可以省略花括号和 return
const greetShort = name => “你好， ” + name + “!”;
```

函数是“一等公民”，意味着可以像变量一样被传递和赋值，这非常强大。

![](img/d144928d9b7cd4c460af009d89439950_18.png)

---

![](img/d144928d9b7cd4c460af009d89439950_20.png)

![](img/d144928d9b7cd4c460af009d89439950_22.png)

## 对象与JSON

![](img/d144928d9b7cd4c460af009d89439950_24.png)

![](img/d144928d9b7cd4c460af009d89439950_26.png)

对象是JavaScript中最重要的概念之一。它用于存储一组相关的数据和功能。

**创建与访问对象**

![](img/d144928d9b7cd4c460af009d89439950_28.png)

对象由花括号 `{}` 定义，内部包含 `键: 值` 对。

![](img/d144928d9b7cd4c460af009d89439950_30.png)

![](img/d144928d9b7cd4c460af009d89439950_32.png)

![](img/d144928d9b7cd4c460af009d89439950_34.png)

```javascript
let person = {
    name: “张三”,
    age: 25,
    isStudent: true,
    greet: function() {
        console.log(“大家好，我是” + this.name);
    }
};

// 访问属性：点号表示法 或 方括号表示法
console.log(person.name); // “张三”
console.log(person[“age”]); // 25

// 调用方法
person.greet(); // “大家好，我是张三”
```

**JSON**

![](img/d144928d9b7cd4c460af009d89439950_36.png)

![](img/d144928d9b7cd4c460af009d89439950_38.png)

JSON是一种轻量级的数据交换格式，它基于JavaScript对象的语法，但要求键名必须用双引号 `“”` 包裹。

```javascript
// JavaScript 对象
let jsObject = { name: “李四”, age: 30 };

// 转换为 JSON 字符串
let jsonString = JSON.stringify(jsObject);
console.log(jsonString); // 输出：{“name”:”李四”,”age”:30} (字符串)

![](img/d144928d9b7cd4c460af009d89439950_40.png)

![](img/d144928d9b7cd4c460af009d89439950_41.png)

// 将 JSON 字符串解析回 JavaScript 对象
let parsedObject = JSON.parse(jsonString);
console.log(parsedObject.name); // “李四”
```

![](img/d144928d9b7cd4c460af009d89439950_43.png)

JSON是前后端通信中最常用的数据格式。

![](img/d144928d9b7cd4c460af009d89439950_45.png)

---

![](img/d144928d9b7cd4c460af009d89439950_47.png)

## 数组

![](img/d144928d9b7cd4c460af009d89439950_49.png)

![](img/d144928d9b7cd4c460af009d89439950_51.png)

数组用于在单个变量中存储多个值的有序列表。

![](img/d144928d9b7cd4c460af009d89439950_52.png)

![](img/d144928d9b7cd4c460af009d89439950_54.png)

![](img/d144928d9b7cd4c460af009d89439950_56.png)

```javascript
let fruits = [“苹果”, “香蕉”, “橙子”];

// 访问元素 (索引从0开始)
console.log(fruits[0]); // “苹果”

// 修改元素
fruits[1] = “葡萄”;

// 数组长度
console.log(fruits.length); // 3

// 添加元素到末尾
fruits.push(“芒果”);

// 遍历数组
for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
}
```

数组和对象可以嵌套使用，以构建复杂的数据结构。

---

## 扩展运算符与复制

扩展运算符 `...` 是ES6引入的一个非常实用的语法，它可以“展开”数组或对象。

**用于数组**

![](img/d144928d9b7cd4c460af009d89439950_58.png)

```javascript
let arr1 = [1, 2, 3];
let arr2 = […arr1, 4, 5]; // 将arr1的元素展开，并添加新元素
console.log(arr2); // [1, 2, 3, 4, 5]
```

![](img/d144928d9b7cd4c460af009d89439950_60.png)

**用于对象 (浅拷贝)**

扩展运算符可以方便地复制或合并对象。注意，这创建的是**浅拷贝**。

```javascript
let original = { a: 1, b: 2 };
let copy = { …original }; // 复制 original 的所有属性
copy.a = 99;
console.log(original.a); // 1 (原对象未受影响)
console.log(copy.a); // 99

![](img/d144928d9b7cd4c460af009d89439950_62.png)

// 合并对象
let defaults = { theme: “dark”, volume: 80 };
let userSettings = { volume: 50 };
let finalSettings = { …defaults, …userSettings };
// userSettings 会覆盖 defaults 中的同名属性
console.log(finalSettings); // { theme: “dark”, volume: 50 }
```

**重要概念：浅拷贝 vs 深拷贝**

*   **浅拷贝**：只复制对象的第一层属性。如果属性值是另一个对象（嵌套对象），则复制的是该对象的**引用**，而不是对象本身。修改嵌套对象会影响所有引用它的变量。
*   **深拷贝**：完全复制整个对象结构，包括所有嵌套对象。修改拷贝后的对象不会影响原对象。

![](img/d144928d9b7cd4c460af009d89439950_64.png)

使用 `JSON.stringify()` 和 `JSON.parse()` 可以快速实现一个简单的深拷贝，但它有局限性（例如，不能处理函数、`undefined`等）。

```javascript
let complexObj = { a: 1, nested: { b: 2 } };
let deepCopy = JSON.parse(JSON.stringify(complexObj));
deepCopy.nested.b = 999;
console.log(complexObj.nested.b); // 2 (原对象未受影响)
```

---

![](img/d144928d9b7cd4c460af009d89439950_66.png)

## 与网页交互初步

![](img/d144928d9b7cd4c460af009d89439950_68.png)

最后，让我们看看JavaScript如何与网页内容互动。`document` 对象代表了整个HTML文档，通过它可以访问和修改页面元素。

![](img/d144928d9b7cd4c460af009d89439950_70.png)

```javascript
// 修改整个<body>内部的HTML
document.body.innerHTML = “<h1>页面内容被JS改变了！</h1>”;

// 弹出对话框
alert(“这是一个警告框！”); // 显示信息
let userName = prompt(“请输入你的名字：”); // 获取用户输入
let isOK = confirm(“你确定要删除吗？”); // 确认取消选择
```

这些只是基础操作，在后续课程中，我们将学习更精细、更强大的DOM操作方法。

---

![](img/d144928d9b7cd4c460af009d89439950_72.png)

本节课中我们一起学习了JavaScript的基础知识，包括如何将其引入网页、声明变量、使用各种数据类型和运算符、编写控制流语句和函数、以及操作对象、数组和JSON。我们还初步了解了如何用JavaScript与网页进行简单交互。JavaScript是一门功能强大且应用广泛的语言，掌握这些基础是构建动态网页和复杂Web应用的第一步。