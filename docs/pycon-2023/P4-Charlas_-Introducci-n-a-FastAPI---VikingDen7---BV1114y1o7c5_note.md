# FastAPI入门教程：P4：FastAPI简介

## 概述
在本节课中，我们将要学习FastAPI的基础知识。FastAPI是一个用于构建API的现代、快速（高性能）的Web框架。我们将了解它的核心特性、如何创建第一个API，以及它如何自动处理数据验证和生成文档。

![](img/961f621bdc0577b20c7f2804f8d9d1e3_1.png)

---

## 什么是FastAPI？🚀

FastAPI是一个基于Python的Web框架，专门用于构建API。它的设计目标是高性能、易于学习且快速编码。

FastAPI建立在标准Python类型提示之上，这带来了许多优势。

---

## 核心特性 ✨

上一节我们介绍了FastAPI的基本概念，本节中我们来看看它的核心特性。

以下是FastAPI的主要优点：

*   **高性能**：FastAPI的性能与NodeJS和Go相当，是现有Python框架中最快的之一。
*   **快速开发**：编码速度可提高约200%至300%。
*   **更少的Bug**：减少约40%的人为错误。
*   **直观**：强大的编辑器支持，处处皆可自动补全。
*   **简单**：设计易于使用和学习，阅读文档的时间更短。
*   **简洁**：最小化代码重复，每个参数声明可提供多重功能。
*   **健壮**：生产就绪的代码，带有自动交互式文档。
*   **基于标准**：完全兼容API的开放标准（OpenAPI和JSON Schema）。

---

## 创建你的第一个API 🛠️

了解了FastAPI的特性后，现在我们来动手创建第一个API。

首先，需要安装FastAPI和一个ASGI服务器，例如`uvicorn`。

```bash
pip install fastapi uvicorn
```

创建一个名为`main.py`的文件，并写入以下代码：

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
async def read_root():
    return {"Hello": "World"}
```

这段代码创建了一个简单的API，当你访问根路径`/`时，它会返回一个JSON响应`{"Hello": "World"}`。

使用以下命令运行服务器：

```bash
uvicorn main:app --reload
```

现在，打开浏览器访问 `http://127.0.0.1:8000`，你将看到`{"Hello": "World"}`。

---

## 路径参数与查询参数 🔍

在上一节中，我们创建了一个简单的端点。本节中，我们将学习如何通过路径参数和查询参数来接收用户输入。

### 路径参数
路径参数是URL路径的一部分。例如，在`/items/{item_id}`中，`item_id`就是一个路径参数。

```python
@app.get("/items/{item_id}")
async def read_item(item_id: int):
    return {"item_id": item_id}
```

FastAPI会自动将URL中的`item_id`转换为整数类型。如果传入的不是整数（如字符串），FastAPI会自动返回一个错误。

### 查询参数
查询参数是URL中`?`后面的键值对，例如`/items/?skip=0&limit=10`。

```python
@app.get("/items/")
async def read_items(skip: int = 0, limit: int = 10):
    return {"skip": skip, "limit": limit}
```

函数参数`skip`和`limit`不是路径的一部分，因此它们自动被识别为查询参数。`=0`和`=10`是它们的默认值。

---

## 请求体与Pydantic模型 📦

我们已经学会了如何通过URL传递参数。但有时我们需要接收更复杂的数据，比如JSON对象，这时就需要使用**请求体**。

FastAPI使用Pydantic模型来定义请求体的结构，这能确保数据的类型安全并自动生成文档。

以下是定义一个`Item`模型并用于POST请求的例子：

```python
from pydantic import BaseModel
from typing import Optional, List

![](img/961f621bdc0577b20c7f2804f8d9d1e3_3.png)

class Item(BaseModel):
    name: str
    description: Optional[str] = None
    price: float
    tax: Optional[float] = None
    tags: List[str] = []  # 定义一个字符串列表

@app.post("/items/")
async def create_item(item: Item):
    return item
```

![](img/961f621bdc0577b20c7f2804f8d9d1e3_5.png)

当你向`/items/`发送一个POST请求，并附带一个符合`Item`模型的JSON数据时，FastAPI会自动：
1.  解析JSON。
2.  转换为相应的类型（如将字符串转为浮点数）。
3.  验证数据。如果数据无效（例如`price`是字符串`”hello”`），会返回清晰详细的错误信息。
4.  在交互式API文档中提供JSON模式。

---

## 自动交互式API文档 📖

FastAPI最强大的特性之一是自动生成交互式API文档。

运行你的应用后，你可以访问以下两个地址查看文档：

*   **Swagger UI 文档**：`http://127.0.0.1:8000/docs`
*   **ReDoc 文档**：`http://127.0.0.1:8000/redoc`

在这些文档中，你可以：
*   查看所有已定义的API端点。
*   看到每个端点所需的参数、请求体模型和响应模型。
*   **直接进行API调用测试**，无需使用其他工具如Postman。

文档完全基于你代码中的类型提示和Pydantic模型自动生成，确保了文档与代码的实时同步。

---

## 总结 🎯

本节课中我们一起学习了FastAPI的核心内容：

1.  **FastAPI是什么**：一个高性能、易学易用的现代Python Web API框架。
2.  **创建第一个API**：如何使用`@app.get()`装饰器定义端点并运行服务器。
3.  **处理输入**：如何使用**路径参数**和**查询参数**从URL获取数据。
4.  **处理复杂数据**：如何使用Pydantic模型定义**请求体**，实现强大的数据验证和类型转换。
5.  **自动文档**：FastAPI如何基于你的代码自动生成交互式API文档（Swagger UI和ReDoc），极大地提升了开发效率。

![](img/961f621bdc0577b20c7f2804f8d9d1e3_7.png)

FastAPI通过利用Python类型提示，在保持代码简洁的同时，提供了无与伦比的开发体验、运行速度和代码可靠性。它是构建现代API的优秀选择。