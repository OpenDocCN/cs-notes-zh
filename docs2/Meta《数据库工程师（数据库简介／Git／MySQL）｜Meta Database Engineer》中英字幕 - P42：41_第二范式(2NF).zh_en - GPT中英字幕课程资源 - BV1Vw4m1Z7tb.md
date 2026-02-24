# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P42：41_第二范式(2NF).zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

As a database engineer， you'll very often come across columns in a table that are filled with duplicates of data and multiple values。

This can make it quite challenging to view， search， and sort your data。

But with the correct implementation of the normalization， this challenge can be dealt with。

By the end of this video， you'll be able to explain how to design a database in a second normal form。

 outline the functional dependency concept， and define the partial dependency concept。

Before you begin， make sure that you've watched the video in first normal form or 1NF。

Database normalization is a progressive process， so you must be familiar with 1NF before you can implement 2 NF。

So why do database developers require database normalization？If you're going to store content。

 you should aim to have the best possible database。



![](img/cc084f0aa792a64d1b746cf2c936f062_1.png)

Best means that it is a proper structure that reduces duplication and ultimately DLAs for accurate data analysis and data retrieval。



![](img/cc084f0aa792a64d1b746cf2c936f062_3.png)

To get the best results， engineers build tables in a way that optimizes the database structure。

This video focuses on how to design tables in a relational database to meet the second normal form criteria。

But before you can learn how to do this， you need to understand what is meant by the terms functional and partial dependency。

Functional dependency refers to the relationship between two attributes in a table。

The unique value of a column in a relation determines the value of another column。



![](img/cc084f0aa792a64d1b746cf2c936f062_5.png)

To demonstrate this concept， let's take the example of a table known as R。

This table contains two columns called X and Y respectively。

X is a column with a set of unique values， which are not replicated elsewhere in the table。

 a primary key for example。Why is aalum without a set of unique values， like a non primary key？

R is the table or relation in which the coum's X and Y exist。Y。

 as a non primary key with duplicated values is dependent on x；

 This is because x is the table's primary key， as it only contains unique values。



![](img/cc084f0aa792a64d1b746cf2c936f062_7.png)

Don't worry if you don't quite understand this concept yet。

I'm going to demonstrate functional dependency in more detail。

Let's take the example of a table called Student that holds key information on students in the college。

The table contains three columns， a student ID column， a name column， and a date of birth column。

I need to use this table to find the date of birth for a specific student。

I can't use the name column because it has duplicated values。There are two students named Tony。

If I query this column， I'll just receive both instances of Tony。

 and I can't use the date of birth column either， because there are two students who share the same date of birth。

But I can complete this task by using the student ID column。All values in this column are unique。

 so it' designated as a table's primary key。And the values of this primary key column determine the information of the other columns。

This means that each column in the table is functionally dependent on the student ID column。



![](img/cc084f0aa792a64d1b746cf2c936f062_9.png)

Is the only co that can be used to return specific data。

Now that you've explored the concept of functional dependency， let's look at partial dependency。



![](img/cc084f0aa792a64d1b746cf2c936f062_11.png)

Pial dependency refers to tables with a composite primary key。

This is a key that consists of a combination of two or more columns。



![](img/cc084f0aa792a64d1b746cf2c936f062_13.png)

To demonstrate， let's take the example of a table that shows the vaccination status of patients in a hospital database。



![](img/cc084f0aa792a64d1b746cf2c936f062_15.png)

The table shows the vaccination status of two patients， David and Kate。

It also displays the patient ID， vaccine ID， and vaccine name。

There's no one single column with unique values in each row。

 so there's no single column that can be used as a primary key。

So it's best to combine both the patient ID and vaccine ID columns as a composite primary key to create a unique value in each record。

The vaccination table must meet the second normal form or 2NF。So all non key attributes。

 the vaccine name， patient name and status， must depend on the entire primary key value。

 which are patient ID and vaccine ID。It can't depend on just part of the value。

 otherwise this creates partial dependency。Let's apply this rule to find out if it's true for every non key co。

 so how do I check that the patient with the idea of 50 has taken vaccine 1？

I checked the value of both the patient ID and vaccine ID keys。

The combined value is the only way to return the vaccination status value of a specific patient。

 this means that there's a functional dependency between a status value and the primary key value。

But if I just want to find out the vaccine name， then I don't need both combined values。

 the only information I need to return the vaccine name is a vaccine ID。As you learned earlier。

 this is called partial dependency。This should be avoided in most instances as it violates a2NF rule。

 Similarlyly， if I want to identify the patient's name， I don't need both combined values。

 I can just use the patient ID to return the patient's name。Next。

 let's look at how you upgrade this table to 2NF。First。

 I need to make all non key columns dependent on all components of the primary key。

So I identify the entities included in the vaccination table。In this instance。

 there are three entities， vaccination status， as represented by the status column vaccine。

 which is the vaccine ID and vaccine name columns， and patient represented by the patient name and patient ID columns。

I then break up the table into three separate tables as follows， patient table。

 vaccine table and vaccination status。

![](img/cc084f0aa792a64d1b746cf2c936f062_17.png)

Now in each of these new tables， all non primary key attributes depend only in the primary key value。



![](img/cc084f0aa792a64d1b746cf2c936f062_19.png)

I've eliminated all unnecessary replication of the vaccine and patient names within the vaccination table。

The three tables are now in the second normal form or 2NF。



![](img/cc084f0aa792a64d1b746cf2c936f062_21.png)

You should now be familiar with the 2NF rule and how to upgrade a table to 2NF。Good work。

