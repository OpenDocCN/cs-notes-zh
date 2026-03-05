# Python与Systemd：第1章：Systemd入门指南 🐍⚙️

![](img/c90a92fa1d2f34ba1a999222b1943e92_1.png)

在本教程中，我们将学习Systemd的基础知识，并探讨为什么作为Python开发者，了解和使用Systemd是有益的。我们将从服务管理器的概念讲起，逐步深入到Systemd的核心特性，如Cgroups和套接字激活，最后介绍如何通过Python库与Systemd进行交互。

## 什么是服务管理器？

![](img/c90a92fa1d2f34ba1a999222b1943e92_3.png)

服务管理器是负责管理服务生命周期的工具。它本身不是服务，而是用于启动、停止、重启和重新加载服务的程序。此外，它还负责管理服务之间的依赖关系，例如确保某个服务在数据库服务准备就绪后才启动。

在Systemd出现之前，Linux系统通常使用自定义的Shell脚本来管理服务。这些脚本包含大量样板代码，用于参数解析、状态打印等，而实际启动服务的核心代码只占很小一部分。每个服务都需要编写和维护这样的脚本，效率较低。

![](img/c90a92fa1d2f34ba1a999222b1943e92_5.png)

## Systemd的引入

随着服务器规模扩大和对更快启动时间的需求，Systemd应运而生。它逐渐成为许多主流Linux发行版的标准服务管理器。

![](img/c90a92fa1d2f34ba1a999222b1943e92_7.png)

![](img/c90a92fa1d2f34ba1a999222b1943e92_9.png)

Systemd的核心改变在于，它使用**单元文件**来定义服务，而不是可执行的Shell脚本。单元文件以声明式的方式描述了服务应该如何运行。例如，一个服务单元文件（`.service`）会指定要执行的命令、运行用户、环境变量等。

要管理服务，你不再直接执行脚本，而是通过`systemctl`命令与Systemd交互。例如：
```bash
systemctl start myapp.service
systemctl stop myapp.service
systemctl status myapp.service
```
Systemd的一个关键优势是能提供详细的服务状态信息，因为它直接跟踪由它启动的进程。

## 核心概念：Cgroups

![](img/c90a92fa1d2f34ba1a999222b1943e92_11.png)

Cgroups是Linux内核的一个功能，允许对一组进程进行资源限制和隔离。Systemd为每个服务自动创建一个Cgroup。

这意味着你可以为服务设置CPU、内存、I/O等资源的使用上限。例如，在单元文件中，你可以这样限制资源：
```
[Service]
CPUQuota=20%
MemoryLimit=10M
```

此外，Cgroups确保了服务的所有子进程（即使是守护进程化的）都能被Systemd追踪和管理。这使得彻底停止一个服务及其所有相关进程成为可能，只需删除其Cgroup即可。

![](img/c90a92fa1d2f34ba1a999222b1943e92_13.png)

![](img/c90a92fa1d2f34ba1a999222b1943e92_15.png)

## 核心概念：套接字激活

套接字激活是Systemd的另一个强大特性。在传统模式下，应用程序启动后自行打开并监听网络端口。

![](img/c90a92fa1d2f34ba1a999222b1943e92_17.png)

![](img/c90a92fa1d2f34ba1a999222b1943e92_19.png)

在套接字激活模式下，这个逻辑被反转：
1.  Systemd首先启动并监听指定的网络端口。
2.  当第一个连接请求到达该端口时，Systemd才启动对应的应用程序服务。
3.  Systemd将已连接的套接字文件描述符传递给应用程序，应用程序只需处理读写操作。

这种方式带来了多重好处：
*   **按需启动**：节省资源，服务只在有请求时才被激活。
*   **权限分离**：Systemd以root身份监听特权端口（如80），而应用程序可以以普通用户身份运行，提升了安全性。
*   **无缝升级**：结合`SO_REUSEPORT`等内核选项，可以实现不同版本应用同时监听同一端口，便于A/B测试和零停机升级。

实现套接字激活需要两个单元文件：一个套接字单元（`.socket`）定义监听规则，一个服务单元（`.service`）定义要启动的应用。在Python代码中，你需要从Systemd传递的文件描述符中获取套接字，而不是自己创建。

## 使用Python与Systemd交互

为了方便Python开发者，可以使用`pystemd`库与Systemd的D-Bus接口进行交互。

![](img/c90a92fa1d2f34ba1a999222b1943e92_21.png)

首先安装该库：
```bash
pip install pystemd
```

![](img/c90a92fa1d2f34ba1a999222b1943e92_23.png)

然后，你可以在Python代码中导入并使用它来管理服务：
```python
from pystemd.systemd1 import Unit

![](img/c90a92fa1d2f34ba1a999222b1943e92_25.png)

# 加载一个服务单元
myapp_unit = Unit(b‘myapp.service’)
myapp_unit.load()

![](img/c90a92fa1d2f34ba1a999222b1943e92_27.png)

# 启动服务
myapp_unit.start()
# 获取服务的主进程PID
print(myapp_unit.Properties.MainPID)
# 获取服务的所有进程列表
print(myapp_unit.get_processes())
```

![](img/c90a92fa1d2f34ba1a999222b1943e92_29.png)

![](img/c90a92fa1d2f34ba1a999222b1943e92_31.png)

`pystemd`提供了类型安全的接口，比通过Shell命令解析文本输出更可靠、更高效。

![](img/c90a92fa1d2f34ba1a999222b1943e92_33.png)

## Systemd的瞬态单元功能

![](img/c90a92fa1d2f34ba1a999222b1943e92_35.png)

除了管理预定义的持久化服务，Systemd还可以通过Python动态创建和管理“瞬态单元”。这类似于运行一个子进程，但具有更多优势。

使用`subprocess.call`运行命令时，子进程与父进程共享用户权限、Cgroup视图，并且父进程退出会导致子进程退出。

而使用`pystemd`的瞬态单元功能，则可以独立运行任务：
```python
from pystemd.run import run

![](img/c90a92fa1d2f34ba1a999222b1943e92_37.png)

![](img/c90a92fa1d2f34ba1a999222b1943e92_39.png)

![](img/c90a92fa1d2f34ba1a999222b1943e92_41.png)

# 以独立服务的形式运行`sleep 100`命令
run([b‘sleep’, b‘100’])
```
这样运行的进程：
*   可以指定不同的运行用户。
*   拥有独立的Cgroup，资源限制与父进程分离。
*   生命周期独立于启动它的Python进程。

这为在Python应用中安全、可控地运行后台任务或批处理作业提供了强大工具。你还可以在运行时指定资源限制、文件系统视图、网络访问策略等，实现高度的隔离和控制。

## 安全与隔离特性

Systemd提供了丰富的安全沙箱选项，可以限制服务的权限，增强安全性。以下是一些关键选项：

![](img/c90a92fa1d2f34ba1a999222b1943e92_43.png)

*   **ProtectHome**：使服务无法访问`/home`、`/root`等用户目录，保护敏感数据。
*   **ProtectSystem**：将整个根文件系统挂载为只读，防止服务写入系统文件。
*   **ReadWritePaths / ReadOnlyPaths / InaccessiblePaths**：精细控制服务对特定目录的访问权限。
*   **PrivateTmp**：为服务提供私有的`/tmp`目录，与其他服务隔离。
*   **TemporaryFileSystem**：可以为任何目录创建临时的内存文件系统，服务停止后数据自动清除。
*   **BindPaths / BindReadOnlyPaths**：可以将主机上的特定路径（文件或目录）以绑定挂载的方式提供给服务，甚至可以重命名路径。
*   **IPAddressDeny / IPAddressAllow**：为服务配置内置的防火墙规则，限制其网络访问，例如只允许访问特定IP。

## 资源限制实践

![](img/c90a92fa1d2f34ba1a999222b1943e92_45.png)

我们之前提到了在单元文件中使用Cgroups进行资源限制。以下是一个例子，限制服务只能使用20%的CPU、10MB内存，并且最多只能创建5个进程：
```
[Service]
CPUQuota=20%
MemoryLimit=10M
TasksMax=5
```

![](img/c90a92fa1d2f34ba1a999222b1943e92_47.png)

你可以编写一个消耗CPU的Python程序来测试这个限制：
```python
# cpu_stress.py
while True:
    pass
```
当这个服务运行时，你会发现它的CPU使用率会被限制在20%左右。如果它尝试分配超过10MB的内存，Systemd会终止该进程。

---

在本教程中，我们一起学习了Systemd作为现代服务管理器的基础。我们了解了它如何通过单元文件取代复杂的Shell脚本，并深入探讨了其两大核心机制：用于资源控制和进程管理的Cgroups，以及实现按需启动和权限分离的套接字激活。

![](img/c90a92fa1d2f34ba1a999222b1943e92_49.png)

我们还介绍了如何通过`pystemd`库在Python代码中方便地与Systemd交互，管理服务状态、动态创建瞬态单元。最后，我们探讨了Systemd提供的多种安全隔离与资源限制选项，这些功能能帮助Python开发者构建更安全、更稳定、更易于管理的生产级应用。

![](img/c90a92fa1d2f34ba1a999222b1943e92_51.png)

掌握Systemd，能让你的Python应用更好地融入现代Linux生态系统，充分利用操作系统提供的管理、安全和隔离能力。