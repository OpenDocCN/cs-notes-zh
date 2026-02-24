# 130：使用SQL查询在MySQL中进行数据分析 📊

在本节课中，我们将学习如何在MySQL数据库中使用SQL查询进行数据分析。我们将探讨如何通过不同的SQL技术（如子查询、连接和视图）来访问数据、提取相关信息，并最终为业务决策提供支持。

---

## SQL查询与数据分析的关系 🔗

上一节我们介绍了数据分析的基本概念。本节中我们来看看SQL查询如何支持这一过程。

数据分析涉及从数据库中收集和呈现数据。在MySQL中，可以使用多种SQL查询来收集数据。以下是几种关键的技术：

*   **连接**：用于将两个或多个表的数据合并在一起。
*   **子查询**：在一个查询内部嵌套另一个查询。
*   **视图**：用于创建虚拟表，简化复杂查询。
*   **函数与运算符**：用于执行复杂操作和过滤所需数据。

因此，在MySQL中使用SQL查询进行数据分析的基本流程如下：
1.  使用一个或多个SQL查询从数据库中提取所需数据。
2.  使用进一步的SQL查询来呈现数据分析结果的描述。
3.  基于这些初步结果，通过数据分析工具获得更深入的业务洞察。

---

## 数据分析流程示例 🧪

现在，让我们通过一个具体示例来理解这个流程。

假设Lucky Shrub公司需要一份销量达到或超过100件的所有产品清单。他们可以使用子查询来提取这些数据。

**核心步骤**：
1.  创建一个SQL子查询，定位并筛选所需数据。
2.  通过执行查询，从数据库中提取出这些数据（即最畅销产品列表）。
3.  利用这些数据，结合更复杂的查询和数据分析工具，生成进一步的业务洞察，例如调整采购策略或制定促销方案。

所有这些洞察和潜在策略的实现，都依赖于通过SQL查询收集到的数据。

---

## 实践：使用子查询提取数据 💻

了解了基本流程后，是时候付诸实践了。Lucky Shrub需要对客户订单进行数据分析。

他们需要一份销量达到或超过10件的所有产品列表。相关数据位于数据库的`orders`表中。

以下是提取该数据的SQL语句：

```sql
SELECT ProductID
FROM orders
WHERE ProductID IN (
    SELECT ProductID
    FROM orders
    WHERE Quantity >= 10
);
```

**代码解释**：
*   外部`SELECT`语句从`orders`表中选择`ProductID`。
*   `WHERE`子句使用一个子查询来筛选出那些在`orders`表中`Quantity`（数量）大于等于10的`ProductID`。
执行此语句后，MySQL将输出一个包含所需记录的表。

---

## 使用连接进行数据分析 ⛓

连接是MySQL中执行数据分析的另一种有效方法，可用于探索数据间的关系。

例如，Lucky Shrub需要分析过去10天内客户及其订单数据，但这些数据分别存在于`orders`和`clients`两个表中。

我们可以使用内连接来帮助他们分析：

![](img/24211f96d301de1edc89c7b2c818566e_1.png)

```sql
SELECT c.ClientName, o.OrderID, o.ProductID, o.OrderDate
FROM orders o
INNER JOIN clients c ON o.ClientID = c.ClientID
WHERE o.OrderDate BETWEEN '2023-10-01' AND '2023-10-10';
```

**代码解释**：
*   `INNER JOIN`将`orders`表（别名`o`）和`clients`表（别名`c`）通过`ClientID`字段连接起来。
*   `WHERE`子句使用`BETWEEN`关键字过滤出指定日期范围内的订单。

---

## 使用视图进行数据分析 👓

视图对于分析数据也很有帮助，它可以创建专注于特定数据类型的虚拟表。

假设Lucky Shrub需要分析销售数据并提取前五名最畅销产品。我们可以创建一个视图来简化这项任务。

以下是创建该视图的SQL语句：

```sql
CREATE VIEW TopProducts AS
SELECT p.ProductName, SUM(o.Quantity) AS TotalQuantity, SUM(o.Quantity * p.Price) AS TotalCost
FROM products p
INNER JOIN orders o ON p.ProductID = o.ProductID
GROUP BY p.ProductID, p.ProductName
ORDER BY TotalQuantity DESC
LIMIT 5;
```

**代码解释**：
*   `CREATE VIEW`语句创建了一个名为`TopProducts`的虚拟表。
*   内部的`SELECT`语句使用`INNER JOIN`合并了`products`和`orders`表的数据。
*   `GROUP BY`对产品进行分组，`SUM`函数计算总销量和总销售额。
*   `ORDER BY ... DESC`按总销量降序排列，`LIMIT 5`只取前五条记录。

视图创建后，你可以使用简单的`SELECT * FROM TopProducts;`来查询其中的数据，以进行进一步分析。

---

## 总结 📝

本节课中，我们一起学习了在MySQL中使用SQL查询进行数据分析的核心方法。

![](img/24211f96d301de1edc89c7b2c818566e_3.png)

我们了解到，数据分析始于通过合适的SQL查询（如子查询、连接和视图）从数据库中提取目标数据。随后，可以对这些数据进行进一步处理和解读，从而获得支持业务决策的洞察。

**关键要点**：
*   子查询适合在查询内部进行条件筛选。
*   连接用于合并多个相关表中的数据。
*   视图可以创建可重用的虚拟表，简化复杂查询。
*   选择哪种SQL技术，完全取决于你需要提取和分析的数据类型，以及你希望通过分析达到的目标。

现在，你应该对使用SQL查询在MySQL中执行数据分析有了基本的了解。出色的工作！