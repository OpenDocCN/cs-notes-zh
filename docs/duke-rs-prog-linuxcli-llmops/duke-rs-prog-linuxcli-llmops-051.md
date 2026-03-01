# 051：理解PyO3中的Rust所有权模型 🦀

![](img/c1289d6c167a25f2bbc0212c1e5c1059_0.png)

![](img/c1289d6c167a25f2bbc0212c1e5c1059_2.png)

在本节课中，我们将学习如何通过PyO3库，将Rust独特的所有权模型与Python结合使用。我们将通过一个具体的项目示例，展示如何在Python脚本中操作Rust的数据结构，并理解其背后的所有权和可变性规则。

## 概述

Rust以其独特的所有权系统而闻名，该系统确保了内存安全和无数据竞争。然而，Python的动态特性意味着其变量默认是可变的。通过PyO3，我们可以将Rust的安全特性暴露给Python，从而在Python环境中利用Rust的强类型和所有权优势。本节将解析一个名为`ownership_py_rust`的项目，演示如何实现这一集成。

## 项目结构解析

首先，让我们查看项目的核心代码文件`src/lib.rs`。以下是该文件的主要内容及其功能。

### Rust结构体与实现

我们使用`#[pyclass]`宏定义了一个可供Python使用的Rust结构体。

```rust
#[pyclass]
struct NumbersList {
    numbers: Vec<i32>,
}
```

这个结构体包含一个`i32`类型的向量。接下来，我们为其实现方法。

```rust
#[pymethods]
impl NumbersList {
    #[new]
    fn new() -> Self {
        NumbersList { numbers: Vec::new() }
    }

    fn add_number(&mut self, number: i32) {
        self.numbers.push(number);
        println!("插入数字: {}", number);
    }

    fn len(&self) -> usize {
        self.numbers.len()
    }

    fn clear(&mut self) {
        self.numbers.clear();
        println!("列表已清空");
    }
}
```

在上面的代码中，我们实现了几个关键方法：
*   `new`: 构造函数，用于创建新的`NumbersList`实例。
*   `add_number`: 向列表中添加一个数字。注意其参数`&mut self`，这明确表示该方法需要**可变引用**来修改结构体内部数据。这是Rust所有权模型的核心体现，与Python的隐式可变性形成对比。
*   `len`: 返回列表当前长度。它使用`&self`不可变引用，因为此操作不修改数据。
*   `clear`: 清空列表。同样需要可变引用`&mut self`。

### 创建Python模块

最后，我们需要将这些Rust代码包装成一个Python可以导入的模块。

```rust
#[pymodule]
fn ownership_py_rust(_py: Python, m: &PyModule) -> PyResult<()> {
    m.add_class::<NumbersList>()?;
    Ok(())
}
```

`#[pymodule]`宏定义了一个名为`ownership_py_rust`的模块，并将`NumbersList`类添加到其中。这是使用PyO3向Python暴露功能的经典方式。

## 构建与配置

上一节我们介绍了核心的Rust代码，本节中我们来看看如何构建项目以及Python端如何调用。

### Cargo.toml 配置

项目的`Cargo.toml`文件定义了库的名称和依赖。

```toml
[lib]
name = "ownership_py_rust"
crate-type = ["cdylib"]

[dependencies]
pyo3 = { version = "0.15", features = ["extension-module"] }
```

关键配置是`crate-type = ["cdylib"]`，这指示Cargo构建一个动态链接库（如`.so`文件），供Python加载。

### Makefile 构建步骤

项目包含一个`Makefile`，其中定义了构建命令，用于编译Rust库并将其复制到合适的位置以便Python脚本导入。

## Python脚本示例

现在，让我们查看如何使用这个已编译的Rust模块的Python脚本`owner.py`。

以下是脚本的主要操作步骤：

```python
import ownership_py_rust

# 1. 创建 NumbersList 实例
list_instance = ownership_py_rust.NumbersList()

# 2. 向实例中添加数字
list_instance.add_number(5)
list_instance.add_number(10)

# 3. 获取并打印列表长度
print(f"列表长度: {list_instance.len()}")

# 4. 清空列表
list_instance.clear()

# 5. 再次验证列表长度
print(f"清空后列表长度: {list_instance.len()}")
```

这个脚本清晰地演示了集成流程：
1.  **导入模块**：导入我们编译好的`ownership_py_rust`模块。
2.  **创建实例**：实例化`NumbersList`类。
3.  **调用方法**：调用`add_number`方法修改列表，调用`len`方法获取信息，调用`clear`方法清空列表。所有这些操作都通过PyO3桥接到我们之前编写的Rust代码上执行。

## 运行与验证

要运行此示例，首先需要构建Rust库（例如通过`make build`），然后执行Python脚本。

运行`python owner.py`后，预期输出如下：
```
插入数字: 5
插入数字: 10
列表长度: 2
列表已清空
清空后列表长度: 0
```

输出结果验证了：
*   Rust代码（包括`println!`语句）在Python环境中成功执行。
*   数据在Rust和Python之间正确传递和修改。
*   Rust的所有权和可变性规则在后台得到了严格执行（例如，通过`&mut self`确保安全修改）。

## 总结

本节课中我们一起学习了如何利用PyO3将Rust的所有权模型集成到Python中。我们通过一个实际项目，看到了如何：
1.  使用`#[pyclass]`和`#[pymethods]`宏定义Python可用的Rust类和其方法。
2.  在Rust方法中显式声明可变性（`&mut self`），这是Rust安全模型的关键。
3.  使用`#[pymodule]`宏创建Python模块。
4.  在Python脚本中导入并使用该模块，像操作普通Python对象一样操作Rust数据结构。

![](img/c1289d6c167a25f2bbc0212c1e5c1059_4.png)

这种集成方式非常直接，它允许你将Rust为安全性和不可变性而设计的强大功能，通过严格控制的接口暴露给Python脚本。这对于构建需要高安全性或高性能计算的库，并希望其核心逻辑能被Python灵活调用的场景非常有价值。