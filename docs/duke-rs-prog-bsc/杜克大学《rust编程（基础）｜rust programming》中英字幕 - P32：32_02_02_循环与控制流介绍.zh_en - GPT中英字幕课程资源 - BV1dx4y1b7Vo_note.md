# Rust编程（基础）：P32：循环与控制流介绍 🔄

在本节课中，我们将要学习Rust中的循环与控制流。上一节我们介绍了变量与赋值，本节中我们来看看如何通过循环结构来控制程序的执行流程。

![](img/90b94793cf594d869e031f2ce4d6e610_0.png)

Rust提供了不同类型的循环，包括`while`循环和`for`循环。此外，还有一个名为`loop`的构造。如果你来自Java或Python等语言，可能会觉得有些不同，因为Rust的循环有其独特之处。我们将看到这些差异，并学习如何使用控制语句来跳出循环或匹配特定条件，从而有效地控制执行流程。你将能够编写代码进入循环，并精细地调整它，以决定何时跳出循环或继续执行更多代码。

## 循环类型

以下是Rust中主要的循环类型：

*   **`loop`循环**：这是一个无限循环，除非使用`break`关键字明确中断，否则会一直执行。
*   **`while`循环**：只要给定的条件表达式求值为`true`，就会重复执行代码块。
*   **`for`循环**：主要用于遍历一个集合（如数组、范围或迭代器）中的每个元素。

## 控制流语句

为了有效地管理循环，Rust提供了以下控制流语句：

*   **`break`**：立即终止当前循环。
*   **`continue`**：跳过当前循环迭代的剩余代码，直接开始下一次迭代。

## 代码示例

让我们通过一些简单的代码示例来理解这些概念。

### 使用 `loop`

`loop`关键字会创建一个无限循环。

```rust
let mut count = 0;
loop {
    count += 1;
    println!("Count is: {}", count);
    if count >= 5 {
        break; // 当 count 达到 5 时跳出循环
    }
}
```

### 使用 `while`

`while`循环在条件为真时持续运行。

```rust
let mut number = 3;
while number != 0 {
    println!("{}!", number);
    number -= 1;
}
println!("Liftoff!");
```

### 使用 `for`

`for`循环是遍历集合的首选方式。

```rust
let arr = [10, 20, 30, 40, 50];
for element in arr.iter() {
    println!("The value is: {}", element);
}
// 使用范围(Range)
for number in 1..4 { // 不包含4
    println!("{}!", number);
}
```

本节课中我们一起学习了Rust中的循环与控制流。我们了解了三种主要的循环：`loop`、`while`和`for`，并掌握了如何使用`break`和`continue`语句来控制循环的执行。理解这些结构是编写能够重复执行任务并根据条件做出决策的程序的基础。