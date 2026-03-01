# 022：自定义环境 🛠️

![](img/07a0fadd19a3122402a18af916003df5_0.png)

在本节课中，我们将学习如何通过自定义Docker文件来修改开发容器的底层系统环境。这允许我们安装额外的系统包或对操作系统进行特定配置，以满足项目需求。

上一节我们介绍了如何通过JSON配置文件来管理开发容器。本节中我们来看看，当需要修改操作系统或底层系统时，应该如何操作。

## 自定义Docker文件

如果需要对操作系统或底层系统进行更改，例如暴露特定文件、添加文件或修改系统配置，仅查看当前的JSON配置文件可能不够清晰。

以下是我们可以采取的自定义步骤：

1.  **使用Docker文件**：我们可以自定义Docker文件。开发容器指南中提供了Docker文件或Docker Compose文件的使用方法，路径始终相对于开发容器配置文件。
2.  **执行系统命令**：在Docker文件中，可以运行如`apt-get update`和`apt-get install`等命令来安装所需的软件包。

![](img/07a0fadd19a3122402a18af916003df5_2.png)

## 实施自定义步骤

现在，让我们具体实施这些更改。

首先，修改开发容器配置文件。我们将指定一个构建配置，并打开一个新部分。原始配置中可能指定了基础镜像，但我们现在要将其改为使用自定义的Docker文件进行构建。

修改后的配置关键部分如下：
```json
{
  "build": {
    "dockerfile": "Dockerfile"
  }
}
```
我们移除了直接指定镜像的行和相关的参数，使配置指向我们即将创建的Docker文件。

接下来，在开发容器配置文件的同级目录中，创建一个新的`Dockerfile`文件。

在这个Docker文件中，我们仍然希望基于之前预配置的镜像。然后，我们可以在其中添加系统级的操作指令。

一个基础的Docker文件内容如下：
```dockerfile
FROM mcr.microsoft.com/devcontainers/rust:1

RUN apt-get update && apt-get install -y \
    <你的软件包名> \
    && rm -rf /var/lib/apt/lists/*

ENV DEBIAN_FRONTEND=noninteractive
```
其中，`FROM`指令指定了基础镜像。`RUN`指令用于执行更新和安装命令。`ENV DEBIAN_FRONTEND=noninteractive`环境变量可以防止在安装过程中出现交互式提示。

保存Docker文件后，即可尝试重建容器。

![](img/07a0fadd19a3122402a18af916003df5_4.png)

![](img/07a0fadd19a3122402a18af916003df5_5.png)

## 重建并验证容器

在VS Code中，执行“重建容器”操作。这将根据新的Docker文件指令触发完整的容器重建过程。

重建完成后，之前通过JSON配置文件添加的扩展（如GitHub Copilot和Rust Analyzer）会被重新安装。同时，在终端中运行`sudo apt-get update`命令会非常快，因为该命令已在容器构建过程中通过Docker文件执行过了。

通过这种方式，`devcontainer.json`文件管理了大多数开发环境更改。当需要进行系统级修改时，则需添加并配置自定义的Docker文件。

![](img/07a0fadd19a3122402a18af916003df5_7.png)

![](img/07a0fadd19a3122402a18af916003df5_8.png)

本节课中我们一起学习了如何通过创建和配置自定义Docker文件来扩展开发容器的系统功能。这为满足特定的项目依赖和系统配置需求提供了灵活的方法。