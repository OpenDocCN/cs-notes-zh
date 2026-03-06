# Java全栈开发：11：ArrayList详解

![](img/c8bcba8d1fe4f590275649e58248630e_0.png)

![](img/c8bcba8d1fe4f590275649e58248630e_2.png)

在本节课中，我们将要学习一个实现了List接口的重要类——ArrayList。我们将了解它的特性、常用方法以及如何在代码中实际使用它。

---

## 概述

ArrayList是Java集合框架中的一个核心类。它类似于数组，但提供了动态调整大小的能力，因此也被称为动态数组。它实现了List接口，这意味着它支持有序的元素集合，并允许重复元素。

上一节我们介绍了List接口，本节中我们来看看它的一个具体实现——ArrayList。

---

## ArrayList的特性

ArrayList的核心特性在于其动态性。与普通数组不同，ArrayList在创建时无需指定固定大小。其容量会根据元素的添加或删除自动增长或缩减。

以下代码展示了如何声明和初始化一个ArrayList：
```java
import java.util.ArrayList;
ArrayList<String> list = new ArrayList<>();
```

需要注意的是，ArrayList不能用于存储基本数据类型（如`int`， `char`）。正如在List接口中讨论的，必须使用对应的包装类（如`Integer`， `Character`）。

---

## ArrayList的常用方法

以下是ArrayList类中一些非常常用和重要的方法。掌握这些方法对于有效操作集合至关重要。

*   **add(E e)**： 将指定元素追加到列表的末尾。
*   **add(int index, E element)**： 将元素插入到列表中的指定位置。
*   **clear()**： 移除列表中的所有元素。
*   **get(int index)**： 返回列表中指定位置的元素。
*   **indexOf(Object o)**： 返回指定元素在列表中首次出现的索引，如果不存在则返回-1。
*   **lastIndexOf(Object o)**： 返回指定元素在列表中最后一次出现的索引。
*   **remove(Object o)**： 移除列表中首次出现的指定元素。
*   **remove(int index)**： 移除列表中指定位置的元素。
*   **size()**： 返回列表中的元素数量。
*   **trimToSize()**： 将此ArrayList实例的容量调整为列表的当前大小。

---

## 实践：使用ArrayList

现在，让我们通过一个简单的例子来理解ArrayList在实际编程中如何工作。

首先，我们创建一个存储字符串的ArrayList，并向其中添加几个元素。

```java
import java.util.ArrayList;

public class ArrayListDemo {
    public static void main(String[] args) {
        // 初始化一个ArrayList
        ArrayList<String> nameList = new ArrayList<>();

        // 使用add方法添加元素
        nameList.add("King");
        nameList.add("Sia");
        nameList.add("Sarah");

        // 方法1：直接打印整个列表
        System.out.println("整个列表: " + nameList);

        // 方法2：使用增强for循环遍历列表
        System.out.println("遍历列表:");
        for (String name : nameList) {
            System.out.println(name);
        }

        // 获取列表大小
        System.out.println("列表大小: " + nameList.size());

        // 移除指定索引的元素（索引0，即"King"）
        nameList.remove(0);
        System.out.println("移除第一个元素后: " + nameList);

        // 再次检查大小
        System.out.println("新列表大小: " + nameList.size());
    }
}
```

运行上述代码，你将看到列表的初始内容、遍历结果，以及在移除一个元素后列表发生的变化。这演示了如何使用`add`、`size`和`remove`等基本方法。

---

## 总结

![](img/c8bcba8d1fe4f590275649e58248630e_4.png)

![](img/c8bcba8d1fe4f590275649e58248630e_6.png)

本节课中我们一起学习了Java集合框架中的ArrayList。我们了解到它是一个**动态数组**，可以自动调整大小。我们学习了其核心特性、常用方法（如`add`， `remove`， `size`），并通过一个完整的代码示例实践了如何创建、填充、遍历和修改一个ArrayList。掌握ArrayList是进行Java集合操作的重要基础。