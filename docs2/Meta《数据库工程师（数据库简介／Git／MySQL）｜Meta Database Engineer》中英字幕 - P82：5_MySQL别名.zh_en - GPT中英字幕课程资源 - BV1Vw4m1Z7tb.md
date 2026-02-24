# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P82：5_MySQL别名.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Little lemon restaurants has run into some problems with their database。

 some of the table and column names in the database are too long。

 which is causing issues with the output of queries。

 They need to find a way to generate results that are simpler to use， read and understand。

 Fortunatelyly， they can solve these issues with MysQL aliases。

Over the next few minutes you'll discover how little lemon can make use of MysQL aliases and by the end of this video you'll be able to demonstrate an understanding of the concept of an alias in a database。

 identify examples of situations in which it is beneficial to use aliases and demonstrate the use of alias in MySQL queries。

 but first you might be wondering what is an alias in the context of SQL。

SQL aliases are used to provide database columns and tables with temporary names。

These temporary names make it simpler to use， read and understand the output of the database For example。

 little Le can use aliases to shorten the names of tables and columns in their database there are three common situations in which it's useful to consider an alias an alias can be used to rename a table or column whose original name is too long or technical it can be used with a concatednation function to combine an output into one column instead of two and you can also use an alias to create distinct table names when dealing with multiple tables。

However， it's important to bear in mind that the syntax for creating and using an alias can change depending on which of these issues you're attempting to resolve。

Let's take a few minutes to review an example of the syntax for each scenario beginning with renaming tables。

To rename a table， you need to use the select statement which begins with the select keyword。

 then type the original column name followed by the alias。

Bothoat must be separated by the as keyword， the as keyword creates the alias。

You can also include other columns in the table with each separated by a comma。

 then write the Fr keyword followed by the table name。If your table requires multiple aliases。

 then write out each column name and use the as keyword for each column you need to create an alias for。

For example， in their client orders table， little Le can use an alias to rename lengthy columns like client order information to just orders Next let's review the syntax for a concatenation function that combines an output into one column instead of two。

The select command is used to retrieve data。This is followed by the Conca function。

 which concatennateates or combines the information extracted from the column names placed in parenthsesis。

These names must be separated by commas and a pair of double quotation marks The quotation marks split the output by creating an empty space between the concatenated values the as keyword is then added。

 followed by the name or alias you want to assign to the new concatenated column。

And the from keyword specifies the table SQL must extract the data from。

Little Le can use a concatednation function to combine the values contained in the first and last name columns of their client De table。

These values are then placed in a new concateninated column called clientient names。Finally。

 let's explore the syntax for querying multiple tables。😊。

The first thing to note when querying multiple tables is that you can use a one character alias to represent each table for example。

 if you're querying two different tables， then you can use X for table1 and Y for table 2。

So the syntax then begins with a select command， followed by the tables and columns to be queried。

You can query columns using dot notation。Such as x dot column 1 to query table 1 column 1 or Y dot column 2 for table 2 column 2。

Next add the Fr keyword， then type the original name of each table alongside its alias withre both separated by the as keyword。

Finally， add a wear clause and conditions as required。For example。

 perhaps you're querying prices in an online storeR database and want to return a list of items that are less than $12 for table1 and 5 for table2 those are the three main instances in which MysQL alias can be used along with their related syntax。

Now that you're familiar with the concept of MySQL alias。

 let's see if you can help little Le with their databases。



![](img/6cfb5461e68e6faefc97385ed8236540_1.png)

Little Lemon Raurant has a table in their database called Food Orders delivery status that keeps track of food orders。

 The table has two columns called dateate food order placed with supplier and date food order received from supplier。

 However， these column names are too long and complex。

 so they need to be simplified to make the database more efficient。

You can use aliases to simplify the output so that the column names are easier to read and understand when queried。

Begin with a select statement and target the order ID column。

 then rename the date food order placed with supplier column as date order placed。

 and rename the date food order received from supplier column as date order received。

Notice that there are double quotation marks used for order date received because the alias name contains a space In other instances you can declare the alias without the use of quotation marks Finally。

 type a Fr keyword followed by the name of the table， then click enter to execute the query。

The output now shows the alias names instead of the original column names。

 which makes it much easier for little lemon to track food orders。However。

 you can make this table even more efficient。For instance。

 you could concatenate order ID and order status into one column instead of two。

As you learned earlier， you can use a SQL alias with functions。Write the statement as follows。

 begin with the select command and then the Conca function。

Then place the columns you want to concatenate in a pair of parenthses。

You should also make sure that you include quotation marks to split the output。Next。

 use the as keyword to create the alias In this instance， you can call the alias column order status。

Then use the from keyword to identify the table。 Finally， hit enter to execute the query。

 The output shows the new order status column with the concatenated info。Finally。

 let's review how to work with multiple tables in the database。

The restaurant has divided their menu into two tables called starters and main courses Both tables show the names of the meals available to order and their respective costs as part of a new promotional campaign。

 little Le want to promote starters that cost $7 or less and main courses that cost $15 or less。

 so you need to query these tables and identify the meals that match these prices。In this instance。

 you can use a one character alias of S to represent starters。

 and you can use C to represent main courses。Add these aliases into a select statement and use dot notation to request the name and cost of the meals。

Then use the from keyword to identify the tables and the as keyword to create aliases for each one。

Courses is C and starters are S。Finally， add a wear clause and specify the condition。

The condition returns all starters less than $7 and all main courses less than $15。Finally。

 press Enter to execute the query。SQL generates an output that shows all related costs in one table All issues with Little Lemons database have now been solved using MySQL aliases。



![](img/6cfb5461e68e6faefc97385ed8236540_3.png)

Thanks to your assistance， Little Lemons database is now more efficient to use and they've identified some great meals to include in their next promotional campaign with the skills you've gained from these tasks。

 you should now be able to demonstrate an understanding of the concept of an alias in a database。

 identify examples of situations in which it is beneficial to use aliases。

 and demonstrate the use of alias in MySQL queries， great work。😊。

