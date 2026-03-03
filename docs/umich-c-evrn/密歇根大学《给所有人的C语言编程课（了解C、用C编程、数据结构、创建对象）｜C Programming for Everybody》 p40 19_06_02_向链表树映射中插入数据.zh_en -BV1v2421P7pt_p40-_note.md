# C语言编程：第40讲：向链表树映射中插入数据

![](img/f75089e0e62249d89e111e6af2a5fa6a_0.png)

在本节课中，我们将学习如何为我们的树映射（Tree Map）数据结构实现 `put` 方法。核心挑战在于，我们需要同时维护两个数据结构：一个有序链表和一个二叉搜索树。我们将通过详细的步骤和图示，理解如何高效地插入新数据，并处理各种边界情况。

---

## 🧠 核心概念与挑战

本节我们将探讨实现 `put` 方法的核心思想。关键在于，我们需要**同时更新两个数据结构**：一个用于快速查找的二叉搜索树和一个用于顺序遍历的有序链表。

二叉搜索树的查找性能是 **O(log n)**，而有序链表的查找性能是 **O(n)**。这意味着，对于一个包含一百万个条目的树，平均只需约20次比较即可找到目标；而链表则需要平均五十万次比较。因此，我们主要利用树进行搜索，仅在需要顺序迭代时才使用链表。但在执行 `put` 操作时，我们必须同时维护两者。

![](img/f75089e0e62249d89e111e6af2a5fa6a_2.png)

这并非易事。仅仅通过搜索或询问AI可能无法直接获得正确答案。你需要真正理解背后的原理。绘制示意图在此过程中极具价值。代码本身最终会显得简洁明了，但实现过程可能需要反复尝试和修正。

---

![](img/f75089e0e62249d89e111e6af2a5fa6a_4.png)

## 📊 数据结构回顾

![](img/f75089e0e62249d89e111e6af2a5fa6a_6.png)

在深入代码之前，我们先回顾一下使用的数据结构。每个条目（Entry）同时属于两个结构：

*   **树结构**：通过 `left` 和 `right` 指针连接。
*   **链表结构**：通过 `next` 指针连接。

![](img/f75089e0e62249d89e111e6af2a5fa6a_8.png)

我们的树映射（TreeMap）类包含两个主要属性：
*   `root`：指向二叉搜索树的根节点。
*   `head`：指向有序链表的头节点。

在构造函数中，我们将两者都初始化为 `null`，表示一个空映射。

![](img/f75089e0e62249d89e111e6af2a5fa6a_10.png)

---

## 🌀 插入算法详解

![](img/f75089e0e62249d89e111e6af2a5fa6a_12.png)

接下来，我们详细分析插入新键值对时的各种情况。算法需要处理以下几种场景：
1.  插入到空映射。
2.  插入到链表头部（新键最小）。
3.  插入到链表尾部（新键最大）。
4.  插入到链表中间。
5.  替换已存在的键的值。

![](img/f75089e0e62249d89e111e6af2a5fa6a_14.png)

我们将使用两个辅助变量 `largest_less` 和 `smallest_greater`（在视频中称为 `left` 和 `right`）来追踪“间隙”。它们就像面包屑，记录着我们遍历树时遇到的小于新键的最大节点和大于新键的最小节点，从而为链表插入精确定位。

![](img/f75089e0e62249d89e111e6af2a5fa6a_16.png)

![](img/f75089e0e62249d89e111e6af2a5fa6a_18.png)

### 情况一：插入到空映射

![](img/f75089e0e62249d89e111e6af2a5fa6a_20.png)

这是最简单的情况。如果 `head` 和 `root` 都为 `null`，我们只需创建一个新节点，并让 `head` 和 `root` 都指向它即可。

```
if self.head is None:
    new_entry = Entry(key, value)
    self.head = new_entry
    self.root = new_entry
    return
```

![](img/f75089e0e62249d89e111e6af2a5fa6a_22.png)

### 情况二：查找与替换

![](img/f75089e0e62249d89e111e6af2a5fa6a_24.png)

在遍历树寻找插入位置时，我们使用 `cur` 指针从根节点开始移动，并不断更新 `largest_less` 和 `smallest_greater`。

![](img/f75089e0e62249d89e111e6af2a5fa6a_26.png)

*   如果 `cur.key > new_key`，则向左子树移动，并更新 `smallest_greater = cur`。
*   如果 `cur.key < new_key`，则向右子树移动，并更新 `largest_less = cur`。
*   如果 `cur.key == new_key`，则找到匹配项。这是最简单的情况：只需更新该节点的值，无需修改链表或树的结构。

![](img/f75089e0e62249d89e111e6af2a5fa6a_28.png)

![](img/f75089e0e62249d89e111e6af2a5fa6a_29.png)

```
if cur.key == key:
    cur.value = value  # 替换值
    return
```

### 情况三：插入到链表中间

当 `cur` 变为 `null` 时，我们找到了树中的插入位置。此时，`largest_less` 和 `smallest_greater` 正好定义了新节点在链表中的前驱和后继。

![](img/f75089e0e62249d89e111e6af2a5fa6a_31.png)

![](img/f75089e0e62249d89e111e6af2a5fa6a_33.png)

1.  创建新节点 `new_entry`。
2.  将新节点插入树中：如果 `new_key < parent.key`，则作为左子节点；否则作为右子节点。
3.  更新链表指针：
    ```
    new_entry.next = smallest_greater
    if largest_less is not None:
        largest_less.next = new_entry
    else:
        # 说明新节点是最小的，需要更新head
        self.head = new_entry
    ```

### 情况四：插入到链表头部或尾部

![](img/f75089e0e62249d89e111e6af2a5fa6a_35.png)

![](img/f75089e0e62249d89e111e6af2a5fa6a_37.png)

这是情况三的特殊形式：
*   **头部插入**：当 `largest_less` 为 `null` 时，说明新键比所有现有键都小。新节点应成为新的链表头 (`self.head`)。
*   **尾部插入**：当 `smallest_greater` 为 `null` 时，说明新键比所有现有键都大。新节点的 `next` 指针应为 `null`，并且前驱节点 (`largest_less`) 的 `next` 指针应指向它。

![](img/f75089e0e62249d89e111e6af2a5fa6a_39.png)

---

![](img/f75089e0e62249d89e111e6af2a5fa6a_41.png)

## 💡 总结与建议

![](img/f75089e0e62249d89e111e6af2a5fa6a_43.png)

本节课中，我们一起学习了如何为同时维护有序链表和二叉搜索树的映射数据结构实现 `put` 方法。我们分析了插入到空映射、链表头、链表尾、链表中间以及替换现有值等多种情况，并理解了如何使用 `largest_less` 和 `smallest_greater` 这两个“面包屑”变量来精确定位链表中的插入点。

![](img/f75089e0e62249d89e111e6af2a5fa6a_45.png)

实现此类复杂数据结构的代码充满挑战，出错是过程的一部分。关键在于理解算法本身，然后耐心地通过绘图和调试来完善实现。测试所有边界情况至关重要。完成这个练习将极大地加深你对指针操作和数据结构协同工作的理解。

![](img/f75089e0e62249d89e111e6af2a5fa6a_47.png)

![](img/f75089e0e62249d89e111e6af2a5fa6a_49.png)

![](img/f75089e0e62249d89e111e6af2a5fa6a_51.png)

接下来，我们将回到“Python for Everybody”课程，对所学内容进行总结和整合。