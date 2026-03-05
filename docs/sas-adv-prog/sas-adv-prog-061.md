# 061：子查询概述 🎯

在本节课中，我们将要学习SQL中一个非常强大的工具——子查询。子查询，顾名思义，是嵌套在另一个查询内部的查询。我们将从它在`WHERE`或`HAVING`子句中的应用开始，逐步深入到更复杂的用法。

## 什么是子查询？ 🤔

上一节我们介绍了课程的整体安排，本节中我们来具体看看子查询的核心概念。一个子查询是一个被嵌入到另一个SQL语句中的完整`SELECT`语句。它通常用于为主查询提供条件或数据。

其基本形式可以表示为：
```sql
SELECT column1, column2, ...
FROM table1
WHERE columnN OPERATOR (SELECT columnM FROM table2 WHERE condition);
```

## 子查询的三种主要用法 📝

以下是子查询在SQL中最常见的三种应用场景，我们将逐一进行详细探讨。

### 1. 在 WHERE 或 HAVING 子句中使用

这种用法最为常见。子查询在这里充当一个条件过滤器，为主查询的`WHERE`或`HAVING`子句返回一个值或一组值，用于比较。

例如，查找薪水高于平均薪水的员工：
```sql
SELECT employee_id, salary
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```

### 2. 在 FROM 子句中使用（派生表）

当子查询出现在`FROM`子句中时，它被称为“派生表”或“内联视图”。它本质上是一个临时的虚拟表，主查询可以像使用普通表一样使用它。

例如，先计算每个部门的平均薪水，再从中筛选：
```sql
SELECT dept_id, avg_salary
FROM (SELECT dept_id, AVG(salary) AS avg_salary FROM employees GROUP BY dept_id) AS dept_avg
WHERE avg_salary > 50000;
```

### 3. 在 SELECT 子句中使用（标量子查询）

这种子查询必须只返回**单个值**（一行一列）。它通常用于为主查询的每一行计算一个相关的值。

例如，在查询员工信息的同时，显示其所在部门的平均薪水：
```sql
SELECT employee_id, name, salary,
       (SELECT AVG(salary) FROM employees e2 WHERE e2.dept_id = e1.dept_id) AS dept_avg_salary
FROM employees e1;
```

---

本节课中我们一起学习了SQL子查询的三种核心用法：在`WHERE/HAVING`子句中作为条件，在`FROM`子句中创建派生表，以及在`SELECT`子句中返回标量值。理解并掌握子查询，能让你编写出更强大、更灵活的SQL语句来处理复杂的数据检索需求。