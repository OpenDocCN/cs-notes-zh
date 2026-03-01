# 028：Azure Cloud Shell 从零开始持续集成 🚀

在本节课中，我们将学习如何在 Azure Cloud Shell 环境中设置一个 Python 项目，进行本地测试，并最终通过 GitHub Actions 实现自动化持续集成。我们将从创建虚拟环境开始，逐步配置项目，使其能在 Azure 的特定 Python 版本下运行，并利用 GitHub Actions 同时测试多个 Python 版本。

---

## 创建 Python 虚拟环境

上一节我们介绍了 Azure Cloud Shell 的基本设置，本节中我们来看看如何为项目创建独立的 Python 运行环境。

首先，我们需要创建一个 Python 虚拟环境。这能确保项目依赖与其他项目隔离。

![](img/bd550697dce7c415e44e398ef59ee987_1.png)

以下是创建虚拟环境的命令：
```bash
python3 -m venv ~/scaffold
```
此命令使用 `venv` 模块，在用户主目录下创建了一个名为 `scaffold` 的虚拟环境。

![](img/bd550697dce7c415e44e398ef59ee987_3.png)

接下来，我们需要激活这个虚拟环境：
```bash
source ~/scaffold/bin/activate
```
激活后，当前终端会话将使用虚拟环境中的 Python 解释器。可以使用 `which python` 命令来验证。

---

![](img/bd550697dce7c415e44e398ef59ee987_5.png)

## 配置 SSH 密钥与克隆仓库

为了与 GitHub 仓库进行安全通信，我们需要生成并配置 SSH 密钥。

以下是生成 SSH 密钥的命令：
```bash
ssh-keygen -t rsa
```
连续按几次回车键接受默认设置即可。生成后，使用以下命令查看公钥内容：
```bash
cat ~/.ssh/id_rsa.pub
```
复制输出的公钥内容。

然后，请按照以下步骤在 GitHub 上添加 SSH 密钥：
1.  登录 GitHub，进入 **Settings**。
2.  在侧边栏找到 **SSH and GPG keys**。
3.  点击 **New SSH key**，将复制的公钥粘贴进去，并为其命名（例如“Azure scaffold”）。

完成配置后，即可使用 SSH 方式克隆项目仓库。在 Cloud Shell 中执行：
```bash
git clone git@github.com:your-username/your-repo.git
```

---

## 调整项目以适应 Azure 环境

Azure Cloud Shell 默认可能使用较旧的 Python 版本（如 3.5），这可能导致项目代码或依赖不兼容。我们需要对项目进行适配。

首先，进入项目目录并创建一个专用于 Azure 环境的依赖文件：
```bash
cd scaffold
touch requirements-azure.txt
```
然后，编辑 `requirements-azure.txt` 文件，移除或替换那些不支持 Python 3.5 的包（例如特定版本的代码格式化工具 `black`）。

接着，检查项目代码。Python 3.5 不支持 **f-string** 语法，需要将其替换为旧式的字符串格式化方法。例如，将：
```python
print(f"The result is {result}")
```
修改为：
```python
print("The result is %s" % result)
```

为了便于管理，我们可以在 `Makefile` 中添加一个专门为 Azure 环境安装依赖的命令：
```makefile
install-azure:
    pip install -r requirements-azure.txt
```
这样，通过运行 `make install-azure` 即可安装适配后的依赖包。

完成代码修改和依赖调整后，运行 `make lint` 和 `make test` 在本地进行验证，确保一切正常。

![](img/bd550697dce7c415e44e398ef59ee987_7.png)

---

## 提交代码并配置 Git

本地测试通过后，将修改提交到 GitHub 仓库。

以下是提交代码的标准步骤：
```bash
git add .
git commit -m "Adding Azure compatible version"
```
首次提交时，可能需要配置 Git 用户信息：
```bash
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```
配置完成后，推送代码到远程仓库：
```bash
git push
```

---

![](img/bd550697dce7c415e44e398ef59ee987_9.png)

![](img/bd550697dce7c415e44e398ef59ee987_10.png)

## 配置 GitHub Actions 进行多版本测试

![](img/bd550697dce7c415e44e398ef59ee987_11.png)

上一节我们完成了代码的本地适配和提交，本节中我们来看看如何利用 GitHub Actions 的强大功能，自动测试项目在多个 Python 版本下的兼容性。

目标是让 GitHub Actions 同时运行两个工作流：一个测试 Python 3.8（或其他较新版本），另一个专门测试 Python 3.5（模拟 Azure 环境）。

为此，我们需要在项目的 `.github/workflows/` 目录下创建一个新的工作流文件，例如 `azure.yml`。

该工作流的核心是定义一个使用 Python 3.5 的作业。关键配置如下：
```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        python-version: ["3.5"]
    steps:
      - uses: actions/checkout@v2
      - name: Set up Python ${{ matrix.python-version }}
        uses: actions/setup-python@v2
        with:
          python-version: ${{ matrix.python-version }}
      - name: Install dependencies
        run: |
          make install-azure
      - name: Lint with pylint
        run: |
          make lint
      - name: Test with pytest
        run: |
          make test
```
请注意，安装依赖的步骤我们指定为运行 `make install-azure`，以确保使用为 Python 3.5 适配的 `requirements-azure.txt` 文件。

提交这个工作流文件后，GitHub Actions 会自动触发。在 Actions 页面，你可以看到两个作业在**并行运行**：一个是原有的 Python 3.8 测试，另一个是新添加的 Python 3.5 测试。

![](img/bd550697dce7c415e44e398ef59ee987_13.png)

![](img/bd550697dce7c415e44e398ef59ee987_15.png)

为了让界面更清晰，你可以将原有工作流中的作业名称从“Python application test”改为“Python 3.8 Test”。这样，不同版本的测试结果一目了然。

---

![](img/bd550697dce7c415e44e398ef59ee987_17.png)

![](img/bd550697dce7c415e44e398ef59ee987_18.png)

![](img/bd550697dce7c415e44e398ef59ee987_19.png)

## 总结

本节课中我们一起学习了如何在 Azure Cloud Shell 中配置 Python 项目并实现持续集成。我们完成了以下关键步骤：
1.  **创建并激活虚拟环境**，隔离项目依赖。
2.  **配置 SSH 密钥并克隆仓库**，建立与 GitHub 的安全连接。
3.  **适配代码与依赖**，解决因 Azure 环境 Python 版本较旧导致的兼容性问题。
4.  **提交代码并配置 Git**，将修改推送到远程仓库。
5.  **配置 GitHub Actions**，创建并行工作流来同时测试项目在 Python 3.8 和 Python 3.5 下的运行情况。

![](img/bd550697dce7c415e44e398ef59ee987_21.png)

![](img/bd550697dce7c415e44e398ef59ee987_22.png)

通过结合 **Azure Cloud Shell** 的便捷性与 **GitHub Actions** 的自动化能力，我们构建了一个能够跨不同云环境（如 Azure、AWS）进行一致性测试的稳健工作流。这确保了代码的可靠性和可移植性，是构建大规模云解决方案的重要实践。