# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P31：2_日期数据类型处理.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/e881779dd8dff4fd64d4ee299e597e2b_0.png)

![](img/e881779dd8dff4fd64d4ee299e597e2b_1.png)

So dates are an important part of databases。 it's important to think about dates in two ways there's kind of like。

The date in the time are， I almost think of them as like string fields。

 If you're entering historical data and like what， what are the significant events of the Civil War in the United States。

 right？ And so， okay， this happened in 1862 and 63 and 64。

 those are like historical dates and no one's arguing， well。

 like what time zone or what time and day there were or and so date and time are just。

Things that you're reading and you're typing in and it's not time zone they're' they're sort of like what was written down at the time that something happened。

Whereas in computers， when we're doing things like you type in a blog post and you send it。

 and it says two hours ago later。 Well， that's what I call a win time， right。

 That's when did something happen。 And the key thing about the difference between a date and a time and a time stamp。

 which is more of a win concept， When did something happen concept。Is that。

the moment that I hit this key。Is a moment in time that is simultaneously the same moment in time in all the time zones of the world at the same time。

So if you start a meeting and you say， hello， everybody。

 that might be 5 o'clock in the East Coast United States。

 It might be 2 o'clock in a West Coast United States， and it might be 11 o'clock in。Inland。

And it's still the same moment， the same when。 And so we use timestamps。

 Now there's two kind of timestamps 1 I find almost useless。

 And then the other one is a timestamp with a time zone。 And they're both8 byte fields in Postgres。

 And for me， I just use timestamp Z all the time。 Now the interesting thing about timestamp Z is you can actually store a time zone in US Eastern time。

 And it knows， okay， this is1 o'clock at in the afternoon， US Eastern time。

 And then if you pull it out。 you can see it in US specific time or British standard time or whatever。

 And there is this Postgres SQl function most all databases generally have this function called now。

 which is within whatever time zone， it's at perhaps told to be in the universal time zone。

 which is of Greenwich Metime ish。 that is now。 And that's this moment in time right this minute。

And it has a time zone associated with it generally。

We tend to put in our databases lots of these timestamp Zs。 Now。

 other databases don't have this timestamp Z， but this is necessary in Postgres。

 And so the other thing that you'll notice is that we have this little bit of text called default now right。

 this not null default now。 And this is kind of like a constraint or unique key or whatever。

 We're talking in our schema definition， our create statement we are talking about what we want the database to do for us automatically。

 And so you'll， if you look at any database I created in the last 10 years。

 I always have a created at， which is either timestamp for some databases or timestamp Z in Postgres that has a automatically generated。

When you insert the row， put the current time in， Don't make me put that in every insert statement。

So I want I name it a particular way， and I give it the database an instruction as to how to prepopulate it。

 Now we'll talk about updated at some databases autopulate update。

 which means that when you do an update， you can mark a field as auto change to be now at now as the moment of update。

 but the way this works and the way in Postgres it works is that you cannot do that on a create statement。

 you have to store procedure， which we're going to talk about in a little bit later。 So in this one。

 both the created at and updated at are set to the current moment of the insert but updates do not alter update at。

 which is counterintuitive and other databases have easier ways to do this。

Timetamp with a time zone is the best practice， and it's not so much that all the timetamps have to be in the time zone。

 although the way I like to do it is I like to pick the UTC Univer time zone。

 I don't know when that is。Pick UTC， which is basically Greenwich mean， independent of timesome。

 So that is the time in Britain， but Britain also has standard daylight time and standard standard time。

 And so UTC is always the same。 It does not。 There's no such thing as standard time in daylight。

 Sams time for UTC。 And that's kind of the difference between。I think Greenwich meanan time。

 British time and UTC， even though they are sort of。

The same time zone So no matter where we're at in the world。

 we tend to use the British time zone for timestamps without daylight savings time。

And so the idea is， is then you can tell Postgres to convert to whatever time zone you want。

 And this is why if you've ever taken a plane flight and gone into a different time zone and you bring like Google Calar up and it says。

 do you want to see these times in Pacific or do you want to keep seeing them in Eastern because you were sitting like me putting all these events in your your calendar and Eastern time zone and then。

They want to show them in the Pacific。 And， and the worst thing， of course。

 is when you're in the Pacific Time zone and someone sends you email says。

 let's meet at 3 o'clock in the afternoon。 So you go in and youre you're putting it in the Pacific Time zone at 3 o'clock。

 and then you fly back home and you you say， what time is it like， oh， wait a sec。 It's noon。

 What's wrong with that， so。So ultimately in databases。

 because of this whole problem of an online application is working all over the world simultaneously quite often。

We do that， but then we can say， look， I want to know what time this was in the local time zone。

 so for each user you can give a different view， and that's where it says at time zoneone， UTC。

 ET or Hawaii standard Time or whatever。So there's a whole bunch of time zones if you look at the earlier versions of Postgres they were like。

Some 14 or so time zones， but they realize that that's actually not accurate。

Just take a look at time zones。 You'll be amazed at how complex time zones really are。

 Not all time zones。 And you see even one here， not all time zones are even hours or even numbers of hours。

 there's this Indian slash cocos is6 hours and 30 minutes away right and you'll see some that are 15 and 45 minutes and you're like。

 I bet it's tough to live in that area and set up a multi-person realtime conference and get it right because that just means that like your calendar goes off by 30 minutes right。

 if you get like。A calendar invite from a person in the US Eastern Time zone in your place is going to be on the hour。

 it's going to be on half hour， but so we're actually going to play with this data a little bit later just because it gives us a little bit of data。

The I the abbreviation is a away the commonly used thing like E S T for Eastern standard time or B S T for British standard time。

 I I S underscore is underscore D ST is whether or not this is daylight savings time or not in this little table。

 This is a common thing that databases do is they make these like sort of pseudo tables that they realize that they they could make a thing called。

What underscore time zones underscore are available or they could just make a fake table that you just use SQL statements to do。

 and that's kind of cool because now you can do things like wear clause in it。

Right so you sayQ is a good way to look at data， so let's just make a fake table with this stuff in it and when you install your Postgress。

 you might have to pick your time zones or you can add new time zones to it。

 And so this looking at this PG underscore time zone underscore names tells you what's going on in the particular database that you're working in。

So this is a good time to talk about casting。 So casting is a。I don't know where the word came from。

Casting is the idea in programming of taking a variable or a constant that's in one type and converting it to another type。

It might be converting from an integer to a string， et cetera。

 And so there are several syntactic ways that Postgres does casting。 So there's this double colon。

 which actually I think is a really pretty syntax that says now and now is giving you a time zone Z a time zone a timetamp with time zone。

 but turn that into a date。 so that effectively is truncating that part off。The cast function。

 So now as date as is a keyword， date is one of the predefined types。

 that is that is a more standard way to do it。 And it's kind of this this here is a contraction。

On that Okay， and then now as time just chops off the part that is the the time only。

 And so these are this think of this as a type conversion。

 So we're reviewing this through a date lens or reviewing this through a time lens。

We can also do date interval arithmetic， this interval itself is a keyword。

And it takes as a parameter， a little language， like two days，5 hours。

 And you can go look up what this interval language is。

 And so this basically a common thing that we want to do is like。What was two days ago， right？

 So this is now。 And this is now two days。 So you say it was June 10， and it was June 8， right。

 And you can also just cast this to a date。 So this is the date right up here。 This right here。

 now minus interval two days Col and colon date is casting two days ago into a date。I。e。

 throwing away the time part so we can do very stick date interval arithmetic。

There's also a function that's built in that allows us to， it's called truncating。

 it's allowing us to throw away some of the accuracy that's in a timest。

 like just chop it off at some level。 so I want to chop this off at the day。

 I want to chop it off at the hour at the minute， etc cetera。And so this is a simple thing that is。

 it's about simple thing， national simple thing， it's a little bit of a complex bit of code where we're trying to find comments that were done today。

And so what we're saying is created at is greater than equal today。

 which is if you take the current moment and you truncate it down to only be a day。There's a day。

 that's a day，6 June 10th。And if today is greater than or equal June 10th。

And created is less than or equal to day plus now plus one day， but truncated down to be only a day。

 That would be June。 This little bit here would be June 11。Okay， so， you know， how did I find this。

 I think I went to stackck Overflow， and I said。How to find things that happen today with a created a or something like that。

 So don don't feel bad about going to stack overflow on this stuff。

 I'm mostly giving you entry points into stack overflow。Now。

This is a topic that will be coming up a lot in this class and in the next class。

 and that is that not all queries that return the same results have the same performance。



![](img/e881779dd8dff4fd64d4ee299e597e2b_3.png)

And it， it。Has to do with the fact that sometimes。The way you express a query。

 the way it has to do is retrieve a lot of rows from the database and then look at every single one of those rows。

That's the slow way to do it。 And we call those things table scans。

 And so when we start looking at the performance， we can say， hey， take a look at this query。

 how' is it going to perform， And then they'll say that thing you did right there is going to call us a cause a full table scan。

 which means， oh， crap， we got to read all the data and use an if statement like a loop in an if statement to read all the records。

 That's the slowest way to do it。 And the problem with databases or' big and there's data spread all over。

 So reading all the records is often has some consequence in terms of performance。

And so the question is， is is there a way to make it so that I give it a where clause so that it's not reading all the records。

 A where clause where you don't read all records is where you have like a unique index on a string field。

 And you say where email equals C7um。 Eu there could easily be millions and millions of records。

 but there's an index that lets it go straight to C7um。 Eu。 So that's what I mean by that's a。

Not a full table scan。 That's like a1，2 I Oos， even for millions of records， okay。

And so I'm just bringing this up now because this particular way of doing business or this particular way of selecting the comments that happened today。

 you could say， let's take today and truncate it down to to date that's converting it to a date。

The date of creation is equal to the date of now。 Now， I can't really explain to you at this point。

 And this could be a fun stack over Phil thing for you to look up why this is a slow query。

And this is a fast query。I'll just say that at some point there's like something inside the data that it can take advantage of with date trunk that it can't take advantage of when you're doing the casting。

So it month， doesn't mean it couldn't in Postgres 14 learn to make this fast， right。

 That's the thing。Just because， I mean， there's just no， there's no rules。

 there's just the fact that this this version of this query is slower than this version of the query。

 And we'll talk about that more。 this particular one， you don't get to control much。

 you just kind of see that if you were to do the explain on this one。 you would see， oh。

 that causes a full table scan。 And this one does not cause a full table scan。 So I just。

 I'm bringing that up because。This will be sort of a running theme as we talk about some of the queries and say。

 yeah， this technique is better than this technique because one technique causes full table scan and the other technique does not。

 So up next， we're going to talk about distinct and group by where we're doing some something with duplicate values in the columns vertically。



![](img/e881779dd8dff4fd64d4ee299e597e2b_5.png)

![](img/e881779dd8dff4fd64d4ee299e597e2b_6.png)