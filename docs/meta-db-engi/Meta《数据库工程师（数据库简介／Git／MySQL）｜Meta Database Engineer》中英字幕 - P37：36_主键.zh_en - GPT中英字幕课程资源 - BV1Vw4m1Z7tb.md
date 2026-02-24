# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P37：36_主键.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

By now you're probably familiar with querying values or records within database tables。

But how do you query specific records and values if they're duplicated across a table？

When you come across obstacles like these， you can use keys as your solution。In this video。

 you'll learn how to explain the purpose of primary key in a database table and select a simple and composite primary key。

😊。

![](img/ee7f2250fad9ea7c2cbedb318d5e478b_1.png)

You may have encountered several examples of primary keys during this course， and in these examples。

 you saw that they're using tables as a unique method to identify a record and prevent duplicates。

Let's take an example of a student table with five attributes， ID， name， date of birth， email。

 and grade。How could we identify a specific student to enter their grade？

Like the student Mary on row2。All you need to do is find the unique ID of Mary to identify a record of her data。

However in this example， you can't use the student name column because there are two students in a table called Mary。

 and you can't use the date of birth either because there' another student in a table called Dan has the same birthday。

Neither of these records are unique to Mary， so what's the best approach？



![](img/ee7f2250fad9ea7c2cbedb318d5e478b_3.png)

The solution is to locate a candidate key。This is an attribute that's unique to each row of the table。

 and it cannot have a null value， In other words， it cannot be empty。



![](img/ee7f2250fad9ea7c2cbedb318d5e478b_5.png)

In this example， there are two possible candidate keys， the student ID and the student email。

Both rows contain unique value for each student。So either one can be used as the primary key。

Let's assign the student ID as the primary key。Whichever column you reject as the primary key becomes the alternate or secondary key in this instance。

 the email column is the secondary key。

![](img/ee7f2250fad9ea7c2cbedb318d5e478b_7.png)

But what happens if you can't locate a unique value within a table？

Maybe all rows of duplicated values。In this instance， you can create a composite primary key。



![](img/ee7f2250fad9ea7c2cbedb318d5e478b_9.png)

This type of key is a combination of two or more attributes。

Let's take the example of the delivery department of an online store。

They have a delivery table that tracks the deliveries placed by their customers。However。

 there is no single column with unique values in each row。So。

 no column can be considered as the primary key。In this case。

 the best approach is to combine the custom ID and product code columns to create a unique value for each specific record of data。

With these columns， you can determine which customer ordered what product。

 so together these columns become the composite primary key。

And this key can be used to track the delivery status for each customer。😊。



![](img/ee7f2250fad9ea7c2cbedb318d5e478b_11.png)

You're now familiar with one single columnum primary and composite primary key。

You should now also be able to identify the most appropriate situation in which to use each one。

Great work。