# 002：SQL概述与入门

在本节课中，我们将要学习结构化查询语言（SQL）的基础知识。我们将探讨SQL是什么，了解其历史背景，并介绍不同的SQL实现。之后，我们将开始使用ProC SQL来探索数据。

## 什么是SQL？📖

上一节我们介绍了本课程的学习目标，本节中我们来看看SQL的核心定义。

SQL是Structured Query Language（结构化查询语言）的缩写。它是一种专门用于管理和操作关系型数据库的标准编程语言。SQL允许用户执行诸如查询数据、更新记录、插入新数据以及管理数据库结构等任务。

## SQL的历史与发展 📜

了解了SQL的基本定义后，我们有必要了解一下它的起源与发展历程。

SQL最初由IBM的研究人员在20世纪70年代开发，当时被称为SEQUEL。其设计初衷是为了管理和处理存储在关系型数据库管理系统（RDBMS）中的数据。由于其强大的功能和清晰的语法，SQL迅速成为行业标准，并被美国国家标准协会（ANSI）和国际标准化组织（ISO）采纳。

## 不同的SQL实现 💻

SQL虽然是一个标准，但在不同的数据库系统中，其具体实现可能存在细微差别。以下是几种常见的SQL实现：

*   **Oracle PL/SQL**：Oracle数据库使用的过程化语言扩展。
*   **Microsoft Transact-SQL (T-SQL)**：Microsoft SQL Server和Azure SQL数据库使用的扩展。
*   **MySQL**：一种流行的开源关系型数据库管理系统使用的SQL。
*   **PostgreSQL**：另一种功能强大的开源对象-关系型数据库系统。
*   **SAS ProC SQL**：SAS软件中用于处理SAS数据集的SQL实现，它允许用户在SAS环境中使用SQL语法。

## 开始使用ProC SQL探索数据 🔍

在介绍了SQL的背景和不同实现后，现在我们将焦点转向SAS环境，学习如何开始使用ProC SQL。

ProC SQL是SAS中一个强大的过程步，它允许用户将SQL语句直接嵌入到SAS程序中，从而以声明式的方式查询和操作SAS数据集。与传统的SAS数据步相比，ProC SQL有时能提供更简洁、更高效的代码来解决复杂的数据操作问题。

一个基本的ProC SQL查询结构如下：

```sas
PROC SQL;
    SELECT column1, column2
    FROM sas_dataset
    WHERE condition;
QUIT;
```

在这个结构中：
*   `PROC SQL;` 表示开始SQL过程。
*   `SELECT` 指定要检索的列。
*   `FROM` 指定数据来源，即SAS数据集。
*   `WHERE` 用于设置过滤数据的条件。
*   `QUIT;` 用于结束PROC SQL过程（在某些情况下可省略，但显式使用是好习惯）。

---

本节课中我们一起学习了SQL的基础概念，包括其定义、历史以及在不同数据库系统中的实现。最后，我们介绍了在SAS环境中使用ProC SQL进行数据探索的基本方法，为后续深入学习具体的SQL查询和操作技巧打下了基础。