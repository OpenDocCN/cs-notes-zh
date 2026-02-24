# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P81：4_使用IN BETWEEN和LIKE逻辑运算符过滤数据.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

You might already be familiar with filtering data using the and and orR operators。

 or what if you need to perform more complex data filtering tasks。

 like filtering data based on a pattern？You can use more logical operators such as in between and like。

By the end of this video， you'll be able to identify the in between and like logical operators and explain how they're used。

 and explain how wild card characters can be used with logical operators to filter data。

Let's begin with a review of the in between and like operators。

The in operator lets you specify multiple values in the where clausets。

 the between operator selects values within a given range。These values can be numbers， text or dates。

 and the like operator is used the filter data based on pattern matching。

Let's look at the syntax for the in operator。The in operatortor requires slightly different syntax than a typical select filter statement。

After the wear clause， you must type the column name to which the in operator is applied。

You then need to add the in operator， and you must also include the set of values within parenthsesis。

If the specified columns value of a record matches with any value in the set。

 then that record will be included in the query result set of the select statement。

The in operator is like a shorthand for multiple ore conditions。

You also can use Not in to filter the opposite results of those you receive from the in operator。

Next， let's review theBetween operator。For theBetween operator。

 you must also specify the column name after the wear clauses。

TheBetween operator is then applied along with the two required values。

These two values mark the boundary of a range； In other words。

 they're the beginning and ending values of the range。

The operator then selects values within this given range。

 the values that can be used with the between operator include numbers， text and dates。

If the specified columns value of a record falls within the value range specified here。

 that record will be included in the query results set of the select statement。Finally。

 let's look at the like operator。The like operator is used to filter data based on pattern matching。

The operator is placed after the wear clause and specified column name。

A pattern to be matched against the column data is then added。

This pattern can be written using what I refer to as wild card characters。

The first of these is the percent sign， which represents zero， one or multiple characters。

The second is the underscore sign， which represents one single character。For example。

 a pattern could be written as G underscore， underscore percent sign， within a pair of single quotes。

As you've just discovered， each underscore represents one single character。

While the percent sign is zero， one or more characters。

So this pattern searches for values that start with the letter G and are at least three characters in length。

If the specified columns value of a record matches the given pattern。

 that record will be included in the query results set of the select statement。



![](img/17f5312976de33c06829c07d2ae93a86_1.png)

Let's look at a demonstration of these operators in the Lucy Srub database。

Looky Schhroub are performing a review of their accounts。

 they need to generate specific details on their customers and the purchases they've made。

They can complete this task by filtering data with the use of the in between and like logical operators。

In Lucy Shruub's database is a table calledCustomer purchasechases。

 this table contains the data Lucy Shub need to complete their queries。

The data is divided into the following four columns， customer ID， customer names， customer locations。

 and purchases， the value of each customer's individual purchase。First。

 Luc Shrub need to use the MySQL in operator in the wear clauses to identify customers from the location Hela County。

 who've made purchases of over $2，000。You might already be familiar with filtering data using the orR operator the in operator is like a form of shorthand for multiple orR conditions。

You can get the same result as the orR example by using the in operator。

To extract the required data using the in operator， write a basic select statement as follows。

Begin with select all data from the table customer purchases Next， type the where clause。

 then the first condition as follows， purchases column， the in operator and the figure of 2000。Then。

 within parenthses， specify the set of values separated by a comma。

 Hela County and Santa Cruz County。When run， this query returns three records or customers。

These are the same results as the orR operator returns。

Now let's check out how the MySQl between operator functions in the where clauses。In this example。

 Lucky Sub need the details of customers whose purchases are in the range of $1，000 and$2，000。

Write the select statement as before， then add the where clauses。

The wear clause is followed by the filter column， which is purchases。

Then add the between operator and give the value range。

The range begins with the value 1000 followed by ant。Then ends with the value of 2000。

TheBetween operator filters out the records that have a purchase value between $1，000 and $2，000。

 including the beginning and end values。In this case。

 theBetween operator is a quicker and easier way to filter out the records that have a purchase's value greater than or equal to $1。

000 and less than or equal to $2，000。Finally， let's see how Luc Sub make use of the MySQL like operator。

The like operator is used for pattern matching when used in aware clause it search as a column for the given pattern；

 this means that it filters out data from the table based on the pattern。

It's often used in conjunction with wild cards for single or multiple characters。

Let's demonstrate an example using the pattern on the location column。

You can filter out the records that have a location value that matches the pattern。

Ly Sub's pattern must be set to find any values that start with G and are at least three characters in length。

First， write the select statement just as you've done before。

Then add the where clause followed by the name of the filter column location。Finally。

 add the like operator followed by the pattern， which in this example is G。

 followed by two underscore characters and a percentage symbol。Press enterter to execute the query。

The output that's generated contains three values that start with G and are at least three characters in length。



![](img/17f5312976de33c06829c07d2ae93a86_3.png)

Any values that don't match the pattern have been omitted from the table。

Looky Shroub have completed their data filtering tasks and returned all the required results from their database。

You should now be able to combine conditions and filter data using the in between and like logical operators great work。

