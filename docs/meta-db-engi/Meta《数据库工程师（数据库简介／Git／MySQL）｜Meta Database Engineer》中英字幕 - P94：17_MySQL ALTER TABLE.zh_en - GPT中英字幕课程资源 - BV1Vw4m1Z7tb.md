# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P94：17_MySQL ALTER TABLE.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Lishhrub Gardening Center has bought new heavy machinery but it can only be operated by qualified employees The business has a database table called Machry that records the contact info of all qualified employees。

 however， the table has issues with its constraints and it's also missing some key information。

Looky Sub can fix these issues by making alterations to the table using theal statement Over the next few minutes you'll learn about the Al statement and then use what you've learned to help Luc Shrub alter their database and by the end of this video you'll be able to add。

 delete and modify columns and constraints in an existing table。

Let's begin with an overview of the altar statement and its syntax。

You might often encounter tables in a database that contain missing columns or constraints。

 or their existing columns and constraints may need to be modified。

You can use the Al table statement to make these changes the Al table statement is often used alongside different SQL commands here's a quick overview of some common commands used with the Al table statement。

The modify command is used to target specific columns and instruct SQL to make changes to them。

The add command can be used to add a new column to a table。

 and the drop command can be used to drop or delete a column from the table。

So how are these commands used to make alterations to a table？

The Al table statement begins with the alar and table clauses。

 followed by the name of the table to be altered。Next。

 insert a modify command followed by the name of the column to be altered and the changes to be made for example。

 you can change a columns data type and add a not null constraint。

Then repeat the modify command for all other columns you want to alter You can also alter a table by adding another column。

 just use the add column command followed by the name of the new column。

To remove a column from a table， just use the D command followed by the name of the column you want to drop or delete。

Now that you're familiar with the Alar table statement。

 see if you can help Lucky Sub make the required changes to their table。

The tasks that Lucie Sub need to complete are as follows。

 set the employee ID column as the primary key， change the column constraints。

 and add a new column to the table， let's get started。



![](img/eb077cb1a9a62b7608bd9019eb585778_1.png)

Lookingy Shru's machinery table includes four columns， employee ID， full name。

 phone number and county。The table is missing a primary key。Fortunately。

 the employee ID column is the perfect candidate because all values are unique。

To set this column as the primary key， you can write an Al table statement。

Add the Altar table clauses followed by the table name。

Then write the modify command and the employee ID column name。Next。

 set the data type as varchar with a character limit of 10。

Then set a not null value to ensure that the column always contains data。Finally。

 add the primary key value to the column。The employee ID column is now the table's primary key。

It looks like each column in the table is also set to accept null values This means that the table can contain empty fields or rows。

 which is poor practice in a database。So to change all columns to not Null。

 you can write another Altar table statement。In fact。

 you can use the same statement as before and just add a new line for each column。😊。

For the full name and county columns， you can write the following syntax。Add a modify command。

 set the Vichar data type to 100， and a value of not null。For the phone number column。

 you can write the same syntax， but with integer and unique values。

This means that the column now accepts unique numeric values only。This avoids any duplicate values。

To view the new table structure， write the following statement， show columns from machinery。

This query's output shows that。The employee ID is now set as the primary key。

 the phone number is a unique value and all columns are set as not null。Now。

 your final task is to add a new column to the table。

Looky Srove's machinery can only be operated by employees aged 18 and over。

 so the company needs to identify each employee's age and determine who is old enough to operate the machinery。

There's currently no age column in the table， so you'll need to create it and add a constraint to ensure every new employee added to the table is at least 18 years old。

You can write the statement as follows， Al table followed by the machinery table name。

 then the add column command。Next， call the new column age and assign it an integer value。Finally。

 use the check function to limit the values in this column to at least 18 or more。

Then click Enter to execute the query。To view the table's new structure， write。

 show columns from machinery。The output now displays the machinery table with a new age column。



![](img/eb077cb1a9a62b7608bd9019eb585778_3.png)

Thanks to your help， all the required changes have now been made to Lucie Sve's machinery table。

You should now be able to use the Al table clause to add， delete。

 and modify columns and constraints in an existing table great work。

