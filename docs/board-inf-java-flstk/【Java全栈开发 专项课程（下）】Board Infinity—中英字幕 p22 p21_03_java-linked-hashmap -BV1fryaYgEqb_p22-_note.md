# Java全栈开发：22：LinkedHashMap详解 📚

![](img/15641c8dacb37584b900bc0cc11516c7_0.png)

在本节课中，我们将学习Java集合框架中的`LinkedHashMap`。我们将了解它是什么、它与普通`HashMap`的区别、如何创建和使用它，并通过代码示例演示其核心方法。

![](img/15641c8dacb37584b900bc0cc11516c7_2.png)

---

## 概述

`LinkedHashMap`是Java集合框架中的一个类，它实现了`Map`接口。它结合了哈希表的快速访问和链表的顺序维护能力。简单来说，它就像一个能记住你添加元素顺序的`HashMap`。

上一节我们介绍了`HashMap`，本节中我们来看看它的一个有序版本——`LinkedHashMap`。

---

## LinkedHashMap 是什么？ 🤔

`LinkedHashMap`类提供了哈希表和链表的双重实现。`HashMap`的优势在于快速的插入、搜索和删除操作，但它从不维护元素的插入顺序。而`LinkedHashMap`则提供了按插入顺序访问元素的能力。

Java的`LinkedHashMap`接口扩展了`HashMap`类，在哈希表中存储条目，并在内部维护一个所有条目的**双向链表**来排序这些条目。

`LinkedHashMap`包含基于键的唯一元素，并且可以有一个`null`键和多个`null`值。它维护插入顺序，初始默认容量为**16**，负载因子为**0.75**。

![](img/15641c8dacb37584b900bc0cc11516c7_4.png)

---

## 如何创建 LinkedHashMap

以下是创建`LinkedHashMap`的语法，其中`Key`和`Value`是关联的。你也可以根据需要修改容量和负载因子。

```java
LinkedHashMap<Key, Value> variableName = new LinkedHashMap<>();
```

**Key** 是用于关联映射中每个元素的唯一标识符。
**Value** 是与该键关联的值。

大多数方法与`HashMap`通用，例如`get`、`clear`、`getOrDefault`、`put`。但它也有一些更具体的方法，如接受`BiConsumer`接口的`forEach`和`containsValue`。

---

![](img/15641c8dacb37584b900bc0cc11516c7_6.png)

## 代码示例与实践

以下是如何创建和使用`LinkedHashMap`的示例。

我将创建一个键为`String`、值为`Integer`的`LinkedHashMap`。这里我添加几个偶数。

```java
LinkedHashMap<String, Integer> evenNumbers = new LinkedHashMap<>();
evenNumbers.put("Two", 2);
evenNumbers.put("Four", 4);
// ... 以此类推
System.out.println(evenNumbers);
```

我们也可以在初始化时添加键值对：

```java
LinkedHashMap<String, Integer> numbers = new LinkedHashMap<>(evenNumbers);
```

现在，如果你想添加更多数字，可以使用`put`方法：

```java
numbers.put("Six", 6);
numbers.put("Eight", 8);
```

---

## 特定方法演示

除了`put`，`LinkedHashMap`还提供了`putIfAbsent`方法。这个方法只在键不存在时才添加元素。

以下是使用示例：

```java
numbers.putIfAbsent("Six", 6); // 不会添加，因为"Six"已存在
numbers.putIfAbsent("Eight", 8); // 会添加，因为"Eight"不存在
```

这样，我们可以确保集合中不会出现重复的键。

此外，还有其他常用方法如`clear`、`containsKey`等，这里不再赘述。

---

## 总结

本节课中，我们一起学习了`LinkedHashMap`。我们了解到它是`HashMap`的一个有序版本，通过内部的双向链表维护了元素的插入顺序。我们学习了如何创建`LinkedHashMap`，如何使用`put`和`putIfAbsent`等方法添加元素，并通过代码示例加深了理解。

![](img/15641c8dacb37584b900bc0cc11516c7_8.png)

掌握`LinkedHashMap`对于需要保持元素顺序的场景非常有用，希望本教程能帮助你更好地理解和使用它。