# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P35：34_数据库模式类型.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

When creating your databases， you need to be able to distinguish between different kinds of database schemas。

In other words， you need to answer the question of what kind of database best suits my project。

Over the next few minutes， youll explore some different types of database schemas。

 and by the end of this video you'll be able to explain the concept of a logical database schema and outline the concept of a physical database schema。



![](img/ed2b399e6e06f8827c30feb694278244_1.png)

Let's begin by exploring logical database schema。A logical database schema is how the data is organized in terms of tables。

In other words， it shows what tables should be in a database and explains how the attributes of different tables are linked together。



![](img/ed2b399e6e06f8827c30feb694278244_3.png)

Creating a logical database schema means illustrating relationships between components of your data。

This is also calledE relationship or E or modeling。



![](img/ed2b399e6e06f8827c30feb694278244_5.png)

It specifies what the relationships between entity types are。

Let's take the example of a simple ER model that shows the logical schema of an ordering application。

It demonstrates the relationship between an order， the shipment in which it will be shipped。

 and the courier assigned to it。

![](img/ed2b399e6e06f8827c30feb694278244_7.png)

The ID attribute in each table is the primary key of the respective entities。

It provides a unique identifier for each entry， row or record in the entities。In the order entity。

 to Shi ID and courier ID are called foreign keys， but in fact。

 they're also the primary keys of the shipment and courier entities respectively。

This creates a relation between these entities and the order table。

 which in turn has its own ID as its primary key。

![](img/ed2b399e6e06f8827c30feb694278244_9.png)

The other type of schema is physical schema。Physical schema is how data is stored on disk。

In other words， this involves creating the actual structure of your database using code。

In MySQL and other relational databases， developers use SQL to create the database， tables。

 and the other database objects。

![](img/ed2b399e6e06f8827c30feb694278244_11.png)

For example， you can create a physical schema for an online store database by writing SQL statements to create tables for customers。

 products， and transactions。However， physical schema creation could differ slightly between different database systems。



![](img/ed2b399e6e06f8827c30feb694278244_13.png)

Database schemas are vital when it comes to the creation of databases and they form the basis of your application。

 you should also be able to describe how a logical database schema refers to the organization of data and tables and that you use an ERR model to specify relationships between entities。

And you should also now know that you can control how data is physically stored on disk by creating a physical schema with SQL statements。

