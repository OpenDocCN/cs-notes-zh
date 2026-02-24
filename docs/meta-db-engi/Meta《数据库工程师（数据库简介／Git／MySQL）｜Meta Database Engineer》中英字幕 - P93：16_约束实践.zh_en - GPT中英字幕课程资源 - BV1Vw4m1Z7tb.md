# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P93：16_约束实践.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Little Lemon Rrant need to build two tables in their database that let customers create accounts and register bookings they also need to apply constraints to the columns in these tables to ensure data consistency and integrity Over the next few minutes you'll help little Lemon create these tables and apply the following common constraints Not null unique check and foreign key。



![](img/303360b8d00ef7457cc4d7fa954cd683_1.png)

![](img/303360b8d00ef7457cc4d7fa954cd683_2.png)

And by the end of this video， you'll be able to demonstrate how to apply these common constraints in a MySQL database table。



![](img/303360b8d00ef7457cc4d7fa954cd683_4.png)

The first table that must be created is customers which records customer details。

 and the table requires the following constraints， the primary key constraint on the customer ID column。

 the not nu constraint on the full name column and a unique constraint on the phone number column to ensure that each customer has a unique number。

 so let's get started。Begin with the createate table command and call the tableCustom。

 then add a pair of parenthses Within the parenthesis。

 define the customer ID column as not null and as the primary key This ensures that all IDs are unique in each row of the table and that the column does not accept a null or empty value Next add a full name column with the constraint not null。

And a sign of value of vchar with a character limit of 100。

Then declare the phone number column as not null unique。

This ensures that it only accepts a unique number for each customer， finally execute the statement。

Now let's view the output by writing and executing the following statement。

 show columns from customers。This shows the customers table。

 the table contains all relevant constraints。The columns are defined with not null；

 two keys have been declared。The customer ID column is the primary key。

 and the phone number column only accepts unique values。

The next task is to apply referential integrity This ensures that each customer can make a booking in the restaurant and that each booking must be assigned to a specific customer。

In other words， any customer ID that exists in the bookings table must also exist in the customer's table。

 otherwise it won't be possible to identify who made the bookings。When creating the bookings table。

 it's important to focus on the referential integrity constraint and the check constraint to limit the number of guests to a maximum of eight。

 begin with a create table command followed by bookings and parenthsesis。In the parenthses。

 create the following columns， booking ID， booking date， table number。

 number of guests and customer ID。All columns are defined as not null to ensure that each one must accept a value。

All columns are also assigned the integer value， except bookings date。

 which is assigned a date value。The bookinging ID column is defined as the primary key。

The number of guest column is defined with a check constraint that specifies its not null。

And use a smaller than or equal to operator so that it can only accept a maximum of eight guests。

Next， define the customer ID column with the far and key constraint。

Then use the references constraints so the far key references the customer ID column in the customer's table Now use ondlete and on updatedate cascade options to delete and automatically update the related rows of data in the bookings table however。

 be aware that these actions depend on the update and delete operations taking place in the customer's table Click Enter to execute the statement。

To display the table structure， type the following syntax， show columns from bookings。

 the output set result shows all columns are assigned the required constraints and values。

 and the customer ID column is Mole。

![](img/303360b8d00ef7457cc4d7fa954cd683_6.png)

This means that it's not a unique key and multiple rows can have the same key value。

This makes sense because each customer might make multiple bookings at the same or at different times This code also joins the two tables and establishes dependencies between them。

 so if you change or delete the customer ID in the customer's table。

 then you also update or delete the related record in the bookings table。

 you should now be able to apply different types of constraints in MySQL database to maintain data integrity and consistency Great work。



![](img/303360b8d00ef7457cc4d7fa954cd683_8.png)