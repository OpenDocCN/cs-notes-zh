# Python 51：导入语句 📦

在本节课中，我们将学习如何使用Python的`import`语句来访问不同目录下的模块。你将了解模块、包的基本概念，以及如何从Python包索引（PyPI）安装和使用第三方包。

---

## 什么是模块？

每一个Python文件（即扩展名为`.py`的文件）都可以被视为一个**模块**。你正在编写的代码文件通常被称为**主模块**。例如，当前目录下的`check_imports.py`文件就是一个主模块。

你可以导入当前工作目录（即项目作用域）内的任何Python文件。导入时，使用`import`关键字，后跟文件名（不带`.py`扩展名）。

```python
import sample
```

执行上述代码，如果导入成功，终端不会报错。但如果你尝试导入一个非Python文件（例如`.txt`文件），系统会返回错误。

```python
import sample_text  # 这将导致 ModuleNotFoundError
```

![](img/0afcf2f8e322cd23d5309c7df4e5bb01_1.png)

---

## 内置模块与标准库

Python自带了一系列标准模块，称为**内置模块**。这些模块已直接集成在Python解释器中，无需单独安装。例如，`json`模块就是一个内置模块。

```python
import json
```

![](img/0afcf2f8e322cd23d5309c7df4e5bb01_3.png)

导入后，你就可以直接使用该模块提供的函数了。所有内置模块的列表可以在[Python标准库文档](https://docs.python.org/3/library/)中找到。

---

## 包与PyPI

**包**可以被看作是Python模块的集合。为了让Python将一个目录识别为包，该目录下必须包含一个名为`__init__.py`的特殊文件。

![](img/0afcf2f8e322cd23d5309c7df4e5bb01_5.png)

Python拥有一个由社区构建的庞大包生态系统，这些包托管在**Python包索引（PyPI）**上。

![](img/0afcf2f8e322cd23d5309c7df4e5bb01_7.png)

**Pip**（或`pip3`）是Python默认的包安装工具，用于从PyPI安装包。

```bash
pip install package_name
```

例如，如果你已经通过Pip安装了`numpy`，就可以直接在Python中导入它：

```python
import numpy
```

如果尝试导入一个未安装的包（例如`seaborn`），则会收到`ModuleNotFoundError`错误。此时，你需要先在终端中运行`pip install seaborn`来安装它。

---

## 导入其他目录中的模块

有时，你可能需要导入位于当前工作目录子文件夹中的模块。这需要修改Python的模块搜索路径。

假设你有一个名为`workplace`的文件夹，里面包含一个`trial.py`文件，该文件定义了一个列表变量`names`。

以下是导入该文件的步骤：

1.  导入`sys`模块，它提供了对Python解释器系统功能的访问。
2.  使用`sys.path.insert()`方法，将目标目录的路径添加到模块搜索路径的开头。
3.  然后，就可以像导入普通模块一样导入目标文件了。

```python
import sys

# 将 'workplace' 文件夹的路径插入到模块搜索路径中
sys.path.insert(0, r'你的/workplace/文件夹/绝对路径')

import trial

# 访问 trial.py 中定义的变量
print(trial.names)
```

**注意**：在传递路径字符串时，前面的`r`表示“原始字符串”，可以避免反斜杠`\`被误解为转义字符。虽然IDE可能会在`import trial`处显示警告（因为它不知道你动态添加的路径），但解释器在执行时能够正确识别。

---

## 总结

本节课我们一起学习了Python中`import`语句的核心用法。

我们了解到，每个`.py`文件都是一个**模块**，而**包**是模块的集合。Python的**内置模块**无需安装即可使用，而丰富的第三方包可以通过**Pip**从**PyPI**安装。

![](img/0afcf2f8e322cd23d5309c7df4e5bb01_9.png)

对于导入其他目录的模块，我们学习了通过修改`sys.path`来实现的方法，虽然这有时会比较具体和复杂。对于初学者，更重要的实践是将所需文件放在当前工作目录下进行导入。但了解从其他目录导入模块作为一种可选方案，也是很有益的。

![](img/0afcf2f8e322cd23d5309c7df4e5bb01_10.png)

![](img/0afcf2f8e322cd23d5309c7df4e5bb01_11.png)

掌握模块和包的导入，是组织和管理更大型Python项目代码的基础。