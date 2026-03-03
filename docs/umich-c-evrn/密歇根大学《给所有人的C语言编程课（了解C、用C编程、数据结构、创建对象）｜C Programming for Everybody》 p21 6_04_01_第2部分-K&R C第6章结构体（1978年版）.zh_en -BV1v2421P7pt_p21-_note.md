# C语言编程：6.04.01：第2部分-K&R C第6章结构体（1978年版）

![](img/c1f9de640ca21fa8ea94b348a48d2b49_0.png)

在本节课中，我们将学习链表的高级操作，包括如何从链表中删除节点，以及双向链表和联合体（union）的概念。我们将通过图示和简单的解释来理解这些核心数据结构的工作原理。

## 链表删除操作

![](img/c1f9de640ca21fa8ea94b348a48d2b49_2.png)

![](img/c1f9de640ca21fa8ea94b348a48d2b49_3.png)

上一节我们介绍了链表的基本概念和遍历。本节中我们来看看如何从链表中删除一个节点。删除操作需要处理三种不同的情况：删除中间节点、删除头节点和删除尾节点。处理这些情况的关键是始终跟踪当前节点（`cur`）和前一个节点（`prev`）。

以下是删除链表节点的三种情况：

![](img/c1f9de640ca21fa8ea94b348a48d2b49_5.png)

![](img/c1f9de640ca21fa8ea94b348a48d2b49_6.png)

1.  **删除中间节点**：这是最简单的情况。找到目标节点后，只需将前一个节点（`prev`）的 `next` 指针指向当前节点（`cur`）的下一个节点（`cur->next`），从而绕过要删除的节点。最后释放被删除节点的内存。
    ```
    prev->next = cur->next;
    free(cur->data); // 假设存储了数据
    free(cur);
    ```

![](img/c1f9de640ca21fa8ea94b348a48d2b49_8.png)

2.  **删除头节点**：当要删除的节点是链表的第一个节点时，前一个节点（`prev`）为 `NULL`。此时，需要将链表的头指针（`head`）指向当前节点的下一个节点（`cur->next`）。
    ```
    if (prev == NULL) {
        head = cur->next;
        free(cur->data);
        free(cur);
    }
    ```

![](img/c1f9de640ca21fa8ea94b348a48d2b49_10.png)

3.  **删除尾节点**：当要删除的节点是链表的最后一个节点时，当前节点（`cur`）的 `next` 指针为 `NULL`。此时，需要将前一个节点（`prev`）的 `next` 指针设为 `NULL`，并将链表的尾指针（`tail`）指向前一个节点（`prev`）。
    ```
    if (cur->next == NULL) {
        prev->next = NULL;
        tail = prev;
        free(cur->data);
        free(cur);
    }
    ```

![](img/c1f9de640ca21fa8ea94b348a48d2b49_12.png)

## 双向链表

![](img/c1f9de640ca21fa8ea94b348a48d2b49_14.png)

现在，我们来看看双向链表。双向链表的主要目的是能够轻松地反向遍历链表。在Python中，列表对象的 `reverse()` 方法内部很可能就使用了双向链表。

在双向链表中，每个节点不仅包含指向下一个节点的指针（`next`），还包含指向前一个节点的指针（`prev`）。链表头节点的 `prev` 指针为 `NULL`，尾节点的 `next` 指针为 `NULL`。

以下是双向链表节点的结构定义示例：
```c
struct DLNode {
    char *data;
    struct DLNode *prev;
    struct DLNode *next;
};
```

![](img/c1f9de640ca21fa8ea94b348a48d2b49_16.png)

![](img/c1f9de640ca21fa8ea94b348a48d2b49_17.png)

## 反向遍历双向链表

![](img/c1f9de640ca21fa8ea94b348a48d2b49_19.png)

使用双向链表进行反向遍历非常简单。我们只需要从尾节点（`tail`）开始，沿着 `prev` 指针向前移动即可。

![](img/c1f9de640ca21fa8ea94b348a48d2b49_21.png)

以下是反向遍历的代码逻辑：
```c
struct DLNode *current = tail;
while (current != NULL) {
    printf("%s\n", current->data); // 处理当前节点数据
    current = current->prev; // 移动到前一个节点
}
```

![](img/c1f9de640ca21fa8ea94b348a48d2b49_22.png)

![](img/c1f9de640ca21fa8ea94b348a48d2b49_23.png)

![](img/c1f9de640ca21fa8ea94b348a48d2b49_24.png)

![](img/c1f9de640ca21fa8ea94b348a48d2b49_26.png)

## 联合体（Union）

![](img/c1f9de640ca21fa8ea94b348a48d2b49_28.png)

最后，我们介绍联合体（union）。联合体与结构体（struct）类似，但关键区别在于：**结构体的成员占用不同的内存空间，而联合体的所有成员共享同一块内存空间**。

![](img/c1f9de640ca21fa8ea94b348a48d2b49_30.png)

这意味着，联合体的大小由其最大的成员决定。你可以通过不同的成员名来访问和解释同一块内存数据，这在处理网络协议、硬件寄存器或需要节省内存时非常有用。

以下是一个联合体的定义和使用示例：
```c
union Sample {
    int i;      // 通常占4字节
    char ca[4]; // 占4字节
    float f;    // 通常占4字节
};

union Sample u;
u.i = 42; // 将同一块内存解释为整数并赋值
printf("As integer: %d\n", u.i);
printf("As string: %s\n", u.ca); // 将同一块内存解释为字符数组（可能输出乱码）
u.f = 1.0/3.0; // 将同一块内存重新解释为浮点数并赋值
printf("As float: %f\n", u.f);
```

![](img/c1f9de640ca21fa8ea94b348a48d2b49_32.png)

## 总结

![](img/c1f9de640ca21fa8ea94b348a48d2b49_34.png)

![](img/c1f9de640ca21fa8ea94b348a48d2b49_36.png)

本节课中我们一起学习了链表的高级操作。我们详细分析了从单链表中删除节点的三种情况及其处理方法。接着，我们引入了双向链表的概念，了解了它如何通过 `prev` 和 `next` 两个指针实现高效的反向遍历。最后，我们探讨了联合体（union），理解了它与结构体的核心区别——共享内存，并看到了它在多种数据解释场景下的应用。掌握这些概念将为理解更复杂的数据结构和底层编程打下坚实基础。