# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P31：30_SELECT DISTINCT子句.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Suppose you have a database that contains the records of college students from all over the world。

As part of an annual report， a list of all the different countries these students belong to is required。

😊，It's very likely many students will come from the same country。

 so how can you retrieve the results you're looking for without any duplicates？

Look no further than the select distinct clause。In the next few minutes。

 you'll learn how to describe the select distinct statement and explain what it's used for。

 demonstrate how to use it in a SQL query， and explain how it interacts with a single column。

 multiple columns， and null values in a few practical examples。



![](img/d1295a062cc7ba0dbd72e40e657bcf73_1.png)

Let's start by exploring what the selectedisting statement is。In its most basic form， distinct。

 as its name states，re only distinct or different values。In other words。

 it returns the results without any duplicates。

![](img/d1295a062cc7ba0dbd72e40e657bcf73_3.png)

Let's take a closer look at duplicate values。As you can imagine。

 columns in a table can often contain duplicate values In a college's student records， for example。

 the country column will likely contain duplicate values as there can be many students who are from the same country。

 let's assume you want to find out which countries the students in the college are from so that you can get an understanding of which nationalities are represented in the college。



![](img/d1295a062cc7ba0dbd72e40e657bcf73_5.png)

![](img/d1295a062cc7ba0dbd72e40e657bcf73_6.png)

You can begin by using a SQL select statement， you can write the select keyword， then country。

 followed by the Fr keyword and the student table name running this select query gives you seven records as the result with multiple duplicate records。



![](img/d1295a062cc7ba0dbd72e40e657bcf73_8.png)

![](img/d1295a062cc7ba0dbd72e40e657bcf73_9.png)

In this case， there are duplicate records for Australia and the USA。

So how can you eliminate these duplicates and retrieve a unique set of results。

 you can use the select distinct statement。You can write a select dateton just like before。

 but this time add distinct after the word select。The word distinct will return all unique values in the table with no duplicates。

You can then write the Fr keyword followed by the student table name。



![](img/d1295a062cc7ba0dbd72e40e657bcf73_11.png)

Once you run this statement， the countries now only appear once in the resulting records。



![](img/d1295a062cc7ba0dbd72e40e657bcf73_13.png)

All the duplicates have been removed。This is how the select distinct statement can be used to return distinct values from one column in this case。

 you've returned distinct values from the country column。Now。

Let's take a few moments to explore the selecteding statement in action。

The examples that follow focus on the select distincting statement with the use of multiple columns or when applied to a column that has a null value。

With the student table in this example， I want to write a query to determine which countries are represented by students in different faculties。

I can use a select distinct statement as before， but this time I lie the word faculty before country。

😊。

![](img/d1295a062cc7ba0dbd72e40e657bcf73_15.png)

Running this statement produces six records The science faculty is students from three different countries。

 as does the engineering faculty。So with this statement which uses multiple columns。

 I've generated each unique faculty and country combination。Now。

 let's return to the table once more and examine how select this st deals with null values and columns。



![](img/d1295a062cc7ba0dbd72e40e657bcf73_17.png)

In this example， I have a new student named Juli Smith from the USA。

She's not yet been assigned a faculty or school address。As a result。

 both fields within these columns assigned to Julia Smith contain a value of null。

 so let's see what happens when I run the same select distinct statement as a previous example。

How does it handle the null values in other words？What results does it return for Julia？

I select go and receive the same result as the last time。



![](img/d1295a062cc7ba0dbd72e40e657bcf73_19.png)

But now there's also a record for Julia with a null faculty value and USA as the country。

 this is because the distinct clause considers null to be a unique value。

So it outputs Null and USA as a unique faculty and country combination。



![](img/d1295a062cc7ba0dbd72e40e657bcf73_21.png)

In this video， you learn how to use the select distinct statement to eliminate duplicate values in a select query result。

You also observed how it behaves in response to values in a single column and multiple columns and to null values in columns。

Great work。