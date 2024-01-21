# UIUC CS241：众包系统编程书

欢迎来到 Angrave 的众包系统编程维基书！这个维基是由伊利诺伊大学的学生和教师共同建立的，是伊利诺伊大学 CS 的 Lawrence Angrave 的众包创作实验。

与本学期要求现有的纸质书籍不同，我们将在这里建立我们自己的资源集。

## 0\. HW0/资源

+   [HW0](/angrave/SystemProgramming/wiki/HW0)

+   [基本术语非正式词汇表](/angrave/SystemProgramming/wiki/%23Informal-Glossary)

+   [#Piazza：何时以及如何寻求帮助](/angrave/SystemProgramming/wiki/%23Piazza%3A-When-And-How-to-Ask-For-Help)

+   [编程技巧，第一部分](/angrave/SystemProgramming/wiki/Programming-Tricks%2C-Part-1)

+   系统编程短篇故事和歌曲[/angrave/SystemProgramming/wiki/System-Programming-Short-Stories-and-Songs]

## 1\. 学习 C

+   [C 编程，第一部分：介绍](/angrave/SystemProgramming/wiki/C-Programming%2C-Part-1%3A-Introduction)

+   [C 编程，第二部分：文本输入和输出](/angrave/SystemProgramming/wiki/C-Programming%2C-Part-2%3A-Text-Input-And-Output)

    +   [打印到流](https://github.com/angrave/SystemProgramming/wiki/C-Programming%2C-Part-2%3A-Text-Input-And-Output#printing-to-streams)

    +   [解析输入](https://github.com/angrave/SystemProgramming/wiki/C-Programming%2C-Part-2%3A-Text-Input-And-Output#parsing-input)

+   [C 编程，第三部分：常见陷阱](/angrave/SystemProgramming/wiki/C-Programming%2C-Part-3%3A-Common-Gotchas)

    +   [内存错误](https://github.com/angrave/SystemProgramming/wiki/C-Programming%2C-Part-3%3A-Common-Gotchas#memory-mistakes)

    +   [逻辑/编程流程](https://github.com/angrave/SystemProgramming/wiki/C-Programming%2C-Part-3%3A-Common-Gotchas#logic-and-program-flow-mistakes)

    +   [其他陷阱](https://github.com/angrave/SystemProgramming/wiki/C-Programming%2C-Part-3%3A-Common-Gotchas#other-gotchas)

+   [C 编程，第四部分：字符串和结构](/angrave/SystemProgramming/wiki/C-Programming%2C-Part-4%3A-Strings-and-Structs)

    +   [字符串](https://github.com/angrave/SystemProgramming/wiki/C-Programming%2C-Part-4%3A-Strings-and-Structs#strings-structs-and-gotchas)

    +   [结构](https://github.com/angrave/SystemProgramming/wiki/C-Programming%2C-Part-4%3A-Strings-and-Structs#so-whats-a-struct)

+   [C 编程，第五部分：调试](/angrave/SystemProgramming/wiki/C-Programming%2C-Part-5%3A-Debugging)

    +   [代码调试](https://github.com/angrave/SystemProgramming/wiki/C-Programming%2C-Part-5%3A-Debugging#in-code-debugging)

    +   [Valgrind](https://github.com/angrave/SystemProgramming/wiki/C-Programming%2C-Part-5%3A-Debugging#valgrind)

    +   [Tsan](https://github.com/angrave/SystemProgramming/wiki/C-Programming%2C-Part-5%3A-Debugging#tsan)

    +   [GDB](https://github.com/angrave/SystemProgramming/wiki/C-Programming%2C-Part-5%3A-Debugging#gdb)

+   [C 编程，复习问题](/angrave/SystemProgramming/wiki/C-Programming%2C-Review-Questions)

## 2\. 进程

+   [进程，第一部分：介绍](/angrave/SystemProgramming/wiki/Processes%2C-Part-1%3A-Introduction)

    +   [概述](https://github.com/angrave/SystemProgramming/wiki/Processes,-Part-1:-Introduction#overview)

    +   [进程内容](https://github.com/angrave/SystemProgramming/wiki/Processes,-Part-1:-Introduction#process-contents)

    +   [奖励：更多内容](https://github.com/angrave/SystemProgramming/wiki/Processes,-Part-1:-Introduction#process-functionslimitations-bonus)

+   [分叉，第一部分：介绍](/angrave/SystemProgramming/wiki/Forking%2C-Part-1%3A-Introduction)

    +   [介绍](https://github.com/angrave/SystemProgramming/wiki/Forking%2C-Part-1%3A-Introduction#intro-to-fork)

    +   [等待和执行](https://github.com/angrave/SystemProgramming/wiki/Forking%2C-Part-1%3A-Introduction#waiting-and-execing)

+   [分叉，第二部分：分叉，执行，等待](/angrave/SystemProgramming/wiki/Forking%2C-Part-2%3A-Fork%2C-Exec%2C-Wait)

    +   [模式](https://github.com/angrave/SystemProgramming/wiki/Forking,-Part-2:-Fork,-Exec,-Wait#the-pattern)

    +   [僵尸进程](https://github.com/angrave/SystemProgramming/wiki/Forking,-Part-2:-Fork,-Exec,-Wait#zombies)

+   [进程控制，第一部分：等待宏，使用信号](/angrave/SystemProgramming/wiki/Process-Control%2C-Part-1%3A-Wait-macros%2C-using-signals)

    +   [等待宏](https://github.com/angrave/SystemProgramming/wiki/Process-Control%2C-Part-1%3A-Wait-macros%2C-using-signals#wait-macros)

    +   [信号](https://github.com/angrave/SystemProgramming/wiki/Process-Control%2C-Part-1%3A-Wait-macros%2C-using-signals#signals)

+   [进程复习问题](/angrave/SystemProgramming/wiki/Processes-Review-Questions)

## 3\. 内存和分配器

+   [内存，第一部分：堆内存介绍](/angrave/SystemProgramming/wiki/Memory%2C-Part-1%3A-Heap-Memory-Introduction)

    +   [C 动态内存分配](https://github.com/angrave/SystemProgramming/wiki/Memory,-Part-1:-Heap-Memory-Introduction#c-dynamic-memory-allocation)

    +   [分配简介](https://github.com/angrave/SystemProgramming/wiki/Memory,-Part-1:-Heap-Memory-Introduction#intro-to-allocating)

+   [内存，第二部分：实现内存分配器](/angrave/SystemProgramming/wiki/Memory%2C-Part-2%3A-Implementing-a-Memory-Allocator)

    +   [内存分配器教程](https://github.com/angrave/SystemProgramming/wiki/Memory%2C-Part-2%3A-Implementing-a-Memory-Allocator#memory-allocator-tutorial)

+   [内存，第三部分：破坏堆栈示例](/angrave/SystemProgramming/wiki/Memory%2C-Part-3%3A-Smashing-the-Stack-Example)

+   [内存复习问题](/angrave/SystemProgramming/wiki/Memory-Review-Questions)

## 4\. Pthreads 简介

+   [Pthreads，第一部分：介绍](/angrave/SystemProgramming/wiki/Pthreads%2C-Part-1%3A-Introduction)

    +   [线程简介](https://github.com/angrave/SystemProgramming/wiki/Pthreads,-Part-1:-Introduction#intro-to-threads)

    +   [简单 Pthreads](https://github.com/angrave/SystemProgramming/wiki/Pthreads,-Part-1:-Introduction#simple-usage)

+   [Pthreads，第二部分：实际使用](/angrave/SystemProgramming/wiki/Pthreads%2C-Part-2%3A-Usage-in-Practice)

    +   [更多 pthread 函数](https://github.com/angrave/SystemProgramming/wiki/Pthreads,-Part-2:-Usage-in-Practice#more-pthread-functions)

    +   [竞争条件简介](https://github.com/angrave/SystemProgramming/wiki/Pthreads,-Part-2:-Usage-in-Practice#intro-to-race-conditions)

+   [Pthreads，第三部分：并行问题（奖励）](/angrave/SystemProgramming/wiki/Pthreads%2C-Part-3%3A-Parallel-Problems-%28Bonus%29)

+   [Pthread 复习问题](/angrave/SystemProgramming/wiki/Pthread-Review-Questions)

## 5\. 同步

+   [同步，第一部分：互斥锁](/angrave/SystemProgramming/wiki/Synchronization%2C-Part-1%3A-Mutex-Locks)

    +   [解决关键部分](https://github.com/angrave/SystemProgramming/wiki/Synchronization,-Part-1:-Mutex-Locks#solving-critical-sections)

    +   [互斥体陷阱](https://github.com/angrave/SystemProgramming/wiki/Synchronization,-Part-1:-Mutex-Locks#mutex-gotchas)

+   [同步，第二部分：计数信号量](/angrave/SystemProgramming/wiki/Synchronization%2C-Part-2%3A-Counting-Semaphores)

+   [同步，第三部分：使用互斥锁和信号量](/angrave/SystemProgramming/wiki/Synchronization%2C-Part-3%3A-Working-with-Mutexes-And-Semaphores)

    +   [线程安全堆栈](https://github.com/angrave/SystemProgramming/wiki/Synchronization%2C-Part-3%3A-Working-with-Mutexes-And-Semaphores#thread-safe-stack)

    +   [堆栈信号量](https://github.com/angrave/SystemProgramming/wiki/Synchronization%2C-Part-3%3A-Working-with-Mutexes-And-Semaphores#stack-semaphores)

+   [同步，第四部分：关键部分问题](/angrave/SystemProgramming/wiki/Synchronization%2C-Part-4%3A-The-Critical-Section-Problem)

    +   [候选解决方案](https://github.com/angrave/SystemProgramming/wiki/Synchronization%2C-Part-4%3A-The-Critical-Section-Problem#candidate-solutions)

    +   [有效的解决方案](https://github.com/angrave/SystemProgramming/wiki/Synchronization%2C-Part-4%3A-The-Critical-Section-Problem#working-solutions)

    +   [硬件解决方案](https://github.com/angrave/SystemProgramming/wiki/Synchronization%2C-Part-4%3A-The-Critical-Section-Problem#hardware-solutions)

+   [同步，第五部分：条件变量](/angrave/SystemProgramming/wiki/Synchronization%2C-Part-5%3A-Condition-Variables)

    +   [条件变量简介](https://github.com/angrave/SystemProgramming/wiki/Synchronization%2C-Part-5%3A-Condition-Variables#intro-to-condition-variables)

    +   [实现计数信号量](https://github.com/angrave/SystemProgramming/wiki/Synchronization%2C-Part-5%3A-Condition-Variables#implementing-counting-semphore)

+   [同步，第六部分：实现屏障](/angrave/SystemProgramming/wiki/Synchronization%2C-Part-6%3A-Implementing-a-barrier)

+   [同步，第七部分：读者写者问题](/angrave/SystemProgramming/wiki/Synchronization%2C-Part-7%3A-The-Reader-Writer-Problem)

+   [同步，第八部分：环形缓冲区示例](/angrave/SystemProgramming/wiki/Synchronization%2C-Part-8%3A-Ring-Buffer-Example)

+   [同步复习问题](/angrave/SystemProgramming/wiki/Synchronization-Review-Questions)

## 6. 死锁

+   [死锁，第一部分：资源分配图](/angrave/SystemProgramming/wiki/Deadlock%2C-Part-1%3A-Resource-Allocation-Graph)

+   [死锁，第二部分：死锁条件](/angrave/SystemProgramming/wiki/Deadlock%2C-Part-2%3A-Deadlock-Conditions)

+   [死锁，第三部分：餐桌哲学家](/angrave/SystemProgramming/wiki/Deadlock%2C-Part-3%3A-Dining-Philosophers)

    +   [失败的解决方案](https://github.com/angrave/SystemProgramming/wiki/Deadlock,-Part-3:-Dining-Philosophers#failed-solutions)

    +   [可行的解决方案](https://github.com/angrave/SystemProgramming/wiki/Deadlock,-Part-3:-Dining-Philosophers#viable-solutions)

+   [死锁复习问题](/angrave/SystemProgramming/wiki/Deadlock-Review-Questions)

## 7. 进程间通信和调度

+   [虚拟内存，第一部分：虚拟内存简介](/angrave/SystemProgramming/wiki/Virtual-Memory%2C-Part-1%3A-Introduction-to-Virtual-Memory)

    +   [什么是虚拟内存？](https://github.com/angrave/SystemProgramming/wiki/Virtual-Memory%2C-Part-1%3A-Introduction-to-Virtual-Memory#what-is-virtual-memory)

    +   [高级帧和保护](https://github.com/angrave/SystemProgramming/wiki/Virtual-Memory%2C-Part-1%3A-Introduction-to-Virtual-Memory#advanced-frames-and-page-protections)

+   [管道，第一部分：管道简介](/angrave/SystemProgramming/wiki/Pipes%2C-Part-1%3A-Introduction-to-pipes)

+   [管道，第二部分：管道编程秘密](/angrave/SystemProgramming/wiki/Pipes%2C-Part-2%3A-Pipe-programming-secrets)

    +   [管道陷阱](https://github.com/angrave/SystemProgramming/wiki/Pipes%2C-Part-2%3A-Pipe-programming-secrets#pipe-gotchas)

    +   [命名管道](https://github.com/angrave/SystemProgramming/wiki/Pipes%2C-Part-2%3A-Pipe-programming-secrets#named-pipes)

+   [文件，第一部分：文件操作](/angrave/SystemProgramming/wiki/Files%2C-Part-1%3A-Working-with-files)

+   [调度，第一部分：调度进程](/angrave/SystemProgramming/wiki/Scheduling%2C-Part-1%3A-Scheduling-Processes)

    +   [考虑调度](https://github.com/angrave/SystemProgramming/wiki/Scheduling%2C-Part-1%3A-Scheduling-Processes#thinking-about-scheduling)

    +   [效率措施](https://github.com/angrave/SystemProgramming/wiki/Scheduling%2C-Part-1%3A-Scheduling-Processes#measures-of-efficiency)

+   [调度，第二部分：调度进程：算法](/angrave/SystemProgramming/wiki/Scheduling%2C-Part-2%3A-Scheduling-Processes%3A-Algorithms)

+   [IPC 复习问题](/angrave/SystemProgramming/wiki/IPC-Review-Questions)

## 8. 网络

+   [POSIX，第一部分：错误处理](/angrave/SystemProgramming/wiki/POSIX%2C-Part-1%3A-Error-handling)

+   [网络，第一部分：介绍](/angrave/SystemProgramming/wiki/Networking%2C-Part-1%3A-Introduction)

+   [网络，第二部分：使用 getaddrinfo](/angrave/SystemProgramming/wiki/Networking%2C-Part-2%3A-Using-getaddrinfo)

+   [网络，第三部分：构建一个简单的 TCP 客户端](/angrave/SystemProgramming/wiki/Networking%2C-Part-3%3A-Building-a-simple-TCP-Client)

+   [网络，第四部分：构建一个简单的 TCP 服务器](/angrave/SystemProgramming/wiki/Networking%2C-Part-4%3A-Building-a-simple-TCP-Server)

+   [网络，第五部分：关闭端口，重用端口和其他技巧](/angrave/SystemProgramming/wiki/Networking%2C-Part-5%3A-Shutting-down-ports%2C-reusing-ports-and-other-tricks)

+   [网络，第六部分：创建一个 UDP 服务器](/angrave/SystemProgramming/wiki/Networking%2C-Part-6%3A-Creating-a-UDP-server)

+   [网络，第七部分：非阻塞 I O，select()和 epoll](/angrave/SystemProgramming/wiki/Networking%2C-Part-7%3A-Nonblocking-I-O%2C-select%28%29%2C-and-epoll)

+   [RPC，第一部分：远程过程调用简介](/angrave/SystemProgramming/wiki/RPC%2C-Part-1%3A-Introduction-to-Remote-Procedure-Calls)

+   [网络复习问题](/angrave/SystemProgramming/wiki/Networking-Review-Questions)

## 9. 文件系统

+   [文件系统，第一部分：介绍](/angrave/SystemProgramming/wiki/File-System%2C-Part-1%3A-Introduction)

    +   [导航/术语](https://github.com/angrave/SystemProgramming/wiki/File-System%2C-Part-1%3A-Introduction#navigationterminology)

    +   [什么是文件系统？](https://github.com/angrave/SystemProgramming/wiki/File-System%2C-Part-1%3A-Introduction#so-whats-a-file-system)

+   [文件系统，第二部分：文件是索引节点（其他一切都是数据...）](/angrave/SystemProgramming/wiki/File-System%2C-Part-2%3A-Files-are-inodes-%28everything-else-is-just-data...%29)

+   [文件系统，第三部分：权限](/angrave/SystemProgramming/wiki/File-System%2C-Part-3%3A-Permissions)

+   [文件系统，第四部分：与目录一起工作](/angrave/SystemProgramming/wiki/File-System%2C-Part-4%3A-Working-with-directories)

+   [文件系统，第五部分：虚拟文件系统](/angrave/SystemProgramming/wiki/File-System%2C-Part-5%3A-Virtual-file-systems)

+   [文件系统，第六部分：内存映射文件和共享内存](/angrave/SystemProgramming/wiki/File-System%2C-Part-6%3A-Memory-mapped-files-and-Shared-memory)

+   [文件系统，第七部分：可扩展和可靠的文件系统](/angrave/SystemProgramming/wiki/File-System%2C-Part-7%3A-Scalable-and-Reliable-Filesystems)

    +   [单磁盘的可靠性](https://github.com/angrave/SystemProgramming/wiki/File-System%2C-Part-7%3A-Scalable-and-Reliable-Filesystems#reliable-single-disk-filesystems)

    +   [冗余](https://github.com/angrave/SystemProgramming/wiki/File-System%2C-Part-7%3A-Scalable-and-Reliable-Filesystems#redundancy)

+   [文件系统，第八部分：从 Android 设备中删除预装的恶意软件](/angrave/SystemProgramming/wiki/File-System%2C-Part-8%3A-Removing-preinstalled-malware-from-an-Android-device)

+   [文件系统，第九部分：磁盘块示例](/angrave/SystemProgramming/wiki/File-System%2C-Part-9%3A-Disk-blocks-example)

+   [文件系统复习问题](/angrave/SystemProgramming/wiki/File-Systems-Review-Questions)

## 10. 信号

+   [进程控制，第一部分：等待宏，使用信号](/angrave/SystemProgramming/wiki/Process-Control%2C-Part-1%3A-Wait-macros%2C-using-signals)

    +   [等待宏](https://github.com/angrave/SystemProgramming/wiki/Process-Control%2C-Part-1%3A-Wait-macros%2C-using-signals#wait-macros)

    +   [信号](https://github.com/angrave/SystemProgramming/wiki/Process-Control%2C-Part-1%3A-Wait-macros%2C-using-signals#signals)

+   [信号，第二部分：待处理信号和信号掩码](/angrave/SystemProgramming/wiki/Signals%2C-Part-2%3A-Pending-Signals-and-Signal-Masks)

    +   [深入了解信号](https://github.com/angrave/SystemProgramming/wiki/Signals,-Part-2:-Pending-Signals-and-Signal-Masks#signals-in-depth)

    +   [线程/子进程中的处理](https://github.com/angrave/SystemProgramming/wiki/Signals,-Part-2:-Pending-Signals-and-Signal-Masks#disposition-in-threadschildren)

+   [信号，第三部分：引发信号](/angrave/SystemProgramming/wiki/Signals%2C-Part-3%3A-Raising-signals)

+   [信号，第四部分：Sigaction](/angrave/SystemProgramming/wiki/Signals%2C-Part-4%3A-Sigaction)

+   [信号复习问题](/angrave/SystemProgramming/wiki/Signals-Review-Questions)

## 考试练习问题

警告：这些是很好的练习，但不全面。CS241 期末考试假设您完全理解并能应用课程的所有主题。问题将主要但不完全集中在您在实验和编程作业中使用过的主题上。

+   [考试主题](/angrave/SystemProgramming/wiki/Exam-Topics)

+   [C 编程：复习问题](/angrave/SystemProgramming/wiki/C-Programming%3A-Review-Questions)

+   [多线程编程：复习问题](/angrave/SystemProgramming/wiki/Multi-threaded-Programming%3A-Review-Questions)

+   [同步概念：复习问题](/angrave/SystemProgramming/wiki/Synchronization-Concepts%3A-Review-Questions)

+   [内存：复习问题](/angrave/SystemProgramming/wiki/Memory%3A-Review-Questions)

+   [管道：复习问题](/angrave/SystemProgramming/wiki/Pipe%3A-Review-Questions)

+   [文件系统：复习问题](/angrave/SystemProgramming/wiki/Filesystem%3A-Review-Questions)

+   [网络：复习问题](/angrave/SystemProgramming/wiki/Networking%3A-Review-Questions)

+   [信号：复习问题](/angrave/SystemProgramming/wiki/Signals%3A-Review-Questions) (待办)

+   [系统编程笑话](/angrave/SystemProgramming/wiki/System-Programming-Jokes)
