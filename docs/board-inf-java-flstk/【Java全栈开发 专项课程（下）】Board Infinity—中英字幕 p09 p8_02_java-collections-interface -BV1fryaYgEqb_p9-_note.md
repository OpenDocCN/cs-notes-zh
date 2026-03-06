Java全栈开发：09：集合框架与Collection接口 🎯

![](img/f90e5335d899ca6bffc1aaaed63a5424_1.png)

在本节课中，我们将要学习Java集合框架的基础，特别是其根接口——Collection接口。我们将了解它的作用、基本操作以及它在整个框架中的位置。

![](img/f90e5335d899ca6bffc1aaaed63a5424_2.png)

上一节我们介绍了集合框架的整体概念，它是一个由接口和类组成的层次化结构。本节中我们来看看这个结构的根基：Collection接口。

Collection接口是整个集合框架构建的基石。它是一个通用接口，本身没有具体的实现声明。在定义时，我们使用泛型来指定该集合将要持有的对象类型。例如，如果集合要存储整数或字符串，我们需要在初始化实现此接口的类时传递相应的类型。

它提供了一系列基础操作，用于管理集合中的元素。以下是Collection接口定义的一些核心方法：

*   **添加元素**：`boolean add(E e)`
*   **移除元素**：`boolean remove(Object o)`
*   **清空集合**：`void clear()`
*   **检查是否为空**：`boolean isEmpty()`
*   **获取大小**：`int size()`
*   **检查是否包含某元素**：`boolean contains(Object o)`

List、Queue和Set是三个重要的组件，它们都扩展（extends）了Collection接口。而集合框架中的所有具体类（如ArrayList, LinkedList, HashSet等）则实现了这些子接口。

因此，主要的层次关系是：Iterable接口被Collection接口扩展，然后List、Queue、Set等接口又扩展了Collection接口。这些子接口最终由具体的类来实现，例如LinkedList、PriorityQueue、HashSet等等。

![](img/f90e5335d899ca6bffc1aaaed63a5424_4.png)

本节课中我们一起学习了Collection接口的核心地位与基本功能。它是操作所有集合类型的通用契约，为添加、删除、检查元素等操作提供了统一的方法定义。理解它是深入学习具体集合类（如List, Set, Queue）的关键第一步。在接下来的课程中，我们将继续探讨这些扩展接口及其实现类。