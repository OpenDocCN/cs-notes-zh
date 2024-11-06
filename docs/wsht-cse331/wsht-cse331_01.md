CSE 331 软件设计与实现

# 在家工作

目录：

+   折衷方案

+   四个主要选项

+   第一步：获取 Oracle 的 Java 开发工具包（JDK）

+   第二步：获取 Eclipse

    +   在您的计算机上放置 Eclipse 的位置

    +   在 Windows 上设置 Eclipse 的 JDK

+   第三步：使用 SVN

    +   Eclipse

    +   命令行

+   使用 SSH 登录`attu`

    +   在 Linux 上使用 SSH

    +   在 Windows 上使用 SSH

    +   服务器身份验证警告

    +   文件传输：SCP

## 折衷方案

许多学生发现使用自己的计算机比使用位于 Allen 中心地下室的 UW CSE 教学实验室中的计算机更方便。但实验室已经安装并正确配置了所有 CSE 331 所需的软件。虽然您可以使用自己的计算机，工作人员将在可行范围内提供帮助，但预测和调试每个安装/配置问题可能会很困难。

最终，考虑到我们有限的时间，工作人员可能不得不建议您使用部门资源，如果您在安装自己的软件时遇到太多麻烦。帮助您在自己的计算机上进行配置比帮助学生解决作业问题、完成评分等工作优先级较低。我们可能无法帮助除 Eclipse 和课程中使用的其他工具之外的软件。

请注意，无论您在哪里工作，您都需要远程登录到部门机器`attu`以验证您的作业提交，以确保您提交了正确的文件，您的程序编译并使用工作人员将用于评分的编译器和工具运行测试。请务必在截止日期前足够提前完成此操作，以避免问题。

## 四个主要选项

1.  您可以在 Allen 中心实验室中进行工作。选择此选项，无需安装软件，您可以直接开始学习如何使用版本控制、Eclipse 等。您需要以下说明的唯一部分是关于登录`attu`的内容。

1.  您可以按照[部门的说明](http://www.cs.washington.edu/lab/software/homeVMs/)在自己的计算机上安装部门的家用虚拟机。这实际上是将实验室的 Linux 安装副本放在您自己的计算机上，即使您的计算机没有 Linux，也能将您自己计算机的便利性与实验室的部署相结合。与在实验室中工作一样，只需根据需要登录`attu`即可。

1.  您可以通过登录`attu`并远程使用它来完成所有工作。这应该是可以的，但`attu`是一个共享的远程机器，因此您可能会发现像 Eclipse 这样的大型程序运行缓慢。

1.  你可以在自己的计算机上安装 Java、Eclipse、Subversion 和其他必要的工具。以下大部分说明都是为此选项准备的。

明确一点，**除非你选择最后一项，否则下面的步骤 1、2 和 3 都可以跳过**。

## 第一步：获取 Oracle 的 Java 开发工具包（JDK）

你想要从他们的网站下载 Oracle 的**J2SE v7.0 JDK**。这有点棘手，因为下载页面上有很多几乎相同名称的东西。例如，**JRE**是**Java 运行时环境**，可以让你运行 Java 程序，但不提供 Java 开发工具。

因此，请访问[`www.oracle.com/technetwork/java/javase/downloads/`](http://www.oracle.com/technetwork/java/javase/downloads/index.html)，确保你点击标记为**Download JDK**的链接。务必获取最新版本的 Java 7，而不是 Java 8，用于 15sp 季度。

## 第二步：获取 Eclipse

如果你想要基本安装，可以在[`download.eclipse.org/eclipse/downloads/`](http://download.eclipse.org/eclipse/downloads/)下载 Eclipse 4.4.1 的副本，或者如果需要一些额外工具（在 CSE 331 中我们不会依赖任何额外工具），则可以在[`www.eclipse.org/downloads/`](https://www.eclipse.org/downloads/)下载“Java 开发者”版本。你也可以使用已经安装了 Eclipse 的实验室机器。

### 在你的计算机上放 Eclipse 的位置

Eclipse 没有安装程序，所以这让很多人感到困惑。基本上，你下载它，解压到一个目录中，然后在该目录中运行可执行文件以启动 Eclipse。如果安装在名称中有空格的目录中，Eclipse 内部的 Ant 会有一些小错误，因此，不要将其安装到如下目录中：

```
C:\Documents and Settings\Joe User\Desktop\eclipse

```

或者

```
C:\Program Files\eclipse

```

使用：

```
C:\eclipse

```

### 在 Windows 上设置 Eclipse 的 JDK

如果你使用 Windows，在编辑、编译、运行和测试 Java 程序工具中描述的方式设置你的 Eclipse 工作区以使用 JDK。

## 第三步：使用 SVN

### Eclipse

我们推荐使用 Subclipse SVN 插件来管理作业。请按照下面提到的说明操作。但如果你遇到问题，请参考[官方安装说明](http://subclipse.tigris.org/servlets/ProjectProcess?pageID=p4wYuA)。

#### 安装 Subclipse

Windows 用户需要在安装 Subclipse 插件之前下载 SSH 客户端（如果尚未安装）。SSH 客户端包括[TortoiseSVN](http://tortoisesvn.net/downloads.html)和[PuTTY](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html)。安装完成后，按照下面的描述安装 Subclipse 并继续其余的设置过程。这样做是为了防止一个常见的 Subclipse 错误：“SVN Cannot Create Tunnel”。更多信息请参考这篇[博客文章](http://beajar.blogspot.com/2011/07/subclipse-cannot-create-tunnel-error.html)。

要安装 Subclipse：

1.  打开 Eclipse（如上面 Eclipse 部分所述，请使用 Eclipse 4.4.1）

1.  转到帮助->安装新软件

1.  点击打开弹出的窗口中的添加按钮

1.  对于名称字段：输入"Subclipse"

1.  对于位置字段：输入"http://subclipse.tigris.org/update_1.10.x"

1.  点击确定

1.  会出现两个复选框，分别是 Subclipse 和 SVNKit。请勾选它们。

1.  点击下一步，同意并完成安装

1.  完成后重新启动 Eclipse

Subclipse 是一个方便的工具：它具有很好的功能，并且集成到您的开发环境中。但是，它也存在一些错误。如果您遇到问题，请不要感到沮丧或困惑。命令行工具`svn`往往更可靠，您也应该熟练使用它。它适用于所有操作系统。另一个选项，比 Subclipse 更可靠的是 TortoiseSVN，它仅适用于 Windows 计算机。

安装 Subclipse 后，您应该能够访问您的 SVN 仓库。

### 命令行

命令行应该与 Allen Center 软件实验室中的相同，唯一的例外是在检出时，您必须指定仓库 URL 为`svn+ssh://*YourCSENetID*@attu.cs.washington.edu/projects/instr/15sp/cse331/*YourCSENetID*/REPOS`。例如，要检出`cse331`目录，您应该运行：

```
svn checkout svn+ssh://*YourCSENetID*@attu.cs.washington.edu/projects/instr/15sp/cse331/*YourCSENetID*/REPOS/cse331 cse331

```

## 使用 SSH 登录 attu

`attu`是一个教学工作站（IWS）Linux 机器的名称。您偶尔需要登录到这台机器上。您如何登录到 attu 取决于您是从 Linux 机器还是 Windows 机器开始的。

### Linux 上的 SSH

1.  获取命令提示符（也称为终端或控制台）。您可以通过点击应用程序 -> 系统工具 -> 终端 来实现。

1.  在命令提示符下，运行以下命令：

    ```
      ssh *YourCSENetID*@attu.cs.washington.edu

    ```

    使用您在 Allen Center 软件实验室登录 Linux 机器时使用的相同密码。

    对于那些对命令行不熟悉的人的注意事项：当您尝试在命令行中输入密码时，您可能会感到惊讶，因为您看不到输入的任何文本。为了保护您的密码，您输入的内容不会显示出来。只需像平常一样输入密码，然后按回车键。

如果您在 Allen Center 软件实验室使用 Linux 机器，您还可以使用命令的简短版本：

```
  ssh attu

```

这是因为用户名默认为您当前登录的用户名，目标域默认为您连接的机器的域。

### Windows 上的 SSH

+   从 CSE 教学机器上：双击桌面上的**SSH attu**快捷方式。

    如果桌面上没有快捷方式，请转到开始菜单中的**所有程序 ? UNIX 连接 ? SSH ? SSH attu**。

+   从家里：

    1.  安装一个 SSH 客户端。一个很好（且免费）的选择是[PuTTY](http://www.chiark.greenend.org.uk/~sgtatham/putty/)。

    1.  使用 PuTTY，通过在`主机名`文本框中输入`attu.cs.washington.edu`并单击`打开`来连接。系统会提示您输入用户名和密码。

无论哪种情况，你的用户名是你的**CSENetID**，密码与你登录艾伦中心软件实验室中的*Linux*机器时使用的相同。

### 服务器身份验证警告

第一次从特定机器连接到`attu`时，你将收到类似以下的服务器真实性警告：

```
  The authenticity of host 'attu.cs.washington.edu (128.208.1.139)' can't be established.

```

除了警告之外，SSH 客户端还会显示远程主机的 RSA 密钥指纹，以便你可以验证主机的身份。安全起见，可以选择“yes”继续连接。连接时，SSH 将缓存主机密钥，以便将来自动验证远程主机的身份。

### 文件传输：SCP

如果你只想在你的 CSE 账户和家用机器之间传输文件，你可以使用`scp`（"secure copy"）。**对于 CSE 331，你几乎不需要手动传输文件。**你所有的代码和其他作业材料将在一个 Subversion 仓库中，允许你在不同机器之间自动且安全地同步你的工作。我们提供有关`scp`的信息作为你一般知识的参考。

在 Mac 或 Linux 机器上，你可以在命令行上运行 scp。运行`man scp`以获取有关此命令的文档。如果你更喜欢图形界面，或者你正在使用 Windows，你可以安装一个[file transfer program](http://www.washington.edu/itconnect/security/securing-computer/#secure-file-transfer)如 WinSCP。上面关于通过 ssh 建立远程连接的大部分指导也适用于 scp。
