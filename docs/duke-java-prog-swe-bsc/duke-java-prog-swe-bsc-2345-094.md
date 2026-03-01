# 094：ArrayList类总结 📚

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_0.png)

在本节课中，我们将总结Java中`ArrayList`类的核心概念和用法。`ArrayList`是一种动态数组，它比传统数组更灵活，可以在运行时自动调整大小。我们将回顾其创建、基本操作以及遍历方法。

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_2.png)

---

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_3.png)

## 概述 📋

`ArrayList`类似于数组，两者都是可索引的集合，允许你使用整数索引访问元素。`ArrayList`的独特之处在于，它可以在添加元素时动态增长，这意味着你无需像使用数组那样预先知道需要分配多少空间。

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_5.png)

---

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_6.png)

## ArrayList与数组的异同 🔄

`ArrayList`和数组都是可索引的集合，你可以使用整数索引访问其中的元素。然而，`ArrayList`可以在添加元素时自动增长，而数组的大小在创建时是固定的。

与数组和单个字符串元素一样，`ArrayList`的索引也是从0开始的。访问`ArrayList`的第一个元素与访问第1000个元素所需的时间是相同的。你可以将列表想象成一系列带有编号的盒子。

---

## 导入与创建ArrayList 📦

要使用`ArrayList`类，你必须从`java.util`包中导入它。你可以只导入`ArrayList`类，也可以使用星号导入整个包中的所有类，例如`Random`类。

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_8.png)

创建`ArrayList`时，你需要使用尖括号语法指定列表中存储的元素类型，这是Java用于泛型或通用元素的语法。

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_9.png)

以下是一个存储`String`对象的`ArrayList`示例：

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_11.png)

```java
import java.util.ArrayList;

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_13.png)

ArrayList<String> stringList = new ArrayList<String>();
```

列表也可以存储`Integer`对象：

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_15.png)

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_16.png)

```java
ArrayList<Integer> integerList = new ArrayList<Integer>();
```

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_18.png)

请注意，一个列表必须统一存储整数或字符串，不能在同一列表中混合存储不同类型。

`Integer`类允许将`int`值（如0、57或-352）作为`Integer`对象存储在`ArrayList`中。`Integer`类会自动将`int`值（如57）转换为`Integer`对象。

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_20.png)

---

## ArrayList的常用方法 🛠️

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_22.png)

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_23.png)

你已经了解了`ArrayList`对象的几种常用方法。

*   **`.add` 方法**：向`ArrayList`的末尾添加一个元素。`ArrayList`会根据需要自动增长。
*   **`.size` 方法**：返回`ArrayList`中存储的元素数量。这通常等于通过`.add`方法添加的元素数量。
*   **`.get` 方法**：使用整数索引访问`ArrayList`中的单个元素。
*   **`.set` 方法**：更改存储在特定索引处的值。

---

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_25.png)

## 遍历ArrayList 🔁

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_27.png)

`ArrayList`通常使用循环进行处理和访问。

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_29.png)

### 使用索引循环遍历

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_31.png)

以下是一个典型的索引循环，用于处理`ArrayList`的每个元素：

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_32.png)

```java
for (int k = 0; k < myList.size(); k++) {
    String value = myList.get(k);
    // 处理 value
}
```

这种循环通常从0开始，循环条件为小于`ArrayList`的大小（即`.size()`返回的值）。在循环内部，使用`.get`方法和循环索引变量访问每个数组元素。

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_34.png)

**重要提示**：在这种循环中访问数组元素时，**不要**调用`.add`或`.remove`方法，因为这些方法会在循环迭代时改变列表的大小，通常会导致算法出现问题，因为你可能会跳过某些元素或访问无效元素。

### 使用迭代循环遍历

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_36.png)

你也可以使用迭代循环（即我们用于Edu.Duke可迭代类的同类型循环）来访问`ArrayList`中的元素。

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_38.png)

```java
for (String value : myList) {
    // 处理 value
}
```

在迭代循环中，你的代码需要指明`ArrayList`中存储的值的类型。循环会依次取出`ArrayList`中存储的每个值，就像处理`FileResource`或`ImageResource`类一样。

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_40.png)

当你不需要每个`ArrayList`元素的索引，而只需要元素本身时，可以使用这种循环。

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_42.png)

**重要提示**：与索引循环一样，在迭代循环中**不要**调用`.add`或`.remove`方法。在这种情况下，如果你尝试这样做，Java会产生运行时错误。

---

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_44.png)

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_45.png)

## 总结 🎯

![](img/7c5d0b89b05bf4b6f03ab67d148bbb74_47.png)

本节课我们一起学习了Java中`ArrayList`类的核心知识。我们了解到`ArrayList`是一种动态、可增长的集合，比传统数组更灵活。我们学习了如何导入和创建指定类型的`ArrayList`，掌握了`.add`、`.size`、`.get`和`.set`等基本操作方法。最后，我们重点探讨了两种遍历`ArrayList`的方式：基于索引的`for`循环和更简洁的迭代`for-each`循环，并强调了在遍历过程中避免修改列表结构的重要性。正确使用`ArrayList`是Java编程中一项非常有用的技能。