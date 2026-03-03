# 005：字典

![](img/2b66443907fb946a813965bfda7ab8c3_0.png)

## 概述

在本节课中，我们将要学习Python中的字典。字典是一种非常有用的数据结构，它允许我们以键值对的形式存储和组织相关联的信息。我们将学习如何创建字典、访问和修改其中的数据，以及如何遍历字典中的键和值。

---

## 字典简介

上一节我们介绍了字典的基本概念。字典非常适合存储像航天器这样具有多种属性的对象信息。例如，一个航天器有名称、与地球的距离等属性。

### 创建字典

以下是创建一个字典的基本语法。字典使用花括号 `{}` 定义，而列表使用方括号 `[]`。

```python
spacecraft = {
    "name": "Voyager 1",
    "distance": 163
}
```

在这个例子中，我们创建了一个名为 `spacecraft` 的字典。它包含两个键值对：
*   **键** `"name"` 对应的**值**是 `"Voyager 1"`。
*   **键** `"distance"` 对应的**值**是 `163`。

键和值之间用冒号 `:` 分隔，不同的键值对之间用逗号 `,` 分隔。

---

## 访问字典中的值

创建字典后，我们经常需要获取其中存储的值。本节中我们来看看如何通过键来访问对应的值。

访问字典值最直接的方法是使用方括号 `[]` 语法，并在其中指定键名。

```python
# 假设我们有一个函数接收字典作为参数
def create_report(spacecraft):
    report = f"{spacecraft['name']} is {spacecraft['distance']} AU from Earth."
    return report
```

在 `create_report` 函数中，我们通过 `spacecraft['name']` 和 `spacecraft['distance']` 来获取航天器的名称和距离，并将它们插入到格式化字符串中。

---

## 处理不存在的键

当我们尝试访问一个字典中不存在的键时，Python会引发 `KeyError` 错误。为了避免程序崩溃，我们需要安全地处理这种情况。

### 使用 `.get()` 方法

`.get()` 方法允许我们尝试获取一个键的值。如果该键不存在，它可以返回一个我们指定的默认值（例如 `"unknown"`），而不是引发错误。

以下是 `.get()` 方法的使用方式：

```python
def create_report(spacecraft):
    name = spacecraft.get("name", "unknown")
    distance = spacecraft.get("distance", "unknown")
    report = f"{name} is {distance} AU from Earth."
    return report
```

在这个改进版本的函数中，即使传入的字典缺少 `"name"` 或 `"distance"` 键，程序也能正常运行并输出 `"unknown"`，而不会崩溃。

---

## 向字典添加键值对

字典创建后，我们仍然可以随时向其中添加新的键值对。以下是几种常见的方法。

### 方法一：直接赋值

最直接的方法是使用赋值语句，就像给变量赋值一样。

```python
spacecraft = {"name": "James Webb Space Telescope"}
spacecraft["distance"] = 0.01  # 添加新的键值对
```

### 方法二：使用 `.update()` 方法

如果需要一次性添加多个键值对，可以使用 `.update()` 方法。它接受一个字典作为参数，并将该字典中的所有键值对合并到原字典中。

```python
spacecraft = {"name": "James Webb Space Telescope"}
new_info = {"distance": 0.01, "orbit": "Sun"}
spacecraft.update(new_info)  # 现在 spacecraft 包含 name, distance, orbit 三个键
```

---

## 遍历字典

字典提供了几种方法来遍历其内容，这对于处理集合数据非常有用。

### 遍历所有键

我们可以使用 `.keys()` 方法获取字典中所有键的列表，然后使用 `for` 循环进行遍历。

```python
distances = {
    "Voyager 1": 163,
    "Voyager 2": 136,
    "Pioneer 10": 80
}

for name in distances.keys():
    au = distances[name]
    print(f"{name} is {au} AU from Earth.")
```

### 遍历所有值

类似地，使用 `.values()` 方法可以直接遍历字典中的所有值。

```python
def convert_au_to_meters(au):
    meters_per_au = 149597870700
    return au * meters_per_au

for distance_au in distances.values():
    distance_m = convert_au_to_meters(distance_au)
    print(f"{distance_au} AU is {distance_m} meters.")
```

---

## 总结

![](img/2b66443907fb946a813965bfda7ab8c3_2.png)

![](img/2b66443907fb946a813965bfda7ab8c3_3.png)

本节课中我们一起学习了Python字典的核心操作。我们首先了解了字典的基本结构，即由键值对组成。接着，我们学习了如何创建字典、如何使用方括号和 `.get()` 方法安全地访问值。然后，我们探索了如何通过直接赋值或使用 `.update()` 方法向字典添加新数据。最后，我们掌握了如何使用 `.keys()` 和 `.values()` 方法来遍历字典中的键和值。字典是组织相关数据的强大工具，在Python编程中应用广泛。