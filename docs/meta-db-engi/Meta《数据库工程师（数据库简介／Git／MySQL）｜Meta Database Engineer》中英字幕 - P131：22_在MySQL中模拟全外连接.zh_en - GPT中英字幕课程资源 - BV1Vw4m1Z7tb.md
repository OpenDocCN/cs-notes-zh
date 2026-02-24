# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P131：22_在MySQL中模拟全外连接.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

When analyzing data， there may be times you need to extract all records from two separate tables。

 You could use a join， but this would just return matching records。

 Sometimes you'll also need records that don't match。

 So the solution is to emulate a full outer join。 This method extracts all records。

 even those that don't match。 In this video， you'll learn how to emulate the full outer join or full join in My SQel to extract data from tables。

 Luc shrub need a list of all their new orders and the clients who place them。

 They also need the data of clients who didn't place orders。 This data is stored in two tables。

 clients and orders。 My SQL supports inner left and right joins。

 but these won't return the required data from both tables。

 So Luc shhrub need to emulate a full join to extract this data。

 You can help Luc Srub to complete this task。 But first。

 let's find out more about what a full join is and how it works In SQl， a full。😊。

Join returns all records from a left and a right table when it identifies a match between the two。

 This includes records that match and those that don't。 However。

 My sQL doesn't support the full outer join。 So you need to emulate it using a combination of the left join and the right join。

 You also need to use the union all operator to return duplicate records。 should they exist。

Alternatively， you could use the union operator to retrieve unique records only。

 Let's take a few moments to explore the syntax for these methods。

 Here's how to emulate a full outer join using a union all operator。 First。

 type a select command followed by the names of the columns that you require。

 Then use a from clause to target the first table which is your left table。 Next。

 use a left join clause to join the first table with the second table。 the right table。

 Then use an on keyword and dot notation to equate the matching columns between the two tables。

 Now that you've。😊，S to the left join。 You need to create the right join。

 but you also need to combine these joins using a method that returns all duplicate records。

 It's at this point in your syntax that you can add the union all operator。

 Once you've added the operator， create the right join。 As you should already know。

 the syntax is almost the same as the left join statement。

 The key difference is that you must use a right join clause。 When executed。

 the union all statement returns all duplicate records should any exist。

 But what if you only want unique records to retrieve unique records only you can use the union operator。

 The syntax is largely the same， you need to script a right join and a left join statement as before。

 But this time place the union operator in between the two statement instead of union all。

 Then when executed the statement only returns unique records。 For example。

 Lucky shrub can use the union operator syntax to return unique records from the clients and orders tables。

 Let's see if you can help lucky shrub to emulate。😊。



![](img/5adfed05cf7e9950fb1804298d8414fd_1.png)

Full outer join using the union operator。As you learned earlier。

 luckyky shrub need records of all new orders from the orders table and the records of the clients who place these orders from the client's table。

 They also need the data of clients who didn't place orders。 Start with a select statement。

 Then target the following required columns from the client's table using dot notation， client I D。

 full name and contact number。😊。

![](img/5adfed05cf7e9950fb1804298d8414fd_3.png)

Then target the following columns from the orders table， order I D， cost and date。

 Then use the from clause to identify clients as the left table。

 Join it to the orders table with a left join clause。

 The next step is to use the on keyword to equate client I D as the matching column between both tables。

 Then add the union operator so that the syntax retrieves unique records only。Now。

 it's time to script the right join statement。 Again。

 the syntax is mostly the same as the left join statement。

 Just use a right join clause instead of a left join one。 Finally。

 press enter to execute the statement。 The output shows all client Is with their related order Is。

 It also shows matching order Is and client Ids along with Ids that don't have a match。

 Lucky Srub now have all the records that they require from their database。

 and you should be familiar with how to emulate a full outer join in My SQL using the union and union all operators。

 Good work。😊。