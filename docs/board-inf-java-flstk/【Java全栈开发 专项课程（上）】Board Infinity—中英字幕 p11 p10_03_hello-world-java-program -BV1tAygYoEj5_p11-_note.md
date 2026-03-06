# Java全栈开发：1.1：第一个Java程序 - Hello World 👋

![](img/0f40a4cadf0d7a4e81ff63949089010e_0.png)

在本节课中，我们将学习如何在Java中编写一个简单的“Hello World”程序。这是一个经典的入门程序，用于向初学者介绍一门新编程语言的基本结构和运行方式。

![](img/0f40a4cadf0d7a4e81ff63949089010e_2.png)

![](img/0f40a4cadf0d7a4e81ff63949089010e_4.png)

## 概述

“Hello World”程序是一个简单的程序，其功能是在屏幕上输出“Hello World”字样。由于其结构简单，它常被用作学习新编程语言的第一步。接下来，我们将一步步学习如何在Eclipse集成开发环境中创建并运行这个程序。

![](img/0f40a4cadf0d7a4e81ff63949089010e_6.png)

## 创建Java项目

上一节我们介绍了课程目标，本节中我们来看看如何设置开发环境并创建项目。

我将使用Eclipse IDE进行整个Java开发课程。我已经为这个批次新启动了Eclipse。

以下是创建新Java项目的步骤：
1.  点击菜单栏的 **File** -> **New**。
2.  在弹出的窗口中，选择 **Other...** 选项。
3.  在搜索框中输入“Java”，然后选择 **Java Project**。
4.  将项目命名为 `Java Fundamentals`。
5.  Eclipse会自动检测并选择已安装的Java标准版环境（在我的机器上是JDK 19）。你可以根据需要更改。
6.  点击 **Next**，然后点击 **Finish**。
7.  系统会询问是否创建 `module-info.java` 文件来存储项目的元信息。我们选择 **Don‘t Create**，然后点击 **Open Perspective**。

![](img/0f40a4cadf0d7a4e81ff63949089010e_8.png)

![](img/0f40a4cadf0d7a4e81ff63949089010e_9.png)

至此，名为“Java Fundamentals”的项目已成功创建。展开项目后，可以看到一个 `src` 文件夹，所有Java程序都需要写在这个文件夹下。

## 创建Java类

现在项目已经建立，我们来创建一个用于编写“Hello World”程序的Java类。

由于这是一个“Hello World”程序，我将在 `src` 文件夹下创建一个新的类文件。
1.  右键点击 `src` 文件夹，选择 **New** -> **Class**。
2.  将类命名为 `HelloWorld`。
3.  在包（Package）输入框中，填写 `basics`。包名本质上是一个文件夹，它创建在 `src` 下，用于将不同概念的代码分隔开。包有助于模块化代码结构并控制代码的可访问性，这些细节我们将在后续课程中逐一讲解。
4.  点击 **Finish**。

现在，你可以在项目结构中看到一个名为 `basics` 的文件夹（包），里面有一个 `HelloWorld.java` 文件。

## 编写并运行代码

我们已经创建了类文件，接下来需要编写具体的程序代码并执行它。

以下是编写和运行“Hello World”程序的步骤：
1.  在 `HelloWorld` 类中，我们需要添加一个 `main` 方法。`main` 方法是程序的入口点。你可以使用快捷键：输入 `main` 然后按 `Ctrl + Space` 来自动生成方法框架。
2.  在 `main` 方法内部，编写输出语句：`System.out.println("Hello World");`。
3.  在代码编辑区域的任意位置右键点击，选择 **Run As** -> **Java Application**。

程序运行后，你将在控制台看到输出的“Hello World”消息。

## 代码解析

程序已经成功运行，现在我们来分析一下这段代码的各个部分。

这是一个Java的“Hello World”程序。我们从 `HelloWorld` 类开始。在Java中，每个应用程序都始于一个类定义。`HelloWorld` 是类的名称，花括号 `{}` 内是类的定义体。

在类定义中，我们有一个 `main` 方法。这是Java应用程序必须包含的主方法，被称为程序的入口点。Java编译器从 `main` 方法开始编译和执行程序。

主方法的签名是 `public static void main(String[] args)`。你将在后续课程中学习这些关键字的具体含义。目前只需知道，`static` 意味着它不需要创建类的实例即可调用，`void` 表示它不返回任何值，`public` 使得Java虚拟机（JVM）能够访问并加载这个类。

程序中有一行关键语句：
```java
System.out.println("Hello World");
```
`System` 是一个类，`out` 是它的一个对象，`println` 是 `out` 对象的一个方法，用于将参数（这里是“Hello World”消息）打印到标准输出（屏幕）。

## 关键要点

最后，我们来总结一下从“Hello World”程序中学到的核心概念。

本节课中我们一起学习了：
*   每个有效的Java应用程序都必须有一个与文件名匹配的类定义。例如，如果公共类名是 `HelloWorld`，那么文件名也必须是 `HelloWorld.java`。
*   `main` 方法必须位于类定义内部，并且该类必须是公共的（`public`）。
*   编译器只从 `main` 方法开始执行代码。

![](img/0f40a4cadf0d7a4e81ff63949089010e_11.png)

我希望这个概念对大家都已清晰。请继续关注，以学习更多关于Java的实践内容。我们下节课再见！