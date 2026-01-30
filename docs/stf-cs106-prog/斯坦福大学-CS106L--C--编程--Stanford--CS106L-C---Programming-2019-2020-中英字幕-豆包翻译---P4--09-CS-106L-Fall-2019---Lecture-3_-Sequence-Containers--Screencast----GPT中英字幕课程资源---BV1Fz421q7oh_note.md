![](img/3204840a2572ad0be828e3eaa5f5c76a_1.png)

# 斯坦福大学《CS106L：C++编程》课程笔记 - 第3讲：序列容器 🧱

在本节课中，我们将学习C++标准模板库（STL）中的序列容器，特别是`std::vector`和`std::deque`。我们将了解它们与斯坦福库中对应容器的区别，探讨其性能特点，并学习如何根据实际需求选择合适的容器。

---

## 1. 结构体与结构化绑定

上一节我们介绍了`std::pair`，它允许将两个不同类型的值打包在一起。本节中我们来看看更通用的结构体以及C++17引入的结构化绑定特性。

结构体是对或元组的更一般形式，其组件可以是不同类型，并且每个组件都有名称，这提供了自文档化的能力。

```cpp
struct PriceRange {
    int min;
    int max;
};
```

结构化绑定允许在函数返回一个结构体（或`std::pair`）时，自动将其成员解包到单独的变量中。

```cpp
auto [minVal, maxVal] = findMinMax(vec); // 假设函数返回一个PriceRange或pair
```

**注意**：在CS106B中应避免使用结构化绑定，因为评分系统可能使用较旧的C++版本。

---

## 2. 统一初始化

![](img/3204840a2572ad0be828e3eaa5f5c76a_3.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_5.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_7.png)

C++有多种初始化变量的方法，这可能导致混淆。为了解决这个问题，C++引入了统一初始化，它使用花括号 `{}`，旨在提供一种通用且一致的初始化方式。

统一初始化适用于多种类型，包括结构体、基本类型和容器。

![](img/3204840a2572ad0be828e3eaa5f5c76a_9.png)

```cpp
// 初始化结构体
Course cs106l = {"CS106L", {15, 30}, {16, 30}, {"Avery", "Anna"}};

// 初始化向量
std::vector<int> vec = {1, 2, 3, 4, 5};
```

当使用统一初始化时，编译器会尝试调用对象的“初始化列表构造函数”。对于`std::vector`，花括号初始化会创建一个包含这些元素的向量，而圆括号初始化则可能调用其他构造函数（例如，指定大小）。

```cpp
std::vector<int> v1(3);    // 创建一个大小为3的向量，元素默认初始化（对int是0）
std::vector<int> v2{3};    // 创建一个包含单个元素3的向量
```

---

## 3. 字符串流的适用场景

我们之前介绍了字符串流（`std::stringstream`），它是一个强大的工具，但并非所有字符串处理都需要它。

以下是字符串流最适合的三种应用场景：
1.  **路径操作**：处理文件系统路径等流式数据。
2.  **格式化I/O**：使用操控器（如`std::uppercase`, `std::hex`）对字符串进行特定格式化。
3.  **类型转换**：在字符串和其他类型（如整数、浮点数）之间进行转换。

![](img/3204840a2572ad0be828e3eaa5f5c76a_11.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_13.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_15.png)

另一方面，如果只是进行简单的字符串连接，使用`std::string`的`append`方法或`+`运算符是更直接、更高效的选择。

![](img/3204840a2572ad0be828e3eaa5f5c76a_17.png)

---

![](img/3204840a2572ad0be828e3eaa5f5c76a_19.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_21.png)

## 4. 标准模板库（STL）简介

![](img/3204840a2572ad0be828e3eaa5f5c76a_23.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_25.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_27.png)

STL是C++标准库的核心组成部分，其设计哲学是将算法和数据结构抽象到最通用的形式。STL包含以下几个主要部分：
*   **容器**：用于存储数据的集合（如`vector`, `deque`）。
*   **迭代器**：用于遍历容器中的元素。
*   **算法**：作用于容器上的通用函数（如`sort`, `find`）。
*   **仿函数与Lambda**：可调用的对象，用于自定义算法行为。

STL的强大之处在于其通用性和效率。下面的例子展示了使用STL算法如何将复杂的机械代码简化为清晰、高级的表述：

```cpp
// 传统方式：生成、排序、打印
std::vector<int> vec(n);
for (int i = 0; i < n; ++i) vec[i] = rand();
bubbleSort(vec); // 自己实现的排序
for (int num : vec) std::cout << num << " ";

// STL方式：
std::vector<int> vec(n);
std::generate(vec.begin(), vec.end(), std::rand);
std::sort(vec.begin(), vec.end());
std::copy(vec.begin(), vec.end(), std::ostream_iterator<int>(std::cout, " "));
```

---

## 5. 序列容器：`std::vector`

`std::vector`是C++中最常用的序列容器，表示一个可以动态增长的数组。

![](img/3204840a2572ad0be828e3eaa5f5c76a_29.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_30.png)

以下是`std::vector`与斯坦福库`Vector`的一些关键区别：

![](img/3204840a2572ad0be828e3eaa5f5c76a_32.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_34.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_36.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_37.png)

| 操作 | 斯坦福库 `Vector` | C++ 标准库 `std::vector` |
| :--- | :--- | :--- |
| **添加元素** | `v.add(value)` | `v.push_back(value)` |
| **获取元素** | `v.get(i)` 或 `v[i]` | `v.at(i)` 或 `v[i]` |
| **设置元素** | `v.set(i, value)` | `v.at(i) = value` 或 `v[i] = value` |

![](img/3204840a2572ad0be828e3eaa5f5c76a_39.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_40.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_42.png)

最重要的区别在于**边界检查**：
*   `v.at(i)`：会进行边界检查，如果索引`i`越界，会抛出`std::out_of_range`异常。
*   `v[i]`：**不进行边界检查**。如果索引越界，行为是未定义的（可能访问到垃圾数据，但不会直接崩溃）。这是为了追求极致的运行效率。

![](img/3204840a2572ad0be828e3eaa5f5c76a_44.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_46.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_48.png)

**结论**：默认使用`v[i]`以获得最佳性能，但必须确保索引在有效范围内。如果安全性更重要，或者无法确定索引是否有效，则使用`v.at(i)`。

![](img/3204840a2572ad0be828e3eaa5f5c76a_50.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_52.png)

---

![](img/3204840a2572ad0be828e3eaa5f5c76a_54.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_55.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_57.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_59.png)

## 6. 序列容器：`std::deque`

![](img/3204840a2572ad0be828e3eaa5f5c76a_61.png)

`std::vector`在尾部添加元素非常高效，但在头部插入元素需要移动所有后续元素，效率很低。`std::deque`（双端队列）解决了这个问题。

`std::deque`支持在头部和尾部进行常数时间的插入和删除操作。

```cpp
std::deque<int> dq;
dq.push_back(10);  // 在尾部添加
dq.push_front(5);  // 在头部添加，对于vector这是低效的
```

然而，这种灵活性带来了权衡。与`std::vector`相比，`std::deque`在随机访问元素（即使用`dq[i]`）时速度稍慢。

**选择指南**：
*   **默认使用 `std::vector`**：它对于大多数用例（尤其是尾部操作和随机访问）都是最快、最缓存友好的。
*   **当需要频繁在序列头部进行插入/删除操作时，使用 `std::deque`**。

![](img/3204840a2572ad0be828e3eaa5f5c76a_63.png)

---

![](img/3204840a2572ad0be828e3eaa5f5c76a_65.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_67.png)

## 总结

本节课中我们一起学习了C++ STL中序列容器的核心知识。

![](img/3204840a2572ad0be828e3eaa5f5c76a_69.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_71.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_73.png)

我们首先回顾了结构体和统一初始化，理解了更安全、更通用的数据打包与初始化方法。接着，我们明确了字符串流的适用场景，避免滥用。

![](img/3204840a2572ad0be828e3eaa5f5c76a_75.png)

![](img/3204840a2572ad0be828e3eaa5f5c76a_77.png)

然后，我们正式引入了强大的标准模板库（STL），并重点探讨了两种基本的序列容器：`std::vector`和`std::deque`。我们详细比较了`std::vector`与斯坦福库`Vector`的区别，特别是访问元素时的边界检查行为。最后，我们通过性能对比，理解了`std::vector`和`std::deque`各自的优势与权衡，并掌握了根据实际需求选择合适容器的原则。

![](img/3204840a2572ad0be828e3eaa5f5c76a_79.png)

记住，`std::vector`是大多数情况下的默认选择，而当你需要一个高效的“双端队列”时，`std::deque`是你的得力工具。