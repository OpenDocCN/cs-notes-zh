# Python导入系统：P84：接入导入系统 🐍

![](img/b0ec26acaf9d7147d5b6c6e702b6b378_1.png)

在本节课中，我们将学习Python的导入系统，并了解如何通过自定义导入钩子来解决实际问题。我们将从导入系统的基本原理开始，逐步深入到如何实现自定义的查找器和加载器，例如创建模块阻止列表或从数据库加载代码。

![](img/b0ec26acaf9d7147d5b6c6e702b6b378_3.png)

## 导入系统概述

Python的导入过程主要分为两个步骤：**查找**和**加载**。查找负责定位模块的源代码，加载则负责执行代码并将其变为可用的模块对象。

## 标准导入机制

默认情况下，Python提供了三种查找器：
1.  **内置导入器**：用于查找像`os`或`sys`这样的内置模块。
2.  **冻结导入器**：用于引导解释器自身的导入过程。
3.  **路径查找器**：这是最常用的查找器，负责在文件系统路径中查找`.py`文件。

查找器列表存储在`sys.meta_path`中。当执行`import`语句时，Python会按顺序遍历这个列表，调用每个查找器的`find_spec`方法，直到有一个返回模块规格（`ModuleSpec`）。如果所有查找器都返回`None`，则会引发`ModuleNotFoundError`。

找到模块规格后，加载过程开始。这包括：
1.  **创建模块**：根据规格创建一个空的模块对象。
2.  **执行模块**：执行模块中的代码，将其内容填充到模块对象的命名空间（`__dict__`）中。

加载后的模块会被缓存到`sys.modules`字典中，后续的导入会直接从这里获取，避免重复加载。

## 自定义导入钩子

Python允许我们通过实现自己的查找器和加载器来介入导入过程，从而实现特殊功能。

### 示例一：跟踪查找器

首先，我们来看一个简单的自定义查找器，它会在每次导入发生时打印日志。

以下是实现一个跟踪查找器的步骤：

1.  **定义查找器类**：继承自`importlib.abc.MetaPathFinder`。
2.  **实现`find_spec`方法**：该方法接收模块名、路径等参数。在此方法中打印日志，并返回`None`以表示不处理此模块，让其他查找器继续。
3.  **插入查找器**：将自定义查找器插入到`sys.meta_path`列表的开头，以确保它最先被调用。

```python
import sys
import importlib.abc

class TracingFinder(importlib.abc.MetaPathFinder):
    def find_spec(self, fullname, path=None, target=None):
        print(f"查找器正在尝试导入: {fullname}, 路径: {path}")
        return None  # 不处理，交由其他查找器

# 将自定义查找器插入到查找器列表的最前面
sys.meta_path.insert(0, TracingFinder())

# 现在执行任何导入都会触发打印
import datetime
print(datetime.datetime.now())
```

运行上述代码，你会看到在导入`datetime`及其内部依赖（如`math`）时，控制台会输出相应的查找日志。

### 示例二：模块阻止列表

在实际开发中，我们可能希望限制某些模块的导入，例如在沙箱环境中。这可以通过自定义查找器来实现。

以下是实现模块阻止列表的步骤：

1.  **定义阻止列表查找器**：同样继承自`importlib.abc.MetaPathFinder`。
2.  **初始化阻止列表**：在`__init__`方法中接收一个被阻止的模块名列表。
3.  **在`find_spec`中检查**：如果请求导入的模块在被阻止列表中，则直接抛出`ImportError`；否则返回`None`。

```python
import sys
import importlib.abc

class BlocklistFinder(importlib.abc.MetaPathFinder):
    def __init__(self, blocklist):
        self.blocklist = blocklist

    def find_spec(self, fullname, path=None, target=None):
        if fullname in self.blocklist:
            raise ImportError(f"导入被阻止: {fullname}")
        return None

# 阻止导入`socket`模块
sys.meta_path.insert(0, BlocklistFinder(['socket']))

# 尝试导入被阻止的模块会报错
try:
    import socket
except ImportError as e:
    print(e)

# 导入其他模块（即使它内部尝试导入socket）也会被阻止
try:
    import http.server  # http.server 内部会导入 socket
except ImportError as e:
    print(e)
```

### 示例三：从数据库加载模块

更高级的用法是实现一个从数据库（而非文件系统）加载Python代码的导入钩子。这需要同时实现**查找器**和**加载器**。

上一节我们介绍了如何阻止模块导入，本节中我们来看看如何从非文件源加载模块。

以下是核心实现步骤：

1.  **定义数据库加载器**：继承自`importlib.abc.Loader`，需要实现`create_module`和`exec_module`方法。
    *   `create_module`：根据规格创建模块对象，如果是包则设置`__path__`。
    *   `exec_module`：从数据库查询代码，并使用`exec()`函数执行，将结果填充到模块的命名空间。
2.  **定义数据库查找器**：继承自`importlib.abc.MetaPathFinder`。其`find_spec`方法会询问关联的加载器是否能提供指定模块，如果能，则使用`importlib.util.spec_from_loader`创建模块规格。
3.  **连接数据库**：在示例中我们使用SQLite内存数据库来模拟。

以下是关键代码片段：

```python
import sys
import sqlite3
import importlib.abc
import importlib.util

class DBLoader(importlib.abc.Loader):
    def __init__(self, package_name, db_conn):
        self.package_name = package_name
        self.db = db_conn

    def create_module(self, spec):
        # 创建一个新的空模块
        module = importlib.util.module_from_spec(spec)
        # 如果导入的是包本身（不是子模块），将其标记为包
        if spec.name == self.package_name:
            module.__path__ = []
        return module

    def exec_module(self, module):
        # 如果是包本身，不执行代码
        if module.__name__ == self.package_name:
            return
        # 从数据库查询代码
        cursor = self.db.cursor()
        cursor.execute("SELECT code FROM modules WHERE name = ?", (module.__name__,))
        row = cursor.fetchone()
        if row:
            code = row[0]
            # 执行代码，将其加载到模块的命名空间中
            exec(code, module.__dict__)

    def provides(self, fullname):
        # 检查数据库是否提供此模块
        cursor = self.db.cursor()
        cursor.execute("SELECT 1 FROM modules WHERE name = ?", (fullname,))
        return cursor.fetchone() is not None

class DBFinder(importlib.abc.MetaPathFinder):
    def __init__(self, loader):
        self.loader = loader

    def find_spec(self, fullname, path=None, target=None):
        if self.loader.provides(fullname):
            # 创建模块规格，并指定使用我们的加载器
            return importlib.util.spec_from_loader(fullname, self.loader)
        return None

# 使用示例
if __name__ == "__main__":
    # 1. 创建内存数据库并插入模块代码
    conn = sqlite3.connect(":memory:")
    conn.execute("CREATE TABLE modules (name TEXT, code TEXT)")
    module_code = """
def fn(x):
    return x * 2
"""
    conn.execute("INSERT INTO modules VALUES (?, ?)", ("mypackage.mymodule", module_code))
    conn.commit()

    # 2. 创建加载器和查找器，并插入到导入路径
    loader = DBLoader("mypackage", conn)
    finder = DBFinder(loader)
    sys.meta_path.insert(0, finder)

    # 3. 现在可以像普通模块一样导入
    from mypackage.mymodule import fn
    print(fn(21))  # 输出: 42
    print(fn(0.5)) # 输出: 1.0

    # 4. 尝试导入不存在的模块会报错
    try:
        import mypackage.nonexistent
    except ModuleNotFoundError as e:
        print(e)
```

这种机制可以用于实现快速的代码部署（只需更新数据库记录），或者管理代码的多版本共存。

## 总结

![](img/b0ec26acaf9d7147d5b6c6e702b6b378_5.png)

本节课中我们一起学习了Python导入系统的核心机制：**查找**与**加载**。我们探讨了如何通过实现自定义的`MetaPathFinder`和`Loader`来介入这个过程，并演示了三个实用案例：
1.  **跟踪导入**：用于调试和日志记录。
2.  **模块阻止列表**：用于在沙箱环境中限制模块导入。
3.  **从数据库加载模块**：实现了一种灵活、快速的代码部署和管理方案。

Python的导入系统非常强大且可扩展，理解它可以帮助你构建更动态、更灵活的应用程序。所有示例代码均可在 [github.com/fofillips/import-hooks](https://github.com/fofillips/import-hooks) 找到。