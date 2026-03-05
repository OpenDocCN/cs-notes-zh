# Python依赖管理：P1：Pipenv - Python依赖管理的未来

![](img/b11954b5468ac09c3c499c218d394ea0_1.png)

![](img/b11954b5468ac09c3c499c218d394ea0_3.png)

![](img/b11954b5468ac09c3c499c218d394ea0_5.png)

![](img/b11954b5468ac09c3c499c218d394ea0_7.png)

在本节课中，我们将学习Python依赖管理的历史、当前面临的挑战以及未来的解决方案——Pipenv。我们将从早期的手动管理方式开始，逐步了解虚拟环境和`requirements.txt`的引入，最后深入探讨Pipenv如何通过`Pipfile`和`Pipfile.lock`来统一和简化整个工作流程。

## 依赖管理的历史演变

![](img/b11954b5468ac09c3c499c218d394ea0_9.png)

上一节我们介绍了课程概述，本节中我们来看看Python依赖管理是如何一步步发展到今天的。

![](img/b11954b5468ac09c3c499c218d394ea0_11.png)

### 早期手动管理阶段
过去，安装Python包是一个完全手动的过程。开发者需要从互联网下载压缩包，解压后运行`setup.py install`命令，将包安装到系统的`site-packages`目录中。有时甚至直接解压文件到该目录。

**核心操作：**
```bash
python setup.py install
```

![](img/b11954b5468ac09c3c499c218d394ea0_13.png)

这种方法存在明显问题：包托管分散、依赖全局安装、无法同时安装同一库的不同版本，导致项目间依赖冲突。

![](img/b11954b5468ac09c3c499c218d394ea0_15.png)

### EasyInstall的出现
为了解决手动安装的繁琐，社区引入了EasyInstall工具。它可以直接从Python包索引（PyPI）抓取并安装包，实现了自动化安装。

然而，EasyInstall只能安装，不能卸载包，功能上存在缺陷。

![](img/b11954b5468ac09c3c499c218d394ea0_17.png)

![](img/b11954b5468ac09c3c499c218d394ea0_19.png)

### 现代标准：Pip与Virtualenv
大约从2010年开始，Pip取代EasyInstall成为包管理的事实标准。同时，Virtualenv被广泛采用，它为每个项目创建独立的Python环境，解决了全局依赖冲突的问题。项目依赖通常被记录在`requirements.txt`文件中。

**核心操作：**
```bash
# 创建虚拟环境
python -m venv myenv
# 激活环境（Linux/macOS）
source myenv/bin/activate
# 使用pip安装依赖
pip install -r requirements.txt
```

虽然这套组合（Pip + Virtualenv + `requirements.txt`）很强大，但它由多个独立工具组成，对新用户不够友好，且`requirements.txt`文件本身存在歧义。

## 当前工作流程的挑战

上一节我们回顾了历史，本节中我们来看看当前主流的Pip和Virtualenv工作流程存在哪些具体问题。

### Virtualenv的复杂性
Virtualenv要求用户理解“虚拟环境”这一抽象概念，增加了学习成本。其手动创建和激活的过程对新手不够直观。

### Requirements.txt文件的歧义
`requirements.txt`文件存在一个根本性的矛盾：它既是**期望的依赖声明**（如`Flask`），又常被用作**确定的依赖锁定文件**（通过`pip freeze`生成包含所有传递依赖的扁平列表）。

以下是两种情况的对比：

1.  **声明期望的依赖（可读性好，但构建不确定）：**
    ```txt
    Flask
    pytest
    ```
    这仅声明了项目直接依赖，但未锁定传递依赖（如Werkzeug、Jinja2）的具体版本，可能导致不同时间或环境下安装的版本不同。

2.  **锁定所有依赖（构建确定，但可读性差）：**
    ```bash
    pip freeze > requirements.txt
    ```
    生成的`requirements.txt`包含所有包及其精确版本，确保了确定性构建，但难以区分直接依赖和传递依赖。

这种“期望”与“需要”之间的不匹配，是当前工作流程的一个核心问题。其他语言社区（如Node.js的`package-lock.json`、Ruby的`Gemfile.lock`）普遍采用**锁文件**机制来解决此问题，而Python原生缺乏这一机制。

## 未来的解决方案：Pipfile与Pipenv

上一节我们分析了现有问题，本节中我们来看看社区提出的未来标准——`Pipfile`，以及能让我们立即用上此标准的工具——`Pipenv`。

![](img/b11954b5468ac09c3c499c218d394ea0_21.png)

![](img/b11954b5468ac09c3c499c218d394ea0_23.png)

### Pipfile：新的依赖声明标准
`Pipfile`旨在取代`requirements.txt`，它使用TOML格式，清晰地将依赖分为不同组，最典型的是`[packages]`（生产依赖）和`[dev-packages]`（开发依赖）。

**一个Pipfile示例：**
```toml
[[source]]
url = "https://pypi.org/simple"
verify_ssl = true
name = "pypi"

![](img/b11954b5468ac09c3c499c218d394ea0_25.png)

![](img/b11954b5468ac09c3c499c218d394ea0_26.png)

[packages]
flask = "*"

![](img/b11954b5468ac09c3c499c218d394ea0_28.png)

[dev-packages]
pytest = "*"
```

![](img/b11954b5468ac09c3c499c218d394ea0_30.png)

### Pipfile.lock：确定的锁文件
`Pipfile.lock`是由工具自动生成的锁文件，采用JSON格式。它包含了所有依赖（直接和传递）的确切版本以及哈希值，确保了每次安装都是完全确定和可验证的。

![](img/b11954b5468ac09c3c499c218d394ea0_32.png)

![](img/b11954b5468ac09c3c499c218d394ea0_34.png)

**锁文件的核心价值：**
*   **确定性构建**：在任何机器、任何时间都能安装完全相同的依赖树。
*   **安全性**：通过哈希校验，确保安装的包未被篡改。
*   **快速安装**：锁文件明确指出了每个包的具体文件，避免了复杂的依赖解析。

### Pipenv：官方推荐的一体化工具
`Pipenv`集成了包管理（Pip）和虚拟环境（Virtualenv）的功能，并原生支持`Pipfile`和`Pipfile.lock`，是Python官方推荐的工具。它提供了简洁的命令行接口，自动化了大部分工作流程。

以下是Pipenv的主要功能演示：

![](img/b11954b5468ac09c3c499c218d394ea0_36.png)

![](img/b11954b5468ac09c3c499c218d394ea0_38.png)

**初始化项目并安装依赖：**
```bash
# 安装Pipenv
pip install pipenv

![](img/b11954b5468ac09c3c499c218d394ea0_40.png)

![](img/b11954b5468ac09c3c499c218d394ea0_42.png)

![](img/b11954b5468ac09c3c499c218d394ea0_44.png)

# 为项目安装一个包（如requests），会自动创建虚拟环境和Pipfile
pipenv install requests

![](img/b11954b5468ac09c3c499c218d394ea0_46.png)

![](img/b11954b5468ac09c3c499c218d394ea0_48.png)

# 安装一个开发依赖
pipenv install pytest --dev
```

**管理环境与依赖：**
```bash
# 进入项目所在的虚拟环境Shell
pipenv shell

![](img/b11954b5468ac09c3c499c218d394ea0_50.png)

![](img/b11954b5468ac09c3c499c218d394ea0_52.png)

# 查看依赖关系树
pipenv graph

![](img/b11954b5468ac09c3c499c218d394ea0_54.png)

![](img/b11954b5468ac09c3c499c218d394ea0_56.png)

# 检查依赖中的已知安全漏洞
pipenv check

![](img/b11954b5468ac09c3c499c218d394ea0_58.png)

![](img/b11954b5468ac09c3c499c218d394ea0_60.png)

# 卸载一个包
pipenv uninstall requests

# 根据Pipfile.lock安装所有依赖（用于生产环境）
pipenv install --deploy
```

![](img/b11954b5468ac09c3c499c218d394ea0_62.png)

![](img/b11954b5468ac09c3c499c218d394ea0_64.png)

**同步与转换：**
```bash
# 将虚拟环境的状态与Pipfile.lock同步
pipenv sync

# 从Pipfile.lock生成一个requirements.txt文件
pipenv lock -r
```

Pipenv通过将依赖声明（`Pipfile`）和依赖锁定（`Pipfile.lock`）分离，并自动化环境管理，完美解决了之前提到的工作流程挑战。

## 总结

本节课中我们一起学习了Python依赖管理的演进历程。我们从手动管理、EasyInstall，走到了当前主流的Pip与Virtualenv组合，并分析了其存在的复杂性和`requirements.txt`文件的歧义性问题。

![](img/b11954b5468ac09c3c499c218d394ea0_66.png)

![](img/b11954b5468ac09c3c499c218d394ea0_68.png)

最终，我们探讨了未来的解决方案：通过`Pipfile`清晰声明依赖，通过`Pipfile.lock`确保确定性构建，并通过`Pipenv`这一体化工具来优雅地管理整个生命周期。Pipenv代表了Python依赖管理的未来方向，它降低了入门门槛，提升了开发体验和项目安全性，是值得所有Python开发者学习和采用的新工具。