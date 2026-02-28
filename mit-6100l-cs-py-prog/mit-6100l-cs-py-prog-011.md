# 011：别名与克隆 🧬

![](img/efad76c3e8c4490c462d988e1439ac55_0.png)

在本节课中，我们将要学习列表的可变性、如何创建列表的副本（克隆），以及多个变量如何指向同一个列表对象（别名）。我们还将探讨在遍历列表时修改列表可能带来的陷阱，并学习如何避免这些问题。

![](img/efad76c3e8c4490c462d988e1439ac55_2.png)

![](img/efad76c3e8c4490c462d988e1439ac55_3.png)

![](img/efad76c3e8c4490c462d988e1439ac55_5.png)

---

![](img/efad76c3e8c4490c462d988e1439ac55_6.png)

![](img/efad76c3e8c4490c462d988e1439ac55_8.png)

![](img/efad76c3e8c4490c462d988e1439ac55_9.png)

## 列表与可变性

![](img/efad76c3e8c4490c462d988e1439ac55_11.png)

![](img/efad76c3e8c4490c462d988e1439ac55_12.png)

上一节我们介绍了列表作为可变数据结构的概念。本节中，我们来看看如何创建列表的副本，以及为什么有时需要这样做。

![](img/efad76c3e8c4490c462d988e1439ac55_14.png)

![](img/efad76c3e8c4490c462d988e1439ac55_16.png)

有时，直接修改原始列表会带来不便，或者我们希望保留原始数据的同时操作一个副本。Python允许我们创建列表的副本。

创建列表副本的语法如下：

![](img/efad76c3e8c4490c462d988e1439ac55_18.png)

![](img/efad76c3e8c4490c462d988e1439ac55_19.png)

```python
L_copy = L[:]
```

这行代码会创建一个名为 `L_copy` 的新列表对象，其元素与列表 `L` 完全相同。

### 内存中的副本

假设我们有以下代码：

```python
L_original = [4, 5, 6]
L_new = L_original[:]
```

在内存中，现在存在两个独立的列表对象，分别由 `L_original` 和 `L_new` 引用。修改其中一个列表不会影响另一个。

---

## 练习：原地移除所有匹配元素

现在，我们来练习编写一个函数，它不创建新列表，而是直接修改（突变）传入的列表。

任务是编写一个名为 `remove_all` 的函数。它接收一个列表 `L` 和一个元素 `E`，并**原地**修改 `L`，移除其中所有值等于 `E` 的元素。

以下是实现此功能的一种方法：

1.  首先，创建列表 `L` 的一个副本。
2.  然后，清空原始列表 `L`。
3.  最后，遍历副本，将所有不等于 `E` 的元素添加回 `L` 中。

```python
def remove_all(L, E):
    L_copy = L[:]      # 步骤1：创建副本
    L.clear()          # 步骤2：清空原始列表
    for item in L_copy: # 步骤3：遍历副本
        if item != E:
            L.append(item) # 将符合条件的元素添加回L
```

![](img/efad76c3e8c4490c462d988e1439ac55_21.png)

调用此函数后，传入的列表 `L` 将被直接修改，无需返回任何值。

![](img/efad76c3e8c4490c462d988e1439ac55_23.png)

---

## 列表的删除操作

![](img/efad76c3e8c4490c462d988e1439ac55_25.png)

![](img/efad76c3e8c4490c462d988e1439ac55_27.png)

![](img/efad76c3e8c4490c462d988e1439ac55_28.png)

![](img/efad76c3e8c4490c462d988e1439ac55_30.png)

![](img/efad76c3e8c4490c462d988e1439ac55_32.png)

除了整体修改，我们经常需要从列表中删除特定元素。Python提供了几种方法。

![](img/efad76c3e8c4490c462d988e1439ac55_34.png)

![](img/efad76c3e8c4490c462d988e1439ac55_36.png)

![](img/efad76c3e8c4490c462d988e1439ac55_37.png)

![](img/efad76c3e8c4490c462d988e1439ac55_39.png)

![](img/efad76c3e8c4490c462d988e1439ac55_41.png)

以下是三种主要的删除方式：

![](img/efad76c3e8c4490c462d988e1439ac55_43.png)

*   **`del L[index]`**：根据索引删除元素。
*   **`L.pop()`**：删除并返回列表的最后一个元素。
*   **`L.remove(value)`**：删除列表中第一个与指定值匹配的元素。

![](img/efad76c3e8c4490c462d988e1439ac55_44.png)

![](img/efad76c3e8c4490c462d988e1439ac55_46.png)

![](img/efad76c3e8c4490c462d988e1439ac55_47.png)

让我们通过一个例子来观察它们的行为：

```python
L = [2, 1, 3, 6, 3, 7, 0]
L.remove(2)   # 删除第一个2 -> L变为 [1, 3, 6, 3, 7, 0]
L.remove(3)   # 删除第一个3 -> L变为 [1, 6, 3, 7, 0]
del L[1]      # 删除索引1的元素（6）-> L变为 [1, 3, 7, 0]
last_item = L.pop() # 删除并返回最后一个元素（0）-> L变为 [1, 3, 7]，last_item为0
```

![](img/efad76c3e8c4490c462d988e1439ac55_49.png)

注意，这些操作都会直接修改（突变）列表 `L`。`pop()` 方法比较特殊，它既有修改列表的副作用，也会返回被删除的值。

![](img/efad76c3e8c4490c462d988e1439ac55_51.png)

![](img/efad76c3e8c4490c462d988e1439ac55_53.png)

![](img/efad76c3e8c4490c462d988e1439ac55_55.png)

---

![](img/efad76c3e8c4490c462d988e1439ac55_57.png)

![](img/efad76c3e8c4490c462d988e1439ac55_59.png)

## 遍历时修改列表的陷阱

![](img/efad76c3e8c4490c462d988e1439ac55_61.png)

![](img/efad76c3e8c4490c462d988e1439ac55_63.png)

现在，我们尝试用 `remove` 方法重写之前的 `remove_all` 函数。一个直观的想法是遍历列表，遇到等于 `E` 的元素就删除它。

![](img/efad76c3e8c4490c462d988e1439ac55_65.png)

![](img/efad76c3e8c4490c462d988e1439ac55_67.png)

![](img/efad76c3e8c4490c462d988e1439ac55_69.png)

![](img/efad76c3e8c4490c462d988e1439ac55_71.png)

```python
def remove_all_buggy(L, E):
    for item in L:
        if item == E:
            L.remove(E)
```

![](img/efad76c3e8c4490c462d988e1439ac55_72.png)

![](img/efad76c3e8c4490c462d988e1439ac55_74.png)

这段代码存在一个严重问题。假设 `L = [1, 2, 2, 2]`，我们要移除所有 `2`。

![](img/efad76c3e8c4490c462d988e1439ac55_76.png)

![](img/efad76c3e8c4490c462d988e1439ac55_77.png)

![](img/efad76c3e8c4490c462d988e1439ac55_79.png)

![](img/efad76c3e8c4490c462d988e1439ac55_81.png)

1.  第一次循环，`item` 是 `1`，不删除。
2.  第二次循环，`item` 是第一个 `2`，条件成立，删除它。列表变为 `[1, 2, 2]`，**但循环的内部指针已经移到了下一个位置（索引2）**。
3.  第三次循环，`item` 是现在位于索引1的 `2`（原列表的第三个 `2`），我们跳过了原列表的第二个 `2`。
4.  最终，列表中可能仍残留未被删除的 `2`。

![](img/efad76c3e8c4490c462d988e1439ac55_83.png)

![](img/efad76c3e8c4490c462d988e1439ac55_84.png)

![](img/efad76c3e8c4490c462d988e1439ac55_86.png)

![](img/efad76c3e8c4490c462d988e1439ac55_87.png)

**核心问题**：在遍历列表的同时对其进行修改（尤其是删除），会导致内部迭代指针错位，从而跳过某些元素或产生不可预测的行为。

---

## 解决方案：遍历副本，修改原始列表

为了避免上述陷阱，一个可靠的方法是：**遍历列表的副本，但修改操作作用于原始列表**。

![](img/efad76c3e8c4490c462d988e1439ac55_89.png)

![](img/efad76c3e8c4490c462d988e1439ac55_91.png)

我们通过另一个函数 `remove_duplicates` 来演示。该函数接收两个列表 `L1` 和 `L2`，并修改 `L1`，移除其中所有也存在于 `L2` 中的元素。

![](img/efad76c3e8c4490c462d988e1439ac55_93.png)

![](img/efad76c3e8c4490c462d988e1439ac55_95.png)

![](img/efad76c3e8c4490c462d988e1439ac55_97.png)

![](img/efad76c3e8c4490c462d988e1439ac55_98.png)

以下是正确的实现：

![](img/efad76c3e8c4490c462d988e1439ac55_100.png)

![](img/efad76c3e8c4490c462d988e1439ac55_102.png)

```python
def remove_duplicates(L1, L2):
    L1_copy = L1[:]        # 创建L1的副本
    for item in L1_copy:   # 遍历副本
        if item in L2:     # 如果该元素也在L2中
            L1.remove(item) # 则从原始L1中移除它
```

通过遍历 `L1_copy`，我们获得了一个稳定的元素序列。即使 `L1` 在循环中被修改，也不会影响我们遍历 `L1_copy` 的过程，从而确保每个元素都被正确检查。

![](img/efad76c3e8c4490c462d988e1439ac55_104.png)

![](img/efad76c3e8c4490c462d988e1439ac55_106.png)

---

![](img/efad76c3e8c4490c462d988e1439ac55_108.png)

![](img/efad76c3e8c4490c462d988e1439ac55_110.png)

![](img/efad76c3e8c4490c462d988e1439ac55_112.png)

## 理解别名（Aliasing）

![](img/efad76c3e8c4490c462d988e1439ac55_114.png)

![](img/efad76c3e8c4490c462d988e1439ac55_115.png)

![](img/efad76c3e8c4490c462d988e1439ac55_116.png)

![](img/efad76c3e8c4490c462d988e1439ac55_118.png)

![](img/efad76c3e8c4490c462d988e1439ac55_120.png)

别名是指多个变量名指向内存中的同一个对象。

![](img/efad76c3e8c4490c462d988e1439ac55_122.png)

![](img/efad76c3e8c4490c462d988e1439ac55_123.png)

在Python中，简单的赋值操作 `new_list = old_list` 并不会创建副本，而只是创建了一个指向同一列表对象的别名。

![](img/efad76c3e8c4490c462d988e1439ac55_125.png)

![](img/efad76c3e8c4490c462d988e1439ac55_127.png)

![](img/efad76c3e8c4490c462d988e1439ac55_129.png)

![](img/efad76c3e8c4490c462d988e1439ac55_131.png)

```python
old_list = [10, 20, 30, 40]
alias_list = old_list # alias_list 是 old_list 的别名，指向同一个列表
alias_list[0] = 999
print(old_list) # 输出：[999, 20, 30, 40]，原始列表也被修改了
```

![](img/efad76c3e8c4490c462d988e1439ac55_133.png)

![](img/efad76c3e8c4490c462d988e1439ac55_134.png)

**关键区别**：
*   `alias_list = old_list` 创建的是**别名**。
*   `copy_list = old_list[:]` 创建的是**副本（克隆）**。

![](img/efad76c3e8c4490c462d988e1439ac55_136.png)

![](img/efad76c3e8c4490c462d988e1439ac55_138.png)

在函数调用中，形参（parameter）会成为实参（argument）的别名。这意味着，如果向函数传递一个可变对象（如列表），并在函数内部修改它，那么函数外部的原始变量所指向的对象也会被改变。

![](img/efad76c3e8c4490c462d988e1439ac55_140.png)

![](img/efad76c3e8c4490c462d988e1439ac55_141.png)

![](img/efad76c3e8c4490c462d988e1439ac55_143.png)

![](img/efad76c3e8c4490c462d988e1439ac55_144.png)

![](img/efad76c3e8c4490c462d988e1439ac55_145.png)

---

![](img/efad76c3e8c4490c462d988e1439ac55_147.png)

![](img/efad76c3e8c4490c462d988e1439ac55_149.png)

![](img/efad76c3e8c4490c462d988e1439ac55_150.png)

![](img/efad76c3e8c4490c462d988e1439ac55_152.png)

## 浅拷贝与深拷贝

![](img/efad76c3e8c4490c462d988e1439ac55_154.png)

当列表的元素本身也是可变对象（如嵌套列表）时，拷贝行为会变得更加复杂。

![](img/efad76c3e8c4490c462d988e1439ac55_156.png)

*   **浅拷贝（Shallow Copy）**：使用 `list.copy()` 或 `list[:]` 创建。只复制最外层的列表结构，内部的子列表等可变元素仍然是引用（别名）。
*   **深拷贝（Deep Copy）**：使用 `copy.deepcopy()` 创建。递归地复制所有层级的对象，创建一个完全独立的新对象。

![](img/efad76c3e8c4490c462d988e1439ac55_158.png)

![](img/efad76c3e8c4490c462d988e1439ac55_160.png)

![](img/efad76c3e8c4490c462d988e1439ac55_162.png)

![](img/efad76c3e8c4490c462d988e1439ac55_164.png)

考虑以下例子：

![](img/efad76c3e8c4490c462d988e1439ac55_166.png)

![](img/efad76c3e8c4490c462d988e1439ac55_168.png)

![](img/efad76c3e8c4490c462d988e1439ac55_169.png)

```python
import copy

![](img/efad76c3e8c4490c462d988e1439ac55_171.png)

![](img/efad76c3e8c4490c462d988e1439ac55_173.png)

![](img/efad76c3e8c4490c462d988e1439ac55_175.png)

![](img/efad76c3e8c4490c462d988e1439ac55_176.png)

old_list = [[1, 2], [3, 4], [5, 6]]

![](img/efad76c3e8c4490c462d988e1439ac55_178.png)

![](img/efad76c3e8c4490c462d988e1439ac55_179.png)

![](img/efad76c3e8c4490c462d988e1439ac55_180.png)

![](img/efad76c3e8c4490c462d988e1439ac55_182.png)

# 浅拷贝
shallow_copy = old_list[:]
# 深拷贝
deep_copy = copy.deepcopy(old_list)

![](img/efad76c3e8c4490c462d988e1439ac55_184.png)

![](img/efad76c3e8c4490c462d988e1439ac55_186.png)

![](img/efad76c3e8c4490c462d988e1439ac55_187.png)

![](img/efad76c3e8c4490c462d988e1439ac55_189.png)

# 修改原始列表的一个子元素
old_list[1][1] = 999

print(shallow_copy) # 输出：[[1, 2], [3, 999], [5, 6]]，子列表被共享，因此被修改
print(deep_copy)    # 输出：[[1, 2], [3, 4], [5, 6]]，完全独立，未被修改

# 在原始列表顶层添加新元素
old_list.append([7, 8])
print(shallow_copy) # 输出：[[1, 2], [3, 999], [5, 6]]，顶层结构独立，未添加[7,8]
```

**选择依据**：如果确定嵌套结构中的元素是不可变的，或者你希望共享子对象，使用浅拷贝。如果需要完全独立的副本，避免任何意外的联动修改，则使用深拷贝。

![](img/efad76c3e8c4490c462d988e1439ac55_191.png)

![](img/efad76c3e8c4490c462d988e1439ac55_192.png)

---

## 总结

本节课中我们一起学习了：
1.  **列表副本的创建**：使用 `L[:]` 语法。
2.  **列表的删除操作**：`del`、`pop()` 和 `remove()` 的使用与区别。
3.  **遍历时修改的陷阱**：在 `for` 循环中直接修改正在遍历的列表可能导致元素被跳过。
4.  **安全的修改模式**：通过**遍历副本，修改原始列表**来避免上述陷阱。
5.  **别名与克隆**：赋值 `=` 创建别名，切片 `[:]` 创建克隆。函数参数传递的是别名。
6.  **浅拷贝与深拷贝**：处理嵌套可变对象时，理解 `copy()` 与 `deepcopy()` 的区别至关重要。

![](img/efad76c3e8c4490c462d988e1439ac55_194.png)

![](img/efad76c3e8c4490c462d988e1439ac55_196.png)

掌握这些概念对于正确、高效地使用Python中的可变数据结构非常重要，能帮助你避免许多隐蔽的错误。