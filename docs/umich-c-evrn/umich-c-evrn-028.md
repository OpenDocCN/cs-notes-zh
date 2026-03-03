# 028：在C语言中实现Python列表(list)类 📝

![](img/cc56c3410e8fbc79ccfde75360d6543a_0.png)

![](img/cc56c3410e8fbc79ccfde75360d6543a_2.png)

在本节课中，我们将学习如何在C语言中模拟实现Python的列表（list）类。我们将从零开始构建一个链表结构，并为其实现创建、添加、查找、打印和销毁等核心功能。通过这个过程，你将深入理解面向对象思想在C语言中的应用以及动态内存管理的细节。

## 从Python到C：列表功能对比 🔄

上一节我们探讨了字符串对象，本节我们来看看如何构建一个列表对象。首先，对比一下Python列表和我们将要在C中实现的列表的基本操作。

![](img/cc56c3410e8fbc79ccfde75360d6543a_4.png)

![](img/cc56c3410e8fbc79ccfde75360d6543a_5.png)

在Python中，我们这样使用列表：
```python
lst = []
lst.append("hello world")
print(lst)
lst.append("catchphrase")
print(lst)
lst.append("Brian")
print(lst)
print(len(lst))
print(lst.index("Brian"))
if "Bob" in lst:
    print(lst.index("Bob"))
else:
    print("Bob not found")
```

![](img/cc56c3410e8fbc79ccfde75360d6543a_7.png)

![](img/cc56c3410e8fbc79ccfde75360d6543a_9.png)

而在我们的C实现中，对应的操作将如下所示：
```c
PList_t *lst = pylist_new();
pylist_append(lst, "hello world");
pylist_print(lst);
pylist_append(lst, "catchphrase");
pylist_print(lst);
pylist_append(lst, "Brian");
pylist_print(lst);
printf("%d\n", pylist_len(lst));
printf("%d\n", pylist_index(lst, "Brian"));
printf("%d\n", pylist_index(lst, "Bob")); // 返回-1表示未找到
pylist_del(lst);
```

![](img/cc56c3410e8fbc79ccfde75360d6543a_10.png)

主要区别在于，在C版本中，我们通过函数调用（如 `pylist_append`）来操作列表对象，并且需要手动管理内存（最后调用 `pylist_del`）。此外，查找操作 `pylist_index` 在未找到元素时会返回 `-1`，而不是像Python那样抛出异常。

## 构建列表对象：数据结构设计 🏗️

现在，我们从列表的使用者转变为构建者。我们的任务是设计数据结构并动态分配所需内存，将实现细节封装在对象内部，这正是面向对象编程的重要思想。

![](img/cc56c3410e8fbc79ccfde75360d6543a_12.png)

![](img/cc56c3410e8fbc79ccfde75360d6543a_13.png)

以下是实现所需的核心数据结构。

![](img/cc56c3410e8fbc79ccfde75360d6543a_15.png)

首先，定义链表中的节点结构 `Lnode_t`：
```c
typedef struct Lnode {
    char *text;          // 指向存储字符串的指针
    struct Lnode *next;  // 指向下一个节点的指针
} Lnode_t;
```
*   `text`： 指向动态分配的字符串。
*   `next`： 指向链表中下一个节点的指针。这是一个约定俗成的命名。

接着，定义列表本身的结构 `PList_t`，它管理整个链表：
```c
typedef struct PList {
    Lnode_t *head; // 指向链表第一个节点的指针
    Lnode_t *tail; // 指向链表最后一个节点的指针
    int count;     // 记录列表中元素的数量
} PList_t;
```
*   `head`： 指向链表头节点。
*   `tail`： 指向链表尾节点，便于在末尾快速添加元素。
*   `count`： 记录当前列表中的元素个数。

## 核心方法实现 ⚙️

![](img/cc56c3410e8fbc79ccfde75360d6543a_17.png)

了解了数据结构后，我们来看看如何实现列表的核心操作方法。

![](img/cc56c3410e8fbc79ccfde75360d6543a_18.png)

![](img/cc56c3410e8fbc79ccfde75360d6543a_19.png)

### 创建与销毁列表

`pylist_new` 函数负责创建一个新的空列表：
```c
PList_t *pylist_new(void) {
    PList_t *p = (PList_t *)malloc(sizeof(PList_t));
    p->head = NULL;
    p->tail = NULL;
    p->count = 0;
    return p;
}
```
该函数分配 `PList_t` 结构所需的内存（约20字节），并将 `head`、`tail` 初始化为 `NULL`，`count` 初始化为0。

![](img/cc56c3410e8fbc79ccfde75360d6543a_21.png)

![](img/cc56c3410e8fbc79ccfde75360d6543a_22.png)

`pylist_del` 函数则负责安全地销毁列表并释放所有内存。这比创建要复杂，因为我们需要按正确顺序释放所有嵌套分配的内存。

释放动态内存的顺序至关重要，必须从“树叶”（最内层的数据）向“树根”（外层结构）进行。以下是 `pylist_del` 的逻辑步骤：
1.  从 `head` 开始遍历链表。
2.  对于每个节点 (`cur`)：
    a. 先释放该节点存储的字符串 (`cur->text`)。
    b. 保存下一个节点的地址 (`next = cur->next`)。
    c. 释放当前节点本身 (`free(cur)`)。
    d. 将 `cur` 移动到下一个节点 (`cur = next`)。
3.  循环结束后，所有节点和字符串都已释放，最后释放列表结构本身 (`free(self)`)。

对于一个包含三个节点（字符串分别为"C"、"is"、"fun"）的列表，释放顺序将是：字符串"C" -> 第一个节点 -> 字符串"is" -> 第二个节点 -> 字符串"fun" -> 第三个节点 -> 列表结构本身。

![](img/cc56c3410e8fbc79ccfde75360d6543a_24.png)

### 实现Python风格的打印输出

接下来，我们实现 `pylist_print` 函数，目标是让输出格式与Python列表完全一致，例如：`['hello world', 'catchphrase', 'Brian']`。

![](img/cc56c3410e8fbc79ccfde75360d6543a_26.png)

具体要求如下：
*   以左方括号 `[` 开始。
*   每个字符串用单引号 `'` 包围。
*   元素间用逗号和空格 `, ` 分隔。
*   以右方括号 `]` 结束。

**实现提示**： 在C语言中，不要尝试拼接字符串再来输出，因为我们无法预知字符串的长度。更有效的方法是直接使用 `printf` 在循环中逐步输出。记住，`printf` 不会自动添加换行符，除非你明确使用 `\n`。你可以通过组合使用 `printf("[")`、`printf("'%s'", cur->text)`、`printf(", ")` 等语句来实现目标格式。这大约需要10行代码。

![](img/cc56c3410e8fbc79ccfde75360d6543a_28.png)

![](img/cc56c3410e8fbc79ccfde75360d6543a_29.png)

### 其他实用方法

此外，我们还需要实现其他几个方法：

*   `pylist_len`： 返回列表长度。这个方法非常简单，直接返回 `PList_t` 结构中的 `count` 字段即可。
*   `pylist_index`： 查找给定字符串在列表中的位置（索引）。实现方式是通过循环遍历链表，将每个节点的 `text` 与目标字符串进行比较（使用 `strcmp`）。如果找到，则返回当前计数（从0开始）；如果遍历完仍未找到，则返回 `-1`。
*   `pylist_append`： 在列表末尾添加一个新元素。这个操作涉及创建新节点、分配字符串内存、更新链表尾指针和计数器。如果你已经学习过第6章关于链表的內容，应该对此很熟悉。

## 功能测试与总结 🎯

最后，让我们用一段测试代码来验证我们实现的列表类的功能，它直接对应本节开头展示的Python代码逻辑：

```c
PList_t *lst = pylist_new();
pylist_append(lst, "hello world");
pylist_print(lst);
pylist_append(lst, "catchphrase");
pylist_print(lst);
pylist_append(lst, "Brian");
pylist_print(lst);
printf("%d\n", pylist_len(lst));
printf("%d\n", pylist_index(lst, "Brian"));
printf("%d\n", pylist_index(lst, "Bob"));
pylist_del(lst);
```

![](img/cc56c3410e8fbc79ccfde75360d6543a_31.png)

![](img/cc56c3410e8fbc79ccfde75360d6543a_32.png)

运行这段代码，其输出将与Python版本高度相似（除了将“Bob not found”替换为索引值 `-1`）。这表明我们已经成功在C语言中构建了一个模拟Python列表行为的对象。

![](img/cc56c3410e8fbc79ccfde75360d6543a_33.png)

![](img/cc56c3410e8fbc79ccfde75360d6543a_34.png)

![](img/cc56c3410e8fbc79ccfde75360d6543a_35.png)

![](img/cc56c3410e8fbc79ccfde75360d6543a_36.png)

![](img/cc56c3410e8fbc79ccfde75360d6543a_38.png)

**本节课总结**：
我们一起学习了如何在C语言中模拟实现Python的列表类。我们设计了 `Lnode_t` 和 `PList_t` 数据结构来构建链表，并实现了 `new`、`del`、`append`、`index`、`len` 和 `print` 等核心方法。重点掌握了面向对象封装的思想以及动态内存分配与释放的正确顺序。通过这个练习，你实际上走过了Python创始人Guido van Rossum在构建列表对象时类似的思考路径。

![](img/cc56c3410e8fbc79ccfde75360d6543a_40.png)

![](img/cc56c3410e8fbc79ccfde75360d6543a_42.png)

接下来，我们将运用这些知识，挑战实现更复杂的数据结构——字典（dictionary）。