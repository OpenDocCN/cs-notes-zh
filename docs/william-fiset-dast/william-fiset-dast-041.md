# 041：Fenwick树源码解析 📚

在本节课中，我们将一起学习Fenwick树（又称二叉索引树）的源代码实现。我们将分析其核心构造方法、关键操作，并理解其内部工作原理。

## 概述

Fenwick树是一种高效的数据结构，用于计算数组前缀和。它支持两种主要操作：在 `O(log n)` 时间内更新单个元素的值，以及在 `O(log n)` 时间内查询前缀和。本节我们将深入其Java源码实现。

## 源码结构

现在，让我们查看Fenwick树的源代码。代码位于一个GitHub仓库中，具体路径在描述中提供。源代码组织在 `FenwickTree` 文件夹下。

以下是Fenwick树类的核心结构：

```java
public class FenwickTree {
    // 树状数组
    private long[] tree;

    // 构造方法一：创建指定大小的空树
    public FenwickTree(int sz) {
        tree = new long[sz + 1];
    }

    // 构造方法二：根据给定数组构造树（线性时间）
    public FenwickTree(long[] values) {
        if (values == null) throw new IllegalArgumentException("Values array cannot be null!");
        tree = values.clone();
        for (int i = 1; i < tree.length; i++) {
            int j = i + lsb(i);
            if (j < tree.length) tree[j] += tree[i];
        }
    }
}
```

## 构造方法详解

上一节我们介绍了类的整体结构，本节中我们来看看两个构造方法的具体实现。

### 空树构造方法

第一个构造方法创建一个指定大小的空Fenwick树。它初始化一个内部数组，其大小为 `sz + 1`。这里加1的原因是Fenwick树通常使用1-based索引。

### 数组构造方法（线性时间）

第二个构造方法接受一个值数组，并在线性时间内构建Fenwick树。这是推荐使用的构造方法。

![](img/489c347e535070fc3f799422f5b8d0f2_1.png)

**关键点**：传入的 `values` 数组必须是 **1-based** 的。这意味着数组的第一个元素（索引0）通常不使用或作为占位符，有效数据从索引1开始。这与上一视频中关于循环边界的讨论相关。

构建过程的核心循环如下：

```java
for (int i = 1; i < tree.length; i++) {
    int j = i + lsb(i);
    if (j < tree.length) tree[j] += tree[i];
}
```

其中，`lsb(i)` 函数返回数字 `i` 的最低有效位（Least Significant Bit）。公式为：
**`lsb(i) = i & -i`**

## 核心操作

理解了构造方法后，我们来看看Fenwick树支持的核心操作。

### 前缀和查询

`prefixSum` 方法计算从索引1到 `i` 的前缀和。

```java
public long prefixSum(int i) {
    long sum = 0L;
    while (i != 0) {
        sum += tree[i];
        i -= lsb(i);
    }
    return sum;
}
```

操作通过不断减去最低有效位（`i -= lsb(i)`）来遍历树节点，累加路径上的值。

### 区间和查询

`sum` 方法计算闭区间 `[i, j]` 的和。它利用前缀和实现：
**`sum(i, j) = prefixSum(j) - prefixSum(i - 1)`**

```java
public long sum(int left, int right) {
    if (right < left) throw new IllegalArgumentException("Make sure right >= left");
    return prefixSum(right) - prefixSum(left - 1);
}
```

### 单点更新

`add` 方法将值 `k` 加到位置 `i` 的元素上。

```java
public void add(int i, long k) {
    while (i < tree.length) {
        tree[i] += k;
        i += lsb(i);
    }
}
```
操作通过不断加上最低有效位（`i += lsb(i)`）来更新所有受影响的父节点。

### 单点设置

`set` 方法将位置 `i` 的值设置为 `k`。它通过计算新旧值的差值，然后调用 `add` 方法实现。

```java
public void set(int i, long k) {
    long value = sum(i, i);
    add(i, k - value);
}
```

## 辅助方法

以下是实现中用到的一个关键辅助方法：

### 最低有效位（LSB）

`lsb` 方法是一个私有静态方法，用于计算整数的最低有效位。

```java
private static int lsb(int i) {
    return i & -i;
}
```
这个方法利用了二进制补码的特性，是Fenwick树高效操作的基础。

## 使用示例

为了让大家更好地理解如何使用这个类，以下是一个简单的示例：

```java
// 假设有一个1-based的输入数组
long[] values = {0, 1, 2, 3, 4, 5}; // 索引0是占位符
FenwickTree ft = new FenwickTree(values);

// 查询前缀和
long sum1to3 = ft.prefixSum(3); // 返回 6 (1+2+3)

// 查询区间和
long sum2to4 = ft.sum(2, 4); // 返回 9 (2+3+4)

// 更新元素
ft.add(3, 10); // 给位置3的元素加10
long newSum1to3 = ft.prefixSum(3); // 返回 16
```

![](img/489c347e535070fc3f799422f5b8d0f2_3.png)

## 总结

本节课中我们一起学习了Fenwick树的完整源代码实现。我们分析了它的两个构造方法，理解了为何需要使用1-based索引。我们详细探讨了其四个核心操作：`prefixSum`（前缀和查询）、`sum`（区间和查询）、`add`（单点更新）和 `set`（单点设置），并了解了最低有效位（LSB）在高效遍历树结构中的关键作用。通过这段简洁的代码，我们获得了一个能在 `O(log n)` 时间内进行前缀和与更新操作的强大数据结构。