# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P70：2_MySQL Python连接.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

Many of the web applications that you use every day rely on a MysQql database to send and store data。

 and many of these same applications are developed in Python。

 Dataase engineers can send and store data from a Python based application to a MysQL database using a MysQL Python connection。

In this video， you'll explore the basics of this important connection and learn how it works。

 Over at Little Lemon， The restaurant needs to connect a Python application with its MysqL database。

 They need to form this connection so that they can perform basic Mysql tasks using Python。

 and they also need your help with these tasks。 But first。

 you need to understand how the connection between Mysql and Python works。

 So let's take a few moments to explore the connection between Python and a Mysql database。

 A connection is established between Python and a Mysql database using an application programming interface or API。

 An API is also commonly known as a driver or client。

 The API is a written set of programs or software that acts as a bridge between the frontend Python application and backend Mysql database。

 This connection can be created using different APIs like SQqL alchemy MysqL client and Mysql connector Pyon。

😊。

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_1.png)

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_2.png)

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_3.png)

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_4.png)

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_5.png)

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_6.png)

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_7.png)

MySQL connector Python is the most common API and the one that you'll focus on in this course。

 a useful way of understanding the connection between MysQL database and Python is visually。



![](img/8a96b62a7a0e2d19f7b9ce71f350760b_9.png)

Picture a diagram with a Python application on one side and a Mysql database on the other in between these two elements is the Mysql connector Python API In a typical interaction between these elements。

 The front end Python application sends a connection request to the connector API。

 The connection request is the Python application asking for permission to access and retrieve information from the database using Python。

 The API forwards the request to the backend Mysql database。 The database accepts the connection。

 It then sends a message to the Python application back through the API confirming that the connection has been established。

 In other words， Mysql gives the API permission for the Python application to access the database。



![](img/8a96b62a7a0e2d19f7b9ce71f350760b_11.png)

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_12.png)

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_13.png)

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_14.png)

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_15.png)

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_16.png)

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_17.png)

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_18.png)

Now， the Python application sends a connection request to the database。

 Once the connection is established， you can then instantiate an instance of the cursor from the connector class。

 And when a cursor object is created， you can then execute SQL queries in the MysqL database using Python。



![](img/8a96b62a7a0e2d19f7b9ce71f350760b_20.png)

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_21.png)

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_22.png)

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_23.png)

Let's look at Little Lemon's database as an example。

Little lemon need to check what time a guest is arriving for dinner using their Python application。



![](img/8a96b62a7a0e2d19f7b9ce71f350760b_25.png)

The date and time data for the guests' booking is stored in the back end database。

 So the Python application uses the execute module from the cursor object to carry out the customer's demand。



![](img/8a96b62a7a0e2d19f7b9ce71f350760b_27.png)

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_28.png)

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_29.png)

The records are returned through the cursor object in the form of topples that show the booking slots of each guest。

 Once the request has been fulfilled， the cursor object and database connection can be closed。

 You should now understand and be able to explain how a connection works between a Python application and a Mysql database。

 I look forward to teaching you more about the Mysql Python connection in other videos。😊。



![](img/8a96b62a7a0e2d19f7b9ce71f350760b_31.png)

![](img/8a96b62a7a0e2d19f7b9ce71f350760b_32.png)