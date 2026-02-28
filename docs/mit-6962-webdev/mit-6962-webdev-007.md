# 007：高级JavaScript概念

## 概述
在本节课中，我们将深入学习JavaScript中的两个核心概念：**回调函数**和**数组方法**。这些概念对于理解后续的React框架至关重要。我们将从复习基础函数和数组操作开始，逐步探讨如何编写更通用、可复用的代码。

---

## 函数回顾

上一节我们介绍了JavaScript的基本语法，本节中我们来看看函数的定义方式。

一个函数可以看作是一个输入输出的机器。输入位于括号内，箭头 `=>` 表示将输入“喂”给函数体，函数体包裹在花括号 `{}` 中，并产生输出。

![](img/d617d8b05e01c33139f31fe8a96ffd40_1.png)

**公式**：
```
(输入参数) => { 函数体; return 输出; }
```

为了能调用这个函数，我们需要将其赋值给一个变量。

![](img/d617d8b05e01c33139f31fe8a96ffd40_3.png)

**代码**：
```javascript
const celsiusToFahrenheit = (tempC) => {
    return (tempC * 9/5) + 32;
};
```

---

## 数组操作回顾

![](img/d617d8b05e01c33139f31fe8a96ffd40_5.png)

在深入新概念之前，我们需要回顾两个基本的数组操作：`push` 和 `pop`。

*   `push`：向数组末尾添加一个新元素。
*   `pop`：从数组末尾移除一个元素。

![](img/d617d8b05e01c33139f31fe8a96ffd40_7.png)

此外，遍历数组是常见操作。以下是使用 `for` 循环遍历数组的标准语法。

**代码**：
```javascript
for (let i = 0; i < array.length; i++) {
    // 对 array[i] 进行操作
}
```

---

![](img/d617d8b05e01c33139f31fe8a96ffd40_9.png)

## 实践：转换温度数组

![](img/d617d8b05e01c33139f31fe8a96ffd40_11.png)

基于以上知识，我们来完成一个练习：编写一个函数，它接收一个摄氏温度数组，并返回一个对应的华氏温度新数组。**注意**：不应修改原数组。

![](img/d617d8b05e01c33139f31fe8a96ffd40_13.png)

以下是实现该功能的一种方法。

**代码**：
```javascript
const arrayCelsiusToFahrenheit = (arrayCelsius) => {
    const arrayF = []; // 创建新数组
    for (let i = 0; i < arrayCelsius.length; i++) {
        const tempF = (arrayCelsius[i] * 9/5) + 32; // 转换单个温度
        arrayF.push(tempF); // 将结果加入新数组
    }
    return arrayF; // 返回新数组
};
```

---

## 引入回调函数

现在，假设我们还需要将数组转换为开尔文温度，或者进行其他运算。复制粘贴上述代码并只修改核心计算部分（高亮部分）效率很低。

我们希望重用那90%相同的代码（循环和构建新数组），只替换核心计算逻辑。这就是**回调函数**的用武之地。

我们将创建一个通用的 `modifyArray` 函数。它接收一个数组和一个“转换函数”作为参数，然后对数组的每个元素应用这个转换函数，并返回新数组。

![](img/d617d8b05e01c33139f31fe8a96ffd40_15.png)

**概念**：`modifyArray(原始数组, 转换函数) => 新数组`

---

## 实现通用数组修改函数

以下是 `modifyArray` 函数的实现。注意它与之前特定温度转换函数的区别。

**代码**：
```javascript
const modifyArray = (inputArray, transformFunc) => {
    const outputArray = [];
    for (let i = 0; i < inputArray.length; i++) {
        // 对每个元素应用传入的转换函数
        const transformedElement = transformFunc(inputArray[i]);
        outputArray.push(transformedElement);
    }
    return outputArray;
};

// 定义具体的转换函数
const cToF = (tempC) => (tempC * 9/5) + 32;

// 使用通用函数
const tempsC = [0, 20, 100];
const tempsF = modifyArray(tempsC, cToF);
```

通过这种方式，我们分离了“遍历数组”的逻辑和“处理每个元素”的逻辑，代码变得更具**可复用性**。

---

![](img/d617d8b05e01c33139f31fe8a96ffd40_17.png)

![](img/d617d8b05e01c33139f31fe8a96ffd40_19.png)

![](img/d617d8b05e01c33139f31fe8a96ffd40_21.png)

## 数组的 map 方法

实际上，JavaScript 已经内置了与我们 `modifyArray` 功能几乎相同的方法，叫做 `map`。区别在于调用语法：它是数组对象的一个方法。

**代码**：
```javascript
const newArray = originalArray.map((element) => {
    // 返回转换后的元素
    return transformedElement;
});
```

使用 `map` 重写温度转换：

**代码**：
```javascript
const tempsF = tempsC.map((tempC) => (tempC * 9/5) + 32);
```

`map` 方法封装了循环过程，让我们只需关心对每个元素的转换规则。

---

## 数组的 filter 方法

另一个强大的数组方法是 `filter`。它用于根据条件筛选数组元素。它接收一个函数，该函数对每个元素返回 `true`（保留）或 `false`（过滤掉）。

**代码**：
```javascript
const numbers = [1, -1, 2, -2, 3];
const positiveNumbers = numbers.filter((x) => x > 0);
// positiveNumbers 现在是 [1, 2, 3]

const staff = [‘Alice‘, ‘Bob‘, ‘Annabel‘, ‘Charlie‘];
const filteredStaff = staff.filter((name) => name !== ‘Annabel‘);
// filteredStaff 现在是 [‘Alice‘, ‘Bob‘, ‘Charlie‘]
```

---

## 为什么使用回调函数？

我们使用回调函数主要有两个原因：

1.  **可复用性**：如 `map` 和 `filter`，避免为每种操作重复编写遍历数组的代码。
2.  **抽象**：将“做什么”（由我们定义的回调函数实现）与“何时做”（由系统或库函数控制）分离开。

**示例**：`setInterval` 函数允许我们定期执行某个操作，我们只需定义操作内容（回调函数），而无需管理计时器底层逻辑。

**代码**：
```javascript
setInterval(() => {
    updateAnimation(); // 这是我们的回调函数，定义“做什么”
}, 10); // 每10毫秒执行一次，由 setInterval 控制“何时做”
```

---

## 回调函数在Web开发中的应用

在后续的Web开发中，你会频繁遇到回调函数，例如：

*   **数据库操作**：在从数据库获取数据后执行特定操作。
*   **处理HTTP请求**：在接收到特定网络请求时运行处理逻辑。

当你看到 `(参数) => { ... }` 这样的结构作为参数传递给另一个函数时，请思考：这里的“**当……发生时**”是什么？这里的“**做这个**”又是什么？这种思考方式将帮助你更好地理解异步编程和事件驱动架构。

---

## 总结

![](img/d617d8b05e01c33139f31fe8a96ffd40_23.png)

本节课我们一起学习了JavaScript中的高级概念。我们回顾了函数和数组基础，然后深入探讨了**回调函数**的核心思想——将函数作为参数传递以实现代码的复用与抽象。我们实践了如何创建通用的数组处理函数，并介绍了JavaScript内置的 `map` 和 `filter` 方法，它们都是回调函数的经典应用。理解这些概念是学习现代前端框架（如React）和进行异步编程的重要基石。