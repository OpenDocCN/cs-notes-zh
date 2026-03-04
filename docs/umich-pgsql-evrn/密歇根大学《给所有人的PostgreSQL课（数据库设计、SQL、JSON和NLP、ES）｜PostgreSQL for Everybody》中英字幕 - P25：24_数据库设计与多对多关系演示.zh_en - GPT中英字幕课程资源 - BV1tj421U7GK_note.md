# PostgreSQL for Everybody：P25：数据库设计与多对多关系演示 🗄️

在本节课中，我们将学习数据库设计中的核心概念，特别是如何使用外键建立表与表之间的关系。我们将通过手动创建和连接数据表，来深入理解“一对多”和“多对多”关系的工作原理。虽然这些操作在后续课程中会被自动化，但掌握其底层机制至关重要。

## 数据模型与表创建

上一节我们介绍了数据库设计的基本概念，本节中我们来看看如何将设计图转化为实际的数据库表。

我们的数据模型包含四个表：
*   **`track`** 表：包含歌曲信息，并拥有指向 `album` 表的外键。
*   **`album`** 表：包含专辑信息，并拥有指向 `artist` 表的外键。
*   **`artist` 表**：存储艺术家信息。
*   **`genre` 表**：存储音乐流派信息。

![](img/8cb9ce152ecd66b94c2224ec904c8265_1.png)

![](img/8cb9ce152ecd66b94c2224ec904c8265_3.png)

`artist` 和 `genre` 这类表被称为“查找表”。它们通常包含一个自动生成的 `ID` 和一个唯一的名称字段。例如，我们只希望系统中存在一行代表“Led Zeppelin”的数据。

![](img/8cb9ce152ecd66b94c2224ec904c8265_5.png)

![](img/8cb9ce152ecd66b94c2224ec904c8265_6.png)

![](img/8cb9ce152ecd66b94c2224ec904c8265_8.png)

以下是创建这些表的SQL语句。注意外键的定义方式，它们本质上就是整数，但通过 `REFERENCES` 关键字指明了关联关系。

![](img/8cb9ce152ecd66b94c2224ec904c8265_10.png)

```sql
CREATE TABLE artist (
    id SERIAL,
    name VARCHAR(128) UNIQUE,
    PRIMARY KEY(id)
);

![](img/8cb9ce152ecd66b94c2224ec904c8265_12.png)

![](img/8cb9ce152ecd66b94c2224ec904c8265_14.png)

CREATE TABLE album (
    id SERIAL,
    title VARCHAR(128) UNIQUE,
    artist_id INTEGER REFERENCES artist(id) ON DELETE CASCADE,
    PRIMARY KEY(id)
);

![](img/8cb9ce152ecd66b94c2224ec904c8265_16.png)

CREATE TABLE genre (
    id SERIAL,
    name VARCHAR(128) UNIQUE,
    PRIMARY KEY(id)
);

![](img/8cb9ce152ecd66b94c2224ec904c8265_18.png)

![](img/8cb9ce152ecd66b94c2224ec904c8265_19.png)

![](img/8cb9ce152ecd66b94c2224ec904c8265_20.png)

CREATE TABLE track (
    id SERIAL,
    title VARCHAR(128),
    len INTEGER,
    rating INTEGER,
    count INTEGER,
    album_id INTEGER REFERENCES album(id) ON DELETE CASCADE,
    genre_id INTEGER REFERENCES genre(id) ON DELETE CASCADE,
    PRIMARY KEY(id)
);
```

![](img/8cb9ce152ecd66b94c2224ec904c8265_22.png)

## 手动插入数据与理解外键

创建表结构后，下一步是向表中插入数据。关键在于理解并手动管理这些作为外键的整数ID。

首先，我们向查找表（`artist`, `genre`）中插入数据，并记录下系统自动生成的ID。

![](img/8cb9ce152ecd66b94c2224ec904c8265_24.png)

![](img/8cb9ce152ecd66b94c2224ec904c8265_25.png)

```sql
INSERT INTO artist (name) VALUES ('Led Zeppelin');
INSERT INTO artist (name) VALUES ('AC/DC');

![](img/8cb9ce152ecd66b94c2224ec904c8265_27.png)

SELECT * FROM artist; -- 查看生成的ID，例如 Led Zeppelin -> 1, AC/DC -> 2
```

![](img/8cb9ce152ecd66b94c2224ec904c8265_29.png)

现在，我们可以使用这些ID来插入关联数据。例如，为AC/DC（ID为2）创建专辑。

![](img/8cb9ce152ecd66b94c2224ec904c8265_31.png)

![](img/8cb9ce152ecd66b94c2224ec904c8265_32.png)

```sql
INSERT INTO album (title, artist_id) VALUES ('Who Made Who', 2);
```

![](img/8cb9ce152ecd66b94c2224ec904c8265_34.png)

![](img/8cb9ce152ecd66b94c2224ec904c8265_35.png)

`genre` 表的操作同理。之后，我们向 `track` 表插入数据。在下面的插入语句中，`album_id` 和 `genre_id` 看起来只是普通的整数，但数据库知道它们是外键。

![](img/8cb9ce152ecd66b94c2224ec904c8265_37.png)

```sql
INSERT INTO track (title, rating, len, count, album_id, genre_id) VALUES ('Black Dog', 5, 297, 0, 2, 1);
```

![](img/8cb9ce152ecd66b94c2224ec904c8265_39.png)

![](img/8cb9ce152ecd66b94c2224ec904c8265_41.png)

**注意**：由于我们在创建表时为 `artist.name` 和 `genre.name` 等字段设置了 `UNIQUE` 约束，尝试插入重复值会导致错误。这是一种保护机制，防止数据出现意外重复。

![](img/8cb9ce152ecd66b94c2224ec904c8265_43.png)

## 执行JOIN查询连接数据

![](img/8cb9ce152ecd66b94c2224ec904c8265_45.png)

![](img/8cb9ce152ecd66b94c2224ec904c8265_47.png)

数据插入完成后，我们可以通过 `JOIN` 操作将分散在多个表中的信息重新组合起来。

一个基础的 `JOIN` 查询示例如下，它连接 `album` 表和 `artist` 表，通过匹配 `artist_id` 来获取专辑及其对应的艺术家名称。

![](img/8cb9ce152ecd66b94c2224ec904c8265_49.png)

```sql
SELECT album.title, artist.name
FROM album
JOIN artist ON album.artist_id = artist.id;
```

![](img/8cb9ce152ecd66b94c2224ec904c8265_51.png)

为了更清晰地展示连接机制，我们可以在查询结果中显示用于匹配的ID字段。

![](img/8cb9ce152ecd66b94c2224ec904c8265_53.png)

```sql
SELECT album.title, album.artist_id, artist.id, artist.name
FROM album
JOIN artist ON album.artist_id = artist.id;
```

理解 `JOIN` 的一种方式是将其视为一个“过滤后的交叉连接”。`CROSS JOIN` 会产生所有可能的行组合，而 `INNER JOIN`（即普通的 `JOIN`）则通过 `ON` 子句过滤，只保留匹配条件的行。

![](img/8cb9ce152ecd66b94c2224ec904c8265_55.png)

![](img/8cb9ce152ecd66b94c2224ec904c8265_56.png)

我们可以连接所有四个表，这只需要连续使用多个 `JOIN` 和 `ON` 子句。遵循“外键字段名包含表名”的命名约定，会让编写连接查询变得更加容易。

![](img/8cb9ce152ecd66b94c2224ec904c8265_58.png)

```sql
SELECT track.title, album.title, artist.name, genre.name
FROM track
JOIN album ON track.album_id = album.id
JOIN artist ON album.artist_id = artist.id
JOIN genre ON track.genre_id = genre.id;
```

![](img/8cb9ce152ecd66b94c2224ec904c8265_60.png)

![](img/8cb9ce152ecd66b94c2224ec904c8265_62.png)

## 理解ON DELETE CASCADE级联删除

![](img/8cb9ce152ecd66b94c2224ec904c8265_64.png)

在创建表时，我们在外键约束中定义了 `ON DELETE CASCADE`。这意味着当父表中的某行被删除时，所有引用该行的子表记录也会被自动删除。

例如，如果我们删除 `genre` 表中的某条记录：

![](img/8cb9ce152ecd66b94c2224ec904c8265_66.png)

```sql
DELETE FROM genre WHERE id = 1;
```

![](img/8cb9ce152ecd66b94c2224ec904c8265_68.png)

那么，所有 `genre_id` 为1的 `track` 记录也会被自动删除。执行 `SELECT * FROM track;` 可以验证这一点。这是一种维护数据引用完整性的强大功能。

## 实现多对多关系

多对多关系是数据库设计中的另一个核心概念。它本质上是通过一个中间表（连接表）和两个一对多关系来实现的。

![](img/8cb9ce152ecd66b94c2224ec904c8265_70.png)

我们以学生选课系统为例：
*   **`student` 表**：学生信息（查找表）。
*   **`course` 表**：课程信息（查找表）。
*   **`member` 表**：连接表，记录哪个学生选了哪门课，以及其角色（如学生或教师）。

![](img/8cb9ce152ecd66b94c2224ec904c8265_72.png)

创建 `student` 和 `course` 表后，我们创建关键的 `member` 表。它的主键是 `(student_id, course_id)` 的组合，这确保了一个学生在一门课中只能有一条记录（除非角色不同，那时可以将 `role` 也加入主键）。它的两个字段都是外键。

![](img/8cb9ce152ecd66b94c2224ec904c8265_74.png)

```sql
CREATE TABLE student (
    id SERIAL,
    name VARCHAR(128) UNIQUE,
    email VARCHAR(128) UNIQUE,
    PRIMARY KEY(id)
);

![](img/8cb9ce152ecd66b94c2224ec904c8265_76.png)

CREATE TABLE course (
    id SERIAL,
    title VARCHAR(128) UNIQUE,
    PRIMARY KEY(id)
);

CREATE TABLE member (
    student_id INTEGER REFERENCES student(id) ON DELETE CASCADE,
    course_id INTEGER REFERENCES course(id) ON DELETE CASCADE,
    role INTEGER,
    PRIMARY KEY (student_id, course_id)
);
```

![](img/8cb9ce152ecd66b94c2224ec904c8265_78.png)

插入基础数据后，我们需要手动将学生和课程关联起来。这需要我们知道具体的ID，并插入到 `member` 表中。

```sql
INSERT INTO member (student_id, course_id, role) VALUES (1, 1, 1); -- Jane 是 Python 课的教师 (role=1)
INSERT INTO member (student_id, course_id, role) VALUES (2, 1, 0); -- Ed 是 Python 课的学生 (role=0)
```

![](img/8cb9ce152ecd66b94c2224ec904c8265_80.png)

最后，我们可以通过一个跨越三表的 `JOIN` 查询，清晰地查看完整的选课情况。逻辑上，我们是从 `student` 表出发，通过 `member` 表，再连接到 `course` 表。

![](img/8cb9ce152ecd66b94c2224ec904c8265_82.png)

```sql
SELECT student.name, member.role, course.title
FROM student
JOIN member ON student.id = member.student_id
JOIN course ON course.id = member.course_id
ORDER BY course.title, member.role DESC, student.name;
```

## 总结

![](img/8cb9ce152ecd66b94c2224ec904c8265_84.png)

![](img/8cb9ce152ecd66b94c2224ec904c8265_85.png)

本节课中我们一起学习了数据库关系设计的核心实践。我们手动创建了具有外键关联的表，并插入了数据，深入理解了“一对多”关系中 `JOIN` 操作和 `ON DELETE CASCADE` 的作用。接着，我们探讨了“多对多”关系的实现方式，即通过一个包含两个外键的中间表来连接两个实体。虽然手动管理外键ID较为繁琐，但这是理解关系数据库运作原理的重要一步。在接下来的课程中，我们将学习如何自动化这些过程。