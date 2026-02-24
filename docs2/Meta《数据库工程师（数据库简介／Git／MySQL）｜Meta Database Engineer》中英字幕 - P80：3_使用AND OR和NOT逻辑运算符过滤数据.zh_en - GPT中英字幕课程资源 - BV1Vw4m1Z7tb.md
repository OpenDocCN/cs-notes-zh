# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P80：3_使用AND OR和NOT逻辑运算符过滤数据.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

You might already be familiar with using a where clause and a condition to filter data in a database table。

 but what if you need to specify multiple conditions in a where clause？

You can use logical operators to specify multiple conditions or rules， so when the data is filtered。

 all specified conditions are applied。By the end of this video。

 you'll be able to identify the logical and and or operators and explain how they're used to combine conditions and develop a working familiarity with the logical nod operator and outline how it is used with data filtering。

Before you explore how to filter data using multiple conditions。

 let's take a moment to recap how the where clause works。

It's important that you understand it before working with logical operators。

When filtering data in a database table， you can add a where clause to your SQL select statement to specify a condition or rule for how the data should be filtered。

A select statement begins with the select keyword or command。

You must then specify the data or columns to be queried。You then add the Fr keyword。

 followed by the table you need to query。Finally， you must add a wear clause and a condition。

But as you've just learned， it's also possible to specify multiple conditions in the wear clauses。

 These conditions are specified using logical operators。

Let's begin by exploring the and and or operators。The and operator is used with the where clause to filter data it checks if all combined conditions meet the value of true。

 and the orR operator checks if any of the combined conditions meet the value of true。

Let's take a moment to explore the syntax for each of these logical operators。

Write the select statement as usual， however， in this instance。

 multiple conditions are placed after the wear clauses and combined using the and operator。

The statement checks of all these conditions yield the value of true for a record。If so。

 then that record is included in the results set。With the orR operator。

 a record is included in the results set if any of the conditions separated by orR is true。That is。

 if at least one condition yields a true value for a record in the table。

 then that record is included in the query results set。Next， let's look at the not logical operator。

The knot operator works slightly differently to other operators it selects a result to be included in the query results set only if the conditions specified in the where clause are not true。

In other words， it reverses or negates the results that are returned once the condition is evaluated。

To use the knot operator， you just type not after the wear clauses。

 followed by the required condition。Let's take a few minutes to find out how these operators are used over at Loki Shrop。

Ly Sroub are reviewing their accounts a need to generate specific details on their customers and the purchases they've made。



![](img/20a38b57c67937002cd42f206242c79b_1.png)

They can complete this task by filtering data with the use of logical operators。

In Lucy Shru's database is a table calledCustom purchases。

 this table contains the data Lucy Shub needs to complete their queries。

 The data is divided into the following four columns， customer ID， customer names。

 customer locations and purchases。The value of each customer's individual purchase。

Ly Sub first need to identify customers from the location Hela County who have made purchases of over $2。

000， this requires two search conditions。The first is customers who are from Hela County。

 and the second is customers who have made purchases of over $2，000。

You can retrieve these details by writing a basic select statement as follows。

Begin with select All from the TCustom_ purchases。Next。

 type the where clause then the first condition as follows。

 purchases column the greater than operator and the figure of 2000。

Then type the and operator to include a second condition。

This second condition targets location column and uses an equal operator to return all results for Hela County。

The and operator here combines the two conditions， it ensures that both conditions are evaluated when filtering data from the table。

So your select statement is instructing SQL to select all records from the customer purchases table that satisfy the following criteria。

Purchases greater than $2，000 and made by customers in the location of Hela County。

For a record to be included in the results set， its purchases column must have a value greater than 2000。

If so， then the first condition yields a true value。In addition。

 the location column must have a value of Healla County， if this is the case。

 then the second condition also yields a value of true。And as you just learned。

 the and operator here insists that the results of both conditions are combined。

 this is another instance which yields a value of true。

So any records that match are included in the result。

 any records in the table that do not yield the value of true for both conditions are omitted from the results。

Your query is now ready to run， so press enterter to execute。

The results set that this query returns contains two records。

There are two customers from Hela County who've made purchases over $2，000。

 Benjamin Claus and Julie Mur。Now lucky showrub need to identify customers who are from Hela County or Santa Cruz County。

The logical operator or can be used to combine multiple conditions in the wear clauses。

 so it's perfectly suited to this task。For this query。

 you first need to generate a list of customers who are from either Hela County or Santa Cruz County。

So the first step is to write the following select statement。

Select all from customer purchases and then add the warehouse clauses。

This wear clause is then followed by the first condition， location equal to Hela County。

 then insert the or operator followed by the second condition， location equal to Santa Cruz County。

You now have a wear clause that uses the orR operator to combine the two conditions。

For a record to be included in the results set， its location column must have a value of Hela County。

 If so then it meets the first condition and yields a true value or the location column must have a value of Santa Cruz County if this is the case。

 then the second condition yields a true value。The orR operator ensures that at least one of these conditions will yield a true value。

 any matching records will be included in the result。

A record in the table that does not yield a true value for either condition is omitted from the result。

 press enter to execute the query。In this case， the result returns three records or customers。Next。

 Luc Srub need to retrieve the details of customers who do not reside in Hela County or Santa Cruz County。

They can perform this task using the not logical operator。

It's used in a similar way in the where clause of a select statement you can write the statement as before。

 but this time type a nu operator after the where clause， then list the conditions。

 location equal to Hela County or location equal to Santa Cruz County。In this query。

 the conditions have been enclosed in parenthses because there are multiple conditions parenthses are not required where you have just one condition。

The N operator checks the records for values that do not yield a true value for the given conditions；

 In other words， records that do not yield a value of true for either of the listed locations。

Press enter to execute the query and generate the output。

So all the records that have a location value which is not Hela County or Santa Cruz County are included in the result。

 the remaining records are omitted。

![](img/20a38b57c67937002cd42f206242c79b_3.png)

The output shows four records from the customer purchases table If you find all these examples and operators a bit complicated。

 don't worry youll review detailed examples of how to use these operators in later videos in this course for now you should just be able to identify each of the operators and explain their syntax。

