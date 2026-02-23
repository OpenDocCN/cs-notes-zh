# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P120：4_开发桌面预订系统.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

Little lemon need to build a table booking system within their database。

 They can then use this system to keep track of guests visiting the restaurant。

 You can use your knowledge of SQL transactions to help them create this system。

 You can help them to create the system using SQL queries， transactions and C operations。😊。



![](img/07c0aa771e53f180251a7f352c6497ff_1.png)

Developing a table booking system requires the use of SQL transactions or queries。

 As you know by now， transactions are statements that are executed within a database。

 The main types of statements that you need to use include。



![](img/07c0aa771e53f180251a7f352c6497ff_3.png)

Create， read， update and delete queries。 These are also known as crud operations。

 Let's run through the basics of how you can use these queries to complete the tasks in this lesson。

 You can help little lemon to develop and populate their table booking system by creating data in the form of new bookings。

 You can create data using a standard insert into statement。

 Just be sure to identify the following within your syntax。

 The table you want to create the data within the columns that must be populated and the values that they need to contain。

 Exute this statement to create the data within your database。

 There might also be instances in which the data that you originally created needs to change。

 Perhaps someone wants to update their booking， or maybe they've cancel their booking。

 so their data needs to be deleted from the table。 You can carry out these actions using update and delete statements。

 Use an update query to alter information within the table。

 Ident the following information within your query。😊。



![](img/07c0aa771e53f180251a7f352c6497ff_5.png)

![](img/07c0aa771e53f180251a7f352c6497ff_6.png)

Name of the table to be updated。 The columns to be updated and the new values to be added to these columns。

 If you're deleting or dropping information from the table， then you'll need to use a delete query。

 Your delete query must contain the following information。

 the name of the table that contains the data to be deleted and any conditions related to that data。

 You can enact these conditions using a where clause。

 Once you've created updated or deleted data within the booking table。

 you'll need to run tests to make sure that your queries have been executed successfully。

 You can carry out these tests by reading the data。

 A read query returns all information that matches the criteria within your statement。

 An example of a basic read query is a select statement。 In this case。

 you must make sure that the select statement contains the following。

 The name of the table and columns that hold the data。

 The values you require and any conditions required to help you target the data。😊。



![](img/07c0aa771e53f180251a7f352c6497ff_8.png)

![](img/07c0aa771e53f180251a7f352c6497ff_9.png)

![](img/07c0aa771e53f180251a7f352c6497ff_10.png)

You can also enhance your transactions with the use of triggers。

 A Mysql trigger is a set of actions available in the form of a stored program。

 The set of actions is then invoked automatically when certain events occur。

 You can use triggers for different types of events like crud operations to use a trigger。

 You first need to create it using the create trigger statement。

 Then define the trigger type Is it an insert， update or delete trigger。

 And should it be executed before or after the event。 You also need to define the triggers logic。

 specify which table is assigned to， and how it should be applied to the table。😊。



![](img/07c0aa771e53f180251a7f352c6497ff_12.png)

You've explored many different examples of read queries within this course。

 The important thing to remember is to make sure that you include conditions within your statement that target the exact data you need。

 This is good advice to follow for all types of operations。

 Once you're confident that your code is correct， you can commit your progress to gi。😊。

It's also a good idea to enact version control。 This way。

 you can keep track of snapshot that show the project in different stages of development。

 You can then roll back to previous versions， if required。😊。

You should now be ready to make use of SQL queries and transactions to help little Lemon develop a booking table system within their database。

 If you need more information on these topics， remember that you can review the learning material from previous courses。

 Good luck。😊。