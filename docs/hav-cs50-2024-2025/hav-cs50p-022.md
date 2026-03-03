# Python编程入门：P22：While循环 🔄

![](img/edb4e446c3609869d05ac1eb47a88aaf_0.png)

在本节课中，我们将要学习Python中的`while`循环。`while`循环是一种强大的控制流工具，它允许我们在某个条件为真时，重复执行一段代码。我们将通过一个给植物浇水的实际例子，来理解它的工作原理和应用场景。

## 概述

生活中充满了不确定性。例如，我最近需要照顾一株植物，它对浇水的时机和水质都很挑剔。我需要在土壤干燥但又不至于太干的时候给它浇水。因此，我每天都需要检查土壤的湿度，以决定是否需要浇水。为了提醒自己，我决定编写一个程序。

我了解到，土壤湿度是以百分比来衡量的。当湿度达到20%或更低时，土壤就被认为是干燥的，需要浇水。理想情况下，这个程序可以每天为我检查一次土壤湿度，并在需要时提醒我。

## 程序初始版本

我创建了一个名为`water.py`的程序。它使用了一个我预先写好的名为`sample`的函数。这个函数的作用是模拟检测土壤，并返回当天检测到的土壤湿度百分比。

我的主程序如下：
```python
moisture = sample()
print(f"Moisture: {moisture}%")
```
运行这个程序（`python water.py`），我看到今天的湿度是28%，还不需要浇水。

但这里有一个问题：这个程序只为我检查了一次。我希望它能持续检查，在土壤仍然湿润时不断检测，直到土壤变干，然后提醒我该浇水了。

## 引入While循环

请注意我的描述：我希望**当**某个条件为真时，**持续**做某事。这正是`while`循环的用武之地。`while`循环非常适合在我不确定需要循环多少次，但希望在某个条件为真时持续执行的情况下使用。

因此，我决定更新程序，使其更动态。我希望在湿度大于20%（即土壤仍然湿润）时，持续执行检测和报告的操作。

更新后的程序结构如下：
```python
moisture = sample()
print(f"Moisture: {moisture}%")

while moisture > 20:
    moisture = sample()
    print(f"Moisture: {moisture}%")

print("Time to water!")
```
程序首先检测一次土壤湿度并报告。然后，只要`moisture > 20`这个条件为真，`while`循环内部的代码（缩进的部分）就会重复执行：再次检测并报告湿度。一旦条件不再为真（即湿度小于或等于20%），程序就会退出循环，并打印出“Time to water!”的提醒。

## 运行示例

让我们运行这个程序看看效果。为了模拟每天检测一次，程序会连续运行多次。

第一次运行，我们可能看到这样的输出：
```
Moisture: 34%
Moisture: 31%
Moisture: 27%
Moisture: 23%
Moisture: 22%
Moisture: 18%
Time to water!
```
只要湿度大于20%，循环就会继续。当检测到湿度为18%时，条件`moisture > 20`变为假，循环结束，并发出浇水提醒。

再次运行程序，由于土壤湿度变化是随机的（受天气、日照等影响），结果可能不同：
```
Moisture: 29%
Moisture: 25%
Moisture: 19%
Time to water!
```
这次只循环了三天。

`while`循环的魅力在于，无论这个过程需要四天、两天还是五天，它都会在条件不再为真时准确结束。

## 添加循环计数器

为了让过程更清晰，我们可以添加一个变量`days`来记录天数。

以下是改进后的程序：
```python
days = 0
moisture = sample()
print(f"Day {days}: Moisture: {moisture}%")

while moisture > 20:
    days += 1
    moisture = sample()
    print(f"Day {days}: Moisture: {moisture}%")

print("Time to water! Your soil is getting too dry.")
```
现在，运行程序时，我们可以看到每次检测发生在第几天：
```
Day 0: Moisture: 34%
Day 1: Moisture: 31%
Day 2: Moisture: 27%
Day 3: Moisture: 23%
Day 4: Moisture: 22%
Day 5: Moisture: 18%
Time to water! Your soil is getting too dry.
```
这次循环持续了5天（从第0天到第5天）。每次运行，天数都可能不同，这再次体现了`while`循环处理不确定循环次数的能力。

## 总结

本节课我们一起学习了`while`循环。

*   `while`循环的语法是：`while condition:`，后面跟着缩进的代码块。
*   它的核心作用是：**当**某个条件为真时，**重复执行**缩进块内的代码。
*   它非常适合用在你不确定需要循环多少次，但循环的**终止条件很明确**的场景中。例如：
    *   等待用户输入特定指令。
    *   处理数据直到达到某个状态。
    *   就像我们的例子一样，持续监测直到满足某个条件（土壤变干）。

![](img/edb4e446c3609869d05ac1eb47a88aaf_2.png)

![](img/edb4e446c3609869d05ac1eb47a88aaf_3.png)

通过给植物浇水的生动例子，我们看到了`while`循环如何将不确定的、重复性的任务自动化，并在恰当时机做出判断。