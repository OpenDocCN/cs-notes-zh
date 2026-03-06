Java全栈开发：24：Java EnumMap详解 🗺️

![](img/430a8afc619651ce29bf19ee34e6ab95_1.png)

![](img/430a8afc619651ce29bf19ee34e6ab95_3.png)

在本节课中，我们将要学习Java集合框架中的`EnumMap`类。我们将了解它的定义、特性、创建方法以及基本操作，并通过示例代码帮助初学者理解其用法。

---

### 概述

`EnumMap`是Java集合框架中一个特殊的Map实现，它专门设计用于使用枚举（Enum）类型作为键。与`HashMap`相比，它具有更高的性能，并且能保证键的自然顺序。

### EnumMap的定义与特性

上一节我们介绍了`EnumMap`的基本概念，本节中我们来看看它的具体定义和核心特性。

`EnumMap`类位于`java.util`包中，它继承自`AbstractMap`类并实现了`Map`接口。其核心特性如下：

*   **键的类型固定**：所有键必须来自同一个枚举类型。
*   **不允许空键**：尝试插入`null`键会抛出`NullPointerException`。
*   **高性能**：由于键在枚举中预先定义，内部使用数组实现，因此访问速度非常快。
*   **保持顺序**：键的顺序与它们在枚举中定义的顺序一致。

其类继承关系可以表示为：
`EnumMap` → `AbstractMap` → 实现 `Map` 接口。

### 创建EnumMap

要使用`EnumMap`，首先需要导入相应的包。以下是创建`EnumMap`的步骤。

首先，定义一个枚举类型作为键：
```java
enum Size {
    SMALL, MEDIUM, LARGE, EXTRA_LARGE
}
```

然后，在`main`方法中创建`EnumMap`实例：
```java
import java.util.EnumMap;

public class EnumMapExample {
    public static void main(String[] args) {
        EnumMap<Size, Integer> sizes = new EnumMap<>(Size.class);
    }
}
```
代码`new EnumMap<>(Size.class)`创建了一个键为`Size`枚举类型、值为`Integer`类型的`EnumMap`。

### EnumMap的基本操作

创建`EnumMap`后，我们可以向其中添加元素并进行各种操作。以下是常用的方法示例。

在创建好的`sizes`映射中添加键值对：
```java
sizes.put(Size.SMALL, 20);
sizes.put(Size.MEDIUM, 30);
sizes.put(Size.LARGE, 40);
sizes.put(Size.EXTRA_LARGE, 50);
```

现在，我们可以使用不同的方法来查看映射中的内容：

*   **获取所有键**：使用`keySet()`方法。
    ```java
    System.out.println(sizes.keySet()); // 输出: [SMALL, MEDIUM, LARGE, EXTRA_LARGE]
    ```
*   **获取所有值**：使用`values()`方法。
    ```java
    System.out.println(sizes.values()); // 输出: [20, 30, 40, 50]
    ```
*   **获取所有条目**：使用`entrySet()`方法，或直接打印整个映射。
    ```java
    System.out.println(sizes.entrySet());
    // 或直接
    System.out.println(sizes); // 输出: {SMALL=20, MEDIUM=30, LARGE=40, EXTRA_LARGE=50}
    ```
*   **获取特定键的值**：使用`get()`方法。
    ```java
    System.out.println(sizes.get(Size.MEDIUM)); // 输出: 30
    ```

此外，像`replace()`、`remove()`、`clear()`这些在集合中通用的方法，在`EnumMap`中同样适用，大家可以自行尝试。

### 总结

![](img/430a8afc619651ce29bf19ee34e6ab95_5.png)

![](img/430a8afc619651ce29bf19ee34e6ab95_7.png)

本节课中我们一起学习了`EnumMap`。我们了解到`EnumMap`是一个专为枚举键设计的高性能Map实现，它要求所有键来自同一枚举类型且不允许空键。我们学习了如何创建`EnumMap`，以及如何通过`put`、`get`、`keySet`、`values`等方法对其进行基本操作。由于其内部基于数组实现且键的顺序固定，`EnumMap`在涉及枚举键的场景下是比`HashMap`更高效的选择。