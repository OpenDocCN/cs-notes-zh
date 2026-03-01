# Rust编程（基础）：P50：创建结构体实例 🏗️

![](img/a31289694d46458fcbbe3cf959badf90_0.png)

在本节课中，我们将学习如何创建结构体（struct）实例，并为其字段赋值。我们还会探讨如何访问这些字段，以及如何处理可选字段。

## 概述

上一节我们介绍了结构体的定义。本节中，我们来看看如何实际创建一个结构体实例，为其填充数据，并访问其内部字段。

## 创建结构体实例

首先，让我们创建一个结构体实例。这类似于我们之前为`Person`结构体添加字段值的操作。

以下是创建`Person`结构体实例的步骤：

```rust
let alfredo = Person {
    first_name: String::from("Alfredo"),
    last_name: String::from("Sanchez"),
    age: 25,
};
```

注意，字段`first_name`和`last_name`的类型是`String`，而不是字符串切片`&str`。因此，我们必须使用`String::from()`或`.to_string()`方法将字符串字面量转换为`String`类型，否则会导致编译错误。

## 访问结构体字段

创建实例后，我们可以访问其字段。访问方式很简单，使用点号（`.`）即可。

例如，如果我们想打印一个人的名字：

```rust
println!("The person's first name is: {}", alfredo.first_name);
```

当你将鼠标悬停在`first_name`上时，集成开发环境（如Visual Studio Code）会显示其类型信息，这有助于理解结构体实例的构成。

## 处理必需字段

结构体的所有字段在创建实例时都是必需的。如果你注释掉`age`字段，即使只想使用`first_name`和`last_name`，编译器也会报错，提示缺少结构体字段。

## 使用`Option`类型处理可选字段

有一种方法可以部分解决这个问题，即使用`Option`类型。`Option`类型表示一个值可能存在（`Some`），也可能不存在（`None`）。

以下是使用`Option`类型定义`age`字段的方法：

```rust
struct Person {
    first_name: String,
    last_name: String,
    age: Option<u32>, // age 现在是可选的
}
```

现在，创建实例时，你可以将`age`设置为`None`：

```rust
let alfredo = Person {
    first_name: String::from("Alfredo"),
    last_name: String::from("Sanchez"),
    age: None,
};
```

或者，如果你想为`age`提供一个值，必须使用`Some`包装：

```rust
let alfredo = Person {
    first_name: String::from("Alfredo"),
    last_name: String::from("Sanchez"),
    age: Some(23), // 使用 Some 包装值
};
```

这样，`age`字段就可以灵活地表示“有值”或“无值”的状态。

## 总结

![](img/a31289694d46458fcbbe3cf959badf90_2.png)

本节课中我们一起学习了如何创建和初始化结构体实例，访问其字段，以及使用`Option`类型来处理可选字段。这些是使用Rust结构体的基础，掌握它们对后续学习至关重要。