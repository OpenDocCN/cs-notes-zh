# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P77：9_使用Python在MySQL数据库中创建和读取数据.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

As you're aware， working with a database in Mysql involves Crd operations Work with databases through Python also involves Crd operations。

 The key difference is that the SQL statements used to carry out your operations must be processed in Python as strings In this video。

 you'll discover how to execute， create and read operations in a MysQL database using Python。😊。

Little Le is populating the restaurant's database with the records of upcoming bookings。

 Little Le also need to retrieve or read this data from their database。

 so they know which guests are attending for dinner。

You need to help little Lemon create and read data in their MysQl database using Python。But first。

 you need to understand how to create and read data in a Mysql database using Python。

Let's get started with creating data。So far， you've learned how to create data in a database using an insert statement like an insert into command。

 For example， little Lemon must use an insert into statement to add the names of customers and the time slots they've booked to the customer name and time columns in a table called bookings in their database。

 However， there are a few more steps to this approach when working with Python。😊。

Create your SQL statement as normal。 Then use quotation marks to convert it to a Python string argument。

This string argument is passed to a MysqL database through a connector which pares it into a format that MysQql can understand。

So the first step in the process is to write your SQL statement。

Then add a pair of quotation marks to convert it to a Python string argument。Finally。

 create a variable in which you can store the query as a Python string。Next。

 Python sends the string to the database through the cursor。

The statement is then executed on the database。Little Lemon can use Python to add booking data from guests to their MysqL database using the MysQqL insertt query variable。

The SQL data just needs to be passed in a string format。As you should know by now。

 you can also retrieve or query data from a database using a select statement。

 and a SQL select query is also the first step to complete when reading data using Python。

Python can read data from a MysQL database using a select statement。

 and just like with your insert query， you create a variable in which the query can be stored as a Python string and you write your select query。

Make sure that it's written within quotation marks to convert it to a Python string。

Little Le can use a Read data query string object to retrieve all data from their bookings table。

They just need to write the select query as a Python string。

 then use the execute module from the cursor object。

Now that you know how to create and read data using Python， let's see if you can help little lemon。

For the purpose of this demonstration， a connection has already been established between Python。

 the API and the MysqL database through the MysQl connector Python API。

So your first task is to instantiate the cursor object from the connection using the cursor method。

The next step is to execute the MySQL insert query by passing it as an argument to the execute method。

😊，Once the query is executed， commit the change to the database using the commit method of the connection object。

Now， each new instance of customer data is added to the bookings table in the database through the MySQL insertert query。

For the next stage of development， little Le needs to read or retrieve the data in their database。

 Some sample customer data has been added to the database to test the read functionality。

You need to develop the functionality and retrieve this data。As you learned earlier。

 the first step is to create a SQL statement as a Python string that you can pass to a variable。😊。

In this case， you need to create a SQL select statement that retrieves all data from the bookings table in the database and pass this statement as a string to the Python variable called Read data query。

Now you need to pass your query to the execute module on the cursor。

 just like you did when creating data。Once the query is executed。

 you need to retrieve the results using the fetcht all method on the cursor。😊。

Create a new variable called results， then pass the results of your query to this variable through the cursor object。

The results variable is at list data type， and it shows each record in the form of a topple。

So the results variable is essentially a list of topples。

 and each topple is a single extracted row from the bookings table。In this instance。

 the items in each topple in the result variable are ordered in the same way as the columns in the bookings table。

They are ordered this way because you are reading all records from the table。

You can retrieve the column names by creating a new variable named columns and calling the column names from the cursor object。

These values are then stored in the columns variable for later use。



![](img/43b08dc18794a2380f9f6dbfcee33f99_1.png)

Don't forget that it's also good practice to close the cursor object and connection when you no longer need them。

😊，You now know how to execute， create and read operations in a back end Mysql database using a front end Python application。

 That's a great start。 I look forward to guiding you through more Crd operations in Python。😊。



![](img/43b08dc18794a2380f9f6dbfcee33f99_3.png)