# 32：fs.c 文件系统代码详解（第一部分）

![](img/f494b40042117d97dc83af82abaa6a30_0.png)

在本节课中，我们将学习 xv6 文件系统核心代码文件 `fs.c` 中的一系列函数。我们将从初始化函数开始，逐步深入到文件创建、数据块管理以及索引节点（inode）缓存的操作。本教程将详细解释每个函数的逻辑，确保初学者能够理解其工作原理。

## 概述

`fs.c` 文件包含了 xv6 文件系统的核心实现。由于函数数量众多，我们将其分为两部分进行讲解。本视频（第一部分）将涵盖初始化、数据块分配与释放、索引节点缓存管理以及文件截断等核心功能。在下一部分中，我们将继续讲解文件读写、路径名解析等高级功能。

## 初始化函数

![](img/f494b40042117d97dc83af82abaa6a30_2.png)

上一节我们介绍了文件系统的整体结构，本节中我们来看看系统启动时如何初始化文件系统组件。

### 文件系统初始化 (`fsinit`)

系统启动后，第一个用户进程会调用 `fsinit` 函数。该函数负责读取磁盘上的超级块（superblock）并初始化日志系统。

```c
void fsinit(int dev) {
    readsb(dev, &sb);
    if(sb.magic != FSMAGIC)
        panic("invalid file system");
    initlog(dev, &sb);
}
```

**代码解释**：
1.  `readsb` 函数从指定设备读取超级块到内存中的 `sb` 结构体。
2.  检查超级块的魔数（`magic`）以确保文件系统类型正确。
3.  调用 `initlog` 初始化日志系统，此后系统可以开始事务操作（如 `begin_op`, `end_op`）。

### 缓冲区缓存初始化 (`binit`)

在 `main` 函数中，会调用 `binit` 来初始化与缓冲区缓存相关的数据。

### 索引节点表初始化 (`iinit`)

索引节点缓存是一个包含 50 个 `inode` 结构的数组，由一个自旋锁保护整个数组，每个结构还有自己的睡眠锁。

```c
void iinit() {
    initlock(&itable.lock, "itable");
    for(i = 0; i < NINODE; i++) {
        initsleeplock(&itable.inode[i].lock, "inode");
    }
}
```

**代码解释**：
1.  初始化保护整个索引节点表（`itable`）的自旋锁。
2.  遍历数组，初始化每个 `inode` 结构体的睡眠锁。
3.  每个结构的引用计数（`ref`）默认初始化为 0，表示该条目未被使用。

## 数据块管理

文件系统需要管理磁盘上的数据块，包括分配空闲块和释放已使用的块。

### 分配数据块 (`balloc`)

每当创建或扩展一个普通文件时，都需要在磁盘上找到一个未使用的数据块，将其清零，然后分配给文件。`balloc` 函数负责此操作。

```c
static uint balloc(uint dev) {
    for(b = 0; b < sb.size; b += BPB) {
        bp = bread(dev, BBLOCK(b, sb));
        for(bi = 0; bi < BPB && b + bi < sb.size; bi++) {
            m = 1 << (bi % 8);
            if((bp->data[bi/8] & m) == 0) {
                bp->data[bi/8] |= m;
                log_write(bp);
                brelse(bp);
                bzero(dev, b + bi);
                return b + bi;
            }
        }
        brelse(bp);
    }
    panic("balloc: out of blocks");
}
```

**算法流程**：
1.  外层循环遍历位图的所有块（`b` 以每块位数 `BPB` 递增）。
2.  对于每个位图块，调用 `bread` 读入缓冲区。
3.  内层循环遍历该块中的所有位（`bi`）。
4.  计算字节内位的位置并创建掩码 `m`。
5.  如果该位为 0（表示空闲），则将其置 1，通过 `log_write` 写回磁盘，然后释放缓冲区。
6.  调用 `bzero` 将新分配的数据块清零，最后返回块号。
7.  如果搜索完所有位图都未找到空闲块，则系统崩溃。

### 释放数据块 (`bfree`)

当文件被删除或缩小时，需要将其占用的数据块归还给空闲池。`bfree` 函数负责此操作。

```c
void bfree(int dev, uint b) {
    bp = bread(dev, BBLOCK(b, sb));
    bi = b % BPB;
    m = 1 << (bi % 8);
    if((bp->data[bi/8] & m) == 0)
        panic("freeing free block");
    bp->data[bi/8] &= ~m;
    log_write(bp);
    brelse(bp);
}
```

**算法流程**：
1.  根据块号 `b` 计算其对应的位图块，并读入缓冲区。
2.  计算块在位图块内的位偏移 `bi`。
3.  创建掩码 `m` 以定位特定位。
4.  检查该位是否已为 0（即已空闲），若是则报错。
5.  使用 `& ~m` 操作将该位清零。
6.  通过 `log_write` 将修改后的位图块写回磁盘，然后释放缓冲区。

## 索引节点缓存操作

文件系统通过索引节点缓存来高效管理正在使用的文件。主要操作包括获取、锁定、释放缓存条目。

### 获取索引节点 (`iget`)

当需要访问一个已存在的文件时，调用 `iget`。它在缓存中查找指定设备号和索引节点号的 `inode`。如果找到，则增加其引用计数并返回指针；如果未找到，则分配一个缓存条目。

```c
struct inode* iget(uint dev, uint inum) {
    acquire(&itable.lock);
    // 1. 查找缓存中是否已存在
    for(ip = &itable.inode[0]; ip < &itable.inode[NINODE]; ip++){
        if(ip->ref > 0 && ip->dev == dev && ip->inum == inum){
            ip->ref++;
            release(&itable.lock);
            return ip;
        }
    }
    // 2. 查找一个空闲条目（ref == 0）并分配
    for(ip = &itable.inode[0]; ip < &itable.inode[NINODE]; ip++){
        if(ip->ref == 0) {
            ip->dev = dev;
            ip->inum = inum;
            ip->ref = 1;
            ip->valid = 0; // 标记数据尚未从磁盘读入
            release(&itable.lock);
            return ip;
        }
    }
    panic("iget: no inodes");
}
```

**关键点**：
*   `iget` **不会**从磁盘读取 `inode` 数据，也不会对其加锁。
*   它只管理缓存条目的分配和引用计数。
*   新分配的条目 `valid` 字段为 0，表示其磁盘数据尚未加载。

### 锁定并读取索引节点 (`ilock`)

在对 `inode` 进行修改或确保其数据已就绪前，需要调用 `ilock`。它会获取该 `inode` 的睡眠锁，如果 `valid` 为 0，则从磁盘读取数据。

```c
void ilock(struct inode *ip) {
    if(ip == 0 || ip->ref < 1)
        panic("ilock");
    acquiresleep(&ip->lock);
    if(ip->valid == 0) {
        bp = bread(ip->dev, IBLOCK(ip->inum, sb));
        dip = (struct dinode*)bp->data + ip->inum % IPB;
        ip->type = dip->type;
        ip->major = dip->major;
        ip->minor = dip->minor;
        ip->nlink = dip->nlink;
        ip->size = dip->size;
        memmove(ip->addrs, dip->addrs, sizeof(ip->addrs));
        brelse(bp);
        ip->valid = 1;
        if(ip->type == 0)
            panic("ilock: no type");
    }
}
```

### 释放索引节点引用 (`iput`)

当一个进程完成对文件的操作后，需要调用 `iput` 来减少缓存 `inode` 的引用计数。如果引用计数降为 0，并且文件的硬链接数也为 0，则删除该文件（释放其所有数据块）。

```c
void iput(struct inode *ip) {
    acquire(&itable.lock);
    if(ip->ref == 1 && ip->valid && ip->nlink == 0) {
        // 这是最后一个引用，且文件已无硬链接，可以删除
        acquiresleep(&ip->lock);
        release(&itable.lock);
        itrunc(ip);        // 截断文件，释放所有数据块
        ip->type = 0;      // 标记 inode 类型为未使用
        iupdate(ip);       // 将 type=0 写回磁盘
        ip->valid = 0;     // 使缓存失效
        releasesleep(&ip->lock);
        acquire(&itable.lock);
    }
    ip->ref--; // 减少引用计数
    release(&itable.lock);
}
```

**关键逻辑**：
1.  检查是否是该 `inode` 的最后一个引用（`ref == 1`）且其硬链接数已为 0（`nlink == 0`）。
2.  如果是，则获取该 `inode` 的睡眠锁，然后释放全局表锁（避免长时间持有）。
3.  调用 `itrunc` 释放文件所有数据块。
4.  将 `inode` 类型置 0 并写回磁盘，标记为未使用。
5.  将缓存条目的 `valid` 置 0，防止后续 `ialloc` 错误重用旧缓存。
6.  最后减少引用计数。如果引用计数不为 0，文件仍保留在缓存中供其他进程使用。

### 解锁并释放 (`iunlockput`)

这是一个常用组合操作：先解锁 `inode` 的睡眠锁，然后调用 `iput` 释放引用。

```c
void iunlockput(struct inode *ip) {
    iunlock(ip);
    iput(ip);
}
```

## 文件创建与截断

### 分配索引节点 (`ialloc`)

当需要创建新文件（或目录）时，调用 `ialloc`。它在磁盘上查找一个类型为 0（未使用）的 `inode`，将其标记为已分配（设置类型），并返回其缓存版本。

```c
struct inode* ialloc(uint dev, short type) {
    for(inum = 1; inum < sb.ninodes; inum++) {
        bp = bread(dev, IBLOCK(inum, sb));
        dip = (struct dinode*)bp->data + inum % IPB;
        if(dip->type == 0) { // 找到空闲 inode
            memset(dip, 0, sizeof(*dip));
            dip->type = type;
            log_write(bp); // 将分配信息写入日志
            brelse(bp);
            return iget(dev, inum); // 获取缓存版本
        }
        brelse(bp);
    }
    panic("ialloc: no inodes");
}
```

**流程**：
1.  从 1 开始遍历所有可能的 `inode` 号（0 号无效）。
2.  读取每个 `inode` 所在的磁盘块。
3.  检查其 `type` 字段，若为 0 则表示空闲。
4.  将该 `inode` 在磁盘上的所有字段清零，然后设置其 `type`。
5.  通过 `log_write` 将修改写回磁盘。
6.  调用 `iget` 获取该 `inode` 的缓存版本并返回。注意，此时缓存中的 `valid` 为 0，后续 `ilock` 会读取数据。

### 更新索引节点到磁盘 (`iupdate`)

当内存中缓存的 `inode` 信息被修改后，必须调用 `iupdate` 将其写回磁盘。调用者必须持有该 `inode` 的睡眠锁。

```c
void iupdate(struct inode *ip) {
    bp = bread(ip->dev, IBLOCK(ip->inum, sb));
    dip = (struct dinode*)bp->data + ip->inum % IPB;
    dip->type = ip->type;
    dip->major = ip->major;
    dip->minor = ip->minor;
    dip->nlink = ip->nlink;
    dip->size = ip->size;
    memmove(dip->addrs, ip->addrs, sizeof(ip->addrs));
    log_write(bp);
    brelse(bp);
}
```

### 截断文件 (`itrunc`)

此函数将文件大小截断为 0，释放其所有数据块（包括直接块和间接块）。它被 `iput` 在删除文件时调用。

```c
void itrunc(struct inode *ip) {
    // 释放直接块
    for(i = 0; i < NDIRECT; i++) {
        if(ip->addrs[i]) {
            bfree(ip->dev, ip->addrs[i]);
            ip->addrs[i] = 0;
        }
    }
    // 释放间接块
    if(ip->addrs[NDIRECT]) {
        bp = bread(ip->dev, ip->addrs[NDIRECT]);
        a = (uint*)bp->data;
        for(j = 0; j < NINDIRECT; j++) {
            if(a[j])
                bfree(ip->dev, a[j]);
        }
        brelse(bp);
        bfree(ip->dev, ip->addrs[NDIRECT]); // 释放间接块本身
        ip->addrs[NDIRECT] = 0;
    }
    ip->size = 0;
    iupdate(ip); // 更新 inode 信息到磁盘
}
```

### 获取文件状态 (`stati`)

这是一个简单的辅助函数，将 `inode` 中的基本信息复制到 `stat` 结构体中，用于 `stat` 系统调用。调用者需持有 `inode` 锁。

```c
void stati(struct inode *ip, struct stat *st) {
    st->dev = ip->dev;
    st->ino = ip->inum;
    st->type = ip->type;
    st->nlink = ip->nlink;
    st->size = ip->size;
}
```

## 总结

本节课中我们一起学习了 xv6 文件系统 `fs.c` 文件前半部分的核心函数。我们详细探讨了：

1.  **初始化流程**：系统启动时如何读取超级块并初始化日志和索引节点缓存。
2.  **数据块管理**：如何使用位图来分配 (`balloc`) 和释放 (`bfree`) 磁盘数据块。
3.  **索引节点缓存**：通过 `iget`、`ilock`、`iunlock`、`iput` 这一套机制来高效、安全地管理正在使用的文件元数据。
4.  **文件生命周期操作**：如何创建新文件 (`ialloc`)，如何将修改写回磁盘 (`iupdate`)，以及如何删除文件 (`itrunc` 在 `iput` 中调用)。

这些函数共同构成了文件系统的基础设施，为上层文件操作（如打开、读写、查找）提供了支持。在下一部分中，我们将继续学习文件读写、目录操作以及路径名解析等更高级的功能。