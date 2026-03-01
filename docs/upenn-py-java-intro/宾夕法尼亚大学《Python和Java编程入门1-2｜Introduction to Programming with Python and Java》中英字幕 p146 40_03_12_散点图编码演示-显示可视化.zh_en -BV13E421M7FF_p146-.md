# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p146 40_03_12_散点图编码演示-显示可视化.zh_en -BV13E421M7FF_p146-

And， of course， to show our plot， P， LT dot show。

![](img/c614c88bdce35f2c2acfec1ed60334f9_1.png)

Let's run our code now we have a visualization。

![](img/c614c88bdce35f2c2acfec1ed60334f9_3.png)

This shows the review count and star rating for each category。

 Each marker represents a single business， and we can observe some clustering and review count and star rating。

 depending on the categories。

![](img/c614c88bdce35f2c2acfec1ed60334f9_5.png)

![](img/c614c88bdce35f2c2acfec1ed60334f9_6.png)

![](img/c614c88bdce35f2c2acfec1ed60334f9_7.png)

So the outliers on the y axis， which is the review count。

 are squashing the other data points in the visualization。

 Let's make a little tweak to the plot to represent the y axis in a logarithmic scale so that the review count is displayed in an order of magnitude or groups of 10。

 All the values will be visualized in a more manageable range。



![](img/c614c88bdce35f2c2acfec1ed60334f9_9.png)

![](img/c614c88bdce35f2c2acfec1ed60334f9_10.png)

![](img/c614c88bdce35f2c2acfec1ed60334f9_11.png)

![](img/c614c88bdce35f2c2acfec1ed60334f9_12.png)

First， we need to get the axes attribute from pie plot。



![](img/c614c88bdce35f2c2acfec1ed60334f9_14.png)

And then we'll define the scale of each axis。 So using pie plot， let's call GCA。

 which is get current axes。

![](img/c614c88bdce35f2c2acfec1ed60334f9_16.png)

Store that in a variable。And then we're going to set the scale of the y axis to logarithmic。

 So using the axes object， let's set y scale。

![](img/c614c88bdce35f2c2acfec1ed60334f9_18.png)

To log。Let's rerun our code to see our updated visualization。



![](img/c614c88bdce35f2c2acfec1ed60334f9_20.png)

![](img/c614c88bdce35f2c2acfec1ed60334f9_21.png)

Looks much better， much more manageable， and our outliers are no longer affecting the display of our other data points。



![](img/c614c88bdce35f2c2acfec1ed60334f9_23.png)