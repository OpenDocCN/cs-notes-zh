# SAS【中英⚡SAS高级程序员 专项课程｜SAS Advanced Programmer Professional Certificate】 p20 P20 11_使用 CASE 表达式按条件赋值 -BV1Cfe3z3EoA_p20-

Suppose we want to create a new column marriedri category based on the married status Emma is for married。

 S is for single， D is for divorced， W is for widowed， and anything else is unknown。

And we want a category column based on a range of credit score values if the numeric value of credit score falls within a specific range。

 the new column will contain the value of that category。



![](img/0325388e5817ad7df7666372c267a8f6_1.png)

You can use conditional logic within a query by using a case expression in the select clause to conditionally assign a value。

You can use a case expression anywhere that you can use a column name。



![](img/0325388e5817ad7df7666372c267a8f6_3.png)

Let's start with the standard form case expression or simple case expression。With this syntax。

 you can use a quality and non equality test for validity。In this example。

 the case expression determines the category for each customer based on the value in the credit score column in the customer table。

So in the first when then clause， when credit score is greater than or equal to 750。

 the category value will be excellent。The keyword endcloses a case expression and optionally assigns an alias category to the column。

The first when clause evaluated is true determines which value the case expression returns。

Subsequent when clauses are not evaluated。The optional else expression provides an alternate action if none of the when expressions are true。

If no else expression is present and every when condition is false。

 the case expression returns a missing value。

![](img/0325388e5817ad7df7666372c267a8f6_5.png)

You can also construct a case expression by using the case operaran form。

You specify the condition as the case opera once at the top of the case expression。

 followed by a series of when then clauses。Here we select the married column and based on the values we assign them to a specified category。

When you use the case operahand form of a case expression， the conditions must all be equality tests。

 that is they cannot use comparison operators or other types of operators。



![](img/0325388e5817ad7df7666372c267a8f6_7.png)