# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P23：22_模型.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

If you are building a dynamic application using a web framework。

 data storage using a database is essential。Recall that the presentation layer is the layer that the user interacts with。

 any data posted from the presentation layer needs to be persisted and also kept for retrieval for laser use。

For example， if the website requires user login， it will need to keep track of who users are and what data they are entitled to view。

 edit and create。The solution is to use a model， the object equivalent of a database table used in Django and acts as a single definitive source of information about your data In this video。

 you will further explore the model part of the MVT architectural pattern and learn how Django uses model classes and methods to perform crud operations。

If you are a developer on the back end of an application。

 working with databases can be achieved in one of two ways。

The first way is to work directly in the database to create the required tables。

 then in your application you would need to create custom queries written in the Strd query language or SQL to store and retrieve the data。

The second way is to use a framework。You've already learned that frameworks are designed to assist developers by providing them with a platform for rapid development。

 and one way developers can speed up their development is by using models to interact with the database。

A model is the single definitive source of information about your data。

 it contains the essential fields and behaviors of the data your story。Generally。

 each model maps to a single database table。Models are an integral part of the Jnangle framework。

Let's explore this structure in a little more detail now。

 each model is a Python class that subclasses django。db。models。model。

Each attribute of the model represents a database field。

This means that instead of having to write a custom query for adding and retrieving database records。

 you can use a model to do it instead， Django gives you an automatically generated database access API to access the database with Python code。

Essentially， you can think of a model as a Python object， and models help developers create， read。

 update， and delete objects commonly called theCd operations。

You will learn more about these crud operations in Djangle in just a few moments。

But before you do this， let's explore a scenario to create a table called user。

 starting with SQL syntax and then using Jnangle models。

You may recall that to create a table in a database using SQL。

 you would need to write a query using the Cate table syntax。When the code runs。

 a table called user will be created with three columns， ID， first name， and last name。

To do this using a model in Django， you define a class that will subclass the Django。db。models。mod。

You may notice that the ID or a primary key， is not specified in the class。

This is because Djanangle automatically adds it。But you can override it if needed。 At this point。

 it's important to know that you cannot create a database table by only defining a model class in Python。

To complete this process， you need to use something called migrations and you will learn more about how they work later。

Okay， so now you know about the concept of models in Django and that they can be used to replace SQL operations to access and manage data。

Let's explore how you can use models and their associated methods to perform CRd operations。

Jengo automatically provides all these methods out of the box， so let's begin with Create。😊。

You may recall that creating records in SQL requires you to use the insert statement， for example。

 to create a new user in the user table in Django， creating records requires you to create a new object from the class user and then persist it using the save function Next is read in SQL to retrieve information you need to write a SQL query using the select statement。

 For example， to retrieve a user from the user table whose ID is equal to one。In Django。

 you can use that gett method， which is bound to the user dot objects。Next is update。

Suppose you have a table of users with the user named John Jones， with the ID of one。

 you want to update the user's last name to Smith。In SQL。

 you use the update statement to update an existing record in a database。

To achieve the same result in djangle， you use the methods get and save。

The code works by checking if a user exists with the ID of one and then updates the user's last name to Smith。

Finally， let's explore deletelete。With SQL， the delete statement is required to delete records in the database。

For example， you can delete a user based on a value such as ID equals1。

To achieve the same result with Django， you use the delete method。

It's important to note that these are only some of the many methods Django provides when working with models。

 as an aspiring developer， it's a good idea to familiarize yourself with the ones mentioned in this video。



![](img/2557d5939d55c691c246617bac3bb2db_1.png)

In this video， you learned about the model part of the MVT architectural pattern and how Django uses classes and methods to perform Chde operations when working with database tables。



![](img/2557d5939d55c691c246617bac3bb2db_3.png)