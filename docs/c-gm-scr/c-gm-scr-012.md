# 012：多线程编程 🧵

![](img/6f18f54518e4455428d5825da1c39f49_1.png)

![](img/6f18f54518e4455428d5825da1c39f49_3.png)

![](img/6f18f54518e4455428d5825da1c39f49_4.png)

![](img/6f18f54518e4455428d5825da1c39f49_6.png)

![](img/6f18f54518e4455428d5825da1c39f49_8.png)

![](img/6f18f54518e4455428d5825da1c39f49_9.png)

在本节课中，我们将学习如何为游戏实现一个多线程作业系统。上一节我们完成了音频系统的基础构建，本节我们将解决音频系统的一些遗留问题，并重点介绍如何创建线程、管理作业队列，最终实现音频更新的异步处理，让游戏即使在主循环卡顿时也能流畅播放声音。

![](img/6f18f54518e4455428d5825da1c39f49_11.png)

![](img/6f18f54518e4455428d5825da1c39f49_13.png)

---

## 概述与回顾

![](img/6f18f54518e4455428d5825da1c39f49_15.png)

![](img/6f18f54518e4455428d5825da1c39f49_17.png)

![](img/6f18f54518e4455428d5825da1c39f49_19.png)

在上一节中，我们成功构建了音频系统，实现了播放音乐、调整音量、声像和循环等功能。然而，我们也遇到了一些问题，例如正弦波音频文件循环不正确，以及当同时播放的声音超过32个时程序会断言失败。

![](img/6f18f54518e4455428d5825da1c39f49_21.png)

![](img/6f18f54518e4455428d5825da1c39f49_23.png)

![](img/6f18f54518e4455428d5825da1c39f49_25.png)

![](img/6f18f54518e4455428d5825da1c39f49_27.png)

![](img/6f18f54518e4455428d5825da1c39f49_29.png)

![](img/6f18f54518e4455428d5825da1c39f49_31.png)

![](img/6f18f54518e4455428d5825da1c39f49_32.png)

![](img/6f18f54518e4455428d5825da1c39f49_34.png)

本节我们将首先修复音频系统的两个小问题，然后深入探讨多线程编程的核心概念，并构建一个作业系统。这个系统将允许我们将音频更新、资源加载等任务放到独立的线程中执行，从而提升游戏的响应性和性能。

![](img/6f18f54518e4455428d5825da1c39f49_36.png)

![](img/6f18f54518e4455428d5825da1c39f49_38.png)

![](img/6f18f54518e4455428d5825da1c39f49_40.png)

![](img/6f18f54518e4455428d5825da1c39f49_42.png)

---

![](img/6f18f54518e4455428d5825da1c39f49_44.png)

![](img/6f18f54518e4455428d5825da1c39f49_46.png)

![](img/6f18f54518e4455428d5825da1c39f49_47.png)

![](img/6f18f54518e4455428d5825da1c39f49_49.png)

![](img/6f18f54518e4455428d5825da1c39f49_50.png)

![](img/6f18f54518e4455428d5825da1c39f49_51.png)

![](img/6f18f54518e4455428d5825da1c39f49_52.png)

![](img/6f18f54518e4455428d5825da1c39f49_53.png)

![](img/6f18f54518e4455428d5825da1c39f49_55.png)

![](img/6f18f54518e4455428d5825da1c39f49_57.png)

## 修复音频系统遗留问题

![](img/6f18f54518e4455428d5825da1c39f49_59.png)

![](img/6f18f54518e4455428d5825da1c39f49_61.png)

上一节我们遗留了两个主要问题：正弦波文件循环异常和声音数量限制。

![](img/6f18f54518e4455428d5825da1c39f49_63.png)

![](img/6f18f54518e4455428d5825da1c39f49_65.png)

![](img/6f18f54518e4455428d5825da1c39f49_67.png)

![](img/6f18f54518e4455428d5825da1c39f49_69.png)

![](img/6f18f54518e4455428d5825da1c39f49_71.png)

![](img/6f18f54518e4455428d5825da1c39f49_73.png)

### 1. 修复音频文件问题

![](img/6f18f54518e4455428d5825da1c39f49_75.png)

![](img/6f18f54518e4455428d5825da1c39f49_76.png)

![](img/6f18f54518e4455428d5825da1c39f49_78.png)

![](img/6f18f54518e4455428d5825da1c39f49_80.png)

![](img/6f18f54518e4455428d5825da1c39f49_82.png)

![](img/6f18f54518e4455428d5825da1c39f49_84.png)

![](img/6f18f54518e4455428d5825da1c39f49_85.png)

经过检查，发现循环问题并非我们的代码错误，而是使用的正弦波音频文件本身有问题。我们只需替换一个正确的音频文件即可解决。

![](img/6f18f54518e4455428d5825da1c39f49_87.png)

![](img/6f18f54518e4455428d5825da1c39f49_89.png)

![](img/6f18f54518e4455428d5825da1c39f49_91.png)

![](img/6f18f54518e4455428d5825da1c39f49_92.png)

![](img/6f18f54518e4455428d5825da1c39f49_94.png)

![](img/6f18f54518e4455428d5825da1c39f49_96.png)

**解决方案：**
用正确的 `sine_wave.ogg` 文件替换 `data/` 目录下的旧文件。

![](img/6f18f54518e4455428d5825da1c39f49_98.png)

![](img/6f18f54518e4455428d5825da1c39f49_100.png)

### 2. 实现声音空闲列表（Free List）

![](img/6f18f54518e4455428d5825da1c39f49_102.png)

![](img/6f18f54518e4455428d5825da1c39f49_104.png)

![](img/6f18f54518e4455428d5825da1c39f49_105.png)

![](img/6f18f54518e4455428d5825da1c39f49_106.png)

![](img/6f18f54518e4455428d5825da1c39f49_108.png)

![](img/6f18f54518e4455428d5825da1c39f49_109.png)

当前系统最多只能同时播放32个声音。为了更高效地管理声音实例，避免断言失败，我们实现一个简单的空闲列表。

![](img/6f18f54518e4455428d5825da1c39f49_111.png)

![](img/6f18f54518e4455428d5825da1c39f49_113.png)

![](img/6f18f54518e4455428d5825da1c39f49_115.png)

![](img/6f18f54518e4455428d5825da1c39f49_117.png)

![](img/6f18f54518e4455428d5825da1c39f49_119.png)

![](img/6f18f54518e4455428d5825da1c39f49_121.png)

![](img/6f18f54518e4455428d5825da1c39f49_122.png)

![](img/6f18f54518e4455428d5825da1c39f49_124.png)

![](img/6f18f54518e4455428d5825da1c39f49_126.png)

![](img/6f18f54518e4455428d5825da1c39f49_127.png)

![](img/6f18f54518e4455428d5825da1c39f49_128.png)

![](img/6f18f54518e4455428d5825da1c39f49_129.png)

**核心概念：**
我们维护一个指向第一个空闲声音的索引 (`first_free_sound`)。当需要播放新声音时，首先尝试从空闲列表中获取，如果没有空闲声音，再按顺序使用新的声音槽位。

![](img/6f18f54518e4455428d5825da1c39f49_131.png)

![](img/6f18f54518e4455428d5825da1c39f49_132.png)

![](img/6f18f54518e4455428d5825da1c39f49_134.png)

![](img/6f18f54518e4455428d5825da1c39f49_136.png)

![](img/6f18f54518e4455428d5825da1c39f49_138.png)

![](img/6f18f54518e4455428d5825da1c39f49_139.png)

![](img/6f18f54518e4455428d5825da1c39f49_140.png)

![](img/6f18f54518e4455428d5825da1c39f49_142.png)

![](img/6f18f54518e4455428d5825da1c39f49_144.png)

**代码实现：**
```c
// 在获取新声音时
if(first_free_sound != -1) {
    result = first_free_sound;
    first_free_sound = sounds[first_free_sound].next_free;
} else {
    // 顺序分配新槽位
    result = next_playing_sound++;
}
// 当声音播放完毕时，将其加入空闲列表
void stop_sound(Playing_Sound* sound) {
    sound->active = false;
    sound->next_free = first_free_sound;
    first_free_sound = sound_index; // 假设 sound_index 是该声音的索引
}
```

![](img/6f18f54518e4455428d5825da1c39f49_146.png)

![](img/6f18f54518e4455428d5825da1c39f49_148.png)

![](img/6f18f54518e4455428d5825da1c39f49_150.png)

![](img/6f18f54518e4455428d5825da1c39f49_152.png)

![](img/6f18f54518e4455428d5825da1c39f49_154.png)

![](img/6f18f54518e4455428d5825da1c39f49_156.png)

![](img/6f18f54518e4455428d5825da1c39f49_157.png)

![](img/6f18f54518e4455428d5825da1c39f49_159.png)

![](img/6f18f54518e4455428d5825da1c39f49_161.png)

![](img/6f18f54518e4455428d5825da1c39f49_163.png)

通过以上修改，声音系统可以更灵活地复用资源。

![](img/6f18f54518e4455428d5825da1c39f49_164.png)

![](img/6f18f54518e4455428d5825da1c39f49_166.png)

---

![](img/6f18f54518e4455428d5825da1c39f49_168.png)

![](img/6f18f54518e4455428d5825da1c39f49_169.png)

![](img/6f18f54518e4455428d5825da1c39f49_171.png)

![](img/6f18f54518e4455428d5825da1c39f49_172.png)

![](img/6f18f54518e4455428d5825da1c39f49_174.png)

![](img/6f18f54518e4455428d5825da1c39f49_175.png)

## 多线程编程基础

![](img/6f18f54518e4455428d5825da1c39f49_177.png)

![](img/6f18f54518e4455428d5825da1c39f49_179.png)

![](img/6f18f54518e4455428d5825da1c39f49_181.png)

![](img/6f18f54518e4455428d5825da1c39f49_183.png)

![](img/6f18f54518e4455428d5825da1c39f49_185.png)

在深入作业系统之前，我们先了解Windows平台创建线程的基本方法。

![](img/6f18f54518e4455428d5825da1c39f49_187.png)

![](img/6f18f54518e4455428d5825da1c39f49_189.png)

![](img/6f18f54518e4455428d5825da1c39f49_191.png)

![](img/6f18f54518e4455428d5825da1c39f49_193.png)

### Windows线程创建

![](img/6f18f54518e4455428d5825da1c39f49_195.png)

![](img/6f18f54518e4455428d5825da1c39f49_197.png)

![](img/6f18f54518e4455428d5825da1c39f49_199.png)

Windows API 提供了 `CreateThread` 函数来创建新线程。

![](img/6f18f54518e4455428d5825da1c39f49_201.png)

![](img/6f18f54518e4455428d5825da1c39f49_203.png)

![](img/6f18f54518e4455428d5825da1c39f49_205.png)

**函数原型：**
```c
HANDLE CreateThread(
  LPSECURITY_ATTRIBUTES   lpThreadAttributes,
  SIZE_T                  dwStackSize,
  LPTHREAD_START_ROUTINE  lpStartAddress,
  LPVOID                  lpParameter,
  DWORD                   dwCreationFlags,
  LPDWORD                 lpThreadId
);
```

![](img/6f18f54518e4455428d5825da1c39f49_207.png)

![](img/6f18f54518e4455428d5825da1c39f49_208.png)

![](img/6f18f54518e4455428d5825da1c39f49_210.png)

![](img/6f18f54518e4455428d5825da1c39f49_212.png)

![](img/6f18f54518e4455428d5825da1c39f49_214.png)

**简单示例：**
我们创建一个线程来打印一个整数。需要注意的是，必须谨慎传递参数，避免主线程修改数据时，新线程读取到过期或错误的值。

![](img/6f18f54518e4455428d5825da1c39f49_216.png)

![](img/6f18f54518e4455428d5825da1c39f49_218.png)

![](img/6f18f54518e4455428d5825da1c39f49_220.png)

![](img/6f18f54518e4455428d5825da1c39f49_222.png)

![](img/6f18f54518e4455428d5825da1c39f49_224.png)

![](img/6f18f54518e4455428d5825da1c39f49_226.png)

```c
DWORD WINAPI thread_proc(LPVOID data) {
    int value = *(int*)data; // 注意：直接传递指针可能有问题
    printf("%d\n", value);
    return 0;
}
// 创建线程
int value = 10;
CreateThread(NULL, 0, thread_proc, &value, 0, NULL);
```

![](img/6f18f54518e4455428d5825da1c39f49_227.png)

![](img/6f18f54518e4455428d5825da1c39f49_229.png)

![](img/6f18f54518e4455428d5825da1c39f49_231.png)

![](img/6f18f54518e4455428d5825da1c39f49_233.png)

**关键点：** 直接传递局部变量的指针是危险的，因为该变量可能在线程访问前就已超出作用域或被修改。更安全的做法是复制数据或使用线程安全的数据结构。

![](img/6f18f54518e4455428d5825da1c39f49_235.png)

![](img/6f18f54518e4455428d5825da1c39f49_237.png)

![](img/6f18f54518e4455428d5825da1c39f49_239.png)

![](img/6f18f54518e4455428d5825da1c39f49_241.png)

---

![](img/6f18f54518e4455428d5825da1c39f49_243.png)

![](img/6f18f54518e4455428d5825da1c39f49_245.png)

## 构建作业系统（Job System）

直接为每个任务创建线程效率低下。我们将构建一个作业系统：创建固定数量的工作线程，它们从一个共享的作业队列中获取并执行任务。

![](img/6f18f54518e4455428d5825da1c39f49_247.png)

### 系统设计

![](img/6f18f54518e4455428d5825da1c39f49_249.png)

![](img/6f18f54518e4455428d5825da1c39f49_251.png)

![](img/6f18f54518e4455428d5825da1c39f49_253.png)

1.  **作业队列 (Job Queue)**： 一个环形缓冲区，存储待执行的作业。
2.  **信号量 (Semaphore)**： 用于在工作线程无任务可执行时，使其休眠；当有新作业加入时，唤醒它们。
3.  **原子操作 (Atomic Operations)**： 确保多个线程安全地读写队列的头部和尾部索引，防止数据竞争。
4.  **工作线程 (Worker Threads)**： 持续循环，从队列中取出作业并执行其回调函数。

![](img/6f18f54518e4455428d5825da1c39f49_255.png)

![](img/6f18f54518e4455428d5825da1c39f49_257.png)

### 数据结构定义

![](img/6f18f54518e4455428d5825da1c39f49_259.png)

![](img/6f18f54518e4455428d5825da1c39f49_261.png)

![](img/6f18f54518e4455428d5825da1c39f49_263.png)

![](img/6f18f54518e4455428d5825da1c39f49_265.png)

![](img/6f18f54518e4455428d5825da1c39f49_267.png)

![](img/6f18f54518e4455428d5825da1c39f49_269.png)

![](img/6f18f54518e4455428d5825da1c39f49_271.png)

![](img/6f18f54518e4455428d5825da1c39f49_273.png)

```c
typedef void OS_Job_Callback(struct OS_Job_Queue* queue, void* data);

![](img/6f18f54518e4455428d5825da1c39f49_275.png)

![](img/6f18f54518e4455428d5825da1c39f49_277.png)

![](img/6f18f54518e4455428d5825da1c39f49_279.png)

![](img/6f18f54518e4455428d5825da1c39f49_281.png)

![](img/6f18f54518e4455428d5825da1c39f49_283.png)

![](img/6f18f54518e4455428d5825da1c39f49_285.png)

![](img/6f18f54518e4455428d5825da1c39f49_287.png)

struct OS_Job {
    OS_Job_Callback* callback;
    void* data;
};

![](img/6f18f54518e4455428d5825da1c39f49_289.png)

struct OS_Job_Queue {
    // 作业存储
    OS_Job jobs[32];
    // 原子索引
    volatile long next_entry_to_read;
    volatile long next_entry_to_write;
    // 线程同步
    HANDLE semaphore;
    // 工作线程句柄
    HANDLE thread_handles[4];
    int thread_count;
};
```

### 工作线程流程

每个工作线程执行以下循环：
1.  尝试从队列中获取一个作业（使用原子操作比较并交换来安全地增加 `next_entry_to_read`）。
2.  如果获取成功，则执行该作业的回调函数。
3.  如果队列为空，则调用 `WaitForSingleObject` 在信号量上等待，直到被新作业唤醒。

![](img/6f18f54518e4455428d5825da1c39f49_291.png)

![](img/6f18f54518e4455428d5825da1c39f49_293.png)

![](img/6f18f54518e4455428d5825da1c39f49_295.png)

![](img/6f18f54518e4455428d5825da1c39f49_297.png)

### 添加作业到队列

游戏主线程通过调用 `OS_do_work_async` 来添加新作业：
1.  计算新的写入位置。
2.  将作业的回调函数和数据写入 `jobs` 数组的相应位置。
3.  使用原子操作更新 `next_entry_to_write`。
4.  调用 `ReleaseSemaphore` 增加信号量计数，唤醒一个等待中的工作线程。

### 创建队列与线程

![](img/6f18f54518e4455428d5825da1c39f49_299.png)

![](img/6f18f54518e4455428d5825da1c39f49_300.png)

在系统初始化时，我们创建作业队列和指定数量的工作线程，每个线程都运行同一个线程过程，并传入队列指针作为参数。

---

## 将音频更新移至作业系统

![](img/6f18f54518e4455428d5825da1c39f49_302.png)

![](img/6f18f54518e4455428d5825da1c39f49_304.png)

现在，我们利用新建的作业系统来异步处理音频更新。

### 创建专用音频队列

![](img/6f18f54518e4455428d5825da1c39f49_306.png)

![](img/6f18f54518e4455428d5825da1c39f49_308.png)

我们创建一个专门用于音频更新的作业队列，并为其分配一个工作线程。

![](img/6f18f54518e4455428d5825da1c39f49_310.png)

![](img/6f18f54518e4455428d5825da1c39f49_312.png)

```c
OS_Job_Queue audio_queue;
OS_create_queue(&audio_queue, 1); // 为音频创建一个线程
```

![](img/6f18f54518e4455428d5825da1c39f49_314.png)

![](img/6f18f54518e4455428d5825da1c39f49_316.png)

![](img/6f18f54518e4455428d5825da1c39f49_318.png)

![](img/6f18f54518e4455428d5825da1c39f49_320.png)

### 修改音频更新循环

![](img/6f18f54518e4455428d5825da1c39f49_322.png)

![](img/6f18f54518e4455428d5825da1c39f49_324.png)

![](img/6f18f54518e4455428d5825da1c39f49_326.png)

原本在游戏主循环中直接调用的 `update_audio` 函数，现在被封装成一个作业，并提交到音频队列。

![](img/6f18f54518e4455428d5825da1c39f49_328.png)

![](img/6f18f54518e4455428d5825da1c39f49_330.png)

```c
void game_update_and_render(...) {
    // 计算上一帧耗时 dt
    // 提交音频更新作业
    OS_do_work_async(&audio_queue, os_job_callback_update_audio, &dt);
    // ... 游戏逻辑和渲染
}
```

![](img/6f18f54518e4455428d5825da1c39f49_332.png)

![](img/6f18f54518e4455428d5825da1c39f49_333.png)

![](img/6f18f54518e4455428d5825da1c39f49_335.png)

![](img/6f18f54518e4455428d5825da1c39f49_337.png)

![](img/6f18f54518e4455428d5825da1c39f49_339.png)

![](img/6f18f54518e4455428d5825da1c39f49_341.png)

![](img/6f18f54518e4455428d5825da1c39f49_342.png)

在音频工作线程中，`os_job_callback_update_audio` 函数被调用，它根据传入的 `dt` 来更新音频混合器状态。

![](img/6f18f54518e4455428d5825da1c39f49_344.png)

![](img/6f18f54518e4455428d5825da1c39f49_346.png)

![](img/6f18f54518e4455428d5825da1c39f49_348.png)

![](img/6f18f54518e4455428d5825da1c39f49_350.png)

![](img/6f18f54518e4455428d5825da1c39f49_352.png)

![](img/6f18f54518e4455428d5825da1c39f49_354.png)

![](img/6f18f54518e4455428d5825da1c39f49_356.png)

### 实现音频线程的独立计时

![](img/6f18f54518e4455428d5825da1c39f49_358.png)

![](img/6f18f54518e4455428d5825da1c39f49_360.png)

为了确保音频以稳定频率更新（例如每秒48000次），音频线程需要自己的计时循环，而不是依赖不稳定的游戏帧时间。

```c
DWORD WINAPI audio_thread_proc(LPVOID data) {
    OS_Job_Queue* queue = (OS_Job_Queue*)data;
    LARGE_INTEGER last_counter, freq;
    QueryPerformanceFrequency(&freq);
    QueryPerformanceCounter(&last_counter);
    
    float target_dt = 1.0f / 48000.0f; // 目标音频更新间隔
    
    while(true) {
        // 计算实际耗时
        LARGE_INTEGER current_counter;
        QueryPerformanceCounter(&current_counter);
        float elapsed = (float)(current_counter.QuadPart - last_counter.QuadPart) / (float)freq.QuadPart;
        last_counter = current_counter;
        
        // 更新音频
        update_audio(target_dt);
        
        // 计算需要休眠的时间，以维持稳定更新率
        float sleep_time = (target_dt - elapsed) * 1000.0f; // 转换为毫秒
        if(sleep_time > 0) {
            Sleep((DWORD)sleep_time);
        }
    }
    return 0;
}
```

![](img/6f18f54518e4455428d5825da1c39f49_362.png)

![](img/6f18f54518e4455428d5825da1c39f49_364.png)

---

![](img/6f18f54518e4455428d5825da1c39f49_366.png)

![](img/6f18f54518e4455428d5825da1c39f49_368.png)

![](img/6f18f54518e4455428d5825da1c39f49_370.png)

![](img/6f18f54518e4455428d5825da1c39f49_372.png)

## 成果与总结

![](img/6f18f54518e4455428d5825da1c39f49_374.png)

![](img/6f18f54518e4455428d5825da1c39f49_376.png)

![](img/6f18f54518e4455428d5825da1c39f49_378.png)

![](img/6f18f54518e4455428d5825da1c39f49_380.png)

![](img/6f18f54518e4455428d5825da1c39f49_381.png)

![](img/6f18f54518e4455428d5825da1c39f49_383.png)

本节课我们一起完成了以下工作：

1.  **修复了音频系统**：解决了文件循环问题，并实现了声音空闲列表以更好地管理资源。
2.  **学习了多线程基础**：了解了如何使用 `CreateThread` 创建线程以及相关的注意事项。
3.  **构建了作业系统**：设计并实现了一个包含作业队列、信号量和原子操作的多线程作业系统。该系统可以安全、高效地在多个线程间分发任务。
4.  **实现了音频异步更新**：将音频更新任务移至独立的作业队列和线程中。现在，即使游戏主循环因窗口拖动、复杂渲染等原因导致卡顿，背景音乐和音效也能持续流畅播放，显著提升了游戏的用户体验。

![](img/6f18f54518e4455428d5825da1c39f49_385.png)

通过本节的实践，我们为游戏引擎增加了强大的并发处理能力。在接下来的课程中，我们将利用这个作业系统进行异步文件I/O（如下一节的存档系统）、资源加载（如OGG音频解码），并进一步优化渲染流程。

![](img/6f18f54518e4455428d5825da1c39f49_387.png)

![](img/6f18f54518e4455428d5825da1c39f49_389.png)

![](img/6f18f54518e4455428d5825da1c39f49_391.png)

---

![](img/6f18f54518e4455428d5825da1c39f49_393.png)

**下一步计划：**
*   P13：文件I/O与存档系统 – 实现游戏进度和高分的保存与读取。
*   P14：完善音频系统 – 利用作业系统异步加载OGG文件，实现更多音效和音乐控制。
*   P15：用户界面(UI) – 创建菜单、计时器和分数显示。
*   P16：性能剖析与优化 – 为渲染等任务引入多线程，进一步提升性能。

![](img/6f18f54518e4455428d5825da1c39f49_395.png)

![](img/6f18f54518e4455428d5825da1c39f49_396.png)

![](img/6f18f54518e4455428d5825da1c39f49_398.png)

![](img/6f18f54518e4455428d5825da1c39f49_399.png)

![](img/6f18f54518e4455428d5825da1c39f49_401.png)

![](img/6f18f54518e4455428d5825da1c39f49_403.png)

你可以访问我的YouTube频道（YouTube.com/sdZDan）观看从第一集开始的完整系列，也可以在Ho（dan.h.o）免费下载每一集的游戏可执行文件和源代码。希望你喜欢今天的课程，我们下次再见！