# 056：代码练习-密码验证 🔐

在本节课中，我们将学习如何使用 `while` 循环来编写一个密码验证程序。程序会持续要求用户输入密码，直到输入正确为止。

## 概述 📋

我们将创建一个程序，其核心功能是验证用户输入的密码。程序会使用一个 `while` 循环来反复提示用户输入，直到输入的密码与预设的密码匹配。如果密码错误，程序会提示用户重新输入；如果密码正确，则输出欢迎信息并结束循环。

## 程序设计与实现

上一节我们介绍了循环的基本概念，本节中我们来看看如何应用 `while` 循环来解决一个实际问题——密码验证。

首先，我们需要初始化一个变量来存储用户输入的密码。由于在首次进入循环前用户尚未输入，我们将其设置为空字符串。

```python
password = ""
```

![](img/7808ea512767690c5ca8168bdd322f02_1.png)

接下来，我们设置循环条件。只要 `password` 变量的值不等于正确的密码 “secret”，循环就会继续执行。

```python
while password != "secret":
```

在循环体内，我们需要做以下几件事：
以下是循环体内需要执行的步骤列表：
1.  提示用户输入密码。
2.  获取用户的输入并存储到 `password` 变量中。
3.  判断输入的密码是否正确。
4.  根据判断结果输出相应的信息。

让我们将这些步骤转化为代码。在循环中，我们使用 `input` 函数获取用户输入。

```python
    password = input("Please, enter the password: ")
```

获取输入后，我们使用 `if` 语句进行判断。如果密码正确，则打印欢迎信息。

```python
    if password == "secret":
        print("Welcome.")
```

如果密码不正确，则需要提示用户输入有误，并请其再次尝试。随后，循环条件会再次被检查，由于 `password` 仍不等于 “secret”，循环将再次执行，重新提示用户输入。

```python
    else:
        print("Sorry, the password you entered is incorrect. Please try again.")
```

将以上所有部分组合起来，就构成了完整的密码验证程序。

## 代码示例与运行

以下是完整的程序代码：

```python
password = ""
while password != "secret":
    password = input("Please, enter the password: ")
    if password == "secret":
        print("Welcome.")
    else:
        print("Sorry, the password you entered is incorrect. Please try again.")
```

**程序运行逻辑**：
1.  程序启动，`password` 为空字符串，满足 `while` 循环条件。
2.  进入循环，提示用户输入。
3.  用户输入后，程序立即判断。
    *   若输入为 `”secret”`，则打印 `”Welcome.”`，循环条件不再满足，程序结束。
    *   若输入错误，则打印错误提示，循环继续，回到步骤2。

**注意事项**：此程序对密码的大小写敏感。输入 `”Secret”` 或 `”SECRET”` 都会被判定为错误密码。

## 总结 🎯

![](img/7808ea512767690c5ca8168bdd322f02_3.png)

本节课中我们一起学习了如何利用 `while` 循环构建一个交互式的密码验证程序。我们掌握了以下关键点：
*   使用 `while` 循环实现重复执行，直到满足特定条件。
*   使用 `input()` 函数获取用户输入。
*   使用 `if-else` 语句根据条件执行不同的代码分支。
*   理解了程序对字符串大小写的敏感性。

通过这个练习，你将 `while` 循环、条件判断和用户输入结合运用，解决了实际问题，这是编程中非常重要的基础技能。