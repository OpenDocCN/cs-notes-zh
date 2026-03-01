# 094：代码练习-成绩考勤簿 📚

在本节课中，我们将通过一个综合练习来巩固对Python字典的理解。我们将创建一个用于管理学生成绩和出勤情况的“成绩考勤簿”。这个练习将涉及创建嵌套字典、访问数据、遍历字典以及进行简单的计算。

![](img/503acde6669ea7ded2286aff59887689_1.png)

---

## 创建学生字典

首先，我们需要为每个学生创建一个字典。每个学生的字典将包含三个键值对：`name`（姓名）、`grades`（成绩列表）和`attendance`（出勤情况列表）。

以下是三个学生的数据：

*   **Billy**:
    *   姓名：`"Billy"`
    *   成绩：`[100, 80, 67, 100, 89]`
    *   出勤：`[True, True, True, True, True]`（全勤）

*   **Sarah**:
    *   姓名：`"Sarah"`
    *   成绩：`[0, 99, 0, 100]`
    *   出勤：`[True, False, True, False, True]`

*   **Ben**:
    *   姓名：`"Ben"`
    *   成绩：`[60, 82, 71, 92, 100]`
    *   出勤：`[False, False, False, False, False]`（全缺勤）

在代码中，我们这样创建它们：

![](img/503acde6669ea7ded2286aff59887689_3.png)

```python
billy = {
    "name": "Billy",
    "grades": [100, 80, 67, 100, 89],
    "attendance": [True, True, True, True, True]
}

![](img/503acde6669ea7ded2286aff59887689_5.png)

sarah = {
    "name": "Sarah",
    "grades": [0, 99, 0, 100],
    "attendance": [True, False, True, False, True]
}

ben = {
    "name": "Ben",
    "grades": [60, 82, 71, 92, 100],
    "attendance": [False, False, False, False, False]
}
```

---

![](img/503acde6669ea7ded2286aff59887689_7.png)

## 构建主学生字典

![](img/503acde6669ea7ded2286aff59887689_8.png)

上一节我们为每个学生创建了独立的字典。本节中，我们将把这些学生字典组织到一个主字典中，以便统一管理。我们将使用唯一的字符串ID（如`"1"`, `"2"`, `"3"`）作为键，对应的学生字典作为值。

```python
students = {
    "1": billy,
    "2": sarah,
    "3": ben
}
```

![](img/503acde6669ea7ded2286aff59887689_10.png)

---

![](img/503acde6669ea7ded2286aff59887689_12.png)

## 访问字典信息

现在我们已经有了结构化的数据，接下来看看如何从中获取信息。

### 获取学生总数

我们可以使用`len()`函数获取主字典中键的数量，即学生总数。

```python
num_students = len(students)
print(f"There are {num_students} students.")
# 输出：There are 3 students.
```

![](img/503acde6669ea7ded2286aff59887689_14.png)

### 获取所有学生ID

![](img/503acde6669ea7ded2286aff59887689_16.png)

有两种方法可以获取所有学生ID（即主字典的所有键）。

**方法一：使用 `.keys()` 方法**
`.keys()`方法返回一个包含所有键的视图对象。

![](img/503acde6669ea7ded2286aff59887689_18.png)

```python
student_ids = students.keys()
print(student_ids)  # 输出：dict_keys(['1', '2', '3'])
```

![](img/503acde6669ea7ded2286aff59887689_19.png)

![](img/503acde6669ea7ded2286aff59887689_20.png)

**方法二：直接遍历字典**
直接遍历字典会默认遍历其键。

```python
for key in students:
    print(key)
# 输出：
# 1
# 2
# 3
```

![](img/503acde6669ea7ded2286aff59887689_22.png)

![](img/503acde6669ea7ded2286aff59887689_23.png)

### 获取特定学生的信息

我们可以通过键来访问嵌套字典中的值。

**获取Billy的出勤记录：**
```python
billy_info = students["1"]  # 获取ID为“1”的学生字典
billy_attendance = billy_info["attendance"] # 从该字典中获取“attendance”键的值
print(billy_attendance)  # 输出：[True, True, True, True, True]
```

**获取Sarah的成绩：**
```python
sarah_grades = students["2"]["grades"] # 链式访问
print(sarah_grades)  # 输出：[0, 99, 0, 100]
```

### 获取一个学生的所有信息

要获取一个学生字典中的所有键值对，可以使用`.items()`方法。它返回一个包含`(键, 值)`元组的视图对象。

以下是获取Ben所有信息的代码：

```python
ben_info = students["3"]  # 获取Ben的字典
ben_items = ben_info.items() # 获取该字典的所有键值对

for key, value in ben_items:
    print(f"{key}: {value}")
# 输出：
# name: Ben
# grades: [60, 82, 71, 92, 100]
# attendance: [False, False, False, False, False]
```

![](img/503acde6669ea7ded2286aff59887689_25.png)

---

## 计算所有学生的平均成绩

上一节我们学习了如何访问单个学生的数据。本节中，我们将遍历所有学生，计算他们所有成绩的平均分。这里介绍两种方法。

![](img/503acde6669ea7ded2286aff59887689_27.png)

**方法一：遍历并收集所有成绩**
思路是创建一个空列表，然后遍历每个学生，将他们的成绩列表中的每一项逐个添加到总列表中。

![](img/503acde6669ea7ded2286aff59887689_29.png)

```python
grades = []  # 用于存放所有成绩的空列表

# 遍历主字典的所有键值对（学生ID和对应的学生字典）
for student_id, student_dict in students.items():
    # 遍历当前学生字典中“grades”键对应的列表
    for grade in student_dict["grades"]:
        grades.append(grade) # 将每个成绩添加到总列表

# 计算平均分：总和 / 数量
average_grade = sum(grades) / len(grades)
print(f"Average grade for all assignments is {round(average_grade)}")
# 输出：Average grade for all assignments is 69
```

**方法二：直接拼接成绩列表**
这种方法更简洁。我们同样创建一个空列表，但在内层循环中，我们不是遍历成绩再添加，而是直接将整个成绩列表“拼接”到总列表的末尾。

```python
grades_concatenated = []  # 用于存放所有成绩的空列表

for student_id, student_dict in students.items():
    # 直接将当前学生的成绩列表整体添加到总列表末尾
    grades_concatenated += student_dict["grades"]

average_grade = sum(grades_concatenated) / len(grades_concatenated)
print(f"Average grade for all assignments is {round(average_grade)}")
# 输出：Average grade for all assignments is 69
```

![](img/503acde6669ea7ded2286aff59887689_31.png)

---

![](img/503acde6669ea7ded2286aff59887689_33.png)

## 总结

![](img/503acde6669ea7ded2286aff59887689_35.png)

本节课中我们一起完成了一个综合练习，创建并操作了一个“成绩考勤簿”。我们实践了以下核心操作：
1.  **创建嵌套字典**：构建了`学生字典 -> 主字典`的两层结构。
2.  **访问数据**：使用键来获取特定学生的信息，如`students["1"]["attendance"]`。
3.  **遍历字典**：使用`.keys()`、`.items()`方法和`for`循环来获取键、值或键值对。
4.  **数据计算**：通过遍历所有学生，收集并计算了全体学生的平均成绩。

![](img/503acde6669ea7ded2286aff59887689_37.png)

这个练习很好地展示了字典在组织和管理结构化数据方面的强大能力。