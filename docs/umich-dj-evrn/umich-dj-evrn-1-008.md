# 008：在PythonAnywhere上使用命令行Shell 🖥️

![](img/fea183fa5643c97927caeb145f0717b8_0.png)

![](img/fea183fa5643c97927caeb145f0717b8_1.png)

在本节课中，我们将学习如何在PythonAnywhere上使用命令行Shell。这是课程早期的作业之一，我们将逐步了解其基本操作。虽然现代用户界面通常是图形化的，但服务器环境大多使用命令行界面。理解命令行的工作原理对于Web开发至关重要。

## 为什么使用命令行？🤔

![](img/fea183fa5643c97927caeb145f0717b8_3.png)

你可能会问，为什么我们要使用这种看似过时的命令行界面？答案在于服务器环境。绝大多数服务器，尤其是运行Linux系统的服务器，都没有图形用户界面。它们使用命令行界面，通过文本提示符接收指令。因此，了解命令行操作是处理服务器和排查问题的基本技能。

![](img/fea183fa5643c97927caeb145f0717b8_5.png)

## 访问PythonAnywhere的Shell

![](img/fea183fa5643c97927caeb145f0717b8_7.png)

![](img/fea183fa5643c97927caeb145f0717b8_9.png)

![](img/fea183fa5643c97927caeb145f0717b8_10.png)

![](img/fea183fa5643c97927caeb145f0717b8_12.png)

![](img/fea183fa5643c97927caeb145f0717b8_13.png)

首先，登录到PythonAnywhere，进入“Consoles”标签页。在这里，你可以启动不同类型的控制台，例如交互式Python环境或MySQL Shell。对于本课程，我们主要使用Bash Shell。Bash是Linux系统中一种常见的Shell变体。

![](img/fea183fa5643c97927caeb145f0717b8_15.png)

![](img/fea183fa5643c97927caeb145f0717b8_17.png)

启动Bash Shell后，你会看到一个美元符号 `$` 提示符，这表示Shell正在等待输入。

![](img/fea183fa5643c97927caeb145f0717b8_19.png)

![](img/fea183fa5643c97927caeb145f0717b8_21.png)

## 基本Shell命令 📝

以下是几个常用的Shell命令，我们将逐一介绍。

![](img/fea183fa5643c97927caeb145f0717b8_23.png)

![](img/fea183fa5643c97927caeb145f0717b8_25.png)

### 1. 列出文件和目录
`ls` 命令用于列出当前工作目录中的文件和文件夹。
```bash
ls
```
使用 `ls -l` 可以显示详细信息，包括文件大小、修改日期和权限。
```bash
ls -l
```

![](img/fea183fa5643c97927caeb145f0717b8_27.png)

![](img/fea183fa5643c97927caeb145f0717b8_29.png)

![](img/fea183fa5643c97927caeb145f0717b8_31.png)

### 2. 显示当前目录
`pwd` 命令用于打印当前工作目录的完整路径。
```bash
pwd
```

![](img/fea183fa5643c97927caeb145f0717b8_33.png)

### 3. 切换目录
`cd` 命令用于切换目录。单独使用 `cd` 会返回你的主目录。
```bash
cd
```
要进入特定目录，可以输入路径。例如，进入名为“django_projects”的目录：
```bash
cd django_projects
```
使用 `cd ~` 可以快速返回主目录。
```bash
cd ~
```

### 4. 删除文件
`rm` 命令用于删除文件。请谨慎使用此命令，因为它会直接删除文件，而不是将其移至回收站。
```bash
rm db.zap
```

![](img/fea183fa5643c97927caeb145f0717b8_35.png)

![](img/fea183fa5643c97927caeb145f0717b8_37.png)

### 5. 搜索文件内容
`grep` 命令用于在文件中搜索特定字符串。使用 `-r` 参数可以递归搜索当前目录及其子目录中的所有文件。
```bash
grep -r "autos_create" *
```

![](img/fea183fa5643c97927caeb145f0717b8_39.png)

## 使用命令行技巧 💡

![](img/fea183fa5643c97927caeb145f0717b8_41.png)

掌握一些技巧可以提高命令行使用效率。

![](img/fea183fa5643c97927caeb145f0717b8_43.png)

![](img/fea183fa5643c97927caeb145f0717b8_45.png)

### 1. 命令自动补全
在输入文件名或目录名时，可以按 `Tab` 键自动补全。如果存在多个匹配项，按两次 `Tab` 键会显示所有选项。

### 2. 历史命令导航
使用上下箭头键可以浏览之前输入的命令。按 `Enter` 键可以重新执行选中的命令，这能节省大量时间。

![](img/fea183fa5643c97927caeb145f0717b8_47.png)

![](img/fea183fa5643c97927caeb145f0717b8_49.png)

## 识别不同的交互环境 🔍

![](img/fea183fa5643c97927caeb145f0717b8_51.png)

![](img/fea183fa5643c97927caeb145f0717b8_52.png)

在使用命令行时，你可能会遇到不同的提示符，这表示你正在与不同的程序交互。识别这些提示符很重要，以免输入错误的命令。

### 1. Python交互环境
输入 `python` 命令会进入Python交互环境，提示符变为 `>>>`。
```bash
python
```
在此环境中，你可以输入Python代码，但不能使用Shell命令。要退出Python环境，输入 `quit()`。
```python
quit()
```

![](img/fea183fa5643c97927caeb145f0717b8_54.png)

![](img/fea183fa5643c97927caeb145f0717b8_56.png)

### 2. SQLite交互环境
输入 `sqlite3` 命令并指定数据库文件会进入SQLite交互环境，提示符变为 `sqlite>`。
```bash
sqlite3 db.sqlite3
```
在此环境中，你可以执行SQL命令。SQL命令必须以分号 `;` 结尾。要退出SQLite环境，输入 `.quit`。
```sql
.quit
```

![](img/fea183fa5643c97927caeb145f0717b8_58.png)

### 3. Django Shell
在Django项目目录中，输入以下命令可以进入Django Shell：
```bash
python manage.py shell
```
Django Shell看起来像Python交互环境，但它预加载了Django应用程序的所有代码。你可以在此执行Django特定的操作。要退出Django Shell，同样使用 `quit()`。

![](img/fea183fa5643c97927caeb145f0717b8_60.png)

![](img/fea183fa5643c97927caeb145f0717b8_62.png)

![](img/fea183fa5643c97927caeb145f0717b8_64.png)

## 总结 📚

![](img/fea183fa5643c97927caeb145f0717b8_66.png)

![](img/fea183fa5643c97927caeb145f0717b8_68.png)

本节课我们一起学习了在PythonAnywhere上使用命令行Shell的基本操作。我们介绍了几个常用的Shell命令，如 `ls`、`pwd`、`cd`、`rm` 和 `grep`，并掌握了一些提高效率的技巧，如命令自动补全和历史命令导航。此外，我们还学习了如何识别和退出不同的交互环境，包括Python、SQLite和Django Shell。理解这些内容将帮助你在服务器环境中更有效地工作。