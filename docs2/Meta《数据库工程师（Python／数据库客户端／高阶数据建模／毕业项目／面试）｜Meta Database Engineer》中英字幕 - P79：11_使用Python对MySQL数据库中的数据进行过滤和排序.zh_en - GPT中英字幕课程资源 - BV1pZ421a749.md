# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P79：11_使用Python对MySQL数据库中的数据进行过滤和排序.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

When you query records in a database， your query can often return hundreds， thousands。

 or even millions of results， depending on how much data there is。😊。

But you might only require a fraction of these results。As you saw in earlier courses。

 you can use filtering and sorting techniques to target only the data you need from these results。

When querying a MysQL database using Python， you can apply these same techniques to ensure that your query targets specific data。

Over the next few minutes， youll recap some basic filtering and sorting techniques and learn how to filter and sort MySQL data using Python。

Over at Little Lemon， the restaurant is currently querying the bill records of each customer in its database。

 They need the records of all bookings with a final bill greater than or equal to $40。😊。

They also need the bookings to appear in ascending order with respect to the total bill amount。



![](img/c033410f9862d5cdbc41d2f105f6b6bc_1.png)

Filtering and sorting techniques are a great way to carry out this task。

Let's find out how these techniques work with Python and then help let a lemon。

One filtering technique that you should be familiar with is the use of the wear claws。

 Let's begin with a quick recap of the wear claws。

![](img/c033410f9862d5cdbc41d2f105f6b6bc_3.png)

As you should know by now， you can use this clause to filter and extract records that satisfy a specific condition。

 For example， little Le can use the where clause to create a sequL select statement that targets the booking I D and billam amount columns in their orders table。

The statement returns all values in the bill amount column equal to a value of 40。😊。



![](img/c033410f9862d5cdbc41d2f105f6b6bc_5.png)

The wh clause helps to filter the records from the database。

 but not to the extent that little lemon require。As you saw earlier。

 little Le need the records of all bookings with a final bill greater than or equal to $40。

 You can use comparison operators to specify the exact data you require from a database。😊。



![](img/c033410f9862d5cdbc41d2f105f6b6bc_7.png)

For example， little lemon can replace the equals operator in their statement with the greater than or equals to comparison operator。

😊，This operator targets all records from a database where the bill amount is greater than or equal to a value of 40。

😊，This narrows down the records even further， returning much more specific results。

 Another technique is the order by clause。 As you should know。

 the order by clause is an optional clause that can be added to a SQL select statement。

 It helps to sort data in ascending or descendending order。

 So to filter their records even more efficiently。 Little lemon can add the order by clause to the end of their statement。

 They target the bill amount column and then type the ascending keyword。 Once executed。

 the query returns all bill amounts greater than or equal to $40 in ascending order。



![](img/c033410f9862d5cdbc41d2f105f6b6bc_9.png)

![](img/c033410f9862d5cdbc41d2f105f6b6bc_10.png)

Now that you've reapppped some examples of filtering and sorting techniques。

 your next question might be， how can I use these techniques in Python to query a MysQqL database？

 Well， as you saw earlier， little lemon need to query the records in their MysqL database using Python。

😊，Let's help them create this query using the filtering and sorting techniques that you just explored。

😊，To recap， little lemon need the records of all bookings with a final bill greater than or equal to $40。

 They also need the bookings to appear in ascending order with respect to the total bill amount。

First， write a SQL select query as a Python string stored in a variable called My SQL query。

The query must target the booking Id and billam amount columns from the orders table。

Use the where clause and a greater than or equal to comparison operator to target all records that are greater than or equal to the value of 40。

😊，Then use the order by clause and the ascending keyword to order all records from the Billam amount column in ascending order。

The next step is to establish a connection through the MysQL Connector Python API between the front end Python application and the back end MysQL database。

Then get the cursor object from the connection using the cursor method。

 Run the query using the execute method from the cursor object。

 Once the query is successfully executed， you can fetch all the results in a new variable called results that satisfies the conditions given in your query。

😊，Just use the fetchol method on the cursor object to grab the query results。

All the retrieved data is in results as a Python list of topples。

 You can display the list on your dashboard for little lemon。



![](img/c033410f9862d5cdbc41d2f105f6b6bc_12.png)

Little lemon now have the data they need。And you should now be able to explain how to make use of filtering and sorting techniques to target records in a Mysql database using Python。

 Great work。😊。