# 5.5   数据压缩

> 原文：[`algs4.cs.princeton.edu/55compression`](https://algs4.cs.princeton.edu/55compression)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)


本节正在大规模施工中。

数据压缩：将文件大小缩小以节省*空间*存储和在传输时节省*时间*。摩尔定律：芯片上的晶体管数量每 18-24 个月翻一番。帕金森定律：数据会扩张以填满可用空间。文本、图像、声音、视频等。维基百科提供[公共转储](http://meta.wikimedia.org/wiki/Data_dumps)以供学术研究和再发布。使用 bzip 和 SevenZip 的 LZMA。对 300GB 数据进行压缩可能需要一周的时间。

### 古代思想。

摩尔斯电码，十进制数系统，自然语言，旋转电话（较低的号码拨号速度更快，所以纽约是 212，芝加哥是 312）。

## 二进制输入和输出流。

我们使用 BinaryStdIn.java、BinaryStdOut.java、BinaryDump.java、HexDump.java 和 PictureDump.java。

### 固定长度编码。

需要 ceil(lg R) 位来指定 R 个符号中的一个。Genome.java。使用 Alphabet.java。

### 运行长度编码。

RunLength.java。

### 变长编码。

希望有唯一可解码的编码。实现这一目标的一种方法是向每个码字附加一个特殊的停止符号。更好的方法是前缀无码：没有字符串是另一个字符串的前缀。例如，{ 01, 10, 0010, 1111 } 是前缀无码，但 { 01, 10, 0010, 1010 } 不是，因为 10 是 1010 的前缀。

给出传真机的例子。

### Huffman 编码。

构建最佳前缀无码的特定方式。由 David Huffman 在 1950 年在 MIT 时发明。Huffman.java 实现了 Huffman 算法。

**属性 A.** 没有前缀无码使用更少的比特。

### LZW 压缩。

使用 TST.java 中的前缀匹配代码，LZW.java 实现了 LZW 压缩。

现实世界：Pkzip = LZW + Shannon-Fano，GIF，TIFF，V.42bis 调制解调器，Unix 压缩。实际问题：

+   将所有内容编码为二进制。

+   限制符号表中元素的数量（GIF = 丢弃并重新开始，Unix 压缩 = 不起作用时丢弃）。

+   最初字典有 512 个元素（其中填充了 256 个 ASCII 字符），因此我们每个整数传输 9 位。当填满时，我们将其扩展到 1024 并开始每个整数传输 10 位。

+   只遍历树一次（可能会破坏我们的字符串表抽象）。

实际问题：限制符号表中元素的数量。

### 总结。

Huffman：固定长度符号的变长编码。LZW：变长字符串的固定长度编码。

### 通用压缩算法。

不可能压缩所有文件（通过简单计数论证）。直观论证：压缩莎士比亚的生平作品，然后压缩结果，再次压缩结果。如果每个文件都严格缩小，最终将只剩下一个比特。

### 参考文献。

卡内基梅隆大学的 Guy Blelloch 在 [数据压缩](http://www.cs.cmu.edu/afs/cs/project/pscico-guyb/realworld/www/compression.pdf) 方面有一章非常出色。

## 错误校正/检测。

假设用于发送信息的信道存在噪声，每个比特以概率 p 翻转。发送每个比特 3 次；解码时取 3 个比特的大多数。解码比特的正确概率为 3p² - 2p³。这小于 p（如果 p < 1/2）。可以通过多次发送每个比特来减少解码比特错误的概率，但这在传输速率方面是浪费的。

### Reed-Solomon 编码。

[参考资料](http://www.cs.cornell.edu/Courses/cs722/2000sp/ReedSolomon.pdf)。用于大容量存储系统（CD 和 DVD）和卫星传输（旅行者号探测器，火星探路者）当错误是突发性的时候。将要发送的数据视为一个度为 d 的多项式。只需要 d+1 个点来唯一指定多项式。发送更多点以实现纠错/检测错误。如果我们要发送的编码是 a0，a1，...，am-1（每个元素在有限域 K 上），将其视为多项式 p(x) = a0 + a1x + ... + am-1 x^m-1。发送 p(0)，p(b)，p(b²)，...，其中 b 是 K 上的乘法循环群的生成元。

### 香农编码定理。

大致来说，如果信道容量为 C，则我们可以以略低于 C 的速率发送比特，使用编码方案将解码错误的概率降低到任意所需水平。证明是非构造性的。

#### 问答

#### 练习

1.  以下哪些编码是前缀自由的？唯一可解码的？对于那些唯一可解码的编码，给出编码为 1000000000000 的编码。

    ```java
        code 1    code 2    code 3   code 4
    A     0         0          1       1
    B     100       1         01      01
    C     10       00        001     001
    D     11       11       0001     000

    ```

1.  给出一个不是前缀自由的唯一可解码编码的例子。

    *解决方案。* 任何无后缀编码都是唯一可解码的，例如，{ 0, 01 }。

1.  给出一个不是前缀自由或无后缀的唯一可解码编码的例子。

    *解决方案。* { 0011, 011, 11, 1110 }或{ 01, 10, 011, 110 }。

1.  { 1, 100000, 00 }，{ 01, 1001, 1011, 111, 1110 }和{ 1, 011, 01110, 1110, 10011 }是唯一可解码的吗？如果不是，找到一个具有两个编码的字符串。*解决方案。* 第一组编码是唯一可解码的。第二组编码不是唯一可解码的，因为 111-01-1110-01 和 1110-111-1001 是 11101111001 的两种解码方式。第三组编码不是唯一可解码的，因为 01110-1110-011 和 011-1-011-10011 是 011101110011 的两种解码方式。

1.  **唯一可解码性测试。** 实现 Sardinas-Patterson 算法，用于测试一组编码词是否是唯一可解码的：将所有编码词添加到一个集合中。检查所有编码词对，看看是否有一个是另一个的前缀；如果是，提取*悬挂后缀*（即，长字符串中不是短字符串前缀的部分）。如果悬挂后缀是一个编码词，则编码不是唯一可解码的；否则，将悬挂后缀添加到列表中（前提是它尚未存在）。重复此过程直到没有剩余的新悬挂后缀为止。

    该算法是有限的，因为添加到列表中的所有悬挂后缀都是有限一组编码词的后缀，并且悬挂后缀最多只能添加一次。

    +   { 0, 01, 11 }。编码词 0 是 01 的前缀，因此添加悬挂后缀 1。{ 0, 01, 11, 1 }。编码词 0 是 01 的前缀，但悬挂后缀 1 已经在列表中；编码词 1 是 11 的前缀，但悬挂后缀 1 已经在列表中。没有其他悬挂后缀，因此得出该集合是唯一可解码的结论。

    +   { 0, 01, 10 }。编码词 0 是 01 的前缀，因此将悬挂后缀 1 添加到列表中。{ 0, 01, 10, 1 }。编码词 1 是 10 的前缀，但悬挂后缀 0 是一个编码词。因此，得出该编码不是唯一可解码的结论。

1.  **Kraft-McMillan 不等式。** 考虑一个具有长度为 n1, n2, ..., nN 的 N 个编码词的编码 C。证明如果编码是唯一可解码的，则 K(C) = sum_i = 1 to N 2^(-ni) ≤ 1。

1.  **Kraft-McMillan 构造。** 假设我们有一组满足不等式 sum_i = 1 to N 2^(-ni) ≤ 1 的整数 n1, n2, ..., nN。证明总是可以找到一个编码长度为 n1, n2, ..., nN 的前缀自由编码。因此，通过将注意力限制在前缀自由编码上（而不是唯一可解码编码），我们不会失去太多。

1.  **Kraft-McMillan 最优前缀自由编码等式。** 证明如果 C 是一个最优前缀自由编码，那么 Kraft-McMillan 不等式是一个等式：K(C) = sum_i = 1 to N 2^(-ni) = 1。

1.  假设所有符号概率都是 2 的负幂次方。描述哈夫曼编码。

1.  假设所有符号频率相等。描述哈夫曼编码。

1.  找到一个哈夫曼编码，其中概率为 pi 的符号的长度大于 ceil(-lg pi)。

    *解决方案.* .01 (000), .30 (001), .34 (01), .35 (1)。码字 001 的长度大于 ceil(-lg .30)。

1.  真或假。任何最优前缀自由编码都可以通过哈夫曼算法获得。

    *解决方案.* 错误。考虑以下符号和频率集合（A 26, B 24, C 14, D 13, E 12, F 11）。

    ```java
           C1   C2   C3
    A 26   01   10   00
    B 24   10   01   01
    C 14  000  111  100
    D 13  001  110  101
    E 12  110  001  110
    F 11  111  000  111

    ```

    在任何哈夫曼编码中，字符 A 和 B 的编码必须以不同的位开始，但是代码 C3 没有这个属性（尽管它是一个最优前缀自由编码）。

1.  以下输入的 LZW 编码是什么？

    +   T O B E O R N O T T O B E

    +   Y A B B A D A B B A D A B B A D O O

    +   A A A A A A A A A A A A A A A A A A A A A

1.  描述 LZW 编码中的棘手情况。

    *解决方案.* 每当遇到 cScSc，其中 c 是一个符号，S 是一个字符串，cS 在字典中但 cSc 不在字典中。

1.  作为 N 的函数，编码 N 个符号 A 需要多少位？N 个序列 ABC 需要多少位？

1.  让 F(i) 为第 i 个斐波那契数。考虑 N 个符号，其中第 i 个符号的频率为 F(i)。注意 F(1) + F(2) + ... + F(N) = F(N+2) - 1。描述哈夫曼编码。

    *解决方案.* 最长的码字长度为 N-1。

1.  显示对于给定的 N 个符号集合，至少有 2^(N-1) 种不同的哈夫曼编码。

    *解决方案.* 有 N-1 个内部节点，每个节点都可以任意选择其左右子节点。

1.  给出一个哈夫曼编码，其中输出中 0 的频率远远高于 1 的频率。

    *解决方案.* 如果字符 'A' 出现一百万次，字符 'B' 出现一次，那么 'A' 的码字将是 0，'B' 的码字将是 1。

1.  证明有关哈夫曼树的以下事实。

    +   两个最长的码字长度相同。

    +   如果符号 i 的频率严格大于符号 j 的频率，则符号 i 的码字长度小于或等于符号 j 的码字长度。

1.  描述如何在一组符号 { 0, 1, ..., N-1 } 上传输哈夫曼编码（或最优前缀自由编码），使用 2N - 1 + N ceil(lg N) 位。

    *提示*：使用 2N-1 位来指定相应 trie 的结构。

1.  假设在一个扩展 ASCII 文件（8 位字符）中，最大字符频率最多是最小字符频率的两倍。证明固定长度的 8 位扩展 ASCII 码是最优的。

1.  **香农-范诺编码。** 证明哈夫曼算法的以下自顶向下版本不是最优的。将码字集合 C 分成两个子集 C1 和 C2，其频率（几乎）相等。递归地为 C1 和 C2 构建树，从 0 开始为 C1 的所有码字，从 1 开始为 C2 的所有码字。为了实现第一步，香农和范诺建议按频率对码字进行排序，并尽可能地将集合分成两个子数组。

    *解决方案.* S 32, H 25, A 20, N 18, O 5。

1.  **LZMW 编码（米勒-韦格曼 1985）。** LZ 变种：在字典中搜索最长的已经存在的字符串（当前匹配）；将前一个匹配与当前匹配的连接添加到字典中。字典条目增长更快。当字典填满时，也可以删除低频率条目。难以实现。

1.  **LZAP 编码。** 类似于 LZMW：不仅添加前一个匹配与当前匹配的连接，还添加前一个匹配与当前匹配的 *所有前缀* 的连接。比 LZMW 更容易实现，但字典条目更多。

1.  确定一个不是前缀自由的最优编码。

    *提示*：只需要 3 个具有相等频率的符号。

1.  确定对于相同输入的两个最优前缀自由编码，其码字长度分布不同。

    *提示*：只需要 4 个符号。

1.  **最小方差 Huffman 编码。** 由于与打破平局相关的不确定性，Huffman 算法可能生成具有不同码字长度分布的编码。在生成压缩流时传输，希望以（近）恒定速率传输比特。找到最小化 sum_i (p_i (l_i - l_average(T)) ²) 的 Huffman 编码。

    *解决方案。* 在组合 tries 时，通过选择具有最小概率的最早生成的 trie 来打破平局。

1.  **用于 Huffman 编码的双队列算法。** 证明以下算法计算出 Huffman 编码（如果输入符号已按频率排序，则在线性时间内运行）。维护两个 FIFO 队列：第一个队列包含输入符号，按频率升序排列，第二个队列包含组合权重的内部节点。只要两个队列中有超过一个节点，就通过检查两个队列的前端出队两个权重最小的节点。创建一个新的内部节点（左右子节点 = 两个节点，权重 = 两个节点的权重之和）并将其加入第二个队列。

    要获得最小方差的 Huffman 编码，通过从第一个队列中选择节点来打破平局。

    *提示*：证明第二个队列按频率升序排列。

1.  **兄弟属性。** 如果（i）每个节点（除了根节点）都有一个兄弟节点，且（ii）二叉树可以按概率的非递增顺序列出，使得在列表中所有兄弟节点都相邻，则二叉树具有 *兄弟属性*。证明二叉树表示 Huffman 树当且仅当它具有兄弟属性。

1.  **相对编码。** 不是压缩图像中的每个像素，而是考虑像素与前一个像素之间的差异并对差异进行编码。直觉：通常像素变化不大。与颜色表字母上的 LZW 一起使用。

1.  **可变宽度 LZW 编码。** 在第 2^p 个码字插入表后，将表的宽度从 p 增加到 p+1。与颜色表字母一起使用。

1.  **自适应 Huffman 编码。** 一次通过算法，不需要发送前缀自由码。根据迄今为止读入的字符的频率构建 Huffman 树。在读入每个字符后更新树。编码器和解码器需要协调处理平局的约定。

1.  **香农熵。** 具有可能值 x1, ..., xN 且以概率 p1, ..., pN 出现的离散随机变量 X 的熵 H 定义为 H(X) = -p1 lg p1 - p2 lg p2 - ... - pN lg pN，其中 0 lg 0 = 0 与极限一致。

    +   一个公平硬币的熵是多少？

    +   一个硬币的熵是什么，其中两面都是正面？

    +   一个六面骰子的熵是多少？

        *解决方案。* -lg (1/6) 大约为 2.584962。

    +   两个公平骰子的和的熵是多少？

    +   给定一个取 N 个值的随机变量。什么分布使熵最大化？熵是信息论中的一个基本概念。香农的源编码定理断言，要压缩来自一系列独立同分布随机变量流的数据，至少需要每个符号 H(X) 位。例如，发送一系列公平骰子投掷结果至少需要每次骰子投掷 2.584962 位。

1.  **经验熵。** *经验熵* 是通过计算每个符号出现频率并将其用作离散随机变量的概率来获得的一段文本的熵。计算你最喜欢小说的经验熵。将其与 Huffman 编码实现的数据压缩率进行比较。

1.  **香农实验。** 进行以下实验。给一个主体一段文本（或 Leipzig 语料库）中的 k 个字母序列，并要求他们预测下一个字母。估计主体在 k = 1, 2, 5, 100 时答对的比例。

1.  真或假。固定长度编码是���一可解码的。

    *解决方案。* 真，它们是前缀自由的。

1.  给出两棵不同高度的 Huffman 树字符串 ABCCDD。

1.  **前缀自由编码。** 设计一个高效的算法来确定一组二进制码字是否是前缀自由的。*提示*：使用二进制 trie 或排序。

1.  **唯一可解码编码。** 设计一个唯一可解码的编码，它不是前缀自由编码。提示：后缀自由编码 = 前缀自由编码的反向。后缀自由编码的反向是前缀自由编码 -> 可以通过以相反顺序读取压缩消息来解码。不太方便。

1.  **哈夫曼树。** 修改 Huffman.java，使得编码器打印查找表而不是先序遍历，并修改解码器以通过读取查找表构建树。

1.  真或假。在最佳前缀自由三进制编码中，出现频率最低的三个符号具有相同的长度。

    *解答。* False.

1.  **三进制哈夫曼编码。** 将哈夫曼算法推广到三进制字母表（0, 1 和 2）上的码字，而不是二进制字母表。也就是说，给定一个字节流，找到一个使用尽可能少的三进制位（0、1 和 2）的前缀自由三进制编码。证明它产生最佳前缀自由三进制编码。

    *解答。* 在每一步中合并最小的 3 个概率（而不是最小的 2 个）。当有 3 + 2k 个符号时，这种方法有效。为了将其减少到这种情况，添加概率为 0 的 1 或 2 个虚拟符号。（或者，如果符号数量不是 3 + 2k，则在第一步中合并少于 3 个符号。）例如：{ 0.1, 0.2, 0.2, 0.5 }。

1.  **非二进制哈夫曼编码。** 将哈夫曼算法扩展到 m 进制字母表（0, 1, 2, ..., m-1）上的码字，而不是二进制字母表。

1.  考虑以下由 3 个 a、7 个 c、6 个 t 和 5 个 g 组成的 21 个字符消息。

    ```java
    a a c c c c a c t t g g g t t t t c c g g 

    ```

    以下的 43 位是否是上述消息的可能哈夫曼编码？

    ```java
    0000001111000101010010010010101010111001001 

    ```

    尽可能简洁而严谨地证明你的答案。

    *解答。* 对于一条消息的哈夫曼编码会产生使用最少位数的编码，其中 2 位二进制码 a = 00, c = 01, g = 10, t = 11 是一个使用 21 * 2 = 42 位的前缀自由编码。因此，哈夫曼编码将使用少于 43 位。

1.  如果一个二叉树是*满的*，则除了叶子节点外的每个节点都有两个子节点。证明与最佳前缀自由编码对应的任何二叉树都是满的。

    *提示*：如果内部节点只有一个子节点，请用其唯一子节点替换该内部节点。

1.  **Move-to-front 编码（Bentley, Sleator, Tarjan 和 Wei 1986）。** 编写一个名为 `MoveToFront` 的程序，实现 move-to-front 编码和解码。维护符号字母表的列表，其中频繁出现的符号位于前面。一个符号被编码为列表中在它之前的符号数。编码一个符号后，将其移动到列表的前面。参考

1.  **Move-ahead-k 编码。** 与 move-to-front 编码相同，但将符号向前移动 k 个位置。

1.  **等待-c-并移动。** 与 move-to-front 编码相同，但只有在符号在上次移动到前面后遇到 c 次后才将其移动到前面。

1.  **双哈夫曼压缩。** 找到一个输入，对该输入应用 Huffman.java 中的 `compress()` 方法两次比仅应用 `compress()` 一次导致输出严格较小。

1.  **合并 k 个排序数组。** 你有 k 个已排序的列表，长度分别为 n1、n2、...、nk。假设你可以执行的唯一操作是 2 路合并：给定长度为 n1 的一个已排序数组和长度为 n2 的另一个已排序数组，用长度为 n = n1 + n2 的已排序数组替换它们。此外，2 路合并操作需要 n 个单位的时间。合并 k 个已排序数组的最佳方法是什么？

    *解决方案.* 将列表长度排序，使得 n1 < n2 < ... < nk。重复地取最小的两个列表并应用 2 路合并操作。最优性的证明与哈夫曼编码的最优性证明相同：重复应用 2 路合并操作会产生一棵二叉树，其中每个叶节点对应于原始排序列表中的一个，每个内部节点对应于一个 2 路合并操作。任何原始列表对总体成本的贡献是列表长度乘以其树深度（因为这是其元素参与 2 路合并的次数）。
