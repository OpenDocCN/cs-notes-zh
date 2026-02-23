# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P76：8_模块小结 使用Python与MySQL交互.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

Congratulations， you've reached the end of the first module in this course。

 You should now be familiar with the basics of how to interact with a Mysql database using Python。😊。

Let's take a moment to recap some of the key skills you've gained in this module's lessons。

In the first lesson， you received an introduction to the course in which you developed an understanding of how a connection is formed between Python and a Mysql database using an application programming interface or API。

 also known as a driver。You now know that a front end Python application sends a connection request to the Connector API。

The API forwards this connection to the back end Mysql database。

 A cursor connection can then be established。 Once the connection is established。

 data can be sent between Python and Mysql。 You also learned about the different APIs that can be used to create this connection and that as a database engineer。

 Youll rely on the Mysql connector Python API。

![](img/f753f8d7a821fa58a6ff2b8333ff046d_1.png)

![](img/f753f8d7a821fa58a6ff2b8333ff046d_2.png)

During this first lesson， you also learned how to install and configure Python software on your system so that you could create a connection between Python and Mysql。

You learned how to download Python， make use of Pip。

 and import the different packages that you require。

 And you also learned how to use aliasing to create custom names to facilitate easier communication with the database。

 You then explored a working example of how to connect to a Mysql database using a Python client。

You saw how the API is imported into a Python program and can be used with an alias。

 and you now know how to make use of its modules and functionality using the access or dot operator。

And you also know how to pass arguments to a connector module， like usernames and passwords。

You then ended this lesson with an overview of the process for creating tables in a database。

 using Python。You learned that you need to create a cursor object that you can use to communicate with the MySQL database。

The cursor object accesses an execute module that carries queries as Python strings to a MysQL database。

😊，Once your connections are set up， you can then create data in a MysQql database using Python like databases and tables。

 In the final lesson in this module， you learned about cursors。

 You learned that cursors are used to indicate where data is positioned in a MysQql database so that it can be accessed by a Python client。

😊，The cursor lets you read， retrieve and move through individual records within the results of your query。

 You then explored the key characteristics or features of cursors that are particularly useful for database engineers。

 You learned that cursors are read only so they can't be modified and preserve results。

 You discovered that cursors are also nonsrollable。 They fetch records in order。

 which helps you to keep track of your current position when processing individual records。

 And you also found out that cursors are a sensitive。

 This means that they point to the original data within the Mysql database Instead of a copy。

 You then explored the code required to use a cursor in a Mysql database。😊。

You can now use commands like declare to declare a cursor。

 the open command to call the cursor's name， the fetch command to fetch results。

 and the close command to close the cursor。You then explored an example of this process from Little Lemon's database。

In the next part of this lesson， you explored different cursor subclass。

 and you learned how they can be used to change or alter the behavior of your cursors。😊。

You discovered that cursor classes are a method of translating communications between Python and a MysqL database。

 Classes take Python string objects and parse them into MysQl friendly commands and data types that can be understood by the database。

You also explored some common examples of cursor subclass。

 Subclass inherit the properties of their parent cursor class， like the cursor Ra subclass。

 the cursor Dictionary subclass and the buffered Cursor class。



![](img/f753f8d7a821fa58a6ff2b8333ff046d_4.png)

You also learned about the interleaving SQL requests。

 which involve taking part of a SQL query to make a subsequent request。



![](img/f753f8d7a821fa58a6ff2b8333ff046d_6.png)

You then explored the syntax for creating and using subclass。

 And you also explored an example of subclass from the little Lemon database。😊。



![](img/f753f8d7a821fa58a6ff2b8333ff046d_8.png)

You should now be familiar with the basics of how to interact with a Mysql database using Python。

 including establishing a Mysql Python connection and working with cursors。 Great work。

 I look forward to guiding you through the next module in which you'll learn how to perform queries in Mysql using Python。

😊。