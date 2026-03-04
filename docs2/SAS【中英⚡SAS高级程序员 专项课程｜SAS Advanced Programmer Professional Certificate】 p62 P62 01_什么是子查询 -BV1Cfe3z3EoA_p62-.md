# SAS【中英⚡SAS高级程序员 专项课程｜SAS Advanced Programmer Professional Certificate】 p62 P62 01_什么是子查询 -BV1Cfe3z3EoA_p62-

You know you can combine data from multiple tables by using different types of joins。

A join is specified in a single query。Another technique for combining data is to use a subquery in the where or have clause。



![](img/e27e2ee2405818c160590780a9337bef_1.png)

A subquery， sometimes known as the inner query， is a query that resides within an outer query or main query。

ProcSQL evaluates queries from the inside out， starting with the subquery and processes the outer query last。

A subquery in the where or having clause can only return one column。

 it can return a single value or multiple values from that one column。

There are two types of subqueries， correlated and non correlated。



![](img/e27e2ee2405818c160590780a9337bef_3.png)

The most common type of subquery is a non correlated subquery。

A non correlated subquery is a self contained subquery。

It executes independently of the outer query before it passes one or more values back to the outer query。

A non correlated subquery enables you to build and test your code and pieces。In this course。

 we'll focus on non correlated subqueries and just refer to them as subqueries for ease。



![](img/e27e2ee2405818c160590780a9337bef_5.png)