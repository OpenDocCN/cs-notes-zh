# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P92：15_MySQL中的约束.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Little Lemon Restaurant have built two new tables in their database that allow customers to create accounts and register bookings to make sure that these tables work as required。

 the restaurant has set up constraints which ensure that the tables only accept valid data。

Over the next few minutes you'll learn about the concept of constraints in MySQL by exploring how little Le have made use of them in their database and by the end of this lesson。

 you'll be able to identify the main types of constraints and explain how they function and explain the MySQL on delete cascade and onupdate cascade options。

Let's begin with an overview of what database engineers mean by the term constraints。

When creating a table， you might decide that each column must hold a unique value in each row of the table。

 like a phone number。

![](img/442417eae3c2fd95396f01081fe8caf6_1.png)

You can enforce this rule using the unique constraint。

 which prevents any violation of the rule whenever data is inserted or updated in your database。



![](img/442417eae3c2fd95396f01081fe8caf6_3.png)

![](img/442417eae3c2fd95396f01081fe8caf6_4.png)

There are three main types of constraints in MySQL database。

 which can be used to enforce these rules。Key constraints which apply rules to key types。

 domain constraints used to govern the values that can be stored for a specific column and referential integrity constraints which establish rules for referential keys Let's take a few moments to explore each of these three MysQl constraint types and discover how they're used by little Le in their database。



![](img/442417eae3c2fd95396f01081fe8caf6_6.png)

![](img/442417eae3c2fd95396f01081fe8caf6_7.png)

![](img/442417eae3c2fd95396f01081fe8caf6_8.png)

As you learned in the previous course， all tables include different types of keys。

 like primary keys and foreign keys。

![](img/442417eae3c2fd95396f01081fe8caf6_10.png)

![](img/442417eae3c2fd95396f01081fe8caf6_11.png)

You can use constraints to establish rules for these keys。For example。

 the primary key constraint can be used to specify that one or more column values must always be unique。



![](img/442417eae3c2fd95396f01081fe8caf6_13.png)

![](img/442417eae3c2fd95396f01081fe8caf6_14.png)

And they cannot accept a nu value。Little Lemons database contains a table calledCustomers This table records key data on customer bookings using the primary key constraint The table has three columns calledCustom ID。

 full name and phone number。

![](img/442417eae3c2fd95396f01081fe8caf6_16.png)

Customer ID is defined as the primary key which returns data on the table's unique records thanks to the primary key constraint。

 this column's values must always be unique and it can never accept an null value In other words。

 every row in the column must hold a customer ID and all customer IDs must be unique。



![](img/442417eae3c2fd95396f01081fe8caf6_18.png)

Next， let's look at domain constraints。As you learned earlier。

 these are special rules defined for values that can be stored for a certain column。

Little Lemons database contains a bookings table that records data on customer bookings； however。

 the restaurant can only facilitate a maximum of eight guests per booking。

 so they enact the SQL check constraint on the number of guests column。



![](img/442417eae3c2fd95396f01081fe8caf6_20.png)

![](img/442417eae3c2fd95396f01081fe8caf6_21.png)

![](img/442417eae3c2fd95396f01081fe8caf6_22.png)

This limits the value range that can be placed in the column。

 which means the table rejects any numeric values greater than 8。



![](img/442417eae3c2fd95396f01081fe8caf6_24.png)

Finally， let's explore referential integrity constraints。

You learned earlier that this type of constraint establishes rules for referential keys。

 but how exactly does this work？Basically， in a referential integrity constraint。

 there are two types of tables， a referencing table that holds a primary key and a referenced table that contains a foreign key。



![](img/442417eae3c2fd95396f01081fe8caf6_26.png)

The value of the far key column that exists in the referencing table must always exist in the referenced table。

 otherwise a connection can't be established between the two tables。



![](img/442417eae3c2fd95396f01081fe8caf6_28.png)

![](img/442417eae3c2fd95396f01081fe8caf6_29.png)

To understand this better， let's explore the example of the related tables in Little Lemons database in the form of an entity relationship diagram。

Little Lemons database includes two related tables。

 the customers table that holds data on customers and the bookings table that records information on customers bookings with the restaurant。



![](img/442417eae3c2fd95396f01081fe8caf6_31.png)

![](img/442417eae3c2fd95396f01081fe8caf6_32.png)

Each booking in the booking table must relate to a specific customer in the customer's table。

 otherwise the restaurant can't identify who made the bookings。

 and this also means that each customer must already be registered in the customer's table before they can make a booking in the bookings table。



![](img/442417eae3c2fd95396f01081fe8caf6_34.png)

![](img/442417eae3c2fd95396f01081fe8caf6_35.png)

The customer ID column in the bookingings table is defined as the foreign key。



![](img/442417eae3c2fd95396f01081fe8caf6_37.png)

This is the attribute that joins the two tables together and establishes dependency between them。



![](img/442417eae3c2fd95396f01081fe8caf6_39.png)

This means that if a row of data is altered or deleted in the customer's table。

 then this action destroys the related row of data in the bookings table。



![](img/442417eae3c2fd95396f01081fe8caf6_41.png)

![](img/442417eae3c2fd95396f01081fe8caf6_42.png)

In other words， deleting a row of data from the customer's table violates the referential integrity rule。

 and this results in an error message from MySQL， warning that the action directly impacts on the bookings table。



![](img/442417eae3c2fd95396f01081fe8caf6_44.png)

![](img/442417eae3c2fd95396f01081fe8caf6_45.png)

So how can you make the required changes to the bookings table without violating the referential integrity constraint？

In this instance， you can use the on the lead cascade option。

This option automatically deletes the related rows of data from the bookings table。

 and if you want to update a primary key value in the customer's table。

 you can use the unupdate cascade option to automatically update the related rows in the bookings table。



![](img/442417eae3c2fd95396f01081fe8caf6_47.png)

![](img/442417eae3c2fd95396f01081fe8caf6_48.png)

![](img/442417eae3c2fd95396f01081fe8caf6_49.png)

You'll discover more about these options in a later video you should now be able to identify the main types of constraints and explain how they function。

And you should also be able to explain the MySQL unle cascade and unupdate cascade options well done。

