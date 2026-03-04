# 094：JSONB 数据类型与操作实战教程 🎵

在本节课中，我们将深入学习 PostgreSQL 中的 JSONB 数据类型。我们将通过一个音乐曲目库的实际例子，演示如何创建 JSONB 表、导入数据、查询、更新数据以及创建索引。JSONB 是 PostgreSQL 中用于存储和处理 JSON 数据的二进制格式，它比传统的 JSON 数据类型更高效，支持索引和复杂的查询操作。

![](img/7a56344963317544ffe97eff4c9fb6b0_1.png)

![](img/7a56344963317544ffe97eff4c9fb6b0_2.png)

---

![](img/7a56344963317544ffe97eff4c9fb6b0_4.png)

![](img/7a56344963317544ffe97eff4c9fb6b0_5.png)

![](img/7a56344963317544ffe97eff4c9fb6b0_6.png)

## 创建与导入数据

![](img/7a56344963317544ffe97eff4c9fb6b0_8.png)

![](img/7a56344963317544ffe97eff4c9fb6b0_9.png)

上一节我们介绍了 JSONB 的基本概念，本节中我们来看看如何创建表并导入 JSONB 数据。

首先，我们需要创建一个表来存储 JSONB 数据。我们将创建一个名为 `jtrack` 的表，它包含一个自增的 `id` 列和一个 `jsonb` 类型的 `body` 列。

![](img/7a56344963317544ffe97eff4c9fb6b0_11.png)

![](img/7a56344963317544ffe97eff4c9fb6b0_12.png)

```sql
DROP TABLE IF EXISTS jtrack;
CREATE TABLE jtrack (
    id SERIAL PRIMARY KEY,
    body JSONB
);
```

![](img/7a56344963317544ffe97eff4c9fb6b0_14.png)

![](img/7a56344963317544ffe97eff4c9fb6b0_16.png)

接下来，我们将从一个文本文件中导入 JSON 数据。该文件每行包含一个完整的 JSON 对象。

![](img/7a56344963317544ffe97eff4c9fb6b0_18.png)

以下是导入数据的 `COPY` 命令。我们使用特殊的 CSV 选项来确保整行 JSON 被作为一个字段导入。

![](img/7a56344963317544ffe97eff4c9fb6b0_20.png)

![](img/7a56344963317544ffe97eff4c9fb6b0_21.png)

```sql
COPY jtrack (body)
FROM '/path/to/library.js.txt'
WITH (FORMAT CSV, QUOTE E'\x01', DELIMITER E'\x02');
```

导入完成后，我们可以验证数据量。

![](img/7a56344963317544ffe97eff4c9fb6b0_23.png)

![](img/7a56344963317544ffe97eff4c9fb6b0_24.png)

```sql
SELECT COUNT(*) FROM jtrack;
-- 返回 318
```

![](img/7a56344963317544ffe97eff4c9fb6b0_26.png)

---

![](img/7a56344963317544ffe97eff4c9fb6b0_28.png)

## 查询 JSONB 数据

![](img/7a56344963317544ffe97eff4c9fb6b0_30.png)

![](img/7a56344963317544ffe97eff4c9fb6b0_31.png)

![](img/7a56344963317544ffe97eff4c9fb6b0_32.png)

现在数据已经导入，本节中我们来看看如何从 JSONB 字段中提取和查询数据。

![](img/7a56344963317544ffe97eff4c9fb6b0_34.png)

![](img/7a56344963317544ffe97eff4c9fb6b0_35.png)

![](img/7a56344963317544ffe97eff4c9fb6b0_37.png)

我们可以使用 `->` 和 `->>` 操作符来访问 JSONB 对象中的键值。`->` 操作符返回一个 JSONB 片段，而 `->>` 操作符返回文本。

```sql
-- 提取 ‘name’ 键的值作为文本
SELECT body->>'name' AS track_name FROM jtrack LIMIT 5;

![](img/7a56344963317544ffe97eff4c9fb6b0_39.png)

-- 提取 ‘name’ 键的值作为 JSONB 片段
SELECT body->'name' AS name_jsonb FROM jtrack LIMIT 5;
```

![](img/7a56344963317544ffe97eff4c9fb6b0_41.png)

需要注意的是，操作符的优先级可能会影响类型转换。为了正确地将 JSONB 片段转换为文本，有时需要使用括号。

![](img/7a56344963317544ffe97eff4c9fb6b0_43.png)

```sql
-- 错误示例：类型转换优先级问题
SELECT body->'name'::text FROM jtrack; -- 错误

-- 正确示例：使用括号
SELECT (body->'name')::text FROM jtrack; -- 正确
```

---

## 使用 WHERE 子句过滤

在学会了基本查询后，本节中我们来看看如何使用 WHERE 子句对 JSONB 数据进行过滤。

![](img/7a56344963317544ffe97eff4c9fb6b0_45.png)

我们可以使用 `->>` 操作符提取文本值并进行字符串比较。

```sql
-- 统计名为 ‘Summer Nights’ 的曲目数量
SELECT COUNT(*) FROM jtrack WHERE body->>'name' = 'Summer Nights';
```

此外，PostgreSQL 提供了专门的 JSONB 操作符 `@>`（包含）和 `?`（存在键）。

```sql
-- 使用 @> 操作符检查 JSONB 是否包含特定片段
SELECT COUNT(*) FROM jtrack WHERE body @> '{"name": "Summer Nights"}'::jsonb;

![](img/7a56344963317544ffe97eff4c9fb6b0_47.png)

![](img/7a56344963317544ffe97eff4c9fb6b0_49.png)

-- 使用 ? 操作符检查是否存在 ‘favorite’ 键
SELECT COUNT(*) FROM jtrack WHERE body ? 'favorite';
```

---

## 更新 JSONB 数据

查询数据是基础，本节中我们来看看如何更新 JSONB 字段的内容。

我们可以使用 `||` 操作符来连接（合并）两个 JSONB 对象，从而为现有对象添加新的键值对。

```sql
-- 为播放次数超过 200 的曲目添加 ‘favorite’: ‘yes’ 标记
UPDATE jtrack
SET body = body || '{"favorite": "yes"}'::jsonb
WHERE (body->>'count')::int > 200;
```

更新后，我们可以验证更改。

```sql
-- 检查哪些曲目现在有 ‘favorite’ 键
SELECT body->>'name', body->>'favorite'
FROM jtrack
WHERE body ? 'favorite'
LIMIT 10;
```

---

## 创建索引以优化查询

随着数据量增长，查询性能变得重要。本节中我们来看看如何为 JSONB 列创建索引以加速查询。

PostgreSQL 支持为 JSONB 数据创建多种类型的索引，最常用的是 B-tree 索引和 GIN 索引。

以下是创建索引的示例：

```sql
-- 1. B-tree 索引：针对特定键的等值查询（如 name）
CREATE INDEX idx_jtrack_name_btree ON jtrack ((body->>'name'));

-- 2. GIN 索引：针对键存在性查询（如 ? 操作符）
CREATE INDEX idx_jtrack_gin ON jtrack USING gin (body);

-- 3. GIN 索引（带 jsonb_path_ops）：针对包含性查询（如 @> 操作符）
CREATE INDEX idx_jtrack_gin_path_ops ON jtrack USING gin (body jsonb_path_ops);
```

创建索引后，使用 `EXPLAIN ANALYZE` 来查看查询计划，确认索引是否被使用。

```sql
EXPLAIN ANALYZE SELECT * FROM jtrack WHERE body->>'name' = 'Summer Nights';
EXPLAIN ANALYZE SELECT * FROM jtrack WHERE body @> '{"artist": "Queen"}'::jsonb;
```

![](img/7a56344963317544ffe97eff4c9fb6b0_51.png)

---

![](img/7a56344963317544ffe97eff4c9fb6b0_53.png)

## 执行数值计算与复杂更新

![](img/7a56344963317544ffe97eff4c9fb6b0_55.png)

最后，我们来看一个更复杂的场景：更新 JSONB 对象内部的数值。

假设我们想将每首曲目的播放次数（`count`）加 1。由于 `count` 在 JSONB 中是整数，我们需要先提取、转换、计算，再写回。

![](img/7a56344963317544ffe97eff4c9fb6b0_57.png)

首先，我们看看如何提取并计算：

```sql
-- 提取 ‘count’ 并转换为整数，然后加 1
SELECT body->>'name', (body->>'count')::int AS old_count, (body->>'count')::int + 1 AS new_count
FROM jtrack
LIMIT 5;
```

![](img/7a56344963317544ffe97eff4c9fb6b0_59.png)

要进行实际的更新，我们需要使用 `jsonb_set` 函数。

```sql
-- 使用 jsonb_set 更新 ‘count’ 值
UPDATE jtrack
SET body = jsonb_set(
    body,
    '{count}',
    to_jsonb((body->>'count')::int + 1)
)
WHERE body->>'name' = 'Summer Nights';
```

这个语法虽然复杂，但它允许我们精准地修改 JSONB 结构内部的特定路径。

![](img/7a56344963317544ffe97eff4c9fb6b0_61.png)

![](img/7a56344963317544ffe97eff4c9fb6b0_63.png)

---

![](img/7a56344963317544ffe97eff4c9fb6b0_65.png)

## 清理工作

完成所有操作后，建议清理临时创建的表，以释放资源。

```sql
DROP TABLE jtrack CASCADE;
```

---

![](img/7a56344963317544ffe97eff4c9fb6b0_67.png)

![](img/7a56344963317544ffe97eff4c9fb6b0_68.png)

本节课中我们一起学习了 PostgreSQL 中 JSONB 数据类型的核心操作。我们从创建表和导入数据开始，逐步探索了数据查询、过滤、更新以及索引优化。关键点包括使用 `->` 和 `->>` 操作符提取数据，利用 `@>` 和 `?` 操作符进行高级查询，以及通过 B-tree 和 GIN 索引提升查询性能。虽然一些更新操作语法较为复杂，但 JSONB 提供了在关系型数据库中高效处理半结构化数据的强大能力。