# PostgreSQL 数据库教程：P74：GIN 倒排索引构建演示 🗂️

在本节课中，我们将学习如何在 PostgreSQL 中构建和使用 GIN 倒排索引。这是一种用于高效全文搜索的强大索引类型。我们将通过实际操作来演示其创建过程和使用方法。

## 概述

我们将使用 PostgreSQL 内置的 `GIN` 索引来构建一个倒排索引。与手动构建相比，这种方法要简单得多。核心步骤包括创建表、建立索引、插入数据，最后通过查询来验证索引的效果。

## 创建文档表与索引

![](img/987d1e5a1f0279d213a3bfb97446b0dc_1.png)

首先，我们需要创建一个用于存储文档的表。如果你之前已经创建过，可以先删除它以确保环境干净。

![](img/987d1e5a1f0279d213a3bfb97446b0dc_3.png)

```sql
DROP TABLE IF EXISTS docs;
DROP INDEX IF EXISTS gin_idx;
```

接下来，创建 `docs` 表。我们将使用一个简单的表结构来存储文本内容。

```sql
CREATE TABLE docs (
    id SERIAL PRIMARY KEY,
    doc TEXT
);
```

![](img/987d1e5a1f0279d213a3bfb97446b0dc_5.png)

现在，我们来创建 GIN 索引。这里有一个重要的细节：PostgreSQL 11 与更早版本（如 9.x）在创建数组索引的语法上有所不同。因此，我们需要先确认数据库版本。

```sql
SELECT version();
```

假设我们使用的是 PostgreSQL 11 或更高版本，创建索引的语句如下。其核心是使用 `string_to_array` 函数将文档文本转换为数组，并指定 `array_ops` 作为操作符类。

```sql
CREATE INDEX gin_idx ON docs USING GIN(string_to_array(doc, ' ') array_ops);
```

这个索引的作用是：它将每个文档按空格分割成单词数组，并建立倒排索引结构，以便后续进行高效的数组包含性查询。

## 插入数据

索引创建好后，我们向表中插入一些数据。首先插入几条示例文档。

```sql
INSERT INTO docs (doc) VALUES
('This is a learning example'),
('PostgreSQL is powerful'),
('Learn about GIN indexes');
```

为了更真实地测试索引性能，我们通常需要足够多的数据。以下语句使用 `generate_series` 函数快速插入 10,000 行填充数据。

```sql
INSERT INTO docs (doc)
SELECT 'Neon ' || generate_series(10000, 20000);
```

`generate_series` 函数会生成一个数字序列，我们将其与字符串连接，从而批量生成多行数据。现在，让我们确认数据已插入。

```sql
SELECT COUNT(*) FROM docs;
```

查询结果应为 10,004 条记录（3条初始数据 + 10,001条生成数据）。

## 使用索引进行查询

索引的真正价值体现在查询中。我们将使用 `@>` 操作符（数组包含操作符）来查找包含特定单词的文档。

以下是查询的核心结构。关键在于 `WHERE` 子句中的条件必须与创建索引时使用的表达式完全匹配，这样才能利用索引。

```sql
SELECT id, doc FROM docs
WHERE string_to_array(doc, ' ') @> ARRAY['learn'];
```

这个查询会查找所有文档单词数组中包含 “learn” 这个词的记录。`ARRAY['learn']` 是 PostgreSQL 中定义单元素数组的语法。

## 理解索引生效与延迟

在大量数据插入后立即执行查询，你可能会发现数据库并没有使用索引，而是进行了全表扫描（Sequential Scan）。这是因为新插入的数据可能尚未被索引完全处理，索引处于“落后”状态。

```sql
EXPLAIN ANALYZE SELECT id, doc FROM docs WHERE string_to_array(doc, ' ') @> ARRAY['learn'];
```

等待一段时间后再次执行 `EXPLAIN` 命令，你会看到查询计划从“顺序扫描”变为“位图堆扫描”或“索引扫描”，这表明索引已经就绪并开始生效。

**这一点非常重要**：在高并发写入的场景下，倒排索引可能永远无法完全“追上”最新的数据，导致查询无法使用索引。这是设计此类系统时需要权衡的一个方面。

## 核心步骤总结

回顾整个过程，在 PostgreSQL 中使用 GIN 倒排索引非常简单：

1.  **创建索引**：使用 `CREATE INDEX ... USING GIN` 语法。
2.  **定义索引表达式**：正确使用如 `string_to_array(doc, ' ')` 这样的表达式。
3.  **指定操作符类**：对于数组类型，使用 `array_ops`。
4.  **编写匹配的查询**：确保 `WHERE` 子句的条件与索引表达式一致。

## 总结

![](img/987d1e5a1f0279d213a3bfb97446b0dc_7.png)

本节课我们一起学习了如何在 PostgreSQL 中利用 GIN 索引构建倒排索引。我们完成了从创建表、建立索引、插入测试数据到执行索引查询的全过程。你看到了索引如何加速特定类型的数组包含查询，也了解了在大数据量插入后索引更新的延迟特性。掌握这一工具，能让你在需要全文搜索或复杂数组查询的应用中大幅提升性能。