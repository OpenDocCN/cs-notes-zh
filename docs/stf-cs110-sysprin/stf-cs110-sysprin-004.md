# 4：文件系统数据结构、系统调用与多进程简介 🖥️

![](img/c5b69340c585f582e2f65bbaf36c1a1e_1.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_3.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_4.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_6.png)

在本节课中，我们将学习操作系统如何通过数据结构管理文件和进程，理解系统调用的工作原理，并初步接触多进程编程的概念。

## 概述 📋

![](img/c5b69340c585f582e2f65bbaf36c1a1e_8.png)

操作系统需要高效地管理计算机资源，特别是文件和正在运行的程序（进程）。本节课将探讨Linux系统用于跟踪这些资源的核心数据结构，解释用户程序如何通过系统调用安全地与操作系统交互，并介绍如何创建和管理多个并发执行的进程。

![](img/c5b69340c585f582e2f65bbaf36c1a1e_10.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_12.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_14.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_16.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_17.png)

---

## 文件系统数据结构 📁

![](img/c5b69340c585f582e2f65bbaf36c1a1e_19.png)

上一节我们提到了操作系统需要管理资源。本节中，我们来看看操作系统内部用于跟踪文件和进程的核心数据结构。

![](img/c5b69340c585f582e2f65bbaf36c1a1e_21.png)

在Linux中，一个运行中的程序被称为**进程**。操作系统为每个进程维护一个**进程控制块**，其中包含了该进程的所有信息。这些进程控制块被组织在一个称为**进程表**的全局数据结构中。

![](img/c5b69340c585f582e2f65bbaf36c1a1e_23.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_25.png)

进程控制块中的一个关键部分是**描述符表**。这是一个数据结构，用于跟踪该进程打开的所有“文件”。在Unix/Linux哲学中，许多资源（如网络连接、终端）都被抽象为文件。因此，描述符表不仅记录常规文件，也记录这些抽象资源。

![](img/c5b69340c585f582e2f65bbaf36c1a1e_27.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_29.png)

每个进程在启动时，默认会获得三个文件描述符：
*   **0**: 标准输入 (`stdin`)
*   **1**: 标准输出 (`stdout`)
*   **2**: 标准错误 (`stderr`)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_31.png)

这些描述符通常连接到用户的终端。我们使用文件描述符来执行`read`、`write`、`open`、`close`等操作。

### 数据结构层级

![](img/c5b69340c585f582e2f65bbaf36c1a1e_33.png)

以下是文件描述符背后的数据结构层级关系：

![](img/c5b69340c585f582e2f65bbaf36c1a1e_35.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_37.png)

1.  **描述符表**: 每个进程独有，存储其打开文件的引用。
2.  **打开文件表**: 系统全局共享。当描述符指向一个打开的文件时，它实际链接到一个**打开文件表项**。该表项存储了文件的**访问模式**（如只读、读写）和当前**读写位置**（游标）。
    *   公式：`打开文件表项 = {模式， 游标， 引用计数， ...}`
3.  **v-node表**: 系统全局共享。每个打开文件表项指向一个**v-node**（虚拟节点）。v-node是磁盘上文件元数据（存储在**i-node**中）的内存缓存副本，包含了文件类型、大小、权限等信息。
    *   公式：`v-node ≈ 内存中的 i-node 缓存`

![](img/c5b69340c585f582e2f65bbaf36c1a1e_39.png)

这种层级结构允许多个进程共享同一个打开的文件（例如，共享终端输出），同时又能让每个进程维护自己独立的读写位置。

![](img/c5b69340c585f582e2f65bbaf36c1a1e_41.png)

**核心概念图示**：
```
进程A描述符表[3] ---> 全局打开文件表项X ---> 全局v-node表项V (链接到磁盘i-node)
进程B描述符表[4] ---> 全局打开文件表项Y ---> 全局v-node表项V (链接到磁盘i-node)
```
（即使进程A和B打开同一个文件，它们也可能有独立的打开文件表项X和Y，从而拥有独立的游标。）

![](img/c5b69340c585f582e2f65bbaf36c1a1e_43.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_45.png)

---

## 系统调用 🔧

![](img/c5b69340c585f582e2f65bbaf36c1a1e_47.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_49.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_51.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_52.png)

上一节我们了解了操作系统内部的数据结构。本节中我们来看看用户程序如何通过系统调用与这些受保护的内核结构进行交互。

![](img/c5b69340c585f582e2f65bbaf36c1a1e_54.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_56.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_58.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_60.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_62.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_63.png)

系统调用是程序与操作系统内核交互的接口，用于执行需要特权的操作，如文件操作、进程创建等。普通函数调用无法提供必要的安全隔离。

![](img/c5b69340c585f582e2f65bbaf36c1a1e_65.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_67.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_69.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_71.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_73.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_75.png)

### 为什么需要系统调用？

![](img/c5b69340c585f582e2f65bbaf36c1a1e_77.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_79.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_81.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_83.png)

用户程序运行在**用户模式**，只能访问自己的内存空间。而操作系统内核运行在**内核模式**，可以访问所有内存和硬件。系统调用是用户模式程序请求内核模式服务的安全桥梁。

![](img/c5b69340c585f582e2f65bbaf36c1a1e_85.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_87.png)

### 系统调用如何工作？

![](img/c5b69340c585f582e2f65bbaf36c1a1e_89.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_91.png)

系统调用的执行流程与普通函数调用不同：

![](img/c5b69340c585f582e2f65bbaf36c1a1e_93.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_95.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_97.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_99.png)

1.  **准备参数**: 将系统调用编号（例如，`open`对应编号2）和参数放入指定的CPU寄存器。
    *   代码示例（概念性汇编）：
        ```asm
        mov rax, 2       ; 系统调用编号 (open)
        mov rdi, filename ; 第一个参数 (文件名指针)
        mov rsi, flags    ; 第二个参数 (打开标志)
        mov rdx, mode     ; 第三个参数 (文件模式)
        ```
2.  **触发中断**: 执行`syscall`指令。这会触发一个软中断，将CPU控制权从用户模式切换到内核模式。
3.  **内核处理**: 内核的中断处理程序根据寄存器中的编号识别请求，执行相应的内核函数（如真正的`open`操作）。
4.  **返回结果**: 内核将结果（成功则返回文件描述符，失败则返回-1）放入`rax`寄存器，并切换回用户模式，程序从`syscall`指令之后继续执行。

![](img/c5b69340c585f582e2f65bbaf36c1a1e_101.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_102.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_104.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_105.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_107.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_109.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_111.png)

**错误处理**：如果系统调用失败，内核除了在`rax`中返回-1，还会设置一个全局变量`errno`来指示具体的错误原因。

![](img/c5b69340c585f582e2f65bbaf36c1a1e_113.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_115.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_116.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_118.png)

---

![](img/c5b69340c585f582e2f65bbaf36c1a1e_120.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_122.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_124.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_126.png)

## 多进程编程简介 👥

前面我们讨论了单个进程如何运行。本节中，我们将探索如何让一个程序创建并管理多个同时执行的进程。

![](img/c5b69340c585f582e2f65bbaf36c1a1e_128.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_130.png)

现代操作系统支持**多任务处理**，可以并发运行多个程序。每个运行中的程序都是一个**进程**，拥有唯一的**进程ID**。

### 创建新进程：`fork`系统调用

`fork`系统调用用于创建一个新的进程。新进程称为**子进程**，调用`fork`的进程称为**父进程**。

![](img/c5b69340c585f582e2f65bbaf36c1a1e_132.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_134.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_136.png)

`fork`的独特之处在于：**它只被调用一次，但会返回两次**——分别在父进程和子进程中返回。

![](img/c5b69340c585f582e2f65bbaf36c1a1e_138.png)

*   在**父进程**中，`fork`返回新创建的子进程的PID。
*   在**子进程**中，`fork`返回0。
*   如果`fork`失败，则返回-1。

![](img/c5b69340c585f582e2f65bbaf36c1a1e_140.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_142.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_144.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_146.png)

代码示例：
```c
#include <stdio.h>
#include <unistd.h>
#include <sys/types.h>

![](img/c5b69340c585f582e2f65bbaf36c1a1e_148.png)

int main() {
    pid_t pid = fork(); // 在这里，进程一分为二
    if (pid == 0) {
        // 子进程执行的代码
        printf("Hello from child process! My PID is %d.\n", getpid());
    } else if (pid > 0) {
        // 父进程执行的代码
        printf("Hello from parent process! My child‘s PID is %d.\n", pid);
    } else {
        // fork失败
        perror("fork failed");
    }
    return 0;
}
```

![](img/c5b69340c585f582e2f65bbaf36c1a1e_150.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_152.png)

### `fork`的语义细节

![](img/c5b69340c585f582e2f65bbaf36c1a1e_154.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_156.png)

*   **继承与复制**：子进程是父进程的副本，它获得父进程代码、数据段、堆栈和文件描述符表的**副本**。然而，现代操作系统使用**写时复制**技术进行优化，只有在任一进程试图修改数据时，才会真正复制内存页，这提高了效率。
*   **执行流**：`fork`调用后，父进程和子进程都从`fork`调用之后的下一行代码开始并发执行。执行顺序由操作系统调度决定，是**非确定性的**。
*   **独立性**：父子进程有各自独立的地址空间。修改其中一个进程的变量，不会影响另一个。

![](img/c5b69340c585f582e2f65bbaf36c1a1e_158.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_160.png)

### 一个`fork`示例：进程树

![](img/c5b69340c585f582e2f65bbaf36c1a1e_162.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_163.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_165.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_167.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_169.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_171.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_173.png)

以下程序演示了多次调用`fork`如何创建一棵进程树：

![](img/c5b69340c585f582e2f65bbaf36c1a1e_175.png)

```c
#include <stdio.h>
#include <unistd.h>
#include <assert.h>

![](img/c5b69340c585f582e2f65bbaf36c1a1e_177.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_179.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_181.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_183.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_184.png)

int main() {
    char trail[] = "ABCD";
    for (int i = 0; trail[i] != ‘\0‘; i++) {
        printf("%c", trail[i]);
        pid_t pid = fork();
        assert(pid >= 0);
    }
    printf("\n");
    return 0;
}
```

![](img/c5b69340c585f582e2f65bbaf36c1a1e_186.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_188.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_189.png)

这个程序会打印出类似`A B B C C C C D D D D D D D`的输出，但字母的顺序和换行符的位置每次运行都可能不同，这生动地展示了多进程执行的并发性和非确定性。

![](img/c5b69340c585f582e2f65bbaf36c1a1e_191.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_193.png)

---

![](img/c5b69340c585f582e2f65bbaf36c1a1e_195.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_197.png)

## 总结 🎯

![](img/c5b69340c585f582e2f65bbaf36c1a1e_199.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_201.png)

本节课中我们一起学习了：

![](img/c5b69340c585f582e2f65bbaf36c1a1e_203.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_205.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_206.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_208.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_210.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_212.png)

1.  **文件系统数据结构**：了解了Linux如何通过进程控制块、描述符表、打开文件表和v-node表的多层结构来高效管理文件和进程资源。
2.  **系统调用**：理解了系统调用作为用户程序与内核安全交互的机制，包括其工作原理（通过`syscall`指令和寄存器传递参数）与普通函数调用的本质区别。
3.  **多进程编程基础**：掌握了使用`fork`系统调用创建新进程的方法，理解了父子进程的关系、`fork`的返回语义、写时复制机制以及多进程执行的并发性和非确定性。

![](img/c5b69340c585f582e2f65bbaf36c1a1e_214.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_216.png)

![](img/c5b69340c585f582e2f65bbaf36c1a1e_218.png)

这些概念是理解操作系统工作原理和进行系统级编程的基石。在接下来的课程中，我们将深入探讨如何协调多个进程（例如，让父进程等待子进程结束），以及更强大的进程间通信机制。