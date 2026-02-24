# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P83：6_联接.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Ly Srub Gardening Center needs to gather information on their customers and the orders they've placed。

 but the records are held in three different tables； however。

 they can extract this information from their database using joinins clauses to join the required elements of these tables together。

Over the next few minutes， you'll discover how the Joins Cla works and by the end of this video you'll be able to。

Demonstrate an understanding of the join concept in a database and describe the main types of joins in MySQL。

Let's take a closer look at the problem that Lucy Sub has encountered with their database tables。

Ly Shrub needs to determine what products were ordered and which customers placed the orders However。

 this information exists in three separate entities or tables， customers， orders and products。

So how can Luc Shrub extract records from three different tables？



![](img/2bd7facc080947055fa12e6dee710f8b_1.png)

Before you can begin to assist Luc Shrub， you first need to understand the concept of joins。

The SQL join clause is used the query data based on a common column between two target tables。



![](img/2bd7facc080947055fa12e6dee710f8b_3.png)

![](img/2bd7facc080947055fa12e6dee710f8b_4.png)

For example， the customers and orders tables both contain a customer ID column。

 and the product ID column is a common column between the orders and products tables。



![](img/2bd7facc080947055fa12e6dee710f8b_6.png)

These common columns can be used to join these tables together and extract their required records。

There are four types of join used to combine tables。

 an inner join which extracts or selects records of data that have matching values in both tables。

 and a left join that extracts or selects records of data from the left table and all matching records from the right table。



![](img/2bd7facc080947055fa12e6dee710f8b_8.png)

![](img/2bd7facc080947055fa12e6dee710f8b_9.png)

The right join which extracts or selects records of data from the right table and matching records from the left table and the self join in which a table is joined with itself to retrieve info that exists in the same table。



![](img/2bd7facc080947055fa12e6dee710f8b_11.png)

![](img/2bd7facc080947055fa12e6dee710f8b_12.png)

Let's begin with a review of the inner join。An inner join returns records of data that have matching values or columns in both the left and the right tables。



![](img/2bd7facc080947055fa12e6dee710f8b_14.png)

This relationship between the two tables can be conceptualized in the format of a Venn diagram。

 as can all other joints。In terms of syntax， the left and right tables are identified as table one and table2 respectively。



![](img/2bd7facc080947055fa12e6dee710f8b_16.png)

Ly Shrub need to identify the full names of all clients that placed orders with the business。

To complete this query， they need the client's table and the orders table。

They can then create an inner join using the client ID column that exists in both tables。



![](img/2bd7facc080947055fa12e6dee710f8b_18.png)

The output result reveals the records of all clients who placed orders。

 and the client ID represents all records with matching IDs to be listed。



![](img/2bd7facc080947055fa12e6dee710f8b_20.png)

The syntax of an inner join begins with a select statement which queries the left table and the column with the matching values。

 The Fr keyword is then added along with the name of the left table。

Next is the inner join clause followed by the name of the right table Finally。

 the on keyword is used to identify the inner join that the tables share。



![](img/2bd7facc080947055fa12e6dee710f8b_22.png)

Next， let's move on to review the left join。The left join returns all common records in a similar way to the inner join。

In addition， it returns all available records of the common column from the left table。

 even if there isn't a match in the right table。

![](img/2bd7facc080947055fa12e6dee710f8b_24.png)

Looky Shrub can use the left join table to extract data from the clients and orders tables using the client ID values。

The join locates four matching records between the two tables and places them in the common area of the Venn diagram。



![](img/2bd7facc080947055fa12e6dee710f8b_26.png)

The left joint syntax begins with a select statement in which the required columns from table one are identified。

The Asz keyword is then used to create an alias for each column。

The Fr keyword is used to identify the left table， which is the one that must be queried。

 and once again， the as keyword is used to create an alias for this table。

The left join clause is then used to join table2 and assign an alias。Finally。

 the on keyword equates the matching columns between the two tables。



![](img/2bd7facc080947055fa12e6dee710f8b_28.png)

Now let's review an example of the right join。The right join returns all records from the right and left tables。

 but with the right table as the main target table。



![](img/2bd7facc080947055fa12e6dee710f8b_30.png)

For example， Lucy Sub can use the right join to extract records of data from the orders and products table based on the product ID values This lists all products from the products table joined with the matching related orders details in the left table。



![](img/2bd7facc080947055fa12e6dee710f8b_32.png)

The right join syntax is very similar to the left join。

 The only difference is that the right join clause is used to extract records of data。



![](img/2bd7facc080947055fa12e6dee710f8b_34.png)

Finally， there is the self join。A self joint is a special case in which a table must be joined with itself。

In other words， one table is treated as two in order to extract specific information from either the left。

 right or inner join。In the case of Lucy Shrub， the business holds records of all staff members in a staff table。

The table contains records on sales floor employees and line managers。

Ly Shrub can treat the table as two tables to determine who is a line manager and who is a Sales floor employee。



![](img/2bd7facc080947055fa12e6dee710f8b_36.png)

A self joint syntax is written as a select statement in which an alias is created for the common column in table2。



![](img/2bd7facc080947055fa12e6dee710f8b_38.png)

You've encountered a lot of information in this video。

 particularly in terms of syntax don't worry if it doesn't all make sense at this stage in the videos that follow you'll learn how to create each type of join in more detail。

 but for now you should be able to demonstrate an understanding of the join concept in a database and describe the main types of joins in MySQL well done。

