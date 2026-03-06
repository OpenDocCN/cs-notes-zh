# 029：Java HashSet 教程 🎼

![](img/67d48129d971446b1aedc4b07d104a09_0.png)

在本节课中，我们将学习 Java 中的 `HashSet` 类。我们将通过一个示例来了解 `HashSet` 的不同方法和操作。

![](img/67d48129d971446b1aedc4b07d104a09_2.png)

## 概述

Java 集合框架中的 `HashSet` 类提供了哈希表数据结构的功能。它继承自 `AbstractSet` 类并实现了 `Set` 接口。`HashSet` 使用一种称为“哈希”的机制来存储元素，并且只包含唯一的元素。

## HashSet 的特性

![](img/67d48129d971446b1aedc4b07d104a09_4.png)

以下是 `HashSet` 的一些关键特性：

*   **唯一元素**：`HashSet` 只存储唯一的元素，重复项会被自动忽略。
*   **初始容量与负载因子**：默认初始容量为 **16**，默认负载因子为 **0.75**。
*   **允许空值**：`HashSet` 允许存储 `null` 值。
*   **高效查找**：由于其哈希表实现，`HashSet` 在执行搜索操作时性能优异。

![](img/67d48129d971446b1aedc4b07d104a09_6.png)

## HashSet 的声明

`HashSet` 的声明结构如下，它扩展了 `AbstractSet` 并实现了 `Set` 接口：
```java
public class HashSet<E> extends AbstractSet<E> implements Set<E>, Cloneable, Serializable
```

![](img/67d48129d971446b1aedc4b07d104a09_8.png)

## 常用方法

上一节我们介绍了 `HashSet` 的基本概念，本节中我们来看看它提供的一些常用方法。这些方法大多继承自 `Collection` 和 `Set` 接口。

以下是 `HashSet` 中一些核心的操作方法：

*   `add(E e)`：向集合中添加元素。
*   `clear()`：移除集合中的所有元素。
*   `contains(Object o)`：判断集合是否包含指定元素。
*   `remove(Object o)`：从集合中移除指定元素。
*   `iterator()`：返回一个迭代器，用于遍历集合中的元素。
*   `isEmpty()`：判断集合是否为空。
*   `clone()`：返回此 `HashSet` 实例的浅拷贝。

## 实践操作

现在，让我们通过代码示例来实践这些方法。

首先，我们创建一个 `HashSet` 并添加一些元素。

```java
HashSet<Integer> numbers = new HashSet<>();
numbers.add(100);
numbers.add(200);
numbers.add(300);
numbers.add(400);
System.out.println(numbers);
```

接下来，我们学习如何使用迭代器来访问集合中的元素。

```java
Iterator<Integer> iterate = numbers.iterator();
while(iterate.hasNext()) {
    System.out.println(iterate.next());
}
```

然后，我们尝试移除一个元素。

```java
System.out.println(numbers.remove(300)); // 返回 true，表示移除成功
```

## 集合运算

`HashSet` 也支持集合之间的运算，如并集、交集和差集。我们创建两个 `HashSet` 来进行演示。

```java
HashSet<Integer> set1 = new HashSet<>();
set1.add(100);
set1.add(200);
set1.add(300);

HashSet<Integer> set2 = new HashSet<>();
set2.add(200);
set2.add(300);
set2.add(400);
set2.add(500);
```

首先，我们进行**并集**操作，使用 `addAll` 方法。

```java
set1.addAll(set2); // set1 现在包含 set1 和 set2 的所有元素（去重后）
System.out.println(set1); // 输出: [400, 100, 500, 200, 300]
```

接着，我们进行**交集**操作，使用 `retainAll` 方法。

```java
set1.retainAll(set2); // set1 现在只保留与 set2 共有的元素
System.out.println(set1); // 输出: [400, 200, 300] (假设set1在执行交集前已恢复原状)
```

最后，我们进行**差集**操作，使用 `removeAll` 方法。

```java
set2.removeAll(set1); // 从 set2 中移除所有也存在于 set1 中的元素
System.out.println(set2); // 输出: [500]
```

## 总结

![](img/67d48129d971446b1aedc4b07d104a09_10.png)

![](img/67d48129d971446b1aedc4b07d104a09_12.png)

本节课中我们一起学习了 Java `HashSet` 类。我们了解了它的特性，如存储唯一元素和高效的搜索性能。我们实践了其核心方法，包括添加、移除、遍历元素。最后，我们通过示例演示了如何使用 `HashSet` 进行并集、交集和差集等集合运算。`HashSet` 是处理无需唯一元素集合的强大工具。