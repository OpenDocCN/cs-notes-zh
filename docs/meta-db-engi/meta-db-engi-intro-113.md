# 113：创建复杂存储过程 🛠️

在本节课中，我们将学习如何创建比基础存储过程更复杂的存储过程。这类过程通常包含多个SQL语句，并能通过输出参数返回结果。我们将通过一个帮助Lucky Shrub公司分析产品价格的实例来掌握其创建与调用方法。

## 概述

上一节我们介绍了基础存储过程的创建。本节中，我们来看看如何构建一个包含多个语句、并能通过`OUT`参数返回数据的复杂存储过程。我们将帮助Lucky Shrub公司统计其产品数据库中价格低于和高于50美元的商品数量，为即将到来的促销活动做准备。

## 步骤详解

以下是创建复杂存储过程的具体步骤。

### 1. 更改语句分隔符

由于存储过程体包含多个以分号结尾的SQL语句，我们需要临时更改MySQL的语句分隔符，以便MySQL能将整个`BEGIN...END`代码块视为一个复合语句来编译。

输入以下命令，将默认的分号分隔符改为双斜杠`//`：

```sql
DELIMITER //
```

![](img/3152a38ca05003c4443603b0f520b9df_1.png)

### 2. 创建存储过程

接下来，使用`CREATE PROCEDURE`命令来定义存储过程。我们需要为其指定名称、定义输出参数，并编写过程体逻辑。

输入以下代码创建名为`GetProductSummary`的存储过程：

```sql
CREATE PROCEDURE GetProductSummary (
    OUT low_price_count INT,
    OUT high_price_count INT
)
BEGIN
    -- 统计价格低于50美元的产品数量
    SELECT COUNT(ProductID) INTO low_price_count FROM products WHERE Price < 50;
    -- 统计价格高于50美元的产品数量
    SELECT COUNT(ProductID) INTO high_price_count FROM products WHERE Price > 50;
END //
```

**代码解释**：
*   `OUT low_price_count INT`：定义一个名为`low_price_count`的整数型输出参数，用于接收低价产品数量。
*   `SELECT ... INTO ...`：将查询结果直接存入指定的输出参数变量中。

### 3. 恢复默认分隔符

存储过程创建完成后，需要将分隔符改回默认的分号，以便后续正常执行其他SQL语句。

```sql
DELIMITER ;
```

### 4. 调用存储过程并查看结果

现在，我们可以执行这个存储过程并获取其输出的数据了。

首先，使用`CALL`语句调用过程。调用时需要提供两个变量来接收输出参数的结果。

```sql
CALL GetProductSummary(@total_low_price_products, @total_high_price_products);
```

**代码解释**：
*   `@total_low_price_products` 和 `@total_high_price_products` 是用户变量，用于接收存储过程计算出的两个数量值。

过程执行完毕后，数据已存储在上述变量中。我们可以通过一个简单的`SELECT`语句来查看结果。

```sql
SELECT @total_low_price_products, @total_high_price_products;
```

执行此查询后，输出结果将分别显示价格低于50美元和高于50美元的产品总数。Lucky Shrub公司便获得了策划促销活动所需的关键数据。

## 总结

![](img/3152a38ca05003c4443603b0f520b9df_3.png)

![](img/3152a38ca05003c4443603b0f520b9df_4.png)

本节课中我们一起学习了如何创建和使用复杂的存储过程。关键步骤包括：使用`DELIMITER`临时更改分隔符、使用`CREATE PROCEDURE`定义包含`OUT`参数的过程体、以及最后通过`CALL`调用并用`SELECT`查看结果。通过这个实例，你掌握了将多个查询逻辑封装在一个可重复调用的数据库对象中的方法，这能极大地提高数据操作的效率和代码的复用性。