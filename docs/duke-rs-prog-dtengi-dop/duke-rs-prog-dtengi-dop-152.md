# GitHub Actions教程：2-3：管理相互依赖的作业

![](img/a7ef9d49a4205b3e1fab99583444273f_1.png)

在本节课中，我们将学习如何在GitHub Actions中管理相互依赖的作业。我们将从一个简单的Rust项目构建工作流开始，逐步将其拆分为独立的“代码质量”检查作业，并最终建立它们之间的依赖关系，确保作业按特定顺序执行。

## 概述

上一节我们介绍了基本的GitHub Actions工作流配置。本节中，我们来看看如何将一个单一的构建作业拆分为多个独立的作业，并控制它们的执行顺序。这对于实现分阶段的代码质量检查（如先格式化，再构建）非常有用。

## 从单一作业到多作业工作流

最初，我们可能只有一个名为 `rust-build` 的作业。为了进行更细致的代码质量管理，我们可以将其扩展为包含多个检查步骤的 `rust-quality` 作业。

以下是创建 `rust-quality` 作业的步骤：

1.  首先，编辑工作流文件，将作业名称从 `rust-build` 改为 `rust-quality`。
2.  然后，在该作业下定义多个独立的步骤（`steps`），例如一个用于代码格式化检查，另一个用于构建检查。

然而，这种方式下所有步骤仍在同一个作业中顺序运行。为了实现真正的并行或顺序控制，我们需要创建多个独立的作业。

## 创建独立的并行作业

我们可以将格式化和构建拆分为两个独立的作业，让它们同时运行。

以下是定义两个独立作业的示例：

```yaml
jobs:
  format:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Ensure code is formatted
        run: cargo fmt -- --check

  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Ensure cargo builds correctly
        run: cargo build
```

在这个配置中，`format` 和 `build` 两个作业没有依赖关系，它们会同时启动和执行。这是一种高效的策略，但如果构建依赖于格式化的成功，则不合适。

## 建立作业间的依赖关系

有时，我们需要作业按顺序执行。例如，我们希望只有在代码格式化检查通过后，才运行构建作业。

为了实现这一点，我们使用 `needs` 关键字。这个关键字允许一个作业声明它需要等待另一个作业成功完成后才能开始。

以下是建立依赖关系的修改方法：

1.  在依赖方作业（如 `build`）的配置中，添加 `needs` 键。
2.  `needs` 的值设置为它所依赖的作业名称（如 `format`）。

修改后的 `build` 作业配置如下：

```yaml
  build:
    needs: format  # 声明此作业需要 `format` 作业成功
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Ensure cargo builds correctly
        run: cargo build
```

添加 `needs: format` 后，`build` 作业会等待 `format` 作业完成。如果 `format` 作业失败，`build` 作业将被自动跳过，不会执行。

## 工作流执行效果

建立依赖关系后，工作流的执行逻辑将发生改变：
*   **无依赖时**：所有作业同时开始，并行执行。
*   **有依赖时**：被依赖的作业（`format`）首先执行。只有在其成功完成后，依赖它的作业（`build`）才会开始执行。如果 `format` 失败，`build` 会显示为“已跳过”。

这为我们管理代码质量流程提供了灵活性：我们可以选择让所有检查并行运行以加快速度，也可以强制它们按顺序执行以确保关键前置条件（如代码格式）得到满足。

## 总结

![](img/a7ef9d49a4205b3e1fab99583444273f_3.png)

本节课中我们一起学习了如何在GitHub Actions中管理作业依赖关系。关键点包括：
1.  将复杂任务拆分为多个独立作业。
2.  使用 `needs` 关键字建立作业间的依赖关系。
3.  理解依赖关系如何影响作业的执行顺序和状态（运行、跳过）。
通过合理设计作业间的依赖，你可以构建出更清晰、更健壮的持续集成/持续部署（CI/CD）流水线。