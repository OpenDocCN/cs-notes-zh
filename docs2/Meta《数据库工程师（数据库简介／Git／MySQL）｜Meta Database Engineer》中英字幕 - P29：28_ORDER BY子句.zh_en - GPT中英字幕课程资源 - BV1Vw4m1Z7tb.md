# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P29：28_ORDER BY子句.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

There are several clauses available in SQL for sorting and filtering data in a table。

 One of the most useful of these is the order by clause。With this clause。

 you can reorder the data in a table by one or more columns， for example。

 in a table that holds data on students in a college， you could sort the data by date of birth。

The table would then present all students in the order of oldest to youngest。

By the end of this video， you'll be able to demonstrate the purpose of the order by clauses for sorting data。

Explain the different forms in which the order by clause can be used to sort data and describe how the ascending and ascending keywords behave when used on sort columns。



![](img/c54f58f69a664217f5c24ccec99bee10_1.png)

Let's begin with an exploration of the purpose of the order clause。

The order by clauseuse is an optional clause that can be added to a select statement。

Its purpose is to help sort data in either acing or descending order， for example。

 you can sort a list of student names in an alphabetical order from A to Z or vice versa。



![](img/c54f58f69a664217f5c24ccec99bee10_3.png)

To get a better understanding of how the order B clauselaus works， let's explore the syntax。

In its most basic form， the syntax of the order by clause is as follows。

It begins with a select statement。😊，Then a list of the columns to be sorted with each one separated by comma。

Next is a Fr keyword， followed by the name of the table to be sorted。Finally。

 the order by clauses added， followed by the name of the column to be sorted。

At the end of the column name， state how you want the data to be sorted。

You can do this by specifying ASC for sending order or DESC for descending。

But the order by clause doesn't limit you to just the one column；

 you can also use this syntax to order the data from multiple columns。

The syntax for sorting multiple columns is very similar to that used for a single column。

The key difference from multiple columns is that you must type the name of each column after the order by clause。

Just make sure that you separate each column with a comm and specify whether you want to sort the columns in ascing or descending order。

It's also possible to specify all columns after the select keyword by using an asterisk。



![](img/c54f58f69a664217f5c24ccec99bee10_5.png)

This is a much easier method than listing all columns one by one。Finally。

 it's also important to note that the type of data in your table affects how it is sorted。

If the column has a numeric data type， the records will be sorted in the ascending or descending numerical order。

And if a column has a text based or string data type。

 then it will be sorted in as sendinging or descending alphabetical order。



![](img/c54f58f69a664217f5c24ccec99bee10_7.png)

Next。Let's explore some examples of the order by clause in a SQL statement。

Let's begin with an example of ordering data by single column。For this example。

 I'll use a table that lists details of students in a college。😊。

I need to sort or order this data in ascending order of each student's country of nationality。

 so in this instance， the order by column must be the nationality of each student。

Each student's nationality is listed in the table's fifth column。



![](img/c54f58f69a664217f5c24ccec99bee10_9.png)

I begin by writing a select statement， followed by the names of the columns that I want in the result。

Id。😊，First name， last name and nationality。Then I write the Fr keyword。

 followed by the name of the table， which is student table。 Next， I type the order by clause。

Then I specify the name of the column by which I want my data to be sorted， which is nationality。

Finally， I type ASC so that the data is sorted in the sending order， I then execute the statement。

All students in a table have now been sorted according to nationality in ascending order。

 note that even if I was to omit ASC from the end of my code， I'd still get the same result。



![](img/c54f58f69a664217f5c24ccec99bee10_11.png)

This is because the order by clause sorts all data in as sendingending order by default。



![](img/c54f58f69a664217f5c24ccec99bee10_13.png)

Let's run the same statement， but this time using DESE or descending instead of ASE。



![](img/c54f58f69a664217f5c24ccec99bee10_15.png)

All students in the table have now been sorted by nationality for a second time。

 but in this instance， they have been sorted by descending or averse alphabetical order。



![](img/c54f58f69a664217f5c24ccec99bee10_17.png)

Finally， let's explore an example of sorting data by multiple columns。In this example。

 I'll sort each student by nationality and date of birth。First， I write the select statement。

Then I write the names of the columns I wanted in my result。Id。First name， last name。

 date of birth and nationality。I then write the Fr keyword and student table， the name of the table。

Next， I type the order by clause and specify the names of the columns by which I want my data to be sorted。

 which are nationality and date of birth。I then add ASC after nationality so that the data is sort of an ascending order of nationality。

And I add DE after date of birth so that the data from this column will be sorted in descending order。

 then I run the statement。

![](img/c54f58f69a664217f5c24ccec99bee10_19.png)

This returns my table with the data for the specified columns organized as instructed。

 which is alphabetically for nationality and youngest to oldest。

This was a short introduction to the SQL order by clauseaws you can now demonstrate the purpose of the order by clauseaws for sorting data。

 and you can also explain the different forms in which the order by clauseaws can be used to sort data。

Great work。