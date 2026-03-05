# Python时区处理：P22：演讲 - 本杰明·扎戈斯基 - 处理 Python 中的时区

![](img/da32327101e4d6f29aad8f16815471db_1.png)

在本教程中，我们将学习如何在Python中正确处理时区。时区问题看似简单，实则复杂，是软件开发中常见的错误来源。我们将从避免常见错误开始，然后学习正确的时区处理模型，并通过代码示例演示如何解决实际问题。最后，我们会简要介绍Django框架中的时区工具。

## 概述：为什么时区如此重要？

一个看似简单的问题：“今天的日期是什么？” 答案取决于你所在的时区。这揭示了时区的复杂性。无论你是否意识到，只要你处理日期或时间，你就在处理时区。忽略时区会导致难以调试的错误，例如用户在不同地区看到错误的日期，或者在夏令时切换时出现计算错误。

即使你的所有用户都在同一个时区，你仍然需要考虑时区规则，比如夏令时。历史数据也可能涉及不同的时区规则。因此，从一开始就在代码库中正确支持时区至关重要。

Python 3.9 引入了 `zoneinfo` 模块，为标准库提供了完整的时区支持，这标志着社区处理时区方式的转变。

## 第一部分：时区处理的常见陷阱 🚫

上一节我们概述了时区的重要性，本节中我们来看看在Python中处理时区时**绝对不应该做**的事情。这些做法是“平均开发者”不期望的，容易引入隐蔽的错误。如果你确实需要这样做，务必添加详细注释。

以下是几个关键的陷阱：

### 1. 不要使用“天真”的日期时间对象

在Python中，`datetime`对象包含年、月、日、时、分、秒等信息，以及一个可选的 `tzinfo` 属性用于存储时区。一个没有附加时区信息的`datetime`对象被称为“天真”的。

*   **问题**：`datetime(2022, 1, 1, 12, 0, 0)` 表示的是“2022年元旦中午”这个概念，但它对应着地球上从UTC-12到UTC+14共26个小时范围内的**多个不同时间点**。这造成了巨大的模糊性。
*   **结论**：如果你构造的`datetime`意在表示一个具体的时间点（过去、现在或未来），**务必为其附加时区信息**。

### 2. 不要使用不带时区的 `datetime.now()` 和 `date.today()`

*   **`datetime.now()`**：
    *   **问题**：不带参数调用时，它返回一个“天真”的`datetime`，其值依赖于运行代码的**系统本地时间**。同一时刻在不同时区的服务器上运行会得到不同结果，这是非确定性的，且难以在本地测试中发现。
    *   **错误示例**：`naive_now = datetime.now()`
*   **`date.today()`**：
    *   **问题**：它从系统本地时间提取日期。东京用户在午夜提交表单时，服务器（可能在其他时区）可能仍认为是“昨天”，导致验证错误。
    *   **错误示例**：`today = date.today() # 可能得到错误的日期`

### 3. 不要在非UTC时区进行“持续时间”算术

“持续时间”算术指在两个时间点之间做加减（例如，`datetime1 - datetime2` 或 `datetime1 + timedelta(hours=2)`）。

*   **问题**：在有时区间断（如夏令时）的时区进行加减，结果可能不符合直觉。Python的加减操作是基于**挂钟时间**的，而不是固定的时间间隔。
*   **示例**：在美国东部时间（EST/EDT）夏令时开始前30分钟（凌晨1:30）加上2小时，结果可能是凌晨4:30（因为跳过了1小时），而不是你期望的3:30。
*   **结论**：进行持续时间计算时，**应先将时间转换到UTC**，在UTC下计算，然后再转换回目标时区。

### 4. 不要使用 `pytz` 库（如果可能）

*   **问题**：`pytz`是一个历史悠久的库，但它与Python标准库处理时区的方式不兼容，可能导致错误的UTC偏移量计算。
*   **解决方案**：使用Python 3.9+标准库中的 `zoneinfo` 模块，或者其向后移植包 `backports.zoneinfo`。

### 5. 不要对有“时区意识”的日期时间使用 `replace(tzinfo=...)`

*   **问题**：`replace` 方法会直接替换时区信息，**而不进行时间转换**。这会导致同一个`datetime`对象表示的时间点发生改变。
*   **示例**：`utc_dt` (UTC时间) 被 `replace` 为美国东部时区后，其表示的实际时间点会偏移数小时。
*   **正确做法**：要转换时区，请使用 `astimezone()` 方法。

## 第二部分：正确的时区处理模型 🗺️

上一节我们介绍了需要避免的陷阱，本节中我们来看看如何从高层次构建正确的时区处理模型。核心思想是：**以UTC为中心，在边界进行转换**。

### 理解UTC

UTC（协调世界时）是所有时区计算的基准。
*   **没有时间间断**：没有夏令时、没有奇怪的日期变更，是进行数学运算的安全环境。
*   **所有时区都基于UTC**：每个时区都定义为相对于UTC的偏移量（如UTC-5, UTC+8）。
*   **理想的内部存储格式**：在系统内部、数据库、API间传递时，应始终使用UTC。

### 核心处理流程图

以下是处理时区的核心模型：

```
[用户输入 (带时区)] -> [转换为UTC] -> [在UTC下存储/计算] -> [转换为用户时区] -> [输出给用户]
```

**解释**：
1.  **输入边界**：从用户那里获取时间信息时，必须同时知道其所在的时区（例如，通过表单字段或用户配置）。将这些信息组合成一个“有时区意识”的`datetime`对象，然后立即**转换为UTC**。
2.  **内部处理**：在代码内部、数据库存储、服务间通信时，**始终使用UTC**。在这里进行所有的持续时间计算、比较和逻辑处理。
3.  **输出边界**：当需要向用户展示时间时，将UTC时间**转换回用户的本地时区**，再格式化为字符串或提取日期。

**例外：日历算术**
如果你想“将日期推迟3天”，这属于日历操作，而不是持续时间计算。应该在**日期对象**上进行，或者在转换到用户时区后，在本地日期上进行，以避免夏令时导致的偏差。

## 第三部分：Python代码示例 💻

上一节我们建立了理论模型，本节中我们来看看如何用Python代码实现它。我们将使用Python 3.9+的`zoneinfo`模块。

首先，确保你有时区数据：
```python
# 安装 backports.zoneinfo (适用于 Python < 3.9)
# pip install backports.zoneinfo

# 同时安装 tzdata 以确保时区数据可用
# pip install tzdata
```

### 1. 获取当前时间和日期

**获取当前UTC时间（带时区信息）**：
```python
from datetime import datetime, timezone
now_utc = datetime.now(timezone.utc)
# 输出： datetime.datetime(2023, 10, 27, 8, 30, 0, 123456, tzinfo=datetime.timezone.utc)
```

**获取特定时区的当前日期**：
```python
from zoneinfo import ZoneInfo
eastern = ZoneInfo(“America/New_York”)
now_eastern = datetime.now(eastern)
date_in_eastern = now_eastern.date() # 安全地获取美国东部时区的当前日期
```

### 2. 时间输入处理

**从组件构造（已知时区）**：
```python
user_input_dt = datetime(2023, 3, 13, 1, 30, tzinfo=eastern) # 直接附加时区
utc_dt = user_input_dt.astimezone(timezone.utc) # 立即转换为UTC存储
```

**处理“天真”的日期时间（必须附加时区）**：
```python
naive_dt = datetime(2023, 3, 13, 1, 30) # 假设来自某个库，没有时区
# 在附加时区前，检查它是否是“天真”的
if naive_dt.tzinfo is None:
    aware_dt = naive_dt.replace(tzinfo=eastern) # 正确：为“天真”对象附加时区
else:
    raise ValueError(“Datetime already has timezone info!”)
utc_dt = aware_dt.astimezone(timezone.utc)
```

**解析ISO 8601字符串**：
```python
iso_string = “2023-03-13T01:30:00-05:00” # 包含偏移量
dt_from_iso = datetime.fromisoformat(iso_string) # Python 3.7+
# dt_from_iso 已经是“有时区意识”的（但时区是简单的固定偏移时区）
utc_dt = dt_from_iso.astimezone(timezone.utc) # 转换为UTC
```

### 3. 时间输出处理

**转换为用户本地时间并格式化**：
```python
# 假设 utc_dt 是UTC时间，user_tz 是用户的时区（如 ZoneInfo(“Asia/Tokyo”)）
user_local_dt = utc_dt.astimezone(user_tz)
formatted_string = user_local_dt.strftime(“%Y-%m-%d %H:%M:%S %Z”)
```

**从UTC时间获取用户本地日期**：
```python
user_local_date = utc_dt.astimezone(user_tz).date()
```

### 4. 持续时间与日历算术

**正确的持续时间加法（在UTC下进行）**：
```python
from datetime import timedelta
# 在UTC下进行加法
utc_dt_plus_2h = utc_dt + timedelta(hours=2)
# 需要时再转换回本地时间
local_dt_plus_2h = utc_dt_plus_2h.astimezone(user_tz)
```

**正确的日历日期加法（在日期对象上进行）**：
```python
from datetime import date, timedelta
user_local_date = utc_dt.astimezone(user_tz).date()
date_plus_120_days = user_local_date + timedelta(days=120) # 直接操作 date 对象
```

## 第四部分：Django中的时区处理 🎸

如果你使用Django框架，它提供了一套强大的工具来简化时区处理。

### 1. 启用时区支持

在 `settings.py` 中确保以下设置：
```python
USE_TZ = True # 默认在Django 5+为True，请手动设置为True
TIME_ZONE = ‘UTC’ # 项目的默认时区。如果所有用户在同一时区，可设为此处。
```

### 2. 处理用户时区

最佳实践是在用户模型上存储其首选时区（如 `”America/New_York”`），并通过中间件为每个请求激活该时区。

**示例中间件**：
```python
import zoneinfo
from django.utils import timezone

class TimezoneMiddleware:
    def __init__(self, get_response):
        self.get_response = get_response

    def __call__(self, request):
        if request.user.is_authenticated:
            # 假设 user.timezone 存储着类似 “America/New_York” 的字符串
            tz_name = request.user.timezone
            try:
                timezone.activate(zoneinfo.ZoneInfo(tz_name))
            except zoneinfo.ZoneInfoNotFoundError:
                pass # 回退到默认 TIME_ZONE
        else:
            timezone.deactivate()
        response = self.get_response(request)
        return response
```
将其添加到 `MIDDLEWARE` 设置中。

### 3. Django的时区工具

激活时区后，Django会自动帮你做很多转换：

*   **模板中自动转换**：在模板中渲染一个UTC的 `datetime` 字段时，Django会自动将其转换为当前激活的时区。
*   **实用函数**：
    ```python
    from django.utils import timezone

    now_utc = timezone.now() # 返回带UTC时区的当前时间
    local_now = timezone.localtime() # 转换为当前激活的时区
    local_date = timezone.localdate() # 获取当前激活时区的日期

    # 处理输入：将“天真”的datetime变为“有意识”的
    naive_dt = datetime(2023, 3, 13, 1, 30)
    aware_dt = timezone.make_aware(naive_dt, timezone.get_current_timezone())
    utc_dt = aware_dt.astimezone(timezone.utc)
    ```

**Django模型**：当 `USE_TZ = True` 时，Django的 `DateTimeField` 在数据库中以UTC存储，并在读取时根据当前时区自动处理。

## 总结

在本教程中，我们一起学习了如何在Python中有效处理时区：

1.  **避免陷阱**：绝不使用“天真”的`datetime`，小心 `now()`/`today()`，在UTC下进行持续时间计算，用 `zoneinfo` 替代 `pytz`，正确使用 `astimezone()` 而非 `replace()`。
2.  **遵循模型**：确立 **“内部用UTC，边界做转换”** 的核心原则。所有内部逻辑和存储均使用UTC，仅在接收用户输入和向用户输出时进行时区转换。
3.  **使用代码**：我们演示了如何使用 `zoneinfo.ZoneInfo` 创建时区对象，如何安全地获取、转换、格式化和计算时间。
4.  **利用框架**：在Django中，通过设置 `USE_TZ = True`、存储用户时区、编写中间件来激活时区，可以极大地简化开发工作，让框架自动处理模板渲染和数据库层面的时区转换。

记住，时区问题不会消失。通过从一开始就采用这些最佳实践，你可以构建出健壮、可维护且全球适用的应用程序。

![](img/da32327101e4d6f29aad8f16815471db_3.png)

---
*致谢：感谢 Paul Ganssle 创建了 `zoneinfo` 模块并将其贡献给 Python 标准库。*