# PostgreSQL for Everybody：P5：使用PythonAnywhere运行SQL 🚀

在本节课中，我们将学习如何利用PythonAnywhere提供的免费Linux Shell，通过PSQL命令行工具来完成所有课程作业。你将学会如何连接数据库、执行SQL命令以及管理文件。

---

## 概述

PythonAnywhere提供了一个免费的Linux环境，我们可以在此环境中使用PostgreSQL命令行客户端（PSQL）来操作数据库。本节将引导你完成从登录到执行SQL查询的完整流程。

![](img/4c3be4deefb70fad7e18fbe5c4b8c3ad_1.png)

## 注册与登录

首先，你需要访问PythonAnywhere并创建一个免费账户。该账户在持续使用的情况下将保持免费。登录后，系统会为你提供一个数据库，并显示连接所需的信息，包括主机、端口、数据库名、用户名和密码。

## 访问控制台与文件管理

登录PythonAnywhere后，进入控制台界面启动一个Bash控制台。以下是一些基本的Linux命令，用于在环境中导航和管理文件：

*   `pwd`：显示当前工作目录。
*   `ls`：列出当前目录下的文件和文件夹。
*   `cd [目录名]`：切换目录。使用 `cd ~` 可以快速返回用户主目录。
*   `cat [文件名]`：显示文件内容。
*   `clear`：清空当前终端屏幕。

![](img/4c3be4deefb70fad7e18fbe5c4b8c3ad_3.png)

你还可以使用文本编辑器来编写和保存SQL脚本文件，这对于需要反复执行的复杂查询非常有用。

![](img/4c3be4deefb70fad7e18fbe5c4b8c3ad_5.png)

## 连接PostgreSQL数据库

在控制台中，使用课程提供的PSQL命令格式来连接你的数据库。命令通常如下所示：

![](img/4c3be4deefb70fad7e18fbe5c4b8c3ad_7.png)

```bash
psql -h [主机地址] -p [端口] -d [数据库名] -U [用户名]
```

![](img/4c3be4deefb70fad7e18fbe5c4b8c3ad_9.png)

![](img/4c3be4deefb70fad7e18fbe5c4b8c3ad_11.png)

执行命令后，系统会提示你输入密码。连接成功后，你将进入PSQL命令行界面。

## 执行SQL与PSQL命令

![](img/4c3be4deefb70fad7e18fbe5c4b8c3ad_13.png)

在PSQL命令行中，你可以执行两种类型的命令：

1.  **SQL命令**：用于操作数据库的标准查询语言，例如 `SELECT * FROM table_name;`。每条SQL语句需以分号 `;` 结尾。
2.  **PSQL元命令**：以反斜杠 `\` 开头的命令，用于管理客户端本身。例如：
    *   `\dt`：列出当前数据库中的所有表。
    *   `\i [文件名]`：执行指定文件中的SQL命令。
    *   `\q`：退出PSQL，返回Linux Shell。

## 退出与资源管理

完成数据库操作后，使用 `\q` 命令退出PSQL。若要关闭整个Bash控制台以释放资源，可以在控制台内输入 `exit` 或按下 `Ctrl+D` 组合键。

---

![](img/4c3be4deefb70fad7e18fbe5c4b8c3ad_15.png)

![](img/4c3be4deefb70fad7e18fbe5c4b8c3ad_16.png)

![](img/4c3be4deefb70fad7e18fbe5c4b8c3ad_17.png)

![](img/4c3be4deefb70fad7e18fbe5c4b8c3ad_19.png)

## 总结

![](img/4c3be4deefb70fad7e18fbe5c4b8c3ad_21.png)

![](img/4c3be4deefb70fad7e18fbe5c4b8c3ad_23.png)

本节课我们一起学习了如何在PythonAnywhere的免费环境中运行PostgreSQL。我们了解了如何访问Linux控制台、管理文件、使用PSQL命令连接数据库，并执行基本的SQL查询和客户端管理命令。掌握这些技能将为后续的数据库学习和作业完成打下坚实基础。