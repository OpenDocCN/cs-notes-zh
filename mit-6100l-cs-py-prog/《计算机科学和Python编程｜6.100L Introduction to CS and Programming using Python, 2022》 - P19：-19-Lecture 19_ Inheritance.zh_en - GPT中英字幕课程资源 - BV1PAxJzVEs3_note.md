# 计算机科学和Python编程：19：继承

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_0.png)

在本节课中，我们将要学习面向对象编程的核心概念之一：继承。我们将从回顾如何创建自定义数据类型开始，然后深入探讨如何通过继承来建立类之间的层次关系，实现代码的重用和扩展。

## 回顾：创建自定义数据类型

上一节我们介绍了如何通过Python类来创建自定义数据类型。其核心思想是模仿现实世界，将具有共同属性和行为的对象归为一类。

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_2.png)

当我们定义一个类时，需要决定其**属性**。属性分为两类：
*   **数据属性**：构成对象的变量。
*   **过程属性**：通过方法实现，定义了如何操作对象。

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_4.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_6.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_7.png)

例如，我们定义一个简单的 `Animal` 类：

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_9.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_10.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_12.png)

```python
class Animal(object):
    def __init__(self, age):
        self.age = age
        self.name = None

    def __str__(self):
        return f"animal:{self.name}:{self.age}"

    def get_age(self):
        return self.age

    def get_name(self):
        return self.name

    def set_age(self, newage):
        self.age = newage

    def set_name(self, newname=""):
        self.name = newname
```

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_14.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_15.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_17.png)

*   `__init__` 方法用于初始化对象，创建数据属性 `self.age` 和 `self.name`。
*   `__str__` 方法定义了打印对象时的字符串表示。
*   `get_age` 和 `get_name` 是**获取器**，用于返回数据属性的值。
*   `set_age` 和 `set_name` 是**设置器**，用于修改数据属性的值。

创建和使用对象的方法如下：

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_19.png)

```python
# 创建一个年龄为4的动物对象
my_animal = Animal(4)
# 使用设置器修改名字
my_animal.set_name("Fluffy")
# 打印对象，会调用 __str__ 方法
print(my_animal)  # 输出：animal:Fluffy:4
# 使用获取器
print(my_animal.get_age())  # 输出：4
```

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_21.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_23.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_25.png)

### 为何要使用获取器和设置器

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_27.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_29.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_30.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_32.png)

直接访问数据属性（如 `my_animal.age`）虽然可行，但不是一个好的编程实践。使用获取器和设置器有以下好处：
1.  **隐藏内部实现**：类的使用者无需关心数据在内部如何存储（例如，变量名是 `age` 还是 `years`）。
2.  **增强健壮性**：可以在设置器中添加验证逻辑（例如，年龄不能为负数）。
3.  **便于维护**：如果内部实现改变，只需修改类内部的方法，而不影响使用该类的其他代码。

**重要原则**：应始终通过类提供的方法（获取器、设置器）来访问和修改对象的属性，而不是直接操作数据属性。

## 引入继承：建立类层次结构

在现实世界中，对象可以进一步分类。例如，“猫”、“兔子”、“人”都是“动物”，但它们各自有独特的属性和行为。在编程中，我们使用**继承**来模拟这种“是一个”的关系。

继承允许我们创建一个新类（**子类**或**派生类**），它自动获得另一个类（**父类**、**基类**或**超类**）的所有属性和方法，并可以添加或覆盖它们。

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_34.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_36.png)

### 创建子类：Cat

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_38.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_40.png)

让我们创建一个 `Cat` 类，它继承自 `Animal` 类。

```python
class Cat(Animal):  # Cat 继承自 Animal
    def speak(self):
        print("meow")

    def __str__(self):
        return f"cat:{self.name}:{self.age}"
```

*   在类定义 `class Cat(Animal)` 中，括号内的 `Animal` 指定了父类。
*   `Cat` 类自动获得了 `Animal` 的所有方法和数据属性。
*   它添加了一个新的方法 `speak`。
*   它**覆盖**了父类的 `__str__` 方法，提供了更具体的字符串表示。

以下是使用 `Cat` 类的示例：

```python
c = Cat(5)
c.set_name("Fluffy")
print(c)        # 输出：cat:Fluffy:5 (使用Cat自己的__str__)
c.speak()       # 输出：meow (Cat特有的方法)
print(c.get_age()) # 输出：5 (继承自Animal的方法)
```

### 方法解析顺序

当调用一个对象的方法时，Python遵循特定的顺序进行查找：
1.  首先在对象自身的类中查找。
2.  如果没找到，则去其父类中查找。
3.  依此类推，直到找到方法或到达最顶层的基类（如 `object`）。
4.  如果最终没找到，则引发 `AttributeError`。

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_42.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_44.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_46.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_47.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_49.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_51.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_53.png)

在 `Cat` 的例子中：
*   调用 `c.speak()` 时，在 `Cat` 类中直接找到。
*   调用 `c.get_age()` 时，在 `Cat` 类中未找到，于是到父类 `Animal` 中查找并找到。
*   调用 `print(c)` 时，在 `Cat` 类中找到 `__str__` 方法，因此使用它而不是 `Animal` 中的版本。

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_55.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_56.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_58.png)

## 扩展子类：Person

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_60.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_61.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_63.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_64.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_66.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_68.png)

现在，我们创建一个更复杂的子类 `Person`。假设创建 `Person` 对象时需要同时指定姓名和年龄，并且 `Person` 有自己特有的属性（如朋友列表）。

```python
class Person(Animal):
    def __init__(self, name, age):
        # 首先调用父类的 __init__ 方法来初始化 age 和 name (name先设为None)
        Animal.__init__(self, age)
        # 然后使用设置器设置具体的名字
        self.set_name(name)
        # 添加Person特有的数据属性
        self.friends = []

    def get_friends(self):
        return self.friends[:]  # 返回副本以保护原始数据

    def add_friend(self, fname):
        if fname not in self.friends:
            self.friends.append(fname)

    def speak(self):
        print("hello")

    def age_diff(self, other):
        diff = self.age - other.age
        print(f"{abs(diff)} year difference")

    def __str__(self):
        return f"person:{self.name}:{self.age}"
```

*   `Person` 定义了自己的 `__init__` 方法，因为它需要不同的初始化参数（`name` 和 `age`）。
*   在 `__init__` 中，首先使用 `Animal.__init__(self, age)` 调用父类的初始化方法，这设置了 `self.age` 并将 `self.name` 初始化为 `None`。
*   然后，它调用 `self.set_name(name)` 来设置具体的名字。
*   最后，它初始化了 `Person` 特有的属性 `self.friends`。
*   这种模式（先调用父类初始化，再添加子类特有内容）在继承中非常常见。

使用 `Person` 类：

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_70.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_71.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_73.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_74.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_75.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_77.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_79.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_81.png)

```python
p1 = Person("Jack", 30)
p2 = Person("Jill", 25)
print(p1)               # 输出：person:Jack:30
p1.speak()              # 输出：hello
p1.age_diff(p2)         # 输出：5 year difference
p1.add_friend("Bob")
print(p1.get_friends()) # 输出：['Bob']
```

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_83.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_84.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_85.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_87.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_89.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_90.png)

## 多层继承：Student

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_92.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_93.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_95.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_97.png)

继承可以有多层。例如，`Student` 是 `Person` 的一种，它继承了 `Person` 的所有特性，并可能增加新的属性（如专业）或覆盖行为（如说话方式）。

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_99.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_101.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_103.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_105.png)

```python
import random

class Student(Person):
    def __init__(self, name, age, major=None):
        # 调用父类Person的初始化方法
        Person.__init__(self, name, age)
        # 添加Student特有的属性
        self.major = major

    def change_major(self, newmajor):
        self.major = newmajor

    def speak(self):
        # 覆盖Person的speak方法，有随机性
        r = random.random()
        if r < 0.25:
            print("i have homework")
        elif 0.25 <= r < 0.5:
            print("i need sleep")
        elif 0.5 <= r < 0.75:
            print("i should eat")
        else:
            print("i am watching tv")

    def __str__(self):
        return f"student:{self.name}:{self.age}:{self.major}"
```

*   `Student.__init__` 调用 `Person.__init__`，后者又会调用 `Animal.__init__`。这体现了继承链。
*   `Student` 覆盖了 `speak` 方法，使其行为与 `Person` 不同。

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_107.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_108.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_110.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_112.png)

## 类变量：共享的属性

到目前为止，我们使用的都是**实例变量**（如 `self.age`），它们属于单个对象实例。Python 还支持**类变量**，它属于类本身，被该类的所有实例共享。

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_114.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_116.png)

类变量的一个典型用途是跟踪创建了多少个该类的实例。

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_118.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_119.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_121.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_123.png)

```python
class Rabbit(Animal):
    # 类变量，在所有Rabbit实例间共享
    tag = 1

    def __init__(self, age, parent1=None, parent2=None):
        Animal.__init__(self, age)
        self.parent1 = parent1
        self.parent2 = parent2
        # 使用当前的类变量tag作为该兔子的ID
        self.rid = Rabbit.tag
        # 创建完成后，递增类变量tag，为下一个实例准备
        Rabbit.tag += 1

    def get_rid(self):
        # 将ID格式化为固定长度，前面补零
        return str(self.rid).zfill(5)

    def get_parent1(self):
        return self.parent1

    def get_parent2(self):
        return self.parent2

    def __add__(self, other):
        # 重载 + 运算符：两只兔子“相加”产生一只新的小兔子
        # 新兔子的年龄为0，父母是参与运算的两只兔子
        return Rabbit(0, self, other)

    def __eq__(self, other):
        # 重载 == 运算符：如果两只兔子有相同的父母（顺序无关），则认为它们相等
        parents_same = self.parent1.rid == other.parent1.rid and self.parent2.rid == other.parent2.rid
        parents_opposite = self.parent1.rid == other.parent2.rid and self.parent2.rid == other.parent1.rid
        return parents_same or parents_opposite
```

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_125.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_127.png)

*   `tag = 1` 是一个类变量，它不属于任何实例，而是属于 `Rabbit` 类。
*   在 `__init__` 中，`self.rid = Rabbit.tag` 将当前的 `tag` 值赋给实例的 `rid`。
*   `Rabbit.tag += 1` 将类变量 `tag` 加1。由于 `tag` 是共享的，下一个创建的 `Rabbit` 实例会获得新的ID。
*   `__add__` 方法重载了 `+` 运算符，使得 `rabbit1 + rabbit2` 返回一个新的 `Rabbit` 对象。
*   `__eq__` 方法重载了 `==` 运算符，定义了两只兔子“相等”的逻辑。

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_129.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_131.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_133.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_135.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_137.png)

使用 `Rabbit` 类：

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_139.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_141.png)

```python
r1 = Rabbit(3)
r2 = Rabbit(4)
r3 = Rabbit(5)
print(f"r1 id: {r1.get_rid()}") # 输出：r1 id: 00001
print(f"r2 id: {r2.get_rid()}") # 输出：r2 id: 00002
print(f"r3 id: {r3.get_rid()}") # 输出：r3 id: 00003

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_143.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_144.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_145.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_147.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_149.png)

r4 = r1 + r2  # 调用 __add__，创建父母为r1和r2的新兔子
print(f"r4 id: {r4.get_rid()}") # 输出：r4 id: 00004
print(f"r4's parent ids: {r4.get_parent1().get_rid()}, {r4.get_parent2().get_rid()}")

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_151.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_153.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_155.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_157.png)

r5 = r2 + r1
print(r4 == r5)  # 输出：True，因为父母相同（r1和r2）
```

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_159.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_160.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_162.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_163.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_165.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_167.png)

## 总结

本节课中我们一起学习了面向对象编程中强大的工具——继承。我们回顾了如何定义类及其方法（`__init__`, `__str__`, 获取器，设置器）。然后，我们深入探讨了继承机制，它允许我们基于现有类创建新类，从而实现代码重用和逻辑分层。

我们学习了：
1.  如何创建子类并指定其父类。
2.  子类如何自动继承父类的属性和方法。
3.  子类如何添加新的方法。
4.  子类如何通过定义同名方法来**覆盖**父类的方法。
5.  在子类的 `__init__` 方法中如何正确调用父类的 `__init__` 方法。
6.  方法解析的顺序。
7.  引入了**类变量**的概念，它被类的所有实例共享，并演示了用它来为实例生成唯一ID。

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_169.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_170.png)

![](img/6839f46cc3482eb7c540e2abc3dd0e9d_171.png)

通过 `Animal`、`Cat`、`Person`、`Student` 和 `Rabbit` 的示例，我们看到了如何利用继承来构建清晰、可维护且易于扩展的代码结构。在接下来的课程中，我们将应用这些概念来构建更实用的项目。