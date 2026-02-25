# 16：3 - 讨论3问题2详解 🐕🐈

在本节课中，我们将详细解析UCB CS 61B课程中关于“Java会怎么做”类型的问题。我们将通过一个具体的代码示例，逐步分析静态类型、动态类型、方法重写以及类型转换等核心概念，帮助你理解Java在编译时和运行时的行为。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_1.png)

---

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_3.png)

## 代码初始化与类型分析

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_5.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_7.png)

首先，我们来看代码的第3至6行，这里创建了几个对象。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_9.png)

```java
Animal a = new Dog();
Animal b = new Animal();
Cat c = new Cat();
Dog d = new Dog();
```

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_11.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_13.png)

我们需要确定每个变量的静态类型和动态类型。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_15.png)

*   **静态类型**：声明变量时写在等号左边的类型。
*   **动态类型**：等号右边`new`关键字实际创建的对象类型。

以下是各变量的类型分析：

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_17.png)

| 变量 | 静态类型 | 动态类型 |
| :--- | :--- | :--- |
| `a` | `Animal` | `Dog` |
| `b` | `Animal` | `Animal` |
| `c` | `Cat` | `Cat` |
| `d` | `Dog` | `Dog` |

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_18.png)

---

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_20.png)

## 逐行代码分析

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_22.png)

上一节我们分析了变量的初始类型，本节中我们来看看后续每一行代码的执行情况。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_24.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_26.png)

### 第8行：`Cat e = new Animal();`

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_28.png)

这行代码尝试将一个`Animal`对象赋值给一个`Cat`类型的变量。
赋值规则是：**右侧对象的类型必须是左侧变量类型的子类型（或相同类型）**。
这里，`Animal`是比`Cat`更通用的类型，`Animal`不一定是`Cat`。因此，这会在**编译时**产生错误。运行时不会执行。

**结果**：编译错误。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_30.png)

---

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_32.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_34.png)

### 第9行：`a.greet(c);`

调用方法时，Java会分两步走：编译时检查和运行时执行。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_36.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_38.png)

1.  **编译时**：编译器只关心静态类型。这里`a`的静态类型是`Animal`。编译器检查`Animal`类中是否有`greet(Cat c)`方法。`Animal`类中定义了`greet(Animal a)`方法。由于`Cat`是`Animal`的子类，所以`greet(c)`调用是合法的。编译器记录下将调用`Animal.greet(Animal)`。
2.  **运行时**：JVM关心动态类型。`a`的动态类型是`Dog`。`Dog`类重写了`greet(Animal a)`方法。因此，实际执行的是`Dog`类中的`greet`方法。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_40.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_41.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_43.png)

**执行过程**：
```
Dog.greet(Animal) 被调用。
输出：“Woof! My name is Pluto.”
```

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_45.png)

---

### 第10行：`a.sleep();`

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_47.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_48.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_50.png)

这行代码调用`sleep`方法。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_52.png)

1.  **编译时**：`a`的静态类型是`Animal`，`Animal`类中有静态方法`sleep()`，编译通过。
2.  **运行时**：**对于静态方法，不适用动态方法查找（Dynamic Method Lookup）规则**。无论对象的动态类型是什么，都直接根据静态类型来决定调用哪个方法。因此，调用的是`Animal.sleep()`。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_54.png)

**执行过程**：
```
Animal.sleep() 被调用。
输出：“Nap time.”
```

---

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_56.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_58.png)

### 第11行：`c.play();`

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_60.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_62.png)

这行代码在`Cat`对象上调用`play`方法。

1.  **编译时**：`c`的静态类型是`Cat`，`Cat`类中有`play()`方法，编译通过。
2.  **运行时**：`c`的动态类型也是`Cat`，没有涉及父类引用，直接调用`Cat.play()`。

**执行过程**：
```
Cat.play() 被调用。
输出：“That was fun! Meow.”
```

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_64.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_65.png)

---

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_67.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_69.png)

### 第12行：`c.greet(d);`

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_71.png)

这行代码让一只猫向一只狗打招呼。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_73.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_74.png)

1.  **编译时**：`c`的静态类型是`Cat`。`Cat`类中有`greet(Animal a)`方法。`d`的静态类型是`Dog`，而`Dog`是`Animal`的子类，因此参数匹配，编译通过。
2.  **运行时**：`c`的动态类型是`Cat`，因此执行`Cat.greet(Animal)`方法。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_76.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_78.png)

**执行过程**：
```
Cat.greet(Animal) 被调用。
输出：“Meow! My name is Garfield.”
```

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_80.png)

---

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_82.png)

### 第13行：`((Animal) c).greet(d);`

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_84.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_85.png)

这行代码先将`c`强制转换为`Animal`类型，再调用`greet`。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_87.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_88.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_89.png)

1.  **编译时**：转换后，表达式的静态类型被视为`Animal`。编译器检查`Animal.greet(Dog)`，同样找到`greet(Animal)`方法，编译通过。
2.  **运行时**：强制转换**不改变**对象的动态类型。`c`的动态类型仍然是`Cat`。`Cat`重写了`greet(Animal)`方法，因此实际执行的还是`Cat.greet(Animal)`。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_91.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_93.png)

**执行过程**：与第12行完全相同。
```
Cat.greet(Animal) 被调用。
输出：“Meow! My name is Garfield.”
```

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_95.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_97.png)

---

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_99.png)

### 第14行：`d.sleep();`

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_101.png)

在`Dog`对象上调用`sleep`。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_103.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_105.png)

1.  **编译时**：`d`的静态类型是`Dog`，`Dog`类中有静态方法`sleep()`，编译通过。
2.  **运行时**：同样是静态方法，根据静态类型`Dog`决定调用`Dog.sleep()`。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_107.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_109.png)

**执行过程**：
```
Dog.sleep() 被调用。
输出：“I love napping.”
```

---

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_111.png)

### 第15行：`a = c;`

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_113.png)

这是一个赋值操作。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_114.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_116.png)

1.  **编译时**：检查类型兼容性。左侧`a`的静态类型是`Animal`，右侧`c`的静态类型是`Cat`。`Cat`是`Animal`的子类，因此赋值合法。
2.  **运行时**：赋值后，变量`a`现在指向`c`所指向的同一个对象（一只猫）。因此，**`a`的动态类型从`Dog`变为`Cat`**。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_118.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_119.png)

**执行结果**：`a`的动态类型更新为`Cat`。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_121.png)

---

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_123.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_125.png)

### 第16行：`a.play(14);`

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_127.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_129.png)

尝试用参数`14`调用`a`的`play`方法。

1.  **编译时**：`a`的静态类型是`Animal`。编译器在`Animal`类中查找`play(int)`方法。`Animal`类中只有无参数的`play()`方法，没有`play(int)`。因此，编译器找不到匹配的方法，产生**编译错误**。

**结果**：编译错误。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_131.png)

---

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_133.png)

### 第17行：`((Cat) b).play();`

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_135.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_137.png)

将`b`强制转换为`Cat`后调用`play`。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_139.png)

1.  **编译时**：转换后静态类型被视为`Cat`。`Cat`类中有无参的`play()`方法，编译通过。
2.  **运行时**：检查`b`的动态类型。`b`的动态类型是`Animal`。我们试图将一个通用的`Animal`对象强制转换为更具体的`Cat`类型。由于`Animal`对象不一定就是`Cat`，这种“向下转型”在运行时可能不安全。此处，`b`实际指向一个`Animal`对象，不是`Cat`，因此会抛出**`ClassCastException`**（类转换异常）。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_141.png)

**结果**：运行时错误 (`ClassCastException`)。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_143.png)

---

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_145.png)

### 第18行：`d = (Dog) a;`

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_147.png)

将`a`强制转换为`Dog`后赋值给`d`。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_149.png)

1.  **编译时**：`d`的静态类型是`Dog`。`(Dog) a`将`a`的静态类型视为`Dog`。编译器允许在父类(`Animal`)和子类(`Dog`)之间进行强制转换的声明，因此编译通过。
2.  **运行时**：检查`a`的动态类型。执行此语句时，`a`的动态类型是`Cat`（来自第15行的赋值）。我们试图将`Cat`转换为`Dog`。`Cat`和`Dog`是兄弟类（同级），没有继承关系，这种转换是不允许的。因此，同样会抛出**`ClassCastException`**。

**结果**：运行时错误 (`ClassCastException`)。`d`的赋值不会发生。

---

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_151.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_152.png)

### 第19行：`c = a;`

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_154.png)

尝试将`a`赋值给`c`。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_156.png)

1.  **编译时**：左侧`c`的静态类型是`Cat`，右侧`a`的静态类型是`Animal`。编译器发现右侧类型比左侧更通用，无法保证`Animal`一定是`Cat`，因此会报**编译错误**。除非像下面这样显式地告诉编译器你的意图。

**结果**：编译错误。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_158.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_160.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_162.png)

---

### 补充：`c = (Cat) a;`

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_164.png)

如果我们显式地进行强制转换，如`c = (Cat) a;`。

1.  **编译时**：`(Cat) a`使右侧表达式静态类型被视为`Cat`。`Cat`赋值给`Cat`，编译通过。
2.  **运行时**：检查`a`的动态类型。此时`a`的动态类型就是`Cat`（来自第15行）。强制转换`(Cat)`对一个本来就是`Cat`的对象是安全的，因此转换成功。`c`被赋值为`a`所指向的同一个`Cat`对象。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_166.png)

**结果**：赋值成功，`c`指向原来的猫对象。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_168.png)

---

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_170.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_172.png)

## 总结

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_174.png)

本节课中我们一起学习了如何分析Java程序在编译时和运行时的行为，核心要点如下：

1.  **静态类型与动态类型**：静态类型决定编译时的方法查找和类型检查；动态类型决定运行时实际执行的方法（实例方法）。
2.  **方法调用规则**：
    *   对于**实例方法**，编译时根据静态类型确定方法签名，运行时根据动态类型执行具体的方法实现（动态绑定）。
    *   对于**静态方法**，无论编译时还是运行时，都只根据静态类型决定调用哪个方法。
3.  **赋值与类型兼容性**：可以将子类对象赋值给父类变量（向上转型，安全），反之则需要强制转换（向下转型，可能不安全）。
4.  **强制转换的风险**：编译时允许声明父类与子类间的转换，但运行时若实际对象类型与转换目标类型不兼容（如兄弟类之间转换，或父类对象转非实际子类），则会抛出`ClassCastException`。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_176.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_178.png)

理解这些概念是掌握Java多态性和面向对象编程的关键。