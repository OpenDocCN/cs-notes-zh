# 密歇根大学《给所有人的C语言编程课》：10_04_02：探索跨语言的映射抽象 🗺️

![](img/6b0334a926013101f9937f8bd835b793_0.png)

![](img/6b0334a926013101f9937f8bd835b793_2.png)

在本节课中，我们将深入探讨“抽象”的概念。我们将以一个接口为例，比较它在多种不同编程语言中的实现。我们将这种抽象称为“映射”（Map）。映射是一个通用术语，用于抽象地描述键值对集合。每种语言对其都有不同的命名。我们将学习映射的基本操作，并了解“迭代器模式”作为一种用于遍历多种实现的抽象方法。

## 映射：一个跨语言的抽象概念

上一节我们介绍了抽象的概念，本节中我们来看看一个具体的抽象：映射。映射是一种常见的数据结构，用于存储键值对。尽管核心概念相同，但不同编程语言对其命名和实现方式各有不同。

以下是几种语言中映射的名称：
*   **C++**： 直接称之为 `map`。
*   **Python**： 称之为 `dictionary`（字典）。
*   **Java**： 也称之为 `Map`（注意首字母大写）。
*   **PHP**： 称之为 `array`（数组）。
*   **JavaScript**： 实际上使用 `Object`（对象）来实现类似功能。

## 迭代器模式：遍历的抽象

为了遍历映射中的元素，我们使用迭代器模式。迭代器是一个对象，它提供了一种顺序访问集合元素的方法，而无需暴露其底层表示。其核心思想是避免一次性复制所有数据，而是通过一个“指针”逐步推进。

迭代器的基本操作通常遵循以下模式：
```python
# 伪代码示例
iterator = collection.get_iterator()
while iterator.has_next():
    item = iterator.next()
    # 处理 item
```

## 各语言中的映射与迭代示例

现在，让我们通过具体代码，看看上述概念在几种流行语言中是如何实现的。

![](img/6b0334a926013101f9937f8bd835b793_4.png)

![](img/6b0334a926013101f9937f8bd835b793_5.png)

![](img/6b0334a926013101f9937f8bd835b793_6.png)

### Python 示例

![](img/6b0334a926013101f9937f8bd835b793_8.png)

![](img/6b0334a926013101f9937f8bd835b793_10.png)

![](img/6b0334a926013101f9937f8bd835b793_11.png)

在Python中，映射通过字典实现。以下是创建字典、添加元素、访问元素以及使用迭代器遍历的示例。

```python
# 创建字典
d = {}
# 添加键值对，重复键会覆盖旧值
d[‘z‘] = 8
d[‘z‘] = 1  # 覆盖，最终 d[‘z‘] 为 1
d[‘x‘] = 9
d[‘b‘] = 3
d[‘a‘] = 4

# 打印字典
print(d)

# 使用 get 方法安全访问，键不存在时返回默认值 42
value_z = d.get(‘z‘, 42)
value_x = d.get(‘x‘, 42)  # ‘x‘ 不存在，返回 42
print(f“z = {value_z}, x = {value_x}“)

# 获取字典项目的迭代器
items_iter = d.items()
# 使用 next() 函数手动迭代
entry = next(items_iter, False)
while entry:
    print(entry)
    entry = next(items_iter, False)
```
**代码说明**：`d.items()` 返回一个视图对象（迭代器），`next()` 函数用于从中获取下一个键值对。当没有更多元素时，返回我们指定的默认值 `False`，循环终止。

### PHP 示例

![](img/6b0334a926013101f9937f8bd835b793_13.png)

在PHP中，数组（`array`）可以充当映射。以下是等效操作。

![](img/6b0334a926013101f9937f8bd835b793_15.png)

```php
// 创建数组（作为映射使用）
$a = array();
// 添加元素，重复键会覆盖
$a[‘z‘] = 8;
$a[‘z‘] = 1; // 覆盖
$a[‘x‘] = 9;
$a[‘b‘] = 3;
$a[‘a‘] = 4;

![](img/6b0334a926013101f9937f8bd835b793_16.png)

// 打印数组
print_r($a);

![](img/6b0334a926013101f9937f8bd835b793_18.png)

![](img/6b0334a926013101f9937f8bd835b793_19.png)

// 使用 null 合并运算符 ?? 进行安全访问（PHP 7+）
$value_z = $a[‘z‘] ?? 42;
$value_x = $a[‘x‘] ?? 42; // ‘x‘ 不存在，返回 42
echo “z = $value_z, x = $value_x\n“;

// 使用 foreach 循环迭代（PHP内置的迭代抽象）
foreach ($a as $key => $value) {
    echo “$key => $value\n“;
}
```
**代码说明**：PHP 的 `foreach` 结构内部实现了迭代器模式，开发者无需直接操作迭代器对象即可遍历数组。

### C++ 示例

![](img/6b0334a926013101f9937f8bd835b793_21.png)

C++ 使用 `std::map`，并且是强类型语言，需要指定键和值的类型。

```cpp
#include <iostream>
#include <map>
#include <string>

int main() {
    // 声明一个映射，键为string，值为int
    std::map<std::string, int> mp;

    // 插入元素，使用下标操作符，重复键会覆盖
    mp[“z“] = 8;
    mp[“z“] = 1; // 覆盖
    mp[“y“] = 2;
    mp[“b“] = 3;
    mp[“a“] = 4;

    // 模拟 get 操作：检查键是否存在
    // count(‘z‘) 返回键 ‘z‘ 出现的次数（0或1）
    int value_z = (mp.count(“z“) > 0) ? mp[“z“] : 42;
    int value_x = (mp.count(“x“) > 0) ? mp[“x“] : 42; // ‘x‘ 不存在，返回 42
    std::cout << “z = “ << value_z << “, x = “ << value_x << std::endl;

    // 使用迭代器遍历
    // auto 关键字自动推导迭代器类型
    for (auto cur = mp.begin(); cur != mp.end(); ++cur) {
        // cur->first 是键，cur->second 是值
        std::cout << cur->first << “ => “ << cur->second << std::endl;
    }
    return 0;
}
```
**代码说明**：`mp.begin()` 和 `mp.end()` 返回迭代器，分别指向第一个元素和“尾后”位置。迭代器通过 `++` 操作符前进，通过 `->first` 和 `->second` 访问键和值。

### Java 示例

Java 中，`Map` 是一个接口，`TreeMap` 是其一种有序的实现。Java 倾向于使用方法调用而非操作符重载。

```java
import java.util.Map;
import java.util.TreeMap;

public class Main {
    public static void main(String[] args) {
        // 声明一个 Map 接口的引用，指向 TreeMap 实现
        Map<String, Integer> map = new TreeMap<>();

        // 使用 put 方法插入键值对
        map.put(“z“, 8);
        map.put(“z“, 1); // 覆盖
        map.put(“y“, 2);
        map.put(“b“, 3);
        map.put(“a“, 4);

        // 打印 Map
        System.out.println(map);

        // 使用 getOrDefault 方法安全访问
        int valueZ = map.getOrDefault(“z“, 42);
        int valueX = map.getOrDefault(“x“, 42); // ‘x‘ 不存在，返回 42
        System.out.println(“z = “ + valueZ + “, x = “ + valueX);

        // 使用 for-each 循环和 entrySet 进行迭代
        // Map.Entry 代表一个键值对条目
        for (Map.Entry<String, Integer> entry : map.entrySet()) {
            // 使用 getKey() 和 getValue() 方法获取键和值
            System.out.println(entry.getKey() + “ => “ + entry.getValue());
        }
    }
}
```
**代码说明**：`map.entrySet()` 返回一个 `Set<Map.Entry>`，它实现了 `Iterable` 接口，因此可以直接用于 for-each 循环。Java 习惯使用 `getKey()` 和 `getValue()` 这样的访问器方法来获取数据。

![](img/6b0334a926013101f9937f8bd835b793_23.png)

## 总结

![](img/6b0334a926013101f9937f8bd835b793_25.png)

![](img/6b0334a926013101f9937f8bd835b793_27.png)

本节课中，我们一起学习了“映射”这一核心数据抽象及其在不同编程语言（Python、PHP、C++、Java）中的具体实现。尽管语法和命名各异（如字典、数组、Map），但它们都提供了存储和访问键值对的基本功能。我们还探讨了“迭代器模式”，它是遍历集合元素的通用抽象，允许我们无需了解底层数据结构细节即可访问所有元素。理解这些跨语言的抽象概念，有助于我们更深刻地把握编程的本质，并在学习新语言时快速触类旁通。