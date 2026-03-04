# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P19：18_数据表构建实践.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/f7524e39959b93a07a9c3f9e66d6447a_0.png)

![](img/f7524e39959b93a07a9c3f9e66d6447a_1.png)

So now that we've come up with a way that we augment our logical model to make a physical data model。

 it's time to do some SQL and actually create these tables and put them together。

 Now if you're going to， you might have to create a whole new database and you do this with the super user depending on how we're having you do assignments。

 there might be slightly different instructions for this。

 but basically we're going to create a database。And the PG freeE account that we made before has a password。

 And so we'll create that。 but you might get slightly different instructions on your assignments。

 but at some point， we got to make a database。 And you' always notice that in this thing I'm running as the super user。

 the super user both the Postgres user， and then that's the one that creates database and PG freeE。

 that is a user who's not so super。 So once you have that database。

 the music database will'll make a connection to that database。

 and then we'll start typing SQL commands。 And so you've been doing create tables before。

 So you sort of know various things here。 you know， you're going to create a table。

 and then there's a series of columns that are in that table。

So the first thing we have is Postgres has a really nice way of indicating the column that's going to be the primary key and so there's it has this extension。

 So that's not in all databases the serial is a thing that basically communicates。

 I want a column named ID and I want it to be the primary key。 make it a number。

 give it to me automatically increment it。 It's a number that starts at 1，2，3，45，6。

7 and this also then added to that as primary key， tells it tells the database that we're going to be looking these things up fast and please make me an index on this a very fast index。

 and then logical key， we just add this word unique。

And so what unique basically is saying is that we're only going to allow one particular name。

 so ACDC can only have one row， so if you try to insert a row with ACDC。

The first one will work and the second one will blow up if it's still ACDC。

 And so that's also a way to communicate that there's supposed to be an index on this field because the database has to index that field so that when it is inserting the next ACDC。

 it can quickly decide whether or not ACDC is already there。

 but the very thing that lets it figure out that ACD is already there。

 makes it so it's pretty easy to look up ACD so So it has a quick way to find the row that belongs to ACDC And so we're going this is going to be these two lines here are going to be our pattern the serial and primary key or our pattern for the primary key and unique will be our basic pattern for string based logical keys。

So if we look at the album table， we see that we've got a primary key using that same pattern。

 this is once you've got these， you just like copy paste。

 copy paste and change a few things right and then we add the unique other there the typo there。

 don't worry about that。 that should be unique right there。

 And so we have a title which is our logical key， we say unique。

 which communicates And then we're putting in our first foreign key and remember foreign key is the thing that points from one to the other。

 The foreign key is at the beginning of the arrow。 So artist ID is a column iss an integer references says this references the ID field in the artist table and then ondelete cascade。

 So ondelete cascade is a way that basically says。If we have an artist table。And an album table。

And there's a bunch of rows in the album table， and they all point to one of the artists。

 if we delete the artist， then all the rows go away。

And that's because it knows we deleted one of these artists。

 It goes and finds all of the corresponding album entries and deletes them。

 So we cascade a delete from the artist table into the album table。

 And that's what on delete cascade means， okay。So the genre table。

 if you remember the picture of the genre table， the genre table just is something we're going to point at。

 So in a many to one， this is a one。 And so it just has a primary key。

 and it has a unique a unique logical key that is the name of the genre。

 and in the track is actually looks complex， but is really not that complex。 We have a primary key。

 We know how to do one of those things。 you make it serial and then indicate primary key down here。

 We make a logical key， but we're going to do this one a little bit different。 I'll show you a sec。

 These are just columns length rating account or just columns。

 and there are two foreign keys because if you remember in the track table。

 They point to an album table。 and it points to the genre table。

 And so we have a pointer album I D points to ondte cascades。 So that looks like normal foreign keys。

 and then the cool part about this one is the unique。 Now， in all these other ones。

 we said we're going to make this field unique。 But here。

Could have a track called moonlight that could be on lots of different albums。 And so actually。

 you can't make the title。Be unique。You can't say there's only one track in all of music do named Moonlight。

 because there's too many of them。 So we have this unique clause。

 And what we're saying is the combination of title and album I D must be unique。 And that is， okay。

 on any album， there can only be one moonlight track。 But on a different album。

 there can also be one。 And so there's unique clauses can be kind of constructed to make the most sense。

 because if you say unique on here， if you put it on that one。 Then it's going to be unique。

 There will be no。2 moonlights。 And you'd be like， that's not a very useful feature。

 So this here is a kind of special， unique to the combination of you title an album is what's unique in this particular situation。

Okay。So once we've built all these things， we can describe it and you can kind of see after you create that track。

 you see that it's got a integer pour key。 and that serial when you saw that serial thing。

 it's it's really not null default next valve blah bla， blah blah， blah。

 you could probably type all that stuff in。 but you could just say it's serial。

 unique key we're done。 So we have a unique constraint it tells us what kind of an index it's using。

 it's using a B tree index。 and here we go， the typographical area is not in this because the code actually works。

 So this is the foreign key references with our mark of on deletete cascade。

 So once you've created that table， you can ask Postgres。

 What did I just make and that's it's telling you what it just made。



![](img/f7524e39959b93a07a9c3f9e66d6447a_3.png)

So up next we're going to do some inserting of the data and you'll see how these foreign keys work together and how we connect those things to each other。



![](img/f7524e39959b93a07a9c3f9e66d6447a_5.png)

![](img/f7524e39959b93a07a9c3f9e66d6447a_6.png)