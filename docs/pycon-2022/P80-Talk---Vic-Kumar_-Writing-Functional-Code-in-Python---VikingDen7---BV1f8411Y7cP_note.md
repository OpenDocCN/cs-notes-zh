# Python函数式编程：P80：用Python编写函数式代码

![](img/74053c9ae9782a56d9156bf3f73c215e_1.png)

![](img/74053c9ae9782a56d9156bf3f73c215e_2.png)

## 概述
在本节课中，我们将学习函数式编程的核心概念，并了解如何在Python中应用这些思想。我们将探讨纯函数、副作用、引用透明性等关键理念，并通过具体的代码示例学习如何使用高阶函数和特定的类（如`Option`、`Try`、`Future`）来编写更清晰、更易于推理的代码。

---

## 什么是函数式编程？
在过去的五到六年里，许多新兴技术都融入了函数式编程的思想。例如，JavaScript中的React.js，.NET中的F#，JVM生态中的Scala和Kotlin，以及iOS开发中的Swift。此外，还有Haskell、OCaml等更传统的函数式语言。

函数式编程的理念非常简单，但影响深远。其核心是施加一个约束：**尝试仅使用纯函数来编写代码**。

### 什么是纯函数？
纯函数是指**没有副作用**的函数。

### 什么是副作用？
副作用是指任何不属于纯粹计算的行为。例如：
*   修改变量的状态。
*   就地修改数据结构。
*   在代码中抛出异常。
*   处理任何类型的输入/输出（如控制台、网络操作）。

另一种理解方式是：函数有输入和输出。如果函数内部执行了任何与输入或输出没有直接、明确关系的操作，那么根据定义，这就是副作用。因为这些操作并未在函数的签名中明确声明。

纯函数具有**引用透明性**的特性。这意味着，在程序中，任何对纯函数的调用都可以用其返回值替换，而不会改变程序的行为。

---

## 从可变状态到不可变状态
上一节我们介绍了纯函数和副作用的概念。本节中，我们来看看一个具体的例子，理解可变状态如何导致代码不纯，以及如何改进。

以下是一个对数字列表求和的函数，它使用了可变状态：

```python
def add_numbers_one(numbers):
    sum = 0
    for n in numbers:
        sum = sum + n
    return sum
```

这个函数看起来简单，但它修改了变量`sum`的状态，因此不是纯函数。我们可以通过“替换模型”来验证其引用透明性：如果将`sum`替换为其初始值`0`，函数的行为会改变，结果不正确。

此外，可变状态`sum`在多线程环境下会引发并发问题，需要额外的锁机制。

### 如何消除可变状态？
以下是两种消除可变状态的方法：

**1. 使用递归**
```python
def add_numbers_two(numbers):
    if len(numbers) == 1:
        return numbers[0]
    else:
        return numbers[0] + add_numbers_two(numbers[1:])
```
这个函数内部没有可变状态，是引用透明的。

**2. 使用高阶函数**
高阶函数是指接收函数作为参数，或返回函数作为结果的函数。
```python
from functools import reduce

def add_numbers_three(numbers):
    return reduce(lambda x, y: x + y, numbers)
```
`reduce`函数抽象了遍历和累积的过程，避免了显式的状态变更。`add_numbers_two`和`add_numbers_three`都是纯函数。

---

## 使用`Option`类处理空值
我们接受了使用高阶函数进行抽象的想法。现在，我们引入一些类来封装常见的行为模式。本节将介绍`Option`类，它用于优雅地处理可能为`None`的值。

`Option`类是一个抽象基类，有两个具体实现：`Some`（封装一个值）和`Empty`（表示空值）。

假设我们有一个嵌套的数据模型：
```python
from dataclasses import dataclass

@dataclass
class Name:
    first_name: str
    last_name: str

@dataclass
class Contact:
    name: Name

@dataclass
class Person:
    contact1: Contact
```

任务：给定一个`Person`对象，安全地获取其`contact1`的`first_name`。

**传统方式（命令式）**：
```python
def get_first_name_imperative(person: Person) -> str:
    if person is not None:
        contact1 = person.contact1
        if contact1 is not None:
            name = contact1.name
            if name is not None:
                return name.first_name
    return None
```
这种方式需要多层嵌套的`if`检查，代码冗长且容易出错。

**使用`Option`类（函数式）**：
首先，我们需要将数据访问函数改为返回`Option`类型。
```python
# 假设有库提供了Option, Some, Empty
def get_contact(person: Person) -> Option[Contact]:
    return Some(person.contact1) if person.contact1 is not None else Empty()

def get_name(contact: Contact) -> Option[Name]:
    return Some(contact.name) if contact.name is not None else Empty()

def get_first_name_func(name: Name) -> Option[str]:
    return Some(name.first_name) if name.first_name is not None else Empty()
```

然后，使用`flat_map`进行链式调用：
```python
def get_first_name_func_person(person: Person) -> Option[str]:
    return (
        Some(person)
        .flat_map(get_contact)
        .flat_map(get_name)
        .flat_map(get_first_name_func)
    )
```
`flat_map`操作负责组合函数：将一个函数的输出（`Option`类型）作为下一个函数的输入。如果链中任何一步得到`Empty`，整个链条会短路并最终返回`Empty`。

**优势**：
1.  **无分支逻辑**：代码从左到右阅读，清晰流畅。
2.  **显式类型**：函数签名明确告知返回值可能是`Option[str]`，调用者必须处理空值情况（例如使用`get_or_else`提供默认值）。
3.  **抽象通用模式**：将空值检查的逻辑抽象到了`Option`类中。

---

## 使用`Try`类处理异常
上一节我们使用`Option`处理了空值。本节中，我们来看看如何使用类似的模式——`Try`类来处理异常，这是另一种常见的副作用。

`Try`类也是一个抽象基类，有两个子类：`Success`（封装成功结果）和`Failure`（封装抛出的异常）。

**示例**：解析JSON字符串并提取信息。
```python
import json

def parse_name(data: dict) -> Name:
    # 如果字典中缺少键，会抛出KeyError
    return Name(first_name=data[“first_name”], last_name=data[“last_name”])

def parse_person(json_str: str) -> str:
    data = json.loads(json_str)
    contact_data = data[“contacts”][0]
    name = parse_name(contact_data) # 可能抛出异常
    return name.first_name
```
`parse_name`的函数签名是`dict -> Name`，但它可能抛出`KeyError`，这个信息并未在签名中体现，代码不够明确。

**使用`Try`类重写**：
```python
def parse_name_safe(data: dict) -> Try[Name]:
    return Try.of(lambda: Name(first_name=data[“first_name”], last_name=data[“last_name”]))

def parse_person_safe(json_str: str) -> Try[str]:
    return (
        Try.of(lambda: json.loads(json_str))
        .flat_map(lambda data: Try.of(lambda: data[“contacts”][0]))
        .flat_map(parse_name_safe)
        .map(lambda name: name.first_name)
    )

# 处理失败情况
result = parse_person_safe(invalid_json_str)
first_name = result.or_else_supply(lambda: “Unknown”)
```
**优势**：
1.  **显式错误处理**：函数签名`dict -> Try[Name]`明确告知调用者此操作可能失败。
2.  **链式组合**：与`Option`类似，可以使用`flat_map`和`map`安全地组合可能失败的操作。
3.  **集中处理**：可以在链条末尾统一处理成功或失败的情况（如`or_else_supply`）。

---

## 使用`Future`类处理并发
我们看到了`Option`和`Try`如何封装同步计算中的不确定性。本节我们将概念延伸到异步计算，使用`Future`（或`Promise`）来处理并发。

`Future`代表一个尚未完成的异步计算的结果。计算完成后，其结果表现为一个`Try`（要么是`Success`，要么是`Failure`）。

**简单示例**：在新线程中运行一个耗时函数。
```python
from concurrent.futures import ThreadPoolExecutor
import time

def long_running_task() -> int:
    time.sleep(3)
    return 100

# 创建Future
with ThreadPoolExecutor() as executor:
    future = executor.submit(long_running_task)
    # 可以继续做其他事情...
    result = future.result() # 阻塞直到获取结果
    print(result + 1) # 输出 101
```

**组合多个Future**：
我们想并行运行两个任务，并在它们都完成后合并结果。
```python
def task1() -> int:
    time.sleep(3)
    return 100

def task2() -> int:
    time.sleep(5)
    return 50

with ThreadPoolExecutor() as executor:
    future1 = executor.submit(task1)
    future2 = executor.submit(task2)

    # 使用回调处理组合结果
    combined_future = future1.flat_map(lambda a: future2.map(lambda b: a + b))
    # 添加回调检查结果
    combined_future.add_done_callback(lambda f: print(f“Result: {f.result()}”))
```
两个任务并行执行（总耗时约5秒，而非8秒），结果正确合并为150。

**处理Future列表**：当需要组合多个`Future`时，可以使用类似`future.sequence`（在Scala中）或`asyncio.gather`（在Python asyncio中）的函数，将一个`Future`列表转换为一个包含结果列表的`Future`。
```python
# 概念性代码，展示思想
futures = [executor.submit(task) for task in task_list]
single_future_of_list = sequence(futures) # 返回 Future[List[Result]]
```
这样，我们可以方便地检查整个批量操作是全部成功还是部分失败。

---

## 总结
本节课中，我们一起学习了函数式编程在Python中的应用。核心要点如下：

1.  **追求纯度**：副作用（如可变状态、异常、I/O）会使代码难以推理。纯函数和引用透明性让逻辑更清晰、更可预测。
2.  **拥抱抽象**：使用高阶函数（如`map`、`reduce`、`flat_map`）和特定的类型类（如`Option`、`Try`、`Future`）来抽象并封装常见的副作用模式。
3.  **声明式风格**：通过链式调用（流式API），将程序构建为“输入 -> 一系列转换 -> 输出”的管道，代码更贴近自然语言的阅读顺序（从左到右），减少了嵌套和分支。
4.  **显式优于隐式**：让可能的失败（空值、异常）在类型签名中显式体现，迫使调用者进行处理，提高了代码的健壮性。

![](img/74053c9ae9782a56d9156bf3f73c215e_4.png)

![](img/74053c9ae9782a56d9156bf3f73c215e_6.png)

函数式编程并非要完全取代命令式编程，而是提供了一套强大的工具和思维方式，帮助我们编写出更简洁、更模块化、更易于测试和维护的代码。