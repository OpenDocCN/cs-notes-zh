# Rust编程4-5：49_03_03：使用PyO3创建基础Rust库 🦀🐍

![](img/89eb0ff5ea50f04799032e3dacab3fd4_0.png)

在本节课中，我们将学习如何利用PyO3库，将用Rust编写的高性能代码集成到Python项目中。我们将创建一个计算圆周率π的Rust库，并在Python脚本中调用它。

---

## 概述

混合使用Python和Rust可以让我们在保持Python开发便捷性的同时，利用Rust在性能和内存安全方面的优势。PyO3是一个强大的工具，它允许我们创建Rust库，并将其作为Python模块直接导入和使用。本节我们将通过一个计算π的示例，一步步演示这个过程。

## 项目结构

首先，我们来看一个混合了Python和Rust的项目。当你使用`cargo new`等命令初始化项目时，PyO3会自动生成一些基础结构。项目的核心是一个Rust库文件，它将被编译成Python可以导入的共享对象文件。

## Rust函数实现

上一节我们了解了项目结构，本节中我们来看看具体的Rust函数实现。

以下是我们将在Rust中实现的计算π的函数。这个函数接收一个参数，指定计算π的迭代次数，并返回一个`f64`类型的π的近似值。

```rust
use pyo3::prelude::*;

/// 计算圆周率π的近似值
/// `iterations`: 迭代次数，次数越多结果越精确
#[pyfunction]
fn calculate_pi(iterations: u64) -> f64 {
    let mut pi = 0.0;
    let mut denominator = 1.0;
    let mut operation = 1.0;

    for _ in 0..iterations {
        pi += operation * (4.0 / denominator);
        denominator += 2.0;
        operation *= -1.0;
    }
    pi
}
```

**代码解释**：
1.  我们定义了一个可变的`pi`变量来存储结果。
2.  使用莱布尼茨公式进行迭代计算：`π/4 = 1 - 1/3 + 1/5 - 1/7 + ...`
3.  每次迭代，我们根据公式更新`pi`的值、分母和运算符号。
4.  循环结束后，返回计算得到的`pi`值。

## 创建Python模块

现在，我们需要将这个Rust函数包装成一个Python模块。这是通过PyO3的`#[pymodule]`宏实现的。

```rust
/// 将Rust函数暴露为Python模块
#[pymodule]
fn lib_digits_pi(_py: Python, m: &PyModule) -> PyResult<()> {
    m.add_function(wrap_pyfunction!(calculate_pi, m)?)?;
    Ok(())
}
```

**代码解释**：
1.  `#[pymodule]`宏标记了`lib_digits_pi`函数，这将是生成的共享对象文件的名字。
2.  在函数内部，我们使用`m.add_function`将之前定义的`calculate_pi`函数添加到模块中。
3.  这个模块编译后，可以被Python脚本直接`import`。

## 配置Cargo.toml

项目的依赖和构建配置都在`Cargo.toml`文件中定义。以下是关键部分：

```toml
[package]
name = "lib_digits_pi"
version = "0.1.0"
edition = "2021"

[lib]
name = "lib_digits_pi"
crate-type = ["cdylib"] # 指定生成C动态库，这是Python可导入的关键

[dependencies]
pyo3 = { version = "0.18", features = ["extension-module"] }
```

**配置说明**：
*   `[lib]`部分的`crate-type = ["cdylib"]`至关重要，它指示Cargo生成一个动态链接库（如`.so`文件），而不是默认的Rust静态库。
*   `dependencies`中声明了对`pyo3`库的依赖，并启用了`extension-module`特性。

## 构建与清理

为了简化构建流程，我们可以使用一个`Makefile`。以下是构建和清理的步骤。

以下是`Makefile`中的关键命令：

```makefile
build:
    cargo build --release
    cp target/release/liblib_digits_pi.so ./lib_digits_pi.so

clean:
    cargo clean
    rm -f ./lib_digits_pi.so
```

**命令说明**：
*   `make build`：使用`--release`模式编译Rust项目以获得优化性能，然后将生成的共享库文件复制到项目根目录，方便Python导入。
*   `make clean`：清理`cargo`构建的产物和复制的共享库文件。建议将生成的`.so`文件加入`.gitignore`，不要提交到版本控制。

## 在Python中调用

最后，我们来看如何在Python脚本中导入并使用我们刚刚构建的Rust模块。

首先，创建一个Python脚本（例如`pi.py`），并使其可执行：

```bash
chmod +x pi.py
```

脚本内容如下：

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

import lib_digits_pi

def main():
    # 调用Rust函数计算π，迭代次数为1,000,000
    pi_approximation = lib_digits_pi.calculate_pi(1_000_000)
    print(f"计算得到的π近似值为: {pi_approximation}")

if __name__ == "__main__":
    main()
```

**脚本解释**：
1.  第一行是shebang行，指定用Python 3解释器执行此脚本。
2.  使用`import lib_digits_pi`导入我们编译好的Rust模块。
3.  直接调用模块中的`calculate_pi`函数，就像调用普通Python函数一样。
4.  运行脚本：`./pi.py`，即可看到输出的π的近似值（例如：3.1415916535897743）。

## 总结

![](img/89eb0ff5ea50f04799032e3dacab3fd4_2.png)

本节课中我们一起学习了使用PyO3桥接Rust与Python的全过程。我们从编写一个计算π的Rust函数开始，将其封装为Python模块，配置项目并完成构建，最后在Python脚本中成功调用。这种方法非常适合将计算密集型或内存敏感的任务用Rust实现，同时享受Python生态的灵活性与易用性。通过Docker等工具，你可以轻松地将这种混合应用打包和部署。