# PostgreSQL for Everybody：P24：多对多关系模型

![](img/8d44c2f13332d63fa90a0b7f442c812a_0.png)

![](img/8d44c2f13332d63fa90a0b7f442c812a_1.png)

## 概述

在本节课中，我们将要学习数据库设计中一个非常重要的概念：多对多关系。我们将探讨为什么在某些情况下，一对多关系模型不再适用，以及如何通过创建“连接表”来正确地建模多对多关系。理解这一概念是构建复杂、可扩展数据库应用的基础。

## 一对多关系的局限性

上一节我们介绍了一对多关系模型，它通过使用外键将“多”的一方连接到“一”的一方。这种模型在很多时候是直观且有效的。例如，一个专辑可以包含多首曲目，但一首曲目通常只属于一个专辑。我们用 `track.album_id` 指向 `album.id` 来建立这种关系。

然而，现实世界的数据关系往往更加复杂。考虑以下场景：一首曲目可能出现在原始专辑、精选集和电影原声带等多个专辑中。如果我们试图在一对多模型下解决这个问题，可能会想到在 `tracks` 表中添加多个外键字段，如 `album_id1`、`album_id2`、`album_id3`。

```sql
-- 不推荐的错误做法
CREATE TABLE tracks (
    id SERIAL PRIMARY KEY,
    title VARCHAR(255),
    album_id1 INTEGER REFERENCES albums(id),
    album_id2 INTEGER REFERENCES albums(id),
    album_id3 INTEGER REFERENCES albums(id)
);
```

这种方法存在严重问题：你无法预知一首曲目最终会出现在多少个专辑中。无论你预设多少个字段（3个、10个或100个），总有可能出现不够用的情况。此外，这会造成大量的空间浪费，因为大多数曲目可能只关联一个专辑，但所有行都必须为可能用不到的字段预留空间。这种设计违背了数据库规范化的原则。

## 引入多对多关系

当你发现数据实体间存在“双向”的一对多关系时，就应该考虑使用多对多模型。例如：
*   一个学生可以选修多门课程，一门课程可以有多个学生。
*   一位作者可以撰写多本书，一本书可以有多个作者。
*   一首曲目可以属于多个专辑，一个专辑可以包含多首曲目。

在逻辑图中，我们用“乌鸦脚”符号表示多对多关系。但数据库表本身无法直接实现这种双向链接。因此，我们需要一个物理解决方案。

## 解决方案：连接表

解决多对多关系的核心技巧是将其分解为两个一对多关系。我们通过创建一个位于中间的新表来实现，这个表通常被称为**连接表**、**联结表**或**关联表**。

这个连接表的核心作用是存储两个外键，分别指向参与多对多关系的两个实体表。

以下是创建学生-课程多对多关系的SQL示例。我们首先创建两个实体表：

```sql
-- 1. 创建“叶子”表（实体表）
CREATE TABLE student (
    id SERIAL PRIMARY KEY,
    name VARCHAR(128),
    email VARCHAR(128) UNIQUE -- 逻辑键
);

CREATE TABLE course (
    id SERIAL PRIMARY KEY,
    title VARCHAR(128) UNIQUE -- 逻辑键
);
```

接下来，我们创建连接表 `member`：

```sql
-- 2. 创建连接表
CREATE TABLE member (
    student_id INTEGER REFERENCES student(id) ON DELETE CASCADE,
    course_id INTEGER REFERENCES course(id) ON DELETE CASCADE,
    role INTEGER, -- 存储在连接上的数据
    PRIMARY KEY (student_id, course_id) -- 联合主键
);
```

让我们分析一下这个连接表：
*   `student_id`：外键，引用 `student(id)`。`ON DELETE CASCADE` 表示当删除一个学生时，其在 `member` 表中的所有关联记录也会被自动删除。
*   `course_id`：外键，引用 `course(id)`。同样设置了级联删除。
*   `role`：这是一个关键点。**连接表不仅可以存储关系，还可以存储与这个特定关系相关的数据**。在这里，`role` 表示学生在某门课程中的身份（例如，1代表教师，0代表学生）。在其他场景中，这可能是一条评论的文本、一个论坛帖子的时间戳等。
*   `PRIMARY KEY (student_id, course_id)`：我们将这两个外键的组合设为主键。这确保了`(学生, 课程)`这个组合在整个表中是唯一的，防止同一个学生被重复添加到同一门课程中。在某些需要允许重复连接的场景（如论坛评论），你可能会使用一个独立的 `SERIAL` 主键，并加上时间戳来排序。

## 插入与查询数据

操作多对多关系的数据也需要遵循从“叶子”到“中心”的顺序。

首先，向实体表插入数据：

```sql
-- 插入学生
INSERT INTO student (name, email) VALUES ('Jane', 'jane@tsugi.org');
INSERT INTO student (name, email) VALUES ('Ed', 'ed@tsugi.org');
INSERT INTO student (name, email) VALUES ('Sue', 'sue@tsugi.org');

-- 插入课程
INSERT INTO course (title) VALUES ('Python');
INSERT INTO course (title) VALUES ('SQL');
INSERT INTO course (title) VALUES ('PHP');
```

然后，向连接表插入关系数据。我们需要知道实体的ID（通常通过查询或应用逻辑获取）：

```sql
-- 假设 IDs: Jane=1, Ed=2, Sue=3; Python=1, SQL=2, PHP=3
-- 插入关系：role 1=教师, 0=学生
INSERT INTO member (student_id, course_id, role) VALUES (1, 1, 1); -- Jane 是 Python 课的教师
INSERT INTO member (student_id, course_id, role) VALUES (2, 1, 0); -- Ed 是 Python 课的学生
INSERT INTO member (student_id, course_id, role) VALUES (3, 1, 0); -- Sue 是 Python 课的学生
INSERT INTO member (student_id, course_id, role) VALUES (1, 2, 0); -- Jane 是 SQL 课的学生
INSERT INTO member (student_id, course_id, role) VALUES (2, 2, 1); -- Ed 是 SQL 课的教师
```

最后，要获取有意义的信息，我们需要使用 `JOIN` 操作将多个表连接起来：

```sql
-- 查询所有课程的学生名单及其角色，按课程和角色排序
SELECT student.name, member.role, course.title
FROM student
JOIN member ON student.id = member.student_id
JOIN course ON member.course_id = course.id
ORDER BY course.title, member.role DESC, student.name;
```

![](img/8d44c2f13332d63fa90a0b7f442c812a_3.png)

这个查询会遍历 `student` 表，通过 `member` 表连接到 `course` 表，最终呈现一个包含学生姓名、角色和课程名称的清晰列表。`ORDER BY` 子句确保结果按课程分组，并且教师（`role=1`，因降序排列而靠前）会显示在学生前面。

## 总结

本节课中我们一起学习了数据库设计中的核心概念——多对多关系模型。我们了解到，当数据实体间存在双向的“一对多”需求时，简单的一对多模型或添加多个外键列的方法都是行不通的。

正确的解决方案是创建一个**连接表**，它包含分别指向两个实体表的外键。这个巧妙的设计将复杂的多对多关系拆解为两个标准的一对多关系。此外，连接表本身还可以存储与该特定关系相关的属性（如角色、时间、状态等），并通过设置联合主键来保证关系的唯一性。

![](img/8d44c2f13332d63fa90a0b7f442c812a_5.png)

虽然这种设计在初期需要更多的思考和规划，但它为数据的完整性、灵活性和可扩展性奠定了坚实基础。当你的应用数据量增长到无法全部装入内存时，一个良好规范化的数据库将继续保持高效运行。掌握多对多关系建模，是你在SQL和数据库设计道路上迈出的关键一步。