# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P85：8_左连接和右连接.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Looky Shrub need to review data on orders made by their clients This data exists in two separate tables clients and orders Luc Shrub can query data from both tables using the left and right join clauses in MySQL These clauses will work because both tables share several closely connected columns In this video you'll help Luc Srub use the left and the right join clauses。

And by the end of this video you'll be able to demonstrate how to apply a left join and a right join in MySQl and utilize aliases to create temporary columns and table names let's quickly review the two tables before creating the query。



![](img/86f0eef9bae5798f00a829e6085d27d8_1.png)

The client's table contains four columns， customer ID， full name， contact number and address。

 and the Order table contains five columns， order ID， client ID， product ID。

 quantity and cost The first step is to create a query for the client ID and client name columns within the client's table which is the left table。

Then you must create a join with the following columns from the order table， the right table。

 order ID， quantity and cost。You can use the left join clause in the SQL statement to complete this task to start。

 use the select command to retrieve data， followed by the column。

 client ID and full name attached to the client's table separated by a dot。

This syntax retrieves data from the two columns from the client's table。

This data then joins the order ID， quantity， and cost columns from the order table。

As you're probably already aware， it's important to specify the table name of each column when dealing with multiple tables in the same statement this is especially important when the column name is used in more than one of the query tables。

😊，For example， the clientient ID column exists in both the clients and orders tables。

 you can also use the SQL as keyword to create suitable aliases for the column names when displayed in the output results set。

And you can use the as keyword to create aliases for the two tables as follows。

 C for clients and O for orders。This now means that instead of repeatedly typing clients to specify the column source table。

 you can just use C， and instead of using the word orders， you can write O。In this statement。

 the left joint clause creates a new row of data for each matching record from the left table。

 the client's table。It does this even if there are no matching records in the orders table which is the right table for example。

 the clients with IDs C5 and C6 have yet to place any orders this means that null values will be inserted for related columns from the right table Finally press enterter to execute the query the output result table contains several null values for the clients with IDs of C5 and C6 This is because they have not yet made any orders Next let's create a similar query using the right join concept。



![](img/86f0eef9bae5798f00a829e6085d27d8_3.png)

You can use similar syntax to the previous query， just replace the left keyword with the right keyword。

In this statement， clients represents the left table and the orders represents the right table。

 the right join clause extracts data from both tables based on the client ID values。

 just like the previous example。Executing this query should return all requested information from the orders table。

 right table， joined by the requested information from the client's table。

 left table based on the common column， clientient ID。

So press enter to run the query and create the output The output shows that the right join has returned all records from the right or orders table where a client has made an order。

And it extracted the matching records from the left or client's table based on the client ID values。

No null values were printed in the output result table this is because all clients who made orders already exist in the client's table。

Lucky Shrub now have the order and client information they need。And you should now be able to。

Demonstrate how to apply a left join and a right join in MySQL and utilize aliases to create temporary columns and table names Good work。



![](img/86f0eef9bae5798f00a829e6085d27d8_5.png)