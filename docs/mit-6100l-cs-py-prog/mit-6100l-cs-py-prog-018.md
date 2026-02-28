# 018：更多Python类方法 🐍

![](img/bda7caa5b8c30732a62547bf1f180abb_0.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_2.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_4.png)

在本节课中，我们将要学习如何创建更复杂的自定义数据类型，并深入探讨类方法的实现。我们将从复习上一节课的坐标类开始，然后构建一个圆类和一个分数类，并学习如何使用特殊方法（Dunder方法）来使我们的类更加强大和易于使用。

![](img/bda7caa5b8c30732a62547bf1f180abb_6.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_7.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_8.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_9.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_11.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_12.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_14.png)

## 课程概述

![](img/bda7caa5b8c30732a62547bf1f180abb_16.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_18.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_19.png)

上一节我们介绍了如何创建自定义数据类型，本节中我们来看看如何为这些类型添加更多功能。我们将学习如何在一个类中使用另一个类的对象作为属性，以及如何实现特殊方法来支持Python的内置操作符（如`+`、`*`和`print`）。

![](img/bda7caa5b8c30732a62547bf1f180abb_21.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_23.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_25.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_26.png)

## 复习：类的两种视角

![](img/bda7caa5b8c30732a62547bf1f180abb_28.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_29.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_31.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_33.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_35.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_36.png)

在编写代码时，我们需要从两种不同的视角来考虑：类的实现者和类的使用者。

*   **实现类**：我们告诉Python这个新数据类型的存在，决定它的名称、构成对象的属性（数据）以及它的行为（方法）。
*   **使用类**：我们假设这个类定义已经存在，然后创建该类型的多个实例对象，并通过调用方法来操作这些对象。

![](img/bda7caa5b8c30732a62547bf1f180abb_38.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_39.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_41.png)

当我们实现类时，是在抽象地定义数据类型的通用属性和行为。而当我们使用类时，是在创建具有特定属性值的具体对象。

![](img/bda7caa5b8c30732a62547bf1f180abb_43.png)

## 构建坐标类 📍

让我们回顾上一节课创建的坐标类。

![](img/bda7caa5b8c30732a62547bf1f180abb_45.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_46.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_48.png)

```python
class Coordinate(object):
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def distance(self, other):
        x_diff_sq = (self.x - other.x) ** 2
        y_diff_sq = (self.y - other.y) ** 2
        return (x_diff_sq + y_diff_sq) ** 0.5

    def to_origin(self):
        self.x = 0
        self.y = 0
```

![](img/bda7caa5b8c30732a62547bf1f180abb_50.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_52.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_53.png)

*   `__init__` 方法是一个构造函数，它告诉Python如何创建这种类型的对象。`self`参数代表即将创建的对象实例本身。
*   `distance` 方法计算当前坐标点与另一个坐标点之间的距离，使用了勾股定理公式：`distance = sqrt((x1 - x2)^2 + (y1 - y2)^2)`。
*   `to_origin` 方法将当前坐标点的x和y值重置为0，从而将其移动到原点。

![](img/bda7caa5b8c30732a62547bf1f180abb_55.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_56.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_58.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_59.png)

以下是使用坐标类的示例：

![](img/bda7caa5b8c30732a62547bf1f180abb_61.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_63.png)

```python
c = Coordinate(3, 4)
origin = Coordinate(0, 0)

![](img/bda7caa5b8c30732a62547bf1f180abb_65.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_66.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_68.png)

print(f"c.x is {c.x}, origin.x is {origin.x}")
print(f"Distance is {c.distance(origin)}")

![](img/bda7caa5b8c30732a62547bf1f180abb_70.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_72.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_73.png)

c.to_origin()
print(f"After reset, c.x is {c.x}, c.y is {c.y}")
```

![](img/bda7caa5b8c30732a62547bf1f180abb_75.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_77.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_79.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_81.png)

## 构建圆类 ⭕

![](img/bda7caa5b8c30732a62547bf1f180abb_83.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_85.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_86.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_88.png)

现在，让我们利用坐标类来构建一个更复杂的圆类。我们将圆定义为由圆心（一个坐标对象）和半径（一个整数）组成。

```python
class Circle(object):
    def __init__(self, center, radius):
        # 类型检查：确保center是Coordinate类型，radius是整数
        if type(center) != Coordinate:
            raise ValueError("Center must be a Coordinate object")
        if type(radius) != int:
            raise ValueError("Radius must be an integer")

        self.center = center
        self.radius = radius

    def is_inside(self, point):
        # 计算圆心到给定点的距离，并与半径比较
        return self.center.distance(point) < self.radius
```

![](img/bda7caa5b8c30732a62547bf1f180abb_90.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_92.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_94.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_96.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_97.png)

在`__init__`方法中，我们添加了类型检查来确保传入的参数符合预期。`is_inside`方法则利用坐标类的`distance`方法来判断一个点是否在圆内。

![](img/bda7caa5b8c30732a62547bf1f180abb_99.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_101.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_102.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_104.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_105.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_106.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_108.png)

以下是使用圆类的示例：

![](img/bda7caa5b8c30732a62547bf1f180abb_110.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_112.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_114.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_116.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_118.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_120.png)

```python
my_circle = Circle(Coordinate(2, 2), 2)
p1 = Coordinate(1, 1)
p2 = Coordinate(10, 10)

![](img/bda7caa5b8c30732a62547bf1f180abb_122.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_123.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_125.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_127.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_129.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_131.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_133.png)

print(my_circle.is_inside(p1))  # 输出: True
print(my_circle.is_inside(p2))  # 输出: False
```

![](img/bda7caa5b8c30732a62547bf1f180abb_135.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_136.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_138.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_140.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_141.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_143.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_145.png)

## 构建分数类 🔢

接下来，我们将创建一个表示分数的类。一个分数由分子和分母两个整数组成。

![](img/bda7caa5b8c30732a62547bf1f180abb_147.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_148.png)

### 简单分数类

![](img/bda7caa5b8c30732a62547bf1f180abb_150.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_151.png)

首先，我们创建一个简单的分数类，并为其添加加法和乘法方法。

![](img/bda7caa5b8c30732a62547bf1f180abb_153.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_155.png)

```python
class SimpleFraction(object):
    def __init__(self, numerator, denominator):
        self.num = numerator
        self.den = denominator

    def times(self, other):
        # 分数乘法：分子乘分子，分母乘分母
        top = self.num * other.num
        bottom = self.den * other.den
        return top / bottom  # 返回浮点数

    def plus(self, other):
        # 分数加法：(a/b) + (c/d) = (a*d + c*b) / (b*d)
        top = self.num * other.den + other.num * self.den
        bottom = self.den * other.den
        return top / bottom  # 返回浮点数
```

这个初步的实现有一个问题：`times`和`plus`方法返回的是浮点数，而不是分数对象。此外，直接打印分数对象会得到不友好的内存地址信息。

![](img/bda7caa5b8c30732a62547bf1f180abb_157.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_158.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_160.png)

### 改进分数类：使用特殊方法

![](img/bda7caa5b8c30732a62547bf1f180abb_162.png)

为了使我们的分数类更加强大和“Pythonic”，我们需要实现一些特殊方法（Dunder方法）。这些方法允许我们的类支持Python的内置操作。

![](img/bda7caa5b8c30732a62547bf1f180abb_164.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_165.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_167.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_168.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_170.png)

以下是需要实现的一些核心方法：

![](img/bda7caa5b8c30732a62547bf1f180abb_172.png)

1.  **`__str__` 方法**：定义当使用`print()`函数打印对象时的字符串表示形式。
2.  **`__mul__` 方法**：定义当使用`*`运算符时的行为。
3.  **`__add__` 方法**：定义当使用`+`运算符时的行为。
4.  **`__float__` 方法**：定义当使用`float()`函数将对象转换为浮点数时的行为。

![](img/bda7caa5b8c30732a62547bf1f180abb_174.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_175.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_176.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_178.png)

让我们来实现它们：

![](img/bda7caa5b8c30732a62547bf1f180abb_180.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_182.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_183.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_185.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_187.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_189.png)

```python
class Fraction(object):
    def __init__(self, numerator, denominator):
        self.num = numerator
        self.den = denominator

    def __str__(self):
        # 美化打印输出，例如 "3/4"
        return str(self.num) + "/" + str(self.den)

    def __mul__(self, other):
        # 分数乘法，返回一个新的分数对象
        new_num = self.num * other.num
        new_den = self.den * other.den
        return Fraction(new_num, new_den)

    def __add__(self, other):
        # 分数加法，返回一个新的分数对象
        new_num = self.num * other.den + other.num * self.den
        new_den = self.den * other.den
        return Fraction(new_num, new_den)

    def __float__(self):
        # 转换为浮点数
        return self.num / self.den
```

![](img/bda7caa5b8c30732a62547bf1f180abb_191.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_193.png)

现在，我们可以更自然地使用分数对象：

![](img/bda7caa5b8c30732a62547bf1f180abb_195.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_197.png)

```python
a = Fraction(1, 4)
b = Fraction(3, 4)

print(a)        # 输出: 1/4
print(b)        # 输出: 3/4

![](img/bda7caa5b8c30732a62547bf1f180abb_199.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_200.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_202.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_203.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_205.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_207.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_209.png)

c = a * b       # 使用 * 运算符
print(c)        # 输出: 3/16
print(float(c)) # 输出: 0.1875

![](img/bda7caa5b8c30732a62547bf1f180abb_211.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_212.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_214.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_216.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_218.png)

d = a + b       # 使用 + 运算符
print(d)        # 输出: 16/16 (即 1/1)
```

![](img/bda7caa5b8c30732a62547bf1f180abb_220.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_221.png)

### 添加约分功能

![](img/bda7caa5b8c30732a62547bf1f180abb_223.png)

为了得到最简分数形式，我们可以为分数类添加一个约分方法。这需要一个辅助函数来计算最大公约数（GCD）。

![](img/bda7caa5b8c30732a62547bf1f180abb_225.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_227.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_228.png)

```python
def gcd(a, b):
    # 计算最大公约数的辅助函数
    while b:
        a, b = b, a % b
    return a

![](img/bda7caa5b8c30732a62547bf1f180abb_230.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_232.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_234.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_236.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_238.png)

class Fraction(object):
    # ... 之前的 __init__, __str__, __mul__, __add__, __float__ 方法 ...

    def reduce(self):
        if self.den == 0:
            return None
        common_divisor = gcd(self.num, self.den)
        new_num = self.num // common_divisor
        new_den = self.den // common_divisor
        return Fraction(new_num, new_den)
```

![](img/bda7caa5b8c30732a62547bf1f180abb_240.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_242.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_244.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_246.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_248.png)

使用约分方法：

![](img/bda7caa5b8c30732a62547bf1f180abb_250.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_252.png)

```python
f = Fraction(2, 12)
print(f)         # 输出: 2/12
print(f.reduce()) # 输出: 1/6
```

![](img/bda7caa5b8c30732a62547bf1f180abb_254.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_256.png)

## 课程总结 🎯

本节课中我们一起学习了如何创建更复杂的自定义数据类型。我们回顾了坐标类，然后构建了一个使用坐标对象作为属性的圆类。接着，我们深入探讨了分数类，并学习了如何通过实现特殊方法（如`__str__`、`__mul__`、`__add__`和`__float__`）来使我们的类支持Python的内置操作符，从而让代码更简洁、更易读。

![](img/bda7caa5b8c30732a62547bf1f180abb_258.png)

![](img/bda7caa5b8c30732a62547bf1f180abb_260.png)

通过将数据和相关的行为捆绑在一起，我们创建了模块化、有组织的代码。这种面向对象编程的方法体现了分解和抽象的核心思想，使得代码更易于维护、扩展和复用。在下一节课中，我们将开始学习继承，探索如何创建具有父子关系的类。