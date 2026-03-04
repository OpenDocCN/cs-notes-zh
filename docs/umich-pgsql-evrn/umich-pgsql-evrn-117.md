# 117：Elasticsearch推文处理 📝

在本节课中，我们将学习如何使用Python客户端与Elasticsearch进行交互，完成一个完整的“索引-查询”流程。我们将通过一个简单的推文处理示例，演示如何建立连接、创建索引、插入文档、刷新索引以及执行查询。

---

## 概述与准备 🛠️

![](img/829e6cd757e6a2ce8a5605e1623d92a7_1.png)

上一节我们介绍了Elasticsearch的基本概念。本节中，我们来看看如何使用Python代码实际操作Elasticsearch。

![](img/829e6cd757e6a2ce8a5605e1623d92a7_2.png)

首先，你需要完成一些准备工作。以下是必要的步骤：

*   确保你已经正确设置了环境变量来存储敏感信息（如主机、用户名、密码）。
*   使用 `pip3` 安装Elasticsearch的Python客户端库（如果尚未安装）。

![](img/829e6cd757e6a2ce8a5605e1623d92a7_4.png)

准备工作完成后，我们就可以开始编写代码了。

![](img/829e6cd757e6a2ce8a5605e1623d92a7_5.png)

---

## 建立Elasticsearch连接 🔌

![](img/829e6cd757e6a2ce8a5605e1623d92a7_7.png)

首先，我们需要导入必要的库并建立与Elasticsearch服务的连接。我们会从环境变量中读取配置信息，以确保安全。

```python
import os
from elasticsearch import Elasticsearch

![](img/829e6cd757e6a2ce8a5605e1623d92a7_9.png)

# 从环境变量读取配置（避免在代码中硬编码敏感信息）
host = os.environ.get('ES_HOST')
user = os.environ.get('ES_USER')
password = os.environ.get('ES_PASSWORD')

![](img/829e6cd757e6a2ce8a5605e1623d92a7_11.png)

# 创建Elasticsearch客户端实例
es = Elasticsearch(
    hosts=[host],
    http_auth=(user, password)
)
```

通过`Elasticsearch`客户端库，我们可以方便地管理连接。当然，你也可以直接使用`requests`库发送HTTP请求来与Elasticsearch交互。

![](img/829e6cd757e6a2ce8a5605e1623d92a7_13.png)

---

## 初始化索引 📇

在插入数据之前，我们通常需要初始化索引。为了演示的清晰性，我们会先删除可能已存在的同名索引，然后创建一个新索引。

```python
index_name = "demo-tweets"

![](img/829e6cd757e6a2ce8a5605e1623d92a7_15.png)

# 如果索引已存在，则删除它
if es.indices.exists(index=index_name):
    es.indices.delete(index=index_name)

# 创建新索引
es.indices.create(index=index_name)
```

Elasticsearch将数据组织为**文档**。每个文档本质上是一个JSON对象，可以包含嵌套的字典、列表等各种结构。

![](img/829e6cd757e6a2ce8a5605e1623d92a7_17.png)

---

## 插入文档 📄

现在，我们可以向索引中插入一个文档。在Elasticsearch中，插入操作被称为“索引”一个文档，这反映了其底层基于倒排索引的设计思想。

![](img/829e6cd757e6a2ce8a5605e1623d92a7_19.png)

以下是插入单个推文文档的代码：

![](img/829e6cd757e6a2ce8a5605e1623d92a7_20.png)

```python
# 定义一个文档
doc = {
    "type": "tweet",
    "author": "demo_user",
    "text": "This is a test tweet about Elasticsearch!",
    "timestamp": "2023-10-27"
}

# 索引（插入）文档。‘id’参数指定文档的主键。
response = es.index(index=index_name, id="abc123", document=doc)
print("插入成功:", response['result'])
```

操作会返回一个结果，我们可以检查`response['result']`来判断是否成功。

---

## 检索与刷新 🔍

插入文档后，我们可以立即通过主键检索它。但为了后续能进行全文搜索，我们需要确保索引已更新。

![](img/829e6cd757e6a2ce8a5605e1623d92a7_22.png)

以下是检索和刷新操作的代码：

![](img/829e6cd757e6a2ce8a5605e1623d92a7_23.png)

![](img/829e6cd757e6a2ce8a5605e1623d92a7_24.png)

```python
# 1. 通过主键检索文档
get_response = es.get(index=index_name, id="abc123")
print("检索到的文档:", get_response['_source'])

![](img/829e6cd757e6a2ce8a5605e1623d92a7_25.png)

# 2. 刷新索引
# 此操作会等待所有索引操作完成，确保新文档可被搜索。
# 注意：在生产环境中，频繁刷新可能影响性能，此处仅用于演示。
es.indices.refresh(index=index_name)
```

`refresh` 操作会强制Elasticsearch完成所有挂起的索引更新，使新文档立即可查。在真实场景中，索引更新通常是近实时的，但可能有短暂延迟。

---

## 执行搜索查询 🔎

![](img/829e6cd757e6a2ce8a5605e1623d92a7_27.png)

![](img/829e6cd757e6a2ce8a5605e1623d92a7_28.png)

上一节我们插入了文档并刷新了索引，本节中我们来看看如何执行一个更复杂的搜索查询。

![](img/829e6cd757e6a2ce8a5605e1623d92a7_29.png)

![](img/829e6cd757e6a2ce8a5605e1623d92a7_30.png)

Elasticsearch的查询功能非常强大。以下是一个组合查询示例，它同时使用了精确过滤和全文匹配。

```python
# 定义查询体
query_body = {
    "query": {
        "bool": {
            "must": [
                {"match": {"text": "test elasticsearch"}}  # 全文软匹配
            ],
            "filter": [
                {"term": {"type": "tweet"}}  # 精确过滤
            ]
        }
    }
}

# 执行搜索
search_response = es.search(index=index_name, body=query_body)
print(f"找到 {search_response['hits']['total']['value']} 个结果。")

# 遍历并输出结果
for hit in search_response['hits']['hits']:
    print(f"得分: {hit['_score']}, 内容: {hit['_source']}")
```

在这个查询中：
*   `bool` 查询用于组合多个条件。
*   `must` 子句中的 `match` 查询用于对`text`字段进行全文搜索，这是一种“软匹配”，支持分词和近似匹配。
*   `filter` 子句中的 `term` 查询用于对`type`字段进行精确匹配，这是一种“硬过滤”，能高效地缩小搜索范围。
*   两者结合的效果类似于SQL中的 `WHERE type=‘tweet’ AND text LIKE ‘%test%elasticsearch%’`，但更加灵活和强大。

---

## 总结 📋

本节课中我们一起学习了使用Elasticsearch Python客户端进行基本操作的完整流程。

![](img/829e6cd757e6a2ce8a5605e1623d92a7_32.png)

我们首先建立了与Elasticsearch服务的连接，然后初始化了索引。接着，我们插入了一个示例推文文档，并通过主键将其检索出来。为了确保数据可被搜索，我们执行了索引刷新操作。最后，我们构建并执行了一个组合查询，演示了如何同时使用精确过滤和全文匹配来查找文档。

这个简单的流程为你提供了一个可工作的起点，你可以在此基础上修改代码，尝试插入不同类型的数据，构建更复杂的查询，从而深入探索Elasticsearch的强大功能。