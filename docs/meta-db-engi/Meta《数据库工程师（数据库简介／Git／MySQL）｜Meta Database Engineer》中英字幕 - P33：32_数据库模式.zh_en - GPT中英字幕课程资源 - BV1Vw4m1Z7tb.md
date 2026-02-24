# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P33：32_数据库模式.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Before developing a database or a software application。

 you first need to plan how you'll organize your data。This plan is referred to as a schema。

It's essentially a blueprint of what your data looks like。In this video。

 you'll learn how to explain the concept of a database schema。

 identify the different meanings of the term schema across different database systems。

 and outline the advantages of a database schema。

![](img/705d0ddbc265530b31890cae5853fe71_1.png)

Let's begin focusing on what developers mean when they use the term schema。

The general meaning of a schema is that it's an organization or grouping of information and the relationships among them。

In the context of a MySQL database， a schema means a collection of data structures or an abstract design of how data is stored in a database essentially schema and database are interchangeable terms within MySQL。

A scheme is how data is organized in the database and how it's related to other data。



![](img/705d0ddbc265530b31890cae5853fe71_3.png)

But schema is defined in different ways across different database systems。In a SQL server。

 a database schema is a collection of different components like tables， fields， data types and keys。

In PostgresSQL， a database schema is a name space with name database objects like views， indexes。

 and functions。An Oracle schema system assigns a single schema to each user。



![](img/705d0ddbc265530b31890cae5853fe71_5.png)

Argo even names each schema after its respective user。

But no matter which type of database you encounter。

 the two most important concepts you need to understand when working with schemas remain the same organization of data in the form of tables and the relationships between the tables。



![](img/705d0ddbc265530b31890cae5853fe71_7.png)

Let's now cover the components of a database。A SQL server schema is comprised of what are known as schema objects。

Many of these objects will probably already be familiar to you from your study of databases。

They include tables， columns， relationships， data types and keys。

 an example of a SQL database schema is a music database with data and artists。

 albums and genres all stored in separate tables， however these tables can still be related to one another through various keys。



![](img/705d0ddbc265530b31890cae5853fe71_9.png)

In other words， the data within this database is organized in separate tables or entities。



![](img/705d0ddbc265530b31890cae5853fe71_11.png)

Yet the tables are also related to one anotherEssential a database schema is comprised of all of the important data and the relationships。

 the unique keys for all entries and databases and a name and data type for each column in a table so now that you're familiar with what a database is。

 let's move on and explore the advantages of a database schema。



![](img/705d0ddbc265530b31890cae5853fe71_13.png)

Schemas provide logical groupings for database objects。



![](img/705d0ddbc265530b31890cae5853fe71_15.png)

They also make it easier to access and manipulate these database objects than other available methods。

Schemas also provide greater database security。You can grant permission to separate and protect database objects based on user access rights。

 and finally， it's possible to transfer ownership of schemas and their objects between users and other schemas。



![](img/705d0ddbc265530b31890cae5853fe71_17.png)

![](img/705d0ddbc265530b31890cae5853fe71_18.png)

In this video， you've learned that a database schema is a structure that represents the storage of data in a database。

 you also now understand how the meaning of schema changes across different database systems。Lastly。

 you explore the advantages of a database schema。