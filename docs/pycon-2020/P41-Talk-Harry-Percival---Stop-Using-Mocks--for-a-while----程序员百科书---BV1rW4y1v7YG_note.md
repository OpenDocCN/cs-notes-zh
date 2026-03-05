# 软件架构与测试：P41：停止使用模拟对象（暂时）

![](img/70f450bbad5ae8f4921bcddae5be82cc_0.png)

![](img/70f450bbad5ae8f4921bcddae5be82cc_0.png)

## 概述

在本节课中，我们将探讨在软件开发中过度依赖模拟对象（Mocks）可能带来的问题，并学习一系列替代方案。我们将通过一个货运系统的例子，逐步了解如何通过构建适配器、使用伪造对象（Fakes）、依赖注入和集成测试来改进代码设计和测试质量。

## 英雄的旅程：从模拟对象开始

我叫哈里，在 `hjwp` 的 Twitter 上可以找到我。我代表一个叫 `cosmicpython.com` 的网站。这个网站讨论如何确保你的 Python 代码尽可能远离混乱。今天要讨论的一个可能的技术是：停止使用模拟对象（Mocks），至少暂时停止。

我以谈论测试驱动开发而闻名，但过去几年，我开始更多地思考软件架构。我在一家叫 `made.com` 的公司工作。我们将跟随一个“英雄的旅程”来讲述这个故事：从冒险的召唤开始，与导师会面，然后与“怪物”（在这里是代码设计决策）战斗，权衡利弊，最后带着“灵药”（即关于如何构造代码的想法）回到社区。

如果你停止使用处理代码中某些东西的常见方法（比如模拟对象），并尝试一些有趣的新方法，你可能会有所收获。这就是我今天想说的。

## 模拟对象的常见场景与问题

我假设大家都熟悉模拟对象。我并不是说模拟对象不好，你永远不应该使用它们。一旦你对软件架构和设计感兴趣，你就会明白“看情况而定”这句陈词滥调。模拟对象是一种常见的工具，但在某些情况下，你可能会发现更好的工具。

所以，我要讨论很多利弊。这里没有黑白分明，只有正反两面。每次我提出一个新的想法或模式，我都会讨论它的优点和缺点。

### 一个示例：货运系统

我和 `made.com` 的同事，尤其是一位叫鲍勃的导师，学到了很多关于软件架构的知识。当我最终写一本关于这个的书时，它叫《架构模式与Python》，你可以在 `cosmicpython.com` 上找到更多信息。

我想通过一些示例代码来重现我学到的东西。例如，在物流领域，假设你有想追踪的货物。一批货物（`Batch`）是多个订单行（`OrderLine`）的集合。订单行代表某个产品的一定数量，用产品标识符 `SKU` 表示。货物有一个订单行列表，它有自己的引用编号、预计到达时间（`ETA`）和 `INCOTERM` 等属性。

我们用一个简单的数据模型来表示系统中的数据，并可能将其保存到数据库。

**第一个业务需求**：当我创建货物时，需要将其与第三方货运 API 同步。

在我的代码中，我有一个类似控制器或业务服务的函数。如果你使用 Django 或 Flask，这可能是视图或从视图调用的东西。

```python
def create_shipping(products, quantity, incoterm):
    # 生成随机引用，创建模型对象，保存到数据库
    batch_ref = str(uuid.uuid4())
    batch = Batch(ref=batch_ref, eta=..., lines=...)
    batch.save()

    # 与 API 同步
    sync_with_api(batch)
```

`sync_with_api` 函数将一些属性构建成简单的数据结构，并将其作为 JSON 发送到第三方 API。

```python
def sync_with_api(batch):
    data = {"ref": batch.ref, "eta": batch.eta, ...}
    requests.post("https://api.shipping.com/batches", json=data)
```

**如何测试它？** 最经典的方法是使用模拟对象，特别是 `unittest.mock` 模块的 `patch` 和 `Mock` 技术。

```python
from unittest.mock import patch

def test_create_shipping():
    with patch('module.requests.post') as mock_post:
        create_shipping(...)
        # 断言 requests.post 被以特定参数调用
        mock_post.assert_called_once_with(
            "https://api.shipping.com/batches",
            json={"ref": ..., "eta": ..., ...}
        )
```

这看起来还不错。如果你用过几次模拟对象，你可以看懂发生了什么。

但生活从未如此简单，是吗？

**第二个业务需求**：为新的货物做 POST 请求，为已存在的货物做 PUT 请求。

所以我的 `sync_with_api` 代码突然变得更复杂了。我需要先做一个 GET 请求来检查货物是否已存在，然后决定是 POST 还是 PUT。

```python
def sync_with_api(batch):
    # 先检查货物是否已存在
    resp = requests.get(f"https://api.shipping.com/batches/{batch.ref}")
    if resp.status_code == 200:
        # 已存在，使用 PUT
        requests.put(..., json=...)
    else:
        # 不存在，使用 POST
        requests.post(..., json=...)
```

这对我们的测试有什么影响？为这个示例编写测试，我现在需要修补的不仅仅是 `requests` 模块，还有 `uuid` 模块，因为我需要确保 GET 请求检查的对象 ID 与 `create_shipping` 函数生成的 `uuid` 匹配。

```python
def test_create_shipping_for_existing():
    with patch('module.uuid.uuid4') as mock_uuid, \
         patch('module.requests.get') as mock_get, \
         patch('module.requests.put') as mock_put:
        # 设置模拟返回值
        mock_uuid.return_value = ...
        mock_get.return_value.status_code = 200

        create_shipping(...)

        # 断言 PUT 被调用
        mock_put.assert_called_once_with(...)
```

测试变得更长、更复杂。我有两个模拟对象，这种测试有点乏味。

**第三个业务需求**：我们需要轮询第三方 API 以获取最新的预计到达时间（ETA）。

又有很多代码。你可能需要许多测试来完成这类事情。我试着编写的代码看起来更像我们每天使用的典型业务代码。

```python
def poll_for_updates():
    batches = get_all_batches_from_db()
    for batch in batches:
        latest_eta = get_latest_eta_from_api(batch.ref)
        if latest_eta != batch.eta:
            # 通知延迟
            notify_delay(batch)
        if is_large_shipment(batch):
            # 触发另一个流程
            trigger_special_process(batch)
```

根据我的计算，我们可能有 12 个或更多的测试，每个测试都要模拟三四个不同的东西。这导致了“模拟恐怖”：每个测试都有五六个不同的模拟，很难理解到底发生了什么。

此外，模拟测试很脆弱。你的每个补丁都依赖于特定的导入方式（例如 `from requests import post`）。如果你决定改用 `requests.Session` 以提高性能，或者对实现进行微小更改，你所有的模拟测试都可能被破坏。

### 模拟对象的利弊总结

让我们回顾一下模拟对象的利弊。

**优点**：
*   **熟悉**：开发者熟悉这种模式。
*   **低努力（初始）**：我可以直接使用模拟，而不必费力改变现有代码结构。

**缺点**：
*   **测试实现细节**：你的测试在验证如何调用第三方（如 `requests.post`），而不是验证业务逻辑（如“如果货物延迟，则通知相关人员”）。
*   **容易遗漏**：你需要记住在每个可能与第三方 API 对话的测试上添加模拟补丁，否则测试会变慢或失败。
*   **鼓励耦合**：它使得业务逻辑（业务规则）与基础设施细节（JSON 格式、端点 URL）混杂在一起。
*   **仍然需要集成测试**：即使有模拟测试，你仍然需要一些端到端的测试来确保事情真的有效。你可能会滑向我朋友 Ed Jung 所说的“模拟地狱”。

既然我们看到了模拟地狱，让我们来谈谈替代方案。

## 替代方案一：构建适配器 🧩

那么，我们该怎么办？以下是我的第一个建议：**构建适配器**。

我说的“适配器”是什么意思？我指的是将我调用的 API 包装起来，将其从我们应用程序的核心业务逻辑中分离出来。“适配器”这个词借鉴了“端口与适配器”架构模式（也称为六边形架构、洋葱架构或整洁架构）。

让我们看看在这个例子中它是什么样子。我将使用一个类来表示我的适配器（你也可以不使用类）。

```python
class ShippingAPI:
    def __init__(self, base_url):
        self.base_url = base_url

    def sync(self, batch):
        """将货物与外部系统同步"""
        # 内部处理 POST/PUT 逻辑
        if self._batch_exists(batch.ref):
            self._update_batch(batch)
        else:
            self._create_batch(batch)

    def get_latest_eta(self, batch_ref):
        """获取最新的预计到达时间"""
        resp = requests.get(f"{self.base_url}/batches/{batch_ref}")
        return resp.json()['eta']

    def _batch_exists(self, batch_ref):
        # 私有方法，检查批次是否存在
        ...

    def _create_batch(self, batch):
        # 私有方法，创建批次
        ...

    def _update_batch(self, batch):
        # 私有方法，更新批次
        ...
```

现在，我的业务逻辑（`create_shipping`）可以用我自己的语言与这个适配器交互，而不是直接处理第三方的细节。

```python
def create_shipping(products, quantity, incoterm, shipping_api): # 注意新增的参数
    batch_ref = str(uuid.uuid4())
    batch = Batch(ref=batch_ref, eta=..., lines=...)
    batch.save()

    # 使用适配器同步
    shipping_api.sync(batch)
```

这对我们的测试有什么影响？我们不再修补 `requests` 模块，而是模拟我们自己的 `ShippingAPI` 类。

```python
def test_create_shipping():
    mock_shipping_api = Mock(spec=ShippingAPI)
    create_shipping(..., shipping_api=mock_shipping_api)
    mock_shipping_api.sync.assert_called_once_with(...)
```

与之前断言 `mock_post.assert_called_once_with(...)` 相比，这至少简化了一点。因为我不是在模拟一个可以做数百件事的复杂库（`requests`），而是在模拟一个只有少数我定义的方法的简单接口。

### 适配器的利弊

**优点**：
*   **解耦**：将基础设施代码与业务逻辑解耦。业务逻辑现在说“我需要同步”，而不关心是 POST 还是 PUT。
*   **模拟更简单**：模拟一个简单的适配器接口比模拟一个复杂的第三方库更容易，也更有信心。
*   **未来证明**：如果以后要更换第三方（例如从 JSON 换到 XML），业务逻辑的测试不需要改变。

**缺点**：
*   **更多代码**：必须构建这个适配器类，增加了额外的复杂性层。
*   **理解成本**：其他人可能需要理解“`ShippingAPI.sync()`”具体做了什么，而直接看 `requests.post` 可能更直观。

但这只是第一步。我们不会就此止步。

## 替代方案二：伪造你的适配器 🎭

本次演讲的标题是“停止使用模拟对象”。让我们继续下一个建议：**伪造你的适配器**。

第一部分：与其使用模拟对象（Mock），我鼓励你制造一个“伪造对象”（Fake）。伪造对象和模拟对象有什么区别？我不想太纠结于此，但基本上：
*   **模拟对象** 是一个你可以事后询问的对象（“你被调用了吗？怎么调用的？”）。
*   **伪造对象** 是一个你用来替换真实依赖的简化但可工作的实现。它不会记录调用，而是实际执行一些逻辑（通常在内存中）。

让我们在现实生活中看看。你可以定义一个抽象基类或协议（如果你喜欢类型提示和 `typing.Protocol`），来说明 `ShippingAPI` 需要哪些方法。

```python
# 使用 Protocol 定义接口
from typing import Protocol

class ShippingAPIProtocol(Protocol):
    def sync(self, batch) -> None: ...
    def get_latest_eta(self, batch_ref): ...

# 真实实现
class RealShippingAPI:
    def __init__(self, base_url):
        self.base_url = base_url
    def sync(self, batch): ... # 真实的网络调用
    def get_latest_eta(self, batch_ref): ... # 真实的网络调用

# 伪造实现
class FakeShippingAPI:
    def __init__(self):
        self._batches = {} # 内存存储

    def sync(self, batch):
        # 只是存储在内存字典中
        self._batches[batch.ref] = {
            'ref': batch.ref,
            'eta': batch.eta,
            # ... 其他属性
        }

    def get_latest_eta(self, batch_ref):
        # 从内存字典中查找
        return self._batches.get(batch_ref, {}).get('eta')

    # 一个方便的语法糖，用于测试断言
    def __contains__(self, batch_ref):
        return batch_ref in self._batches
```

现在，在测试中，我们可以使用这个伪造对象。

```python
def test_create_shipping():
    fake_api = FakeShippingAPI()
    create_shipping(..., shipping_api=fake_api)
    # 断言：货物应该出现在伪造的 API 中
    assert batch.ref in fake_api
```

我希望你会同意，这最终比我们之前那些 `mock_post.assert_called_once_with(...)` 的测试更具可读性。

### 伪造对象的利弊

**优点**：
*   **更可读的测试**：测试意图更清晰（“货物应出现在 API 中”）。
*   **施加设计压力**：这是一个有趣的概念。当你尝试为你的适配器编写一个伪造版本时，如果伪造起来非常困难，这可能是一个信号，表明你的适配器设计得太复杂了，也许应该拆分成更简单的部分。这有助于保持代码整洁。

**缺点**：
*   **更多测试代码**：必须构建和维护这个伪造类。
*   **维护负担**：每次更改真实适配器，都可能需要手动更新伪造版本，这在使用模拟对象时是不需要的。

## 替代方案三：依赖注入 💉

如果你觉得构建伪造对象听起来像很多工作，那么接下来的事情在 Python 世界可能有些争议：你应该尝试使用**依赖注入**。

如果这已经让你生气，让你觉得这像是“企业级 Java”的东西，别担心。我不想改变你的一生，我只是建议你尝试一下。与其在猴子补丁（`unittest.patch`）中替换依赖，不如通过参数显式传递它们。

```python
# 生产代码
def create_shipping(products, quantity, incoterm, shipping_api): # 依赖作为参数传入
    batch_ref = str(uuid.uuid4())
    batch = Batch(ref=batch_ref, eta=..., lines=...)
    batch.save()
    shipping_api.sync(batch) # 使用传入的 api
```

在测试中，我们不再需要 `mock.patch`。

```python
def test_create_shipping():
    fake_api = FakeShippingAPI()
    create_shipping(..., shipping_api=fake_api) # 直接传入伪造对象
    assert batch.ref in fake_api
```

我认为这是对这段代码最简单、最易理解的测试。与旧版本及其复杂的模拟补丁设置相比，这简单多了。

### 依赖注入的利弊

**优点**：
*   **更好的测试**：测试设置更简单、更清晰。
*   **依赖关系明确**：不可能在忘记模拟的情况下意外调用真实 API。函数签名清楚地表明了它的依赖。
*   **代码可读性**：查看函数签名就能立刻知道它依赖哪些外部服务，而不必深入实现细节去寻找 `import requests`。

**缺点**：
*   **更多的参数**：生产代码中函数签名变长，需要传递更多参数。
*   **传递负担**：如果 `create_shipping` 调用另一个函数 `recalculate_shipping`，而那个函数也需要 `shipping_api`，那么你就需要把这个参数传递一整条调用链，这可能很乏味。
    *   有方法可以缓解，比如使用依赖注入容器或特定的架构模式来组织代码，但这本身也增加了复杂性。

关于“不必要的参数”的争论，是我经常遇到的。人们觉得为了测试而让应用程序代码“变丑”是不可接受的。但请考虑：如果能让测试的编写和维护容易两倍，而只让应用代码的阅读和维护难度增加 10%，这可能是一笔很好的交易。至少值得一试。

## 如何测试适配器本身？ 🔍

你可能会说：“好了，哈利，我们不用模拟对象了。但我们仍然有最初的问题：你仍然需要一些真正的测试来检查适配器是否真的能与第三方工作！”

没错。对于适配器本身（即与第三方集成的代码），我建议最好的测试是**集成测试**。

集成测试可能是什么样子？我们可能最终还是会在这一层使用模拟对象，但让我们看看能否做得更好。

```python
# 集成测试示例
def test_shipping_api_sync():
    # 使用真实的沙箱环境 URL
    api = RealShippingAPI(base_url="https://sandbox.shipping.com")
    batch = create_test_batch()
    api.sync(batch)
    # 断言：通过 API 能成功查询到这批货
    retrieved_data = api._get_batch(batch.ref) # 假设有查询方法
    assert retrieved_data['eta'] == batch.eta
```

注意，这个测试关注的是行为（“同步后，数据能通过 API 正确检索”），而不是实现细节（“是否调用了 `requests.post`”）。

当然，集成测试也有其挑战：
*   **需要沙箱环境**：第三方需要提供可用的测试沙箱。
*   **速度慢且脆弱**：网络调用慢，沙箱环境可能不稳定。
*   **需要清理**：测试创建的数据需要清理，否则沙箱会堆积垃圾数据，影响后续测试。

这就引出了最后一个建议。

## 进阶建议：为集成测试构建伪造的第三方 🌐

如果你在集成真实第三方时遇到了真正的问题（沙箱慢、脆、难清理），为什么不为你集成的第三方构建一个伪造版本呢？

这听起来有点危险，但请忍耐一下。构建一个行为像第三方的简单伪造服务器（例如，用一个小的 Docker 容器）可能比你想象的要容易。大多数 REST API 本质上是 CRUD（创建、读取、更新、删除）。一个简单的内存存储就可以模拟很多行为。

**你能得到什么？**
*   **更可靠的测试**：测试不再受外部网络和第三方沙箱状态的影响。
*   **更快的测试**：所有交互都在本地内存或进程中完成。
*   **仍然可以测试适配器**：你仍然在测试你的适配器能进行正确的 HTTP 调用、JSON 编码/解码。
*   **选择性运行**：你仍然可以选择偶尔针对真实沙箱运行测试（例如，在 CI 的夜间构建中），而日常开发和 PR 验证则使用快速的伪造版本。

**需要注意**：
*   你现在有两套测试：一套针对伪造的第三方，一套针对真实的第三方。这引入了“契约测试”的概念——确保你的伪造版本与真实版本的行为一致。
*   有一个很酷的库叫 `vcrpy`，它可以记录真实 API 的响应并在测试中回放，这也是一个解决模拟问题的好方法，尽管有时也会变得复杂。

## 总结 🎯

回顾一下，我的建议是：

1.  **停止使用模拟对象（至少尝试一下）**。
2.  **构建一个适配器**：创建一个代表外部依赖的类或模块，用你的领域语言提供清晰的 API。
3.  **尝试使用伪造对象**：为你的适配器编写一个简化的、内存中的实现，并在测试中使用它，而不是模拟对象。
4.  **尝试依赖注入**：通过函数参数显式传递依赖，而不是在模块级别隐式导入并用猴子补丁替换。
5.  **使用集成测试来测试适配器**：针对真实沙箱或你构建的伪造第三方服务进行测试，以验证集成是否真正有效。

我们做这些是因为：
*   **更好的测试**：更易于阅读、编写和维护的测试。
*   **施加设计压力**：促使你思考如何将外部依赖分离成小而可管理的部分。
*   **强制解耦**：将核心业务逻辑与易变的基础设施细节分离，允许它们以不同的速率独立变化。

希望你喜欢这些想法。如果你决定尝试停止使用模拟对象，请告诉我进展如何。你可以在 Twitter 上找到我，或者写一篇博客文章。我很想听听你的经验。

![](img/70f450bbad5ae8f4921bcddae5be82cc_2.png)

![](img/70f450bbad5ae8f4921bcddae5be82cc_2.png)