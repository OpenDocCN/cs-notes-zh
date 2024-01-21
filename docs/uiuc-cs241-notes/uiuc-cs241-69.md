# 文件系统，第五部分：虚拟文件系统

## 虚拟文件系统

POSIX 系统，如 Linux 和基于 BSD 的 Mac OSX，包括几个作为文件系统的一部分挂载（可用）的虚拟文件系统。这些虚拟文件系统中的文件不存在于磁盘上；当进程请求目录列表时，它们由内核动态生成。Linux 提供了 3 个主要的虚拟文件系统

```cpp
/dev  - A list of physical and virtual devices (for example network card, cdrom, random number generator)
/proc - A list of resources used by each process and (by tradition) set of system information
/sys - An organized list of internal kernel entities 
```

例如，如果我想要一个连续的 0 流，我可以`cat /dev/zero`。

## 如何找出当前有哪些文件系统可用（已挂载）？

使用`mount`，不带任何选项地使用 mount 会生成一个列表（每行一个文件系统）已挂载的文件系统，包括网络、虚拟和本地（旋转磁盘/基于 SSD 的）文件系统。以下是 mount 的典型输出

```cpp
$ mount
/dev/mapper/cs241--server_sys-root on / type ext4 (rw)
proc on /proc type proc (rw)
sysfs on /sys type sysfs (rw)
devpts on /dev/pts type devpts (rw,gid=5,mode=620)
tmpfs on /dev/shm type tmpfs (rw,rootcontext="system_u:object_r:tmpfs_t:s0")
/dev/sda1 on /boot type ext3 (rw)
/dev/mapper/cs241--server_sys-srv on /srv type ext4 (rw)
/dev/mapper/cs241--server_sys-tmp on /tmp type ext4 (rw)
/dev/mapper/cs241--server_sys-var on /var type ext4 (rw)rw,bind)
/srv/software/Mathematica-8.0 on /software/Mathematica-8.0 type none (rw,bind)
engr-ews-homes.engr.illinois.edu:/fs1-homes/angrave/linux on /home/angrave type nfs (rw,soft,intr,tcp,noacl,acregmin=30,vers=3,sec=sys,sloppy,addr=128.174.252.102) 
```

请注意，每行都包括文件系统类型、文件系统源和挂载点。为了减少这种输出，我们可以将其导入到`grep`中，只看到与正则表达式匹配的行。

```cpp
>mount | grep proc  # only see lines that contain 'proc'
proc on /proc type proc (rw)
none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw) 
```

## random 和 urandom 之间的区别？

/dev/random 是一个包含数字生成器的文件，其中熵是从环境噪声中确定的。随机将阻塞/等待，直到从环境中收集到足够的熵。

/dev/urandom 就像 random 一样，但不同之处在于它允许重复（熵阈值较低），因此不会阻塞。

## 其他文件系统

```cpp
$ cat /proc/sys/kernel/random/entropy_avail
$ hexdump /dev/random
$ hexdump /dev/urandom

$ cat /proc/meminfo
$ cat /proc/cpuinfo
$ cat /proc/cpuinfo | grep bogomips

$ cat /proc/meminfo | grep Swap

$ cd /proc/self
$ echo $$; cd /proc/12345; cat maps 
```

## 挂载文件系统

假设我有一个挂接在`/dev/cdrom`上的文件系统，我想要从中读取。我必须在进行任何操作之前将其挂载到一个目录上。

```cpp
$ sudo mount /dev/cdrom /media/cdrom
$ mount
$ mount | grep proc 
```

## 如何挂载磁盘映像？

假设你下载了一个可引导的 Linux 磁盘映像...

```cpp
wget http://cosmos.cites.illinois.edu/pub/archlinux/iso/2015.04.01/archlinux-2015.04.01-dual.iso 
```

在将文件系统放入 CD 之前，我们可以将文件作为文件系统挂载并浏览其内容。请注意，挂载需要 root 访问权限，因此让我们使用 sudo 来运行它

```cpp
$ mkdir arch
$ sudo mount -o loop archlinux-2015.04.01-dual.iso ./arch
$ cd arch 
```

在挂载命令之前，arch 目录是新的，显然是空的。挂载后，`arch/`的内容将从存储在`archlinux-2014.11.01-dual.iso`文件中的文件和目录中提取出来。需要`loop`选项，因为我们想要挂载一个常规文件而不是物理磁盘这样的块设备。

loop 选项将原始文件包装为块设备-在这个例子中，我们将在下面找到文件系统是在`/dev/loop0`下提供的：我们可以通过运行不带任何参数的 mount 命令来检查文件系统类型和挂载选项。我们将将输出导入到`grep`中，以便只看到包含'arch'的相关输出行(s)

```cpp
$ mount | grep arch
/home/demo/archlinux-2014.11.01-dual.iso on /home/demo/arch type iso9660 (rw,loop=/dev/loop0) 
```

iso9660 文件系统是最初为光学存储介质（即 CDRom）设计的只读文件系统。尝试更改文件系统的内容将失败

```cpp
$ touch arch/nocando
touch: cannot touch `/home/demo/arch/nocando': Read-only file system 
```

[转到文件系统：第六部分](https://github.com/angrave/SystemProgramming/wiki/File-System,-Part-6:-Memory-mapped-files-and-Shared-memory)
