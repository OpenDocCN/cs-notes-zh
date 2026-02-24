# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P10：9_SQL语法介绍.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

As you might already know， you can interact with the database using SQL。

But just like with other coding languages， you need experience with SQL syntax and its subsets before you can make use of it。

Over the next few minutes， you'll learn how to create a database using the data definition language or DDL's subset of SQL。

Utilize the data manipulation language， also known as the DML subset to populate and modify data in a database and read and query data within databases using the data query language or DQL subset of SQL。



![](img/55e0ab481500487c56869c494928274f_1.png)

In order to demonstrate SQLs syntax and its subsets。

I'm going to show you the SQL commands that can be used to develop a database for a college， however。

 take note that the demonstration which follows will only briefly show each step in the process。

You just need to develop a working familiarity with SQL for now。

You'll explore the language and as subsets in much more detail later in this program。

 the first task is to create the database。To do this。

 I write a create statement using SQL DDL subset。So the syntax to create a database is create database followed by the name of the database。

I then place a semicolon at the end of the statement。

Let's create a college database as an example using the syntax createreate Dataase College。



![](img/55e0ab481500487c56869c494928274f_3.png)

Once you've created a database， the next step is to create the tables。😊。

You can create tables using the Cre table syntax， followed by the table name。



![](img/55e0ab481500487c56869c494928274f_5.png)

Just repeat these same steps for each new table you want to add to your database。

I can use this syntax to create a student table in my college database。

 this table will hold information on each student。

![](img/55e0ab481500487c56869c494928274f_7.png)

To create the table， I just write createre Table student。Now we need to populate the table with data。

This is where I can use the data manipulation language or DL's subset of SQL to add table data。

 I use the insert into syntax。This inserts rows of data into a given table。I just type insertt into。

 followed by the table name and then list of required columns or fields within a pair of parentheses。

 then I add the values keyword and specify in order the values for each of the fields。



![](img/55e0ab481500487c56869c494928274f_9.png)

As an example， let's add data to the student table in our college database。



![](img/55e0ab481500487c56869c494928274f_11.png)

I'll used the student table I created earlier and add student data to it by specifying values for each of the following columns。

 ID， first name， last name and date of birth。And then populate the table with the required data。



![](img/55e0ab481500487c56869c494928274f_13.png)

But what if I need to update or modify data？For example。

 let's say I've input the wrong date of birth for a student。To change this data。

 I can use the Up syntax， which is part of the DML's subset of SQL。First， I add the update keyword。

 followed by the student table name。Then I use the set keyword。

 followed by columns and values I want to update， written as key value pairings。

In this instance is a date of birth column and a new date of birth value。😊。



![](img/55e0ab481500487c56869c494928274f_15.png)

Finally， I add the wear clauses and a condition to filter the records I need。For example。

 to change the data for the student with the ID of two， I can type where ID equal to 2。



![](img/55e0ab481500487c56869c494928274f_17.png)

It's also possible to delete data from a table。😊，Let's delete the table record for the student with the ID of three using the delete syntax。

😊，First， I typeDelete from， then the table name。

![](img/55e0ab481500487c56869c494928274f_19.png)

This tells MySQL where the data must be deleted from。



![](img/55e0ab481500487c56869c494928274f_21.png)

This is followed by the where clauses in a condition such as ID equal to 3。

 which would remove all data on row 3 of the table。😊。

So I could instruct MySQl to remove the data of the student on row 3。



![](img/55e0ab481500487c56869c494928274f_23.png)

Once I run the statement， the student's data is removed from my table。



![](img/55e0ab481500487c56869c494928274f_25.png)

You're now familiar with how to add， update， or delete data in a database。

But how would you read data stored in your database tables？

That's where SQL's DQL or data query language comes in。The main syntax of DQL is select。

As his name says， it's used to select data from the database。

A select statement is written using the select keyword。

 followed by the columns that hold the data you required。😊。



![](img/55e0ab481500487c56869c494928274f_27.png)

You then write the from keyword， followed by the name of the table you want to select data from。

As an example， you could use the select statement to query the student table to find the name of the student with an idea of one。



![](img/55e0ab481500487c56869c494928274f_29.png)

Youll just need to add the where keyword followed by the student's ID。



![](img/55e0ab481500487c56869c494928274f_31.png)

This would then return the name of John Murphy。You're now familiar with the basics of SQL syntax and its subsets。

Don't worry if you're still trying to figure out these subsets。

 you'll explore each of them in more depth later in this specialization。

 and you'll also get an opportunity to try them for yourself。😊。

