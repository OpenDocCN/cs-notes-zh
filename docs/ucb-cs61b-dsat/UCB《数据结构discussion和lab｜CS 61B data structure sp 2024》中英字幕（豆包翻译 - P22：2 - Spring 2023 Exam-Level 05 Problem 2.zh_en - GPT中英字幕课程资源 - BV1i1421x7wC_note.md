# 数据结构：P22：迭代器的迭代器实现教程 🧩

![](img/12f9873a807b45724c6aa7b27a0a078d_0.png)

在本教程中，我们将学习如何实现一个“迭代器的迭代器”。这个特殊的迭代器会接收一个整数迭代器的列表，并以轮询的方式依次从每个迭代器中取出一个元素，直到所有迭代器中的元素都被耗尽。我们将通过一个具体的例子来理解其工作原理，并逐步编写代码实现它。

---

## 迭代器基础回顾 🔄

在深入问题之前，我们先回顾一下迭代器的基本概念。一个迭代器必须实现两个核心方法：`hasNext` 和 `next`。

*   `hasNext()` 方法返回一个布尔值，指示迭代器中是否还有剩余元素。
*   `next()` 方法返回迭代器中的下一个元素。

用代码表示，一个迭代器的接口大致如下：
```java
interface Iterator<T> {
    boolean hasNext();
    T next();
}
```

理解了这些基础后，我们就可以开始构建我们的“迭代器的迭代器”了。

---

## 问题理解与示例分析 🧠

我们的目标是创建一个 `IteratorOfIterators` 类，它本身也是一个迭代器。它接收一个 `List<Iterator<Integer>>` 作为输入，并以轮询的方式输出整数。

让我们通过题目提供的具体例子来理解这个过程。假设我们有三个迭代器：
*   迭代器 A 包含元素：`[1, 3, 4, 5]`
*   迭代器 B 是空的：`[]`
*   迭代器 C 包含元素：`[2]`

`IteratorOfIterators` 应该按以下顺序输出元素：
1.  从 A 取 `1`
2.  跳过空的 B
3.  从 C 取 `2`
4.  轮询回到 A，取 `3`
5.  再次检查 B 和 C，它们都已空，所以继续从 A 取 `4` 和 `5`

因此，最终的输出序列是：`1, 2, 3, 4, 5`。

---

## 实现思路与步骤 🛠️

上一节我们通过例子理解了需求，本节中我们来看看如何用代码实现它。核心思路是使用一个链表来管理这些非空的迭代器，并模拟轮询行为。

### 步骤一：定义类与实例变量

首先，我们定义类并声明一个实例变量来存储传入的迭代器列表。为了方便后续的轮询操作，我们选择使用 `LinkedList`。

```java
import java.util.Iterator;
import java.util.LinkedList;
import java.util.List;
import java.util.NoSuchElementException;

public class IteratorOfIterators implements Iterator<Integer> {
    private LinkedList<Iterator<Integer>> iterators;

    // 构造函数将在下一步实现
    public IteratorOfIterators(List<Iterator<Integer>> a) {
        // 初始化代码
    }

    @Override
    public boolean hasNext() {
        // 实现代码
    }

    @Override
    public Integer next() {
        // 实现代码
    }
}
```

### 步骤二：构造函数与初始化

在构造函数中，我们需要过滤掉输入列表中所有一开始就是空的迭代器，因为它们在轮询中毫无作用。以下是构造函数的实现：

```java
public IteratorOfIterators(List<Iterator<Integer>> a) {
    iterators = new LinkedList<>();
    for (Iterator<Integer> iterator : a) {
        if (iterator.hasNext()) { // 只添加还有元素的迭代器
            iterators.add(iterator);
        }
    }
}
```
经过这个步骤，`iterators` 链表中的所有迭代器都保证至少有一个元素。

### 步骤三：实现 `next()` 方法

`next()` 方法是实现轮询逻辑的核心。其算法如下：
1.  检查是否还有下一个元素（依赖 `hasNext`）。
2.  从链表头部移除第一个迭代器。
3.  从该迭代器中取出一个元素。
4.  如果该迭代器取完后还有元素（`hasNext` 为真），则将其重新放回链表的**尾部**。
5.  返回取出的元素。

这样，链表就形成了一个“队列”，迭代器在被处理后会排到队尾，等待下一轮被处理。耗尽的迭代器则不会被加回队列。

```java
@Override
public Integer next() {
    if (!hasNext()) {
        throw new NoSuchElementException();
    }
    // 1. 从链表头部移除第一个迭代器
    Iterator<Integer> currentIterator = iterators.removeFirst();
    // 2. 从该迭代器中取出下一个元素
    Integer nextValue = currentIterator.next();
    // 3. 如果该迭代器还有元素，则将其加回链表尾部
    if (currentIterator.hasNext()) {
        iterators.addLast(currentIterator);
    }
    // 4. 返回取出的值
    return nextValue;
}
```

### 步骤四：实现 `hasNext()` 方法

`hasNext()` 方法的逻辑相对简单。当我们的 `iterators` 链表为空时，意味着所有迭代器中的元素都已被取出，此时 `hasNext` 应返回 `false`。

```java
@Override
public boolean hasNext() {
    return !iterators.isEmpty();
}
```

---

## 核心要点总结 📝

本节课中我们一起学习了如何实现一个“迭代器的迭代器”。我们回顾了迭代器的两个基本方法 `hasNext` 和 `next`，并通过一个轮询的例子理解了问题需求。实现的关键步骤包括：

1.  **过滤空迭代器**：在构造函数中只保留非空迭代器。
2.  **使用队列管理**：用 `LinkedList` 存储迭代器，利用其 `removeFirst` 和 `addLast` 方法实现轮询。
3.  **实现轮询逻辑**：在 `next()` 方法中，从队列头取出迭代器、获取值，如果迭代器未耗尽则放回队尾。
4.  **判断终止条件**：当队列为空时，`hasNext()` 返回 `false`。

![](img/12f9873a807b45724c6aa7b27a0a078d_2.png)

记住，当处理迭代器相关问题时，先明确 `hasNext` 和 `next` 方法各自的责任，并通过画图或举例来梳理逻辑，是解决问题的有效方法。