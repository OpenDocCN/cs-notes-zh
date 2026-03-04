# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P21：20_跨表连接查询应用.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/edaf9c6024c2ebd40a6e925f150c9c7b_0.png)

![](img/edaf9c6024c2ebd40a6e925f150c9c7b_1.png)

So now that we've spread our data out across all these tables。

 created primary keys and linked them together with foreign keys。

 it is time to actually make some sense of it and this is the power of relational databases again I've only showed you like a total of seven records you have to imagine millions instead of seven so now we're going to take these foreign keys and we're going to traverse the foreign keys to walk across this web of information that's now efficiently stored。

The SQL construct that we use for this is called join。

 The join operation links across several tables as part of a select。

 So it's kind of an extended select but extends across a number of tables。

And you have to tell join how to connect the tables， and that's what's called the on clauseuse。

So we have all this data and these are just the tables that we just got done creating and so we have the ID。

 we have the foreign key and so we're going to connect them together so we're going to get a select。

 we want to produce an output that looks like this we don't want the numbers anymore because that's not good for users those foreign keys are primary keys are just bookkeeping stuff we do is database creators but we want to make it so it looks nice so now we're gonna to have the select we have a slightly different format now we have the table name followed by the field within table album title comma artist name so we're now selecting data from two tables and so we say oh from from now I tend to when you can do this in either order so we're gonna to have two tables the from the album table joined with the artist table so we're horizontally connecting the album in the artist table and I start with the I follow the arrows so I start in the album table and then I'm kind of like looking these guys up I'm saying oh okay two and1 I want to turn those into the strings。

You could do it either way， but I tend to go from and I tend to follow it。

 so album joined with artist。And then we've connected these two tables。

 but then we have to have this on clause to say when rows are connected and we want the one to connect to one and two to connect to two。

That's important because that's meaning we， in effect， look up the corresponding string of name。

 given the foreign key1 or2 right And so that's what the on album do artist I。

 That's the album artist I field and equals artist do I。 Now again， when you have a convention。

 I can look at this。 And I can know， okay， that's a table named album。

 artist I is a foreign key into the artist table。 artist dot I is the primary key。

 And so I can see all that stuff。 And so it goes through and it looks at all these things。

 and it connects those and shows us only the data。 So one of the things that the select。

 and you make too much of a fuss about it。 Select picks among the things that you could see。

 It shows you what you want to see。 we don't want to see the I。

 We don't want to see artist I or I from artist， but we could see all that。

 So select picks what we want to see。So that's basically how we can say I'd like to see a little bit more I want to see the album title。

 the album's artist ID， the artist ID， so we're going to explore and show the data that is the part of the encluse now in the previous one we just didn't show it so if we just add these and the rest of those I mean it's just adding those things compared to the last one and basically you just get these two columns where artist ID and ID and then then just show you how the oncluse has made that connection for you。

Now that's what's called an inner join。 So the inner join is filters where they match right But in a sense。

 the join is taking and looking at all possible combinations of these things Now in a table where there're only two and 2 the number of possible combinations is four all the rows of the first table combined with all the rows the second table that is four。

 Now you can actually express a join and it's called a crossjo So the inner join means take the things that match cross means join means join everything and you'll notice that this crossjoin doesn't have an on clauseuse because it doesn't need an on clauseuse So track cross joinin with genre says take all the combinations and in this case the track has four items in it and the genre has two items in it。

 So we end up with eight rows when we come back and we're also seeing the genres ID and the genre dot ID which is the thing we've。

're going to use as the en clauses， but you'll notice in the cross join。

 in particular the cross join， we both get the ones that match。And we get the ones that don't match。

 The difference between the inner join is these ones that don't match21 and these get chopped out in when we're doing the inner join。

 But the crossjo shows us all those。 So the cross join is like the inner join with a wear clause。

 you can almost think of the on clause as a wear clause after you've done a cross join。

 but we just normally we don't want to do this， but sometimes we do on all combinations。

 This is not a very efficient thing。 Imagine a million on one side and a million on other side。

 you don't really want that。 you just want the on clauseaws and the connection。

 I'm just showing you this not because I expect you to do cross joins。

 but just so you kind of get the the basic mechanics of what join is doing。

 It's like taking combinations and then filtering I mean， the whole join is these eight rows， right。

And the on clause throws away the rows where these two fields don't match。And in some databases。You。

 you do this not with a join and on clause， but you just say from this come of that。

 come of that and put it on the where clauses。 I don't think that's as pretty。But you might。

 that's okay。So this is when we're going to do this with an inner join， which makes a lot more sense。

Right now we're going to do an inner join。 if you don't say enter， it's an inner join。

 which means it's filtering， you take all the tracks and you look up and you put the corresponding genre in。

 and we're only asking for track title and genre name。 So this is a normal join。

 inner join with an en clauseuse。 And all I'm showing here is this join will reconstruct that vertical replication。

 The join will reconstruct the vertical replication。 The rock， rock metal metal。

 So that was the thing we didn't like。 but that's the thing we need for the user interface。

And this gets complex， but again。You're just like， when I write this。

 I write it really fast because all my joins look the same。 all my field names look the same。

 All my patterns look the same。 So I'm going to say， I want to see the track title。

 the artist name and the album title and the genre name。 from the track。 joined with the genre。

 And here's the matching condition for that join。 joinedin with the album。

 Here's the matching condition for that join。 joinedin with the artist。

 and here's the matching condition for that join。 again。

 you can kind of see how I'm just going copy and paste， Change a little bit。😊。

And it's not that all bad。 And so then and we're not we're only seeing the text things。

 And now what you see is you see the title of the track。 you see the name of the album。

 you see I mean， you see the name of the artist， you see the title of the album and then you see the genre and you see all that vertical replication back。

 So again， I like to think of this as with all of this。

 we compress the database using numbers rather than strings and join reconstitutes the strings。

 but it's it's not stored anywhere。 it's just sort of at the last moment we make the strings and we show them to user and then it's really efficient still sitting in the database。

And so that was a long set of data models and serial columns and IDs and foreign keys and primary keys。

 and all that stuff， just to go from the point where we had a prototype UI that had vertical replication in it to a database that had no vertical replication string replication in it。

 back to a UI that we can then reconstruct on the fly using all of this joint stuff。

Now the one thing I want to touch on is this ondte cascade。

 which I put in all those create statements now that we've done this。

 we can see how these ondte cascade， and so you can think of these rows。

 you can think of many to one relationship meaning many tracks go to one genre or you can think of the genres kind of a parent row and the question would be is what if we removed that row。

 what would we do with these because these point now to a row that doesn't exist。

And so this is where the ondte cascade is helping us maintain these internal links。

 I told you that these are just kind of integers。But when we have a constraint foreign key。

 we tell it that， oh， I know what When this parent row gets deleted。

 what to do with the corresponding rows in this child field。 Okay， so when we say on delete cascade。

 that means cascade delete from the parent into the child。 So once you delete this row。

 these rows are going to be gone too。 Okay， So if you run this command。

That is going to not just delete one row from the genre。

 but it's also going to delete two rows from the track。 right， We have four rows。

 We delete one row from genre， and then we've inadvertently， I mean， as a side effect。

 we have deleted two rows， the ones that had a genre I of two。

 We deleted those rows from the track as well。 So that's how the ondte cascade。

 Now there's more choices that you have。 you you can do restrict。

 meaning that that delete of metal wouldn't work。Meaning that if you delete metal from genre。

 then there's going to be these rows in track that don't point。 And then that would be a fail。

 it would blow up on us。 Remember that when SQL blows up。

 it's often because you or I asked it to enforce a rule。 So if I said on delete restrict。

That means don't let me delete things if I would break my internal data model。 and you like that。

 I mean， it may seem wrong to you like， how come I can't do what I want to do well。

Then tell it you want to do that。 Cascade is the 1 I tend to do because it keeps your data model clean。

 So if you delete a parent row， you throw away the child row so the consistency is maintained。

 And then the last thing you do is you can set it to null， which effectively deletes those。

 not the whole row， but it deletes those foreign key columns。 So you don't end up with a two。

 you end up with null in that， meaning it doesn't point。 now you've got it。

 if you're going to do delete set null， you've got to allow your foreign key to have a value of null。

 because you can decide whether or not， is this an integer field， or integer null。

 meaningan integer null field means I'm allowing nulls in this field， which null is empty。



![](img/edaf9c6024c2ebd40a6e925f150c9c7b_3.png)

So I'd have to say integer null if I was going to say on delete set null because and it won't even create the table that way again。

You always think like， oh， it won't create the table that's so means's like， no。

 just put delete cascade， so I I don't know。We spend it's a weird thing that you got to get used to when you're building databases where you're like。

 in force I have decided to make you enforce rules on me the programmer。

Because it saves you all the time， so that's your choices for onelete。

So the next thing I're going to take a look at is many to many relationships and at this point you're probably thinking。

 well， you know artists and albums， that's not quite right。

 yeah because they're not really one to many relationships in the real world and so now we're going to get to an example that shows you the other really valuable way of representing data called the many to many relationship。



![](img/edaf9c6024c2ebd40a6e925f150c9c7b_5.png)

![](img/edaf9c6024c2ebd40a6e925f150c9c7b_6.png)

![](img/edaf9c6024c2ebd40a6e925f150c9c7b_7.png)