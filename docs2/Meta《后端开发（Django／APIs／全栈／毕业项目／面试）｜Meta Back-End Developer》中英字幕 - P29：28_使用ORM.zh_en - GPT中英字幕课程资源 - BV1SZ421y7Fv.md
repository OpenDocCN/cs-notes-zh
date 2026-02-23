# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P29：28_使用ORM.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

When building web applications， developers use databases to store data and write SQL queries to fetch and manipulate that data as applications grow in size and complexity。

 so too can the amount and complexity of the SQL queries to assist developers Django provides a feature known as objectject relational mapping R orRM that automatically creates the required SQL queries in this video you will learn about object relational mapping and how Django uses it to create SQL queries against the database。

You will also explore the queryery set API and how developers use it to save and retrieve data in the database。

 one of the earlier challenges of object oriented programming languages used in web development included the complexity of working with databases。

Object relational mapping is an abstraction layer created to facilitate interaction between the programming language and databases。

This allows programmers to use the SQL databases without needing to write SQL queries。

 a structured map is created internally by ORM that generates SQL code for a given relational database by observing the changes made to the data objects ORM can be accessed by using the Shell command。

Previously， you may have noticed how each row entry added for a given model creates an object。

You may recall the output had the prefix query set。

A query set is a collection of such objects for a given model used in Django。

And Django uses a query set to retrieve and manipulate these objects from the database。For example。

 suppose you have a model calledCustom。 You can access the contents of this model by running the command customer。

 objectsject do all。 This command returns the output as a query set。

 The list will contain the entries for the different objects corresponding to the row entries in a database。

For every SQL query that can be constructed， there is a corresponding command。

 These commands are a part of the query set API。So for example。

 if you want to join multiple parameters using the where are limit clauses in SQL。

 you can use the filter function and pass the conditions to it as arguments。

This would select the entry for customers who have reserved a table for four people。

Considering the variety of complex queries that can be constructed in SQL。

 Django has several functions that support these operations。

They can be categorized as follows based on the required logic to run on the query set。

 methods that return new query sets， operators that return new query sets。

 and methods that do not return query sets。

![](img/93b4bc5db9bd8b9516c80ff706c2b4dc_1.png)

Let's now open VS code and explore an example to interact with the database using these methods to return query sets。

😊，Suppose the management staff at Little Le wants to keep track of customers visiting the restaurant。

In the Models。pi file， there is a model calledCustomer that consists of attributes such as name。

 reservation day， and the number of seats that the customer has requested。

This model has already been migrated and the database contains some entries。

To view the contents of the database， click the SQLL Explorer and select the customer table。

Notice that the data is displayed。Once the database has entries。

 open the shell by typing Python 3 manageage dot Py shellll in the terminal。

You may recall that once inside the shell， you first have to import the customer class from the Model。

pi file。So type from My app dot models， import customer。



![](img/93b4bc5db9bd8b9516c80ff706c2b4dc_3.png)

Now， let's explore an example of methods that do not run a query string。

Let's use the customertobject。ge method。Inside the parenthesis， enter an ID value such as4。

Notice that the customer name is returned corresponding to the ID of4。

 This method is similar to the select statement that you use in SQL next。

Let's explore methods that return new query sets using a filter function。

Suppose you want to find reservations for a Saturday。Use the method customer。objects。filter。

 and pass the reservation day equal to Saturday。Make sure to use double quotes as you are working with a string value。

Press enter and notice that the query sets for James and Jacqueline are returned。

The filter method is similar to the wear clause in SQL。

 Let's say you change the day to Friday and add another filter method with a different condition。

 set the condition to seats equal 4 and press enter。 notice that only one query set is returned。

 And this is because that is the only query set that meets both conditions。

The end operator used is similar to the end operator used in SQL。

This operator is part of the Queery sets API that returns new queryery sets。

 it's important to know that the Queery sets API is a broad topic。

If you would like to learn more about it， there is a link to an additional reading at the end of this lesson。

In this video you learned about object relational mapping and how Djangle uses it to create SQL queries against the database。

 you also explored the Queery set API and how developers use it to save and retrieve data in the database。

