# PostgreSQL for Everybody：17：Python连接PostgreSQL基础演示 🐍➡️🗄️

在本节课中，我们将学习如何使用Python连接到PostgreSQL数据库，并执行基本的SQL操作，包括创建表、插入数据和查询数据。

## 概述

我们将通过一个名为 `simple.py` 的示例程序，演示Python与PostgreSQL交互的核心步骤。这包括建立连接、创建游标、执行SQL命令以及处理结果集。

![](img/e26e6e3968a2a00d3bd26a927515c88e_1.png)

## 准备工作

![](img/e26e6e3968a2a00d3bd26a927515c88e_3.png)

在开始编写代码之前，需要确保环境已准备就绪。以下是需要完成的步骤。

![](img/e26e6e3968a2a00d3bd26a927515c88e_4.png)

![](img/e26e6e3968a2a00d3bd26a927515c88e_6.png)

![](img/e26e6e3968a2a00d3bd26a927515c88e_8.png)

### 清理现有数据库表

![](img/e26e6e3968a2a00d3bd26a927515c88e_10.png)

首先，建议清理可能存在的旧表，以确保演示从一个干净的状态开始。可以在 `psql` 命令行中执行以下命令：

![](img/e26e6e3968a2a00d3bd26a927515c88e_12.png)

![](img/e26e6e3968a2a00d3bd26a927515c88e_14.png)

```sql
DROP TABLE IF EXISTS docs_stem CASCADE;
DROP TABLE IF EXISTS stop_words CASCADE;
DROP TABLE IF EXISTS python_fun CASCADE;
```

执行后，使用 `\dt` 命令确认只剩下 `pg4e_debug`、`pg4e_meta` 和 `pg4e_result` 这三个由自动评分器使用的表。

### 安装Python数据库连接器

![](img/e26e6e3968a2a00d3bd26a927515c88e_16.png)

![](img/e26e6e3968a2a00d3bd26a927515c88e_17.png)

Python需要通过 `psycopg2` 库来连接PostgreSQL。首先检查是否已安装：

![](img/e26e6e3968a2a00d3bd26a927515c88e_19.png)

![](img/e26e6e3968a2a00d3bd26a927515c88e_20.png)

```python
import psycopg2
```

如果导入失败，则需要使用pip安装：

```bash
pip3 install psycopg2
```

![](img/e26e6e3968a2a00d3bd26a927515c88e_22.png)

![](img/e26e6e3968a2a00d3bd26a927515c88e_24.png)

### 获取示例代码

![](img/e26e6e3968a2a00d3bd26a927515c88e_26.png)

![](img/e26e6e3968a2a00d3bd26a927515c88e_27.png)

示例代码可以从课程网站获取。我们将使用两个关键文件：
1.  `simple.py`：主程序文件。
2.  `hidden.py`：存储数据库连接机密信息的文件（如主机、用户名、密码）。

![](img/e26e6e3968a2a00d3bd26a927515c88e_29.png)

使用以下命令下载 `simple.py`：

```bash
wget https://www.pg4e.com/code/simple.py
```

`hidden.py` 文件需要根据你的数据库连接信息自行创建。课程提供了一个模板文件 `hidden_dist.py`，你可以将其复制并修改为 `hidden.py`，填入真实的连接参数。

![](img/e26e6e3968a2a00d3bd26a927515c88e_31.png)

## 代码解析：simple.py

现在，让我们深入分析 `simple.py` 文件，理解每一部分的作用。

### 1. 导入模块与建立连接

![](img/e26e6e3968a2a00d3bd26a927515c88e_33.png)

程序首先导入 `psycopg2` 和包含连接信息的 `hidden` 模块。

```python
import psycopg2
import hidden
```

![](img/e26e6e3968a2a00d3bd26a927515c88e_35.png)

![](img/e26e6e3968a2a00d3bd26a927515c88e_37.png)

接着，从 `hidden` 模块读取连接秘密，并使用 `psycopg2.connect()` 函数建立数据库连接。连接参数包括主机、数据库名、用户名和密码。

```python
secrets = hidden.secrets()
conn = psycopg2.connect(
    host=secrets['host'],
    port=secrets['port'],
    database=secrets['database'],
    user=secrets['user'],
    password=secrets['pass'],
    connect_timeout=3
)
```

![](img/e26e6e3968a2a00d3bd26a927515c88e_39.png)

### 2. 创建游标

与数据库的所有交互都通过游标（cursor）对象进行。游标类似于一个指向数据库的“指针”，用于发送SQL命令和获取结果。

```python
cur = conn.cursor()
```

### 3. 执行SQL命令：创建表

我们通过游标的 `.execute()` 方法发送SQL命令。以下代码先删除已存在的 `python_fun` 表，然后创建一个新表。

```python
sql = 'DROP TABLE IF EXISTS python_fun CASCADE;'
print(sql)
cur.execute(sql)

sql = 'CREATE TABLE python_fun (id SERIAL, line TEXT);'
print(sql)
cur.execute(sql)
```

执行创建或修改数据的SQL后，需要调用 `conn.commit()` 来确保更改被永久写入数据库。在此之前，更改可能仅存在于缓存中。

```python
conn.commit()
```

### 4. 执行SQL命令：插入数据

![](img/e26e6e3968a2a00d3bd26a927515c88e_41.png)

![](img/e26e6e3968a2a00d3bd26a927515c88e_42.png)

插入数据时，我们使用参数化查询来防止SQL注入攻击。SQL语句中的 `%s` 是占位符，实际值通过一个元组传递给 `.execute()` 方法。

```python
for i in range(10):
    txt = f"第 {i} 行数据"
    sql = 'INSERT INTO python_fun (line) VALUES (%s);'
    cur.execute(sql, (txt, )) # 注意单个元素的元组需要加逗号
conn.commit()
```

### 5. 执行SQL命令：查询数据

![](img/e26e6e3968a2a00d3bd26a927515c88e_44.png)

查询数据也使用 `.execute()` 方法。执行后，可以使用游标的 `.fetchone()` 方法获取一行结果，或使用 `.fetchall()` 获取所有结果。

```python
sql = 'SELECT id, line FROM python_fun WHERE id = 5;'
print(sql)
cur.execute(sql)
row = cur.fetchone()
if row is None:
    print('未找到数据')
else:
    print('找到行：', row)
```

![](img/e26e6e3968a2a00d3bd26a927515c88e_46.png)

`.fetchone()` 返回的是一个元组，其元素对应查询语句中的列。

### 6. 获取插入数据的ID（SERIAL类型）

当向具有 `SERIAL` 自增列的表插入数据时，可以使用 `RETURNING` 子句立即获取生成的主键ID。

![](img/e26e6e3968a2a00d3bd26a927515c88e_48.png)

```python
txt = "新插入的文本"
sql = 'INSERT INTO python_fun (line) VALUES (%s) RETURNING id;'
cur.execute(sql, (txt, ))
row = cur.fetchone()
id = row[0]
print('新记录的ID是：', id)
# 注意：这里还没有执行 conn.commit()
```

### 7. 错误处理与资源清理

如果SQL语句存在语法错误，`.execute()` 方法会抛出异常。良好的实践是在 `finally` 块中关闭游标和连接，以确保资源被释放。

```python
try:
    # ... 执行各种SQL操作 ...
    conn.commit()
except Exception as e:
    print('发生错误：', e)
    conn.rollback() # 回滚未提交的事务
finally:
    if cur is not None:
        cur.close()
    if conn is not None:
        conn.close()
```

![](img/e26e6e3968a2a00d3bd26a927515c88e_50.png)

![](img/e26e6e3968a2a00d3bd26a927515c88e_51.png)

在示例中，程序最后故意执行了一条错误的SQL来演示异常情况。

![](img/e26e6e3968a2a00d3bd26a927515c88e_52.png)

![](img/e26e6e3968a2a00d3bd26a927515c88e_54.png)

```python
sql = "这是一个错误的SQL语句；"
cur.execute(sql) # 这里会抛出异常
conn.commit() # 由于异常，这行不会执行
```

![](img/e26e6e3968a2a00d3bd26a927515c88e_56.png)

## 核心概念总结

![](img/e26e6e3968a2a00d3bd26a927515c88e_57.png)

![](img/e26e6e3968a2a00d3bd26a927515c88e_58.png)

![](img/e26e6e3968a2a00d3bd26a927515c88e_60.png)

上一节我们逐步解析了代码，本节中我们来总结与Python操作PostgreSQL相关的几个核心概念。

以下是关键操作的模式：

![](img/e26e6e3968a2a00d3bd26a927515c88e_62.png)

![](img/e26e6e3968a2a00d3bd26a927515c88e_64.png)

*   **连接数据库**：使用 `psycopg2.connect()` 并提供连接参数。
*   **创建游标**：通过 `conn.cursor()` 获取操作句柄。
*   **执行命令**：使用 `cur.execute(sql, params)` 发送SQL。增删改操作后通常需要 `conn.commit()`。
*   **查询数据**：使用 `cur.execute()` 执行查询，然后通过 `cur.fetchone()` 或 `cur.fetchall()` 获取结果。
*   **事务管理**：`commit()` 提交事务，`rollback()` 回滚事务。未提交的更改在程序崩溃或连接关闭时可能会丢失。
*   **资源清理**：始终在最后关闭游标 (`cur.close()`) 和连接 (`conn.close()`)。

## 注意事项

在运行程序时，可以同时在另一个 `psql` 会话中观察数据库的变化。但需要注意 **事务的可见性**：在Python程序中，除非执行了 `conn.commit()`，否则插入或更新的数据可能不会立即在其他数据库会话中可见。这就是为什么示例中最后一条插入的数据（ID为11）在程序因错误而未能提交时，没有真正保存到数据库中的原因。

## 总结

![](img/e26e6e3968a2a00d3bd26a927515c88e_66.png)

![](img/e26e6e3968a2a00d3bd26a927515c88e_68.png)

本节课中我们一起学习了使用Python连接和操作PostgreSQL数据库的基础知识。我们掌握了如何安装 `psycopg2` 库、建立连接、使用游标执行SQL命令、进行参数化查询以提升安全性，以及管理事务和清理资源。理解 `commit()` 的时机对于保证数据一致性至关重要。这些基础操作为后续进行更复杂的数据处理和应用开发打下了坚实的基础。