# 004：C++基础（第二部分）🚀

![](img/19b429d67b955be61d2c4d78f317efc9_1.png)

![](img/19b429d67b955be61d2c4d78f317efc9_3.png)

![](img/19b429d67b955be61d2c4d78f317efc9_5.png)

![](img/19b429d67b955be61d2c4d78f317efc9_7.png)

在本节课中，我们将继续学习C++的基础知识，涵盖类型转换、函数、控制流、引用、标准库容器以及错误类型等核心概念。我们将通过简单的示例和清晰的解释，帮助你建立扎实的C++编程基础。

![](img/19b429d67b955be61d2c4d78f317efc9_9.png)

## 值语义与类型转换 🔄

![](img/19b429d67b955be61d2c4d78f317efc9_11.png)

上一节我们介绍了表达式，本节我们来看看C++中的**值语义**。值语义意味着对象在赋值和比较时，关注的是其值本身，而不是内存地址。这与Java等语言不同，在Java中，对象赋值通常传递的是引用。

例如，在C++中：
```cpp
std::string s = "hello";
std::string s2 = s; // s2 是 s 的一个副本，不是同一个对象的引用
assert(s == s2); // 比较的是字符串的内容（值），而不是内存地址
```

![](img/19b429d67b955be61d2c4d78f317efc9_13.png)

![](img/19b429d67b955be61d2c4d78f317efc9_15.png)

接下来，我们探讨类型转换。C++提供了隐式和显式两种类型转换方式。

![](img/19b429d67b955be61d2c4d78f317efc9_17.png)

![](img/19b429d67b955be61d2c4d78f317efc9_18.png)

![](img/19b429d67b955be61d2c4d78f317efc9_20.png)

### 隐式类型转换

![](img/19b429d67b955be61d2c4d78f317efc9_22.png)

![](img/19b429d67b955be61d2c4d78f317efc9_24.png)

![](img/19b429d67b955be61d2c4d78f317efc9_26.png)

当从一种类型转换为另一种类型不会丢失精度时，编译器会自动进行隐式转换，也称为**提升**。

![](img/19b429d67b955be61d2c4d78f317efc9_28.png)

![](img/19b429d67b955be61d2c4d78f317efc9_29.png)

以下是隐式类型转换的示例：
```cpp
auto i = 42; // int 类型
auto d = 0.0; // double 类型
d = i; // 隐式将 int 转换为 double
```

### 显式类型转换

![](img/19b429d67b955be61d2c4d78f317efc9_31.png)

当转换可能丢失精度，或者你希望明确表达转换意图时，应使用显式类型转换。C++推荐使用 `static_cast`。

![](img/19b429d67b955be61d2c4d78f317efc9_33.png)

![](img/19b429d67b955be61d2c4d78f317efc9_35.png)

![](img/19b429d67b955be61d2c4d78f317efc9_36.png)

以下是显式类型转换的示例：
```cpp
auto i = 42;
auto d = static_cast<double>(i); // 显式将 int 转换为 double
```

需要注意的是，从大类型（如 `int`）转换为小类型（如 `char`）是**有损转换**，可能导致数据溢出或产生意外结果，使用时应格外小心。

![](img/19b429d67b955be61d2c4d78f317efc9_38.png)

![](img/19b429d67b955be61d2c4d78f317efc9_40.png)

## 函数 📞

![](img/19b429d67b955be61d2c4d78f317efc9_42.png)

函数是组织代码的基本单元。C++中的函数定义与其他语言类似。

以下是函数的基本语法示例：
```cpp
// 传统风格（C风格）
int add(int a, int b) {
    return a + b;
}

![](img/19b429d67b955be61d2c4d78f317efc9_44.png)

![](img/19b429d67b955be61d2c4d78f317efc9_45.png)

![](img/19b429d67b955be61d2c4d78f317efc9_46.png)

![](img/19b429d67b955be61d2c4d78f317efc9_48.png)

// C++20 引入的新风格（返回类型后置）
auto add(int a, int b) -> int {
    return a + b;
}
```

![](img/19b429d67b955be61d2c4d78f317efc9_50.png)

![](img/19b429d67b955be61d2c4d78f317efc9_52.png)

在课程中，你可以选择任意一种风格，但请确保在代码中保持一致性。

![](img/19b429d67b955be61d2c4d78f317efc9_54.png)

### 默认参数

C++允许为函数参数指定默认值。调用函数时，可以省略这些具有默认值的参数。

以下是默认参数的示例：
```cpp
std::string rgb(short r = 0, short g = 0, short b = 0) {
    // ... 函数体
}
rgb(); // 相当于 rgb(0, 0, 0)
rgb(255); // 相当于 rgb(255, 0, 0)
```

![](img/19b429d67b955be61d2c4d78f317efc9_56.png)

需要注意的是，一旦某个参数被赋予了默认值，它之后的所有参数也必须具有默认值。

### 函数重载

![](img/19b429d67b955be61d2c4d78f317efc9_58.png)

![](img/19b429d67b955be61d2c4d78f317efc9_59.png)

C++支持**函数重载**，即可以定义多个同名函数，只要它们的参数列表（类型、数量或顺序）不同即可。编译器会根据调用时提供的参数来决定使用哪个函数。

![](img/19b429d67b955be61d2c4d78f317efc9_61.png)

以下是函数重载的示例：
```cpp
int square(int const x) { return x * x; }
double square(double const x) { return x * x; }
// 错误示例：仅返回值不同不能构成重载
// double square(int const x) { return x * x; }
```

重载函数时，应确保所有同名函数的行为语义一致，否则应使用不同的函数名。

![](img/19b429d67b955be61d2c4d78f317efc9_63.png)

## 控制流 🧭

![](img/19b429d67b955be61d2c4d78f317efc9_65.png)

![](img/19b429d67b955be61d2c4d78f317efc9_67.png)

C++提供了常见的控制流语句，如 `if`、`switch` 和循环。

![](img/19b429d67b955be61d2c4d78f317efc9_69.png)

![](img/19b429d67b955be61d2c4d78f317efc9_71.png)

### If 语句与三元运算符

![](img/19b429d67b955be61d2c4d78f317efc9_73.png)

`if` 语句用于条件判断。此外，C++也支持三元运算符 `? :` 进行简化的条件赋值。

以下是控制流的示例：
```cpp
// if 语句
if (condition) {
    // 代码块
} else {
    // 代码块
}

![](img/19b429d67b955be61d2c4d78f317efc9_75.png)

// 三元运算符
int max = (a > b) ? a : b;
```

![](img/19b429d67b955be61d2c4d78f317efc9_77.png)

### Switch 语句

`switch` 语句用于基于一个整型或枚举值进行多路分支。C++17引入了 `[[fallthrough]]` 属性，用于明确告知编译器故意不写 `break` 语句。

以下是 `switch` 语句的示例：
```cpp
switch (value) {
    case 0:
        // 执行操作
        [[fallthrough]]; // 明确告知编译器继续执行下一个 case
    case 1:
        // 执行操作
        break;
    default:
        // 执行操作
}
```

![](img/19b429d67b955be61d2c4d78f317efc9_79.png)

![](img/19b429d67b955be61d2c4d78f317efc9_81.png)

## 序列容器：Vector 📦

`std::vector` 是C++中最常用的动态数组容器，类似于其他语言中的列表（List）或数组列表（ArrayList）。

以下是 `vector` 的基本操作示例：
```cpp
#include <vector>
#include <iostream>

![](img/19b429d67b955be61d2c4d78f317efc9_83.png)

![](img/19b429d67b955be61d2c4d78f317efc9_85.png)

int main() {
    // 创建并初始化 vector
    std::vector<int> single_digits = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};

    // 复制 vector
    std::vector<int> more_single_digits = single_digits;

    // 访问和修改元素
    more_single_digits[2] = 0;

    // 遍历 vector (使用范围for循环)
    for (auto const& digit : more_single_digits) {
        std::cout << digit << " ";
    }
    return 0;
}
```

## 引用 🎯

![](img/19b429d67b955be61d2c4d78f317efc9_87.png)

**引用**是C++中一个关键概念，它为一个已存在的对象提供了一个别名。引用主要用于函数参数传递，以实现**按引用传递**，避免不必要的拷贝，并允许函数修改外部变量。

### 引用基础

引用在声明时使用 `&` 符号。一旦引用被初始化指向某个对象，它就不能再指向其他对象。

![](img/19b429d67b955be61d2c4d78f317efc9_89.png)

![](img/19b429d67b955be61d2c4d78f317efc9_91.png)

以下是引用的基本示例：
```cpp
int i = 5;
int& ref_i = i; // ref_i 是 i 的引用（别名）
ref_i = 10; // 修改 ref_i 实际上修改了 i
std::cout << i; // 输出 10
```

### 常量引用

如果不想通过引用修改原对象，可以使用**常量引用**（`const &`）。常量引用常用于函数参数，以高效地传递大型对象，同时防止函数内部意外修改它。

以下是常量引用的示例：
```cpp
void print_vector(std::vector<int> const& vec) {
    // 可以读取 vec，但不能修改它
    for (auto const& num : vec) {
        std::cout << num << " ";
    }
}
```

![](img/19b429d67b955be61d2c4d78f317efc9_93.png)

### 引用与函数参数

通过使用引用作为函数参数，我们可以实现经典的“交换两个数”功能，而无需使用指针。

以下是使用引用交换两个数的示例：
```cpp
void swap(int& a, int& b) {
    int temp = a;
    a = b;
    b = temp;
}

![](img/19b429d67b955be61d2c4d78f317efc9_95.png)

int main() {
    int x = 5, y = 10;
    swap(x, y); // x 和 y 的值被交换
    return 0;
}
```

## 范围 For 循环与更多容器 🔄

### 范围 For 循环

![](img/19b429d67b955be61d2c4d78f317efc9_97.png)

C++11引入了**范围for循环**，可以更简洁地遍历容器（如 `vector`）中的所有元素。

![](img/19b429d67b955be61d2c4d78f317efc9_99.png)

以下是范围for循环的示例：
```cpp
std::vector<int> vec = {1, 2, 3, 4, 5};
for (auto const& element : vec) {
    std::cout << element << " ";
}
// 输出：1 2 3 4 5
```

![](img/19b429d67b955be61d2c4d78f317efc9_101.png)

### 无序集合与映射

![](img/19b429d67b955be61d2c4d78f317efc9_103.png)

![](img/19b429d67b955be61d2c4d78f317efc9_105.png)

C++标准库提供了基于哈希表实现的高效容器：`std::unordered_set`（集合）和 `std::unordered_map`（映射/字典）。

![](img/19b429d67b955be61d2c4d78f317efc9_107.png)

以下是 `unordered_set` 和 `unordered_map` 的示例：
```cpp
#include <unordered_set>
#include <unordered_map>
#include <string>

// 无序集合：存储唯一元素
std::unordered_set<std::string> names = {"Alice", "Bob"};
names.insert("Charlie");
if (names.find("Alice") != names.end()) {
    // 找到了 "Alice"
}

![](img/19b429d67b955be61d2c4d78f317efc9_109.png)

// 无序映射：键值对
std::unordered_map<std::string, int> age_map = {{"Alice", 30}, {"Bob", 25}};
age_map["Charlie"] = 28; // 插入或修改
int alice_age = age_map["Alice"]; // 访问
```

![](img/19b429d67b955be61d2c4d78f317efc9_111.png)

这些容器在平均情况下提供常数时间复杂度的查找和插入操作，非常适合需要快速查找的场景。

![](img/19b429d67b955be61d2c4d78f317efc9_113.png)

![](img/19b429d67b955be61d2c4d78f317efc9_115.png)

![](img/19b429d67b955be61d2c4d78f317efc9_116.png)

## 声明与定义 📝

![](img/19b429d67b955be61d2c4d78f317efc9_118.png)

在C++中，理解**声明**和**定义**的区别非常重要：
*   **声明**：告诉编译器某个名称（变量、函数、类）的存在及其类型。一个名称可以多次声明。
*   **定义**：为声明的名称分配存储空间或提供具体实现。一个名称在同一个作用域内只能定义一次。

简单来说，定义是一种特殊的声明，它“实现”了所声明的实体。

![](img/19b429d67b955be61d2c4d78f317efc9_120.png)

![](img/19b429d67b955be61d2c4d78f317efc9_122.png)

## 错误类型 🚨

![](img/19b429d67b955be61d2c4d78f317efc9_124.png)

程序错误主要分为四类，理解它们有助于调试：
1.  **编译时错误**：代码语法或类型错误，编译器无法生成目标文件。
2.  **链接时错误**：各个编译好的模块（`.o`文件）在链接成可执行文件时出错，例如找不到某个函数的定义。
3.  **运行时错误**：程序运行期间发生的错误，如除以零、文件不存在等，可能导致程序崩溃。
4.  **逻辑错误**：程序可以编译和运行，但行为不符合预期。这是最隐蔽的错误，通常源于程序员的逻辑失误。

## 文件输入输出 📁

C++使用**流**的概念来处理输入输出，包括文件操作。

![](img/19b429d67b955be61d2c4d78f317efc9_126.png)

![](img/19b429d67b955be61d2c4d78f317efc9_128.png)

![](img/19b429d67b955be61d2c4d78f317efc9_129.png)

以下是文件读写的基本示例：
```cpp
#include <fstream>
#include <string>

// 写入文件
std::ofstream fout("output.txt");
if (fout) { // 检查文件是否成功打开
    fout << "Hello, File!" << std::endl;
    fout.close();
}

// 读取文件
std::ifstream fin("input.txt");
std::string line;
if (fin) {
    while (std::getline(fin, line)) { // 逐行读取
        std::cout << line << std::endl;
    }
    fin.close();
}
```

## 总结 🎉

本节课中我们一起学习了C++基础的第二部分。我们深入探讨了值语义、类型转换（隐式与显式）、函数的定义与重载、控制流语句、`vector`容器的使用、引用的概念及其在函数参数传递中的应用、范围for循环、以及`unordered_set`和`unordered_map`等高效容器。此外，我们还了解了声明与定义的区别、不同类型的程序错误以及基本的文件I/O操作。

![](img/19b429d67b955be61d2c4d78f317efc9_131.png)

![](img/19b429d67b955be61d2c4d78f317efc9_133.png)

![](img/19b429d67b955be61d2c4d78f317efc9_135.png)

掌握这些基础知识是编写高效、正确C++程序的关键。在接下来的课程中，我们将基于这些概念，探索更高级的C++特性和编程技巧。