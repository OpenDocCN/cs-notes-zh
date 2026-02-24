# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P96：19_MySQL子查询.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Little Lemon restaurant need to extract financial info from their database to complete their accounts；

 they can carry out this task using a subquery。Over the next few minutes。

 you'll explore the concept of a subquery and learn how to recognize a subquery and understand its syntax。

 identify scenarios in which a subquery can be used。

 and explain how subqueries are used to retrieve data。So to begin。

 let's answer the question of what is a sub queryry？As the name states。

 a sub queryry is a query within another query。In other words。

 it's an inner query placed within an outer query。The inner query is viewed as the child query and the outer query as the parent query。

But what does a query within a query look like？Well。

 the best way to understand the subquery is through its syntax。As you just learned。

 a subquery is a query within a query。An inner or child query within an outer or parent query。

The In query or Sub query executes first， and its results are then passed through the Outer or parent query。

You can also build multiple subqueries in MySQL the outer query is presented like any normal query。

 it contains select from and where clauses。Likewise， the subquery is written as a standard query。

However， the sub query must always be placed within a pair of parenthses。When executed。

 a sub query can return any of the following results， a single value， a single row， a single column。

 or multiple rows of one or more columns。A key advantage of a sub query is that you can compare it against other values using a comparison operator。

You should be familiar with comparison operators from previous lesson items in this specialization。

If not， here's a quick recap。Examples of commonly used standard comparison operators include equal to。

 less than and greater than。There's also less than or equal to， greater than or equal to。

 and not equal to。Let's look at the syntax for Squeries and comparison operators。

A sub query can be placed before or after a comparison operator in the where clause of your parent query。



![](img/98ddfd9e9b776f95ae86275816b5436d_1.png)

Now that you're familiar with the basics of subqueries， here's a demonstration of how they're used。

Little Lemon R are reviewing their accounts and need employee salary data from their database。

This data is held in the employees table。The table contains four columns， employee ID， employee name。

 role and annual salary。Little Lemon must use this table to identify which employees earn a salary higher than that of the assistant chef。

You can use a sub query to complete this task。This query can be completed in two parts as follows。

The outer or main query must extract details of all employees whose annual salary is greater than the specified value。

And the sub query must identify the annual salary of the assistant chef。When executed。

 the sub query provides a subsetet of data from the employee's database。

 and this subet of data is then used as an input for the outer query。

Begin by writing the outer query as follows， a select command followed by an asterisk。

Then the F clause， which targets the employee's table。

The next part of the Outer query must filter out the employee's table data based on the annual salary。

So add a where clause followed by the annual salary column。

Then add the filter condition in the wear clauses， the annual salary column followed by a greater than operator symbol。

The greater than operator most target a specific value。But how do you determine what this value is？

You can use a soap query。Write a soap query within your main query as follows。

Add parenthsesis after you're greater than operator。Within the parenthses。

 write select Anual salary column fromEmployees table。Then write a wear clause。

 followed by the roll column。Finally， add an equals operator followed by the Asist Che value。

Now that you've written bold queries， press Enter to execute。

The So query executes first and extracts the annual salary of the assistant chef。

This value is now the input for the outer query's where clauses。Next， the outer query is executed。

The Outer Que's War clause filters out the records of all employees earning an annual salary greater than that of the As Che；

 In other words， the Outer query filters out the values greater than the value retrieved by the sub query。

The Sobque'riess result shows that the assistant chef earns $45，000 a year。

And the Outer query shows that there are three employees who earn more than the assistant chef。

These employees are the manager， assistant manager， and head chef。



![](img/98ddfd9e9b776f95ae86275816b5436d_3.png)

And that's an example of how the sub queryry is used in a database。

You should now be able to recognize a sub query， understand its syntax and identify scenarios in which a sub queryry can be used well done。

