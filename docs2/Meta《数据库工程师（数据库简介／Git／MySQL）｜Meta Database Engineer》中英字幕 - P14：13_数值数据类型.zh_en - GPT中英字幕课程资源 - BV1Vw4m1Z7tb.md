# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P14：13_数值数据类型.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

You probably know the database tables store data in the forms of columns and rows。

But how do you make sure that every column accepts the correct type of data？For instance。

 that your cost column stores values in decimal， or your product quantity column accepts positive numbers。

This is exactly what data types do。With data types。

 you can determine what kind of data is accepted by each field in your table。

Over the next few minutes， you'll learn how to explain the numeric data type in a database and differentiate between integer and decimal data types。

Before you begin exploring numeric data types， let's take a moment to explore the concept of data types when you create a table in a database。

 you need to define column names and the data type of the content that will reside in those columns。



![](img/5ab45c54de4a97fb2dfbcf348b420033_1.png)

Data type tells a database management system such as MySQL how to interpret the value of the column Data types maintain data in the right format and make sure the value of each column is as expected。



![](img/5ab45c54de4a97fb2dfbcf348b420033_3.png)

The most used data types are numeric， string and date and time data types。

 Let's take the example of a table from the database of an online store。



![](img/5ab45c54de4a97fb2dfbcf348b420033_5.png)

![](img/5ab45c54de4a97fb2dfbcf348b420033_6.png)

This table collects information and customers in the form of columns called customer name。Order date。

Product， quantity and total price。Each of these columns must store data in the form of a suitable data type。

The customer name column can use string data。Order date can use a date type and product。

 quantity and total price columns are best suited to numeric data。



![](img/5ab45c54de4a97fb2dfbcf348b420033_8.png)

The focus of this video is the numeric data type。Nummeric data typess is the generic term used for all specific data types that let a column store data as numbers in the database。

The two most common numeric data types used in databases are the integer data type used for a whole number value and the decimal data type used for a number with a fraction value to return to our earlier table example。

 the product quantity column is defined as an integer data type。

 This is because it holds whole numbers only。

![](img/5ab45c54de4a97fb2dfbcf348b420033_10.png)

Fraactctionional numbers can be inserted， but they will always be automatically rendered up or down to the nearest whole number in the database。

And the total price column is a decimal type。 This is because it holds fractional numbers。

 For example， an item that costs $80。90 is a fractional value。

80 is the whole number and 90 is a decimal。 Who numbers can also be inserted。



![](img/5ab45c54de4a97fb2dfbcf348b420033_12.png)

The database will add a decimal point along with a fractional value of0。

In most database management systems， you'll find different types of integer and decimal data types。

Each type is intended to store a minimum and a maximum number value， for example。

 in My SQL database management system， tiny integer or tiny int。

iss used for a very small integer number value where the maximumim possible value that can be inserted is 255。

 while integer or in can be used to store a very big number。

 the maximum value that it can store is over 4 billion these data types can also accept negative and positive values。



![](img/5ab45c54de4a97fb2dfbcf348b420033_14.png)

In some database management systems you can also force columns to accept positive numbers This increases the maximum value they can store you should now be able to explain the numeric data type in a database and you should also be capable of differentiating between integer and decimal data types great work。



![](img/5ab45c54de4a97fb2dfbcf348b420033_16.png)