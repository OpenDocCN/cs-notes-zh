# 050：用 Rust 构建你的第一个真实项目（Grep）🔍

在本节课中，我们将学习如何使用 Rust 构建一个名为 `grep` 的命令行工具。这个工具用于在文本文件中搜索包含特定模式的行。我们将创建一个简化版本，它能够处理搜索模式、多个文件以及大小写不敏感的搜索选项。

![](img/08e3e4950ee4c0131327b3c6bc9de685_1.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_2.png)

## 项目概述与目标 🎯

我们将构建一个命令行工具，其功能是在一个或多个文本文件中搜索包含指定模式的行。程序运行效果如下：在终端中输入 `cargo run`，后跟搜索模式、文件名以及可选的 `-i` 标志（用于启用大小写不敏感搜索）。例如，命令 `cargo run Bob text1.txt -i` 将返回 `text1.txt` 文件中所有包含“Bob”（不区分大小写）的行。

![](img/08e3e4950ee4c0131327b3c6bc9de685_4.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_5.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_6.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_7.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_8.png)

## 第一步：定义配置结构体 ⚙️

![](img/08e3e4950ee4c0131327b3c6bc9de685_10.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_11.png)

首先，我们需要定义一个结构体来存储程序的配置信息。这个结构体将包含搜索模式、要搜索的文件列表以及一个控制是否忽略大小写的标志。

上一节我们介绍了项目的目标，本节中我们来看看如何组织程序的核心配置。

![](img/08e3e4950ee4c0131327b3c6bc9de685_13.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_14.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_15.png)

```rust
struct Config {
    pattern: String,
    files: Vec<String>,
    case_insensitive: bool,
}
```
这里，`Vec<String>` 是一个字符串向量，你可以暂时将其理解为一个可以动态增减元素的数组。我们将在后续课程中详细学习向量。

## 第二步：实现配置的构造函数 🛠️

![](img/08e3e4950ee4c0131327b3c6bc9de685_17.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_19.png)

接下来，我们需要为 `Config` 结构体实现一个构造函数 `new`。这个函数负责解析命令行参数，并返回一个包含有效配置或错误信息的 `Result`。

以下是 `Config::new` 方法需要完成的步骤：

![](img/08e3e4950ee4c0131327b3c6bc9de685_21.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_22.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_23.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_24.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_25.png)

1.  **检查参数数量**：确保用户至少提供了模式和文件名。
2.  **处理标志参数**：识别并处理 `-i` 标志。
3.  **提取非标志参数**：从参数中分离出搜索模式和文件名。
4.  **验证并返回配置**：确保模式已提供，并收集所有文件名。

![](img/08e3e4950ee4c0131327b3c6bc9de685_27.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_28.png)

```rust
impl Config {
    fn new(args: &[String]) -> Result<Config, String> {
        if args.len() < 3 {
            return Err(format!("用法: {} <模式> <文件>... [-i]", args[0]));
        }

        let mut case_insensitive = false;
        let mut non_flag_args: Vec<String> = Vec::new();

        for arg in &args[1..] {
            if arg == "-i" {
                case_insensitive = true;
            } else {
                non_flag_args.push(arg.clone());
            }
        }

        if non_flag_args.is_empty() {
            return Err("错误：未提供模式".to_string());
        }

        let pattern = non_flag_args[0].clone();

        if non_flag_args.len() < 2 {
            return Err("错误：未提供输入文件".to_string());
        }

        let files = non_flag_args[1..].to_vec();

        Ok(Config {
            pattern,
            files,
            case_insensitive,
        })
    }
}
```
代码解析：
*   `args[0]` 通常是程序自身的名称。
*   我们遍历从第二个参数开始的所有参数（`&args[1..]`）。
*   如果遇到 `-i`，则将 `case_insensitive` 设为 `true`。
*   否则，将参数视为非标志参数（模式或文件名）并存入 `non_flag_args` 向量。
*   最后，从 `non_flag_args` 中提取模式和文件列表，构建 `Config` 实例。

![](img/08e3e4950ee4c0131327b3c6bc9de685_29.png)

## 第三步：实现核心搜索函数 🔎

![](img/08e3e4950ee4c0131327b3c6bc9de685_31.png)

现在，我们需要实现两个核心函数：`grep_file` 用于处理单个文件，`grep` 用于在文件内容中逐行搜索模式。

首先，我们实现 `grep` 函数，它负责读取文件的每一行并进行匹配。

![](img/08e3e4950ee4c0131327b3c6bc9de685_33.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_34.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_35.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_36.png)

```rust
use std::io::{BufRead, BufReader};

![](img/08e3e4950ee4c0131327b3c6bc9de685_38.png)

fn grep(reader: &mut BufReader<std::fs::File>, pattern: &str, case_insensitive: bool) {
    let mut line = String::new();

    while let Ok(bytes_read) = reader.read_line(&mut line) {
        if bytes_read == 0 {
            break;
        }

        let matched = if case_insensitive {
            line.to_lowercase().contains(&pattern.to_lowercase())
        } else {
            line.contains(pattern)
        };

        if matched {
            print!("{}", line);
        }

        line.clear();
    }
}
```
代码解析：
*   `BufReader` 提供了高效的缓冲读取。
*   `reader.read_line(&mut line)` 每次读取一行到 `line` 字符串中。
*   如果读取的字节数为0，表示已到达文件末尾，循环终止。
*   根据 `case_insensitive` 标志，决定是否将行内容和模式都转换为小写后再进行包含性检查。
*   如果匹配成功，则打印该行。
*   每次循环后使用 `line.clear()` 清空缓冲区，以便读取下一行。

![](img/08e3e4950ee4c0131327b3c6bc9de685_40.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_42.png)

接着，我们实现 `grep_file` 函数，它打开指定文件并将文件句柄传递给 `grep` 函数。

```rust
use std::fs::File;

![](img/08e3e4950ee4c0131327b3c6bc9de685_44.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_46.png)

fn grep_file(file: &str, config: &Config) -> Result<(), String> {
    let file = match File::open(file) {
        Ok(f) => f,
        Err(e) => return Err(format!("无法打开文件 '{}': {}", file, e)),
    };

    let mut reader = BufReader::new(file);
    grep(&mut reader, &config.pattern, config.case_insensitive);
    Ok(())
}
```
这个函数尝试打开文件，如果成功，则创建 `BufReader` 并调用 `grep` 函数进行搜索；如果失败，则返回一个描述性的错误信息。

![](img/08e3e4950ee4c0131327b3c6bc9de685_48.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_49.png)

## 第四步：组装主函数 🧩

![](img/08e3e4950ee4c0131327b3c6bc9de685_51.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_52.png)

最后，我们需要在 `main` 函数中将所有部分连接起来：收集命令行参数、创建配置、然后对每个文件执行搜索。

![](img/08e3e4950ee4c0131327b3c6bc9de685_54.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_55.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_56.png)

```rust
use std::env;

![](img/08e3e4950ee4c0131327b3c6bc9de685_58.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_59.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_61.png)

fn main() -> Result<(), String> {
    let args: Vec<String> = env::args().collect();
    let config = Config::new(&args)?;

    for file in &config.files {
        if let Err(e) = grep_file(file, &config) {
            eprintln!("处理文件 '{}' 时出错: {}", file, e);
        }
    }

    Ok(())
}
```
代码解析：
*   `env::args().collect()` 获取命令行参数并将其收集到一个 `Vec<String>` 中。
*   `Config::new(&args)?` 调用构造函数，如果出错则使用 `?` 操作符将错误提前返回。
*   遍历配置中的所有文件，对每个文件调用 `grep_file`。如果某个文件处理出错，我们会打印错误信息但不会终止整个程序（这是简化处理）。

## 运行与测试 🚀

![](img/08e3e4950ee4c0131327b3c6bc9de685_63.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_64.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_65.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_66.png)

现在，你可以使用 `cargo run` 来测试你的 `grep` 程序了。

1.  **基本搜索**：`cargo run Bob text1.txt`
2.  **多文件搜索**：`cargo run Bob text1.txt text2.txt`
3.  **大小写不敏感搜索**：`cargo run BOB text1.txt -i`
4.  **搜索短语**：`cargo run "his cat" text1.txt text2.txt`

![](img/08e3e4950ee4c0131327b3c6bc9de685_68.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_69.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_70.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_71.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_72.png)

确保你的项目目录下存在用于测试的 `text1.txt` 和 `text2.txt` 文件。

## 总结 📝

本节课中我们一起学习了如何使用 Rust 构建一个简化版的 `grep` 命令行工具。我们涵盖了以下核心内容：

*   使用 `struct` 组织程序配置。
*   解析命令行参数，包括处理可选标志（`-i`）。
*   使用 `Vec<T>`（向量）来存储动态列表。
*   使用 `File` 和 `BufReader` 进行文件读写。
*   实现逐行读取和字符串匹配的逻辑。
*   在 `main` 函数中整合所有模块，并处理潜在的错误。

![](img/08e3e4950ee4c0131327b3c6bc9de685_74.png)

这个项目虽然基础，但它很好地串联了 Rust 的多个核心概念，如结构体、枚举、错误处理、集合类型和文件 I/O。你可以在此基础上继续扩展功能，例如支持正则表达式、递归目录搜索等。项目的完整源代码可以在相关的 GitHub 仓库中找到。