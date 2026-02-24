# 86：使用Python访问存储过程 📖

在本节课中，我们将学习如何使用Python来调用MySQL数据库中的存储过程。我们将通过一个为“小柠檬”餐厅筛选符合赠券条件的顾客的实际案例，来演示从创建存储过程到在Python中执行并获取结果的全过程。

---

## 概述

存储过程是预编译并存储在数据库中的SQL语句集合，可以像函数一样被调用。在Python中，我们可以通过数据库连接来创建和执行这些存储过程，从而高效地处理复杂的数据操作。

上一节我们介绍了在MySQL中创建存储过程的基础知识，本节中我们来看看如何用Python与之交互。

---

## 创建存储过程字符串

第一步，我们需要将创建存储过程的SQL语句定义为一个Python字符串。

以下是创建名为 `get_customers_and_bills` 的存储过程的代码。该过程通过内连接（`INNER JOIN`）查询 `bookings` 和 `orders` 表，筛选出消费金额大于等于50美元的顾客信息。

```python
stored_procedure_query = """
CREATE PROCEDURE get_customers_and_bills()
BEGIN
    SELECT 
        CONCAT(g.first_name, ' ', g.last_name) AS guest_name,
        b.booking_id,
        o.bill_amount
    FROM bookings b
    INNER JOIN orders o ON b.booking_id = o.booking_id
    INNER JOIN guests g ON b.guest_id = g.guest_id
    WHERE o.bill_amount >= 50;
END
"""
```

**核心概念**：在Python API中执行SQL时，整个字符串被视为一个MySQL语句，因此无需像在MySQL客户端中那样设置分隔符（`DELIMITER`）。所需的结束分号会自动附加。

---

## 在数据库中创建存储过程

当执行存储过程时，你需要在MySQL数据库上存储一段代码块，以便在需要时调用。

你可以使用游标（cursor）的 `execute` 方法来执行这个SQL字符串，从而将存储过程存储在MySQL数据库中。

```python
# 假设 `cursor` 是已建立的数据库游标对象
cursor.execute(stored_procedure_query)
```

如果执行成功，该过程就被保存在数据库中了。

---

## 调用存储过程并获取结果

现在，存储过程已经创建好，我们可以从Python中调用它。

首先，你需要调用或触发这个过程。

你可以使用游标对象的 `callproc` 方法来调用存储过程，将过程名作为参数传递给该方法。

```python
cursor.callproc('get_customers_and_bills')
```

接下来，你需要检索存储过程返回的结果。

以下是完成此任务的步骤：

1.  使用Python内置的 `next()` 函数从游标的 `stored_results()` 迭代器中获取结果集。
2.  将结果集保存到一个变量中。
3.  使用 `fetchall()` 方法获取所有数据行。

```python
# 获取存储的结果
results = next(cursor.stored_results())
# 获取所有数据行
dataset = results.fetchall()
```

代码成功运行后，`dataset` 变量将包含一个Python列表，列表中的每个元素都是一个元组（tuple），代表存储过程返回的一行记录。

---

## 处理与查看结果

你可以通过索引访问数据集，或者运行循环来打印所有记录。

```python
# 打印所有记录
for record in dataset:
    print(record)
# 或者通过索引访问
# rint(dataset[0])
```

根据案例，查询结果显示有一位顾客在“小柠檬”消费了50美元或以上，符合获得赠券的条件。

![](img/6be4157064663602dd3b9f922d3831e6_1.png)

---

## 总结

![](img/6be4157064663602dd3b9f922d3831e6_3.png)

![](img/6be4157064663602dd3b9f922d3831e6_4.png)

本节课中我们一起学习了使用Python访问MySQL存储过程的完整流程。我们首先将创建存储过程的SQL语句定义为字符串，然后通过游标执行它以在数据库中创建该过程。接着，我们使用 `callproc` 方法调用存储过程，并通过 `stored_results()` 和 `fetchall()` 方法获取和处理返回的数据集。这种方法将数据库的预编译逻辑与Python程序的灵活性结合起来，能有效执行复杂的数据操作。