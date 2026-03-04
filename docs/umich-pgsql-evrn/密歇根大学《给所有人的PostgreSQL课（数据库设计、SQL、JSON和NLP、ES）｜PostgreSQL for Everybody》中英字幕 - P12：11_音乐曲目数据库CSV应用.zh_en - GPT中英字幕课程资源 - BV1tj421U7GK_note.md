# PostgreSQL for Everybody：P12：音乐曲目数据库CSV应用 🎵

在本节课中，我们将学习如何将一个包含音乐曲目信息的CSV文件导入到PostgreSQL数据库中。我们将重点探索`COPY`命令的使用，并完成一个简单的数据库创建与数据导入任务。

![](img/7beca017416ad2e2154cbaeb837d04d7_1.png)

## 概述

我们将从一个远程URL获取一个CSV格式的音乐曲目文件，将其下载到本地，然后使用PostgreSQL的`psql`客户端工具，通过SQL语句创建表，并使用`\copy`命令将CSV数据导入到新创建的表中。最后，我们将验证数据是否成功导入。

## 准备工作

首先，我们需要在命令行环境中操作。假设我们处于一个Linux环境（例如PythonAnywhere）的家目录下，并且当前目录下没有其他文件。

以下是初始步骤：

![](img/7beca017416ad2e2154cbaeb837d04d7_3.png)

![](img/7beca017416ad2e2154cbaeb837d04d7_4.png)

![](img/7beca017416ad2e2154cbaeb837d04d7_5.png)

1.  使用`wget`或`curl`命令从指定的URL下载CSV文件。
2.  使用文本编辑器（如`vi`）查看文件内容，确认其为包含艺术家、标题、专辑等信息的逗号分隔值文件。

## 创建数据库表

![](img/7beca017416ad2e2154cbaeb837d04d7_7.png)

上一节我们准备好了数据文件，本节中我们来看看如何在数据库中创建对应的表结构。

我们需要在PostgreSQL中创建一个表，其列数与CSV文件的列数相匹配。通过`psql`命令连接到数据库后，执行创建表的SQL语句。

```sql
CREATE TABLE track_raw
(
    title TEXT,
    artist TEXT,
    album TEXT,
    count INTEGER,
    rating INTEGER,
    len INTEGER
);
```

执行上述SQL语句后，可以使用`\dt`命令（`psql`特有的元命令）来列出所有表，确认`track_raw`表已创建成功。

## 导入CSV数据

表结构已经就绪，现在我们需要将本地CSV文件的数据导入到这个表中。我们将使用`psql`的`\copy`命令。

`\copy`是一个`psql`客户端命令，而非标准SQL命令。它的作用是将客户端机器上的文件数据复制到数据库服务器上的指定表中。

以下是导入命令：

```sql
\copy track_raw(title, artist, album, count, rating, len) FROM 'library.csv' WITH DELIMITER ',' CSV;
```

这条命令指示数据库从`library.csv`文件中读取数据，按照逗号分隔，并插入到`track_raw`表的指定列中。

## 验证数据

数据导入后，验证操作是否成功至关重要。我们可以通过执行SQL查询语句来检查表中的记录数量和内容。

首先，查询表中的总记录数：

```sql
SELECT COUNT(*) FROM track_raw;
```

如果导入成功，查询应返回一个数字（例如296条记录）。接着，我们可以查看前几行数据以确认内容：

```sql
SELECT * FROM track_raw LIMIT 5;
```

这将显示表中最前面的几条记录，我们可以核对艺术家、曲目名等信息是否与CSV文件内容一致。

![](img/7beca017416ad2e2154cbaeb837d04d7_9.png)

## 任务提交与总结

![](img/7beca017416ad2e2154cbaeb837d04d7_11.png)

完成数据导入和验证后，即可提交作业。自动评分系统会连接到同一数据库，执行查询来验证`track_raw`表及其数据是否正确。

本节课中我们一起学习了如何将外部CSV数据文件导入PostgreSQL数据库。核心步骤包括：
1.  使用命令行工具下载文件。
2.  使用`CREATE TABLE`语句创建匹配的表结构。
3.  使用`psql`的`\copy`命令导入数据。
4.  使用`SELECT`语句验证数据完整性。

![](img/7beca017416ad2e2154cbaeb837d04d7_13.png)

对于本任务，使用`psql`客户端配合`\copy`命令是较为直接的方法。在其他图形化数据库客户端中，可能需要使用“导入”功能按钮。掌握这一流程为后续使用Python等编程语言进行更复杂的数据操作打下了基础。