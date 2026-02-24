# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P95：3_数据模型类型.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

When creating a database system， you first need to design a data model。

 but there are many kinds of data models that you can choose from。

 so how can you determine which one is best for your database system？In this video。

 you'll learn how to choose between different types of database models and find out how they can be used to create databases。

 Mangeta and Gallo or M&G need to build their database system so that it meets the needs of their business。

 so they need to choose a data model that fulfills their data requirements。

Explore the different types of data models， including their advantages and disadvantages。

 and see if you can help M&G figure out which model is best for their business。

There are many kinds of models that can be used to build a database system In this video。

 you'll explore the following data models， the relational data model。

 the entity relationship model and the hierarchical data model。

 You'll also review the object oriented model and the dimensional data model。

 Let's begin with a look at the relational data model。

 You might already be familiar with the relational data model from previous courses。

 It's a popular and widely used database model。 It represents the database as a collection of relations。

 Each relation is presented as a table that stores information in the form of rows and columns。

 A key advantage of this model is that it's much simpler to use than other models。

 You can quickly identify and access data。But the relationships between the data in this model can become more difficult to navigate with complex relational database systems。

 and you might also need to structure and organize the data differently when performing data analytics Next is the entity relationship model This model is similar to the relational data model The key difference is that you can present each table as a separate entity by assigning each one its own set of attributes the model also covers many different types of relationships between entities such as one to one。

 one to many and many to many relationships。For example。

 M&G can use an entity relationship model to visualize the relationship between their clients and orders tables。

The two entities are connected through the client ID column using a one to many relationship In other words。

 one or more orders belong to a specific client There's also the hierarchical data model The hierarchical data model organizes data in a tree like or parent child structure Each record of data has a parent node and it can also have its own child node The main disadvantage is that it can only be used to record one to many relationships between nodes。

Each child node can only have one parent node。M&G can use this model to depict the relationship between their orders and clients entities。

Clients are connected to their root node and each order is connected to the related client。

 while each client can be connected to many orders。

M and G can continue to add nodes as required Another option for database developers is the object oriented model This model is based on the object oriented concept。

 This is where each object is translated to a class that defines the object's characteristics and behavior。

A key advantage of this model is that you can define different types of associations between objects like aggregations。

 compositions and inheritance This makes object oriented databases suitable for complicated projects that require an object oriented approach。

This model also relies heavily on the inheritance feature。

 This is where one class inherits its attributes from another。 You can create a parent or superclass。

 also called a base to hold the common attributes。 Each child class that follows inherits the attributes of the parent class。

 However， if you do make use of this model， then you need a good understanding of object oriented principles and related programming skills。

M andG can make use of an object oriented model to retain attributes between classes they can create a base or parent class called person entity that contains attributes and operations the staff and client classes then inherit these attributes and operations from the person entity class so each staff member and client are a person。

Finally， there's the dimensional data model。 This model is based on two key concepts。

 dimensions and facts facts are measurements obtained from a process。 For example。

 sales facts obtained from MG's business data dimensionmenions define the context of these measurements like a specific sales period。

 So sales facts measure how many quantities of a particular product MG sold in each week。

The key advantage of this model is that it optimizes the database for faster data retrieval and restructures data for more efficient data analytics。

 You'll explore the dimensional data model in more detail later in this course you should now be familiar with the different types of data models that can be used to build a database system。

 and some of their key advantages and disadvantages。

 you're making great progress on your database modeling journey。



![](img/281af6969a8e0188b0ae34b7d0332b37_1.png)

![](img/281af6969a8e0188b0ae34b7d0332b37_2.png)