# 037：哈希表开放寻址法代码实现 🔧

在本节课中，我们将学习一个使用开放寻址法（具体为二次探测）作为冲突解决策略的哈希表的源代码实现。我们将逐步解析代码结构、核心变量、关键方法以及其背后的逻辑，确保初学者也能理解。

## 概述

我们将分析一个名为 `HashTableQuadraticProbing` 的泛型类。它管理键值对，并通过二次探测法处理哈希冲突。代码中定义了负载因子、容量、大小阈值以及用于标记已删除条目的特殊令牌。

---

### 类定义与实例变量

首先，我们来看类的定义和它内部使用的主要变量。

```java
public class HashTableQuadraticProbing<K, V> {
    private double loadFactor;
    private int capacity, threshold, modificationCount;
    private int usedBuckets, keyCount;
    private K[] keys;
    private V[] values;
    private final K TOMBSTONE = (K) (new Object());
}
```

*   **`loadFactor`**: 这是哈希表愿意承受的最大负载因子。当实际负载超过此阈值时，哈希表将进行扩容。
*   **`capacity`**: 表示哈希表底层数组的当前容量。
*   **`threshold`**: 这是触发扩容的临界大小，计算公式为 `threshold = (int)(capacity * loadFactor)`。
*   **`modificationCount`**: 用于跟踪哈希表的结构性修改次数，常用于迭代器中以快速失败。
*   **`usedBuckets`**: 记录已被占用的桶数量（包括存放有效键值对的桶和标记为已删除的桶）。
*   **`keyCount`**: 记录哈希表中实际存在的有效键值对数量。
*   **`keys` 与 `values`**: 这是两个并行数组，分别用于存储键和值。
*   **`TOMBSTONE`**: 这是一个特殊的常量对象，用于标记数组中已被删除的条目位置，以避免查找链中断。

---

### 构造方法与初始化

上一节我们介绍了核心变量，本节中我们来看看对象的初始化过程。哈希表提供了多个构造函数，允许用户指定初始容量和负载因子。

```java
public HashTableQuadraticProbing() {
    this(16, 0.75);
}

public HashTableQuadraticProbing(int capacity) {
    this(capacity, 0.75);
}

public HashTableQuadraticProbing(int capacity, double loadFactor) {
    if (capacity <= 0) throw new IllegalArgumentException("Illegal capacity: " + capacity);
    if (loadFactor <= 0 || Double.isNaN(loadFactor) || Double.isInfinite(loadFactor))
        throw new IllegalArgumentException("Illegal loadFactor: " + loadFactor);

    this.loadFactor = loadFactor;
    this.capacity = Math.max(capacity, 16);
    adjustCapacity();
    threshold = (int)(this.capacity * loadFactor);

    keys = (K[]) new Object[this.capacity];
    values = (V[]) new Object[this.capacity];
}
```

关键点在于 `adjustCapacity()` 方法。由于二次探测法的特性，为了确保探测序列能够遍历所有桶，哈希表的容量必须是一个**质数**。此方法负责将用户传入的容量调整为一个不小于原值的质数。

---

### 核心辅助方法：哈希函数与探测

哈希表的核心操作依赖于两个函数：将键映射到数组索引的哈希函数，以及在发生冲突时寻找下一个可用位置的探测函数。

*   **哈希函数**：它首先调用键对象的 `hashCode()` 方法，然后将结果与 `0x7FFFFFFF` 进行按位与运算以消除符号位，最后对容量取模得到初始索引。
    ```java
    private int normalizeIndex(int keyHash) {
        return (keyHash & 0x7FFFFFFF) % capacity;
    }
    ```
*   **二次探测**：当初始位置被占用时，该方法通过一个二次方程 `i = (originalIndex + (j * j)) % capacity` 来计算下一个探测位置，其中 `j` 是探测次数。

---

### 关键操作：插入、查找与删除

以下是哈希表最关键的三个操作：插入（或更新）、查找和删除。

#### 插入键值对 (`put`)

`put` 方法负责将新的键值对添加到表中，如果键已存在则更新其对应的值。

![](img/049a832737adbe08b9ea6ed5db518fc9_1.png)

```java
public V put(K key, V value) {
    if (key == null) throw new IllegalArgumentException("Null key");
    if (usedBuckets >= threshold) resizeTable();

    int index = normalizeIndex(key.hashCode());
    int i = index, j = 1;
    // 探测循环
    do {
        // 情况1：找到空桶，直接插入
        if (keys[i] == null) {
            keys[i] = key;
            values[i] = value;
            keyCount++;
            usedBuckets++;
            modificationCount++;
            return null;
        }
        // 情况2：找到相同键，更新值
        if (keys[i].equals(key)) {
            V oldValue = values[i];
            values[i] = value;
            modificationCount++;
            return oldValue;
        }
        // 情况3：当前位置是墓碑或已被其他键占用，继续探测
        i = normalizeIndex(index + j * j);
        j++;
    } while (true);
}
```
插入逻辑的步骤如下：
1.  检查负载，必要时扩容。
2.  计算初始哈希索引。
3.  进入探测循环：
    *   如果当前位置为空，直接插入。
    *   如果当前位置的键与目标键相同，则更新值。
    *   否则，使用二次探测公式计算下一个位置，继续查找。

#### 查找值 (`get`)

`get` 方法根据给定的键查找对应的值。

```java
public V get(K key) {
    if (key == null) throw new IllegalArgumentException("Null key");
    int index = normalizeIndex(key.hashCode());
    int i = index, j = 1;
    // 探测循环
    do {
        if (keys[i] == null) return null; // 遇到空桶，说明键不存在
        if (keys[i].equals(key)) {
            if (keys[i] == TOMBSTONE) return null; // 键已被删除
            return values[i]; // 找到键，返回值
        }
        i = normalizeIndex(index + j * j);
        j++;
    } while (true);
}
```
查找过程与插入类似，沿着探测序列查找，直到找到键、遇到空桶或回到起点。遇到 `TOMBSTONE` 时需继续探测。

#### 删除键值对 (`remove`)

`remove` 方法删除指定的键及其关联的值。

```java
public V remove(K key) {
    if (key == null) throw new IllegalArgumentException("Null key");
    int index = normalizeIndex(key.hashCode());
    int i = index, j = 1;
    // 探测循环
    do {
        if (keys[i] == null) return null; // 键不存在
        if (keys[i].equals(key)) {
            if (keys[i] == TOMBSTONE) return null; // 键已被删除
            keyCount--;
            modificationCount++;
            V oldValue = values[i];
            keys[i] = TOMBSTONE; // 标记为已删除
            values[i] = null;
            return oldValue;
        }
        i = normalizeIndex(index + j * j);
        j++;
    } while (true);
}
```
删除操作不是简单地将桶置空，而是用 `TOMBSTONE` 标记该位置。这保证了后续的查找和插入操作能正确遍历整个探测链。

---

### 动态调整：扩容机制

当哈希表中的元素数量达到阈值（`threshold`）时，为了维持操作效率，需要进行扩容。

```java
private void resizeTable() {
    capacity = nextPowerOfTwo(capacity * 2); // 容量翻倍并调整
    adjustCapacity(); // 再次确保容量为质数
    threshold = (int)(capacity * loadFactor);

    K[] oldKeys = keys;
    V[] oldValues = values;
    keys = (K[]) new Object[capacity];
    values = (V[]) new Object[capacity];

    keyCount = usedBuckets = 0;
    // 重新哈希所有有效条目
    for (int i = 0; i < oldKeys.length; i++) {
        if (oldKeys[i] != null && oldKeys[i] != TOMBSTONE) {
            put(oldKeys[i], oldValues[i]);
        }
    }
}
```
扩容步骤包括：
1.  计算新的容量（通常翻倍并确保为质数）。
2.  创建新的、更大的键值数组。
3.  遍历旧数组，将所有非空且非墓碑的有效键值对重新插入到新表中。这个过程称为“重新哈希”。

---

### 其他实用方法

除了核心操作，哈希表还提供了一些查询方法：

*   `hasKey(K key)`: 检查哈希表中是否包含指定的键。
*   `size()`: 返回当前有效键值对的数量。
*   `isEmpty()`: 判断哈希表是否为空。
*   `clear()`: 清空哈希表，将所有桶重置。

![](img/049a832737adbe08b9ea6ed5db518fc9_3.png)

---

## 总结

本节课中我们一起学习了基于二次探测的开放寻址哈希表的完整代码实现。我们分析了其数据结构设计，包括使用并行数组存储键值、用特殊令牌标记删除位。我们深入探讨了核心操作：插入时的线性探测与更新逻辑、查找时的链式搜索以及删除时使用墓碑标记的策略。最后，我们了解了当负载过高时，哈希表如何通过扩容并重新哈希所有元素来保持性能。理解这个实现是掌握哈希表这一重要数据结构的关键一步。