# 063：AWS CloudShell学习 🚀

![](img/84b7999a7bd5f3c62a978f0eac362292_0.png)

在本节课中，我们将要学习如何使用AWS CloudShell。AWS CloudShell是一个基于浏览器的命令行工具，它允许你直接访问和管理AWS资源，无需在本地安装任何软件或管理额外的凭证。这对于在不同地点（如图书馆或咖啡馆）快速开始工作非常有用。

## 概述

![](img/84b7999a7bd5f3c62a978f0eac362292_2.png)

AWS CloudShell提供了对AWS资源和工具的浏览器内命令行访问。它的一个关键特性是，由于你身处AWS生态系统内部，操作速度会非常快。接下来，我们将通过实际操作来探索它的各项功能。

## 启动与重置环境

![](img/84b7999a7bd5f3c62a978f0eac362292_4.png)

![](img/84b7999a7bd5f3c62a978f0eac362292_5.png)

上一节我们介绍了CloudShell的基本概念，本节中我们来看看如何启动和重置环境。

在AWS管理控制台的任何区域，你都可以找到并启动CloudShell。启动后，你可能会看到之前工作的历史消息。一个非常实用的技巧是，如果你在CloudShell中进行了大量实验性操作并导致环境混乱，你可以选择删除当前环境并重新开始。

**操作示例：重置环境**
```bash
# 在CloudShell界面中，通过“Actions”菜单选择重置或删除环境。
```

## 界面与多窗口操作

了解了如何启动环境后，我们来看看CloudShell强大的界面管理功能。

![](img/84b7999a7bd5f3c62a978f0eac362292_7.png)

![](img/84b7999a7bd5f3c62a978f0eac362292_8.png)

CloudShell的“Actions”菜单提供了多项实用功能。例如，你可以打开新的Shell标签页，也可以将窗口分割成上下或左右布局。这对于同时运行前端服务（如Flask）并在下方调用它，或者构建一个终端仪表盘来说非常方便。

以下是“Actions”菜单提供的主要功能列表：

![](img/84b7999a7bd5f3c62a978f0eac362292_10.png)

![](img/84b7999a7bd5f3c62a978f0eac362292_11.png)

*   **打开新Shell**：可以打开任意数量的新标签页。
*   **分割为行**：创建上下分割的窗口布局。
*   **分割为列**：创建左右分割的窗口布局。

![](img/84b7999a7bd5f3c62a978f0eac362292_13.png)

## 文件上传与下载

掌握了界面操作后，一个核心需求就是如何在本地和CloudShell之间传输文件。

![](img/84b7999a7bd5f3c62a978f0eac362292_15.png)

CloudShell允许你从本地上传单个文件到其家目录（`/home/cloudshell-user`），也支持从CloudShell下载文件到家目录。家目录的存储空间限制为1GB，这对于上传CSV文件或机器学习数据集等常见数据工程任务通常足够。

**操作示例：上传与下载**
```bash
# 1. 通过“Upload file”按钮上传本地文件。
# 2. 在Shell中解压或处理文件。
unzip cats_dogs_small.zip

# 3. 通过“Download file”按钮，输入文件完整路径进行下载。
# 例如：/home/cloudshell-user/cats_dogs_small/cat.0.jpg
```

你可以使用 `df -h` 命令查看存储空间使用情况。

## 支持多种Shell环境

除了文件操作，CloudShell还支持多种Shell环境，以适应不同开发者的偏好。

CloudShell默认使用Bash，但你也可以轻松切换到Zsh或PowerShell。你可以通过编辑相应的配置文件（如 `~/.bashrc` 或 `~/.zshrc`）来自定义Shell环境。

**操作示例：切换与自定义Shell**
```bash
# 查看当前Shell
echo $SHELL

![](img/84b7999a7bd5f3c62a978f0eac362292_17.png)

# 切换到Zsh
zsh

# 编辑Bash配置文件
nano ~/.bashrc
# 添加自定义命令，例如：echo "This is Bash"
```

![](img/84b7999a7bd5f3c62a978f0eac362292_19.png)

这对于.NET开发者使用PowerShell，或者喜欢Zsh自动补全等高级功能的用户来说非常有用。

![](img/84b7999a7bd5f3c62a978f0eac362292_21.png)

## 与AWS服务交互：以S3为例

![](img/84b7999a7bd5f3c62a978f0eac362292_23.png)

现在，让我们利用CloudShell环境实际做一些工作，特别是与AWS服务交互。

CloudShell预装了AWS CLI，因此你可以直接通过命令行管理AWS资源，无需配置访问密钥。这是一个强大的功能，允许你以编程方式控制AWS平台。

![](img/84b7999a7bd5f3c62a978f0eac362292_25.png)

![](img/84b7999a7bd5f3c62a978f0eac362292_26.png)

![](img/84b7999a7bd5f3c62a978f0eac362292_27.png)

![](img/84b7999a7bd5f3c62a978f0eac362292_28.png)

**操作示例：使用AWS CLI管理S3**
```bash
# 1. 创建一个S3存储桶
aws s3 mb s3://your-unique-bucket-name-20231121

# 2. 列出所有S3存储桶并计数
aws s3 ls | wc -l

# 3. 将本地目录同步到S3存储桶
aws s3 sync ./local_directory s3://your-bucket-name/

# 4. 从S3存储桶下载文件
aws s3 cp s3://your-bucket-name/remote_file.zip ./
```

通过同步命令，你可以快速将大量文件上传到S3，这对于数据流水线或机器学习工程任务来说是无价之宝。

![](img/84b7999a7bd5f3c62a978f0eac362292_30.png)

![](img/84b7999a7bd5f3c62a978f0eac362292_31.png)

## 总结

![](img/84b7999a7bd5f3c62a978f0eac362292_33.png)

本节课中我们一起学习了AWS CloudShell的核心功能与应用。我们了解了如何启动和重置环境、使用多窗口界面、在本地与CloudShell之间传输文件、切换不同的Shell环境，以及最重要的——如何利用CloudShell内集成的AWS CLI直接与S3等服务进行交互，从而高效地完成数据工程和DevOps任务。CloudShell作为一个基于浏览器的集成工具，极大地简化了在AWS云上进行命令行操作和资源管理的流程。