# Python编程入门：P10：实例变量 📦

![](img/7b25470d5570a713bd45dd40288765bd_0.png)

![](img/7b25470d5570a713bd45dd40288765bd_2.png)

![](img/7b25470d5570a713bd45dd40288765bd_3.png)

在本节课中，我们将要学习面向对象编程中的一个核心概念——**实例变量**。我们将通过一个“包裹”类的例子，了解如何为类的每个独立对象存储和访问其特有的数据。

![](img/7b25470d5570a713bd45dd40288765bd_4.png)

![](img/7b25470d5570a713bd45dd40288765bd_5.png)

## 概述

上一节我们介绍了如何定义类来创建对象的模板。本节中，我们来看看如何为这个模板创建的每一个具体对象，赋予其独特的属性，这些属性就是**实例变量**。

![](img/7b25470d5570a713bd45dd40288765bd_7.png)

![](img/7b25470d5570a713bd45dd40288765bd_8.png)

![](img/7b25470d5570a713bd45dd40288765bd_9.png)

![](img/7b25470d5570a713bd45dd40288765bd_10.png)

## 定义类与 `__init__` 方法

![](img/7b25470d5570a713bd45dd40288765bd_11.png)

![](img/7b25470d5570a713bd45dd40288765bd_12.png)

![](img/7b25470d5570a713bd45dd40288765bd_13.png)

首先，我们回顾如何定义一个名为 `Package` 的类，它代表一个包裹。类的定义中有一个特殊的方法 `__init__`，它在创建类的新实例时被自动调用。

![](img/7b25470d5570a713bd45dd40288765bd_15.png)

![](img/7b25470d5570a713bd45dd40288765bd_16.png)

![](img/7b25470d5570a713bd45dd40288765bd_17.png)

```python
class Package:
    def __init__(self, number, sender, recipient, weight):
        self.number = number
        self.sender = sender
        self.recipient = recipient
        self.weight = weight
```

在这个 `__init__` 方法中：
*   `self` 参数指向正在创建的这个新实例本身。
*   其他参数（`number`, `sender`, `recipient`, `weight`）是我们创建包裹时需要提供的信息。
*   方法内部，我们使用 `self.变量名 = 参数值` 的语法，将传入的值赋给这个新实例的属性。这些属性就是**实例变量**。

![](img/7b25470d5570a713bd45dd40288765bd_19.png)

![](img/7b25470d5570a713bd45dd40288765bd_20.png)

![](img/7b25470d5570a713bd45dd40288765bd_21.png)

![](img/7b25470d5570a713bd45dd40288765bd_22.png)

## 创建类的实例

定义好类之后，我们就可以创建它的具体实例了。以下是创建两个包裹实例的代码：

![](img/7b25470d5570a713bd45dd40288765bd_24.png)

![](img/7b25470d5570a713bd45dd40288765bd_25.png)

```python
package1 = Package(1, "Alice", "Bob", 10)
package2 = Package(2, "Bob", "Charlie", 20)
```

![](img/7b25470d5570a713bd45dd40288765bd_26.png)

![](img/7b25470d5570a713bd45dd40288765bd_27.png)

![](img/7b25470d5570a713bd45dd40288765bd_28.png)

![](img/7b25470d5570a713bd45dd40288765bd_29.png)

![](img/7b25470d5570a713bd45dd40288765bd_30.png)

当我们执行 `Package(1, "Alice", "Bob", 10)` 时：
1.  Python 会创建一个新的 `Package` 对象。
2.  自动调用 `__init__` 方法。
3.  将参数 `1`, `"Alice"`, `"Bob"`, `10` 分别传递给 `__init__` 方法。
4.  在 `__init__` 方法内部，这些值被赋值给 `self.number`, `self.sender` 等，从而成为 `package1` 这个**特定实例**的变量。

![](img/7b25470d5570a713bd45dd40288765bd_31.png)

![](img/7b25470d5570a713bd45dd40288765bd_32.png)

因此，`package1` 拥有自己的 `number=1`, `sender="Alice"` 等属性，而 `package2` 则拥有另一套完全独立的属性值。这就是“实例变量”的含义——它们属于类的单个实例。

![](img/7b25470d5570a713bd45dd40288765bd_34.png)

## 访问实例变量

![](img/7b25470d5570a713bd45dd40288765bd_35.png)

![](img/7b25470d5570a713bd45dd40288765bd_36.png)

![](img/7b25470d5570a713bd45dd40288765bd_37.png)

![](img/7b25470d5570a713bd45dd40288765bd_38.png)

![](img/7b25470d5570a713bd45dd40288765bd_39.png)

创建了实例并设置了实例变量后，我们如何获取这些值呢？访问方式非常简单直接。

![](img/7b25470d5570a713bd45dd40288765bd_41.png)

![](img/7b25470d5570a713bd45dd40288765bd_42.png)

我们可以将多个实例放入一个列表，然后通过循环来访问每个实例的变量：

![](img/7b25470d5570a713bd45dd40288765bd_44.png)

```python
packages = [package1, package2]

![](img/7b25470d5570a713bd45dd40288765bd_45.png)

![](img/7b25470d5570a713bd45dd40288765bd_46.png)

![](img/7b25470d5570a713bd45dd40288765bd_47.png)

for package in packages:
    print(package.number)
```

运行这段代码，将会输出：
```
1
2
```

![](img/7b25470d5570a713bd45dd40288765bd_49.png)

![](img/7b25470d5570a713bd45dd40288765bd_50.png)

访问实例变量的语法是：`实例名.变量名`。例如，`package.number` 就获取了当前 `package` 实例的 `number` 属性的值。

![](img/7b25470d5570a713bd45dd40288765bd_51.png)

![](img/7b25470d5570a713bd45dd40288765bd_52.png)

![](img/7b25470d5570a713bd45dd40288765bd_53.png)

![](img/7b25470d5570a713bd45dd40288765bd_54.png)

![](img/7b25470d5570a713bd45dd40288765bd_55.png)

![](img/7b25470d5570a713bd45dd40288765bd_56.png)

## 格式化输出实例信息

![](img/7b25470d5570a713bd45dd40288765bd_57.png)

仅仅打印一个数字可能不够直观。我们可以利用实例变量，格式化地输出包裹的完整信息。

以下是使用 f-string 进行更友好输出的示例：

![](img/7b25470d5570a713bd45dd40288765bd_59.png)

![](img/7b25470d5570a713bd45dd40288765bd_60.png)

![](img/7b25470d5570a713bd45dd40288765bd_61.png)

![](img/7b25470d5570a713bd45dd40288765bd_62.png)

![](img/7b25470d5570a713bd45dd40288765bd_63.png)

![](img/7b25470d5570a713bd45dd40288765bd_64.png)

```python
for package in packages:
    print(f"Package {package.number}: {package.sender} to {package.recipient}, {package.weight}kg")
```

![](img/7b25470d5570a713bd45dd40288765bd_65.png)

![](img/7b25470d5570a713bd45dd40288765bd_66.png)

运行这段代码，将会输出：
```
Package 1: Alice to Bob, 10kg
Package 2: Bob to Charlie, 20kg
```

![](img/7b25470d5570a713bd45dd40288765bd_68.png)

![](img/7b25470d5570a713bd45dd40288765bd_69.png)

![](img/7b25470d5570a713bd45dd40288765bd_70.png)

![](img/7b25470d5570a713bd45dd40288765bd_71.png)

通过这种方式，我们成功地将与每个包裹相关的数据（编号、发件人、收件人、重量）**封装**在了各自的对象内部，并通过实例变量清晰地访问和展示出来。

## 总结

![](img/7b25470d5570a713bd45dd40288765bd_73.png)

本节课中我们一起学习了**实例变量**。
*   实例变量是定义在类的方法（通常是 `__init__`）内部，并以 `self.变量名` 形式存在的变量。
*   它们属于类的**每一个具体实例**，不同实例的同一实例变量可以拥有不同的值。
*   我们通过 `实例名.变量名` 的语法来访问或修改某个实例的变量。
*   使用实例变量，我们可以将数据有效地封装在对象内部，这是面向对象编程组织和管理代码的基础。

![](img/7b25470d5570a713bd45dd40288765bd_74.png)

![](img/7b25470d5570a713bd45dd40288765bd_75.png)

![](img/7b25470d5570a713bd45dd40288765bd_76.png)

![](img/7b25470d5570a713bd45dd40288765bd_78.png)

通过将数据（实例变量）和行为（类方法，后续会学到）绑定在一起，类为我们提供了一种强大而清晰的方式来构建复杂的程序。