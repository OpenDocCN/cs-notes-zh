# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P98：6_MySQL Workbench中的数据管理.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

As a database engineer， you'll frequently need to create complex and robust database systems。

 This can be a difficult task。 But luckily， you can use tools like MysqL workbench to create database systems quickly and efficiently。

 In this video， you'll learn how to use MysQL workbench to create databases and tables and view。

 insert and select data。 over at M and G， they need to create a database system to manage staff records。

 They've decided to create this new database using MysqL workbench because of its SQL editor。

 G U I and other useful features。 Let's help M and G to create their new database using MysqL workbench。

 The first task is to create a new database schema Choose a MysqL server instance and select the schema menu to create a new schema。

 select the create schema option from the menu pane in the schema toolbar。

 This action opens a new window。 within this new window， enter Mg underscore schema。😊。

In the database name text field， select apply this generates a SQL script called create schema MG schema。

 You are then asked to review the SQL script to be applied to your new database。

 Click on the apply button within the review window if you're satisfied with the script a new window screen appears。

 Ask me if you'd like to execute the create schema statement。

 Select the finish button to create the MG schema。The schema has now been successfully created and is listed in the schema menu。

You might need to select the refresh icon from the menu to view new schemas to view information on the MG schema。

 select it and click the information icon。 This action brings up a new window that contains several options like tables。

 columns， triggers and more you can also double click the schema name to view a submenu of all created tables。

 views， procedures and functions。 If you want to delete the schema right click the name and select the drop schema option。

The next task is to create a new table inside the MG schema to hold the staff information。

 right click the tableables option in the submenu， select Create table from the list of options that appear。

This brings up a new table form， enter staff in the table name text field。

 use the default settings for all other fields。Fill the column details in the middle window as required。

 change the name of the first column to staff ID， define the column as integer and set it as the primary key using the check boxes。

Add the following remaining columns using the same method， full name， contact number， role and email。

 set each column's data type。Then declare each column as either null or not null as required。

 Finally， click the apply button to generate the relevant SQL statement you should now be able to review the SQL statement that creates the staff table。

 Click the apply button to generate the relevant SQL statement。

 review the SQL statement and click apply to execute the statement then select finish to Sa your changes。

 You can now view the staff table in the MG Schema database。

 Select the information icon to view the table structure。

The information window appears and shows options for columns， indexes， and other table elements。

Click the columns tab to show the column structure。

Another method is to typeDescribe staff in the SQL editor。

 then click the run button to execute the statement。

This displays the details of the staff table structure。

Your next task is to create a virtual table in the schema called Staff View。First。

 right click the View submenu of the MG schema， select the Cate View option to open the SQL editor。

Type a Cate View SQL statement to create the virtual table。

Create a basic view to show the staff full names and contact numbers。

Click the apply button to bring up the review window。

You'll see some SQL code with suggestions that you can either accept or amend as required for now。

 amend the table by creating aliases for the columns so that they're easier to view when querying the table Finally。

 click the apply button then click finish to create the table you can now view the virtual table in the MG Schema submenu Next MG needs you to populate the staff table with data。

To insert data in the staff table， you'd usually use the insertt SQL statement in the SQL editor。

 however， with My SQL workbench you can populate the table grid directly first。

 right click the staff table， then select rows from the list of options that appear。

 enter the MG staff records into the table。Click the apply button to generate an automatic insert into statement。

 then click the apply button again once you review the statement in the review window to execute the statement Finally。

 select finish。The staff records are now stored in the staff table。

 Your final task is to query data from the M&G database。

 You can query the database using My SQL Workbench's SQL editor write a select query that extracts all data from the staff view table。

 This query outputs all data that exists within the staff view table into a table grid。

M and G have now created their staff table and populated it with required data。

M and G have now created their staff table and populated it with the required data。

 and you should now be familiar with how to use MySQL Workbench to create databases and tables。

 as well as view， insert and select data， great work。



![](img/55c313acaf40d402ee15f8dc1a136bd7_1.png)

![](img/55c313acaf40d402ee15f8dc1a136bd7_2.png)