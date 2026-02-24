# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P103：26_比较函数.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

M and G are approaching the end of their business year and need to extract sales revenue data for each item in their inventory。

 they can extract this data using comparison functions。Over the next few minutes。

 you'll explore the concept of comparison functions and at the end of this video。

 you'll be able to identify common MysqL comparison functions and explain how these functions are used to process and manipulate data in a MysQL database。

 So what do database engineers mean by the term comparison functions。

MysQl comparison functions allow you to compare values within a database。 For example。

 the function can be used to determine the highest， lowest and other values。

 A benefit of comparison functions is that they can be used with a wide range of values。

 including numerical strings and characters。 Here's a few examples of MysQl comparison functions。

 The greatest function is used to find the highest value。 Le determines the lowest value。

 and is null is used as an alternative to the equals operator to test of a value as null。

To demonstrate the syntax， let's identify the highest and lowest values from a table that contains numerical values only。

The syntax begins with a select command， followed by the name of the required column。

Often this is the column that holds the table's primary key or identifying attribute Next。

 type the greatest function followed by parenthsesis containing the names of the columns you need to compare。

Then use the as keyword with a column alias of highest to ensure SQL returns the required values in a new table under this column。

Next， utilize the least function in the same manner。Finally， identify the table to be queried。

For example， MG can use the greatest and least syntax to extract sales revenue data。

They can target the last four business quarters and deliver the highest and lowest values from each。

You'll find out more about how M&G can do this in a few moments。For now。

 let's look at the syntax for the final comparison operator is Null。

Is Nll is often used with a select command， followed by the name of the required column。

Then a Fr keyword is used to identify the required table。

An I no function can also be used with aware clause The clause cause the is no function and identifies the column it must pass through now that you're familiar with the syntax of comparison functions。

 let's take a few moments to find out how they're used in the M&G database As you learned earlier。

 M&G require data on their sales revenue for each item in their inventory for the last four business quarters。



![](img/508de013486c960235cd204e2370c03d_1.png)

The sales revenue data is contained in the sales revenue table。The table has five columns。

One column called item ID which identifies each item in the inventory and an individual column for each quarter。

M&G first need to identify the highest and lowest revenue each item brought in over the past four quarters。

You can help them by using the greatest and least comparison functions。

 just like the syntax example from earlier。Start with a select command and list item ID as the first column。

Then to identify the items that brought in the highest revenue， call the greatest function。

 and pass the four business quarter columns as arguments。Then， create the alias highest。

Write a similar line of syntax for the least function and assign it the alias of lowest。Finally。

 use the Fr keyword to target the sales revenue table。Once executed。

 the query's output presents the highest and lowest sales revenue values for each item over the last four business quarters。

For example， the item with the ID of one was worth $138，000 to M&G at its peak and 60。

000 during its lowest sales period。M&G need to determine which of their most recent orders have yet to be delivered。

The delivery data is held in the MG order table， the table contains seven columns， order ID， item ID。

 quantity， cost， order date， delivery date， and order status。

The delivery date column is your primary concern here。

All orders yet to be delivered have a no value within this column。

So you can use the I null function on this column with the where clauses to filter these orders。

Begin by writing the select statement as usual， followed by an asterisk。

Then use a from keyword to target the table。Finally。

 write aware clause and call the is noll function to pass through the delivery date column。

Once executed， the query returns a value of  three；

 This is a true value for all records that have a null value for the delivery date column。



![](img/508de013486c960235cd204e2370c03d_3.png)

M andG now have their required sales data， and you should now be able to use comparison functions in a MySQL database。

 great work。