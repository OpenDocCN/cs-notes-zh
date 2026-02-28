# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p117 11_02_03_检查数据.zh_en -BV13E421M7FF_p117-

Let's load and read the Yelp data file。Import pandas and use the Excel file class to load the entire Yelp Excel file。



![](img/386cb22e046c744684e79111efee2525_1.png)

Then read the Yelp data sheet into a data frame using the parse method。😡。



![](img/386cb22e046c744684e79111efee2525_3.png)

We see that the type of DF is a data frame。We can get count of the rose。

And get the size or account of the rows and columns by accessing the shape attribute。



![](img/386cb22e046c744684e79111efee2525_5.png)

Get count of the values in each column。

![](img/386cb22e046c744684e79111efee2525_7.png)

You can inspect the column headers by accessing the columns attribute。😡。



![](img/386cb22e046c744684e79111efee2525_9.png)

And get the type of data stored in each column by accessing the D types attribute。😡。



![](img/386cb22e046c744684e79111efee2525_11.png)

![](img/386cb22e046c744684e79111efee2525_12.png)

The describe method provides various summary statistics for the numerical values in a data frame。



![](img/386cb22e046c744684e79111efee2525_14.png)

The head method displays the first five rows of data。If you provide an argument。

 it will display the given number of rows。This displays the first 100 rows of data。



![](img/386cb22e046c744684e79111efee2525_16.png)

You can drop the duplicates from a data frame by using the D duplicates method By default。

 this will look at all columns to identify and drop duplicate rows in the data。



![](img/386cb22e046c744684e79111efee2525_18.png)

![](img/386cb22e046c744684e79111efee2525_19.png)

![](img/386cb22e046c744684e79111efee2525_20.png)