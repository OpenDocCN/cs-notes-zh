# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P43：42_第三范式(3NF).zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

When working with tables in the database， you may often encounter tables that contain repetitive data。

 perhaps two columns contain values that are very similar。

 so you might split the table in two to simplify the data。When building relational databases。

 you can solve similar issues of repetitive data using what's known as third normal form or 3NF。

By the end of this video， you'll be able to understand how to design a database in third normal form and explain the concept of transitive dependency before you begin。

 make sure that you've watched the videos in the first and second normal form。



![](img/705e00e49772c94dbbabde3f22aface3_1.png)

A database must be in first and second normal form before it can be in third normal form。

In addition to these rules， databases can contain any instances of transitive dependency。

In the context of third normal form， transitive dependency means that a non key attribute cannot be functionally dependent on another non key attribute。

In other words， non key attributes cannot depend upon one another。

A key attribute in a database is an attribute that helps to uniquely identify a row of data in a table。



![](img/705e00e49772c94dbbabde3f22aface3_3.png)

To demonstrate this concept， let's take the example of a basic table with three columns， A， B， and C。

The concept of transitive dependency means that the value of a determines the value of B。Likewise。

 the value of B determines the value of C。The relation between these table columns is represented by A。

 B， and C。This means that A determines C through B。

This is the type of relation that database engineers call transitive dependency。



![](img/705e00e49772c94dbbabde3f22aface3_5.png)

Let's see how this works using a more complex example。

I have a table of bestsel books within Europe from the database of an online bookstore。

 the table organizes the books according to five attributes， bulk ID and title， author name。

 author language and country。In this table， ID is the only key or primary key that exists in the table。

All other attributes are non key attributes。But to determine what these non key attributes are。

 I must use the ID of the top setting books。This means if I want to find any specific information about any attribute。

 I need to use the ID attribute value to find a targeted attribute value for example。

If I use the ID of three， then I can locate the author Cormer Oduuyre， the language Irish。

 the country Ireland and so on； however it's also possible to determine the country based on the language or to determine the language based on the country。

And both country and language are non key attributes。For example， in the context of Europe。

 it's always possible to determine the country is France， if the language is French and vice versa。😊。

This means that I have a transitive dependency in this relation。

A non key attribute depends on another non key attribute。



![](img/705e00e49772c94dbbabde3f22aface3_7.png)

This dependency relation can be presented as follows。

Language determines country and country determines language。



![](img/705e00e49772c94dbbabde3f22aface3_9.png)

The rest of the attributes are fine， as they only depend on the ID primary key。So you can't say。

 for instance， that author name determines book title， or that author name determines language。

For example， the author Michelle Laurri has written two books in two different languages。

 French and Spanish。

![](img/705e00e49772c94dbbabde3f22aface3_11.png)

As I've just pointed out， the only transitive dependency that exists in this example is between language and country。

 so how do I solve this transitive dependency within my table and remove any repetition of data？😊。



![](img/705e00e49772c94dbbabde3f22aface3_13.png)

I can split the table into two tables while joining them to conform with3 NF rules。

 so I keep the top books table while splitting off the country and language columns into a new table called Country。

While I also leave the country column inside the top books table as a foreign key that connects the two tables。

 the country table now holds just four records with no repetition of data。

And there's no need for a language column within a top box table。

Stateating the country is enough to determine the language and most importantly。

 all non key attributes are determined only by the primary key in each table；

 this means that my table now meets the requirements of 3 andF。



![](img/705e00e49772c94dbbabde3f22aface3_15.png)

You should now know how to design a database in third normal form。

 and you should also be able to explain the concept of transitive dependency。Well done。

