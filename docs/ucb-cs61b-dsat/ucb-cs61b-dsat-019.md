# 19：讨论课 05 内容回顾

![](img/eee5baf3bc5adf7412c9a1620d8d59eb_1.png)

## 概述
在本节课中，我们将要学习迭代器、可迭代对象和多态性。这些是Java编程中用于处理集合和创建通用、灵活代码的核心概念。

## 多态性简介
多态性描述了方法能够处理多种类型的能力。这使我们能够编写更通用的代码，或者说，创建一个能与多种类型协同工作的统一接口。

在Java中，我们常使用泛型来实现这一点，用一个占位符（如字母 **T**）来代表某种通用的对象类型。

**代码示例：**
```java
public class LinkedListDeck<T> {
    // T 可以是 String, Integer, 或任何其他对象类型
}
```

上一节我们介绍了多态性的基本概念，本节中我们来看看一种更具体的多态形式。

## 子类型多态性
子类型多态性描述了一个类或接口的子类型也是该类或接口的实例这一事实。

例如，如果我们有一个 `Animal` 父类，以及 `Dog` 和 `Cat` 子类。那么，任何接受 `Animal` 类型参数的函数，也可以接受一个 `Dog` 或 `Cat` 类型的实例，因为狗和猫本身也是动物。

**公式描述：**
如果 `Dog extends Animal`，那么 `Dog` 的实例也是 `Animal` 的实例。

一个更具体的例子是使用泛型绑定。我们可以创建一个 `ComparableArray<T>` 类，其中 **T** 被限定为实现 `Comparable` 接口的类型。这样，`ComparableArray` 就可以与任何可比较的类型一起工作。

**代码示例：**
```java
public class ComparableArray<T extends Comparable<T>> implements Comparable<ComparableArray<T>> {
    // 类内部可以安全地调用 T 类型的 compareTo 方法
    public int compareElements(T item1, T item2) {
        return item1.compareTo(item2); // 可行，因为 T 是 Comparable 的
    }
}
```

理解了子类型多态性后，我们来看一个在Java中非常常见的应用实例。

## 比较器接口
比较器是Java中展示多态性的一个典型例子。`Comparator<T>` 是一个接口，它定义了一种比较两个 **T** 类型对象的方法。

以下是 `Comparator` 接口的核心方法：

**代码示例：**
```java
public interface Comparator<T> {
    int compare(T o1, T o2);
}
```
`compare` 方法返回一个整数：
*   如果 `o1` 小于 `o2`，返回负整数。
*   如果 `o1` 大于 `o2`，返回正整数。
*   如果 `o1` 等于 `o2`，返回 0。

这里的“小于”、“大于”和“等于”的含义由实现 `Comparator` 接口的类来定义。例如，对于 `Dog` 类，我们可以定义按名字字母顺序比较，或者按年龄比较。接口只规定“如何调用”，而具体类决定“如何实现”。

在深入迭代器之前，我们先快速回顾一下类和接口的关系，这有助于理解后续内容。

## 接口与继承回顾
*   一个类可以实现多个接口，但只能继承一个父类。
*   接口告诉我们“要做什么”，但不提供具体实现；类则告诉我们“如何去做”。
*   实现接口的类必须填充接口中定义的方法体（除非是默认方法）。
*   子类通过 `extends` 关键字继承父类。它们会继承父类所有的非私有实例变量、静态变量和方法（可被重写）以及嵌套类。
*   子类不继承父类的构造器。要调用父类的构造器或方法，需使用 `super` 关键字。

**代码示例：**
```java
public class Dog extends Animal {
    public Dog(String name) {
        super(name); // 调用父类 Animal 的构造器
    }
    
    public void barkTwice() {
        super.bark(); // 调用父类 Animal 的 bark 方法
        super.bark();
    }
}
```

掌握了这些基础后，我们现在可以探讨两个对本课至关重要的接口。

## 迭代器与可迭代对象
迭代器是可以在Java循环中遍历的对象。`Iterator<T>` 是一个接口。

任何实现 `Iterator` 接口的类都必须实现以下两个方法：

**代码示例：**
```java
public interface Iterator<T> {
    boolean hasNext();
    T next();
}
```
*   `hasNext()`: 如果迭代器中还有剩余元素可供遍历，则返回 `true`。
*   `next()`: 返回迭代器中的下一个 **T** 类型的元素。

可迭代对象是能够生成迭代器的对象。`Iterable<T>` 也是一个接口。

实现 `Iterable` 接口的类需要实现以下方法：

**代码示例：**
```java
public interface Iterable<T> {
    Iterator<T> iterator();
}
```

那么，这两者如何协同工作呢？我们通过增强型for循环来理解。

## 增强型for循环的原理
你可能见过这样的语法：
```java
for (String x : listOfStrings) {
    // 处理 x
}
```
这种语法之所以能工作，是因为 `List`、`Set` 和数组都实现了 `Iterable` 接口。

上面的增强型for循环实际上是以下代码的简写：

**代码示例：**
```java
Iterator<String> iter = listOfStrings.iterator();
while (iter.hasNext()) {
    String x = iter.next();
    // 处理 x
}
```
当我们使用冒号 `:` 时，Java会自动调用可迭代对象（`listOfStrings`）的 `iterator()` 方法来获取一个迭代器，然后使用 `hasNext()` 和 `next()` 方法进行遍历。

为了检验理解，以下是几个概念性问题：

**概念检查：**
1.  定义一个实现 `Iterable<Dog>` 接口的类，需要实现什么方法？
    *   `public Iterator<Dog> iterator()`
2.  定义一个实现 `Iterator<Integer>` 接口的类，需要实现什么方法？
    *   `public boolean hasNext()`
    *   `public Integer next()`
3.  `Iterator` 和 `Iterable` 的区别是什么？
    *   **迭代器** 是实际进行遍历的对象，你可以把它想象成在集合上移动并逐个“吐出”元素的指针。
    *   **可迭代对象** 是能够产生迭代器的对象，通常是某种集合（如列表、数组）。数组是可迭代的，而数组的迭代器可以逐个访问数组的每个索引。

最后，我们来区分一个在Java中容易混淆的操作。

## `==` 与 `.equals()` 的区别
`==` 和 `.equals()` 各有用途。

`==` 操作符比较的是变量存储位置的原始比特位。它通常用于基本数据类型（如 `int`, `char`）。

对于引用类型（对象），`==` 比较的是两个变量指向的内存地址是否相同。这可以用来判断两个引用是否指向内存中的同一个对象。

**例外情况：** `null` 是一个特殊的指针，几乎总是使用 `==` 来比较。

`.equals()` 方法是所有Java对象都从 `Object` 类继承的方法。它的默认行为与 `==` 相同，即比较内存地址。

但是，`.equals()` 方法可以在每个类中被重写，以定义什么样的两个对象应该被视为“逻辑上相等”。例如，即使两个 `List` 对象位于不同的内存地址，如果它们包含相同的元素序列，我们可能希望认为它们相等。

**示例说明：**
假设我们定义 `Dog` 类的 `.equals()` 方法：当且仅当两只狗的名字相同时返回 `true`。

```java
Dog fido = new Dog("Fido");
Dog otherFido = new Dog("Fido");

boolean test1 = (fido == otherFido); // false，指向两个不同的内存对象
boolean test2 = fido.equals(otherFido); // true，因为我们重写的 equals 方法只比较名字
```

## 总结
本节课中我们一起学习了：
1.  **多态性**：编写通用代码的能力，通过泛型 **T** 和接口实现。
2.  **子类型多态**：子类实例可被视作父类类型使用。
3.  **比较器**：`Comparator<T>` 接口允许我们自定义对象的比较逻辑。
4.  **迭代器与可迭代对象**：`Iterator<T>` 用于遍历，`Iterable<T>` 用于生成迭代器，它们是增强型for循环的基础。
5.  **`==` 与 `.equals()`**：`==` 比较引用（内存地址），`.equals()` 默认比较引用，但可被重写为比较对象内容。

![](img/eee5baf3bc5adf7412c9a1620d8d59eb_3.png)

理解这些概念对于编写灵活、可重用和高效的Java代码至关重要。