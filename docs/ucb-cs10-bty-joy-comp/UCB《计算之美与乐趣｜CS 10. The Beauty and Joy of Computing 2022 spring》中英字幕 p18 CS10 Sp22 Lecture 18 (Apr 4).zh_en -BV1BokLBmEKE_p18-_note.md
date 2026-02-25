# 计算之美与乐趣：CS10 Sp22：第18讲 - 面向对象编程进阶 🐍

![](img/b9786997e60ac7567f16a6f18c4ed822_1.png)

![](img/b9786997e60ac7567f16a6f18c4ed822_3.png)

![](img/b9786997e60ac7567f16a6f18c4ed822_5.png)

![](img/b9786997e60ac7567f16a6f18c4ed822_7.png)

在本节课中，我们将继续学习Python面向对象编程，重点探讨如何为自定义类添加功能，包括实例方法、特殊方法（如构造函数和字符串表示方法），以及如何比较对象。我们将通过构建一个`Time`类来演示这些概念。

---

## 概述 📋

上一节我们介绍了如何创建一个简单的`Time`类并为其添加属性。本节中，我们将为这个类添加实用的功能，使其不仅仅是一个数据容器。我们将学习如何定义**实例方法**来执行计算，如何使用特殊的**构造函数**来简化对象创建，以及如何利用Python的**特殊方法**（如`__str__`和`__lt__`）来定制对象的行为，使其更直观、更易用。

---

![](img/b9786997e60ac7567f16a6f18c4ed822_9.png)

## 实例方法：为对象添加行为 🛠️

![](img/b9786997e60ac7567f16a6f18c4ed822_11.png)

![](img/b9786997e60ac7567f16a6f18c4ed822_13.png)

实例方法是属于类的函数，它们操作特定对象（实例）的数据。我们首先为`Time`类添加一个方法，用于计算从午夜到当前时间所经过的总秒数。

![](img/b9786997e60ac7567f16a6f18c4ed822_15.png)

**核心概念：实例方法**
实例方法的第一个参数通常是`self`，它代表调用该方法的对象实例本身。Python会自动将调用该方法的对象作为`self`参数传入。

以下是计算秒数的方法定义：
```python
class Time:
    def time_in_seconds(self):
        return self.hour * 3600 + self.minute * 60 + self.second
```
调用此方法有两种等效方式：
1. 通过类调用：`Time.time_in_seconds(t1)`
2. 通过实例调用（更常用、更自然）：`t1.time_in_seconds()`

![](img/b9786997e60ac7567f16a6f18c4ed822_17.png)

在第二种方式中，`t1`自动成为了`self`参数的值。

---

![](img/b9786997e60ac7567f16a6f18c4ed822_19.png)

## 构造函数：简化对象初始化 🏗️

之前，我们创建`Time`对象后，需要手动为其`hour`、`minute`、`second`属性赋值。这很繁琐。我们可以使用名为`__init__`的特殊方法（构造函数）来一次性完成初始化。

**核心概念：构造函数 `__init__`**
`__init__`方法在创建类的新实例时自动调用。我们可以在其中设置实例的初始状态。

以下是带有构造函数的`Time`类：
```python
class Time:
    def __init__(self, hour, minute, second):
        self.hour = hour
        self.minute = minute
        self.second = second
```
现在，创建对象变得非常简洁：
```python
t1 = Time(17, 10, 22) # 直接创建一个表示17:10:22的时间对象
```

![](img/b9786997e60ac7567f16a6f18c4ed822_21.png)

---

![](img/b9786997e60ac7567f16a6f18c4ed822_23.png)

![](img/b9786997e60ac7567f16a6f18c4ed822_25.png)

## 特殊方法：定制对象行为 ✨

Python提供了许多“特殊方法”（也称为“魔术方法”），它们以双下划线开头和结尾。这些方法允许我们定义对象在特定操作下的行为，例如打印对象或进行比较。

### `__str__` 方法：定义对象的字符串表示

当我们使用`print()`函数或`str()`函数时，Python会尝试调用对象的`__str__`方法来获取其字符串表示。

![](img/b9786997e60ac7567f16a6f18c4ed822_27.png)

![](img/b9786997e60ac7567f16a6f18c4ed822_29.png)

以下是`Time`类的`__str__`方法：
```python
class Time:
    # ... __init__ 和其他方法 ...
    def __str__(self):
        return f"{self.hour}:{self.minute}:{self.second}"
```
定义此方法后，`print(t1)`将输出`17:10:22`，而不是默认的 `<__main__.Time object at 0x...>` 这种不友好的内存地址信息。

![](img/b9786997e60ac7567f16a6f18c4ed822_31.png)

### `__lt__` 方法：定义“小于”比较

我们可能想比较两个`Time`对象哪个更早。通过定义`__lt__`（less than）方法，我们可以使用`<`运算符来比较。

![](img/b9786997e60ac7567f16a6f18c4ed822_33.png)

以下是`Time`类的`__lt__`方法的一种实现：
```python
class Time:
    # ... 其他方法 ...
    def __lt__(self, other):
        if self.hour < other.hour:
            return True
        elif self.hour == other.hour:
            if self.minute < other.minute:
                return True
            elif self.minute == other.minute:
                return self.second < other.second
        return False
```
定义此方法后，我们就可以直接写`t1 < t2`来判断`t1`是否早于`t2`。

![](img/b9786997e60ac7567f16a6f18c4ed822_35.png)

**更优雅的实现**
由于我们已经有了`time_in_seconds`方法，可以更简洁地实现比较：
```python
def __lt__(self, other):
    return self.time_in_seconds() < other.time_in_seconds()
```
这体现了代码复用的优势。

**带来的便利**
定义了`__lt__`方法后，我们的`Time`对象就可以直接使用Python内置的`sorted()`函数进行排序：
```python
time_list = [t1, t2, t3, t4]
sorted_times = sorted(time_list) # 这会根据我们定义的`__lt__`逻辑进行排序
```

![](img/b9786997e60ac7567f16a6f18c4ed822_37.png)

---

## 类属性与注意事项 ⚠️

![](img/b9786997e60ac7567f16a6f18c4ed822_39.png)

除了实例属性，Python还支持**类属性**。类属性属于类本身，被该类的所有实例共享。

```python
class Time:
    midnight = 0 # 这是一个类属性
    def __init__(self, hour, minute, second):
        # ... 实例属性初始化 ...
```
所有`Time`实例都可以访问`Time.midnight`或`t1.midnight`。

![](img/b9786997e60ac7567f16a6f18c4ed822_41.png)

**注意**：需要谨慎使用类属性。因为实例也可以修改同名的属性，这可能会意外地覆盖类属性或导致混淆。在初学阶段，建议尽量将所有数据定义为实例属性，除非有明确的共享需求。

---

## 总结 🎯

本节课中我们一起学习了面向对象编程的几个核心进阶概念：
1.  **实例方法**：我们学会了如何定义操作对象数据的方法，并使用`self`参数来访问当前实例。
2.  **构造函数 (`__init__`)**：我们使用这个特殊方法来简化对象的创建和初始化过程。
3.  **特殊方法**：我们探索了`__str__`和`__lt__`方法，它们让我们能够定制对象的字符串表示和比较行为，使自定义类用起来更像Python内置类型一样自然。
4.  **类属性**：我们简要了解了类属性的概念及其潜在风险。

![](img/b9786997e60ac7567f16a6f18c4ed822_43.png)

![](img/b9786997e60ac7567f16a6f18c4ed822_45.png)

掌握这些知识后，你就能创建功能更强大、接口更友好的自定义类了。在接下来的课程中，我们将继续探索Python的其他有趣特性。