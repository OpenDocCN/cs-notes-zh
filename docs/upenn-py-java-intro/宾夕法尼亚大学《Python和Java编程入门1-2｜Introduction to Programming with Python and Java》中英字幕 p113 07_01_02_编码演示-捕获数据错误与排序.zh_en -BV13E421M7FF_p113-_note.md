# Python和Java编程入门1-2：07_01_02：编码演示-捕获数据错误与排序 🐍

在本节课中，我们将学习如何处理数据集中的错误数据，并探索如何使用Lambda函数对数据进行排序。我们将从一个包含专辑信息的数据集开始，目标是找出其中最早的发行年份，并学习如何按艺术家姓名对专辑列表进行排序。

## 概述

我们将首先尝试从数据集中提取发行年份并找出最小值，但会遇到非数值数据导致的错误。为了解决这个问题，我们将编写一个函数来安全地验证和转换数据。之后，我们将介绍Lambda函数的概念，并演示如何使用它作为`sorted`函数的参数来对数据进行自定义排序。

## 处理数据错误

首先，我们的目标是找出数据集中所有专辑的最早发行年份。我们尝试创建一个包含所有发行年份的整数列表。

以下是创建发行年份列表的初始代码：
```python
release_years = []
for row in albums:
    if row['year']:
        release_years.append(int(row['year']))
```

![](img/694d604a67995b99494a301711b264b9_1.png)

运行这段代码时，我们遇到了一个`ValueError`，提示“invalid literal for int() with base 10”。这意味着`year`列中的某个值不是有效的数字字符串，无法转换为整数。

与其手动查找这个无效值，我们更合理的做法是编写代码来处理这种异常情况。我们将定义一个函数，通过捕获`ValueError`来安全地检查一个字符串是否能被转换为整数。

### 定义验证函数

我们定义一个名为`is_valid_year`的函数。在Python中，我们使用`def`关键字来定义函数。

```python
def is_valid_year(year_string):
    try:
        year = int(year_string)
        return year
    except ValueError:
        return False
```
这个函数尝试将输入的字符串转换为整数。如果转换成功，则返回该整数；如果引发`ValueError`异常，则返回`False`，表示提供的年份无效。

### 使用验证函数过滤数据

现在，我们使用这个`is_valid_year`函数来生成一个只包含有效年份的列表。我们使用列表推导式来简化代码。

```python
release_years = [int(row['year']) for row in albums if is_valid_year(row['year'])]
print(release_years)
```
运行代码后，我们得到了一个有效的发行年份列表。

接着，我们打印出最小的发行年份：
```python
print(min(release_years))
```
输出结果是`1399`。然而，`1399`年对于我们的数据集来说并不是一个合理的年份。这表明我们的验证逻辑还需要加强。

![](img/694d604a67995b99494a301711b264b9_3.png)

### 完善验证逻辑

我们需要修改`is_valid_year`函数，使其不仅检查能否转换为整数，还要检查年份是否大于一个合理的阈值（例如1400年）。

```python
def is_valid_year(year_string):
    try:
        year = int(year_string)
        if year > 1400:
            return year
        else:
            return False
    except ValueError:
        return False
```
现在，一个有效的年份必须能转换为整数**并且**大于1400。我们重新运行生成列表和查找最小值的代码，得到了更合理的结果`1955`。

![](img/694d604a67995b99494a301711b264b9_5.png)

上一节我们介绍了如何捕获和处理数据错误，确保我们只处理有效的数据。接下来，我们将看看如何对处理后的数据进行排序。

![](img/694d604a67995b99494a301711b264b9_7.png)

## 使用Lambda函数进行排序

为了对数据进行灵活的排序，Python提供了`sorted`函数和一个强大的工具——Lambda函数。

![](img/694d604a67995b99494a301711b264b9_9.png)

### 理解Lambda函数

![](img/694d604a67995b99494a301711b264b9_11.png)

![](img/694d604a67995b99494a301711b264b9_12.png)

Lambda函数是一种匿名、单行的迷你函数，可以即时定义和使用。它适用于需要一个简单函数作为参数的场景。

以下是一个将数字加倍的常规函数定义：
```python
def double(x):
    return x * 2
print(double(4))  # 输出 8
```
使用Lambda函数可以实现相同的功能：
```python
double_l = lambda x: x * 2
print(double_l(4))  # 输出 8
```
Lambda函数特别适合作为参数传递给其他高阶函数，例如`sorted`函数的`key`参数。

### 对专辑列表进行排序

![](img/694d604a67995b99494a301711b264b9_14.png)

`sorted`函数接受一个可选的`key`参数，该参数指定一个函数，用于从每个元素中提取比较键。

假设我们想按艺术家（artist）的名字对`albums`列表进行排序。我们可以向`sorted`函数传递一个Lambda函数作为`key`。

![](img/694d604a67995b99494a301711b264b9_16.png)

```python
albums_sorted = sorted(albums, key=lambda x: x['artist'])
```
在这行代码中：
*   `sorted(albums, ...)` 对`albums`列表进行排序。
*   `key=lambda x: x[‘artist’]` 定义了一个Lambda函数，它接收一个参数`x`（代表列表中的每一行数据），并返回该行的`artist`字段的值。`sorted`函数将根据这个返回值来排列列表中的元素。

运行这行代码后，`albums_sorted`就是一个按艺术家名字字母顺序排列的新列表。

## 总结

![](img/694d604a67995b99494a301711b264b9_18.png)

本节课中我们一起学习了两个重要的编程技巧。
首先，我们学习了如何处理数据集中的异常值。通过定义`is_valid_year`函数并使用`try-except`块捕获`ValueError`，我们能够安全地过滤掉无效的年份数据，并在此基础上计算出合理的最早发行年份。
其次，我们介绍了Lambda函数，这是一种简洁的定义匿名函数的方式。我们演示了如何将Lambda函数作为`sorted`函数的`key`参数，从而实现对数据列表的自定义排序，例如按艺术家姓名对专辑进行排序。
掌握错误处理和Lambda函数的使用，将使你能够更稳健、更灵活地处理和分析数据。