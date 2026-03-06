# 031：Java LinkedHashSet 类详解

![](img/fced59cfd00b6576d4132f62489aa62f_0.png)

在本节课中，我们将通过示例学习 Java 中的 `LinkedHashSet` 类及其方法。

![](img/fced59cfd00b6576d4132f62489aa62f_2.png)

## 概述

`LinkedHashSet` 是 Java 集合框架中的一个类，它结合了哈希表和链表数据结构的特性。当需要维护元素的迭代顺序时，就会使用这个类。它是有序版本的 `HashSet`。

## LinkedHashSet 的工作原理

`LinkedHashSet` 的元素存储在一个哈希表中，这一点与 `HashSet` 类似。但不同之处在于，`LinkedHashSet` 内部为所有元素维护了一个**双向链表**。这个链表定义了元素插入哈希表的顺序。

因此，当使用迭代器遍历 `LinkedHashSet` 时，元素将按照它们被插入的顺序返回。

## 类的声明

`LinkedHashSet` 的类声明如下，它扩展了 `HashSet` 并实现了 `Set` 接口：

![](img/fced59cfd00b6576d4132f62489aa62f_4.png)

```java
public class LinkedHashSet<E> extends HashSet<E> implements Set<E>, Cloneable, Serializable
```

![](img/fced59cfd00b6576d4132f62489aa62f_6.png)

## 常用方法

以下是 `LinkedHashSet` 中一些常用的方法：

*   `equals(Object o)`
*   `hashCode()`
*   `removeAll(Collection<?> c)`
*   `addAll(Collection<? extends E> c)`
*   `containsAll(Collection<?> c)`

## 容量与负载因子

`LinkedHashSet` 的默认初始容量是 **8**，默认负载因子是 **0.75**。它位于 `java.util` 包中。

![](img/fced59cfd00b6576d4132f62489aa62f_8.png)

如果你想修改初始容量和负载因子，可以在创建 `LinkedHashSet` 实例时，通过构造函数传入这些参数。

## 示例演示

现在，让我们通过一个示例来演示 `LinkedHashSet` 的用法。

首先，我们创建一个包含偶数的 `ArrayList`：

```java
ArrayList<Integer> evenNumbers = new ArrayList<>();
evenNumbers.add(2);
evenNumbers.add(4);
evenNumbers.add(6);
System.out.println("ArrayList: " + evenNumbers);
```

接下来，我们创建一个 `LinkedHashSet`，并将上面列表中的所有偶数添加进去：

```java
LinkedHashSet<Integer> numbers = new LinkedHashSet<>(evenNumbers);
System.out.println("LinkedHashSet: " + numbers);
```

如果你没有现成的列表，也可以先创建一个空的 `LinkedHashSet`，然后使用 `addAll` 方法或多次调用 `add` 方法来添加元素：

```java
LinkedHashSet<Integer> numbers = new LinkedHashSet<>();
numbers.addAll(evenNumbers);
numbers.add(8);
System.out.println("New LinkedHashSet: " + numbers);
```

### 遍历与删除

要遍历 `LinkedHashSet`，可以使用迭代器：

```java
Iterator<Integer> iterate = numbers.iterator();
while(iterate.hasNext()) {
    System.out.print(iterate.next());
    System.out.print(", ");
}
```

要删除特定元素或清空集合：

```java
numbers.remove(2); // 删除元素 2
numbers.removeAll(numbers); // 删除所有元素
```

### 集合运算

`LinkedHashSet` 支持集合运算，如并集、交集和差集。

首先，创建两个 `LinkedHashSet`：

```java
LinkedHashSet<Integer> set1 = new LinkedHashSet<>();
set1.add(2);
set1.add(4);
LinkedHashSet<Integer> set2 = new LinkedHashSet<>();
set2.add(2);
set2.add(4);
set2.add(6);
```

**1. 并集 (Union)**
使用 `addAll` 方法可以将一个集合的所有元素添加到另一个集合中，实现并集操作：

```java
set1.addAll(set2);
System.out.println("Union: " + set1); // 输出: [2, 4, 6]
```

**2. 交集 (Intersection)**
使用 `retainAll` 方法可以保留两个集合中共有的元素，实现交集操作：

```java
set1.retainAll(set2);
System.out.println("Intersection: " + set1); // 输出: [2, 4]
```

**3. 差集 (Difference)**
使用 `removeAll` 方法可以从一个集合中移除另一个集合中包含的所有元素，实现差集操作。注意，通常将较大的集合放在前面：

```java
set2.removeAll(set1);
System.out.println("Difference: " + set2); // 输出: [6]
```
在上面的差集操作中，`set2` 中与 `set1` 相同的元素（2和4）被移除，只剩下6。

## 总结

本节课我们一起学习了 `LinkedHashSet` 类。我们了解到它是 `HashSet` 的一个有序版本，通过内部维护的双向链表来保证元素的插入顺序。我们学习了它的声明、常用方法、默认容量和负载因子，并通过详细的代码示例演示了如何创建、遍历、删除元素以及执行并集、交集和差集等集合运算。掌握 `LinkedHashSet` 对于在需要维护元素顺序的场景下使用集合非常有帮助。

![](img/fced59cfd00b6576d4132f62489aa62f_10.png)

![](img/fced59cfd00b6576d4132f62489aa62f_12.png)

请继续关注后续课程，以了解更多关于 Set 接口及其其他实现的内容。我们下节课再见。