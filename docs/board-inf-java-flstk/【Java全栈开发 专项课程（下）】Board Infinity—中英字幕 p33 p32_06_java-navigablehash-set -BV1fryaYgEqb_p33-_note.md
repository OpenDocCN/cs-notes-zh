Java全栈开发：33：NavigableSet接口详解 🧭

![](img/937e4ae9576df4e93afa953933bde562_0.png)

在本节课中，我们将学习Java集合框架中的NavigableSet接口，并通过一个示例来了解其方法。

![](img/937e4ae9576df4e93afa953933bde562_2.png)

---

NavigableSet接口提供了在集合元素间导航的功能。它类似于SortedSet，但除了排序机制外，还额外提供了导航方法。为了使用NavigableSet接口的功能，我们需要使用实现了该接口的TreeSet类。NavigableSet可以按升序或降序存在和遍历，具体取决于你的导航需求。

以下是NavigableSet接口在集合框架中的层次结构：SortedSet接口扩展了NavigableSet接口，而NavigableSet则由TreeSet类实现。

上一节我们介绍了接口的基本概念，本节中我们来看看如何通过具体示例来迭代和实现NavigableSet。

![](img/937e4ae9576df4e93afa953933bde562_4.png)

以下是一个使用NavigableSet的代码示例：

```java
import java.util.NavigableSet;
import java.util.TreeSet;

![](img/937e4ae9576df4e93afa953933bde562_6.png)

public class NavigableSetExample {
    public static void main(String[] args) {
        // 创建一个NavigableSet
        NavigableSet<Integer> set = new TreeSet<>();
        set.add(10);
        set.add(20);
        set.add(30);
        set.add(40);
        set.add(50);

        // 打印原始集合
        System.out.println("Original Set: " + set);

        // 获取逆序视图
        NavigableSet<Integer> reverseSet = set.descendingSet();
        System.out.println("Reversed Set: " + reverseSet);
    }
}
```

执行此程序，输出结果为：原始集合是`[10, 20, 30, 40, 50]`，其逆序视图是`[50, 40, 30, 20, 10]`。

接下来，我们看看NavigableSet提供的其他一些核心方法。

以下是`tailSet`、`lower`、`pollFirst`和`pollLast`方法的示例：

```java
// 获取大于等于3的元素视图（此处exclusive参数为false，表示包含下限）
NavigableSet<Integer> threeOrMore = set.tailSet(3, false);
System.out.println("Elements >= 3: " + threeOrMore);

// 获取小于给定元素的最大元素
Integer lowerOfThree = set.lower(3);
System.out.println("Greatest element less than 3: " + lowerOfThree); // 输出null，因为集合中所有元素都大于3

// 检索并移除第一个（最低）元素
Integer first = set.pollFirst();
System.out.println("Polled First Element: " + first);
System.out.println("Set after pollFirst: " + set);

// 检索并移除最后一个（最高）元素
Integer last = set.pollLast();
System.out.println("Polled Last Element: " + last);
System.out.println("Set after pollLast: " + set);
```

执行这些操作后，集合中的元素`10`和`50`被依次移除。

此外，你还可以使用`contains`方法来检查集合是否包含特定元素。

```java
boolean containsFirst = set.contains(set.first());
System.out.println("Set contains its first element: " + containsFirst);
```

如果集合不为空，此检查将返回`true`。

这就是NavigableSet的基本实现方式。在实际开发中，你可以将其用于更复杂的面向对象场景，例如存储`Employee`对象或其他实体，并进行相应的操作。

![](img/937e4ae9576df4e93afa953933bde562_8.png)

---

![](img/937e4ae9576df4e93afa953933bde562_10.png)

![](img/937e4ae9576df4e93afa953933bde562_11.png)

本节课中我们一起学习了Java的NavigableSet接口。我们了解了它作为SortedSet的扩展，所提供的导航功能，并通过TreeSet示例实践了`descendingSet`、`tailSet`、`lower`、`pollFirst`、`pollLast`和`contains`等核心方法的使用。掌握这些方法有助于你在需要有序且可双向导航的数据集合时进行高效操作。