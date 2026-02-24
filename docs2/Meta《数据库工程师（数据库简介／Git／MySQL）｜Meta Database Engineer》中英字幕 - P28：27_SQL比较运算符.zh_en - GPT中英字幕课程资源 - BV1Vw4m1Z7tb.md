# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P28：27_SQL比较运算符.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Imagine you're running a database for a soccer club。As a database engineer。

 there's a lot of work required to manage this database， for example。

 you might need to categorize players into groups according to their ages。

 how can you complete this kind of task。You can use SQL comparison operators。

Over the next few minutes， you'll learn how to explain the concept of SQL comparison operators and utilize SQL comparison operators in a database。



![](img/ecf5115cb98944afb87c6c2f49c41280_1.png)

so。What are SQL comparison operators？Comparison operators are used to compare two values or expressions。

 where the outcome result can be either true or false。



![](img/ecf5115cb98944afb87c6c2f49c41280_3.png)

They can be used to filter data and to include and exclude data。

So how are these operators used in SQL？SQL uses common mathematical comparison operators by means of the symbols equal to。

Less than and greater than。It also uses less than or equal to， greater than or equal to。

 and not equal to。

![](img/ecf5115cb98944afb87c6c2f49c41280_5.png)

Now let's explore how to use these comparison operators and relevant symbols in a practical way using a database。

To demonstrate the use of SQL comparison operators。

 I'll use the example of an employee table from a company database。

This table includes information on each employee's ID。Name and salary。Now。

 let's assume the employer wants to extract relevant data from the employee table about the employee's salaries for different purposes。

 each instance of data extraction will require a different comparison operator。

 so in the first example the employer wants to identify all employees receiving a salary equal to $18。

000 per year。I can identify these employees using the Equ2 operator。



![](img/ecf5115cb98944afb87c6c2f49c41280_7.png)

First I click the SQL tab in the main menu， then I write selectAs risk fromEmploy where salary equal to symbol 18。

000。Let's break the SQL statement down the select command is used to retrieve data。

 the asterisk star denotes that I am selecting data from all columns。

 the Fr keyword and the table name specify where the data will come from and then I define the condition using the wear clauses。

In this case， the condition uses the equal to symbol to check if the salary value in each record of the table is equal to $18。

000。If the result is true， then the data is retrieved。So I run the query and generate an output。



![](img/ecf5115cb98944afb87c6c2f49c41280_9.png)

The output result of this query is that the employees Carl and John， earn $18，000 per year。



![](img/ecf5115cb98944afb87c6c2f49c41280_11.png)

You can apply the other comparison operators in a similar way to perform different functions。

Let's take another example to find out more。In this next example。

 the employer needs to know which employees are receiving a salary that is less than $24。

000 per year。This task requires a different operator to find this information I can write select。

 asked risk from employee， where， salary， less than symbol  24，000。

This SQL statement utilizes the less than symbol to check whether the value stored in each field of salary column is less than $24。

000。

![](img/ecf5115cb98944afb87c6c2f49c41280_13.png)

Once again， I select the Go button to execute the query and generate an output。

The output of this query is that the employees， Carl and John， earn less than $24，000。



![](img/ecf5115cb98944afb87c6c2f49c41280_15.png)

Let's take another example where the employer needs to determine which employees receive a salary that is less than or equal to $24。

000 per year。In this case， I need to write the following query， select asterisk from employee， where。

 salary less than or equal to symbol 24，000。The only thing in this statement that has changed from the previous example is the operator symbol。

This less than or equal to symbol tells the SQL statement to check whether the value stored in each field of the salary column is less than or equal to $24。

000。

![](img/ecf5115cb98944afb87c6c2f49c41280_17.png)

I click the go button to execute the query。The output results show that there are four employees who earn less than or equal to $24。

000 per year What if the employer wants to know which employees receive a salary that is greater than or equal to $24。

000 per year？

![](img/ecf5115cb98944afb87c6c2f49c41280_19.png)

To generate these results， I can use the greater than or equal to operator in my SQL statement。

 so I write the following SQL query， select asterisk from employee， where salary。

 greater than or equal to symbol 24000。This time， the greater than or equal to symbol is used to check whether the value stored in each field of the salary column is greater than or equal to $24。

000。I click go to execute the query and the output shows that there are three employees who earned $24。

000 or more per year。

![](img/ecf5115cb98944afb87c6c2f49c41280_21.png)

The final comparison operator available in SQL is a not equal to operator。



![](img/ecf5115cb98944afb87c6c2f49c41280_23.png)

In this final example， the employer wants to know which employees receive a salary that is not equal to 24。

000 per year， I can determine this using the following SQL code。

 select asterisk fromEmployee where salary。Then I type less than and the greater than symbols to denote the not equal to operation。

 and then I type 24，000。As with the previous operators。

 the SQL statement utilizes the operator to check the value stored in each field of the salary column。

In this case， it checks for values that do not equate to $24，000。



![](img/ecf5115cb98944afb87c6c2f49c41280_25.png)

The output results of this query show that there are three employees whose salaries are not equal to $24。

000 per year。

![](img/ecf5115cb98944afb87c6c2f49c41280_27.png)

You should now be able to describe comparison operators and use them in a database in SQL congratulations on building another important database skill。

