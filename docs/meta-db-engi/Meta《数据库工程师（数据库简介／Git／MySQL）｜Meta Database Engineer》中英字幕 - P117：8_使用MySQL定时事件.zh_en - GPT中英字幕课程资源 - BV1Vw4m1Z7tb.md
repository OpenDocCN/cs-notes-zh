# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P117：8_使用MySQL定时事件.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

When working with MysQL databases， there'll often be tasks or events that must be completed at specific times。

 like inserting data or generating reports with MysQqlL scheduled events。

 you can make sure that these events occur at the scheduled time。

 even if you're not present In this video， you'll learn what a Mysql event is。

 review the syntax used to create events and explore some examples。😊。

Lucky shrub often make use of MysQL scheduled events。 For example。

 the F department has just requested a report on all orders received this month。 However。

 this report must be generated at 1159 PM on the last day of the month。

 Lucy shhrub can use a one time event to create this report。

 They can schedule their Mysql database to generate the report at the specified time and date。

 before you find out how lucky shrub can create this event。

 let's first find out more about what a MysqL scheduled event is。

 A scheduled event in MysqL is a task executed according to a given schedule。 In other words。

 it's an event that takes place at a specified time。

 Each event has a unique name and contains one or more SQL statements。

 They're stored in the database and can be executed just once or they can be a recurring event。

 The main types of scheduled events that you'll work with in MysQqL include one time events and recurring events。

 Onetime events。😊，Scheduled events that occur just once， for example。

 inserting data into a table one hour from now。 and a recurring event is a scheduled event that occurs on a regular basis。

 like generating a weekly report from a database。 So how do you create a MysQL scheduled event。

 Event are created in MysQl using the create event keywords。

 Let's find out more about how this syntax works。 First。

 create the event using the create event keywords。 You can follow these keywords with， if not exist。

 This tells Mysql to create the event only if it doesn't already exist。

 Then follow these keywords with a unique event name。 Next。

 type the on schedule keywords and specify a scheduled time at which the event must occur。

 Then type the do keyword。 This keyword is followed by the event body in which you specify the logic of the event using SQL statements。

😊，So how can you use this syntax to differentiate between one time and recurring events。

 If your scheduled event is a one time event， then specify the schedule using the at clause。

 This is followed by a time stamp and interval keyword and a specific time at which the event must be executed。

 For example， Lucky shhrub can use this syntax to generate a one off revenue report 12 hours from now。

 and they can create their event logic within a begin end clause。

 C a recurring event is more complicated。 The syntax is largely the same。

 The key difference is that you must use the every clause instead of at followed by an interval。

 You can also use the starts and ends keywords with the times stamps and intervals to designate specific start and end pointss for the event。

 Lucky shhrub can use the recurring event syntax to create a daily stock check event。

 If the event identifies that some stock levels are too low。

 It sends out an order to restock those items。 You'll find out more about how lucky shr。😊。

Can create this and the previous event in just a moment。 before then。

 let's look at how to delete or remove an existing MysQL event that's no longer needed using a drop event statement。

 First， type the drop event keywords。 It's also good practice to include if exists。

 This tells MysQL to check if the event still exists and hasn't already been dropped from the database。

 Finally， type the event name and then execute the statement。😊。



![](img/a06c0d884471af31892215c5e034a833_1.png)

Now that you're familiar with scheduled events and their syntax。

 let's see if you can help Lucky Shrub generate that report。😊，As you saw earlier。

 Luc Srbb's finance department has just requested a report on all orders received this month。

 They need the report generated at 1159 PM on the last day of the month。 However。

 it's now the last day of the month， and it's also approaching 12 noon。

 So they need the report 12 hours from now。 This is a one off event。

 So begin with the create event keywords。 Then assign the event a unique name。

 Let's use generate revenue report。 Now you need to specify the schedule。

 Since this is a one time event。 Use the Act clause。

 Then schedule the event to occur 12 hours from now。

 So include the current time stamp and add a 12 hour interval。

 The next step is to add the schedule's logic。 type the do keyword and at begin an end block。

 within this block， Instruct my sequel to select all data inserted into the orders table this month。

 and to place that data within a report data table。 Great，12 hours from now， the finance department。

😊，Have their report。 Lucy shrub need your help with another task。

 They're reviewing their stock and need to make sure that they have at least 50 units available for each item on sale。

 You can help them by using a recurring event。 First， create the event and call it daily restock。

 then specify the schedule。 as this is a recurring event。

 use the every clause and schedule it to occur once a day。 Next。

 add the do keyword followed by a begin and end block。 within this block to the event's logic。

 My SQL must check if the number of items for any record in the product table is below 50。

 If My SQL locates a record below 50， then the number of items must be updated。

 If at any stage you need to remove this event， just type the drop event keywords， then if exists。

 followed by the event name。😊。

![](img/a06c0d884471af31892215c5e034a833_3.png)

Great work you've helped Lucky Srub to create these events in their database。

 you should now be familiar with the basics of MySQL scheduled events。

 include different types of events and their syntax well done。😊。

