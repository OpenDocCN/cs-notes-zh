# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P27：26_变更历史记录.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

Migrations play a significant role in helping carve out the data tables and the interactions from the web application to the database By now。

 you know that developers can use a model to query data directly from code instead of writing SQL commands。

An advantage of this approach is that Django directly provides a history of changes to the codebase in this video you will learn about their history of changes of Django migrations and how developers use them for version control of the model codebase。

Every model created in the project provides a full history of how it was created， when it was added。

 and any changes that have occurred。

![](img/bb5568edfdb5d88e577128d36f9636b5_1.png)

Web application development requirements tend to change quite a bitss in small increments。



![](img/bb5568edfdb5d88e577128d36f9636b5_3.png)

For example， adding an extra attribute to a model or changing an attribute name。Additionally。

 there are occasions when multiple users use more than one database and migrations ensure schema changes are applied and updated on each database。

In Django， a developer must create the change directly in the model。

 then apply the migration by using the migration scripts。

Another important advantage of using migrations is to avoid repetition once you create some model。

 writing SQL queries to create corresponding databases for it is repetitive。

Migrations generated from the models help prevent duplication of efforts；

 this is in line with one of the core principles of Django， don't repeat yourself。

So you may be wondering how Djanle keeps a history of all changes made in the database。

It all begins with the file structure， migration files are stored in a migrations folder。

If you expand the migrations folder， notice that it automatically updates the file system after the migration has run。



![](img/bb5568edfdb5d88e577128d36f9636b5_5.png)

You can explore the details of the migrations using the Show Mirations Command。



![](img/bb5568edfdb5d88e577128d36f9636b5_7.png)

In this example， the migrations are listed under a given model with an auto incrementing prefix such as 0001。

Jianangle automatically generates the file names in line with the actions performed in the given migrations or the timestamp。

The X symbol represents the status of applying migrations after making them。

This is after the command make migrations， but before the command migrate。After applying migrations。

 Django does not apply a new migration to the same database again， unless it detects changes。



![](img/bb5568edfdb5d88e577128d36f9636b5_9.png)

Behind the scenes， Django creates a new table calledjangle migrations with reference to the migration files。

Let's explore this table in a little more detail now。

 a new row is inserted after each migration tracking the changes。

 apps and the timestamp of the migration。The first column is the ID。

 and this is auto incremented based on the position in the table。

 the second column is the app that the migration is associated to。Recall that in Django。

 you can have multiple applications inside a project。

The third column is the name and refers to the file name of the migration。

The final column is the timestamp of when the migration was applied。



![](img/bb5568edfdb5d88e577128d36f9636b5_11.png)

Every time a migration script is run， this table is updated with the latest changes。

 this also means that it's checked prior to the migration script running。

This is done so that it knows which scripts have been run and which ones need to be applied。



![](img/bb5568edfdb5d88e577128d36f9636b5_13.png)

Migrationations can also be applied to a specific app by placing the app name after the make migrations command Okay。

 so now you know about the migration file structure， let's explore the contents of a migration file。



![](img/bb5568edfdb5d88e577128d36f9636b5_15.png)

Migration files are basically Python code。Inside the migrations class。

 it will typically contain two important sequences or list items。

 such as dependencies and operations。Depenencies refer to the previous migration that must be applied before this。

 and operations refer to actions performed in the given migration。

Some of the commonly used operations are Create model， which creates a model and drops a table。

Delete model， which deletes a model and drops a table。

Add field which adds a database column and field definition creations are additions， Al field。

 which creates a database column and field definition changes。And add index。

 which creates a database index。So for example， an operation such as Delete model will generate a corresponding SQL query。

 such as Dele T customers。

![](img/bb5568edfdb5d88e577128d36f9636b5_17.png)

In this video you learned about the history of changes and how Django applies it to migrations。

 you also explored how developers can use migration history for version control of the model code base。

