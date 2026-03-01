# Java编程和软件工程基础：2-5：读取与存储数据 📊

![](img/482fb728fd9fefc55aed4662e1688247_0.png)

![](img/482fb728fd9fefc55aed4662e1688247_2.png)

![](img/482fb728fd9fefc55aed4662e1688247_3.png)

在本节课中，我们将学习如何为创建电影推荐程序而读取和存储评分数据。这是毕业设计项目的第一步，你将编写一系列程序来读取数据，并将其存储在程序可以访问和处理的特定结构中，以便后续生成推荐。

## 数据来源与格式 🎬

上一节我们介绍了推荐程序的目标，本节中我们来看看具体使用哪些数据。

你将使用来自Twitter帖子的电影推荐数据，这些数据通过一个名为“Movie Tweetings”的项目收集。我们已对数据进行了整理，以便为本次毕业设计提供良好的学习体验。

![](img/482fb728fd9fefc55aed4662e1688247_5.png)

你可以通过相关网站获取所有数据，这些数据会随着新推文的发布而频繁更新。

![](img/482fb728fd9fefc55aed4662e1688247_7.png)

你将使用的数据存储在CSV文件中，因此需要使用Edu.Duke库和Apache CSV项目中的包来访问这些数据。

![](img/482fb728fd9fefc55aed4662e1688247_8.png)

## 电影数据与POJO类 🎥

![](img/482fb728fd9fefc55aed4662e1688247_10.png)

你将读取数据，并将电影评分数据存储在集合中，供程序访问以创建推荐。

![](img/482fb728fd9fefc55aed4662e1688247_12.png)

![](img/482fb728fd9fefc55aed4662e1688247_13.png)

你将从简单的存储技术开始，随着创建更复杂的推荐，你将运用在本专项课程中学到的软件设计原则，使用更高效的数据结构。

![](img/482fb728fd9fefc55aed4662e1688247_15.png)

![](img/482fb728fd9fefc55aed4662e1688247_16.png)

你将使用普通的Java对象（POJO）来存储电影数据。

![](img/482fb728fd9fefc55aed4662e1688247_18.png)

`Movie.java`类镜像了存储电影数据的CSV文件。该CSV文件为每部电影包含一行逗号分隔值数据。

![](img/482fb728fd9fefc55aed4662e1688247_20.png)

![](img/482fb728fd9fefc55aed4662e1688247_21.png)

以下是CSV文件中一行的示例文本：
```
tt0119217,Good Will Hunting,1997,USA,"Comedy,Drama",Gus Van Sant,126,https://...
```

![](img/482fb728fd9fefc55aed4662e1688247_23.png)

![](img/482fb728fd9fefc55aed4662e1688247_25.png)

CSV文件的每一行存储了关于每部电影的八项信息：
1.  电影的IMDB（互联网电影数据库）ID号。
2.  电影标题。
3.  电影制作年份。
4.  电影制作国家（有时可能不止一个）。
5.  电影类型（如喜剧、剧情、冒险、恐怖等），一部电影也可能有多个类型。
6.  电影导演。
7.  电影时长（以分钟为单位）。
8.  电影海报图片的URL。

你将读取CSV文件，并使用我们创建的POJO类来存储每部电影的数据。

`Movie.java`类有一个构造函数和几个用于访问电影数据的getter方法。一旦创建了电影对象，它就不会改变。这些get方法包括`getTitle()`、`getID()`、`getYear()`等，用于访问你读取的每部电影的信息。你将使用`edu.duke.FileResource`类和Apache CSV解析器来读取这些数据。

## 评分数据与Rater类 ⭐

除了电影数据，你还需要对电影进行评分的数据。

另一个CSV文件将存储许多电影的评分。这些评分是从Twitter帖子中整理出来的。

![](img/482fb728fd9fefc55aed4662e1688247_27.png)

CSV文件中的每一行存储一个评分的数据，即Twitter上关于某部特定电影的一条评分。每行存储评分者的ID、被评分电影的IMDB电影ID，以及1到10分制下对该电影的评分。

![](img/482fb728fd9fefc55aed4662e1688247_29.png)

CSV文件还存储了日期和时间信息，但在你将创建的推荐中不会使用该数据。

![](img/482fb728fd9fefc55aed4662e1688247_31.png)

电影ID是获取被评分电影信息的关键。它可以用于你在读取我们讨论过的电影CSV文件时将创建的数据结构中。

![](img/482fb728fd9fefc55aed4662e1688247_32.png)

![](img/482fb728fd9fefc55aed4662e1688247_33.png)

![](img/482fb728fd9fefc55aed4662e1688247_34.png)

`Rater`类支持多种操作，因此它比仅支持简单get操作的POJO类更复杂。

![](img/482fb728fd9fefc55aed4662e1688247_36.png)

![](img/482fb728fd9fefc55aed4662e1688247_37.png)

以下是`Rater`类支持的一些操作：
*   `hasRating(String movieID)`：一个布尔方法，用于判断评分者是否对特定电影（作为参数传入）提供了评分。
*   `getRating(String movieID)`：返回一个`double`值，用于获取由电影ID指定的电影的评分。
*   `addRating(String movieID, double rating)`：添加一个评分，例如在读取评分数据CSV文件时可能会用到。
*   `getItemsRated()`：获取所有已评分电影的ID，以便你可以编写代码遍历所有有评分的电影。

![](img/482fb728fd9fefc55aed4662e1688247_39.png)

![](img/482fb728fd9fefc55aed4662e1688247_40.png)

详情请参阅`Rater.java`类文件。

![](img/482fb728fd9fefc55aed4662e1688247_42.png)

## 核心类总结 📝

让我们总结一下你将用于读取和存储数据以创建推荐的三个类。

在毕业设计项目的第一部分，你将使用`Movie.java`、`Rater.java`和`Rating.java`，通过读取CSV文件并将数据存储在列表中来创建程序化推荐。

![](img/482fb728fd9fefc55aed4662e1688247_44.png)

`Rater` Java类为一个评分者存储电影评分，这可能包含对多部电影的评分。

![](img/482fb728fd9fefc55aed4662e1688247_46.png)

每个`Rating`对象在`Rating` Java类的实例中存储电影ID和该电影的评分。

![](img/482fb728fd9fefc55aed4662e1688247_47.png)

![](img/482fb728fd9fefc55aed4662e1688247_48.png)

这使得`Movie.java`和`Rating.java`都成为POJO类。每个类都有一个用于创建对象的构造函数，以及用于访问电影或评分信息的get方法。

![](img/482fb728fd9fefc55aed4662e1688247_50.png)

![](img/482fb728fd9fefc55aed4662e1688247_51.png)

`Rater.java`类支持关于一个评分者所做评分的查询，例如哪些电影已被评分，以及特定电影的评分是多少。

![](img/482fb728fd9fefc55aed4662e1688247_53.png)

## 课程总结

本节课中我们一起学习了毕业设计项目第一部分的数据处理基础。我们了解了推荐程序将使用的数据来源（Movie Tweetings项目的Twitter数据）和格式（CSV文件）。我们详细介绍了用于存储电影信息的`Movie` POJO类，以及用于存储用户评分的`Rater`类和`Rating` POJO类。这些类构成了后续构建推荐算法的基础数据结构。下一节，我们将开始学习如何具体读取这些数据文件并构建初始的数据集合。