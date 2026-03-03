# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P86：22_PostgreSQL搜索结果排序技术.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

So now we're going to talk about how we rank the results， you don't have to rank the results。

 but you may want to and with Googling other search engines there is kind of an expectation that if you do a search that the most relevant results will appear first and so there's a series of ranking functions inside a Postgress that help you do that now。

It's important to see that the rank is generally in the select， the select part。

 not the where clause， the where clause is which rows that dominates the cost of queries。

 calculating the rank。That's actually really cheap。

And and yeah you're going to do an order buy in this one you're going order by rank descending but once you have the rows。

 if you have a million rows and you pulled 300 out ranking them。

 that's cheap even if there's an order buy and you have to pick like 20 of the 300 as you're paging through maybe don't worry the order buy is the cheap part about it going from a million rows to 30 that's the expensive part and that going from a million rows to 30 is where the index saves us so the index is not all that important for the ranking because if you're going to do a ranking on every record the fact that you're reading every record is actually the problem okay that's the real problem then so you don't want to read every record you want to index to save you from reading every record we have a where clause in in the where clause we have a TS query and a TS vector the TS query is personal and learning and we're just going to check the body of this document we're using our email messages in this particular one。

And that's the where clause it works and then in the select clause in the select clause you see the computation that happens and it is taking the vector and the query and it's simply looking at how close they are it's not picking rows。

 it's just I've got rows here's a vector coming from the row and here's a query that I used how close are they and so that's it。

 you can order by like I said the number of rows that are going to be sorted in the order by or hopefully small because the where clauses did its job and so we get some ranking and I had them in descending order there from zero through one and there are two different and you can read up on these there are two different ranking functions but really all they are is a different calculation with the same data and there's some theory and some paper and someone says I think this is a better ranking function。

 somebody says this is a better ranking function， you can write your own ranking functions if you want and it just ends up with the ranking。

And so the ranking was really kind of an afterthought because the hard part was getting the roses that you wanted to get and a away you go and so I'll just close by talking about how impressed I am by Postgrees。

Depth of capabilities when it comes to。

![](img/54d3b64662c845754e6a152323975103_1.png)

Indexes， I've got this select statement， select AM name etc here。

 I got this off I got this off post of a stack overflow。

 but it's a lot of rows it's 159 rows and what it's showing is the different kinds of indexes that you can do in the different kinds of operations if you're call we did the string index we had to tell it we wanted to do text operations and that's because there is code that somebody wrote inside Postgress that knows the difference between a text array comparison and an integer array comparison and it's optimized and that's because how you compared text and integers are quite different at the lowest of levels。



![](img/54d3b64662c845754e6a152323975103_3.png)

![](img/54d3b64662c845754e6a152323975103_4.png)

And so I just type this command and get these 159 rows back just。

To be amazed at just how much work goes into not only just GenX indexes， but the Bree， brand and ash。

 all these indexes and how much work these Postgres folks have put into to this software to make our job easier as those of us who have to look through this data to write applications to make use of this data。

