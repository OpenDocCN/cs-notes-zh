![](img/09ab7f555a33b141c1d158d778f655d6_1.png)

# 课程名称：CS106L C++编程 - 第6讲：模板 🧩

## 概述
在本节课中，我们将学习C++中的模板函数。模板是泛型编程的核心工具，它允许我们编写独立于特定数据类型的代码，从而提高代码的复用性和灵活性。我们将从理解为什么需要模板开始，学习其基本语法，并通过实例来掌握如何创建和使用模板函数。

---

## 1. 为什么需要模板？🤔
在编程中，我们经常需要为不同类型的数据编写功能相似的函数。例如，一个找出两个值中较小和较大值的函数，我们可能需要对整数、浮点数甚至字符串都实现它。

如果不使用模板，传统的做法是为每种类型都编写一个几乎完全相同的函数。这会导致代码冗余，难以维护。

**示例：冗余的函数**
```cpp
// 为整数编写的函数
std::pair<int, int> myMinMax(int a, int b) {
    if (a < b) return {a, b};
    else return {b, a};
}
// 为双精度浮点数编写的函数
std::pair<double, double> myMinMax(double a, double b) {
    if (a < b) return {a, b};
    else return {b, a};
}
// 为字符串编写的函数
std::pair<std::string, std::string> myMinMax(std::string a, std::string b) {
    if (a < b) return {a, b};
    else return {b, a};
}
```
可以看到，除了类型声明，函数体完全一样。模板就是为了解决这种重复劳动而生的。

---

## 2. 模板函数基础 🛠️
模板函数允许我们定义一个“蓝图”，编译器会根据调用时提供的具体类型来生成对应的函数代码。

### 2.1 基本语法
创建一个模板函数，需要使用 `template` 关键字，后面跟着用尖括号 `<>` 括起来的模板参数列表。通常使用 `typename T`（或 `class T`）来声明一个类型参数 `T`。

**通用格式：**
```cpp
template <typename T>
返回类型 函数名(参数列表) {
    // 函数体，使用类型 T
}
```

### 2.2 第一个模板函数
让我们将上面的 `myMinMax` 函数改造成一个模板函数。

**代码示例：**
```cpp
#include <iostream>
#include <utility>
#include <string>

// 声明一个模板函数
template <typename T>
std::pair<T, T> myMinMax(T a, T b) {
    if (a < b) return {a, b};
    else return {b, a};
}

// 辅助打印函数
template <typename T>
void printMinMax(const std::pair<T, T>& result) {
    std::cout << "Min: " << result.first << ", Max: " << result.second << std::endl;
}

int main() {
    // 用于整数
    auto result1 = myMinMax(3, -2);
    printMinMax(result1); // 输出: Min: -2, Max: 3

    // 用于双精度浮点数
    auto result2 = myMinMax(8.3, 7.4);
    printMinMax(result2); // 输出: Min: 7.4, Max: 8.3

    // 用于字符串
    auto result3 = myMinMax(std::string("Anna"), std::string("Avery"));
    printMinMax(result3); // 输出: Min: Anna, Max: Avery (按字母顺序)

    return 0;
}
```
现在，一个函数就能处理多种类型的数据。

---

## 3. 模板实例化 ⚙️
模板本身不是真正的函数，它只是一个蓝图。当编译器在代码中看到对模板函数的调用时，它会根据提供的具体类型来“实例化”出一个具体的函数。这发生在编译时。

### 3.1 显式实例化
你可以在调用时明确指定模板参数 `T` 的类型。

**示例：**
```cpp
auto result = myMinMax<double>(3, 5.2); // 明确告诉编译器 T 是 double
```
在这种情况下，`3` 会被隐式转换为 `double`。

### 3.2 隐式实例化
更常见的是让编译器根据传入的参数自动推导类型。

**示例：**
```cpp
auto result = myMinMax(3, 5); // 编译器推导出 T 是 int
```
编译器会查看所有可能的匹配（包括重载函数和模板），并应用一系列规则来选择“最佳匹配”。

---

## 4. 模板的威力与注意事项 💪
上一节我们介绍了模板的基本用法，本节中我们来看看使用模板时的一些高级概念和潜在问题。

### 4.1 多个模板参数
一个函数模板可以有多个类型参数。

**示例：一个（可能不实用的）混合类型比较函数**
```cpp
template <typename T, typename U>
void printTwoTypes(T a, U b) {
    std::cout << "First: " << a << ", Second: " << b << std::endl;
}
```
需要注意的是，对于 `myMinMax` 这样的函数，让两个参数类型不同通常没有意义，因为不同类型之间可能无法直接比较。

### 4.2 对类型的假设（隐式接口）
模板函数对其操作的类型做出了**隐式假设**。例如，我们的 `myMinMax` 函数假设类型 `T` 支持 `<` 运算符。

如果传入一个不支持 `<` 运算符的自定义类型，代码将无法编译。
```cpp
struct MyStruct { int x; };
MyStruct s1{1}, s2{2};
auto result = myMinMax(s1, s2); // 编译错误！MyStruct 没有定义 operator<
```
这就要求我们在设计模板时，必须清楚地知道并对调用者声明函数对类型的要求。C++20引入了“概念（Concepts）”来更明确地表达这些约束，我们将在后续课程中讨论。

### 4.3 模板与重载
当存在普通重载函数和模板函数时，编译器有一套复杂的规则来决定调用哪一个。基本原则是：非模板函数优先于模板函数，更特化的模板优先于更通用的模板。

**最佳实践：** 避免创建与模板函数签名完全相同（仅类型不同）的非模板重载函数，以免引起混淆。

---

## 5. 实践练习：通用输入函数 ✍️
让我们通过一个练习来巩固所学。我们将模板化一个常见的 `getInteger` 函数，使其能获取任意类型的值。

**原始函数（获取整数）：**
```cpp
int getInteger(const std::string& prompt) {
    int value;
    std::cout << prompt;
    std::cin >> value;
    return value;
}
```

**模板化后的通用函数：**
```cpp
template <typename T>
T getValue(const std::string& prompt) {
    T value;
    std::cout << prompt;
    std::cin >> value;
    return value;
}

int main() {
    // 获取整数
    int i = getValue<int>("Enter an integer: ");
    // 获取浮点数
    double d = getValue<double>("Enter a double: ");
    // 获取字符串（注意：会读取到第一个空白字符为止）
    std::string s = getValue<std::string>("Enter a string: ");

    std::cout << "You entered: " << i << ", " << d << ", " << s << std::endl;
    return 0;
}
```
这个模板函数现在可以用于任何定义了 `>>` 输入运算符的类型。

---

## 6. 迈向泛型编程：概念提升 🚀
泛型编程的核心思想是编写不依赖于具体数据结构的算法。模板是实现这一思想的工具。

考虑一个计算某个值在集合中出现次数的函数：

**初始版本（针对 `vector<int>`）：**
```cpp
int countOccurrences(const std::vector<int>& vec, int value) {
    int count = 0;
    for (size_t i = 0; i < vec.size(); ++i) {
        if (vec[i] == value) ++count;
    }
    return count;
}
```
这个函数做了很多限制性假设：
1.  容器必须是 `std::vector`。
2.  容器元素必须是 `int`。
3.  使用索引访问，这要求容器支持随机访问。

我们可以通过模板和迭代器来逐步“提升”这个函数，移除这些假设：

**第一步：模板化元素类型和容器类型**
```cpp
template <typename Container, typename DataType>
int countOccurrences(const Container& collection, const DataType& value) {
    int count = 0;
    for (size_t i = 0; i < collection.size(); ++i) { // 问题依然存在：假设有 .size() 和 []
        if (collection[i] == value) ++count;
    }
    return count;
}
```

**第二步：使用迭代器（更通用的方式）**
```cpp
template <typename InputIt, typename DataType>
int countOccurrences(InputIt begin, InputIt end, const DataType& value) {
    int count = 0;
    for (InputIt it = begin; it != end; ++it) { // 只假设迭代器支持 !=, *, ++
        if (*it == value) ++count;
    }
    return count;
}
// 使用示例
std::vector<int> vec = {1, 2, 2, 3, 2};
int cnt = countOccurrences(vec.begin(), vec.end(), 2); // 计算2出现的次数
```
现在，这个函数可以用于任何提供前向迭代器的容器（如 `vector`, `list`, `set` 的一部分等），并且不关心容器的具体类型和内存布局。这就是标准库算法（如 `std::count`）的工作方式。

---

## 总结
本节课中我们一起学习了C++模板函数的基础知识。我们从解决代码冗余的需求出发，学习了如何声明和使用模板函数，理解了模板实例化在编译时发生的过程。我们探讨了模板对类型的隐式接口要求，并通过实践练习加深了理解。最后，我们看到了如何利用模板和迭代器进行“概念提升”，编写出真正通用、灵活的算法，这正是泛型编程的强大之处。

![](img/09ab7f555a33b141c1d158d778f655d6_3.png)

模板是C++强大功能的基石之一，掌握它将为你打开编写高效、复用库代码的大门。在接下来的课程中，我们将继续探索标准模板库（STL）中的泛型组件。