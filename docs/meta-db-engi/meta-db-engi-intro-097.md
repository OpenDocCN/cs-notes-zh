# 97：子查询与复杂比较运算符 🧮

在本节课中，我们将学习如何将子查询与复杂的比较运算符结合使用，以执行更高级的数据检索任务。我们将重点介绍 `ALL`、`ANY`、`SOME`、`EXISTS` 和 `NOT EXISTS` 这些运算符，并通过 Little Lemon 餐厅的实际案例来演示它们的应用。

---

## 概述

子查询是嵌套在主查询（外部查询）内部的查询。一个关键优势在于，你可以使用运算符将子查询的结果与其他值进行比较。然而，当子查询返回多行结果时，就需要使用更复杂的比较运算符来处理这些结果集。

上一节我们介绍了标准子查询，本节中我们来看看如何与 `ALL`、`ANY`、`SOME`、`EXISTS` 和 `NOT EXISTS` 这些运算符配合使用。

---

## 复杂比较运算符简介

以下是可与多行子查询一起使用的核心运算符：

*   **`ANY` 运算符**：如果主查询中的值与子查询返回的**任意一个**值满足比较条件，则返回数据。
*   **`ALL` 运算符**：只有当主查询中的值与子查询返回的**所有**值都满足比较条件时，才返回数据。
*   **`SOME` 运算符**：功能与 `ANY` 相同，返回与子查询中**一个或多个**值匹配的数据。

这些运算符允许你在一个单一的比较值和一系列其他值之间进行比较。

---

## EXISTS 与 NOT EXISTS 运算符

![](img/26e3494cf6f2481fc28703a53a879043_1.png)

子查询也可以与 `EXISTS` 和 `NOT EXISTS` 运算符结合使用。

*   **`EXISTS` 运算符**：用于测试子查询返回的结果集中是否存在行。如果子查询返回**一行或多行**记录，则结果为 `TRUE`。
*   **`NOT EXISTS` 运算符**：检查子查询返回的结果是否**不存在**。当子查询**没有返回任何行**时，结果为 `TRUE`。

让我们回顾一下 `EXISTS` 和 `NOT EXISTS` 的语法。其语法与标准子查询非常相似，关键区别在于 `EXISTS` 或 `NOT EXISTS` 运算符被放置在 `WHERE` 子句之后，用于判断子查询中指定值的存在与否。

```sql
-- EXISTS 语法示例
SELECT * FROM 表A
WHERE EXISTS (SELECT * FROM 表B WHERE 条件);

-- NOT EXISTS 语法示例
SELECT * FROM 表A
WHERE NOT EXISTS (SELECT * FROM 表B WHERE 条件);
```

---

## 实战演示：使用 ALL 运算符

Little Lemon 餐厅需要识别出所有年薪**小于或等于**以下所有职位员工年薪的员工：经理、助理经理、主厨和服务领班。

所需数据在 `employees` 表中，该表包含 `EmployeeID`、`Name`、`Role`、`AnnualSalary` 四列。

我们可以使用一个外部查询来识别年薪符合条件的员工，以及一个子查询来提取指定职位员工的年薪数据。

以下是构建查询的步骤：

1.  **编写外部查询**：选择所有列，从 `employees` 表，并设置 `WHERE` 条件比较 `AnnualSalary`。
2.  **编写子查询**：在括号内，选择 `AnnualSalary` 列，从 `employees` 表，并筛选 `Role` 在指定列表中。
3.  **使用 ALL 运算符**：在比较运算符 `<=` 之后、子查询之前插入 `ALL` 运算符。

最终查询语句如下：

```sql
SELECT *
FROM employees
WHERE AnnualSalary <= ALL (
    SELECT AnnualSalary
    FROM employees
    WHERE Role IN ('Manager', 'Assistant Manager', 'Head Chef', 'Head Waiter')
);
```

执行过程：子查询先执行，找出经理等四个角色的年薪（例如 70,000， 65,000， 50,000， 40,000）。然后外部查询筛选出年薪小于或等于**所有这些值**的员工。最终输出显示，只有 ID 为 5 和 6 的员工满足条件。

---

## 实战演示：使用 ANY 运算符

接下来，Little Lemon 需要识别年薪**大于或等于**前述四个职位中**任意一个**职位员工年薪的员工。

我们可以复用之前的查询结构，但需要调整比较运算符并使用 `ANY`。

1.  将外部查询 `WHERE` 条件中的比较运算符改为 `>=`。
2.  将 `ALL` 运算符替换为 `ANY` 运算符。

修改后的查询如下：

```sql
SELECT *
FROM employees
WHERE AnnualSalary >= ANY (
    SELECT AnnualSalary
    FROM employees
    WHERE Role IN ('Manager', 'Assistant Manager', 'Head Chef', 'Head Waiter')
);
```

执行后，输出显示有五名员工的年薪大于或等于子查询返回的任意一个值。

---

## 实战演示：使用 EXISTS 与 NOT EXISTS

最后，Little Lemon 需要确定他们的主厨和服务领班是否被分配了预订任务。这可以使用 `EXISTS` 或 `NOT EXISTS` 运算符来完成。

查询涉及两个动作：外部查询提取员工详情，子查询判断主厨或服务领班是否被分配了预订。相关数据在 `bookings` 表中。

**使用 EXISTS 的查询：**

```sql
SELECT *
FROM employees e
WHERE EXISTS (
    SELECT *
    FROM bookings b
    WHERE b.EmployeeID = e.EmployeeID
    AND e.Role IN ('Head Chef', 'Head Waiter')
);
```

`EXISTS` 运算符检查子查询中是否存在指定结果。如果存在（结果为 `TRUE`），则外部查询会筛选出那两名被分配了预订的员工详情。

**使用 NOT EXISTS 的查询：**

```sql
SELECT *
FROM employees e
WHERE NOT EXISTS (
    SELECT *
    FROM bookings b
    WHERE b.EmployeeID = e.EmployeeID
    AND e.Role IN ('Head Chef', 'Head Waiter')
);
```

`NOT EXISTS` 运算符检查子查询结果是否不存在。在本例中，`WHERE` 子句会筛选出**不在**子查询结果中的员工，即返回那些**不满足**子查询条件（未被分配预订）的四名员工的数据。

---

![](img/26e3494cf6f2481fc28703a53a879043_3.png)

## 总结

本节课中我们一起学习了如何将子查询与复杂的比较运算符结合使用。我们探讨了 `ALL`、`ANY`/`SOME` 运算符用于多值比较的场景，以及 `EXISTS` 和 `NOT EXISTS` 运算符用于检查结果存在性的场景。通过 Little Lemon 餐厅的具体示例，我们演示了这些技术在复杂数据检索任务中的应用，使你能够更灵活、更强大地操作数据库。