# 未来数据系统研讨会系列：P8：Mooncake：无妥协的实时 Apache Iceberg

![](img/27e5fb4fb5c29542a36cb78990afdee9_0.png)

![](img/27e5fb4fb5c29542a36cb78990afdee9_0.png)

在本节课中，我们将学习 Mooncake 项目，这是一个旨在构建可组合 HTAP 架构的系统。我们将探讨如何在不牺牲性能的前提下，实现从 PostgreSQL 到 Apache Iceberg 的实时数据同步，并支持在 PostgreSQL 内直接进行快速分析查询。

## 概述：HTAP 的挑战与机遇

上一节我们介绍了数据系统的发展背景。传统的单一关系型数据库难以同时满足在线事务处理（OLTP）和在线分析处理（OLAP）的需求。OLTP 需要微秒级的插入和点查询，而 OLAP 则要求全表扫描和大规模聚合，这导致了系统设计的根本性矛盾。

随着云计算的兴起，计算与存储分离，湖仓一体架构通过开放格式统一了存储层。然而，事务处理端与分析处理端仍然是两个独立的系统，用户被迫使用复杂且脆弱的数据管道手动将它们拼接在一起。这引出了一个核心问题：我们能否做得更好？

## 从单体 HTAP 到可组合 HTAP

最初的 HTAP 愿景是构建一个单体引擎，能够同时服务 OLTP 和 OLAP 工作负载。然而，实践证明，构建这样的单体引擎极具挑战性。它需要同时与最好的 OLTP 引擎和最好的 OLAP 引擎竞争，并且常常为了兼顾两者而做出妥协，而这些妥协只为少数极端用例服务。

更现实的需求是：用户希望在新鲜的事务数据上运行更快的分析，以做出更智能、更快的决策。对于这类需求，并不需要一个单体 HTAP 引擎。

因此，我们提出了 **可组合 HTAP 架构**。其核心思想不是替换用户现有的系统，而是**桥接**它们。用户继续使用他们喜欢的 OLTP 系统（如 PostgreSQL）和 OLAP 系统（如基于 Iceberg 或 Delta Lake 的湖仓），而 Mooncake 则在这之上添加一个实时层，实现从 OLTP 到 OLAP 的秒级数据同步，并支持直接从 OLTP 读取数据以进行新鲜度极高的分析。

这是一种可以按需开启的“特性”，旨在简化整个数据栈。

## Mooncake 的核心组件

Mooncake 架构主要由两个核心组件构成：
1.  **Moonlink**：构建在 Iceberg 之上的实时层，负责实现从 PostgreSQL 到 Iceberg 的秒级数据摄取。
2.  **PG Mooncake**：一个 PostgreSQL 扩展，允许在 PostgreSQL 内部直接对 Iceberg 镜像表执行快速分析查询。当与 Moonlink 结合时，它提供了一个完整的、可组合的 HTAP 解决方案。

接下来，我们将深入探讨这两个组件的技术细节。

## 深入 Moonlink：构建实时数据摄取层

构建实时数据摄取到 Iceberg 的挑战，主要不在于 ETL 过程本身，而在于目标系统（Iceberg）本身不足以实时跟上源系统（PostgreSQL）的事务速度。

我们的目标是支持流式写入和批量写入，同时处理插入、更新和删除操作，并始终确保目标表为读取优化。从数据在 PostgreSQL 端产生，到在分析端可被查询，其延迟需要极低（亚秒级），才能被认为是真正的实时。

以下是 Moonlink 解决的关键挑战：

### 1. 流式写入与仅插入场景

核心挑战在于不能过于频繁地向 Iceberg 写入，否则会产生大量小文件，导致元数据爆炸和读取成本高昂。同时，我们需要提供一致的视图供读取。

**解决方案**：我们解耦了 Mooncake 快照和 Iceberg 快照。
*   **Mooncake 快照**：一个轻量级快照，每 500 毫秒创建一次，用于服务“联合读取”。
*   **Iceberg 快照**：基于最新的 Mooncake 快照创建，频率较低（例如每5分钟或当累积足够多变更时）。

具体流程如下：
1.  新插入的数据首先被追加到一个内存中的 Arrow 缓冲区。
2.  读取时，组合这个内存缓冲区和磁盘上的 Parquet 文件，以提供最新数据的一致视图。
3.  当需要创建 Iceberg 快照时，将内存中的 Arrow 缓冲区刷新为一个新的 Parquet 文件，并基于最新的 Mooncake 快照形成新的 Iceberg 快照。

### 2. 支持更新和删除

PostgreSQL 使用 `REPLICA IDENTITY` 来标识行以进行更新和删除的复制。默认是主键，也可以是唯一键或整行。复制时，删除会发送旧的标识，更新会发送旧的标识和新的行。

**挑战**：需要将 PostgreSQL 的等值删除转换为更适合高效读取的**位置删除**（如 Iceberg V3 的删除向量）。

**解决方案**：构建一个哈希索引，将 `REPLICA IDENTITY` 的哈希值映射到行的位置（文件ID + 行ID）。
*   对于内存中的 Arrow 部分，使用内存哈希表。
*   对于磁盘上的 Parquet 部分，使用磁盘优化的哈希表（索引 LSM 结构），并存储在 Iceberg 的元数据文件中。

**优化**：由于我们与 PostgreSQL 保持同步，如果 PostgreSQL 说某行存在，那么它一定存在。因此，哈希查找通常只需一次，无需回读数据进行比较。

处理流程：
1.  当从 PostgreSQL 复制来更新/删除时，首先将等值删除记录追加到一个删除日志中（前台操作，非常快）。
2.  在后台，Mooncake 快照会使用哈希索引将这些等值删除转换为位置删除。
3.  Iceberg 快照随后用来自 Mooncake 快照的位置删除来更新删除向量。

### 3. 支持大事务

PostgreSQL 16 增强了逻辑复制，支持流式传输进行中的大事务。我们为每个大事务维护单独的数据日志和删除日志，并允许在事务中间刷新 Parquet 文件，而不是等待整个事务提交，以避免内存溢出。

**关键细节**：将等值删除转换为位置删除的操作必须是全局的，以确保事务间的可见性（如读已提交隔离级别）。

### 4. 初始表复制与崩溃恢复

**初始复制**：通过逻辑复制槽导出一个一致性快照，然后启动并行工作器（按 `CTID` 分片）复制表数据。完成后，从该槽开始应用增量变更。

**崩溃恢复**：早期方案依赖 PostgreSQL WAL，但这会导致复制槽滞后。改进方案是引入 **Mooncake 预写日志**。我们在数据写入 Mooncake WAL 后即向 PostgreSQL 确认，允许复制槽前进。恢复时需要仔细协调最新的 Mooncake 快照、Iceberg 快照和 Mooncake WAL，以确保一致性。

### 5. 压缩与优化

需要定期合并小文件以优化读取。压缩是长时间运行的事务，不应阻塞并发写入。

**解决方案**：在压缩时，同时构建一个重映射表，将旧行位置映射到新位置。在提交压缩前，快速遍历删除日志，将其中引用的旧位置重映射到新位置。这个过程很快，之后压缩便可提交。

![](img/27e5fb4fb5c29542a36cb78990afdee9_2.png)

![](img/27e5fb4fb5c29542a36cb78990afdee9_4.png)

**集群键**：在列表存储上定义集群键（哈希键、排序键或更智能的液态集群），可以更有效地跳过数据。Mooncake 正在构建此功能，而加入 Databricks 后可以利用其现有的集群能力。

### 总结 Moonlink

Moonlink 通过缓冲和索引在 Iceberg 之上添加了一个实时层。
*   **前台**：仅消费 PostgreSQL CDC，将新行追加到 Arrow 缓冲区，并将等值删除记录到删除日志。这是快速路径。
*   **后台**：异步进行 Mooncake 快照、Iceberg 快照、压缩等重操作，这些都不会阻塞前台的复制。

读取引擎可以直接从 Iceberg 读取历史数据。如果需要读取最新变更，可以通过“联合读取”直接从 Moonlink 获取，实现亚秒级延迟。

## 深入 PG Mooncake：在 PostgreSQL 内实现快速分析

PG Mooncake 支持在 PostgreSQL 内直接进行快速分析，当与 Moonlink 结合时，它提供了完整的可组合 HTAP 体验。

用户接口非常简单：
```sql
-- 在 PostgreSQL 中为现有表创建一个 Mooncake（列表存储）镜像
CALL mooncake.create_mirror(
    source_table => 'public.orders',
    iceberg_table => 'analytics.orders_mirror',
    cluster_by => 'customer_id, order_date'
);
```
创建后，`orders_mirror` 就像普通的 PostgreSQL 表一样，可以查询、甚至可以与堆表进行连接。但它是只读的，写入应通过源 `orders` 表进行。在 ClickBench 等基准测试中，对此类镜像表的分析查询性能可比直接查询 PostgreSQL 堆表快上千倍。

### 技术实现：基于 PG DuckDB

PG Mooncake 建立在 **PG DuckDB** 扩展之上。PG DuckDB 将 PostgreSQL 查询联合到 DuckDB 执行，它挂钩到 PostgreSQL 规划器，重写查询语法，在 DuckDB 中执行，然后将结果流式传回并转换为 PostgreSQL 类型。

然而，PG DuckDB 缺少存储层。如果只是用 DuckDB 查询 PostgreSQL 原生表，性能提升有限。DuckDB 的真正优势在于查询列式格式（如 Parquet）的数据。

**PG Mooncake 的贡献**：
1.  **存储层**：通过集成 Moonlink，为 PostgreSQL 表创建并维护一个实时的 Iceberg 镜像。
2.  **目录集成**：PG Mooncake 指示 PG DuckDB 将 Mooncake 表重写为 Mooncake 目录下的表。该目录由我们的 Mooncake DuckDB 扩展注册。
3.  **读取路径**：当执行表扫描时，通过 RPC 调用向 Moonlink 请求当前快照的元数据（包括数据文件、删除文件、内存缓冲区等），然后利用 DuckDB 的 Parquet 扫描器来处理所有这些，向用户呈现最新视图。

### 会话级一致性

为了提供真正的 HTAP 体验，PG Mooncake 旨在提供**会话级一致性**。即，在一个 PostgreSQL 连接中写入后，立即从列表存储镜像表进行查询，应该能立即看到更改。

这是通过将最后一个提交的 LSN 传递给 Moonlink 实现的。Moonlink 会等待，直到该 LSN 之前的变更都已被应用后，才返回快照。由于 Moonlink 速度极快，即使在一次大写入后，`SELECT` 查询也能在亚秒级延迟内完成。

需要注意的是，由于 PostgreSQL 逻辑复制的限制，无法捕获所有未提交的更改，因此**在事务内进行分析**这种“完全体”HTAP 用例无法实现。但正如之前所讨论的，这并非我们的目标，因为该用例非常小众。

## 总结与展望

本节课我们一起学习了 Mooncake 如何通过可组合的架构重新思考 HTAP。
*   **Moonlink** 作为实时层，解决了向 Iceberg 实时摄取的挑战，支持流式/批量写入、更新/删除，并优化了读取性能。
*   **PG Mooncake** 作为 PostgreSQL 扩展，利用 DuckDB 的执行能力，并通过集成 Moonlink 提供了存储层，使得在 PostgreSQL 内进行快速分析成为可能，同时保证了会话级一致性。

这种模块化、可组合的设计原则，使得该框架不仅能用于 PostgreSQL 和 Iceberg，也能扩展到其他 OLTP 系统（如 MySQL）和湖仓格式（如 Delta Lake），甚至支持从 Kafka 等事件流摄取数据。

展望未来，在湖仓基座（Lakebase）与湖仓一体（Lakehouse）融合的背景下，有许多开放问题值得探索：反向 ETL、跨组织的 PostgreSQL 数据共享、为 OLTP 定义开放格式、在湖仓上构建二级索引以服务查询、智能的跨引擎负载路由，以及利用 Unity Catalog 等实现跨事务和分析数据的统一治理等。

![](img/27e5fb4fb5c29542a36cb78990afdee9_6.png)

Mooncake 为构建未来的数据系统提供了一个激动人心的方向。