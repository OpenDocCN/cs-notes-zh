# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P18：17_创建表语句.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Building a database involves working with substantial amounts of data。

 but how do you organize your data so that you can find exactly what you need and make sense of it？

With SQL， you can create a table within your database to hold and organize your data。In this video。

 you'll learn how to create tables in a database management system using SQL synyntax。

Let's begin with a look at the SQL create table statement syntax I begin the statement with the keywords createre T to let SQL know that I want to create a new table。

I then add the name of the table I want to create。Finally， I add a pair of parentheses。

Within these parentheses， I type the name of each column that must be included within the table。

 followed by its respective data type。

![](img/eaacbf76a54eaaf9aa33530966f8a627_1.png)

Now that you're familiar with the syntax， let's look at it in action。

Be aware that before you can create tables， you must already have a database on the server。

 in other words， you can't build tables if there's no database to create them in。

So let's assume that I already have a database ready to work with in this example I'll create a customer table in the bookstore database to store customer data like names and phone numbers。

😊。

![](img/eaacbf76a54eaaf9aa33530966f8a627_3.png)

First， I write a SQL statement that contains the C table commands followed by the name of the table。

 in this case， customers， then I add an open parenthesis。

It's within this parenthesis that I need to create my own columns。

So I write the name of my first column， which is cost Rename。

This is followed by the data type Varchar。This data type means that the column can hold data of any type。

I then add a numeric value within a pair of parentheses。

Then I add a comma and write the name of the second column which is phone number。

I add end at the data type so that only whole numbers can be stored。

Then I had a closing parenthsesis and a semicolon。

![](img/eaacbf76a54eaaf9aa33530966f8a627_5.png)

Finally， I execute the statement。The customer's table is now stored in the database。



![](img/eaacbf76a54eaaf9aa33530966f8a627_7.png)

In this video you learned how to create tables in a database using SQL synyntax。Well done。

