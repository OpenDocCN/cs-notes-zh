# 🍽️ 课程 P12：第11讲 多线程、条件变量和信号量

![](img/048b7e540d7f0db4c80128b8a9481077_1.png)

![](img/048b7e540d7f0db4c80128b8a9481077_3.png)

![](img/048b7e540d7f0db4c80128b8a9481077_5.png)

在本节课中，我们将学习多线程编程中的经典问题——哲学家就餐问题。我们将探讨如何通过互斥锁、条件变量和信号量来解决线程间的资源竞争与死锁问题，并编写代码进行实践。

![](img/048b7e540d7f0db4c80128b8a9481077_7.png)

---

![](img/048b7e540d7f0db4c80128b8a9481077_9.png)

## 📅 课程安排与期中提醒

本周没有实验课。取而代之的是，要求大家观看一个约五分钟的短视频。这个视频是斯坦福毕业生关于计算机科学的简短分享。观看该视频将作为本周的实验签到。大家可以利用这一小时二十分钟的时间进行学习或完成其他课程作业。

![](img/048b7e540d7f0db4c80128b8a9481077_11.png)

![](img/048b7e540d7f0db4c80128b8a9481077_13.png)

![](img/048b7e540d7f0db4c80128b8a9481077_15.png)

---

![](img/048b7e540d7f0db4c80128b8a9481077_17.png)

![](img/048b7e540d7f0db4c80128b8a9481077_19.png)

## 🔍 回顾与调试：一个编译错误的解决

![](img/048b7e540d7f0db4c80128b8a9481077_21.png)

在上一节课的编码演示中，我们遇到了一个编译错误。问题出现在向线程函数传递参数时，类型不匹配。具体来说，我们试图将一个 `size_t` 类型的变量以 `unsigned int` 类型的引用进行传递。编译器因此报错。

![](img/048b7e540d7f0db4c80128b8a9481077_23.png)

![](img/048b7e540d7f0db4c80128b8a9481077_25.png)

![](img/048b7e540d7f0db4c80128b8a9481077_27.png)

![](img/048b7e540d7f0db4c80128b8a9481077_29.png)

**解决方案**是修正类型声明，确保传递的引用类型与参数期望的类型完全一致。修正后代码如下：

![](img/048b7e540d7f0db4c80128b8a9481077_31.png)

![](img/048b7e540d7f0db4c80128b8a9481077_33.png)

![](img/048b7e540d7f0db4c80128b8a9481077_35.png)

![](img/048b7e540d7f0db4c80128b8a9481077_37.png)

```cpp
// 修正前：传递了错误的类型引用
threadFunction(..., (unsigned int&)remainingTickets, ...);

![](img/048b7e540d7f0db4c80128b8a9481077_39.png)

![](img/048b7e540d7f0db4c80128b8a9481077_41.png)

// 修正后：使用正确的 size_t 类型
threadFunction(..., (size_t&)remainingTickets, ...);
```

![](img/048b7e540d7f0db4c80128b8a9481077_43.png)

![](img/048b7e540d7f0db4c80128b8a9481077_45.png)

![](img/048b7e540d7f0db4c80128b8a9481077_47.png)

![](img/048b7e540d7f0db4c80128b8a9481077_49.png)

![](img/048b7e540d7f0db4c80128b8a9481077_51.png)

![](img/048b7e540d7f0db4c80128b8a9481077_53.png)

这个错误提醒我们，编程中遇到难以发现的 Bug 是常事，即使经验丰富的程序员也不例外。关键在于耐心分析和调试。

![](img/048b7e540d7f0db4c80128b8a9481077_55.png)

![](img/048b7e540d7f0db4c80128b8a9481077_57.png)

![](img/048b7e540d7f0db4c80128b8a9481077_59.png)

![](img/048b7e540d7f0db4c80128b8a9481077_61.png)

![](img/048b7e540d7f0db4c80128b8a9481077_63.png)

---

![](img/048b7e540d7f0db4c80128b8a9481077_65.png)

![](img/048b7e540d7f0db4c80128b8a9481077_67.png)

## 🧠 哲学家就餐问题介绍

![](img/048b7e540d7f0db4c80128b8a9481077_69.png)

![](img/048b7e540d7f0db4c80128b8a9481077_71.png)

![](img/048b7e540d7f0db4c80128b8a9481077_73.png)

![](img/048b7e540d7f0db4c80128b8a9481077_75.png)

哲学家就餐问题是多线程编程中的一个经典死锁案例。它描述了五位哲学家围坐在圆桌旁，每人面前有一碗意面，每两人之间放有一把叉子。哲学家交替进行思考和进餐。

**进餐规则**：
1.  哲学家必须同时拿到左手边和右手边的两把叉子才能进餐。
2.  进餐完毕后，哲学家会放下两把叉子，继续思考。

**核心矛盾**：如果所有哲学家同时拿起自己左手边的叉子，那么每个人都会等待右手边的叉子被释放，从而导致**死锁**——所有人都无法进餐。

![](img/048b7e540d7f0db4c80128b8a9481077_77.png)

![](img/048b7e540d7f0db4c80128b8a9481077_79.png)

接下来，我们将通过代码模拟这个问题，并尝试解决它。

![](img/048b7e540d7f0db4c80128b8a9481077_81.png)

![](img/048b7e540d7f0db4c80128b8a9481077_83.png)

![](img/048b7e540d7f0db4c80128b8a9481077_85.png)

![](img/048b7e540d7f0db4c80128b8a9481077_87.png)

![](img/048b7e540d7f0db4c80128b8a9481077_89.png)

![](img/048b7e540d7f0db4c80128b8a9481077_91.png)

---

## ⚙️ 基础实现：使用互斥锁模拟

![](img/048b7e540d7f0db4c80128b8a9481077_93.png)

![](img/048b7e540d7f0db4c80128b8a9481077_95.png)

![](img/048b7e540d7f0db4c80128b8a9481077_97.png)

首先，我们使用互斥锁（`mutex`）来模拟叉子。每个叉子对应一个互斥锁，哲学家必须成功锁定（拿起）左右两把叉子才能进餐。

![](img/048b7e540d7f0db4c80128b8a9481077_99.png)

以下是哲学家线程的主要行为逻辑：

![](img/048b7e540d7f0db4c80128b8a9481077_101.png)

![](img/048b7e540d7f0db4c80128b8a9481077_103.png)

```cpp
void philosopher(size_t id, mutex& leftFork, mutex& rightFork) {
    for (size_t i = 0; i < 3; ++i) { // 每个哲学家进行3轮思考-进餐
        think(id); // 思考一段时间
        eat(id, leftFork, rightFork); // 尝试进餐
    }
}

![](img/048b7e540d7f0db4c80128b8a9481077_105.png)

![](img/048b7e540d7f0db4c80128b8a9481077_107.png)

![](img/048b7e540d7f0db4c80128b8a9481077_109.png)

void eat(size_t id, mutex& leftFork, mutex& rightFork) {
    leftFork.lock();   // 拿起左手边的叉子
    rightFork.lock();  // 拿起右手边的叉子
    // ... 模拟进餐 ...
    rightFork.unlock(); // 放下右手边的叉子
    leftFork.unlock();  // 放下左手边的叉子
}
```

![](img/048b7e540d7f0db4c80128b8a9481077_111.png)

![](img/048b7e540d7f0db4c80128b8a9481077_113.png)

在主函数中，我们创建5个哲学家线程和5个叉子（互斥锁），并为每个哲学家分配其左右叉子。

![](img/048b7e540d7f0db4c80128b8a9481077_115.png)

![](img/048b7e540d7f0db4c80128b8a9481077_117.png)

**运行风险**：如果所有哲学家同时执行，极有可能发生死锁。我们可以通过在所有线程开始进食前插入一个统一的延迟来人为触发这种死锁条件。

```cpp
// 在主线程中，启动所有哲学家线程前
sleep_for(milliseconds(5000)); // 等待5秒，让所有线程准备就绪
```

![](img/048b7e540d7f0db4c80128b8a9481077_119.png)

![](img/048b7e540d7f0db4c80128b8a9481077_121.png)

![](img/048b7e540d7f0db4c80128b8a9481077_123.png)

这样，所有哲学家线程会几乎同时尝试获取叉子，从而暴露出死锁问题。

![](img/048b7e540d7f0db4c80128b8a9481077_125.png)

![](img/048b7e540d7f0db4c80128b8a9481077_127.png)

![](img/048b7e540d7f0db4c80128b8a9481077_129.png)

---

![](img/048b7e540d7f0db4c80128b8a9481077_131.png)

![](img/048b7e540d7f0db4c80128b8a9481077_133.png)

![](img/048b7e540d7f0db4c80128b8a9481077_135.png)

## 🚫 解决死锁方案一：引入许可证（忙等待）

![](img/048b7e540d7f0db4c80128b8a9481077_137.png)

![](img/048b7e540d7f0db4c80128b8a9481077_139.png)

![](img/048b7e540d7f0db4c80128b8a9481077_141.png)

![](img/048b7e540d7f0db4c80128b8a9481077_143.png)

![](img/048b7e540d7f0db4c80128b8a9481077_145.png)

![](img/048b7e540d7f0db4c80128b8a9481077_147.png)

为了防止死锁，一个思路是限制同时尝试进餐的哲学家数量。例如，只允许最多4位哲学家同时尝试拿叉子。我们引入一个“许可证”计数器来实现这个限制。

![](img/048b7e540d7f0db4c80128b8a9481077_149.png)

![](img/048b7e540d7f0db4c80128b8a9481077_151.png)

![](img/048b7e540d7f0db4c80128b8a9481077_153.png)

![](img/048b7e540d7f0db4c80128b8a9481077_155.png)

**实现逻辑**：
1.  设置初始许可证数量为4（比哲学家总数少1）。
2.  哲学家在尝试拿叉子前，必须先获得一个许可证。
3.  如果没有许可证可用，哲学家必须等待。

![](img/048b7e540d7f0db4c80128b8a9481077_157.png)

以下是“等待许可证”函数的初步实现，它采用“忙等待”策略，即不断循环检查：

![](img/048b7e540d7f0db4c80128b8a9481077_159.png)

![](img/048b7e540d7f0db4c80128b8a9481077_161.png)

![](img/048b7e540d7f0db4c80128b8a9481077_162.png)

![](img/048b7e540d7f0db4c80128b8a9481077_164.png)

```cpp
void waitForPermission(size_t& permits, mutex& permitsLock) {
    while (true) {
        permitsLock.lock();
        if (permits > 0) {
            permits--; // 获取一个许可证
            permitsLock.unlock();
            break; // 成功获得，退出循环
        }
        permitsLock.unlock();
        // 忙等待：未获得许可证，休眠一小段时间后重试
        sleep_for(milliseconds(10));
    }
}
```

![](img/048b7e540d7f0db4c80128b8a9481077_166.png)

![](img/048b7e540d7f0db4c80128b8a9481077_168.png)

![](img/048b7e540d7f0db4c80128b8a9481077_170.png)

**缺点**：忙等待会持续消耗CPU资源，效率低下。哲学家线程在等待时会不断被唤醒和休眠。

![](img/048b7e540d7f0db4c80128b8a9481077_172.png)

---

![](img/048b7e540d7f0db4c80128b8a9481077_174.png)

![](img/048b7e540d7f0db4c80128b8a9481077_176.png)

## ✅ 解决死锁方案二：使用条件变量

为了更高效地等待，我们使用**条件变量**。条件变量允许线程在某个条件不满足时主动进入休眠状态，并在条件可能满足时被其他线程唤醒。

我们使用 `condition_variable_any` 和 `mutex` 配合工作。关键工具是 **`lock_guard`**，它能自动管理互斥锁的上锁与解锁。

![](img/048b7e540d7f0db4c80128b8a9481077_178.png)

![](img/048b7e540d7f0db4c80128b8a9481077_180.png)

![](img/048b7e540d7f0db4c80128b8a9481077_182.png)

![](img/048b7e540d7f0db4c80128b8a9481077_184.png)

**改进后的 `waitForPermission` 函数**：

![](img/048b7e540d7f0db4c80128b8a9481077_186.png)

![](img/048b7e540d7f0db4c80128b8a9481077_188.png)

![](img/048b7e540d7f0db4c80128b8a9481077_190.png)

![](img/048b7e540d7f0db4c80128b8a9481077_192.png)

![](img/048b7e540d7f0db4c80128b8a9481077_194.png)

![](img/048b7e540d7f0db4c80128b8a9481077_196.png)

```cpp
void waitForPermission(size_t& permits, mutex& m, condition_variable_any& cv) {
    lock_guard<mutex> lg(m); // 构造时上锁，析构时自动解锁
    // 使用lambda表达式作为等待条件
    cv.wait(m, [&permits] { return permits > 0; });
    permits--; // 获得许可证
    // lock_guard 超出作用域，自动解锁m
}
```

![](img/048b7e540d7f0db4c80128b8a9481077_198.png)

**对应的 `grantPermission` 函数**：

![](img/048b7e540d7f0db4c80128b8a9481077_200.png)

![](img/048b7e540d7f0db4c80128b8a9481077_202.png)

![](img/048b7e540d7f0db4c80128b8a9481077_204.png)

```cpp
void grantPermission(size_t& permits, mutex& m, condition_variable_any& cv) {
    lock_guard<mutex> lg(m);
    permits++; // 释放一个许可证
    if (permits == 1) { // 如果许可证从0变为1，可能有线程在等待
        cv.notify_all(); // 通知所有等待的线程
    }
}
```

![](img/048b7e540d7f0db4c80128b8a9481077_206.png)

![](img/048b7e540d7f0db4c80128b8a9481077_208.png)

![](img/048b7e540d7f0db4c80128b8a9481077_210.png)

**工作流程**：
1.  哲学家线程调用 `waitForPermission`。如果 `permits > 0`，则立即减少许可并继续。
2.  如果 `permits == 0`，`cv.wait()` 会解锁互斥锁 `m` 并使线程休眠。
3.  当有哲学家进餐完毕，调用 `grantPermission` 增加许可，并调用 `cv.notify_all()` 唤醒所有等待的线程。
4.  被唤醒的线程会重新获取锁并检查条件，成功者获得许可证。

这种方式避免了忙等待，让线程在等待期间完全不消耗CPU资源。

![](img/048b7e540d7f0db4c80128b8a9481077_212.png)

![](img/048b7e540d7f0db4c80128b8a9481077_214.png)

---

![](img/048b7e540d7f0db4c80128b8a9481077_216.png)

## 🚦 解决方案三：使用信号量

![](img/048b7e540d7f0db4c80128b8a9481077_218.png)

![](img/048b7e540d7f0db4c80128b8a9481077_220.png)

![](img/048b7e540d7f0db4c80128b8a9481077_222.png)

![](img/048b7e540d7f0db4c80128b8a9481077_224.png)

条件变量的模式非常通用，以至于可以被封装成一个更高级的工具——**信号量**。信号量维护一个计数器，提供了 `wait`（获取资源）和 `signal`（释放资源）两种原子操作。

![](img/048b7e540d7f0db4c80128b8a9481077_226.png)

![](img/048b7e540d7f0db4c80128b8a9481077_228.png)

在C++标准库中并没有直接提供信号量，但我们可以很容易地利用 `mutex` 和 `condition_variable_any` 实现它，或者使用课程提供的封装类。

![](img/048b7e540d7f0db4c80128b8a9481077_230.png)

![](img/048b7e540d7f0db4c80128b8a9481077_232.png)

![](img/048b7e540d7f0db4c80128b8a9481077_234.png)

![](img/048b7e540d7f0db4c80128b8a9481077_236.png)

**使用信号量简化哲学家问题**：

```cpp
// 声明一个初始值为4的信号量
semaphore permits(4);

![](img/048b7e540d7f0db4c80128b8a9481077_238.png)

![](img/048b7e540d7f0db4c80128b8a9481077_240.png)

![](img/048b7e540d7f0db4c80128b8a9481077_242.png)

// 在哲学家线程中，替换之前的 waitForPermission 和 grantPermission
void philosopher(size_t id, mutex& leftFork, mutex& rightFork, semaphore& permits) {
    for (size_t i = 0; i < 3; ++i) {
        think(id);
        permits.wait();    // 等待并获得一个许可证（信号量内部操作）
        eat(id, leftFork, rightFork);
        permits.signal();  // 释放许可证
    }
}
```

信号量的 `wait()` 和 `signal()` 方法内部已经封装了锁和条件变量的逻辑，使得代码更加简洁清晰。**互斥锁本质上就是初始值为1的信号量**。

![](img/048b7e540d7f0db4c80128b8a9481077_244.png)

![](img/048b7e540d7f0db4c80128b8a9481077_246.png)

![](img/048b7e540d7f0db4c80128b8a9481077_248.png)

![](img/048b7e540d7f0db4c80128b8a9481077_250.png)

---

![](img/048b7e540d7f0db4c80128b8a9481077_252.png)

![](img/048b7e540d7f0db4c80128b8a9481077_254.png)

![](img/048b7e540d7f0db4c80128b8a9481077_256.png)

## 📚 本节课总结

![](img/048b7e540d7f0db4c80128b8a9481077_258.png)

![](img/048b7e540d7f0db4c80128b8a9481077_260.png)

![](img/048b7e540d7f0db4c80128b8a9481077_261.png)

![](img/048b7e540d7f0db4c80128b8a9481077_263.png)

在本节课中，我们一起学习了：

![](img/048b7e540d7f0db4c80128b8a9481077_265.png)

![](img/048b7e540d7f0db4c80128b8a9481077_267.png)

![](img/048b7e540d7f0db4c80128b8a9481077_269.png)

1.  **哲学家就餐问题**：一个经典的多线程死锁场景。
2.  **互斥锁**：用于保护共享资源（叉子），但直接使用可能导致死锁。
3.  **许可证模式**：通过限制并发数量来预防死锁。
4.  **忙等待的缺点**：低效且消耗CPU。
5.  **条件变量**：与互斥锁配合，让线程能高效等待条件成熟，并通过 `lock_guard` 自动管理锁的生命周期。
6.  **信号量**：一个更高级的同步原语，基于条件变量封装，用于管理一组资源的访问许可，极大简化了代码。

![](img/048b7e540d7f0db4c80128b8a9481077_271.png)

![](img/048b7e540d7f0db4c80128b8a9481077_273.png)

通过从基础实现到高级同步原语的演进，我们掌握了解决复杂线程同步问题的多种工具和思路。在实际编程中，应根据具体场景选择最合适的方法。