# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P25：24_迁移.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

In the world of web application development， application requirements constantly change。

 and it's a developer's job to implement these changes。For example。

 a common task is to alter the data model of the application。

 and to do this in Django you use something called migrations。

In this video you will learn about migrations in Django and how developers use them to make changes to the models representing the database schema recall that Django is designed to work with a relational database management system like PostgresSQL。

My sQL or sQL light。And in a relational database， data is organized in tables。



![](img/cf14810ffbb89dca1ac870db7fa1e14d_1.png)

By now， you know that you can use models to represent data tables stored in the database。

 recall that when using models， Djanangle provides many methods that allow you to add。

 update and delete data right from the code without having to write SQL。

 This is made possible by using something called an object relational Naper R ORM。



![](img/cf14810ffbb89dca1ac870db7fa1e14d_3.png)

You will learn more about this laser。For now， just know that it maps the relational database to objects represented as junangle models。

The models define the database fields which correspond to the columns in their associated database tables。



![](img/cf14810ffbb89dca1ac870db7fa1e14d_5.png)

For example， if you have a model called user， you know it will represent a table called user。

 and each attribute of the model has a column representation in the database。



![](img/cf14810ffbb89dca1ac870db7fa1e14d_7.png)

![](img/cf14810ffbb89dca1ac870db7fa1e14d_8.png)

So in the Python code， if the user class has an attribute of first name。

 the table will have a column of first name。

![](img/cf14810ffbb89dca1ac870db7fa1e14d_10.png)

It's common that during the lifecycle of the development of the application。

 changes to the structure of the database or schema will be required。For example。

 the initial model may need to be extended with additional attributes。

 This means adding a new attribute which will add a new column from the perspective of the database。



![](img/cf14810ffbb89dca1ac870db7fa1e14d_12.png)

Or suppose you need to perform a different operation。

 like changing a column name or even deleting a model for these operations to work。

 Python uses something called database migrations。

![](img/cf14810ffbb89dca1ac870db7fa1e14d_14.png)

Migrations are how Dngle records changes made to models and implements these changes to the database schema。



![](img/cf14810ffbb89dca1ac870db7fa1e14d_16.png)

Migrationations are tied into Jnangle models and stored as migration files in a migrations folder inside each app。



![](img/cf14810ffbb89dca1ac870db7fa1e14d_18.png)

You will learn more about migration storage later for now。

 let's explore how migrations work and return to the example of the users's table。

Suppose you wanted to add a new column called City to the user table。Without an ORM。

 like the one Jngle provides， a developer must log into the database and run a SQL Al statement。

You may recall that you can use the alter statements to alter a specific table to add a column of whatever type is required when the statement runs the user table updates with another column called City。



![](img/cf14810ffbb89dca1ac870db7fa1e14d_20.png)

In Django， the user table is created using a model。

 which you may recall is a class based representation of the user table in the database。

So instead of writing the SQL query， you only need to add the new attributes to the model。

 then run the migration scripts to implement the changes。Once the migration scripts run。

 the changes are applied。

![](img/cf14810ffbb89dca1ac870db7fa1e14d_22.png)

Let's explore the process of running the migration script a little further now。

 Dngo provides a list of CLI commands that allows you to apply the migrations First you must create a migration script and then apply the migrations。



![](img/cf14810ffbb89dca1ac870db7fa1e14d_24.png)

The migration script is a set of instructions on what models to create against the database。

You apply the change to the model， run the migration file， and Django will take care of the rest。

You do not need to write any SQL as the application handles everything。Later in this lesson。

 you will learn more about running a script and applying it to the database。For now。

 let's focus on some of the reasons developers use migrations instead of SQL。

You may wonder why you need migrations when it appears straightforward to just run a SQL query。

 like the earlier example， to update a table。Migrations do more than just implement SQL commands。

They can help with syncing issues， version control and database maintenance。

 it's good to think of migrations as a version control system for your database schema。



![](img/cf14810ffbb89dca1ac870db7fa1e14d_26.png)

Let's explore some of those benefits in more detail now， beginning with sinking issues。

With migrations， you have less possibility of syncing issues between what the model has and what the database contains。



![](img/cf14810ffbb89dca1ac870db7fa1e14d_28.png)

When working in a team， each developer usually has their own local copy of the database so they can code and test against it migrationration scripts are kept in the code repository。



![](img/cf14810ffbb89dca1ac870db7fa1e14d_30.png)

So when a developer on the team makes changes， they run the migration script to update their local copy of database to the latest version next is version control。

 All the changes are kept in version control which provides an entire history of changes across the application developers can also use this to determine what changes have been added and by whom。



![](img/cf14810ffbb89dca1ac870db7fa1e14d_32.png)

Generally， in application development， the more you can track changes that occur in the app。

 the fewer problems you will encounter。The alternative is running scripts in the database directly。

 which is usually more problematic as it is outside version control。😊。



![](img/cf14810ffbb89dca1ac870db7fa1e14d_34.png)

The last benefit of using migrations is the ease of maintenance。

 along with helping syncing issues and version control。

 maintaining all the database changes from the codebase makes it easier for the development team。

They don't have to worry about creating SQL queries directly against the database。

 or where to store these files so other developers can run them。



![](img/cf14810ffbb89dca1ac870db7fa1e14d_36.png)

In this video， you learned about migrations in Djangle and how developers use them to make changes to the models representing the database schema。

