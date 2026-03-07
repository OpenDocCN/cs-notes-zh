# 018：第3周热身练习1 - 在NetBSD上调整文件系统大小 💾

在本教程中，我们将学习如何在NetBSD操作系统上非破坏性地调整一个现有文件系统的大小。我们将通过一个完整的实践练习来演示如何扩展和收缩文件系统，同时确保数据安全。

![](img/7c81c3dfdaaabaee73ea399233b66a67_1.png)

## 概述

在第二周，我们已经完成了一些与文件系统相关的实践练习。本节我们将继续实践课堂所学的知识。具体来说，我们将使用一个AWS实例上的NetBSD系统，对一个文件系统进行扩容和缩容操作，并验证数据的完整性。

上一节我们讨论了ZFS存储池的扩展和存储虚拟化。本节中我们来看看在不使用ZFS的传统Unix文件系统上，是否也能实现类似的功能。

## 准备工作

![](img/7c81c3dfdaaabaee73ea399233b66a67_3.png)

以下是本次练习的步骤概览：
1.  启动一个NetBSD实例，并为其附加一个新的存储卷。
2.  在该磁盘上创建两个512MB的分区。
3.  在每个分区上创建文件系统，挂载它们，并创建一个测试文件以验证操作的非破坏性。
4.  将第一个分区扩展回1GB，并验证文件可访问。
5.  将该分区收缩至256MB，观察结果。

## 操作步骤

### 1. 创建实例与存储卷

![](img/7c81c3dfdaaabaee73ea399233b66a67_5.png)

首先，我们创建一个新的存储卷，并启动一个NetBSD实例。我们可以立即将卷附加到实例上，无需等待实例完全启动。请确保已加载之前定义的AWS命令行别名。

### 2. 查看磁盘与准备

![](img/7c81c3dfdaaabaee73ea399233b66a67_7.png)

实例启动后，我们通过SSH连接。首先，查看系统磁盘情况。

![](img/7c81c3dfdaaabaee73ea399233b66a67_9.png)

使用 `dmesg` 命令查找我们附加的第二块磁盘，它被识别为 `ld5`。

![](img/7c81c3dfdaaabaee73ea399233b66a67_11.png)

运行 `disklabel` 命令查看当前分区表。

![](img/7c81c3dfdaaabaee73ea399233b66a67_13.png)

### 3. 创建分区

![](img/7c81c3dfdaaabaee73ea399233b66a67_15.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_17.png)

接下来，我们以交互模式编辑分区表，创建两个512MB的分区。

![](img/7c81c3dfdaaabaee73ea399233b66a67_19.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_20.png)

以下是具体操作命令：
-   进入交互模式后，首先显示当前分区表。
-   重新定义分区 `a`，接受默认文件系统类型，从磁盘起始位置开始，指定大小为 `512m`。
-   创建第二个分区 `b`，同样使用标准Unix文件系统，从分区 `a` 之后开始，延伸到磁盘末尾。
-   最后，将新的分区表写入磁盘。

![](img/7c81c3dfdaaabaee73ea399233b66a67_22.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_23.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_25.png)

### 4. 创建并挂载文件系统

![](img/7c81c3dfdaaabaee73ea399233b66a67_27.png)

在两个新分区上分别创建文件系统。

![](img/7c81c3dfdaaabaee73ea399233b66a67_29.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_30.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_32.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_34.png)

使用 `newfs` 命令：
-   在分区 `ld5a` 上创建：`newfs /dev/rld5a`
-   在分区 `ld5b` 上创建：`newfs /dev/rld5b`

![](img/7c81c3dfdaaabaee73ea399233b66a67_36.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_37.png)

挂载这两个分区：
-   将 `ld5a` 挂载到 `/mount`
-   将 `ld5b` 挂载到 `/mount2`

![](img/7c81c3dfdaaabaee73ea399233b66a67_39.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_41.png)

使用 `df -h` 命令确认磁盘空间符合预期。

![](img/7c81c3dfdaaabaee73ea399233b66a67_43.png)

### 5. 创建测试文件

![](img/7c81c3dfdaaabaee73ea399233b66a67_45.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_46.png)

在第一个分区上创建一个测试文件，用于后续验证。
```bash
touch /mount/testfile
```

![](img/7c81c3dfdaaabaee73ea399233b66a67_48.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_50.png)

### 6. 扩展文件系统

![](img/7c81c3dfdaaabaee73ea399233b66a67_52.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_54.png)

现在，我们尝试扩展第一个分区。首先，需要卸载该文件系统。

![](img/7c81c3dfdaaabaee73ea399233b66a67_56.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_57.png)

为了给文件系统扩容，我们需要先调整分区表，释放空间。
-   编辑分区表，删除分区 `ld5b`。
-   将分区 `a` 的大小调整为占用整个磁盘。

![](img/7c81c3dfdaaabaee73ea399233b66a67_59.png)

然后，运行 `resize_ffs` 命令来扩展文件系统。指定原始磁盘设备 `/dev/rld5a`，该命令会自动根据磁盘标签信息扩展到可用空间。
```bash
resize_ffs /dev/rld5a
```

![](img/7c81c3dfdaaabaee73ea399233b66a67_61.png)

完成后，重新挂载分区，并使用 `df -h` 验证其大小已变为约1GB。检查测试文件 `testfile` 依然存在，证明扩展操作是非破坏性的。

![](img/7c81c3dfdaaabaee73ea399233b66a67_63.png)

### 7. 收缩文件系统

![](img/7c81c3dfdaaabaee73ea399233b66a67_65.png)

接下来，我们尝试将1GB的文件系统收缩到256MB。首先，再次卸载它。

![](img/7c81c3dfdaaabaee73ea399233b66a67_67.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_68.png)

收缩操作顺序与扩展相反：
-   首先，使用 `resize_ffs` 指定新的大小（256MB对应的扇区数，例如524288）。
    ```bash
    resize_ffs -s 524288 /dev/rld5a
    ```
-   然后，调整磁盘标签，将分区 `a` 的大小设置为对应的扇区数。
-   利用释放出的空间，创建一个新的分区 `b`，占据磁盘剩余部分。

![](img/7c81c3dfdaaabaee73ea399233b66a67_70.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_72.png)

重新挂载收缩后的分区 `a`，确认其大小已变为256MB，并且测试文件仍然完好。

![](img/7c81c3dfdaaabaee73ea399233b66a67_74.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_76.png)

![](img/7c81c3dfdaaabaee73ea399233b66a67_77.png)

此时，新的分区 `b` 还没有文件系统，因此无法直接挂载。我们需要在其上创建一个新的文件系统。
```bash
newfs /dev/rld5b
```
创建完成后，即可挂载并使用第二个分区。

## 总结

本节课中我们一起学习了在NetBSD上调整传统Unix文件系统大小的完整流程。

我们了解到，要扩展一个文件系统，**必须首先调整分区表**，为文件系统提供增长的空间，然后使用 `resize_ffs` 命令进行扩展。需要注意的是，扩展操作会覆盖目标空间上的原有数据。

反之，要收缩一个文件系统，**顺序则相反**：先使用 `resize_ffs` 命令收缩文件系统本身，然后再调整分区表以匹配新的尺寸。释放出的空间可以用于创建新分区，但必须在其上建立新的文件系统才能使用。

![](img/7c81c3dfdaaabaee73ea399233b66a67_79.png)

在整个过程中，原始文件系统上的数据始终保持不变，这证实了操作的非破坏性。下次课程，我们将在Linux系统上完成相同的任务。