# 📚 课程导航：UCB CS186 数据库导论笔记

在本教程中，我们将一起浏览加州大学伯克利分校CS186《数据库导论》课程的核心内容。本课程从基础概念讲起，逐步深入到数据库系统的内部原理与高级主题，涵盖了SQL、存储管理、查询处理、事务、并发控制、恢复、数据库设计以及现代分布式与NoSQL系统等关键知识。我们将按照课程的自然顺序，为你梳理每一讲的重点。



## 📖 概述

本课程笔记基于UCB CS186的公开视频内容整理，旨在为初学者提供一条清晰的学习路径。我们将从最基础的SQL语言开始，逐步深入到数据库系统如何存储数据、处理查询、保证数据一致性，并最终探讨现代大规模数据处理技术。每一节都对应课程中的一个核心主题。



## 📝 课程内容列表

以下是本课程涵盖的所有主题及其对应的笔记链接：

*   [UCB CS186 数据库导论笔记](README.md)
*   [P1：第1讲 介绍 + SQL I](P1-Lecture-1-Introduction---SQL-I---___main___---BV1cL411t7Fz.md)
*   [P2：第2讲 SQL I（续）+ SQL II](P2-Lecture-2-SQL-I--cont----SQL-II---___main___---BV1cL411t7Fz.md)
*   [P3：第3讲 SQL II（续）+ 磁盘、缓冲区、文件 I](P3-Lecture-3-SQL-II--cont----Disks--Buffers--Files-I---___main___---BV1cL411t7Fz.md)
*   [P4：第4讲 磁盘、缓冲区、文件 I（续）+ 磁盘、缓冲区、文件 II](P4-Lecture-4-Disks--Buffers--Files-I--cont----Disks--Buffers--Files-II---___main___---BV1cL411t7Fz.md)
*   [P5：第5讲 成本模型与索引 + B+ 树](P5-Lecture-5-Cost-Models-and-Index---B--Trees---___main___---BV1cL411t7Fz.md)
*   [P6：第6讲 索引与 B+ 树优化](P6-Lecture-6-Indices---B--Tree-Refinements---___main___---BV1cL411t7Fz.md)
*   [P7：第7讲 缓冲区管理](P7-Lecture-7-Buffer-Management---___main___---BV1cL411t7Fz.md)
*   [P8：第8讲 关系代数](P8-Lecture-8-Relational-Algebra---___main___---BV1cL411t7Fz.md)
*   [P9：第9讲 排序与哈希](P9-Lecture-9-Sorting---Hashing---___main___---BV1cL411t7Fz.md)
*   [P10：第10讲 迭代器与连接 I](P10-Lecture-10-Iterators---Joins-I---___main___---BV1cL411t7Fz.md)
*   [P11：第11讲 迭代器与连接 II](P11-Lecture-11-Iterators---Joins-II---___main___---BV1cL411t7Fz.md)
*   [P13：第13讲 查询优化 成本与搜索](P13-Lecture-13-Query-Optimization-Costs---Search---___main___---BV1cL411t7Fz.md)
*   [P14：第14讲 事务与并发 I](P14-Lecture-14-Transactions---Concurrency-I---___main___---BV1cL411t7Fz.md)
*   [P15：第15讲 事务与并发 II](P15-Lecture-15-Transactions---Concurrency-II---___main___---BV1cL411t7Fz.md)
*   [P16：第16讲 恢复 I](P16-Lecture-16-Recovery-I---___main___---BV1cL411t7Fz.md)
*   [P17：第17讲 恢复 II](P17-Lecture-17-Recovery-II---___main___---BV1cL411t7Fz.md)
*   [P18：第18讲 恢复 II（续）](P18-Lecture-18-Recovery-II--cont----___main___---BV1cL411t7Fz.md)
*   [P19：第19讲 数据库设计 ER 模型](P19-Lecture-19-DB-Design-ER-Models---___main___---BV1cL411t7Fz.md)
*   [P20：第20讲 数据库设计 FDs 和规范化](P20-Lecture-20-DB-Design-FDs-and-Normalization---___main___---BV1cL411t7Fz.md)
*   [P21：第21讲 并行查询处理](P21-Lecture-21-Parallel-Query-Processing---___main___---BV1cL411t7Fz.md)
*   [P22：第22讲 数据复制与分布式事务 I](P22-Lecture-22-Data-Replication-and-Distributed-Transactions-I---___main___---BV1cL411t7Fz.md)
*   [P23：第23讲 数据复制与分布式事务 II](P23-Lecture-23-Data-Replication-and-Distributed-Transactions-II---___main___---BV1cL411t7Fz.md)
*   [P24：第24讲 NoSQL I](P24-Lecture-24-NoSQL-I---___main___---BV1cL411t7Fz.md)
*   [P25：第25讲 NoSQL II](P25-Lecture-25-NoSQL-II---___main___---BV1cL411t7Fz.md)
*   [P26：第26讲 MapReduce 和 Spark](P26-Lecture-26-MapReduce-and-Spark---___main___---BV1cL411t7Fz.md)
*   [P27：第27讲 OLAP，列存储](P27-Lecture-27-OLAP--Column-Stores---___main___---BV1cL411t7Fz.md)



## 🧭 学习路径指引

上一节我们列出了所有课程主题，本节中我们来看看如何高效地使用这些资料。建议初学者按照以下模块顺序进行学习：

1.  **基础篇 (P1-P4)**：从SQL语言和数据库基本概念入手，了解数据如何存储在磁盘上。
2.  **存储与索引篇 (P5-P7)**：深入学习索引（特别是**B+树**）和缓冲区管理，这是数据库高效存取数据的核心。
3.  **查询处理篇 (P8-P13)**：掌握关系代数、排序、哈希、连接算法以及查询优化器的工作原理。
4.  **事务与恢复篇 (P14-P18)**：理解数据库保证**ACID**属性的关键机制，包括锁、并发控制和日志恢复。
5.  **设计篇 (P19-P20)**：学习如何使用ER模型进行概念设计，并通过函数依赖和规范化理论优化表结构。
6.  **高级与分布式篇 (P21-P27)**：探索现代数据库系统的前沿，包括并行处理、分布式事务、**NoSQL**系统、大数据计算框架（如**MapReduce/Spark**）以及分析型数据库（**OLAP**）。



## 🎯 总结

在本教程中，我们一起梳理了UCB CS186《数据库导论》课程的全貌。我们从最基础的SQL语法和存储模型出发，逐步深入到索引、查询优化、事务管理、数据库设计等核心内部原理，最后扩展到分布式系统和大数据处理等现代主题。这份笔记列表为你提供了一条系统性的学习路线，你可以根据自身兴趣和需求，选择相应的章节深入研读，逐步构建起完整的数据库知识体系。