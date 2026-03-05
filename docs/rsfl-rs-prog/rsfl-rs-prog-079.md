# 079：Rust 中的重复模式 🚀

在本节课中，我们将继续学习 Rust 宏中的重复模式。我们将探讨多重重复、条件重复、计数重复等高级用法，并通过实例展示如何利用这些模式创建灵活且强大的宏。

上一节我们介绍了 Rust 宏中重复模式的基础概念，本节中我们来看看更复杂的重复模式应用。

## 多重重复模式

在 Rust 中，你可以在同一个模式中使用多个重复器，并且它们必须具有相同数量的匹配项。这种模式非常适合处理像键值对这样的结构。

以下是创建一个使用 `hashmap!` 宏的示例：

![](img/705964c04e1873f8171b389f3e5fd375_1.png)

![](img/705964c04e1873f8171b389f3e5fd375_2.png)

![](img/705964c04e1873f8171b389f3e5fd375_3.png)

```rust
let config = hashmap! {
    "timeout" => 30,
    "retries" => 3,
    "debug" => true,
};
println!("Config: {:?}", config);
```

![](img/705964c04e1873f8171b389f3e5fd375_4.png)

![](img/705964c04e1873f8171b389f3e5fd375_5.png)

![](img/705964c04e1873f8171b389f3e5fd375_6.png)

![](img/705964c04e1873f8171b389f3e5fd375_7.png)

运行此代码，输出将显示 `config` 包含我们提供的数据。回到宏定义本身，需要注意的是，`key_expr` 和 `value_expr` 都重复了相同的次数。宏系统确保每个键都对应一个值。这就是宏中键值对的工作方式，也是一种非常常见的模式。

![](img/705964c04e1873f8171b389f3e5fd375_8.png)

![](img/705964c04e1873f8171b389f3e5fd375_9.png)

**注意**：不能只键入 `timeout` 而不提供值，这会导致错误。必须确保同时提供键和值对。

![](img/705964c04e1873f8171b389f3e5fd375_11.png)

## 条件重复

![](img/705964c04e1873f8171b389f3e5fd375_13.png)

条件重复可以使重复的某些部分变为可选。这通过使用问号运算符 `?` 来实现。

以下是一个创建带有可选参数的宏的示例：

```rust
macro_rules! call_with_log {
    ($func:ident($($arg:expr),* $(,)?)) => {
        println!("Calling {} with args: {:?}", stringify!($func), &[$($arg),*]);
        $func($($arg),*)
    };
}

fn greet(name: &str) {
    println!("Hello, {}!", name);
}

![](img/705964c04e1873f8171b389f3e5fd375_15.png)

![](img/705964c04e1873f8171b389f3e5fd375_16.png)

![](img/705964c04e1873f8171b389f3e5fd375_17.png)

![](img/705964c04e1873f8171b389f3e5fd375_18.png)

fn add(a: i32, b: i32) -> i32 {
    a + b
}

![](img/705964c04e1873f8171b389f3e5fd375_19.png)

![](img/705964c04e1873f8171b389f3e5fd375_20.png)

![](img/705964c04e1873f8171b389f3e5fd375_21.png)

fn main() {
    call_with_log!(greet("Alice"));
    println!("Result: {}", call_with_log!(add(1, 2)));
    // 即使有尾随逗号也能工作
    println!("Result: {}", call_with_log!(add(1, 2,)));
}
```

![](img/705964c04e1873f8171b389f3e5fd375_22.png)

![](img/705964c04e1873f8171b389f3e5fd375_24.png)

运行此代码，你会注意到我们同时得到了日志输出和原始函数调用的结果。回到宏定义，这里的问号 `?` 使尾随逗号成为可选。这是宏中一个非常常见的模式，旨在使宏更加灵活和用户友好，允许用户按照自己偏好的风格编写代码。

## 计数重复

有时你需要知道某个模式会重复多少次。你可以通过使用重复器本身来实现这一点。

![](img/705964c04e1873f8171b389f3e5fd375_26.png)

让我们创建一个宏，用于格式化消息并计数：

![](img/705964c04e1873f8171b389f3e5fd375_27.png)

![](img/705964c04e1873f8171b389f3e5fd375_28.png)

```rust
macro_rules! format_with_count {
    ($($item:expr),*) => {{
        let count = 0usize;
        $(let count = count + 1;)* // 对每个重复项递增计数器
        let items = vec![$($item),*];
        (count, items)
    }};
}

![](img/705964c04e1873f8171b389f3e5fd375_30.png)

fn main() {
    let (count, items) = format_with_count!("apple", "banana", "cherry");
    println!("Count: {}, Items: {:?}", count, items);
}
```

![](img/705964c04e1873f8171b389f3e5fd375_32.png)

这个宏的作用是将项目格式化为一个向量并计算其数量。它的工作原理是为每次重复生成一个语句来计数，每次迭代都会递增计数器，最终得到总计数。当你需要知道传递了多少个参数时，这非常有用。

## 创建自定义 Vec 宏

理解了重复模式后，我们现在可以创建一个自定义的 `vec!` 宏。这是一个简化版本：

![](img/705964c04e1873f8171b389f3e5fd375_34.png)

![](img/705964c04e1873f8171b389f3e5fd375_35.png)

![](img/705964c04e1873f8171b389f3e5fd375_36.png)

```rust
macro_rules! my_vec {
    () => {
        Vec::new()
    };
    ($($elem:expr),*) => {
        {
            let mut v = Vec::new();
            $(v.push($elem);)*
            v
        }
    };
}

![](img/705964c04e1873f8171b389f3e5fd375_37.png)

![](img/705964c04e1873f8171b389f3e5fd375_39.png)

fn main() {
    let empty: Vec<i32> = my_vec!();
    let numbers = my_vec!(1, 2, 3, 4, 5);
    println!("Empty: {:?}", empty);
    println!("Numbers: {:?}", numbers);
}
```

运行此代码，我们将得到一个空向量和一个包含那些数字的向量。这演示了向量宏的核心概念。真正的 `vec!` 宏在可能的情况下会预分配容量，但此示例展示了重复模式如何使其能够处理任意数量的参数。

## 生成多个项目

你还可以使用重复模式来生成多个项目，而不仅仅是表达式。

让我们创建一个生成多个常量的宏：

![](img/705964c04e1873f8171b389f3e5fd375_41.png)

![](img/705964c04e1873f8171b389f3e5fd375_42.png)

![](img/705964c04e1873f8171b389f3e5fd375_43.png)

```rust
macro_rules! constants {
    ($($name:ident = $value:expr);*) => {
        $(const $name: i32 = $value;)*
    };
}

![](img/705964c04e1873f8171b389f3e5fd375_44.png)

![](img/705964c04e1873f8171b389f3e5fd375_45.png)

![](img/705964c04e1873f8171b389f3e5fd375_46.png)

constants! {
    MAX_SIZE = 1024;
    DEFAULT_TIMEOUT = 30;
    BUFFER_SIZE = 256;
}

fn main() {
    println!("Max Size: {}", MAX_SIZE);
    println!("Default Timeout: {}", DEFAULT_TIMEOUT);
    println!("Buffer Size: {}", BUFFER_SIZE);
}
```

如你所见，我们定义了 `MAX_SIZE`、`DEFAULT_TIMEOUT` 和 `BUFFER_SIZE`。这里我们生成的是整个常量声明，而不仅仅是表达式。这表明重复模式可以生成任何类型的 Rust 代码，而不仅仅是值，这在定义许多类似项目以减少样板代码时非常有用。

## 常见重复模式

最后，我们展示一些在实际代码中常见的重复模式。

![](img/705964c04e1873f8171b389f3e5fd375_48.png)

以下是几种常见模式：

![](img/705964c04e1873f8171b389f3e5fd375_49.png)

![](img/705964c04e1873f8171b389f3e5fd375_50.png)

![](img/705964c04e1873f8171b389f3e5fd375_51.png)

*   **带可选尾随逗号的列表**：`$($item:expr),* $(,)?`
*   **键值对**：`$($key:expr => $value:expr),*`
*   **交替模式**：类似于键值对，但语法不同，例如 `$($k:ident: $v:expr),*`
*   **带分隔符的嵌套模式**：用于处理更复杂的嵌套结构。
*   **生成多个项目**：用于一次性声明多个常量、函数或结构体。

这些模式涵盖了大多数用例。一旦你理解了它们，就可以根据特定需求进行组合和修改。关键在于理解重复语法如何映射到你想要生成的代码。

![](img/705964c04e1873f8171b389f3e5fd375_53.png)

本节课中我们一起学习了 Rust 宏中重复模式的高级应用，包括多重重复、条件重复、计数重复，以及如何利用这些模式创建自定义宏和生成代码。掌握这些模式将极大地提升你编写灵活、强大宏的能力。