# 108：使用Rust构建无发行版容器 🐳

![](img/dc9ebc149fe4a111c4e48708e8c7992d_0.png)

在本节课中，我们将学习如何使用Rust构建一个极小的、无发行版（Distroless）的Docker容器。我们将通过一个真实的Rust项目（一个基于Actix-web的API）来演示，如何将构建好的Rust二进制文件放入一个极简的基础镜像中，从而将容器镜像的大小从数百兆字节缩减到仅约36MB。

## 项目概述

我们有一个Rust项目，它实现了一个基于令牌（token）的API。这个API使用预训练的模型进行文本分词。项目的核心是一个使用Actix-web框架构建的Web服务器，它绑定在`0.0.0.0:8000`端口上。

以下是API路由处理函数的一个简化示例，它接受一个POST请求：
```rust
#[post("/tokens/{pretrained_model}")]
async fn tokenize(/* ... 参数 ... */) -> impl Responder {
    // ... 分词逻辑 ...
}
```
这个函数是泛型的，可以处理不同的预训练模型（例如 `bert-base-uncased`）。

## 构建Docker镜像

接下来，我们进入最关键的部分：编写Dockerfile。我们将使用多阶段构建来创建一个极小的最终镜像。

### 第一阶段：构建阶段

首先，我们使用一个包含完整Rust工具链的镜像作为构建器（builder）。

```dockerfile
FROM rust:1.67-buster AS builder
WORKDIR /usr/src/app
COPY . .
RUN cargo build --release
```
这个阶段与我们常规的Rust Docker构建流程一致。我们复制源代码，并使用`cargo build --release`命令编译出优化的二进制文件。

### 第二阶段：运行阶段

上一节我们完成了代码的编译，本节中我们来看看如何创建一个极简的运行环境。这里就是“无发行版”技巧发挥作用的地方。

```dockerfile
FROM gcr.io/distroless/cc-debian10
COPY --from=builder /usr/src/app/target/release/rust-tokens-api /usr/local/bin/rust-tokens-api
CMD ["rust-tokens-api"]
```
我们做了以下关键操作：
1.  我们使用了Google容器注册表提供的 `gcr.io/distroless/cc-debian10` 作为基础镜像。这个镜像只包含运行C/C++/Rust等编译型语言程序所必需的最少库文件，没有shell、包管理器或其他工具。
2.  我们从第一阶段的`builder`镜像中，将编译好的二进制文件 `rust-tokens-api` 复制到最终镜像的 `/usr/local/bin/` 目录下。
3.  我们将容器的启动命令设置为直接运行这个二进制文件。

Rust的一个强大特性是它可以生成静态链接或仅依赖少量系统库的独立二进制文件，这使得将其放入`distroless`这类极简镜像成为可能。

## 构建与运行

现在，让我们在终端中构建这个镜像。

```bash
docker build -t rust-local-distroless .
```
构建过程可能需要几分钟时间，因为它需要下载Rust工具链和基础镜像。

构建完成后，我们可以查看生成的镜像列表：
```bash
docker images | grep rust-local-distroless
```
你会看到镜像大小大约只有**36MB**，这与包含完整操作系统的传统镜像（通常几百MB甚至上GB）形成了鲜明对比。

接下来，我们运行这个容器，并将本地的8000端口映射到容器的8000端口：
```bash
docker run -p 8000:8000 rust-local-distroless
```
容器会快速启动，我们的Rust API服务已经开始运行。

## 测试API

为了验证服务是否正常工作，我们使用`curl`命令向API发送一个POST请求。

以下是请求示例，我们使用`bert-base-uncased`模型对文本“Hello, world!”进行分词：
```bash
curl -X POST http://localhost:8000/tokens/bert-base-uncased \
  -H "Content-Type: application/json" \
  -d '{"text":"Hello, world!"}'
```
服务器会返回分词后的结果。通过切换请求路径中的模型名称（如`bert-base-cased`），我们可以测试不同的分词器。

## 优势总结

本节课中我们一起学习了如何使用Rust和Distroless镜像构建超小型容器。回顾一下，我们主要完成了以下工作：
1.  编写了一个标准的多阶段Dockerfile。
2.  在构建阶段使用完整的Rust镜像编译应用程序。
3.  在运行阶段使用极简的`distroless`镜像，仅包含运行二进制文件所必需的库。
4.  最终得到了一个约36MB的、安全且高效的容器镜像。

这种方法带来了显著的优势：
*   **极小的镜像尺寸**：加快镜像上传、下载和部署速度。
*   **更高的安全性**：由于镜像中不包含Shell等多余工具，攻击面大大减少。
*   **更快的实验迭代**：小镜像意味着在开发和测试环境中能更快地启动和停止容器。

![](img/dc9ebc149fe4a111c4e48708e8c7992d_2.png)

只需对Dockerfile进行一些微小的调整，你就可以将自己的Rust应用程序打包成如此轻量级的容器，从而享受更快的部署、更轻松的发布流程。