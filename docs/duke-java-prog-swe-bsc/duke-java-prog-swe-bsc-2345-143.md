# 143：基于距离的Comparator实现

![](img/05a42f0b4bf2184267cdeaa2238b4f32_0.png)

![](img/05a42f0b4bf2184267cdeaa2238b4f32_0.png)

在本节课中，我们将学习如何编写一个基于距离的Comparator，用于根据地震事件与特定位置的距离来对它们进行排序。

我们将创建一个名为`DistanceComparator`的类，它实现了`Comparator<QuakeEntry>`接口。这个类将包含一个表示参考位置的变量`fromWhere`，并通过构造函数初始化。核心任务是实现`compare`方法，该方法会比较两个地震事件到参考位置的距离。

## 实现DistanceComparator类

上一节我们介绍了本课程的目标，本节中我们来看看如何具体实现`DistanceComparator`类。

首先，我们需要获取两个地震事件`q1`和`q2`各自的位置信息。接着，计算每个位置到参考位置`fromWhere`的距离。最后，使用`Double.compare`方法比较这两个距离值，并返回比较结果。

以下是`compare`方法的具体实现步骤：

1.  获取第一个地震事件`q1`的位置。
2.  计算该位置到参考位置`fromWhere`的距离，并存储在变量`distance1`中。
3.  获取第二个地震事件`q2`的位置。
4.  计算该位置到参考位置`fromWhere`的距离，并存储在变量`distance2`中。
5.  使用`Double.compare(distance1, distance2)`比较两个距离，并返回结果。

对应的核心代码如下：

```java
public int compare(QuakeEntry q1, QuakeEntry q2) {
    double distance1 = q1.getLocation().distanceTo(fromWhere);
    double distance2 = q2.getLocation().distanceTo(fromWhere);
    return Double.compare(distance1, distance2);
}
```

## 使用DistanceComparator进行排序

我们已经完成了比较器的编写，现在来看看如何在程序中使用它来对地震数据进行排序。

假设我们有一个`DistSorter`类，它读取了一系列地震数据，并希望根据它们到北卡罗来纳州达勒姆市的距离进行排序。在打印列表之前，我们需要使用`Collections.sort`方法并传入我们自定义的`DistanceComparator`。

以下是实现排序的关键步骤：

1.  创建一个`DistanceComparator`实例，并将参考位置（例如达勒姆市）作为参数传入构造函数。
2.  调用`Collections.sort`方法，传入地震数据列表和上一步创建的`DistanceComparator`实例。

对应的核心代码如下：

```java
Collections.sort(list, new DistanceComparator(where));
```

运行程序后，输出结果将按照地震发生地距离达勒姆市的远近进行排序，从最近到最远依次显示。

## 总结

本节课中我们一起学习了如何创建和使用一个基于自定义规则的Comparator。我们首先实现了`DistanceComparator`类，通过计算并比较地震事件到指定位置的距离来定义排序逻辑。然后，我们在主程序中利用`Collections.sort`方法和这个自定义比较器，成功地将地震数据按照与达勒姆市的距离进行了排序。通过这个练习，你掌握了实现`Comparator`接口来满足特定排序需求的方法。