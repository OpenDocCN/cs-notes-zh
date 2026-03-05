# Pydantic 简介：1：Python 数据类的运行时类型检查 🧑‍💻

![](img/98d3126a31287dc7ece0555ee1b7c225_1.png)

![](img/98d3126a31287dc7ece0555ee1b7c225_2.png)

在本教程中，我们将学习 Pydantic 库。Pydantic 是一个 Python 库，它利用 Python 的类型注解在运行时强制执行数据验证和设置管理。我们将从回顾 Python 数据类开始，逐步探索 Pydantic 的核心功能，包括数据验证、JSON 序列化、自定义验证器以及与 Web 框架的集成。

---

## Python 数据类快速回顾 📝

在深入了解 Pydantic 之前，我们先快速回顾一下 Python 的数据类。数据类（`@dataclass`）是 Python 3.7+ 引入的一个装饰器，用于自动生成特殊方法（如 `__init__` 和 `__repr__`）的类，非常适合用来存储数据。

假设我们经营一家名为 WaffleBistro 的华夫饼店，我们需要对华夫饼订单进行建模。一个简单的数据类可能如下所示：

```python
from dataclasses import dataclass
from typing import List

@dataclass
class Waffle:
    style: str
    toppings: List[str]
```

我们可以轻松创建华夫饼对象：

```python
waffle = Waffle(style="Swedish", toppings=["chocolate sauce", "ham"])
```

然而，这个模型存在一个问题：`style` 和 `toppings` 被定义为字符串列表，这意味着我们可以传入任何字符串值，即使它不符合业务逻辑（例如，在华夫饼上加火腿）。静态类型检查器（如 `mypy`）可能会在开发时捕获类型错误，但在运行时，程序不会阻止这种无效数据的创建。

为了解决这个问题，我们可以尝试使用枚举（Enum）来限制可选值：

```python
from enum import Enum
from dataclasses import dataclass
from typing import List

class Topping(Enum):
    WHIPPED_CREAM = "whipped cream"
    ICE_CREAM = "ice cream"

class Sauce(Enum):
    CLOUDBERRY_JAM = "cloudberry jam"
    RASPBERRY_JAM = "raspberry jam"
    CHOCOLATE_SAUCE = "chocolate sauce"

class WaffleStyle(Enum):
    SWEDISH = "Swedish"
    BELGIAN = "Belgian"

@dataclass
class Waffle:
    style: WaffleStyle
    toppings: List[Union[Topping, Sauce]]
```

尽管使用了枚举，Python 数据类在运行时仍然不会强制执行这些类型约束。以下代码不会引发错误：

```python
# 这仍然可以创建，尽管火腿不是有效的 Topping 或 Sauce
invalid_waffle = Waffle(style=WaffleStyle.SWEDISH, toppings=["ham"])
```

因此，我们需要一种在运行时进行类型检查的机制。这就是 Pydantic 的用武之地。

---

## 引入 Pydantic ✅

Pydantic 是一个库，它允许你在运行时强制执行 Python 类型注解。它与数据类兼容，但功能更强大。Pydantic 提供友好的错误信息、内置序列化支持，并且完全基于标准的 Python 类型注解，没有特殊的语法要求。

Pydantic 有几个关键优势：
*   **运行时类型检查**：确保数据符合定义的模型。
*   **数据解析与转换**：自动将输入数据（如 JSON、字典）转换为正确的 Python 类型。
*   **易于使用**：只需继承 `BaseModel` 或使用 `@pydantic.dataclasses.dataclass` 装饰器。
*   **出色的文档**：拥有全面且清晰的文档。

现在，让我们看看如何用 Pydantic 解决华夫饼的问题。

---

## 运行时类型检查 🔍

上一节我们看到了纯数据类在运行时验证上的不足。本节中，我们来看看如何使用 Pydantic 在创建对象时进行类型检查。

首先，我们需要从 Pydantic 导入数据类装饰器：

```python
from enum import Enum
from typing import List, Union
from pydantic.dataclasses import dataclass

# 使用之前定义的 Enum: Topping, Sauce, WaffleStyle

@dataclass
class Waffle:
    style: WaffleStyle
    toppings: List[Union[Topping, Sauce]]
```

现在，当我们尝试用无效数据创建 `Waffle` 对象时，Pydantic 会在运行时抛出一个清晰的验证错误：

```python
try:
    invalid_waffle = Waffle(style=WaffleStyle.SWEDISH, toppings=["ham"])
except Exception as e:
    print(e)
```
**输出示例**：
```
ValidationError: 2 validation errors for Waffle
toppings -> 0
  value is not a valid enumeration member; permitted: <Topping.WHIPPED_CREAM: 'whipped cream'>, <Topping.ICE_CREAM: 'ice cream'>, <Sauce.CLOUDBERRY_JAM: 'cloudberry jam'>, <Sauce.RASPBERRY_JAM: 'raspberry jam'>, <Sauce.CHOCOLATE_SAUCE: 'chocolate sauce'> (type=type_error.enum)
```

错误信息明确指出了哪个字段（`toppings` 的第 0 个元素）出了问题，以及允许的值有哪些。Pydantic 还会尝试解析数据，例如，如果你传入字符串 `"whipped cream"`，它会自动转换为 `Topping.WHIPPED_CREAM` 枚举成员。

```python
# Pydantic 自动将字符串解析为对应的枚举
valid_waffle = Waffle(style="Swedish", toppings=["whipped cream", "cloudberry jam"])
print(valid_waffle)
# 输出: Waffle(style=<WaffleStyle.SWEDISH: 'Swedish'>, toppings=[<Topping.WHIPPED_CREAM: 'whipped cream'>, <Sauce.CLOUDBERRY_JAM: 'cloudberry jam'>])
```

---

## 使用 BaseModel 与 JSON 支持 📄

虽然 Pydantic 的数据类很好用，但直接继承 `BaseModel` 类能提供更多功能，尤其是一流的 JSON 支持。

让我们将 `Waffle` 类改为继承自 `BaseModel`：

```python
from pydantic import BaseModel
from enum import Enum
from typing import List, Union

# ... 枚举定义同上 ...

class Waffle(BaseModel):
    style: WaffleStyle
    toppings: List[Union[Topping, Sauce]]

    class Config:
        # 允许使用枚举值（字符串）进行实例化
        use_enum_values = True
```

创建对象的方式类似，但通常使用关键字参数：

```python
waffle = Waffle(style=WaffleStyle.SWEDISH, toppings=[Topping.WHIPPED_CREAM, Sauce.CLOUDBERRY_JAM])
```

`BaseModel` 的强大之处在于其内置的序列化方法。以下是如何将对象转换为 JSON 以及从 JSON 重建对象：

```python
# 序列化为 JSON 字符串
json_str = waffle.json()
print(json_str)
# 输出: {"style": "Swedish", "toppings": ["whipped cream", "cloudberry jam"]}

# 从 JSON 字符串反序列化（解析）为对象
reconstructed_waffle = Waffle.parse_raw(json_str)
print(reconstructed_waffle)
# 输出: style='Swedish' toppings=['whipped cream', 'cloudberry jam']
```

当验证失败时，Pydantic 提供了结构化的错误信息，非常适合 API 开发：

```python
try:
    invalid = Waffle.parse_raw('{"style": 42, "toppings": ["ham"]}')
except Exception as e:
    error_dict = e.json()
    print(error_dict)
```
**输出示例**（格式化后）：
```json
[
  {
    "loc": ["style"],
    "msg": "value is not a valid enumeration member; permitted: 'Swedish', 'Belgian'",
    "type": "type_error.enum"
  },
  {
    "loc": ["toppings", 0],
    "msg": "value is not a valid enumeration member; permitted: 'whipped cream', 'ice cream', 'cloudberry jam', 'raspberry jam', 'chocolate sauce'",
    "type": "type_error.enum"
  }
]
```

---

## 自定义验证器与业务逻辑 ⚙️

内置的类型检查很强大，但现实中的业务规则往往更复杂。Pydantic 允许你定义自定义验证器来实施这些规则。

假设 WaffleBistro 有以下业务规则：
1.  瑞典风格华夫饼只允许搭配果酱（`Sauce`）。
2.  比利时风格华夫饼允许搭配巧克力酱。
3.  一份华夫饼不能同时包含冰淇淋和打发奶油。

我们可以通过创建一个继承自 `Waffle` 的 `WaffleOrder` 类，并添加根验证器来实现这些规则：

```python
from pydantic import BaseModel, validator, root_validator
from typing import List, Union

class WaffleOrder(Waffle): # 继承自之前的 Waffle(BaseModel)
    @root_validator(pre=False, skip_on_failure=True)
    def check_order_rules(cls, values):
        style = values.get('style')
        toppings = values.get('toppings', [])

        # 规则 1 & 2: 检查风格与酱料的搭配
        if style == WaffleStyle.SWEDISH:
            for topping in toppings:
                if isinstance(topping, Sauce) and topping == Sauce.CHOCOLATE_SAUCE:
                    raise ValueError('WaffleBistro does not sell Swedish waffles with chocolate sauce.')
        # 注意：比利时风格允许巧克力酱，所以无需额外检查

        # 规则 3: 检查奶油类配料的数量
        cream_toppings = [t for t in toppings if isinstance(t, Topping)]
        if len(cream_toppings) > 1:
            raise ValueError('Only one cream topping (whipped cream or ice cream) is allowed.')

        return values
```

现在，让我们测试这些验证器：

```python
# 有效的订单
order1 = WaffleOrder(style="Swedish", toppings=["whipped cream", "cloudberry jam"])
print("Order 1 valid:", order1)

# 无效的订单：同时包含冰淇淋和奶油
try:
    order2 = WaffleOrder(style="Belgian", toppings=["ice cream", "whipped cream", "chocolate sauce"])
except ValueError as e:
    print("Order 2 error:", e)

# 无效的订单：瑞典华夫饼配巧克力酱
try:
    order3 = WaffleOrder(style="Swedish", toppings=["whipped cream", "chocolate sauce"])
except ValueError as e:
    print("Order 3 error:", e)
```

---

## 函数参数验证 🛠️

除了验证类，Pydantic 还可以验证函数参数。`validate_arguments` 装饰器（在 Pydantic 1.5+ 中引入）可以自动验证传递给函数的参数。

```python
from pydantic import validate_arguments
from typing import Union

@validate_arguments
def make_waffle_order(order: WaffleOrder) -> str:
    # 业务逻辑：处理订单
    return f"Order received: {order.style} waffle with {', '.join([str(t) for t in order.toppings])}"

# 有效的调用
result = make_waffle_order({"style": "Belgian", "toppings": ["ice cream", "chocolate sauce"]})
print(result) # 字典会被自动解析为 WaffleOrder 对象

# 无效的调用会抛出验证错误
try:
    make_waffle_order({"style": "Breakfast", "toppings": ["ham"]})
except Exception as e:
    print(e)
```

---

## 框架集成 🌐

Pydantic 与许多流行的 Python Web 框架有着良好的集成，这使得它在构建 API 时特别有用。

以下是支持 Pydantic 的部分框架：
*   **FastAPI**：深度集成，用于请求和响应模型，自动生成 API 文档。
*   **Starlette**：通过 `pydantic` 和 `requests`/`responses` 集成。
*   **Flask**：可通过扩展（如 `flask-pydantic`）或手动使用。
*   **Django Ninja**：为 Django 提供类似 FastAPI 的体验。
*   **Quart-Schema**：为异步框架 Quart 提供 Pydantic 集成。

一个使用 FastAPI 的简单示例如下：

```python
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()

class WaffleOrder(BaseModel):
    style: str
    toppings: List[str]

@app.post("/order/")
async def create_order(order: WaffleOrder):
    # `order` 参数已经过 Pydantic 验证
    # 处理订单的业务逻辑...
    return {"message": "Order placed!", "order_details": order.dict()}

@app.get("/order/{order_id}")
async def get_order(order_id: int):
    # 获取订单逻辑...
    return {"order_id": order_id}
```

FastAPI 会自动为这个端点生成交互式 API 文档（Swagger UI），并且所有传入 `create_order` 的数据都会根据 `WaffleOrder` 模型进行验证。

---

## 其他实用功能与总结 🎯

Pydantic 还有许多其他有用的功能：
*   **JSON Schema 生成**：可以使用 `WaffleOrder.schema()` 或 `WaffleOrder.schema_json()` 为模型生成 JSON Schema，这对于生成 OpenAPI 文档非常有用。
*   **设置管理**：Pydantic 的 `BaseSettings` 类非常适合管理应用程序配置，可以从环境变量、文件等来源加载设置。
*   **严格模式**：正在开发中的功能，将提供更严格的类型强制（例如，禁止字符串到枚举的自动转换）。
*   **性能**：Pydantic 的核心部分用 Cython 编写，速度很快。
*   **测试支持**：可以与 `hypothesis` 等测试库配合，进行基于属性的测试。

![](img/98d3126a31287dc7ece0555ee1b7c225_4.png)

**总结**

在本教程中，我们一起学习了 Pydantic 库的核心概念。我们从 Python 数据类的局限性出发，看到了 Pydantic 如何通过运行时类型检查来解决这些问题。我们探索了如何使用 `BaseModel` 进行数据验证和 JSON 序列化，如何编写自定义验证器来实现复杂的业务逻辑，以及如何验证函数参数。最后，我们了解了 Pydantic 如何与 FastAPI 等 Web 框架无缝集成，极大地简化了 API 的开发和数据验证工作。

![](img/98d3126a31287dc7ece0555ee1b7c225_6.png)

Pydantic 的核心优势在于它使用纯 Python 类型注解，提供了强大的运行时验证、友好的错误提示和出色的工具链集成。无论是小型脚本还是大型生产应用，它都是一个非常有价值的工具。建议你通过实际项目来尝试使用 Pydantic，以充分体验其便利性。