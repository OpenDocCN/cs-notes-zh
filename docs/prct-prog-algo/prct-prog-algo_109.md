# 5.3 �� 子字符串搜索

> 原文：[`algs4.cs.princeton.edu/53substring`](https://algs4.cs.princeton.edu/53substring)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)


本节正在大规模施工中。在长字符串中搜索 - 在线。

[这个网站](http://www-igm.univ-mlv.fr/~lecroq/string/)是一个关于精确字符串搜索算法的重要资源。

[Java 中的高性能模式匹配](http://johannburkard.de/software/stringsearch/)用于一般字符串搜索，带通配符的搜索和带字符类的搜索。

程序 Brute.java 是暴力字符串搜索。基本上等同于 SystemSearch.java。

## 拉宾卡普。

程序 RabinKarp.java 实现了拉宾卡普随机指纹算法。

## Knuth-Morris-Pratt。

程序 KMP.java 是 Knuth-Morris-Pratt 算法。KMPplus.java 是一个改进版本，时间和空间复杂度与 M + N 成正比（与字母表大小 R 无关）。

## Boyer-Moore。

程序 BoyerMoore.java 实现了 Boyer-Moore 算法的坏字符规则部分。它不实现强好后缀规则。

### 入侵检测系统。

需要非常快速的字符串搜索，因为这些部署在网络的瓶颈处。应用

#### 问答

#### 练习

1.  设计一个从右到左扫描模式的暴力子字符串搜索算法。

1.  展示 Brute-Force 算法的跟踪，样式类似于图 XYZ，用于以下模式和文本字符串。

    +   AAAAAAAB; AAAAAAAAAAAAAAAAAAAAAAAAB

    +   ABABABAB; ABABABABAABABABABAAAAAAAA

1.  确定以下模式字符串的 KMP DFA。

    +   AAAAAAAB

    +   AACAAAB

    +   ABABABAB

    +   ABAABAAABAAAB

    +   ABAABCABAABCB

1.  假设模式和文本是在大小为 R >= 2 的字母表上的随机字符串。证明字符比较的期望次数为(N - M + 1) (1 - R^-M) / (1 - R^-1) <= 2 (N - M + 1)。

1.  构造一个例子，其中 Boyer-Moore 算法（仅使用坏字符规则）性能较差。

1.  如何修改拉宾卡普算法以搜索给定模式，并附加条件中间字符是一个“通配符”（任何文本字符都可以匹配它）。

1.  如何修改拉宾卡普算法以确定文本中是否存在 k 个模式子集中的任何一个（比如，所有长度相同）？

    *解决方案。* 计算 k 个模式的哈希值，并将哈希值存储在一个集合中。

1.  如何修改拉宾卡普算法以在 N×N 文本中搜索 M×M 模式？或者在 N×N 文本中搜索其他不规则形状的模式？

1.  蒙特卡洛与拉斯维加斯拉宾卡普。

1.  **在线回文检测。** 逐个读入字符。报告每个瞬间当前字符串是否是回文。*提示*：使用 Karp-Rabin 哈希思想。

1.  **串联重复。** 在字符串 s 中，基本字符串 b 的串联重复是由至少一个连续的基本字符串 b 的副本组成的子字符串。给定 b 和 s，设计一个算法，在 s 中找到 b 的最大长度的串联重复。运行时间应与 M + N 成正比，其中 M 是 b 的长度，N 是 s 的长度。

    *解决方案。* 这个问题是子字符串搜索的一般化（s 中是否至少有一个连续的 b 的副本？），所以我们需要一个泛化的子字符串搜索算法。创建 k 个 b 的连接副本的 Knuth-Morris-Pratt DFA，其中 k = n/m。现在，在输入 s 上模拟 DFA 并记录它达到的最大状态。从中，我们可以识别最长的串联重复。

1.  **后缀前缀匹配。** 设计一个线性时间算法，找到一个字符串*a*的最长后缀，恰好匹配另一个字符串*b*的前缀。

1.  **循环旋转。** 设计一个线性时间算法来确定一个字符串是否是另一个字符串的循环旋转。如果字符串*a*是字符串*b*的循环旋转，那么*a*和*b*具有相同的长度，*a*由*b*的后缀和前缀组成。

1.  **循环字符串的子串。** 设计一个线性时间算法来确定一个字符串 *a* 是否是循环字符串 *b* 的子串。

1.  **最长回文子串。** 给定一个字符串 s，找到最长的回文子串（或 Watson-crick 回文串）。*解决方案*：可以使用后缀树或[Manacher's algorithm](http://www.leetcode.com/2011/11/longest-palindromic-substring-part-ii.html)在线性时��内解决。这里有一个通常在线性对数时间内运行的更简单的解决方案。首先，我们描述如何在线性时间内找到长度恰好为 L 的所有回文子串：使用 Karp-Rabin 迭代地形成每个长度为 L 的子串（及其反转）的哈希值，并进行比较。由于你不知道 L，重复将你对 L 的猜测加倍，直到你知道最佳长度在 L 和 2L 之间。然后使用二分查找找到确切的长度。

    *解决方案。* Manacher.java 是 Manacher 算法的实现。

1.  **重复子串。** [ [Mihai Patrascu](http://web.mit.edu/~mip/www/probs.html)] 给定一个整数 K 和长度为 N 的字符串，找到至少出现 K 次的最长子串。

    *一个解决方案。* 假设你知道重复字符串的长度 L。对长度为 L 的每个子串进行哈希处理，并检查任何哈希是否出现 K 次或更多。如果是，检查以确保你没有运气不佳。由于你不知道 L，重复将你对 L 的猜测加倍，直到你知道最佳长度在 L 和 2L 之间。然后使用二分查找找到正确的值。

1.  **最长公共子串。** 给定两个（或三个）字符串，找到在所有三个字符串中都出现的最长子串。*提示*：假设你知道最长公共子串的长度 L。对长度为 L 的每个子串进行哈希处理，并检查任何哈希桶是否包含每个字符串的（至少）一个条目。

1.  **所有匹配。** 修改 KMP 以在线性时间内找到所有匹配（而不是最左匹配）。

1.  **斐波那契字符串。** KMP 的有趣案例。F(1) = B, F(2) = A, F(3) = AB, F(4) = ABA, F(5) = ABAAB, F(N) = F(N-1) F(N-2)。

1.  假设 x 和 y 是两个字符串。设计一个线性时间算法来确定是否存在整数 m 和 n 使得 x^m = y^n（其中 x^m 表示 x 的 m 个副本的连接）。

    *解决方案。* 只需检查 xy = yx 的位置（这个事实并不平凡 - 它来自于 Lyndon-Schutzenberger 定理）。

1.  **字符串的周期。** 让 s 为一个非空字符串。如果对于所有 i = 0, 1, ..., N-p-1 都有 s[i] = s[i+p]，则整数 p 被称为 s 的*周期*。字符串 s 的周期是是 s 的周期中最小的整数 p（可以是 N）。例如，ABCABCABCABCAB 的周期是 3。设计一个线性时间算法来计算字符串的周期。

1.  **字符串的边界。** 给定一个非空字符串 s，如果 s = yw = wz 对于一些字符串 y、z 和 w 且 |y| = |z| = p，则我们将字符串 w 定义为 s 的*边界*，即 w 是 s 的既是前缀又是后缀的一个合适子串。字符串的边界是 s 的最长合适边界（可以为空）。例如，ABCABCABCABCAB 的边界是 w = ABCABCAB（其中 y = ABC，z = CAB，p = 3）。设计一个线性时间算法来计算字符串的边界。

1.  **变位词子串搜索。** 给定长度为 N 的文本字符串 txt[] 和长度为 M 的模式字符串 pat[]，确定 pat[] 或其任何变位词（其 M! 种排列之一）是否出现在文本中。

    *提示*：在文本中维护长度为 M 的给定子串的字母频率直方图。
