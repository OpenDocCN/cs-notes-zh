# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P39：38_查找实体.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

When building a database， there's often a lot of different tables that you'd need to consider including。

But how do you determine what to include and what to exclude？

The answer is to identify the entities you're interested in maintaining data on。In this video。

 you'll learn how to explain the meaning of entities in a relational database。

 differentiate between attribute types， and be able to identify entities and attributes。



![](img/fcca964ba76ffee55daa81cfe01076f6_1.png)

So let's begin by exploring what an entity is。An entity can be described as an object that as properties which define its characteristics。

An entity can be anything that represents a single object in a database， such as a place or a person。



![](img/fcca964ba76ffee55daa81cfe01076f6_3.png)

In a relational database system， each interesting object in a project could be considered an entity。

 For example， a customer or individual。And an entity in a table is comprised of rows and columns created in database management systems such as MySQL。

Let's explore this concept in more depth using the example of a table that holds delivery records for the database of an e-commerce store。

😊，The table name represents the entity name， deliveries。

 and each column represents the entity related attributes。

And the system holds customer or entity relevant attributes such as ID， name。

 and delivery status details。These attributes hold relevant data about the table entity。

 so each instance of the customer entity in this ecommerce system contains a record of data about each customer。



![](img/fcca964ba76ffee55daa81cfe01076f6_5.png)

But there are also different types of attributes in a relational database system。

 these include simple attributes， composite attributes， and single valued attributes。

And there are also multi valued attributes， derived attributes， and key attributes。



![](img/fcca964ba76ffee55daa81cfe01076f6_7.png)

Let's explore these attributes in more detail using the example of a student table in a relational database system。

A simple attribute is an attribute that cannot be classified further。

In the example of the student records， the grade values cannot be classified further。

A composite attribute is an attribute that can be split into different components。For example。

 the name value of each student could be split into sub attributes such as first and last name。

A single value attribute can only store one value in a student table example。

 the date of birth column can only contain one value per student。

So these values could be defined as a single valued attribute。With a multivalued attribute。

 the attribute can store multiple values in a field for example。

 the student email column could hold more than one email per student。

A college email address and a personal email address。However。

 this practice should be avoided in a relational database。

 a derived attribute is where the value of one attribute is derived from another。😊。

In the student table， the age of each student can be derived from their respective date of births。

And finally， there's the key attribute。This is a field that holds a unique value used to identify a unique entity record。

A good example are the values contained in the student ID column。

Each ID is a unique value which can be used to obtain data about a specific student。



![](img/fcca964ba76ffee55daa81cfe01076f6_9.png)

Remember that there's no point in considering entities or attributes that will not be used in your project。

You only need to capture data in your database system that helps the users of your system complete certain tasks and activities。

You should now understand the concept entities in a relational database and be able to differentiate between attribute types。

Good work。