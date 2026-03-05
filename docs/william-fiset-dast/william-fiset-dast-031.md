# 031：哈希表分离链接法源码解析 🧩

在本节课中，我们将学习哈希表的一种经典实现方式——分离链接法（Separate Chaining）的源代码。我们将通过分析一个具体的Java实现，来理解如何将键值对存储在哈希表中，以及如何处理哈希冲突。

---

## 源码概览

首先，我们来看一下代码的整体结构。实现主要包含两个类：`Entry` 和 `SeparateChainingHashTable`。

`Entry` 类代表一个将要插入哈希表的键值对条目。`SeparateChainingHashTable` 类则是哈希表本身，它使用一个链表数组来处理哈希冲突。

## Entry类详解

`Entry` 类封装了哈希表中的单个数据项。它包含三个核心部分：键（Key）、值（Value）和该键的哈希码（Hash Code）。

以下是 `Entry` 类的关键代码结构：

```java
public class Entry<K, V> {
    int hash; // 缓存的哈希码
    K key;    // 键
    V value;  // 值

    public Entry(K key, V value) {
        this.key = key;
        this.value = value;
        this.hash = key.hashCode(); // 计算并缓存哈希码
    }
}
```

**核心概念解析**：
*   **键（Key）**：用于查找和存储数据的唯一标识符。
*   **值（Value）**：与键相关联的数据。
*   **哈希码（Hash Code）**：通过键的 `hashCode()` 方法计算出的一个整数值。这个值决定了该条目在哈希表数组中的初始位置。

缓存哈希码至关重要。对于像字符串这样的对象，计算哈希码可能需要线性时间（O(n)）。在构造时计算一次并存储起来，可以避免在后续操作（如查找、比较）中重复计算，从而提升性能。

## SeparateChainingHashTable类结构

![](img/13416353eb38932f364de3c714552d08_1.png)

上一节我们介绍了存储单个数据的 `Entry` 类，本节中我们来看看管理这些条目的哈希表主体结构。

`SeparateChainingHashTable` 类使用一个链表（或其它动态集合，如 `ArrayList`）数组作为底层存储。每个数组位置（通常称为“桶”或“槽”）都对应一个链表，用于存放所有哈希到该位置的条目。

以下是该类的核心成员变量：

```java
public class SeparateChainingHashTable<K, V> {
    private static final int DEFAULT_CAPACITY = 3; // 默认容量
    private static final double DEFAULT_LOAD_FACTOR = 0.75; // 默认负载因子

    private double maxLoadFactor; // 最大负载因子
    private int capacity, threshold, size = 0; // 容量、扩容阈值、当前大小
    private LinkedList<Entry<K, V>>[] table; // 链表数组
}
```

**核心概念解析**：
*   **容量（Capacity）**：哈希表底层数组的长度，即桶的数量。初始值设为 `DEFAULT_CAPACITY`。
*   **负载因子（Load Factor）**：衡量哈希表满的程度，计算公式为：`size / capacity`。当负载因子超过 `maxLoadFactor` 时，会触发扩容（Rehashing）。
*   **扩容阈值（Threshold）**：触发扩容的临界值，计算公式为：`threshold = capacity * maxLoadFactor`。
*   **链表数组（Table）**：这是实现分离链接法的核心数据结构。数组的每个索引位置都挂载着一个链表。

## 核心方法流程

理解了基本结构后，我们来看看哈希表的核心操作是如何利用这些结构完成的。

### 1. 规范化索引

任何键在通过哈希函数计算后，都需要被映射到数组的有效索引范围内（0 到 capacity-1）。这个过程称为“规范化”。

```java
private int normalizeIndex(int keyHash) {
    return (keyHash & 0x7FFFFFFF) % capacity;
}
```
**代码解释**：首先，`keyHash & 0x7FFFFFFF` 将哈希码的最高位符号位清零，确保得到一个非负整数。然后，通过取模运算 `% capacity` 将这个整数压缩到数组索引的范围内。

### 2. 插入条目（put）

插入操作是哈希表的核心。以下是其逻辑步骤：

以下是插入条目的关键步骤：
1.  如果键为 `null`，则抛出异常（本实现假定键不为空）。
2.  根据键计算哈希码，并调用 `normalizeIndex` 方法得到桶的索引。
3.  获取该索引对应的链表。
4.  **遍历链表**：
    *   如果找到具有相同键的条目，则更新其值并返回旧值。
    *   如果未找到，则在链表末尾添加新条目。
5.  增加 `size`。如果 `size` 超过了 `threshold`，则执行扩容操作。

### 3. 查找条目（get）

查找操作与插入的遍历部分类似：
1.  计算键的哈希码并规范化得到桶索引。
2.  获取该索引对应的链表。
3.  遍历链表，比较键是否相等（使用 `equals` 方法）。
4.  找到则返回对应的值，否则返回 `null`。

### 4. 扩容（Resize）

当元素数量超过阈值时，哈希表的性能会下降，因此需要扩容。

以下是扩容的主要步骤：
1.  将容量加倍（或按其他策略增加）。
2.  根据新容量计算新的阈值。
3.  创建一个新的、更大的链表数组。
4.  遍历旧表中的每一个条目，根据新的容量重新计算其索引位置（即重新哈希），并将其插入到新数组对应的链表中。
5.  用新数组替换旧数组。

---

![](img/13416353eb38932f364de3c714552d08_3.png)

本节课中我们一起学习了哈希表分离链接法的Java源码实现。我们从最基础的 `Entry` 类开始，理解了如何存储键值对和缓存哈希码。然后，我们深入分析了 `SeparateChainingHashTable` 类的结构，包括其底层链表数组以及容量、负载因子等核心参数。最后，我们梳理了插入、查找和扩容这几个关键操作的执行流程。通过将数据分散到多个链表中，分离链接法有效地解决了哈希冲突问题，是构建高效哈希表的一种经典而实用的方法。