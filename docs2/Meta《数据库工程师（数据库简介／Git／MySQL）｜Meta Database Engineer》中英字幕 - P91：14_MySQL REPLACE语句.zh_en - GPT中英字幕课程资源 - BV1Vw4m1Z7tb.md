# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P91：14_MySQL REPLACE语句.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Ly Shrub Gardening Center are hiring some new employees once these new employees have been hired。

 the company then needs to add their contact details to the database some of these contact details must also replace those of employees who've recently left。

The replace command is the best method for Luc Shrub to make these changes。In this video。

 you'll learn how the replace command can be used to help Luc Srub make these changes。

And once you've helped Luc Shub， you'll then know how to。

Explain how the replace command works in a MySQL database and demonstrate an understanding of the replace command by inserting or updating data。

Let's begin with an overview of the replace command。

The replace command is used to insert or update data in a table， however。

 unlike the standard insert and update commands， replace first checks for a duplicatea key if found it deletes the existing record and replaces it with the new one。

So now that you know what the replace command is used for， it's time to look at this syntax。

But first， let's quickly recap this syntax for the insert command。

Its similarity to the replace command should help you to understand the replace command better。

You should be familiar with the insertt into command from the previous course With this command。

 you instruct SQL to insert new values into designated columns within your chosen table。

The replace command works in much the same way。You type out your table name， column names。

 and values just like before。The only difference is that you must begin the statement with a replace command。

You can also use replaceplace command with the set keyword。

The set clause assigns a value for the selected column but without using the where clause to specify the condition；

 In other words， it locates the required record of data then replaces the values with the new set。

If you don't specify a column value in the set clause。

 then the replace command uses a default value or sets the value to null。

The replace command is a complicated concept and a similarity to other commands can be confusing。

So to help you out further， let's take a moment to visualize how the replace command works。😊。

As you just learned， the replaceplace command first checks if the new record of data already exists in the table by checking the primary or unique key of existing records。

 if there's no matching key， then replace works like a normal insert statement and adds the new data。

If a matching key is found， then the command deletes the existing record and replaces it with a new one。

Now that you're familiar with how the replace command works。

 take a few moments to see if you can help Lucky Shrub insert and replace new and existing employee records in their database。



![](img/b994cb3b39c09cf2c7499c783b7a37eb_1.png)

Lookingy Shrub's employee contact records are stored in the employee's contact info table The table consists of three columns。

 the employee ID， which is the primary key， the contact number and email address columns。

You need to insert a new record of data for the new employee Shamus Hogan with the following details。

 an ID equal to one， a contact number， and an email address。

You can add this data to the table using the standard insertst command。

 just type insertsert into followed by the table and column names。

Then add the values to be inserted into each column， ID， contact number and email address。

Click Enter to execute the query。The new employee record is added to the table。

You can do the same with a replace command for the employee Thomas Erickson。

Begin with the replace into command， followed by the table and column names to be updated。

Then use the values keyword and list of values to be added to the table for Thomas。

These values are as ID， contact number， and email address。Click Enter to execute the query。

You can then use a select statement to check the table's records。

The output shows that Thomas's contact details are now in the table as are those of Seamus； however。

 Seamus has decided to leave Luc Shrub to work for a rival gardening center。

 so you now need to replace his details with those of a new employee Maria Carter。

You can try updating the table using the insertert command。

Type an insert into statement just like before， and assign Maria an ID of one in your statement's values alongside her contact number and email address so that her records replace those of shames in the table。

 then execute the query。But it looks like SQL can't execute this query。

Instead of adding Maria's details to the table， it's returned an error message warning of a duplicate entry。

This is because you're trying to assign Maria an ID of one。

But this idea is already assigned to shame us as a primary key value。

The primary key must always have a unique value in each row of the table， otherwise。

 MySQL returns an error message。So how can you replace Seamus's records with Maria's？

Type the statement again， but this time use the replace command instead of insertt。

 then click enter to execute the query。My SQL has accepted the statement with no errors。

Let's query the table to make sure it contains Maria's records。

Type a select statement and from keyword followed by the table name。

 then click enterter to execute the query。The output returns the contact details from Maria and Thomas。

My SQL has replaced James's records just like you instructed。There's one more task to complete。

Maria has recently changed her contact number， so the number also needs to be updated in the table。

You can use the replace commands to update the record of data。

Type the replace command and the table name， then use the set clause with Maria's employee ID of one。

 followed by the new value which is her contact number。

But make sure that you set values for all columns， otherwise they'll be set to null or default values。

Pss enter to execute the query You can use a select statement to check the table and confirm that Maria's details are updated thanks to your efforts Luc Sve's employee contact info is now up to date you should now be able to explain how the replace command works and demonstrate the replace command by inserting or updating data great work。



![](img/b994cb3b39c09cf2c7499c783b7a37eb_3.png)