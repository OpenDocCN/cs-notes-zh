# 076：全文检索函数 tsquery 与 tsvector 演示 🧠

在本节课中，我们将学习 PostgreSQL 内置的全文检索功能。我们将重点介绍两个核心函数：`tsvector` 和 `tsquery`，它们能高效地处理文本，自动完成词干提取和停用词移除，远比我们之前用纯 SQL 实现的方法更强大、更便捷。

上一节我们介绍了如何使用 SQL 手动处理停用词和词干提取。本节中，我们来看看 PostgreSQL 如何通过内置功能自动完成这些任务。

## 核心函数：`tsvector` 与 `tsquery`

PostgreSQL 提供了两个语言感知的函数来构建全文检索：
*   **`to_tsvector`**：将文本字符串转换为一个特殊的 `tsvector` 数据结构，其中包含词干化后的词汇及其在原文中的位置。
*   **`to_tsquery`**：将搜索查询字符串转换为一个 `tsquery` 对象，它代表一个可执行的搜索条件。

这两个函数都需要指定语言，以便 PostgreSQL 选择对应的词典进行词干提取和停用词处理。

### 使用 `to_tsvector`

以下是 `to_tsvector` 函数的使用示例：

```sql
SELECT to_tsvector('english', 'I am teaching people SQL and Python');
```

执行结果类似于：
```
‘peopl’:2 ‘python’:7 ‘sql’:6 ‘teach’:3
```
*   停用词 “I”, “am”, “and” 被移除。
*   “teaching” 被词干化为 “teach”。
*   “people” 被词干化为 “peopl”。
*   数字 `2`、`7`、`6`、`3` 表示这些词在原始句子中的位置。

### 使用 `to_tsquery`

![](img/0a5a76e3b3792da1aa8662134b46bc85_1.png)

以下是 `to_tsquery` 函数的使用示例：

```sql
SELECT to_tsquery('english', 'teaching');
```

执行结果为：
```
‘teach’
```
可以看到，“teaching” 被正确地词干化为 “teach”。

## 执行全文搜索

我们可以使用 `@@` 操作符来检查一个 `tsquery` 是否匹配一个 `tsvector`。

```sql
SELECT to_tsquery('english', 'teach') @@ to_tsvector('english', 'I am teaching people');
```

这个查询将返回 `true`，因为经过处理后的查询词 “teach” 匹配到了文本向量中的 “teach”。

## 构建更复杂的查询

`tsquery` 支持逻辑运算符，允许构建更复杂的搜索条件。

以下是 `tsquery` 支持的一些高级构造方式：

*   **逻辑 OR**：使用 `|` 符号。
    ```sql
    SELECT to_tsquery('english', 'teaching | learns | learned');
    ```
    这会被处理为搜索 “teach” 或 “learn”。

*   **`plainto_tsquery`**：将普通短语转换为 `tsquery`，词与词之间默认为 **AND** 关系。
    ```sql
    SELECT plainto_tsquery('english', 'SQL Python');
    ```
    这相当于搜索同时包含 “sql” **和** “python” 的文档。

*   **`phraseto_tsquery`**：用于搜索确切的短语。
    ```sql
    SELECT phraseto_tsquery('english', 'SQL followed by Python');
    ```
    这会搜索 “sql” 后面紧跟着 “python” 的短语。

*   **`websearch_to_tsquery` (PostgreSQL 11+)**：使用更接近网络搜索引擎的语法（例如，引号表示短语，`-` 表示排除），并且对用户输入错误有更好的容错性。
    ```sql
    SELECT websearch_to_tsquery('english', '"SQL tutorial" -basic');
    ```
    这会搜索精确短语 “sql tutorial” 并且排除包含 “basic” 的文档。

## 本节总结

本节课中我们一起学习了 PostgreSQL 全文检索的核心基础。我们了解了 `to_tsvector` 和 `to_tsquery` 函数如何自动、高效地处理文本的词干提取和停用词过滤，并学会了使用 `@@` 操作符进行基本匹配，以及构建带有逻辑运算符的复杂查询。

![](img/0a5a76e3b3792da1aa8662134b46bc85_3.png)

关键在于，无论是被搜索的文档（使用 `to_tsvector` 处理）还是搜索查询本身（使用 `to_tsquery` 处理），都必须经过相同的处理流程，才能进行准确的匹配。

![](img/0a5a76e3b3792da1aa8662134b46bc85_5.png)

下一节，我们将探讨如何在实际的数据库表列上创建全文检索索引，以大幅提升这类搜索查询的性能。