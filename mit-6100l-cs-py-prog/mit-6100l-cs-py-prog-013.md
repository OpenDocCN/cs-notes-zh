# 013：异常与断言 🐛

![](img/b69ddd28c09bcfce9388980855d29f9d_0.png)

在本节课中，我们将要学习Python中的异常与断言。它们是程序运行时出现的错误，但我们可以通过特定的代码结构来“捕获”并处理这些错误，而不是让程序直接崩溃。我们将学习如何使用`try`和`except`块来优雅地处理异常，以及如何使用`assert`语句来确保代码的假设条件得到满足。

---

## 什么是异常？🚨

当你的代码运行时，通常一切顺利。但有时，代码会遇到意外情况，这时就会引发一个“异常”。我们已经见过很多异常的例子，例如：
*   **索引错误**：当你试图访问列表中不存在的索引时。
*   **类型错误**：当你对不兼容的类型进行操作时。
*   **语法错误**：当代码的语法不正确时。
*   **名称错误**：当你引用一个未定义的变量时。

到目前为止，每当遇到异常，程序就会立即崩溃。但在Python中，我们可以编写代码来“处理”这些异常，让程序有机会从错误中恢复或优雅地终止。

---

![](img/b69ddd28c09bcfce9388980855d29f9d_2.png)

## 处理异常：try 和 except 🛡️

![](img/b69ddd28c09bcfce9388980855d29f9d_4.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_5.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_7.png)

我们使用`try`和`except`代码块来处理异常。其基本思想是：将可能出问题的代码放在`try`块中，如果这些代码成功执行，则跳过`except`块；如果`try`块中的代码引发了异常，程序会立即跳转到对应的`except`块中执行处理代码。

![](img/b69ddd28c09bcfce9388980855d29f9d_9.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_11.png)

我们可以将其类比为`if-else`结构：
*   `try`块：相当于“尝试执行这些代码”。
*   如果成功（无异常）：相当于`if`条件为真，不执行`else`部分。
*   如果失败（有异常）：相当于`if`条件为假，执行`else`（即`except`）部分来处理问题。

### 示例：对字符串中的数字求和

![](img/b69ddd28c09bcfce9388980855d29f9d_13.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_15.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_16.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_17.png)

假设我们有一个函数`sum_digits`，它接收一个字符串，并返回其中所有数字字符的和。

![](img/b69ddd28c09bcfce9388980855d29f9d_19.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_21.png)

**不使用异常处理的版本：**
```python
def sum_digits(s):
    total = 0
    for char in s:
        if char in ‘0123456789‘:
            total += int(char)
    return total

print(sum_digits(‘123‘)) # 输出：6
print(sum_digits(‘123abc‘)) # 输出：6 (非数字字符被if语句过滤)
```
如果去掉`if`判断，直接对每个字符进行`int()`转换，当遇到非数字字符（如`‘a‘`）时，程序会抛出`ValueError`并崩溃。

**使用异常处理的版本：**
```python
def sum_digits_except(s):
    total = 0
    for char in s:
        try:
            total += int(char)
        except ValueError:
            print(f‘Could not convert character: {char}‘)
    return total

print(sum_digits_except(‘123‘)) # 正常输出：6
print(sum_digits_except(‘123abc‘)) # 会打印无法转换的字符，但仍返回6
```
在这个版本中，`try`块尝试将每个字符转换为整数。如果转换成功，就加到总和里。如果转换失败（引发`ValueError`），则执行`except`块中的代码，打印一条提示信息，然后继续处理下一个字符，程序不会崩溃。

---

![](img/b69ddd28c09bcfce9388980855d29f9d_23.png)

## 捕获特定类型的异常 🎯

![](img/b69ddd28c09bcfce9388980855d29f9d_25.png)

我们可以为不同类型的异常编写不同的`except`块，从而进行更精细的错误处理。

### 示例：处理用户输入

考虑一个需要用户输入两个数字并进行除法的程序。

```python
# 没有异常处理
a = int(input(‘Enter first number: ‘))
b = int(input(‘Enter second number: ‘))
print(f‘a / b = {a / b}‘)
```
这段代码可能遇到两种异常：
1.  `ValueError`：如果用户输入的不是数字（如`‘hello‘`）。
2.  `ZeroDivisionError`：如果用户输入的第二个数字是`0`。

**使用特定异常处理的版本：**
```python
try:
    a = int(input(‘Enter first number: ‘))
    b = int(input(‘Enter second number: ‘))
    print(f‘a / b = {a / b}‘)
except ValueError:
    print(‘Could not convert to a number.‘)
except ZeroDivisionError:
    print(‘Cannot divide by zero.‘)
    print(f‘a / b = Infinity‘)
    print(f‘a + b = {a + b}‘)
except:
    print(‘Something went very wrong!‘)
```
*   如果输入引发`ValueError`，则执行第一个`except`块。
*   如果输入引发`ZeroDivisionError`，则执行第二个`except`块。
*   最后一个`except`块（不指定异常类型）会捕获所有其他未被前面捕获的异常，作为“安全网”。

---

## 主动引发异常 ⚠️

有时，我们希望在检测到某种错误条件时，主动停止程序，但使用我们自定义的错误信息。这可以通过`raise`语句实现。

![](img/b69ddd28c09bcfce9388980855d29f9d_27.png)

### 示例：在异常处理中引发自定义异常

![](img/b69ddd28c09bcfce9388980855d29f9d_28.png)

修改之前的`sum_digits`函数，如果字符串包含非数字字符，我们不是简单地跳过，而是主动引发一个带有清晰信息的`ValueError`。

```python
def sum_digits_raise(s):
    total = 0
    for char in s:
        try:
            total += int(char)
        except ValueError:
            raise ValueError(‘String contained a non-digit character.‘)
    return total

![](img/b69ddd28c09bcfce9388980855d29f9d_30.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_32.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_34.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_36.png)

print(sum_digits_raise(‘123‘)) # 正常输出：6
print(sum_digits_raise(‘123a‘)) # 引发 ValueError: String contained a non-digit character.
```
这样，程序仍然会停止，但错误信息对我们和用户来说都更清晰、更有帮助。

![](img/b69ddd28c09bcfce9388980855d29f9d_38.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_40.png)

---

## 断言：强制执行约定 ✅

断言是一种特殊的异常，用于“防御性编程”。它用于在代码中强制执行为函数或变量设定的“约定”或假设。如果断言的条件为`False`，程序会立即引发一个`AssertionError`并停止。

断言的语法是：
```python
assert <condition>, ‘Error message if condition is False‘
```

### 示例：在函数中使用断言

继续使用`sum_digits`函数，假设我们的约定要求输入字符串`s`非空。

```python
def sum_digits_assert(s):
    assert len(s) > 0, ‘Input string cannot be empty‘
    total = 0
    for char in s:
        if char in ‘0123456789‘:
            total += int(char)
    return total

![](img/b69ddd28c09bcfce9388980855d29f9d_42.png)

print(sum_digits_assert(‘123‘)) # 正常输出：6
print(sum_digits_assert(‘‘)) # 引发 AssertionError: Input string cannot be empty
```
使用断言的好处是，它能在错误发生的源头就阻止程序继续执行，防止错误的值在后续代码中传播，使得调试更加容易。

![](img/b69ddd28c09bcfce9388980855d29f9d_44.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_45.png)

---

## 综合练习：成对除法函数 ✍️

让我们编写一个函数`pairwise_division`，它接受两个等长的非空列表`L_num`和`L_denom`，返回一个新列表，其中每个元素是`L_num[i] / L_denom[i]`。

要求：
1.  如果`L_denom`中包含`0`，则引发一个`ValueError`。
2.  使用断言来确保输入列表非空且长度相等。

以下是实现步骤：

![](img/b69ddd28c09bcfce9388980855d29f9d_47.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_49.png)

首先，实现基本功能：
```python
def pairwise_division(L_num, L_denom):
    result = []
    for i in range(len(L_num)):
        result.append(L_num[i] / L_denom[i])
    return result
```

![](img/b69ddd28c09bcfce9388980855d29f9d_51.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_52.png)

然后，添加异常处理来检查分母是否为0：
```python
def pairwise_division(L_num, L_denom):
    result = []
    for i in range(len(L_num)):
        if L_denom[i] == 0:
            raise ValueError(‘Denominator list contains zero.‘)
        result.append(L_num[i] / L_denom[i])
    return result
```

![](img/b69ddd28c09bcfce9388980855d29f9d_54.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_56.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_58.png)

最后，添加断言来强制执行输入约定：
```python
def pairwise_division(L_num, L_denom):
    assert len(L_num) > 0 and len(L_denom) > 0, ‘Input lists cannot be empty.‘
    assert len(L_num) == len(L_denom), ‘Input lists must have the same length.‘

    result = []
    for i in range(len(L_num)):
        if L_denom[i] == 0:
            raise ValueError(‘Denominator list contains zero.‘)
        result.append(L_num[i] / L_denom[i])
    return result

![](img/b69ddd28c09bcfce9388980855d29f9d_60.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_62.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_64.png)

# 测试
print(pairwise_division([4,5,6], [1,2,3])) # 输出：[4.0, 2.5, 2.0]
print(pairwise_division([4,5], [1,2,3])) # 引发 AssertionError: Input lists must have the same length.
print(pairwise_division([4,5,6], [1,0,3])) # 引发 ValueError: Denominator list contains zero.
```

![](img/b69ddd28c09bcfce9388980855d29f9d_66.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_67.png)

---

![](img/b69ddd28c09bcfce9388980855d29f9d_69.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_71.png)

## 总结 📚

本节课中我们一起学习了Python中的异常与断言。

*   **异常**是程序运行时发生的错误。使用`try`和`except`块可以“捕获”并处理异常，避免程序直接崩溃。你可以：
    *   打印友好的错误信息。
    *   设置默认值。
    *   或者使用`raise`主动引发自定义的异常。
*   **断言**是一种特殊的异常，使用`assert`语句。它用于在代码中强制执行假设和约定（例如函数参数必须满足的条件）。如果断言失败，程序会立即停止，这有助于在错误传播开之前就发现它们，是防御性编程的重要工具。

![](img/b69ddd28c09bcfce9388980855d29f9d_73.png)

![](img/b69ddd28c09bcfce9388980855d29f9d_75.png)

掌握异常和断言能让你编写出更健壮、更易于调试和维护的程序。