# Python魔法揭秘：P15：如何在方法中自动插入 `self`

![](img/004cf16b0f11e3c700137499ce789b4f_1.png)

![](img/004cf16b0f11e3c700137499ce789b4f_2.png)

## 概述

在本节课中，我们将要学习Python中一个看似“魔法”的特性：当通过实例调用方法时，Python如何自动将实例本身作为第一个参数（即 `self`）插入。我们将深入探讨其背后的机制——描述符协议，并理解这并非无法理解的魔法，而是我们可以掌握和运用的强大工具。

---

## P15：1：回到基础——理解 `self` 的“魔法”

上一节我们介绍了本课程的目标。本节中，我们来看看 `self` 这个基础概念，以确保我们处于同一起点。

Python具有层层叠叠的抽象和功能，使其成为一门高级语言。一些人抱怨语言中添加了太多“魔法”。然而，这种“魔法”旨在帮助开发者专注于业务逻辑，而非底层细节。使用“魔法”一词可能让人感觉无法理解其机制。但事实并非如此，许多“魔法”是我们可以理解和创造的。

为了揭示 `self` 的魔法，我们需要先回到基础。定义一个简单的类有助于我们观察。

```python
class Guitar:
    def __init__(self, name):
        self.name = name

    def play_note(self, note):
        print(f"{self.name} is playing the note {note}.")
```

![](img/004cf16b0f11e3c700137499ce789b4f_4.png)

现在，我们可以创建实例并调用方法：

```python
my_guitar = Guitar("Warwick Streamer")
my_guitar.play_note("C#")
```

输出将是：`Warwick Streamer is playing the note C#.`

这里有趣的是：`play_note` 方法定义时接受两个参数 `self` 和 `note`，但调用时我们只提供了一个参数 `"C#"`。显然，`"C#"` 被用作 `note` 参数，那么 `self` 的值从何而来？这就是自动插入 `self` 的“魔法”。Python负责将我们调用的具体实例（`my_guitar`）作为第一个参数插入。

要理解这个魔法，我们需要探究方法究竟是什么，以及它们如何运作。

---

![](img/004cf16b0f11e3c700137499ce789b4f_6.png)

## P15：2：方法与函数的关系

![](img/004cf16b0f11e3c700137499ce789b4f_8.png)

上一节我们看到了 `self` 被自动插入的现象。本节中，我们来探究方法与普通函数的关系。

当Python读取包含 `play_note` 方法的 `Guitar` 类定义时，会发生以下情况：
1.  Python创建一个类对象（`Guitar`）来表示这个类。
2.  读取 `def play_note...` 语句时，它只是在内存中创建一个**普通的函数对象**。
3.  关键的一步是：这个函数对象的名称 `play_note` 被赋值给 `Guitar` 类的一个**类属性**。

简而言之，在类中定义一个函数并不会创建一种特殊的“方法对象”，它只是创建了一个普通函数，并将其赋值给一个类属性。

当我们尝试访问这个属性时，魔法才开始发生。

---

![](img/004cf16b0f11e3c700137499ce789b4f_10.png)

## P15：3：属性访问与绑定方法

![](img/004cf16b0f11e3c700137499ce789b4f_12.png)

上一节我们了解到方法最初只是作为类属性的普通函数。本节中，我们来看看通过不同方式访问它时会发生什么。

我们可以通过两种方式访问 `play_note`：
1.  通过类本身：`Guitar.play_note`
2.  通过类的实例：`my_guitar.play_note`

以下是关键区别：

```python
# 通过类访问，返回函数对象本身
print(Guitar.play_note)  # 输出: <function Guitar.play_note at 0x...>

# 通过实例访问，返回一个“绑定方法”
print(my_guitar.play_note)  # 输出: <bound method Guitar.play_note of <__main__.Guitar object at 0x...>>
```

当通过实例访问属性时，Python在实例上查找 `play_note`。如果找不到，它会继续在类中查找。更重要的是，这个查找过程可以通过**描述符协议**进行挂钩。Python的函数对象实现了这个协议。

![](img/004cf16b0f11e3c700137499ce789b4f_14.png)

因此，当通过实例（`my_guitar`）访问函数属性（`play_note`）时，描述符协议启动，将实例（`my_guitar`）绑定到函数上，从而创建一个**绑定方法**。在这个绑定方法中，实例已经作为第一个参数（`self`）被插入。这就是为什么调用时我们不再需要手动传递 `self`。

现在，让我们通过引入描述符协议来揭示这个魔法背后的窍门。

---

## P15：4：描述符协议简介

上一节我们提到了绑定方法背后的描述符协议。本节中，我们来初步了解什么是描述符。

描述符是能够修改我们在Python中与属性交互方式的对象。具体来说，它可以自定义属性的**查找**、**赋值**和**删除**行为。

![](img/004cf16b0f11e3c700137499ce789b4f_16.png)

描述符通过实现**描述符协议**来做到这一点，该协议包含三个特殊方法：
*   `__get__(self, instance, owner)`: 自定义获取（查找）属性时的行为。
*   `__set__(self, instance, value)`: 自定义给属性赋值时的行为。
*   `__delete__(self, instance)`: 自定义删除属性时的行为。

描述符不需要实现所有三个方法。例如，Python的函数对象只实现了 `__get__` 方法，这就是它能创建绑定方法的原因。

为了理解 `__get__` 如何工作，我们将自己实现一个简单的描述符。

---

## P15：5：实现一个简单的描述符

上一节我们介绍了描述符协议。本节中，我们通过一个简单例子来实现 `__get__` 方法。

我们将创建一个 `FavoriteDescriptor` 描述符。将其作为类属性 `is_my_favorite` 分配给 `Guitar` 类后，当在吉他实例上访问该属性时，它会告诉我这个实例是否是我最喜欢的吉他（这里硬编码为“Warwick Streamer”）。

```python
class FavoriteDescriptor:
    def __get__(self, instance, owner):
        # 如果通过类访问（instance为None），返回描述符本身
        if instance is None:
            return self
        # 否则，检查实例的name属性
        return instance.name == "Warwick Streamer"

class Guitar:
    is_my_favorite = FavoriteDescriptor()  # 描述符作为类属性

    def __init__(self, name):
        self.name = name

# 测试描述符
warwick = Guitar("Warwick Streamer")
fender = Guitar("Fender Jazz Bass")

print(warwick.is_my_favorite)  # 输出: True
print(fender.is_my_favorite)   # 输出: False
print(Guitar.is_my_favorite)   # 输出: <__main__.FavoriteDescriptor object at 0x...>
```

这个例子展示了 `__get__` 方法的基本结构：它接收 `instance`（访问属性的实例）和 `owner`（拥有该属性的类）参数。通过检查 `instance` 是否为 `None`，我们可以区分是通过类访问还是通过实例访问。

![](img/004cf16b0f11e3c700137499ce789b4f_18.png)

现在，我们已经看到了描述符的一个实现，接下来可以看看Python中函数的 `__get__` 方法是如何实现的。

![](img/004cf16b0f11e3c700137499ce789b4f_20.png)

---

## P15：6：函数描述符的实现原理

上一节我们手动实现了一个描述符。本节中，我们来看看Python中函数对象的 `__get__` 方法是如何工作的（用Python伪代码表示其逻辑）。

```python
# 这是函数对象 __get__ 方法的简化逻辑
class Function:
    def __get__(self, instance, owner):
        if instance is None:
            # 通过类访问，返回函数本身
            return self
        else:
            # 通过实例访问，返回一个绑定方法
            return types.MethodType(self, instance)
```

其工作原理如下：
1.  如果 `instance` 是 `None`（意味着通过类访问，如 `Guitar.play_note`），则直接返回函数对象本身。
2.  如果 `instance` 不是 `None`（意味着通过实例访问，如 `my_guitar.play_note`），则使用 `types.MethodType` 将函数（`self`）和实例（`instance`）绑定在一起，创建一个新的**绑定方法对象**并返回。

![](img/004cf16b0f11e3c700137499ce789b4f_22.png)

这就是 `self` 魔法的核心：**函数是实现了 `__get__` 方法的描述符**。当你通过实例访问它们时，`__get__` 方法被调用，并返回一个已将实例绑定为第一个参数的绑定方法。

---

## P15：7：其他内置描述符示例

上一节我们揭示了函数描述符的秘密。本节中，我们来看看Python中其他利用描述符协议的内置工具，它们都通过包装函数来改变其行为。

以下是几个常见示例：

**1. `@classmethod` 装饰器**
它将函数包装起来，其 `__get__` 方法总是将函数绑定到**类**，而不是实例。
```python
class MyClass:
    @classmethod
    def my_class_method(cls):
        print(f"Called from {cls}")

obj = MyClass()
obj.my_class_method()  # 输出: Called from <class '__main__.MyClass'>
MyClass.my_class_method() # 输出相同
```

**2. `@staticmethod` 装饰器**
它将函数包装起来，其 `__get__` 方法总是返回原始函数本身，不进行任何绑定。
```python
class MyClass:
    @staticmethod
    def my_static_method():
        print("Static method called")

obj = MyClass()
obj.my_static_method()  # 输出: Static method called
MyClass.my_static_method() # 输出相同
```

**3. `@property` 装饰器**
它允许你轻松地为属性添加getter、setter和deleter方法。一个巨大优势是：你可以先直接暴露实例属性，后期再根据需要添加 `@property` 来实现更复杂的逻辑，而无需改变类的公共接口。
```python
class Guitar:
    def __init__(self, name):
        self._name = name  # “私有”属性

    @property
    def name(self):        # Getter
        return self._name.upper()  # 返回大写名称

    @name.setter
    def name(self, value): # Setter
        self._name = value.title() # 存储标题化格式
```

这些工具都非常强大，它们都基于描述符协议，让你能专注于高级逻辑。

---

## 总结

本节课中我们一起学习了Python中 `self` 自动插入背后的魔法。我们了解到：

1.  方法最初只是作为类属性的普通函数。
2.  当通过实例访问这些函数属性时，Python的**描述符协议**开始起作用。
3.  函数对象实现了 `__get__` 方法，该方法在通过实例访问时，会返回一个已将实例绑定为第一个参数（`self`）的**绑定方法**。
4.  描述符是一个强大的协议，允许自定义属性的访问、赋值和删除行为。`@property`、`@classmethod` 和 `@staticmethod` 等都是基于描述符构建的实用工具。

![](img/004cf16b0f11e3c700137499ce789b4f_24.png)

Python中的“魔法”并非不可触及。就像魔术师拥有咒语书一样，在Python中，我们拥有像描述符协议这样的“咒语书”，让我们能够理解、甚至创造自己的“魔法”。希望本课程能激发你进一步探索Python内部机制的兴趣。