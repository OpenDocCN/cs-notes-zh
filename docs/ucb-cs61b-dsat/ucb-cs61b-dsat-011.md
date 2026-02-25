# 数据结构与算法：P11：从双链表中移除重复元素

![](img/18893352cf80a347ec4a340dedd70cfc_0.png)

![](img/18893352cf80a347ec4a340dedd70cfc_1.png)

在本教程中，我们将学习如何从一个双链表中移除所有重复的元素。我们将通过分析一个具体的编程问题来理解其背后的逻辑和实现步骤，并学习如何使用指针操作来安全地删除节点。

## 概述

本节我们将探讨一个双链表问题：移除所有重复的元素。核心挑战在于，重复的元素可能并不相邻，因此我们需要一种方法来识别并删除列表中所有重复出现的值。我们将使用嵌套循环的策略来遍历和比较元素，并通过调整节点指针来移除重复项。

## 问题分析与策略

首先，让我们思考如何在列表中查找重复项。一个直观的方法是使用两个嵌套循环。

*   外层循环遍历列表中的每一个元素。
*   内层循环检查当前元素之后的所有元素，看是否存在重复。

以下是这个思路的伪代码表示：
```java
for (Node ref = sentinel.next; ref != sentinel; ref = ref.next) {
    for (Node checker = ref.next; checker != sentinel; checker = checker.next) {
        if (ref.item.equals(checker.item)) {
            // 找到重复项，需要移除checker指向的节点
        }
    }
}
```
在上面的代码中，`ref`代表我们当前正在检查的元素，`checker`则用于遍历`ref`之后的所有元素以寻找重复。

## 实现节点移除

当我们通过`checker`找到一个重复节点时，需要将其从双链表中移除。这涉及到调整其前驱节点和后继节点的指针，使其“跳过”当前节点。

假设我们有以下节点关系：`A <-> B <-> C`，其中`B`是我们要删除的重复节点（即`checker`指向的节点）。

我们需要进行两步指针操作：
1.  让`A`的`next`指针指向`C`：`A.next = C`
2.  让`C`的`prev`指针指向`A`：`C.prev = A`

完成这两步后，节点`B`就不再被列表中的任何节点引用，在Java中将被垃圾回收机制自动清理。

在代码中，如果我们将`checker`的前驱节点和后继节点分别存储在变量`checkerPrev`和`checkerNext`中，那么移除操作可以表示为：
```java
checkerPrev.next = checkerNext; // 步骤1
checkerNext.prev = checkerPrev; // 步骤2
```

## 完整代码与流程整合

现在，我们将移除逻辑整合到之前的嵌套循环框架中。关键点在于，在内层循环中移除一个节点后，`checker`变量需要被正确地更新到下一个待检查的节点。

以下是整合后的核心代码逻辑：
```java
Node ref = sentinel.next;
while (ref != sentinel) {
    Node checker = ref.next;
    while (checker != sentinel) {
        if (ref.item.equals(checker.item)) {
            // 找到重复，移除checker节点
            Node checkerPrev = checker.prev;
            Node checkerNext = checker.next;
            checkerPrev.next = checkerNext;
            checkerNext.prev = checkerPrev;
            // 将checker移动到被删除节点的下一个节点，继续循环
            checker = checkerNext;
        } else {
            // 不是重复，正常移动到下一个节点
            checker = checker.next;
        }
    }
    // 检查完与当前ref元素相关的所有可能重复项后，移动ref到下一个元素
    ref = ref.next;
}
```

## 总结

本节课我们一起学习了如何从双链表中移除所有重复元素。

我们首先分析了使用嵌套循环遍历和比较元素的策略。接着，我们深入探讨了双链表中删除节点的核心操作，即调整前驱和后继节点的指针以“绕过”要删除的节点。最后，我们将这些步骤整合成一个完整的解决方案。

![](img/18893352cf80a347ec4a340dedd70cfc_3.png)

记住，在处理链表问题时，绘制节点和指针的示意图是理解指针操作和验证逻辑的极佳方法。