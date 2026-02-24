# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P30：29_WHERE子句.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

An admin department at the university wants to create different reports for students in the engineering faculty。

The department needs to filter out students from the engineering faculty to retrieve their details from the student database。

So how can this be done with SQL Well， the wear clause is useful in scenarios like this？

In this video， you'll learn how to explain the purpose of the wear clothess。

Demonstrate how to filter data using the wear clauses and make use of different operators in the wear clauses condition。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_1.png)

So what is the wearclo？The wear clause is used to filter data， more specifically。

 it is used to filter and extract records that satisfy a specified condition。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_3.png)

To better understand how the wear clause is used， it may help to break down its syntax in a SQL select statement。

The syntax begins with a standard SQL select statement， followed by the columns you want to query。

Next is the Fr clause followed by the table name。Then you can bring in the wearclos。

After the wear clause， you can specify condition。

![](img/490640bfbef7d8c69f6bd5911d2f3ec5_5.png)

You may be wondering what the purpose of the condition is。Well。

 the condition makes it possible to filter out and fetch the required records from the table。

You can think of the conditions as filter criteria。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_7.png)

Only the records that meet the condition will be retrieved。For example。

 you can use the condition or filter criteria to check if the desired column name is equal to a certain value or upper end。

In between the column and value， you can place an operator。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_9.png)

As you've just discovered， the opera followed the operator。

Let's take a quick look at it in more detail。The operaran can be either a text value or a numeric value；

 it all depends on the data type of the table column or field。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_11.png)

To demonstrate。Let's take an example where student ID equals 01。In this case。

 the condition is instructed to filter a numeric value， so it functions as a filter criteria。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_13.png)

Once you run the SQL select statement， it retrieves the records as instructed。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_15.png)

Let's take another example， where first name equals John， a text value。

All text values must be enclosed in a pair of single quotes。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_17.png)

Once again， you just run the SQL select statement and filters the required records。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_19.png)

To specify your filter condition， you can make use of a wide range of operators。

You've just reviewed an example of the Es operator and others you may have encountered in a previous lesson。

Let's quickly review these other operators。SQL comparison operators include equal2。

Less than and greater than。There is also less than or equal to。

 greater than or equal to and not equal to。

![](img/490640bfbef7d8c69f6bd5911d2f3ec5_21.png)

In addition to these symbols， the wear clauses can also use the between， like， and in operators。

With theBetween operator， you can filter records within a specific numeric or time and date range。

The like operator is used to specify a pattern in the wire clause filter criteria。

And the in operator is used to specify multiple possible values for column。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_23.png)

Now， let's explore some examples of the wear clauses in select statements。

Recall the scenario of the admin department that wants to create reports for its engineering and science students。

I can use the wear clauses to filter out the details of students who are in the engineering faculty。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_25.png)

In this case， I need to retrieve all details or all columns from the student table。

 so I write select。Asis from student table。Next， I type where， followed by the filter criteria。

The criteria is written as faculty， then an equal operator。Finally。

 I write engineering enclosed in single quotes， which are required for text values or operas。

So I'm instructing my SQel to fetch only the details of the students who are attached to the engineering faculty。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_27.png)

Then I run the query。

![](img/490640bfbef7d8c69f6bd5911d2f3ec5_29.png)

As per the filter condition， does retrieve the student records of the three students in the student table listed in the engineering faculty。

Note that I could have used other operators such as greater than， less than less than or equal to。

 greater than or equal to， and not equal in the same way as the equal to operator in this wear clause condition。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_31.png)

You can use any of these operators with numeric values or operas。

Now let's review some examples that use between， like and in operators in the wear claw condition。

The college is a financial aid program available to students of a certain age。

 the funding department would like to notify eligible students only。

I can use the between operator in the wear clause condition to filter the records in the student table。

As before， I type select asterisk from student table， followed by where。After the wear keyword。

 I specify the filter column as DOB or date of birth。Then I insert the between operator。Lastly。

 I give the date range as 1s of January 2010 and 30th of June 2010。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_33.png)

Running this query retrieves the records of four students whose date of birth falls in the specified date range。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_35.png)

Note that I could use any numeric range here， not just dates。For the next example。

 let's assume the admin department requires the details of the students who are in the science faculty。

I can do this with the like operator， which can be used when you want to specify a pattern in the wear cloud filter criteria。

Within the select statement and after the where keyword， I type facultyy for faculty column。

 then the like operator， followed by SC percentage sign within single quotes。

The percentage character in the pattern is a wild card character that represents zero。

 one or multiple characters。The underscore sign can also be used to represent one single character。

In this case， my wear clause asks My SQL to search for and filtererate values within the faculty column that start with SC C。

 followed by any number of characters。So I run the statement and it filters out the five student records whose faculty column has a value of science。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_37.png)

That is starting with the pattern SC。In the final example。

 the admin department needs to know the details of the students who are studying in specific locations。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_39.png)

![](img/490640bfbef7d8c69f6bd5911d2f3ec5_40.png)

You can use the in operator in the where condition to retrieve the relevant student records。Remember。

 the in operator is used to specify multiple possible values for column。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_42.png)

Within the select statement and following the where keyword， I type the column name。

 which is country， the in operator。

![](img/490640bfbef7d8c69f6bd5911d2f3ec5_44.png)

Then an open pair of parentheses。Within these， I placed the values USA in UK each in single quotes。

My select query will filter out all student records that have a value of USA or UK in the country column。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_46.png)

Running this query returns four records， two students from the USA and two students from the UK。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_48.png)

So the in operator searches for multiple possible values in the country column and filters out based on them。

Note that although the examples in this video looked at the wear clause in the select statement。

 it can also be used in other statements， such as update and delete。



![](img/490640bfbef7d8c69f6bd5911d2f3ec5_50.png)

You've now learned what the wear clauses。And you should now know how to use it to filter data as well as how to use different operators。

Great work。