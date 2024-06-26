# Pthread 复习问题

## 主题

+   pthread 生命周期

+   每个线程都有一个堆栈

+   从线程中捕获返回值

+   使用`pthread_join`

+   使用`pthread_create`

+   使用`pthread_exit`

+   在什么条件下进程会退出

## 问题

+   当创建一个 pthread 时会发生什么？（你不需要进入超级细节）

+   每个线程的堆栈在哪里？

+   如何在给定`pthread_t`的情况下获得返回值？线程可以如何设置返回值？如果丢弃返回值会发生什么？

+   为什么`pthread_join`很重要（考虑堆栈空间、寄存器、返回值）？

+   在正常情况下`pthread_exit`做什么（即你不是最后一个线程）？调用 pthread_exit 时会调用哪些其他函数？

+   给我三个多线程进程将退出的条件。你还能想到其他条件吗？

+   什么是尴尬并行问题？
