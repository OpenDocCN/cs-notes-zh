# 077：深入探索 Rust 宏 🔍

在本节课中，我们将深入探索 Rust 宏的模式匹配。模式匹配是声明式宏工作的核心，它通过匹配代码中的模式来生成新的代码。理解越多的模式，你编写的宏就越强大。我们将通过一系列实际代码中可能用到的例子来学习。

上一节我们介绍了宏的基本语法，本节中我们来看看模式匹配的具体应用。

## 匹配类型标识符

有时，我们希望匹配一个类型来创建类型别名或泛型辅助工具。让我们创建一个生成结果类型别名的宏。

以下是宏的定义：

```rust
macro_rules! result_type {
    ($name:ident = Result<$ok:ty, $err:ty>) => {
        type $name = Result<$ok, $err>;
    };
}
```

![](img/9ccfa8b60feff587b5bb515d85680373_1.png)

我们使用 `macro_rules!` 定义宏，宏名为 `result_type`。模式 `$name:ident = Result<$ok:ty, $err:ty>` 用于匹配一个标识符（作为类型别名名）和两个类型（作为 `Result` 的成功与错误类型）。当匹配成功时，宏会生成对应的类型别名代码。

![](img/9ccfa8b60feff587b5bb515d85680373_2.png)

![](img/9ccfa8b60feff587b5bb515d85680373_3.png)

![](img/9ccfa8b60feff587b5bb515d85680373_4.png)

使用这个宏的方法如下：

![](img/9ccfa8b60feff587b5bb515d85680373_5.png)

![](img/9ccfa8b60feff587b5bb515d85680373_6.png)

![](img/9ccfa8b60feff587b5bb515d85680373_7.png)

```rust
result_type!(MyResult = Result<i32, String>);

![](img/9ccfa8b60feff587b5bb515d85680373_8.png)

fn my_function() -> MyResult {
    Ok(42)
}
```

我们可以创建一个简单的函数，让它返回 `MyResult` 类型。之后，我们就可以像处理普通 `Result` 类型一样处理它。

```rust
fn handle_result() {
    let example: MyResult = Ok(100);
    match example {
        Ok(value) => println!("成功，值为: {}", value),
        Err(e) => println!("错误: {}", e),
    }
}
```

这里，如果匹配到 `Ok`，我们会打印成功的值；如果匹配到 `Err`，则打印错误信息。重要的是，`$ok:ty` 和 `$err:ty` 匹配了类型。这个宏为 `Result` 类型创建了一个类型别名，当你在多处使用相同的 `Result` 类型时，这可以使代码更具可读性。

## 匹配字面量

字面量在需要确保编译时常量时非常有用。让我们创建一个从字面量生成常量的宏。

以下是宏的定义：

![](img/9ccfa8b60feff587b5bb515d85680373_10.png)

![](img/9ccfa8b60feff587b5bb515d85680373_11.png)

![](img/9ccfa8b60feff587b5bb515d85680373_12.png)

```rust
macro_rules! constant_from_literal {
    ($name:ident = $value:literal) => {
        const $name: &str = stringify!($value);
    };
}
```

![](img/9ccfa8b60feff587b5bb515d85680373_13.png)

![](img/9ccfa8b60feff587b5bb515d85680373_14.png)

![](img/9ccfa8b60feff587b5bb515d85680373_15.png)

我们使用 `macro_rules!` 定义宏，宏名为 `constant_from_literal`。这里的关键是使用了 `$value:literal` 说明符，它确保我们只接受实际的字面量，而不是变量。这对于创建必须在编译时已知的常量非常有用。在宏体内，我们使用 `stringify!` 将字面量转换为字符串，并创建一个同名的常量。

![](img/9ccfa8b60feff587b5bb515d85680373_16.png)

![](img/9ccfa8b60feff587b5bb515d85680373_17.png)

使用这个宏的方法如下：

![](img/9ccfa8b60feff587b5bb515d85680373_18.png)

```rust
constant_from_literal!(API_VERSION = "v1.0");
constant_from_literal!(DEFAULT_PORT = 8080);

fn main() {
    println!("API 版本: {}", API_VERSION);
    println!("默认端口: {}", DEFAULT_PORT);
}
```

要使用它，我们只需用我们选择的名字调用宏。从那时起，我们就可以将其用作常量。运行此代码，输出将是 API 版本和默认端口。

## 匹配路径

使用 `path` 说明符匹配路径在处理模块时很有用。让我们创建一个宏来帮助从路径导入和使用项目。

以下是宏的定义：

![](img/9ccfa8b60feff587b5bb515d85680373_20.png)

![](img/9ccfa8b60feff587b5bb515d85680373_21.png)

```rust
macro_rules! use_and_call {
    ($path:path) => {
        println!("正在使用路径: {:?}", $path);
    };
}
```

![](img/9ccfa8b60feff587b5bb515d85680373_22.png)

![](img/9ccfa8b60feff587b5bb515d85680373_23.png)

![](img/9ccfa8b60feff587b5bb515d85680373_24.png)

这里我们创建一个名为 `use_and_call` 的宏，它接受一个路径。在实际场景中，可能会使用这个路径，但在这个例子中，我们只是打印它。

![](img/9ccfa8b60feff587b5bb515d85680373_25.png)

![](img/9ccfa8b60feff587b5bb515d85680373_26.png)

![](img/9ccfa8b60feff587b5bb515d85680373_27.png)

使用这个宏的方法如下：

![](img/9ccfa8b60feff587b5bb515d85680373_28.png)

```rust
use_and_call!(std::collections::HashMap::new);
use_and_call!(std::io::stdout);
```

我们可以使用宏并插入一个路径，例如创建一个新的 `HashMap`，或者使用标准输出。运行此代码，我们将在控制台中看到我们正在使用每个路径。

`path` 说明符匹配限定路径。这在创建与不同模块或 crate 一起工作的宏时很有用，尽管在实践中你通常会直接使用 `use` 语句。

![](img/9ccfa8b60feff587b5bb515d85680373_30.png)

![](img/9ccfa8b60feff587b5bb515d85680373_31.png)

## 匹配代码块

![](img/9ccfa8b60feff587b5bb515d85680373_32.png)

代码块对于创建控制流宏非常强大。让我们创建一个更有用的计时宏，它还会打印正在计时的内容。

以下是宏的定义：

```rust
macro_rules! benchmark {
    ($name:expr, $block:block) => {
        {
            let start = std::time::Instant::now();
            let result = $block;
            let duration = start.elapsed();
            println!("执行 '{}' 耗时: {:?}", $name, duration);
            result
        }
    };
}
```

在这个例子中，我们创建一个 `benchmark` 宏。它接受表达式的名称和代码块。在宏体内，我们获取开始时间，执行代码块，计算耗时，然后打印执行该块所花费的时间，并返回结果。

使用这个宏的方法如下：

```rust
fn main() {
    let total = benchmark!("计算总和", {
        let mut sum = 0;
        for i in 0..1_000_000 {
            sum += i;
        }
        sum
    });
    println!("结果是: {}", total);
}
```

在 `main` 函数中，我们可以创建一些使用 `benchmark` 宏的功能。宏的名称是 `"计算总和"`，里面的代码将 `i` 加到 `total` 很多次。在底部，我们也可以打印结果。运行此代码，输出将显示它花费了约 1.2 毫秒，结果是这个数字。

![](img/9ccfa8b60feff587b5bb515d85680373_34.png)

![](img/9ccfa8b60feff587b5bb515d85680373_35.png)

`$block:block` 匹配一个代码块。这个宏用计时代码和一个标签包装了代码块，使得对代码不同部分进行基准测试变得容易。这是一个你可能最终会实际使用的实用案例。

![](img/9ccfa8b60feff587b5bb515d85680373_36.png)

![](img/9ccfa8b60feff587b5bb515d85680373_37.png)

![](img/9ccfa8b60feff587b5bb515d85680373_38.png)

## 匹配语句

![](img/9ccfa8b60feff587b5bb515d85680373_39.png)

![](img/9ccfa8b60feff587b5bb515d85680373_40.png)

![](img/9ccfa8b60feff587b5bb515d85680373_41.png)

语句对于生成需要多次执行的代码很有用。让我们创建一个重试语句的宏。

以下是宏的定义：

```rust
macro_rules! retry {
    ($max_attempts:expr, $statement:stmt) => {
        {
            let mut attempts = 0;
            loop {
                $statement;
                attempts += 1;
                if attempts >= $max_attempts {
                    break;
                }
            }
        }
    };
}
```

这里我们创建一个名为 `retry` 的宏。表达式 `$max_attempts:expr` 代表最大尝试次数，语句 `$statement:stmt` 代表要执行的语句。在宏体内，我们跟踪尝试次数并创建一个循环。然后我们插入语句。每次运行时，我们将尝试次数加一。如果尝试次数大于或等于最大尝试次数，我们就跳出循环。

使用这个宏的方法如下：

```rust
fn main() {
    let mut counter = 0;
    retry!(3, {
        counter += 1;
        println!("尝试 {}", counter);
    });
}
```

我们创建一个计数器，然后在 `retry` 宏内部调用它，指定尝试次数和我们想要执行的语句。运行此代码，输出应该是“尝试 1”、“尝试 2”和“尝试 3”。

`$statement:stmt` 说明符匹配一个语句。这个例子展示了如何创建一个重试机制，尽管在实践中你可能需要更复杂的错误处理。

![](img/9ccfa8b60feff587b5bb515d85680373_43.png)

![](img/9ccfa8b60feff587b5bb515d85680373_44.png)

![](img/9ccfa8b60feff587b5bb515d85680373_45.png)

## 组合匹配

![](img/9ccfa8b60feff587b5bb515d85680373_46.png)

![](img/9ccfa8b60feff587b5bb515d85680373_47.png)

你可以组合多个匹配来创建强大的宏。让我们创建一个生成带有构造函数的结构体的宏。

以下是宏的定义：

![](img/9ccfa8b60feff587b5bb515d85680373_49.png)

![](img/9ccfa8b60feff587b5bb515d85680373_50.png)

```rust
macro_rules! struct_with_new {
    ($name:ident { $($field_name:ident : $field_type:ty),* $(,)? }) => {
        struct $name {
            $($field_name: $field_type),*
        }
        impl $name {
            fn new($($field_name: $field_type),*) -> Self {
                Self {
                    $($field_name),*
                }
            }
        }
    };
}
```

对于这个例子，我们创建一个名为 `struct_with_new` 的宏。这个宏的作用是创建一个结构体定义以及一个 `new` 构造函数。它匹配一个结构体名称的标识符，然后是一个包含字段定义的块，最后每个字段都有一个名称和一个类型。这比仅仅创建结构体更有用，它还生成了一个方便的构造函数。

使用这个宏的方法如下：

![](img/9ccfa8b60feff587b5bb515d85680373_52.png)

```rust
struct_with_new!(Point {
    x: i32,
    y: i32,
});

![](img/9ccfa8b60feff587b5bb515d85680373_53.png)

![](img/9ccfa8b60feff587b5bb515d85680373_54.png)

fn main() {
    let point = Point::new(3, 4);
    println!("点: x = {}, y = {}", point.x, point.y);
}
```

为了展示它是如何工作的，我们进入 `main` 函数，使用 `struct_with_new` 创建一个 `Point`。然后我们可以使用该结构体创建一个新的点，最后我们可以打印这个点及其值。运行此代码，输出应该是一个值为 3 和 4 的点。

## 匹配特定标记以创建自定义语法

让我们看看如何匹配特定标记来创建自定义语法。创建一个宏，提供一种更清晰的方式来创建键值对。

以下是宏的定义：

```rust
macro_rules! kv {
    ($key:ident => $value:expr) => {
        (stringify!($key), $value)
    };
}
```

这里我们将创建一个名为 `kv` 的宏，它接受一个标识符作为键，一个表达式作为值。它的作用是将它们转换成一个键值对。

![](img/9ccfa8b60feff587b5bb515d85680373_56.png)

![](img/9ccfa8b60feff587b5bb515d85680373_57.png)

使用这个宏的方法如下：

![](img/9ccfa8b60feff587b5bb515d85680373_58.png)

![](img/9ccfa8b60feff587b5bb515d85680373_59.png)

![](img/9ccfa8b60feff587b5bb515d85680373_60.png)

```rust
fn main() {
    let person = "Alice";
    let age = 30;
    let pair1 = kv!(name => person);
    let pair2 = kv!(age => age);
    println!("键值对 1: {:?}", pair1);
    println!("键值对 2: {:?}", pair2);
}
```

![](img/9ccfa8b60feff587b5bb515d85680373_61.png)

![](img/9ccfa8b60feff587b5bb515d85680373_62.png)

![](img/9ccfa8b60feff587b5bb515d85680373_63.png)

我们创建一个名为 Alice 的人，让年龄等于 30。要使用我们的宏，我们只需要调用 `kv!`，提供一个标识符和值。然后为了查看里面有什么，我们可以打印 `pair1` 和 `pair2`。打印后，我们应该会得到这些键值。

![](img/9ccfa8b60feff587b5bb515d85680373_64.png)

![](img/9ccfa8b60feff587b5bb515d85680373_65.png)

这里我们匹配 `=>` 标记，为键值对创建类似 DSL 的语法。宏自动将标识符转换为字符串，这对于配置或日志记录很有用。

## 条件匹配

作为本视频的最后一部分，我们将讨论条件匹配。你可以创建灵活处理不同情况的宏。让我们创建一个处理有无尾随逗号的宏，这是 Rust 宏中的常见模式。

以下是宏的定义：

```rust
macro_rules! create_array {
    ($($element:expr),* $(,)?) => {
        [$($element),*]
    };
}
```

这里我们创建一个名为 `create_array` 的宏。这个宏的作用是允许我们创建带有或不带有尾随逗号的数组。如你所见，这里我们有 `1, 2, 3` 没有尾随逗号，以及 `4, 5, 6,` 带有尾随逗号。很酷的是两者都有效。

使用这个宏的方法如下：

![](img/9ccfa8b60feff587b5bb515d85680373_67.png)

```rust
fn main() {
    let arr1 = create_array!(1, 2, 3);
    let arr2 = create_array!(4, 5, 6,);
    println!("数组 1: {:?}", arr1);
    println!("数组 2: {:?}", arr2);
}
```

![](img/9ccfa8b60feff587b5bb515d85680373_68.png)

![](img/9ccfa8b60feff587b5bb515d85680373_69.png)

![](img/9ccfa8b60feff587b5bb515d85680373_70.png)

我知道这看起来语法很多，但这里重要的是，我们通过 `$(,)?` 告诉 Rust 这个宏应该可选地匹配一个逗号。这使得宏更加灵活和用户友好，无论是否有尾随逗号它都能工作。这是 Rust 宏中一个非常常见的模式。

![](img/9ccfa8b60feff587b5bb515d85680373_71.png)

![](img/9ccfa8b60feff587b5bb515d85680373_72.png)

## 总结

![](img/9ccfa8b60feff587b5bb515d85680373_74.png)

本节课中我们一起深入学习了 Rust 宏的模式匹配。我们从匹配类型标识符开始，学习了如何创建类型别名宏。接着，我们探讨了匹配字面量来生成编译时常量，以及匹配路径来处理模块导入。通过匹配代码块，我们创建了实用的性能基准测试宏。我们还学习了匹配语句来实现重试逻辑，并组合多种匹配来生成带有构造函数的复杂结构体。最后，我们了解了如何匹配特定标记创建自定义语法，以及使用条件匹配使宏更灵活地处理有无尾随逗号的情况。掌握这些模式匹配技巧，将极大地增强你编写强大、灵活且可读性高的 Rust 宏的能力。