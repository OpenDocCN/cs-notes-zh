# Python与Pandas扩展方法比较：1：概述与挑战

![](img/7a0a16a9552ae890dfb1d9cc57f2ba2c_1.png)

![](img/7a0a16a9552ae890dfb1d9cc57f2ba2c_2.png)

在本节课中，我们将学习如何将单机运行的Python和Pandas代码扩展到分布式计算环境中。我们将探讨传统扩展方法（如类Pandas和类SQL语义层）的局限性，并介绍Fugue如何作为一个更优的抽象层来解决这些问题。

扩展Python和Pandas代码的需求源于其固有的限制。Pandas默认是单核运行的，内存效率不高，并且其处理能力受限于单台机器的资源。当数据量增长或计算复杂度增加时，这些限制会成为瓶颈。为了突破这些瓶颈，我们需要借助分布式计算框架，如Spark、Dask或Ray。然而，直接使用这些框架需要学习新的语法和概念，迁移成本很高。因此，出现了“语义层”作为桥梁，将用户熟悉的逻辑映射到分布式框架上执行。

---

## Python与Pandas扩展方法比较：2：传统语义层的局限性

上一节我们介绍了扩展代码的必要性。本节中，我们将深入探讨两种常见的传统语义层——类Pandas语义和类SQL语义——各自存在的缺陷。

### 类Pandas语义的挑战

类Pandas语义（如Modin、Koalas）试图让用户用Pandas语法编写代码，然后在分布式后端执行。然而，Pandas的许多基本假设在分布式环境中并不成立，导致接口不一致和执行行为难以预测。

以下是几个关键的不匹配点：

1.  **随机访问的代价**：Pandas的`iloc`等操作假设随机访问是廉价的，但在分布式系统中，数据分散在不同节点，随机访问代价高昂。
    *   **代码示例**：`df.iloc[500000]` 在Pandas上很快，但在Spark上可能慢15倍。
2.  **自然顺序的保留**：Pandas会保持数据的自然顺序，但在分布式系统中，全局排序非常昂贵且并非总是有明确定义。
    *   **代码示例**：对分布式数据框排序后计算差异，结果可能与Pandas不同。
3.  **数据洗牌的优化**：在Pandas中，某些优雅的写法（如排序后去重）可能比另一种写法（如分组求索引再连接）更快。但在分布式系统中，后者可能通过避免大规模数据洗牌而快得多。用户不得不在代码优雅性和性能之间做出艰难选择。
4.  **索引的效率**：Pandas的索引能加速查询，但在分布式后端中，`set_index`后的查询性能可能反而不如直接查询，且多重索引支持不完全。
5.  **惰性求值的陷阱**：Spark、Dask等框架采用惰性求值来优化。如果不理解这一点，简单的操作（如多次计算不同统计量）可能导致同一数据被重复读取多次，性能急剧下降。而Pandas是即时求值的，行为可预测。

### 类SQL语义的挑战

使用SQL（特别是CTE公用表表达式）来描述复杂逻辑是另一种常见做法，但它也存在问题：

1.  **语法冗长**：CTE要求为每个子查询命名并嵌套括号，代码冗长且起名困难。
2.  **供应商锁定**：SQL语句中常包含特定平台的语法（如`parquet.`file），可移植性差。
3.  **缺乏关键控制**：SQL没有原生语法来控制持久化（缓存中间结果以避免重复计算）或广播变量等优化手段。
4.  **逻辑拆分**：为了实现持久化等优化，常常需要将一个完整的逻辑单元拆分成多个SQL语句执行，降低了代码的可读性和可维护性。
5.  **开发迭代慢**：处理大数据时，每次修改SQL查询都可能需要从头重新执行所有子查询，开发试错成本高。
6.  **表达能力有限**：对于复杂的逐组处理（`groupby-apply`）或改变数据形状的转换，纯SQL表达起来非常繁琐甚至无法实现。

---

## Python与Pandas扩展方法比较：3：Fugue解决方案

在了解了传统方法的不足后，本节我们来看看Fugue如何作为一个统一的抽象层，提供更简单、直观且高性能的扩展方案。

Fugue的核心思想是：**让用户用自己最熟悉的语法（Python原生函数、Pandas或SQL）描述计算逻辑，然后由Fugue负责将其移植到不同的分布式计算引擎（Spark、Dask）上执行**。它旨在降低维护成本，加快大数据项目的迭代速度。

### 基本使用示例

假设我们有一个简单的映射操作，用Pandas实现如下：

```python
import pandas as pd

input_df = pd.DataFrame({"id": [0, 1, 2], "value": ["apple", "banana", "cherry"]})
map_dict = {"apple": "fruit", "banana": "fruit", "cherry": "berry"}

# Pandas实现
def map_to_food(df: pd.DataFrame) -> pd.DataFrame:
    df["food"] = df["value"].map(map_dict)
    return df

result_pandas = map_to_food(input_df.copy())
```

如果要将此逻辑迁移到Spark，通常需要重写代码。而使用Fugue，只需将函数封装为一个“转换”：

```python
from fugue import transform
from pyspark.sql import SparkSession

# 同样的函数，无需修改
def map_to_food(df: pd.DataFrame) -> pd.DataFrame:
    df["food"] = df["value"].map(map_dict)
    return df

# 在Pandas上运行
result_local = transform(input_df, map_to_food, schema="*, food:str")
print(result_local)

# 在Spark上运行，只需指定引擎
spark_session = SparkSession.builder.getOrCreate()
result_spark = transform(input_df, map_to_food, schema="*, food:str", engine=spark_session)
result_spark.show()
```

**关键点**：`transform`函数、用户定义的逻辑函数、输出模式`schema`。通过切换`engine`参数，同一份逻辑可以在不同后端执行。

### 灵活的函数定义

Fugue不仅支持Pandas函数，也支持纯Python函数，使其更加灵活：

```python
# 方式1: 输入输出都是Pandas DataFrame
def map_to_food_pd(df: pd.DataFrame) -> pd.DataFrame:
    df["food"] = df["value"].map(map_dict)
    return df

# 方式2: 输入输出都是Python列表
def map_to_food_py(rows: List[List[Any]]) -> List[List[Any]]:
    for row in rows:
        row.append(map_dict[row[1]])  # 假设结构是 [id, value]
    return rows

# 两种函数都可以通过 `transform` 在Pandas或Spark上执行
```

### 增强的SQL与Python集成

Fugue提供了增强的SQL接口（FugueSQL），解决了传统SQL的诸多痛点：

1.  **简化语法**：无需强制使用CTE和层层嵌套。
2.  **避免供应商锁定**：使用`LOAD`等关键字，Fugue会适配到当前引擎。
3.  **内置优化控制**：直接使用`PERSIST`关键字来缓存中间结果，无需拆分查询。
4.  **无缝集成Python**：在SQL中可以直接调用Python函数处理数据，特别适合复杂的分组转换或UDF。

**FugueSQL示例对比**：
```sql
-- 传统Spark SQL (冗长，需要CTE)
WITH step1 AS (SELECT ... FROM ...),
     step2 AS (SELECT ... FROM step1 ...)
SELECT ... FROM step2 ...;

-- FugueSQL (更简洁，支持PERSIST)
result = SELECT ... FROM df TRANSFORM USING python_func PERSIST;
```
通过`TRANSFORM USING`子句，可以将数据传递给一个Python函数进行处理，结合了SQL的声明性和Python的灵活性。

---

## Python与Pandas扩展方法比较：4：总结

本节课中我们一起学习了扩展Python和Pandas代码的不同路径及其挑战。

我们首先认识到，由于Pandas的单机与内存限制，迈向分布式计算是处理更大规模数据的必然选择。然而，直接使用分布式框架学习曲线陡峭。

接着，我们分析了两种常见的迁移方案：
*   **类Pandas语义层**（如Modin）：虽然降低了入门门槛，但由于Pandas与分布式系统底层原理的差异，导致接口不一致、性能不可预测，最终可能仍需编写后端特定的优化代码，造成“供应商锁定”。
*   **类SQL语义层**：虽然强大，但语法冗长、缺乏对持久化等优化的直接控制、开发迭代慢，并且难以表达复杂的非标量转换。

最后，我们介绍了**Fugue**作为解决方案。Fugue作为一个抽象层，允许用户用原生Python、Pandas或增强的SQL来描述逻辑，然后统一执行在Pandas、Spark或Dask等引擎上。它通过提供一致的接口和关键优化控制（如`PERSIST`），在保持代码简洁和直观的同时，让用户能遵循分布式计算的最佳实践，从而降低迁移成本，提升开发效率和运行时性能。

![](img/7a0a16a9552ae890dfb1d9cc57f2ba2c_4.png)

从本地计算到分布式计算的过渡，就像从整数到实数的扩展，需要学习和思维方式的转变。Fugue的目标不是提供魔法，而是让这个转变过程更加平滑和可控。