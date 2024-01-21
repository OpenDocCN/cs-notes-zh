# 死锁复习问题

## 主题

Coffman 条件资源分配图餐厅哲学家

+   失败的 DP 解决方案

+   活锁 DP 解决方案

+   工作的 DP 解决方案：优缺点

## 问题

+   科夫曼条件是什么？

+   科夫曼条件的每个意思是什么？（例如，你能提供每个条件的定义吗？）

+   举一个打破科夫曼条件的真实例子。一个需要考虑的情况：画家，油漆，画笔等。你如何确保工作会完成？

+   能够识别餐厅哲学家代码何时导致死锁（或者不导致）。例如，如果你看到以下代码片段，哪个科夫曼条件没有满足？

```cpp
// Get both locks or none.
pthread_mutex_lock( a );
if( pthread_mutex_trylock( b ) ) { /*failed*/
   pthread_mutex_unlock( a );
   ...
}
```

+   如果一个线程调用

```cpp
  pthread_mutex_lock(m1) // success
  pthread_mutex_lock(m2) // blocks
```

还有另一个线程调用

```cpp
  pthread_mutex_lock(m2) // success
  pthread_mutex_lock(m1) // blocks
```

发生了什么，为什么？如果第三个线程调用`pthread_mutex_lock(m1)`会发生什么？

+   有多少进程被阻塞？通常情况下，假设一个进程能够完成，如果它能够获取下面列出的所有资源。

    +   P1 获取 R1

    +   P2 获取 R2

    +   P1 获取 R3

    +   P2 等待 R3

    +   P3 获取 R5

    +   P1 等待 R4

    +   P3 等待 R1

    +   P4 等待 R5

    +   P5 等待 R1

（画出资源图！）
