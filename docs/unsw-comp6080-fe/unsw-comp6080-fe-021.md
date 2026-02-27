# 021：🛠️ 高级函数

![](img/385031d2a9f0b9ff6eba7402c73d3934_1.png)

在本节课中，我们将要学习 JavaScript 中函数的多种定义方式，以及“一等函数”和“高阶函数”这两个核心概念。这些概念是理解现代 JavaScript 编程风格（如回调函数、数组方法）的基础，并能帮助我们编写更简洁、更易维护的代码。

## 函数的三种定义方式

在 JavaScript 中，有三种主要的方式来定义一个函数。理解这些方式有助于我们理解函数在 JavaScript 中是如何被处理的。

### 方法一：传统函数声明

这是最经典、我们最熟悉的函数定义方式，类似于 C 语言中的函数定义。它使用 `function` 关键字，后跟函数名和参数列表。

```javascript
function sum(a, b) {
    return a + b;
}
```

### 方法二：函数表达式

在这种方式中，我们将一个匿名函数赋值给一个变量（常量）。这强调了“函数可以像变量一样被赋值”的概念。

![](img/385031d2a9f0b9ff6eba7402c73d3934_3.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_5.png)

```javascript
const sum = function(a, b) {
    return a + b;
};
```

![](img/385031d2a9f0b9ff6eba7402c73d3934_7.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_8.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_10.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_12.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_14.png)

### 方法三：箭头函数

![](img/385031d2a9f0b9ff6eba7402c73d3934_16.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_18.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_19.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_20.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_21.png)

这是现代 JavaScript 中最常用的简洁语法。它移除了 `function` 关键字，并使用箭头 (`=>`) 来连接参数和函数体。

```javascript
const sum = (a, b) => {
    return a + b;
};
```

箭头函数还有一个重要的特性：如果函数体只有单行返回语句，可以省略大括号 `{}` 和 `return` 关键字，进一步简化代码。

```javascript
const sum = (a, b) => a + b;
```

上一节我们介绍了函数的三种定义方式，本节中我们来看看这些方式如何引出一个核心概念：一等函数。

## 一等函数

![](img/385031d2a9f0b9ff6eba7402c73d3934_23.png)

JavaScript 中的函数是“一等公民”或“一等函数”。这意味着函数可以像其他任何值（如字符串、数字）一样被使用。具体来说，函数可以被赋值给变量，可以作为参数传递给其他函数，也可以作为其他函数的返回值。

![](img/385031d2a9f0b9ff6eba7402c73d3934_25.png)

以下是一个将函数作为参数传递的示例：

![](img/385031d2a9f0b9ff6eba7402c73d3934_27.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_29.png)

```typescript
// 定义两个格式化函数
const brackets = (str: string): string => `(${str})`;
const fullStop = (str: string): string => `${str}.`;

// 定义一个接受函数作为参数的函数
const sayHi = (name: string, format: (str: string) => string): string => {
    return `Hello ${format(name)}`;
};

![](img/385031d2a9f0b9ff6eba7402c73d3934_31.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_33.png)

// 使用
const result = sayHi("Hayden", brackets) + " " + sayHi("Hayden", fullStop);
console.log(result); // 输出：Hello (Hayden) Hello Hayden.
```

![](img/385031d2a9f0b9ff6eba7402c73d3934_35.png)

在这个例子中，`sayHi` 函数接受一个字符串 `name` 和一个函数 `format` 作为参数。通过传递不同的 `format` 函数（`brackets` 或 `fullStop`），我们可以灵活地改变输出格式，而无需重写 `sayHi` 函数的逻辑。

![](img/385031d2a9f0b9ff6eba7402c73d3934_37.png)

理解了函数可以作为参数传递后，我们自然会遇到一种常见情况：匿名函数。

![](img/385031d2a9f0b9ff6eba7402c73d3934_39.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_40.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_42.png)

## 匿名函数

![](img/385031d2a9f0b9ff6eba7402c73d3934_44.png)

当我们只需要在一个地方使用一个简单的函数，而不想为其专门命名时，可以使用匿名函数。匿名函数通常直接作为参数传递给其他函数（如 `map`、`filter`）。

以下是使用匿名函数简化之前 `sayHi` 调用的示例：

![](img/385031d2a9f0b9ff6eba7402c73d3934_46.png)

```javascript
// 直接内联定义函数，而不是先定义再传递
const result = sayHi("Hayden", (str) => `[${str}]`);
console.log(result); // 输出：Hello [Hayden]
```

![](img/385031d2a9f0b9ff6eba7402c73d3934_48.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_50.png)

匿名函数与数组方法结合使用时尤其强大。接下来，我们将探讨 JavaScript 数组中最常用的三个高阶函数方法。

![](img/385031d2a9f0b9ff6eba7402c73d3934_52.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_54.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_56.png)

## 数组的高阶函数方法：Map, Filter, Reduce

![](img/385031d2a9f0b9ff6eba7402c73d3934_58.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_60.png)

JavaScript 数组提供了 `map`、`filter` 和 `reduce` 等方法，它们都接受一个函数作为参数，用于对数组元素进行操作。这些方法可以极大地简化循环遍历数组的代码。

![](img/385031d2a9f0b9ff6eba7402c73d3934_62.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_64.png)

### Map 方法

![](img/385031d2a9f0b9ff6eba7402c73d3934_66.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_67.png)

`map` 方法遍历数组的每个元素，对其应用一个函数，并返回一个由函数结果组成的**新数组**。新数组长度与原数组相同。

![](img/385031d2a9f0b9ff6eba7402c73d3934_69.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_71.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_73.png)

以下是使用循环和使用 `map` 方法的对比：

![](img/385031d2a9f0b9ff6eba7402c73d3934_75.png)

```javascript
// 使用循环
const tutors = ["Sim", "Theresa", "Kai", "Michelle"];
const shoutedTutors = [];
for (const tutor of tutors) {
    shoutedTutors.push(tutor.toUpperCase() + "!");
}

// 使用 map 方法
const shoutedTutorsMap = tutors.map(tutor => tutor.toUpperCase() + "!");
```

![](img/385031d2a9f0b9ff6eba7402c73d3934_77.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_79.png)

### Filter 方法

![](img/385031d2a9f0b9ff6eba7402c73d3934_81.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_83.png)

`filter` 方法遍历数组，对每个元素应用一个测试函数。只有使该函数返回 `true` 的元素会被包含在返回的**新数组**中。新数组长度可能小于或等于原数组。

![](img/385031d2a9f0b9ff6eba7402c73d3934_85.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_87.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_89.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_91.png)

以下是使用循环和使用 `filter` 方法的对比：

![](img/385031d2a9f0b9ff6eba7402c73d3934_93.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_95.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_97.png)

```javascript
// 使用循环
const marks = [39, 43, 48, 24, 33];
const passMarks = [];
for (const mark of marks) {
    if (mark >= 50) {
        passMarks.push(mark);
    }
}

![](img/385031d2a9f0b9ff6eba7402c73d3934_99.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_101.png)

// 使用 filter 方法
const passMarksFilter = marks.filter(mark => mark >= 50);
```

![](img/385031d2a9f0b9ff6eba7402c73d3934_103.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_105.png)

### Reduce 方法

`reduce` 方法将数组“缩减”为单个值。它接受一个“累加器”函数和一个初始值。该函数会遍历数组，将当前元素与当前的“累加值”合并，最终返回一个结果。

![](img/385031d2a9f0b9ff6eba7402c73d3934_107.png)

以下是使用循环和使用 `reduce` 方法求总和的对比：

![](img/385031d2a9f0b9ff6eba7402c73d3934_109.png)

```javascript
// 使用循环
const students = [
    { name: "Hayden", mark: 55 },
    { name: "Juliana", mark: 43 },
    // ... 其他学生
];
let total = 0;
for (const student of students) {
    total += student.mark;
}

// 使用 reduce 方法
const totalReduce = students.reduce((prevTotal, student) => prevTotal + student.mark, 0);
```

我们已经看到了函数如何作为参数传递。现在，让我们看看更进阶的概念：函数也可以作为返回值，这就是高阶函数。

## 高阶函数

高阶函数是指那些**返回另一个函数**的函数。你可以把它们想象成“函数工厂”，用于生成具有特定行为的函数。

![](img/385031d2a9f0b9ff6eba7402c73d3934_111.png)

假设我们需要多个功能相似但细节不同的函数：

![](img/385031d2a9f0b9ff6eba7402c73d3934_113.png)

```javascript
// 传统方式：定义多个独立函数
const congratulateMarkPass = (name: string) => `Congratulations ${name} on your pass!`;
const congratulateMarkCredit = (name: string) => `Congratulations ${name} on your credit!`;
// ... 更多
```

![](img/385031d2a9f0b9ff6eba7402c73d3934_115.png)

我们可以使用高阶函数来生成这些函数，避免重复代码：

![](img/385031d2a9f0b9ff6eba7402c73d3934_117.png)

```typescript
// 高阶函数：生成特定祝贺语的函数
const generateCongratulateMark = (mark: string) => {
    // 返回一个新的函数
    return (name: string) => `Congratulations ${name} on your ${mark}!`;
};

![](img/385031d2a9f0b9ff6eba7402c73d3934_119.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_121.png)

// 使用高阶函数“工厂”来创建我们需要的具体函数
const congratulateMarkPass = generateCongratulateMark("pass");
const congratulateMarkCredit = generateCongratulateMark("credit");

// 使用生成的函数
console.log(congratulateMarkCredit("Hayden")); // 输出：Congratulations Hayden on your credit!
```

在这个例子中，`generateCongratulateMark` 是一个高阶函数。它根据传入的 `mark` 字符串，动态地创建并返回一个新的函数。这种方式在需要创建多个逻辑相似、仅某些参数或行为不同的函数时非常有用，可以使代码更简洁、更易于维护。

![](img/385031d2a9f0b9ff6eba7402c73d3934_123.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_125.png)

![](img/385031d2a9f0b9ff6eba7402c73d3934_127.png)

本节课中我们一起学习了 JavaScript 中函数的多种定义方式，深入理解了一等函数（函数可作为参数传递）和高阶函数（函数可作为返回值）的概念。我们还探讨了如何利用这些概念，通过 `map`、`filter`、`reduce` 等数组方法以及匿名函数来编写更简洁、更声明式的代码。掌握这些高级函数技巧，将帮助你更好地理解和运用现代 JavaScript 的编程范式，构建更清晰、更易维护的应用程序。