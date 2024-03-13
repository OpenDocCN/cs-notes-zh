# 3\.   搜索

> 原文：[`algs4.cs.princeton.edu/30searching`](https://algs4.cs.princeton.edu/30searching)

## 概述。

现代计算和互联网使得大量信息变得可访问。高效搜索这些信息的能力对计算至关重要。本章描述了几十年来在众多应用中证明有效的经典*搜索*算法。我们使用术语*符号表*来描述一个抽象机制，我们可以保存信息（一个*值*），��后通过指定一个*键*进行搜索和检索。

+   *3.1 基础符号表*包括无序和有序的实现，使用数组或链表。

+   *3.2 二叉查找树*描述了二叉查找树。

+   *3.3 平衡查找树*描述了红黑树，这是一种保证每个符号表操作具有对数性能的数据结构。

+   *3.4 哈希表*描述了两种经典的哈希算法：分离链接和线性探测。

+   *3.5 应用*介绍了集合数据类型，并包括了符号表和集合的众多应用。

## 本章的 Java 程序。

以下是本章的 Java 程序列表。点击程序名称以访问 Java 代码；点击参考号以获取简要描述；阅读教材以获取详细讨论。

> | REF | 程序 | 描述 / JAVADOC |
> | --- | --- | --- |
> | - | FrequencyCounter.java | 频率计数器 |
> | 3.1 | SequentialSearchST.java | 顺序查找 |
> | 3.2 | BinarySearchST.java | 二分查找 |
> | 3.3 | BST.java | 二叉查找树 |
> | 3.4 | RedBlackBST.java | 红黑树 |
> | 3.5 | SeparateChainingHashST.java | 分离链接哈希表 |
> | 3.6 | LinearProbingHashST.java | 线性探测哈希表 |
> | - | ST.java | 有序符号表 |
> | - | SET.java | 有序集合 |
> | - | DeDup.java | 去重 |
> | - | AllowFilter.java | 允许列表过滤器 |
> | - | BlockFilter.java | 阻止列表过滤器 |
> | - | LookupCSV.java | 字典查找 |
> | - | LookupIndex.java | 索引和倒排索引 |
> | - | FileIndex.java | 文件索引 |
> | - | SparseVector.java | 稀疏向量 |
