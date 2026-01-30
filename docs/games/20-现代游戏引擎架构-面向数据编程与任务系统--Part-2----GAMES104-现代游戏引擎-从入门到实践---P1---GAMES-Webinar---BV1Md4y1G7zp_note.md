![](img/d56be7a995132f5163a102a2693f91a7_0.png)

# 20.现代游戏引擎架构：面向数据编程与任务系统 (Part 2) ｜ GAMES104-现代游戏引擎：从入门到实践 - P1 - GAMES-Webinar - BV1Md4y1G7zp

![](img/d56be7a995132f5163a102a2693f91a7_0.png)

## 概述

在本节课中，我们将深入探讨现代游戏引擎架构中的面向数据编程（Data-Oriented Programming，简称DOP）和任务系统。我们将分析面向对象编程（Object-Oriented Programming，简称OOP）的局限性，并介绍DOP如何解决这些问题。

## 面向对象编程的局限性

### 1. 代码一致性差

面向对象编程虽然直观，但容易导致代码一致性差。例如，攻击者与受害者之间的关系在不同程序员之间可能存在不同的实现方式。

### 2. 深度继承树

面向对象编程的继承树可能非常深，这使得在大型系统中查找函数实现变得困难。

### 3. 基类臃肿

面向对象编程的基类可能包含大量功能，导致派生类变得臃肿。

### 4. 性能问题

面向对象编程的性能可能较低，因为数据分散在各个对象中，且对象创建和销毁需要频繁进行内存分配和释放。

### 5. 可测试性差

面向对象编程的可测试性较差，因为难以将单个模块从系统中提取出来进行测试。

## 面向数据编程

### 1. 数据局部性

面向数据编程强调数据局部性，即数据应尽可能紧密地存储在一起，以便CPU可以高效地访问和处理。

### 2. 数组结构（AoS）和结构数组（SoA）

面向数据编程推荐使用结构数组（SoA）而不是数组结构（AoS）来组织数据，以提高内存访问效率。

### 3. ECS系统

ECS（Entity Component System）系统将数据、组件和系统分离，以充分利用数据局部性和提高性能。

### 4. Unity的DOTS系统

Unity的DOTS系统基于ECS，并使用 Burst Compiler将C#代码编译成原生代码，以提高性能。

### 5. Unreal Engine的Max系统

Unreal Engine的Max系统类似于DOTS，并使用Fragment和Processor的概念来处理数据。

## 总结

本节课介绍了面向数据编程和任务系统，并分析了面向对象编程的局限性。我们了解到，面向数据编程可以提高性能和可测试性，并介绍了ECS系统和Unity的DOTS系统等实际应用案例。

## 参考资料

![](img/d56be7a995132f5163a102a2693f91a7_2.png)

![](img/d56be7a995132f5163a102a2693f91a7_3.png)

*   [Cash系统](https://www.example.com/cash-system)
*   [并行编程](https://www.example.com/parallel-programming)
*   [面向数据编程](https://www.example.com/data-oriented-programming)