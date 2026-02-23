# XV6 操作系统内核：31：Inodes 详解 🗂️

![](img/d4bb997f8b5f85a7b57b01018fb882d7_0.png)

在本节课中，我们将学习 XV6 操作系统中 Inode 的核心概念。我们将了解 Inode 在磁盘上的表示方式、在内存中的缓存机制，以及相关的数据结构和关键函数。通过本节内容，你将掌握文件系统如何通过 Inode 来组织和管理文件。

---

## 磁盘布局概览 📊

上一节我们介绍了文件系统的基本概念，本节中我们来看看 XV6 磁盘的具体布局。下图展示了磁盘的示意图，其中每个小方块代表一个磁盘块。

![](img/d4bb997f8b5f85a7b57b01018fb882d7_0.png)

磁盘布局包含以下几个关键区域：
*   **日志区**：用于事务日志记录。
*   **Inode 数组区**：存储所有 Inode 结构。
*   **位图区**：标记数据块的使用情况。
*   **数据块区**：存储常规文件和目录的实际数据。

位图中的每一位对应一个数据块，`1` 表示已使用，`0` 表示空闲。当需要为文件或目录分配新块时，内核会在此位图中查找空闲块。

---

## Inode 在磁盘上的结构 💾

让我们更深入地观察 Inode 数组区。该区域从超级块中 `inodestart` 字段指定的块号开始。这个数组由多个 `inode` 结构紧密排列组成。

每个磁盘上的 `inode` 结构包含以下字段：
*   **type**：文件类型（常规文件、目录或设备）。
*   **major** 与 **minor**：设备的主、次设备号（仅对设备文件有效）。
*   **nlink**：指向此文件的硬链接数量。
*   **size**：文件大小（字节数，对设备文件无效）。
*   **addrs[]**：一个包含 **12** 个直接块指针的数组。

如果文件大小超过 12 个块，系统将使用一个**间接块**。`addrs[12]` 指向一个磁盘块，该块本身不存储数据，而是存储 **256** 个指向其他数据块的指针。

因此，XV6 中单个文件的最大尺寸由以下公式决定：
`最大文件大小 = (直接指针数 + 间接块指针数) * 块大小`
`最大文件大小 = (12 + 256) * 1024 字节`

与支持双重、三重间接块的现代系统相比，XV6 的文件大小限制较为严格。

---

## Inode 在内存中的缓存 🧠

为了高效操作，内核会将正在使用的 Inode 读入内存进行缓存。内存中有一个名为 `itable` 的结构，它包含一个自旋锁和一个大小为 50 的 `inode` 结构数组。

以下是内存中缓存的 `inode` 结构（定义在 `file.h` 中）包含的字段：
```c
struct inode {
    uint dev;           // 设备号
    uint inum;          // Inode 编号
    int ref;            // 引用计数
    struct sleeplock lock; // 睡眠锁
    int valid;          // 数据是否已从磁盘读入的标志位
    short type;         // 文件类型
    short major;        // 主设备号
    short minor;        // 次设备号
    short nlink;        // 硬链接数
    uint size;          // 文件大小
    uint addrs[NDIRECT+1]; // 数据块地址数组
};
```

*   `dev` 和 `inum` 共同唯一标识一个文件。
*   `ref` 表示当前有多少个指针（或线程）正在使用此缓存 Inode。`ref` 为 0 表示该缓存槽位空闲。
*   `lock` 是一个睡眠锁，用于保护 `valid` 标志位及以下的所有字段（`type`, `size`, `addrs` 等）。
*   `valid` 标志位指示该 Inode 的元数据（如 `type`, `size`）是否已从磁盘读入。若为 0，则在需要访问时必须先从磁盘读取。

`itable` 中的自旋锁保护的是整个缓存数组的**分配状态**，即 `dev`、`inum` 和 `ref` 字段。

![](img/d4bb997f8b5f85a7b57b01018fb882d7_2.png)

---

## 设备切换表 ⚙️

XV6 通过一个名为 `devsw`（设备切换表）的数组来管理不同设备的驱动函数。该数组有 `NDEV`（默认为 10）个元素。

每个元素是一个包含 `read` 和 `write` 函数指针的结构体：
```c
struct devsw {
    int (*read)(int, uint64, int);
    int (*write)(int, uint64, int);
};
extern struct devsw devsw[NDEV];
```

例如，控制台设备（主设备号 1）就使用此表中的特定函数进行读写操作。`read` 和 `write` 函数的参数包括目标/源地址、字节数以及一个标识地址空间（内核物理地址或用户虚拟地址）的标志位。

---

## 关键头文件解析 📄

以下是 `fs.h` 和 `file.h` 中与 Inode 相关的核心定义：

**在 `fs.h` 中：**
*   `ROOTINO`：根目录的 Inode 编号，固定为 1。
*   `BSIZE`：磁盘块大小，固定为 1024 字节。
*   `NDIRECT`：直接指针数量，值为 12。
*   `NINDIRECT`：一个间接块能容纳的指针数，值为 `BSIZE / sizeof(uint)` = 256。
*   `MAXFILE`：最大文件块数，值为 `NDIRECT + NINDIRECT`。
*   `struct dinode`：磁盘上 Inode 的结构体定义，与内存版本对应，但不包含缓存管理字段。
*   `IPB`：每块磁盘能容纳的 Inode 数量，计算公式为 `BSIZE / sizeof(struct dinode)`。
*   `IBLOCK` 宏：根据 Inode 编号计算其所在的磁盘块号。
*   `BPB`：每个位图块包含的比特数，值为 `BSIZE * 8`。
*   `struct dirent`：目录项结构，包含一个 Inode 编号 (`inum`) 和一个最多 14 字符的文件名。

**在 `file.h` 中：**
*   `struct inode`：如前所述，内存中缓存的 Inode 结构。
*   `struct devsw`：如前所述，设备切换表项结构。

---

## 文件系统函数概览 🔧

`fs.c` 文件中包含了约 25 个管理文件系统的函数。在深入代码之前，我们先对这些函数进行简要介绍：

**初始化与块管理：**
*   `iinit()`: 初始化内存中的 Inode 缓存表 (`itable`)。
*   `fsinit(int dev)`: 初始化文件系统，读取超级块。
*   `bzero(int dev, int bno)`: 将指定块清零。
*   `balloc(uint dev)`: 分配一个空闲数据块，更新位图并返回块号。
*   `bfree(int dev, uint b)`: 释放一个数据块，更新位图。

**Inode 生命周期管理：**
*   `ialloc(uint dev, short type)`: 在磁盘上分配一个新的 Inode（类型为 `type`），将其读入内存缓存，并返回指针。它会设置磁盘 Inode 的 `type` 字段。
*   `iget(uint dev, uint inum)`: 根据设备号和 Inode 编号，在内存缓存中获取对应的 Inode 结构。如果尚未缓存，则分配一个缓存槽位。增加其引用计数 (`ref`)，但**不**对其加锁，也**不**保证数据 (`valid`) 已从磁盘读入。
*   `ilock(struct inode *ip)`: 对 Inode 加睡眠锁。如果 `valid` 为 0，则从磁盘读取其元数据。
*   `iunlock(struct inode *ip)`: 对 Inode 解锁。
*   `iupdate(struct inode *ip)`: 将内存中已修改的 Inode 元数据写回磁盘。
*   `idup(struct inode *ip)`: 增加 Inode 的引用计数。
*   `iput(struct inode *ip)`: 减少 Inode 的引用计数。如果引用计数和硬链接数 (`nlink`) 都降为 0，则调用 `itrunc` 释放文件占用的所有数据块，并将磁盘 Inode 的 `type` 置 0 以标记为空闲。
*   `itrunc(struct inode *ip)`: 将文件截断为长度 0，释放其所有数据块和间接块。

**数据访问与路径解析：**
*   `bmap(struct inode *ip, uint bn)`: 将文件内的逻辑块号 `bn` 转换为磁盘上的物理块号。如果需要，会分配新的数据块。
*   `readi(struct inode *ip, int user_dst, uint64 dst, uint off, uint n)`: 从文件的偏移 `off` 处读取 `n` 字节到内存地址 `dst`。
*   `writei(struct inode *ip, int user_src, uint64 src, uint off, uint n)`: 从内存地址 `src` 写入 `n` 字节到文件的偏移 `off` 处。
*   `dirlookup(struct inode *dp, char *name, uint *poff)`: 在目录 `dp` 中查找文件名 `name`。如果找到，则通过 `iget` 获取其 Inode，并可在 `poff` 中返回目录项偏移量。
*   `dirlink(struct inode *dp, char *name, uint inum)`: 在目录 `dp` 中创建一个新的目录项，将 `name` 链接到 Inode 编号 `inum`。
*   `skipelem(char *path, char *name)`: 解析路径名，提取第一个组成部分到 `name`，并返回指向路径剩余部分的指针。
*   `namex(char *path, int nameiparent, char *name)`: 路径名解析的核心函数，根据 `nameiparent` 标志决定是解析到最后一级（返回目标 Inode）还是倒数第二级（返回父目录 Inode 并保存最后一级名称）。
*   `namei(char *path)` 与 `nameiparent(char *path, char *name)`: 对外接口，封装了对 `namex` 的调用，分别用于获取目标 Inode 和父目录 Inode。

**重要提示**：以上所有涉及磁盘读写的函数（如 `readi`, `writei`, `iupdate`）本身**并不**包含事务（transaction）的开始 (`begin_op`) 和结束 (`end_op`)。它们被设计为在由更高层函数发起的事务上下文中被调用，通过日志系统来保证操作的原子性。

---

## 总结 📝

本节课中我们一起学习了 XV6 操作系统中 Inode 的核心机制。我们了解了 Inode 在磁盘上的物理布局与数据结构，以及在内核中如何通过缓存表 (`itable`) 进行高效管理。我们还浏览了 `fs.h` 和 `file.h` 中的关键定义，并对 `fs.c` 中负责 Inode 分配、释放、数据读写和路径解析的主要函数有了整体认识。理解这些基础组件是掌握 XV6 文件系统工作原理的关键。在下一节中，我们将深入这些函数的源代码，探究其具体实现细节。