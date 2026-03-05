# 052：向量 🧮

在本节课中，我们将要学习 Rust 中的向量。向量是一种非常强大的集合类型，允许我们在单个数据结构中存储多个值。我们将学习如何创建、修改和访问向量中的元素，并理解其背后的核心概念。

![](img/d119a7c99f7e75f28df603a55faef301_1.png)

![](img/d119a7c99f7e75f28df603a55faef301_2.png)

向量允许我们在一个数据结构中存储多个值，这些值在内存中是连续存放的。与 Python 列表不同，Rust 向量只能存储相同类型的值。当你需要处理一系列项目时，例如文件中的文本行或购物车中的商品价格，向量会非常有用。向量指向的数据存储在**堆**上，这意味着数据量在编译时无需已知，并且可以在程序运行时增长或缩小。

## 创建向量

要创建一个新的空向量，我们使用 `Vec::new` 函数。创建空向量时需要指定类型，因为 Rust 没有关于该向量的信息，需要提前知道它要保存的类型。

![](img/d119a7c99f7e75f28df603a55faef301_4.png)

```rust
let v: Vec<i32> = Vec::new();
```

![](img/d119a7c99f7e75f28df603a55faef301_5.png)

![](img/d119a7c99f7e75f28df603a55faef301_6.png)

![](img/d119a7c99f7e75f28df603a55faef301_7.png)

Rust 还提供了一个用于创建向量的宏 `vec!`，这在你想创建一个非空向量时非常方便。

```rust
let v = vec![1, 2, 3];
```

![](img/d119a7c99f7e75f28df603a55faef301_9.png)

![](img/d119a7c99f7e75f28df603a55faef301_10.png)

## 修改向量

![](img/d119a7c99f7e75f28df603a55faef301_12.png)

上一节我们介绍了如何创建向量，本节中我们来看看如何修改它。要修改向量，首先需要将其声明为可变的。

以下是向向量中添加和移除元素的方法：
*   使用 `push` 方法在向量末尾添加元素。
*   使用 `pop` 方法移除并返回向量中的最后一个元素。`pop` 返回一个 `Option<T>` 类型，因为如果向量为空，它将返回 `None`。

```rust
let mut numbers = vec![0];
numbers.push(1);
numbers.push(2);
numbers.push(3);

let popped = numbers.pop(); // 返回 Some(3)
```

![](img/d119a7c99f7e75f28df603a55faef301_14.png)

![](img/d119a7c99f7e75f28df603a55faef301_15.png)

![](img/d119a7c99f7e75f28df603a55faef301_16.png)

![](img/d119a7c99f7e75f28df603a55faef301_18.png)

## 访问向量元素

在 Rust 中，有两种方法可以引用向量中存储的值：通过索引或通过 `get` 方法。

以下是两种访问方式的区别：
*   **索引访问**：使用 `&v[index]`。如果索引越界，程序会**panic**（崩溃）。
*   **`get` 方法访问**：使用 `v.get(index)`。它返回一个 `Option<&T>` 类型（例如 `Some(&value)` 或 `None`），因此即使索引越界，程序也不会 panic，而是可以优雅地处理。

![](img/d119a7c99f7e75f28df603a55faef301_20.png)

```rust
let numbers = vec![1, 2, 3];
let second = &numbers[1]; // 索引访问，可能 panic
let second_option = numbers.get(1); // get方法访问，返回 Option
```

这两种方法的存在是为了让你决定当访问超出范围的值时程序应如何行为。

## 所有权与借用规则

当程序持有一个有效的引用时，借用检查器会强制执行所有权和借用规则，以确保该引用以及对向量内容的任何其他引用保持有效。

例如，如果你有一个可变向量并获取了其中某个元素的不可变引用，那么在该引用被使用之前，你不能修改向量（例如使用 `push`）。你需要在使用引用**之前**或**之后**修改向量，程序才能编译通过。

![](img/d119a7c99f7e75f28df603a55faef301_22.png)

![](img/d119a7c99f7e75f28df603a55faef301_24.png)

```rust
let mut numbers = vec![1, 2, 3, 4, 5];
let first = &numbers[0]; // 获取不可变引用
// numbers.push(6); // 这里编译错误！不能在持有不可变引用时修改向量
println!("The first element is {}", first); // 先使用引用
numbers.push(6); // 然后修改向量，这样是允许的
```

## 遍历向量

![](img/d119a7c99f7e75f28df603a55faef301_26.png)

![](img/d119a7c99f7e75f28df603a55faef301_27.png)

我们可以使用 `for` 循环来遍历向量中的所有值。

以下是遍历向量的两种方式：
*   **不可变遍历**：迭代对每个元素的不可变引用。
*   **可变遍历**：迭代对每个元素的可变引用，从而可以在遍历时修改它们。使用 `*` 解引用运算符来获取并修改值。

```rust
// 不可变遍历
let people = vec!["Bob", "James", "Sandra"];
for person in &people {
    println!("{}", person);
}

![](img/d119a7c99f7e75f28df603a55faef301_29.png)

![](img/d119a7c99f7e75f28df603a55faef301_30.png)

![](img/d119a7c99f7e75f28df603a55faef301_31.png)

// 可变遍历
let mut numbers = vec![1, 2, 3];
for n in &mut numbers {
    *n += 10; // 解引用并修改值
}
// numbers 现在是 [11, 12, 13]
```

## 在向量中存储多种类型

向量只能存储单一类型。但是，有一个变通方法：使用枚举。因为枚举的变体可以定义不同的关联数据类型，所以我们可以创建一个包含不同枚举变体的向量，从而间接存储“不同类型”的值。

![](img/d119a7c99f7e75f28df603a55faef301_33.png)

![](img/d119a7c99f7e75f28df603a55faef301_34.png)

![](img/d119a7c99f7e75f28df603a55faef301_35.png)

![](img/d119a7c99f7e75f28df603a55faef301_36.png)

![](img/d119a7c99f7e75f28df603a55faef301_37.png)

![](img/d119a7c99f7e75f28df603a55faef301_38.png)

Rust 需要在编译时知道向量中将包含哪些类型，因为它需要确切地知道堆上需要多少内存来存储每个元素。

![](img/d119a7c99f7e75f28df603a55faef301_39.png)

```rust
#[derive(Debug)] // 为枚举派生Debug trait以便打印
enum Value {
    Int(i32),
    Float(f64),
    Text(String),
}

![](img/d119a7c99f7e75f28df603a55faef301_41.png)

![](img/d119a7c99f7e75f28df603a55faef301_42.png)

![](img/d119a7c99f7e75f28df603a55faef301_43.png)

let mut values = vec![
    Value::Float(std::f64::consts::PI),
    Value::Int(42),
];
values.push(Value::Text(String::from("Bob")));
```

![](img/d119a7c99f7e75f28df603a55faef301_45.png)

本节课中我们一起学习了 Rust 向量的核心知识。我们了解了向量是一种在堆上存储同类型数据集合的方式，学习了如何用 `Vec::new` 和 `vec!` 宏创建向量，如何使用 `push` 和 `pop` 修改向量，以及通过索引和 `get` 方法安全地访问元素。我们还探讨了遍历向量的方法，并了解了借用规则如何应用于向量引用。最后，我们看到了如何使用枚举在向量中间接存储多种类型。向量是 Rust 中处理数据集合的基础工具，掌握它们对后续学习至关重要。