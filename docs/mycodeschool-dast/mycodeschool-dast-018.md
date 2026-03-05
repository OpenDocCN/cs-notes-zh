# 018：使用栈检查括号平衡性 🔍

![](img/f4cd63dafe8a5d075cd8592475fb40a6_1.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_2.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_3.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_4.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_6.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_7.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_9.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_11.png)

在本节课中，我们将学习如何使用栈（Stack）这一数据结构来解决一个经典问题：检查表达式中的括号（包括圆括号、花括号和方括号）是否平衡。这是编程面试中的一个常见问题，也是编译器进行语法检查的基础任务之一。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_13.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_14.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_16.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_18.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_19.png)

## 概述

![](img/f4cd63dafe8a5d075cd8592475fb40a6_20.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_22.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_24.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_26.png)

上一节我们介绍了栈的一个简单应用——反转列表或集合。本节中，我们将探讨另一个可以使用栈解决的著名问题：检查括号平衡性。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_28.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_29.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_31.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_33.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_34.png)

给定一个由常量、变量、运算符和括号组成的字符串表达式，我们需要编写一个程序来判断其中的括号是否平衡。这里的“括号”包括圆括号 `()`、花括号 `{}` 和方括号 `[]`。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_36.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_37.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_38.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_39.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_40.png)

一个表达式中的括号是“平衡”的，意味着每一个开括号都必须有一个对应的、顺序正确的闭括号与之匹配。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_42.png)

## 什么是平衡括号？ ⚖️

![](img/f4cd63dafe8a5d075cd8592475fb40a6_44.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_45.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_46.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_47.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_48.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_50.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_52.png)

以下是平衡括号的核心定义：
*   每个开括号（`(`, `{`, `[`）都必须有一个相同类型的闭括号（`)`, `}`, `]`）在其右侧与之匹配。
*   每个闭括号都必须有一个相同类型的开括号在其左侧与之匹配。
*   括号必须正确嵌套。后打开的左括号必须先闭合，这符合栈的 **后进先出（LIFO）** 特性。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_54.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_55.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_56.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_58.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_60.png)

**示例：**
*   `(A + B)` - 平衡
*   `{ [A + B] * (C - D) }` - 平衡
*   `(A + B` - 不平衡（缺少闭括号）
*   `[A + B) * (C - D]` - 不平衡（括号类型不匹配）
*   `{ (A + B) * (C - D)` - 不平衡（缺少闭花括号）

![](img/f4cd63dafe8a5d075cd8592475fb40a6_62.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_63.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_65.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_67.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_68.png)

编译器在解析我们编写的代码时，就会执行类似的检查以确保语法正确。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_69.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_71.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_73.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_75.png)

## 为什么简单的计数法行不通？ ❌

![](img/f4cd63dafe8a5d075cd8592475fb40a6_77.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_79.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_81.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_83.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_84.png)

一个直观的想法是分别统计三种开括号和闭括号的数量，如果各自相等，则括号平衡。但这种方法并不充分。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_86.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_87.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_88.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_89.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_90.png)

考虑表达式：`[ ( ] )`
*   开括号 `[` 和 `(` 各有一个。
*   闭括号 `]` 和 `)` 也各有一个。
*   数量相等，但该表达式**并不平衡**，因为方括号和圆括号的嵌套顺序错误。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_92.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_93.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_94.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_95.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_96.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_97.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_99.png)

因此，除了数量，**顺序**和**嵌套关系**也至关重要。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_101.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_102.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_103.png)

## 解决方案思路：使用栈 🧠

![](img/f4cd63dafe8a5d075cd8592475fb40a6_105.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_106.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_107.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_109.png)

解决问题的关键在于：当我们从左到右扫描表达式时，**最后一个未匹配的开括号，必须与接下来遇到的第一个闭括号匹配**。这正是栈（后进先出）的用武之地。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_111.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_113.png)

**算法步骤：**
1.  创建一个空栈。
2.  从左到右遍历表达式的每个字符。
3.  如果当前字符是开括号（`(`, `{`, `[`），则将其**压入（Push）**栈中。
4.  如果当前字符是闭括号（`)`, `}`, `]`），则：
    *   检查栈是否为空。如果为空，说明没有与之匹配的开括号，表达式不平衡。
    *   如果栈非空，则**弹出（Pop）**栈顶元素。
    *   检查弹出的开括号是否与当前闭括号类型相同。如果类型不同，表达式不平衡。
5.  遍历结束后，检查栈是否为空。
    *   如果栈为空，说明所有开括号都找到了匹配的闭括号，表达式**平衡**。
    *   如果栈非空，说明还有未匹配的开括号，表达式**不平衡**。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_114.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_115.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_116.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_117.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_118.png)

## 算法伪代码 📝

![](img/f4cd63dafe8a5d075cd8592475fb40a6_120.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_121.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_122.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_123.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_124.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_125.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_127.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_128.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_129.png)

以下是该算法的伪代码实现：

![](img/f4cd63dafe8a5d075cd8592475fb40a6_131.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_132.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_133.png)

```pseudocode
函数 checkBalancedParentheses(expression):
    n = expression的长度
    创建栈 S

    循环 i 从 0 到 n-1:
        字符 ch = expression[i]

        如果 ch 是开括号 ('(', '{', '['):
            将 ch 压入栈 S
        否则 如果 ch 是闭括号 (')', '}', ']'):
            如果 栈 S 为空:
                返回 false // 不平衡，闭括号没有匹配项
            否则:
                栈顶字符 topChar = 弹出栈 S
                如果 (ch 是 ')' 且 topChar 不是 '(') 或
                   (ch 是 '}' 且 topChar 不是 '{') 或
                   (ch 是 ']' 且 topChar 不是 '['):
                    返回 false // 不平衡，括号类型不匹配

    循环结束

    如果 栈 S 为空:
        返回 true // 平衡
    否则:
        返回 false // 不平衡，还有未匹配的开括号
```

![](img/f4cd63dafe8a5d075cd8592475fb40a6_135.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_136.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_137.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_138.png)

## 示例推演 📊

![](img/f4cd63dafe8a5d075cd8592475fb40a6_140.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_141.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_142.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_143.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_144.png)

让我们用算法推演一个平衡表达式 `{ [ ( ) ] }` 的过程。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_146.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_147.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_148.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_149.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_150.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_151.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_152.png)

| 步骤 | 当前字符 | 操作 | 栈内容 (底->顶) | 说明 |
| :--- | :--- | :--- | :--- | :--- |
| 1 | `{` | Push `{` | `{` | 开括号入栈 |
| 2 | `[` | Push `[` | `{` `[` | 开括号入栈 |
| 3 | `(` | Push `(` | `{` `[` `(` | 开括号入栈 |
| 4 | `)` | Pop, 匹配 `(` | `{` `[` | 闭括号与栈顶匹配，弹出 |
| 5 | `]` | Pop, 匹配 `[` | `{` | 闭括号与栈顶匹配，弹出 |
| 6 | `}` | Pop, 匹配 `{` | (空) | 闭括号与栈顶匹配，弹出 |
| 结束 | | 栈为空 | (空) | **表达式平衡** |

![](img/f4cd63dafe8a5d075cd8592475fb40a6_154.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_155.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_157.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_158.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_159.png)

## 总结

![](img/f4cd63dafe8a5d075cd8592475fb40a6_161.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_162.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_163.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_164.png)

本节课我们一起学习了如何使用栈来高效地检查表达式中的括号是否平衡。我们首先明确了“平衡括号”的定义，然后分析了简单计数法的缺陷，最后引出了基于栈的解决方案。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_166.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_167.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_169.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_171.png)

**核心要点：**
*   **问题**：检查字符串中 `()`, `{}`, `[]` 的匹配是否正确。
*   **数据结构**：**栈（Stack）**，利用其**后进先出（LIFO）** 的特性。
*   **算法核心**：遍历字符串，开括号入栈，遇到闭括号时检查栈顶元素是否与之匹配。
*   **判断条件**：最终栈为空且匹配过程中无错误，则括号平衡。

![](img/f4cd63dafe8a5d075cd8592475fb40a6_173.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_174.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_175.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_176.png)

![](img/f4cd63dafe8a5d075cd8592475fb40a6_178.png)

你可以尝试在你熟悉的编程语言中实现这个算法，并测试各种边界情况。在接下来的课程中，我们将继续探索栈的更多应用场景。