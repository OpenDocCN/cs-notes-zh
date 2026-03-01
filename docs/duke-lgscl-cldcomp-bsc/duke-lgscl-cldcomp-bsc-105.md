# 105：使用Flask在Azure部署微服务 🚀

在本节课中，我们将学习如何使用Flask框架和Python语言，通过Azure命令行界面，快速创建并部署一个简单的微服务。整个过程将涵盖从环境准备、本地测试到云端部署和更新的完整流程。

![](img/fdc7a753176ee352c354eeb5dd51819c_1.png)

![](img/fdc7a753176ee352c354eeb5dd51819c_3.png)

---

## 概述

我们将创建一个基础的“Hello World” Flask应用，并将其部署到Azure应用服务。随后，我们将修改应用代码，添加一个新功能，并学习如何将更新部署到云端。通过本教程，你将掌握使用Azure CLI部署和更新Python微服务的基本方法。

---

## 环境准备与代码获取

首先，我们需要在Azure Cloud Shell环境中进行操作。这是一个基于浏览器的命令行工具，预装了Azure CLI和其他必要的工具。

接下来，我们将克隆一个包含初始代码的Git仓库。这为我们提供了一个快速开始的脚手架。

```bash
git clone <仓库地址>
```

克隆完成后，我们进入项目目录。典型的Python项目最佳实践是从创建虚拟环境开始。

```bash
python3 -m venv venv
source venv/bin/activate
```

激活虚拟环境后，我们进入项目目录。可以看到项目结构包含一个应用文件（`application.py`）和一个依赖文件（`requirements.txt`）。

---

## 安装依赖与本地运行

以下是安装项目所需Python包的步骤。

![](img/fdc7a753176ee352c354eeb5dd51819c_5.png)

![](img/fdc7a753176ee352c354eeb5dd51819c_6.png)

我们使用`pip`根据`requirements.txt`文件安装所有依赖项。

![](img/fdc7a753176ee352c354eeb5dd51819c_8.png)

```bash
pip install -r requirements.txt
```

安装完成后，我们需要运行Flask应用。直接运行`python application.py`可能不会启动Flask开发服务器。Flask提供了一个便捷的方法：设置环境变量。

```bash
export FLASK_APP=application.py
flask run
```

此时，应用将在本地运行。我们可以在Cloud Shell中点击“Web预览”图标，并配置端口为5000，即可在浏览器中预览运行的应用。此时，你将看到一个显示“Hello World”的简单网页。

---

## 部署应用到Azure

![](img/fdc7a753176ee352c354eeb5dd51819c_10.png)

上一节我们完成了本地测试，本节中我们来看看如何将应用部署到Azure云平台。

![](img/fdc7a753176ee352c354eeb5dd51819c_11.png)

我们将使用Azure CLI命令创建一个Azure应用服务。这里我们选择免费的F1定价层。

```bash
az webapp up --sku F1 --name <你的唯一应用名称>
```

![](img/fdc7a753176ee352c354eeb5dd51819c_13.png)

**注意**：应用名称必须在整个Azure中保持唯一。如果名称已存在，命令会失败，需要更换一个名称。

命令执行后，Azure会在后台创建必要的资源组和应用服务环境。完成后，你将获得一个公开可访问的URL。访问该URL，即可看到你的应用已成功运行在云端。

---

## 修改应用与测试更新

我们的应用已成功上线。接下来，我们对其进行功能增强，并学习如何部署更新。

我们将打开Cloud Shell中的代码编辑器，编辑`application.py`文件。原始应用只有一个根路由。现在，我们添加一个新的路由。

![](img/fdc7a753176ee352c354eeb5dd51819c_15.png)

```python
@app.route('/marco/<polo>')
def marco_polo(polo):
    return polo
```

这个新路由`/marco/<polo>`会接收URL路径中的`<polo>`参数，并将其作为响应返回。例如，访问`/marco/hello`将返回“hello”。

![](img/fdc7a753176ee352c354eeb5dd51819c_17.png)

在部署到云端之前，最好在本地测试新功能。我们再次在本地运行Flask服务器，并通过Web预览测试新路由，确保其按预期工作。

测试无误后，停止本地服务器。现在，我们将本地修改部署到Azure。

![](img/fdc7a753176ee352c354eeb5dd51819c_19.png)

```bash
az webapp up
```

此命令会检测本地代码的更改，并将其同步到已部署的Azure应用服务中。部署完成后，再次访问你的应用URL，并测试新的`/marco/<polo>`路由，确认更新已生效。

![](img/fdc7a753176ee352c354eeb5dd51819c_21.png)

---

## 总结

本节课中我们一起学习了使用Flask和Azure CLI部署微服务的完整流程。我们从准备环境、安装依赖、本地运行开始，然后使用`az webapp up`命令将应用部署到Azure应用服务。最后，我们修改了应用代码，并再次使用同一命令将更新部署到了云端。

![](img/fdc7a753176ee352c354eeb5dd51819c_23.png)

![](img/fdc7a753176ee352c354eeb5dd51819c_24.png)

![](img/fdc7a753176ee352c354eeb5dd51819c_25.png)

整个过程展示了Azure平台即服务（PaaS）的便捷性，使得部署和更新微服务变得非常简单直接，并能轻松集成到Azure Pipelines等云原生构建环境中。