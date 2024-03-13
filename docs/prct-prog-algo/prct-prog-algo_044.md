# 8.1 系统库

> 原文：[`introcs.cs.princeton.edu/java/81library`](https://introcs.cs.princeton.edu/java/81library)

本节正在大规模施工中。

Java 包含许多由专家设计和实现的库。还可以从网络上下载更多通用库。我们已经考虑过的许多数据结构和算法（二叉堆、二叉搜索树、哈希表、快速排序）在这些库中起着核心作用。避免重复造轮子。知道如何找到正确的库并与之交互是一项有用的技能。

以下是一些值得了解的类。

**NumberFormatter。** DecimalFormat 用于格式化实数以便通过 System.out.println 打印。

> ```
> DecimalFormat df = new DecimalFormat("###.##");
> System.out.println(df.format("123456.789"));
> System.out.println(df.format("16.1111111"));
> 
> ```

**BigInteger。** 这个类实现了任意精度整数的算术运算，包括加法、乘法、模算术、素性测试、素数生成和位操作。这个类对于实现各种加密方案包括 RSA 非常有用。

**StringBuffer。** 有两个用于操作字符串的内置类：String 和 StringBuffer。第一个用于存储*不可变*的字符序列，即其值永远不会更改的字符串。第二个用于存储其字符可能被修改的字符串。在幕后，编译器使用 StringBuffer 执行任何连接操作，例如，s = "Hello " + "World"。

一个常见的性能错误是逐个连接一系列字符（或单词）以形成一个长字符串。以下代码说明了问题。

> ```
> String s = "";
> while(!In.isEmpty()) {
>    char c = In.getChar();
>    s = s + c;
> }
> 
> ```

每次将新字符 c 附加到 s 时，会出现问题，因为字符串是不可变的，所以每次都会创建 s 的新副本。构建长度为 N 的字符串可能需要与 N² 成正比的时间。相反，应该使用 StringBuffer，这样时间与 N 成正比。

> ```
> StringBuffer sb = new StringBuffer();
> while(!In.isEmpty()) {
>    char c = In.getChar();
>    sb.append(c);
> }
> String s = sb.toString();
> 
> ```

**包。** 有许多情况下没有现成的库符合您的需求。在这种情况下，您必须创建自己的库。在 Java 中，有一种内置机制称为*包*，它组织相关类，以便可以像内置系统库一样访问。要构建名为`Jama`的包，必须在客户端程序的开头包含语句`import Jama;`。Jama 包中的类必须存储在名为`Jama`的子目录中。父目录必须在您的 CLASSPATH 中，例如，当前目录。

**Javadoc。** 在 Jama 包上运行 Javadoc，自动生成 Java 风格的文档。命令

> ```
> % javadoc -d Jama/javadoc Jama
> 
> ```

生成一个文件`Jama/javadoc/index.html`，记录 Jama 包中的所有类和方法。

**HTML 解析。** Java 之外还有许多重要的库。例如，如果要解析 HTML 中的 Web 文档，可以使用[HTMLParser v 1.3](http://htmlparser.sourceforge.net/)。示例应用程序：网络爬虫，提取文本内容。解释如何下载外部库作为.jar 文件并使用它。

#### 练习

#### 创意练习

#### 课程

1.  使用内置库节省编码时间。

1.  注意系统库中的性能保证（或缺乏性能保证）。

1.  使用包来构建自己的库。

1.  使用 javadoc 自动生成文档。库。
