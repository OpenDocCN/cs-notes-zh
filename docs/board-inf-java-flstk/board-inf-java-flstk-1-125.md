# 125：使用算术与比较运算符 🧮

在本节课中，我们将要学习 JavaScript 中的算术运算符与比较运算符。它们是进行数学计算和逻辑判断的基础工具。

上一节我们介绍了 JavaScript 的数据类型，本节中我们来看看如何对数据进行运算和比较。

![](img/0a9f67f74adfd7409bc56f6102410949_1.png)

## 算术运算符

算术运算符用于对数值执行数学计算。

以下是 JavaScript 中主要的算术运算符及其符号：

*   **加法**：`+`
*   **减法**：`-`
*   **乘法**：`*`
*   **除法**：`/`
*   **取模（求余）**：`%`
*   **指数运算**：`**`

让我们通过代码示例来理解它们。

```javascript
let x = 10;
let y = 5;

// 加法
let sum = x + y;
console.log(sum); // 输出：15

// 减法
let difference = x - y;
console.log(difference); // 输出：5

// 乘法
let product = x * y;
console.log(product); // 输出：50

// 除法
let quotient = x / y;
console.log(quotient); // 输出：2

// 取模（求余）
let remainder = x % y;
console.log(remainder); // 输出：0

// 指数运算
let result = x ** y; // 10的5次方
console.log(result); // 输出：100000
```

![](img/0a9f67f74adfd7409bc56f6102410949_3.png)

## 比较运算符

比较运算符用于比较两个值，并根据比较结果返回一个布尔值（`true` 或 `false`）。

以下是 JavaScript 中的比较运算符：

![](img/0a9f67f74adfd7409bc56f6102410949_5.png)

*   **等于**：`==`
*   **不等于**：`!=`
*   **严格等于**：`===`
*   **严格不等于**：`!==`
*   **大于**：`>`
*   **大于或等于**：`>=`
*   **小于**：`<`
*   **小于或等于**：`<=`

让我们通过示例来理解这些运算符。请记住，它们的输出总是布尔值。

```javascript
let a = 10;
let b = 5;

// 等于
console.log(a == b); // 输出：false

// 不等于
console.log(a != b); // 输出：true

// 严格等于（同时比较值和类型）
console.log(a === b); // 输出：false

// 严格不等于
console.log(a !== b); // 输出：true

// 大于
console.log(a > b); // 输出：true

// 大于或等于
console.log(a >= b); // 输出：true

// 小于
console.log(a < b); // 输出：false

// 小于或等于
console.log(a <= b); // 输出：false
```

![](img/0a9f67f74adfd7409bc56f6102410949_7.png)

## 总结 📝

本节课中我们一起学习了 JavaScript 中的两种核心运算符。

*   **算术运算符**用于执行数学计算，如加法、减法、乘法、除法等。
*   **比较运算符**用于比较值，并根据比较结果返回布尔值，例如等于、不等于、大于、小于等。

![](img/0a9f67f74adfd7409bc56f6102410949_9.png)

这些运算符是 JavaScript 编程的基础，理解并掌握它们的使用对于后续学习至关重要。下一节，我们将学习 JavaScript 中的数组。