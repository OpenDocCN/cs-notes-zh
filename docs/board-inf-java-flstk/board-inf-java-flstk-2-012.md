Java 全栈开发：12：LinkedList 数据结构详解 📚

![](img/d53009eae46031eeac23f0fc7aa20634_0.png)

在本节课中，我们将要学习 Java 集合框架中的 `LinkedList` 类。我们将了解它的基本概念、如何创建和使用它，以及一些常用的操作方法。

---

![](img/d53009eae46031eeac23f0fc7aa20634_2.png)

`LinkedList` 是一个实现了 `List` 和 `Deque` 接口的类，它构成了一个链表数据结构，其中的元素被称为节点。`LinkedList` 类默认被包含在集合框架中。

上一节我们介绍了集合框架的基本概念，本节中我们来看看如何具体使用 `LinkedList`。

首先，我们需要初始化一个 `LinkedList` 对象。你可以创建一个 `List` 类型的引用变量来指向它，但通常直接使用 `LinkedList` 类型。

以下是初始化 `LinkedList` 的代码示例：

```java
LinkedList<String> linkedList = new LinkedList<>();
```

初始化后，我们可以使用 `size()` 方法来查看链表的初始大小。

```java
System.out.println("初始大小: " + linkedList.size());
```

接下来，我们向链表中添加一些元素。`LinkedList` 提供了 `add` 方法来添加元素。

以下是向链表添加元素的步骤：

1.  使用 `add` 方法添加第一个元素 “Java”。
2.  继续添加 “Python”。
3.  添加 “JavaScript”。
4.  添加 “C#”。

添加完成后，我们可以打印整个链表来查看内容。

```java
linkedList.add("Java");
linkedList.add("Python");
linkedList.add("JavaScript");
linkedList.add("C#");
System.out.println("添加元素后: " + linkedList);
```

如果你想在链表的特定索引位置插入一个元素，可以使用 `add(int index, E element)` 方法。

例如，在索引 2 的位置插入 “C++”：

```java
linkedList.add(2, "C++");
```

如果你想从链表中移除元素，可以使用 `remove` 方法。它有两种方式：通过索引移除，或者直接指定要移除的对象。

以下是移除元素的方法：

*   通过索引移除：`linkedList.remove(0)` 会移除第一个元素（“Java”）。
*   通过对象移除：`linkedList.remove(“JavaScript”)` 会移除值为 “JavaScript” 的元素。

在添加和移除了若干元素后，我们可以再次打印链表，并检查其最终大小。

```java
linkedList.remove(0); // 移除索引0的元素
linkedList.remove("JavaScript"); // 移除“JavaScript”
System.out.println("操作后链表: " + linkedList);
System.out.println("最终大小: " + linkedList.size());
```

除了 `add`、`remove` 和 `size`，`LinkedList` 还提供了许多其他方法，例如查找元素的索引（`indexOf`）、检查是否包含某元素（`contains`）等。这些方法与 `ArrayList` 中的方法非常相似。

![](img/d53009eae46031eeac23f0fc7aa20634_4.png)

![](img/d53009eae46031eeac23f0fc7aa20634_5.png)

本节课中我们一起学习了 `LinkedList` 的基本用法，包括如何创建链表、添加元素到特定位置、移除元素以及获取链表大小。`LinkedList` 的操作方法与 `ArrayList` 类似，但底层数据结构不同，这会在特定场景下影响性能。