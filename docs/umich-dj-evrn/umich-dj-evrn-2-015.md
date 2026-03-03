# Django for Everybody：4：JavaScript函数与数组

![](img/cb3cf5088c1e40e258396cd03f3f8e34_1.png)

![](img/cb3cf5088c1e40e258396cd03f3f8e34_3.png)

在本节课中，我们将要学习JavaScript中的两个核心概念：函数与数组。理解这些概念对于编写动态的网页交互逻辑至关重要。

## 函数

![](img/cb3cf5088c1e40e258396cd03f3f8e34_5.png)

上一节我们介绍了JavaScript的基础语法，本节中我们来看看如何定义和使用函数。JavaScript函数使用 `function` 关键字定义，这与Python使用 `def` 关键字不同。

![](img/cb3cf5088c1e40e258396cd03f3f8e34_7.png)

函数的基本结构如下：
```javascript
function functionName(parameters) {
    // 函数体
    return value; // 返回值
}
```
当代码执行到一个表达式并遇到函数调用时，它会运行该函数，并用 `return` 语句返回的值替换该调用位置。例如，`add(4, 5)` 的返回值 `9` 会用于后续计算。

![](img/cb3cf5088c1e40e258396cd03f3f8e34_9.png)

### 变量作用域

函数内部定义的变量通常是该函数的局部变量。然而，JavaScript有一个特殊之处：如果不明确声明，函数内赋值的变量可能会成为全局变量。

请看以下示例：
```javascript
var GL = 123; // 这是一个全局变量

![](img/cb3cf5088c1e40e258396cd03f3f8e34_11.png)

function check() {
    GL = 456; // 如果没有使用 `var`，这里会修改全局的 GL
}
check();
console.log(GL); // 输出：456
```
在这个例子中，函数 `check` 内部没有使用 `var` 声明 `GL`，因此它修改了外部的全局变量。

![](img/cb3cf5088c1e40e258396cd03f3f8e34_13.png)

为了避免这种混淆，并让函数的行为更符合常规编程语言的预期，我们应始终使用 `var` 关键字在函数内部声明局部变量：
```javascript
var GL = 123;

function check() {
    var GL = 456; // 使用 `var` 声明，这是一个局部变量
}
check();
console.log(GL); // 输出：123，全局变量未被修改
```
使用 `var` 可以确保函数变量被限制在自己的作用域内，除非你明确需要操作全局变量。养成在函数内使用 `var` 的习惯非常重要。

## 数组与对象

![](img/cb3cf5088c1e40e258396cd03f3f8e34_15.png)

理解了函数的作用域后，我们接下来探讨JavaScript中用于组织数据的两种主要结构：数组和对象。

JavaScript的数组与Python的列表非常相似。以下是一个包含三个字符串的数组：
```javascript
var a = [‘x‘, ‘y‘, ‘z‘];
```
你可以通过索引访问数组元素，例如 `a[0]` 会返回 `‘x‘`。

JavaScript的关联结构不是“字典”，而是“对象”。对象可以包含多种内容，我们之后会有专门课程讲解。目前，你可以将其视为键值对的集合：
```javascript
var b = {‘name‘: ‘Chuck‘, ‘class‘: ‘DJ3‘};
```
访问对象属性有两种等效的语法：
1.  使用方括号：`b[‘name‘]`
2.  使用点号：`b.name`

这两种语法都表示查找对象 `b` 中名为 `‘name‘` 的属性。对于初学者来说，理解它们是同一回事很重要。

![](img/cb3cf5088c1e40e258396cd03f3f8e34_17.png)

### 数组操作

![](img/cb3cf5088c1e40e258396cd03f3f8e34_19.png)

以下是创建和填充数组的几种方式：

你可以先创建一个空数组，然后使用 `push` 方法添加元素（类似于Python列表的 `append`）：
```javascript
var arr = [];
arr.push(‘zero‘);
arr.push(‘one‘);
```
你也可以在创建时直接初始化数组：
```javascript
var arr = [‘zero‘, ‘one‘];
```
或者使用 `Array` 构造函数：
```javascript
var arr = new Array(‘zero‘, ‘one‘);
```
最简洁和常用的方式还是使用方括号 `[]` 字面量语法，这与Python的列表语法一致。

![](img/cb3cf5088c1e40e258396cd03f3f8e34_21.png)

总结一下，JavaScript用**数组**存储有序列表，用**对象**存储键值对关联数据，而Python则分别使用**列表**和**字典**。

![](img/cb3cf5088c1e40e258396cd03f3f8e34_23.png)

## 总结

本节课中我们一起学习了JavaScript的函数与数组。
*   我们学习了如何使用 `function` 关键字定义函数，以及 `return` 语句的作用。
*   我们深入探讨了变量作用域，强调了在函数内部使用 `var` 关键字声明局部变量的重要性，以避免意外修改全局变量。
*   我们介绍了数组的创建和访问方式，以及对象作为关联结构的两种属性访问语法。
*   我们比较了JavaScript（数组与对象）和Python（列表与字典）在数据结构上的异同。

![](img/cb3cf5088c1e40e258396cd03f3f8e34_25.png)

![](img/cb3cf5088c1e40e258396cd03f3f8e34_26.png)

掌握这些基础概念是编写有效JavaScript代码的关键。下一节，我们将探讨JavaScript中的控制结构。