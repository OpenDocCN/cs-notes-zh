# 004：面向对象的Rust

在本节课中，我们将一起使用Rust实现一个链表。这是一个很好的实践机会，我们将接触到所有权、借用、`Box`智能指针以及面向对象编程等核心概念。

## 概述

![](img/67b74d5773190a9f9823e870d25cb11c_1.png)

![](img/67b74d5773190a9f9823e870d25cb11c_2.png)

我们将从定义链表节点和链表结构体开始，然后逐步实现构造函数、查询方法以及修改链表的方法（如`push`和`pop`）。在整个过程中，我们会看到Rust的所有权和借用规则如何确保内存安全。

## 定义节点和链表结构体

![](img/67b74d5773190a9f9823e870d25cb11c_4.png)

![](img/67b74d5773190a9f9823e870d25cb11c_6.png)

![](img/67b74d5773190a9f9823e870d25cb11c_7.png)

![](img/67b74d5773190a9f9823e870d25cb11c_8.png)

![](img/67b74d5773190a9f9823e870d25cb11c_10.png)

![](img/67b74d5773190a9f9823e870d25cb11c_12.png)

首先，我们需要定义链表的基本构成单元——节点。在Rust中，我们使用`struct`来定义结构体。

![](img/67b74d5773190a9f9823e870d25cb11c_13.png)

![](img/67b74d5773190a9f9823e870d25cb11c_14.png)

![](img/67b74d5773190a9f9823e870d25cb11c_16.png)

![](img/67b74d5773190a9f9823e870d25cb11c_18.png)

![](img/67b74d5773190a9f9823e870d25cb11c_19.png)

![](img/67b74d5773190a9f9823e870d25cb11c_21.png)

![](img/67b74d5773190a9f9823e870d25cb11c_22.png)

![](img/67b74d5773190a9f9823e870d25cb11c_24.png)

```rust
struct Node {
    value: u32,
    next: Option<Box<Node>>,
}
```

![](img/67b74d5773190a9f9823e870d25cb11c_26.png)

![](img/67b74d5773190a9f9823e870d25cb11c_28.png)

这里，`value`字段存储节点的值，我们暂时使用`u32`类型。`next`字段是一个`Option<Box<Node>>`，表示它可能包含一个指向下一个节点的`Box`智能指针，也可能是`None`（表示链表结束）。使用`Box`是因为我们需要在堆上分配节点，并且每个节点需要拥有其下一个节点。

![](img/67b74d5773190a9f9823e870d25cb11c_30.png)

接下来，我们定义链表本身，它包含一个头节点和记录大小的字段。

![](img/67b74d5773190a9f9823e870d25cb11c_32.png)

![](img/67b74d5773190a9f9823e870d25cb11c_33.png)

```rust
struct LinkedList {
    head: Option<Box<Node>>,
    size: usize,
}
```

![](img/67b74d5773190a9f9823e870d25cb11c_35.png)

![](img/67b74d5773190a9f9823e870d25cb11c_36.png)

![](img/67b74d5773190a9f9823e870d25cb11c_38.png)

`head`字段也是一个`Option<Box<Node>>`，因为链表可能为空。`size`字段记录链表中的元素数量。

![](img/67b74d5773190a9f9823e870d25cb11c_40.png)

![](img/67b74d5773190a9f9823e870d25cb11c_41.png)

## 实现构造函数

![](img/67b74d5773190a9f9823e870d25cb11c_43.png)

现在，让我们为`Node`和`LinkedList`实现构造函数（`new`方法）。

![](img/67b74d5773190a9f9823e870d25cb11c_45.png)

![](img/67b74d5773190a9f9823e870d25cb11c_46.png)

![](img/67b74d5773190a9f9823e870d25cb11c_48.png)

首先为`Node`实现：

![](img/67b74d5773190a9f9823e870d25cb11c_50.png)

```rust
impl Node {
    pub fn new(value: u32, next: Option<Box<Node>>) -> Node {
        Node {
            value: value,
            next: next,
        }
    }
}
```

![](img/67b74d5773190a9f9823e870d25cb11c_52.png)

![](img/67b74d5773190a9f9823e870d25cb11c_54.png)

![](img/67b74d5773190a9f9823e870d25cb11c_55.png)

![](img/67b74d5773190a9f9823e870d25cb11c_57.png)

![](img/67b74d5773190a9f9823e870d25cb11c_59.png)

![](img/67b74d5773190a9f9823e870d25cb11c_61.png)

![](img/67b74d5773190a9f9823e870d25cb11c_62.png)

![](img/67b74d5773190a9f9823e870d25cb11c_64.png)

`Node::new`函数接受一个值和一个`next`选项，然后返回构造好的`Node`实例。注意，函数体最后没有分号，这意味着该表达式的结果（即新创建的`Node`）将作为返回值。

![](img/67b74d5773190a9f9823e870d25cb11c_66.png)

![](img/67b74d5773190a9f9823e870d25cb11c_68.png)

接着为`LinkedList`实现：

![](img/67b74d5773190a9f9823e870d25cb11c_70.png)

![](img/67b74d5773190a9f9823e870d25cb11c_72.png)

![](img/67b74d5773190a9f9823e870d25cb11c_74.png)

![](img/67b74d5773190a9f9823e870d25cb11c_76.png)

![](img/67b74d5773190a9f9823e870d25cb11c_78.png)

```rust
impl LinkedList {
    pub fn new() -> LinkedList {
        LinkedList {
            head: None,
            size: 0,
        }
    }
}
```

![](img/67b74d5773190a9f9823e870d25cb11c_80.png)

![](img/67b74d5773190a9f9823e870d25cb11c_81.png)

![](img/67b74d5773190a9f9823e870d25cb11c_82.png)

`LinkedList::new`函数创建一个空的链表，头节点为`None`，大小为0。

![](img/67b74d5773190a9f9823e870d25cb11c_84.png)

![](img/67b74d5773190a9f9823e870d25cb11c_85.png)

![](img/67b74d5773190a9f9823e870d25cb11c_87.png)

## 实现查询方法

![](img/67b74d5773190a9f9823e870d25cb11c_89.png)

![](img/67b74d5773190a9f9823e870d25cb11c_91.png)

![](img/67b74d5773190a9f9823e870d25cb11c_92.png)

有了基本结构后，我们可以实现一些查询方法，例如获取大小和判断是否为空。

![](img/67b74d5773190a9f9823e870d25cb11c_94.png)

![](img/67b74d5773190a9f9823e870d25cb11c_96.png)

![](img/67b74d5773190a9f9823e870d25cb11c_97.png)

![](img/67b74d5773190a9f9823e870d25cb11c_99.png)

![](img/67b74d5773190a9f9823e870d25cb11c_100.png)

以下是`get_size`方法的实现：

![](img/67b74d5773190a9f9823e870d25cb11c_102.png)

![](img/67b74d5773190a9f9823e870d25cb11c_103.png)

```rust
impl LinkedList {
    pub fn get_size(&self) -> usize {
        self.size
    }
}
```

方法第一个参数是`&self`，表示这是一个不可变引用，该方法不会修改链表。它直接返回`size`字段的值。

![](img/67b74d5773190a9f9823e870d25cb11c_105.png)

![](img/67b74d5773190a9f9823e870d25cb11c_106.png)

![](img/67b74d5773190a9f9823e870d25cb11c_108.png)

![](img/67b74d5773190a9f9823e870d25cb11c_109.png)

类似地，实现`is_empty`方法：

![](img/67b74d5773190a9f9823e870d25cb11c_111.png)

![](img/67b74d5773190a9f9823e870d25cb11c_112.png)

![](img/67b74d5773190a9f9823e870d25cb11c_114.png)

![](img/67b74d5773190a9f9823e870d25cb11c_116.png)

![](img/67b74d5773190a9f9823e870d25cb11c_118.png)

![](img/67b74d5773190a9f9823e870d25cb11c_119.png)

![](img/67b74d5773190a9f9823e870d25cb11c_121.png)

![](img/67b74d5773190a9f9823e870d25cb11c_123.png)

```rust
impl LinkedList {
    pub fn is_empty(&self) -> bool {
        self.size == 0
        // 也可以写成：self.head.is_none()
        // 或者：self.get_size() == 0
    }
}
```

![](img/67b74d5773190a9f9823e870d25cb11c_125.png)

![](img/67b74d5773190a9f9823e870d25cb11c_127.png)

![](img/67b74d5773190a9f9823e870d25cb11c_129.png)

![](img/67b74d5773190a9f9823e870d25cb11c_131.png)

![](img/67b74d5773190a9f9823e870d25cb11c_133.png)

![](img/67b74d5773190a9f9823e870d25cb11c_134.png)

![](img/67b74d5773190a9f9823e870d25cb11c_136.png)

![](img/67b74d5773190a9f9823e870d25cb11c_137.png)

## 实现修改方法：`push`

![](img/67b74d5773190a9f9823e870d25cb11c_139.png)

![](img/67b74d5773190a9f9823e870d25cb11c_141.png)

![](img/67b74d5773190a9f9823e870d25cb11c_143.png)

![](img/67b74d5773190a9f9823e870d25cb11c_144.png)

![](img/67b74d5773190a9f9823e870d25cb11c_146.png)

![](img/67b74d5773190a9f9823e870d25cb11c_147.png)

现在，我们来实现一个能修改链表的方法——`push`，它将在链表头部添加一个新元素。

![](img/67b74d5773190a9f9823e870d25cb11c_149.png)

![](img/67b74d5773190a9f9823e870d25cb11c_151.png)

![](img/67b74d5773190a9f9823e870d25cb11c_153.png)

```rust
impl LinkedList {
    pub fn push(&mut self, value: u32) {
        let new_node = Box::new(Node::new(value, self.head.take()));
        self.head = Some(new_node);
        self.size += 1;
    }
}
```

![](img/67b74d5773190a9f9823e870d25cb11c_155.png)

让我们分解一下：
1.  `&mut self`：这是一个可变引用，因为`push`方法需要修改链表。
2.  `self.head.take()`：这是关键的一步。`take`方法作用于`Option`上，它会取出`self.head`当前的值（一个`Option<Box<Node>>`），并在原位置留下`None`。这有效地转移了旧头节点的所有权，使我们能够将其作为新节点的`next`。
3.  我们创建一个新的`Box<Node>`，其`next`指向旧的头部。
4.  将链表的`head`更新为这个新节点。
5.  将`size`加1。

![](img/67b74d5773190a9f9823e870d25cb11c_157.png)

![](img/67b74d5773190a9f9823e870d25cb11c_158.png)

![](img/67b74d5773190a9f9823e870d25cb11c_160.png)

![](img/67b74d5773190a9f9823e870d25cb11c_162.png)

## 实现修改方法：`pop`

![](img/67b74d5773190a9f9823e870d25cb11c_164.png)

![](img/67b74d5773190a9f9823e870d25cb11c_165.png)

接下来，我们实现`pop`方法，它移除并返回链表头部的元素。

![](img/67b74d5773190a9f9823e870d25cb11c_167.png)

![](img/67b74d5773190a9f9823e870d25cb11c_168.png)

![](img/67b74d5773190a9f9823e870d25cb11c_170.png)

![](img/67b74d5773190a9f9823e870d25cb11c_172.png)

![](img/67b74d5773190a9f9823e870d25cb11c_174.png)

```rust
impl LinkedList {
    pub fn pop(&mut self) -> Option<u32> {
        let node = self.head.take()?;
        self.head = node.next;
        self.size -= 1;
        Some(node.value)
    }
}
```

![](img/67b74d5773190a9f9823e870d25cb11c_176.png)

![](img/67b74d5773190a9f9823e870d25cb11c_178.png)

![](img/67b74d5773190a9f9823e870d25cb11c_180.png)

![](img/67b74d5773190a9f9823e870d25cb11c_182.png)

分解步骤：
1.  `self.head.take()?`：再次使用`take`获取当前头节点。`?`操作符是Rust的错误处理语法糖。如果`take()`的结果是`None`（即链表为空），则`?`会提前从函数返回`None`。如果是`Some(node)`，则`node`被解包出来，类型为`Box<Node>`。
2.  将链表的`head`更新为被移除节点的`next`节点。
3.  将`size`减1。
4.  返回被移除节点的值，包装在`Some`中。

![](img/67b74d5773190a9f9823e870d25cb11c_184.png)

![](img/67b74d5773190a9f9823e870d25cb11c_186.png)

![](img/67b74d5773190a9f9823e870d25cb11c_188.png)

## 测试链表功能

![](img/67b74d5773190a9f9823e870d25cb11c_190.png)

![](img/67b74d5773190a9f9823e870d25cb11c_192.png)

![](img/67b74d5773190a9f9823e870d25cb11c_194.png)

让我们编写一些代码来测试我们实现的链表。

![](img/67b74d5773190a9f9823e870d25cb11c_196.png)

![](img/67b74d5773190a9f9823e870d25cb11c_197.png)

![](img/67b74d5773190a9f9823e870d25cb11c_199.png)

![](img/67b74d5773190a9f9823e870d25cb11c_200.png)

```rust
fn main() {
    let mut list = LinkedList::new(); // 必须声明为mut
    for i in 1..10 {
        list.push(i);
    }
    list.display(); // 假设有一个display方法用于打印链表
    println!("List size: {}", list.get_size());
    if let Some(top_value) = list.pop() {
        println!("Popped value: {}", top_value);
    }
    println!("List size after pop: {}", list.get_size());
    list.display();
}
```

![](img/67b74d5773190a9f9823e870d25cb11c_202.png)

![](img/67b74d5773190a9f9823e870d25cb11c_203.png)

![](img/67b74d5773190a9f9823e870d25cb11c_205.png)

![](img/67b74d5773190a9f9823e870d25cb11c_207.png)

![](img/67b74d5773190a9f9823e870d25cb11c_209.png)

![](img/67b74d5773190a9f9823e870d25cb11c_210.png)

这段代码会创建一个链表，依次压入1到9，然后弹出头部元素。你可以观察到链表大小和内容的变化。

![](img/67b74d5773190a9f9823e870d25cb11c_212.png)

![](img/67b74d5773190a9f9823e870d25cb11c_214.png)

## 总结

![](img/67b74d5773190a9f9823e870d25cb11c_216.png)

![](img/67b74d5773190a9f9823e870d25cb11c_217.png)

![](img/67b74d5773190a9f9823e870d25cb11c_219.png)

本节课中，我们一起使用Rust实现了一个简单的链表。我们学习了：

![](img/67b74d5773190a9f9823e870d25cb11c_221.png)

![](img/67b74d5773190a9f9823e870d25cb11c_222.png)

![](img/67b74d5773190a9f9823e870d25cb11c_224.png)

![](img/67b74d5773190a9f9823e870d25cb11c_226.png)

![](img/67b74d5773190a9f9823e870d25cb11c_227.png)

![](img/67b74d5773190a9f9823e870d25cb11c_229.png)

*   如何使用`struct`定义结构体。
*   如何使用`Box<T>`在堆上分配内存并拥有其数据。
*   如何使用`Option<T>`优雅地处理可能为空的值。
*   如何为结构体实现方法（`impl`块），并区分不可变方法（`&self`）和可变方法（`&mut self`）。
*   关键方法`take()`的使用，它允许我们通过可变引用取得`Option`内部值的所有权。
*   `?`操作符在错误处理中的便捷应用。

![](img/67b74d5773190a9f9823e870d25cb11c_231.png)

![](img/67b74d5773190a9f9823e870d25cb11c_233.png)

![](img/67b74d5773190a9f9823e870d25cb11c_235.png)

![](img/67b74d5773190a9f9823e870d25cb11c_237.png)

![](img/67b74d5773190a9f9823e870d25cb11c_239.png)

这个例子综合运用了所有权、借用和生命周期等Rust核心概念，是理解Rust内存安全模型的绝佳实践。你可以基于此代码进一步探索，例如实现迭代器、使其支持泛型等。