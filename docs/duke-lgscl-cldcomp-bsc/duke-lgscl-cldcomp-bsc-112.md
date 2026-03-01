# 112：Google Cloud Function 变更实践 💰

在本节课中，我们将学习如何使用 Google Cloud Functions 这一无服务器技术，创建一个名为“找零机”的函数，并通过多种方式触发和调用它。

Google Cloud Functions 是一种无服务器技术，它允许你将一段逻辑映射到一个函数，并通过触发器来调用它。在本例中，我们将在 Google Cloud Platform 内部创建一个函数。

## 创建函数

首先，在 Google Cloud Platform 中选择 Cloud Functions 服务。我们将创建一个新函数。

以下是创建函数的主要步骤：

1.  **命名函数**：将函数命名为 `change_machine`。
2.  **选择区域**：为函数选择一个部署区域。
3.  **选择触发器类型**：选择 **HTTP 触发器**，这允许我们通过 Web 接口调用它。
4.  **设置身份验证**：选择“允许未经身份验证的调用”，以便将其用作常规的、无需身份验证的 Web 服务。
5.  **保存并继续**：点击“保存”，然后进入下一步。

## 配置运行时与代码

接下来，我们需要为函数选择运行时环境并编写代码。

以下是配置运行时和代码的步骤：

1.  **选择运行时**：从多种运行时中选择，例如 .NET (C#)、Go、Java、Node.js 或 Python。这里我们选择 **Python 3.8**。
2.  **使用内联编辑器**：平台提供了方便的内联编辑器，并允许安装第三方包。
3.  **编写函数代码**：我们将实现一个简单的“找零机”逻辑。该函数接收一个包含 `amount` 字段的 JSON 载荷，计算并返回最优的硬币找零组合（优先使用大面额硬币）。

我们将替换掉默认的样板代码。函数的入口点（即被调用时执行的函数）需要正确设置。代码如下所示：

```python
import json

def make_change(request):
    """HTTP Cloud Function.
    Args:
        request (flask.Request): The request object.
    Returns:
        The response text, or any set of values that can be turned into a
        Response object using `make_response`
        <http://flask.pocoo.org/docs/1.0/api/#flask.Flask.make_response>.
    """
    request_json = request.get_json(silent=True)
    
    if request_json and 'amount' in request_json:
        amount = float(request_json['amount'].replace('$', ''))
    else:
        return json.dumps({"error": "Please provide an 'amount' in JSON payload."})

    cents = int(amount * 100)
    
    quarters = cents // 25
    cents %= 25
    dimes = cents // 10
    cents %= 10
    nickels = cents // 5
    cents %= 5
    pennies = cents

    result = {
        "quarters": quarters,
        "dimes": dimes,
        "nickels": nickels,
        "pennies": pennies
    }
    
    return json.dumps(result)
```

确认代码和入口点正确后，点击“部署”按钮。

## 在控制台测试函数

函数部署完成后，我们可以在 Google Cloud 控制台内对其进行测试。

以下是测试步骤：

1.  转到函数的“测试”标签页。
2.  在“触发事件”部分，提供一个 JSON 载荷，例如 `{"amount": "$1.34"}`。
3.  点击“测试函数”。

测试成功后，函数将返回计算结果，例如 `{"quarters": 5, "dimes": 0, "nickels": 1, "pennies": 4}`。我们可以尝试输入不同的金额进行多次测试，以验证其功能。

![](img/a6b99e843175d584f34f21a7c95650c0_1.png)

## 通过命令行调用函数

除了在 Web 控制台测试，我们还可以通过命令行工具调用此函数。这展示了 Cloud Functions 如何集成到自动化工作流中。

![](img/a6b99e843175d584f34f21a7c95650c0_3.png)

以下是使用 `gcloud` 命令行工具调用函数的步骤：

![](img/a6b99e843175d584f34f21a7c95650c0_4.png)

1.  打开 Cloud Shell。
2.  使用以下命令格式调用函数，并传递 `amount` 参数：
    ```bash
    gcloud functions call change_machine --data '{"amount":"$1.34"}'
    ```
3.  首次调用时，可能需要登录授权。按照提示完成登录流程。

调用成功后，你将在命令行中看到相同的 JSON 格式结果。这种方式使得该函数可以被用于数据处理、机器学习预处理或并行操作等自动化任务中。

## 通过外部 HTTP 请求调用函数

由于我们的函数配置了 HTTP 触发器且允许未经身份验证的调用，因此任何能访问互联网的设备都可以通过 HTTP POST 请求来调用它。

![](img/a6b99e843175d584f34f21a7c95650c0_6.png)

以下是使用 `curl` 命令从外部调用的方法：

![](img/a6b99e843175d584f34f21a7c95650c0_7.png)

1.  在函数详情页找到并复制其触发 URL。
2.  在命令行中使用 `curl` 命令向该 URL 发送 POST 请求和 JSON 数据：
    ```bash
    curl -X POST https://YOUR_REGION-YOUR_PROJECT.cloudfunctions.net/change_machine \
    -H "Content-Type: application/json" \
    -d '{"amount": "$1.34"}'
    ```
    *请将 URL 替换为你自己的函数 URL。*

调用成功后，你将收到来自函数的找零结果。这证明了 Cloud Functions 可以作为公开的 Web 服务使用。

---

![](img/a6b99e843175d584f34f21a7c95650c0_9.png)

![](img/a6b99e843175d584f34f21a7c95650c0_10.png)

本节课中我们一起学习了 Google Cloud Functions 的核心实践。我们创建了一个“找零机”函数，并通过三种方式成功调用：在云控制台测试、使用 `gcloud` 命令行工具、以及通过外部的 `curl` HTTP 请求。这充分展示了 Cloud Functions 响应事件、集成到命令行工作流以及作为简单 Web 服务使用的灵活性和强大能力。