# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P77：13_GIN tsvector索引构建演示.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

So now we're going to get the payoff。 We're going to actually make a natural language in inverted index with Postgres and it's way simpler than everything I've done so far again。

 the key is you have to understand where the Ts vector works and how the Ts query works but once you understand what those do stemming stop wordss etc it's pretty straightforward and again I'm working from wwwpg3。

 co/ lectures/05 fulltext。sql So I don't know I might have to drop this table well drop the index。2。

And then we will recreate them。😔，did not exist。 So we'll create our documents。

 which again has just an ID in a document text field and then we're going to create a this is the critical one。

 we're going to create an index named Gin1 on the docs table using the gin and the index expression is2 TS vector English quotecom doc So that says take the document column run it through a TS vector with the English。



![](img/c96be75a2c46cb2f3ab69722e9e8bd85_1.png)

![](img/c96be75a2c46cb2f3ab69722e9e8bd85_2.png)

English dictionary。 and then give me a reverse index for everything that makes it through。

 Stop words， lowercase and stemming are all done。 So if you look at this。

 the earlier thing I did that was just strings was actually harder than doing a inverse index。

 So I'm just gonna run it。

![](img/c96be75a2c46cb2f3ab69722e9e8bd85_4.png)

And then I'm going to insert some rows， insert my three rows in there。

And then I'm going to insert some filler rows to make sure that Postgres nodes were serious。

 so I did the generaterate series， insert 10，001 rows of neon and some numbers。



![](img/c96be75a2c46cb2f3ab69722e9e8bd85_6.png)

And remember， it might take some time。It might take some time to get things to work so I can do a select ID doc from Docsware to TS query。

Is matched matches the2 Ts vector of English doc And again， look at the where clause and the indexed。

 the expression that's being indexed is to underscore Ts vector using English dictionary。

 the doc that is exactly the same as what's inside of the g expression right So we created the index that expression so we generally know that the kinds of things that are going to use the indexes are the ones that end like that。

 Now you can create more than you can create more than one index and you can create more than one index with more than one expression。

 you can do a lot of things with these things。But of course， the cost of the inserts and the queries。

 you know how much space the index is taking， how much cost for each invert index and let's go ahead and see if our index while I was talking blah。

 blah， blah blah， blah let's do a query explain just to see if it' if it's made it yet yep all the inserts in that time frame it was able to process 10001 documents and insert them So let's let's do something really I I don't know if it'll be interesting or not。

Probably not。So let's just try it。Let's just try its we're going off the script a little bit。

 so I got this C index Gin1。I'm going to drop index Genin1。So now it's gone。Oh yeah。Drop index Gen1。

Index is just data that the database has， so I can get rid of them。

 and now I'm going to do my explain。A way it goes。ok。So now I am going to create。

A just index that does the exact same thing。So I'm going to copy this line。

 create index Gen 1 on Docs。And the only change I'm going to do is'm on the using。

 I'm going to say using justest。Now， the thing about the gist is that it is and by the way。

 all those rows are still there， we still have 10004 rows in。 So the question is。

 how fast can a just just vector adjust。An inverted search tree。

 how fast can Postgres make one of those versus how fast it can make gin because the main advantage of gist is that it's easier and quicker to make and maintain and it's smaller。

 but you might have to retrieve a few more blocks of data so what I want to do is create the index and then see sort of how long it takes before the explain starts to work。

So the the explain instantly worked to see that as fast as I could type it， the gist was there。

 Now let's do it again， drop index。Jin1。Get rid of that one， now it's gone。

Now I'm going to make a Gin index。And we will see if we can catch it having not yet been indexed。

 So I just made it a gin the index expression is the same。

 gin and just both know this T S vector like perfectly。

 So I'm going to create it and then up then I'm going to do the explain select again。 boom， boom。

 boom， explain select。It was too fast for me， so I didn't get to show you。

It made the g really fast as well， but。I wish I could have showed you that the just happens faster than the gin。

 You get the same rose back because the gin takes care of all of that so。

It's really quite straightforward。 The goal is to get to the point where your explain doesn't do a sequential scan。

 That's all we're trying to do Okay， so I hope you found this useful cheers。



![](img/c96be75a2c46cb2f3ab69722e9e8bd85_8.png)