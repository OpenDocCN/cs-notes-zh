# 024：浏览器中的JavaScript执行模型 🚀

在本节课中，我们将要学习JavaScript在浏览器环境中的独特执行模型。我们将探讨它与传统编程语言（如Python）的区别，并理解事件驱动、非阻塞执行等核心概念。

## 概述

JavaScript不仅是一种编程语言，在浏览器中运行时，它还承担了部分类似操作系统的职责。与在操作系统上运行、可以执行“等待”操作的Python程序不同，浏览器中的JavaScript采用**协作式多任务**模型。这意味着开发者需要帮助浏览器协调诸如更新文档对象模型、处理滚动、管理多个标签页事件以及处理计时器等多种任务。

## 浏览器中的执行时机

![](img/ab6c59ac2912179caf8a14ddc9c496da_1.png)

JavaScript代码可以在多个不同的时机被触发执行。以下是主要的几种情况：

![](img/ab6c59ac2912179caf8a14ddc9c496da_3.png)

*   **文档解析时**：当浏览器解析HTML遇到`<script>`标签时，会暂停解析并立即执行其中的JavaScript代码。
*   **用户界面事件触发时**：例如用户点击（`click`）、调整窗口大小（`resize`）等。
*   **计时器到期时**：通过`setTimeout`或`setInterval`设置的延时任务。
*   **异步活动完成时**：例如通过网络请求（如`fetch`）获取数据完成。

这种模型的核心在于，我们需要告诉浏览器：“**当某件事发生时，请运行这段代码**”。这直接引出了JavaScript中**一等函数**概念的重要性，因为函数可以作为数据被传递和存储，以便在将来某个时刻被调用。

## 代码执行方式解析

![](img/ab6c59ac2912179caf8a14ddc9c496da_5.png)

上一节我们介绍了JavaScript的执行时机，本节中我们来看看几种具体的代码执行方式及其原理。

![](img/ab6c59ac2912179caf8a14ddc9c496da_7.png)

### 1. 无JavaScript的页面

首先，看一个最简单的HTML页面（`01-noscript.htm`），它不包含任何JavaScript。

```html
<h1>Hello World</h1>
<p>This is a paragraph.</p>
```

浏览器收到服务器响应后，会解析这些HTML标签并构建**文档对象模型**。你在开发者工具“检查元素”中看到的，并非原始的服务器响应文本，而是浏览器根据解析结果创建的DOM树。在此过程中，JavaScript引擎处于闲置状态。

![](img/ab6c59ac2912179caf8a14ddc9c496da_9.png)

### 2. 完全由JavaScript生成的页面

接下来是一个极端的例子（`02-document-write.htm`），整个页面内容完全由JavaScript生成。

```html
<script>
    document.write("<h1>Hello World</h1>");
    document.write("<p>This is a paragraph.</p>");
</script>
```

这个页面没有直接的HTML标签。当浏览器解析到`<script>`标签时，会立即执行其中的`document.write()`方法。该方法会直接将传入的HTML字符串写入DOM。因此，尽管源代码不同，但最终生成的DOM与第一个例子完全相同。这说明了**JavaScript在解析阶段就能完全控制DOM的构建**。

![](img/ab6c59ac2912179caf8a14ddc9c496da_11.png)

### 3. 通过事件属性执行代码

更常见的方式是将JavaScript代码与用户事件绑定。例如，在HTML标签的`onclick`属性中内联编写代码（`03-onclick.htm`）。

```html
<a href="#" onclick="console.log('I was clicked');">Click Me</a>
<script>
    function myFunc() {
        console.log("I was clicked (from function)");
    }
</script>
```

页面解析时，`<script>`标签内的`myFunc`函数被定义，但不会立即执行。`onclick`属性中的字符串`"console.log('I was clicked');"`也被解析。只有当用户点击链接时，浏览器才会执行这段字符串形式的代码。`onclick`属性是指定事件处理程序的一种直接方式。

### 4. 通过计时器执行代码

![](img/ab6c59ac2912179caf8a14ddc9c496da_13.png)

JavaScript还可以通过计时器在未来某个时刻执行代码，这是异步编程的基础（`04-timer.htm`）。

![](img/ab6c59ac2912179caf8a14ddc9c496da_15.png)

```html
<h1>Timer Test</h1>
<p>Check the console.</p>
<script>
    function myFunc() {
        console.log("I was called later");
    }
    setTimeout(myFunc, 5000); // 5秒后执行myFunc
    console.log("Timer started");
</script>
```

解析到`<script>`标签时，代码立即执行。关键点在于`setTimeout(myFunc, 5000)`这行代码：它**立即返回**，并不会等待5秒。它只是向浏览器注册了一个任务：“5秒后，请调用`myFunc`函数”。因此，控制台会先立刻输出“Timer started”，大约5秒后再输出“I was called later”。计时器到期就是一个触发代码执行的事件。

![](img/ab6c59ac2912179caf8a14ddc9c496da_17.png)

### 5. 一等函数的关键作用

理解上述事件模型的关键是**一等函数**。我们通过修改计时器例子来演示这一点（`05-function-ref.htm`）。

```javascript
function myFunc() {
    console.log("I was called later");
}
console.log(myFunc); // 输出：ƒ myFunc() { ... }
setTimeout(myFunc, 5000); // 注意：myFunc后没有括号()
```

这里有一个重要区别：
*   `myFunc()`：带括号表示**调用函数**，会立即执行函数体并返回其返回值。
*   `myFunc`：不带括号表示**函数引用**，它是一个代表函数本身的值，可以像变量一样被传递。

![](img/ab6c59ac2912179caf8a14ddc9c496da_19.png)

![](img/ab6c59ac2912179caf8a14ddc9c496da_20.png)

![](img/ab6c59ac2912179caf8a14ddc9c496da_21.png)

`setTimeout`需要接收一个函数引用作为参数，以便在将来调用它。如果错误地写成`setTimeout(myFunc(), 5000)`，则会立即执行`myFunc`，并将其返回值（可能是`undefined`）传给`setTimeout`，导致计时器设置失败。`console.log(myFunc)`的输出直接展示了这个函数对象。

![](img/ab6c59ac2912179caf8a14ddc9c496da_22.png)

![](img/ab6c59ac2912179caf8a14ddc9c496da_24.png)

## 总结

![](img/ab6c59ac2912179caf8a14ddc9c496da_26.png)

本节课中我们一起学习了JavaScript在浏览器中的执行模型。我们了解到它与传统阻塞式编程的区别，核心在于**事件驱动**和**非阻塞执行**。JavaScript代码可以通过文档解析、UI事件、计时器或异步回调等多种方式被触发。**一等函数**是这个模型得以实现的基石，它允许我们将函数作为参数传递，从而告诉浏览器“在事件发生时执行这个函数”。掌握这些概念是理解现代前端异步编程（如Promise、async/await）的基础。接下来，我们将更深入地探讨如何使用JavaScript来操作**文档对象模型**。