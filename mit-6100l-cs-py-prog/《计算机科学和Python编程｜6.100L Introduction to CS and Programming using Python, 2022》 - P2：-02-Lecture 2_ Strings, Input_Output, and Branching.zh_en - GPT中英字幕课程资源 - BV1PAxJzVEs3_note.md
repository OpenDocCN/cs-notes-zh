# 计算机科学和Python编程：02：字符串、输入输出与分支

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_0.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_2.png)

## 概述

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_3.png)

在本节课中，我们将要学习三个核心主题：一种新的对象类型——字符串；如何编写与用户交互的程序，即获取输入和显示输出；以及如何编写能够根据代码中的决策做出判断的程序。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_5.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_7.png)

## 快速回顾

上一节我们介绍了对象的概念。在开始新内容之前，我们先快速回顾一下。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_9.png)

在Python中，每个对象都有特定的类型。类型决定了可以对该对象执行哪些操作。我们可以将对象赋值给变量，变量本质上是将名称绑定到内存中的对象。通过组合对象，我们可以创建表达式。表达式可以是数学运算，也可以是类似命令的操作。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_11.png)

例如，以下代码展示了变量的创建和赋值过程：

```python
pi = 3.14
radius = 2.2
area = pi * radius ** 2
```

在内存中，`pi` 绑定到浮点数 `3.14`，`radius` 绑定到浮点数 `2.2`。当计算 `area` 时，Python会获取这些值，执行运算，并将结果 `15.1976` 作为一个新对象绑定到变量 `area`。

我们还可以重新为变量赋值，例如 `radius = radius + 1`。这并不会修改原始对象 `2.2`，而是创建一个新对象 `3.2` 并重新绑定给 `radius`。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_13.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_15.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_16.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_18.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_20.png)

## 字符串对象

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_22.png)

上一节我们简要提到了字符串。本节中我们来看看它的具体细节。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_24.png)

字符串是一个字符序列。字符可以是字母、数字、键盘上的特殊符号，甚至是换行符或制表符。我们通过将字符放在引号内来告诉Python创建一个字符串对象。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_26.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_28.png)

```python
a = "me"
z = "you"
```

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_30.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_31.png)

在内存中，字符串 `"me"` 被绑定到变量 `a`。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_33.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_34.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_36.png)

### 字符串操作

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_38.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_40.png)

以下是我们可以对字符串执行的一些常见操作。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_42.png)

#### 拼接与重复

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_44.png)

我们可以使用 `+` 运算符拼接字符串，使用 `*` 运算符重复字符串。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_46.png)

```python
b = "myself"
c = a + b  # 结果为 "memyself"
d = a + " " + b  # 结果为 "me myself"
silly = a * 3  # 结果为 "mememe"
```

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_48.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_50.png)

注意，拼接不会自动插入空格，需要手动添加。

#### 获取长度

我们可以使用 `len()` 函数获取字符串的长度。

```python
s = "abc"
chars = len(s)  # chars 的值为 3
```

#### 索引与切片

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_52.png)

我们可以通过索引获取字符串中的单个字符。在Python中，索引从0开始。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_54.png)

```python
s = "abc"
first_char = s[0]  # 结果为 'a'
second_char = s[1]  # 结果为 'b'
last_char = s[-1]  # 结果为 'c'，负索引表示从右向左数
```

如果索引超出范围，例如 `s[3]`，Python会抛出 `IndexError`。

除了获取单个字符，我们还可以通过切片获取子字符串。切片语法为 `[start:stop:step]`。
*   `start`：起始索引（包含）。
*   `stop`：结束索引（不包含）。
*   `step`：步长，决定跳过多少字符。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_56.png)

```python
s = "abcdefgh"
sub1 = s[3:6]    # 结果为 "def"，从索引3到5
sub2 = s[3:6:2]  # 结果为 "df"，从索引3到5，步长为2
reverse = s[::-1] # 结果为 "hgfedcba"，步长为-1表示反向
```

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_58.png)

如果省略 `step`，默认为1。如果 `start` 大于 `stop` 且步长为正，则返回空字符串 `""`。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_60.png)

#### 字符串的不可变性

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_62.png)

字符串是不可变对象。这意味着一旦创建，就无法修改。任何看似修改的操作，实际上都是创建了一个新的字符串对象。

```python
s = "car"
# s[0] = "b"  # 这行代码会报错，因为不能修改字符串
new_s = "b" + s[1:]  # 正确做法：创建一个新字符串 "bar"
```

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_64.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_66.png)

## 输入与输出

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_68.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_69.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_71.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_72.png)

到目前为止，我们编写的程序都是静态的，缺乏与用户的交互。本节我们来看看如何实现输入和输出。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_74.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_76.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_78.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_79.png)

### 输出：`print()` 函数

在文件编辑器中，Python不会自动显示表达式的值。我们必须使用 `print()` 函数来显式输出内容。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_81.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_83.png)

```python
s = "hello"
print(len(s))        # 输出：5
print(s[-3])         # 输出：l
```

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_85.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_87.png)

`print()` 会在输出内容后自动换行。如果想在同一行打印多个对象，可以用逗号分隔，它们之间会以空格分开。

```python
a = "the"
b = 3
c = "musketeers"
print(a, b, c)  # 输出：the 3 musketeers
```

如果想拼接输出（不加空格），需要确保所有部分都是字符串，必要时进行类型转换。

```python
print(a + str(b) + c)  # 输出：the3musketeers
```

### 输入：`input()` 函数

我们可以使用 `input()` 函数获取用户输入。它接受一个字符串参数作为提示信息，并返回用户输入的内容（始终作为字符串）。

```python
text = input("Type anything: ")
print(5 * text)  # 如果输入"hi"，则输出"hihihihihi"
```

如果希望输入的是数字，需要进行类型转换。

```python
num_str = input("Type a number: ")  # 输入"3"，num_str 是字符串 "3"
num_int = int(num_str)              # num_int 是整数 3
print(5 * num_int)                  # 输出 15
```

### 格式化字符串（f-string）

f-string 提供了一种更便捷的方式来混合输出文本和表达式。在字符串前加 `f` 或 `F`，并在字符串内用花括号 `{}` 包裹表达式。

```python
num = 10
fraction = 0.3
print(f"{num * fraction}% of {num}")  # 输出：3.0% of 10
```

## 布尔值与分支

现在，我们的程序都是线性执行的。本节我们将引入决策点，让程序可以根据条件执行不同的代码块。

### 布尔表达式与比较运算符

布尔类型只有两个值：`True` 和 `False`。我们可以通过比较运算符创建布尔表达式。

```python
print(2 < 3)        # 输出：True
print(5 == 5)       # 输出：True
print(5 != 5)       # 输出：False
print("a" == "A")   # 输出：False，区分大小写
```

我们还可以使用逻辑运算符 `and`、`or`、`not` 组合布尔表达式。

```python
print((2 < 3) and (3 < 4))  # 输出：True
print((2 < 3) or (5 < 4))   # 输出：True
print(not (2 < 3))          # 输出：False
```

### 条件语句：`if`、`elif`、`else`

条件语句允许我们根据布尔表达式的值来决定执行哪部分代码。Python使用缩进来定义代码块。

#### 简单的 `if` 语句

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_89.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_90.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_92.png)

如果条件为 `True`，则执行缩进块内的代码；否则跳过。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_94.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_96.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_97.png)

```python
x = 10
if x > 5:
    print("x is greater than 5")
print("This always prints.")
```

#### `if-else` 语句

如果 `if` 条件为 `True`，执行第一个代码块；否则执行 `else` 后的代码块。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_99.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_101.png)

```python
guess = int(input("Guess a number: "))
secret = 5
if guess == secret:
    print("Correct!")
else:
    print("Wrong!")
```

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_103.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_104.png)

#### `if-elif-else` 语句

可以检查多个条件。`elif` 是 `else if` 的缩写。Python会按顺序检查条件，执行第一个为 `True` 的代码块。如果所有条件都不为 `True`，则执行 `else` 块（如果存在）。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_106.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_108.png)

```python
peace = 22
sleep = 2
total = peace + sleep

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_110.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_111.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_113.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_114.png)

if total > 24:
    print("Impossible schedule")
elif total == 24:
    print("Full schedule")
else:
    remaining = 24 - total
    print(f"Have {remaining} hours left")
print("End of day")
```

#### 嵌套条件语句

条件语句内部可以包含其他条件语句。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_116.png)

```python
x = 10
y = 10
if x == y:
    print("x and y are equal")
    if y != 0:
        print("and y is not zero")
elif x > y:
    print("x is greater than y")
else:
    print("x is less than y")
```

**重要**：缩进决定了代码的归属。不正确的缩进会导致逻辑错误。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_118.png)

## 总结

本节课我们一起学习了三个核心内容：
1.  **字符串**：一种表示文本序列的数据类型，支持拼接、重复、索引、切片等操作，并且是不可变的。
2.  **输入与输出**：使用 `input()` 函数获取用户输入（始终为字符串），使用 `print()` 函数输出结果，并介绍了方便的 f-string 格式化方法。
3.  **分支**：通过 `if`、`elif`、`else` 语句和布尔表达式，我们可以在程序中引入决策点，让代码根据条件执行不同的路径，从而编写出更具交互性和灵活性的程序。

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_120.png)

![](img/9a9d3b2482d9097b8e6a514e32a7a11b_121.png)

下一节课，我们将进一步探讨分支，并开始学习循环，这是让程序重复执行某些操作的关键。