# Rust编程（基础）：P48：结构化数据介绍 🏗️

![](img/39525d4ef2ec1472fec812cf16ec6e75_0.png)

在本节课中，我们将要学习Rust中用于组织相似数据的核心概念——结构体（`struct`）。我们将了解如何定义结构体、如何使用它们，并初步接触与之相关的便捷功能。

## 结构体的概念

Rust通过结构体（`struct`）来组织和归类相似的数据。如果你有Java背景，可以将其类比为Java中的对象；如果你熟悉Python，则可以将其想象为字典（`dict`）或哈希映射。虽然不完全相同，但其核心思想都是以结构化的方式组织数据。

## 定义与使用结构体

上一节我们介绍了结构体的基本概念，本节中我们来看看如何具体定义和使用一个结构体。

以下是一个定义结构体的基本语法示例：

```rust
struct User {
    username: String,
    email: String,
    sign_in_count: u64,
    active: bool,
}
```

定义好结构体后，我们可以创建它的实例：

```rust
let user1 = User {
    email: String::from("someone@example.com"),
    username: String::from("someusername123"),
    active: true,
    sign_in_count: 1,
};
```

## 结构体的关联函数

Rust为结构体提供了一种特殊的实现，允许我们创建类似于构造函数的关联函数。这使我们能够便捷地创建结构体实例，而无需每次都从头手动构建。

以下是如何为结构体定义关联函数的示例：

```rust
impl User {
    fn new(email: String, username: String) -> User {
        User {
            email,
            username,
            active: true,
            sign_in_count: 1,
        }
    }
}

// 使用关联函数创建实例
let user2 = User::new(String::from("another@example.com"), String::from("anotheruser"));
```

## 结构体的常见操作模式

创建、定义结构体以及与它交互的方式有很多种。我们将尝试涵盖你在开发Rust程序时最常见的一些模式。

以下是几种常见的结构体使用模式：

1.  **字段初始化简写**：当变量名与字段名相同时，可以简化初始化语法。
2.  **结构体更新语法**：使用`..`语法基于一个实例快速创建另一个实例。
3.  **元组结构体**：没有具体字段名，只有字段类型的结构体。
4.  **类单元结构体**：没有任何字段的结构体，常用于在泛型中标记类型。

## 总结

本节课中我们一起学习了Rust中结构体（`struct`）的基础知识。我们了解了结构体是用于组织相似数据的结构化方式，学习了如何定义结构体、创建其实例，并初步接触了通过`impl`块定义关联函数来便捷地构造实例。掌握结构体是理解Rust数据建模的关键第一步。