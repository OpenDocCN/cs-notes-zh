# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P89：12_MySQL HAVING.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

At this stage of the course， you may be familiar with the group Boy clauses。

 having helped Lucie Shroub group data from their customer orders in an earlier video Luc Shub now need to filter this grouped data against the list of conditions to determine the best performing departments in the business they can use the MySQL having clause to specify filter conditions that will generate this data。

Over the next few minutes you'll explore the having clauses so that you can help Luc Shrub。

 and by the end of this video you'll be able to identify the MySQL having clause and explain its purpose and demonstrate the use of the having clauses to specify a filter condition for groups of rows。

So what is the H clause and what does it add to your grouping data skill set？

The havinglving clause is used in a SQL statement to specify a filter condition for the group data that the group boy clause generates。

Let's take a moment to review the syntax for this clause。

 starting with a quick recap of the syntax of a typical SQL statement。

As you learned in previous videos， the wear clauseuse is used in a select statement to specify one or more filter conditions。

 and you must place a where clause before the use of the group by clause。

 but the where clause can't be used to specify a filter condition for the group data that the group by clause generates。

 so how do you filter this data？You can add the having clause to your SQL statement。

The having clause is added after the group by clause。

 the having clause is used to specify the filter condition that needs to be applied to your grouped data。

The having clause evaluates the group filter condition against each group returned by the group by clause。

If the result is true， the row is included in the result set， however。

 don't forget that if you omit the group by clause。

 then the having clause behaves just like the where clause。😊。

Let's take a quick look at a basic example of the having clause。😊。

Looky Shbe can use the having clause with aggregate functions to determine which of their departments received orders of a certain dollar amount。



![](img/21982ecea016416aa54446fc71095806_1.png)

Now it's time to use your new having clause knowledge to assist Luc Shrub。As you discovered earlier。

 Lucy Shub needs to filter their customer order data to check which departments met their monthly sales target of $2。

275 Let's see if you can help them out。Let's begin with a review of the order table。

 which holds the required data。The table is divided into five columns， order ID， department。

 order date， order quantity， and order total The first task is to identify which departments have order totals of a value greater than $2275。

 so you're only concerned with the department and order total columns。

You can determine the order total of each department by using a select statement with a group by clause。

First， type the select clause followed by the department column。

You then need to include the sum aggregate function。

Then place the order total column in parenthsesis。Next， add the Fr keyword。

 followed by the table name， which is orders。And finally。

 include the group Boy Claaws and targeted the department column。

Run the statement to retrieve an output that shows the total sales figures for each of the five departments。

Your next step is to filter this data to retrieve the results that have an order total value greater than $2。

275。You can use the same statement as before， but this time add the having clause after the group by clause。

😊，The having clause is followed by a second instance of the Som aggregate function。

 which once again targets the order total column。Finally， use the greater than operator。

 followed by the figure 2275。This instructs the SQL statement to filter results greater than $2，275。

This SQL statement is now ready to execute。 however。

 you can make the syntax more efficient by using an alias。

 You should be familiar with the concept of an alias from previous lessons。

 You can use an alias called total in the select clause for the aggregate function。

This alias can then be referred to in the having clauses。

This makes the condition concise and easier to read。Now you can execute the query。

The output that's generated reveals three departments in Lucky Shub which met this month's sales targets。

Thanks for your assistance， Luc Shub has identified their best performing departments。



![](img/21982ecea016416aa54446fc71095806_3.png)

You should now be able to identify the MySQl having clause and explain its purpose。

 and you should also be able to demonstrate the use of the having clause to specify a filter condition for groups of rows you're making great progress with grouping data。

😊。