# 全栈开发：P7：JavaScript 进阶概念（作用域与异步）🚀

![](img/2c08eb44f71fd5e70b78fc82e83f390d_1.png)

![](img/2c08eb44f71fd5e70b78fc82e83f390d_3.png)

![](img/2c08eb44f71fd5e70b78fc82e83f390d_5.png)

![](img/2c08eb44f71fd5e70b78fc82e83f390d_7.png)

![](img/2c08eb44f71fd5e70b78fc82e83f390d_9.png)

![](img/2c08eb44f71fd5e70b78fc82e83f390d_11.png)

![](img/2c08eb44f71fd5e70b78fc82e83f390d_13.png)

在本节课中，我们将要学习 JavaScript 中的两个核心概念：**作用域** 和 **异步编程**。我们将从函数声明和作用域规则开始，然后深入探讨如何编写非阻塞的异步代码，包括回调、Promise 以及现代的 `async/await` 语法。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_15.png)

---

## 函数声明：常规函数与箭头函数

![](img/2c08eb44f71fd5e70b78fc82e83f390d_17.png)

![](img/2c08eb44f71fd5e70b78fc82e83f390d_19.png)

![](img/2c08eb44f71fd5e70b78fc82e83f390d_21.png)

![](img/2c08eb44f71fd5e70b78fc82e83f390d_23.png)

JavaScript 中有两种主要的函数声明方式：常规函数和箭头函数。它们功能相似，但在语法和 `this` 关键字的行为上有所不同。

以下是一个常规函数：
```javascript
function add(x, y) {
    return x + y;
}
```

以下是一个箭头函数：
```javascript
const addTwo = (x, y) => {
    return x + y;
}
```

常规函数在调试时，堆栈跟踪会显示函数名，而箭头函数有时会显示为“匿名函数”，这可能使调试稍微困难一些。除此之外，它们本质上执行相同的任务。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_25.png)

运行上述代码，两者都会返回预期的相加结果。`console.log` 是 JavaScript 中打印输出的主要方式。

---

![](img/2c08eb44f71fd5e70b78fc82e83f390d_27.png)

## 作用域与变量声明

![](img/2c08eb44f71fd5e70b78fc82e83f390d_29.png)

上一节我们介绍了函数，本节中我们来看看变量在代码中的可访问范围，即作用域。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_31.png)

JavaScript 使用**词法作用域**。这意味着，如果在当前作用域中找不到某个变量，解释器会向上一级作用域查找，就像 Python 中使用了 `nonlocal` 关键字一样。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_33.png)

以下是声明变量的三种方式：
*   **`var`**：**不建议使用**。它的行为怪异，例如变量声明会被“提升”到作用域顶部，容易导致难以调试的问题。
*   **`let`**：允许你重新赋值，但不能在同一作用域内重新声明。
*   **`const`**：声明一个常量，**不能被重新赋值**。但请注意，如果常量指向一个对象或数组，其内部属性或元素仍然是可变的。

最佳实践是：默认使用 `const`，只有当确定需要重新赋值时，才改为使用 `let`。应尽量避免使用 `var`。

例如：
```javascript
const a = 5;
a = 10; // 错误：Assignment to constant variable.
a.property = 10; // 正确：可以修改对象的属性。
```

---

## `this` 关键字

![](img/2c08eb44f71fd5e70b78fc82e83f390d_35.png)

在 Python 或 Java 中，`this`（或 `self`）通常指向当前类的实例。但在 JavaScript 中，`this` 的值是动态的，取决于函数是如何被调用的。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_37.png)

以下是 `this` 的几种常见情况：
*   对于大多数函数，`this` 指向调用该函数的“所有者”对象。
*   如果函数没有所有者（如全局函数），在严格模式下 `this` 是 `undefined`，非严格模式下是全局对象。
*   可以使用 `.bind()` 方法显式地绑定 `this` 的值。
*   **箭头函数不绑定自己的 `this`**，它会从定义它的外层作用域继承 `this` 值。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_39.png)

![](img/2c08eb44f71fd5e70b78fc82e83f390d_40.png)

考虑以下示例：
```javascript
const me = {
    petName: ‘dog‘,
    numberPets: 1,
    getPetName: function() { return this.petName; },
    morePets: function() { this.numberPets++; }
};

![](img/2c08eb44f71fd5e70b78fc82e83f390d_42.png)

const stolenMorePets = me.morePets;
stolenMorePets(); // 此时函数内的 `this` 不是 `me`，所以 `me.numberPets` 不会增加。

const you = { petName: ‘cat‘, numberPets: 1 };
const boundFunction = stolenMorePets.bind(you);
boundFunction(); // 此时函数内的 `this` 被绑定为 `you`，所以 `you.numberPets` 会增加。
```

---

![](img/2c08eb44f71fd5e70b78fc82e83f390d_44.png)

## 异步 JavaScript 简介

在 Web 开发中，我们经常需要执行耗时操作（如网络请求）。如果等待这些操作完成再更新页面，用户体验会很差。异步编程允许我们在等待操作完成的同时，保持页面的交互性。

然而，编写异步代码可能很复杂，并可能引发**竞态条件**（当多个异步操作以意外顺序修改数据时）。JavaScript 是单线程的，所以没有死锁问题，但数据竞争依然存在。

---

## 回调函数

最初，JavaScript 使用**回调函数**来处理异步操作。回调是一个在异步事件完成后被调用的函数。

以下是使用回调的例子（嵌套回调常被称为“回调地狱”）：
```javascript
function callbackHell() {
    setTimeout(() => {
        console.log(‘First job done‘);
        setTimeout(() => {
            console.log(‘Second job done‘);
            setTimeout(() => {
                console.log(‘Third job done‘);
            }, 1000);
        }, 1000);
    }, 1000);
}
callbackHell();
console.log(‘Called callbackHell first‘);
```

![](img/2c08eb44f71fd5e70b78fc82e83f390d_46.png)

`setTimeout` 函数接受一个回调函数和延迟的毫秒数。它会在指定时间后将回调函数放入任务队列。JavaScript 的事件循环会同步执行完所有代码后，再执行队列中的异步任务。因此，最后的 `console.log` 会先打印出来。

当需要串联多个异步操作时，嵌套回调会使代码难以阅读和维护。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_48.png)

---

## Promise

为了解决回调地狱的问题，ES6 引入了 **Promise**。Promise 是一个对象，它代表一个异步操作的最终完成（或失败）及其结果值。

一个 Promise 有三种状态：
*   **Pending（待定）**：初始状态。
*   **Fulfilled（已兑现）**：操作成功完成。
*   **Rejected（已拒绝）**：操作失败。

你可以使用 `.then()` 处理成功情况，使用 `.catch()` 处理失败情况。

以下是一个 Promise 示例：
```javascript
function betterJob(succeed, time) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            if (succeed) {
                resolve();
            } else {
                reject();
            }
        }, time);
    });
}

betterJob(true, 1000)
    .then(() => console.log(‘Successfully did the job‘),
          () => console.log(‘Job failed‘))
    .catch((error) => console.log(‘Caught an error:‘, error));
```

`.then()` 方法接受两个回调函数作为参数（成功和失败），`.catch()` 则用于捕获链中任何未被处理的错误。Promise 链式调用提高了代码的可读性。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_50.png)

![](img/2c08eb44f71fd5e70b78fc82e83f390d_52.png)

---

![](img/2c08eb44f71fd5e70b78fc82e83f390d_54.png)

## Async/Await

虽然 Promise 链比回调更好，但代码仍然不是完全同步的风格。ES7 引入了 `async` 和 `await` 关键字，使得异步代码看起来和同步代码一样。

*   在函数前加上 `async` 关键字，使其成为异步函数。
*   在 Promise 前加上 `await` 关键字，它会“暂停”函数的执行，直到 Promise 被解决，并返回结果值。
*   可以使用传统的 `try...catch` 块来处理错误。

以下是使用 `async/await` 的例子：
```javascript
async function promiseAsyncFunction() {
    try {
        const result = await betterJob(true, 1000); // 假设返回值为 5
        console.log(‘On success:‘, result); // 输出：5
        const failedResult = await betterJob(false, 1000); // 假设拒绝值为 10
        console.log(‘This will not print‘);
    } catch (error) {
        console.log(‘Caught error with value:‘, error); // 输出：10
    }
}
promiseAsyncFunction();
console.log(‘This prints first‘);
```

![](img/2c08eb44f71fd5e70b78fc82e83f390d_56.png)

`await` 在心理模型上可以理解为“阻塞”线程直到 Promise 完成（实际上并非如此，但有助于理解）。`async/await` 是现代 JavaScript 中处理异步操作的首选方式，因为它使代码更清晰、更易于调试。

---

## 补充：Fetch API

`fetch()` 是一个用于发起网络请求的 Web API，它返回一个 Promise。你可以用它来获取远程资源的数据，并使用我们刚学到的 Promise 或 `async/await` 来处理响应。

```javascript
async function getData() {
    try {
        const response = await fetch(‘https://api.example.com/data‘);
        const data = await response.json();
        console.log(data);
    } catch (error) {
        console.error(‘Fetch error:‘, error);
    }
}
```

---

## 总结

![](img/2c08eb44f71fd5e70b78fc82e83f390d_58.png)

本节课中我们一起学习了 JavaScript 的核心进阶概念。
1.  **作用域与变量**：理解了 `let`、`const` 和 `var` 的区别，以及词法作用域的工作方式。
2.  **`this` 关键字**：了解了 `this` 的动态绑定特性，以及箭头函数在此处的不同行为。
3.  **异步编程**：从最初的**回调函数**及其“地狱”嵌套问题，到更优雅的 **Promise** 链式调用，最后到使用 **`async/await`** 编写类似同步风格的异步代码。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_60.png)

![](img/2c08eb44f71fd5e70b78fc82e83f390d_61.png)

![](img/2c08eb44f71fd5e70b78fc82e83f390d_63.png)

掌握这些概念对于构建高效、可维护的现代 Web 应用至关重要。在实践中，应优先使用 `const`/`let`、箭头函数以及 `async/await` 来编写清晰可靠的代码。