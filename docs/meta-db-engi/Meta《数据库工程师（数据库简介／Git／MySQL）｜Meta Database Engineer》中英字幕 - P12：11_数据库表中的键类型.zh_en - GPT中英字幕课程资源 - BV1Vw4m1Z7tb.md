# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P12：11_数据库表中的键类型.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

At this stage of the course， you're probably familiar with the relational database model。

 but to fully understand how a relational database model works。

 you first need to understand how tables within a database are related。Essentially。

 relationships are established between tables with the use of keys。By the end of this video。

 you'll be able to identify the main keys used in tables in a relational database and explain the relationship between keys in a table。



![](img/fd6d45fa4e03e6fe151d5ce86a1bce43_1.png)

The relational database model is based on two main concepts。

Entities which are defined as tables and relations that connect to related tables。

To realize how this model works， you need to understand the different key attributes that exist in the relational database。

To demonstrate， let's use the example of a sports competition that uses three tables to keep track of the league。

 the league table， the teamss table， and the points table。😊。



![](img/fd6d45fa4e03e6fe151d5ce86a1bce43_3.png)

Each table has relevant columns where each column represents an attribute of the table entity。

The league table keeps track of each team's position in the league， their name。

 and the state they represent。The team's table tracks， the team name。

 the team captain and the team coach， and the points table records the team's position in the league。

 the team's name， and how many points the team has this season。

Notice that the Teams table includes team name， which also belongs to the league table。

These attributes could be of a simple attribute type that can hold a single value。



![](img/fd6d45fa4e03e6fe151d5ce86a1bce43_5.png)

For example， in a table of staff members in a college。

 each staff name attribute has a single value in each row。

Or they could also have a multi value attribute that can have multiple values。😊。

Like a list of subjects taught。However， multi value attributes should be avoided in relational database design。



![](img/fd6d45fa4e03e6fe151d5ce86a1bce43_7.png)

You'll learn more about this concept later in the course。

Let's use the example of the staff table to explore some examples of attribute keys。

Let's begin with the key attributes。

![](img/fd6d45fa4e03e6fe151d5ce86a1bce43_9.png)

This is a value used to uniquely identify an individual record of data in a table。😊，For example。

 in the staff table， the key attribute is staff ID。

This attribute has unique value in each row of the table。

 so it's the perfect way to uniquely identify each record of data。😊，In a relational database。

 there are a range of different types of key attributes。There's also the candidate key attribute。

This is any attribute that contains a unique value in each row of the table。

In the case of the staff table， both the staff ID and contact numbers are examples of candidate keys。

Each has a new unique value in each row。The other columns can contain repeated information。

 so they're designated as non key attributes。A composite key is a key that is composed of two or more attributes to form a unique value in each new row。

In the staff table， an example of a composite key is a combination of the staff name and staff title。

 assuming that there isnt another instance of the same combination elsewhere in the table。😊。

A composite key is usually considered when a single attribute key can't be identified。

A relational database must also contain a primary key， which you should already be familiar with。

In the staff table， the staff ID is the primary key。An alternate key also known as the secondary key。

 is a candidate key that was not selected to be the primary key。Just like a primary key。

 it's a column that contains a unique value in each field for the staff table。

 the contact number is the secondary key on each row。And finally， there's the foreign key。

The foreign key is an attribute in a table that references a unique key in another table。😊。

Typically a foreign key references the primary key of another table， for example。

 the staff ID might also be a firing key in one or more tables within a college database。

The relationship between primary and foreign keys will be discussed in more detail at a later point in this course。



![](img/fd6d45fa4e03e6fe151d5ce86a1bce43_11.png)

You're now familiar with the different types of keys in a relational database。

