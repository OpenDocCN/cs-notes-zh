# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p119 13_02_03_数据连接.zh_en -BV13E421M7FF_p119-

![](img/92497d506fc04a1b2c36c8e92ec80363_0.png)

We need to look up the values of each city and state in the city sheet and state sheet。



![](img/92497d506fc04a1b2c36c8e92ec80363_2.png)

Then combine them with the data in the Yelp data sheet。



![](img/92497d506fc04a1b2c36c8e92ec80363_4.png)

We do this by joining the data sets using a common field or identifier in each。



![](img/92497d506fc04a1b2c36c8e92ec80363_6.png)

This process of joining tables is similar to what we do with tables in a relational database。😡。

The city ID in the Yelp data sheet will join to the ID in the Cities tab。



![](img/92497d506fc04a1b2c36c8e92ec80363_8.png)

And the state ID in the Yelp data sheet will join to the ID in the States tab。



![](img/92497d506fc04a1b2c36c8e92ec80363_10.png)

The most common type of join is called an inner join。

This combines data frames based on a join key or common identifier and returns a new data frame that contains only those rows where the value being joined exists in both tables。



![](img/92497d506fc04a1b2c36c8e92ec80363_12.png)