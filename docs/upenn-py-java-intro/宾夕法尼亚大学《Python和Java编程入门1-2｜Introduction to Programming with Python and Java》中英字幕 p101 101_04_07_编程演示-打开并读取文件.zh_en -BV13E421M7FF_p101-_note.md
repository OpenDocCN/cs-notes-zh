# Python和Java编程入门1-2：101：编程演示-打开并读取文件 📂

在本节课中，我们将学习如何编写一个Python函数来打开、读取并打印文本文件的内容。我们将通过一个具体的编程演示，逐步讲解文件操作的核心步骤。

## 概述

![](img/28bf1053f8034d8d2b01ae4a918c3c83_1.png)

我们将创建一个名为 `open_read_file` 的函数。该函数接收一个文件名作为参数，执行以下操作：以读取模式打开文件，逐行读取内容并打印到控制台，同时统计文件的总行数，最后安全地关闭文件。通过这个练习，你将掌握Python中处理文件的基本方法。

## 函数定义与文件打开

首先，我们定义 `open_read_file` 函数。它使用Python内置的 `open()` 函数来打开指定的文件。

```python
def open_read_file(filename):
    f = open(filename, 'r')
```

在这里，`open(filename, 'r')` 是关键。`filename` 是我们要打开的文件名，`'r'` 参数表示以“读取”模式打开。这个操作会返回一个文件流对象，我们将其赋值给变量 `f`。

为了确认文件已成功打开并查看流对象的类型，我们可以添加一行打印语句：

```python
    print(type(f))
```

## 逐行读取与内容处理

成功打开文件后，下一步是读取其中的内容。我们将使用一个循环来逐行读取文件。

以下是实现这一过程的核心代码逻辑：

1.  初始化一个计数器 `count` 为0，用于统计行数。
2.  使用 `f.readline()` 方法读取第一行。
3.  进入一个 `while` 循环，只要读取到的行不是空字符串（表示文件末尾），就继续执行。
4.  在循环体内，打印当前行，然后读取下一行，并将计数器加1。

对应的代码如下：

![](img/28bf1053f8034d8d2b01ae4a918c3c83_3.png)

```python
    count = 0
    line = f.readline()
    while line:
        print(line)
        line = f.readline()
        count += 1
```

![](img/28bf1053f8034d8d2b01ae4a918c3c83_5.png)

循环结束后，我们打印出文件的总行数。

```python
    print(f"There are {count} lines in the file.")
```

## 关闭文件与程序执行

文件操作完成后，非常重要的一步是关闭文件，以释放系统资源。这通过文件流对象的 `.close()` 方法实现。

```python
    f.close()
```

为了运行这个函数，我们定义一个 `main` 函数来调用它，并传入一个位于同一目录下的文件名（例如 `news.txt`）。

```python
def main():
    open_read_file('news.txt')

if __name__ == "__main__":
    main()
```

![](img/28bf1053f8034d8d2b01ae4a918c3c83_7.png)

运行程序后，控制台将依次输出：
1.  文件流对象的类型（例如 `<class ‘_io.TextIOWrapper’>`）。
2.  文件 `news.txt` 的每一行内容。
3.  文件的总行数统计（例如 “There are 10 lines in the file.”）。

![](img/28bf1053f8034d8d2b01ae4a918c3c83_9.png)

## 总结

![](img/28bf1053f8034d8d2b01ae4a918c3c83_10.png)

本节课我们一起学习了Python中基本的文件操作。我们创建了一个完整的函数，演示了如何安全地**打开**文件、**读取**其内容、**处理**数据（打印和计数）以及最终**关闭**文件。理解并掌握 `open()`、`readline()` 和 `close()` 这些方法是进行任何文件处理任务的基础。