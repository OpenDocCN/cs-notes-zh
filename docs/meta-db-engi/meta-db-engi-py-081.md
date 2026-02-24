# 数据库工程师（Python/数据库客户端/高阶数据建模/毕业项目/面试）：模块二：使用Python对MySQL数据库执行高级查询小结 📚

在本节课中，我们将回顾并总结本模块的核心内容。本模块主要讲解了如何使用Python编程语言对MySQL数据库执行查询操作，包括基础的增删改查（CRUD）和更高级的查询技术，如数据过滤、排序与表连接。

## 模块内容回顾

![](img/18bca2efd032af10318d22478977aea1_1.png)

![](img/18bca2efd032af10318d22478977aea1_2.png)

恭喜你完成了本课程的第二个模块。现在，你应该已经熟悉如何使用Python在MySQL数据库中执行查询操作。

![](img/18bca2efd032af10318d22478977aea1_4.png)

让我们花点时间回顾一下你在本模块课程中获得的一些关键技能。

![](img/18bca2efd032af10318d22478977aea1_6.png)

### 第一课：使用Python执行CRUD操作

![](img/18bca2efd032af10318d22478977aea1_7.png)

![](img/18bca2efd032af10318d22478977aea1_8.png)

在第一课中，你学习了如何使用Python在MySQL数据库中执行创建、读取、更新和删除（CRUD）操作。

![](img/18bca2efd032af10318d22478977aea1_10.png)

你首先回顾了如何使用`INSERT`语句在MySQL数据库中创建数据。接着，你学习了如何通过Python将数据插入MySQL数据库。

![](img/18bca2efd032af10318d22478977aea1_11.png)

![](img/18bca2efd032af10318d22478977aea1_12.png)

这个过程的核心步骤如下：
1.  首先，SQL查询被创建为一个Python字符串参数。
2.  然后，这个参数通过一个连接器（connector）传递给MySQL数据库。
3.  连接器将其解析为MySQL能够理解的格式。

![](img/18bca2efd032af10318d22478977aea1_14.png)

你随后探索了将MySQL数据库查询渲染为Python字符串参数的语法示例，并研究了在Little Lemon数据库中使用Python创建和读取数据的实例。

![](img/18bca2efd032af10318d22478977aea1_15.png)

接下来，你重新学习了如何使用`UPDATE`和`DELETE`操作在MySQL数据库中删除和更新记录。你学习了如何将这些查询创建为Python字符串参数，并探索了来自Little Lemon数据库的一些示例。

![](img/18bca2efd032af10318d22478977aea1_17.png)

![](img/18bca2efd032af10318d22478977aea1_18.png)

之后，你进行了一系列实验练习，获得了在自己MySQL数据库中使用Python执行CRUD操作的机会。

![](img/18bca2efd032af10318d22478977aea1_20.png)

你还通过完成几个测验来测试你对这些主题的掌握程度。

### 第二课：使用Python执行高级查询

在本模块的第二课中，你学习了如何使用Python在MySQL数据库中执行高级查询。

![](img/18bca2efd032af10318d22478977aea1_22.png)

![](img/18bca2efd032af10318d22478977aea1_23.png)

![](img/18bca2efd032af10318d22478977aea1_24.png)

你首先学习了如何使用Python在MySQL中过滤和排序记录。你重温了在其他课程中学到的基本过滤和排序技术。

![](img/18bca2efd032af10318d22478977aea1_26.png)

以下是这些技术的核心：
*   使用`WHERE`子句来满足一个或多个特定条件。
*   利用`ORDER BY`子句按升序或降序对数据进行排序。
*   包含比较运算符以指定所需的确切数据。

你随后通过探索Little Lemon数据库的几个示例，发现了这些技术如何在Python中使用。

![](img/18bca2efd032af10318d22478977aea1_28.png)

本课的下一个部分重点介绍了如何使用Python连接MySQL数据库中不同表的数据。你回顾了`JOIN`子句的基础知识，以及如何使用它来定位两个目标表之间的公共列。

![](img/18bca2efd032af10318d22478977aea1_30.png)

接着，你学习了如何将`JOIN`与Python结合使用，以从MySQL数据库中提取数据。这个过程可以概括为：
1.  使用`JOIN`创建一个SQL查询，并将其作为Python字符串。
2.  使用游标对象上的`execute`模块执行该字符串。
3.  然后，使用另一个满足查询条件的变量和`fetchall`方法从MySQL数据库中检索结果。

![](img/18bca2efd032af10318d22478977aea1_31.png)

你还探索了来自Little Lemon数据库的此过程示例。与第一课一样，你也完成了一个实验练习。

![](img/18bca2efd032af10318d22478977aea1_33.png)

在这个实验练习中，你使用Python执行了一个`JOIN`操作，以从MySQL数据库中提取数据。然后，你通过一个测验测试了对该过程的掌握程度。

![](img/18bca2efd032af10318d22478977aea1_35.png)

## 总结

![](img/18bca2efd032af10318d22478977aea1_37.png)

本节课中我们一起学习了如何使用Python对MySQL数据库执行查询。你现在应该已经掌握了使用Python在MySQL数据库中执行查询所需的技能和知识。

做得很好。我期待在下一个模块中继续指导你，在那里你将探索高级数据库客户端的主题。