# 102：编程演示-打开读取并追加到新文件 📂

在本节课中，我们将学习如何编写一个Python函数。这个函数会打开并读取一个文件的内容，将其中的文本行顺序反转，然后将反转后的内容追加到另一个文件中。

![](img/24c0ab2c29a9ec9a051af534a2f77e25_1.png)

## 概述

我们将创建一个名为 `open_read_append_new_file` 的函数。该函数接收两个参数：一个用于读取的源文件路径和一个用于写入（追加）的目标文件路径。函数的核心任务是读取源文件的所有行，反转这些行的顺序，然后将反转后的行追加到目标文件的末尾。

## 函数定义与逻辑

首先，我们来定义这个函数。以下是函数的基本框架和逻辑步骤：

```python
def open_read_append_new_file(file_to_read, file_to_write):
    # 函数逻辑将在这里实现
```

上一节我们介绍了函数的目标，本节中我们来看看如何一步步实现它。以下是实现该功能的具体步骤：

1.  **打开并读取源文件**：使用 `with` 语句以读取模式打开第一个文件，并将其所有行读入一个列表。
2.  **反转列表顺序**：对包含文件行的列表调用 `.reverse()` 方法。
3.  **打开并写入目标文件**：使用 `with` 语句以追加模式打开第二个文件，并将反转后的列表写入该文件。
4.  **自动关闭文件**：利用 `with` 语句的特性，文件会在代码块执行完毕后自动关闭，无需手动调用 `.close()` 方法。

## 代码实现详解

现在，让我们将上述步骤转化为完整的Python代码。

![](img/24c0ab2c29a9ec9a051af534a2f77e25_3.png)

```python
def open_read_append_new_file(file_to_read, file_to_write):
    # 步骤1：打开并读取源文件
    with open(file_to_read, 'r') as fin:
        lines_list = fin.readlines()

    # 步骤2：反转列表顺序
    lines_list.reverse()

    # 步骤3：打开并追加到目标文件
    with open(file_to_write, 'a') as fout:
        fout.writelines(lines_list)
```

![](img/24c0ab2c29a9ec9a051af534a2f77e25_4.png)

代码解释：
*   `with open(file_to_read, 'r') as fin:`：这行代码使用 `with` 上下文管理器打开 `file_to_read` 指定的文件。模式 `'r'` 表示读取。文件对象被赋值给变量 `fin`。`with` 语句确保文件在代码块结束后会被正确关闭。
*   `lines_list = fin.readlines()`：`readlines()` 方法读取文件的所有行，并将每一行作为一个字符串元素，返回一个列表。这个列表被存储在变量 `lines_list` 中。
*   `lines_list.reverse()`：这是列表对象的一个方法，它会**原地**反转列表中元素的顺序。执行后，`lines_list` 中的第一行变成最后一行，最后一行变成第一行。
*   `with open(file_to_write, 'a') as fout:`：同样使用 `with` 语句打开 `file_to_write` 指定的文件。模式 `'a'` 表示追加。如果文件不存在，Python会自动创建它。文件对象被赋值给变量 `fout`。
*   `fout.writelines(lines_list)`：`writelines()` 方法接收一个字符串列表作为参数，并将列表中的所有字符串写入文件。由于我们是以追加模式打开的，新内容会被添加到文件原有内容的末尾。

## 调用函数

![](img/24c0ab2c29a9ec9a051af534a2f77e25_6.png)

![](img/24c0ab2c29a9ec9a051af534a2f77e25_7.png)

函数定义好后，我们需要从程序的主入口（例如 `main` 函数或脚本的顶层代码）调用它。

假设我们有一个名为 `news.txt` 的源文件，并希望将反转后的内容输出到 `news_out.txt` 文件。

```python
# 调用我们定义的函数
open_read_append_new_file('news.txt', 'news_out.txt')
```

运行这段程序后，你会在当前目录下发现一个新文件 `news_out.txt`。打开它，你会看到其内容正是 `news.txt` 中所有行的反向排列。

## 总结

本节课中我们一起学习了如何操作文件。我们创建了一个 `open_read_append_new_file` 函数，它完整演示了文件的读取、数据处理（反转行顺序）和写入（追加）的流程。关键点在于：
1.  使用 `with open(...) as ...:` 语句可以安全、自动地管理文件对象的打开和关闭。
2.  `readlines()` 方法用于将文件所有行读入列表。
3.  列表的 `.reverse()` 方法用于反转列表元素顺序。
4.  使用 `'a'`（追加）模式打开文件进行写入，如果文件不存在则会自动创建。
5.  `writelines()` 方法用于将一个字符串列表写入文件。

![](img/24c0ab2c29a9ec9a051af534a2f77e25_9.png)

通过这个练习，你掌握了Python中进行基础文件I/O操作的核心方法。