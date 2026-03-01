# Java编程和软件工程基础：2-5：使用HashMap统计单词出现次数 📊

![](img/5cdf7bebedbe945c6ddb4da5d89191ea_0.png)

在本节课中，我们将学习如何使用Java中的`HashMap`数据结构来统计一个文件中每个单词出现的次数。我们将从一个统计单词总数的程序开始，逐步将其改造为能够统计每个单词具体出现次数的程序。

---

## 概述

我们将编写一个程序，读取一个文本文件，并计算文件中每个单词出现的频率。例如，统计单词“the”或“wonderful”出现了多少次。我们将使用`HashMap`来存储单词（作为键）和其对应的出现次数（作为值）。

---

![](img/5cdf7bebedbe945c6ddb4da5d89191ea_2.png)

![](img/5cdf7bebedbe945c6ddb4da5d89191ea_3.png)

## 从统计单词总数开始

我们从一个已经可以工作的程序开始。这个程序包含一个名为`countWords`的方法，它的功能是读取文件，遍历所有单词，并统计单词的总数。

```java
public void countWords() {
    FileResource resource = new FileResource();
    int total = 0;
    for (String word : resource.words()) {
        total = total + 1;
    }
    System.out.println("Total words: " + total);
}
```

运行这个程序，例如输入文件名“Confucius”，它会输出文件中的总单词数，例如34582个。

---

## 引入HashMap统计每个单词

上一节我们介绍了如何统计单词总数，本节中我们来看看如何统计每个单词的具体出现次数。为了实现这个功能，我们需要使用`HashMap`。

我们需要在方法中添加一个局部变量：一个`HashMap<String, Integer>`。在这个映射中，键（Key）是文件中出现的每个单词（字符串），值（Value）是该单词出现的次数（整数）。

![](img/5cdf7bebedbe945c6ddb4da5d89191ea_5.png)

首先，我们需要创建这个`HashMap`。确保已经导入了`java.util.HashMap`包。

```java
import java.util.HashMap;

public void countWords() {
    FileResource resource = new FileResource();
    HashMap<String, Integer> map = new HashMap<String, Integer>();
    // ... 后续代码
}
```

---

## 填充HashMap的逻辑

现在，当我们读取每个单词时，不再只是增加总数，而是需要检查这个单词是否已经在`map`中出现过。

以下是填充`HashMap`的核心逻辑步骤：

1.  将读取的单词转换为小写，以确保统计不区分大小写。
2.  检查这个单词是否已经是`map`中的一个键。
3.  如果单词已存在（即我们之前见过它），则获取其当前的计数值，加1，然后更新`map`。
4.  如果单词不存在（即第一次见到），则将其作为新键放入`map`，并将值设为1。

以下是实现上述逻辑的代码：

```java
for (String w : resource.words()) {
    w = w.toLowerCase(); // 转换为小写
    if (map.containsKey(w)) {
        // 单词已存在，计数加1
        map.put(w, map.get(w) + 1);
    } else {
        // 单词第一次出现
        map.put(w, 1);
    }
}
```

---

## 输出统计结果

在将所有单词及其计数添加到`map`之后，我们需要将结果打印出来。我们将遍历`map`的键集合（即所有不同的单词），获取每个单词对应的出现次数，并选择性地打印那些出现频率较高的单词。

以下是输出结果的步骤：

1.  使用`keySet()`方法获取`map`中所有键的集合。
2.  遍历这个集合，对于每个键（单词），通过`map.get(key)`获取其出现次数。
3.  设置一个阈值（例如500次），只打印出现次数超过这个阈值的单词。

```java
for (String word : map.keySet()) {
    int occurrences = map.get(word);
    if (occurrences > 500) { // 设置阈值
        System.out.println(occurrences + "\t" + word);
    }
}
```

运行修改后的程序，输入“Confucius”文件，我们可以看到出现次数超过500次的单词，例如“the”出现了2000多次，“and”出现了762次。

如果想看到更多单词，可以降低阈值，例如改为200次。再次运行程序，我们会看到更多单词及其出现次数，例如“master”出现了484次。

---

## 总结

本节课中我们一起学习了如何使用Java的`HashMap`来高效地统计文本文件中单词的出现频率。我们掌握了以下关键步骤：

*   **创建`HashMap`**：使用`HashMap<String, Integer>`来建立单词到计数的映射。
*   **填充映射**：通过遍历单词，使用`containsKey()`检查单词是否存在，并使用`put()`和`get()`方法来更新或添加计数。
*   **遍历输出**：使用`keySet()`遍历所有单词，并根据阈值筛选和输出结果。

![](img/5cdf7bebedbe945c6ddb4da5d89191ea_7.png)

![](img/5cdf7bebedbe945c6ddb4da5d89191ea_8.png)

通过将键映射到值，`HashMap`成为了解决此类计数问题的强大工具。随着你更多地使用映射来解决问题，你将成为编程的大师。享受编码的乐趣吧！