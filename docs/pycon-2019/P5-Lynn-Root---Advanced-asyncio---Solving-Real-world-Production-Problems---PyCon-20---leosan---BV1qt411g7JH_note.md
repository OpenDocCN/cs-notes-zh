# 高级异步IO：解决真实世界的生产问题 🚀

![](img/70c5fa474cb4ff7321ee8fd9410d75b7_0.png)

在本教程中，我们将跟随 Lynn Root 在 PyCon 2019 的演讲，学习如何在实际生产环境中应用 Python 的异步 I/O (`asyncio`)。我们将构建一个名为“混沌曼德尔”的服务，它监听发布/订阅消息并重启主机，以此为例，探讨优雅关闭、异常处理、多线程、测试、调试和性能分析等高级主题。

---

## 1️⃣：基础概念与项目初始化

异步 I/O 是 Python 中实现并发编程的强大工具。它提供了不同层次的抽象，让开发者可以根据需求进行精细控制。一个简单的“Hello, World”示例虽然容易上手，但容易让人产生虚假的安全感。真实世界的服务（如处理 HTTP 请求、响应发布/订阅事件、管理指标等）要复杂得多。

我们将构建一个服务来模拟“混沌猴子”，它监听消息并重启主机。首先，我们从编写基础代码开始。

### 发布者协程

以下是发布者协程的代码。它在一个无限循环中生成带有唯一 ID 的消息，并将其发布到队列中。

```python
import asyncio
import uuid

async def publisher(queue):
    while True:
        message_id = str(uuid.uuid4())
        # 使用 create_task 来调度协程，避免阻塞循环
        task = asyncio.create_task(queue.put(message_id))
        # 这里没有 await task，实现了“发射即忘”
```

**关键点**：我们使用 `asyncio.create_task` 来调度 `queue.put` 协程，而不是直接使用 `await`。这样做可以避免阻塞 `while` 循环的后续迭代，允许事件循环继续处理其他任务。如果队列有大小限制，我们可能需要等待空间，但此例中我们继续使用 `create_task`。

### 消费者协程

现在，我们需要一个消费者来接收并处理这些消息。

```python
async def consumer(queue):
    while True:
        # 等待队列中的消息，这里使用 await 是合理的，因为消费者在没有消息时无事可做
        message = await queue.get()
        # 处理消息（后续会填充具体逻辑）
        print(f"Consumed: {message}")
```

**关键点**：消费者在 `queue.get()` 上使用 `await`。这只会阻塞消费者协程本身，而不会阻塞整个事件循环或其他任务。这是处理 I/O 等待的典型模式。

---

## 2️⃣：处理消息与任务编排

上一节我们介绍了生产者和消费者的基础结构。本节中，我们来看看如何处理具体的消息，并协调多个可能并发的任务。

当我们消费到一条消息时，可能需要执行多个操作，例如重启主机和将消息保存到数据库。这两个操作可能彼此独立，可以并发执行。

### 独立任务处理

我们将消息处理逻辑封装到一个单独的协程中，并使用 `asyncio.create_task` 来并发执行重启和保存操作。

```python
async def process_message(message):
    # 创建重启主机的任务
    restart_task = asyncio.create_task(restart_host(message))
    # 创建保存消息的任务
    save_task = asyncio.create_task(save_message(message))

    # 使用 asyncio.gather 等待两个任务都完成
    await asyncio.gather(restart_task, save_task)
    # 两个任务完成后，确认消息，防止重新投递
    await acknowledge_message(message)

async def restart_host(message):
    # 模拟重启主机的 I/O 操作
    await asyncio.sleep(1)
    print(f"Host restarted for message: {message}")

async def save_message(message):
    # 模拟保存消息到数据库的 I/O 操作
    await asyncio.sleep(0.5)
    print(f"Message saved: {message}")
```

**关键点**：`asyncio.gather` 用于并发运行多个协程，并等待它们全部完成。它返回一个结果列表（顺序与传入的协程顺序一致）。这确保了在确认消息之前，重启和保存操作都已完成。

### 顺序性依赖任务

有时，任务之间存在依赖关系，必须按顺序执行。例如，你可能需要先检查主机正常运行时间，然后再决定是否重启。

```python
async def process_message_sequential(message):
    # 必须先检查
    uptime = await check_uptime(message)
    if uptime > 7 * 24 * 3600: # 超过7天
        # 然后重启
        await restart_host(message)
    await save_message(message)
```

**关键点**：即使代码在逻辑上是顺序的（先 A 后 B），它仍然是异步的。`await check_uptime` 会让出控制权给事件循环，允许其他任务运行，但 `restart_host` 只会在 `check_uptime` 完成后才执行。

---

## 3️⃣：优雅关闭服务

我们的服务需要能够优雅地关闭，例如在收到终止信号时，清理数据库连接、停止消费消息、完成现有请求等。

### 信号处理

我们不能仅仅依赖 `try...except KeyboardInterrupt`，因为程序可能通过其他信号（如 SIGTERM）终止。我们应该为事件循环设置信号处理程序。

以下是设置优雅关闭的模板代码：

```python
import asyncio
import signal

async def shutdown(signal_name, loop, tasks):
    """执行关闭任务"""
    print(f"Received exit signal {signal_name}...")
    # 取消所有未完成的任务（除了当前关闭任务本身）
    for task in [t for t in tasks if t is not asyncio.current_task()]:
        task.cancel()
    # 等待任务取消
    await asyncio.gather(*tasks, return_exceptions=True)
    # 停止事件循环
    loop.stop()

def main():
    loop = asyncio.get_event_loop()
    # 创建任务列表以便后续取消
    tasks = [asyncio.create_task(publisher(queue)), asyncio.create_task(consumer(queue))]

    # 为 SIGINT 和 SIGTERM 设置信号处理程序
    for sig in (signal.SIGINT, signal.SIGTERM):
        loop.add_signal_handler(
            sig,
            lambda s=sig: asyncio.create_task(shutdown(s.name, loop, tasks))
        )

    try:
        loop.run_forever()
    finally:
        loop.close()
        print("Shutdown complete.")
```

**关键点**：
*   `loop.add_signal_handler` 用于注册信号处理程序。
*   处理程序内部创建一个 `shutdown` 协程任务来执行清理。
*   我们收集并取消所有运行中的任务（使用 `return_exceptions=True` 防止未处理异常导致崩溃）。
*   `finally` 块确保循环最终被关闭。

**关于 `asyncio.shield` 的警告**：文档中提到 `asyncio.shield` 可以保护任务不被取消，但在实际关闭场景中，它可能无法按预期工作，因为被保护的任务仍然包含在 `asyncio.all_tasks()` 中并会被取消。需要谨慎使用。

---

## 4️⃣：异常处理

异步代码中的异常如果不被正确处理，可能会被静默吞没，导致难以调试的问题。

### 全局异常处理器

我们可以为事件循环设置一个全局默认异常处理器。

```python
def handle_exception(loop, context):
    """全局异常处理器"""
    msg = context.get("exception", context["message"])
    print(f"Caught global exception: {msg}")
    # 这里可以记录日志、发送警报等

loop = asyncio.get_event_loop()
loop.set_exception_handler(handle_exception)
```

### 任务级异常处理

对于 `asyncio.gather`，我们可以通过 `return_exceptions=True` 参数来获取任务中的异常作为结果，而不是让异常立即抛出。

```python
async def process_message_safe(message):
    restart_task = asyncio.create_task(restart_host(message))
    save_task = asyncio.create_task(save_message(message))

    # 使用 return_exceptions=True 来收集异常
    results = await asyncio.gather(restart_task, save_task, return_exceptions=True)

    for i, result in enumerate(results):
        if isinstance(result, Exception):
            print(f"Task {i} failed with: {result}")
            # 根据具体异常类型进行特定处理，例如重试或拒绝消息
        else:
            print(f"Task {i} succeeded with: {result}")
```

**关键点**：务必设置某种形式的异常处理（全局或任务级），否则异常可能导致未定义行为或被忽略。

---

## 5️⃣：与多线程代码协作

有时你不得不与同步（阻塞）代码或线程交互，例如使用一个基于线程的发布/订阅客户端。

### 在线程中调度协程

如果从另一个线程需要调度协程到主事件循环，必须使用线程安全的 API。

```python
import asyncio
from concurrent.futures import ThreadPoolExecutor

def blocking_io_operation():
    # 这是一个阻塞的 I/O 函数
    time.sleep(2)
    return "Data from blocking IO"

async def main_in_async_world():
    loop = asyncio.get_event_loop()
    # 在线程池中运行阻塞函数
    executor = ThreadPoolExecutor()
    blocking_data = await loop.run_in_executor(executor, blocking_io_operation)
    print(blocking_data)

    # 如果要从线程回调中调度新协程，必须使用 `call_soon_threadsafe` 或 `run_coroutine_threadsafe`
    def callback_from_thread():
        future = asyncio.run_coroutine_threadsafe(async_task(), loop)
        # 可以 future.result() 等待结果，但会阻塞线程
```

**关键点**：
*   使用 `loop.run_in_executor` 将阻塞调用转移到线程池，避免阻塞事件循环。
*   要从非主线程调度协程，必须使用 `asyncio.run_coroutine_threadsafe` 或 `loop.call_soon_threadsafe`，直接调用 `loop.create_task` 不是线程安全的。

---

## 6️⃣：测试异步代码

测试异步代码需要特殊的工具和方法，因为测试函数本身需要在事件循环中运行。

### 使用 pytest-asyncio 插件

`pytest-asyncio` 插件简化了异步测试的编写。

```python
import pytest
import asyncio

@pytest.mark.asyncio
async def test_save_coroutine():
    """测试一个异步函数"""
    result = await save_message("test_msg")
    assert result is None  # 根据实际函数定义断言
```

**关键点**：使用 `@pytest.mark.asyncio` 装饰器，并将测试函数本身定义为 `async`。插件会自动管理事件循环。

### 模拟异步函数（Mocking）

模拟（Mocking）异步函数和协程需要一些技巧，因为标准的 `unittest.mock` 对 `async` 支持有限。

以下是一个使用 `pytest` 夹具来模拟协程的示例：

```python
import pytest
from unittest.mock import Mock, AsyncMock, patch

@pytest.fixture
def mock_sleep():
    """创建一个模拟的 asyncio.sleep"""
    with patch('mayhem.asyncio.sleep', new_callable=AsyncMock) as mock_sleep:
        yield mock_sleep

@pytest.mark.asyncio
async def test_save_with_mock(mock_sleep):
    """使用模拟的 sleep 测试 save_message"""
    mock_sleep.return_value = None
    await save_message("test")
    mock_sleep.assert_awaited_once_with(0.5)  # 使用 assert_awaited_* 用于 AsyncMock
```

**关键点**：
*   对于 Python 3.8+，可以使用 `unittest.mock.AsyncMock`。
*   使用 `pytest` 的 `patch` 夹具来替换目标协程。
*   对 `AsyncMock` 的断言需要使用 `assert_awaited_once_with` 等方法。

### 测试调用了 `create_task` 的代码

测试创建了任务的函数时，需要确保任务被实际执行。仅仅调度任务（`create_task`）可能不足以在测试中推进它们。

```python
@pytest.mark.asyncio
async def test_consumer_schedules_task():
    mock_queue = AsyncMock()
    mock_queue.get.side_effect = ["msg1", asyncio.CancelledError()] # 发送一个消息然后取消

    mock_process = AsyncMock()
    with patch('mayhem.process_message', mock_process):
        consumer_task = asyncio.create_task(consumer(mock_queue))
        # 需要给事件循环一个机会来运行调度的任务
        await asyncio.sleep(0.01)
        consumer_task.cancel()
        try:
            await consumer_task
        except asyncio.CancelledError:
            pass

    mock_process.assert_awaited_once_with("msg1")
```

**关键点**：在测试中，可能需要手动 `await asyncio.sleep(0)` 或一小段时间，以让事件循环处理已调度的任务。

对于更复杂的场景，可以考虑使用 `asyncio` 标准库中的 `asynctest` 模块，它提供了更强大的测试工具。

---

## 7️⃣：调试异步代码

调试异步程序有其独特的挑战，比如跟踪多个并发任务的状态。

### 使用内置调试模式

`asyncio` 有一个内置的调试模式，可以提供丰富的信息。

```python
import asyncio
import logging

# 启用调试模式
logging.basicConfig(level=logging.DEBUG)
asyncio.run(main(), debug=True)
```

**调试模式提供**：
1.  **未处理异常的详细信息**：包括异常发生时的任务和源跟踪。
2.  **线程安全警告**：如果检测到非线程安全的操作，会抛出 `RuntimeError`。
3.  **慢回调日志**：默认记录执行时间超过 100ms 的协程，帮助识别性能瓶颈。

### 打印任务堆栈

对于临时调试，可以打印运行中任务的堆栈信息。

```python
for task in asyncio.all_tasks():
    print(task)
    task.print_stack(limit=5)
```

### 生产环境下的轻量级调试

在生产环境中启用完全调试模式可能开销太大。可以使用 `aiodebug` 这样的轻量级库，它专注于记录慢回调和执行时间。

```python
import aiodebug

aiodebug.log_slow_callbacks.enable(0.05)  # 记录超过50ms的回调
```

---

## 8️⃣：性能分析

分析异步代码的性能可能与同步代码略有不同，因为时间花费在多个交错的任务上。

### 使用 cProfile 和可视化工具

1.  **使用 cProfile 收集数据**：
    ```bash
    python -m cProfile -o output.prof your_script.py
    ```

2.  **使用 snakeviz 进行可视化**：
    ```bash
    pip install snakeviz
    snakeviz output.prof
    ```
    `snakeviz` 会提供一个交互式的火焰图，帮助你直观地看到时间消耗在哪里。

### 使用 py-spy 进行实时分析

`py-spy` 是一个采样分析器，可以连接到正在运行的进程，对生产环境的影响很小。

```bash
pip install py-spy
py-spy top --pid <PID>  # 查看实时统计
py-spy record -o profile.svg --pid <PID>  # 记录并生成火焰图
```

### 使用 line_profiler 进行逐行分析

当你怀疑某个特定函数是热点时，可以使用 `line_profiler` 进行更细粒度的分析。

1.  **装饰目标函数**：
    ```python
    from line_profiler import profile

    @profile
    async def save_message(message):
        # ... 函数体
    ```

2.  **使用 kernprof 运行脚本**：
    ```bash
    kernprof -l -v your_script.py
    ```
    它会输出函数中每一行代码的执行时间和次数。

### 针对异步的优化发现

在分析过程中，你可能会发现一些意想不到的瓶颈。例如，Lynn 在分析中发现大量的时间花在了标准库的 `logging` 模块上，这本身是阻塞的。

**解决方案**：使用 `aiologger` 这样的异步日志记录库。

![](img/70c5fa474cb4ff7321ee8fd9410d75b7_2.png)

```python
import asyncio
from aiologger import Logger

![](img/70c5fa474cb4ff7321ee8fd9410d75b7_4.png)

![](img/70c5fa474cb4ff7321ee8fd9410d75b7_6.png)

async def main():
    logger = Logger.with_default_handlers()
    await logger.info("This is a non-blocking log message!")
    await logger.shutdown()
```

![](img/70c5fa474cb4ff7321ee8fd9410d75b7_8.png)

![](img/70c5fa474cb4ff7321ee8fd9410d75b7_10.png)

替换为异步日志记录器后，相关函数的执行时间显著减少。

---

## 总结 📝

在本教程中，我们一起学习了如何在实际生产项目中应用高级 `asyncio` 技术：

1.  **基础与编排**：理解了 `create_task` 和 `gather` 的用法，学会了如何编排独立或具有依赖关系的并发任务。
2.  **优雅关闭**：学会了通过信号处理程序实现服务的优雅关闭，确保资源被正确清理。
3.  **异常处理**：掌握了设置全局和任务级异常处理器的方法，避免异常被静默吞没。
4.  **多线程协作**：了解了如何安全地在异步事件循环和线程之间进行交互。
5.  **测试**：使用 `pytest-asyncio` 和 mocking 技术来有效地测试异步代码。
6.  **调试**：利用 `asyncio` 的调试模式、任务堆栈打印和 `aiodebug` 等工具来定位问题。
7.  **性能分析**：通过 `cProfile`/`snakeviz`、`py-spy` 和 `line_profiler` 等工具链，识别并优化性能瓶颈。

![](img/70c5fa474cb4ff7321ee8fd9410d75b7_12.png)

记住，使用 `asyncio` 不仅仅是添加 `async`/`await` 关键字，它需要一种思维模式的转变，仔细考虑哪些操作可以并发，哪些必须顺序执行，并妥善处理并发带来的复杂性。希望这个基于真实场景的教程能帮助你构建更健壮、高效的异步 Python 服务。