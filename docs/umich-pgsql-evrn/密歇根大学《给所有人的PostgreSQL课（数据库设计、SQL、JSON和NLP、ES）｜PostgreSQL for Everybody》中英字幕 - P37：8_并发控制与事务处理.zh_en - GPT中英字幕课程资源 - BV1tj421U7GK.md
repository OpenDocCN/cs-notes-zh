# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P37：8_并发控制与事务处理.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/8ff4a19d46c65b044a7dc8eb1bebb424_0.png)

![](img/8ff4a19d46c65b044a7dc8eb1bebb424_1.png)

So now we're going to talk about concurrency concurrency。Makes the most sense in an online system。

 and like I said， data mining doesn't always work with an online system。

 Sometimes data mining is working on an online system， but concurrency is an important concept。

 and I just sort of want to bring you you bring you up to sort of basic understanding concurrency if we're teaching sort of an online gaming how to use databases in online gaming or something。

 this would be an essential part of it。 we'd spend a lot more time with it。So databases in general。

Are designed to be multius， right？ You got a database back here。 and you got， you know。

100 simultaneous logged in users。 And they're like adding one or subtracting one or updating their bank balance。

 And it's kind of like if database sees this flow of continuous transactions coming in。

 And the key the database has to solve is atomically。 So in this case， we've got simultaneously。

 we're going to receive three update statements that are going to set count equals count plus one。

 for a row number 42。And now all we need to know， we don't necessarily know which one of these is going to go first。

 but we know that after all three are done， it's got to be 103。

And the place that it might not be 103 is is what if what it did was the first one retrieved the old value。

 The second one retrieved the old value， and the third one retrieved the old value。

 and they would all have 100。 They would all add one to it。 And they all store the new value。

 and they would all store 101。 So you had three attempts to add one to it。

 But the number turn went from 100 to 101 instead of 103。So that's the problem， the problem is is。

We don't know which one actually has to go first， but at the end， all three have to happen。

 which means that the database has to enforce a rule， here comes an update。If there is two updates。

 they got to go in some order， but they can't go at the same time。 That's the concurrency。

 bet they can't be at the same time。And that's the atomic bit。

 So the read and the right of the value count has got to happen atomically before the read and the right of the value count for the next transaction。

 So that's got to be atomic okay。So the way this really works is there is a locking mechanism inside these databases and the better the database。

 the better the locking mechanism， because if you're doing a lot of locking in a database。

 then actually the lock effort is often greater than the cost of just reading and writing the data。

And so when Postgres says， you know， we're really awesome， or Oracle says we're really awesome。

The granularity of the locks and the performance of the locks and the amount of memory that takes to do locking。

As your database size grows， that's like a competitive strategy。

 competitive advantage to be good at locking to because this atomity， the atomness。

 the ability to do things atomically is such an essential feature of a relational database。

So the pattern is really simple。What you basically do is you， you know。

 if you're going to update something， you got to first lock it， then you can read it。

 then you can add one to it， then you can write the new value， and then you unlock it。

 And if two things go to the lock， hit them at the same time。

 one gets the lock and the other one has to wait。And then the when they gets the lock gets to completely work。

 and this one's still waiting。 And then when this one unlocks it， then this one gets to come in。

 But then they're going to see 102。Right so it's。You know， locke。Read 100， add 1， store 1，01， unlock。

 read1，01， right， So that's how you guarantee that if there are three coming at the same time。

 it goes from 10 to 1003， rather 100 to1001。And so each of the SQL statements that we send are atomic。

 and it's not just update statements。 insertser statements are also atomic。

 and we use a serial type column like I D in all these tables that we're building。

We're basically saying， I want a unique number。 You can have three simultaneous inserts happening。

 Sa know what， you're all key number one。 and the next insert' is going to be 4。

 We do know that we got four three records。No， one of these has to be one。

 and the next one has to be2， and the next one has to be3。 We don't know which one gets which。

 And so that so even when their insert statements， they somehow have to line up behind each other。

At least in the ID and unique key generation， the primary key generation。

 they've got to line up behind each other so that they get a unique thing right。

 but you can't say who got there first because they arrived at the same time。

 but the database will force an ordering on them and key the next one will be four。

These three will be one through three， but in some random order。So， because。Each statement。 And。

 and when I say a statement， what I really mean is a bunch of stuff that ends in a semicolon， right。

 so so。So this is like an insert， bh， bh， blah， blah， blah， semicolon。

So there are things that sort of extend one statement to do two things in one statement， right。

 So more than one thing in one statement。Fficiiency and concurrency。

 So one of the things you can do is you can do an insert and then add this little kind of like。

Extra little things is a， you inserted all those things into the thing， including the primary key。

 which is the I D that you generated and give it back to me。

 And then this becomes one atomic statement。 and your code gets back。The numbers。

 including the automatically assigned I D。And the same thing is here。

 So if you say I want to add one to this。Set how much equals how much plus 1 where post ID equals 1 and account ID equals1。

What value was it afterwards， How many were there， Like。

 you might be clicking a button like this that makes something go up。 And then what's the new number。

 What if two people and two screens are clicking that same button， It shouldn't be 80。

 It should be 81。So you can basically click this button， and it will send add one to it and say。

 what's the resulting number。 And the answer will be0，81。

 because other people are clicking at the exact same time。

 And so that's what this is saying is add one to it。And then afterwards， give me that record back。

 the updated record。Cool， so that's another taking advantage of this concurrency and the atomic nature of each SQL statement by adding stuff to the same SQL statement。

This doesn can't just keep doing this forever。 This returning is a feature that we use and we use a lot。

So the next thing that you do is sometimes you make a constraint and with the intention that you're going to bump into the constraint and then tell it what to do when it bumps into the constraint。

You can almost think of this as like a try and accept in Python where you say like try this。

 if it works just great if it doesn't do this other thing。So if we inserted a record。

 this record here， and then we tried to do the insert again， it would actually fail， right？

And so sometimes the record exists because a unique constraint on post ID and account ID because the insert that's already there。

 that combination of 11 is already in the database。Because of this insert。

Now this one here is going to fail。And so it's just going to blow up。

But it turns out that what you can do is you can say， I would like to insert this stuff。

So a lot of my updates turn into inserts。And then on conflict。

 And so what this is saying is if this insert would fail because of the unique key constraint of post I D and account。

 I D don't blow up。 But instead， this is like。This is like the try accept。Instead。

 add one to the thing that's there。 Add one to that How much value。 Okay。

 set how much equals fd out how much plus1。 So that's like try and accept this update doesn't trigger unless this is true。

And so this always works， and it works whether there's a record in there or not。

It works whether there's a record in there or not， and it does a third thing。

 so it's got a if statement in here。If this if this insert is not going to work well。

 then do this instead。 And oh， by the way， we' turn the new data。

 whether it was an insert or an update， and that includes the new value。

 like the 85 or 90 or whatever it is。 after you click this。 right now， if there's 0 here。

 then it's going to insert it and you're going to get one back。 If there's 79。

 you're going to insert it。 are you're to update it's going to be 80。

 Or if a bunch of people are updating the same time。 and you might update it and get 85。

 And it all works。 and it's all， it's all atomic， right， it's all atomic。

 And this is one transaction， one SQL statement， one semicolon。 And it's a beautiful thing。

And so you look at my code and you find that I'm doing a lot of inserts where you think I need to be doing updates。

Because it's really its insert only happens once， and then the primary key。

 the unique constraint clicks， and then it just turns into an update。

 but it's easier than me putting an if statement and making two actual SQL queries because that's costly and that's a waste of time。

So I'm not going to go into great detail， I might do a little visual demo of this。

This is what we do when we're actually explicitly doing transactions。

 I haven't done this much mostly because the applications I build are online but not banking。

But the one time I did it， I built a little tiny multius game to match people up to play rock paper scissors and then play the rock paper scissors。

 And the problem I had was when you're starting to play rock paper scissors and you pick your rock paper scissors and you want to play。

 we have to decide if someone already has。Is halfway into a game and you play them or you start a new game。

And so you kind of have to go and you have to check to see if someone's ready to play a game and if they are ready to play a game。

 then you lock them and then you play the game and then update them and then one of you wins right So there's there's things where you just have to grab the data。

So when you this is real transactions， right， you're really going to do it。

 and in particular it has to do with time passing。And so I want to say， select how much from here。

 where this and this， and then this for update this。This four oops。Is for update。

That basically says lock it。It doesn't lock for people who are just reading it。

Because they might read it before you change it。 They might read it after you change it。

 And because of the the asynchrony， they kind of don't know。

 But if there's any one else that's also locking it for update。 If you get here first。

 then this one will actually wait。So if you select it and no one's done it and you get both the data and the lock。

 so you get the how much value and you have locked it。 And if you wait， you are now just。

 there's a little wall around that row。That you put there， beside I saying for update。

 you put a wall around that row。 The second one comes and they hit the wall， and they simply wait。

 Now they only wait。You know，30 seconds or something because these locks are not supposed to last a super long time。

 They're supposed to be like。You know， just like。Millionth of a second and be done with。 But you can。

 if you're doing it by hand， be mean and hold a lock for a long time。

 So you this is where you might do this with two windows。 You do a select， hold a lock。

And then in the other window， you try to select and hold a lock。 and it just sits。

 It doesn't even say could not find lock。It just stops and sets。And then。What you do。

I you do your stuff。And there are one or two ways and a transaction。 One is rollback。

 And rollback basically says， I want to whatever I did， since I said， begin， discard it。Unlock it。

 unlock everything and discard it。A commit says。Take what I have done。And commit it to the database。

 So in a sense， when I do a rollback， this update doesn't even。 by the time you get down to here。

 this update was actually discarded。 In a sense， what you're doing。

 you're kind of working on a copy of the row in here。

And then the rollback says throw away the copy and let go of the lock here you're working on a copy of the row。

But it's blocked for others that can't use it here you're saying update the real row and let go the lock。

Okay， so。You can read up on this。 It's' it's pretty cool。

 and there's are some I've given you only the very simplest bits of it。As I said earlier。

 the performance and lock granularity is a feature for a database that says I'm an awesome database because of how I do locks。

 and so the lock implementation and how we serialize simultaneous access to various parts of our database is a core competency of database systems。

So I didn't cover everything， there's some more things， you know。

 sometimes you're you're getting a least less strong lock。Like you're going to update this record。

 including maybe change its key or a no key update means I'm going to update this record。

 and I'm not going to change。 I'm going to update something in it。

 but I'm not going to change its key。 You can tell what to do when you're waiting for a lock。

 you can say， you know what， I don't even want to wait。 Just select it for update。

 And if I don't get it。

![](img/8ff4a19d46c65b044a7dc8eb1bebb424_3.png)

Tell me I didn't get it and let me do something about it。

 And skip locked is when you are doing a select for more multiple roles， which you can do for update。

 And there might be four rows that would meet your wear clauses。

 but only three are available because the one of them is locked。 you'll get three rows back。

 So I would like to select something for update， Sip locked means just give me the rows that are not currently locked。

 And give them all to me if there are none that are locked。

 And so those are all really cool features。 And once you kind of get a little more skill in it。

 these will make a lot more sense to you。So up next we're going to talk about stored procedures and stored procedures are another way when you have multiple things that you kind of want to do。

 you kind of store the code in the database server and it runs in the database server versus you writing a bunch of Python。

 say outside the database server and running query after query after query。

 some of these multistep activities can be moved into a stored procedure。



![](img/8ff4a19d46c65b044a7dc8eb1bebb424_5.png)

![](img/8ff4a19d46c65b044a7dc8eb1bebb424_6.png)

![](img/8ff4a19d46c65b044a7dc8eb1bebb424_7.png)