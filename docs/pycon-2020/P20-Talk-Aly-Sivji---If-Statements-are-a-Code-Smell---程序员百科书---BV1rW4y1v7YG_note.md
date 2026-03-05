# 代码重构：P20：如果语句是一种代码异味 🚨

![](img/62a307e40635ec771b228bfe8aa8073b_0.png)

在本节课中，我们将学习如何识别代码中的“代码异味”，特别是与 `if` 语句相关的几种常见模式。我们将探讨这些模式为何会使代码难以理解和维护，并学习如何通过重构，例如使用多态性，来改善代码设计，使其更清晰、更易于测试和扩展。

---

## 概述

`if` 语句是编程语言的基本元素，它允许我们根据条件控制程序的执行流程。虽然功能强大，但过度或不当使用 `if` 语句会导致代码变得复杂、难以阅读和修改。这种复杂性被称为“代码异味”，它暗示着代码设计可能存在问题。本节课将介绍三种与 `if` 语句相关的代码异味，并提供重构策略。

---

## 什么是 `if` 语句？

`if` 语句是编程语言的元素，允许我们控制执行哪些语句。通常，程序从上到下逐行执行。`if` 语句让我们能够在条件为真时执行一段代码，条件为假时则跳过该段代码。

**代码示例：**
```python
if today == user_birthday:
    print("Happy Birthday!")
```
如果 `today` 等于 `user_birthday`，则打印生日祝福；否则，跳过打印，继续执行后续代码。

通过串联一系列 `if` 语句，我们可以完成各种任务。然而，如果代码中包含过多的 `if` 语句，会使逻辑难以遵循，也更难修改。

---

## 代码异味：难以理解和修改的代码

难以理解的代码可能表现为“意大利面逻辑”，即需要上下滚动或跨多个模块查看才能理清执行流程。它也可能是冗长的函数，混杂了多种不同类型的操作，或者相关功能没有逻辑地分组在一起。糟糕的变量名、函数名，或过度使用线性流程而非高级抽象，都会导致代码难以理解。

难以修改的代码意味着，当我们需要进行更改时，必须触及代码库的许多不同部分。添加新功能时，可能需要修改大量现有代码。代码中散布的重复逻辑也使得修改时容易遗漏某些需要更新的地方。缺乏测试的代码尤其难以修改，因为我们无法确保更改不会破坏现有功能。

这种难以理解和修改的代码，我们称之为“代码异味”。它可能表明设计存在问题，但并非绝对。我们的目标是：如果逻辑难以理解，就尝试简化它；如果修改耗时过长，就调整设计以提高效率。

---

## 代码异味一：复杂的复合 `if` 语句

上一节我们介绍了代码异味的概念，本节中我们来看看第一种具体的异味：复杂的复合 `if` 语句。

单个 `if` 语句通常易于阅读。但当条件变得复杂，尤其是包含多个逻辑运算符（如 `and`、`or`）时，理解其意图就变得困难。

**重构建议：将复杂条件重构为具有描述性名称的布尔变量或函数。**

例如，对于一个包含两个条件的 `if` 语句：
```python
if user.is_active and user.has_valid_subscription:
    # do something
```
可以重构为：
```python
is_eligible_user = user.is_active and user.has_valid_subscription
if is_eligible_user:
    # do something
```
如果这个复杂条件在代码中多次使用，可以将其重构为一个函数：
```python
def is_eligible_user(user):
    return user.is_active and user.has_valid_subscription

if is_eligible_user(user):
    # do something
```
这样做提高了代码的可读性和可重用性。

---

## 代码异味二：嵌套的 `if` 语句（箭头代码）

接下来，我们探讨第二种代码异味：深层嵌套的 `if` 语句，它会使代码形成向右延伸的“箭头”形状。

箭头代码存在几个问题。首先，它具有很高的“圈复杂度”，即代码中不同执行路径的数量。高圈复杂度的代码难以理解，也更难测试。其次，深层嵌套会浪费大量缩进字符，限制每行代码的有效表达空间。

**重构技巧：展平箭头代码，核心思想是尽早返回。**

让我们通过一个案例来理解。假设我们有一个查询自行车共享站点信息的仪表板代码：

```python
import requests

def get_bike_availability(station_id):
    response = requests.get(f"api_url/{station_id}")
    if response.status_code == 200:
        stations = response.json()
        for station in stations:
            if station[‘id‘] == station_id:
                if station[‘bikes‘] <= 3:
                    return "Bikes are low!"
                else:
                    return "Bikes are available."
        raise Exception("Station not found")
    else:
        raise Exception("API request failed")
```
这段代码嵌套了三层，形成了箭头形状。

以下是重构后的版本，使用“保护子句”尽早返回，从而展平了嵌套结构：

```python
import requests

def get_bike_availability(station_id):
    response = requests.get(f"api_url/{station_id}")
    # 保护子句：尽早处理错误情况并返回
    if response.status_code != 200:
        raise Exception("API request failed")

    stations = response.json()
    for station in stations:
        if station[‘id‘] == station_id:
            # 另一个保护子句
            if station[‘bikes‘] <= 3:
                return "Bikes are low!"
            # 主逻辑变得清晰直接
            return "Bikes are available."
    # 最终的错误情况
    raise Exception("Station not found")
```
通过将正面检查转换为负面检查并提前返回，我们消除了深层嵌套，使主逻辑更加清晰。

---

## 代码异味三：散布各处的重复 `if` 语句

最后，我们来看第三种代码异味：相同的 `if` 语句检查遍布整个代码库。

前两种异味相对容易识别和修复。而这种异味虽然也容易发现，但在设计解决方案前，需要对问题有更深入的理解。如果这段代码永远不需要修改，问题可能不大。但如果需要阅读或修改它，探索一种不同的抽象（如多态性）可能更有意义。

**案例研究：GitHub 活动摘要机器人**

假设我们有一个为 GitHub 用户生成每日活动摘要的机器人。最初，我们只关心两种事件：推送代码和加星标仓库。

一个简单的实现可能包含一系列 `if-elif` 语句来处理不同事件类型：

```python
def generate_summary(events):
    summary = ""
    for event in events:
        if event[‘type‘] == ‘PushEvent‘:
            summary += f"Pushed {len(event[‘payload‘][‘commits‘])} commits.\n"
        elif event[‘type‘] == ‘WatchEvent‘:
            summary += "Starred a repository.\n"
    return summary
```
当需要添加对新事件类型（如新开的拉取请求）的支持时，我们只需添加一个 `elif` 块。起初这很简单。

**问题浮现：**
然而，随着支持的事件类型增多，这个函数会变得越来越长，越来越难以阅读和维护。更严重的是，每次添加新功能时：
1.  需要修改这个核心函数。
2.  可能需要修改已有的测试，以确保新功能不会意外影响旧逻辑。
3.  测试这个函数会变得复杂，因为它承担了过多不同类型的职责。

如果你发现添加新功能需要修改多个地方的代码或已有测试，那么你的代码中很可能存在这种异味。

---

## 重构策略：使用多态性替代条件逻辑

面对散布的重复条件逻辑，我们可以运用面向对象编程中的“多态性”来进行重构。

**面向对象编程（OOP）简介：**
OOP 是一种基于“对象”的编程范式。对象将数据和行为捆绑在一起。
*   **类**：创建对象的模板（像饼干模具）。
*   **对象**：类的实例（像压出的饼干）。
*   **四大支柱**：
    1.  **封装**：将数据和行为捆绑在对象内，隐藏内部细节。
    2.  **抽象**：隐藏对象内部的复杂性，只暴露简单的接口。
    3.  **继承**：子类可以继承父类的数据和行为，并可以覆盖或扩展它们，用于消除冗余代码。
    4.  **多态性**：为不同类型的对象提供相同的接口，但具体行为由对象类型决定。

**多态性的力量：**
在过程式编程中，我们使用 `if` 语句来选择执行哪段代码。在 OOP 中，我们可以将条件逻辑“嵌入”到对象的结构中。当代码运行时，对象的类型自动决定了执行哪种行为。

**一个简单例子：**

```python
class Animal:
    def speak(self):
        raise NotImplementedError("Subclass must implement this method")

class Dog(Animal):
    def speak(self):
        return "Woof!"

class Cat(Animal):
    def speak(self):
        return "Meow!"

# 使用多态性
animals = [Dog(), Cat()]
for animal in animals:
    print(animal.speak()) # 输出: Woof! Meow!
```
在这里，`animal.speak()` 的调用根据具体对象类型（`Dog` 或 `Cat`）产生不同行为，无需 `if` 语句检查类型。

---

## 将案例重构为多态性设计

让我们将 GitHub 摘要机器人的案例重构为使用多态性。

**步骤 1：识别重复的条件块**
在我们的函数中，条件块根据事件类型匹配事件并生成摘要文本。

**步骤 2：创建基类来建模问题**
我们创建一个 `EventList` 基类，它定义了接口。
```python
class EventList:
    def __init__(self):
        self.events = []

    def add_event(self, event):
        self.events.append(event)

    def matches(self, event):
        """检查给定事件是否属于此类事件"""
        raise NotImplementedError

    def generate_summary(self):
        """为此类事件生成摘要文本"""
        raise NotImplementedError
```

**步骤 3：为每种事件类型创建子类**
每个子类实现具体的 `matches` 和 `generate_summary` 逻辑。
```python
class PushEventList(EventList):
    def matches(self, event):
        return event[‘type‘] == ‘PushEvent‘

    def generate_summary(self):
        count = sum(len(e[‘payload‘][‘commits‘]) for e in self.events)
        return f"Pushed {count} commits."

class WatchEventList(EventList):
    def matches(self, event):
        return event[‘type‘] == ‘WatchEvent‘

    def generate_summary(self):
        return f"Starred {len(self.events)} repositories."
```

**步骤 4：创建驱动类来协调流程**
这个类负责将事件分类到各自的 `EventList` 子类中，并生成总摘要。
```python
class GitHubSummaryGenerator:
    def __init__(self, event_types): # event_types 是 EventList 子类的列表
        self.event_types = event_types
        # 为每种类型初始化一个空列表
        for et in self.event_types:
            et.events = []

    def categorize_events(self, all_events):
        for event in all_events:
            for event_type in self.event_types:
                if event_type.matches(event): # 这里有一个 if 语句
                    event_type.add_event(event)
                    break # 找到匹配类型后跳出内层循环

    def generate_summary(self):
        summary = ""
        for event_type in self.event_types:
            if event_type.events: # 这里有一个 if 语句
                summary += event_type.generate_summary() + "\n"
        return summary.strip()
```

**步骤 5：更新主函数使用新设计**
```python
def generate_github_summary(events):
    # 定义我们关心的事件类型
    event_handlers = [PushEventList(), WatchEventList()]
    generator = GitHubSummaryGenerator(event_handlers)
    generator.categorize_events(events)
    return generator.generate_summary()
```

**添加新功能变得简单：**
现在，要支持新的“拉取请求”事件，我们只需：
1.  创建一个新的 `PROpenedEventList` 子类。
2.  将其添加到 `event_handlers` 列表中。

无需修改现有的 `PushEventList`、`WatchEventList` 类或 `GitHubSummaryGenerator` 的核心逻辑。测试也变得更容易，因为每个类职责单一，可以独立测试。

---

## 注意事项与权衡

虽然多态性是强大的工具，但并非银弹。引入类层次结构增加了设计的复杂性。新人需要理解这些类和它们的关系，而不是直接阅读线性逻辑。

**何时重构？遵循“三次法则”：**
1.  第一次做某事：直接完成即可。
2.  第二次做类似的事：感到重复的痛楚，可以复制一次代码，问题不大。
3.  第三次做类似的事：是时候停下来，寻找一个更好的抽象了。

**组合优于继承：**
过度深的继承层次会带来耦合和僵化。很多时候，“组合”（即一个对象拥有其他对象的功能）比“继承”更灵活。有时，甚至复制粘贴代码也比使用一个错误的抽象要好。

重构的前提是拥有可靠的测试套件，以确保重构不会破坏现有功能。

---

## 总结

在本节课中，我们一起学习了 `if` 语句作为代码异味的几种常见形式：
1.  **复杂的复合条件**：通过提取到布尔变量或函数来简化。
2.  **深层嵌套的箭头代码**：通过使用保护子句尽早返回来展平。
3.  **散布的重复条件逻辑**：通过使用面向对象的多态性进行重构，将条件逻辑嵌入到对象层次结构中。

记住，重构的目的是提高代码的清晰度和可维护性。在决定投入时间进行重大重构（如引入多态性）前，请权衡收益与成本，并始终在良好测试的保护下进行。现在，你已经掌握了识别这些异味和进行重构的工具，可以更有信心地让你的代码变得更加整洁。

![](img/62a307e40635ec771b228bfe8aa8073b_2.png)

---
*本次课程内容基于 Ali Sivji 的演讲“If Statements are a Code Smell”整理。涉及的“忙碌海狸”机器人是芝加哥 Python 用户组的开源项目。*