Python与Java编程入门：1-2：编程演示 - 创建成绩转换函数 🎯

在本节课中，我们将学习如何将一个简单的成绩转换程序重构为使用用户自定义函数。我们将从一段接收用户输入并打印对应字母成绩的代码开始，逐步将其转换为更模块化、可重用的函数形式。

---

上一节我们回顾了基础的成绩转换逻辑。本节中，我们来看看如何将这些代码封装到一个用户自定义函数中。

首先，我们有一段原始代码。这段代码的功能是：提示用户输入一个数字成绩，将其转换为整数，然后根据数值范围打印出对应的字母成绩。

以下是原始代码的逻辑步骤：
1.  获取用户的数字成绩输入。
2.  将输入值转换为整数。
3.  测试数字的范围并打印相应的字母成绩。

现在，我们将所有这些代码放入一个用户自定义函数中。

![](img/e85eb83029bbe1f03dc552ee38aabc50_1.png)

```python
def numeric_to_letter_grade():
    grade = input("Enter a numeric grade: ")
    grade = int(grade)

    if grade >= 90:
        print("A")
    elif grade >= 80:
        print("B")
    elif grade >= 70:
        print("C")
    elif grade >= 60:
        print("D")
    else:
        print("F")
```

![](img/e85eb83029bbe1f03dc552ee38aabc50_3.png)

定义好函数后，我们可以通过调用它来运行函数体内的所有代码。

```python
numeric_to_letter_grade()
```

运行这段代码，输入 `87`，程序会输出 `B`。这里，我们调用了上面定义的 `numeric_to_letter_grade` 函数，它执行了函数体内的所有逻辑。

---

上面我们创建了一个无参数的函数。另一种更灵活的方法是定义一个带有参数的函数。

让我们修改函数，使其接受一个名为 `grade` 的参数，并移除函数内部获取用户输入的代码。

```python
def numeric_to_letter_grade(grade):
    if grade >= 90:
        print("A")
    elif grade >= 80:
        print("B")
    elif grade >= 70:
        print("C")
    elif grade >= 60:
        print("D")
    else:
        print("F")
```

现在，我们可以向函数传递一个具体的数值来转换为字母成绩。例如，我们可以这样传递数值 `87`：

```python
numeric_to_letter_grade(87)
```

运行这个函数调用，会得到输出 `B`。

我们也可以结合用户输入来使用这个函数。以下是具体做法：

```python
# 获取用户输入
user_grade = input("Enter a numeric grade: ")
user_grade = int(user_grade)

# 将输入值作为参数传递给函数
numeric_to_letter_grade(user_grade)
```

再次运行代码，输入 `92`，程序会输出 `A`。在这个过程中，我们获取用户输入，将其转换为整数，然后将这个值作为**参数**传递给函数。函数执行时，会接收这个给定的**参数**，并运行函数体内的代码进行判断和输出。

![](img/e85eb83029bbe1f03dc552ee38aabc50_5.png)

---

![](img/e85eb83029bbe1f03dc552ee38aabc50_6.png)

本节课中我们一起学习了如何将过程式代码重构为函数式代码。我们首先创建了一个无参数函数来封装整个流程，然后将其改进为带参数的函数，使逻辑更清晰且更具复用性。通过定义函数，我们可以将特定功能的代码块模块化，便于多次调用和代码管理。