# 022：在Rust中创建和使用模块

![](img/928531a9b1c6b5af861802f0cf0633d9_0.png)

在本节课中，我们将要学习如何在Rust中使用`mod`关键字来创建和组织模块。模块是Rust中管理代码结构、控制可见性的核心机制。我们将从基础定义开始，逐步探讨模块的嵌套、可见性控制，以及它与`use`关键字的区别。

## 模块基础定义

上一节我们介绍了模块的概念，本节中我们来看看如何使用`mod`关键字来定义一个模块。

`mod`关键字允许你创建并定义一个Rust模块。通过模块，你可以将相关的代码组织在一起，并控制其对外部的可见性。例如，在一个库文件（如`lib.rs`）中，你可以这样定义一个模块：

```rust
mod utilities {
    pub struct Color {
        pub red: u8,
        pub green: u8,
        pub blue: u8,
    }
}
```

在这个例子中，我们创建了一个名为`utilities`的模块，并在其中定义了一个公开的`Color`结构体。`pub`关键字用于控制可见性。如果移除`pub`，结构体及其字段将变为私有，无法在模块外部访问。

## 使用模块中的项

定义了模块之后，我们来看看如何在其他代码中使用它。

要使用模块中定义的项，你需要通过模块路径来引用它们。路径使用双冒号`::`作为分隔符。以下是如何在主函数中使用上述`utilities`模块中的`Color`结构体：

```rust
fn main() {
    let color = utilities::Color {
        red: 255,
        green: 0,
        blue: 0,
    };
    println!("Red: {}, Green: {}, Blue: {}", color.red, color.green, color.blue);
}
```

这里，`utilities::Color`表示从`utilities`模块中访问`Color`类型。这种方式让你能够清晰地组织代码，并通过模块路径来访问特定功能。

## 嵌套模块与代码组织

除了基础模块，Rust还支持创建嵌套模块，这有助于进一步组织复杂的代码结构。

你可以在一个模块内部定义子模块。例如，创建一个`shapes`模块，并在其中定义`square`和`rectangle`子模块：

```rust
mod shapes {
    pub mod square {
        pub fn area(side: f64) -> f64 {
            side * side
        }
    }

    pub mod rectangle {
        pub fn area(length: f64, width: f64) -> f64 {
            length * width
        }
    }
}
```

在嵌套模块中，你同样可以定义公开的函数或结构体。使用嵌套模块时，访问路径会相应变长：

```rust
fn main() {
    let square_area = shapes::square::area(5.0);
    let rect_area = shapes::rectangle::area(4.0, 6.0);
    println!("Square area: {}, Rectangle area: {}", square_area, rect_area);
}
```

通过嵌套模块，你可以将代码逻辑划分得更加细致，提高代码的可读性和可维护性。

## `mod`与`use`关键字的区别

在组织代码时，你可能会遇到`mod`和`use`两个关键字，理解它们的区别很重要。

`mod`关键字用于**定义**一个新的模块。它创建了一个包含代码、类型、函数或结构体的命名空间。

`use`关键字则用于将模块中的项**引入**当前作用域，从而简化路径书写。例如，不使用`use`时，你需要写完整的路径：

```rust
let color = utilities::Color { ... };
```

使用`use`关键字后，你可以直接使用项的名称：

```rust
use utilities::Color;

fn main() {
    let color = Color { ... };
}
```

以下是两者的核心区别总结：
*   `mod`：定义和组织代码结构。
*   `use`：引入路径到当前作用域，避免重复书写长路径。

## 总结

![](img/928531a9b1c6b5af861802f0cf0633d9_2.png)

本节课中我们一起学习了Rust模块系统的核心知识。我们首先使用`mod`关键字来定义模块，并了解了如何通过`pub`控制可见性。接着，我们探讨了如何使用模块路径来访问其中定义的项。然后，我们介绍了如何创建嵌套模块来更好地组织复杂代码。最后，我们区分了`mod`（用于定义模块）和`use`（用于引入路径）这两个关键字的用途。掌握这些概念，能够帮助你编写出结构清晰、易于维护的Rust代码。