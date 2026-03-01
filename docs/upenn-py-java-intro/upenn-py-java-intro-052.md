# 052：代码练习-遍历姓名 ✍️

在本节课中，我们将通过一个简单的代码练习来学习如何使用 `for` 循环遍历字符串，并在这个过程中统计字符串的长度。我们将编写一个程序，提示用户输入他们的名字，然后逐个字母地打印出来，并最终统计名字中的字母总数。

## 概述

我们将创建一个程序，其核心功能包括：
1.  获取用户输入的名字。
2.  使用 `for` 循环遍历名字中的每个字母。
3.  在遍历过程中打印每个字母并统计字母总数。
4.  最后输出统计结果。

## 分步教程

### 第一步：获取用户输入

首先，我们需要从用户那里获取他们的名字。我们将使用 Python 的 `input()` 函数来实现这一点，并将用户输入的值存储在一个变量中。

![](img/f60818fabeb1656cc704fdef1cd0e72c_1.png)

以下是获取用户输入的代码：
```python
name = input("What is your first name? ")
```
这段代码会在屏幕上显示提示信息 “What is your first name?”，并等待用户输入。用户输入的内容将被赋值给变量 `name`。

### 第二步：初始化计数器

为了统计名字中的字母数量，我们需要一个计数器变量。在开始遍历之前，我们将这个计数器初始化为 0。

初始化计数器的代码如下：
```python
letter_count = 0
```
变量 `letter_count` 将用于记录我们遍历到的字母数量。

### 第三步：打印初始信息并开始遍历

在开始遍历之前，我们先打印一条消息，告知用户程序即将开始拼写他们的名字。

接着，我们使用 `for` 循环来遍历名字 `name` 中的每一个字符。在循环中，变量 `x` 会依次代表名字中的每一个字母。

以下是打印初始信息和 `for` 循环的代码：
```python
print(name, "is spelled:")
for x in name:
```
现在，我们已经准备好了循环结构。在下一节中，我们将看看在循环内部需要执行哪些操作。

### 第四步：循环内的操作

在 `for` 循环内部，我们需要完成三件事：
1.  打印当前字母 `x`。
2.  在打印的字母后面添加一个空格，使输出更清晰。
3.  将计数器 `letter_count` 的值增加 1，以记录这个字母。

以下是循环体内的代码：
```python
    print(x, end=" ")
    letter_count += 1
```
这里，`print(x, end=" ")` 中的 `end=" "` 参数确保每个字母打印在同一行，并用空格分隔。`letter_count += 1` 是 `letter_count = letter_count + 1` 的简写，用于递增计数器。

### 第五步：输出最终结果

当 `for` 循环遍历完名字中的所有字母后，我们会退出循环。此时，我们需要输出最终的统计结果。

首先，我们打印一个空行，让输出更美观。然后，我们打印出统计到的字母总数以及用户的名字。

以下是输出最终结果的代码：
```python
print()
print("That is", letter_count, "letters in the name", name)
```
`print()` 会输出一个空行。第二行 `print` 语句将计数器 `letter_count` 的值和变量 `name` 的值一起输出，形成完整的句子。

## 完整代码与运行示例

将以上所有步骤组合起来，就得到了完整的程序代码：

```python
name = input("What is your first name? ")
letter_count = 0

print(name, "is spelled:")
for x in name:
    print(x, end=" ")
    letter_count += 1

print()
print("That is", letter_count, "letters in the name", name)
```

当你运行这段代码时，程序会与你进行如下交互（假设用户输入的名字是 “Brandon”）：
```
What is your first name? Brandon
Brandon is spelled:
B r a n d o n
That is 7 letters in the name Brandon
```

![](img/f60818fabeb1656cc704fdef1cd0e72c_3.png)

## 总结

在本节课中，我们一起学习并完成了一个 Python 编程练习。我们掌握了如何使用 `for` 循环来遍历字符串中的每一个字符，并在循环过程中进行打印和计数操作。关键步骤包括：使用 `input()` 获取输入，初始化变量，利用 `for x in name:` 进行遍历，在循环体内处理每个字符，最后格式化输出结果。这个练习巩固了循环和字符串处理的基本概念。