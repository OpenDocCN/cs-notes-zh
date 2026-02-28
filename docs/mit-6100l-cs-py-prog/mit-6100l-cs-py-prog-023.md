# 023：复杂度类别示例 📊

![](img/8d3f95150591a6e124fd3f887a14868a_0.png)

在本节课中，我们将学习如何分析代码并确定其复杂度类别。我们将回顾Θ表示法，并通过大量代码示例来识别不同复杂度类别的特征，包括常数、线性、多项式、对数和指数复杂度。

---

## 回顾：Θ表示法与复杂度分析

上一节我们介绍了Θ表示法，它用于标记特定函数或代码段的增长阶数。我们更倾向于使用Θ而不是大O表示法，因为Θ为我们提供了函数最坏情况运行时间的渐近上界。

给定一个函数，其Θ值将是该函数的主导项。如果有多个项，我们关注增长最快的那一项，并舍弃任何加法常数、乘法常数以及增长不如主导项快的其他项。

为了得到代码的Θ值，我们首先识别函数的输入参数，然后找出代码中所有依赖于这些输入参数的部分。这包括直接依赖（如遍历输入的循环）或间接依赖。

---

![](img/8d3f95150591a6e124fd3f887a14868a_2.png)

![](img/8d3f95150591a6e124fd3f887a14868a_4.png)

![](img/8d3f95150591a6e124fd3f887a14868a_6.png)

![](img/8d3f95150591a6e124fd3f887a14868a_7.png)

![](img/8d3f95150591a6e124fd3f887a14868a_9.png)

## 常见的复杂度类别

![](img/8d3f95150591a6e124fd3f887a14868a_11.png)

在上一讲的结尾，我们总结出了一些常见的算法复杂度类别。以下是这些类别，其中n代表输入规模：

*   **Θ(1)**：常数复杂度
*   **Θ(log n)**：对数复杂度
*   **Θ(n)**：线性复杂度
*   **Θ(n log n)**：线性对数复杂度
*   **Θ(nᶜ)**：多项式复杂度（c为常数，如n², n³）
*   **Θ(cⁿ)**：指数复杂度（c为常数，如2ⁿ, 3ⁿ）

![](img/8d3f95150591a6e124fd3f887a14868a_13.png)

![](img/8d3f95150591a6e124fd3f887a14868a_15.png)

我们的目标是编写属于前几个类别的算法。如果发现代码是指数级的，通常需要重新思考解决方案。

接下来，我们将通过具体代码示例来探索这些类别。

---

![](img/8d3f95150591a6e124fd3f887a14868a_17.png)

![](img/8d3f95150591a6e124fd3f887a14868a_19.png)

## 常数复杂度 Θ(1) ⏱️

![](img/8d3f95150591a6e124fd3f887a14868a_21.png)

![](img/8d3f95150591a6e124fd3f887a14868a_22.png)

![](img/8d3f95150591a6e124fd3f887a14868a_24.png)

如果代码属于常数复杂度类别，意味着其运行时间不依赖于输入规模。代码中可以有循环或递归结构，只要这些结构不依赖于输入即可。

![](img/8d3f95150591a6e124fd3f887a14868a_25.png)

一些内置操作是常数时间的，例如：
*   列表索引 `L[i]`
*   列表追加 `L.append(x)`
*   字典键值查找 `D[key]`

以下是常数复杂度的代码示例：

![](img/8d3f95150591a6e124fd3f887a14868a_27.png)

**示例1：简单加法**
```python
def add(x, y):
    return x + y
```
此函数没有循环或递归，复杂度为 **Θ(1)**。

![](img/8d3f95150591a6e124fd3f887a14868a_29.png)

![](img/8d3f95150591a6e124fd3f887a14868a_31.png)

**示例2：单位转换**
```python
def km_to_miles(km):
    return km * 0.621371
```
此函数仅进行一次乘法运算，复杂度为 **Θ(1)**。

![](img/8d3f95150591a6e124fd3f887a14868a_33.png)

**示例3：包含循环但不依赖输入**
```python
def add_x_to_100(x):
    total = 0
    for i in range(100):  # 循环次数固定为100，与输入x无关
        total += x
    return total
```
此函数虽然包含循环，但循环次数固定（100次），不随输入`x`变化，因此复杂度为 **Θ(1)**。

![](img/8d3f95150591a6e124fd3f887a14868a_35.png)

![](img/8d3f95150591a6e124fd3f887a14868a_36.png)

![](img/8d3f95150591a6e124fd3f887a14868a_38.png)

![](img/8d3f95150591a6e124fd3f887a14868a_39.png)

---

![](img/8d3f95150591a6e124fd3f887a14868a_41.png)

![](img/8d3f95150591a6e124fd3f887a14868a_42.png)

## 线性复杂度 Θ(n) 📈

线性复杂度的函数通常由一个或多个线性依赖于输入n的循环（或递归调用）构成。这些循环可以是串联的（使用加法法则）。

![](img/8d3f95150591a6e124fd3f887a14868a_44.png)

![](img/8d3f95150591a6e124fd3f887a14868a_45.png)

需要注意的是，一些内置操作是线性时间的，在分析时不能忽略：
*   检查元素是否在列表中 `e in L`
*   复制列表 `L.copy()` 或 `L[:]`
*   检查两个列表是否相等 `L1 == L2`
*   删除列表中的元素 `del L[i]`

![](img/8d3f95150591a6e124fd3f887a14868a_47.png)

![](img/8d3f95150591a6e124fd3f887a14868a_48.png)

![](img/8d3f95150591a6e124fd3f887a14868a_50.png)

以下是线性复杂度的代码示例：

![](img/8d3f95150591a6e124fd3f887a14868a_52.png)

![](img/8d3f95150591a6e124fd3f887a14868a_53.png)

![](img/8d3f95150591a6e124fd3f887a14868a_54.png)

![](img/8d3f95150591a6e124fd3f887a14868a_56.png)

![](img/8d3f95150591a6e124fd3f887a14868a_57.png)

**示例1：乘法（循环依赖一个输入）**
```python
def multiply(x, y):
    result = 0
    for i in range(y):  # 循环次数依赖于y
        result += x
    return result
```
此函数复杂度相对于`y`是 **Θ(y)**，相对于`x`是 **Θ(1)**。总体复杂度为 **Θ(y)**。

![](img/8d3f95150591a6e124fd3f887a14868a_59.png)

![](img/8d3f95150591a6e124fd3f887a14868a_60.png)

![](img/8d3f95150591a6e124fd3f887a14868a_62.png)

**示例2：字符串数字求和**
```python
def sum_digits(s):
    total = 0
    for c in s:          # 循环遍历字符串s的每个字符
        total += int(c)
    return total
```
此函数有一个循环，遍历输入字符串`s`的每个字符。运行时间取决于字符串的长度，因此复杂度为 **Θ(len(s))**。

![](img/8d3f95150591a6e124fd3f887a14868a_63.png)

![](img/8d3f95150591a6e124fd3f887a14868a_65.png)

![](img/8d3f95150591a6e124fd3f887a14868a_66.png)

![](img/8d3f95150591a6e124fd3f887a14868a_68.png)

![](img/8d3f95150591a6e124fd3f887a14868a_70.png)

**示例3：迭代计算阶乘**
```python
def factorial_iterative(n):
    result = 1
    for i in range(2, n+1):  # 循环n-1次
        result *= i
    return result
```
此函数有一个循环，从2迭代到n，循环次数线性依赖于`n`，因此复杂度为 **Θ(n)**。

![](img/8d3f95150591a6e124fd3f887a14868a_72.png)

![](img/8d3f95150591a6e124fd3f887a14868a_74.png)

![](img/8d3f95150591a6e124fd3f887a14868a_75.png)

![](img/8d3f95150591a6e124fd3f887a14868a_77.png)

![](img/8d3f95150591a6e124fd3f887a14868a_79.png)

![](img/8d3f95150591a6e124fd3f887a14868a_80.png)

**示例4：递归计算阶乘**
```python
def factorial_recursive(n):
    if n == 0:
        return 1
    else:
        return n * factorial_recursive(n-1)
```
对于递归函数，我们关注函数被调用的次数。此函数会递归调用自身n次，每次调用的开销是常数（减法操作），因此总体复杂度为 **Θ(n)**。

**示例5：复利计算**
```python
def compound(monthly_amt, monthly_rate, num_months):
    total = 0
    for m in range(num_months):  # 循环次数依赖于num_months
        total += monthly_amt
        total *= (1 + monthly_rate)
    return total
```
此函数有一个循环，迭代`num_months`次。循环内部的操作是常数时间。因此，复杂度为 **Θ(num_months)**。其他参数不影响复杂度。

![](img/8d3f95150591a6e124fd3f887a14868a_82.png)

![](img/8d3f95150591a6e124fd3f887a14868a_84.png)

**示例6：迭代计算斐波那契数**
```python
def fib_iterative(n):
    if n == 0 or n == 1:
        return n
    else:
        fib_i_minus_2 = 0
        fib_i_minus_1 = 1
        for i in range(2, n+1):  # 循环n-1次
            fib_i = fib_i_minus_1 + fib_i_minus_2
            fib_i_minus_2 = fib_i_minus_1
            fib_i_minus_1 = fib_i
        return fib_i
```
此函数有一个循环，迭代约n次。循环内部是常数时间操作。因此，复杂度为 **Θ(n)**。

![](img/8d3f95150591a6e124fd3f887a14868a_86.png)

![](img/8d3f95150591a6e124fd3f887a14868a_87.png)

![](img/8d3f95150591a6e124fd3f887a14868a_88.png)

![](img/8d3f95150591a6e124fd3f887a14868a_90.png)

---

![](img/8d3f95150591a6e124fd3f887a14868a_92.png)

![](img/8d3f95150591a6e124fd3f887a14868a_93.png)

![](img/8d3f95150591a6e124fd3f887a14868a_95.png)

## 多项式复杂度 Θ(nᶜ) 📊

![](img/8d3f95150591a6e124fd3f887a14868a_96.png)

多项式复杂度通常涉及嵌套循环。如果存在两个线性依赖于输入的嵌套循环，复杂度通常是Θ(n²)；如果是三个，则是Θ(n³)，依此类推。

以下是多项式复杂度的代码示例：

![](img/8d3f95150591a6e124fd3f887a14868a_98.png)

**示例1：简单嵌套循环**
```python
def g(n):
    total = 0
    for i in range(n):       # 外层循环 Θ(n)
        for j in range(n):   # 内层循环 Θ(n)
            total += i * j
    return total
```
外层循环迭代n次，内层循环也为每次外层迭代迭代n次。根据乘法法则，总体复杂度为 **Θ(n) * Θ(n) = Θ(n²)**。

![](img/8d3f95150591a6e124fd3f887a14868a_100.png)

**示例2：判断子集**
```python
def is_subset(L1, L2):
    """假设L1和L2是列表。如果L1的每个元素都在L2中，则返回True，否则返回False。"""
    for e1 in L1:                # 外层循环 Θ(len(L1))
        matched = False
        for e2 in L2:            # 内层循环 Θ(len(L2))
            if e1 == e2:
                matched = True
                break
        if not matched:
            return False
    return True
```
此函数检查L1是否为L2的子集。外层循环遍历L1，内层循环（在最坏情况下）遍历整个L2。根据乘法法则，复杂度为 **Θ(len(L1) * len(L2))**。如果L1和L2长度相同（设为n），则复杂度为 **Θ(n²)**。

![](img/8d3f95150591a6e124fd3f887a14868a_102.png)

**示例3：求列表交集（保留唯一值）**
```python
def intersect(L1, L2):
    """假设L1和L2是列表。返回一个列表，包含同时出现在L1和L2中的元素（无重复）。"""
    # 构建包含所有共同元素的临时列表（可能有重复）
    tmp = []
    for e1 in L1:                # 外层循环 Θ(len(L1))
        for e2 in L2:            # 内层循环 Θ(len(L2))
            if e1 == e2:
                tmp.append(e1)
                break
    # 从临时列表中提取唯一元素
    result = []
    for e in tmp:                # 遍历tmp，最坏情况大小为 len(L1)*len(L2)
        if e not in result:      # 检查e是否在result中，最坏情况为Θ(len(result))
            result.append(e)
    return result
```
此函数分为两部分：
1.  第一部分是嵌套循环，用于找到所有共同元素（可能重复），复杂度为 **Θ(len(L1) * len(L2))**。
2.  第二部分遍历临时列表`tmp`（在最坏情况下，其大小为`len(L1)*len(L2)`），并为每个元素检查是否已在结果列表中（这也是一个线性检查）。因此，第二部分的复杂度在最坏情况下也是 **Θ(len(L1) * len(L2))**。

![](img/8d3f95150591a6e124fd3f887a14868a_104.png)

![](img/8d3f95150591a6e124fd3f887a14868a_106.png)

总体复杂度为两部分之和，即 **Θ(len(L1) * len(L2))**。

![](img/8d3f95150591a6e124fd3f887a14868a_108.png)

![](img/8d3f95150591a6e124fd3f887a14868a_110.png)

![](img/8d3f95150591a6e124fd3f887a14868a_111.png)

**示例4：计算点集直径**
```python
def diameter(points):
    """假设points是(x, y)坐标对的列表。返回任意两点之间的最大距离。"""
    max_dist = 0
    for i in range(len(points)):          # 外层循环 Θ(len(points))
        for j in range(i+1, len(points)): # 内层循环，平均约 Θ(len(points)/2)
            dist = ((points[i][0] - points[j][0])**2 +
                    (points[i][1] - points[j][1])**2)**0.5
            if dist > max_dist:
                max_dist = dist
    return max_dist
```
外层循环遍历列表`points`的每个索引。内层循环从`i+1`开始，到列表末尾结束。内层循环的迭代次数不是固定的n，而是从n-1, n-2, ..., 1递减。其总和约为n(n-1)/2，这仍然是 **Θ(n²)**。因此，总体复杂度为 **Θ(n²)**，其中n是`points`的长度。

![](img/8d3f95150591a6e124fd3f887a14868a_113.png)

![](img/8d3f95150591a6e124fd3f887a14868a_115.png)

---

![](img/8d3f95150591a6e124fd3f887a14868a_117.png)

![](img/8d3f95150591a6e124fd3f887a14868a_119.png)

![](img/8d3f95150591a6e124fd3f887a14868a_120.png)

![](img/8d3f95150591a6e124fd3f887a14868a_122.png)

![](img/8d3f95150591a6e124fd3f887a14868a_123.png)

![](img/8d3f95150591a6e124fd3f887a14868a_125.png)

## 指数复杂度 Θ(cⁿ) 🚀

指数复杂度增长非常迅速，我们应尽量避免编写此类算法。然而，有些问题本质上就需要指数级的时间来解决。

![](img/8d3f95150591a6e124fd3f887a14868a_127.png)

![](img/8d3f95150591a6e124fd3f887a14868a_128.png)

**示例1：递归计算斐波那契数**
```python
def fib_recursive(n):
    if n == 0 or n == 1:
        return n
    else:
        return fib_recursive(n-1) + fib_recursive(n-2)
```
此递归版本的斐波那契函数会生成一个递归调用树。每个调用（除了叶子节点）会产生两个新的递归调用。因此，总的函数调用次数大约是2ⁿ量级，复杂度为 **Θ(2ⁿ)**。

**示例2：生成列表的所有子集**
```python
def gen_subsets(L):
    """假设L是列表。返回一个包含L所有子集的列表。"""
    if len(L) == 0:
        return [[]]  # 空列表的唯一子集是空列表本身
    else:
        extra = L[-1:]          # 获取最后一个元素
        smaller = gen_subsets(L[:-1])  # 递归生成不包含最后一个元素的所有子集
        new = []
        for small in smaller:   # 遍历smaller中的每个子集
            new.append(small + extra) # 将最后一个元素添加到每个子集中，形成新的子集
        return smaller + new    # 合并原有子集和新子集
```
此递归函数生成列表L的所有子集。分析其复杂度：
1.  **递归调用次数**：函数会递归调用自身n次（每次列表长度减1），直到基例。
2.  **每次调用的开销**：在每次递归调用中，有一个循环遍历`smaller`列表（即前一步生成的所有子集），并将`extra`元素添加到每个子集中。`smaller`列表的大小随着递归深度指数增长（第k层约有2ᵏ个子集）。此外，`small + extra`操作涉及列表复制，其开销与子集大小成线性关系。

![](img/8d3f95150591a6e124fd3f887a14868a_130.png)

![](img/8d3f95150591a6e124fd3f887a14868a_132.png)

![](img/8d3f95150591a6e124fd3f887a14868a_134.png)

综合来看，总工作量大致为 **Θ(n * 2ⁿ)**，这比纯指数级更差。

![](img/8d3f95150591a6e124fd3f887a14868a_136.png)

![](img/8d3f95150591a6e124fd3f887a14868a_138.png)

![](img/8d3f95150591a6e124fd3f887a14868a_140.png)

---

## 对数复杂度 Θ(log n) 📉

对数复杂度通常出现在每次迭代都将问题规模除以一个常数的算法中，例如二分搜索。这种依赖关系可能不像线性循环那样直接。

**示例：数字各位求和（通过字符串转换）**
```python
def digit_sum_str(n):
    """假设n是非负整数。返回n的各位数字之和。"""
    total = 0
    s = str(n)               # 将整数转换为字符串
    for c in s:              # 遍历字符串的每个字符
        total += int(c)
    return total
```
此函数遍历字符串`s`的每个字符，因此复杂度相对于字符串长度是线性的，即 **Θ(len(s))**。但输入是整数`n`，字符串长度`len(s)`与`n`的关系是什么？`len(s)`实际上是`n`的位数，约等于 **log₁₀ n**。因此，该函数的复杂度为 **Θ(log n)**。在复杂度分析中，我们通常忽略对数的底数。

![](img/8d3f95150591a6e124fd3f887a14868a_142.png)

---

![](img/8d3f95150591a6e124fd3f887a14868a_144.png)

![](img/8d3f95150591a6e124fd3f887a14868a_145.png)

![](img/8d3f95150591a6e124fd3f887a14868a_146.png)

![](img/8d3f95150591a6e124fd3f887a14868a_148.png)

![](img/8d3f95150591a6e124fd3f887a14868a_149.png)

![](img/8d3f95150591a6e124fd3f887a14868a_150.png)

![](img/8d3f95150591a6e124fd3f887a14868a_152.png)

![](img/8d3f95150591a6e124fd3f887a14868a_154.png)

## 搜索算法复杂度分析 🔍

![](img/8d3f95150591a6e124fd3f887a14868a_156.png)

![](img/8d3f95150591a6e124fd3f887a14868a_158.png)

![](img/8d3f95150591a6e124fd3f887a14868a_160.png)

上一节我们介绍了Θ表示法和复杂度类别。本节中，我们来看看搜索算法的具体复杂度分析，比较线性搜索和二分搜索。

![](img/8d3f95150591a6e124fd3f887a14868a_161.png)

![](img/8d3f95150591a6e124fd3f887a14868a_162.png)

### 线性搜索

![](img/8d3f95150591a6e124fd3f887a14868a_164.png)

**1. 无序列表的线性搜索**
```python
def linear_search_unsorted(L, e):
    found = False
    for i in range(len(L)):  # 循环 Θ(len(L)) 次
        if L[i] == e:
            found = True
    return found
```
在最坏情况下（元素不存在），需要遍历整个列表，复杂度为 **Θ(len(L))**。

![](img/8d3f95150591a6e124fd3f887a14868a_166.png)

**2. 优化版（提前返回）**
```python
def linear_search_unsorted_early(L, e):
    for i in range(len(L)):  # 循环 Θ(len(L)) 次
        if L[i] == e:
            return True
    return False
```
尽管找到元素时可以提前返回，但在最坏情况下（元素不存在），仍然需要遍历整个列表，因此最坏情况复杂度仍为 **Θ(len(L))**。

**3. 有序列表的线性搜索（提前终止）**
```python
def linear_search_sorted(L, e):
    for i in range(len(L)):  # 循环 Θ(len(L)) 次
        if L[i] == e:
            return True
        if L[i] > e:         # 利用有序性提前终止
            return False
    return False
```
即使列表有序，可以在遇到大于目标元素的元素时提前终止，但在最坏情况下（目标元素大于所有列表元素或不存在），仍然需要遍历整个列表。因此，最坏情况复杂度仍为 **Θ(len(L))**。

### 二分搜索（折半搜索）

二分搜索要求列表是有序的。其基本思想是：比较中间元素与目标值，如果相等则找到；如果目标值更小，则在左半部分继续搜索；否则在右半部分继续搜索。每次比较都将搜索范围减半。

**复杂度推导**：
假设列表长度为n。每次递归调用后，问题规模减半。设需要k次递归调用（或迭代）才能将规模降至1（即找到元素或确定不存在）。则有：
n / 2ᵏ ≈ 1 => 2ᵏ ≈ n => k ≈ log₂ n
因此，二分搜索的复杂度为 **Θ(log n)**。

![](img/8d3f95150591a6e124fd3f887a14868a_168.png)

![](img/8d3f95150591a6e124fd3f887a14868a_170.png)

**1. 二分搜索实现（复制列表）**
```python
def bisect_search_copy(L, e):
    if L == []:
        return False
    elif len(L) == 1:
        return L[0] == e
    else:
        half = len(L) // 2
        if L[half] > e:
            return bisect_search_copy(L[:half], e)  # 复制左半部分列表
        else:
            return bisect_search_copy(L[half:], e)  # 复制右半部分列表
```
此实现虽然递归深度是Θ(log n)，但每次递归调用都通过切片`L[:half]`或`L[half:]`复制了列表的一部分。复制列表的操作是线性时间Θ(k)（k为切片长度）。总复制开销大致为n + n/2 + n/4 + ... ≈ 2n，即Θ(n)。因此，总体复杂度为 **Θ(n)**（由于复制）而不是Θ(log n)。

**2. 二分搜索实现（使用索引，避免复制）**
```python
def bisect_search(L, e):
    def bisect_search_helper(L, e, low, high):
        if high == low:  # 搜索范围缩小到单个元素
            return L[low] == e
        mid = (low + high) // 2
        if L[mid] == e:
            return True
        elif L[mid] > e:
            if low == mid: # 没有元素可搜索了
                return False
            else:
                return bisect_search_helper(L, e, low, mid - 1)
        else:
            return bisect_search_helper(L, e, mid + 1, high)
    if len(L) == 0:
        return False
    else:
        return bisect_search_helper(L, e, 0, len(L) - 1)
```
此实现通过传递索引`low`和`high`来界定搜索范围，避免了列表复制。每次递归调用只进行常数时间的操作（计算中点、比较）。因此，真正的二分搜索复杂度得以实现，为 **Θ(log n)**。

![](img/8d3f95150591a6e124fd3f887a14868a_172.png)

![](img/8d3f95150591a6e124fd3f887a14868a_173.png)

### 何时使用二分搜索？

二分搜索（Θ(log n)）比线性搜索（Θ(n)）快得多，但前提是列表必须有序。那么，对于一个无序列表，是先排序再二分搜索，还是直接线性搜索更划算？

![](img/8d3f95150591a6e124fd3f887a14868a_175.png)

考虑对无序列表进行一次搜索：
*   **方案A（排序+二分搜索）**：排序至少需要Θ(n log n)时间，加上二分搜索Θ(log n)，总时间 ≈ Θ(n log n)。
*   **方案B（线性搜索）**：需要Θ(n)时间。

![](img/8d3f95150591a6e124fd3f887a14868a_177.png)

![](img/8d3f95150591a6e124fd3f887a14868a_179.png)

![](img/8d3f95150591a6e124fd3f887a14868a_181.png)

显然，对于单次搜索，Θ(n) < Θ(n log n)，**直接线性搜索更快**。

但是，如果我们需要对同一个数据集进行k次搜索：
*   **方案A**：排序一次Θ(n log n)，然后k次二分搜索Θ(k log n)。总时间 ≈ Θ(n log n + k log n)。
*   **方案B**：k次线性搜索Θ(k n)。

当k很大时，方案A可能更优，因为排序的一次性成本被分摊了。具体来说，当 **k >> log n** 时，方案A更具优势。

![](img/8d3f95150591a6e124fd3f887a14868a_183.png)

![](img/8d3f95150591a6e124fd3f887a14868a_184.png)

---

![](img/8d3f95150591a6e124fd3f887a14868a_186.png)

![](img/8d3f95150591a6e124fd3f887a14868a_188.png)

## 总结 📝

![](img/8d3f95150591a6e124fd3f887a14868a_190.png)

![](img/8d3f95150591a6e124fd3f887a14868a_191.png)

本节课中，我们一起学习了如何分析代码的复杂度并将其归类到不同的复杂度类别中。我们通过大量示例探讨了：

*   **常数复杂度 Θ(1)**：运行时间不依赖于输入规模。
*   **线性复杂度 Θ(n)**：通常包含单个线性循环或递归。
*   **多项式复杂度 Θ(nᶜ)**：通常由嵌套循环导致。
*   **指数复杂度 Θ(cⁿ)**：通常出现在递归调用产生分支的算法中，应尽量避免。
*   **对数复杂度 Θ(log n)**：通常出现在每次迭代将问题规模除以常数的算法中，如二分搜索。

![](img/8d3f95150591a6e124fd3f887a14868a_193.png)

![](img/8d3f95150591a6e124fd3f887a14868a_195.png)

我们还重点比较了线性搜索和二分搜索的复杂度，并讨论了在无序列表上何时使用二分搜索是合理的。理解这些复杂度类别有助于我们评估算法效率，并指导我们选择或设计更优的算法。下一讲，我们将探讨各种排序算法。