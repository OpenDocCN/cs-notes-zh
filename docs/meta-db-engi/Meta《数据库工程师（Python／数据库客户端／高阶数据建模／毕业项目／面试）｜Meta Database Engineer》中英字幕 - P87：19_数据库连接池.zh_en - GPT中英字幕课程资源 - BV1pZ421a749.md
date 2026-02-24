# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P87：19_数据库连接池.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

A MysQL database needs to provide access to many users at once。

 and each connection must be secure and stable so that only authenticated users can gain access and theres no risk of their connections failing。

But managing secure and stable connections requires many resource heavy actions。

 So how can you perform these actions efficiently， The answer lies in database connection pooling。

In this video， you'll explore the concept of database connection pooling， investigate how it works。

 and learn about its advantages。Little Les website has a Python based application that lets guests book time slots with the restaurant。

 The application sends the guests' bookings as SQL statements to the little Le database。 However。

 the website needs to provide each guest with a secure and stable connection to the little Le database。

 This is so that they can input their booking data without any risk of connection failure。



![](img/eccc9ef2ee9149d971c9cb953838efc0_1.png)

Little Le can manage these connections with the use of database connection pooling；

 let's find out more。Database connection pooling involves creating and managing a pool of connections to run faster。

 more efficient and optimized connections between clients and a MySQL database。



![](img/eccc9ef2ee9149d971c9cb953838efc0_3.png)

To gain a better understanding of how connection cooling works， let's explore a visual example。😊。

Visualize a pool of four open connections to a Mysql database。

 Two of the connections are currently being used by clients to access the database。

 The other two connections are free and ready to use by any new user。

A new user can arrive and request access to the database。

 The connection pool then assigns this new user， one of the open connections。

 Shortly after the new user is assigned their connection， the first two users complete their tasks。

 end their sessions and leave the pool。Even though the users have left the pool。

 the connections remain open。 technicalically speaking， the connections aren't closed。

 They are just placed back in the connection pool where they remain available for new users。

There are now three free and ready to use connections that can be assigned to new users。



![](img/eccc9ef2ee9149d971c9cb953838efc0_5.png)

But what if all four connections are in use and a fifth user wants to join。

There are only four connections available， so how can you serve the fifth user's access request？

To avoid this situation， the best approach is to create multiple pools with a specific number of connections assigned to each pool。

This means that different users can be assigned to different pools。

 So there's always an available connection in at least one pool for new users。



![](img/eccc9ef2ee9149d971c9cb953838efc0_7.png)

You can also program the system to create a new connection within a pool if an appropriate connection isn't available in other pools。



![](img/eccc9ef2ee9149d971c9cb953838efc0_9.png)

Little Le can use this approach to manage connections to their MysqL database。

 They can create a series of connection pools that their guests can use to record their bookings in the database。



![](img/eccc9ef2ee9149d971c9cb953838efc0_11.png)

There are a few key advantages to connection pooling。

 Connect pooling makes efficient use of available resources。

 It reduces the time and effort required to establish connections。

 Connect pools simplify programming models， and they increase the performance of the Python application when connecting to the My equalql database。



![](img/eccc9ef2ee9149d971c9cb953838efc0_13.png)

You should now be familiar with the concept of database connection pooling。

 be able to explain how it works and describe its advantages。

 There's lots more to learn about connection pooling in this lesson。

 but you are off to a great start。😊。