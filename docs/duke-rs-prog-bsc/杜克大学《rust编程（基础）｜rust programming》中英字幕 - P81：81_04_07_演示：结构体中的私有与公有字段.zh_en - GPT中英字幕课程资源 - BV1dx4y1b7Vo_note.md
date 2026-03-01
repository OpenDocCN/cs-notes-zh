# Rust编程（基础）：P81：演示：结构体中的私有与公有字段 🏗️

![](img/e18daefc89c544240e60429498d80ba4_0.png)

在本节课中，我们将学习如何控制Rust结构体中字段的访问权限，即区分私有字段与公有字段。我们将通过创建一个配置模块来演示这一概念，并了解如何通过文档测试来验证我们的代码。

## 概述

上一节我们介绍了如何使用文档测试以及如何控制模块和项的公开与私有范围。本节中，我们将实际创建一个新的模块，并定义一个包含私有和公有字段的结构体，以此来演示Rust中的访问控制机制。

## 创建配置模块

首先，我们创建一个名为 `config.rs` 的新模块。这个模块将包含应用程序的配置选项。

```rust
pub mod config {
    // 配置内容将在这里定义
}
```

## 定义枚举

在配置模块中，我们首先定义两个枚举，用于表示日志级别和日志输出目标。

以下是日志级别枚举的定义：

```rust
pub enum LogLevel {
    Debug,
    Info,
    Error,
}
```

接下来，我们定义日志输出目标枚举：

```rust
pub enum LogOutput {
    StdOut,
    StdErr,
    File(String),
}
```

## 定义结构体

现在，我们定义一个名为 `Logging` 的结构体，它将包含日志配置的具体字段。

```rust
pub struct Logging {
    enabled: bool,
    level: LogLevel,
    destination: LogOutput,
}
```

## 为结构体实现方法

为了能够方便地创建 `Logging` 结构体的实例，我们为其实现一个构造函数 `new`。

```rust
impl Logging {
    pub fn new() -> Self {
        Logging {
            enabled: false,
            level: LogLevel::Info,
            destination: LogOutput::StdOut,
        }
    }
}
```

## 添加文档和示例

为了验证我们的代码，并为使用者提供参考，我们为结构体添加文档注释和示例。

以下是结构体的文档注释和一个使用示例：

```rust
/// 该结构体包含用于控制日志的配置选项。
///
/// # 示例
///
/// ```
/// use crate::config::Logging;
///
/// let config = Logging::new();
/// ```
pub struct Logging {
    enabled: bool,
    level: LogLevel,
    destination: LogOutput,
}
```

我们还可以添加另一个示例，展示如何使用自定义值创建结构体实例：

```rust
/// # 使用自定义值创建的示例
///
/// ```
/// use crate::config::{Logging, LogLevel, LogOutput};
///
/// let config = Logging {
///     enabled: true,
///     level: LogLevel::Debug,
///     destination: LogOutput::File("log.txt".to_string()),
/// };
/// ```
```

## 理解访问控制问题

当我们运行文档测试时，可能会遇到编译错误，提示结构体的字段是私有的。这是因为在Rust中，结构体的字段默认是私有的，只能在定义它们的模块内部访问。

错误信息可能如下所示：
- `field `enabled` of struct `Logging` is private`
- `field `level` ... is private`
- `field `destination` ... is private`

## 解决方案：使用 `pub` 关键字

为了使结构体的字段能够在模块外部被访问和构造，我们需要使用 `pub` 关键字将它们标记为公有。

修改后的结构体定义如下：

```rust
pub struct Logging {
    pub enabled: bool,
    pub level: LogLevel,
    pub destination: LogOutput,
}
```

进行此更改后，文档测试应该能够顺利通过。这演示了如何通过 `pub` 关键字来控制对结构体字段的访问。

## 灵活控制访问权限

Rust的访问控制非常灵活。你可以根据需求，只将部分字段设为公有，而将其他字段保持私有。例如，如果你不希望使用者直接修改 `destination` 字段，可以将其保持为私有，并通过提供公有方法来间接修改或访问它。

```rust
pub struct Logging {
    pub enabled: bool,
    pub level: LogLevel,
    destination: LogOutput, // 保持私有
}

impl Logging {
    pub fn set_destination(&mut self, dest: LogOutput) {
        self.destination = dest;
    }
}
```

## 枚举的访问控制

需要注意的是，枚举变体（如 `LogLevel::Debug`）的访问控制与结构体字段类似。如果枚举本身是公有的，但其变体在模块外部被用于构造一个结构体（该结构体在模块外部），那么这些变体也必须是公有的，或者通过其他公有接口来使用。

## 总结

本节课中，我们一起学习了Rust结构体中字段的访问控制。我们了解到：
1.  结构体字段默认是**私有**的。
2.  使用 `pub` 关键字可以将字段标记为**公有**，从而允许在定义它们的模块之外进行访问。
3.  你可以根据设计意图，灵活地选择将哪些字段设为公有或私有，以封装内部实现细节。
4.  枚举变体也遵循类似的访问规则。

![](img/e18daefc89c544240e60429498d80ba4_2.png)

建议你通过修改字段的 `pub` 状态、编写文档测试或在模块外部使用这些结构体来实践这一概念，以加深对Rust访问控制机制的理解。