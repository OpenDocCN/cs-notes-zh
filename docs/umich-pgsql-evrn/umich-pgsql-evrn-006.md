# 006：使用DBeaver客户端执行SQL命令

## 概述
在本节课程中，我们将学习如何使用DBeaver桌面客户端来连接PostgreSQL数据库并执行SQL命令。我们将从建立数据库连接开始，逐步演示如何创建表格、执行脚本以及验证操作结果。通过本教程，你将掌握使用图形化界面工具管理数据库的基本方法。

## 建立数据库连接

上一节我们介绍了多种连接PostgreSQL的方式，本节中我们来看看如何使用DBeaver这一图形化客户端。

DBeaver是一款免费开源的数据库管理工具，它支持包括PostgreSQL在内的多种数据库系统。与某些工具不同，DBeaver在连接资源有限的数据库时表现稳定。

以下是建立连接的步骤：

1.  打开DBeaver，点击“新建连接”按钮。
2.  从数据库列表中选择“PostgreSQL”。
3.  在连接设置界面中，填写必要的连接信息。

连接信息通常来自你的作业或数据库提供方。例如，在本例中：
*   **主机**：`pg.pg4e.com`
*   **数据库**：`pg4e_debug`
*   **用户**：`pg4e_debug`
*   **密码**：需要从作业中复制并粘贴

填写完毕后，点击“测试连接”以确保配置正确，然后完成连接创建。至此，我们便建立了一个可以通过图形界面发送SQL命令的客户端通道。

## 执行SQL命令与创建表格

成功连接数据库后，我们来看看如何在DBeaver中执行SQL语句来操作数据库。

在DBeaver左侧的数据库导航器中，选中你刚建立的连接下的数据库（例如 `pg4e_debug`）。然后，点击工具栏上的“新建SQL脚本”按钮，这将打开一个用于编写和运行SQL命令的编辑器窗口。

我们需要根据作业要求执行创建表格的SQL语句。第一个任务是创建 `pg4e_debug` 表。

![](img/ad0115dc8c957af133f672de2b0d1f89_1.png)

在SQL编辑器中输入以下命令：
```sql
CREATE TABLE pg4e_debug (
  id SERIAL,
  query VARCHAR(4096),
  result VARCHAR(4096),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY(id)
);
```
输入完成后，点击工具栏上的“执行SQL语句”按钮（通常是一个播放图标）。执行成功后，界面下方会显示确认信息。

![](img/ad0115dc8c957af133f672de2b0d1f89_3.png)

为了验证表格是否创建成功，我们需要刷新数据库连接。在导航器中右键点击数据库连接，选择“刷新”。随后展开“架构” -> “public” -> “表”，你应该能看到新创建的 `pg4e_debug` 表。

接下来，我们执行第二个创建表格的命令。在SQL编辑器中输入以下语句以创建 `pg4e_result` 表：
```sql
CREATE TABLE pg4e_result (
  id SERIAL,
  query VARCHAR(4096),
  result VARCHAR(4096),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY(id)
);
```
再次点击“执行SQL语句”按钮。执行完毕后，同样地刷新数据库连接，你将在表列表中看到新增的 `pg4e_result` 表。

## 验证与总结

创建完所需的表格后，通常需要验证作业是否完成。根据课程设置，系统可能会自动检查数据库中的表结构。

此时，如果你再次刷新数据库连接，可能会发现系统自动创建了一个名为 `meta` 的表，这标志着自动评分系统已成功检测到你创建的表结构。

通过DBeaver这类图形化客户端，你可以方便地执行SQL、管理数据库对象。在课程中，你可以根据情况选择使用DBeaver、PSQL命令行或其他客户端来完成作业。掌握PSQL命令行工具同样重要，因为在服务器环境中通常需要通过命令行进行操作。而像DBeaver这样的高级客户端则能提供更直观便捷的管理体验。

![](img/ad0115dc8c957af133f672de2b0d1f89_5.png)

本节课中我们一起学习了如何使用DBeaver客户端连接PostgreSQL数据库、执行SQL命令创建表格，以及如何刷新和验证操作结果。