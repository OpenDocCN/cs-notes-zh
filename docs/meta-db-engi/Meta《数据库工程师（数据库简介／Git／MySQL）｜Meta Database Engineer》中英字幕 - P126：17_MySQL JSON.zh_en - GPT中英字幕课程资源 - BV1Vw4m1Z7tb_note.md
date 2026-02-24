# 数据库工程师课程：P126：MySQL JSON数据类型 🗃️

在本节课中，我们将要学习如何在MySQL中使用JSON数据类型来优化数据库性能。JSON是一种轻量级的数据交换格式，能够简化不同系统间的数据通信，并减少数据库解析不同类型数据时的资源压力。

## 什么是JSON？ 📄

上一节我们介绍了JSON在数据库优化中的作用，本节中我们来看看JSON的具体结构。

JSON，全称为JavaScript Object Notation，是一种用于存储和传输数据的文本格式。它易于人阅读和编写，同时也易于机器解析和生成。在MySQL中，使用JSON数据类型可以高效地存储结构化的数据，而无需预先定义严格的表结构。

JSON数据由键值对组成，存储在一对大括号 `{}` 中。以下是一个来自Lucky Shrub数据库的JSON代码示例：

```json
{"client_id": "Cl1", "product_id": "P1", "order": true}
```

*   **键值对**：每个属性（如`"client_id"`）和其对应的值（如`"Cl1"`）被包裹在双引号中，并用冒号分隔。
*   **分隔符**：每个键值对之间用逗号分隔。

这种格式使得数据组织清晰，且MySQL能够快速处理。

![](img/6da1d0053b8962f3c7813545bf952219_1.png)

## 实践：在MySQL中创建JSON表 🛠️

理解了JSON的基本概念后，我们来看看如何在MySQL数据库中实际应用它。Lucky Shrub公司需要追踪客户在网店中的行为，例如浏览产品和下单。使用JSON格式存储这些动态信息非常合适。

以下是创建存储客户活动表的步骤：

1.  **创建表**：首先，创建一个名为 `activity` 的表。
2.  **定义列**：表中包含两列。
    *   第一列是 `activity_id`，使用整数数据类型，作为每条客户活动的唯一标识符。
    *   第二列是 `properties`，将其数据类型定义为 **`JSON`**。这一列将存储客户活动的具体属性。

创建表的SQL语句如下：

```sql
CREATE TABLE activity (
    activity_id INT AUTO_INCREMENT PRIMARY KEY,
    properties JSON
);
```

## 向JSON表中插入数据 ➕

表结构准备好后，下一步是向其中填充数据。我们将为三个不同的客户ID记录活动，并使用JSON代码来记录详细信息。

以下是插入数据的示例：

```sql
INSERT INTO activity (properties) VALUES
('{"client_id": "Cl1", "product_id": "P1", "order": true}'),
('{"client_id": "Cl2", "product_id": "P4", "order": false}'),
('{"client_id": "Cl3", "product_id": "P5", "order": true}');
```

在这三条记录中，两个客户（Cl1和Cl3）下了订单（`"order": true`），一个客户（Cl2）没有下单（`"order": false`）。

## 从JSON列中检索数据 🔍

由于`properties`列是JSON数据类型，我们不能像查询普通列那样直接访问其中的具体属性。我们需要使用MySQL提供的**列路径运算符**来检索JSON对象内的数据。

列路径运算符使用美元符号 `$` 和点号 `.` 来表示JSON对象中的元素。

例如，要查询所有活动的ID及其完整的JSON属性，可以使用以下语句：

```sql
SELECT activity_id, properties FROM activity;
```

如果只想提取JSON对象中的特定值，比如客户ID，则需要使用路径运算符。以下是查询语句：

```sql
SELECT
    activity_id,
    properties->'$.client_id' AS client_id,
    properties->'$.order' AS order_placed
FROM activity;
```

在这个语句中：
*   `properties->'$.client_id'` 用于提取 `client_id` 的值。
*   `properties->'$.order'` 用于提取 `order` 的值。
*   `AS` 关键字为提取出的值指定了易于理解的列别名。

执行此查询将返回一个清晰的结果集，显示每条活动记录对应的客户ID和是否下单的状态。

## 总结 📝

![](img/6da1d0053b8962f3c7813545bf952219_3.png)

本节课中我们一起学习了MySQL中JSON数据类型的应用。我们了解到，JSON是一种高效存储半结构化数据的方式，能够减轻数据库处理多种数据类型的压力。通过创建包含JSON列的表、插入JSON格式的数据以及使用列路径运算符（`$`）查询特定信息，我们帮助Lucky Shrub公司建立了一个优化的客户活动数据存储与访问方案。掌握JSON在MySQL中的使用，是数据库工程师进行性能优化的重要技能。