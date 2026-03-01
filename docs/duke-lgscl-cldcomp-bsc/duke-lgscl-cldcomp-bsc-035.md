# 035：使用Google Cloud Functions 🚀

![](img/da2a22497a2c2f7f7591d28389eeed8a_0.png)

在本节课中，我们将学习Google Cloud Functions（GCF）的基础知识。这是一种无服务器计算服务，允许你运行代码以响应事件，而无需管理服务器。我们将从架构概述开始，然后逐步学习如何创建、配置、测试和部署一个简单的云函数。

## 概述

Google Cloud Functions 是一种事件驱动的无服务器计算平台。它允许开发者编写单一用途的函数，这些函数在特定事件（如文件上传、消息发布或HTTP请求）发生时被触发执行。其核心优势在于无需管理基础设施，支持多种编程语言，并且可以轻松集成到Google Cloud生态系统中。

## Google Cloud Functions 架构

理解Google Cloud Functions的架构是掌握其在Google Cloud平台上如何工作的最佳方式。

架构的第一步是**事件触发器**。在触发器系统中，你可以监听多种事件。例如，你可以监听存储事件，当有图像或文本文件被放入存储桶时，它会调用云函数。同样，你可以设置一个发布/订阅系统，当流数据作为消息传入时，也可以触发云函数。其中更简单的一种是**HTTP触发器**，即通过向一个URL发送POST请求并附带有效载荷来调用函数。

Google Cloud Functions 的一个显著优点是它支持多种语言，包括Go、Python、C#、Ruby、Node.js等几乎所有现代语言。这些函数可以通过命令行界面或HTTP请求轻松进行测试。

## 创建你的第一个云函数

上一节我们介绍了GCF的架构，本节中我们来看看如何在Google Cloud控制台中实际创建一个函数。

首先，进入Google Cloud Functions控制台，点击“创建函数”。你会注意到有两个版本：第一代和第二代。第二代提供了更多的触发器和事件类型，功能也更强大，但目前仍处于初步阶段。本教程将使用第一代进行演示。

以下是创建函数的主要步骤：

1.  **为函数命名**：例如，可以命名为 `hello-world`。
2.  **选择触发器类型**：对于初学者，从**HTTP触发器**开始是个好选择。当然，你也可以配置其他触发器，如发布/订阅、云存储、Firestore或数据库事件。一个良好的默认设置是要求调用者进行身份验证，除非你确定要创建一个公开的API。
3.  **选择运行时和编写代码**：点击“下一步”后，选择你想要的编程语言。Google Cloud Functions 支持众多选项，包括 .NET、Go、Java、PHP、Python、Ruby等。选择 `Python 3.11`。对于所有语言，GCF都提供了包管理功能，允许你安装依赖项。你只需将依赖项名称列在指定区域即可。代码编辑区会提供一个入口函数。例如，函数名 `hello_world` 与入口点名称匹配。该函数接收一个请求对象，你可以解析其中的数据并返回响应。
4.  **部署函数**：编写完代码后，点击“部署”按钮即可。部署完成后，函数就可以被调用了。

## 编写与测试函数代码

现在，让我们深入代码部分，并学习如何测试它。我们将创建一个稍微复杂一点的Python函数。

以下是一个示例函数，它检查HTTP请求体中是否包含特定的名字：

```python
def hello_world(request):
    request_json = request.get_json()
    if request_json and ‘name’ in request_json:
        name = request_json[‘name’]
        if name.lower() == ‘marco’:
            return ‘Polo!’
        else:
            return f‘I don‘t know you, {name}.’
    else:
        return ‘Please provide a “name” in the request body.’
```

部署此函数后，你可以直接在控制台进行测试。转到函数的“测试”标签页，这里提供了两种测试方式：

*   **在控制台内测试**：你可以直接在提供的JSON输入框中构造测试负载。例如，输入 `{“name”: “Marco”}`，点击“测试函数”，应返回 `“Polo!”`。输入 `{“name”: “Bob”}`，则会返回 `“I don‘t know you, Bob.”`。
*   **在Cloud Shell中测试**：你也可以选择在Cloud Shell中使用 `curl` 命令进行测试，这对于模拟真实HTTP调用非常有用。

## 使用其他语言（以Go为例）

Google Cloud Functions 的多语言支持使其非常灵活。让我们快速看一下用Go语言实现的相同功能。

以下是一个Go版本的“Marco Polo”函数：

![](img/da2a22497a2c2f7f7591d28389eeed8a_2.png)

```go
package p

import (
    “encoding/json”
    “fmt”
    “net/http”
)

// NameStruct 定义了期望的JSON结构
type NameStruct struct {
    Name string `json:“name”`
}

// HelloWorld 是云函数的入口点
func HelloWorld(w http.ResponseWriter, r *http.Request) {
    var d NameStruct

    if err := json.NewDecoder(r.Body).Decode(&d); err != nil {
        fmt.Fprint(w, “Error decoding JSON. Please provide a {‘name’: ‘value’} payload.“)
        return
    }

    if d.Name == “Marco” {
        fmt.Fprint(w, “Polo!”)
    } else {
        fmt.Fprintf(w, “I need another name. You provided: %s”, d.Name)
    }
}
```

创建和测试Go函数的过程与Python类似：选择Go运行时，粘贴代码，部署，然后在测试标签页使用相同的JSON负载进行验证。

![](img/da2a22497a2c2f7f7591d28389eeed8a_4.png)

## 监控与管理函数

函数部署后，管理它同样重要。Google Cloud Functions 控制台提供了强大的工具。

*   **指标**：在“指标”标签页，你可以查看每秒调用次数、执行时间、错误率等图表，这对于监控函数性能和健康状况至关重要。
*   **编辑与重新部署**：如果需要修改代码，只需点击“编辑”，进入代码编辑页面进行更改，然后再次点击“部署”即可更新函数，无需重新配置触发器。
*   **日志**：“日志”标签页显示了函数的所有执行日志，包括标准输出、错误信息以及系统日志。这是调试和排查问题不可或缺的工具。

## 总结

![](img/da2a22497a2c2f7f7591d28389eeed8a_6.png)

![](img/da2a22497a2c2f7f7591d28389eeed8a_7.png)

本节课中，我们一起学习了Google Cloud Functions的核心概念和基本操作。我们了解了其基于事件触发的无服务器架构，逐步实践了如何创建、配置、编写代码、测试以及部署一个云函数。无论是使用Python还是Go，流程都清晰而直接。我们还探索了如何通过控制台监控函数指标、查看日志以及更新代码。Google Cloud Functions 提供了一个完整、易用且功能强大的计算环境，让你能够专注于业务逻辑，而无需操心底层基础设施。