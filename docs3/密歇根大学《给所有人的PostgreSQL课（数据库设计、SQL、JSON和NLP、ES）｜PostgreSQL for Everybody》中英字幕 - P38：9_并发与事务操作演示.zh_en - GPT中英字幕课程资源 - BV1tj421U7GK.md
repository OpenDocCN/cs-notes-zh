# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P38：9_并发与事务操作演示.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

Hello and welcome to our SQL walkthrough on concurrency now concurrency。

Is not necessarily something that we end up worrying about too much in data mining applications it's really critical for online applications。

 but the key idea is is that we have things that are happening as a flow of transactions to the database server。

 so we have many clients for example， for us， we could have one client here we could have another client here。

 these are two independent terminals that are connected to the same SQL server and somehow select。



![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_1.png)

Star from fav So this and now'll do that from that one。

 And I'll say select star from fab from this one。 Somehow the server has to resolve things that might end up with these two different connections。

 And literally there could be hundreds of simultaneous connections that are doing things。 Now。

 reading is not that big of a deal from a con currency perspective， as's a matter of fact。

 if two things are reading the same thing off in the database is very clever about that。

 But if we're starting to add data or delete data or update data。

 Then sometimes the fact that more than one thing is simultaneously trying to do the same thing。



![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_3.png)

That can be a problem。Okay， so let's take a look。 so in this fab just to refresh your memory。

 the fab is a many to many table。 So it's we're taking a person who is favoring particular posts and we're going to make it so that they can indicate that they really like something by favoring it many times。

 So so this is me and this is my post that I like and I'm going to how much is going be 0，1，2，3，4。

5 and we have updated at and created a stuff right so the the motion that the user is going to go through at some point is。



![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_5.png)

![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_6.png)

Hitting a plus one on this it's like this is even more of a favorite。

And so let's let's go ahead and run an insert。 So the first time if user one was going to favorite post one。

 we would set it to be one， right。

![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_8.png)

AndSo now if I did a select star from Fab， there we go， user one and has likes post one this much。

Right now we only can do that if we know that that was done that wasn't done before because if I say insert into Fav again。

 it complains the duplicate key， which is exactly what we want。

 we put a duplicate key on the combination of post ID and account ID here on these fs。

 we take a look。

![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_10.png)

Let's go back up to the top here。Here's the favs。 We basically made a unique constraint on the combination of post ID and account ID on purpose。

 and then we are going to。We're going to take advantage of that。

 but you can't necessarily do the same， you can't do the same thing T because。We want to do that。

 By the way， this returning is basically combining like a select。



![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_12.png)

In。So that。Returning star， this is like do the insert and then do a select。

Okay this is like returning is after that insert is done。

 select star from the table I just inserted into。

![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_14.png)

那。If there's already a record in here， we know that the thing we want to do is we want to do an update and we'll stick a returning star in there。

 so we see the post update。

![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_16.png)

And so look， how much has become2。 So we you know update fab said how much equals how much plus one where post I equals1 and account ID equals1 returning star。

 that just is a quick way to tell us what's going on。 And so there we go how much is now two。

 Now what's cool about this is this is run a single transaction。

 So we know what the value was after we added one to it， which is really quite cool。

 and so if two things were going on right now。 Like if if I was doing this。

 two people were hitting two screens were hitting this update at the same time。 know。

 this is now three， it went up to three。 So this is my other terminal and it's updated at3。

 So go back going back to the first table select star from favs。

Remember they're singular Chuck remember they're always singular right so how much is three。

 So we've got these simultaneous things happening going on both at the same time in two different clients might be two different web servers。

 two different threads in the same web server or might just be two things connected from two terminals。



![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_18.png)

So it turns out that we don't know which of these two things to do。

 we don't know whether to do an insert or to update。

 and conveniently there's this on conflict capability。So we can say insert into Fav。

On conflict means if that insert failed because of a conflict post I account ID。

 you' got to tell it which columns are causing the conflict。

 These are our two unique constraint columns。 So on conflict。

 do update set fab equals how much plus how much plus one。So we add one to it。

 So what we're doing was really combining this with an automatic if statement。

 But what's really important is then this is wrapped into a single transaction。 so you can have many。

Many clients sending this a message like this， an SQL like this at the same time。

 and the database is going to resolve them， one is going to go first and the other is going to go second。



![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_20.png)

Okay。So。In this case。It is going to。Do or select again。It's now four， but let's just do delete。

From fab， get rid of everything。 So we just got rid of everything。 So select star oops。

 select star from fab。 There's nothing in there。 And now I'm going to run this insert statement again。

And so this time， there is nothing in fav。 So there is no conflict。

 So this first half of the statement is actually going to run。 So if I select star from fav。

Then it's there。 And if I run that same statement again。

 this time it's going to have a conflict because it's already there because of the unique misconstraint between post ID and count ID and so now if you take a look at the select you'll see it's too So this is in effect insert or update depending on whether or not the record is there the only attempt does an update is when we have a conflict and that's why we put those unique constraints in these we put these unique constraints in our create statements so that we can then trigger this on purpose if I input a unique statement though insert would keep on working and you just get more and more rows with duplicate stuff。

So we're using the unique constraint。And then we are taking advantage of the unique constraint here。

 but even more importantly， this is all done as one transaction。

 So if this code is run simultaneously。Somewhere else they're going to be ordered one is going to be one is going to win。

 they don't hit simultaneously。 if they hit simultaneously， then the database will stop。

 pause one briefly， do the other one， and then the second one will get run and so that's。



![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_22.png)

Sort of real simple。 And so we love to do these kinds of things。 You know。

 we love to do these kinds of things where we use on conflict。 I do it all the time。

 insert or update， insert or update。 you could add a returning star to this。

 And then you can tell what the value of how much was after so you're gonna like hit the plus button and it should say4。

 And then if you did this in a different window， it would say you just added it to5。

 But even then that's all done in a single transaction。

 So even if two things happen at the same time。 One would get 4 and one would get5。

 And so they would know where they are at。 okay。

![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_24.png)

![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_25.png)

So that is sort of it concurrency in that we want this to work and the database server Postgres puts a transaction around this automatically because it's a single statement right。

 it's a single statement in a transaction。那。Sometimes you want to put more than one statement in the transaction。



![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_27.png)

Okay。And so there is this SQL statement called begin。And then an SQL statement called rollback。

 which means give up。 and then a statement that says commit， which says actually do it。

And so the idea is is sometimes we can't。Do such a cool thing where we can wrap in a single SQl statement。

 a whole bunch of cool stuff to do two things。 Now， if you didn't have this， and of course。

 you do have this， this is a silly example。 But I I want to basically make it so I can do a select and then an update later。

 Who knows why？ I mean， I make this really simple。 So it stay simple。

 So this select has this special bit。And this is effectively grabbing a log on a row。

The lock scope depends on whether I mean， I'm telling it I'm going to lock a row。

 but it might lock more than a row。 We don't know how it does it。

 The first the you're at least locking the row， you don't want to lock this too long because other things can't happen。

 So it says I'm going to select this。And hold on to it until I tell you to let it go。

So let's go ahead and do this。I'll say begin， that's an SQL statement。

We're now in the middle of transaction。Select how much from Vav。At this point。That row。Is locked。

Okay。Now， I can then say。啊，对。Set it to 99， oops， what I do， Ron。Said how much。啊对懂。Sorry。

I have to change this。 I've got a typo。This is why I like Boops， update fan。

 This is going to be wrong too。I've got a tyypo there。So I'm going to do this right now。

 this is why I edit these things inside of a text editor and then paste them over。冇。Current。

 I wonder if I took too long on this transaction， let me do it faster。 let's say roll back。

 which probablys not going to do any。Yeah， okay， let's do it faster。s， soups， undo。

Do these two really fast？And then I'm going to do this part。Faster and yep， it's happy now。

 and then I'm going to do what's called a rollback。不。

So what this rollback does is this rollback begin brackets the begin and rolling back is giving up on the transaction。

 So what happens here is this update。I'll have to show you this again in slow motion， slower motion。

 So I'm going to do this select again， but without the。For update。

And you'll notice that this number tick never changed。 It changed in the middle of the transaction。

 So transactions are a group of commands that are either all going to execute or none of them。

 so it sort of cues them in a way and locks all this chunks of data。



![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_29.png)

![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_30.png)

So let me， let me do that again fast enough。 so I don't time my transaction out because it doesn't like these things。



![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_32.png)

![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_33.png)

We add this select right in here。So I'm going to do this。



![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_35.png)

Let's clear this all out。I'm going to start a transaction， I'm going to update in the transaction。

 and I'm going to select in the transaction。And then I'm going to roll back。

 Let me do all these all these really quick。

![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_37.png)

Because that what would happen if it was an online thing， it would the start the transaction。

Do the update， it selects it， right？And everything between the begin and the rollback is like needs to be done。

Quickly。And that's why I pasted them all at the same time。 But here's look what happens now。

 because the rollback we gave up on the transaction。



![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_39.png)

The transaction was discarded。 So this during this begin and the rollback。

 it was like working on its own little isolated， siloed version of the database。

 It wasn't the official database。 It wasn't the whole database。

 And and so you can go really far down。 And this has to do with the fact that sometimes you got to say you're going to do some banking transaction that you've got to look up some data。

 look up another thing， look up another thing and lock all those things So other people aren't looking them up then you give out the money。

 and then you got to update it and then you got to commit the transaction or you try to give the money out and the money money giver out or fails and you got to roll back the transaction。

 So sometimes you're doing a bunch of work in the middle of a transaction and you want to give up now。



![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_41.png)

![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_42.png)

If you don't want to give up。Youd say， commit。So now we're going to set this。

And we're going to do it again， we're going to select。

 and then hopefully Ill be able to do it fast enough to do a commit。



![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_44.png)

![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_45.png)

Ch。So there we are， we're 99， but now I'm going to commit the transaction。

 which means that everything that was in my little， you know， my own version of this database。



![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_47.png)

That's now committed to the real database。 So they all win at the same time。

 so that either none of them happen or all of them happen。 And I could have a whole series of。



![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_49.png)

I could have a whole series of statements that are， in effect， temporary until I say。

 commitit now I'm not in a hurry， but now I can say select how much from Fav。Fortnate 99。Okay。Now。

I want to show you something。I'll get two windows up。Not in the transaction in either window。

So I'm going to start a transaction in one window。In this first window。

 and then I'm going to try to start another transaction in the second window to show you how the one transaction。

 So I'm just going to do this。

![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_51.png)

I' run this transaction and I'm going to try， so I'm not going to do the rollback or the commit。

I'm going to start a transaction。 I'm going to grab it and lock it with this update。

 Then I'm going to try to update the locked row， Then I'm going to see how the update went。喂。

And then I'm going to commit a rollback。 So I'm going to do this in two windows。

 I'm going to do it in one window， and it's going to work just fine。



![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_53.png)

Right， so it's just fine。 I'm going to go to the other window。

 and I'm going to run this and notice how。This select for update。 I can't get my hands on that row。

 I just can't get my hands on that row。 So let me roll this one back。

It's still being nice to me rollback。Back。We can't roll back fast enough， okay， roll back。

And look what happened。This finished。So this was waiting。

 this statement right here was waiting until I rolled it back。

 and that's because this statement over here on this terminal locked it。Until I said， roll back。

So what was going on is the database was insisting that this statement happened。

 I'm attempting to run this simultaneously， but the database picked an order。

 And it was whoever got there first。 And I just because I'm doing it。 So this one got there first。

 But even if they arrived at the same time， it's like a doorway。

 one goes through the doorway and the other one is paused at the doorway now。

There is a timeout on this。 I don't know if I'll be able to get you to see the timeout。

 So let's run this again。

![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_55.png)

Let runun it again。 Let's run the。

![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_57.png)

run this one， in this window， and now I'm not going to。What happened？Oh， this one， I mean。

 I got to roll this one back。Because I was in a， a， we're all back。

 I was in a transaction in this one。O。Im got to roll this one back。Got myself all messed up。

 too many transactions。All at the same time。Roll back， rule back， Okay， so there we go。

So I don't know how long this will time out。 I'm going to just let this sit for a bit。

Clear this all out。

![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_59.png)

![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_60.png)

I not know how long this is going to wait。Sometimes they have timeouts。Okay。

 so this this terminal has a transaction， it's got to begin， select for update。

 and it's got to update， it sees its result。And then I am going to go into the other other。

Window and I'm going to do this and you'll notice that it's stopped at the select statement because that lock is held。

Now we're going to sit and see how long it takes。We're not going to do a rollback or a commit。

 we could do a rollbacker commit in this first one， and then that would unlock the second one。



![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_62.png)

So I don't know how long that's going to take。So that's the basic idea of transactions。

This we can use this like insert on conflict as a way to have it's a much more common way。

 you want to send the send the database SQL in and have it do everything it wants without having to talk to it twice。

 So if we were talking this PG4E application， I mean this PGSQL application that you're running is a client and it's sending commands to the database server。

And。This is great because this is just one command， and it allows us to do two things。

At the same time， right， do this two things。Here's the data， if it's not there， insert it。

 if it is there update。Okay， and then at the same moment do a select so that is really insert。

 update and select all in one statement， one round trip between our client。And the database server。

 and we'd like to minimize those。These， the begin， the select， the update， the select， the rollback。

 the select， these are all separate communications， so transactions。

 explicit transactions are slightly more costly。

![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_64.png)

And I don't know。 this doesn't look like it's going to time out。 This is what's called a deadlock。

 And if this sits long enough。It will detect a deadlock。And so I'll just finish this。

 If you let it sit long enough on yours， you might find it something about a deadlock。

Roll back this transaction。Excuse me。 I'll roll back that transaction， which will unlock this side。

 and then I will do a rollback on this side to make sure my database is not messed up。

 So I hope that was interesting。 You have to run this with two。

 You got to run two terminals and you got to run the P GSQ L and two terminals。



![](img/57c7865ee47e8bc2ece69a06c5d1b4ab_66.png)

But I hope that you found this a little bit interesting look at concurrency and transactions。

