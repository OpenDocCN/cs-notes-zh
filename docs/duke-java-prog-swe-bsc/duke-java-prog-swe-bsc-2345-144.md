Java编程和软件工程基础：2-5：两种排序方式的总结 🎯

在本节课中，我们将总结Java中定义对象排序顺序的两种核心方法：`Comparable`接口和`Comparator`接口。理解这两种方式的区别与适用场景，是掌握Java集合排序的关键。

---

你已经学习了两种不同的方式来为一个类型定义排序顺序。

![](img/ecaf3bfdb51e6625d1ac2d4c0423de91_0.png)

---

### `Comparable`接口：定义自然顺序

`Comparable`接口允许一个类通过实现其承诺的 `compareTo` 方法来定义自身的**自然排序**。

这意味着，如果一个类实现了`Comparable`接口，它就拥有了一个默认的、与生俱来的比较规则。例如，`String`类实现了`Comparable`，所以字符串可以根据字典序自动排序。

![](img/ecaf3bfdb51e6625d1ac2d4c0423de91_2.png)

其核心方法是：
```java
public int compareTo(T o);
```
该方法将当前对象与指定对象进行比较，返回负整数、零或正整数，分别表示当前对象小于、等于或大于指定对象。

---

### `Comparator`接口：定义外部比较器

而`Comparator`接口允许一个类为**其他类型**定义一种排序规则，通过实现其承诺的 `compare` 方法。

当你无法修改类的源代码（例如使用第三方库的类），或者需要为同一个类提供多种不同的排序方式时，`Comparator`就非常有用。它是一个独立的“比较器”。

其核心方法是：
```java
int compare(T o1, T o2);
```
该方法比较两个参数对象`o1`和`o2`，同样返回负整数、零或正整数来表示它们的大小关系。

![](img/ecaf3bfdb51e6625d1ac2d4c0423de91_4.png)

---

![](img/ecaf3bfdb51e6625d1ac2d4c0423de91_5.png)

### 如何选择使用

这两种方式都可以用来指定集合（如`ArrayList`）在进行排序时应使用的排序标准。

上一节我们介绍了两种接口的定义，本节中我们来看看如何在实际的集合排序中应用它们。

以下是使用`Collections.sort`方法时的两种典型场景：

*   **使用自然排序（`Comparable`）**：当列表中的元素类已经实现了`Comparable`接口时，可以直接排序。
    ```java
    Collections.sort(list); // list中的元素必须实现Comparable
    ```

*   **使用自定义比较器（`Comparator`）**：可以传入一个`Comparator`对象来指定排序规则，这不会影响元素类本身的`compareTo`方法。
    ```java
    Collections.sort(list, customComparator); // 使用自定义的比较器
    // 或者在Java 8+中使用Lambda表达式
    Collections.sort(list, (o1, o2) -> o1.getField() - o2.getField());
    ```

---

### 总结

本节课中我们一起学习了Java中实现对象排序的两种核心机制。

*   **`Comparable`（可比较的）**：用于定义对象**内部的、默认的**自然排序顺序。通过实现`compareTo`方法实现。
*   **`Comparator`（比较器）**：用于定义**外部的、灵活的**排序规则，尤其适用于为无法修改的类或多个排序标准提供支持。通过实现`compare`方法实现。

掌握这两种接口，你就能灵活地控制Java集合中元素的排列顺序，满足各种复杂的排序需求。