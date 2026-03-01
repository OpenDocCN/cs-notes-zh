# 078：列表复习 📝

在本节课中，我们将要学习Python中一个非常重要的数据结构——列表。我们将回顾列表的基本概念、创建方法以及常用的操作。

![](img/383a9f17fe1f3af77d71d4bb553dad17_0.png)

## 概述

列表是Python中最常用的序列类型之一。它是一种可变的数据结构，这意味着在列表被定义之后，其中的单个元素可以被修改。

## 列表的创建

要创建一个列表，需要在方括号 `[]` 内指定用逗号分隔的值。

![](img/383a9f17fe1f3af77d71d4bb553dad17_2.png)

![](img/383a9f17fe1f3af77d71d4bb553dad17_3.png)

```python
my_list = [1, 2, 3, 4]
```

![](img/383a9f17fe1f3af77d71d4bb553dad17_4.png)

列表中的值不必都是相同的数据类型。你可以在同一个列表中混合使用不同的数据类型。例如，下面的列表包含三个字符串和一个整数。

```python
mixed_list = [‘cat‘, ‘dog‘, 5, ‘bird‘]
```

![](img/383a9f17fe1f3af77d71d4bb553dad17_6.png)

## 列表索引

列表中的每个项目都被分配了一个索引值，索引从零开始。

```python
animals = [‘cat‘, ‘dog‘, ‘bird‘]
```

这里，在方括号内使用索引 `1`，我们可以得到列表中的第二个项目。

![](img/383a9f17fe1f3af77d71d4bb553dad17_8.png)

```python
print(animals[1])  # 输出: dog
```

![](img/383a9f17fe1f3af77d71d4bb553dad17_9.png)

如果我们尝试使用索引 `4` 来打印列表中的第五个项目呢？

![](img/383a9f17fe1f3af77d71d4bb553dad17_10.png)

```python
print(animals[4])
```

这个项目不存在，所以我们会得到一个索引错误，因为索引超出了范围。

![](img/383a9f17fe1f3af77d71d4bb553dad17_12.png)

## 查找项目索引

我们可以使用Python内置的 `list.index()` 方法来查找列表中特定值的索引。

![](img/383a9f17fe1f3af77d71d4bb553dad17_14.png)

```python
animals = [‘cat‘, ‘dog‘, ‘bird‘]
index_of_dog = animals.index(‘dog‘)
print(index_of_dog)  # 输出: 1
```

![](img/383a9f17fe1f3af77d71d4bb553dad17_16.png)

这里我们得到了列表中 `‘dog‘` 项目的索引，即 `1`。

## 列表的常用操作

上一节我们介绍了如何访问列表元素，本节中我们来看看如何修改列表。

![](img/383a9f17fe1f3af77d71d4bb553dad17_18.png)

![](img/383a9f17fe1f3af77d71d4bb553dad17_19.png)

以下是向列表中添加项目的方法。

你可以使用 `append()` 方法向列表添加项目。这个方法会将一个项目添加到列表的末尾。

```python
animals = [‘cat‘, ‘dog‘, ‘bird‘]
animals.append(‘fish‘)
print(animals)  # 输出: [‘cat‘, ‘dog‘, ‘bird‘, ‘fish‘]
```

![](img/383a9f17fe1f3af77d71d4bb553dad17_21.png)

---

以下是获取列表长度的方法。

![](img/383a9f17fe1f3af77d71d4bb553dad17_23.png)

使用Python内置的 `len()` 函数获取列表的长度。

![](img/383a9f17fe1f3af77d71d4bb553dad17_24.png)

```python
animals = [‘cat‘, ‘dog‘, ‘bird‘]
length = len(animals)
print(length)  # 输出: 3
```

这会返回列表中项目的数量。

![](img/383a9f17fe1f3af77d71d4bb553dad17_26.png)

---

以下是移除列表中项目的方法。

![](img/383a9f17fe1f3af77d71d4bb553dad17_28.png)

使用 `pop()` 方法从列表中移除项目。

![](img/383a9f17fe1f3af77d71d4bb553dad17_30.png)

```python
animals = [‘cat‘, ‘dog‘, ‘bird‘]
animals.pop()  # 移除最后一个项目
print(animals)  # 输出: [‘cat‘, ‘dog‘]
```

这会移除列表中的最后一个项目。通过在 `pop()` 方法中指定索引 `1`，可以移除列表中的第二个项目。

![](img/383a9f17fe1f3af77d71d4bb553dad17_32.png)

```python
animals = [‘cat‘, ‘dog‘, ‘bird‘]
animals.pop(1)  # 移除索引为1的项目
print(animals)  # 输出: [‘cat‘, ‘bird‘]
```

---

![](img/383a9f17fe1f3af77d71d4bb553dad17_34.png)

以下是在列表中特定位置插入项目的方法。

![](img/383a9f17fe1f3af77d71d4bb553dad17_35.png)

通过指定索引 `2` 和要插入的字符串，可以在列表的第三个位置插入一个项目。

```python
animals = [‘cat‘, ‘dog‘, ‘bird‘]
animals.insert(2, ‘fish‘)
print(animals)  # 输出: [‘cat‘, ‘dog‘, ‘fish‘, ‘bird‘]
```

---

![](img/383a9f17fe1f3af77d71d4bb553dad17_37.png)

以下是检查特定项目是否在列表中的方法。

![](img/383a9f17fe1f3af77d71d4bb553dad17_38.png)

```python
animals = [‘cat‘, ‘dog‘, ‘bird‘]
print(‘dog‘ in animals)  # 输出: True
print(‘elephant‘ in animals)  # 输出: False
```

## 总结

![](img/383a9f17fe1f3af77d71d4bb553dad17_40.png)

本节课中我们一起学习了Python列表的基础知识。我们回顾了如何创建列表、理解列表索引、以及执行添加、获取长度、移除、插入和检查成员等常见操作。列表是Python编程中不可或缺的工具，掌握这些基本操作是进行更复杂数据处理的第一步。