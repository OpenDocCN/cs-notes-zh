# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P105：28_MySQL存储过程.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Ly Shrub often perform the same queries on their database every day。

 and each time they perform these queries， they have to rewrite the same SQL code again。

 there must be an easier way， right？Well， with MySQL。

 Luc Sbe can use the stored procedures method to save a specific query as a block of code that they can then recall whenever required。

 Over the next few minutes， you'll discover how this works by exploring the concept of stored procedures and by the end of this video。

 you'll be able to。Demonstrate an understanding of stored procedures in a MySQL database and create and drop simple stored procedures in MySQL。

So let's begin with an overview of what database engineers mean by the term stored procedures。

A stored procedure is a block of code or pre preparedpared query that can be stored in your database。

You can then invoke or call the stored procedure using the call command。

There are a lot of benefits to be gained from using stored procedures with stored procedures。

 your code is more consistent。Your code is also reusable。

 you no longer need to write the same SQL statements repeatedly。

 and your code is also easier to use and maintain Next。

 let's explore the syntax to get a better understanding of how the stored procedure works。First。

 to create a basic stored procedure， write the Cate Proc command。

This must be followed by the name of the procedure and a pair of parenthses。

 which hold a list of parameters。This parenthesis is required even if your stored procedure contains no parameters。

Then write the rest of your procedure logic as required。For example。

 if your procedure must select all data from a table。

 then write a select command with an asterisk and the Fr keyword followed by the table name。

When writing a stored procedure with one or more parameters， the syntax is much the same。

The key difference is that you must include all required parameters within the parenthesis。

Then write the rest of your procedure logic。Once you've created the stored procedure。

 the next step is to invoke it。To invoke a procedure。

 you can use the call command followed by the procedure name。Make sure to include the parenthsesis。

But what have you no longer required a stored procedure， how do you remove it from your database？

To delete a stored procedure， you can use the drop Proc command followed by the procedure name。

In this instance， you don't need to include any parenthsesis。



![](img/3bba7ad914467cb7b9bdd68f917c9b7a_1.png)

As you learned earlier， Luc Srub make heavy use of the same queries in their database For example。

 they often need to query the list of products in their database products table to find items for customers or check what's in stock in their store。

 however， they need to rewrite the same query each time they interact with the products table It's a time consuming process。

Why don't you use your new knowledge of stored procedures to help them create a reusable query？

Ly Shrub need to create a stored procedure that can extract all data from their products table。

The table holds data on all products in the store and is divided into three columns。

 the product IDd column， the item column used to list all products by name and price column。

 which lists all prices rounded to two decimal places。

To create a stored procedure that returns all data from the table。

 you can write the following syntax。Begin with the Create Procedure command。

 followed by the procedure name。Since the goal of this procedure is to return details of all products。

 you can call it Get products details， then add parenthesis。

This stored procedure doesn't require any parameters so you can leave the parenthses empty。Next。

 write a select command and an asterisk symbol to instruct MySQL to extract all data。Finally。

 write the Fr keyword and target the products table， click Enter to run the query。

The new procedure Get Product details has been created。

Ly Shb can now call this query to extract data from the table instead of rewriting a new select statement each time。

To demonstrate the stored procedure， just write the following call command call。

 get Product details and parenthesis， click Enter to run the procedure and extract a set of results that includes all product data Lucy Srub also frequently write queries to identify the lowest priced products in their database so that they can add these items to sales or promotions。

You can create a stored procedure with one or more parameters for this query。

Begin with the createreate Proced command， then write the procedurec name。

You can call it get lowest price products。In parenthsesis， you need to declare the parameters。

 lowest price and the integer value。These parameters return the lowest integer values in the form of a table column called lowest price。

Next， write a select command and an asterisk risk symbol。

Then write the F clause and target the products table。

After the from clause include a less than or equal to operator。

 followed by the lowest price parameter。Click Enter to execute the query。In this statement。

 you've declared a parameter with an integer data type that must pass an integer value into the stored procedure。

However， don't forget that this query also includes parameters。

So each time the query is called you need to specify the value of the stored procedure must process as an example。

 let's return the data of products with a price of less than or equal to $50 by typing the call command。

 the Get lowest price product stored procedure name， and placing the value of 50 in parenthesis。

Click Enter to execute the query。The query passes the value of 50 to the stored procedure through the parameter。

The output appears on screen with a list of all products price less than or equal to $50。Finally。

 Lucky Sub have decided to remove the Get products details stored procedure from their database。

To drop the stored procedure from the database， type droprop Procedure command。

 and the name of the procedure， get products details。Click Enter to execute the query。

The stored procedure has now been dropped from the database Luc Shrub can now perform queries in their database much more efficiently。

 thanks to the use of stored procedures。

![](img/3bba7ad914467cb7b9bdd68f917c9b7a_3.png)

You should now be able to demonstrate an understanding of stored procedures in a MySQL database and create and drop simple stored procedures in MySQL well done。

