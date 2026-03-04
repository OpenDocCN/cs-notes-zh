# PostgreSQL 数据库教程：第15章：数据库创建与数据加载演示 🗄️

在本节课中，我们将学习如何创建数据库表、修改表结构以及向表中加载数据。我们将通过一个包含用户、帖子和评论的三表关系示例来演示这些操作。

## 概述

我们将创建一个简单的多对多关系数据库模型，包含用户、帖子和评论三个表。随后，我们将学习如何使用 `ALTER TABLE` 命令修改表结构，并演示如何从外部文件加载数据到数据库中。

## 创建数据库表

首先，我们来创建三个核心表。这个模型描述了一个简单的社交场景：用户可以发布帖子，也可以对帖子发表评论。评论表本质上是一个连接用户和帖子的多对多关联表，但它额外存储了重要的关联信息，如评论内容和创建时间。

以下是创建这些表的 SQL 命令：

```sql
CREATE TABLE account (
    id SERIAL PRIMARY KEY,
    email VARCHAR(128) UNIQUE,
    created_at TIMESTAMPTZ NOT NULL DEFAULT now(),
    updated_at TIMESTAMPTZ NOT NULL DEFAULT now()
);

CREATE TABLE post (
    id SERIAL PRIMARY KEY,
    title VARCHAR(256),
    content VARCHAR(1024), -- 注意：我们稍后会修改此列
    account_id INTEGER REFERENCES account(id),
    created_at TIMESTAMPTZ NOT NULL DEFAULT now(),
    updated_at TIMESTAMPTZ NOT NULL DEFAULT now()
);

CREATE TABLE comment (
    id SERIAL PRIMARY KEY,
    content TEXT,
    account_id INTEGER REFERENCES account(id),
    post_id INTEGER REFERENCES post(id),
    created_at TIMESTAMPTZ NOT NULL DEFAULT now(),
    updated_at TIMESTAMPTZ NOT NULL DEFAULT now()
);
```

**代码解释**：
*   `SERIAL` 是 PostgreSQL 中自动递增的整数类型，常用作主键。
*   `VARCHAR(n)` 定义了最大长度为 `n` 的可变字符串。
*   `TIMESTAMPTZ` 是包含时区信息的时间戳类型。请注意一个常见拼写错误是 `timestamp Z`，正确的应为 `TIMESTAMPTZ`。
*   `REFERENCES` 用于定义外键约束，例如 `account_id INTEGER REFERENCES account(id)` 表示 `comment` 表中的 `account_id` 列引用了 `account` 表中的 `id` 列。

执行这些命令后，我们的数据库结构就建立好了。

## 修改表结构

上一节我们创建了初始表结构，但在实际开发中，需求可能会变化，我们需要修改表结构。PostgreSQL 的 `ALTER TABLE` 命令非常强大，允许我们在数据库运行时动态调整表定义。

假设我们收到新需求，帖子内容可能超过最初设定的 1024 字符限制，我们需要修改 `post` 表的 `content` 列类型。

### 使用 ALTER TABLE 命令

以下是修改表结构的几个常见操作示例：

1.  **修改列的数据类型**：将 `post` 表的 `content` 列从 `VARCHAR(1024)` 改为容量更大的 `TEXT` 类型。
    ```sql
    ALTER TABLE post
    ALTER COLUMN content TYPE TEXT;
    ```
    **注意**：此命令会尝试转换表中已有的数据。如果原数据与新类型不兼容（例如，将包含字母的字符串转为整数），操作可能会失败。

2.  **删除一个列**：假设我们想删除一个名为 `oops` 的列。
    ```sql
    ALTER TABLE post
    DROP COLUMN oops;
    ```
    **警告**：在生产数据库中删除正在被应用程序使用的列，会导致查询立即失败。

3.  **添加一个新列**：例如，向 `post` 表添加一个表示“点赞数”的列。
    ```sql
    ALTER TABLE post
    ADD COLUMN likes INTEGER;
    ```

数据库模式（Schema）的设计本意是为了约束和保证数据一致性，但 `ALTER TABLE` 提供了在必要时安全修改它的能力。只要不破坏现有应用程序的逻辑，这些操作甚至可以在事务处理过程中进行。

## 加载数据到表中

![](img/4a148343c847ec4b1de6813ef1f8c7e9_1.png)

表结构准备就绪后，下一步就是向表中填充数据。我们可以手动执行 `INSERT` 语句，但对于大量数据，从文件加载更为高效。

![](img/4a148343c847ec4b1de6813ef1f8c7e9_2.png)

### 准备数据文件

通常，我们会将一系列 SQL 命令（如 `DELETE`、`INSERT`）保存到一个 `.sql` 文件中。例如，一个名为 `03_techniques_load.sql` 的文件可能包含以下内容：

```sql
-- 清空 account 表并重置序列（仅用于演示，生产环境慎用）
DELETE FROM account;
ALTER SEQUENCE account_id_seq RESTART;

-- 插入示例用户数据
INSERT INTO account (email) VALUES ('user1@example.com');
INSERT INTO account (email) VALUES ('user2@example.com');

![](img/4a148343c847ec4b1de6813ef1f8c7e9_4.png)

-- 插入示例帖子数据
INSERT INTO post (title, content, account_id) VALUES ('First Post', 'Hello World!', 1);
INSERT INTO post (title, content, account_id) VALUES ('Another Post', 'Database tutorial.', 2);
```

![](img/4a148343c847ec4b1de6813ef1f8c7e9_6.png)

**代码解释**：
*   `DELETE FROM account;` 会删除 `account` 表中的所有记录。
*   `ALTER SEQUENCE ... RESTART;` 将主键的序列计数器重置。**请注意**，这种清空并重置的操作仅适用于测试或演示环境，切勿在正在运行的生产数据库上随意执行。

### 在 PostgreSQL 客户端中执行文件

有多种方法可以将此文件加载到数据库中。一种常见方式是在 `psql`（PostgreSQL 命令行客户端）中使用 `\i` 命令。

操作步骤如下：
1.  确保 `.sql` 数据文件位于当前工作目录。
2.  在 `psql` 客户端中，使用以下命令执行该文件：
    ```sql
    \i 03_techniques_load.sql
    ```
    **注意**：以反斜杠 `\` 开头的命令（如 `\i`, `\dt`, `\d+`）是 `psql` 客户端特有的元命令，并非标准 SQL。它们在其他数据库的客户端工具中可能有不同的名称或不可用。

执行后，文件中的所有 SQL 命令都会按顺序运行，数据便被加载到相应的表中。之后，你可以使用 `SELECT * FROM post;` 等查询来验证数据是否已成功插入。

## 总结

本节课中我们一起学习了 PostgreSQL 数据库操作的核心流程。
我们首先创建了定义数据关系的表结构，然后使用 `ALTER TABLE` 命令灵活地修改了表定义以适应变化的需求，最后演示了如何通过执行外部 SQL 文件来高效地向表中加载初始数据。
掌握这些基本操作，是进行后续数据查询、管理和应用开发的重要基础。