# 019：JavaScript面向对象-类 🧩

在本节课中，我们将学习如何在JavaScript中构建和使用类。我们将了解类的内部工作原理，包括如何定义类、创建实例、理解构造函数以及管理多个独立的对象实例。

![](img/16fad4d178a71749f2d47b9e5a440cb0_1.png)

---

## 概述

![](img/16fad4d178a71749f2d47b9e5a440cb0_3.png)

![](img/16fad4d178a71749f2d47b9e5a440cb0_4.png)

JavaScript中的类是一种创建对象的模板。虽然ES6引入了更简洁的类语法，但理解其底层基于函数的实现方式，能帮助我们更深刻地掌握JavaScript面向对象编程的核心机制。本节将介绍如何使用`function`关键字定义类，如何使用`new`关键字创建实例，以及`this`关键字在其中的作用。

![](img/16fad4d178a71749f2d47b9e5a440cb0_6.png)

![](img/16fad4d178a71749f2d47b9e5a440cb0_7.png)

---

![](img/16fad4d178a71749f2d47b9e5a440cb0_9.png)

## 类的定义与构造函数

![](img/16fad4d178a71749f2d47b9e5a440cb0_11.png)

![](img/16fad4d178a71749f2d47b9e5a440cb0_13.png)

上一节我们介绍了对象的基本概念，本节中我们来看看如何在JavaScript中定义一个类。在JavaScript中，类本质上是一个特殊的函数。

![](img/16fad4d178a71749f2d47b9e5a440cb0_14.png)

**定义类的基本语法如下：**
```javascript
function PartyAnimal() {
    this.x = 0;
    this.party = function() {
        this.x = this.x + 1;
        console.log("So far " + this.x);
    };
}
```
*   `function PartyAnimal()` 是类的定义，其名称`PartyAnimal`就是类名。
*   在函数体内部，`this`关键字代表即将创建的新对象实例。
*   `this.x = 0;` 为实例创建了一个名为`x`的属性（成员变量），并初始化为0。
*   `this.party = function() { ... }` 为实例创建了一个名为`party`的方法。这里使用了一个匿名函数。

![](img/16fad4d178a71749f2d47b9e5a440cb0_16.png)

![](img/16fad4d178a71749f2d47b9e5a440cb0_18.png)

---

![](img/16fad4d178a71749f2d47b9e5a440cb0_20.png)

![](img/16fad4d178a71749f2d47b9e5a440cb0_21.png)

## 创建类的实例

![](img/16fad4d178a71749f2d47b9e5a440cb0_23.png)

![](img/16fad4d178a71749f2d47b9e5a440cb0_25.png)

定义好类之后，我们需要使用`new`关键字来创建具体的对象实例。

![](img/16fad4d178a71749f2d47b9e5a440cb0_27.png)

**创建实例的语法如下：**
```javascript
let an = new PartyAnimal();
```
*   `new PartyAnimal()` 是关键步骤。`new`操作符会执行以下操作：
    1.  创建一个新的空对象。
    2.  将`PartyAnimal`函数中的代码在这个新对象的上下文中执行（此时函数内的`this`就指向这个新对象）。
    3.  执行构造函数中的代码（如`this.x = 0`），为对象设置初始状态。
    4.  返回这个新创建并初始化好的对象。
*   `let an =` 将这个新创建的对象赋值给变量`an`，这样我们就可以通过`an`来操作这个实例了。

---

## 调用对象的方法

![](img/16fad4d178a71749f2d47b9e5a440cb0_29.png)

创建实例后，我们可以通过点符号（`.`）来访问其属性和调用其方法。

![](img/16fad4d178a71749f2d47b9e5a440cb0_31.png)

以下是调用方法的示例：
```javascript
an.party(); // 输出: So far 1
an.party(); // 输出: So far 2
an.party(); // 输出: So far 3
```
每次调用`an.party()`方法时，都会执行方法内的代码：将实例自身的`x`属性加1，然后打印出当前值。由于`an`是`PartyAnimal`的一个实例，方法内的`this.x`指的就是`an.x`。

![](img/16fad4d178a71749f2d47b9e5a440cb0_33.png)

---

![](img/16fad4d178a71749f2d47b9e5a440cb0_34.png)

![](img/16fad4d178a71749f2d47b9e5a440cb0_35.png)

## 构造函数详解

构造函数是类中一段特殊的代码，它在使用`new`关键字创建新实例时自动执行，用于初始化对象的状态。

![](img/16fad4d178a71749f2d47b9e5a440cb0_37.png)

**一个带有构造函数的类示例：**
```javascript
function PartyAnimal(name) {
    this.x = 0;
    this.name = name;
    console.log("Built " + this.name);
    this.party = function() {
        this.x = this.x + 1;
        console.log(this.name + "=" + this.x);
    };
}
```
*   构造函数可以接收参数。这里的`name`参数在创建实例时传入。
*   `this.name = name;` 将传入的参数赋值给实例的`name`属性。
*   `console.log("Built " + this.name);` 这行代码让我们能直观地看到构造函数何时被执行。

![](img/16fad4d178a71749f2d47b9e5a440cb0_39.png)

![](img/16fad4d178a71749f2d47b9e5a440cb0_40.png)

---

## 创建多个独立实例

类的强大之处在于可以根据同一个模板创建多个相互独立的实例，每个实例都拥有自己独立的属性值。

以下是创建多个实例的示例：
```javascript
let s = new PartyAnimal("Sally");
let j = new PartyAnimal("Jim");

![](img/16fad4d178a71749f2d47b9e5a440cb0_42.png)

![](img/16fad4d178a71749f2d47b9e5a440cb0_43.png)

s.party(); // 输出: Sally=1
j.party(); // 输出: Jim=1
s.party(); // 输出: Sally=2
```
*   `let s = new PartyAnimal("Sally");` 创建了第一个实例`s`，其`name`属性为"Sally"，`x`初始为0。
*   `let j = new PartyAnimal("Jim");` 创建了第二个实例`j`，其`name`属性为"Jim"，`x`初始为0。它与实例`s`完全独立。
*   当调用`s.party()`时，方法内的`this`指向`s`，因此修改的是`s.x`。
*   当调用`j.party()`时，方法内的`this`指向`j`，因此修改的是`j.x`。
*   最后再次调用`s.party()`时，`s.x`从1增加到2，而`j.x`仍然保持为1，这证明了两个实例状态的独立性。

---

## 核心概念总结

![](img/16fad4d178a71749f2d47b9e5a440cb0_45.png)

![](img/16fad4d178a71749f2d47b9e5a440cb0_46.png)

本节课中我们一起学习了JavaScript面向对象编程中关于类的核心概念：

1.  **类 (Class)**：创建对象的模板或蓝图。在JavaScript中，类通过`function`定义。
2.  **实例/对象 (Instance/Object)**：根据类创建的具体实体。使用`new`关键字创建。
3.  **属性 (Attribute/Member Variable)**：对象内部存储的数据，如`this.x`和`this.name`。
4.  **方法 (Method)**：对象内部定义的函数，代表对象的行为，如`this.party`。
5.  **构造函数 (Constructor)**：在创建新实例时自动运行的代码，用于初始化对象的状态。它是类定义函数本身的主体部分。
6.  **`this` 关键字**：在方法或构造函数内部，`this`指向当前所属的对象实例。

![](img/16fad4d178a71749f2d47b9e5a440cb0_48.png)

理解这些概念是后续学习DOM操作、jQuery等高级JavaScript技术的基础。JavaScript（和Python一样）提供了一套成熟而优雅的面向对象编程模型。