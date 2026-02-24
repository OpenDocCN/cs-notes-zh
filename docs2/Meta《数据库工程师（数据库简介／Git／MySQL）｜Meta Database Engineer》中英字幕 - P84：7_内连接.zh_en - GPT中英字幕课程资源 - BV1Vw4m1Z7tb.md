# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P84：7_内连接.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Ly Shrub Gardening Center require information on orders recently made by their clients this information is stored in two separate tables。

 the client's table and the orders table， but there must be a more efficient way to review this information that doesn't involve using two tables at the same time。

 right？Thankfully， Luc Shrub can use the inner join clause to return records of data based on a common column with matching values in both tables in this video you'll help Luc Srub to complete this task and by the end of this video you'll be able to apply the inner join concept in MySQL and use SQL aliases to create temporary column names。



![](img/7a17cb67d7006c9601e90615a9b3d72c_1.png)

As you're probably aware by now， databases normally have more than one table in fact。

 database normalization rules dictate that related data should be held in separate tables。

 so let's begin with a quick review of the two tables。The client's table has four columns， client ID。

 full name， contact number and address。And the orders table has five columns， order ID， client ID。

 product ID， quantity and cost。The first task is to identify the full names of all clients who made orders you can do this using the inner join clause in a SQL select statement。

The statement begins with the select command This is then followed by the column full name attached to the client's table separated by a dot。

This queries data from the full name column of the client's table。

Then the Fr keyword is used to target the client's table Next。

 the inner join clause creates a new row of data for each matching record。In other words。

 where the client ID in the client table matches the client ID in the orders table and the equal operator ensures the matching condition must be met。



![](img/7a17cb67d7006c9601e90615a9b3d72c_3.png)

Remember that it's important to specify the table name of each column when you are dealing with multiple tables in the same statement this is especially important when the column name is used in more than one of the queried tables for example client ID exists in both the client and the order tables press enterter to execute the query。



![](img/7a17cb67d7006c9601e90615a9b3d72c_5.png)

The output result set lists the full names for all clients that have made orders This example just extracts a list of names we can also query other information from both tables for example you can display the column names with more user friendlyend labels if required For instance you can take the client ID full name and contact number columns from the client's table and create a join with the product ID quantity and total cost column from the orders table you can do this with the following SQL statement。

Start with a select command that selects the required columns from the client's table。

 then use the as keyword after each column to create an alias， in other words。

 create a new name for each column。Then do the same for the required columns on the orders table。

 so in this statement each column is attached to the related table name and the alias technique is used to create new names for each column。



![](img/7a17cb67d7006c9601e90615a9b3d72c_7.png)

Click Enter to execute the query。The results set is a table with all required data related to the four matchingching clients IDs C1。

 C2， C3 and C4 as shown in the output table In this video you explored how to work with the inner join clause in MySQL to query data from two tables in the database Also you learned how to use an alias to create temporary column names that have more readable labels Lucy Shrub can now review the data they need using a more efficient table thanks to the inner join clause and you should now be able to apply the inner join concept in MySQL and use SQL aliases to create temporary column names Great work。



![](img/7a17cb67d7006c9601e90615a9b3d72c_9.png)