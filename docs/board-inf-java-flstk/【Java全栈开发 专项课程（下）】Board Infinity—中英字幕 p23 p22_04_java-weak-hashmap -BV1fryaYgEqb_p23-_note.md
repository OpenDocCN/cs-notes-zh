Java全栈开发：23：Java WeakHashMap详解

![](img/1865dab61d7bbef571c25e78ed221802_0.png)

在本节课中，我们将学习Java中的WeakHashMap，通过示例了解其操作，并阐明它与普通HashMap之间的区别。

---

![](img/1865dab61d7bbef571c25e78ed221802_2.png)

### 概述

WeakHashMap是基于哈希表实现的Map接口，其特点是拥有**弱键**。当某个键不再被普通使用时，其在WeakHashMap中的条目会自动被移除。它支持`null`值和`null`键，性能特征与HashMap类似，并具有相同的初始容量和负载因子参数。默认初始容量为**16**，默认负载因子为**0.75**。

上一节我们介绍了Map接口的基本概念，本节中我们来看看一个特殊的实现——WeakHashMap。

### 创建WeakHashMap

以下是创建WeakHashMap的示例代码：

![](img/1865dab61d7bbef571c25e78ed221802_4.png)

```java
WeakHashMap<String, Integer> numbers = new WeakHashMap<>();
numbers.put("One", 1);
numbers.put("Two", 2);
numbers.put("Three", 3);
```

在以上代码中，`String`类型的键是唯一标识符，`Integer`类型的值通过键关联。我们也可以指定初始容量和负载因子：

```java
WeakHashMap<String, Integer> map = new WeakHashMap<>(8, 0.6f);
```
此映射的容量为**8**，意味着它可以存储8个条目，负载因子为**0.6**。

### WeakHashMap的特性演示

现在，我们通过一个具体示例来演示WeakHashMap的核心特性，特别是其弱键和垃圾回收行为。

以下是操作步骤：

1.  **插入元素并打印**：首先，我们插入几个键值对并打印映射内容。
2.  **使用新对象作为键**：创建一个新的`String`对象作为键插入，并打印映射。
3.  **将键引用置为null并触发垃圾回收**：将该键的引用置为`null`，然后显式调用垃圾回收，再次打印映射以观察变化。

```java
public class WeakHashMapDemo {
    public static void main(String[] args) {
        // 1. 创建并初始化WeakHashMap
        WeakHashMap<String, Integer> numbers = new WeakHashMap<>();
        numbers.put("One", 1);
        numbers.put("Two", 2);
        numbers.put("Three", 3);
        System.out.println("初始WeakHashMap: " + numbers);

        // 2. 使用新创建的String对象作为键
        String keyFour = new String("Four");
        numbers.put(keyFour, 4);
        System.out.println("插入‘Four’后: " + numbers);

        // 3. 将键引用置为null并触发垃圾回收
        keyFour = null;
        System.gc(); // 建议JVM进行垃圾回收

        // 等待一下，让GC有机会运行
        try {
            Thread.sleep(1000);
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        System.out.println("GC后，键‘Four’被移除: " + numbers);
    }
}
```

**代码解析与输出**：
*   初始打印会显示包含`"One"`, `"Two"`, `"Three"`的映射。
*   插入`keyFour`（值为`"Four"`的新对象）后，映射会包含四个条目。
*   当我们将`keyFour`引用置为`null`并调用`System.gc()`后，由于`"Four"`这个键除了WeakHashMap内部的弱引用外已无其他强引用，它便成为垃圾回收的候选对象。垃圾回收后，对应的条目（`"Four" -> 4`）会从WeakHashMap中自动移除。因此，最后的输出将不再包含键`"Four"`。

这个例子清晰地展示了**弱键**如何工作：一旦键对象失去所有强引用，它就可以被垃圾回收器回收，同时WeakHashMap会自动清理对应的映射条目。

### WeakHashMap与HashMap的区别

理解了基本操作后，我们来总结一下WeakHashMap与普通HashMap的核心区别。

以下是主要差异点：

*   **键的引用强度**：
    *   **HashMap**：使用**强引用**持有键。只要HashMap实例存在，其内的键即使在其他地方已无引用，也不会被垃圾回收。
    *   **WeakHashMap**：使用**弱引用**持有键。如果某个键对象在WeakHashMap之外没有其他强引用指向它，那么当垃圾回收器运行时，该键对象可以被回收，同时WeakHashMap中的对应条目会被自动移除。
*   **内存管理**：WeakHashMap的这种特性使其适用于需要缓存数据，但又不想阻止键对象被垃圾回收的场景（例如缓存大型对象的映射）。而HashMap可能造成内存泄漏，如果不再使用的键被长期保留在映射中。
*   **允许null键**：两者都允许`null`键和`null`值。

### 常用方法

WeakHashMap继承了`AbstractMap`并实现了`Map`接口，因此它包含了Map的标准方法。以下是一些关键方法：

*   `put(K key, V value)`: 将指定值与此映射中的指定键关联。
*   `get(Object key)`: 返回指定键所映射的值。
*   `remove(Object key)`: 如果存在，则从此映射中移除键的映射关系。
*   `containsKey(Object key)`: 如果此映射包含指定键的映射关系，则返回`true`。
*   `keySet()`: 返回此映射中包含的键的`Set`视图。
*   `values()`: 返回此映射中包含的值的`Collection`视图。
*   `entrySet()`: 返回此映射中包含的映射关系的`Set`视图。

这些方法的用法与HashMap中一致。

---

### 总结

![](img/1865dab61d7bbef571c25e78ed221802_6.png)

本节课中我们一起学习了Java WeakHashMap。我们了解了它是一个基于弱键实现的Map，当键不再被外部强引用时，其条目会被自动清理。我们通过代码示例演示了这一核心特性，并对比了WeakHashMap与普通HashMap在键引用强度和适用场景上的主要区别。掌握WeakHashMap有助于在特定场景下（如实现缓存）进行更优雅的内存管理。