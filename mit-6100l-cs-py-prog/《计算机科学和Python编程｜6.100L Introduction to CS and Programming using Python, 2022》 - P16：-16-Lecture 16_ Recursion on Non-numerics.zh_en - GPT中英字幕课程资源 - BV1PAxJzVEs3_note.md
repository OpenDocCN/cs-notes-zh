# 计算机科学和Python编程：16：非数值递归 🧮➡️📋

![](img/4d2ae59e3beb8d01b12549e1935775a3_0.png)

在本节课中，我们将要学习递归在非数值数据上的应用，特别是列表。我们将从回顾数值递归开始，然后深入探讨如何将递归思想应用于列表操作，例如求和、查找元素、展平列表和深度反转列表。

![](img/4d2ae59e3beb8d01b12549e1935775a3_2.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_3.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_5.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_6.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_8.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_10.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_12.png)

## 数值递归回顾 🔄

![](img/4d2ae59e3beb8d01b12549e1935775a3_13.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_15.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_17.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_18.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_19.png)

上一节我们介绍了递归的基本思想，本节中我们来看看如何将其应用于斐波那契数列和篮球得分问题。

![](img/4d2ae59e3beb8d01b12549e1935775a3_21.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_22.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_23.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_25.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_26.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_28.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_30.png)

### 斐波那契数列

![](img/4d2ae59e3beb8d01b12549e1935775a3_32.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_34.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_35.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_36.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_38.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_40.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_41.png)

斐波那契数列的数学定义如下：
*   **基础情况**：`fib(1) = 1`, `fib(2) = 1`
*   **递归步骤**：`fib(n) = fib(n-1) + fib(n-2)`

![](img/4d2ae59e3beb8d01b12549e1935775a3_43.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_44.png)

对应的Python递归函数如下：

![](img/4d2ae59e3beb8d01b12549e1935775a3_46.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_48.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_49.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_51.png)

```python
def fib(x):
    if x == 1 or x == 2:
        return 1
    else:
        return fib(x-1) + fib(x-2)
```

![](img/4d2ae59e3beb8d01b12549e1935775a3_53.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_55.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_57.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_58.png)

然而，这种实现效率低下，因为它会重复计算许多子问题。例如，计算 `fib(6)` 时，`fib(3)` 被计算了多次。

![](img/4d2ae59e3beb8d01b12549e1935775a3_60.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_61.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_63.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_64.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_66.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_67.png)

为了提高效率，我们可以使用**记忆化**技术，即用一个字典来存储已经计算过的结果。

![](img/4d2ae59e3beb8d01b12549e1935775a3_69.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_70.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_72.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_73.png)

```python
def fib_efficient(n, d):
    if n in d:
        return d[n]
    else:
        ans = fib_efficient(n-1, d) + fib_efficient(n-2, d)
        d[n] = ans
        return ans

![](img/4d2ae59e3beb8d01b12549e1935775a3_75.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_77.png)

# 初始化字典，包含基础情况
d = {1:1, 2:1}
print(fib_efficient(6, d))
```

使用记忆化后，计算 `fib(34)` 的函数调用次数从约1150万次减少到仅65次，极大地提升了性能。

### 篮球得分问题 🏀

问题：篮球得分可以是1分、2分或3分。给定一个总分 `x`，计算有多少种不同的得分组合方式。

![](img/4d2ae59e3beb8d01b12549e1935775a3_79.png)

以下是递归思路：
*   **基础情况**：
    *   `score(1) = 1` (仅一种方式：得1分)
    *   `score(2) = 2` (两种方式：1+1 或 2)
    *   `score(3) = 4` (四种方式：1+1+1, 1+2, 2+1, 3)
*   **递归步骤**：要得到总分 `x`，最后一步可以是得1分、2分或3分。因此，`score(x) = score(x-1) + score(x-2) + score(x-3)`。

![](img/4d2ae59e3beb8d01b12549e1935775a3_80.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_81.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_82.png)

对应的Python函数如下：

```python
def score_count(x):
    if x == 1:
        return 1
    elif x == 2:
        return 2
    elif x == 3:
        return 4
    else:
        return score_count(x-1) + score_count(x-2) + score_count(x-3)
```

![](img/4d2ae59e3beb8d01b12549e1935775a3_84.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_85.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_87.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_89.png)

同样，这个函数也存在重复计算的问题，你可以尝试为其添加记忆化功能来优化。

![](img/4d2ae59e3beb8d01b12549e1935775a3_91.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_92.png)

## 列表上的递归 📋

现在，我们将递归思想应用于列表。列表具有天然的递归结构：一个列表可以看作是它的第一个元素与剩余元素组成的子列表的组合。

![](img/4d2ae59e3beb8d01b12549e1935775a3_94.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_96.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_98.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_100.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_102.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_104.png)

### 递归求列表元素和

![](img/4d2ae59e3beb8d01b12549e1935775a3_106.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_107.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_109.png)

**问题**：计算一个列表中所有数字元素的和。

![](img/4d2ae59e3beb8d01b12549e1935775a3_111.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_113.png)

**递归思路**：
*   **基础情况**：如果列表只有一个元素，和就是这个元素的值。
*   **递归步骤**：列表的总和 = 第一个元素 + 剩余列表的总和。

```python
def total_recur(L):
    if len(L) == 1:
        return L[0]
    else:
        return L[0] + total_recur(L[1:])
```

![](img/4d2ae59e3beb8d01b12549e1935775a3_115.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_117.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_119.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_120.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_122.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_123.png)

**练习**：修改上述函数，计算列表中所有**字符串元素**的长度之和。
提示：基础情况返回 `len(L[0])`，递归步骤类似。

![](img/4d2ae59e3beb8d01b12549e1935775a3_125.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_127.png)

### 递归检查元素是否在列表中

![](img/4d2ae59e3beb8d01b12549e1935775a3_129.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_130.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_132.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_134.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_135.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_137.png)

**问题**：检查一个元素 `e` 是否存在于列表 `L` 中。

![](img/4d2ae59e3beb8d01b12549e1935775a3_139.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_141.png)

**递归思路**：
*   **基础情况**：如果列表为空，返回 `False`。如果列表只有一个元素，检查该元素是否等于 `e`。
*   **递归步骤**：如果第一个元素等于 `e`，返回 `True`；否则，在剩余列表中递归查找。

![](img/4d2ae59e3beb8d01b12549e1935775a3_143.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_144.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_146.png)

```python
def in_list(L, e):
    if len(L) == 0:
        return False
    elif L[0] == e:
        return True
    else:
        return in_list(L[1:], e)
```

![](img/4d2ae59e3beb8d01b12549e1935775a3_148.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_150.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_151.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_153.png)

**重要原则**：递归函数中所有的 `return` 语句必须返回**相同类型**的值。在这个例子中，所有返回都是布尔值 (`True`/`False`)。

![](img/4d2ae59e3beb8d01b12549e1935775a3_155.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_157.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_158.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_160.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_162.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_163.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_165.png)

### 递归展平列表

![](img/4d2ae59e3beb8d01b12549e1935775a3_166.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_168.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_170.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_171.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_173.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_175.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_177.png)

**问题**：给定一个列表，其元素也是列表（仅一层嵌套），将其“展平”，即移除嵌套，将所有子列表的元素提取到顶层。

![](img/4d2ae59e3beb8d01b12549e1935775a3_179.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_181.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_183.png)

例如：`[[1,2], [3,4], [9,8,7]]` 展平后为 `[1, 2, 3, 4, 9, 8, 7]`。

**递归思路**：
*   **基础情况**：如果列表只有一个元素（该元素是一个子列表），直接返回这个子列表 `L[0]`。
*   **递归步骤**：将第一个子列表与展平后的剩余列表连接起来。

```python
def flatten(L):
    if len(L) == 1:
        return L[0]
    else:
        return L[0] + flatten(L[1:])
```

**练习**：编写递归函数 `in_lists_of_lists(L, e)`，检查元素 `e` 是否存在于一个由子列表构成的列表 `L` 的**任何子列表**中。
提示：基础情况检查 `e in L[0]`；递归步骤中，如果 `e` 不在第一个子列表，则在剩余部分递归查找。

## 深度递归：处理嵌套列表 🔍

当列表包含多层嵌套时（列表中的列表，其中还可以有列表），迭代方法会变得复杂，而递归则能优雅地处理。

![](img/4d2ae59e3beb8d01b12549e1935775a3_185.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_187.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_189.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_191.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_192.png)

### 深度反转列表

![](img/4d2ae59e3beb8d01b12549e1935775a3_194.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_196.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_198.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_200.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_202.png)

**问题**：完全反转一个列表及其所有嵌套子列表中的元素顺序。

![](img/4d2ae59e3beb8d01b12549e1935775a3_204.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_205.png)

例如：深度反转 `[1, [2, 3], [4, [5, 6]]]` 应该得到 `[[[6, 5], 4], [3, 2], 1]`。

![](img/4d2ae59e3beb8d01b12549e1935775a3_207.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_209.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_211.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_212.png)

**递归思路**：我们需要区分当前处理的元素是普通值还是另一个列表。
*   **基础情况**：如果列表长度为1。
    *   如果这个唯一元素**不是**列表，则列表已反转，直接返回 `[元素]`。
    *   如果这个唯一元素**是**列表，则需要先深度反转这个子列表，然后返回结果。
*   **递归步骤**：列表有多个元素。
    *   提取第一个元素 `first`。
    *   对剩余列表 `L[1:]` 进行深度反转，得到 `reversed_rest`。
    *   如果 `first` 是列表，则先深度反转 `first`，然后将结果附加到 `reversed_rest` 的末尾。
    *   如果 `first` 不是列表，则直接将 `[first]` 附加到 `reversed_rest` 的末尾。

```python
def deep_reverse(L):
    if len(L) == 0:
        return []
    elif len(L) == 1:
        # 基础情况：只有一个元素
        if isinstance(L[0], list):
            # 如果它是列表，深度反转它
            return [deep_reverse(L[0])]
        else:
            # 如果它不是列表，直接返回它（包装在列表中）
            return [L[0]]
    else:
        # 递归步骤：多个元素
        first = L[0]
        rest = L[1:]
        reversed_rest = deep_reverse(rest)
        if isinstance(first, list):
            # 如果第一个元素是列表，深度反转它后再拼接
            return reversed_rest + [deep_reverse(first)]
        else:
            # 如果第一个元素不是列表，直接拼接
            return reversed_rest + [first]
```

![](img/4d2ae59e3beb8d01b12549e1935775a3_214.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_216.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_218.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_220.png)

这个函数的核心思想是：**在递归的每一层，不仅反转当前层的顺序，还要求任何是列表的元素也进行自我深度反转**。

![](img/4d2ae59e3beb8d01b12549e1935775a3_222.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_224.png)

## 何时使用递归？ 🤔

在以下情况，递归通常是更优或更直观的选择：
1.  **数据结构本身是递归的**：例如文件目录树、嵌套列表、语法树等。
2.  **问题可以自然地分解为相同的子问题**：例如分治算法（归并排序、快速排序）、遍历树或图。
3.  **迭代解决方案需要复杂的状态管理或嵌套循环**，而递归能提供更清晰、更简洁的描述。

![](img/4d2ae59e3beb8d01b12549e1935775a3_226.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_227.png)

## 总结 📝

![](img/4d2ae59e3beb8d01b12549e1935775a3_229.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_230.png)

本节课中我们一起学习了：
1.  **递归的核心模式**：定义基础情况（直接有解的问题）和递归步骤（将问题分解为更小的同类问题）。
2.  **记忆化**：使用字典存储已计算结果，避免重复计算，显著提升递归函数效率（如斐波那契数列）。
3.  **将递归应用于列表**：通过“第一个元素 + 剩余列表”的模式，我们实现了对列表的求和、查找、展平等操作。
4.  **深度递归**：处理嵌套数据结构（如多层列表）时，递归能够简洁地描述“深入每一层进行处理”的逻辑，例如深度反转列表。
5.  **递归函数的设计原则**：确保所有分支返回相同数据类型；可以从清晰（即使冗余）的逻辑开始，再逐步优化简化。

![](img/4d2ae59e3beb8d01b12549e1935775a3_232.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_233.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_234.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_236.png)

![](img/4d2ae59e3beb8d01b12549e1935775a3_237.png)

递归是一种强大的编程范式，它允许我们用简洁的代码描述复杂的重复性结构。掌握递归的关键在于练习识别问题的递归结构并信任函数能正确解决更小的子问题。