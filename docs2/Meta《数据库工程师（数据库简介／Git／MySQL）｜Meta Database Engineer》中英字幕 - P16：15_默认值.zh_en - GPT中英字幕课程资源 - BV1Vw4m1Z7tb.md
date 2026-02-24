# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P16：15_默认值.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

To ensure the accuracy and reliability of the data in your database。

 you must limit the type of data that can go into your database table。

In this video you'll learn how to describe the purpose of constraints in a database and identify default constraints to set default values in a table。



![](img/ebe74ea1bd403a5f222bf8ccb23cdf5d_1.png)

Database constraints are used to limit the type of data that can be stored in a table this ensures that all data inserted into the table is accurate and reliable。



![](img/ebe74ea1bd403a5f222bf8ccb23cdf5d_3.png)

If the database detects a violation between the constraint and the data operations。

 then it aborts these operations。An example of a violation might be an attempt to insert or upload invalid data to a table。

The database realizes that the data is invalid and rejects it Cons can be column level where the rule applies to a specific column。

 They can also be applied at table level。 For example。

 I could use the foreign key constraints to prevent actions that would destroy links between tables。

 I'll demonstrate this in more detail in a later lesson。

 Two of the most used database constraints include not know a method of preventing empty value fields and default。

 a method of assigning default values。

![](img/ebe74ea1bd403a5f222bf8ccb23cdf5d_5.png)

![](img/ebe74ea1bd403a5f222bf8ccb23cdf5d_6.png)

![](img/ebe74ea1bd403a5f222bf8ccb23cdf5d_7.png)

![](img/ebe74ea1bd403a5f222bf8ccb23cdf5d_8.png)

For now， let's begin our exploration of default values with the not null constraint the not null SQL constraint is used to ensure that data fields are always completed and never left blank。



![](img/ebe74ea1bd403a5f222bf8ccb23cdf5d_10.png)

![](img/ebe74ea1bd403a5f222bf8ccb23cdf5d_11.png)

Let's explore this concept using the example of a table from an online store that records the IDs and names of customers。

The table records this data in its customer ID and customer name columns。

These columns must always contain data。If there's no data or values insert into either of these columns。

 then the creation of a new customer record is aborted。



![](img/ebe74ea1bd403a5f222bf8ccb23cdf5d_13.png)

The not null default value is implemented using a SQL statement。

A typical not no SQL statement begins with the creation of a basic table in the database。



![](img/ebe74ea1bd403a5f222bf8ccb23cdf5d_15.png)

I can write a create table clause， followed by customer to define the table name。

 followed by a pair of parentheses。Within the parentheses， I add two columns。

 customer ID and customer name。I also define each column with relevant data types in for customer ID as it stores numeric values。

 and var for customer name as it stores string values。Finally。

 I also declare a notal constraint for each card。This makes sure that neither column would accept null values。

Now， any operation that attempts to place a null value in these columns will fail。

 like inserting or updating data。

![](img/ebe74ea1bd403a5f222bf8ccb23cdf5d_17.png)

Next， let's look at how the default constraint works in a table。

The default constraint sets a default value for a column of no value was specified。

 This means that if no data is entered for a specific field within a column。

 then a table will automatically insert a default value instead。



![](img/ebe74ea1bd403a5f222bf8ccb23cdf5d_19.png)

To gain a better understanding of default values， let's look at a table that holds player records for a football clubs database。

The table is called playerer table and contains two columns。

The first is player name and lists the names of each player in the team。

 and the second column is city and lists which city each player is from。

Most of the players in this club are from Barcelona。

 so I can specify the default value of the city column as Barcelona。

This means that I don't have to enter Barcelona repeatedly into the city field for each new player。

If no value is entered in the table， then each field is automatically filled with the default value of Barcelona。



![](img/ebe74ea1bd403a5f222bf8ccb23cdf5d_21.png)

Let's find out how the default command is incorporated into a SQL statement。First。

 I used the create table commands to create a table and then call it playerer。

Then within a pair of parentheses， I input the column names， assign a string data type for each。

 and assign a default value of not nu for the name column。Finally。

 I add the default keyword statement， followed by the default value Barcelona for the city column。



![](img/ebe74ea1bd403a5f222bf8ccb23cdf5d_23.png)

Now when I add data into the table for a new player。

 I don't need to type in Barcelona for players who are from the city。



![](img/ebe74ea1bd403a5f222bf8ccb23cdf5d_25.png)

Instead， it will be inserted automatically。You should now be familiar with the importance of using database constraints。

You should also be able to explain database constraints as a method of enforcing rules on a column or table level。

Good work。