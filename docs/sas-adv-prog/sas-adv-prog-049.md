# 049：处理缺失值

在本节课中，我们将学习在SAS PROC SQL中进行表连接时，如何处理缺失值。理解缺失值在连接操作中的行为至关重要，因为它可能导致意想不到的查询结果。

## 缺失值在连接中的行为

大多数数据库产品将缺失值视为空值。由于它们不包含任何实际值，因此在条件评估中通常被排除。

在SAS PROC SQL中，情况有所不同。当基于包含缺失值的列进行表连接时，PROC SQL会将缺失值视为可匹配的值。

## 一个连接示例

以下是一个连接示例，它基于 `account ID` 列连接 `small_customer2` 和 `small_transaction2` 两个表。两个表的 `account ID` 列中都存在缺失值。

```sql
PROC SQL;
    SELECT *
    FROM small_customer2 AS c, small_transaction2 AS t
    WHERE c.account_ID = t.account_ID;
QUIT;
```

PROC SQL 将缺失值作为缺失值本身来处理并进行匹配连接。**任何缺失值都会与同一类型（字符型或数值型）的其他任何缺失值相匹配**。

## 连接结果分析

这可能会返回意想不到的结果。如下图所示，输出结果显示，`small_customer2` 中的缺失值行匹配了 `small_transaction2` 中的所有缺失值，导致返回了15行数据。

![](img/1a331a3a9779d86b19e780e459081f47_1.png)

![](img/1a331a3a9779d86b19e780e459081f47_1.png)

![](img/1a331a3a9779d86b19e780e459081f47_3.png)

这很可能不是此次连接操作期望得到的结果。

## 如何排除缺失值进行连接

为了避免这种情况，我们可以指定只连接非缺失值。通过在 `WHERE` 子句中添加 `IS NOT NULL` 运算符，可以防止缺失值相互连接在一起。

![](img/1a331a3a9779d86b19e780e459081f47_3.png)

更新后的SQL代码如下：

```sql
PROC SQL;
    SELECT *
    FROM small_customer2 AS c, small_transaction2 AS t
    WHERE c.account_ID = t.account_ID
          AND c.account_ID IS NOT NULL
          AND t.account_ID IS NOT NULL;
QUIT;
```

![](img/1a331a3a9779d86b19e780e459081f47_5.png)

此修改确保了连接操作只针对 `account_ID` 列中具有有效、非缺失值的行进行。

## 本节总结

![](img/1a331a3a9779d86b19e780e459081f47_5.png)

本节课中，我们一起学习了SAS PROC SQL中缺失值在表连接时的特殊行为。关键点是，PROC SQL默认会将同类型的缺失值相互匹配，这可能导致查询结果行数异常增多。为了获得预期的连接结果，我们学会了使用 `IS NOT NULL` 运算符在连接条件中明确排除缺失值，从而确保只对有效数据进行操作。