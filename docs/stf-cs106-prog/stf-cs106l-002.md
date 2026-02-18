# 斯坦福大学《CS106L：C++编程》课程笔记 - 第2讲：流 (Streams) 📚

![](img/9fab00c46a74e6ad5591779d88bfd206_0.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_1.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_2.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_3.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_5.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_7.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_9.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_10.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_12.png)

在本节课中，我们将要学习C++中一个非常重要的概念：**流 (Streams)**。流是程序与外部世界（如控制台、文件、网络等）进行数据交互的统一接口。我们将从高层次概述开始，然后深入探讨字符串流、状态位以及输入/输出流，最后简要了解流操作符。

---

![](img/9fab00c46a74e6ad5591779d88bfd206_14.png)

## 概述：为什么需要流？ 🤔

我们通常希望程序能与各种外部设备交互，例如键盘、控制台、文件、网络等。流提供了一个统一的接口来处理所有这些交互。无论你是向屏幕打印内容、从文件读取数据，还是通过网络发送信息，都可以使用相似的操作方式。

例如，向控制台输出内容使用 `cout`，其操作符是 `<<`。这个统一的接口抽象了底层复杂的读写过程，让我们只需关注数据的转换和传输。

---

![](img/9fab00c46a74e6ad5591779d88bfd206_16.png)

## C++字符串快速入门 🚀

在深入流之前，我们先快速回顾一下C++中的字符串，因为流经常处理字符串数据。

在C++中，我们使用 `std::string` 类型来表示字符串。

```cpp
std::string str = "hello world";
```

**访问和修改字符**：你可以像访问数组一样访问和修改字符串中的单个字符。C++字符串是零索引的。

```cpp
std::cout << str[1]; // 输出 'e'
str[1] = 'i'; // 将字符串修改为 "hillo world"
```

![](img/9fab00c46a74e6ad5591779d88bfd206_18.png)

**重要区别**：C++中有两种字符串：C风格字符串（`char*` 或 `char[]`）和C++字符串（`std::string`）。在C++编程中，应优先使用 `std::string`，因为它更安全、功能更强大。

---

## 流的高层次概念 🌊

流的核心理念是将程序与外部设备的交互抽象为对一个**字符缓冲区**的读写操作。

当你向流写入数据（例如 `cout << 3.14`）时：
1.  数据（如双精度浮点数 `3.14`）被转换为字符串形式。
2.  字符串被放入流的内部缓冲区。
3.  流负责将缓冲区的内容传输到目标设备（如控制台）。

![](img/9fab00c46a74e6ad5591779d88bfd206_20.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_22.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_24.png)

当你从流读取数据时，过程相反。流会从缓冲区读取字符，并将其转换为你指定的类型（如整数、浮点数）。

![](img/9fab00c46a74e6ad5591779d88bfd206_26.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_28.png)

这种抽象让我们无需关心数据如何具体地显示到屏幕或从文件读取，只需关注与缓冲区的交互。

![](img/9fab00c46a74e6ad5591779d88bfd206_30.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_32.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_34.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_35.png)

---

![](img/9fab00c46a74e6ad5591779d88bfd206_37.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_39.png)

## 字符串流 (String Streams) 🔤

字符串流是最简单的流类型，它不与任何外部设备关联，只用于在内存中进行字符串的转换和格式化。它完美地展示了流的“转换”功能。

主要有两种字符串流：
*   `std::ostringstream`：用于输出（构建字符串）。
*   `std::istringstream`：用于输入（解析字符串）。

### 输出字符串流 (ostringstream)

![](img/9fab00c46a74e6ad5591779d88bfd206_41.png)

输出字符串流允许你将各种类型的数据“写入”到一个字符串缓冲区中。

![](img/9fab00c46a74e6ad5591779d88bfd206_43.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_45.png)

以下是使用 `ostringstream` 的基本步骤：

首先，你需要包含头文件并声明一个 `ostringstream` 对象。

```cpp
#include <sstream> // 字符串流所需的头文件
std::ostringstream oss;
```

![](img/9fab00c46a74e6ad5591779d88bfd206_47.png)

接着，你可以使用插入运算符 `<<` 向流中写入内容。

![](img/9fab00c46a74e6ad5591779d88bfd206_49.png)

```cpp
oss << "The answer is: ";
oss << 42;
```

![](img/9fab00c46a74e6ad5591779d88bfd206_51.png)

最后，你可以使用 `.str()` 成员函数获取缓冲区中的所有内容，并将其作为一个完整的 `std::string` 返回。

```cpp
std::string result = oss.str();
std::cout << result; // 输出: The answer is: 42
```

![](img/9fab00c46a74e6ad5591779d88bfd206_53.png)

**一个重要概念——位置指针**：流内部有一个“位置指针”，指示下一个读写操作发生的位置。当你在一个全新的 `ostringstream` 上写入时，会从开头覆盖。如果你希望从末尾追加，可以在构造时指定模式。

```cpp
// 从末尾开始写入（追加模式）
std::ostringstream oss(std::ios::ate);
oss << "Initial";
oss << "Appended";
std::cout << oss.str(); // 输出: InitialAppended
```

![](img/9fab00c46a74e6ad5591779d88bfd206_55.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_57.png)

### 输入字符串流 (istringstream)

![](img/9fab00c46a74e6ad5591779d88bfd206_59.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_61.png)

输入字符串流允许你从一个已有的字符串中“读取”并解析出各种类型的数据。

![](img/9fab00c46a74e6ad5591779d88bfd206_63.png)

以下是使用 `istringstream` 的基本步骤：

![](img/9fab00c46a74e6ad5591779d88bfd206_65.png)

首先，用一个字符串来初始化 `istringstream`。

![](img/9fab00c46a74e6ad5591779d88bfd206_67.png)

```cpp
std::string data = "123 45.6 hello";
std::istringstream iss(data);
```

然后，使用提取运算符 `>>` 从流中读取数据到变量中。流会自动跳过空白字符（空格、换行、制表符等），并尝试将读取到的“标记”转换为目标变量的类型。

![](img/9fab00c46a74e6ad5591779d88bfd206_69.png)

```cpp
int num;
double val;
std::string word;

iss >> num;   // 读取整数 123
iss >> val;   // 读取浮点数 45.6
iss >> word; // 读取字符串 "hello"
```

![](img/9fab00c46a74e6ad5591779d88bfd206_71.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_73.png)

**类型转换是关键**：`>>` 操作符会根据你提供的变量类型进行转换。如果你尝试将 `"hello"` 读入一个 `int` 变量，操作会失败。

![](img/9fab00c46a74e6ad5591779d88bfd206_75.png)

---

![](img/9fab00c46a74e6ad5591779d88bfd206_77.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_79.png)

## 流的状态位 (State Bits) 🚦

当我们从流中读取数据时，可能会失败（例如类型不匹配、到达末尾）。流使用四个状态位来记录其当前状态：

![](img/9fab00c46a74e6ad5591779d88bfd206_81.png)

1.  **`goodbit`**：一切正常，没有错误。
2.  **`failbit`**：上一次读取/写入操作失败（例如，尝试将 `"abc"` 读入 `int`）。
3.  **`eofbit`**：已到达流的末尾（End Of File）。
4.  **`badbit`**：发生了与流缓冲区相关的严重错误（很少见）。

![](img/9fab00c46a74e6ad5591779d88bfd206_83.png)

**状态位的重要性**：一旦 `failbit` 或 `badbit` 被设置，所有后续的流操作都会被忽略，直到你清除了这些错误状态。

![](img/9fab00c46a74e6ad5591779d88bfd206_85.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_87.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_89.png)

你可以通过成员函数来检查这些状态：
*   `stream.good()`
*   `stream.fail()`
*   `stream.eof()`
*   `stream.bad()`

![](img/9fab00c46a74e6ad5591779d88bfd206_91.png)

**一个关键点**：`good()` 并非 `fail()` 的简单对立面。`good()` 仅在**所有**错误位都未设置时为真。而 `fail()` 为真时，`good()` 必然为假。通常我们更关心 `fail()` 和 `eof()`。

### 实践：实现 `stringToInteger` 函数

利用字符串流和状态位，我们可以实现一个健壮的字符串转整数函数。

![](img/9fab00c46a74e6ad5591779d88bfd206_93.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_95.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_97.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_99.png)

基本思路：
1.  用输入字符串创建一个 `istringstream`。
2.  尝试从中读取一个整数。
3.  检查读取操作后流的状态。
    *   如果 `failbit` 被设置，说明根本没能读取整数。
    *   如果读取成功后，流中还有非空白字符，说明输入不“纯净”（如 `"123abc"`）。
4.  根据状态决定是返回整数还是抛出错误。

以下是核心代码框架：

![](img/9fab00c46a74e6ad5591779d88bfd206_101.png)

```cpp
int stringToInteger(const std::string& str) {
    std::istringstream iss(str);
    int result;
    iss >> result; // 尝试读取

    // 检查是否读取失败，或者读取后还有多余内容
    if (iss.fail() || !iss.eof()) {
        // 抛出异常或进行错误处理
        throw std::domain_error("字符串无法转换为整数，或包含额外字符。");
    }
    return result;
}
```

![](img/9fab00c46a74e6ad5591779d88bfd206_103.png)

**更简洁的写法**：流对象本身在布尔上下文中会被转换为 `true`（如果 `!fail()`）或 `false`（如果 `fail()`）。因此，检查 `if (iss >> result)` 可以判断读取是否成功。

```cpp
int stringToInteger(const std::string& str) {
    std::istringstream iss(str);
    int result;
    char remaining;
    // 如果读取整数成功，并且下一个字符读取失败（说明后面只有空白或已到末尾）
    if (!(iss >> result) || (iss >> remaining)) {
        throw std::domain_error("无效的整数格式。");
    }
    return result;
}
```

![](img/9fab00c46a74e6ad5591779d88bfd206_105.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_107.png)

---

![](img/9fab00c46a74e6ad5591779d88bfd206_109.png)

## 输入/输出流 (I/O Streams) 与缓冲 🐢⚡

![](img/9fab00c46a74e6ad5591779d88bfd206_111.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_113.png)

我们最熟悉的 `std::cout` 和 `std::cin` 就是标准的输出/输入流。它们连接到控制台。

![](img/9fab00c46a74e6ad5591779d88bfd206_115.png)

### 缓冲 (Buffering)

![](img/9fab00c46a74e6ad5591779d88bfd206_117.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_119.png)

为了提高效率，像 `cout` 这样的输出流通常是**缓冲的**。这意味着你写入的数据不会立即显示在屏幕上，而是先存储在一个内存缓冲区中。缓冲区会在以下情况被“刷新”到实际设备：
*   缓冲区已满。
*   遇到换行符 `\n`（但 `\n` 本身不一定触发刷新）。
*   显式使用 `std::endl`（它输出换行符**并**刷新缓冲区）。
*   显式使用 `std::flush` 操控符。
*   在读取 `std::cin` 之前，`cout` 的缓冲区会被自动刷新，以确保用户能看到提示信息。

![](img/9fab00c46a74e6ad5591779d88bfd206_121.png)

**示例：`endl` vs `\n`**
```cpp
// 方法一：使用 endl，每次都会刷新缓冲区，可能较慢
for (int i = 0; i < 1000; ++i) {
    std::cout << i << std::endl;
}

// 方法二：使用 \n，最后一次性刷新，通常更快
for (int i = 0; i < 1000; ++i) {
    std::cout << i << '\n';
}
// 循环结束后，缓冲区可能在程序退出时自动刷新
```
在需要高性能的场景，应避免频繁使用 `std::endl`。但在调试或需要确保输出立即可见时，`std::endl` 很有用。

![](img/9fab00c46a74e6ad5591779d88bfd206_123.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_125.png)

### 流操作符 (Manipulators) 🎛️

流操作符是像 `std::endl`、`std::flush` 这样的特殊对象，当用 `<<` 或 `>>` 将它们放入流时，会改变流的格式或状态，而不是输出字符本身。

![](img/9fab00c46a74e6ad5591779d88bfd206_127.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_129.png)

常见的操作符包括：
*   `std::endl`：换行并刷新。
*   `std::flush`：仅刷新缓冲区。
*   `std::setw(n)`：设置下一个输出字段的宽度。
*   `std::setprecision(n)`：设置浮点数输出精度。

它们的使用方式如下：
```cpp
#include <iomanip> // 对于 setw, setprecision
std::cout << std::setw(10) << std::left << "Hello" << std::setprecision(2) << 3.14159 << std::endl;
```

![](img/9fab00c46a74e6ad5591779d88bfd206_131.png)

---

![](img/9fab00c46a74e6ad5591779d88bfd206_133.png)

## 总结 📝

本节课我们一起学习了C++中流的核心概念：

1.  **流的角色**：作为程序与外部设备交互的统一、抽象的接口。
2.  **字符串流**：`std::istringstream` 用于从字符串解析数据，`std::ostringstream` 用于将数据格式化为字符串。它们是内存中强大的类型转换工具。
3.  **状态位**：`goodbit`、`failbit`、`eofbit`、`badbit` 用于诊断流操作的成功与否，是编写健壮代码的关键。
4.  **I/O流与缓冲**：`cout`/`cin` 是标准I/O流，了解缓冲机制和 `std::endl` 与 `\n` 的区别对程序性能和调试有重要意义。
5.  **流操作符**：像 `std::endl` 这样的特殊对象，可以控制流的格式和行为。

![](img/9fab00c46a74e6ad5591779d88bfd206_135.png)

![](img/9fab00c46a74e6ad5591779d88bfd206_136.png)

理解流是掌握C++输入输出的基础。在接下来的课程中，我们将继续探索C++的其他特性，并实现更复杂的库函数。