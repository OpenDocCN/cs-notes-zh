# 008：函数作为对象 🐍

![](img/44fc4ecde02490e505a2bd8808a8b3ce_0.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_2.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_3.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_5.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_7.png)

在本节课中，我们将继续学习函数，并深入探讨如何将函数视为对象。我们将学习函数的作用域、环境以及如何将函数作为参数传递给其他函数。

![](img/44fc4ecde02490e505a2bd8808a8b3ce_9.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_11.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_13.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_14.png)

---

![](img/44fc4ecde02490e505a2bd8808a8b3ce_16.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_18.png)

## 函数定义与执行回顾

上一节我们介绍了函数的基本语法和动机。本节中，我们来看看函数定义的具体组成部分。

一个函数定义包含以下部分：
*   `def` 关键字：告诉Python我们正在定义一个函数。
*   函数名：我们为函数指定的名称。
*   参数列表：在括号内命名函数的所有输入。
*   冒号：标志着函数体的开始。
*   文档字符串（可选但推荐）：用三引号包裹的长注释，描述了函数的契约（输入、功能、输出）。
*   函数体：缩进的代码块，包含要执行的语句。
*   `return` 语句：结束函数执行，并将一个值传递回调用者。

**代码示例：判断偶数的函数**
```python
def is_even(i):
    """
    输入：整数 i
    返回：如果 i 是偶数则返回 True，否则返回 False
    """
    remainder = i % 2
    return remainder == 0
```

![](img/44fc4ecde02490e505a2bd8808a8b3ce_20.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_22.png)

所有函数都会返回一个值。如果函数体中没有显式的 `return` 语句，Python会在函数执行结束时自动返回 `None`。`None` 是 `NoneType` 类型的唯一值，通常用于表示“没有值”。

![](img/44fc4ecde02490e505a2bd8808a8b3ce_24.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_26.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_28.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_30.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_32.png)

---

![](img/44fc4ecde02490e505a2bd8808a8b3ce_34.png)

## `return` 与 `print` 的区别

理解 `return` 和 `print` 的区别至关重要。

以下是两者的核心区别：
*   **`return`**：仅能在函数内部使用。它结束函数执行，并将一个值传递回调用者。函数调用本身是一个表达式，其值就是返回的值。
*   **`print`**：可以在任何地方使用（函数内或函数外）。它将内容输出到控制台，但其本身不传递值给程序的其他部分。`print` 函数本身返回 `None`。

**关键点**：在函数内部打印一个值（使用 `print`）与返回一个值（使用 `return`）是两件不同的事。为了在其他代码中使用函数的计算结果，通常需要使用 `return`。

![](img/44fc4ecde02490e505a2bd8808a8b3ce_36.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_38.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_40.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_41.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_43.png)

---

![](img/44fc4ecde02490e505a2bd8808a8b3ce_45.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_47.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_48.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_50.png)

## 函数作用域与环境 🧠

![](img/44fc4ecde02490e505a2bd8808a8b3ce_52.png)

当进行函数调用时，Python会创建一个新的**环境**（或作用域）。这个环境与调用它的程序（全局环境）是分离的。

以下是理解环境的关键规则：
1.  **参数映射**：调用函数时，实参的值被映射到函数定义中的形参。
2.  **局部变量**：在函数内部创建的变量只存在于该函数的环境（局部作用域）中。
3.  **环境隔离**：不同环境中的变量，即使同名，也互不干扰。
4.  **环境生命周期**：函数执行完毕并返回后，其对应的环境就会消失，其中的所有局部变量也随之销毁。
5.  **变量查找**：如果函数内部引用了一个变量，Python会首先在本地环境中查找。如果找不到，它会向外层环境（例如全局环境）查找该变量。但是，**函数不能直接修改外层作用域的变量**（除非使用 `global` 关键字，但初学者应避免使用）。

**示例：作用域演示**
```python
def func_a(y):
    x = 1          # 在 func_a 的作用域内创建局部变量 x
    x = x + 1
    print(x)       # 打印 2
    # 函数结束，返回 None，局部变量 x 和 y 消失

x = 5              # 在全局作用域创建变量 x
func_a(x)          # 调用函数，传递 x 的值 5
print(x)           # 打印全局变量 x，仍然是 5
```
输出将是 `2` 和 `5`，证明了局部变量 `x` 和全局变量 `x` 是独立的。

---

## 函数作为对象 🎯

在Python中，**函数也是对象**。这意味着函数名实际上是一个指向包含代码的函数对象的变量。

因为函数是对象，所以我们可以：
1.  将函数赋值给另一个变量。
2.  将函数作为参数传递给另一个函数。
3.  从一个函数中返回另一个函数。

**示例：函数赋值**
```python
def is_even(i):
    return i % 2 == 0

![](img/44fc4ecde02490e505a2bd8808a8b3ce_54.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_55.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_57.png)

my_func = is_even  # 将 is_even 函数对象赋值给变量 my_func
# 现在 my_func 和 is_even 指向同一个函数
a = my_func(3)     # 返回 False
b = is_even(4)     # 返回 True
```

![](img/44fc4ecde02490e505a2bd8808a8b3ce_59.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_61.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_63.png)

---

![](img/44fc4ecde02490e505a2bd8808a8b3ce_65.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_67.png)

## 将函数作为参数传递

![](img/44fc4ecde02490e505a2bd8808a8b3ce_69.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_71.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_73.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_75.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_77.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_79.png)

既然函数可以作为对象传递，我们就可以编写接收其他函数作为参数的“高阶函数”。这极大地增加了代码的灵活性和复用性。

![](img/44fc4ecde02490e505a2bd8808a8b3ce_81.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_83.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_85.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_87.png)

**示例：通用计算器函数**
```python
def add(a, b):
    return a + b

![](img/44fc4ecde02490e505a2bd8808a8b3ce_89.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_91.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_93.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_95.png)

def div(a, b):
    print(f"Dividing {a} by {b}")
    return a / b if b != 0 else None

![](img/44fc4ecde02490e505a2bd8808a8b3ce_97.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_99.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_101.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_103.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_105.png)

def calc(op, x, y):
    """ op 是一个函数，接受两个参数 """
    return op(x, y)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_107.png)

result1 = calc(add, 2, 3)   # 调用 calc，传入 add 函数，返回 5
result2 = calc(div, 6, 2)   # 调用 calc，传入 div 函数，打印信息并返回 3.0
```

**练习：编写一个应用条件的函数**

![](img/44fc4ecde02490e505a2bd8808a8b3ce_109.png)

让我们编写一个函数 `apply_criteria`，它接收一个判断函数 `criteria` 和一个整数 `n`，返回从 `0` 到 `n`（包含）之间有多少个数字满足 `criteria` 函数。

![](img/44fc4ecde02490e505a2bd8808a8b3ce_111.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_113.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_115.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_117.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_119.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_121.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_123.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_125.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_127.png)

```python
def apply_criteria(criteria, n):
    """
    参数:
        criteria: 一个函数，接受一个整数，返回布尔值。
        n: 一个整数。
    返回:
        满足 criteria 函数的数字的个数 (从 0 到 n)。
    """
    count = 0
    for i in range(n + 1):          # 遍历 0 到 n
        if criteria(i):             # 调用传入的判断函数
            count += 1
    return count

![](img/44fc4ecde02490e505a2bd8808a8b3ce_129.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_131.png)

# 使用示例
def is_even(num):
    return num % 2 == 0

![](img/44fc4ecde02490e505a2bd8808a8b3ce_133.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_135.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_137.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_139.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_141.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_143.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_145.png)

def equals_five(num):
    return num == 5

![](img/44fc4ecde02490e505a2bd8808a8b3ce_147.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_149.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_151.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_153.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_154.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_156.png)

print(apply_criteria(is_even, 10))   # 输出 6 (0,2,4,6,8,10)
print(apply_criteria(equals_five, 10)) # 输出 1 (只有5)
```

![](img/44fc4ecde02490e505a2bd8808a8b3ce_158.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_160.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_162.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_164.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_166.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_167.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_168.png)

这个 `apply_criteria` 函数非常强大，它可以与任何符合签名（接受整数，返回布尔值）的函数一起工作，实现了逻辑与数据的分离。

![](img/44fc4ecde02490e505a2bd8808a8b3ce_170.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_171.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_173.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_175.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_177.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_178.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_180.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_182.png)

---

![](img/44fc4ecde02490e505a2bd8808a8b3ce_184.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_186.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_188.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_190.png)

## 总结 📚

本节课中我们一起学习了：
1.  函数中 `return` 与 `print` 的根本区别。
2.  **函数作用域和环境**的概念：每次函数调用都会创建独立的环境，变量在其中生命周期有限且互不干扰。
3.  **函数作为对象**的特性：函数可以像其他数据（如整数、字符串）一样被赋值、传递和返回。
4.  如何编写**高阶函数**，即接收其他函数作为参数的函数，这能极大提升代码的通用性和可复用性。

![](img/44fc4ecde02490e505a2bd8808a8b3ce_192.png)

![](img/44fc4ecde02490e505a2bd8808a8b3ce_194.png)

理解这些概念是编写模块化、清晰且强大代码的关键。在接下来的学习和问题集中，你会经常运用这些知识。