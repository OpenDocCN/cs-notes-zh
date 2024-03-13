# 8.5 应用系统

> 原文：[`introcs.cs.princeton.edu/java/85application`](https://introcs.cs.princeton.edu/java/85application)

这一部分正在进行重大改造。

**JavaServer Pages（JSP）。** 一种类似于 PHP 和 ASP 的 Web 脚本技术。可以编写 Java 代码来显示网页。

**JAR 文件。** *Java 存档*，简称 JAR，使您能够将各种文件打包到单个存档中。它类似于 ZIP 或 tar 文件。要创建一个存档，请在命令行中键入以下内容：

```
jar cf *jar-file* *input-files*

```

要从 JAR 中提取所有文件，请键入：

```
jar xf *jar-file*

```

或者，Java 程序可以直接访问 JAR 文件中的资源，前提是 JAR 文件在类路径中。例如，cards.jar 包含 52 张扑克牌的 GIF 图像，而 Card.java 访问它以显示图像。请注意，您必须将 JAR 文件放入类路径中，并将资源作为 URL 访问。

**可执行的 JAR 文件。** JAR 文件的另一个用途是将程序的所有资源捆绑在一起，以便用户可以下载 JAR 文件并执行它（假设他们已安装了 Java 运行时环境）。这里有创建*可执行 JAR 文件*的说明。Windows 用户的另一个选择是[JSmooth](http://jsmooth.sourceforge.net/)，它可以从 Java JAR 文件创建标准的 Windows EXE 文件。

**Java Web Start。** Java Web Start 是通过 Web 分发 Java 应用程序的框架。与 JAR 可执行文件不同，客户端从托管在 Web 上的资源启动应用程序，而不是从本地文件系统启动。如果您希望用户始终运行应用程序的最新版本，则此方法很有用。这里有创建 Java Web Start 应用程序的说明。

**小程序。** Java 小程序会自动下载并在 Web 浏览器中启动并在安全沙箱中执行。小程序的一个困难之处在于某些浏览器不支持当前版本的 Java。因此，如果尚未安装，您需要指示浏览器下载适当的插件。`appletviewer`。

#### 创意练习
