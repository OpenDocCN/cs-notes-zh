# Rust编程2-3（数据工程、DevOps）：157：为拉取请求设置代码检查 🛠️

在本节课中，我们将学习如何为Rust项目集成代码检查工具，并配置自动化工作流。我们将创建一个Makefile来抽象常用命令，并设置GitHub Actions工作流，以便在每次拉取请求时自动运行代码质量检查。

## 概述

在软件开发中，保持代码质量至关重要。本节我们将通过添加`clippy`（Rust的代码检查工具）和自动化工作流，确保项目在合并前通过代码质量检查。我们将从创建一个Makefile开始，它可以帮助我们标准化项目命令，然后配置GitHub Actions来运行这些检查。

## 创建并配置Makefile

上一节我们讨论了代码质量的重要性，本节中我们来看看如何通过Makefile来标准化我们的开发流程。Makefile允许我们抽象复杂的命令调用，并为所有项目提供一致的接口。

![](img/d4cdbcf008e7c5c6b5f970b767e5c6e2_1.png)

首先，我们在项目根目录创建一个名为`Makefile`的文件。其核心作用是定义一系列目标（targets），例如格式化代码、运行测试和代码检查。

以下是一个实用的Makefile示例，它定义了`format`、`test`、`lint`等目标：

```makefile
# 定义默认目标
.DEFAULT_GOAL := help

# 帮助信息目标
help:
	@echo "可用命令:"
	@echo "  make format    # 格式化代码"
	@echo "  make test      # 运行测试"
	@echo "  make lint      # 运行clippy代码检查（将警告视为错误）"

# 格式化代码
format:
	cargo fmt

# 运行测试
test:
	cargo test

# 运行clippy进行代码检查
lint:
	cargo clippy --all -- -F warnings -D warnings
```

在这个Makefile中：
*   `help` 目标列出了所有可用命令。
*   `format` 目标使用 `cargo fmt` 格式化代码。
*   `test` 目标运行项目测试。
*   `lint` 目标是核心，它使用 `cargo clippy` 进行代码检查。`--all` 标志检查所有特性，`-F warnings` 禁止警告，`-D warnings` 则将警告升级为错误，确保代码完全符合规范。

现在，我们可以在终端中运行 `make help` 来查看所有命令，或运行 `make lint` 来执行代码检查。如果代码中存在`clippy`建议改进的地方，此命令会报错，从而阻止构建。

## 配置GitHub Actions工作流

我们已经有了本地运行的代码检查命令，接下来需要将其集成到持续集成/持续交付（CI/CD）流程中。我们将配置GitHub Actions，使其在每次代码推送或拉取请求时自动运行`make lint`。

以下是设置步骤：

1.  在项目根目录创建 `.github/workflows/` 文件夹结构。
2.  在该文件夹内创建一个YAML文件，例如 `clippy.yml`，用于定义工作流。

以下是一个GitHub Actions工作流配置示例：

```yaml
name: Clippy Check

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  clippy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions-rs/toolchain@v1
        with:
          toolchain: stable
          components: clippy
      - name: Run Clippy
        run: make lint
```

这个工作流定义了一个名为“Clippy Check”的任务：
*   **触发时机**：在向`main`分支推送代码或创建指向`main`分支的拉取请求时触发。
*   **运行环境**：使用最新的Ubuntu系统。
*   **执行步骤**：
    1.  检出（checkout）仓库代码。
    2.  安装包含`clippy`组件的稳定版Rust工具链。
    3.  执行 `make lint` 命令进行代码检查。

配置完成后，将此文件推送到GitHub仓库。此后，每次相关的代码活动都会自动触发这个工作流。你可以在GitHub仓库的“Actions”标签页查看运行结果。如果`make lint`检查失败（即代码存在`clippy`指出的问题），工作流会显示失败，从而阻止拉取请求的合并。

## 总结

![](img/d4cdbcf008e7c5c6b5f970b767e5c6e2_3.png)

本节课中我们一起学习了如何为Rust项目设置自动化的代码质量检查流程。我们首先创建了一个Makefile来封装和标准化`cargo clippy`等命令，然后配置了GitHub Actions工作流，使其能响应代码变更自动执行代码检查。这套组合确保了代码在合并前必须通过严格的质量关卡，是维持项目代码健康度的有效实践。