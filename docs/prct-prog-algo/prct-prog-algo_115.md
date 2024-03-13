# 6.3 后缀数组

> 原文：[`algs4.cs.princeton.edu/63suffix`](https://algs4.cs.princeton.edu/63suffix)

本章正在大规模施工中。

## 重要说明。

*从 Oracle 和 OpenJDK Java 7，Update 6 开始，`substring()`方法在提取的子串大小上花费[线性时间和空间](http://java-performance.info/changes-to-string-java-1-7-0_06)（而不是常数时间和空间）。[String API](http://docs.oracle.com/javase/7/docs/api/java/lang/String.html)对其所有方法，包括`substring()`和`charAt()`，都不提供性能保证。

课本和书站中的程序已经更新，不再依赖于常数时间的子串操作。但是，如果您使用的是课本的第三版印刷版（或更早版本），请自行考虑。*

## 后缀排序和后缀数组。

后缀排序：给定一个字符串，按升序对该字符串的后缀进行排序。排序后的列表称为*后缀数组*。程序 SuffixArray.java 构建了一个后缀数组数据结构。

### 最长重复子串。

将排序应用于计算生物学和抄袭检测。程序 LongestRepeatedSubstring.java 使用后缀数组解决了这个问题。

### 上下文关键词（KWIC）。

给定后缀数组，通过二分搜索很容易搜索字符串或句子。内存是线性的。搜索是 O(K log N)，其中 K 是您要搜索的字符串的长度。（通过使用 lcp 数组，可以在 K + log N 内完成。）有时被称为 KWIK（关键词上下文）和共现。被语言学家使用。Concordancer = 制作索引的程序。马丁·阿贝格（Martin Abegg）曾经将死海古卷的索引反向工程并转换为可读文本。程序 KWIK.java。

### Manber 算法。

然而，输入大小为 N，因此我们可能希望利用子串的重叠性质并取得更好的效果。程序 Manber.java 使用 Manber-Myers 重复加倍算法的版本对字符串后缀进行排序。[Larsson](http://www.larsson.dogma.net/tr204.pdf)在内部排序例程替换为 O(N log N)基于比较的排序算法时给出了 O(N log N)的分析。

### Kasai 算法。

这里是描述[Kasai 算法](https://www.geeksforgeeks.org/%C2%AD%C2%ADkasais-algorithm-for-construction-of-lcp-array-from-suffix-array/)计算 lcp 数组的内容。

#### 问答

### 线性时间后缀排序。

倾斜分治。最简单的线性时间后缀排序解决方案。递归地对索引为{0, 1, 2} mod 3 的后缀进行排序，然后合并。

#### 练习

1.  给出字符串"abacadaba"的后缀数组。此外，给出 i 从 1 到 n-1 的`lcp(i)`值表。

1.  对字符串"mississippi"重复上一个问题。

1.  创建一个长度为 n 的`SuffixArray`对象需要多少字节？

1.  下面的代码片段计算后缀排序的所有后缀有什么问题？

    ```
    suffix = ""; 
    for (int i = s.length() - 1; i >= 0; i--) {
        suffix = s.charAt(i) + suffix;
        suffixes[i] = suffix;
    }

    ```

    *答案*：二次时间 *和* 二次空间。

1.  下面的代码片段计算后缀排序的所有循环后缀有什么问题？

    ```
    int n = s.length();
    for (int i = 0; i < n; i++)
        suffixes[i] = s.substring(i, n) + s.substring(0, i);

    ```

    *答案*：二次时间 *和* 二次空间。

1.  下面的代码片段计算后缀排序的所有循环后缀有什么问题？

    ```
    int n = s.length;
    StringBuilder ss = new StringBuilder();
    ss.append(s).append(s);
    for (int i = 0; i < N; i++)
        suffixes[i] = ss.substring(i, i + n);

    ```

    *答案*：二次时间 *和* 二次空间。

1.  **最长公共子串。** 编写一个程序 LongestCommonSubstring.java，接受两个文件名作为命令行参数，读取这两个文本文件，并找到两者中都出现的最长子串。*提示*：为 s#t 创建一个后缀数组，其中 s 和 t 是两个文本字符串，#是两者都不出现的字符。

    1970 年，D. Knuth 猜想在线性时间内解决这个问题是不可能的。事实上，可以使用后缀树或后缀数组在线性时间内（在最坏情况下）解决这个问题。

1.  **Burrows-Wheeler 变换。** Burrows-Wheeler 变换（BWT）是数据压缩算法中使用的一种转换，包括 bzip2 和基因组学中的高通量测序。给定长度为 N 的文本字符串（以特殊的文件结束符 $ 结尾，比任何其他字符都小），考虑 N×N 矩阵，其中每行包含原始文本字符串的不同循环旋转。按字典顺序对行进行排序。Burrows-Wheeler 变换是排序矩阵中的最右列。例如，BWT (mississippi$) = ipssm$pissii。

1.  **Burrows-Wheeler 逆变换。** Burrows-Wheeler 逆变换（BWI）用于反转 BWT。给定文本字符串的 BWT，设计一个线性时间算法来恢复原始文本字符串。例如，BWI(ipssm$pissii) = mississippi$。

1.  **循环字符串线性化。** 给定一个字符串 s，找到字典序最小的旋转。在化学数据库中用于循环分子。每个分子表示为循环字符串。规范表示是字典序最小的旋转。设计一个算法来计算循环字符串的规范表示 *提示*：后缀排序。

    *其他解决方案*：Duval 算法使用 Lyndon 分解和由周元提出的令人惊讶优雅的[最小表达算法](http://online-judge.uva.es/board/viewtopic.php?f=22&t=42601#p100062)。

1.  **加速排名。** 使用以下思想加速 `rank()` 方法中的二分搜索。让 `lo` 和 `hi` 表示当前搜索区间的左右端点。让 `lcpLo` 表示查询字符串和 `suffixes[lo]` 的 lcp，让 `lcpHi` 表示查询字符串和 `suffixes[hi]` 的 lcp。然后，在将查询字符串与 `suffixes[mid]` 进行比较时，只需要比较从 `lcp = min(lcpLo, lcpHi)` 开始的字符，因为搜索区间中的所有后缀都具有相同的前 `lcp` 个字符。

1.  **加速排名分析。** 显示加速排名的最坏情况运行时间仍然与 L log N 成正比，其中 L 是查询的长度，N 是文本的长度。然而，Myers 和 Manber 报告说这在实践中加快了计算。理论上，可以使用非相邻的 lcp 值将其改进为 L + log N。

1.  **最长 3 重复子串。** 给定一个文本字符串，找到重复 3 次或更多次的最长子串。

1.  **最长 k 重复子串。** 给定一个文本字符串和一个整数 k，找到重复 k 次或更多次的最长子串。

1.  **长重复子串。** 给定一个文本字符串和一个整数 L，找到所有长度大于等于 L 的重复子串。

1.  **三个字符串中的最长公共子串。** 给定三个字符串 r、s 和 t，找到在所有三个字符���中出现的最长子串。

1.  **最长公共反向互补子串。** 给定两个 DNA 字符串，找到出现在一个字符串中的最长子串，其反向 Watson-Crick 互补出现在另一个字符串中。如果 t 是 s 的反向，除了以下替换 AT、CG，则两个字符串 s 和 t 是反向互补的。例如 ATTTCGG 和 CCGAAAT 是彼此的反向互补。 *提示*：后缀排序。

1.  **具有更少内存的后缀数组。** 不使用子字符串数组，其中 `suffixes[i]` 指的是第 i 个排序后缀，而是维护一个整数数组，其中 index[i] 指的是第 i 个排序后缀的偏移量。要比较由 a = index[i] 和 b = index[j] 表示的子字符串，比较字符 `s.charAt(a)` 与 `s.charAt(b)`，`s.charAt(a+1)` 与 `s.charAt(b+1)`，依此类推。你节省了多少内存？你的程序更快吗？

1.  **k-gram 频率计数。** 给定一个文本字符串，设计一个数据结构以高效地回答以下形式的查询：给定一个 k-gram 出现了多少次？在最坏情况下，时间复杂度应该与 k log N 成正比，其中 k 是 k-gram 的长度，N 是文本字符串的长度。

1.  **最频繁的 k-gram。** 给定一个文本字符串和一个整数 k，找到出现频率最高的 k-gram。

1.  **最短唯一子串。** 给定一个文本字符串，找到一个出现仅一次的最短子串。这个问题常见于生物信息学。

1.  **最短非子串。** 给定一个比特串，找到一个最短的比特串，它不作为子串出现。

1.  **最短唯一子串。** 给定一个文本字符串，预处理它以回答以下形式的最短唯一子串查询：给定一个索引 q 到文本字符串，找到一个包含索引 q 且在文本中其他地方不作为子串出现的最短子串。
