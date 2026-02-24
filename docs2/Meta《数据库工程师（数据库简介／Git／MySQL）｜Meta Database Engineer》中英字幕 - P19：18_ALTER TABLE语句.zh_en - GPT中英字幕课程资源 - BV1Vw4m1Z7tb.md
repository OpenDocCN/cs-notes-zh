# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P19：18_ALTER TABLE语句.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

At this stage you're probably familiar with creating tables and databases。

 but no table is ever static。Database developers are always restructuring tables。

Sometimes they need to add new columns， delete old ones， or edit the data they contain。

You can complete many of these basic restructuring actions using SQL syntax。In this video。

 you'll learn how to alter a database table by adding and removing columns and modify the attributes of a database table。

Let's start by exploring the SQL Alstate syntax。The first part of an alar statement is the altar and table keywords。

These keywords inform the database that there is a table whose contents must be altered。

This is followed by the name of the table to be altered。 I then include the add keyword。

 This keyword tells SQL that there's one or more items to be added to the table。

There are other keywords I could include here instead， but for the purposes of this example。

 I'll work with add。Finally， I insert a pair of parentheses。Within these parentheses。

 I declare the name of a new column to be added to the table， along with this data type。



![](img/7048acbb3c9f781c0b820dc673643b7e_1.png)

Now that you're familiar with the Alar tableable statement。

 let's explore an example of this statement in action。😊，However。

 before you can begin altering tables， you must already have a database on the server， so as always。

 make sure that you know how to create databases before proceeding and ensure that you already have a table in your database with data that you can alter。

In my example， I have a student's table located within a database called College。

My student's table holds information on their IDs， names and emails of each student in the college。

I can demonstrate the alter statement by adding， deleting and modifying columns in this table。

My first task is to add three new columns to the table， age， nationality and country。

To add these columns using SQL syntax， I first typed the Al table command。

 followed by the name of the table， studentss。Next。

 I use the Add command to let the database know that I want to add new columns to the table。

Then I input a pair of parentheses that contain the columns I want to add along with the type of data they'll hold These columns are an age column which holds data in integer format。

😊，A country column with vchar is the data type。And nationality and country columns that hold vchar or string data。

I also add a character limit of 50 to the country columns fields。

 and a limit of 255 to the nationality columns fields。



![](img/7048acbb3c9f781c0b820dc673643b7e_3.png)

Then I execute this statement，I now have two new columns and students table in the College database。

Country and nationality are very similar columns， and in most cases will'll probably hold the same type of information。



![](img/7048acbb3c9f781c0b820dc673643b7e_5.png)

So I can write a SQL statement to remove the nationality column。😊，Just like the last example。

 I start my statement with Alar table studentss table。Next。

 I type the D columnum command followed by nationality。

This command instruct SQL to delete or drop this column from the table， then I run the statement。

ANotification message appears requesting confirmation of deletion， I press OK to confirm。



![](img/7048acbb3c9f781c0b820dc673643b7e_7.png)

![](img/7048acbb3c9f781c0b820dc673643b7e_8.png)

The nationality column has now been dropped。Now it's time to alter the structure of the table。



![](img/7048acbb3c9f781c0b820dc673643b7e_10.png)

The country column has a limit of 50 characters， just as I said it originally。

But now I'm going to change it so that it holds 100 characters instead using the Al table command。😊。

I start with the syntax Al table， followed by Students table。Then I type the modify command。

 the country column name， and the varchar data type。

 and finally I had a pair of parentheses containing my new value of 100。



![](img/7048acbb3c9f781c0b820dc673643b7e_12.png)

I then execute the query。My country columnum's limit has now been updated to 100 characters。😊。

In this video， you learn how to alter and modify tables in a database using SQL synyntax。Well done。

