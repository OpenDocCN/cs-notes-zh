# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P120：11_优化数据库选择语句.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

When working with a database， it's important that your SQL queries are compiled and executed quickly and efficiently by the database。

 but this can only happen if your queries are optimized。 over the next few minutes。

 you'll explore techniques for optimizeimizing select statements。

 Luc Shrub have received large numbers of orders from their clients。

 This is LED to increased volumes of data in their database。

 They need to query this data using select statements。 to improve the performance of their queries。

 They'll need to make sure that the statements are optimized。

 Let's find out more about optimize guidelines and explore some techniques that Luc Srub can make use of。

 As you might already know， select statements belong to a category of SQL statements called data retrieval statements。

 These types of statements are designed to return data from the database。

 But if they' are not optimize correctly。 Then they add extra load to the database and slow down its performance。

 This means that it then takes longer for the database to execute your SQL select statements or queries。

😊。

![](img/a35efe596df18b27ef4ab935a55fff34_1.png)

And return the data you need。 However， there are a few basic guidelines or best practices that you can follow to optimize your select statements。

 You might already be familiar with some of these methods。

 Targett only required columns in your select clause。

 Aid using functions in predicates and avoid using a leading wild card in predicates。

Use inner join where possible and make use of distinct and union clauses only when necessary。

Let's take a few moments to explore some examples of these guidelines when querying a table。

 you might often make use of an asterisksteroids in your select statement to extract all available data。

 However， instructing My SQL to query all data in a table adds extra load on the database and slows down its performance。

😊，Particularly if you only require data from specific columns。

 a more optimal approach is to list only the columns in your statement that hold the data you require instead of using an asterisk。

😊，Lucky shrub can use this method to target the required data in their orders table and return the data faster。

 Another common mistake that database engineers make is using MysQL functions in predicates that refer to columns which aren't indexed。

 A predicate is an expression that returns a true or false value。

 An example of this is where clause conditions。 You should also avoid using functions in the where clause on a column that's indexed。

 because this prevents the database from using the index。

You'll explore indexes in more detail later in this lesson。😊。

Using a leading wild card on predicates can also lead to a slowdown in the database。

 an example of this is using patterns that begin with a wild card when combining the like operator in the warehouse clauses。

😊，My Sequel can't make use of an index in a column during a search when it's matched against a pattern with a leading wild card。

Another method for optimizing databases involves using the inner join instead of the outer join where possible。

 an outer join retrieves all records from both tables。

 including rows that don't contain matching values。 This takes longer for MysQl to process。😊。

The inner join is more efficient because it retrieves only the necessary data or matching records from both tables。

 this helps to optimize your queries。😊，Often when creating SQL queries。

 you'll use the distinct clause to eliminate duplicate values or the union clause to combine multiple query results This can slow down the query because it must perform a sorting operation and eliminate duplicate records。

 however， if you use union all instead， then this eliminates the need for a sorting operation and speeds up the execution process。

😊。

![](img/a35efe596df18b27ef4ab935a55fff34_3.png)

You should now know how to optimize MySQL select queries and be familiar with basic optimization guidelines well done。

😊。