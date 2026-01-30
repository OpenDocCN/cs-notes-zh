# 课程 P11：第10讲 从C线程到C++线程 🧵

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_1.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_2.png)

在本节课中，我们将学习如何从C语言的Pthreads过渡到C++11内置的线程库。我们将探讨C++线程的基本用法、如何传递参数、以及如何处理多线程编程中常见的竞争条件问题。

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_4.png)

---

## 期中考试安排 📝

上一节我们介绍了多进程和多线程的基本概念，本节中我们来看看本周的重要安排。

期中考试定于本周四晚上6点到8点，地点在Hewlett 200教室。考试将使用Blue Book系统进行。

以下是关于考试的重要信息列表：
*   考试形式为在笔记本电脑上使用Blue Book程序答题并提交。
*   考试内容加密，将在考前发布，进入考场后获得密码即可开始。
*   考试时长为两小时，但预计多数同学可在一个半小时内完成。
*   允许携带一张正反面写有个人笔记的纸张进入考场。
*   考试时会提供一份有限的参考资料，包含常用函数原型和常量。
*   如果需要特殊考试安排，请务必提前通过邮件联系老师。

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_6.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_8.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_9.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_11.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_13.png)

考试内容将涵盖信号处理、多进程编程等，形式与练习题相似，包括编程题和简答题。

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_15.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_17.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_19.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_21.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_23.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_25.png)

---

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_27.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_29.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_31.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_33.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_35.png)

## 本周作业：斯坦福Shell 🐚

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_37.png)

接下来，我们看看本周的作业。这是一个构建简易Shell的程序，名为“斯坦福Shell”(Stanford Shell)。

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_39.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_41.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_43.png)

这个作业要求你实现一个功能相对完整的Shell，需要处理以下核心功能：
*   执行基本命令，并支持前台/后台运行。
*   使用 `jobs` 命令查看所有后台作业。
*   使用 `fg` 命令将后台作业调至前台。
*   使用 `bg` 命令重启一个已停止的后台作业。
*   使用 `slay` 命令向整个进程组发送信号以终止一组进程。
*   支持管道操作，例如 `ls | grep | cut`。
*   支持输入/输出重定向。
*   正确处理 `Ctrl+C` (SIGINT) 和 `Ctrl+Z` (SIGTSTP) 信号，使其影响前台进程而非Shell本身。

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_45.png)

作业的核心难点在于管理多个子进程、实现管道以及处理信号。建议按照提供的里程碑顺序完成，并充分利用测试驱动文件进行调试。作业截止日期为下周三。

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_47.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_49.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_51.png)

---

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_53.png)

## 从C的Pthreads到C++线程 🔄

现在，让我们正式进入C++线程的世界。与C的Pthreads相比，C++11内置的线程库语法更简洁，集成度更高。

C++线程同样共享进程内存，每个线程拥有独立的栈，但可以访问共享的全局数据。它们被认为是“轻量级进程”，能够真正在多核CPU上并行执行。

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_55.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_57.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_59.png)

### 基础示例：充电程序

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_61.png)

我们从一个简单的程序开始，创建多个线程，每个线程打印一条信息。

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_63.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_65.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_67.png)

```cpp
#include <iostream>
#include <thread>
#include <vector>
// 需要包含自定义的 oslock.h 来保证 cout 的线程安全
#include "oslock.h"

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_69.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_71.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_73.png)

void recharge() {
    oslock lock;
    std::cout << "I recharge by spending time alone." << std::endl;
    osunlock unlock;
}

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_75.png)

int main(int argc, char *argv[]) {
    const size_t kNumIntroverts = 6;
    std::vector<std::thread> introverts(kNumIntroverts);
    for (size_t i = 0; i < kNumIntroverts; ++i) {
        // 创建线程并执行 recharge 函数
        std::thread t(recharge);
        // 使用 swap 将线程对象移入数组
        introverts[i].swap(t);
    }
    for (std::thread& introvert : introverts) {
        introvert.join(); // 等待所有线程结束
    }
    return 0;
}
```
**关键点说明**：
*   `std::thread t(recharge)`：创建并启动一个执行 `recharge` 函数的新线程。
*   `introverts[i].swap(t)`：这是一个C++的“移动”操作，将新创建的线程对象 `t` 移入数组 `introverts`，避免不必要的拷贝。
*   `introvert.join()`：主线程等待该子线程执行完毕。

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_77.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_79.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_81.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_83.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_85.png)

---

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_87.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_89.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_91.png)

### 向线程传递参数 📨

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_93.png)

线程函数可以接受参数。C++线程库允许你以值传递或引用传递的方式向线程函数传参。

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_95.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_97.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_99.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_100.png)

以下是传递参数的示例程序：
```cpp
#include <iostream>
#include <thread>
#include <vector>
#include "oslock.h"

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_102.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_103.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_105.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_107.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_109.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_111.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_113.png)

void greeter(size_t id, size_t numTimes) {
    for (size_t i = 0; i < numTimes; ++i) {
        oslock lock;
        std::cout << "Greeter #" << id << " says 'Hello!'" << std::endl;
        osunlock unlock;
        // 模拟一些处理时间
        struct timespec ts = {0, random() % 1000000000};
        nanosleep(&ts, NULL);
    }
    oslock lock;
    std::cout << "Greeter #" << id << " has issued all greetings and goes home." << std::endl;
    osunlock unlock;
}

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_115.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_117.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_119.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_121.png)

int main(int argc, char *argv[]) {
    std::cout << "Welcome to Greetland!" << std::endl;
    const size_t kNumGreeters = 6;
    std::thread greeters[kNumGreeters];
    for (size_t i = 0; i < kNumGreeters; ++i) {
        // 创建线程，并传递参数 i+1 (值传递)
        greeters[i] = std::thread(greeter, i + 1, i + 1);
    }
    for (std::thread& greeter : greeters) {
        greeter.join();
    }
    std::cout << "Everyone has been greeted. The end." << std::endl;
    return 0;
}
```
**关键点说明**：
*   `std::thread(greeter, i + 1, i + 1)`：第一个 `greeter` 是函数名，后续参数 `i+1` 将按值传递给 `greeter` 函数。
*   若需传递引用，需使用 `std::ref()` 进行包装，例如 `std::ref(sharedVariable)`。

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_123.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_125.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_127.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_129.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_131.png)

---

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_133.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_135.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_137.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_139.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_141.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_143.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_145.png)

## 处理竞争条件与互斥锁 🔐

多线程访问共享资源时，会产生竞争条件。我们通过一个模拟售票的程序来演示这个问题及其解决方案。

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_147.png)

### 存在竞争条件的版本

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_149.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_150.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_152.png)

假设有多个售票代理线程共享一个剩余票数变量。
```cpp
size_t remainingTickets = 250; // 共享变量

void ticketAgent(size_t id, size_t& tickets) {
    while (tickets > 0) {
        // 模拟处理票务的时间
        handleCall();
        tickets--; // 非原子操作，存在竞争条件！
        oslock lock;
        std::cout << "Agent #" << id << " sold a ticket (" << tickets << " more to be sold)." << std::endl;
        osunlock unlock;
        takeBreak();
    }
    oslock lock;
    std::cout << "Agent #" << id << " notices all tickets are sold and goes home." << std::endl;
    osunlock unlock;
}
```
**问题**：`tickets--` 不是原子操作，多个线程可能同时读取、修改该变量，导致票数计算错误（如卖超或负数）。

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_154.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_156.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_158.png)

### 使用互斥锁解决问题

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_160.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_162.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_164.png)

互斥锁可以确保同一时间只有一个线程能进入被锁保护的“临界区”代码。
```cpp
#include <mutex>

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_166.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_168.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_170.png)

std::mutex ticketLock; // 全局互斥锁
size_t remainingTickets = 250;

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_172.png)

void ticketAgent(size_t id, size_t& tickets, std::mutex& lock) {
    while (true) {
        lock.lock(); // 加锁
        if (tickets == 0) {
            lock.unlock(); // 检查后立即解锁
            break;
        }
        tickets--; // 在锁的保护下修改共享变量
        size_t myTicket = tickets;
        lock.unlock(); // 尽快解锁，让其他线程进入

        // 在锁外执行耗时的操作（如打印、模拟工作）
        handleCall();
        oslock outLock;
        std::cout << "Agent #" << id << " sold a ticket (" << myTicket << " more to be sold)." << std::endl;
        osunlock outUnlock;
        takeBreak();
    }
    oslock lock;
    std::cout << "Agent #" << id << " notices all tickets are sold and goes home." << std::endl;
    osunlock unlock;
}

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_174.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_176.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_178.png)

int main() {
    std::thread agents[10];
    for (size_t i = 0; i < 10; ++i) {
        // 传递共享变量和互斥锁的引用
        agents[i] = std::thread(ticketAgent, 100 + i, std::ref(remainingTickets), std::ref(ticketLock));
    }
    for (std::thread& agent : agents) { agent.join(); }
    return 0;
}
```
**关键点说明**：
*   `std::mutex`：定义互斥锁。
*   `lock.lock()` / `lock.unlock()`：手动加锁与解锁。确保锁的粒度尽可能小，只包围访问共享资源的代码，避免长时间持有锁导致性能下降。
*   `std::ref()`：用于向线程函数传递引用类型的参数（如 `remainingTickets` 和 `ticketLock`）。

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_180.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_182.png)

---

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_184.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_186.png)

## 总结 🎯

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_188.png)

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_189.png)

本节课中我们一起学习了：
1.  **C++线程基础**：如何使用 `std::thread` 创建线程、传递参数以及使用 `join` 等待线程结束。
2.  **线程安全输出**：通过自定义的 `oslock`/`osunlock` 保证 `std::cout` 在多线程环境下的输出完整性。
3.  **竞争条件**：理解了多线程并发修改共享数据时导致的问题。
4.  **互斥锁**：掌握了使用 `std::mutex` 保护临界区，解决竞争条件的基本方法。记住要尽量缩短锁的持有时间以提高程序效率。

![](img/87f93b0bc9a9d8e944eb7fb7dd38f262_191.png)

从C的Pthreads到C++线程，我们拥有了更现代、更易用的工具来处理并发编程。在接下来的课程中，我们将探讨更高级的同步机制，如条件变量和信号量。