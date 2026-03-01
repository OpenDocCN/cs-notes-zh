# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p133 27_03_05_代码练习-平均评论数与评分.zh_en -BV13E421M7FF_p133-

Let's do an exercise with pivot tables。 Cate a pivot table that displays the average or mean review count and star rating for bars and restaurants in each city。

 only use category 0 for simplicity。 For some hints。 filter for bars and restaurants。

 then pivot on state， city and category 0。

![](img/de144282677c9d8843fcce5e737b18f0_1.png)

Let's make a data frame that only contains bars and restaurants。 So from the data frame。

 let's look at the category 0 column and let's see if the value is in a list。The list has bars。

Restaurants。This checks to see if the value in the category 0 column is either bars or restaurants。

 Let's store that condition in variable bars underscore rest equals。

 And then let's use that to filter the data frame。 So from the data frame， there is our condition。

 Let's store the new data frame and variable D F underscore bars， underscore rest equals。

 And then if I run that， I should have a new data frame with just bars and restaurants。

 And this is only based on the category 0 values。Now let's create a pivot table and pivot along state。

 city， and category。So using our pandas module， let's call pivot table。 Let's give it the data frame。

 D。Bars rest， and they were going to index on the following columns。Stay。City。And category，0。😔。

We'll store that pivot table in pivot， state， cat。If I run that， I have a data frame here。

 which is actually a pivot table， And I'm only going to look at certain columns without a relevant within that pivot table。

 I'm going to look at review。Count。And。Stars， if I run that， I now have a pivot table。

 I can see for each state and city and category， the average review count and the average stars rating。



![](img/de144282677c9d8843fcce5e737b18f0_3.png)

![](img/de144282677c9d8843fcce5e737b18f0_4.png)