# 46：抽象类和方法 🧩

在本节课中，我们将要学习面向对象编程中的一个重要概念：抽象类和方法。抽象类提供了一种定义通用接口和强制子类实现特定方法的方式，有助于提高代码的一致性、互操作性和可维护性。

## 什么是抽象类？ 🤔

上一节我们介绍了课程概述，本节中我们来看看抽象类的核心定义。

在面向对象编程中，抽象类是一种**无法被实例化**的类。你不能直接创建一个抽象类的对象。它的主要作用是作为其他类的“蓝图”或“模板”。

**公式/概念**：`抽象类` = 一个不能被实例化、用于定义子类必须实现的方法的类。

![](img/5338a094655ffa6e35abef70b8b4f445_1.png)

## 抽象类的作用与优势 🚀

![](img/5338a094655ffa6e35abef70b8b4f445_3.png)

了解了抽象类的基本定义后，我们来看看为什么需要使用它。

![](img/5338a094655ffa6e35abef70b8b4f445_4.png)

抽象类的主要作用是确保所有从它派生出来的子类都具备某些特定的功能。例如，“交通工具”（Vehicle）可以是一个抽象类。你不能创建一个“交通工具”对象，但你可以从它派生出“汽车”（Car）、“拖拉机”（Tractor）或“小船”（Boat）。

![](img/5338a094655ffa6e35abef70b8b4f445_6.png)

将方法定义在抽象类中，可以保证这些方法一定会出现在派生类中，因为派生类必须实现它们。如果“交通工具”有一个 `turn_on_engine`（启动引擎）方法，那么我们就可以确信，任何对派生类调用 `turn_on_engine` 的代码都能找到这个方法。

![](img/5338a094655ffa6e35abef70b8b4f445_8.png)

使用抽象类主要出于以下原因：
*   **互操作性**：确保不同子类对象能以统一的方式被调用。
*   **一致性**：强制子类遵循相同的接口规范。
*   **避免代码重复**：将公共接口的定义集中在一处。

## Python中的抽象类 ⚙️

![](img/5338a094655ffa6e35abef70b8b4f445_10.png)

Python本身并不直接支持抽象类，因此我们需要导入一个专门的模块来定义它。这个模块叫做 **ABC（Abstract Base Class，抽象基类）**。

![](img/5338a094655ffa6e35abef70b8b4f445_11.png)

此外，抽象类中的方法需要先被声明，然后才能在子类中实现。考虑到这些限制，你可能会疑惑为什么要使用抽象类。它的一个关键优势是：**能够在保持功能的前提下，隐藏具体的实现细节**。

## 抽象方法的实现方式 🛠️

![](img/5338a094655ffa6e35abef70b8b4f445_13.png)

在抽象类中，方法的实现主要有两种方式。

![](img/5338a094655ffa6e35abef70b8b4f445_15.png)

![](img/5338a094655ffa6e35abef70b8b4f445_16.png)

第一种是，作为基础的抽象类自身没有实现，其方法**必须由派生类来具体实现**。

另一种可能性是使用 `super()` 函数，但这属于更高级的话题，我们暂时不深入讨论。

现在，让我们聚焦于如何定义抽象类。

![](img/5338a094655ffa6e35abef70b8b4f445_18.png)

## 如何定义抽象类与抽象方法 📝

![](img/5338a094655ffa6e35abef70b8b4f445_19.png)

你可能现在对模块还不熟悉，这没关系，后续课程会详细讲解。目前，你只需要跟着步骤操作即可。

![](img/5338a094655ffa6e35abef70b8b4f445_21.png)

首先，需要导入 `ABC` 模块和 `abstractmethod` 装饰器。

![](img/5338a094655ffa6e35abef70b8b4f445_22.png)

```python
from abc import ABC, abstractmethod
```

![](img/5338a094655ffa6e35abef70b8b4f445_24.png)

接下来，创建一个类，并让它继承自 `ABC` 类，这样就定义了一个抽象类。

```python
class SomeAbstractClass(ABC):
    pass
```

然后，在抽象类内部，使用 `@abstractmethod` 装饰器来定义抽象方法。**装饰器**是一个以另一个函数为参数并返回一个新函数的函数，用 `@` 符号表示。你可以暂时将装饰器理解为给现有函数添加功能的辅助函数。

这里定义的抽象方法不能在这个抽象类的对象上直接调用。你只能在继承了这个抽象类的子类对象上调用这个方法。

```python
class SomeAbstractClass(ABC):
    @abstractmethod
    def some_abstract_method(self):
        pass
```

![](img/5338a094655ffa6e35abef70b8b4f445_26.png)

一个抽象类可以包含一个或多个抽象方法。然而，**任何以抽象类为父类的子类，除非它重写（实现）了父类中的所有抽象方法，否则它自身也无法被实例化**。

![](img/5338a094655ffa6e35abef70b8b4f445_28.png)

## 实战演练：员工捐款示例 💻

理解了理论之后，让我们通过一个实际场景来编写代码。假设一个雇主想为慈善事业向员工募集捐款。

![](img/5338a094655ffa6e35abef70b8b4f445_30.png)

以下是实现步骤：

首先，导入必要的模块。

![](img/5338a094655ffa6e35abef70b8b4f445_32.png)

```python
from abc import ABC, abstractmethod
```

![](img/5338a094655ffa6e35abef70b8b4f445_34.png)

然后，创建员工抽象类 `Employee`，并使用抽象方法装饰器定义一个名为 `donate` 的方法。注意，这里只声明方法，不提供具体实现。

![](img/5338a094655ffa6e35abef70b8b4f445_36.png)

```python
class Employee(ABC):
    @abstractmethod
    def donate(self):
        pass
```

![](img/5338a094655ffa6e35abef70b8b4f445_38.png)

接着，创建一个继承自 `Employee` 抽象类的具体类 `Donation`。这个类必须重写 `donate` 抽象方法。

![](img/5338a094655ffa6e35abef70b8b4f445_40.png)

```python
class Donation(Employee):
    def donate(self):
        a = input("How much would you like to donate: ")
        return int(a)
```

![](img/5338a094655ffa6e35abef70b8b4f445_42.png)

现在，我们可以创建员工实例并调用方法了。同时，创建一个列表来存储捐款金额。

```python
john = Donation()
peter = Donation()

![](img/5338a094655ffa6e35abef70b8b4f445_44.png)

![](img/5338a094655ffa6e35abef70b8b4f445_45.png)

amounts = []
amounts.append(john.donate())
amounts.append(peter.donate())
```

最后，打印出两位员工的捐款总额。

![](img/5338a094655ffa6e35abef70b8b4f445_47.png)

![](img/5338a094655ffa6e35abef70b8b4f445_48.png)

```python
print(f"Total donations: {sum(amounts)}")
```

![](img/5338a094655ffa6e35abef70b8b4f445_50.png)

## 总结 📚

本节课中我们一起学习了抽象类和方法的核心概念。我们了解到抽象类是一种不能被直接实例化的类，它通过定义抽象方法来强制其子类实现特定的功能，从而保证了代码的接口一致性和可维护性。我们还掌握了在Python中如何使用 `ABC` 模块和 `@abstractmethod` 装饰器来定义抽象类和方法，并通过一个员工捐款的实例演示了其具体应用。掌握抽象类将帮助你设计出结构更清晰、更健壮的面向对象程序。