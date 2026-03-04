# PostgreSQL for Everybody：9：基于GIN的PostgreSQL倒排索引 🗂️

在本节课中，我们将学习PostgreSQL内置的倒排索引，特别是GIN（通用倒排索引）索引。我们将了解其工作原理、如何创建以及如何利用它来高效执行文本搜索查询。

## 概述

上一节我们手动使用SQL语句创建了倒排索引，以理解其核心概念。本节中，我们来看看PostgreSQL内置的、功能更强大的倒排索引实现。PostgreSQL主要提供两种倒排索引：GIN和GiST。我们将重点介绍GIN索引，它适用于需要高效查询但可以接受稍高插入成本的场景。

## GIN索引与GiST索引

以下是PostgreSQL中两种主要倒排索引的对比：

*   **GIN（通用倒排索引）**：这是首选的文本搜索索引类型。它类似于B树索引，能进行精确匹配，只读取包含目标数据的必要数据块，查询效率极高。其缺点是插入或更新数据时成本较高。
*   **GiST（通用搜索树）**：这种索引体积更小，更新速度更快。它使用哈希算法，虽然计算更简单，但可能因哈希冲突导致读取额外的数据块（尽管最终结果集仍是正确的）。它适用于插入/更新非常频繁，而查询性能要求相对较低的场景。

选择哪种索引取决于**插入操作与查询操作之间的平衡**。对于博客这类查询远多于新文章发布的场景，GIN是更好的选择。对于类似持续接收数据流、偶尔才进行查询的场景，GiST可能更合适。

## 创建并使用GIN索引

现在，我们通过一个具体示例来学习如何创建和使用GIN索引。关键在于，**索引创建时的表达式必须与`WHERE`子句中使用的表达式完全匹配**，这样PostgreSQL的查询优化器才能有效地利用索引。

以下是创建和使用GIN索引的核心步骤：

1.  **创建表并插入数据**：
    ```sql
    CREATE TABLE docs (id SERIAL PRIMARY KEY, doc TEXT);
    INSERT INTO docs (doc) VALUES ('This is a sample document.');
    INSERT INTO docs (doc) VALUES ('Learn about PostgreSQL indexing.');
    INSERT INTO docs (doc) VALUES ('Another example for learning.');
    ```

2.  **创建GIN索引**：
    我们基于将文档文本按空格拆分成单词数组的结果来创建索引。
    ```sql
    CREATE INDEX gin1 ON docs USING GIN(string_to_array(doc, ' ')::text[]);
    ```
    这个命令创建了一个GIN索引，它索引的是`docs`表中`doc`列内容被分割成的文本数组。

3.  **编写利用索引的查询**：
    查询时，我们使用`<@`（包含于）操作符来检查我们的搜索词数组是否被包含在文档生成的单词数组中。
    ```sql
    SELECT * FROM docs WHERE string_to_array(doc, ' ')::text[] <@ ARRAY['Learn']::text[];
    ```
    此查询将高效地返回所有包含单词“Learn”的文档行。

## 验证索引使用

创建索引和查询后，务必验证PostgreSQL是否真的使用了索引。我们可以使用`EXPLAIN`命令来查看查询计划。

执行以下命令：
```sql
EXPLAIN SELECT * FROM docs WHERE string_to_array(doc, ' ')::text[] <@ ARRAY['Learn']::text[];
```

在输出结果中，你需要寻找类似`Index Scan using gin1 on docs`这样的信息。**最需要避免的是看到`Seq Scan`（顺序扫描）**，这表示查询没有使用索引，而是遍历了所有行，意味着索引未被正确触发。

调试查询计划可能需要一些实践，但确保关键查询能利用索引是优化数据库性能的重要环节。

## 从字符串索引到自然语言索引

本节我们介绍的是基于纯字符串分割的简单倒排索引。虽然示例使用的是英文文本，但当前索引对语言本身并无理解（例如，它不知道“learn”和“learning”是同一个词的不同形式）。

在接下来的课程中，我们将开始从这种纯字符串索引转向更高级的**自然语言索引**。PostgreSQL的倒排索引非常强大，它们通过特定的“操作符类”来理解被索引数据的类型，从而构建更优化的索引结构，以支持更复杂的文本搜索需求。

## 总结

本节课中我们一起学习了PostgreSQL内置的GIN倒排索引。我们了解了GIN与GiST索引的区别及适用场景，掌握了创建GIN索引的语法，并学会了如何编写查询以利用索引提升性能，以及如何使用`EXPLAIN`命令验证索引是否生效。记住，让`WHERE`子句中的表达式与索引定义表达式匹配是关键。这些索引功能强大且易于使用，能极大提升全文搜索的效率。