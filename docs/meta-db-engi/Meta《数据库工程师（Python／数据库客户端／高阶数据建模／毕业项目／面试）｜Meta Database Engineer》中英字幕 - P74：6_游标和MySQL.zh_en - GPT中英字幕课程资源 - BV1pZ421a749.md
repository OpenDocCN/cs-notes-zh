# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P74：6_游标和MySQL.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

When accessing a Mysql backend database using a Python frontend client。

 your Python application needs to know where the data required to complete your query is stored。

 A cursor indicates where this data is positioned on the database。 Over the next few minutes。

 you'll explore the concept of cursors。 Their key characteristics and learn how they work。

 Let's look at an example of cursors from little Les database。

 Little Le need to retrieve a guest's booking details。

 They can carry out this task with a SQL select query using Python。 However。

 the Python frontend client needs to know where the data is stored within the backend MysqL database。

 The MysqL database can use a cursor object to point to the records that little Le needs。

 This cursor helps the Python client locate the required data。



![](img/0de29f7a12074ab5aefeda3b72b6ae53_1.png)

This example offers a good understanding of what database engineers mean by the term cursors。

 A cursor is a pointer that directs the Python client to the results of your SQL query within the MysQqL database。

 The cursor indicates the location of the queried data by identifying specific rows or records。

 You can use a cursor to read， retrieve and move through individual records within the results of your query。

 Cursors have several key characteristics or features that are particularly useful to database engineers。

 For example， cursors are read only。 So you can't update the data that they are associated with。

 The results can't be modified。 Theyre preserved by the cursor。 Cursors are also nonscrorollable。

 They fetch records in order， which helps to keep track of your position when processing individual records。

 You can't skip or jump between records or fetch them in reverse order。

 and cursors are also a sensitiveensitive。😊。

![](img/0de29f7a12074ab5aefeda3b72b6ae53_3.png)

This means that they point to the original data within the Mysql database instead of a copy。

 This is faster than using insensitive cursors， which take longer to return results because they can only point to a copy of the data。

 So how can you use a cursor in a Mysql database query。



![](img/0de29f7a12074ab5aefeda3b72b6ae53_5.png)

The first step is to declare the cursor。 Use the declare statement and assign your cursor a custom name。

 followed by the cursor keyword。Then use the four keyword and a relevant SQL select statement to determine the purpose of the cursor。

 Next， you need to open the cursor。😊，Type the open command and call your cursor's name to establish the results set。

 Now， the cursor is pointing to the set of results from your select statement。

The next step is to fetch or retrieve the results of your statement。

 type the fetch command and the name of your cursor。 Then type the into keyword。

 followed by the name of the location the results need to be transferred to。For example。

 the results can be transferred to a local variable to be used in your Python application。

The final step is to close the cursor。 type the close command， followed by the cursor name。



![](img/0de29f7a12074ab5aefeda3b72b6ae53_7.png)

Closing a cursor is always good practice to release the memory associated with it。

 As you learned earlier， a cursor is non scrollrollable。 It works through the results set and order。

 So once it reaches the last result， it no longer needs to remain open。

 So close the cursor to free up the memory it uses。😊。



![](img/0de29f7a12074ab5aefeda3b72b6ae53_9.png)

Now that you are familiar with how cursors work， let's return to Little Lemon's query。



![](img/0de29f7a12074ab5aefeda3b72b6ae53_11.png)

Little lemon can use a cursor to retrieve the booking data for their guest。 First。

 they declare a new cursor called guest booking details。

 This is followed by a SQL select statement that targets the guestss data from the little lemon Mysql database。

 They then open the cursor。 Next， they fetch the data and store it in a variable within their Python client called booking data。

 You should now be able to explain what cursors are in a Mysql database。

 De their key characteristics and explain how they work。😊。



![](img/0de29f7a12074ab5aefeda3b72b6ae53_13.png)

You'll explore cursors in much more detail as you progress through this course。

 So this is a great start to your MysQL Python journey。😊。

