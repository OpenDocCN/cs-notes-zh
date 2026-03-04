# 093：PostgreSQL的JSON支持 📊

在本章中，我们将学习PostgreSQL如何存储和处理JSON数据。我们将了解PostgreSQL中JSON支持的演变历程，并重点学习当前最常用的JSONB数据类型及其操作方法。

## 概述

上一节我们讨论了Python中的JSON处理，本节中我们来看看如何在PostgreSQL中存储结构化JSON数据。PostgreSQL对JSON的支持是逐步演进的，这在一定程度上是对基于JSON的NoSQL数据库兴起的回应。在9.4版本之前，PostgreSQL不支持JSON，导致一些用户转向其他数据库。现在PostgreSQL提供了完整的JSON支持，使其能够与MongoDB等NoSQL数据库竞争。

## JSON支持的演进历程

以下是PostgreSQL中JSON相关数据类型的演进过程：

**HSTORE类型**：这是JSON支持的先驱，本质上是一个键值对字典。它允许将多个数据元素存储在单个列中，无需为每个元素创建单独的列。HSTORE的语法类似于字典：`a=>1, b=>2`。它的优点是模式灵活，可以随时添加新键而无需修改表结构。但缺点是**不支持嵌套结构**。

**JSON类型（早期版本）**：在PostgreSQL 9.3中引入，最初基本上是一个增强的文本字段。虽然可以对其使用正则表达式进行查询，并建立GIN（通用倒排索引），但性能不如专门的JSON类型。

**JSONB类型**：这是当前推荐使用的JSON类型。与纯文本的JSON类型不同，JSONB会解析JSON数据，以二进制格式存储，支持更高效的查询和索引。它结合了HSTORE的索引优势和JSON的灵活性，**支持嵌套结构**，是与MongoDB等NoSQL数据库竞争的关键特性。

## JSONB的基本操作

现在我们已经了解了JSONB的历史背景，让我们具体看看如何使用JSONB类型。

### 创建JSONB表

首先创建一个包含JSONB列的表：

```sql
CREATE TABLE jtrack (
    id SERIAL PRIMARY KEY,
    body JSONB
);
```

### 导入JSON数据

使用COPY命令导入JSON数据，每行一个JSON对象：

```sql
COPY jtrack(body) FROM '/path/to/data.json' 
WITH (FORMAT CSV, QUOTE E'\x01', DELIMITER E'\x02');
```

这个技巧性的命令通过设置不可打印的引号和分隔符，使每行都被视为一个完整的JSON对象。

### JSONB查询操作符

以下是JSONB的主要查询操作符：

**双箭头操作符（->>）**：提取JSON中的值并转换为文本。例如，`body->>'count'`提取"count"键的值。

**类型转换**：使用`::int`将提取的值转换为整数：`(body->>'count')::int`

**单箭头操作符（->）**：提取JSON中的值但保持JSONB类型。

**包含操作符（@>）**：检查JSONB文档是否包含指定的JSON片段。例如，`body @> '{"name": "Summer Nights"}'`

**键存在操作符（?）**：检查JSONB文档是否包含指定的键。例如，`body ? 'name'`

### 查询示例

以下是一些JSONB查询示例：

```sql
-- 提取播放次数并按专辑名筛选
SELECT (body->>'count')::int 
FROM jtrack 
WHERE body->>'name' = 'Summer Nights';

-- 使用包含操作符查询
SELECT * FROM jtrack 
WHERE body @> '{"name": "Summer Nights"}';

-- 按播放次数排序
SELECT body->>'name' AS name 
FROM jtrack 
ORDER BY (body->>'count')::int DESC;
```

## JSONB索引优化

为了提高JSONB查询性能，PostgreSQL支持多种索引类型：

**B树索引**：针对特定JSON路径创建索引，类似于普通列索引：

```sql
CREATE INDEX idx_name ON jtrack ((body->>'name'));
```

**GIN索引（通用倒排索引）**：对整个JSONB文档创建索引，加速键存在性查询：

```sql
CREATE INDEX idx_gin ON jtrack USING gin(body);
```

**GIN索引（带路径操作）**：创建更丰富的倒排索引，加速包含操作符查询：

```sql
CREATE INDEX idx_gin_path ON jtrack USING gin(body jsonb_path_ops);
```

这些索引可以显著提高`?`和`@>`等操作符的查询性能。

## 总结

本节课中我们一起学习了PostgreSQL的JSON支持。我们了解了JSONB类型的演进历史，从HSTORE到JSON再到JSONB的发展过程。我们学习了如何创建JSONB表、导入JSON数据、使用各种JSONB操作符进行查询，以及如何通过创建适当的索引来优化查询性能。JSONB是PostgreSQL与NoSQL数据库竞争的关键特性，它结合了关系数据库的严谨性和NoSQL数据库的灵活性，为处理半结构化数据提供了强大的工具。