# 数据结构：讨论3：静态与实例变量解析 🧩

![](img/e96333d5f61257b9967bdc00913765d3_0.png)

在本节课中，我们将通过分析一个关于`Pokemon`类的Java程序，来学习静态变量、实例变量以及方法调用的核心概念。我们将逐步执行代码，并绘制环境图来可视化变量的状态变化。

---

## 概述 📋

我们将分析一个包含`Pokemon`类的Java程序。该类具有实例变量（如`name`和`level`）、静态变量（如`trainer`和`partySize`），以及实例方法和静态方法。通过逐步执行`main`方法，我们将理解不同变量的作用域、生命周期以及它们如何被修改。

---

## 第一部分：绘制环境图与代码执行 🗺️

为了清晰地追踪变量状态，我们首先绘制一个环境图。图中将包含`main`方法的局部变量、创建的`Pokemon`实例对象，以及`Pokemon`类的静态变量区。

以下是`Pokemon`类的关键部分：
```java
public class Pokemon {
    private String name;
    private int level;
    private static String trainer = "Ash";
    private static int partySize = 0;

    // 构造方法、main方法、change静态方法、printStats实例方法...
}
```

在`main`方法开始前，静态变量已初始化：`trainer`为“Ash”，`partySize`为0。

### 逐步执行`main`方法

1.  **第14行：创建第一个Pokemon**
    ```java
    Pokemon p = new Pokemon("Pikachu", 17);
    ```
    *   创建一个新的`Pokemon`实例，其`name`为“Pikachu”，`level`为17。
    *   变量`p`指向该对象。
    *   执行构造方法，`partySize`增加1，变为1。

2.  **第15行：创建第二个Pokemon**
    ```java
    Pokemon j = new Pokemon("Jolteon", 99);
    ```
    *   创建另一个`Pokemon`实例，其`name`为“Jolteon”，`level`为99。
    *   变量`j`指向该对象。
    *   执行构造方法，`partySize`再次增加1，变为2。

3.  **第16行：第一次打印**
    ```java
    System.out.println("party size: " + Pokemon.partySize);
    ```
    *   直接通过类名`Pokemon`访问静态变量`partySize`，其值为2。
    *   **输出：** `party size: 2`

4.  **第17行：调用实例方法`printStats`**
    ```java
    p.printStats();
    ```
    *   在实例`p`上调用`printStats()`方法。该方法打印该实例的`name`、`level`和静态变量`trainer`。
    *   `p.name` 是 “Pikachu”， `p.level` 是 17， `trainer` 是 “Ash”。
    *   **输出：** `Pikachu 17 Ash`

上一节我们介绍了对象的创建和实例方法的调用，本节中我们来看看当方法涉及参数传递和变量作用域时会发生什么。

5.  **第18-19行：调用静态方法`change`**
    ```java
    int level = 18;
    Pokemon.change(p, level);
    ```
    *   声明局部变量`level`并赋值为18。
    *   调用静态方法`change`，传入实例`p`和变量`level`的值。

    为了理解`change`方法内部的操作，我们需要为其创建新的局部变量框架：

    *   **参数传递：**
        *   参数`poke`接收的是指向`p`所指向对象的**指针的副本**。因此，`poke`也指向内存中同一个“Pikachu”对象。
        *   参数`level`是基本类型`int`，因此接收的是值`18`的副本。
    *   **`change`方法内部操作（第27-30行）：**
        *   `poke.level = level;`：这将修改`poke`指向的对象（即“Pikachu”）的`level`属性。由于`poke.level`指向实例变量，而传入的`level`参数值为18，因此“Pikachu”的`level`被改为18。
        *   `level = 50;`：这修改的是`change`方法局部变量`level`的值，将其从18改为50。**这并不影响`main`方法中的`level`变量，也不影响任何`Pokemon`对象的`level`。**
        *   `poke = new Pokemon("Luxray", 1);`：这创建了一个新的`Pokemon`实例（“Luxray”, 1）。`poke`局部变量现在改为指向这个新对象。**注意：** 这**不会**改变`main`方法中`p`的指向，`p`仍然指向原来的“Pikachu”对象。同时，构造方法使`partySize`增加为3。
        *   `poke.trainer = "Team Rocket";`：`trainer`是静态变量。通过任何实例（此处是`poke`指向的新“Luxray”对象）修改静态变量，都会影响整个类。因此，静态变量`trainer`被改为“Team Rocket”。
    *   **方法返回：** `change`方法结束，其局部变量`poke`和`level`被销毁。新创建的“Luxray”对象由于没有其他引用指向它，随后会被Java垃圾回收。

6.  **第20行：再次调用`p.printStats()`**
    ```java
    p.printStats();
    ```
    *   再次在实例`p`上调用`printStats()`。
    *   `p.name` 仍是 “Pikachu”。
    *   `p.level` 在上一步中被改为 18。
    *   `trainer` 静态变量在上一步中被改为 “Team Rocket”。
    *   **输出：** `Pikachu 18 Team Rocket`

7.  **第21-22行：直接修改静态变量和通过实例修改**
    ```java
    Pokemon.trainer = "Ash";
    j.trainer = "Cynthia";
    ```
    *   `Pokemon.trainer = "Ash";`：直接通过类名将静态变量`trainer`改回“Ash”。
    *   `j.trainer = "Cynthia";`：通过实例`j`访问并修改静态变量`trainer`。这同样会修改整个类的静态变量，将其从“Ash”改为“Cynthia”。

8.  **第23行：第三次调用`p.printStats()`**
    ```java
    p.printStats();
    ```
    *   `p.name` 仍是 “Pikachu”。
    *   `p.level` 仍是 18。
    *   `trainer` 静态变量现在是 “Cynthia”。
    *   **输出：** `Pikachu 18 Cynthia`

### 第一部分输出总结

以下是执行`main`方法后控制台的完整输出：
```
party size: 2
Pikachu 17 Ash
Pikachu 18 Team Rocket
Pikachu 18 Cynthia
```

---

## 第二部分：理解变量作用域 🔍

现在，我们来回答一个关于变量作用域的具体问题。

**问题：** 在`change`方法的第28行`level = 50;`中，`level`指的是哪个变量？

**分析与答案：**
在`change`方法内部，当引用`level`时，Java首先在方法的局部作用域内查找。参数`level`就是一个局部变量。因此，第28行的`level`指的是**作为参数传入`change`方法的局部变量`level`**。这行代码改变了这个局部变量的值，但不会影响`main`方法中的`level`变量，也不会影响任何`Pokemon`对象的实例变量`level`。

---

## 第三部分：辨析静态方法与实例方法调用 ⚠️

最后，我们探讨一个关于方法调用的关键问题。

**问题：** 如果在`main`方法的末尾尝试调用`Pokemon.printStats()`，会发生什么？

**分析与答案：**
`printStats()`方法在类中被定义为实例方法（没有`static`关键字）。实例方法的设计必须在一个具体的对象实例上调用，因为其方法体中通常会访问该实例特有的属性（如`this.name`, `this.level`）。

`Pokemon.printStats()`这种调用方式试图在**类本身**上调用实例方法。类`Pokemon`是一个蓝图，它本身并没有`name`或`level`这样的具体值。因此，Java编译器或运行时无法确定`printStats()`方法中的`name`和`level`应该指向什么。

所以，这样的调用会导致**编译错误**（或某些语言中的运行时错误），错误信息大致意为“无法从静态上下文中引用非静态方法”。

---

## 总结 🎯

本节课中我们一起学习了：

1.  **静态变量 vs 实例变量：** 静态变量属于类，所有实例共享同一份拷贝；实例变量属于对象，每个对象拥有独立拷贝。
2.  **环境图可视化：** 通过绘制环境图，可以清晰追踪对象创建、引用传递和变量状态变化的过程。
3.  **参数传递：** 对象引用传递的是指针副本，修改对象内容会影响原对象；基本类型传递的是值副本。
4.  **变量作用域：** 局部变量优先于外部变量，方法内部的操作可能只影响局部副本。
5.  **方法调用限制：** 实例方法必须在对象实例上调用，不能直接在类上调用。

![](img/e96333d5f61257b9967bdc00913765d3_2.png)

通过这个具体的例子，你应该对Java中静态与实例成员的区别、方法调用机制以及参数传递行为有了更直观的理解。