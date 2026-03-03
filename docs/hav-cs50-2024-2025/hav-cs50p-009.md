# Python编程入门：P9：实例方法 🧩

![](img/2749873fe240ad6c6aff3cb9929078a9_0.png)

在本节课中，我们将要学习Python中的**实例方法**。我们将了解如何为类定义方法，这些方法可以封装与类实例相关的功能，例如自定义对象的打印格式或计算特定属性。

---

![](img/2749873fe240ad6c6aff3cb9929078a9_2.png)

## 概述

![](img/2749873fe240ad6c6aff3cb9929078a9_3.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_4.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_5.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_6.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_7.png)

在之前的课程中，我们学习了如何定义类和实例变量，以创建对象的模板并存储其属性。本节我们将探讨**实例方法**，它允许我们将功能（而不仅仅是数据）封装到类中。我们将学习如何定义和使用它们，包括一个名为 `__str__` 的特殊方法。

![](img/2749873fe240ad6c6aff3cb9929078a9_8.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_9.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_10.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_11.png)

---

## 回顾：类与实例变量

首先，让我们回顾一下如何定义一个简单的类并创建其实例。我们以一个表示“包裹”的类为例。

![](img/2749873fe240ad6c6aff3cb9929078a9_13.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_14.png)

```python
class Package:
    def __init__(self, number, sender, recipient, weight):
        self.number = number
        self.sender = sender
        self.recipient = recipient
        self.weight = weight

![](img/2749873fe240ad6c6aff3cb9929078a9_15.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_16.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_17.png)

# 创建实例
package1 = Package(1, "Alice", "Bob", 10)
package2 = Package(2, "Charlie", "David", 5)

# 访问实例变量并打印
packages = [package1, package2]
for package in packages:
    print(f"Package {package.number}: {package.sender} to {package.recipient}, {package.weight}kg")
```

![](img/2749873fe240ad6c6aff3cb9929078a9_19.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_20.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_21.png)

在上面的代码中，`Package` 类是一个模板，`package1` 和 `package2` 是它的两个实例。我们通过点符号（如 `package.number`）访问每个实例的变量。

---

![](img/2749873fe240ad6c6aff3cb9929078a9_23.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_24.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_25.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_26.png)

## 引入实例方法

类不仅可以组合信息，还可以封装所有实例共有的功能。这是通过定义**实例方法**来实现的。

实例方法是定义在类内部的函数，它可以被该类的任何实例调用。方法的第一个参数通常是 `self`，它代表调用该方法的实例本身。

![](img/2749873fe240ad6c6aff3cb9929078a9_28.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_29.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_30.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_31.png)

---

![](img/2749873fe240ad6c6aff3cb9929078a9_32.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_33.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_34.png)

## 特殊实例方法：`__str__`

一个非常有用的特殊实例方法是 `__str__`（读作“dunder str”）。当使用 `print()` 函数打印一个类的实例时，Python会自动调用这个方法。它应该返回一个字符串，表示该实例的“友好”描述。

目前，如果我们直接打印一个 `Package` 实例，输出并不直观：

![](img/2749873fe240ad6c6aff3cb9929078a9_36.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_37.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_38.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_39.png)

```python
print(package1)
# 输出类似：<__main__.Package object at 0x...>
```

![](img/2749873fe240ad6c6aff3cb9929078a9_40.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_41.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_42.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_43.png)

为了改善这一点，我们可以在 `Package` 类中定义 `__str__` 方法。

![](img/2749873fe240ad6c6aff3cb9929078a9_45.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_46.png)

以下是定义 `__str__` 方法的步骤：

![](img/2749873fe240ad6c6aff3cb9929078a9_48.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_49.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_51.png)

1.  在类内部定义一个名为 `__str__` 的方法。
2.  该方法必须接受 `self` 作为参数。
3.  返回一个格式化的字符串。

![](img/2749873fe240ad6c6aff3cb9929078a9_53.png)

让我们修改 `Package` 类：

![](img/2749873fe240ad6c6aff3cb9929078a9_55.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_57.png)

```python
class Package:
    def __init__(self, number, sender, recipient, weight):
        self.number = number
        self.sender = sender
        self.recipient = recipient
        self.weight = weight

    def __str__(self):
        return f"Package {self.number}: {self.sender} to {self.recipient}, {self.weight}kg"

# 创建实例
package1 = Package(1, "Alice", "Bob", 10)

# 现在打印实例会调用 __str__ 方法
print(package1)
# 输出：Package 1: Alice to Bob, 10kg
```

![](img/2749873fe240ad6c6aff3cb9929078a9_59.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_60.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_61.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_62.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_63.png)

通过定义 `__str__`，我们成功地将格式化输出的逻辑封装在了类内部，使代码更整洁、更易维护。

---

![](img/2749873fe240ad6c6aff3cb9929078a9_65.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_66.png)

## 定义自定义实例方法

除了 `__str__` 这样的特殊方法，我们还可以定义自己的实例方法来执行与类相关的操作。

例如，我们可以为 `Package` 类添加一个计算运费的方法。假设运费按重量（公斤）乘以每公斤单价计算。

以下是定义自定义实例方法 `calculate_cost` 的步骤：

![](img/2749873fe240ad6c6aff3cb9929078a9_68.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_69.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_70.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_71.png)

1.  在类内部定义一个方法（例如 `calculate_cost`）。
2.  第一个参数是 `self`。
3.  可以定义其他参数（例如 `cost_per_kg`）。
4.  在方法体内，使用 `self` 访问实例变量并执行计算。
5.  使用 `return` 语句返回结果。

![](img/2749873fe240ad6c6aff3cb9929078a9_72.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_73.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_74.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_75.png)

让我们在 `Package` 类中添加这个方法：

![](img/2749873fe240ad6c6aff3cb9929078a9_77.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_78.png)

```python
class Package:
    def __init__(self, number, sender, recipient, weight):
        self.number = number
        self.sender = sender
        self.recipient = recipient
        self.weight = weight

    def __str__(self):
        return f"Package {self.number}: {self.sender} to {self.recipient}, {self.weight}kg"

    def calculate_cost(self, cost_per_kg):
        """计算包裹的运费"""
        return self.weight * cost_per_kg

![](img/2749873fe240ad6c6aff3cb9929078a9_80.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_81.png)

# 使用实例方法
package1 = Package(1, "Alice", "Bob", 10)
shipping_cost = package1.calculate_cost(2)  # 每公斤2美元
print(f"{package1} costs ${shipping_cost} to ship.")
# 输出：Package 1: Alice to Bob, 10kg costs $20 to ship.
```

在这个例子中，`calculate_cost` 是一个实例方法。我们通过实例 `package1` 调用它（`package1.calculate_cost(2)`），方法内部通过 `self.weight` 访问该实例的重量属性。

![](img/2749873fe240ad6c6aff3cb9929078a9_83.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_84.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_85.png)

---

## 综合应用

现在，让我们将所学内容结合起来，创建一个完整的示例程序。

![](img/2749873fe240ad6c6aff3cb9929078a9_87.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_88.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_89.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_90.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_91.png)

```python
class Package:
    def __init__(self, number, sender, recipient, weight):
        self.number = number
        self.sender = sender
        self.recipient = recipient
        self.weight = weight

    def __str__(self):
        return f"Package {self.number}: {self.sender} to {self.recipient}, {self.weight}kg"

    def calculate_cost(self, cost_per_kg):
        """计算包裹的运费"""
        return self.weight * cost_per_kg

![](img/2749873fe240ad6c6aff3cb9929078a9_93.png)

# 创建包裹列表
packages = [
    Package(1, "Alice", "Bob", 10),
    Package(2, "Charlie", "David", 5)
]

# 遍历列表，打印每个包裹信息并计算运费
cost_per_kg = 2  # 每公斤运费
for package in packages:
    cost = package.calculate_cost(cost_per_kg)
    print(f"{package} costs ${cost} to ship.")
```

运行此代码将输出：
```
Package 1: Alice to Bob, 10kg costs $20 to ship.
Package 2: Charlie to David, 5kg costs $10 to ship.
```

---

![](img/2749873fe240ad6c6aff3cb9929078a9_95.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_96.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_97.png)

## 总结

![](img/2749873fe240ad6c6aff3cb9929078a9_98.png)

![](img/2749873fe240ad6c6aff3cb9929078a9_99.png)

本节课中我们一起学习了Python中的**实例方法**。

![](img/2749873fe240ad6c6aff3cb9929078a9_101.png)

*   **实例方法**是定义在类内部的函数，用于封装与该类实例相关的行为或功能。
*   方法的第一个参数通常是 `self`，它指向调用该方法的实例本身。
*   特殊方法 `__str__` 允许我们自定义使用 `print()` 打印对象时的输出格式。
*   我们可以定义自己的实例方法（如 `calculate_cost`）来执行特定计算或操作，使代码更加模块化和可重用。

通过使用实例方法，我们能够创建更强大、更组织良好的面向对象程序。在接下来的课程中，我们将继续探索Python类的其他特性。