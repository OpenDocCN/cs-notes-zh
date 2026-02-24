# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P88：11_MySQL GROUP BY.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Looky Shroba reviewing recent customer orders in their database。

 they need to find a way to group records with similar values into one single record so that they can analyze the order data and produce summaries。

The MysQL group boyCaws and its related aggregate functions are a great way for the company to complete this task。

😊，Over the next few minutes， you'll explore these concepts and use them to help Luc Shrub produce summaries of their orders。

 and by the end of this video you'll be able to group rows into subgroups using the MySQL group bylaws and utilize the MySQL group bylaws with SQL aggregate functions。

So before you begin helping Luc Shrub， let's take a moment to find out what database developers mean by the term group by。

The group Boy clause is used in SQL syntax to group rows in a table based on given columns into summary rows。

 also known as subgroups。To get a better understanding of this clause， let's look at the syntax。

The syntax begins with a select statement followed by the name of the required column。

The from clause is then added and targets the name of the table that holds the required column。

 Finally， there is the group by clause After this clause。

 a list of column names are added each one is separated by a comma。

These are the columns according to which the data must be grouped if there's a where clause in your select statement。

 then the group by clause must be placed after this clause。

And make sure that the columns listed in the select clause include the columns listed in the group by clause。

Additionally， the group by clauses is also frequently used with aggregate functions。

An aggregate function can be used with the group by clause to perform one or more calculations and return a single value for each subgroup。

You might be familiar with aggregate functions from previous videos， but if not， don't worry。

Here's a quick recap of the main aggregate functions used by database developers with the group by clauseus。

Some used to add values of given columns together and return a single value。

 average used to determine the average of column values and max。

 which returns the maximum value of one or more given columns。

 the minimum aggregate function determines the minimum value of one or more given columns。

And finally， count is used to count the number of instances that a given column value occurs。

Let's review this syntax of the select statement when using the group by clause with an aggregate function。

First， input a select statement followed by a list of columns。

You can then apply the aggregate function on any of these columns as required， for example。

 you can use the max aggregate function to calculate the maximum values in column 1。

Just make sure to place the column in parenthesis。Next。

 include the from clause and the name of the table that holds the columns finally。

 include the group by clause followed by the names of the columns by which the data should be grouped。

Make sure that these same columns are also present in the select column list。

Lucky Shrub can make use of the group by syntax and aggregate functions to determine the total number of orders received by each department in the business。

 so now that you've learned about the group B clause and aggregate functions。

 it's time to use your knowledge to help Luc Shrub。



![](img/c64ce7ab137c8ce5f8b1dd028fe2bc03_1.png)

Let's start with a quick review of the order table。The table contains five columns， order ID。

 department， order date， order quantity， and order total There are multiple records with the same value for the department column。

For example， there were five orders placed with the lawn and Care Department。

 this means that there are a total of five records for the lawn Care Department。

 and there are more instances of multiple records with the same value for other departments like decking。

The best approach in this instance is for Lucy Shub to group all these records so that they have just one row for each group or department。

 this will make it much easier to analyze the data and produce summaries。

You can help them to reduce the departments into five groups or subgroups using the group by clause First。

 write a select statement followed by department the column name。Next。

 insert a from clause followed by orders， the table name。

Then add the group by clause and the name of the column。Finally。

 run the statement to generate the output。In the output that's returned。

 all records in the department column have been reduced to five groups。

 one row or one single record for each department in the business Now that you've simplified the table。

 you can use aggregate functions to analyze the data。

Ly Shruub's report must show the number of orders placed with each department。

 you can use the count function to produce this data。

The syntax for this query is almost the same as the previous one you just performed。

The key difference is that you must add the count function followed by the column name in parenthsesis after select department。

This specifies which column holds the data and the count function counts the occurrences of each department among the order records。

Now just execute the query to generate the output。The output returns the five departments alongside the total number of orders placed with each Next。

 let's find out how much money each department made from these orders。

You can use the same syntax from the previous query。

 but this time use the sum aggregate function with the order total column。Then execute the query。

The output returns the total sum of the selected numeric column。In other words。

 it adds the values in the order total column for each instance of each department。

Now let's determine the minimum order quantities for each department。Once again。

 you can use the same syntax but with the min function targeting the order quantity column。

Once you run the query， the output returns the smallest value of the column Finally。

 Luc Sub also need the average order total for each department。

 so write the syntax one last time and in this instance you can use the average aggregate function to query the order total column。

The output that's returned shows the average value of the order total column thanks to your help。

 Luc Sub now have a summary that shows all the relevant data from the order table grouped together as required。



![](img/c64ce7ab137c8ce5f8b1dd028fe2bc03_3.png)

Have improved your skills with Luc shrub， you should now be able to group rows into subgroups using the MysQL group by clause。

 and you should also know how to use the clause with SQL aggregate functions。Well done。

