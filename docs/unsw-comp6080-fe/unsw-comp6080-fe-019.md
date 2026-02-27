# 019：🛠️ Javascript

在本节课中，我们将要学习Javascript编程语言。我们将从学习第二门编程语言的一般方法开始，然后重点探讨Javascript的核心语言特性，特别是它与C语言的区别。我们将涵盖变量、字符串、控制结构、函数以及两种主要的数据结构：数组和对象。

![](img/af879d0ef4b899e7e429a73a844847fb_1.png)

## 为什么学习Javascript？

Javascript是一种高级、多范式、解释型的脚本语言。它之所以重要，是因为它在基于Web的软件工程领域拥有极高的普及度。如今，大多数软件都是基于Web的，而Javascript是构建Web应用程序的通用首选语言。

此外，Javascript拥有极其丰富的开源库和包管理器生态系统，这能帮助你快速构建应用，避免重复造轮子。它是一门高级语言，编写代码非常快捷，在工业界得到了极好的支持，是大型软件工程项目的常见选择。

## 从C到Javascript：核心差异

你已经熟悉了C语言，学习Javascript时，关注两者的差异会很有帮助。以下是主要区别：

![](img/af879d0ef4b899e7e429a73a844847fb_3.png)

*   **编程范式**：C是过程式语言，而Javascript是多范式语言，支持过程式、函数式和面向对象编程。
*   **类型系统**：C是静态类型语言，而Javascript是动态类型语言，变量在声明时无需指定类型。
*   **内存管理**：C涉及指针和手动内存管理（`malloc`/`free`），Javascript是高级语言，无需直接操作内存。
*   **编译与解释**：C是编译型语言，需要单独的编译和运行步骤。Javascript是解释型语言，通常使用Node.js等工具直接解释执行代码，步骤合二为一。

![](img/af879d0ef4b899e7e429a73a844847fb_5.png)

简单来说，Javascript的语法更简洁，开发更便捷，但语言本身感觉更“庞大”，功能也更丰富。

## 运行Javascript代码

在C语言中，你需要使用GCC等编译器将代码编译成可执行文件。在Javascript中，我们通常使用Node.js来运行代码。

Node.js是一个命令行接口，用于解释和执行Javascript代码。运行一个Javascript文件非常简单：

```bash
node 你的文件名.js
```

![](img/af879d0ef4b899e7e429a73a844847fb_7.png)

![](img/af879d0ef4b899e7e429a73a844847fb_8.png)

![](img/af879d0ef4b899e7e429a73a844847fb_9.png)

![](img/af879d0ef4b899e7e429a73a844847fb_11.png)

例如，对于一个简单的打印函数：

```javascript
// compare.js
function minimum(a, b) {
    if (a > b) return b;
    return a;
}
console.log(minimum(3, 5));
```

![](img/af879d0ef4b899e7e429a73a844847fb_13.png)

运行命令 `node compare.js` 将在终端输出 `3`。在Javascript中，`console.log` 相当于C语言中的 `printf`，用于向控制台输出信息，并且它会自动在末尾添加换行符。

![](img/af879d0ef4b899e7e429a73a844847fb_15.png)

## 变量与常量

在Javascript中声明变量时，你需要使用 `let` 或 `const` 关键字，而不是像C那样指定类型（如 `int`, `char`）。

![](img/af879d0ef4b899e7e429a73a844847fb_17.png)

*   `let` 用于声明**可以改变**的变量。
*   `const` 用于声明**不可改变**的常量（注意：对于对象和数组，`const` 保证的是变量指向的引用不变，但对象内部属性或数组元素可以改变）。

```javascript
let changeable = 10; // 这个值以后可以改变
changeable = 20; // 正确

![](img/af879d0ef4b899e7e429a73a844847fb_19.png)

const constantVal = 5; // 这个值不能改变
// constantVal = 6; // 错误！不能给常量赋值

![](img/af879d0ef4b899e7e429a73a844847fb_21.png)

// 对于对象和数组
const myArray = [1, 2, 3];
myArray.push(4); // 正确：修改了数组内容
// myArray = [5, 6, 7]; // 错误：不能改变 myArray 指向的引用

![](img/af879d0ef4b899e7e429a73a844847fb_23.png)

![](img/af879d0ef4b899e7e429a73a844847fb_25.png)

const myObject = { name: 'Alice' };
myObject.age = 25; // 正确：修改了对象属性
// myObject = { name: 'Bob' }; // 错误：不能改变 myObject 指向的引用
```

![](img/af879d0ef4b899e7e429a73a844847fb_27.png)

Javascript中的基本数据类型包括数字、字符串、布尔值，以及两个表示“空”的特殊值：`undefined`（未定义）和 `null`（空值）。

## 字符串操作

Javascript中的字符串操作比C语言简单直观得多。你可以使用加号 `+` 来连接字符串。

![](img/af879d0ef4b899e7e429a73a844847fb_29.png)

```javascript
let greeting = 'Hello';
let name = 'World';
let sentence = greeting + ', ' + name + '!'; // "Hello, World!"
```

![](img/af879d0ef4b899e7e429a73a844847fb_31.png)

更强大的功能是**模板字符串**，它使用反引号 `` ` `` 定义，并允许你在字符串中直接嵌入变量或表达式，语法是 `${变量名}`。

```javascript
const age = 7;
const name = 'Hayden';
// 使用模板字符串
const phrase = `Hello, my name is ${name} and I am ${age}.`;
console.log(phrase); // 输出: Hello, my name is Hayden and I am 7.
```

模板字符串使得构建复杂字符串变得非常清晰和方便。

![](img/af879d0ef4b899e7e429a73a844847fb_33.png)

## 控制结构

![](img/af879d0ef4b899e7e429a73a844847fb_35.png)

![](img/af879d0ef4b899e7e429a73a844847fb_36.png)

![](img/af879d0ef4b899e7e429a73a844847fb_37.png)

如果你熟悉C语言，那么Javascript中的 `if`、`else if`、`else`、`while` 和 `for` 循环看起来会非常熟悉。语法几乎一致，只是去掉了类型声明。

```javascript
let number = 5;

if (number > 10) {
    console.log('Large');
} else if (number > 0) {
    // 什么都不做
} else {
    console.log('Small or negative');
}

// while循环
let i = 0;
while (i < 5) {
    console.log(i);
    i++;
}

// for循环
for (let j = 0; j < 5; j++) {
    console.log(j);
}
```

## 函数

![](img/af879d0ef4b899e7e429a73a844847fb_39.png)

在Javascript中定义函数使用 `function` 关键字。由于是动态类型，你不需要指定参数和返回值的类型。

```javascript
function minimum(a, b) {
    if (a > b) {
        return b;
    }
    return a;
}

// 调用函数
let result = minimum(10, 20);
console.log(result); // 输出: 10
```

函数是Javascript中的一等公民，可以作为参数传递，也可以从其他函数返回，这为函数式编程风格提供了支持。

![](img/af879d0ef4b899e7e429a73a844847fb_41.png)

## 数据结构：顺序集合 (数组)

![](img/af879d0ef4b899e7e429a73a844847fb_43.png)

在Javascript中，**数组** 是主要的顺序集合，它是可变的、有序的，并且通常包含相同类型的元素（但语言并不强制）。你可以动态地添加或删除元素。

以下是数组的基本操作：

```javascript
// 1. 创建数组
const names = ['Hayden', 'Jake', 'Nick', 'Emily'];

![](img/af879d0ef4b899e7e429a73a844847fb_45.png)

![](img/af879d0ef4b899e7e429a73a844847fb_46.png)

![](img/af879d0ef4b899e7e429a73a844847fb_48.png)

// 2. 访问和打印
console.log(names); // 打印整个数组: ['Hayden', 'Jake', 'Nick', 'Emily']
console.log(names[1]); // 访问第二个元素 (索引从0开始): 'Jake'

![](img/af879d0ef4b899e7e429a73a844847fb_50.png)

![](img/af879d0ef4b899e7e429a73a844847fb_52.png)

![](img/af879d0ef4b899e7e429a73a844847fb_53.png)

![](img/af879d0ef4b899e7e429a73a844847fb_54.png)

// 3. 修改元素
names[1] = 'Jacob'; // 数组变为: ['Hayden', 'Jacob', 'Nick', 'Emily']

![](img/af879d0ef4b899e7e429a73a844847fb_56.png)

// 4. 添加元素到末尾
names.push('Rennie'); // 数组变为: ['Hayden', 'Jacob', 'Nick', 'Emily', 'Rennie']

![](img/af879d0ef4b899e7e429a73a844847fb_58.png)

// 5. 遍历数组
// 方式一：传统的 for 循环
for (let i = 0; i < names.length; i++) {
    console.log(names[i]);
}

![](img/af879d0ef4b899e7e429a73a844847fb_60.png)

![](img/af879d0ef4b899e7e429a73a844847fb_62.png)

// 方式二：for...of 循环 (遍历值)
for (const name of names) {
    console.log(name);
}

![](img/af879d0ef4b899e7e429a73a844847fb_64.png)

// 方式三：for...in 循环 (遍历索引)
for (const index in names) {
    console.log(`Index ${index}: ${names[index]}`);
}
```

![](img/af879d0ef4b899e7e429a73a844847fb_66.png)

数组自带很多有用的方法，例如 `push`, `pop`, `length` 属性等。`array.length` 可以直接获取数组的长度。

## 数据结构：关联集合 (对象)

**对象** 是Javascript中主要的关联集合，类似于C语言中的结构体，但功能更强大、更灵活。对象是键值对的集合，键通常是字符串，值可以是任何类型。对象中的元素没有内在的顺序。

以下是对象的基本操作：

![](img/af879d0ef4b899e7e429a73a844847fb_68.png)

```javascript
// 1. 创建对象
const student = {
    name: 'Sally',
    score: 95,
    rank: 1
};

// 2. 访问和打印
console.log(student); // 打印整个对象
console.log(student.name); // 使用点语法访问: 'Sally'
console.log(student['score']); // 使用方括号语法访问: 95

![](img/af879d0ef4b899e7e429a73a844847fb_70.png)

![](img/af879d0ef4b899e7e429a73a844847fb_72.png)

![](img/af879d0ef4b899e7e429a73a844847fb_74.png)

// 3. 修改属性
student.name = 'Hayden';

// 4. 动态添加新属性
student.height = 159; // 对象现在拥有 height 属性

![](img/af879d0ef4b899e7e429a73a844847fb_76.png)

// 5. 遍历对象
// 遍历对象的键
for (const key in student) {
    console.log(`Key: ${key}, Value: ${student[key]}`);
}

![](img/af879d0ef4b899e7e429a73a844847fb_78.png)

![](img/af879d0ef4b899e7e429a73a844847fb_80.png)

![](img/af879d0ef4b899e7e429a73a844847fb_82.png)

![](img/af879d0ef4b899e7e429a73a844847fb_84.png)

![](img/af879d0ef4b899e7e429a73a844847fb_85.png)

// 使用 Object.keys(), Object.values(), Object.entries()
const keys = Object.keys(student); // 返回键的数组: ['name', 'score', 'rank', 'height']
const values = Object.values(student); // 返回值的数组: ['Hayden', 95, 1, 159]
const entries = Object.entries(student); // 返回键值对数组: [['name','Hayden'], ['score',95], ...]

// 6. 检查对象是否拥有某个属性
if ('name' in student) {
    console.log('Student has a name property');
}
```

![](img/af879d0ef4b899e7e429a73a844847fb_87.png)

对象在表示现实世界的实体（如用户、产品）时非常有用，你可以通过有意义的属性名（键）来访问数据。

![](img/af879d0ef4b899e7e429a73a844847fb_89.png)

## 数组与对象的结合

![](img/af879d0ef4b899e7e429a73a844847fb_91.png)

![](img/af879d0ef4b899e7e429a73a844847fb_93.png)

在实际应用中，我们经常将数组和对象组合使用，例如创建一个对象数组。

![](img/af879d0ef4b899e7e429a73a844847fb_95.png)

![](img/af879d0ef4b899e7e429a73a844847fb_97.png)

![](img/af879d0ef4b899e7e429a73a844847fb_99.png)

```javascript
// 一个包含学生对象的数组
const students = [
    { name: 'Alice', score: 88 },
    { name: 'Bob', score: 92 },
    { name: 'Charlie', score: 76 }
];

// 遍历数组，并访问每个对象的属性
for (const student of students) {
    if (student.score > 85) {
        console.log(`${student.name} got a High Distinction!`);
    }
}

![](img/af879d0ef4b899e7e429a73a844847fb_101.png)

![](img/af879d0ef4b899e7e429a73a844847fb_102.png)

// 也可以是一个以字符串为键，对象为值的对象
const classData = {
    'Alice': { age: 20, grade: 'A' },
    'Bob': { age: 21, grade: 'B+' }
};
console.log(classData['Alice'].age); // 访问 Alice 的年龄: 20
```

![](img/af879d0ef4b899e7e429a73a844847fb_104.png)

![](img/af879d0ef4b899e7e429a73a844847fb_106.png)

选择使用数组还是对象，取决于你的数据是否需要顺序（用数组），还是需要通过唯一的字符串标识符来访问（用对象）。

![](img/af879d0ef4b899e7e429a73a844847fb_108.png)

![](img/af879d0ef4b899e7e429a73a844847fb_110.png)

![](img/af879d0ef4b899e7e429a73a844847fb_112.png)

## 重要注意事项

1.  **相等性比较**：在Javascript中，使用 `==` 进行相等比较时，如果类型不同，它会尝试进行类型转换再比较，这可能导致意想不到的结果。**最佳实践是始终使用严格相等运算符 `===`（值和类型都相等）和严格不相等运算符 `!==`**。
    ```javascript
    console.log(5 == '5'); // true (类型转换)
    console.log(5 === '5'); // false (类型不同)
    console.log(0 == false); // true
    console.log(0 === false); // false
    ```

2.  **注释**：Javascript的注释语法与C语言相同。
    ```javascript
    // 这是单行注释

    /*
    这是
    多行
    注释
    */
    ```

![](img/af879d0ef4b899e7e429a73a844847fb_114.png)

3.  **一切都是对象**：在Javascript中，几乎所有东西（数组、函数、甚至数字和字符串）在底层都可以被视为对象，这意味着它们可以拥有属性和方法。例如，数组有 `.length` 属性、`.push()` 方法；字符串有 `.toUpperCase()`、`.slice()` 等方法。这是语言强大的一部分，但也意味着有更多需要学习的内容。

![](img/af879d0ef4b899e7e429a73a844847fb_116.png)

## 总结

![](img/af879d0ef4b899e7e429a73a844847fb_118.png)

本节课中我们一起学习了Javascript的基础知识。我们了解了它作为一门高级、解释型脚本语言的特点，以及它与C语言在类型系统、内存管理和执行方式上的主要区别。我们掌握了如何使用 `let` 和 `const` 声明变量，如何操作字符串（特别是模板字符串），以及控制结构和函数的写法。重点探讨了两种核心数据结构：**数组**（用于有序列表）和**对象**（用于键值对集合），并学习了如何遍历和操作它们。最后，我们提醒了严格相等 (`===`) 的重要性。Javascript是一门功能丰富且灵活的语言，初学时会感觉比C“庞大”，但通过实践，你会逐渐熟悉并享受其高效的开发体验。