# Rust编程（基础）：P49：定义结构体 🏗️

![](img/c489de60300c14a3bf08fac5f8836fd0_0.png)

在本节课中，我们将要学习如何在Rust中定义结构体。结构体是一种将多个相关数据项组合在一起的方式，类似于其他编程语言中的对象。

## 概述

Rust提供了一种定义结构化数据的方法，你可以将其视为相关项的集合。这类似于在Python、Ruby或Java等语言中创建对象并为其定义一些属性。本节我们将从创建一个结构体开始。

## 定义结构体

要定义一个结构体，我们使用关键字 `struct`。下面我们来定义一个名为 `Person` 的结构体。

```rust
struct Person {
    first_name: String,
    last_name: String,
    age: u8,
}
```

这是定义结构体最基本的方式。这里我们创建了一个名为 `Person` 的结构化数据类型，它包含了与个人相关的属性数据。这是一种组织数据的简洁方法。

## 使用 `#[derive(Debug)]` 属性

现在，我们不会深入探讨如何实例化或创建结构体，这将在后续课程中介绍。但让我们先尝试一个简单的操作：打印整个结构体。

如果我们尝试直接使用 `println!` 宏打印结构体，会遇到错误。这是因为Rust默认不知道如何格式化结构体以进行调试输出。

```rust
// 这会导致编译错误
println!("{:?}", person);
```

为了能够打印整个结构体，我们需要为结构体添加 `#[derive(Debug)]` 属性。这个属性允许我们使用调试格式打印结构体。

```rust
#[derive(Debug)]
struct Person {
    first_name: String,
    last_name: String,
    age: u8,
}
```

添加此属性后，我们就可以使用 `println!("{:?}", person);` 来打印结构体了。

## 结构体字段与类型

在结构体定义中，左边的部分称为**字段**，冒号右边指定的是字段的**类型**。例如，在上面的 `Person` 结构体中：
- `first_name` 字段的类型是 `String`。
- `last_name` 字段的类型也是 `String`。
- `age` 字段的类型是 `u8`，即一个8位无符号整数，这限制了我们可以使用的整数范围。

值得注意的是，我们在这里使用冒号来分隔字段名和类型，而不是等号。这种方式与某些语言中的哈希映射或字典定义类似，例如Python的字典（尽管Python没有类型注解）。

## 示例代码与输出

以下是一个完整的示例，展示了如何定义结构体并打印它：

```rust
#[derive(Debug)]
struct Person {
    first_name: String,
    last_name: String,
    age: u8,
}

fn main() {
    let person = Person {
        first_name: String::from("John"),
        last_name: String::from("Doe"),
        age: 25,
    };
    println!("{:?}", person);
}
```

运行此代码，输出将类似于：
`Person { first_name: "John", last_name: "Doe", age: 25 }`

你可以看到输出清晰地展示了结构体名称及其字段和对应的值。

## 总结

![](img/c489de60300c14a3bf08fac5f8836fd0_2.png)

本节课中我们一起学习了Rust结构体的基础知识。我们了解了如何使用 `struct` 关键字定义结构体，如何通过 `#[derive(Debug)]` 属性使结构体能够被打印，以及结构体字段和类型注解的语法。记住，为了能够使用 `println!` 宏的调试格式打印结构体，添加 `#[derive(Debug)]` 属性是必要的，否则编译器会报错。结构体是组织相关数据的强大工具，我们将在后续课程中继续探索其用法。