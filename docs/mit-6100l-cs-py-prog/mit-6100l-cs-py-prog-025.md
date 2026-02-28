# 025：数据可视化 📊

![](img/c1f3dd4c058738be1c0c627d923b1011_0.png)

在本节课中，我们将要学习如何使用Python的`matplotlib`库进行数据绘图。数据可视化是理解和分析数据的关键步骤，无论是在学术研究、项目报告还是日常工作中都非常有用。我们将从基础绘图开始，逐步学习如何自定义图表、处理真实数据集，并通过可视化来发现数据中的模式和趋势。

## 导入库与基础概念

首先，我们需要导入绘图库。在Python中，最常用的基础绘图库是`matplotlib`。为了简化代码，我们通常会给它起一个简短的别名。

```python
import matplotlib.pyplot as plt
```

![](img/c1f3dd4c058738be1c0c627d923b1011_2.png)

上述代码将`matplotlib.pyplot`模块导入，并重命名为`plt`。这样，我们就可以使用`plt.`来调用库中的所有函数，使代码更加简洁。

![](img/c1f3dd4c058738be1c0c627d923b1011_4.png)

## 绘制基础图形

![](img/c1f3dd4c058738be1c0c627d923b1011_6.png)

要绘制一个图形，我们需要提供两组数据：X轴的值和Y轴的值。这两组数据通常是长度相同的列表，列表中的每个索引位置共同构成一个坐标点。

![](img/c1f3dd4c058738be1c0c627d923b1011_8.png)

以下是创建和绘制几组基础数据的示例：

```python
# 创建X轴数据：0到29的整数
x_vals = list(range(30))

# 创建不同的Y轴数据：线性、二次方、三次方和指数函数
linear = [n for n in x_vals]
quadratic = [n**2 for n in x_vals]
cubic = [n**3 for n in x_vals]
exponential = [1.5**n for n in x_vals]

# 绘制线性图
plt.plot(x_vals, linear)
plt.show()
```

运行上述代码会弹出一个窗口，显示一条从(0,0)到(29,29)的直线。`matplotlib`会自动调整坐标轴的范围，使图形能够完整且美观地显示在画布中。

默认情况下，`plt.plot()`会用线段连接所有的数据点。如果数据点的顺序是混乱的，连接线可能会显得杂乱无章。

## 散点图与数据点顺序

当数据点没有特定的顺序，或者你只想观察数据点的分布而非趋势时，散点图是更好的选择。

![](img/c1f3dd4c058738be1c0c627d923b1011_10.png)

```python
# 创建无序的X和Y数据
test_x = [0, 5, 3, 2, 8, 1]
test_y = [0, 25, 9, 4, 64, 1]  # 对应x值的平方

![](img/c1f3dd4c058738be1c0c627d923b1011_12.png)

# 绘制散点图
plt.scatter(test_x, test_y)
plt.show()
```

![](img/c1f3dd4c058738be1c0c627d923b1011_14.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_16.png)

使用`plt.scatter()`可以只绘制数据点而不进行连接，这样即使数据无序，图形也能正确显示。

## 在同一图形中绘制多条线

你可以通过连续调用`plt.plot()`命令，将多条线绘制在同一个图形窗口中。

```python
plt.plot(x_vals, linear)
plt.plot(x_vals, quadratic)
plt.plot(x_vals, cubic)
plt.plot(x_vals, exponential)
plt.show()
```

所有线条都会被添加到当前激活的图形中。但是，当不同线条的数据尺度差异很大时（比如线性增长和指数增长），将它们放在同一张图上可能不利于观察细节。

## 创建多个图形窗口

![](img/c1f3dd4c058738be1c0c627d923b1011_18.png)

为了更清晰地比较不同尺度的数据，我们可以创建多个独立的图形窗口。

![](img/c1f3dd4c058738be1c0c627d923b1011_20.png)

```python
# 创建第一个图形窗口并绘制指数数据
plt.figure('Exponential')
plt.plot(x_vals, exponential)

![](img/c1f3dd4c058738be1c0c627d923b1011_22.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_23.png)

# 创建第二个图形窗口并绘制线性数据
plt.figure('Linear')
plt.plot(x_vals, linear)

# 再次激活第一个窗口，并添加另一条指数曲线
plt.figure('Exponential')
plt.plot(x_vals, [1.6**n for n in x_vals])
plt.show()
```

`plt.figure(‘窗口名称’)`命令可以创建或激活一个指定名称的图形窗口。后续的绘图命令会作用于当前激活的窗口。

## 添加图表标签和自定义坐标轴

![](img/c1f3dd4c058738be1c0c627d923b1011_25.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_26.png)

一个专业的图表必须包含清晰的标题和坐标轴标签。我们还可以自定义坐标轴的范围和刻度。

```python
# 模拟月度温度数据
months = range(1, 13)
temps = [30, 35, 40, 50, 60, 70, 75, 73, 65, 55, 45, 35]

plt.plot(months, temps)

# 添加标题和坐标轴标签
plt.title('Average Monthly Temperature')
plt.xlabel('Month')
plt.ylabel('Temperature (F)')

# 设置X轴范围，去掉两边的空白
plt.xlim(1, 12)

![](img/c1f3dd4c058738be1c0c627d923b1011_28.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_29.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_31.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_32.png)

# 设置X轴刻度为每个月，并用月份名称标注
month_names = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec']
plt.xticks(months, month_names)

![](img/c1f3dd4c058738be1c0c627d923b1011_34.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_35.png)

plt.show()
```

通过这些自定义，图表变得信息丰富且易于理解。

## 绘制多条数据线并添加图例

![](img/c1f3dd4c058738be1c0c627d923b1011_37.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_39.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_41.png)

当一张图中有多条数据线时，添加图例至关重要。我们需要在绘图时为每条线指定一个标签，然后调用`plt.legend()`来显示图例。

![](img/c1f3dd4c058738be1c0c627d923b1011_43.png)

```python
boston_temps = [30, 32, 40, 50, 60, 70, 75, 73, 65, 55, 45, 35]
phoenix_temps = [55, 58, 65, 73, 82, 92, 95, 93, 88, 78, 65, 56]

![](img/c1f3dd4c058738be1c0c627d923b1011_45.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_46.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_48.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_49.png)

plt.plot(months, boston_temps, label='Boston')
plt.plot(months, phoenix_temps, label='Phoenix')

![](img/c1f3dd4c058738be1c0c627d923b1011_51.png)

plt.title('Average Monthly Temperature Comparison')
plt.xlabel('Month')
plt.ylabel('Temperature (F)')
plt.xticks(months, month_names)
plt.legend(loc='best')  # 自动选择最佳位置放置图例
plt.show()
```

![](img/c1f3dd4c058738be1c0c627d923b1011_53.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_55.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_56.png)

## 自定义线条样式、颜色和标记

![](img/c1f3dd4c058738be1c0c627d923b1011_58.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_59.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_60.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_61.png)

`matplotlib`允许你精细控制线条的外观，包括颜色、线型和数据点标记。

以下是自定义样式的两种方法：

![](img/c1f3dd4c058738be1c0c627d923b1011_63.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_65.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_67.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_68.png)

**1. 简写参数法：**
```python
plt.plot(months, boston_temps, ‘b-‘, label=‘Boston‘) # 蓝色实线
plt.plot(months, phoenix_temps, ‘r--‘, label=‘Phoenix‘) # 红色虚线
```

**2. 显式参数法：**
```python
plt.plot(months, boston_temps, color=‘b‘, linestyle=‘-‘, label=‘Boston‘)
plt.plot(months, phoenix_temps, color=‘r‘, linestyle=‘--‘, label=‘Phoenix‘)
```

你还可以添加数据点标记和调整线宽：

![](img/c1f3dd4c058738be1c0c627d923b1011_70.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_71.png)

```python
plt.plot(months, boston_temps, ‘b.-‘, linewidth=1, label=‘Boston‘) # 蓝色实线，带圆点标记，细线
plt.plot(months, phoenix_temps, ‘ro--‘, linewidth=3, label=‘Phoenix‘) # 红色虚线，带圆圈标记，粗线
```

![](img/c1f3dd4c058738be1c0c627d923b1011_73.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_75.png)

## 创建子图

![](img/c1f3dd4c058738be1c0c627d923b1011_77.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_78.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_79.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_81.png)

子图允许你在一个图形窗口中并排显示多个图表，便于比较。

![](img/c1f3dd4c058738be1c0c627d923b1011_83.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_84.png)

```python
# 创建一个2行1列的子图布局，并激活第一个子图（顶部）
plt.subplot(2, 1, 1)
plt.plot(months, boston_temps, ‘b-‘)
plt.title(‘Boston‘)
plt.ylim(0, 100) # 统一Y轴范围以便比较

![](img/c1f3dd4c058738be1c0c627d923b1011_86.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_88.png)

# 激活第二个子图（底部）
plt.subplot(2, 1, 2)
plt.plot(months, phoenix_temps, ‘r--‘)
plt.title(‘Phoenix‘)
plt.ylim(0, 100)

plt.tight_layout() # 自动调整子图参数，使之填充整个图像区域
plt.show()
```

`plt.subplot(行数, 列数, 序号)`用于指定子图的位置。序号从1开始，按行优先计数。

## 分析真实数据集：美国人口

现在，让我们将所学应用于真实数据。我们将读取一个包含美国400年间每十年人口数据的文件，并绘制图表。

首先，我们需要编写函数来读取和处理数据文件：

```python
def read_population_data(filename):
    """读取人口数据文件，返回年份列表和人口列表。"""
    dates = []
    populations = []
    with open(filename, ‘r‘) as f:
        for line in f:
            # 移除非数字字符（如逗号），只保留数字和空格
            line = ‘‘.join([c for c in line if c.isdigit() or c == ‘ ‘])
            parts = line.split()
            if len(parts) == 2:
                year, pop = parts
                dates.append(int(year))
                populations.append(int(pop))
    return dates, populations

![](img/c1f3dd4c058738be1c0c627d923b1011_90.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_91.png)

# 使用函数读取数据并绘图
years, population = read_population_data(‘us_population.txt‘)
plt.plot(years, population)
plt.title(‘US Population Over Time‘)
plt.xlabel(‘Year‘)
plt.ylabel(‘Population‘)
plt.show()
```

通过可视化，我们可以轻松发现历史事件对人口的影响，例如战争导致的人口增长放缓。

![](img/c1f3dd4c058738be1c0c627d923b1011_93.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_95.png)

## 对数尺度绘图

![](img/c1f3dd4c058738be1c0c627d923b1011_97.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_98.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_99.png)

对于呈指数级增长的数据，使用对数尺度（Log Scale）Y轴可以更清晰地观察增长趋势。

![](img/c1f3dd4c058738be1c0c627d923b1011_101.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_103.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_104.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_106.png)

```python
plt.plot(years, population)
plt.yscale(‘log‘) # 将Y轴设置为对数尺度
plt.title(‘US Population Over Time (Log Scale)‘)
plt.xlabel(‘Year‘)
plt.ylabel(‘Population (Log)‘)
plt.show()
```

在对数图上，指数增长会显示为一条直线，这使得我们能够识别出数据中不同阶段的增长速率。

## 深入分析：本福特定律

![](img/c1f3dd4c058738be1c0c627d923b1011_108.png)

我们来看一个有趣的数据集：各国人口排名。我们将分析各国人口数字的**首位数字**的分布。

```python
def read_country_populations(filename):
    """读取国家人口文件，返回人口数字列表。"""
    populations = []
    with open(filename, ‘r‘) as f:
        for line in f:
            parts = line.split(‘\t‘) # 制表符分隔
            if len(parts) >= 3:
                pop_str = parts[2] # 人口数据在第三列
                # 移除逗号并转换为整数
                pop_num = int(‘‘.join([c for c in pop_str if c.isdigit()]))
                populations.append(pop_num)
    return populations

# 获取人口数据并提取首位数字
pops = read_country_populations(‘country_populations.txt‘)
first_digits = [int(str(p)[0]) for p in pops] # 提取每个数字的首位

# 绘制首位数字的直方图
plt.hist(first_digits, bins=range(1, 11), edgecolor=‘black‘, align=‘left‘)
plt.title(‘First Digit Distribution of Country Populations‘)
plt.xlabel(‘First Digit‘)
plt.ylabel(‘Frequency‘)
plt.xticks(range(1, 10))
plt.show()
```

![](img/c1f3dd4c058738be1c0c627d923b1011_110.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_112.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_114.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_116.png)

令人惊讶的是，首位数字的分布并不均匀。数字1出现的频率最高（约30%），而数字9出现的频率最低。这符合**本福特定律**，该定律描述了在许多自然产生的数据集中，较小数字作为首位数字出现的概率更高。其公式为：

![](img/c1f3dd4c058738be1c0c627d923b1011_118.png)

**P(d) = log₁₀(1 + 1/d)**

其中，`d`是1到9的数字，`P(d)`是该数字作为首位出现的概率。

## 分析城市温度趋势

最后，我们分析一个更复杂的数据集：多个城市长达55年的每日温度数据。我们将计算每个城市的年平均温度，并观察其变化趋势。

```python
def get_yearly_averages(filename, city_name):
    """获取指定城市每年的平均温度。"""
    yearly_temps = {}
    with open(filename, ‘r‘) as f:
        for line in f:
            parts = line.strip().split(‘,‘)
            if len(parts) == 3:
                city, temp_str, date_str = parts
                if city == city_name:
                    year = date_str[:4] # 从日期中提取年份
                    temp_f = celsius_to_fahrenheit(float(temp_str)) # 假设有转换函数
                    yearly_temps.setdefault(year, []).append(temp_f)
    # 计算每年的平均温度
    avg_temps = {year: sum(temps)/len(temps) for year, temps in yearly_temps.items()}
    # 按年份排序并返回列表
    sorted_years = sorted(avg_temps.keys())
    sorted_avgs = [avg_temps[yr] for yr in sorted_years]
    return sorted_years, sorted_avgs

![](img/c1f3dd4c058738be1c0c627d923b1011_120.png)

# 比较四个城市的温度趋势
cities = [‘Boston‘, ‘San Diego‘, ‘Phoenix‘, ‘Miami‘]
for city in cities:
    years, avgs = get_yearly_averages(‘global_temperatures.csv‘, city)
    plt.plot(years, avgs, label=city)

plt.title(‘Average Yearly Temperature Trend‘)
plt.xlabel(‘Year‘)
plt.ylabel(‘Temperature (F)‘)
plt.legend()
plt.show()
```

![](img/c1f3dd4c058738be1c0c627d923b1011_122.png)

通过可视化，我们可以直观地比较不同城市的变暖趋势和温度波动范围。

![](img/c1f3dd4c058738be1c0c627d923b1011_124.png)

## 总结

本节课中我们一起学习了使用`matplotlib`库进行数据可视化的核心技能。我们从最基本的绘制线条和散点图开始，逐步学会了如何添加标签、图例，自定义线条样式，以及创建子图来组织多个图表。更重要的是，我们应用这些技能分析了真实世界的数据集，如美国人口变化和各国人口的首位数字分布（本福特定律），并通过可视化发现了数据中隐藏的模式和趋势。

![](img/c1f3dd4c058738be1c0c627d923b1011_126.png)

![](img/c1f3dd4c058738be1c0c627d923b1011_128.png)

记住，可视化的目的不仅仅是生成漂亮的图片，更是为了探索数据、提出问题并传达信息。当你面对新的数据集时，第一步就应该是将其可视化，这通常会为你带来最初也是最关键的洞察。