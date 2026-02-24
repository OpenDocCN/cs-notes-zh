# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P22：21_INSERT INTO SELECT语句.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

When working with tables， there might be instances where you need to retrieve information from one or more tables in order to populate columns in another table。

You can complete these actions using the insert into select statement。

Over the next few minutes you'll explore the SQL syntax for these actions。

 and by the end of this video you'll know how to identify and understand。

 insert into syntax and insert data from a source table into a target table using the insert into clause。



![](img/53adb249ea22bc2c1afe0632d2823f40_1.png)

First， let's find out more about the insert into select statement。Essentially。

 the insert into select statement is used to query data from a column within a source table and place the results of that query in the column within a target table。

😊，For example， you could use an insert into select statement to query data in columnum C in the source table and place the results of that query in column B of the target table。



![](img/53adb249ea22bc2c1afe0632d2823f40_3.png)

So what does the insert into select statement syntax look like here's an example。

First type an insert inter clauseuse， followed by the name of the target table and the name of the column you want to insert data into。

Then type the select keyword with the name of the column you want to extract data from， and finally。

 type a from keyword and the name of the source table that holds that column or source data。



![](img/53adb249ea22bc2c1afe0632d2823f40_5.png)

To find out more about how this syntax works， let's explore an example of insert into select。

To demonstrate the statement， I'll use tables from a soccer club database that contain important data about the club。

However， before I begin querying this data， let's quickly review these tables。😊，In this database。

 I have a table called Players that holds the records of four different players in the team。



![](img/53adb249ea22bc2c1afe0632d2823f40_7.png)

I also have a table called Country that holds information about the countries that these players are from。

 but right now the country table is missing the names of the countries。In other words。

 it has no data。I can perform a SQL query using the insert into select statement to populate this missing data。

Do you remember the example of the source and target tables from earlier in this video？

In this instance， the player table is a source table that I need to query。

 and the country table is a target table in which SQL places the results for my query。

So to query data from my source table and populate my target table with it。

 I write an insert into select statement。Note that for the purposes of this demonstration。

 I have organized the player data and the player table in the same order in which it must appear within the country table。

So to perform this task， I first click on the SQL tab to open the code editor。



![](img/53adb249ea22bc2c1afe0632d2823f40_9.png)

Then I write an insert into command， followed by the name of my target table， which is country table。

I then state the name of the column that the data from my query must be inserted into within a pair of parentheses。

In this instance， the column is called country name。Next。

 I type the select keyword and state what column I want to query within the source table。

 which is country。Finally， I typed the Fr keyword and state the name of the source table I want to query the data from。

 which is player table， I add a semico onto the end of my query， then run it。



![](img/53adb249ea22bc2c1afe0632d2823f40_11.png)

Now I select countryry table， my target table from the database。

 and check that the country name column has been populated with the correct data。😊。



![](img/53adb249ea22bc2c1afe0632d2823f40_13.png)

![](img/53adb249ea22bc2c1afe0632d2823f40_14.png)

You now know how to query tables using the insertt select statement。Well done。

