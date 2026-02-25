# Python编程：第17讲：Python III 🐍

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_0.png)

在本节课中，我们将继续学习Python编程，重点探讨Python中的序列数据类型、类型转换以及面向对象编程的初步概念。我们将看到Python如何以简洁高效的方式处理数据，并了解如何创建自定义的数据类型。

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_2.png)

## 序列数据类型 📊

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_4.png)

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_6.png)

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_8.png)

上一节我们介绍了Python的基本数据结构。本节中，我们来看看Python中几种重要的序列数据类型：字符串、列表和`range`对象。它们都支持类似的操作，如索引和切片。

### 字符串作为序列

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_10.png)

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_12.png)

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_14.png)

在Python中，字符串是一种序列类型，可以像列表一样进行索引和切片操作。

```python
course = "CS10"
print(course[0])  # 输出 'C'
print(course[3])  # 输出 '0'
```

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_16.png)

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_18.png)

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_20.png)

字符串支持切片操作，其语法为`[start:end]`，其中`start`是包含的，而`end`是排除的。

```python
print(course[2:4])  # 输出 '10'
```

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_22.png)

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_23.png)

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_25.png)

需要注意的是，字符串在Python中是不可变的（immutable）。这意味着一旦创建，就不能修改字符串中的单个字符。

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_27.png)

```python
# 以下操作会引发错误
# course[0] = 'D'  # TypeError: 'str' object does not support item assignment
```

字符串拥有许多内置方法，例如计算长度、转换大小写等。

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_29.png)

```python
print(len(course))  # 输出 4
print(course.upper())  # 输出 'CS10'
```

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_31.png)

### 序列的通用操作

字符串、列表和`range`对象作为序列，共享许多行为。例如，它们都支持`in`关键字来检查成员资格。

```python
print("CS" in course)  # 输出 True
print("data" in course)  # 输出 False
```

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_33.png)

它们也都可以在`for`循环中使用。

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_35.png)

```python
for letter in course:
    print(letter)
```

### Range对象

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_37.png)

`range`函数生成一个数字序列，常用于循环。其结束值是排除的。

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_39.png)

```python
numbers = range(0, 10)  # 包含 0 到 9
print(list(numbers))  # 输出 [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
print(5 in numbers)  # 输出 True
print(10 in numbers)  # 输出 False
```

## 类型转换与严格性 ⚙️

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_41.png)

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_43.png)

Python对数据类型有严格的规定，这与Snap等图形化语言不同。在Python中，不能直接将不同类型的值相加。

```python
number = 5
text = "6"
# 以下操作会引发类型错误
# result = number + text  # TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_45.png)

需要使用内置函数进行显式类型转换。

```python
# 将数字转换为字符串后拼接
result_str = str(number) + text  # 结果为字符串 "56"
# 将字符串转换为数字后相加
result_num = number + int(text)  # 结果为数字 11
```

Python提供了多种类型转换函数：
*   `int()`: 将值转换为整数。
*   `str()`: 将值转换为字符串。
*   `list()`: 将可迭代对象转换为列表。

## 其他数据结构 🧩

除了列表和字符串，Python还提供了其他有用的数据结构。

### 元组

元组（tuple）使用圆括号`()`创建，与列表类似，但它是不可变的。

```python
some_tuple = (1, 2, "hello")
# some_tuple[0] = 10  # 这行会报错，因为元组不可变
```

### 集合

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_47.png)

集合（set）是一个无序且不包含重复元素的集合。它对于去重或成员检查非常高效。

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_49.png)

```python
unique_numbers = set([1, 2, 2, 3, 5])
print(unique_numbers)  # 输出 {1, 2, 3, 5}
```

### 字典

字典（dictionary）是Python中极其有用的数据结构。它存储键值对，允许通过键快速访问值。

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_51.png)

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_53.png)

```python
phone_book = {"Alice": "555-1234", "Bob": "555-5678"}
print(phone_book["Alice"])  # 输出 '555-1234'
print(phone_book.keys())    # 输出 dict_keys(['Alice', 'Bob'])
print(phone_book.values())  # 输出 dict_values(['555-1234', '555-5678'])
```

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_55.png)

## 面向对象编程入门 🏗️

现在，让我们转向面向对象编程。其核心思想是创建自定义的数据类型（类），这些类型可以拥有自己的属性（数据）和方法（函数）。

### 创建简单的类

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_57.png)

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_59.png)

我们创建一个`Time`类来表示时间。

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_61.png)

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_63.png)

```python
class Time:
    pass  # 暂时为空

t1 = Time()
t1.hour = 17
t1.minute = 10
t1.second = 22
```

### 格式化字符串

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_65.png)

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_67.png)

为了更清晰地输出对象信息，Python提供了强大的字符串格式化方法，特别是f-string。

```python
# 使用 .format() 方法
print("Time is {}:{}:{}".format(t1.hour, t1.minute, t1.second))
# 使用更简洁的 f-string
print(f"Time is {t1.hour}:{t1.minute}:{t1.second}")
```

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_69.png)

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_71.png)

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_73.png)

## 总结 📝

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_75.png)

本节课中我们一起学习了：
1.  **序列数据类型**：字符串、列表和`range`对象都支持索引、切片和迭代。
2.  **类型严格性**：Python要求显式类型转换，使用`int()`, `str()`, `list()`等函数。
3.  **其他数据结构**：了解了不可变的元组、用于去重的集合以及强大的键值对字典。
4.  **面向对象编程基础**：初步了解了如何通过定义`class`来创建自定义数据类型，并为其添加属性。

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_77.png)

![](img/d4476a1b4a8b6dd5aff75cfaa8062541_79.png)

这些工具使我们能够更清晰、更高效地组织和处理数据，为编写更复杂的程序奠定了基础。下节课我们将深入探讨如何为类添加方法，使其功能更加强大。