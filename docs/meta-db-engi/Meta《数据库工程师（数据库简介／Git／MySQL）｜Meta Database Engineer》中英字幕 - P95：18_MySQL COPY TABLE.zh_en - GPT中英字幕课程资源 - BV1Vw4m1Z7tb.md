# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P95：18_MySQL COPY TABLE.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Looky Shrub are planning an overhaul of their database In preparation。

 they want to create copies of their data to keep it safe during the rebuild they can complete this task using the copy table process over the next few minutes you'll learn about the process for copying a table and then help Lucie Srub to copy tables in their database and by the time you complete this video you'll have learned how to。

Copy data from an existing table to a new table within the same database。

 copy a table to a new location while ensuring it retains its constraints and copy data from an existing table to a new table from a different database。

These tasks are carried out using the Create table syntax； however， before you explore this syntax。

 let's take a moment to review the process for copying tables。

It's important that you're familiar with the process before you begin copying tables。

You first need to identify the database and the table you want to copy the data from。Next。

 determine the columns you want to copy， either all columns are just some of them。

Then use the Create table statement to build a new table with a relevant table name and finally。

 use the select command to structure the new table by specifying the columns you want to copy data from。

Now that you're familiar with the process steps， let's review the Create table syntax。

The copy tableable SQL statement begins with the Create tableable command。

 followed by the name of your new table。Next， write the select command。

 then identify the columns to be copied。You can copy one， several or all columns。Finally。

 use the Fr command followed by the name of the existing table you want to copy。

But what about copying a table between two different databases？Once again。

 begin with a create table command however， in this instance。

 you must use dot notation to identify the names of the new database and table。

Then use the select command to select the existing tables columns and finally， use the F clauses。

Then follow this with another instance of dot notation that identifies the names of the existing table and database to be copied。



![](img/f9a5c76969769a7b8c2cc18d7294ce6d_1.png)

Ly Schhroub are now ready to begin copying tables in their database。

 They want to carry out the process as follows。 First。

 they need to copy the client's table to a new table called client's test in the same database They then need to copy a few select columns to the table。

 Next， they need to make sure that all constraints from the original table were copied over to the new one。

And finally， they want to copy a table from one database to another。

Use your new knowledge of the copying tables process to help them out First。

 let's review the client's table in the Lucy Srub database by typingSe asterisk from Cl。

 then click Enter to execute the query。This generates the client table on screen。

The table contains four columns， client ID， full name， contact number and location。

For the first part of the test， Lucy Shrub need to copy the Klein's table to a new table called Klein's Test in the same database。

You can perform this task using the Create TableSQL query to create two statements。

In the first statement， use a basic C table clause to create the new clientient test table in the second statement。

 type the select command with the asterisksteris as shorthand for all columns。

 then type the existing table name which is clients。Finally， click Enter to execute the query。

This query copies all columns and their data from the client's table to the new client's test table。

To check that the query was successful， you can type the following statement。

 select asterisk from client Test， then click Enter to execute。

This query generates the client's test table and the table contains a copy of all the data as required。

Next， Lucy Srub needs you to copy partial data only。

They need to copy the full name and contact number columns from the client's table to another table。

Begin with a Cate table statement， followed by the name of the new table， which is client Test 2。

Then use a select command。But in this instance， specify just the full name and contact number columns。

Type the Fr keyword， followed by the name of the existing table， which is clients。Finally。

 use the where clause in the select statement to specify a condition in this case。

 copy the data only for those employees who live in Pal County， click Enter to execute the query。

The query's output shows the client's test2 table。And the table contains a copy of all the data from client Test for all employees from Pal County。

 the test worked。Next， you need to make sure that all constraints from the original table were copied over to the new one。

It's important to remember that copying data using the methods you've encountered so far doesn't copy the key constraints。

You can check the constraints on the original table by typing and executing the statement。

 show columns from clients。The query generates the client's table。

The table structure shows all columns with the key constraints set for the client ID and contact number columns。

Now let's check for these constraints on the client's test table by typing and executing the following statement。

 show columns from Clients test。This statement shows the client's test table。

The table is missing the primary and unique keys defined in the original table。

So how can you copy these keys？You can use the following statement。Create table clients test3。

 like clients。The like keyword creates an exact copy of the existing table structure。

Press enter to execute the statement。Then type and execute the following SQL statement to display the new table structure。

Show columns from clientss Test3。The output shows an exact copy of the initial client's table。

 and all the key constraints have been copied as expected。

Your final task is to copy the client's table from the Lucy Srub database to the new Test database。

Begin with their C table statement。Then specify the new database and table names as testdb。

clients test。Type select asterisksteris to instruct SQL to copy all data。And finally。

 add the Fr keyword followed by the existing database and table names， which are Lucshub。 clients。

Click Enter to execute the query。Now you just need to check that the query was successful by moving into the test database。

Type Test DB， then show tables to reveal all tables in the test database。

This statement reveals all the tables created in the test database。

 including the client's test table you just copied over from the Lucy Shub database。

 and the table contains all the data from the original one。



![](img/f9a5c76969769a7b8c2cc18d7294ce6d_3.png)

Ly Shroub now have all the required copies of their tables in their database You should now be able to copy data from an existing table to a new table within the same database。

 copy a table to a new location while ensuring it retains its constraints and copy data from an existing table to a new table from a different database。

 great work。