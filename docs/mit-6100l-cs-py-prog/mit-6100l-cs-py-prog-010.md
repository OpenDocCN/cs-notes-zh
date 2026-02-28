# 010：列表与可变性 📚

![](img/faafd195adde2fbf0b6029296d7ca827_0.png)

在本节课中，我们将要学习列表（List）数据类型的核心概念——可变性（Mutability）。我们将探讨如何创建和操作列表，理解可变对象在内存中的行为，并学习一系列用于修改列表的内置方法。

![](img/faafd195adde2fbf0b6029296d7ca827_2.png)

![](img/faafd195adde2fbf0b6029296d7ca827_4.png)

![](img/faafd195adde2fbf0b6029296d7ca827_5.png)

![](img/faafd195adde2fbf0b6029296d7ca827_7.png)

---

![](img/faafd195adde2fbf0b6029296d7ca827_9.png)

![](img/faafd195adde2fbf0b6029296d7ca827_10.png)

## 列表基础回顾 🔄

![](img/faafd195adde2fbf0b6029296d7ca827_12.png)

![](img/faafd195adde2fbf0b6029296d7ca827_13.png)

![](img/faafd195adde2fbf0b6029296d7ca827_15.png)

![](img/faafd195adde2fbf0b6029296d7ca827_17.png)

上一讲我们介绍了元组（tuple）和列表（list）这两种复合数据类型。与元组和字符串类似，列表支持许多相同的操作，例如获取长度、索引、切片、连接和迭代。

以下是列表的一些基本操作示例：

```python
L = []  # 创建一个空列表
L = [1, 'a', 2, [1, 2]]  # 列表可以包含不同类型的元素
len(L)  # 获取长度
L[0]    # 索引访问
L[1:3]  # 切片
L1 + L2 # 连接
max(L)  # 获取最大值（如果元素可比较）
for e in L:  # 直接迭代列表元素
    print(e)
```

![](img/faafd195adde2fbf0b6029296d7ca827_19.png)

![](img/faafd195adde2fbf0b6029296d7ca827_21.png)

列表与元组和字符串的关键区别在于其**可变性**。这意味着我们可以在列表创建后修改其内容。

![](img/faafd195adde2fbf0b6029296d7ca827_23.png)

![](img/faafd195adde2fbf0b6029296d7ca827_24.png)

![](img/faafd195adde2fbf0b6029296d7ca827_26.png)

---

![](img/faafd195adde2fbf0b6029296d7ca827_27.png)

![](img/faafd195adde2fbf0b6029296d7ca827_29.png)

![](img/faafd195adde2fbf0b6029296d7ca827_30.png)

![](img/faafd195adde2fbf0b6029296d7ca827_31.png)

## 理解可变性：修改列表元素 ✏️

![](img/faafd195adde2fbf0b6029296d7ca827_33.png)

![](img/faafd195adde2fbf0b6029296d7ca827_35.png)

![](img/faafd195adde2fbf0b6029296d7ca827_36.png)

对于字符串和元组这样的不可变对象，一旦创建就无法更改。但列表允许我们修改其内部的元素。

![](img/faafd195adde2fbf0b6029296d7ca827_38.png)

以下是如何修改列表中特定索引处的元素：

![](img/faafd195adde2fbf0b6029296d7ca827_39.png)

![](img/faafd195adde2fbf0b6029296d7ca827_41.png)

![](img/faafd195adde2fbf0b6029296d7ca827_43.png)

![](img/faafd195adde2fbf0b6029296d7ca827_45.png)

```python
L = [2, 4, 3]
L[1] = 5  # 将索引1处的元素（值4）修改为5
# 现在 L 变为 [2, 5, 3]
```

![](img/faafd195adde2fbf0b6029296d7ca827_47.png)

让我们通过内存图来理解这个过程。当执行 `L[1] = 5` 时，Python会：
1.  跟随变量名 `L` 找到内存中的列表对象。
2.  定位到索引 `1` 对应的位置。
3.  用右侧的值（`5`）覆盖该位置原有的值。

**这个过程直接修改了内存中的列表对象本身，而不是创建一个新的副本。** 这与元组的赋值操作形成对比：

```python
T = (2, 4, 3)
T = (2, 5, 3)  # 这创建了一个新的元组对象，并让 T 指向它。原元组 (2,4,3) 未被修改，只是失去了引用。
```

---

## 列表的常用修改操作 🛠️

除了直接修改元素，列表还提供了一系列用于修改自身的方法。这些方法通常**没有返回值**（返回 `None`），它们的作用在于其产生的“副作用”——即改变列表本身。

以下是几个核心的修改操作：

### 1. 添加元素：`append()`

![](img/faafd195adde2fbf0b6029296d7ca827_49.png)

![](img/faafd195adde2fbf0b6029296d7ca827_51.png)

`append()` 方法用于在列表末尾添加一个元素。

```python
L = [2, 1, 3]
L.append(5)  # 将 5 添加到列表末尾
# 现在 L 变为 [2, 1, 3, 5]
```

![](img/faafd195adde2fbf0b6029296d7ca827_53.png)

![](img/faafd195adde2fbf0b6029296d7ca827_54.png)

![](img/faafd195adde2fbf0b6029296d7ca827_56.png)

![](img/faafd195adde2fbf0b6029296d7ca827_57.png)

**重要提示**：`append()` 返回 `None`。一个常见的错误是尝试将结果保存回变量：

![](img/faafd195adde2fbf0b6029296d7ca827_59.png)

![](img/faafd195adde2fbf0b6029296d7ca827_61.png)

```python
L = [2, 1, 3]
L = L.append(5)  # 错误！这会使 L 变为 None
# 正确做法：直接调用 L.append(5)
```

![](img/faafd195adde2fbf0b6029296d7ca827_63.png)

![](img/faafd195adde2fbf0b6029296d7ca827_64.png)

![](img/faafd195adde2fbf0b6029296d7ca827_66.png)

![](img/faafd195adde2fbf0b6029296d7ca827_68.png)

### 2. 添加多个元素：`extend()`

![](img/faafd195adde2fbf0b6029296d7ca827_70.png)

![](img/faafd195adde2fbf0b6029296d7ca827_71.png)

![](img/faafd195adde2fbf0b6029296d7ca827_72.png)

![](img/faafd195adde2fbf0b6029296d7ca827_74.png)

![](img/faafd195adde2fbf0b6029296d7ca827_75.png)

![](img/faafd195adde2fbf0b6029296d7ca827_77.png)

![](img/faafd195adde2fbf0b6029296d7ca827_79.png)

`extend()` 方法用于将一个列表中的所有元素添加到另一个列表的末尾。

![](img/faafd195adde2fbf0b6029296d7ca827_81.png)

![](img/faafd195adde2fbf0b6029296d7ca827_83.png)

![](img/faafd195adde2fbf0b6029296d7ca827_84.png)

```python
L1 = [2, 1, 3]
L2 = [0, 6]
L1.extend(L2)  # 将 L2 中的所有元素添加到 L1 末尾
# 现在 L1 变为 [2, 1, 3, 0, 6]
```

注意 `extend()` 与连接操作 `+` 的区别：`+` 会创建一个**新的列表**，而 `extend()` 是**修改原列表**。

![](img/faafd195adde2fbf0b6029296d7ca827_86.png)

### 3. 排序与反转：`sort()` 和 `reverse()`

![](img/faafd195adde2fbf0b6029296d7ca827_88.png)

![](img/faafd195adde2fbf0b6029296d7ca827_90.png)

![](img/faafd195adde2fbf0b6029296d7ca827_92.png)

![](img/faafd195adde2fbf0b6029296d7ca827_94.png)

![](img/faafd195adde2fbf0b6029296d7ca827_96.png)

`sort()` 和 `reverse()` 方法会直接修改列表，使其按顺序排序或反转。

![](img/faafd195adde2fbf0b6029296d7ca827_98.png)

```python
L = [4, 2, 7]
L.sort()    # 将 L 修改为 [2, 4, 7]
L.reverse() # 将 L 修改为 [7, 4, 2]
```

![](img/faafd195adde2fbf0b6029296d7ca827_100.png)

如果你希望得到一个排序后的新列表，同时保留原列表不变，可以使用内置的 `sorted()` 函数：

```python
L = [4, 2, 7]
L_new = sorted(L)  # L_new 是 [2, 4, 7]，L 仍然是 [4, 2, 7]
```

![](img/faafd195adde2fbf0b6029296d7ca827_102.png)

![](img/faafd195adde2fbf0b6029296d7ca827_103.png)

![](img/faafd195adde2fbf0b6029296d7ca827_104.png)

![](img/faafd195adde2fbf0b6029296d7ca827_106.png)

### 4. 清空列表：`clear()`

![](img/faafd195adde2fbf0b6029296d7ca827_108.png)

![](img/faafd195adde2fbf0b6029296d7ca827_110.png)

![](img/faafd195adde2fbf0b6029296d7ca827_111.png)

![](img/faafd195adde2fbf0b6029296d7ca827_113.png)

`clear()` 方法用于移除列表中的所有元素，使其变为空列表。

![](img/faafd195adde2fbf0b6029296d7ca827_115.png)

![](img/faafd195adde2fbf0b6029296d7ca827_117.png)

![](img/faafd195adde2fbf0b6029296d7ca827_119.png)

![](img/faafd195adde2fbf0b6029296d7ca827_120.png)

```python
L = [4, 5, 6]
L.clear()  # 现在 L 变为 []
```

![](img/faafd195adde2fbf0b6029296d7ca827_122.png)

![](img/faafd195adde2fbf0b6029296d7ca827_123.png)

---

![](img/faafd195adde2fbf0b6029296d7ca827_125.png)

![](img/faafd195adde2fbf0b6029296d7ca827_126.png)

## 遍历并修改列表 🔄

![](img/faafd195adde2fbf0b6029296d7ca827_128.png)

当我们需要遍历列表并修改其中的元素时，通常需要获取元素的索引。因为修改元素的语法 `L[i] = new_value` 需要索引 `i`。

![](img/faafd195adde2fbf0b6029296d7ca827_130.png)

以下是几种常见的遍历方式：

![](img/faafd195adde2fbf0b6029296d7ca827_132.png)

![](img/faafd195adde2fbf0b6029296d7ca827_133.png)

**方法一：遍历索引**
这是最直接的方法，使用 `range(len(L))` 生成索引序列。

![](img/faafd195adde2fbf0b6029296d7ca827_135.png)

![](img/faafd195adde2fbf0b6029296d7ca827_137.png)

```python
def square_list(L):
    """将列表 L 中的每个元素替换为其平方（直接修改 L）"""
    for i in range(len(L)):
        L[i] = L[i] ** 2
    # 函数没有 return 语句，默认返回 None
```

![](img/faafd195adde2fbf0b6029296d7ca827_139.png)

![](img/faafd195adde2fbf0b6029296d7ca827_140.png)

![](img/faafd195adde2fbf0b6029296d7ca827_142.png)

![](img/faafd195adde2fbf0b6029296d7ca827_143.png)

**方法二：使用 `enumerate()`**
`enumerate()` 函数可以在迭代时同时获得索引和元素值。

![](img/faafd195adde2fbf0b6029296d7ca827_145.png)

![](img/faafd195adde2fbf0b6029296d7ca827_147.png)

![](img/faafd195adde2fbf0b6029296d7ca827_148.png)

![](img/faafd195adde2fbf0b6029296d7ca827_149.png)

![](img/faafd195adde2fbf0b6029296d7ca827_151.png)

![](img/faafd195adde2fbf0b6029296d7ca827_152.png)

```python
for index, element in enumerate(L):
    # 使用 index 和 element
    L[index] = element ** 2
```

![](img/faafd195adde2fbf0b6029296d7ca827_154.png)

![](img/faafd195adde2fbf0b6029296d7ca827_156.png)

---

## 字符串与列表的转换 🔀

列表和字符串之间可以方便地相互转换，这在处理文本时非常有用。

**将字符串转换为列表：**
*   `list(s)`：将字符串 `s` 的每个字符（包括空格）变成列表的独立元素。
*   `s.split(sep)`：根据分隔符 `sep` 将字符串 `s` 分割成单词列表。常用的是按空格分割：`s.split(‘ ‘)`。

![](img/faafd195adde2fbf0b6029296d7ca827_158.png)

![](img/faafd195adde2fbf0b6029296d7ca827_160.png)

![](img/faafd195adde2fbf0b6029296d7ca827_162.png)

![](img/faafd195adde2fbf0b6029296d7ca827_164.png)

```python
s = “I <3 CS @ NU”
list(s)          # 结果: [‘I’, ‘ ‘, ‘<‘, ‘3’, ‘ ‘, ‘C’, ‘S’, ‘ ‘, ‘@’, ‘ ‘, ‘N’, ‘U’]
s.split(‘ ‘)     # 结果: [‘I’, ‘<3’, ‘CS’, ‘@’, ‘NU’]
s.split(‘<‘)     # 结果: [‘I ‘, ‘3 CS @ NU’]
```

![](img/faafd195adde2fbf0b6029296d7ca827_166.png)

![](img/faafd195adde2fbf0b6029296d7ca827_167.png)

![](img/faafd195adde2fbf0b6029296d7ca827_169.png)

![](img/faafd195adde2fbf0b6029296d7ca827_170.png)

![](img/faafd195adde2fbf0b6029296d7ca827_172.png)

**将列表转换为字符串：**
使用 `join()` 方法，它需要一个字符串作为连接符。

![](img/faafd195adde2fbf0b6029296d7ca827_173.png)

![](img/faafd195adde2fbf0b6029296d7ca827_175.png)

![](img/faafd195adde2fbf0b6029296d7ca827_177.png)

![](img/faafd195adde2fbf0b6029296d7ca827_179.png)

![](img/faafd195adde2fbf0b6029296d7ca827_181.png)

![](img/faafd195adde2fbf0b6029296d7ca827_183.png)

![](img/faafd195adde2fbf0b6029296d7ca827_184.png)

```python
L = [‘A’, ‘B’, ‘C’]
‘‘.join(L)      # 结果: ‘ABC’
‘_’.join(L)     # 结果: ‘A_B_C’
```

![](img/faafd195adde2fbf0b6029296d7ca827_186.png)

![](img/faafd195adde2fbf0b6029296d7ca827_188.png)

**注意**：`join()` 要求列表中的所有元素都是字符串类型。

---

![](img/faafd195adde2fbf0b6029296d7ca827_190.png)

![](img/faafd195adde2fbf0b6029296d7ca827_192.png)

![](img/faafd195adde2fbf0b6029296d7ca827_194.png)

![](img/faafd195adde2fbf0b6029296d7ca827_196.png)

![](img/faafd195adde2fbf0b6029296d7ca827_197.png)

![](img/faafd195adde2fbf0b6029296d7ca827_199.png)

![](img/faafd195adde2fbf0b6029296d7ca827_201.png)

![](img/faafd195adde2fbf0b6029296d7ca827_202.png)

## 可变性带来的陷阱与思考 🤔

![](img/faafd195adde2fbf0b6029296d7ca827_204.png)

![](img/faafd195adde2fbf0b6029296d7ca827_206.png)

可变性虽然强大，但也可能引入一些意想不到的行为，尤其是在循环中修改列表时。理解“对象”与“对象名称”的区别至关重要。

![](img/faafd195adde2fbf0b6029296d7ca827_208.png)

![](img/faafd195adde2fbf0b6029296d7ca827_209.png)

![](img/faafd195adde2fbf0b6029296d7ca827_211.png)

![](img/faafd195adde2fbf0b6029296d7ca827_212.png)

**关键概念**：变量名（如 `L`）是对内存中某个对象的**引用**或**绑定**。`L = new_value` 操作是改变这个绑定，让它指向一个新的对象。而 `L.append(x)` 或 `L[i] = y` 是改变 `L` 当前所指向的那个对象本身。

![](img/faafd195adde2fbf0b6029296d7ca827_214.png)

![](img/faafd195adde2fbf0b6029296d7ca827_215.png)

![](img/faafd195adde2fbf0b6029296d7ca827_217.png)

![](img/faafd195adde2fbf0b6029296d7ca827_218.png)

![](img/faafd195adde2fbf0b6029296d7ca827_220.png)

我们可以使用 `id()` 函数来查看一个对象在内存中的唯一标识，从而判断两个变量是否指向同一个对象。

![](img/faafd195adde2fbf0b6029296d7ca827_222.png)

![](img/faafd195adde2fbf0b6029296d7ca827_224.png)

![](img/faafd195adde2fbf0b6029296d7ca827_226.png)

```python
L = [4, 5, 6]
print(id(L))  # 输出一个代表内存地址的数字

![](img/faafd195adde2fbf0b6029296d7ca827_228.png)

![](img/faafd195adde2fbf0b6029296d7ca827_229.png)

![](img/faafd195adde2fbf0b6029296d7ca827_231.png)

![](img/faafd195adde2fbf0b6029296d7ca827_232.png)

L.append(8)
print(id(L))  # 输出相同的数字，说明是同一个对象被修改了

![](img/faafd195adde2fbf0b6029296d7ca827_234.png)

![](img/faafd195adde2fbf0b6029296d7ca827_236.png)

![](img/faafd195adde2fbf0b6029296d7ca827_238.png)

![](img/faafd195adde2fbf0b6029296d7ca827_240.png)

L = []        # 将名称 L 绑定到一个新的空列表对象
print(id(L))  # 输出不同的数字，说明 L 现在指向了另一个对象
```

---

![](img/faafd195adde2fbf0b6029296d7ca827_242.png)

## 总结 📝

![](img/faafd195adde2fbf0b6029296d7ca827_244.png)

![](img/faafd195adde2fbf0b6029296d7ca827_246.png)

![](img/faafd195adde2fbf0b6029296d7ca827_247.png)

本节课中我们一起学习了列表的核心特性——可变性。

*   **列表是可变对象**：创建后可以修改其内容（增、删、改元素），这使其适用于需要动态变化的数据集合（如员工名单、待办事项）。
*   **元组是不可变对象**：创建后内容不可更改，适用于表示固定不变的数据（如坐标、常量配置）。
*   **修改列表的方法**：如 `append()`, `extend()`, `sort()`, `reverse()`, `clear()` 等，它们直接修改列表本身，通常返回 `None`。
*   **操作语法**：使用 `L[i] = value` 修改元素，使用 `L.method()` 调用修改方法。
*   **重要区别**：要清晰地区分“修改变量绑定”（`L = something`）和“修改对象本身”（`L.append(x)`）。前者可能丢失对原对象的引用，后者则是在原地改变对象。
*   **转换工具**：`split()` 和 `join()` 是字符串与列表间转换的利器。

![](img/faafd195adde2fbf0b6029296d7ca827_249.png)

![](img/faafd195adde2fbf0b6029296d7ca827_250.png)

理解可变性是掌握Python中复杂数据操作的关键。下一讲我们将继续探讨与可变性相关的更多细节和复杂情况。