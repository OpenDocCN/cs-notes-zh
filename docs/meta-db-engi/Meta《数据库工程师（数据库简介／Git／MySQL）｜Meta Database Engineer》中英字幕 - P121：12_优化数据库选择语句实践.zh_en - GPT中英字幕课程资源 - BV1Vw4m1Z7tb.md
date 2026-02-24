# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P121：12_优化数据库选择语句实践.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Lucky shrub have received large numbers of orders from their clients and need to query this data quickly and efficiently using select statements。

 They must make sure their queries are optimized so that my SQL can compile and execute them efficiently。

 First， the sales department needs to find out which orders are arriving on September 12。

 They can write a select query that uses the where clause and date underscore ad function。

 But sorting through the data to calculate delivery dates using the date underscore ad function in the where clause places a lot of extra load on the database。

 A more efficient method is to generate a custom column in the orders table called expected delivery date。

 This column shows the expected date of each delivery。 So now。

 Luc Srub just need to scan this column for all values that match September 12。

 and they no longer need to use a function。 The sales department's next task is to process an order for a customer with the surname of Eto。

 First， they need to find the customers。😊。

![](img/6e292254dd76eca3f3321ea749575ac7_1.png)

Details in the client's table in the database。 One method is to use a select statement that combines a leading wild card with the like operator。

 But My SQL can't make use of an index when there's a leading wild card。

 The solution is to add a new column to the client's table using an alter table statement and call it reverse full name。

 The reverse full name column contains the client names， but reversed。 In other words。

 the client's last name or surname is listed first。 Then their first name。

 You can run an update statement on the client's table to carry out this task。 Next。

 use that create index syntax to create an index on the new column。 Don't worry about this syntax。

 for now， you'll explore it in more detail in a later video。😊。

You can now make use of a trailing wild card with the like operator on the reverse full name column to achieve the same result。

 and you can still use the index。 Finally， the finance department need a report on all orders placed with the store。

 They can extract this information by targeting that product and orders tables in the database。

 Usually， this task could be completed by using an outer join query。 However。

 this type of query also returns records that don't match from both tables。

 even though they're not required。 A more efficient method of querying these tables is for lucky sh to use an inner join that targets the shared product I D columns from both tables。

 This returns only the matching records。 So it's a much more efficient way to execute the query。😊。



![](img/6e292254dd76eca3f3321ea749575ac7_3.png)

You should now know how to optimize My SQL select queries and be familiar with basic optimization guidelines。

 well done。😊。

![](img/6e292254dd76eca3f3321ea749575ac7_5.png)