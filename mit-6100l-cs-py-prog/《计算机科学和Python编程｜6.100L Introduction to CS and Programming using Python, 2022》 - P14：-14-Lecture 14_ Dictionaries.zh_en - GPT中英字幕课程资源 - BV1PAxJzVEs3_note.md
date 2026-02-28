# 计算机科学和Python编程：14：字典 📚

![](img/eafcba2c2d0205decd9962752d38c30a_0.png)

在本节课中，我们将要学习一种新的复合数据类型——Python字典。我们将了解为什么需要字典，学习其基本语法和操作，并通过实例理解如何有效地使用字典来组织和处理数据。

---

![](img/eafcba2c2d0205decd9962752d38c30a_2.png)

## 为什么需要字典？ 🤔

![](img/eafcba2c2d0205decd9962752d38c30a_4.png)

在之前的课程中，我们学习了列表和元组。假设我们需要存储学生的信息，例如姓名和成绩。使用列表，一种方法可能是创建两个平行的列表：一个存储姓名，另一个存储成绩，并约定相同索引位置的信息属于同一个学生。

![](img/eafcba2c2d0205decd9962752d38c30a_6.png)

```python
names = ['Anna', 'John', 'Eric']
grades = ['B', 'B', 'A']
```

![](img/eafcba2c2d0205decd9962752d38c30a_8.png)

![](img/eafcba2c2d0205decd9962752d38c30a_9.png)

![](img/eafcba2c2d0205decd9962752d38c30a_10.png)

![](img/eafcba2c2d0205decd9962752d38c30a_12.png)

![](img/eafcba2c2d0205decd9962752d38c30a_13.png)

要查找特定学生的成绩，我们需要编写一个函数，首先在`names`列表中查找该学生的索引，然后使用该索引从`grades`列表中获取成绩。这种方法在数据量很大或需要维护多个平行列表（如作业成绩、小测验成绩）时会变得非常繁琐且容易出错。

![](img/eafcba2c2d0205decd9962752d38c30a_15.png)

![](img/eafcba2c2d0205decd9962752d38c30a_16.png)

另一种方法是使用一个“主列表”，其中每个元素本身又是一个列表，包含一个学生的所有信息。但这会导致数据结构非常复杂，代码难以阅读和维护。

![](img/eafcba2c2d0205decd9962752d38c30a_18.png)

![](img/eafcba2c2d0205decd9962752d38c30a_20.png)

![](img/eafcba2c2d0205decd9962752d38c30a_22.png)

上一节我们介绍了使用列表存储关联数据的局限性，本节中我们来看看字典如何提供一种更优雅的解决方案。

![](img/eafcba2c2d0205decd9962752d38c30a_24.png)

![](img/eafcba2c2d0205decd9962752d38c30a_26.png)

![](img/eafcba2c2d0205decd9962752d38c30a_28.png)

![](img/eafcba2c2d0205decd9962752d38c30a_29.png)

---

## 什么是字典？ 🔑

![](img/eafcba2c2d0205decd9962752d38c30a_31.png)

Python字典是一种映射类型的数据结构。它存储的是**键值对**。你可以将“键”想象成自定义的索引，将“值”想象成与该索引关联的数据。这就像一本真正的字典，将单词（键）映射到其定义（值）。

![](img/eafcba2c2d0205decd9962752d38c30a_33.png)

![](img/eafcba2c2d0205decd9962752d38c30a_35.png)

![](img/eafcba2c2d0205decd9962752d38c30a_36.png)

![](img/eafcba2c2d0205decd9962752d38c30a_37.png)

![](img/eafcba2c2d0205decd9962752d38c30a_39.png)

与列表不同，列表的“索引”必须是连续的整数（0, 1, 2...），而字典的“键”可以是任何**不可变**的对象（如整数、浮点数、字符串、元组）。

![](img/eafcba2c2d0205decd9962752d38c30a_41.png)

![](img/eafcba2c2d0205decd9962752d38c30a_43.png)

![](img/eafcba2c2d0205decd9962752d38c30a_45.png)

### 创建字典

字典使用花括号 `{}` 创建。

![](img/eafcba2c2d0205decd9962752d38c30a_47.png)

![](img/eafcba2c2d0205decd9962752d38c30a_48.png)

*   创建一个空字典：`my_dict = {}`
*   创建包含键值对的字典：`my_dict = {key1: value1, key2: value2}`

键和值之间用冒号 `:` 分隔，每个键值对之间用逗号 `,` 分隔。

![](img/eafcba2c2d0205decd9962752d38c30a_50.png)

![](img/eafcba2c2d0205decd9962752d38c30a_51.png)

```python
# 创建一个将学生姓名映射到成绩的字典
grades = {'Anna': 'B', 'Matt': 'A', 'John': 'B', 'Katie': 'A'}
print(grades)  # 输出：{'Anna': 'B', 'Matt': 'A', 'John': 'B', 'Katie': 'A'}
```

![](img/eafcba2c2d0205decd9962752d38c30a_53.png)

![](img/eafcba2c2d0205decd9962752d38c30a_54.png)

---

## 字典的基本操作 🛠️

![](img/eafcba2c2d0205decd9962752d38c30a_56.png)

![](img/eafcba2c2d0205decd9962752d38c30a_58.png)

![](img/eafcba2c2d0205decd9962752d38c30a_60.png)

![](img/eafcba2c2d0205decd9962752d38c30a_62.png)

### 查找值

![](img/eafcba2c2d0205decd9962752d38c30a_64.png)

![](img/eafcba2c2d0205decd9962752d38c30a_66.png)

要获取与某个键关联的值，使用与列表索引类似的语法：`字典名[键]`。

```python
grades = {'Anna': 'B', 'Matt': 'A', 'John': 'B'}
print(grades['John'])  # 输出：B
```

如果查找的键不存在，Python会引发`KeyError`异常。

### 添加或修改条目

直接为字典中一个新的键赋值，即可添加新条目。如果该键已存在，则会修改其对应的值。

![](img/eafcba2c2d0205decd9962752d38c30a_68.png)

![](img/eafcba2c2d0205decd9962752d38c30a_69.png)

```python
grades = {'Anna': 'B', 'Matt': 'A'}
grades['Grace'] = 'A'  # 添加新条目：Grace -> A
print(grades)  # 输出：{'Anna': 'B', 'Matt': 'A', 'Grace': 'A'}

![](img/eafcba2c2d0205decd9962752d38c30a_71.png)

![](img/eafcba2c2d0205decd9962752d38c30a_73.png)

grades['Grace'] = 'C'  # 修改已有条目：Grace -> C
print(grades)  # 输出：{'Anna': 'B', 'Matt': 'A', 'Grace': 'C'}
```

![](img/eafcba2c2d0205decd9962752d38c30a_75.png)

![](img/eafcba2c2d0205decd9962752d38c30a_76.png)

![](img/eafcba2c2d0205decd9962752d38c30a_78.png)

![](img/eafcba2c2d0205decd9962752d38c30a_80.png)

![](img/eafcba2c2d0205decd9962752d38c30a_82.png)

### 删除条目

![](img/eafcba2c2d0205decd9962752d38c30a_84.png)

使用`del`语句可以删除字典中的键值对。

```python
grades = {'Anna': 'B', 'Matt': 'A', 'John': 'B'}
del grades['Anna']
print(grades)  # 输出：{'Matt': 'A', 'John': 'B'}
```

### 检查键是否存在

使用`in`操作符可以检查一个键是否存在于字典中。**注意**：`in`只检查键，不检查值。

![](img/eafcba2c2d0205decd9962752d38c30a_86.png)

```python
grades = {'Anna': 'B', 'Matt': 'A', 'John': 'B'}
print('John' in grades)   # 输出：True
print('Daniel' in grades) # 输出：False
print('B' in grades)      # 输出：False (因为'B'是值，不是键)
```

![](img/eafcba2c2d0205decd9962752d38c30a_88.png)

---

## 遍历字典 🔄

![](img/eafcba2c2d0205decd9962752d38c30a_90.png)

![](img/eafcba2c2d0205decd9962752d38c30a_91.png)

字典不是有序序列，但我们可以方便地遍历其所有内容。

### 遍历所有键

![](img/eafcba2c2d0205decd9962752d38c30a_93.png)

使用`.keys()`方法获取一个包含所有键的可迭代对象。

![](img/eafcba2c2d0205decd9962752d38c30a_95.png)

![](img/eafcba2c2d0205decd9962752d38c30a_97.png)

![](img/eafcba2c2d0205decd9962752d38c30a_98.png)

```python
grades = {'Anna': 'B', 'Matt': 'A', 'John': 'B'}
for student in grades.keys():
    print(student)
# 输出：
# Anna
# Matt
# John
```

### 遍历所有值

使用`.values()`方法获取一个包含所有值的可迭代对象。

```python
for grade in grades.values():
    print(grade)
# 输出：
# B
# A
# B
```

### 遍历所有键值对（条目）

使用`.items()`方法获取一个可迭代对象，其中每个元素是一个`(键, 值)`元组。这是最常用的遍历方式。

```python
for student, grade in grades.items():
    print(f"{student} got a {grade}")
# 输出：
# Anna got a B
# Matt got a A
# John got a B
```

![](img/eafcba2c2d0205decd9962752d38c30a_100.png)

![](img/eafcba2c2d0205decd9962752d38c30a_102.png)

---

![](img/eafcba2c2d0205decd9962752d38c30a_104.png)

![](img/eafcba2c2d0205decd9962752d38c30a_106.png)

![](img/eafcba2c2d0205decd9962752d38c30a_108.png)

![](img/eafcba2c2d0205decd9962752d38c30a_110.png)

## 字典的特性与限制 ⚠️

![](img/eafcba2c2d0205decd9962752d38c30a_112.png)

![](img/eafcba2c2d0205decd9962752d38c30a_113.png)

![](img/eafcba2c2d0205decd9962752d38c30a_114.png)

![](img/eafcba2c2d0205decd9962752d38c30a_116.png)

### 可变性

字典是可变对象。使用赋值`=`会创建别名，使用`.copy()`方法可以创建副本。

```python
d1 = {'a': 1}
d2 = d1          # d2是d1的别名，指向同一个字典对象
d2['a'] = 99
print(d1)        # 输出：{'a': 99}

d3 = d1.copy()   # d3是d1的副本，是一个新对象
d3['a'] = 100
print(d1)        # 输出：{'a': 99} (d1未被修改)
```

### 键的限制

![](img/eafcba2c2d0205decd9962752d38c30a_118.png)

1.  **唯一性**：字典中的键必须是唯一的。如果为同一个键赋值两次，后一个值会覆盖前一个。
2.  **不可变性**：键必须是**不可变**（可哈希）的类型，如整数、浮点数、字符串、元组。**列表**和**字典**等可变类型不能作为键。

![](img/eafcba2c2d0205decd9962752d38c30a_120.png)

![](img/eafcba2c2d0205decd9962752d38c30a_121.png)

![](img/eafcba2c2d0205decd9962752d38c30a_123.png)

![](img/eafcba2c2d0205decd9962752d38c30a_124.png)

**为什么键必须不可变？**
Python使用哈希函数将键转换为一个数字（哈希值），这个数字决定了键值对在内存中的存储位置。如果键是可变对象（如列表），其内容改变后，哈希值也可能改变，导致无法再通过原来的键找到存储的值。

![](img/eafcba2c2d0205decd9962752d38c30a_126.png)

![](img/eafcba2c2d0205decd9962752d38c30a_128.png)

### 值的自由性

![](img/eafcba2c2d0205decd9962752d38c30a_130.png)

![](img/eafcba2c2d0205decd9962752d38c30a_132.png)

![](img/eafcba2c2d0205decd9962752d38c30a_134.png)

字典的值可以是任何类型的对象，包括列表、其他字典等，并且值可以重复。

![](img/eafcba2c2d0205decd9962752d38c30a_136.png)

![](img/eafcba2c2d0205decd9962752d38c30a_137.png)

---

## 综合示例：分析歌词词频 🎵

让我们通过一个完整的例子来应用字典。我们的目标是找出歌曲歌词中出现频率最高的单词。

我们将问题分解为三个步骤：
1.  创建频率字典：将歌词字符串转换为一个字典，记录每个单词出现的次数。
2.  找出最高频单词：在频率字典中，找到出现次数最多的单词（可能有多个）。
3.  找出所有高频单词：找出所有出现次数超过某个阈值的单词。

### 步骤1：创建频率字典

```python
def generate_freq_dict(song):
    """接收一个歌词字符串，返回一个单词频率字典。"""
    song = song.lower()           # 转换为小写，避免大小写差异
    words = song.split()          # 按空格分割成单词列表
    freq_dict = {}
    for word in words:
        if word in freq_dict:     # 如果单词已在字典中
            freq_dict[word] += 1  # 计数加1
        else:                     # 如果单词是第一次出现
            freq_dict[word] = 1   # 在字典中添加该单词，计数为1
    return freq_dict

![](img/eafcba2c2d0205decd9962752d38c30a_139.png)

![](img/eafcba2c2d0205decd9962752d38c30a_141.png)

# 示例
lyrics = "Ro Ro Ro your boat gently down the stream"
freq = generate_freq_dict(lyrics)
print(freq)  # 输出类似：{'ro': 3, 'your': 1, 'boat': 1, ...}
```

### 步骤2：找出最高频单词

![](img/eafcba2c2d0205decd9962752d38c30a_143.png)

![](img/eafcba2c2d0205decd9962752d38c30a_145.png)

```python
def most_common_words(freq_dict):
    """接收频率字典，返回一个元组 (最高频单词列表, 最高频率)。"""
    highest_freq = max(freq_dict.values())  # 找到最高的频率值
    words = []
    for word, count in freq_dict.items():   # 遍历所有条目
        if count == highest_freq:           # 如果频率等于最高值
            words.append(word)              # 将该单词加入列表
    return (words, highest_freq)

# 接上例
common_words, freq_num = most_common_words(freq)
print(f"Most common word(s): {common_words}, appearing {freq_num} times.")
```

![](img/eafcba2c2d0205decd9962752d38c30a_147.png)

![](img/eafcba2c2d0205decd9962752d38c30a_148.png)

### 步骤3：找出所有高频单词（利用可变性和函数复用）

![](img/eafcba2c2d0205decd9962752d38c30a_149.png)

![](img/eafcba2c2d0205decd9962752d38c30a_151.png)

![](img/eafcba2c2d0205decd9962752d38c30a_153.png)

![](img/eafcba2c2d0205decd9962752d38c30a_155.png)

```python
def words_with_freq_at_least(freq_dict, min_freq):
    """
    接收频率字典和最小频率阈值。
    返回一个列表，其中每个元素是一个元组 (单词列表, 频率)，
    代表所有频率至少为 min_freq 的单词组，按频率从高到低排序。
    """
    result = []
    # 重复查找当前字典中的最高频单词，直到最高频率低于阈值
    while True:
        common_words, current_freq = most_common_words(freq_dict)
        if current_freq < min_freq:
            break  # 如果当前最高频率已低于阈值，停止循环
        result.append((common_words, current_freq))
        # 从字典中删除这些最高频单词，以便下一轮查找次高频的
        for word in common_words:
            del freq_dict[word]
    return result

![](img/eafcba2c2d0205decd9962752d38c30a_157.png)

# 接上例 (注意：此函数会修改输入的字典)
freq_copy = freq.copy()  # 使用副本，避免修改原数据
high_freq_words = words_with_freq_at_least(freq_copy, 2)
print(high_freq_words)
```

![](img/eafcba2c2d0205decd9962752d38c30a_159.png)

---

![](img/eafcba2c2d0205decd9962752d38c30a_161.png)

![](img/eafcba2c2d0205decd9962752d38c30a_163.png)

## 总结 📝

本节课中我们一起学习了Python字典。

![](img/eafcba2c2d0205decd9962752d38c30a_165.png)

![](img/eafcba2c2d0205decd9962752d38c30a_166.png)

![](img/eafcba2c2d0205decd9962752d38c30a_168.png)

*   **字典**是一种强大的映射类型数据结构，用于存储**键值对**。
*   与列表相比，字典的“键”可以是自定义的、不可变的对象，使得数据关联更加直观和高效。
*   我们掌握了字典的基本操作：创建、查找、添加/修改、删除条目，以及检查键是否存在。
*   我们学习了如何遍历字典的键、值和键值对。
*   我们了解了字典的关键特性：它是可变的，键必须唯一且不可变，而值可以是任意类型。
*   最后，通过分析歌词词频的综合示例，我们看到了字典在实际问题中的应用，以及如何将复杂任务分解并利用字典的特性（如`.items()`遍历、可变性）来简化代码。

![](img/eafcba2c2d0205decd9962752d38c30a_170.png)

字典是Python中极其重要的数据结构，它将帮助你更优雅地处理许多需要建立关联关系的数据问题。