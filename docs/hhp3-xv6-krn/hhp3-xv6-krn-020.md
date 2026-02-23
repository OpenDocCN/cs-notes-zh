# 20：VM 函数代码详解 🧠

![](img/5e964734889d7046269d2bd5a76227f8_0.png)

![](img/5e964734889d7046269d2bd5a76227f8_2.png)

在本节课中，我们将深入学习 xv6 内核中虚拟内存（VM）相关的辅助函数。这些函数位于 `vm.c` 文件中，负责管理页表、地址映射、内存分配与释放等核心操作。我们将通过代码走查的方式，逐一解析每个函数的工作原理和实现细节。

---

## 函数 `walk`：遍历页表 🚶‍♂️

上一节我们概述了 VM 函数的功能，本节中我们来看看 `walk` 函数的具体实现。该函数接收一个指向页表树根节点的指针、一个虚拟地址和一个布尔值 `alloc`。它的作用是遍历页表树，并返回指向目标虚拟地址对应的页表项（PTE）的指针。如果遍历过程中发现中间层页表不存在，且 `alloc` 为真，则会分配并初始化这些页表。

以下是 `walk` 函数的核心逻辑：

```c
pte_t *walk(pagetable_t pagetable, uint64 va, int alloc) {
    if(va >= MAXVA)
        panic("walk");
    for(int level = 2; level > 0; level--) {
        pte_t *pte = &pagetable[PX(level, va)];
        if(*pte & PTE_V) {
            pagetable = (pagetable_t)PTE2PA(*pte);
        } else {
            if(!alloc || (pagetable = (pde_t*)kalloc()) == 0)
                return 0;
            memset(pagetable, 0, PGSIZE);
            *pte = PA2PTE(pagetable) | PTE_V;
        }
    }
    return &pagetable[PX(0, va)];
}
```

代码执行步骤如下：

1.  **检查虚拟地址**：确保虚拟地址 `va` 不超过最大允许值 `MAXVA`。
2.  **循环遍历层级**：从第 2 级（根页表）开始，向下遍历到第 1 级。
    *   使用宏 `PX(level, va)` 从虚拟地址中提取当前层级的索引位。
    *   通过索引在当前页表中找到对应的页表项（PTE）。
3.  **处理页表项**：
    *   如果 PTE 的有效位（`PTE_V`）已设置，则通过 `PTE2PA` 宏将 PTE 转换为物理地址，并更新 `pagetable` 指针，指向下一级页表。
    *   如果 PTE 无效：
        *   若 `alloc` 为假，则返回 0（表示失败）。
        *   若 `alloc` 为真，则调用 `kalloc` 分配一个新的物理页作为下一级页表，用 `memset` 清零，并通过 `PA2PTE` 宏将其物理地址转换为 PTE 格式，设置有效位后，存入当前 PTE。
4.  **返回最终 PTE**：循环结束后，`pagetable` 指向第 0 级页表。使用 `PX(0, va)` 提取最终索引，返回指向目标页表项的指针。

---

## 函数 `mappages`：建立地址映射 🗺️

理解了如何查找页表项后，我们来看看如何建立虚拟地址到物理地址的映射。`mappages` 函数用于在页表中创建一系列连续的页表项，将一段虚拟地址空间映射到一段物理地址空间。

该函数接收页表根指针、起始虚拟地址 `va`、映射大小 `size`、起始物理地址 `pa` 以及权限位 `perm`。它会为 `[va, va+size)` 范围内的每个虚拟页，在页表中创建对应的页表项，使其指向 `[pa, pa+size)` 范围内对应的物理页，并设置相同的权限。

以下是 `mappages` 函数的关键部分：

```c
int mappages(pagetable_t pagetable, uint64 va, uint64 size, uint64 pa, int perm) {
    uint64 a, last;
    pte_t *pte;
    a = PGROUNDDOWN(va);
    last = PGROUNDDOWN(va + size - 1);
    for(;;) {
        if((pte = walk(pagetable, a, 1)) == 0)
            return -1;
        if(*pte & PTE_V)
            panic("remap");
        *pte = PA2PTE(pa) | perm | PTE_V;
        if(a == last)
            break;
        a += PGSIZE;
        pa += PGSIZE;
    }
    return 0;
}
```

执行流程如下：

1.  **地址对齐**：使用 `PGROUNDDOWN` 确保起始虚拟地址 `a` 和结束地址 `last` 是页对齐的。
2.  **逐页映射**：循环处理每一页。
    *   调用 `walk` 函数查找或创建当前虚拟地址 `a` 对应的页表项 `pte`。`alloc` 参数为 1，允许分配中间页表。
    *   检查找到的 PTE 是否已经有效（`PTE_V`），如果是，说明发生了重映射，触发 `panic`。
    *   使用 `PA2PTE` 将物理地址 `pa` 转换为 PTE 格式，与权限位 `perm` 和有效位 `PTE_V` 进行或操作，然后存入页表项 `*pte`。
    *   如果当前页是最后一页（`a == last`），则结束循环。
    *   否则，虚拟地址 `a` 和物理地址 `pa` 都增加一个页的大小（`PGSIZE`），处理下一页。
3.  **返回结果**：成功映射所有页后返回 0。

---

## 函数 `kvmmake`：构建内核页表 🏗️

现在，我们来看内核如何构建自己的页表。`kvmmake` 函数负责创建并初始化内核的页表，它通过调用 `kvmmap`（一个包装了 `mappages` 的函数）来建立各种映射。

内核页表需要建立以下几种映射：
1.  **直接映射**：将大部分物理内存（包括内核代码、数据）以相同的虚拟地址进行映射，方便内核访问。
2.  **设备映射**：将 UART、磁盘、PLIC 等 I/O 设备的物理地址映射到特定的虚拟地址。
3.  **跳板页映射**：将 `trampoline` 代码页映射到虚拟地址空间的最高页。
4.  **进程内核栈映射**：为每个进程分配一个独立的内核栈页，并映射到内核地址空间。

以下是 `kvmmake` 函数的核心映射调用：

```c
pagetable_t kvmmake(void) {
    pagetable_t kpgtbl = (pagetable_t) kalloc();
    memset(kpgtbl, 0, PGSIZE);
    // 映射 UART 设备
    kvmmap(kpgtbl, UART0, UART0, PGSIZE, PTE_R | PTE_W);
    // 映射磁盘设备
    kvmmap(kpgtbl, VIRTIO0, VIRTIO0, PGSIZE, PTE_R | PTE_W);
    // 映射 PLIC
    kvmmap(kpgtbl, PLIC, PLIC, 0x400000, PTE_R | PTE_W);
    // 映射内核代码段 (只读、可执行)
    kvmmap(kpgtbl, KERNBASE, KERNBASE, (uint64)etext-KERNBASE, PTE_R | PTE_X);
    // 映射内核数据段及剩余物理内存 (可读、可写)
    kvmmap(kpgtbl, (uint64)etext, (uint64)etext, PHYSTOP-(uint64)etext, PTE_R | PTE_W);
    // 映射跳板页 (只读、可执行)
    kvmmap(kpgtbl, TRAMPOLINE, (uint64)trampoline, PGSIZE, PTE_R | PTE_X);
    // 为每个进程映射内核栈
    proc_mapstacks(kpgtbl);
    return kpgtbl;
}
```

函数 `proc_mapstacks` 会为每个进程分配一个物理页作为内核栈，并使用 `kvmmap` 将其映射到内核虚拟地址空间中一个特定的、受保护的位置（通常每个栈之间有一个“保护页”以防止溢出）。

---

## 函数 `uvmalloc` 与 `uvmdealloc`：管理用户地址空间大小 📏

用户进程的堆空间需要能够动态增长和收缩。`uvmalloc` 和 `uvmdealloc` 函数分别用于扩展和缩小用户虚拟地址空间。

**`uvmalloc`**：当进程需要更多内存时（例如通过 `sbrk` 系统调用），此函数被调用。
*   **输入**：用户页表 `pagetable`，旧大小 `oldsz`，新大小 `newsz`。
*   **逻辑**：
    1.  将 `oldsz` 向上舍入到页边界。
    2.  循环分配新的物理页，并调用 `mappages` 将其映射到从舍入后地址开始的虚拟地址空间。
    3.  新页的权限设置为可读、可写、用户可访问（`PTE_R | PTE_W | PTE_U`）。
    4.  如果任何一步失败（如 `kalloc` 失败），则调用 `uvmdealloc` 回滚所有已分配的页，并返回 0。
    5.  成功则返回 `newsz`。

**`uvmdealloc`**：当进程释放内存或 `uvmalloc` 需要回滚时，此函数被调用。
*   **输入**：用户页表 `pagetable`，旧大小 `oldsz`，新大小 `newsz`。
*   **逻辑**：
    1.  检查 `newsz` 是否小于 `oldsz`，如果不是，则不进行收缩。
    2.  计算需要释放的页数：`(PGROUNDUP(oldsz) - PGROUNDUP(newsz)) / PGSIZE`。
    3.  调用 `uvmunmap` 函数，从虚拟地址 `PGROUNDUP(newsz)` 开始，取消映射指定数量的页，并释放对应的物理页（如果 `do_free` 参数为真）。
    4.  返回 `newsz`。

---

## 函数 `uvmcopy`：复制用户地址空间 (用于 fork) 👯‍♂️

`fork` 系统调用需要复制父进程的整个用户地址空间给子进程。`uvmcopy` 函数实现了这个功能。

*   **输入**：父进程页表 `old`，子进程页表 `new`，父进程地址空间大小 `sz`。
*   **逻辑**：
    1.  遍历父进程地址空间的每一页（从 0 到 `sz`）。
    2.  对于每一页：
        *   使用 `walk` 找到父进程页表中对应的 PTE。
        *   获取该 PTE 指向的物理页地址和权限标志。
        *   为子进程分配一个新的物理页（`kalloc`）。
        *   将父进程物理页的内容复制到子进程的新物理页中（`memmove`）。
        *   调用 `mappages` 将子进程的新物理页映射到子进程页表中相同的虚拟地址，并设置相同的权限。
    3.  如果任何一步失败（如分配失败），则跳转到错误处理标签，调用 `uvmunmap` 释放子进程中已成功映射的所有页及其物理内存，并返回 -1。
    4.  成功复制所有页后返回 0。

---

## 函数 `copyin` / `copyout` / `copyinstr`：内核与用户空间的数据拷贝 🔄

内核经常需要从用户空间读取数据（如系统调用参数），或向用户空间写入数据（如系统调用结果）。由于用户空间可能跨页，且需要检查地址有效性，xv6 提供了专门的拷贝函数。

**`copyin`**：从用户虚拟地址空间拷贝数据到内核缓冲区。
*   **逻辑**：循环处理可能跨页的数据。每次迭代：
    1.  使用 `walkaddr`（内部调用 `walk`）将用户虚拟地址转换为物理地址。此函数会检查地址有效性和用户权限。
    2.  计算当前页内可拷贝的字节数。
    3.  使用 `memmove` 从转换得到的物理地址拷贝数据到内核目标地址。
    4.  更新指针和剩余长度。

**`copyout`**：从内核缓冲区拷贝数据到用户虚拟地址空间。
*   **逻辑**：与 `copyin` 几乎对称，只是方向相反。

**`copyinstr`**：从用户空间拷贝一个以空字符结尾的字符串到内核缓冲区，并防止缓冲区溢出。
*   **逻辑**：与 `copyin` 类似，但逐字节拷贝，并在遇到空字符 `\0` 或达到最大长度 `max` 时停止。如果成功拷贝到空字符，返回 0；如果达到最大长度仍未遇到空字符，返回 -1。

---

## 其他重要函数概览

*   **`uvmcreate`**：创建一个空的用户页表（仅分配根页表并清零）。
*   **`uvmfree`**：释放整个用户地址空间。它先调用 `uvmunmap` 释放所有用户页（数据页和页表项），然后调用 `freewalk` 递归释放页表树本身的所有层级页表。
*   **`freewalk`**：递归地释放页表树。它遍历一个页表，对所有有效的、指向下一级页表（非叶子节点）的 PTE，递归调用自身释放下级页表，最后释放当前页表页。
*   **`walkaddr`**：将用户虚拟地址转换为物理地址。它调用 `walk`（`alloc=0`），并检查 PTE 的有效性和用户权限位。

---

![](img/5e964734889d7046269d2bd5a76227f8_4.png)

## 总结 🎯

![](img/5e964734889d7046269d2bd5a76227f8_6.png)

本节课中我们一起深入学习了 xv6 操作系统中虚拟内存管理的核心函数。我们从遍历页表的 `walk` 函数开始，了解了如何查找和创建页表项。接着，我们分析了建立地址映射的 `mappages`，以及构建内核页表的 `kvmmake`。然后，我们探讨了管理用户地址空间动态大小的 `uvmalloc` 和 `uvmdealloc`，以及用于 `fork` 系统调用的 `uvmcopy` 函数。最后，我们学习了在内核与用户空间之间安全拷贝数据的 `copyin`、`copyout` 和 `copyinstr` 函数。这些函数共同构成了 xv6 内存管理子系统的基础，确保了进程隔离、内存分配和高效的系统调用数据传递。