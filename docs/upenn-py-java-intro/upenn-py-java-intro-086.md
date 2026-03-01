Python和Java编程入门1-2：086_03_01：创建元组 🧱

在本节课中，我们将要学习Python中一个重要的数据结构——元组。我们将了解元组的定义、特性以及如何创建它。

![](img/5edee83e7a7d036af2490ed098b78b64_0.png)

---

### 什么是元组？

元组是一个**不可变**的值序列。一旦定义，你就无法更改其中的单个元素。

![](img/5edee83e7a7d036af2490ed098b78b64_2.png)

这与**可变**的列表不同。

与列表类似，元组中包含的值不必是同一类型。

![](img/5edee83e7a7d036af2490ed098b78b64_4.png)

---

### 如何创建元组？

![](img/5edee83e7a7d036af2490ed098b78b64_6.png)

创建元组非常简单，只需将逗号分隔的值用圆括号括起来即可。

以下是一个包含四个值的元组示例，其类型是 `tuple`。

```python
my_tuple = (1, 2, 'hello', 3.14)
print(type(my_tuple))  # 输出: <class 'tuple'>
```

![](img/5edee83e7a7d036af2490ed098b78b64_8.png)

实际上，即使不使用圆括号，仅用逗号分隔值，也能创建元组。其类型依然是 `tuple`。

```python
another_tuple = 1, 2, 'world'
print(type(another_tuple))  # 输出: <class 'tuple'>
```

![](img/5edee83e7a7d036af2490ed098b78b64_10.png)

---

### 使用内置函数创建元组

![](img/5edee83e7a7d036af2490ed098b78b64_12.png)

你还可以使用Python内置的 `tuple()` 函数，从字符串或列表等可迭代对象创建元组。

![](img/5edee83e7a7d036af2490ed098b78b64_14.png)

以下是将字符串转换为元组的示例，其中每个字符成为元组中的一个独立项。

```python
tuple_from_string = tuple('Python')
print(tuple_from_string)  # 输出: ('P', 'y', 't', 'h', 'o', 'n')
```

---

![](img/5edee83e7a7d036af2490ed098b78b64_16.png)

### 元组的不可变性

如果你尝试更新元组中的元素，将会得到一个错误。因此，以下操作是无效的。

```python
my_tuple[0] = 100  # 这会导致 TypeError
```

![](img/5edee83e7a7d036af2490ed098b78b64_18.png)

同样，以下操作也是无效的。

```python
my_tuple.append(5)  # 元组没有 append 方法，这会导致 AttributeError
```

![](img/5edee83e7a7d036af2490ed098b78b64_20.png)

---

![](img/5edee83e7a7d036af2490ed098b78b64_21.png)

### 元组的应用场景

我们将看到，当你希望从一个函数中一次性返回多个值时，元组会变得极其有用。

---

### 总结

![](img/5edee83e7a7d036af2490ed098b78b64_23.png)

本节课中我们一起学习了Python元组。我们了解到元组是一个不可变的序列，可以通过圆括号或逗号直接创建，也可以使用 `tuple()` 函数从其他对象转换而来。元组的不可变性保证了数据的安全性，使其在需要返回多个值的函数等场景中非常实用。