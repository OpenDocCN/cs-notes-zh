# 003：在虚拟机中安装你的操作系统 🖥️

在本节课中，我们将学习如何将你编写的操作系统安装到虚拟机中。这样做的好处是，你无需在每次修改代码后都重启你的物理计算机，从而极大地提高开发效率。

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_1.png)

上一节我们介绍了如何编写一个简单的内核并生成可引导的磁盘镜像。本节中我们来看看如何配置一个虚拟机来运行这个镜像。

## 准备工作

首先，你需要安装一个虚拟机软件。本教程将使用 **VirtualBox** 作为示例。同时，我们还需要 **GRUB** 引导加载器来帮助我们创建一个可引导的CD镜像。

## 修改 Makefile 以生成 ISO 镜像

为了在虚拟机中运行，我们需要将内核打包成一个可引导的CD镜像（ISO文件）。以下是修改 `Makefile` 的步骤。

首先，我们添加一个目标来创建ISO镜像。这个目标依赖于编译好的内核文件。

```makefile
mykernel.iso: mykernel.bin
```

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_3.png)

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_5.png)

接下来，我们需要为ISO镜像创建正确的目录结构。这与我们之前使用GRUB引导时的结构类似。

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_7.png)

以下是创建目录结构和配置文件的步骤：

1.  创建一个临时工作目录 `iso`。
2.  在 `iso` 目录下创建子目录 `boot/grub`。
3.  将编译好的内核文件 `mykernel.bin` 复制到 `iso/boot/` 目录下。
4.  在 `iso/boot/grub/` 目录下手动创建一个 `grub.cfg` 配置文件。

`grub.cfg` 文件的内容非常简单，因为我们只有一个启动项。

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_9.png)

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_11.png)

```cfg
set timeout=0
set default=0

menuentry "My Operating System" {
    multiboot /boot/mykernel.bin
    boot
}
```

配置完成后，我们使用 `grub-mkrescue` 命令将这个目录打包成ISO镜像文件。之后，可以删除临时的 `iso` 目录。

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_13.png)

```makefile
mykernel.iso: mykernel.bin
    mkdir -p iso/boot/grub
    cp mykernel.bin iso/boot/
    echo 'set timeout=0' > iso/boot/grub/grub.cfg
    echo 'set default=0' >> iso/boot/grub/grub.cfg
    echo 'menuentry "My Operating System" {' >> iso/boot/grub/grub.cfg
    echo '    multiboot /boot/mykernel.bin' >> iso/boot/grub/grub.cfg
    echo '    boot' >> iso/boot/grub/grub.cfg
    echo '}' >> iso/boot/grub/grub.cfg
    grub-mkrescue -o mykernel.iso iso
    rm -rf iso
```

## 在 VirtualBox 中创建并运行虚拟机

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_15.png)

现在，我们有了 `mykernel.iso` 镜像文件，可以在VirtualBox中创建一个新的虚拟机来运行它。

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_17.png)

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_19.png)

1.  打开VirtualBox，点击“新建”。
2.  为虚拟机命名（例如“MyOS”），类型选择“Other”，版本选择“Unknown/Other”。
3.  为虚拟机分配少量内存（例如64MB），这已经足够我们的简单内核运行。
4.  在创建虚拟硬盘的步骤中，选择“不添加虚拟硬盘”，因为我们目前只需要从ISO镜像启动。
5.  创建完成后，选中新虚拟机，点击“设置”。
6.  在“存储”设置中，为“控制器: IDE”添加一个光驱，并选择我们生成的 `mykernel.iso` 文件。
7.  启动虚拟机，你应该能看到内核输出的“Hello, Kernel World!”信息。

## 优化 Makefile：添加一键运行命令

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_21.png)

为了进一步提升开发体验，我们可以在 `Makefile` 中添加一个 `run` 目标，让它自动完成编译、生成ISO并启动虚拟机的全过程。

这个目标需要先构建 `mykernel.iso`，然后启动VirtualBox。为了避免重复启动虚拟机导致冲突，我们会在启动新实例前尝试终止可能正在运行的旧虚拟机进程。

```makefile
run: mykernel.iso
    killall VirtualBoxVM || true
    sleep 1
    VirtualBox --startvm "My Operating System" &
```

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_23.png)

现在，你只需要在终端中输入 `make run`，Make工具就会处理所有步骤，并自动在虚拟机中运行你的操作系统。

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_25.png)

## 引入精确数据类型

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_27.png)

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_29.png)

在结束本节之前，我们需要讨论一个与硬件通信相关的重要预备知识：**数据类型的精确性**。

当软件内部通信时，编译器会处理 `int`、`short` 等类型的具体大小。但当操作系统内核与硬件直接通信时，必须精确知道每一个数据占用的字节数。例如，汇编代码可能期望一个4字节的整数，如果C编译器认为 `int` 是8字节，就会导致错误。

为了解决这个问题，常见的做法是定义一个专用的头文件来确保数据类型的宽度。

我们创建一个 `types.h` 文件：

```c
#ifndef TYPES_H
#define TYPES_H

typedef char int8_t;
typedef unsigned char uint8_t;

typedef short int16_t;
typedef unsigned short uint16_t;

typedef int int32_t;
typedef unsigned int uint32_t;

typedef long long int64_t;
typedef unsigned long long uint64_t;

#endif
```

然后，在内核源码（例如 `kernel.cpp`）中，我们不再使用原生的 `int`、`unsigned int`，而是使用这些明确指定大小的类型，如 `uint32_t`。

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_31.png)

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_33.png)

```cpp
#include “types.h”

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_35.png)

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_36.png)

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_37.png)

// 之前: unsigned int magic_number;
// 之后:
uint32_t magic_number;
```

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_39.png)

这样，无论在哪一种编译器下，`uint32_t` 都明确表示一个32位无符号整数，保证了与硬件或其他底层代码交互时的精确性。

## 总结

本节课中我们一起学习了如何将操作系统内核部署到虚拟机中。我们修改了 `Makefile` 来自动生成可引导的ISO镜像，配置了VirtualBox虚拟机来运行它，并添加了一键运行的便捷命令。最后，我们引入了精确数据类型的概念，为下一节与硬件通信打下了重要基础。

![](img/c36e8c7c75eaec6465c53d8b9aaa7537_41.png)

下一节，我们将开始探索操作系统开发中一个关键且具有挑战性的部分：与硬件通信（例如读取键盘输入）。虽然初始设置较为复杂，但一旦打通这个环节，后续添加鼠标、显示器等支持就会变得相对容易。