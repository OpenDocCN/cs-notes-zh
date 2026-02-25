# 8：基于锁的并发与parking_lot库API 🧠

![](img/e00c7c1043418153f8c6b04611165f3d_1.png)

![](img/e00c7c1043418153f8c6b04611165f3d_3.png)

在本节课中，我们将继续学习Rust中的并发库，重点介绍一个名为`parking_lot`的库。`parking_lot`提供了几个非常基础的并发原语，包括互斥锁、条件变量和读写锁。虽然它提供了更多功能，但本节我们只学习这三个核心部分。

## Mutex（互斥锁）🔒

上一节我们介绍了`Arc`，本节我们来看看如何使用`parking_lot`中的`Mutex`来保护共享数据。`Mutex`允许你通过不可变引用可变地访问其内部数据，其关键在于访问数据前必须获取锁。锁的获取是独占的，因此在持有锁期间，其他线程无法访问内部数据，从而保证了线程安全。

以下是`Mutex`的一个典型使用示例，该示例复制自`parking_lot`的官方文档：

```rust
use parking_lot::Mutex;
use std::sync::{Arc, mpsc::channel};
use std::thread;

const N: usize = 10;

let data = Arc::new(Mutex::new(0));
let (tx, rx) = channel();

for _ in 0..N {
    let (data, tx) = (Arc::clone(&data), tx.clone());
    thread::spawn(move || {
        let mut data = data.lock();
        *data += 1;
        if *data == N {
            tx.send(()).unwrap();
        }
    });
}

rx.recv().unwrap();
```

让我们分析这段代码：
1.  **创建受保护的数据**：`Mutex::new(0)`创建了一个初始值为`0`、受互斥锁保护的数据。随后用`Arc`将其包装，使得这个被保护数据的引用可以被安全地复制并跨线程共享，而无需担心其生命周期。
2.  **创建线程**：程序创建了10个线程。每个线程都获得一个指向共享数据的`Arc`引用和一个通道的发送端。
3.  **获取锁与修改数据**：在每个线程中，`data.lock()`尝试获取锁。成功后会返回一个`MutexGuard`（在代码中命名为`data`），它是已持有锁的证明。通过这个守卫，可以安全地修改底层数据（`*data += 1`）。
4.  **发送信号**：最后一个将计数器增加到`N`的线程，会通过通道发送一个信号。
5.  **自动释放锁**：`MutexGuard`在作用域结束时（即`}`处）会被自动丢弃（`drop`），锁也随之自动释放。这是Rust所有权系统带来的优势，避免了手动释放锁可能导致的错误。
6.  **主线程接收**：主线程通过通道接收信号，得知所有线程已完成工作。

`parking_lot`的`Mutex`与自旋锁（`spinlock`）的主要区别在于阻塞行为：自旋锁在无法获取锁时会循环忙等待；而`Mutex`在无法获取锁时会让线程休眠，不消耗CPU时间。

关于`Mutex`的更多API，请查阅其官方文档。

![](img/e00c7c1043418153f8c6b04611165f3d_5.png)

## Condvar（条件变量）⏳

接下来，我们学习`parking_lot`的第二个API：条件变量（`Condvar`）。条件变量用于让线程等待某个特定条件发生，在等待期间线程会进入休眠状态，不消耗CPU资源。条件变量几乎总是与`Mutex`配合使用。

![](img/e00c7c1043418153f8c6b04611165f3d_7.png)

![](img/e00c7c1043418153f8c6b04611165f3d_9.png)

以下是条件变量的一个示例：

```rust
use parking_lot::{Condvar, Mutex};
use std::sync::Arc;
use std::thread;

let pair = Arc::new((Mutex::new(false), Condvar::new()));
let pair2 = Arc::clone(&pair);

thread::spawn(move || {
    let (lock, cvar) = &*pair2;
    let mut started = lock.lock();
    *started = true;
    cvar.notify_one();
});

let (lock, cvar) = &*pair;
let mut started = lock.lock();
while !*started {
    cvar.wait(&mut started);
}
```

让我们分析其工作流程：
1.  **关联锁与条件变量**：创建一个元组，包含一个`Mutex<bool>`和一个`Condvar`，并用`Arc`包装以便共享。
2.  **线程设置条件**：新线程获取锁，将布尔值设为`true`，然后通过`cvar.notify_one()`通知（唤醒）一个正在等待此条件变量的线程。
3.  **主线程等待条件**：主线程获取锁后，检查条件（`*started`）。如果条件为假，则调用`cvar.wait(&mut started)`进行等待。
    *   **关键点**：`wait`方法接收一个`MutexGuard`的可变引用。在调用`wait`时，它会**自动释放**传入的锁，并让线程休眠。
    *   当其他线程调用`notify_one()`时，等待的线程被唤醒。在`wait`方法返回前，它会**自动重新获取**锁。
4.  **条件保证**：当`wait`返回后，由于是在被通知后唤醒并重新持有锁，因此可以保证此时`*started`一定为`true`。

条件变量API的一个安全特性体现在`wait`函数签名上：它要求一个`MutexGuard`的可变引用（`&mut MutexGuard`）。这防止了在等待前后持有对受保护数据的普通引用，因为等待期间锁会被释放和重新获取，数据可能被其他线程修改，持有旧引用是不安全的。Rust的类型系统在此确保了安全。

`parking_lot`的条件变量主要提供安全API，足以应对大多数场景。

## RwLock（读写锁）📖✏️

最后，我们学习读写锁（`RwLock`）。它与`Mutex`类似，但区分了读操作和写操作：
*   **读锁**：可以被多个线程同时获取，用于只读访问。
*   **写锁**：是独占的，同一时间只能有一个线程持有写锁，用于写入访问。

![](img/e00c7c1043418153f8c6b04611165f3d_11.png)

![](img/e00c7c1043418153f8c6b04611165f3d_12.png)

这对于“读多写少”的数据访问模式非常高效。以下是示例：

```rust
use parking_lot::RwLock;

let lock = RwLock::new(5);

![](img/e00c7c1043418153f8c6b04611165f3d_14.png)

// 多个线程可以同时获取读锁
{
    let r1 = lock.read();
    let r2 = lock.read();
    assert_eq!(*r1, 5);
    assert_eq!(*r2, 5);
} // 读锁在这里自动释放

![](img/e00c7c1043418153f8c6b04611165f3d_16.png)

// 同一时间只能有一个线程获取写锁
{
    let mut w = lock.write();
    *w += 1;
    assert_eq!(*w, 6);
} // 写锁在这里自动释放
```

## 总结 🎯

本节课我们一起学习了`parking_lot`库提供的三个核心、安全的并发原语：
1.  **`Mutex`**：提供独占访问，通过`MutexGuard`的自动释放来安全管理锁。
2.  **`Condvar`**：与`Mutex`配合，用于线程间等待和通知条件达成，其API设计避免了等待期间的数据引用安全问题。
3.  **`RwLock`**：区分读写访问，允许多个读锁或一个写锁，适用于读多写少的场景。

![](img/e00c7c1043418153f8c6b04611165f3d_18.png)

![](img/e00c7c1043418153f8c6b04611165f3d_19.png)

![](img/e00c7c1043418153f8c6b04611165f3d_21.png)

这些原语的API设计充分利用了Rust的所有权和类型系统，在编译期就能防止许多常见的并发错误。在下一节课中，我们将继续探索其他并发库。