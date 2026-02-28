# 004：字符串循环、猜测试算法与二进制

![](img/9e0784c65c73f82fc05451c8c8ab04cd_0.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_0.png)

在本节课中，我们将继续学习循环，并了解循环的一些其他细节。然后，我们将开始学习第一个算法——猜测试算法。最后，我们将开始讨论二进制数，为学习下一个算法做准备。

![](img/9e0784c65c73f82fc05451c8c8ab04cd_2.png)

## 循环回顾与`break`语句

![](img/9e0784c65c73f82fc05451c8c8ab04cd_4.png)

上一节我们介绍了`while`循环和`for`循环，它们是控制代码执行流程的两种方式，可以自动重复执行某些代码行。`while`循环在某个条件为真时重复执行代码，而`for`循环则针对一系列值重复执行代码。今天我们将看到，`for`循环中的值序列也可以是非数值的。

![](img/9e0784c65c73f82fc05451c8c8ab04cd_6.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_8.png)

这两种循环类型都会在特定时刻结束：`while`循环在条件变为假时结束，`for`循环在值序列耗尽时结束。但有时我们希望提前退出循环，而不是等待条件变为假或序列耗尽。

![](img/9e0784c65c73f82fc05451c8c8ab04cd_10.png)

为了在自然结束之前退出循环，我们可以使用`break`语句。`break`语句允许我们退出循环，退出的将是紧邻包围该`break`语句的循环。

以下是一个嵌套`while`循环的例子：

![](img/9e0784c65c73f82fc05451c8c8ab04cd_12.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_14.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_16.png)

```python
while condition1:
    while condition2:
        expression_A
        break
        expression_B
    expression_C
```

当Python看到`break`语句时，它会立即退出包围该`break`语句的循环（即条件为`condition2`的循环）。它甚至不会返回去检查`condition2`，这意味着`expression_B`将永远不会被执行。这是一个糟糕的代码示例，仅用于展示`break`语句的影响。`expression_C`则只会在`condition1`为真时执行。

`break`语句只退出直接包围它的循环。例如，在嵌套循环中，它只退出内层循环，外层循环会继续执行。

## 循环遍历字符串

上一节我们主要使用`for`循环遍历数字序列。实际上，`for`循环可以遍历任何序列的值，包括字符串中的字符。

以下是两种遍历字符串并检查特定字符的方法：

![](img/9e0784c65c73f82fc05451c8c8ab04cd_18.png)

```python
# 方法一：通过索引遍历
s = "demo string"
for index in range(len(s)):
    if s[index] == 'i' or s[index] == 'u':
        print("There's an i or u")

![](img/9e0784c65c73f82fc05451c8c8ab04cd_20.png)

# 方法二：直接遍历字符
s = "demo string"
for char in s:
    if char == 'i' or char == 'u':
        print("There's an i or u")
```

![](img/9e0784c65c73f82fc05451c8c8ab04cd_22.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_24.png)

第二种方法更简洁，因为它直接遍历字符串中的每个字符，无需通过索引间接访问。

此外，我们还可以使用`in`关键字来简化条件判断：

![](img/9e0784c65c73f82fc05451c8c8ab04cd_26.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_28.png)

```python
s = "demo string"
for char in s:
    if char in 'iu':
        print("There's an i or u")
```

这种方法在需要检查字符是否属于一个较长的字符集合时尤其有用，可以避免编写冗长的`or`条件。

## 实践：编写加油机器人程序

现在，让我们编写一个稍微复杂一点的程序，这是一个加油机器人程序的初级版本。

该程序接收一个单词和一个热情等级，然后进行拼写加油，并重复打印该单词多次。

以下是代码示例：

```python
word = input("Enter a word: ")
times = int(input("Enter enthusiasm level: "))

# 拼写部分
vowels = 'aeiou'
for w in word:
    if w in vowels:
        print(f"Give me an {w}!")
    else:
        print(f"Give me a {w}!")
print(f"What does that spell? {word.upper()}!")

# 重复部分
for i in range(times):
    print(f"{word.upper()}!!!")
```

这个程序包含两个独立的循环：一个用于拼写单词，另一个用于根据热情等级重复打印单词。注意，在第二个循环中，我们并没有使用循环变量`i`，这完全没问题，因为我们只是需要重复执行某个动作特定的次数。

## 实践：计算字符串中唯一字母的数量

接下来，我们尝试编写一个程序，计算给定字符串中唯一字母的数量。假设字符串只包含小写字母。

例如，对于字符串`"abca"`，唯一字母是`a`、`b`、`c`，因此数量为3。

我们可以使用一个额外的字符串变量来记录已经见过的字母，然后遍历字符串中的每个字符，如果该字符不在已见字符串中，则将其添加进去并计数。

以下是实现代码：

```python
s = "abca"
seen = ""
count = 0

for char in s:
    if char not in seen:
        seen += char
        count += 1

print(f"Number of unique letters: {count}")
```

或者，我们可以直接利用`seen`字符串的长度来得到唯一字母的数量，从而省略计数器：

```python
s = "abca"
seen = ""

for char in s:
    if char not in seen:
        seen += char

print(f"Number of unique letters: {len(seen)}")
```

这种方法通过一个额外的变量来跟踪状态，是解决此类问题的常见模式。

## 猜测试算法

到目前为止，我们已经学习了对象、变量、表达式、分支和循环。这些工具足以让我们开始编写有趣的算法。第一个要学习的算法是猜测试算法，也称为穷举枚举法。

猜测试算法的基本思想是：给定一个问题，我们猜测一个可能的解，然后测试这个猜测是否正确。如果正确，我们就找到了解；如果不正确，我们继续猜测，直到穷尽所有可能的猜测。这样，我们要么找到解，要么确定在给定的猜测范围内没有解。

### 应用：寻找完全平方根

让我们以寻找完全平方根为例。假设我们想判断一个数`x`是否为完全平方数，如果是，找出它的平方根；如果不是，则说明它不是完全平方数。

![](img/9e0784c65c73f82fc05451c8c8ab04cd_30.png)

我们可以系统地从0开始猜测，依次检查每个数的平方是否等于`x`。如果某个数的平方等于`x`，我们就找到了平方根。如果某个数的平方超过了`x`，我们就可以停止，因为更大的数的平方只会更大。

![](img/9e0784c65c73f82fc05451c8c8ab04cd_32.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_33.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_35.png)

以下是使用`while`循环实现的代码：

![](img/9e0784c65c73f82fc05451c8c8ab04cd_37.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_39.png)

```python
x = int(input("Enter an integer: "))
guess = 0

![](img/9e0784c65c73f82fc05451c8c8ab04cd_41.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_43.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_45.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_47.png)

while guess**2 < x:
    guess += 1

if guess**2 == x:
    print(f"Square root of {x} is {guess}")
else:
    print(f"{x} is not a perfect square")
```

这段代码对于正数有效，但对于负数，循环不会执行，因为0的平方不小于负数。我们可以通过添加一个标志变量来处理负数情况：

![](img/9e0784c65c73f82fc05451c8c8ab04cd_49.png)

```python
x = int(input("Enter an integer: "))
neg_flag = False

![](img/9e0784c65c73f82fc05451c8c8ab04cd_51.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_53.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_54.png)

if x < 0:
    neg_flag = True
    x = abs(x)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_56.png)

guess = 0
while guess**2 < x:
    guess += 1

![](img/9e0784c65c73f82fc05451c8c8ab04cd_58.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_59.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_61.png)

if guess**2 == x:
    if neg_flag:
        print(f"Square root of {-x} is {guess}i")
    else:
        print(f"Square root of {x} is {guess}")
else:
    print(f"{x} is not a perfect square")
    if neg_flag:
        print("Just checking. Did you mean", abs(x), "?")
```

通过使用布尔标志，我们可以跟踪用户输入是否为负数，并在最后进行相应的处理。

![](img/9e0784c65c73f82fc05451c8c8ab04cd_63.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_64.png)

### 使用`for`循环实现猜测试

![](img/9e0784c65c73f82fc05451c8c8ab04cd_66.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_68.png)

猜测试算法本质上是在遍历一系列可能的值，因此使用`for`循环可能更直观。以下是使用`for`循环寻找完全立方根的示例：

```python
cube = int(input("Enter an integer: "))

for guess in range(abs(cube) + 1):
    if guess**3 == abs(cube):
        break

if guess**3 != abs(cube):
    print(f"{cube} is not a perfect cube")
else:
    if cube < 0:
        guess = -guess
    print(f"Cube root of {cube} is {guess}")
```

这段代码通过`break`语句在找到解时提前退出循环，然后检查退出循环的原因，以判断是否找到了解。

## 布尔标志

在上述例子中，我们使用了布尔变量（通常称为“标志”）来跟踪某些事件是否发生。布尔标志是一个只能取两个值（通常是`True`或`False`）的变量，用于在代码中标记某个状态或事件。

例如，在寻找完全平方根的程序中，我们使用`neg_flag`来标记输入是否为负数。在检查秘密数字是否在范围内的程序中，我们使用`found`标志来标记是否找到了数字。

使用布尔标志可以使代码更清晰，特别是在需要在循环结束后根据之前发生的事件做出决策时。

![](img/9e0784c65c73f82fc05451c8c8ab04cd_70.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_71.png)

## 应用：解决数学问题

![](img/9e0784c65c73f82fc05451c8c8ab04cd_73.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_74.png)

猜测试算法不仅可以用于数学计算，还可以解决实际生活中的问题，例如分配问题。

假设Alyssa、Ben和Cindy在卖筹款活动的门票。Ben比Alyssa少卖2张，Cindy卖的是Alyssa的两倍。总共卖了10张票。问Alyssa卖了多少张？

我们可以通过遍历所有可能的组合来解决这个问题：

```python
for a in range(11):  # Alyssa could sell 0 to 10 tickets
    for b in range(11):  # Ben could sell 0 to 10 tickets
        for c in range(11):  # Cindy could sell 0 to 10 tickets
            if a + b + c == 10 and b == a - 2 and c == 2 * a:
                print(f"Alyssa sold {a}, Ben sold {b}, Cindy sold {c}")
```

![](img/9e0784c65c73f82fc05451c8c8ab04cd_76.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_78.png)

然而，这种方法在数字较大时会非常慢。我们可以结合代数知识，只遍历Alyssa的可能票数，然后根据关系式计算Ben和Cindy的票数，从而大大提高效率：

![](img/9e0784c65c73f82fc05451c8c8ab04cd_80.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_82.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_84.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_86.png)

```python
for a in range(11):
    b = a - 2
    c = 2 * a
    if a + b + c == 10:
        print(f"Alyssa sold {a}, Ben sold {b}, Cindy sold {c}")
```

![](img/9e0784c65c73f82fc05451c8c8ab04cd_88.png)

这种方法展示了计算思维的力量：通过结合计算和代数，我们可以高效地解决问题。

![](img/9e0784c65c73f82fc05451c8c8ab04cd_90.png)

## 二进制数

![](img/9e0784c65c73f82fc05451c8c8ab04cd_92.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_94.png)

在编程中，我们处理两种主要的数字类型：整数和浮点数。整数是完整的数字，浮点数是实数。然而，在处理浮点数时，可能会出现一些意想不到的问题。

例如，考虑以下代码：

```python
x = 0.0
for i in range(10):
    x += 0.1

print(x == 1.0)  # 输出 False
print(x)         # 输出 0.9999999999999999
```

尽管我们加了10次0.1，期望得到1.0，但由于浮点数在计算机中的表示方式，实际结果略有误差。这种误差在多次操作后会累积，导致令人惊讶的结果。

计算机使用二进制（基数为2）表示数字，因为硬件更容易处理两种状态（如高电压和低电压）。人类通常使用十进制（基数为10），但计算机内部使用二进制。

### 整数转换

将十进制整数转换为二进制相对简单。例如，将1507转换为二进制：

1. 找到最大的2的幂，使其不超过1507（2^10 = 1024）。
2. 从1507中减去1024，得到483。
3. 找到下一个最大的2的幂，使其不超过483（2^8 = 256）。
4. 重复此过程，直到余数为0。

最终，1507的二进制表示为`10111100011`。

### 转换算法

我们可以通过连续除以2并记录余数的方法，系统地將十进制数转换为二进制。以下是一个示例算法：

![](img/9e0784c65c73f82fc05451c8c8ab04cd_96.png)

```python
num = 1507
result = ""

![](img/9e0784c65c73f82fc05451c8c8ab04cd_98.png)

if num == 0:
    result = "0"
else:
    while num > 0:
        remainder = num % 2
        result = str(remainder) + result
        num = num // 2

![](img/9e0784c65c73f82fc05451c8c8ab04cd_100.png)

print(result)  # 输出 10111100011
```

![](img/9e0784c65c73f82fc05451c8c8ab04cd_102.png)

这个算法通过循环不断将数字除以2，并将余数添加到结果字符串的前面，从而得到二进制表示。

## 总结

![](img/9e0784c65c73f82fc05451c8c8ab04cd_104.png)

本节课中，我们一起学习了以下内容：

1.  **`break`语句**：用于提前退出循环，只退出直接包围它的循环。
2.  **循环遍历字符串**：`for`循环可以直接遍历字符串中的字符，无需通过索引。
3.  **猜测试算法**：通过系统性地猜测和检查来解决问题，可以使用`while`循环或`for`循环实现。
4.  **布尔标志**：使用布尔变量跟踪代码中的事件或状态，使逻辑更清晰。
5.  **二进制数**：计算机使用二进制表示数字，浮点数运算可能导致微小误差，了解二进制有助于理解这些误差的来源。

![](img/9e0784c65c73f82fc05451c8c8ab04cd_106.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_108.png)

![](img/9e0784c65c73f82fc05451c8c8ab04cd_109.png)

通过结合循环、条件判断和布尔标志，我们可以解决各种实际问题，从数学计算到逻辑推理。在接下来的课程中，我们将学习近似算法，以更高效地处理浮点数误差和其他复杂问题。