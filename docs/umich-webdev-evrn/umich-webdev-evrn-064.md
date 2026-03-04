# 064：构建物理数据模型 🗺️

![](img/dc3da283c9304fc962c6df09476e27c0_0.png)

![](img/dc3da283c9304fc962c6df09476e27c0_1.png)

![](img/dc3da283c9304fc962c6df09476e27c0_3.png)

在本节课中，我们将学习如何将之前绘制的逻辑数据模型图，转化为实际的、可以在数据库中创建和填充的物理数据模型。我们将通过一个音乐数据库的示例，一步步地创建表、定义主键和外键，并插入数据。

---

## 从逻辑模型到物理模型

上一节我们介绍了逻辑数据模型的概念，并用图表描绘了数据之间的关系。本节中，我们来看看如何将这些图表转化为具体的SQL表结构。

我们从一个在白板上绘制的逻辑模型图开始。这个图展示了艺术家、专辑、曲目和流派之间的关系。在绘制逻辑模型时，我们关注的是数据的逻辑结构，而非具体的列名或技术细节。

![](img/dc3da283c9304fc962c6df09476e27c0_5.png)

现在，我们的任务是将这个逻辑结构映射到一个更具体的物理结构。这意味着我们需要决定表名、列名以及如何精确地实现图表中的关系。

![](img/dc3da283c9304fc962c6df09476e27c0_7.png)

![](img/dc3da283c9304fc962c6df09476e27c0_9.png)

## 构建表结构

![](img/dc3da283c9304fc962c6df09476e27c0_11.png)

以下是构建物理数据模型的核心步骤。我们将从最外层的表开始创建，逐步向内，因为一个表必须在其所引用的表创建之后才能创建。

### 1. 创建艺术家表

首先，我们创建 `artist` 表。几乎每个表的第一步都是定义一个自增的主键，这为我们后续引用每一行数据提供了一个唯一的“句柄”。

```sql
CREATE TABLE artist (
    artist_id INTEGER NOT NULL AUTO_INCREMENT,
    name VARCHAR(128),
    PRIMARY KEY (artist_id)
) ENGINE=InnoDB;
```

*   **`artist_id`**： 这是表的主键，一个自增的整数。
*   **`name`**： 这是逻辑键，我们可能会通过艺术家名称来查找记录。

### 2. 创建专辑表

接下来创建 `album` 表。专辑属于艺术家，因此我们需要在 `album` 表中建立一个指向 `artist` 表的外键。

![](img/dc3da283c9304fc962c6df09476e27c0_13.png)

```sql
CREATE TABLE album (
    album_id INTEGER NOT NULL AUTO_INCREMENT,
    title VARCHAR(128),
    artist_id INTEGER,
    PRIMARY KEY (album_id),
    INDEX (title),
    CONSTRAINT FOREIGN KEY (artist_id) REFERENCES artist (artist_id) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB;
```

*   **`CONSTRAINT FOREIGN KEY`**： 这是关键部分。它明确告诉数据库，`album` 表中的 `artist_id` 列引用了 `artist` 表中的 `artist_id` 列。这就在两者之间建立了“多对一”的关系（一个艺术家可以有多张专辑）。
*   **`ON DELETE CASCADE`**： 这是一个可选的约束，表示如果引用的艺术家记录被删除，那么属于该艺术家的所有专辑记录也会被自动删除。

### 3. 创建流派表

`genre` 表是关系树中的一个“叶子”节点，它不指向其他表，只被其他表引用。

```sql
CREATE TABLE genre (
    genre_id INTEGER NOT NULL AUTO_INCREMENT,
    name VARCHAR(128),
    PRIMARY KEY (genre_id),
    INDEX (name)
) ENGINE=InnoDB;
```

![](img/dc3da283c9304fc962c6df09476e27c0_15.png)

### 4. 创建曲目表

最后创建 `track` 表。曲目同时指向专辑和流派，因此它包含两个外键。

![](img/dc3da283c9304fc962c6df09476e27c0_17.png)

```sql
CREATE TABLE track (
    track_id INTEGER NOT NULL AUTO_INCREMENT,
    title VARCHAR(128),
    len INTEGER,
    rating INTEGER,
    count INTEGER,
    album_id INTEGER,
    genre_id INTEGER,
    PRIMARY KEY (track_id),
    INDEX (title),
    CONSTRAINT FOREIGN KEY (album_id) REFERENCES album (album_id) ON DELETE CASCADE ON UPDATE CASCADE,
    CONSTRAINT FOREIGN KEY (genre_id) REFERENCES genre (genre_id) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB;
```

*   **多个外键**： 一个表拥有多个外键是完全正常的，这准确地反映了数据间的复杂关系。
*   **命名约定**： 遵循一致的命名约定（如 `artist_id`, `album_id`）至关重要。它能让代码更易读、易维护，也便于在需要时获得帮助。

## 执行SQL与插入数据

创建表时，必须按照从“叶子”到“根”的顺序，即先创建没有外键依赖的表。如果尝试先创建 `track` 表，数据库会因为找不到它引用的 `album` 和 `genre` 表而报错。

表创建完成后，我们开始插入数据。插入数据也需要遵循类似的顺序：必须先插入被引用的数据（如艺术家、流派），获取它们的主键ID，然后才能插入引用这些ID的数据（如专辑、曲目）。

![](img/dc3da283c9304fc962c6df09476e27c0_19.png)

以下是插入数据的示例：

![](img/dc3da283c9304fc962c6df09476e27c0_21.png)

1.  **插入艺术家**： 插入“Led Zeppelin”和“AC/DC”。数据库会为它们分配 `artist_id` (例如 1 和 2)。
2.  **插入流派**： 插入“Rock”和“Metal”，获取 `genre_id` (例如 1 和 2)。
3.  **插入专辑**： 插入专辑“Who Made Who”，并指定其 `artist_id` 为 2 (AC/DC)。插入专辑“IV”，指定 `artist_id` 为 1 (Led Zeppelin)。数据库会为专辑分配 `album_id`。
4.  **插入曲目**： 插入曲目“Black Dog”，并指定它所属的 `album_id` 和 `genre_id`。

当使用PHP等编程语言操作数据库时，这个过程会更简单，因为可以在插入一条记录后立即从数据库获取其自动生成的主键ID，然后用于后续的插入操作。

![](img/dc3da283c9304fc962c6df09476e27c0_23.png)

## 成果与总结

完成所有操作后，我们就成功地用数据库表重建了最初的逻辑模型图。通过外键约束，数据库管理工具（如phpMyAdmin）能够识别这些关系，并允许我们通过点击链接在不同表的数据间导航。

![](img/dc3da283c9304fc962c6df09476e27c0_25.png)

![](img/dc3da283c9304fc962c6df09476e27c0_27.png)

本节课中我们一起学习了如何将逻辑数据模型转化为物理数据模型。我们掌握了创建表、定义主键和外键约束的SQL语法，并理解了按正确顺序创建表和插入数据的重要性。最终，我们构建了一个没有字符串数据垂直冗余（如专辑名、流派名只存储一次）的高效数据库结构，而整数外键的重复则是允许且高效的。这个过程的核心在于用清晰的文本（SQL）来精确描述和实现我们心中的数据关系图。