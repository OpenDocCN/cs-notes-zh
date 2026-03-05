# Python属性访问与描述符详解：P6：Andy Fundinger - 在点上发生的8件事

![](img/d9b78ecadbf81eb9828e4c03279b0041_1.png)

![](img/d9b78ecadbf81eb9828e4c03279b0041_2.png)

## 概述

在本教程中，我们将深入探讨Python中一个强大但常被忽视的特性：属性访问机制与描述符协议。我们将学习当你在对象上使用点号（`.`）访问或设置属性时，Python解释器在幕后执行的八个关键步骤。理解这些机制对于编写高级、灵活且高效的Python代码至关重要。

---

## 属性访问的八个步骤 🔍

上一节我们概述了本教程的目标，本节中我们来看看属性访问过程中具体发生的八件事。这八件事共同构成了Python对象属性查找和操作的完整链条。

以下是属性访问时发生的八个步骤：

1.  **实例字典查找**：首先，Python会检查对象的 `__dict__` 中是否存在该属性。
2.  **类字典查找**：如果实例字典中没有，则查找其所属类的 `__dict__`。
3.  **基类字典查找**：如果类字典中也没有，则按照方法解析顺序（MRO）在其基类字典中查找。
4.  **调用 `__getattr__`**：如果以上都未找到，且类定义了 `__getattr__` 方法，则调用它。
5.  **调用 `__getattribute__`**：实际上，`__getattribute__` 方法管理着整个属性访问流程，它总是被最先调用。
6.  **调用描述符的 `__get__`**：如果在类字典中找到的是一个定义了 `__get__` 方法的对象（描述符），则调用它。
7.  **调用描述符的 `__set__`**：当为属性赋值时，如果类字典中的对象定义了 `__set__` 方法，则调用它。
8.  **引发 `AttributeError`**：如果所有查找路径都失败，`__getattribute__` 最终会引发 `AttributeError` 异常。

![](img/d9b78ecadbf81eb9828e4c03279b0041_4.png)

---

## 基础属性访问 📖

![](img/d9b78ecadbf81eb9828e4c03279b0041_6.png)

上一节我们列出了属性访问的八个步骤，本节中我们来看看最基础、最直接的几种属性查找方式。

### 来自实例字典

最简单的属性访问直接从对象的 `__dict__` 中获取值。

```python
class MyObject:
    pass

![](img/d9b78ecadbf81eb9828e4c03279b0041_8.png)

o = MyObject()
o.__dict__[‘x‘] = 3
print(o.x)  # 输出: 3
```

### 来自类字典

![](img/d9b78ecadbf81eb9828e4c03279b0041_10.png)

如果实例字典中没有该属性，Python会到其所属类的字典中查找。

```python
class MyObject:
    y = 2

o = MyObject()
print(o.y)  # 输出: 2
```

### 来自父类（基类）字典

![](img/d9b78ecadbf81eb9828e4c03279b0041_12.png)

如果当前类字典中也没有，查找会沿着继承链向上进行。

```python
class Base:
    t = 4

class MyObject(Base):
    pass

o = MyObject()
print(o.t)  # 输出: 4
```

---

## 特殊方法拦截 🛡️

上一节我们了解了基础的字典查找，本节中我们来看看如何通过特殊方法更精细地控制属性访问。

### `__getattr__` 方法

当在实例和类的字典中都找不到属性时，如果定义了 `__getattr__`，它会被调用。

```python
class Probe:
    def __getattr__(self, name):
        print(f‘__getattr__ called for {name}‘)
        return ‘RetVal‘

p = Probe()
print(p.r)  # 触发 __getattr__，输出: RetVal
p.r = 5     # 设置值后，__getattr__ 不再被调用
print(p.r)  # 直接输出: 5
```

### `__setattr__` 方法

当给实例属性赋值时，`__setattr__` 方法会被调用。

![](img/d9b78ecadbf81eb9828e4c03279b0041_14.png)

```python
class Probe:
    def __setattr__(self, name, value):
        print(f‘Setting {name} to {value}‘)
        # 注意：如果不调用父类方法，属性不会被真正设置
        super().__setattr__(name, value)

p = Probe()
p.t = 3  # 输出: Setting t to 3
```

### `__getattribute__` 方法

`__getattribute__` 是属性访问的总入口，**每次**属性访问都会触发它，优先级最高。

![](img/d9b78ecadbf81eb9828e4c03279b0041_16.png)

```python
class Probe:
    def __getattribute__(self, name):
        print(f‘__getattribute__ called for {name}‘)
        return ‘Anything‘

p = Probe()
print(p.any_var)  # 输出: Anything
p.any_var = 10
print(p.any_var)  # 仍然输出: Anything，因为 __getattribute__ 完全接管了访问
```

---

## 描述符协议 ⚙️

上一节我们介绍了通过特殊方法进行拦截，本节中我们来看看Python属性系统的核心机制：描述符协议。

描述符是实现了特定协议（`__get__`， `__set__`， `__delete__`）的类。它们允许你自定义属性在访问、设置和删除时的行为。

### 非数据描述符

![](img/d9b78ecadbf81eb9828e4c03279b0041_18.png)

只定义了 `__get__` 方法的描述符称为非数据描述符。

```python
class NonDataDesc:
    def __get__(self, obj, objtype=None):
        print(‘NonDataDesc.__get__ called‘)
        return ‘A value from get‘

class MyClass:
    z = NonDataDesc()  # 描述符作为类属性

o = MyClass()
print(o.z)  # 触发 __get__，输出: A value from get
o.z = None  # 在实例字典中设置值
print(o.z)  # 输出: None，实例字典优先级高于非数据描述符
```

![](img/d9b78ecadbf81eb9828e4c03279b0041_20.png)

### 数据描述符

定义了 `__get__` 和 `__set__`（或 `__delete__`）方法的描述符称为数据描述符。**数据描述符的优先级高于实例字典**。

```python
class DataDesc:
    def __get__(self, obj, objtype=None):
        print(‘DataDesc.__get__ called‘)
        return ‘Value from DataDesc get‘
    def __set__(self, obj, value):
        print(f‘DataDesc.__set__ called with {value}‘)

![](img/d9b78ecadbf81eb9828e4c03279b0041_22.png)

class MyClass:
    z = DataDesc()

o = MyClass()
o.z = 100  # 触发 __set__，输出: DataDesc.__set__ called with 100
print(o.z)  # 触发 __get__，输出: Value from DataDesc get
           # 尽管没有真正存储值，但 __get__ 仍被调用
print(o.__dict__)  # 输出: {}，实例字典为空
```

### 描述符的签名

以下是描述符方法的典型签名：

*   `__get__(self, obj, objtype=None) -> object`
    *   `obj`: 调用描述符的实例。如果从类访问，则为 `None`。
    *   `objtype`: 所有者类。
*   `__set__(self, obj, value) -> None`
    *   `obj`: 实例。
    *   `value`: 要设置的值。
*   `__delete__(self, obj) -> None`
    *   `obj`: 实例。
*   `__set_name__(self, owner, name)` (Python 3.6+)
    *   在类创建时调用，告知描述符它被赋予的名称。

---

![](img/d9b78ecadbf81eb9828e4c03279b0041_24.png)

## 描述符的实际应用 🛠️

![](img/d9b78ecadbf81eb9828e4c03279b0041_26.png)

上一节我们学习了描述符协议的理论，本节中我们来看看描述符在现实世界中的强大应用。

![](img/d9b78ecadbf81eb9828e4c03279b0041_28.png)

描述符是许多Python高级特性的基石。

### 方法绑定

**实例方法之所以能自动绑定 `self` 参数，正是利用了非数据描述符。**

```python
class Greeter:
    def greeting(self):
        print(‘Hi‘)

print(Greeter.greeting)  # 输出: <function Greeter.greeting at ...>
g = Greeter()
print(g.greeting)        # 输出: <bound method Greeter.greeting of <__main__.Greeter object at ...>>
g.greeting()             # 输出: Hi
```
函数对象本身就是一个非数据描述符，其 `__get__` 方法返回一个绑定了实例的 `method` 对象。

### 属性别名

以下是一个数据描述符的实用例子：为属性创建别名。

```python
class Alias:
    """一个属性别名描述符"""
    def __init__(self, name):
        self.name = name  # 实际存储数据的属性名

    def __get__(self, obj, objtype=None):
        if obj is None:
            return self
        return getattr(obj, self.name)

    def __set__(self, obj, value):
        setattr(obj, self.name, value)

class DataClass:
    data_x = Alias(‘legacy_x‘)
    data_y = Alias(‘legacy_y‘)
    data_z = Alias(‘legacy_z‘)

    def __init__(self, x, y, z):
        self.legacy_x = x
        self.legacy_y = y
        self.legacy_z = z

![](img/d9b78ecadbf81eb9828e4c03279b0041_30.png)

obj = DataClass(‘high‘, ‘pycon‘, 2019)
print(obj.data_x, obj.legacy_x)  # 输出: high high
obj.data_x = ‘higher‘
print(obj.legacy_x)              # 输出: higher
```

### 带默认实例的方法调用

![](img/d9b78ecadbf81eb9828e4c03279b0041_32.png)

这是一个非数据描述符的例子，它允许在类级别调用实例方法时，自动创建一个默认实例。

```python
from functools import partial

class DefaultMethod:
    """一个装饰器/描述符，允许在类级别调用实例方法"""
    def __init__(self, func):
        self.func = func

    def __get__(self, obj, objtype=None):
        if obj is None:
            # 如果在类级别调用，创建一个默认实例
            print(‘Creating default instance‘)
            obj = objtype()  # 调用无参 __init__
            return partial(self.func, obj)  # 绑定实例
        return partial(self.func, obj)      # 绑定实例

class NamePrinter:
    def __init__(self, name=‘Default‘):
        self.name = name

    @DefaultMethod
    def name_print(self):
        print(f‘Name: {self.name}‘)

    def print_name(self):
        print(f‘Name: {self.name}‘)

andy = NamePrinter(‘Andy‘)
andy.name_print()    # 输出: Name: Andy
andy.print_name()    # 输出: Name: Andy

NamePrinter.name_print()   # 输出: Creating default instance \n Name: Default
# NamePrinter.print_name() # 会引发 TypeError
```

---

## 总结与建议 📝

本节课中我们一起学习了Python属性访问的完整流程和强大的描述符协议。

我们了解到，一个简单的点号操作背后，Python解释器可能执行多达八个步骤的查找和调用。描述符协议（`__get__`， `__set__`， `__delete__`）是Python实现属性管理、方法绑定、`@property`、`@classmethod`、`@staticmethod`等特性的核心机制。

**何时使用描述符？**

![](img/d9b78ecadbf81eb9828e4c03279b0041_34.png)

描述符是一种高级的“元编程”工具，就像一把强大的铲子。

*   **不要过早使用**：如果你的问题可以用简单的属性或方法解决，就不要使用描述符。过早引入会增加代码的复杂性。
*   **在需要时使用**：当你需要跨多个属性实现一致的复杂行为（如类型验证、惰性求值、数据持久化到数据库、属性别名、监控等），并且收益大于维护成本时，描述符是绝佳的选择。

![](img/d9b78ecadbf81eb9828e4c03279b0041_36.png)

记住，强大的能力意味着更大的责任。理解这些底层机制能让你更好地驾驭Python，写出更优雅、高效的代码。