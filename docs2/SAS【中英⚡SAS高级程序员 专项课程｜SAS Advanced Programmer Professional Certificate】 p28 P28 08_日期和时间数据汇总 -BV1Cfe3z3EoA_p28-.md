# SAS【中英⚡SAS高级程序员 专项课程｜SAS Advanced Programmer Professional Certificate】 p28 P28 08_日期和时间数据汇总 -BV1Cfe3z3EoA_p28-

When summarizing dates or times in SAS， you can use specific SAS day or time functions to use these functions。

 your data can't be a date time value。The data must be either a date value to summarize date information like month。

 year， day， etc， or a time value to summarize information like hour， minute， second， etc。

This can be easily accomplished with the date part or time part function。

The only required argument is assess datetime value。

The transaction table includes a datetime column with the date and time combined。

By using the date part and time part functions， we can extract the date and time values respectively and create two new columns。

 date and time。These functions return raw SAS date and SAS time numeric values。

 which we can then format to improve the display。that we have the date and time columns。

 we can begin summarizing our transactions to determine things like which month or quarter do our customers spend the most money？



![](img/3b4396b9be40b2d89ec8e2c29e51b41c_1.png)

We can also nest the date part function inside the month function to extract the numeric month。

After you create the new values， you can name the column month and use that column in the group by clause with a summary function。

In this example， we're grouping the months and finding the median amount spent per month。



![](img/3b4396b9be40b2d89ec8e2c29e51b41c_3.png)