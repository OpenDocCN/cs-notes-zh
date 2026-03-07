# 010：第10讲 - AWS 别名预热练习 🚀

在本节课中，我们将学习如何通过创建 Shell 别名和函数，来简化与 Amazon Web Services 命令行工具的交互，从而节省大量重复输入命令的时间。

---

## 概述

系统管理员通常希望避免重复劳动。在本课程中，我们将全程使用 AWS 命令行界面。因此，本节将演示如何设置一些 Shell 别名和函数，让启动、管理和连接 AWS 实例等常见操作变得更加快捷高效。

---

## 创建启动实例的别名

我们经常需要启动新的 AWS 实例。通常，这需要运行 `aws ec2 run-instances` 命令并指定 AMI ID。此外，为本课程创建的实例都需要使用特定的密钥对 `stevens`。

每次输入完整的命令非常繁琐。为此，我们可以创建一个 Shell 别名。

**代码示例：创建别名**
```bash
alias instance='aws ec2 run-instances --key-name stevens'
```
创建此别名后，启动实例只需输入 `instance` 后跟 AMI ID 即可。

---

## 启用双栈网络

我希望所有实例都启用 IPv4 和 IPv6 双栈网络。默认情况下，AWS 不启用此功能，需要正确配置子网和安全组。

我已在本节幻灯片末尾附上博客文章链接。按照该指南操作后，你将获得一个带有 `dual-stack` 标签的子网和安全组。

因此，我们可以创建一个 Shell 函数来启动具有双栈网络的实例。

**代码示例：启动双栈实例的函数**
```bash
start_instance() {
    # 根据标签获取子网和安全组ID
    subnet_id=$(aws ec2 describe-subnets --filters "Name=tag:Name,Values=dual-stack" --query "Subnets[0].SubnetId" --output text)
    sg_id=$(aws ec2 describe-security-groups --filters "Name=tag:Name,Values=dual-stack" --query "SecurityGroups[0].GroupId" --output text)
    # 使用之前定义的别名启动实例
    instance --subnet-id $subnet_id --security-group-ids $sg_id --image-id $1
}
```
这个函数会根据标签获取子网和安全组 ID，然后调用 `instance` 别名来启动实例。现在，你只需提供 AMI ID 作为参数。

---

## 为常用 AMI 创建快捷方式

![](img/7ea35cfe176b5d8d4a91e9a302039e50_1.png)

我经常使用 NetBSD AMI，但不想每次都记住其标识符。为此，可以创建另一个别名。

**代码示例：启动 NetBSD 实例的别名**
```bash
alias startnetbsd='start_instance ami-xxxxxxxx'
```
运行 `startnetbsd` 别名即可使用正确的 AMI ID 调用 `start_instance` 函数。

在展示这些别名和函数时，你会发现其中重复使用了某些构建块。这种模式在本学期后续讨论系统管理中的自动化和编程时还会再次出现。

---

![](img/7ea35cfe176b5d8d4a91e9a302039e50_3.png)

## 获取实例信息

启动实例后，我们需要知道其主机名才能登录。通常，我们会运行 `aws ec2 describe-instances` 命令，但其输出信息繁杂。

因此，可以创建一个函数来根据实例 ID 提取主机名。

![](img/7ea35cfe176b5d8d4a91e9a302039e50_5.png)

**代码示例：根据实例ID获取主机名的函数**
```bash
iname() {
    aws ec2 describe-instances --instance-ids $1 --query "Reservations[0].Instances[0].PublicDnsName" --output text
}
```
现在，使用 `iname <实例ID>` 命令就能直接获得主机名。

---

## 等待实例就绪

启动实例后，系统需要一段时间才能完全启动并接受 SSH 连接。反复尝试 SSH 登录并不高效。

![](img/7ea35cfe176b5d8d4a91e9a302039e50_7.png)

我们可以编写一个函数，使用 AWS CLI 的 `wait` 命令来等待实例进入运行状态，并额外添加一点延迟以确保系统完全启动。

**代码示例：等待实例就绪的函数**
```bash
e2wait() {
    aws ec2 wait instance-running --instance-ids $1
    sleep 30  # 额外等待30秒，确保系统服务已启动
}
```
虽然添加固定延迟并非最优方案，但比反复尝试 SSH 连接要好。你也可以尝试寻找更好的方法。

![](img/7ea35cfe176b5d8d4a91e9a302039e50_9.png)

---

![](img/7ea35cfe176b5d8d4a91e9a302039e50_11.png)

## 管理多个实例

当我们运行多个实例时，可能需要快速查看所有实例的列表。

以下是几个有用的别名：

*   **列出所有实例ID：**
    ```bash
    alias instances='aws ec2 describe-instances --query "Reservations[*].Instances[*].InstanceId" --output text'
    ```
*   **列出所有实例主机名：**
    ```bash
    alias inames='aws ec2 describe-instances --query "Reservations[*].Instances[*].PublicDnsName" --output text'
    ```
*   **同时列出ID和主机名：**
    ```bash
    alias instances2='aws ec2 describe-instances --query "Reservations[*].Instances[*].[InstanceId, PublicDnsName]" --output table'
    ```

---

## 终止实例

终止实例同样可以通过别名来简化。

*   **终止单个实例：**
    ```bash
    alias terminstance='aws ec2 terminate-instances --instance-ids'
    ```
    使用方式：`terminstance <实例ID>`。
*   **终止所有正在运行的实例（请谨慎使用）：**
    ```bash
    alias killallinstances='aws ec2 terminate-instances --instance-ids $(instances)'
    ```

运行终止命令后，实例会进入“关闭中”状态，但仍会出现在 `instances` 列表中。若只想查看当前处于“运行中”状态的实例，可以使用更精确的查询。

![](img/7ea35cfe176b5d8d4a91e9a302039e50_13.png)

---

## 获取并使用预定义的别名文件

我已经将上述常用的别名和函数整理到一个文件中，你可以从课程网站下载并使用它们。

![](img/7ea35cfe176b5d8d4a91e9a302039e50_15.png)

**代码示例：下载并查看别名文件**
```bash
curl -O https://course-website.example.com/aws-aliases.sh
cat aws-aliases.sh
```
该文件包含了我们将要使用的各种实例类型对应的快捷命令。

你可以将此文件放在方便的位置，然后从你的 Shell 启动文件（如 `~/.bashrc` 或 `~/.zshrc`）中加载它。

**代码示例：在 Shell 启动文件中加载别名**
```bash
# 在 ~/.bashrc 或 ~/.zshrc 中添加
source /path/to/your/aws-aliases.sh
```
这样，每次启动新的 Shell 会话时，所有这些便捷的别名和函数就都可以使用了。

---

## 总结

本节课我们一起学习了如何通过自定义 Shell 环境来提升 AWS 命令行工具的使用效率。我们创建了用于启动实例、启用双栈网络、获取实例信息、等待实例就绪以及管理多个实例的别名和函数。掌握这些技巧可以显著减少重复性输入，让你更专注于系统管理的核心任务。

![](img/7ea35cfe176b5d8d4a91e9a302039e50_17.png)

在下一个视频中，我们将进行另一个预热练习，探讨第二周的主题：存储模型与磁盘。谢谢观看，再见！