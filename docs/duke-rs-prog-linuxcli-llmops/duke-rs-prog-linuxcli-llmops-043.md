# 043：在Rust中使用不同类型的日志

![](img/6a3c23391c20c6783125dcab1b41b008_0.png)

![](img/6a3c23391c20c6783125dcab1b41b008_0.png)

在本节课中，我们将学习如何为Rust命令行工具添加日志功能，特别是如何通过命令行选项来控制日志是输出到终端还是写入到文件。我们将使用`clap`库来解析命令行参数，并使用`env_logger`库来配置日志输出目标。

## 概述

有时，将日志写入文件比输出到终端更有用。本节将演示如何添加一个命令行选项来启用日志文件功能。默认情况下，日志输出到标准错误。我们将添加一个布尔选项，当启用时，日志将被写入文件。

## 添加日志文件选项

上一节我们介绍了基本的日志配置。本节中，我们来看看如何通过命令行参数动态控制日志的输出目标。

首先，我们需要使用`clap`库添加一个命令行选项。以下是具体步骤：

1.  在定义命令行参数的结构体中，添加一个布尔类型的字段。
2.  为该字段添加描述信息，说明其用途是启用日志文件输出。
3.  设置其默认值为`false`，即默认不写入文件。

对应的代码修改如下：
```rust
#[derive(Parser)]
struct Opts {
    // ... 其他字段
    /// 启用日志写入文件
    #[clap(long)]
    log_file: bool,
}
```

## 实现日志文件功能

添加了选项之后，我们需要在`main`函数中根据该选项的值来配置日志记录器。

以下是实现逻辑：

*   如果`log_file`选项为`true`，则创建一个文件并将日志记录器的输出目标指向该文件。
*   我们使用`std::fs::OpenOptions`来创建或追加写入文件。
*   通过`env_logger::Builder`的`target`方法，将输出目标设置为一个`Box`包装的文件句柄。

以下是核心实现代码：
```rust
use std::fs::OpenOptions;
use env_logger::Target;

fn main() {
    let opts = Opts::parse();
    // 初始化日志
    let mut builder = env_logger::Builder::from_default_env();

    if opts.log_file {
        // 创建或打开日志文件
        let file = OpenOptions::new()
            .create(true)
            .append(true)
            .open("blocker.log")
            .unwrap();
        // 将日志目标设置为文件
        builder.target(Target::Pipe(Box::new(file)));
    }

    builder.init();
    // ... 程序后续逻辑
}
```

## 测试功能

代码修改完成后，我们需要测试新功能是否按预期工作。

以下是测试步骤：

1.  不带`--log-file`参数运行程序，日志应正常输出到终端。
2.  带上`--log-file`参数运行程序，终端将不再显示日志信息。
3.  检查当前目录下是否生成了名为`blocker.log`的文件，并且日志内容已写入该文件。

你可以通过以下命令进行测试：
```bash
# 测试终端输出
cargo run -- info video1
# 测试文件输出
cargo run -- --log-file info video1
# 查看日志文件内容
less blocker.log
```

## 总结

![](img/6a3c23391c20c6783125dcab1b41b008_2.png)

![](img/6a3c23391c20c6783125dcab1b41b008_3.png)

本节课中我们一起学习了如何在Rust命令行工具中灵活配置日志输出。我们通过`clap`库添加了一个`--log-file`选项，并在代码中根据该选项的值，使用`env_logger`和`std::fs`将日志动态地输出到终端或文件。这种方法使得程序更易于调试和监控。如果你的`main`函数因此变得复杂，可以考虑将这些配置逻辑提取到独立的函数中，以保持代码清晰。你可以继续添加更多日志语句，以便为用户提供更丰富的运行时信息。