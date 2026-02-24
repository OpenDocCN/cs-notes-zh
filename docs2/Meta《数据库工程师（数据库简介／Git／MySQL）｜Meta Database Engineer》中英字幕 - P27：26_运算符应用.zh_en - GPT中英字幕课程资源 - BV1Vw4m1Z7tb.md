# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P27：26_运算符应用.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

So far， you have learned how to use SQL arithmetic operators to perform basic functions。

In this video， you'll take one step further by learning how to use these arithmetic operators in practice when working with a database。

Let's explore the use of arithmetic operators using the example of a corporate table of employee data。

It's populated with the following information about each employee， ID， name and salary。

I'm going to demonstrate how to use each of the arithmetic operators in SQL to perform various functions with this practical data and retrieve the desired results。

In this first example， let's say that an employer wants to give each employee on their team a $500 bonus。

But first， they'd like to see what each employee's salary looks like after adding the $500。

I can type， select。Salary。Plus。500。From。Employ。To add the $500 bonus to each employee's salary。

This select command works by retrieving the salary of each employee from the employee table and then adding $500 to each value。

Let's execute the query by clicking the Go button。The result is that each employee's salary has increased by 500。

You can create other statements that use the select command in a similar way。For example。

Let's say the employer wants to deduct $500 from the salary of each employee。To do this。

 I typed the SQL query statement。Select salary minus 500 from employee。Again。

 I'm using the select command to retrieve the salary value of each employee record stored in the employee table。

This time， I used a subtraction sign minus to subtract $500 from the salary of each employee。

Now I click the go button。And the database returns a table that shows the output result of salaries after the deductions。

In the next example， let's imagine a scenario where the employer would like to increase the employee's salaries by doubling their current annual salary。

To do this， I use the select command to perform the same function as discussed previously。

I then use the multiplication sign， an asterisk symbol。

To multiply the salary value of each employee by two。So the SQL statement now reads，Se salary。

 asterisk2 from employee。I can now click the Go button to generate an output of the results of salaries from multiplying the values by two。

Now let's suppose the employer needs to determine the monthly salary of each employee。

I can perform this task using an SQL query statement as I have done in the previous scenarios。

However， this time I'll divide the annual salary by 12 months。To determine the monthly salary。

 my statement reads as follow。Select。Salary。Forward slash。12。From employee。

The Select command retrieves the salary value for each employee stored in the employee table。

Then division sign or the forward slash divides the annual salary value by 12。

So I click the go button to generate the output results。

The employer can now use this output result to determine what each employee's monthly salary is。

In our final example， the employer would like to know if the ID of each employee is an even or odd number。

I can use the modulus operator to complete this task。I just need to type the following statement。

Select ID。Modulus 2。From employee。I then clickGo to execute the statement。

This divides each employee ID by2 and returns the remainder of the division operation。In this case。

 a remainder of 0 denotes an even I D， as all even numbers are divisible by2。

 meaning there will be no remainder。The result shows that there are three odd IDs and two even IDs。



![](img/5341c65cdf28140a36b8f554fa89b5ce_1.png)

You should now know how to make use of the SQL arithmetic operators in a database。



![](img/5341c65cdf28140a36b8f554fa89b5ce_3.png)

You're making great progress。 Keep it up。