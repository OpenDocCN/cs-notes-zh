# 计算机科学和Python编程：17：Python类 🐍

![](img/6daf992be145b59b96625ecb91023232_0.png)

![](img/6daf992be145b59b96625ecb91023232_2.png)

![](img/6daf992be145b59b96625ecb91023232_3.png)

在本节课中，我们将要学习如何创建自己的对象类型。我们将通过定义Python类，将数据和操作数据的行为捆绑在一起，从而构建可重用的代码模块。

![](img/6daf992be145b59b96625ecb91023232_5.png)

![](img/6daf992be145b59b96625ecb91023232_7.png)

![](img/6daf992be145b59b96625ecb91023232_8.png)

![](img/6daf992be145b59b96625ecb91023232_10.png)

![](img/6daf992be145b59b96625ecb91023232_11.png)

---

![](img/6daf992be145b59b96625ecb91023232_13.png)

![](img/6daf992be145b59b96625ecb91023232_15.png)

![](img/6daf992be145b59b96625ecb91023232_16.png)

## 概述：什么是对象类型？ 🤔

我们一直在使用各种对象，例如整数 `1234`、浮点数 `3.14159`、字符串 `"hello"`、列表 `[1, 2, 3]` 和字典 `{'a': 1}`。每个对象都有一个**类型**，类型决定了我们可以对该对象执行哪些操作。

当我们决定创建一个新的对象类型时，需要考虑两件事：
1.  **数据抽象**：用什么数据来表示这个对象？
2.  **接口/行为**：这个对象可以执行哪些操作？

例如，一个“汽车”对象的数据抽象可能包括长度、宽度、高度和颜色。其行为可能包括“改变颜色”、“鸣笛”和“从A点行驶到B点”。

---

## 定义类：蓝图 📐

上一节我们介绍了对象类型的基本概念，本节中我们来看看如何用Python代码来定义它。

我们通过**类**来定义新的对象类型。类就像一个蓝图，它描述了这类对象应该包含哪些数据（属性）以及可以执行哪些操作（方法）。

我们将创建一个表示二维平面坐标点的类 `Coordinate`。

### 类的结构

定义一个类的基本语法如下：

![](img/6daf992be145b59b96625ecb91023232_18.png)

![](img/6daf992be145b59b96625ecb91023232_19.png)

```python
class ClassName(object):
    def __init__(self, param1, param2, ...):
        # 初始化对象属性的代码
        self.attribute1 = param1
        self.attribute2 = param2

    def method1(self, ...):
        # 定义对象行为的代码
```

![](img/6daf992be145b59b96625ecb91023232_21.png)

![](img/6daf992be145b59b96625ecb91023232_23.png)

*   `class` 是定义类的关键字。
*   `ClassName` 是你为新对象类型起的名字（例如 `Coordinate`）。
*   `(object)` 表示这个类继承自Python的基本对象类型，目前我们总是这样写。
*   `__init__` 是一个特殊方法，称为**构造函数**。当我们创建这个类的一个新实例（即一个具体的对象）时，会自动调用它来初始化对象。
*   `self` 是一个特殊的参数，它代表**将来要创建的这个对象本身**。在类定义内部，我们通过 `self` 来访问和设置对象的属性和方法。

### 定义Coordinate类

对于我们的 `Coordinate` 类：
*   **数据抽象**：一个坐标点需要两个数字来表示，即x坐标和y坐标。
*   **行为**：我们希望能够获取点的x、y值，并计算它到另一个点的距离。

以下是 `Coordinate` 类的定义代码：

```python
class Coordinate(object):
    """表示二维平面上的一个点"""

    def __init__(self, x, y):
        """初始化一个坐标点。
        参数:
            x (float): x坐标值
            y (float): y坐标值
        """
        self.x = x  # 将传入的x值赋给这个对象的x属性
        self.y = y  # 将传入的y值赋给这个对象的y属性

    def distance(self, other):
        """计算当前点到另一个点的欧几里得距离。
        参数:
            other (Coordinate): 另一个坐标点对象
        返回:
            float: 两点之间的距离
        """
        x_diff_sq = (self.x - other.x) ** 2  # (x1 - x2)的平方
        y_diff_sq = (self.y - other.y) ** 2  # (y1 - y2)的平方
        return (x_diff_sq + y_diff_sq) ** 0.5  # 平方根

    def get_x(self):
        """返回当前点的x坐标"""
        return self.x

    def get_y(self):
        """返回当前点的y坐标"""
        return self.y
```

**关键点解释**：
*   在 `__init__` 方法中，`self.x = x` 创建了对象的一个**数据属性**。`self.x` 会随着对象一直存在。
*   在 `distance` 方法中，`self` 代表调用这个方法的那个坐标点对象，`other` 代表作为参数传入的另一个坐标点对象。我们通过 `self.x` 和 `other.x` 来访问各自的数据。

---

## 使用类：创建和操作实例 🛠️

上一节我们定义了 `Coordinate` 类的蓝图，本节中我们来看看如何根据这个蓝图创建具体的对象（称为**实例**）并与之交互。

### 创建实例

![](img/6daf992be145b59b96625ecb91023232_25.png)

![](img/6daf992be145b59b96625ecb91023232_26.png)

要创建一个 `Coordinate` 对象，我们像调用函数一样调用类名，并传入 `__init__` 方法中除 `self` 外所需的参数。

![](img/6daf992be145b59b96625ecb91023232_28.png)

![](img/6daf992be145b59b96625ecb91023232_29.png)

![](img/6daf992be145b59b96625ecb91023232_30.png)

![](img/6daf992be145b59b96625ecb91023232_31.png)

![](img/6daf992be145b59b96625ecb91023232_33.png)

![](img/6daf992be145b59b96625ecb91023232_35.png)

![](img/6daf992be145b59b96625ecb91023232_37.png)

![](img/6daf992be145b59b96625ecb91023232_39.png)

```python
# 创建两个Coordinate对象（实例）
c = Coordinate(3, 4)      # 创建一个坐标为(3, 4)的点，变量c指向它
origin = Coordinate(0, 0) # 创建一个坐标为(0, 0)的点，变量origin指向它
```

执行 `c = Coordinate(3, 4)` 时，Python会：
1.  在内存中创建一个新的 `Coordinate` 对象。
2.  自动调用 `__init__(self, 3, 4)` 方法，其中 `self` 就是这个新创建的对象。
3.  执行 `self.x = 3` 和 `self.y = 4`，为新对象设置属性。
4.  返回这个新对象，并将其赋值给变量 `c`。

### 访问数据属性

![](img/6daf992be145b59b96625ecb91023232_41.png)

![](img/6daf992be145b59b96625ecb91023232_42.png)

使用**点运算符** `.` 可以访问对象的数据属性。

![](img/6daf992be145b59b96625ecb91023232_44.png)

![](img/6daf992be145b59b96625ecb91023232_46.png)

![](img/6daf992be145b59b96625ecb91023232_48.png)

![](img/6daf992be145b59b96625ecb91023232_49.png)

![](img/6daf992be145b59b96625ecb91023232_51.png)

```python
print(c.x)      # 输出: 3
print(origin.x) # 输出: 0
print(c.y)      # 输出: 4
```

![](img/6daf992be145b59b96625ecb91023232_53.png)

### 调用方法

![](img/6daf992be145b59b96625ecb91023232_55.png)

![](img/6daf992be145b59b96625ecb91023232_56.png)

同样使用点运算符 `.` 来调用对象的方法。调用方法时，**不需要**显式地为 `self` 参数传递值，`self` 会自动绑定到点运算符**之前**的那个对象上。

![](img/6daf992be145b59b96625ecb91023232_58.png)

![](img/6daf992be145b59b96625ecb91023232_59.png)

![](img/6daf992be145b59b96625ecb91023232_60.png)

![](img/6daf992be145b59b96625ecb91023232_62.png)

```python
# 计算点c到点origin的距离
dist = c.distance(origin)
print(dist)  # 输出: 5.0 (因为3-0=3, 4-0=4, 勾股定理 sqrt(3^2 + 4^2) = 5)
```

![](img/6daf992be145b59b96625ecb91023232_64.png)

![](img/6daf992be145b59b96625ecb91023232_65.png)

![](img/6daf992be145b59b96625ecb91023232_67.png)

![](img/6daf992be145b59b96625ecb91023232_68.png)

**方法调用解析**：
*   `c.distance(origin)` 意味着：“在对象 `c` 上调用 `distance` 方法，并将 `origin` 作为参数传递”。
*   在 `distance` 方法内部，`self` 的值就是 `c`，`other` 的值就是 `origin`。
*   因此，代码计算的是 `(c.x - origin.x)^2 + (c.y - origin.y)^2` 的平方根。

![](img/6daf992be145b59b96625ecb91023232_70.png)

![](img/6daf992be145b59b96625ecb91023232_72.png)

![](img/6daf992be145b59b96625ecb91023232_73.png)

![](img/6daf992be145b59b96625ecb91023232_75.png)

![](img/6daf992be145b59b96625ecb91023232_77.png)

![](img/6daf992be145b59b96625ecb91023232_78.png)

### 理解self的另一种方式

![](img/6daf992be145b59b96625ecb91023232_80.png)

![](img/6daf992be145b59b96625ecb91023232_81.png)

为了更清晰地理解 `self`，我们可以用另一种等价但更冗长的方式调用方法：

```python
# 常规方式（推荐）
dist = c.distance(origin)

# 等价方式（显式传递self）
dist = Coordinate.distance(c, origin)
```

在第二种方式中，我们直接通过类名 `Coordinate` 来访问 `distance` 方法，并**显式地**将 `c` 作为第一个参数（即 `self`）传入。这证明了在常规调用中，`self` 是如何被自动绑定的。

![](img/6daf992be145b59b96625ecb91023232_83.png)

![](img/6daf992be145b59b96625ecb91023232_84.png)

---

![](img/6daf992be145b59b96625ecb91023232_86.png)

![](img/6daf992be145b59b96625ecb91023232_88.png)

![](img/6daf992be145b59b96625ecb91023232_90.png)

![](img/6daf992be145b59b96625ecb91023232_91.png)

## 总结 🎯

本节课中我们一起学习了Python面向对象编程的基础——类的定义和使用。

我们掌握了以下核心概念：
*   **类**是创建新对象类型的蓝图，它封装了**数据属性**和**方法**。
*   `__init__(self, ...)` 方法是构造函数，用于初始化新创建对象的数据属性。使用 `self.attribute = value` 来定义属性。
*   **方法**是定义在类内部的函数，第一个参数总是 `self`，代表调用该方法的对象实例。
*   使用 `ClassName(...)` 来创建类的**实例**（具体对象）。
*   使用**点运算符** `.` 来访问对象的属性（`obj.attribute`）或调用其方法（`obj.method(...)`）。
*   在方法调用中，点运算符之前的对象会自动绑定到方法的 `self` 参数上。

![](img/6daf992be145b59b96625ecb91023232_93.png)

![](img/6daf992be145b59b96625ecb91023232_94.png)

通过创建 `Coordinate` 类，我们实践了如何设计一个简单对象的数据抽象（x和y坐标）和行为（计算距离）。这是构建更复杂程序模块的第一步。在接下来的课程中，我们将以此为基础，构建更丰富的类层次结构。