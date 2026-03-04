# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P43：14_文件读取与解析演示.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/a590137fe2f0d31afe3f9127fcdbad81_0.png)

![](img/a590137fe2f0d31afe3f9127fcdbad81_1.png)

So now I'm going to show you just a bit of a demo。 Now， I'm not going to do this demo here。

 I'm going to make a separate screen recording because I like to give you screen recordings for things where I want you to follow along。

But basically， if you recall in a previous assignment previous lecture。

 the thing we did was we made a database and we were getting rid of vertical replication。

 Ver replication teamss coming back right So here we got some vertical replication。

 you know just you know two things like make and model or whatever it is。

 We got some vertical replication。 So we're going to end up with a little table that is our lookup table here。

 That is this second thing that says， you know B is one。

 and then we could end up with numbers like know foreign key into this table。

 why underscore Id and we're going to put these in right so that so I could I could give you as an assignment。

 you know， take this data， make two tables and one as a foreign key into the other and put the second column in。

And just put the distinct values。 sound familiar。 Just put the distinct values in of that second column into here。

 That's what I want you to do。 And I want you to do it by hand。

So what we're going to do in this particular thing is we're going to automate it。



![](img/a590137fe2f0d31afe3f9127fcdbad81_3.png)

And we're going to make it so that you you could really take any and it doesn't just take two tables。

 you could extend this to be more than one table， I mean more than two tables。

But it's going to auto generate these things。 and we're going to use things like distinct。

 We're going to use things like subse。And I'll talk about it when I talk about it。 I was like。

 see how we're using the subselect。 Yes， if this was an online application， it would matter。

 but it doesn't。 we're using kind of this batch job that's taken this CSv file and turning it into a set of normalized tables And so the key thing is this might not be using the best techniques for online applications。

 But this is the best technique for the convenience of getting a nicely normalized database out of a non-normalized CSv file。

 So I'll go over this and show it to you in some detail。

 and it will use most of the ideas that we talked about in this set of lectures。 So in summary。

 a lot of what we talked about in this set of lectures is the select statement and select is often the last thing I talked about because create read create update and delete or like you know they're the big ones in select oh yeah。

 that's how you check to make sure those other ones work。 But it turns out， as I said before。

 the select is where a lot of this relational power matters。The select like narrows your view。

 which increases performance。 then this whole distinct thing happens。

 And so if you go and you look at the documentation on Postgres。

 you will see that literally we have only talked about almost half of what select does。

 And there's so much more than it does。 And again， the select that looking at this。Suff。

In the database， after you've done all this normal and all this optimization。

 how you ask to look at it is super critical and super amazing。

 But we've done a pretty good job at this point covering a lot of the different things that select is capable of doing。

 So up next， we're going to talk in the next set of lectures。

 we're going to talk more about text data。 talk a little bit about text data in that demo that I'm going to show you in a bit。

 And but we'll talk a lot more about text data in SQl coming up next。😊。



![](img/a590137fe2f0d31afe3f9127fcdbad81_5.png)