# 058：AWS CDK for Python 入门示例 🚀

在本节课中，我们将学习如何使用 AWS CDK（Cloud Development Kit）和 Python 语言，通过基础设施即代码的方式，在几分钟内部署一个简单的 AWS Lambda 函数。我们将使用 AWS Cloud9 作为开发环境。

---

![](img/fbb906a4721b1b3c3ff1f6418c0e65bb_1.png)

## 概述

我们将从设置 AWS Cloud9 环境开始，初始化一个 CDK 项目，编写一个简单的 Lambda 函数，并使用 CDK 命令将其部署到 AWS 云上。整个过程将展示基础设施即代码的核心工作流。

---

## 环境准备与 CDK 初始化

首先，我们位于 AWS Cloud9 环境中，这是一个非常适合使用 CDK 的工作环境。

第一步是运行官方文档中的命令，以确认我们安装了正确版本的 CDK。

```bash
cdk --version
```

确认版本无误后，接下来我们将参考一个官方的 AWS 研讨会内容来初始化项目结构。我们将复制相关命令来创建一个工作目录。

![](img/fbb906a4721b1b3c3ff1f6418c0e65bb_3.png)

![](img/fbb906a4721b1b3c3ff1f6418c0e65bb_4.png)

```bash
mkdir cdk-workshop && cd cdk-workshop
```

进入目录后，我们将创建一个示例 CDK 应用程序。

```bash
cdk init sample-app --language python
```

现在，我们已经生成了示例应用。根据终端提示，我们需要先创建一个 Python 虚拟环境并激活它。

```bash
python3 -m venv .venv
source .venv/bin/activate
```

激活虚拟环境后，下一步是安装项目 `requirements.txt` 文件中列出的所有依赖包。让我们先查看一下这个文件的内容。

`requirements.txt` 文件包含了运行 CDK Python 项目所需的核心库。

```bash
pip install -r requirements.txt
```

这些是关键的初始步骤。安装完成后，我们就可以运行其他 CDK 命令了。

---

## 验证 CDK 与创建 Lambda 函数

安装顺利结束后，我们可以通过输入 `cdk ls` 命令来验证 CDK 是否正常工作。

![](img/fbb906a4721b1b3c3ff1f6418c0e65bb_6.png)

```bash
cdk ls
```

如果命令成功运行并列出栈（Stack）的信息，则说明 CDK 已准备就绪。

接下来，我们将回到官方文档，创建一个 Lambda 函数。文档要求我们在 `cdk-workshop` 目录下创建一个名为 `lambda` 的文件夹，并在其中创建一个 Python 文件。

![](img/fbb906a4721b1b3c3ff1f6418c0e65bb_8.png)

```bash
mkdir lambda
touch lambda/hello.py
```

然后，我们将简单的 Lambda 函数代码粘贴到 `hello.py` 文件中。在 Python 中，Lambda 函数就是接收一个 `event` 参数的普通函数，它将在 AWS 环境中运行。

**lambda/hello.py 文件内容：**
```python
def handler(event, context):
    return {
        'statusCode': 200,
        'body': 'Hello from Lambda!'
    }
```

![](img/fbb906a4721b1b3c3ff1f6418c0e65bb_10.png)

![](img/fbb906a4721b1b3c3ff1f6418c0e65bb_11.png)

---

![](img/fbb906a4721b1b3c3ff1f6418c0e65bb_12.png)

## 集成 Lambda 到 CDK 栈

下一步是将 Lambda 函数集成到我们的 CDK 基础设施代码中。我们需要安装 AWS Lambda 的构造（Construct）库。一种方法是在项目的基础设施代码文件中直接引入。

在我们的项目中，基础设施代码位于 `cdk_workshop/cdk_workshop_stack.py` 文件中。我们将打开这个文件，用新的代码替换其内容，以部署我们刚刚创建的 Lambda 函数。

**cdk_workshop/cdk_workshop_stack.py 文件更新后内容：**
```python
from aws_cdk import (
    aws_lambda as _lambda,
    core
)

class CdkWorkshopStack(core.Stack):

    def __init__(self, scope: core.Construct, construct_id: str, **kwargs) -> None:
        super().__init__(scope, construct_id, **kwargs)

        # 定义 Lambda 函数资源
        my_lambda = _lambda.Function(
            self, 'HelloHandler',
            runtime=_lambda.Runtime.PYTHON_3_8,
            code=_lambda.Code.from_asset('lambda'),
            handler='hello.handler',
        )
```

更新栈文件后，我们可以运行 `cdk diff` 命令来查看本地代码与云端配置之间的差异。

```bash
cdk diff
```

由于这是我们第一次部署，应该会显示许多即将创建的变更。确认无误后，就可以进行部署了。

![](img/fbb906a4721b1b3c3ff1f6418c0e65bb_14.png)

---

## 部署与测试

现在，我们使用 `cdk deploy` 命令将基础设施部署到 AWS。

```bash
cdk deploy
```

系统可能会提示需要先运行 `cdk bootstrap` 来初始化部署环境。这在首次使用 CDK 时很常见。

```bash
cdk bootstrap
```

在 Cloud9 环境中进行此操作非常方便，因为它通常已具备执行这些操作所需的角色权限。部署过程大约需要一分钟。

部署完成后，我们可以打开 AWS Lambda 控制台。在控制台中，使用“最后修改时间”过滤器，应该能看到我们刚创建的 Lambda 函数。

为了测试函数，我们可以在控制台中创建一个测试事件。根据我们的代码，Lambda 函数期望事件中包含 `path` 字段。因此，我们可以配置一个简单的测试事件。

**测试事件示例：**
```json
{
  "path": "hello"
}
```

保存测试事件后，点击“测试”。如果配置正确，函数将执行并返回成功的响应，而不会出现堆栈跟踪错误。

---

## 总结

![](img/fbb906a4721b1b3c3ff1f6418c0e65bb_16.png)

本节课中，我们一起学习了使用 AWS CDK 和 Python 部署基础设施的基本流程。我们从设置 Cloud9 环境和初始化 CDK 项目开始，然后创建了一个简单的 Lambda 函数，并将其集成到 CDK 栈中。最后，我们通过 `cdk diff` 和 `cdk deploy` 命令完成了对 AWS 资源的部署和测试。这个流程展示了如何通过代码来定义、管理和更新云资源，是基础设施即代码的核心实践。