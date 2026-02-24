# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P82：14_MySQL函数快速回顾.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

There are many different types of tasks that you need to perform when working with a Mysql database。

 Funs are a great way to store the syntax that you need for these tasks as reusable blocks of code。

These code blocks mean that you don't have to retype your code each time you need to use it。

Over the next few minutes， you'll recap the basics of functions and learn how they are used with Python。

Little Lemon's MysqL database holds a lot of data on different aspects of the company。

 like customer behavior and sales revenue。Little lemon can use functions to perform specific operations on their database and return results。

 They can then use the data from these results to improve the restaurant's performance。

 So let's quickly recap the basics of MysQl functions。😊。



![](img/af3829321c6d205dffd64f677d896ea0_1.png)

As you probably already know， a MysQL function is a piece of code that performs a specific operation and returns a result。

 In other words， it's a task that combines a set of instructions and produces results in the form of an output。

😊。

![](img/af3829321c6d205dffd64f677d896ea0_3.png)

Mysql functions provide a lot of advantages for database engineers。 Some Mysql functions。

 accept parameters or arguments， While others don't。

 They're great for manipulating data in a database。

 You can also create custom functions that combine several tasks in a block of code。

 You can then store these functions within your database and invoke them when needed。

 And as you've just discovered， Mysql functions are reusable。

 so they can be used to complete repeat tasks。😊。

![](img/af3829321c6d205dffd64f677d896ea0_5.png)

![](img/af3829321c6d205dffd64f677d896ea0_6.png)

![](img/af3829321c6d205dffd64f677d896ea0_7.png)

![](img/af3829321c6d205dffd64f677d896ea0_8.png)

![](img/af3829321c6d205dffd64f677d896ea0_9.png)

At this stage of your database engineering journey。

 you've probably made use of many different types of functions。

The most common built in functions available in MysQqL include string functions。

 numeric functions and date and time functions。There's also comparison and control flow functions。



![](img/af3829321c6d205dffd64f677d896ea0_11.png)

Let's take a moment to recap the basics of these different types of functions and look at how little lemon can make use of them。

Let's begin with string functions。These functions are used to manipulate string values。

 like adding strings together or extracting a segment of a string。



![](img/af3829321c6d205dffd64f677d896ea0_13.png)

An example of a string function is Concat。 Concat combines data from two separate tables into one string。



![](img/af3829321c6d205dffd64f677d896ea0_15.png)

Little Lemon can use a Conca string query function on their database records to extract information on each customer like how much money they spent。

😊。

![](img/af3829321c6d205dffd64f677d896ea0_17.png)

You can also use numeric functions in MysQL。 Numeric functions include aggregate and math functions。

 These functions are used to carry out common tasks on numeric dataset sets。



![](img/af3829321c6d205dffd64f677d896ea0_19.png)

![](img/af3829321c6d205dffd64f677d896ea0_20.png)

For example， little lemon can use the average numeric function to determine the average dollar amount that each customer spends with the business。

😊。

![](img/af3829321c6d205dffd64f677d896ea0_22.png)

![](img/af3829321c6d205dffd64f677d896ea0_23.png)

Another example of MysQL functions includes date and time functions。

Date and time functions can be used to query a MysQL database to extract date and time values in a range of different formats。

 depending on the query。

![](img/af3829321c6d205dffd64f677d896ea0_25.png)

Over at Little Le， they often extract date and time data to analyze the behavior of their customers。

They can use this data to find out how long guests spend at the restaurant and which days are the busiest。



![](img/af3829321c6d205dffd64f677d896ea0_27.png)

Next up is comparison functions。 You can use these functions to compare values within a database。

 and they can be used with many different types of values， like numerical strings and characters。



![](img/af3829321c6d205dffd64f677d896ea0_29.png)

![](img/af3829321c6d205dffd64f677d896ea0_30.png)

Little lemon make use of comparison functions to identify the best and lowest selling items on their menu by using greatest and least comparison functions on their sales data。

😊。

![](img/af3829321c6d205dffd64f677d896ea0_32.png)

And finally， there's control flow functions。Control flow functions are used to evaluate conditions and to determine the execution path or flow of a query。



![](img/af3829321c6d205dffd64f677d896ea0_34.png)

For example， as you learned previously， the case function runs through a set of conditions within a case block。

It then returns a value once a condition is mesh or a null value if no conditions are mesh。



![](img/af3829321c6d205dffd64f677d896ea0_36.png)

Little lemon often rely on control flow functions to determine which items on their menu are loss making and which items have turned to profit。



![](img/af3829321c6d205dffd64f677d896ea0_38.png)

Now that you've reappped the different functions available in MySQL。

 let's find out how they work with Python。Let's take the example of numeric functions and see how little lemon calculate the mean or average bill for each customer。

They can create a select query that uses the average function to determine the average bill amount。



![](img/af3829321c6d205dffd64f677d896ea0_40.png)

This query is passed to the database， to be executed。Once the query is executed。

 little Le can access the results and see the average dollar amount each client spent with the business。



![](img/af3829321c6d205dffd64f677d896ea0_42.png)

![](img/af3829321c6d205dffd64f677d896ea0_43.png)

This is just a basic recap of My SQL functions and a short demonstration of how they work in Python。

The rest of this lesson will explore methods for accessing MysQL functions using Python in more detail。

I'm looking forward to exploring this topic in more detail with you。😊。

