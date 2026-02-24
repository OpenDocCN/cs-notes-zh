# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P40：39_什么是数据库规范化.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

At this stage， you might be familiar with the process for creating tables within a database。

But there are several issues that you're likely to encounter when working with tables such as unnecessary data duplication。

 issues with updating data， and the effort required to query data。Fortunately。

 these issues can be resolved with the use of database normalization。By the end of this video。

 youll be able to explain what database normalization is。

 and you'll also be able to demonstrate an understanding of insert， update and deletion anomalies。

 and be able to list some of the issues associated with them。

Normalization is an important process used in database systems。



![](img/8693bccc06c2c16ebee40fae3caac935_1.png)

It structures tables in a way that minimizes challenges by reducing data duplication。

 avoiding data modification implications， and helping to simplify data queries from the database。



![](img/8693bccc06c2c16ebee40fae3caac935_3.png)

To gain a better understanding of normalization and the challenges it addresses。

 let's explore an example of a table that hasn't been normalized。In this example。

 I'll use a college enrollment table。😊，The table serves multiple purposes by providing a list of the college students。

 courses and departments。And the outline of relationships or associations between students。

 courses and departments。A name and contact details for the head of each department。



![](img/8693bccc06c2c16ebee40fae3caac935_5.png)

Creating tables that serve multiple purposes causes serious challenges and problems for database systems。

The most common of these challenges include insert anomaly， update anomaly， and deletion anomaly。



![](img/8693bccc06c2c16ebee40fae3caac935_7.png)

Let's begin with an overview of insert anomaly In anomaly occurs when new data is inserted into a table which then requires the insertion of additional data。



![](img/8693bccc06c2c16ebee40fae3caac935_9.png)

I'll use the college enrollment table to demonstrate an example。In the College enrollment table。

 the student ID column serves as the primary key。Each field in a primary key column must contain data before new records can be added to any other column in the table。

For example， I can enter a new course name in the table。

 but I can't add any new records until I enroll in new students。

And I can't enroll new students without assigning each student an ID。



![](img/8693bccc06c2c16ebee40fae3caac935_11.png)

The ID column can contain empty fields。So I can't insert a new course unless I insert new student data。

Ive encountered the insert anomaly problem。An update anomaly occurs when you attempt to update a record in a table column only to discover that this results in further updates across the table。



![](img/8693bccc06c2c16ebee40fae3caac935_13.png)

Let's return to the college enrollment table once again to understand how an updated anomaly occurs。

In the enrollment table， the course and department information is repeated or duplicated for each student on that course。

 This duplication increases database storage and makes it more difficult to maintain data changes。

I'll demonstrate this with a scenario in which Dr。 Jones， the Director of the Computing department。

 leaves his post and replaced with another director。I now need to update all instances of Dr。

 Jones in the table with the new director's name。And I also need to update the records of every student enrolled in the department。

This poses a major challenge because if I miss any students。

 then the table will contain inaccurate or inconsistent information。



![](img/8693bccc06c2c16ebee40fae3caac935_15.png)

This is a prime example of the update anomaly problem。

Updating data in one column requires updates in multiple others。Next。

 let's review the final challenge， deletion anomaly。

A deletion anomaly is when the deletion of a record of data causes the deletion of more than one set of data required in the database；

 for example Rose， the student assigned the ID of four has decided to leave her course。



![](img/8693bccc06c2c16ebee40fae3caac935_17.png)

So I need to delete her data。

![](img/8693bccc06c2c16ebee40fae3caac935_19.png)

But deleting Rose's data results in the loss of the records for the design department。

 as theyre dependent on Roses on her ID。

![](img/8693bccc06c2c16ebee40fae3caac935_21.png)

This is an example of the deletion anomaly problem。

Removing one instance of a record of data causes the deletion of other records。

So how can you solve these problems？As you learned earlier。

 the answer lies in database normalization。Normalization optimizes the database design by creating a single purpose for each table。



![](img/8693bccc06c2c16ebee40fae3caac935_23.png)

To normalize the college enrollment table， I need to redesign it。As you discovered earlier。

 the table's current design serves three different purposes。

So the solution is to split the table on three， essentially creating a single table for each purpose。



![](img/8693bccc06c2c16ebee40fae3caac935_25.png)

This means that I now have a student table with information on each student。

 a course table that contains the records for each course and a department table with information for each department。

😊。

![](img/8693bccc06c2c16ebee40fae3caac935_27.png)

![](img/8693bccc06c2c16ebee40fae3caac935_28.png)

This separation of information helps to fix the anomaly challenges。

 it also makes it easier to write SQL queries in order to search for， sort and analyze data。

You should now be able to explain what database normalization is。

 and you should also be able to demonstrate an understanding of anomalies and challenges。Well done。

