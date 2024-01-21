# 文件系统：复习问题

> 问题编号可能会更改

## 问题 1

编写一个使用 fseek 和 ftell 的函数，将文件的中间字符替换为'X'

```cpp
void xout(char* filename) {
  FILE *f = fopen(filename, ____ );

}
```

## 问题 2

在`ext2`文件系统中，从磁盘读取多少个 inode 才能访问文件`/dir1/subdirA/notes.txt`的第一个字节？假设根目录中的目录名称和 inode 编号（但不是 inode 本身）已经在内存中。

## 问题 3

在`ext2`文件系统中，必须从磁盘读取多少个最小磁盘块才能访问文件`/dir1/subdirA/notes.txt`的第一个字节？假设根目录中的目录名称和 inode 编号以及所有 inode 已经在内存中。

## 问题 4

在具有 32 位地址和 4KB 磁盘块的`ext2`文件系统中，一个 inode 可以存储 10 个直接磁盘块编号。需要多大的文件大小才需要单一间接表？ii）双重间接表？

## 问题 5

修复下面的 shell 命令`chmod`，以设置文件`secret.txt`的权限，使所有者可以读取、写入和执行权限，组可以读取，其他人没有访问权限。

```cpp
chmod 000 secret.txt 
```
