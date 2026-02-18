# 斯坦福大学《CS106L：C++编程》课程笔记 P6：高级迭代器与容器 🚀

![](img/0a95bd144f2647b8324d3a24c1c161f7_1.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_3.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_4.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_5.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_7.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_8.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_9.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_10.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_11.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_12.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_13.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_14.png)

在本节课中，我们将深入学习C++标准模板库（STL）中迭代器和容器的高级用法。我们将探讨迭代器的不同类型、它们与算法的配合，以及如何在实际编程中灵活运用这些工具。

---

## 课程回顾与迭代器基础 🔄

上一节我们介绍了关联容器（如`map`和`set`）以及迭代器的基本概念。迭代器就像一个“爪子机”，可以遍历容器中的元素。其基本语法包括创建、解引用、递增和比较。

以下是迭代器的四个基本操作：
1.  **创建**：通过容器的`.begin()`和`.end()`方法获取迭代器。
    ```cpp
    std::vector<int>::iterator it = vec.begin();
    ```
2.  **解引用**：使用`*`运算符获取迭代器指向的值。
    ```cpp
    int value = *it;
    ```
3.  **递增**：使用`++`运算符移动到下一个元素。
    ```cpp
    ++it; // 或 it++;
    ```
4.  **比较**：使用`==`或`!=`判断迭代器是否到达终点。
    ```cpp
    while (it != vec.end()) { ... }
    ```

![](img/0a95bd144f2647b8324d3a24c1c161f7_16.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_18.png)

迭代器的强大之处在于，它允许我们编写通用的代码来处理不同的容器（如`vector`、`list`、`set`），而无需关心其底层实现。

---

## 映射（Map）迭代器的特殊性 🗺️

![](img/0a95bd144f2647b8324d3a24c1c161f7_20.png)

本节中我们来看看`map`迭代器的一个特殊之处。与其他容器不同，解引用一个`map`迭代器不会直接得到一个值，而是得到一个`std::pair`对象。

`std::pair`是一个模板类，用于将两个值组合成一个单元。在`map`中，`pair.first`是键（key），`pair.second`是值（value）。

![](img/0a95bd144f2647b8324d3a24c1c161f7_22.png)

创建`pair`的两种常见方法：
```cpp
// 方法一：统一初始化
std::pair<std::string, int> p1 = {"Stanford", 6507232300};

![](img/0a95bd144f2647b8324d3a24c1c161f7_24.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_26.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_28.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_30.png)

// 方法二：使用 std::make_pair (可自动推断类型)
auto p2 = std::make_pair("Stanford", 6507232300);
```

遍历`map`的示例：
```cpp
std::map<std::string, int> freqMap = {{"apple", 2}, {"banana", 5}};
for (auto it = freqMap.begin(); it != freqMap.end(); ++it) {
    // 注意括号：先解引用迭代器，再访问pair成员
    std::cout << (*it).first << ": " << (*it).second << std::endl;
    // 等价简写：it->first 和 it->second
}
```
对于`multimap`（允许重复键），插入元素通常使用`insert`方法配合`make_pair`。

![](img/0a95bd144f2647b8324d3a24c1c161f7_32.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_34.png)

---

![](img/0a95bd144f2647b8324d3a24c1c161f7_36.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_38.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_40.png)

## 迭代器与STL算法 ⚙️

迭代器是STL算法（如排序、查找）能够工作的基础。这些算法定义在`<algorithm>`头文件中。

![](img/0a95bd144f2647b8324d3a24c1c161f7_42.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_43.png)

以下是几个常用算法的示例：

![](img/0a95bd144f2647b8324d3a24c1c161f7_45.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_47.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_48.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_50.png)

**1. 排序（std::sort）**
`std::sort`要求**随机访问迭代器**，因此可用于`vector`、`deque`等，但不能直接用于`set`或`list`（它们已排序或需要特殊算法）。
```cpp
std::vector<int> vec = {5, 3, 8, 1};
std::sort(vec.begin(), vec.end()); // 排序整个向量
std::sort(vec.begin(), vec.begin() + 2); // 只排序前两个元素
```

![](img/0a95bd144f2647b8324d3a24c1c161f7_52.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_54.png)

**2. 查找（std::find）**
`std::find`只要求**输入迭代器**，因此可用于几乎所有容器，甚至输入流。它返回一个指向找到元素的迭代器，若未找到则返回`.end()`。
```cpp
std::set<int> mySet = {3, 1, 4, 1, 5, 9};
auto it = std::find(mySet.begin(), mySet.end(), 5);
if (it != mySet.end()) {
    std::cout << "Found: " << *it << std::endl;
}
```
检查元素是否在`map`/`set`中，除了用`.count()`，也可用`.find()`，后者效率略高。

**3. 范围操作**
我们可以使用像`std::lower_bound`和`std::upper_bound`这样的函数来获取迭代器范围，从而只处理容器的一部分。
- `lower_bound(k)`: 返回指向**第一个不小于k**的元素的迭代器。
- `upper_bound(k)`: 返回指向**第一个大于k**的元素的迭代器。
```cpp
std::set<int> s = {1, 4, 5, 6, 9};
auto low = s.lower_bound(4); // 指向4
auto high = s.upper_bound(6); // 指向9
for (auto it = low; it != high; ++it) {
    std::cout << *it << " "; // 输出：4 5 6
}
```

![](img/0a95bd144f2647b8324d3a24c1c161f7_56.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_58.png)

---

![](img/0a95bd144f2647b8324d3a24c1c161f7_60.png)

## 基于范围的for循环与迭代器 🔄

在遍历整个容器时，基于范围的for循环（range-based for loop）语法更简洁，它是基于迭代器实现的语法糖。
```cpp
std::map<std::string, int> freqMap;
// 使用迭代器遍历
for (auto it = freqMap.begin(); it != freqMap.end(); ++it) { ... }
// 使用基于范围的for循环遍历
for (const auto& entry : freqMap) { ... }
// 使用结构化绑定（C++17）直接解包pair
for (const auto& [key, value] : freqMap) {
    std::cout << key << ": " << value << std::endl;
}
```
当需要**部分遍历**或**使用迭代器本身**（如传递给算法）时，传统的迭代器循环更灵活。

![](img/0a95bd144f2647b8324d3a24c1c161f7_62.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_64.png)

---

## 迭代器的五种类型 🏷️

并非所有迭代器都支持相同的操作。C++定义了五种迭代器类型，其功能由弱到强：

1.  **输入迭代器（Input Iterator）**
    *   **只读**，且通常只能**单次遍历**（遍历一次后迭代器可能失效）。
    *   例如：从`std::cin`读取数据的迭代器。
    *   `std::find`要求输入迭代器。

2.  **输出迭代器（Output Iterator）**
    *   **只写**，通常也是单次遍历。
    *   例如：向`std::cout`写入数据的迭代器。

![](img/0a95bd144f2647b8324d3a24c1c161f7_66.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_68.png)

3.  **前向迭代器（Forward Iterator）**
    *   支持**读写**，且支持**多次遍历**（可以保存迭代器并重新遍历）。
    *   例如：`std::forward_list`的迭代器。

![](img/0a95bd144f2647b8324d3a24c1c161f7_70.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_71.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_73.png)

4.  **双向迭代器（Bidirectional Iterator）**
    *   在前向迭代器基础上，支持**递减**（`--`操作）。
    *   例如：`std::list`、`std::set`、`std::map`的迭代器。

![](img/0a95bd144f2647b8324d3a24c1c161f7_75.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_77.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_79.png)

5.  **随机访问迭代器（Random Access Iterator）**
    *   功能最强大，支持在常数时间内**任意跳跃**（如`it + 5`、`it - 3`）。
    *   例如：`std::vector`、`std::deque`、`std::string`的迭代器，以及**原生指针**。

**重要关系**：随机访问迭代器 > 双向迭代器 > 前向迭代器 > (输入/输出迭代器)。一个函数如果要求输入迭代器，那么传入更强大的迭代器（如前向、双向迭代器）也是可以的。

---

## 迭代器与指针的关系 ⚖️

指针可以看作是随机访问迭代器的一种具体实现。更广义地说：
*   **指针**：是一种具体的变量类型，存储内存地址。
*   **迭代器**：是一个抽象概念，定义了遍历容器的一组操作接口。
所有随机访问迭代器（包括指针）都满足这个接口。因此，在许多STL算法中，原生指针可以直接当作迭代器使用。

---

![](img/0a95bd144f2647b8324d3a24c1c161f7_81.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_83.png)

## 总结 📚

![](img/0a95bd144f2647b8324d3a24c1c161f7_85.png)

本节课中我们一起学习了：
1.  **迭代器的高级应用**：如何与`std::pair`配合使用`map`迭代器。
2.  **STL算法**：如何使用迭代器配合`std::sort`、`std::find`等强大算法。
3.  **迭代器范围**：如何使用`lower_bound`等函数操作容器的子范围。
4.  **迭代器类型体系**：理解了五种迭代器类型及其能力差异，明白了为何某些算法（如`sort`）不能用于所有容器。
5.  **迭代器与指针**：了解了指针是迭代器概念的一种具体实现。

![](img/0a95bd144f2647b8324d3a24c1c161f7_87.png)

![](img/0a95bd144f2647b8324d3a24c1c161f7_88.png)

掌握迭代器是理解和使用C++ STL的关键。它们提供了统一的方式来处理和操作各种数据结构，使代码更加通用和强大。在下一讲中，我们将学习**模板**，这是将迭代器、容器和算法的通用性发挥到极致的核心技术。