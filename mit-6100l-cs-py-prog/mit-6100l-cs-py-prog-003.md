# 003：迭代

![](img/03edf7a90b8886750aea939717f30f97_0.png)

在本节课中，我们将要学习一种新的控制流机制——迭代。我们将探讨如何使用 `while` 循环和 `for` 循环来重复执行代码块，并理解它们在不同场景下的应用。

## 回顾：分支结构

![](img/03edf7a90b8886750aea939717f30f97_2.png)

![](img/03edf7a90b8886750aea939717f30f97_4.png)

![](img/03edf7a90b8886750aea939717f30f97_6.png)

上一节我们介绍了如何使用分支结构（`if`、`elif`、`else`）来控制程序流程。分支允许程序根据条件是否为真，选择性地执行不同的代码块。

![](img/03edf7a90b8886750aea939717f30f97_8.png)

以下是分支结构的关键点：
*   `if` 语句：如果条件为真，则执行其缩进的代码块。
*   `if-else` 语句：如果 `if` 条件为真，执行其代码块；否则，执行 `else` 的代码块。
*   `if-elif-else` 语句：可以检查多个条件。Python 会按顺序检查，并执行第一个为真的条件对应的代码块。如果所有条件都为假，则执行 `else` 块（如果存在）。

代码块通过缩进来定义，这在 Python 中是强制性的。

## 引入迭代的动机

![](img/03edf7a90b8886750aea939717f30f97_10.png)

![](img/03edf7a90b8886750aea939717f30f97_11.png)

![](img/03edf7a90b8886750aea939717f30f97_13.png)

现在，我们来看一个简单的游戏场景：角色进入“迷失森林”，需要选择向左或向右走。如果选择向右，会再次看到相同的场景；只有选择向左，才能成功离开。

![](img/03edf7a90b8886750aea939717f30f97_15.png)

![](img/03edf7a90b8886750aea939717f30f97_17.png)

![](img/03edf7a90b8886750aea939717f30f97_18.png)

如果我们只用分支结构来编写这个游戏，会遇到一个问题：我们无法预知用户会连续选择多少次“向右”。因此，我们需要嵌套无数层 `if` 语句，这显然是不可行的。

![](img/03edf7a90b8886750aea939717f30f97_20.png)

![](img/03edf7a90b8886750aea939717f30f97_22.png)

![](img/03edf7a90b8886750aea939717f30f97_24.png)

这种情况非常适合使用迭代：**只要用户选择“向右”这个条件为真，就重复显示森林场景并询问方向**。一旦条件变为假（用户选择“向左”），就跳出循环，显示出口。

![](img/03edf7a90b8886750aea939717f30f97_25.png)

![](img/03edf7a90b8886750aea939717f30f97_27.png)

![](img/03edf7a90b8886750aea939717f30f97_28.png)

## While 循环

![](img/03edf7a90b8886750aea939717f30f97_30.png)

![](img/03edf7a90b8886750aea939717f30f97_32.png)

![](img/03edf7a90b8886750aea939717f30f97_34.png)

![](img/03edf7a90b8886750aea939717f30f97_36.png)

`while` 循环正是用于处理这种“当某个条件为真时，重复执行代码”的情况。

其语法结构如下：
```python
while <条件>:
    # 当条件为真时要执行的代码块
```
*   `while` 是关键字。
*   `<条件>` 是一个表达式，其结果为布尔值（`True` 或 `False`）。
*   冒号 `:` 表示代码块开始。
*   缩进的代码是循环体，会在条件为真时重复执行。

执行流程：
1.  检查 `<条件>` 是否为真。
2.  如果为真，执行循环体内的所有缩进代码。
3.  执行完毕后，**自动返回第一步重新检查条件**。
4.  如果条件为假，则跳过循环体，继续执行后续代码。

![](img/03edf7a90b8886750aea939717f30f97_38.png)

![](img/03edf7a90b8886750aea939717f30f97_40.png)

### 示例：迷失森林游戏

![](img/03edf7a90b8886750aea939717f30f97_42.png)

![](img/03edf7a90b8886750aea939717f30f97_43.png)

让我们用 `while` 循环实现这个游戏：
```python
where = input("你在迷失森林中，想向左走还是向右走？")
while where == "right":
    where = input("你在迷失森林中，想向左走还是向右走？")
print("你成功走出了森林！")
```
**注意**：字符串比较是区分大小写的。如果用户输入 `"RIGHT"`，条件 `where == "right"` 将为假，循环会立即结束。

### 示例：打印多个字符

![](img/03edf7a90b8886750aea939717f30f97_45.png)

![](img/03edf7a90b8886750aea939717f30f97_46.png)

我们也可以用循环来处理数字：
```python
n = int(input("请输入一个整数："))
while n > 0:
    print("X")
    n = n - 1  # 或者写作 n -= 1
```
这段代码会根据用户输入的数字 `n`，打印相应次数的 `"X"`。关键在于循环体内必须修改 `n` 的值（`n = n - 1`），使其逐渐向条件 `n > 0` 为假的方向变化，否则循环将无限进行下去。

![](img/03edf7a90b8886750aea939717f30f97_48.png)

![](img/03edf7a90b8886750aea939717f30f97_49.png)

### 避免无限循环

如果循环条件永远为真，程序将陷入**无限循环**。在开发环境中，你可以通过点击停止按钮、按 `Ctrl+C`（Windows/Linux）或 `Command+C`（Mac）来中断程序。

![](img/03edf7a90b8886750aea939717f30f97_51.png)

![](img/03edf7a90b8886750aea939717f30f97_53.png)

一个常见的无限循环例子是：
```python
while True:
    print("陷入循环")
```
因为条件 `True` 永远为真。

### 练习：增强版迷失森林

现在，尝试修改迷失森林游戏，增加一个功能：当用户连续选择“向右”超过两次后，下次询问时先打印一个悲伤的表情 `:(`。

思路是引入一个计数器变量：
```python
count = 0
where = input("你在迷失森林中，想向左走还是向右走？")
while where == "right":
    count = count + 1  # 或者 count += 1
    if count > 2:
        print(":(")
    where = input("你在迷失森林中，想向左走还是向右走？")
print("你成功走出了森林！")
```

![](img/03edf7a90b8886750aea939717f30f97_55.png)

![](img/03edf7a90b8886750aea939717f30f97_57.png)

## For 循环

`while` 循环适用于不确定循环次数的情况。但当我们需要**遍历一个已知的序列**（例如一系列数字）时，`for` 循环是更简洁、更不易出错的选择。

回顾一下之前用 `while` 循环打印数字的模式：
```python
# while 循环版本
n = 0
while n < 5:
    print(n)
    n = n + 1
```
这种“初始化变量 -> 检查条件 -> 执行操作 -> 更新变量”的模式非常常见。`for` 循环可以将其简化为：
```python
# for 循环版本
for n in range(5):
    print(n)
```

### For 循环语法

```python
for <变量> in <序列>:
    # 对序列中每个元素要执行的代码
```
*   `for` 和 `in` 是关键字。
*   `<变量>` 是一个变量名，在每次循环中会被自动赋值为序列中的下一个元素。
*   `<序列>` 可以是数字序列、字符串、列表等。
*   冒号和缩进规则与 `while` 循环相同。

![](img/03edf7a90b8886750aea939717f30f97_59.png)

![](img/03edf7a90b8886750aea939717f30f97_61.png)

![](img/03edf7a90b8886750aea939717f30f97_63.png)

![](img/03edf7a90b8886750aea939717f30f97_65.png)

执行流程：`<变量>` 会依次取 `<序列>` 中的每一个值，并对每个值执行一次循环体内的代码。

![](img/03edf7a90b8886750aea939717f30f97_67.png)

![](img/03edf7a90b8886750aea939717f30f97_68.png)

![](img/03edf7a90b8886750aea939717f30f97_70.png)

![](img/03edf7a90b8886750aea939717f30f97_72.png)

### Range 函数

![](img/03edf7a90b8886750aea939717f30f97_74.png)

![](img/03edf7a90b8886750aea939717f30f97_76.png)

![](img/03edf7a90b8886750aea939717f30f97_77.png)

![](img/03edf7a90b8886750aea939717f30f97_78.png)

`range()` 函数用于生成一个数字序列，常与 `for` 循环搭配使用。

![](img/03edf7a90b8886750aea939717f30f97_80.png)

`range()` 有三种用法：
*   `range(stop)`：生成从 `0` 到 `stop-1` 的整数序列。
*   `range(start, stop)`：生成从 `start` 到 `stop-1` 的整数序列。
*   `range(start, stop, step)`：生成从 `start` 到 `stop-1`，步长为 `step` 的整数序列。

![](img/03edf7a90b8886750aea939717f30f97_82.png)

示例：
```python
for i in range(4):        # i: 0, 1, 2, 3
    print(i)
for j in range(3, 5):     # j: 3, 4
    print(j)
for k in range(1, 6, 2):  # k: 1, 3, 5
    print(k)
for l in range(4, 0, -1): # l: 4, 3, 2, 1
    print("$" * l)
```

![](img/03edf7a90b8886750aea939717f30f97_84.png)

![](img/03edf7a90b8886750aea939717f30f97_86.png)

### 示例：计算序列和

使用 `for` 循环计算从 0 到 9 的和：
```python
my_sum = 0
for i in range(10):
    my_sum += i  # 等价于 my_sum = my_sum + i
print(my_sum)  # 输出 45
```

![](img/03edf7a90b8886750aea939717f30f97_88.png)

![](img/03edf7a90b8886750aea939717f30f97_90.png)

![](img/03edf7a90b8886750aea939717f30f97_92.png)

![](img/03edf7a90b8886750aea939717f30f97_94.png)

![](img/03edf7a90b8886750aea939717f30f97_95.png)

### 练习：计算指定范围的累加和

![](img/03edf7a90b8886750aea939717f30f97_97.png)

![](img/03edf7a90b8886750aea939717f30f97_98.png)

![](img/03edf7a90b8886750aea939717f30f97_100.png)

假设我们想计算从 `start` 到 `end`（包含两端）的整数和。以下代码有一个小错误，请修复它：
```python
start = 3
end = 5
total = 0
for num in range(start, end):
    total += num
print(total)
```
这段代码只会计算 `3+4=7`，因为它没有包含 `end`（5）。修复方法是让 `range` 的停止参数为 `end + 1`：
```python
for num in range(start, end + 1):
    total += num
```
在调试时，可以在循环内添加 `print` 语句来查看 `num` 的实际取值，这非常有用。

![](img/03edf7a90b8886750aea939717f30f97_102.png)

![](img/03edf7a90b8886750aea939717f30f97_103.png)

### 对比：计算阶乘

![](img/03edf7a90b8886750aea939717f30f97_105.png)

![](img/03edf7a90b8886750aea939717f30f97_107.png)

![](img/03edf7a90b8886750aea939717f30f97_108.png)

![](img/03edf7a90b8886750aea939717f30f97_110.png)

最后，让我们用 `for` 循环重写之前计算阶乘的 `while` 循环代码，感受其简洁性：
```python
# while 循环计算 4!
x = 4
factorial = 1
i = 1
while i <= x:
    factorial *= i
    i += 1
print(f"{x}! = {factorial}")

# for 循环计算 4!
x = 4
factorial = 1
for i in range(1, x + 1):
    factorial *= i
print(f"{x}! = {factorial}")
```
`for` 循环将变量的初始化、条件检查和更新都浓缩在了一行之内。

![](img/03edf7a90b8886750aea939717f30f97_112.png)

![](img/03edf7a90b8886750aea939717f30f97_113.png)

## 总结

![](img/03edf7a90b8886750aea939717f30f97_115.png)

![](img/03edf7a90b8886750aea939717f30f97_117.png)

![](img/03edf7a90b8886750aea939717f30f97_118.png)

![](img/03edf7a90b8886750aea939717f30f97_120.png)

本节课我们一起学习了两种迭代结构：
*   **`while` 循环**：在条件为真时重复执行代码块。适用于循环次数未知的场景，但需注意避免无限循环。
*   **`for` 循环**：遍历一个序列（如 `range()` 生成的数字序列），对其中每个元素执行一次代码块。适用于循环次数已知或需要遍历集合的场景。

![](img/03edf7a90b8886750aea939717f30f97_122.png)

![](img/03edf7a90b8886750aea939717f30f97_124.png)

![](img/03edf7a90b8886750aea939717f30f97_125.png)

![](img/03edf7a90b8886750aea939717f30f97_126.png)

理解循环的执行流程（特别是变量如何变化）是编写正确代码的关键。请务必通过课后练习来巩固这些概念。