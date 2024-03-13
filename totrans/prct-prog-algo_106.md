# 5\.   字符串

> 原文：[`algs4.cs.princeton.edu/50strings`](https://algs4.cs.princeton.edu/50strings)

## 概述。

我们通过交换字符串来进行通信。我们考虑经典算法来解决围绕以下应用程序的基本计算挑战：

+   *5.1 字符串排序* 包括 LSD 基数排序、MSD 基数排序和用于对字符串数组进行排序的三向基数快速排序。

+   *5.2 Trie* 描述了用于实现具有字符串键的符号表的 R-way trie 和三向搜索 trie。

+   *5.3 子字符串搜索* 描述了在大段文本中搜索子字符串的算法，包括经典的 Knuth-Morris-Pratt、Boyer-Moore 和 Rabin-Karp 算法。

+   *5.4 正则表达式* 介绍了一种称为 grep 的基本搜索工具，我们用它来搜索不完全指定的子字符串。

+   *5.5 数据压缩* 介绍了数据压缩，我们试图将字符串的大小减少到最小。我们介绍了经典的 Huffman 和 LZW 算法。

## 游戏规则。

为了清晰和高效，我们的实现是基于 Java [String](http://download.oracle.com/javase/6/docs/api/java/lang/String.html) 类表达的。我们简要回顾它们最重要的特性。

+   *字符.* `String` 是字符序列。字符的类型是 `char`，可以有 2¹⁶ 种可能的值。几十年来，程序员们一直关注编码为 7 位 ASCII 或 8 位扩展 ASCII 的字符，但许多现代应用程序需要 16 位 Unicode。

+   *不可变性.* `String` 对象是不可变的，因此我们可以在赋值语句中使用它们，并且作为方法的参数和返回值，而不必担心它们的值会改变。

+   *索引.* `charAt()` 方法以常数时间从字符串中提取指定字符。

+   *长度.* `length()` 方法以常数时间返回字符串的长度。

+   *子字符串.* `substring()` 方法通常以常数时间提取指定的子字符串。

    警告：从 Oracle 和 OpenJDK Java 7，更新 6 开始，`substring()` 方法在提取的子字符串大小上需要线性时间和空间。由于我们没有预料到这种 drastical 变化，我们的一些字符串处理代码将受到影响。[String API](http://docs.oracle.com/javase/7/docs/api/java/lang/String.html) 对其任何方法，包括 `substring()` 和 `charAt()`，都不提供性能保证。教训是自行承担风险。

    查看[这篇文章](http://java-performance.info/changes-to-string-java-1-7-0_06/)获取更多细节。

    ![字符串操作](img/e5ccb96ba41b7fdc8ca13f7f422cdc99.png)

+   *连接.* `+` 运算符执行字符串连接。我们避免逐个字符附加形成字符串，因为在 Java 中这是一个 *二次时间* 的过程。（Java 有一个 [StringBuilder](http://download.oracle.com/javase/6/docs/api/java/lang/StringBuilder.html) 类用于这种用途。）

+   *字符数组.* Java 的 `String` 不是原始类型。标准实现提供了上述操作，以便于客户端编程。相比之下，我们考虑的许多算法可以使用低级表示，比如一个 `char` 值数组，许多客户端可能更喜欢这种表示，因为它占用更少的空间并且耗时更少。

## 字母表。

一些应用程序涉及从受限字母表中获取的字符串。在这种应用程序中，使用具有以下 API 的 Alphabet.java 类通常是有意义的：![Alphabet API](img/f98f6543a37b5dbceed04162ad50f388.png)

构造函数以 R 个字符的字符串作为参数，该字符串指定了字母表；`toChar()`和`toIndex()`方法在常数时间内在字符串字符和介于 0 和 R-1 之间的`int`值之间进行转换。`R()`方法返回字母表或*基数*中的字符数。包括一些预定义的字母表：

![字母表](img/2b81c444b7268baf93da09e17c286e43.png)

Count.java 是一个客户端程序，它在命令行上指定一个字母表，读取该字母表上的一系列字符（忽略不在字母表中的字符），计算每个字符出现的频率，

## 本章中的 Java 程序。

以下是本章中的 Java 程序列表。单击程序名称以访问 Java 代码；单击参考号以获取简要描述；阅读教科书以获取全面讨论。

> | REF | 程序 | 描述 / JAVADOC |
> | --- | --- | --- |
> | - | Alphabet.java | 字母表 |
> | - | Count.java | 字母表客户端 |
> | 5.1 | LSD.java | LSD 基数排序 |
> | 5.2 | MSD.java | MSD 基数排序 |
> | - | InplaceMSD.java | 原地 MSD 基数排序¹ |
> | 5.3 | Quick3string.java | 三向字符串快速排序 |
> | - | AmericanFlag.java | 美国国旗排序¹ |
> | - | AmericanFlagX.java | 非递归美国国旗排序¹ |
> | 5.4 | TrieST.java | 多向字典树符号表 |
> | - | TrieSET.java | 多向字典树集合 |
> | 5.5 | TST.java | 三向单词查找树 |
> | 5.6 | KMP.java | 子字符串查找（Knuth–Morris–Pratt） |
> | 5.7 | BoyerMoore.java | 子字符串查找（Boyer–Moore） |
> | 5.8 | RabinKarp.java | 子字符串查找（Rabin–Karp） |
> | 5.9 | NFA.java | 正则表达式的 NFA |
> | - | GREP.java | grep |
> | - | BinaryDump.java | 二进制转储 |
> | - | HexDump.java | 十六进制转储 |
> | - | PictureDump.java | 图片转储 |
> | - | Genome.java | 基因组编码 |
> | - | RunLength.java | 数据压缩（行程长度编码） |
> | 5.10 | Huffman.java | 数据压缩（赫夫曼） |
> | 5.11 | LZW.java | 数据压缩（Lempel–Ziv–Welch） |

#### Q + A

**Q.** 什么是 Unicode。

**A.** Unicode（通用字符编码）= 复杂的 21 位代码，用于表示国际符号和其他字符。

**Q.** 什么是 UTF-16。

**A.** UTF-16（Unicode 转换格式）= 复杂的 16 位可变宽度代码，用于表示 Unicode 字符。大多数常见字符使用 16 位（一个`char`）表示，但*代理对*使用一对`char`值表示。如果第一个`char`值在`D800`和`DFFF`之间，则与下一个`char`（在相同范围内）组合形成代理对。没有 Unicode 字符对应于`D800`到`DFFF`。例如，`007A`表示小写字母 Z，`6C34`表示中文水的符号，`D834 DD1E`表示音乐的 G 大调。

[Unicode 参考](http://docs.oracle.com/javase/6/docs/api/java//lang/Character.html#unicode)。

**Q.** 什么是子字符串陷阱？

**A.** 字符串方法调用`s.substring(i, j)`返回 s 从索引 i 开始到 j-1 结束的子字符串（而不是在 j 结束，正如你可能会怀疑的那样）。

**Q.** 如何更改字符串的值？

**A.** 在 Java 中无法修改字符串，因为字符串是不可变的。如果你想要一个新的字符串，那么你必须使用字符串连接或返回新字符串的字符串方法之一，如`toLowerCase()`或`substring()`来创建一个新的字符串。

#### 网页练习

1.  **挤压空格。**编写一个程序 Squeeze.java，该程序接受一个字符串作为输入，并删除相邻的空格，最多保留一个空格。

1.  **删除重复项。**给定一个字符串，创建一个新字符串，其中删除所有连续的重复项。例如，`ABBCCCCCBBAB`变为`ABCBAB`。

1.  **N 个 x 的字符串。**描述以下函数返回的字符串，给定一个正整数`N`？

    ```
    public static String mystery(int N) {
       String s = "";
       while(N > 0) {
           if (N % 2 == 1) s = s + s + "x";
           else            s = s + s;
           N = N / 2;
       }
       return s;
    }

    ```

1.  **回文检查。**编写一个函数，该函数以字符串作为输入，并在字符串是回文时返回`true`，否则返回`false`。*回文*是指字符串从前往后读和从后往前读是相同的。

1.  **Watson-Crick 互补回文检查。**编写一个函数，该函数以字符串作为输入，并在字符串是 Watson-Crick 互补回文时返回`true`，否则返回`false`。*Watson-Crick 互补回文*是指 DNA 字符串等于其反向的互补（A-T，C-G）。

1.  **Watson-Crick 互补。**编写一个函数，该函数以 A、C、G 和 T 字符的 DNA 字符串作为输入，并返回以其互补替换所有字符的反向字符串。例如，如果输入是 ACGGAT，则返回 ATCCGT。

1.  **完美洗牌。**给定长度相同的两个字符串`s`和`t`，以下递归函数返回什么？

    ```
    public static String mystery(String s, String t) {
       int N = s.length();
       if (N <= 1) return s + t;
       String a = mystery(s.substring(0, N/2), t.substring(0, N/2));
       String b = mystery(s.substring(N/2, N), t.substring(N/2, N));
       return a + b;
    }

    ```

1.  **二叉树表示。**编写一个名为`TreeString.java`的数据类型，使用二叉树表示不可变字符串。它应该支持在常数时间内进行连接，并在与字符数成比例的时间内打印出字符串。

1.  **反转字符串。**编写一个递归函数来反转一个字符串。不要使用任何循环。*提示*：使用 String 方法`substring()`。

    ```
    public static String reverse(String s) {
       int N = s.length();
       if (N <= 1) return s;
       String a = s.substring(0, N/2);
       String b = s.substring(N/2, N);
       return reverse(b) + reverse(a);
    }

    ```

    你的方法效率如何？我们的方法具有线性对数运行时间。

1.  **随机字符串。**编写一个递归函数，创建一个由字符'A'和'Z'之间的随机字符组成的字符串。

    ```
    public static String random(int N) {
       if (N == 0) return "";
       if (N == 1) return 'A' + StdRandom.uniform(26);
       return random(N/2) + random(N - N/2);
    }

    ```

1.  **子序列。**给定两个字符串`s`和`t`，编写一个程序 Subsequence.java，确定`s`是否是`t`的子序列。也就是说，`s`的字母应该按照相同的顺序出现在`t`中，但不一定是连续的。例如`accag`是`taagcccaaccgg`的子序列。

1.  **最长互补回文。** 在 DNA 序列分析中，*互补回文*是一个等于其反向互补的字符串。腺嘌呤（A）和胸腺嘧啶（T）是互补的，胞嘧啶（C）和鸟嘌呤（G）也是互补的。例如，ACGGT 是一个互补回文。这样的序列作为转录结合位点，并与基因扩增和遗传不稳定性相关。给定一个长度为 N 的文本输入，找到文本的最长互补回文子串。例如，如果文本是 `GACACGGTTTTA`，那么最长的互补回文是 `ACGGT`。*提示*：将每个字母视为奇数长度可能回文的中心，然后将每对字母视为偶数长度可能回文的中心。

1.  **DNA 转 RNA。** 编写一个函数，该函数接受一个 DNA 字符串（A、C、G、T）并返回相应的 RNA 字符串（A、C、G、U）。

1.  **DNA 互补。** 编写一个函数，该函数以 DNA 字符串（A、C、G、T）作为输入，并返回互补的碱基对（T、G、C、A）。DNA 通常以*双螺旋*结构存在。两条互补的 DNA 链以螺旋结构连接在一起。

1.  **从十六进制转换为十进制。** Hex2Decimal.java 包含一个函数，该函数接受一个十六进制字符串（使用 A-F 表示数字 11-15）并返回相应的十进制整数。它使用了一些字符串库方法和霍纳方法。

    ```
    public static int hex2decimal(String s) {
       String digits = "0123456789ABCDEF";  
       s = s.toUpperCase();
       int val = 0;
       for (int i = 0; i < s.length(); i++) {
          char c = s.charAt(i);
          int d = digits.indexOf(c);
          val = 16*val + d;
       }
       return val;
    }

    ```

    替代方案：`Integer.parseInt(String s, int radix)`。更加健壮，并且适用于负整数。
