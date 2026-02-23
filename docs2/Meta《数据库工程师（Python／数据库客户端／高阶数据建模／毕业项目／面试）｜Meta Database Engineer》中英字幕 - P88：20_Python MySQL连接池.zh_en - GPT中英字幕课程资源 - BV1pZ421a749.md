# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P88：20_Python MySQL连接池.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

Daabase connection pools are a great way of providing secure。

 authenticated connections to a database for multiple users。

 and the MySQL Connector Python API provides a useful method for developing connection pools in the form of the MysSQL connection pool module。

In this video， you'll learn how to create a connection pool for a database using the MySQL connection Po module。

Little lemon need to provide secure， authenticated connections to their database for their team of web developers。

 They've decided that the most efficient way of providing these connections is through connection pooling。



![](img/112589b4502bdf9ed744380bfdddc8f8_1.png)

Let's take a few minutes to find out how to build a connection pool。

Then use your new skills to help little Le build a secure connection pool。

A database connection pool is managed and maintained using a module called MySQL connection Po。



![](img/112589b4502bdf9ed744380bfdddc8f8_3.png)

The module is held in a directory called MysQL dot connector dot Poing。



![](img/112589b4502bdf9ed744380bfdddc8f8_5.png)

You can import the module into your working environment and access its functionality using the import syntax。

 and the Fr keyword is used to identify the module's location。In other words。

 the code is instructing Python to access the subdirecty and return the MysQL connection Po library。



![](img/112589b4502bdf9ed744380bfdddc8f8_7.png)

The MysQL connection pool module has many useful functions and attributes that you can make use of Let's look at a few of these。

😊，The pool name class attribute is used to identify the name of the pool to be used in the connection。

If you don't specify a pool， then one is automatically generated。 Instead。

 you can create as many pools as you need。The pool size attribute states the number of connections that have been created for a pool。

 The default number of connections is 5， but you can create up to 32 connections for a single pool。

And finally， there's the connection I D attribute。 This is a unique I D assigned to each connection in the pool。

 There are also many class methods available in the MysQL connection pool module。😊。



![](img/112589b4502bdf9ed744380bfdddc8f8_9.png)

You can use the get connection method to request a connection。

 The pool then assigns a free connection If one is available。 If no connection is available。

 then you'll receive a pool， exhausted error instead。

The is connected method is a boolean function that returns either a true or false value。

 depending on whether a connection has been made。This is a useful way of avoiding errors。 Finally。

 the close method informs the connection pool that a user has completed their session。

 The user no longer needs the connection， so the connection can be placed back into the pool as an available connection for any new users who need it。

😊。

![](img/112589b4502bdf9ed744380bfdddc8f8_11.png)

Now that you're familiar with the module connection pool， let's see if you can help little lemon。

As you learned earlier， little Lemon want to create a connection pool to provide users with efficient access to their database before you can create a connection pool。

 you first need to import the MysQql connection pool library using the MysQqL Connector Python API。😊。



![](img/112589b4502bdf9ed744380bfdddc8f8_13.png)

Once you've imported the connector， the next step is to make a connection to the database。

 Call the pool little lemon pool， Then use the pool size attribute to specify four connections。

 Use the local host as your host and place the pool on the little Le database。

 Then type the username and password。😊。

![](img/112589b4502bdf9ed744380bfdddc8f8_15.png)

![](img/112589b4502bdf9ed744380bfdddc8f8_16.png)

All this code is passed as arguments or parameters to the MysQL connection pool module and assigned to the pool。

 Next， you need to create a Python list of users for the connection pool。

 you can call this list users。😊。

![](img/112589b4502bdf9ed744380bfdddc8f8_18.png)

Populate the list with members of Little Lemon's guest list。

You then need to create a SQL select statement。

![](img/112589b4502bdf9ed744380bfdddc8f8_20.png)

This statement must accept an integer。 The integer must correspond with different I requests。

 accessing different data points as database users。



![](img/112589b4502bdf9ed744380bfdddc8f8_22.png)

Now， you need to use the for loop。 You can use it with the range function。

 The range function is used with the pool size attribute。



![](img/112589b4502bdf9ed744380bfdddc8f8_24.png)

This means that no matter how big the pool is， the loop always runs to the end。

The next step is to set up the application's connection。😊。

Write a statement that checks if a connection was successfully made within the pool。

This statement also avoids any errors appearing in your coat。

Then write a statement that instantiates a new cursor from the existing active pool connections。

This action must occur for each new live connection thats successfully made with the pool。😊，Next。

 create a print statement that displays the following information on screened。

The user requesting information from the database， the unique connection assigned to this user and the unique booking ID that they're requesting。

The print statement is formatted using curly braces。

These symbols take the specified variables in the order that they are specified from the format function。

So this means that the information is printed in the order you specify。

The next line of your code is a parameterized select statement。

 This statement uses the initial SQL select statement from earlier and combines it with the incremented eye to assign a different booking I to each user。

😊。

![](img/112589b4502bdf9ed744380bfdddc8f8_26.png)

Then you can use the fetch all method to return all information that corresponds with this SQL select statement and print the information on screen。

You can also create an else statement that generates an error message on screen if a live connection cannot be found。

Finally， use the close method to return a user's connection back to the pool when they have ended their session。



![](img/112589b4502bdf9ed744380bfdddc8f8_28.png)

You should now know how to create a connection pool for a database using the functions and attributes available with the MySQL connection pool module。

