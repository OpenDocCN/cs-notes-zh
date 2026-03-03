# 密歇根大学《给所有人的Django课程》4：4：JavaScript语言特性 🧩

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_1.png)

在本节课中，我们将学习JavaScript作为一种编程语言的基础语法。我们将从注释开始，逐步介绍变量、数据类型、运算符等核心概念，帮助你理解JavaScript的基本构成。

## 注释

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_3.png)

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_4.png)

JavaScript支持两种风格的注释，它们分别受到不同编程语言的影响。

以下是两种注释的写法：

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_6.png)

*   `/* 这是一个多行注释，可以跨越多行。 */`：这种多行注释风格来源于C语言。
*   `// 这是一个单行注释，到行尾结束。`：这种单行注释风格来源于C++语言。

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_8.png)

我倾向于使用多行注释来编写文档区块，而使用单行注释进行简短说明。

## 语句与空格

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_10.png)

在JavaScript中，空格和换行符通常不影响代码执行。虽然技术上并非所有语句都必须以分号结尾，但养成在每个语句末尾添加分号的习惯是有益的。

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_12.png)

例如，以下代码虽然格式混乱，但依然可以运行：
```javascript
x = 3 + 5
    * 4;
console.log(x);
```
对于JavaScript这类语言，解释器主要识别字符和分号来界定语句的结束，换行符被视为另一种空白字符。

## 变量与常量

现在，我们来看看如何命名变量以及定义字符串和数字常量。

### 变量命名

变量名可以包含字母、数字、下划线和美元符号，但不能以数字开头。变量名是大小写敏感的。

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_14.png)

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_15.png)

关于命名风格：
*   我们有时使用大小写来传递信息，例如驼峰式命名或全大写命名。
*   虽然JavaScript允许变量名以美元符号开头（受PHP和Perl影响），但为了代码风格更接近Java，通常不建议这样做。

### 字符串常量

单引号（`'`）和双引号（`"`）在定义字符串时功能完全相同。我倾向于在JavaScript代码中尽可能使用单引号，因为双引号是HTML的属性值界定符。这样在混合编写JavaScript和HTML代码时，可以更容易地区分两者。

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_17.png)

例如，在编写包含HTML的JavaScript字符串时：
```javascript
let htmlSnippet = '<p class="highlight">Text</p>';
```
这里，外层使用单引号表示JavaScript字符串，内层的双引号则是HTML属性所需。

### 数字常量

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_19.png)

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_20.png)

JavaScript只有一种数字类型：`Number`。所有数字在内部都是浮点数，没有独立的整数类型。

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_22.png)

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_24.png)

例如：
```javascript
let result = 5 / 3; // 结果是浮点数 1.666...
let intPart = Math.trunc(result); // 使用 Math.trunc 截取整数部分，得到 1
```
即使`intPart`显示为1，它本质上仍然是一个浮点数。

## 运算符

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_26.png)

上一节我们介绍了变量和常量，本节中我们来看看JavaScript中用于操作这些值的各种运算符。

### 算术运算符

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_28.png)

基本的算术运算符与其他语言类似。

以下是常见的算术运算符：

*   `+`：加法
*   `-`：减法
*   `*`：乘法
*   `/`：除法
*   `%`：取模（求余数）

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_30.png)

取模运算符（`%`）非常实用，例如，可以用它来在循环中每隔一定次数执行某个操作：
```javascript
if (iterationCount % 100 === 0) {
    // 每循环100次执行一次
}
```

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_32.png)

### 副作用运算符

这些运算符会在计算值的同时改变变量本身。

以下是常见的副作用运算符：

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_34.png)

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_36.png)

*   `k++`：先使用`k`的值，然后将`k`加1。
*   `++k`：先将`k`加1，然后使用`k`的新值。
*   `j += 5`：等同于 `j = j + 5`。类似的还有 `-=`， `*=`， `/=`。

虽然这些运算符源自C语言，在JavaScript和Java中也很常见，但为了代码清晰，我通常更倾向于使用完整的赋值语句（如 `j = j + 5`）。

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_38.png)

### 比较与逻辑运算符

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_40.png)

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_41.png)

比较运算符用于比较值，并返回布尔值（`true`或`false`）。

以下是常见的比较运算符：

*   `=`：赋值（例如 `j = 10`）。
*   `==`：相等比较（允许类型转换）。
*   `===`：严格相等比较（要求值和类型都相同）。
*   `!=`：不相等比较。
*   `!==`：严格不相等比较。
*   `<`, `>`, `<=`, `>=`：小于、大于、小于等于、大于等于。

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_43.png)

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_44.png)

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_46.png)

严格相等（`===`）和严格不相等（`!==`）非常重要，它们能避免因JavaScript自动类型转换而导致的意外结果。

逻辑运算符用于组合多个布尔条件。

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_48.png)

以下是常见的逻辑运算符：

*   `&&`：逻辑与（AND），两边都为`true`时结果为`true`。
*   `||`：逻辑或（OR），至少一边为`true`时结果为`true`。
*   `!`：逻辑非（NOT），对布尔值取反。

例如：
```javascript
if (k > 1 && j < 10) { /* 两者都成立时执行 */ }
if (!(k > 10)) { /* k 不大于 10 时执行 */ }
```

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_50.png)

## 类型转换与特殊值

我们已经了解了运算符，现在来看看JavaScript在处理不同类型数据交互时的一些特性，特别是字符串拼接和特殊的数字值。

### 字符串拼接

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_52.png)

JavaScript使用加号（`+`）进行字符串拼接，并且会自动将非字符串值转换为字符串。

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_54.png)

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_56.png)

例如：
```javascript
let x = 12;
let message = "Hello " + x + " people"; // 结果为 "Hello 12 people"
```
这里，数字`12`被自动转换成了字符串。这种便利性有时可能导致意料之外的结果，尤其是在与加法运算混淆时。

### 特殊数字值：NaN 和 Infinity

当数学运算无法返回一个有效的数字时，会产生一些特殊值。

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_58.png)

以下是两个主要的特殊数字值：

*   `NaN`：表示“非数字”。例如，将字符串“hello”乘以1会得到`NaN`。`NaN`具有粘性，任何涉及`NaN`的后续运算通常仍会得到`NaN`。可以使用`isNaN()`函数来检测一个值是否为`NaN`。
*   `Infinity`：表示无穷大。例如，`1 / 0`的结果是`Infinity`。可以使用`isFinite()`函数来检测一个值是否为有限数（即不是`Infinity`或`NaN`）。

JavaScript遵循IEEE 754浮点数算术标准，对这些特殊值的处理方式在科学计算上是严谨和一致的。

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_60.png)

### 类型检测

在动态类型语言中，有时需要检查变量的类型。`typeof`运算符可以返回一个表示变量类型的字符串。

例如：
```javascript
typeof 42;        // 返回 "number"
typeof 'Hello';   // 返回 "string"
typeof undefinedVariable; // 如果变量未定义，返回 "undefined"
```
这在处理来自外部或用户输入的参数时非常有用，可以确保代码按预期处理不同类型的数据。

![](img/f2a9d4f5f84eccf4d8fba9e78f43a8ff_62.png)

本节课中我们一起学习了JavaScript的基础语法，包括注释、变量、常量、各种运算符（算术、比较、逻辑）、类型自动转换以及`NaN`、`Infinity`等特殊值的概念。理解这些基础是编写任何JavaScript代码的前提。下一节，我们将探讨函数和数组。