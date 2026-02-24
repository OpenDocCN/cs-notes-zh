# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P132：23_使用联接从多个表中提取数据.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

At this stage of the module， you should now be familiar with the data analysis process and how the results can inform data analytics。

 Now， let's look at an example of how to perform data analysis in My SQL by querying multiple tables using joins。

 Lucky shrub need to identify all clients who bought 10 items or more from a specific product line so that they can send them a special offer to make more purchases。

 The clients must have made their purchases after the 5 September 2020。

 and there must be 50 units or more of the product currently available in stock。

 so that all special offers can be redeemed。😊。

![](img/f2548e965b4220994db3d5551b8c63d0_1.png)

There are three tables in the database that contain the required data。

 the orders table with information on each order， the client's table。

 which contains key information about each client and the products table。

 which holds the data on all products in the store。

 You can help Luc shrub to query these tables by using an inner joint to target the following data。



![](img/f2548e965b4220994db3d5551b8c63d0_3.png)

The client Id and contact number columns from the client's table， the order。

 I D quantity and date columns from the orders table and the number of items column from the products table。

 Let's get started。 begin with a select statement， then use dot notation to identify the required columns from each table。

 Next， use an as keyword to create an alias for the product tables number of items column。

 Rename it as items in stock。 Then target the client's table with a from keyword and use the inner join clause to join it to the orders and products tables within a pair of parentheses。

 The first join is created between the client and orders table using the client I D column。

 which exists in both tables。 The second join is created between the orders and products tables using their respective product I D columns。

 Next， add a where clause and parentheses。 within the parentheses。 state the following。

 Custom must have purchased 10 or more units of the item。 All purchases must have been made。😊。

5 September 2020， and there must be at least 50 units of the item currently in stock。 Finally。

 click enter it to execute the query。 My SQL extracts the required data from the tables and displays it on screen。

 You've now performed data analysis on three tables within the Lucky Srub database and through data analysis。

 You can use this data to identify clients that you can send special offers to。 Great work。😊。



![](img/f2548e965b4220994db3d5551b8c63d0_5.png)