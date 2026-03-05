# Python 函数剖析实验室：P64：函数对象与作用域详解

![](img/60c13f72707c907d0fbb45b67db702f7_0.png)

在本节课中，我们将深入探讨 Python 函数的内部机制。我们将学习函数如何被 Python 视为对象，以及函数对象的各种属性如何决定其行为，例如参数处理和作用域规则。理解这些概念将帮助你编写更高效、更健壮的代码。

## 函数即对象 🧱

上一节我们介绍了课程概述，本节中我们来看看 Python 如何看待函数。在 Python 中，当你使用 `def` 关键字定义一个函数时，实际上发生了两件事：创建了一个函数对象，然后将该对象赋值给一个变量名。

例如，以下代码定义了变量和一个函数：
```python
x = [10, 20, 30]
d = {'a': 1, 'b': 2, 'c': 3}
def hello(name):
    return f'Hello {name}!'
```
Python 将 `x`、`d` 和 `hello` 都视为全局变量，只是它们引用的对象类型不同。`hello` 变量引用的是一个函数对象。

将函数视为对象（名词）而不仅仅是可执行的代码（动词），为我们带来了灵活性。以下是函数作为对象的一些特性：

*   **函数可以被赋值给其他变量**：`hi = hello`，现在 `hi` 和 `hello` 引用同一个函数对象。
*   **函数可以作为参数传递**：`print(hello(‘world’))` 中，`hello` 作为动词执行，而其返回值作为参数传递给 `print`。
*   **函数对象拥有属性**：像所有 Python 对象一样，函数对象也有属性。例如，`dir(hello)` 可以列出其所有属性。

## 函数的“心脏”：`__code__` 对象 💓

上一节我们了解了函数作为对象的基本概念，本节中我们来看看函数对象的核心属性。函数对象上最重要的属性是 `__code__` 对象，它包含了函数的“心脏、灵魂和大脑”——即编译后的字节码和各种元数据。

Python 不是纯粹的解释型语言。当我们定义一个函数时，它会被编译成一种称为“字节码”的中间形式，并存储在 `__code__` 对象中。执行函数时，Python 虚拟机就运行这些字节码。

`__code__` 对象本身也有属性，这些属性决定了函数如何工作。例如，Python 如何知道函数需要多少个参数？答案就在 `__code__` 的属性中。

以下是 `__code__` 对象中与参数相关的关键属性：

*   **`co_argcount`**：表示函数接收的位置参数的数量（不包括 `*args` 和 `**kwargs`）。
*   **`co_varnames`**：一个包含函数所有局部变量名称的元组，其中前 `co_argcount` 个元素就是参数名。
*   **`co_flags`**：一个整数，其二进制位用于标记函数的特殊特性，例如是否包含 `*args`、`**kwargs`，是否是生成器函数等。可以通过位运算进行检查，例如 `hello.__code__.co_flags & 0x04` 检查是否有 `*args`。

当调用函数时，Python 会检查传入的参数数量是否与 `co_argcount` 匹配。如果不匹配，它会利用 `co_varnames` 中的信息生成清晰的错误信息，例如“`hello()` missing 1 required positional argument: ‘name’”。

## 处理特殊参数：默认值、`*args` 与 `**kwargs` 🧩

上一节我们探讨了函数如何通过 `__code__` 跟踪基本参数，本节中我们来看看更复杂的参数类型。函数可以定义默认参数、接收任意数量位置参数的 `*args` 和接收任意数量关键字参数的 `**kwargs`。

对于默认参数，信息存储在函数对象本身的一个属性中：

*   **`__defaults__`**：一个元组，包含了所有位置参数的默认值。如果没有默认值，则为 `None`。

一个常见的陷阱是使用可变对象（如列表）作为默认值。因为 `__defaults__` 中的默认值在函数定义时就被创建并固定了，后续所有调用都会共享同一个可变对象。

```python
def add_one(x=[]): # 危险！默认值是一个在定义时创建的列表对象
    x.append(1)
    return x

print(add_one()) # 输出：[1]
print(add_one()) # 输出：[1, 1] 而不是预期的 [1]
```

**结论：永远不要使用可变对象作为函数参数的默认值。**

对于 `*args` 和 `**kwargs`，Python 通过检查 `__code__.co_flags` 中的相应位来判断函数是否接受它们。此外，还有一个属性专门记录仅限关键字参数（keyword-only arguments）的数量：

*   **`__code__.co_kwonlyargcount`**：表示仅限关键字参数的数量。

## 作用域规则与变量查找 🔍

上一节我们讨论了函数的参数，本节中我们来看看函数内部如何查找变量，即作用域规则。Python 遵循 LEGB 规则查找变量：Local（局部）-> Enclosing（闭包）-> Global（全局）-> Built-in（内置）。

Python 在编译函数时（即执行 `def` 语句时），就会确定哪些变量是局部变量。这个信息记录在 `__code__.co_varnames` 中。

考虑以下代码：
```python
x = 100
def func():
    print(x) # 这行代码会让 Python 认为 x 是局部变量吗？
    x = 200

func() # 会引发 UnboundLocalError
```
运行 `func()` 会得到 `UnboundLocalError: local variable ‘x’ referenced before assignment`。这是因为函数体内存在 `x = 200` 这个赋值语句，Python 在编译阶段就将 `x` 标记为局部变量。当执行到 `print(x)` 时，Python 在局部作用域查找 `x`，发现它尚未被赋值，因此报错。

如果需要修改函数外部的变量，可以使用 `global` 或 `nonlocal` 声明：

*   **`global`**：声明变量来自全局作用域。
*   **`nonlocal`**：声明变量来自外层（非全局）作用域，用于嵌套函数。

```python
def outer():
    total = 0
    def inner(x):
        nonlocal total # 声明 total 来自外层作用域
        total += x
        return total
    return inner

counter = outer()
print(counter(10)) # 输出：10
print(counter(20)) # 输出：30
```
`nonlocal` 使得内部函数 `inner` 可以修改外部函数 `outer` 的局部变量 `total`。Python 通过一种称为“闭包”的机制来实现这一点，外部函数的变量会被“捕获”到内部函数对象的 `__closure__` 属性中。

## 总结 📚

本节课中我们一起学习了 Python 函数的内部工作原理。

首先，我们明确了 `def` 语句的双重作用：创建函数对象并将其赋值给一个名称。

其次，我们深入探讨了函数对象的各种属性，特别是 `__code__` 对象，它存储了决定函数行为的核心信息，如参数数量（`co_argcount`）、参数名（`co_varnames`）、特殊标志（`co_flags`）以及编译后的字节码。

接着，我们分析了如何使用 `__defaults__` 处理默认参数，并强调了避免使用可变默认值的重要性。我们还了解了 Python 如何通过 `co_flags` 和 `co_kwonlyargcount` 来支持 `*args`、`**kwargs` 和仅限关键字参数。

![](img/60c13f72707c907d0fbb45b67db702f7_2.png)

最后，我们研究了 Python 的作用域规则（LEGB）和变量查找机制。理解了 Python 如何在编译时确定局部变量，以及如何使用 `global` 和 `nonlocal` 声明来跨作用域修改变量。这些知识揭示了那些我们习以为常的函数行为背后的精确逻辑。