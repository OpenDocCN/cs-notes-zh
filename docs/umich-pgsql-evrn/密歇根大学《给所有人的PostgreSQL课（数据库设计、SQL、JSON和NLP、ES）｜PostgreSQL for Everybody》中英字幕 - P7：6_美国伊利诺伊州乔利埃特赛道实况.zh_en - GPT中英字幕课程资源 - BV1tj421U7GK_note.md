# PostgreSQL for Everybody：P7：6_美国伊利诺伊州乔利埃特赛道实况

![](img/a27f97e2eef4c2fceff677194dd61e50_0.png)

## 概述

在本节课中，我们将学习如何使用SQL的`JOIN`操作来关联数据库中的多个表。我们将通过一个关于美国伊利诺伊州乔利埃特赛道的实际数据示例，来理解如何从不同的表中组合信息，以回答更复杂的数据查询问题。

## 理解数据表结构

在开始使用`JOIN`之前，了解我们拥有的数据表及其关系至关重要。本节中，我们将查看示例中涉及的两个核心数据表。

我们有两个主要的数据表。第一个表`track`存储了赛道的基本信息。第二个表`race`则记录了在赛道上举行的具体比赛信息。

以下是`track`表可能包含的字段示例：
```sql
CREATE TABLE track (
    id SERIAL PRIMARY KEY,
    name VARCHAR(255),
    location VARCHAR(255)
);
```

`race`表可能包含以下字段：
```sql
CREATE TABLE race (
    id SERIAL PRIMARY KEY,
    track_id INTEGER REFERENCES track(id),
    date DATE,
    winner VARCHAR(255)
);
```

## 使用INNER JOIN关联表

上一节我们介绍了数据表的结构，本节中我们来看看如何使用`INNER JOIN`将这两个表连接起来。`INNER JOIN`只返回两个表中匹配的行。

其基本语法公式如下：
```sql
SELECT 列名
FROM 表A
INNER JOIN 表B ON 表A.关联列 = 表B.关联列;
```

假设我们想查询所有比赛及其对应的赛道名称。以下是一个具体的操作示例。

以下是实现此查询的SQL代码：
```sql
SELECT race.date, race.winner, track.name AS track_name
FROM race
INNER JOIN track ON race.track_id = track.id;
```
这段代码将从`race`表中选择比赛日期和获胜者，并从`track`表中选择赛道名称，条件是`race.track_id`与`track.id`相匹配。

## 应用LEFT JOIN获取完整信息

`INNER JOIN`只显示有匹配项的数据。如果我们想查看所有赛道的信息，即使某些赛道上还没有举办过比赛，这时就需要使用`LEFT JOIN`。

![](img/a27f97e2eef4c2fceff677194dd61e50_0.png)

`LEFT JOIN`会返回左表（`JOIN`关键字前的表）的所有行，即使右表中没有匹配的行。如果右表没有匹配项，结果中对应的字段将为`NULL`。

其语法公式为：
```sql
SELECT 列名
FROM 左表
LEFT JOIN 右表 ON 左表.关联列 = 右表.关联列;
```

例如，我们想列出所有赛道，并显示其上举办过的比赛（如果有的话）。

以下是使用`LEFT JOIN`的查询示例：
```sql
SELECT track.name AS track_name, race.date, race.winner
FROM track
LEFT JOIN race ON track.id = race.track_id;
```
此查询会列出所有赛道。对于有比赛的赛道，会显示比赛日期和获胜者；对于没有比赛的赛道，比赛相关字段显示为`NULL`。

## 总结

本节课中我们一起学习了SQL中两种重要的表连接操作：`INNER JOIN`和`LEFT JOIN`。我们通过乔利埃特赛道的实例，理解了如何根据`track_id`字段将`race`表与`track`表关联起来。`INNER JOIN`用于获取两个表中相互匹配的数据，而`LEFT JOIN`则确保左表的所有记录都被包含在结果中，无论右表是否存在匹配。掌握这些连接操作是进行复杂数据库查询和分析的基础。