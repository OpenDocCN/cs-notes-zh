# 022：大O与Theta 🧮

![](img/fab48594dbaecf147b9624d58eff4fe6_0.png)

在本节课中，我们将学习如何分析程序的运行时间。我们将通过计时和计数操作两种方法来评估不同函数的性能，并最终引入“增长阶”的概念，特别是大O（Big O）和Theta（Θ）表示法，用于描述算法效率随输入规模增长的变化趋势。

---

![](img/fab48594dbaecf147b9624d58eff4fe6_2.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_4.png)

## 第一部分：程序计时 ⏱️

![](img/fab48594dbaecf147b9624d58eff4fe6_6.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_7.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_9.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_11.png)

上一讲我们开始讨论如何计算程序的运行时间。今天，我们将继续这一主题，首先通过计时来观察不同程序的性能。

![](img/fab48594dbaecf147b9624d58eff4fe6_13.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_14.png)

### 使用 `perf_counter` 进行精确计时

![](img/fab48594dbaecf147b9624d58eff4fe6_16.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_17.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_19.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_21.png)

为了更精确地测量时间，我们将使用 `time` 模块中的 `perf_counter` 函数，而不是上一讲使用的 `time` 函数。`perf_counter` 能提供更高的精度（例如，可达10⁻⁸秒级别），使我们能够测量那些运行时间极短的程序。

计时方法如下：
1.  调用 `perf_counter()` 获取开始时间。
2.  运行目标函数。
3.  再次调用 `perf_counter()` 获取结束时间。
4.  计算时间差 `dt = 结束时间 - 开始时间`。

以下是计时代码的基本结构：
```python
import time

start = time.perf_counter()
# 调用要计时的函数
stop = time.perf_counter()
dt = stop - start
print(f"运行时间: {dt} 秒")
```

### 分析示例函数

我们将分析两个函数，观察其运行时间如何随输入变化。

![](img/fab48594dbaecf147b9624d58eff4fe6_23.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_24.png)

#### 函数一：`convert_to_kilometers`

此函数将英里数转换为公里数。
```python
def convert_to_kilometers(miles):
    return miles * 1.60934
```

![](img/fab48594dbaecf147b9624d58eff4fe6_26.png)

**计时结果与观察：**
无论输入 `miles` 的值是多少（例如1, 10, 1000000），该函数的运行时间都基本恒定，大约在 3×10⁻⁷ 秒左右。这表明其运行时间与输入参数无关。

![](img/fab48594dbaecf147b9624d58eff4fe6_27.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_29.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_31.png)

#### 函数二：`compound`

此函数计算按月定投的复利收益，类似于问题集1中的内容。
```python
def compound(monthly_invest, monthly_rate, months):
    total = 0
    for month in range(months):
        total = (total + monthly_invest) * monthly_rate
    return total
```

我们分别测试改变三个参数（每月投资额 `monthly_invest`、月利率 `monthly_rate`、投资月数 `months`）对运行时间的影响。

**计时结果与观察：**
1.  改变 `monthly_invest` 或 `monthly_rate` 对运行时间几乎没有影响。
2.  改变 `months` 对运行时间有显著影响。当 `months` 增加10倍时，运行时间也大约增加10倍。
3.  当输入规模（`months`）很大时，这种线性增长关系更为明显和可预测。对于小规模输入，运行时间可能受计算机后台活动干扰而波动。

---

## 第二部分：处理列表作为输入的函数 📊

现在，我们来看输入为列表的函数。

### 函数三：`sum_of`

此函数计算列表中所有元素的总和。
```python
def sum_of(L):
    total = 0
    for i in L:
        total += i
    return total
```

为了测试，我们创建不同长度的列表（例如长度为1, 10, 100, 1000, ...），列表内容为虚拟数据（如0到n-1）。

**计时结果与观察：**
1.  函数的运行时间依赖于输入列表的长度 `len(L)`。
2.  当列表长度增加10倍时，运行时间也大约增加10倍，呈现线性关系。
3.  与 `compound` 函数类似，对于大规模输入，这种线性关系更稳定。对于小规模输入，由于系统干扰，可能出现反直觉的结果（例如，更长的列表运行时间更短）。
4.  在输入规模相当时（例如处理1亿个月或1亿个列表元素），`sum_of` 和 `compound` 函数的运行时间处于同一数量级（几秒）。这表明，尽管功能不同，但两者都包含一个遍历输入的循环，算法复杂度相似。

### 函数四：列表搜索算法比较

![](img/fab48594dbaecf147b9624d58eff4fe6_33.png)

我们比较三种在列表中查找元素的方法：
1.  **暴力搜索 (`is_in`)**：逐个检查列表元素。
    ```python
    def is_in(L, e):
        for i in L:
            if i == e:
                return True
        return False
    ```
2.  **二分查找 (`binary_search`)**：要求列表有序，每次比较后排除一半的搜索空间。
    ```python
    def binary_search(L, e):
        low = 0
        high = len(L) - 1
        while high >= low:
            mid = (low + high) // 2
            if L[mid] == e:
                return True
            elif L[mid] < e:
                low = mid + 1
            else:
                high = mid - 1
        return False
    ```
3.  **内置运算符 `in`**：直接使用 `e in L`。

为了公平比较，我们对每个函数测试三种情况（查找第一个元素、中间元素、最后一个元素）并取平均时间。

![](img/fab48594dbaecf147b9624d58eff4fe6_35.png)

**计时结果与观察：**
1.  **`is_in` (暴力搜索)** 和 **内置 `in`** 运算符都表现出线性关系：列表长度增加10倍，运行时间也增加约10倍。
2.  **`binary_search` (二分查找)** 的运行时间增长远低于线性。当输入增长10倍时，运行时间的增长倍数不固定（不是10倍）。其增长模式是对数级的。
3.  **性能对比**：
    *   二分查找比暴力搜索快数个数量级（例如，对于1亿长度的列表，暴力搜索需约1.6秒，而二分搜索仅需约10⁻⁵秒）。
    *   内置 `in` 运算符虽然也是线性复杂度，但比我们自己写的暴力搜索函数快约10倍，说明其实现更优化。

### 函数五：`diameter` (计算点集最大距离)

此函数计算二维平面上一组点中任意两点之间的最大距离。
```python
def diameter(points):
    max_dist = 0
    for i in range(len(points)):
        for j in range(i+1, len(points)):
            # 计算points[i]和points[j]之间的距离
            dist = ((points[i][0]-points[j][0])**2 + (points[i][1]-points[j][1])**2)**0.5
            if dist > max_dist:
                max_dist = dist
    return max_dist
```
该函数使用嵌套循环遍历所有不重复的点对。

**计时结果与观察：**
1.  该函数整体运行非常慢。对于约6000个点，运行时间已达14秒，而之前线性算法处理1亿数据也仅需几秒。
2.  运行时间与输入规模（点数 `n`）呈平方关系。当点数增加2倍时，运行时间增加约4倍；如果增加10倍，运行时间将增加约100倍。

![](img/fab48594dbaecf147b9624d58eff4fe6_37.png)

### 可视化运行时间趋势

![](img/fab48594dbaecf147b9624d58eff4fe6_39.png)

将上述函数的运行时间相对于输入规模绘图，可以清晰看到不同的增长趋势：
*   `is_in` 和内置 `in`：线性增长，图像为一条斜线。
*   `binary_search`：对数增长，图像初期上升较快，随后趋于平缓。
*   `diameter`：平方增长，图像为一条上升的曲线。

### 关于计时的总结

![](img/fab48594dbaecf147b9624d58eff4fe6_41.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_43.png)

*   **计时**能给出程序运行的实际时间，对于预估等待时间很重要。
*   运行时间受具体计算机硬件影响，在不同机器上结果不同。
*   然而，**运行时间随输入规模增长的相对关系（如线性、平方）在不同机器上是一致的**。这是我们分析算法效率的关键。

---

## 第三部分：计数操作 🔢

计时给出了实际时间，但计数操作能帮助我们建立输入规模与计算量之间的公式化关系。

### 计数方法

我们将各种基本操作（数学运算、比较、索引、赋值等）视为消耗一个“单位时间”。通过统计函数执行的基本操作次数，可以得到一个关于输入规模的表达式。

![](img/fab48594dbaecf147b9624d58eff4fe6_45.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_46.png)

#### 示例分析

![](img/fab48594dbaecf147b9624d58eff4fe6_48.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_49.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_50.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_52.png)

*   **`convert_to_kilometers`**：包含一次乘法和一次返回操作。操作数恒为2，与输入无关。公式：**操作数 = 2**。
*   **`sum_of`**：
    *   `total = 0`：1次赋值。
    *   `for i in L:`：循环 `len(L)` 次，每次包含1次索引取值和赋值给 `i`。
    *   `total += i`：每次循环包含1次加法 (`total + i`) 和1次赋值 (`total = ...`)。
    *   `return total`：1次返回。
    *   公式：**操作数 = 1 + len(L) * (1 + 2) + 1 = 3*len(L) + 2**。

![](img/fab48594dbaecf147b9624d58eff4fe6_54.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_55.png)

### 使用全局变量辅助计数

为了在函数内部计数，我们可以（仅用于调试和分析目的）使用全局变量。**注意：在实际编程中应避免使用全局变量**。

以下是给 `is_in` 函数添加计数器的示例：
```python
count = 0  # 全局计数器

def is_in(L, e):
    global count  # 声明使用全局变量count
    for i in L:
        count += 2  # 索引L[i]和比较 (i == e)
        if i == e:
            count += 1  # return操作
            return True
    count += 1  # return False操作
    return False
```
运行此函数并打印 `count`，可以验证操作次数与列表长度 `len(L)` 的线性关系。

对 `binary_search` 进行类似计数，并绘制“操作次数 vs 输入规模”图，会得到与计时相似的对数增长曲线。

### 计数与计时的关联

计数得到的公式（如 `3n+2`）和计时观察到的增长趋势（线性）是吻合的。计数为我们提供了理论依据。

![](img/fab48594dbaecf147b9624d58eff4fe6_57.png)

---

![](img/fab48594dbaecf147b9624d58eff4fe6_59.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_61.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_62.png)

## 第四部分：增长阶、大O与Theta表示法 📈

![](img/fab48594dbaecf147b9624d58eff4fe6_64.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_66.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_68.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_69.png)

我们分析了多个函数，发现它们的复杂度可以归类为几种基本类型：常数、线性、对数、平方等。为了在数学上简洁地描述这种随着输入增长的趋势，并专注于主要影响因素，我们引入**增长阶（Order of Growth）**的概念，并使用**大O (Big O)** 和 **Theta (Θ)** 表示法。

![](img/fab48594dbaecf147b9624d58eff4fe6_71.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_72.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_73.png)

### 核心思想

![](img/fab48594dbaecf147b9624d58eff4fe6_75.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_76.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_78.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_80.png)

*   当输入规模 `n` 变得非常大时，函数运行时间或操作数表达式中**增长最快的项**将主导整个增长趋势。
*   我们忽略常数系数和低阶项，只关注这个主导项与输入规模 `n` 的关系。

![](img/fab48594dbaecf147b9624d58eff4fe6_82.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_83.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_84.png)

### 大O (Big O) 表示法：上界

![](img/fab48594dbaecf147b9624d58eff4fe6_86.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_88.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_90.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_92.png)

大O定义了一个函数增长率的**上界（Upper Bound）**。形式化定义如下：

> 如果存在正常数 `c` 和 `n₀`，使得对于所有 `n > n₀`，都有 `f(n) ≤ c * g(n)`，则称 `f(n)` 是 `O(g(n))`。

**直观理解**：当 `n` 足够大后，函数 `f(n)` 的增长速度不会超过 `g(n)` 的某个常数倍。

**例子**：`f(n) = 3n² + 20n + 1`。当 `n` 很大时，`n²` 项占主导。我们可以找到 `c=4` 和某个 `n₀`，使得 `3n² + 20n + 1 ≤ 4n²` 对所有 `n > n₀` 成立。因此，`f(n)` 是 `O(n²)`。

![](img/fab48594dbaecf147b9624d58eff4fe6_94.png)

**注意**：一个函数的上界可以有很多。`f(n)=3n²+...` 也是 `O(n³)`, `O(2ⁿ)` 等，因为这些函数增长得更快。大O只保证“不超过”，但不一定“紧贴”。

![](img/fab48594dbaecf147b9624d58eff4fe6_96.png)

### Theta (Θ) 表示法：紧确界

Theta定义了一个函数增长率的**紧确界（Tight Bound）**，它同时是上界和下界。形式化定义如下：

> 如果存在正常数 `c₁`, `c₂` 和 `n₀`，使得对于所有 `n > n₀`，都有 `c₁ * g(n) ≤ f(n) ≤ c₂ * g(n)`，则称 `f(n)` 是 `Θ(g(n))`。

**直观理解**：当 `n` 足够大后，函数 `f(n)` 的增长速度与 `g(n)` 同阶，被夹在两个常数倍之间。

**例子**：对于 `f(n) = 3n² + 20n + 1`，我们可以找到 `c₁=2`, `c₂=4` 和某个 `n₀`，使得 `2n² ≤ 3n²+20n+1 ≤ 4n²` 对所有 `n > n₀` 成立。因此，`f(n)` 是 `Θ(n²)`。

![](img/fab48594dbaecf147b9624d58eff4fe6_98.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_100.png)

**关键**：Theta表示法描述的是增长的主要趋势，是我们通常用来描述算法复杂度的方式。它比大O更精确地反映了函数的增长阶。

### 如何确定Theta

确定一个函数 `f(n)` 的 Θ，只需：
1.  找出其关于输入规模 `n` 的表达式中的**最高阶项**。
2.  忽略该项的**常数系数**。

**示例**：
*   `f(n) = n² + 2n + 2` → **Θ(n²)**
*   `f(n) = 3x² + 100000x + 10¹⁰` → **Θ(x²)** （输入变量是 `x`）
*   `f(n) = 5a + 3` → **Θ(a)** （输入变量是 `a`）
*   `f(n) = 2ᵇ + a³`，输入为 `a` 和 `b` → **Θ(2ᵇ + a³)** （两个变量都影响）

![](img/fab48594dbaecf147b9624d58eff4fe6_102.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_103.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_105.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_107.png)

### 分析程序代码的复杂度

对于程序，我们通过分析循环结构来确定其 Θ。

![](img/fab48594dbaecf147b9624d58eff4fe6_109.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_110.png)

#### 法则一：相加（顺序结构）

![](img/fab48594dbaecf147b9624d58eff4fe6_112.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_113.png)

如果程序包含顺序执行的两个部分，其复杂度分别为 `Θ(f(n))` 和 `Θ(g(n))`，则总复杂度为 `Θ(f(n) + g(n))`，再化简为其中增长更快的项。

**示例**：
```python
for i in range(n):    # Θ(n)
    # 常数时间操作
for i in range(n):    # Θ(n²)，因为内层循环
    for j in range(n):
        # 常数时间操作
```
总复杂度：`Θ(n + n²) = Θ(n²)`。

![](img/fab48594dbaecf147b9624d58eff4fe6_115.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_116.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_118.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_120.png)

#### 法则二：相乘（嵌套结构）

![](img/fab48594dbaecf147b9624d58eff4fe6_122.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_124.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_125.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_126.png)

如果程序包含嵌套结构（如循环嵌套），外层复杂度为 `Θ(f(n))`，内层复杂度为 `Θ(g(n))`，则总复杂度为 `Θ(f(n) * g(n))`。

**示例**：
```python
for i in range(n):          # Θ(n)
    for j in range(i, n):   # 平均来看也是 Θ(n)
        # 常数时间操作
```
总复杂度：`Θ(n * n) = Θ(n²)`。

#### 应用示例

![](img/fab48594dbaecf147b9624d58eff4fe6_128.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_129.png)

1.  **线性搜索列表**：
    ```python
    def linear_search(L, e):
        for i in L:         # 循环 len(L) 次 → Θ(len(L))
            if i == e:      # 常数时间操作
                return True
        return False
    ```
    复杂度：**Θ(len(L))**。

![](img/fab48594dbaecf147b9624d58eff4fe6_131.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_133.png)

2.  **比较两个等长列表**：
    ```python
    def compare_lists(L1, L2):
        if len(L1) != len(L2):      # 常数时间
            return False
        for i in range(len(L1)):    # 循环 len(L1) 次 → Θ(len(L1))
            if L1[i] != L2[i]:      # 常数时间
                return False
        return True
    ```
    复杂度：`Θ(1) + Θ(len(L1)) = Θ(len(L1))`。

---

## 常见的复杂度类别

算法复杂度通常可以归类为以下几种常见类别（按效率从高到低排列）：
*   **常数时间**：Θ(1) - 运行时间与输入规模无关。
*   **对数时间**：Θ(log n) - 如二分查找。
*   **线性时间**：Θ(n) - 如遍历列表。
*   **线性对数时间**：Θ(n log n) - 许多高效排序算法（如归并排序）。
*   **多项式时间**：Θ(nᶜ)，其中c为常数。常见的有：
    *   平方时间：Θ(n²) - 如嵌套循环比较所有元素对。
    *   立方时间：Θ(n³)
*   **指数时间**：Θ(cⁿ)，其中c>1为常数。如穷举所有子集。这类算法在输入稍大时就变得不可行。

![](img/fab48594dbaecf147b9624d58eff4fe6_135.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_137.png)

在设计和分析算法时，我们应努力使算法复杂度尽可能位于列表的上方（更高效）。

![](img/fab48594dbaecf147b9624d58eff4fe6_139.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_141.png)

---

![](img/fab48594dbaecf147b9624d58eff4fe6_143.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_145.png)

## 总结 🎯

本节课中我们一起学习了：
1.  **程序计时**：使用 `perf_counter` 测量实际运行时间，观察了不同函数（如单位转换、复利计算、列表求和、搜索、最大距离计算）的运行时间如何随输入规模变化，识别出线性、对数、平方等增长模式。
2.  **操作计数**：通过统计基本操作次数，建立了输入规模与计算量之间的公式关系，从理论上验证了计时观察到的趋势。
3.  **增长阶与渐近表示法**：引入了大O (O) 和 Theta (Θ) 表示法。
    *   **大O** 描述算法运行时间的**上界**。
    *   **Theta** 描述算法运行时间的**紧确界**，是我们用于刻画算法复杂度的主要工具。
4.  **复杂度分析**：学习了如何通过分析代码结构（特别是循环）来确定算法的 Θ 复杂度，并介绍了常见复杂度类别。

![](img/fab48594dbaecf147b9624d58eff4fe6_147.png)

![](img/fab48594dbaecf147b9624d58eff4fe6_149.png)

掌握这些概念，你将能够预估算法的效率，并在设计程序时做出更明智的选择，避免编写出输入稍大就运行极慢的代码。下一讲我们将深入探讨更多不同复杂度类别的具体算法示例。