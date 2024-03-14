# 4\. 算法和数据结构

> 原文：[`introcs.cs.princeton.edu/python/40algorithms`](https://introcs.cs.princeton.edu/python/40algorithms)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)


本章介绍了作为各种应用的基本构建块的基本数据类型。我们提供完整的实现，尽管其中一些内置在 Python 中，这样你就可以清楚地了解它们的工作原理以及它们为什么重要。

本章介绍的算法和数据结构构成了过去几十年发展的一系列知识，为计算机在各种应用中的高效使用奠定了基础。随着计算应用范围的不断扩大，这些基本方法的影响也在不断增长。

+   *4.1 性能*概述了一种科学方法和强大的理论，用于理解我们编写的程序的性能和资源消耗。

+   *4.2 排序和搜索*描述了两种经典算法——归并排序和二分查找——以及它们的效率在几个关键应用中起着重要作用。

+   *4.3 栈和队列*介绍了两种密切相关的数据结构，用于操作任意大量的数据集合。

+   *4.4 符号表*考虑了一种称为符号表的基本数据结构，用于存储信息，以及一种高效的实现称为二叉搜索树。

+   *4.5 小世界现象*提供了一个案例研究，以调查小世界现象——我们都通过短链条的熟人联系相互联系。

## 本章的 Python 程序

下面是本章中的 Python 程序列表。

> | **REF** | **PROGRAM** | **DESCRIPTION** | **DATA** |
> | --- | --- | --- | --- |
> | 4.1.1 | threesum.py | 3-sum 问题 | 8ints.txt  1kints.txt  2kints.txt  4kints.txt  8kints.txt  16kints.txt  32kints.txt  64kints.txt  128kints.txt   |
> | 4.1.2 | doublingtest.py | 验证倍增假设 | – |
> | 4.1.3 | timeops.py | 计时操作和函数 | – |
> | 4.1.4 | bigarray.py | 发现内存容量 | – |
> | 4.2.1 | questions.py | 二分查找（20 个问题） | – |
> | 4.2.2 | bisection.py | 二分查找（反转函数） | – |
> | 4.2.3 | binarysearch.py | 二分查找（有序数组） | emails.txt  white.txt   |
> | 4.2.4 | insertion.py | 插入排序 | tiny.txt  tomsawyer.txt   |
> | 4.2.5 | timesort.py | 排序函数的倍增测试 | – |
> | 4.2.6 | merge.py | 归并排序 | tiny.txt  tomsawyer.txt   |
> | 4.2.7 | frequencycount.py | 频率统计 | leipzig100k.txt  leipzig200k.txt  leipzig1m.txt   |
> | 4.3.1 | arraystack.py | 栈（可变大小数组实现） | tobe.txt   |
> | 4.3.2 | linkedstack.py | 栈（链表实现） | tobe.txt   |
> | 4.3.3 | evaluate.py | 表达式求值 | expression1.txt  expression2.txt   |
> | 4.3.4 | linkedqueue.py | 队列（链表实现） | tobe.txt   |
> | 4.3.5 | mm1queue.py | M/M/1 队列模拟 | – |
> | 4.3.6 | loadbalance.py | 负载均衡模拟 | – |
> | 4.4.1 | lookup.py | 字典查找 | amino.csv  djia.csv  elements.csv  ip.csv  ip-by-country.csv  morse.csv  phone-na.csv   |
> | 4.4.2 | index.py | 索引 | mobydick.txt  tale.txt   |
> | 4.4.3 | hashst.py | 哈希符号表数据类型 | – |
> | 4.4.4 | bst.py | 二叉搜索树符号表数据类型 | – |
> | 4.5.1 | graph.py | 图数据类型 | tinygraph.txt   |
> | 4.5.2 | invert.py | 使用图来反转索引 | tinygraph.txt  movies.txt   |
> | 4.5.3 | separation.py | 最短路径客户端 | routes.txt  movies.txt   |
> | 4.5.4 | pathfinder.py | 最短路径客户端 | – |
> | 4.5.5 | smallworld.py | 小世界测试 | tinygraph.txt   |
> | 4.5.6 | performer.py | 表演者-表演者图 | tinymovies.txt  moviesg.txt   |
