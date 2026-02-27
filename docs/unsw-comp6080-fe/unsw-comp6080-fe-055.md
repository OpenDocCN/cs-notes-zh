# 055：多文件与导入 🛠️

在本节课中，我们将学习如何在JavaScript项目中处理多个文件，以及如何在这些文件之间共享代码。你将了解如何导入内置库、第三方库以及你自己编写的模块。

![](img/85988d628516a6d841ace419e002d1b9_1.png)

## 概述

![](img/85988d628516a6d841ace419e002d1b9_3.png)

在软件开发中，很少会将所有代码都写在一个文件里。本节课将介绍JavaScript中多文件项目的组织方式，重点讲解`import`和`export`语句的用法，以及它们与C语言中`#include`的区别。

## 与C语言的对比

![](img/85988d628516a6d841ace419e002d1b9_5.png)

上一节我们提到了模块化的概念，本节中我们来看看JavaScript与C语言在处理多文件时的具体差异。

![](img/85988d628516a6d841ace419e002d1b9_7.png)

在C语言中，我们使用`#include <stdio.h>`来引入标准库。预处理器会将该文件的内容“复制粘贴”到当前文件中，因此我们可以直接使用`printf`等函数。

![](img/85988d628516a6d841ace419e002d1b9_9.png)

![](img/85988d628516a6d841ace419e002d1b9_10.png)

![](img/85988d628516a6d841ace419e002d1b9_12.png)

![](img/85988d628516a6d841ace419e002d1b9_14.png)

![](img/85988d628516a6d841ace419e002d1b9_15.png)

JavaScript（以及大多数非C系语言）的做法则更加明确。我们使用`import`语句来从库中“获取”一个特定的对象或功能。

![](img/85988d628516a6d841ace419e002d1b9_17.png)

例如，导入Node.js内置的`path`库：
```javascript
import path from 'path';
```
然后通过`path.resolve()`来使用其中的函数。这里的`path`是一个代表整个库的变量。

![](img/85988d628516a6d841ace419e002d1b9_19.png)

**核心区别**：C语言的`#include`是文本替换，而JavaScript的`import`是按需获取对象。

![](img/85988d628516a6d841ace419e002d1b9_21.png)

## 导入内置模块

Node.js自带了一系列内置模块，无需通过npm安装即可使用。最常用的两个是`fs`（文件系统）和`path`（路径处理）。

以下是使用`path.resolve`的示例：
```javascript
import path from 'path';
console.log(path.resolve('./m1'));
```
这段代码会解析并输出`./m1`目录的完整绝对路径，功能类似于在命令行中先`cd`到该目录再执行`pwd`。

## 导出和导入自定义模块

![](img/85988d628516a6d841ace419e002d1b9_23.png)

![](img/85988d628516a6d841ace419e002d1b9_25.png)

现在，让我们看看如何在自己创建的文件之间共享代码。

![](img/85988d628516a6d841ace419e002d1b9_27.png)

![](img/85988d628516a6d841ace419e002d1b9_29.png)

假设我们有一个文件 `manyString.js`，其中包含一个函数：
```javascript
function manyString(times, str) {
    let result = '';
    for (let i = 0; i < times; i++) {
        result += str;
    }
    return result;
}
// 导出这个函数，使其可供其他文件使用
export default manyString;
```
在另一个文件中，我们可以这样导入并使用它：
```javascript
import manyString from './manyString.js';
console.log(manyString(5, 'hello '));
```
**关键点**：一个文件通过`export`来“发送”代码，另一个文件通过`import`来“接收”代码。

![](img/85988d628516a6d841ace419e002d1b9_31.png)

![](img/85988d628516a6d841ace419e002d1b9_33.png)

如果被导入的文件位于不同目录，需要在路径中指明：
```javascript
import manyString from '../lib/manyString.js';
```
- `./` 表示当前目录。
- `../` 表示上一级目录。

![](img/85988d628516a6d841ace419e002d1b9_35.png)

![](img/85988d628516a6d841ace419e002d1b9_37.png)

![](img/85988d628516a6d841ace419e002d1b9_39.png)

## 导出多个项目（命名导出）

上一节我们导出了单个函数，本节中我们来看看如何从一个模块中导出多个函数或变量。

![](img/85988d628516a6d841ace419e002d1b9_41.png)

![](img/85988d628516a6d841ace419e002d1b9_43.png)

![](img/85988d628516a6d841ace419e002d1b9_45.png)

当需要导出多个项目时，我们使用**命名导出**，并省略`default`关键字。

![](img/85988d628516a6d841ace419e002d1b9_47.png)

![](img/85988d628516a6d841ace419e002d1b9_49.png)

以下是导出多个函数的方法：
```javascript
// 方法一：在函数声明前直接导出
export function manyString(times, str) { ... }
export function addBrackets(str) { ... }

// 方法二：在文件末尾统一导出
export { manyString, addBrackets };
```
在导入时，需要使用花括号`{}`来指定要导入的项目：
```javascript
import { manyString, addBrackets } from './myLib.js';
```
**注意**：导入时使用的名称必须与导出时完全一致。

![](img/85988d628516a6d841ace419e002d1b9_51.png)

![](img/85988d628516a6d841ace419e002d1b9_53.png)

## 默认导出 vs. 命名导出

我们已经见到了两种导出方式，理解它们的区别和适用场景非常重要。

![](img/85988d628516a6d841ace419e002d1b9_55.png)

**默认导出 (`export default`)**:
- 一个模块只能有一个默认导出。
- 导入时可以任意命名导入的项目。
- 例如：`import myName from ‘./module.js‘;` 这里的`myName`可以是任何名字。

**命名导出 (`export { thing }`)**:
- 一个模块可以有多个命名导出。
- 导入时必须使用导出时的确切名称（但可以通过“别名”重命名）。
- 通常更受推荐，因为它更明确，且避免了未来扩展时可能出现的兼容性问题。

![](img/85988d628516a6d841ace419e002d1b9_57.png)

![](img/85988d628516a6d841ace419e002d1b9_59.png)

![](img/85988d628516a6d841ace419e002d1b9_60.png)

**命名导出的优势**：
1.  **明确性**：清晰指出导出了什么。
2.  **可扩展性**：未来添加新导出项时，不影响现有导入代码的结构。
3.  **避免命名冲突**：可以通过`as`关键字创建别名。

重命名示例：
```javascript
// 导入时将 `isValid` 重命名为 `dateFuncIsValid`
import { isValid as dateFuncIsValid } from 'date-fns';
```

![](img/85988d628516a6d841ace419e002d1b9_62.png)

## 代码风格与最佳实践

随着项目变大，良好的代码风格有助于提高可读性。

当从同一个模块导入很多项目时，建议将导入语句分成多行：
```javascript
import {
    functionA,
    functionB,
    constantC,
    ClassD
} from './largeModule.js';
```
在编程中，**可读性**通常比微小的“聪明”优化更重要。现代编译器和解释器非常智能，能够高效处理代码。清晰的代码能让团队成员（包括未来的你）更容易理解和维护。

## 总结

本节课中我们一起学习了JavaScript中多文件编程的核心机制：
1.  使用 `import` 和 `export` 在文件间共享代码。
2.  **默认导出**用于导出一个主要项目，导入时可自定义名称。
3.  **命名导出**用于导出多个项目，导入时需使用对应名称，更推荐使用。
4.  可以通过 `as` 关键字解决命名冲突或提高清晰度。
5.  良好的代码组织和可读性是高质量软件的基础。

![](img/85988d628516a6d841ace419e002d1b9_64.png)

记住，虽然掌握语法很重要，但编写清晰、易于他人理解的代码是更重要的长期技能。