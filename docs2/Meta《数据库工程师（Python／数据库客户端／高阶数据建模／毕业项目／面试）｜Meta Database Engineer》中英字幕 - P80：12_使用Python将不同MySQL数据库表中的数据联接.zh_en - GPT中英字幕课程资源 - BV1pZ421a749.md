# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P80：12_使用Python将不同MySQL数据库表中的数据联接.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

At this stage of your database engineering journey。

 you should have experience of using join operations to extract data from multiple tables。

 There are also instances in which you'll need to perform a join operation on a Mysql database using Python。

😊，In this video， you'll explore the process for executing join operations using Python。

Little lemon are adding a new menu feature to their website。

 This feature lets customers view menu items， their prices。

 and the type of cuisine each meal is related to。The data that the feature requires is in two different tables in their MysQL database。

 menu and menu items。

![](img/c8e706fcbe2b8242d012a6856d0916c0_1.png)

Little lemon need to use a join to combine the data from these tables to create their menu feature。

Let's quickly recap the concept of a join。A join is created using the sQL join clause。

 It targets a common column between the two target tables。

 These common columns are used to join the tables together and extract the required records。

 Some examples of joins used in My SQL include left join， right join， inner join and outer join。

 All these joins can be used with Python。

![](img/c8e706fcbe2b8242d012a6856d0916c0_3.png)

![](img/c8e706fcbe2b8242d012a6856d0916c0_4.png)

Let's explore an example of the syntax and process for creating an inner join。First。

 a SQL query is created using join as a Python string that can be passed to a variable。

The query is then run using the execute method from the cursor object。



![](img/c8e706fcbe2b8242d012a6856d0916c0_6.png)

Once the query is executed， you can retrieve its results into another variable。

Use the fetchol method on the cursor object that holds the results of the join。



![](img/c8e706fcbe2b8242d012a6856d0916c0_8.png)

The data is retrieved as a list of topples。 For example。

 little Le can create a join query as a string object in Python that combines the menu items and menu tables。

 This join is performed using an inner join on the item I D column， which is common to both tables。

 When executed using Python on a Mysql database， This statement returns all required results。



![](img/c8e706fcbe2b8242d012a6856d0916c0_10.png)

Now that you're familiar with the process for joining data from different tables using Python。

 let's see if you can help little Le to create this query。As you learned earlier。

 little Lemon need to use a join query to extract the data for the new menu feature on their website。

😊，They begin by creating the joint statement as a string object in Python。

Store it in a variable called My Jo query。The Jo query must target the name。

 type and price columns from the menu items table。And it must also target the cuisine column from the menu table。

An inner join is created on the item ID column， which is common to both tables。



![](img/c8e706fcbe2b8242d012a6856d0916c0_12.png)

Let's assume that the MysQL connector Python API is running a connection between the front and back end and that the cursor object is also available。

This means that you can now execute your query using the join statement。



![](img/c8e706fcbe2b8242d012a6856d0916c0_14.png)

Run the query using the execute method from the cursor object。When the query is executed。

 you can fetch all the results from the cursor object in a new variable called results using the fetch all method。



![](img/c8e706fcbe2b8242d012a6856d0916c0_16.png)

The results are retrieved as a list of topples， one for each row。



![](img/c8e706fcbe2b8242d012a6856d0916c0_18.png)

Little lemon can view the order of each individual entry。



![](img/c8e706fcbe2b8242d012a6856d0916c0_20.png)

They just called the column names attribute on the cursor to return the names of the column in order。



![](img/c8e706fcbe2b8242d012a6856d0916c0_22.png)

At this stage of your database engineering journey。

 you should have experience of using joins to extract data from multiple tables。

 and you should now be familiar with extracting data from a Mysql database using joins and Python Well done。

