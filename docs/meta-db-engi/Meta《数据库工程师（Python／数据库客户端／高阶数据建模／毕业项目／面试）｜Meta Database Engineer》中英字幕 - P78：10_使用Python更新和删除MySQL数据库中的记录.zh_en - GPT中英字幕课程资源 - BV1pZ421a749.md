# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P78：10_使用Python更新和删除MySQL数据库中的记录.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

Updating and deleting records in a Mysql database involves routine crud operations。

 They are also common operations for a Python based application that interacts with the Mysql database。

 Over the next few minutes， you'll learn how to execute update and delete operations in a back end Mysql database using Python。

😊，Little Le needs to update and delete the records of the restaurant guests in the bookings table in their database using Python。

 You need to help little Le with this task。 But first， let's take a quick look at the bookings table。

This table holds the booking data of each guest。 This includes their booking I， table number。

 first and last name， booking slot， and the I D of their waiter。

Little Lemon must update and delete data within this table using Python。

Let's begin with updating records。As you know from previous courses。

 data is updated in a database using update statements。

 Little Lemon needs to update the booking data of a guest。 Let's see if you can help them out。

You can start by writing a SQL update query that uses a where clause to let little Le update a guest's table number。

The update query is created as a string。 It's then passed to a string object called Up bookings。

Little Le just needs to update the specific values of each query。

Let's test this query by updating the booking information for guest 6， Diana Pinto。

 who has been moved to table 10。Use the execute method to run the query and update the records in the bookings table in the database。

😊，To commit these changes to the table in the database。

 use the commit method to check that the data was updated correctly。

 you can run the print cells of the Jupiter notebook。

 The guest with the booking I D of 6 is now assigned to table 10。 The update query has worked。

There are also times when guests cancel their bookings。 when this happens。

 little Lemon needs to delete their records from the database to carry out this task。

 Write a sQL delete statement that deletes the record of a specific guest from the bookings table。😊。

Your statement can use a where clause of bookinging ID。

The delete statement is created as a Python string。

It's then assigned to a string object called Delete Booking ID。

You can test this query by deleting the booking information from Marcos Romemerro。

 who has assigned the booking ID of4。😊，Use the execute method to run the query。

Then commit the changes to the database。Now， it's time to check that the query worked with another print out。

 You can rerun the cells with the initial select query from the Jupiter notebook。

The printout changes if the database has been altered。

There's no data in the table for Marco's Romemerro。

 This means that your delete statement was successful。

You can also amend the wear clause in your delete statement to check for null values next to table and employee IDs。

If the value is null， then you can set the bookings to be deleted。



![](img/0d32bdecd8bdc76869312130fee014f7_1.png)

You now know how to perform update and delete operations in a MysQL database using Python。

 great work。😊。

![](img/0d32bdecd8bdc76869312130fee014f7_3.png)