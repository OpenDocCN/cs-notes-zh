# 175：平均评分计算教程 🎬

![](img/8eead52fe895adc9cb216bb232489d84_0.png)

在本节课中，我们将学习如何从一个电影评分列表中，筛选出有足够评分数据的电影，并计算它们的平均评分。这是一个结合了数据筛选、迭代和计算的经典编程问题。

## 问题概述

首先，我们需要处理一个电影列表。目标是检查列表中的每一部电影是否拥有足够数量的评分，以便计算出一个有意义的平均分。如果某部电影的评分数量达到要求，我们就计算它的平均评分。

由于您现在已经熟练掌握了解决问题的七个步骤，我们将不再逐步引导您开发算法。您应该能够独立完成。不过，我们会通过一个具体例子来确保您完全理解需要做什么。

![](img/8eead52fe895adc9cb216bb232489d84_2.png)

## 示例分析 🎥

我们将使用以下几部精彩的电影作为示例：
*   My blocklockbuster Cosera spinoff
*   Dude, Where‘s My Code
*   The Comedic Adventures of Owen and Robert Go to White Castle
*   The Thrilling Tale of Susan Roger and the Goblet of Java
*   以及我个人的最爱：Snow White and the Seven Step

现在，让我们查看列表中的第一部电影《Dude, Where‘s My Code》的评分情况：
*   Justin 给了 2 星。
*   Quinin 给了 3 星。
*   Genevieve 没有评分。
*   Nick 给了 4 星。
*   Mitch 给了 2 星。

因此，计算平均分时，我们有 (2 + 3 + 4 + 2) / 4 = 11 / 4 = **2.75**。

接下来看下一部电影《The Comedic Adventures of Owen and Robert Go to White Castle》，只有 Genevieve 一个人评分，她给了 5 星。但是，如果只有一条评分记录，我们可能认为其数据不足以作为可靠的推荐依据。

这就是您将要编写的方法中 **`minimumRater`** 参数的作用。它定义了需要多少条评分才能认为数据是有意义的。在本例中，我们设定至少需要**两条**评分，因此《Owen and Robert Go to White Castle》将不会包含在结果中。这很遗憾，因为我听说那是部好电影，而且它唯一的评分相当高。

有三个人为《Susan Roger and the Goblet of Java》评分，平均分是 **3.33**。

每个人都喜爱《Snow White and the Seven Steps》，它的平均评分是 **4.0**。这几乎是最高分了。

所以，针对这个问题，答案将是包含以下三部电影及其平均评分的列表：
*   Dude, Where‘s My Code: 2.75
*   Susan Roger and the Goblet of Java: 3.33
*   Snow White and the Seven Steps: 4.0

## 核心模式与实现思路

您可能注意到了许多熟悉的编程模式：
1.  **遍历每部电影**：使用循环迭代电影列表。
2.  **遍历每条评分**：对于每部电影，循环遍历其评分列表。
3.  **计算平均值**：对有效评分求和并除以数量。
4.  **将结果存入列表**：将符合条件的电影及其平均分添加到结果列表中。

当您为每部电影计算平均分时，您的代码将反映这些模式。伪代码逻辑如下：

```java
// 伪代码示例
for (每一部电影 movie in 电影列表) {
    int 评分数量 = 0;
    double 评分总和 = 0.0;

    for (每一个评分 r in movie的评分列表) {
        if (r 不为空) {
            评分总和 += r.getValue();
            评分数量++;
        }
    }

    if (评分数量 >= 要求的最小数量 minimumRater) {
        double 平均分 = 评分总和 / 评分数量;
        将 (movie, 平均分) 加入结果列表;
    }
}
```

## 总结

本节课中，我们一起学习了如何根据最小评分数量要求来筛选电影，并计算其平均评分。您需要运用迭代、条件判断和数值计算等核心编程技能。现在您已经理解了问题，准备好去解决它吧。

**请注意**：在编写代码时，请不要被电影本身分散了注意力。专注于实现逻辑。