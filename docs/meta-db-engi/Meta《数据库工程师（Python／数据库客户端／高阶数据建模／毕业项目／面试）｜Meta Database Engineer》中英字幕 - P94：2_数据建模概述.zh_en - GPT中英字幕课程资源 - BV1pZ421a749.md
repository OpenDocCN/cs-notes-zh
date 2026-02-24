# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P94：2_数据建模概述.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

When developing a database system， you need to make sure that it operates efficiently and that you can extract information from it quickly the best way to create such a system is to first design a data model with the data model。

 you can plan how data is stored and accessed within your database before you create the database system。

In this video， you'll explore the concept of data modeling and review different levels of data models。

 The jewelry store meant data and gallo or MG are in the process of designing and building a database system to store data on customers。

 products and orders。 but their current design is very inefficient。 However。

 if MG first focuses on creating a suitable database model。

 then they can design a more simplified and logical database system。

 Exp the basics of database modeling， then see if you can assist MG。

 Let's begin with the term data modeling。 A data model provides a visual representation of data elements and shows how they relate to one another。

 In other words， it demonstrates how your database system is structured。

 This structure helps you to understand how data is stored， accessed。

 updated and queried within the database， and it also ensures a consistent structure in high quality。

😊，Data modeling is used to develop all kinds of databases， particularly entity relational databases。

 These databases are planned with the use of an entity relationship diagram。

There are three different levels of data modeling， conceptual data models。

 logical data models and physical data models。Let's take a few moments to explore these different types you might already be familiar with conceptual data models from previous courses。

 a conceptual data model consists of high abstract level of data elements called entities the relationship between the data elements or entities links related records of data within your database system the purpose of a conceptual model is to present a high level overview of the database system through a visual representation of the entities it contains and the relationship to one another。

M&G can make use of a conceptual data model to create their database system。

They can present their customers products and orders as entities。

 then document how these entities are related。 The conceptual model provides the basis for the logical data model again。

 you should have a basic familiarity with examples of a logical data model from previous courses The logical data model builds on the conceptual model by providing a more detailed overview of the entities and their respective relationships。

 It identifies the attributes of each entity， defines the primary keys and specifies the foreign keys MG can build on their conceptual data model by using it to create a logical data model their logical data model must include all attributes required for each entity like a list of the attributes each entity contains。

😊，It then needs to define which of these columns serve as the primary key for each table。

 for example， the client ID column is the primary key for the clients table。

And M&G's logical data model also specifies the foreign keys they're using to create relationships between the tables。

In the current model， the client table is connected to the orders table through the clientient ID foreign key a physical data model is used to create the internal SQL schema of the database。

 which is implemented in the database management system。

The physical data model must outline features like the data types。

 constraints and attributes for example， M andG need to define a specific data type for each attribute like barchar for the full name attribute in the client's table or integer for the contact number attribute They also need to apply relevant constraints They can impose a constraint of not null for each column in the client's table to make sure that each one contains data There are also a range of tools available to generate and execute the internal schema of a physical data model you'll cover these tools in later lessons you should now be familiar with the basics of data modeling and the importance of the role that it plays in the development of a database system You should also be able to differentiate between different levels of data models and explain how each one contributes to the creation of a database system Great work。

😊。

![](img/50f1da95e8474faf5f81d4dc784bb694_1.png)

![](img/50f1da95e8474faf5f81d4dc784bb694_2.png)