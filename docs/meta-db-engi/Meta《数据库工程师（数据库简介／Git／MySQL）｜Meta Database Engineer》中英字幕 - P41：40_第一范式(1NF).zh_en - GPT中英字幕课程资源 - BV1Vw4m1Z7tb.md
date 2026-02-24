# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P41：40_第一范式(1NF).zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

As a database engineer， you'll very often come across columns in a table that are filled with duplicates of data and multiple values。

This can make it quite challenging to view， search， and sort your data。

But with the correct implementation of normalization。

 this challenge can be dealt with by the end of this video you'll be able to demonstrate how to design a database in first normal form。

Identify the atomomicity rule and how to enforce it and analyze effective ways to eliminate the repeating group of data problems in data sets。

As you might already know from previous videos in this lesson。

 the normalization process makes it easier and more efficient for engineers to perform basic database tasks。

It's an especially useful process for helping to fix the well known insert to lead and update anomalies。

However， in order to achieve database normalization。

 you first need to perform the three fundamental normalization forms。

The database normalization forms include first normal form or 1NF， second normal form or 2NF。

 and third normal form or 3NF。

![](img/2440b8cdbcf73acf74deccd2c9f9cab7_1.png)

This video focuses on designing a database to meet the first normal form or1F rules。

These rules enforce data atity and eliminate unnecessary repeating groups of data and database tables。



![](img/2440b8cdbcf73acf74deccd2c9f9cab7_3.png)

Data atdimity means that there must only be one single instance value of the coum attribute in any field of the table In other words。

 your table should only have one value per field。By eliminating repeating groups of data。

 you can avoid repeating data unnecessarily in the database。

Instances of repeated data can cause data redundancy and inconsistency。



![](img/2440b8cdbcf73acf74deccd2c9f9cab7_5.png)

To understand this better， let's explore an example。To demonstrate data atity。

 I've built an unnormalized table called Course Table within a college database。

It includes information about the college's computing courses。

 along with the names and contact details of the course tutors。

And the courseur ID column serves as the table's primary key。However。

 there are multiple values in each row of the contact number column。

Each row contains two contact details for each tutor， a cell phone number， and a Laline number。



![](img/2440b8cdbcf73acf74deccd2c9f9cab7_7.png)

This table isn't in 1 NF。It violates the atomity rule by including multiple values in a single field。

I can try and fix this by creating a new row for each number， this solves my data atity problem。



![](img/2440b8cdbcf73acf74deccd2c9f9cab7_9.png)

The table now has just one value in each field， but this solution has also created another problem。😊。

The primary key is no longer unique because multiple rows now have the same course ID。



![](img/2440b8cdbcf73acf74deccd2c9f9cab7_11.png)

Another way that I could solve the problem of atomicity while retaining the primary key is by creating two columns for contact numbers。



![](img/2440b8cdbcf73acf74deccd2c9f9cab7_13.png)

One column for cell phones and a second column for landline numbers。

But I still have the issue of unnecessary repeated groups of data。

Mary Evans is the assigned tutor for two of the courses。

 so her name appears twice in the table as do her contact details。

These instances of data will continue to reappear if she's assigned more courses to teach。

And it's likely that our details will appear in other tables within a database system。

This means I could have even more groups of repeated data。

This creates another problem if this tutor changes any of their details then I'll have to update their details in this table and all others in which it appears。

 and if I miss any of these tables， then I'll have inconsistency and invalid data within my database system。

😊，To solve this issue， I can redesign my table to adhere to 1NF or first normal form。First。

 I identified the repeating groups of data。In this case， it's the tutor's name and contact numbers。

Next， I identify the entities I'm dealing with which are course and tutor。



![](img/2440b8cdbcf73acf74deccd2c9f9cab7_15.png)

Then I split the course table so that I now have one table for each entity。

A course table that contains information about the courses。

And a tutor table that maintains the name and contact numbers of each tutor。

Now I need to assign a primary key to the choosetor table。So I select the tutor ID column。

I've solved the problem of data atomimity。But I also need to provide a link between the two tables。

I can connect the two tables by using a foreign key I just add the tutor ID column to the course table now both tables are linked。



![](img/2440b8cdbcf73acf74deccd2c9f9cab7_17.png)

I've now achieved data atity and eliminated unnecessary repeating groups of data。

You should now be familiar with 1NF and the rules that you should apply to avoid it。Good work。

