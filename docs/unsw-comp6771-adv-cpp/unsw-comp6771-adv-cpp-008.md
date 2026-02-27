# 008：STL算法 🧮

![](img/bb50045a4e130df13b3f6c5aaff5f61f_1.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_3.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_5.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_7.png)

## 概述
在本节课中，我们将要学习C++标准模板库（STL）中的算法。STL算法是一组通用的函数，它们基于迭代器的抽象概念来操作容器中的数据。我们将了解如何使用这些算法来简化代码、提高可读性，并避免编写重复的循环逻辑。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_9.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_10.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_12.png)

---

![](img/bb50045a4e130df13b3f6c5aaff5f61f_14.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_16.png)

## STL算法简介
上一节我们介绍了STL容器和迭代器，本节中我们来看看STL算法。STL算法本质上是一些函数，它们基于抽象的“指针”（即迭代器）概念来执行特定操作。例如，二分查找算法可以作用于任何提供了适当迭代器的数据结构上。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_18.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_20.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_22.png)

一个简单的例子是求和。假设我们有一个整数向量：
```cpp
std::vector<int> nums = {1, 2, 3, 4, 5};
```
我们可以使用传统的循环来求和，但STL提供了 `std::accumulate` 算法：
```cpp
int sum = std::accumulate(nums.begin(), nums.end(), 0);
```
`std::accumulate` 函数接受容器的起始和结束迭代器，以及一个初始值，然后对所有元素进行累加。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_24.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_26.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_28.png)

---

## 常用STL算法示例
以下是几个核心的STL算法及其用法。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_30.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_32.png)

### 1. 累加与归约
`std::accumulate` 是典型的归约算法。它默认使用加法操作符，但也可以接受自定义的二元操作符。
```cpp
// 使用默认加法
int sum = std::accumulate(nums.begin(), nums.end(), 0);
// 使用乘法操作符
int product = std::accumulate(nums.begin(), nums.end(), 1, std::multiplies<int>());
```

![](img/bb50045a4e130df13b3f6c5aaff5f61f_34.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_36.png)

### 2. 查找元素
`std::find` 算法用于在容器中查找特定值。
```cpp
auto it = std::find(nums.begin(), nums.end(), 4);
if (it != nums.end()) {
    std::cout << "Found: " << *it << std::endl;
}
```
需要注意的是，对于像 `std::map` 这样的关联容器，使用其自身的 `find` 成员函数（如 `map.find(key)`）通常比 `std::find` 更高效，因为成员函数可以利用容器的内部结构（如二叉搜索树）。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_38.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_40.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_42.png)

### 3. 计算距离与移动迭代器
`std::distance` 用于计算两个迭代器之间的元素数量。
```cpp
auto dist = std::distance(nums.begin(), nums.end()); // 返回容器大小
```
`std::next` 和 `std::advance` 用于移动迭代器。`std::next` 返回移动后的新迭代器而不修改原迭代器，而 `std::advance` 直接修改传入的迭代器。
```cpp
auto mid = std::next(nums.begin(), std::distance(nums.begin(), nums.end()) / 2);
```

![](img/bb50045a4e130df13b3f6c5aaff5f61f_44.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_46.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_48.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_50.png)

### 4. 变换与映射
`std::transform` 算法将一个容器的元素转换后存入另一个容器，类似于函数式编程中的 `map` 操作。
```cpp
std::string s = "hello";
std::string upper;
std::transform(s.begin(), s.end(), std::back_inserter(upper), ::toupper);
```

### 5. 遍历与修改
`std::for_each` 算法对容器中的每个元素应用一个函数。
```cpp
std::for_each(s.begin(), s.end(), [](char &c) { c = ::toupper(c); });
```

![](img/bb50045a4e130df13b3f6c5aaff5f61f_52.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_54.png)

---

![](img/bb50045a4e130df13b3f6c5aaff5f61f_56.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_58.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_60.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_61.png)

## Lambda表达式与STL算法
Lambda表达式允许我们内联定义匿名函数，这在配合STL算法使用时非常方便。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_63.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_65.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_67.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_69.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_71.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_73.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_75.png)

Lambda的基本语法如下：
```cpp
[capture](parameters) -> return_type { body }
```
*   **捕获列表 `[capture]`**：指定哪些外部变量可以在Lambda体内使用（按值或按引用捕获）。
*   **参数列表 `(parameters)`**：与普通函数参数列表类似。
*   **返回类型 `-> return_type`**：可选的返回类型声明。
*   **函数体 `{ body }`**：Lambda的执行代码。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_77.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_79.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_80.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_82.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_84.png)

以下是一个使用Lambda为向量每个元素加上一个值的例子：
```cpp
void add_n(std::vector<int> &v, int n) {
    std::for_each(v.begin(), v.end(), [n](int &val) { val += n; });
}
```
在这个例子中，`[n]` 表示按值捕获外部变量 `n`。如果使用 `[&n]`，则是按引用捕获，Lambda内部对 `n` 的修改会影响外部变量。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_86.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_88.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_90.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_92.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_94.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_96.png)

---

## 迭代器类别与算法约束
并非所有算法都适用于所有容器。算法对迭代器有不同的要求，而容器提供的迭代器能力也不同。主要迭代器类别包括：
*   **输入迭代器**：只能向前读取。
*   **输出迭代器**：只能向前写入。
*   **前向迭代器**：可以多次向前读取/写入。
*   **双向迭代器**：可以向前和向后移动。
*   **随机访问迭代器**：可以任意跳转（如 `vector` 的迭代器）。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_98.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_100.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_102.png)

例如，`std::advance` 只需要输入迭代器，而 `std::binary_search` 在随机访问迭代器上具有对数复杂度，但在双向或前向迭代器上会退化为线性复杂度。

![](img/bb50045a4e130df13b3f6c5aaff5f61f_104.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_106.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_108.png)

---

![](img/bb50045a4e130df13b3f6c5aaff5f61f_110.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_112.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_113.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_115.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_116.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_118.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_120.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_122.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_123.png)

![](img/bb50045a4e130df13b3f6c5aaff5f61f_125.png)

## 总结
本节课中我们一起学习了STL算法的核心概念。我们了解了如何使用 `std::accumulate`、`std::find`、`std::transform` 等通用算法来操作容器，从而编写出更简洁、更易读的代码。我们还探讨了Lambda表达式如何与这些算法结合，以提供灵活的操作逻辑。最后，我们简要介绍了迭代器类别对算法性能的影响。掌握这些工具将帮助你更高效地使用C++标准库。