# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P34：33_模式应用.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

By the end of this video， you'll know how to create a simple database schema using SQL。

You'll do this by building the schema for a shopping cart database consisting of three tables。

Let's start by creating a new database called Shopping Cart TBB。First。

 I type the Create database keyword， followed by the name Shopping cart TV。Then I run the statement。

The Shop cart DB database appears in the left hand Explorer。

Now I can create the tables inside this database。First。

 I need to create the customer table which stores the following information on each customer。

Customer I D， name， address， email and phone number。To create this table。

 I use the create table keyword， and then I type customer。Followed by parentheses。In the parentheses。

 I specify the fields and their data types as follows。The customer ID data type is integer。

 while the others are varchar。I give the name and email fields a character limit of 100。

I assign a character limit of 255 per address。And I assign the limit of 10 characters for phone。

Also note that I've used the primary key keyword on the customer ID column。

This designates that field as the primary key of the table， a role you'll learn more about soon。

Next is the product table， which stores the product I， name， price and description。

I can specify this table。As follows。The product I D has the integer data type。 The name is a varchar。

 with a 100 character limit。The price has a numeric type with parameters of 8 and 2。

The description is varchar with a 255 character limit。

And the product ID is set as the primary key within this table。And finally。

 there's the cart order table， which holds the order ID，Custom ID， product ID， quantity， order date。

 and status。This table is set up as follows。The order ID， customer ID。

 product ID and quantity are all integer types。Order date is date。

 and status is varchar with a 100 character limit。Order ID is the primary key here， however。

 this table also introduces something new in the form of two foreign keys。Before moving forward。

 let's quickly discuss what primary and foreign keys are。

You may have noticed that the CAt order table contains the customer ID and product ID fields。

These same fields are also found in the other two tables。

This is because these fields in the CAt order table are directly linked to the same fields in the corresponding tables。

To establish this relationship， each table must contain a primary key。

The referencing table then uses foreign keys that point it to the external source table or the reference table。

You'll learn more about primary and foreign keys in greater detail in a later lesson。But for now。

 let's return to the shopping cart database example。All primary keys have been set up。

So the foreign keys for the cart order table come next。

I create the first one by using the foreign key keyword， along with the custom ID column name。

To link to the customer ID field in the customer table。

 I then used a references keyword followed by the source table name， customer。

 and thenCustom ID in parentheses。Creating a foreign key for product ID is similar。

 but with product and product ID as references。So I use the foreign key keyword and name it product ID。

I then reference it in the product source table， product， and then product ID。

Then I execute these statements。

![](img/11c015633b79df4bde1f90d1991c7638_1.png)

And the tables appear nested beneath shopping cart to B in the left hand Explorer。In this video。

 you learn the steps for creating a simple database schema using SQL。

 The same process applies for both small and large scale databases。



![](img/11c015633b79df4bde1f90d1991c7638_3.png)