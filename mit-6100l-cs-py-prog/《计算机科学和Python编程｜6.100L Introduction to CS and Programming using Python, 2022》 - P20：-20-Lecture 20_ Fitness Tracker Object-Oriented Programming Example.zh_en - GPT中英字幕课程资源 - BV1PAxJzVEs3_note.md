# 计算机科学和Python编程：20：面向对象编程示例 - 健身追踪器 🏃‍♂️💻

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_0.png)

在本节课中，我们将通过创建一个健身追踪器应用中的“锻炼”对象，深入学习面向对象编程。我们将从设计一个简单的锻炼类开始，逐步改进它，并最终利用继承的概念创建更具体的子类（如跑步锻炼）。我们将学习如何设计类、使用类变量、重写方法以及理解对象的状态字典。

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_2.png)

---

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_4.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_5.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_6.png)

## 设计蓝图与实例

在面向对象编程中，我们编写代码时有两种视角。第一种是设计视角，我们决定新对象（数据类型）的名称、属性（数据或过程）。第二种是使用视角，我们创建该类型的多个对象实例并操作它们。之前的课程我们主要在使用他人创建的对象，而现在我们学习如何创建自己的对象类型。

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_8.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_9.png)

## 创建简单的锻炼类

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_11.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_12.png)

首先，我们创建一个基础的 `Workout` 类。所有类型的锻炼（如跑步、游泳、骑行）都有一些共同属性，例如图标、种类、开始时间、结束时间、心率、距离和消耗的卡路里。在本教程中，我们的 `Workout` 类将实现其中核心的几个属性。

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_14.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_15.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_17.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_19.png)

以下是 `Workout` 类的初始设计，包含数据属性和方法。

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_21.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_22.png)

**数据属性**：
*   `start_time`：锻炼开始时间（字符串）。
*   `end_time`：锻炼结束时间（字符串）。
*   `calories`：消耗的卡路里数（数字）。

**方法**：
*   `__init__`：构造函数，用于初始化对象。
*   `get_calories`, `get_start_time`, `get_end_time`：获取器方法。
*   `set_calories`, `set_start_time`, `set_end_time`：设置器方法。
*   `__str__`：用于以友好格式打印锻炼信息。

让我们开始定义这个类。

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_24.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_25.png)

```python
class Workout:
    """一个表示健身锻炼的类。"""

    def __init__(self, start, end, calories):
        self.start = start
        self.end = end
        self.calories = calories
        self.icon = "💦"  # 默认图标
        self.kind = "Workout"  # 默认种类

    # 获取器方法
    def get_calories(self):
        return self.calories

    def get_start_time(self):
        return self.start

    def get_end_time(self):
        return self.end

    # 设置器方法
    def set_calories(self, new_cal):
        self.calories = new_cal

    def set_start_time(self, new_start):
        self.start = new_start

    def set_end_time(self, new_end):
        self.end = new_end
```

创建对象实例：
```python
my_workout = Workout("Sep 1, 2022 1:35 PM", "Sep 1, 2022 1:45 PM", 200)
```

## 探索类与对象的状态

在Python中，类定义本身也是一个对象，拥有一个“状态字典”（`__dict__`），其中存储了类中定义的所有方法和类变量。同样，每个对象实例也有自己的状态字典，存储其数据属性的具体值。

查看类的状态字典：
```python
print(list(Workout.__dict__.keys()))
# 输出可能包含：['__module__', '__init__', 'get_calories', ... , '__dict__', '__weakref__']
```

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_27.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_29.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_31.png)

查看对象实例的状态字典：
```python
print(my_workout.__dict__)
# 输出：{'start': 'Sep 1, 2022 1:35 PM', 'end': 'Sep 1, 2022 1:45 PM', 'calories': 200, 'icon': '💦', 'kind': 'Workout'}
```

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_32.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_34.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_36.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_37.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_39.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_40.png)

访问属性时，应优先使用获取器方法（如 `my_workout.get_calories()`）而非直接访问数据属性（如 `my_workout.calories`）。这遵循了信息隐藏和抽象的原则，即使底层实现改变，使用方法的代码也无需修改。

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_42.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_44.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_46.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_48.png)

## 改进锻炼类：类变量与智能卡路里估算

上一节我们创建了一个简单的锻炼类。本节中，我们将改进它，引入类变量，并让 `get_calories` 方法更智能：如果用户创建对象时未提供卡路里数，则根据锻炼时长进行估算。

主要改进点：
1.  添加类变量 `CAL_PER_HOUR`，表示每小时消耗的卡路里基数。
2.  修改 `__init__` 方法，使 `calories` 参数可选（默认值为 `None`）。
3.  修改 `get_calories` 方法：如果卡路里有具体值则直接返回；如果为 `None`，则根据时长和 `CAL_PER_HOUR` 估算。
4.  使用 `datetime` 库更精确地处理时间，计算时长。

改进后的类定义如下：

```python
from datetime import datetime
from dateutil import parser

class Workout:
    """一个改进后的健身锻炼类，支持卡路里估算。"""
    CAL_PER_HOUR = 200  # 类变量：每小时消耗卡路里

    def __init__(self, start, end, calories=None):
        # 将字符串时间解析为datetime对象，便于计算
        self.start = parser.parse(start)
        self.end = parser.parse(end)
        self.calories = calories  # 可能是None
        self.icon = "💦"
        self.kind = "Workout"

    def get_calories(self):
        if self.calories is None:
            # 估算卡路里：时长(小时) * CAL_PER_HOUR
            duration = self.end - self.start  # 得到timedelta对象
            hours = duration.total_seconds() / 3600
            estimated_cal = hours * Workout.CAL_PER_HOUR
            return estimated_cal
        else:
            return self.calories

    # ... 其他获取器和设置器方法保持不变 ...
```

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_50.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_52.png)

**关于 `datetime` 库**：`parser.parse()` 函数可以将多种格式的日期时间字符串转换为 `datetime` 对象。两个 `datetime` 对象相减得到一个 `timedelta` 对象（表示时间间隔），其 `total_seconds()` 方法可以获取总秒数。

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_54.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_55.png)

类变量 `CAL_PER_HOUR` 可以通过类名（`Workout.CAL_PER_HOUR`）或实例（`my_workout.CAL_PER_HOUR`）访问。但应注意，最佳实践是通过类内部的方法来访问或修改它，而不是直接在类外部操作，以保持封装性。

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_57.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_58.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_59.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_60.png)

让我们实践一下，创建两个锻炼对象：

```python
# 对象1：不提供卡路里，让其估算
w1 = Workout("Jan 1, 2001 3:30 PM", "Jan 1, 2001 4:00 PM")
print(w1.get_calories())  # 输出: 100.0 (0.5小时 * 200)

# 对象2：提供具体卡路里值
w2 = Workout("Jan 1, 2001 3:30 PM", "Jan 1, 2001 4:00 PM", 300)
print(w2.get_calories())  # 输出: 300
```

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_62.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_63.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_65.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_67.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_69.png)

## 使用继承创建子类：RunWorkout

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_71.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_72.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_73.png)

我们已经有了一个通用的 `Workout` 类。现在，假设我们需要一个专门针对跑步的锻炼类 `RunWorkout`。跑步锻炼具有通用锻炼的所有属性，但可能还有额外的属性（如海拔爬升）或不同的行为。这时，我们可以使用继承。

`RunWorkout` 类将：
1.  继承自 `Workout` 类（它是 `Workout` 的子类）。
2.  在初始化时，调用父类的 `__init__` 方法完成基础设置，然后覆盖图标和种类，并添加新的数据属性 `elevation`（海拔）。
3.  添加 `get_elevation` 和 `set_elevation` 方法。
4.  后续我们还会重写和添加其他方法。

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_75.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_76.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_78.png)

以下是 `RunWorkout` 类的初步实现：

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_79.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_81.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_82.png)

```python
class RunWorkout(Workout):  # 继承自Workout
    """表示跑步锻炼的子类。"""

    def __init__(self, start, end, elevation=0, calories=None):
        # 调用父类的__init__方法初始化通用属性
        super().__init__(start, end, calories)
        # 覆盖父类的图标和种类
        self.icon = "🏃"
        self.kind = "Running"
        # 添加子类特有的属性
        self.elevation = elevation

    def get_elevation(self):
        return self.elevation

    def set_elevation(self, new_elev):
        self.elevation = new_elev
```

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_84.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_85.png)

**关键点**：
*   `class RunWorkout(Workout):` 表示 `RunWorkout` 继承自 `Workout`。
*   `super().__init__(start, end, calories)` 调用父类的构造函数，避免了代码重复。
*   子类自动拥有父类的所有方法（如 `get_calories`），除非子类重写了它们。

创建跑步锻炼对象：
```python
rw1 = RunWorkout("Sep 1, 2022 2:00 PM", "Sep 1, 2022 3:00 PM", elevation=150)
print(rw1.get_calories())  # 继承的方法，估算卡路里
print(rw1.get_elevation()) # 子类特有的方法
```

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_87.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_89.png)

## 方法的重用、重写与添加

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_91.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_92.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_93.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_95.png)

在继承体系中，子类可以以三种方式对待父类的方法：
1.  **完全重用**：直接使用父类实现的方法。
2.  **重写**：提供自己的实现，覆盖父类的方法。
3.  **添加**：定义父类中没有的新方法。

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_97.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_99.png)

### 1. 重用父类方法：`__str__`

我们可以在父类 `Workout` 中实现一个 `__str__` 方法，用于以美观的格式打印锻炼信息。由于继承，`RunWorkout` 对象会自动使用这个 `__str__` 方法，无需在子类中重写。

`Workout` 类中的 `__str__` 方法（示例，非完整代码）：
```python
def __str__(self):
    # 构建一个字符串，包含图标、种类、时长、卡路里等信息
    duration = self.end - self.start
    cal = self.get_calories()
    return f"{self.icon} {self.kind}\nDuration: {duration}\nCalories: {cal:.0f}"
```
打印任何 `Workout` 或其子类的对象时，都会调用此方法。

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_101.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_102.png)

### 2. 重写父类方法：`get_calories`

对于 `RunWorkout`，我们可能想用更精确的方式计算卡路里，例如根据GPS轨迹点计算总距离，然后乘以一个“每公里卡路里”系数。为此，我们可以在 `RunWorkout` 类中重写 `get_calories` 方法。

```python
class RunWorkout(Workout):
    CAL_PER_KM = 60  # 类变量：每公里消耗卡路里

    def get_calories(self, gps_points=[]):
        """计算卡路里。如果提供了GPS点列表，则根据距离计算；否则使用父类方法估算。"""
        if not gps_points:
            # 没有GPS数据，则调用父类的估算方法
            return super().get_calories()
        else:
            # 根据GPS点计算总距离（假设有辅助函数gps_distance）
            total_km = 0
            for i in range(len(gps_points)-1):
                pt1 = gps_points[i]
                pt2 = gps_points[i+1]
                total_km += gps_distance(pt1, pt2)  # 假设的函数
            # 根据距离计算卡路里
            estimated_cal = total_km * RunWorkout.CAL_PER_KM
            return estimated_cal
```
**关键点**：
*   子类定义了与父类同名的方法 `get_calories`，这构成了重写。
*   在重写的方法中，可以通过 `super().get_calories()` 调用父类原本的实现。
*   这样，`RunWorkout` 对象在调用 `get_calories` 时，会根据是否提供 `gps_points` 参数决定使用哪种计算方式。

### 3. 添加新方法并重写：`__eq__`

我们还可以添加父类中没有的方法。例如，我们想比较两个锻炼对象是否相等。可以在父类 `Workout` 中实现 `__eq__` 方法，规定比较规则（如类型相同、开始时间、结束时间、卡路里均相同则相等）。然后在子类 `RunWorkout` 中重写它，在父类比较规则的基础上，额外要求 `elevation` 属性也相同。

`Workout` 类中的 `__eq__` 方法：
```python
def __eq__(self, other):
    if type(self) != type(other):
        return False
    return (self.start == other.start and
            self.end == other.end and
            self.get_calories() == other.get_calories())
```

`RunWorkout` 类中重写的 `__eq__` 方法：
```python
def __eq__(self, other):
    # 先使用父类的比较逻辑
    parent_check = super().__eq__(other)
    # 再额外检查海拔是否相等
    return parent_check and (self.elevation == other.elevation)
```
这样，`RunWorkout` 对象的相等性判断既包含了通用规则，也包含了特有规则。

## 多态与类型检查

由于继承关系，`RunWorkout` 对象也是 `Workout` 类型。这意味着，一个期望接收 `Workout` 对象列表的函数，也可以安全地接收 `RunWorkout` 对象列表。这体现了“子类是父类”的多态思想。

例如，一个计算总卡路里的函数：
```python
def total_calories(workout_list):
    total = 0
    for w in workout_list:
        total += w.get_calories()  # 无论w是Workout还是RunWorkout，都能调用get_calories
    return total
```

但是，反过来则不成立。一个专门为 `RunWorkout` 设计、需要调用 `get_elevation` 的函数，如果传入普通的 `Workout` 对象，则会出错，因为 `Workout` 没有这个方法。

## 总结

本节课中，我们一起学习了如何通过一个健身追踪器的例子深入实践面向对象编程。

我们首先设计并实现了一个基础的 `Workout` 类，理解了构造函数、数据属性和方法。接着，我们改进了这个类，引入了类变量 `CAL_PER_HOUR`，并实现了更智能的 `get_calories` 方法，使其能够在用户未提供数据时进行估算，同时学习了使用 `datetime` 库处理时间。

然后，我们进入了继承的核心主题，创建了 `RunWorkout` 子类。我们看到了如何通过 `super()` 调用父类方法，如何添加子类特有的属性（`elevation`）和方法。我们还深入探讨了方法的三种处理方式：重用父类的 `__str__` 方法、重写 `get_calories` 方法以支持基于GPS的精确计算，以及重写 `__eq__` 方法来实现子类特有的相等性判断。

最后，我们讨论了多态的概念，理解了子类对象可以用于任何期望父类对象的上下文中，这提高了代码的灵活性和可复用性。

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_104.png)

![](img/f6eb7cd66f416fb88dc7cd2d7934b2e9_106.png)

面向对象编程的核心思想——封装、继承和多态——通过这个逐步构建的示例得到了生动的体现。掌握这些概念后，你将能够设计出结构清晰、易于维护和扩展的复杂程序。