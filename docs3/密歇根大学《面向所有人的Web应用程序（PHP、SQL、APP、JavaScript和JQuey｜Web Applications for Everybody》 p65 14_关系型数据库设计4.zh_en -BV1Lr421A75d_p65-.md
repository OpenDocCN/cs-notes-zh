# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p65 14_关系型数据库设计4.zh_en -BV1Lr421A75d_p65-

![](img/8db46e7d761a042fd0dc3c5978816662_0.png)

![](img/8db46e7d761a042fd0dc3c5978816662_1.png)

So we have successfully moved all of our data into tables and we've successfully made connections with those tables in the databases using primary keys and foreign keys。

 but literally you can't go back and tell our UI person says， look at this new thing we did。

 This is your new user interface。 people will be able to use our software We'll just have to teach them up about foreign keys。

 isnsn't that great。 We'll just use PhP myadmin as our user interface because it's so gorgeous and beautiful。



![](img/8db46e7d761a042fd0dc3c5978816662_3.png)

Or not。 So our job。Is to take what we've done with all this splitting of the data and all this performance tuning and then bring this all back together。

 meaning we have to follow the foreign keys。 So now we've established the foreign keys。

 we now have to follow the foreign keys， and this is where we'll ask it to follow the foreign keys。

 and this is where it magically does it super fast。

So the new SQL concept that we are going to come up with and understand next is the join operation。

 So the join operation says we're going to pull data from multiple tables simultaneously。

 and we're going to pull these things together and there's an on clauseuse as part of it that says here are the rules to connect this row to that row。

 It's that simple。 So the join says more than one table and the on clauseuse says the tool the rules upon which we can do this。

 And so here's a really basic join。So what we have is we have an album table。

And we have an artist table and we want to show not just we just want to show the album title and the artist name。

 We're not interested in these numbers。 So we have to do is kind of like follow all the corresponding links between this except that that's what the join does for us。

 And so we say select。And then there's a new syntax here。 This is a list of columns。

 But if we're talking about more than one table， we say album dot title。

 artist dot name from we've done that before。 And then the table name。

 So we're pulling from one table。 and I tend to do it in the order of the arrows。

 So if the arrow starts here and goes there。 So album is the first thing I say And then join that basically says we're taking data from both tables to the artist table。

 So that's just all that's really saying is the the super set of data is both those tables。

 album join artist is connecting those two tables and getting data from both them。

 The on clause is the more precise thing that says when does a row from this table connect to a row in the other table。

 That's the on clause。So on says when album's artist ID。

Albums artistist ID when this column right here is equal to artist' artist ID。

Which is that column right there。 So I want to join when these two rows together when that is true。

 So on is the when this is true actually makes the connection。

 So don't make the connection between all possible rows。 You don't want this。

 You don't want this row connected to this row and this row connected to this row and this row connected to this row and that one。

 You could have four connections。 I'm only interested in the connections that meet this criteria and that is when they match and。

That's kind of always what we say。 And again， you can kind of see by the fact that I've named these things cleverly。

 it's easier to write these joints， right， Naming convention makes a lot of difference。

 And so what we see is it connects these things appropriately and gives us back the title and the name。

 And so now we've gone from an internal data model that's super efficient and highly scalable to a user interface that is showing the user what they want。

 And that is， what's the name of this album and what is the name of the artist that does the album。

 So our job then is to reconstruct all this stuff。

![](img/8db46e7d761a042fd0dc3c5978816662_5.png)

![](img/8db46e7d761a042fd0dc3c5978816662_6.png)

Right。And so if we sort to look at this in a little more detail。

 you can think of the join as creating a super long meta row。That is all combinations of rows。

 so all combinations rows， and then you can think of the on clauses as filtering out the combinations that don't match。

And so we can show this exact same select statement select， we want the title。

 but this time we're going to actually show the artist ID in both of the table。

 So this is from this table， and this is from this table and so artist ID So we see the matching and then the artist name so we see the name。

 we see the title， but we also see this thing where we created this super long row that's all the data and we're only showing the ones where it matches。

Okay，And that on reduces this from four up here to two down here because there's only two records where this match happens now。

If we go back， this is， this is the many to one。We'll get there so just because there's only there's one in each one doesn't mean it's like this。

 there could be many album albums for one artist， but right now because our data is so small。

 we're only seeing one， but if you go back to this is a many relationship and this is one relationship。

 we'll see we'll see where they have more than one on the starting point。



![](img/8db46e7d761a042fd0dc3c5978816662_8.png)

Okay。😊，So here we have a little bit more where we're going to go between the track title now we're going to have some the many right so if we go like this this is the track table。

And this is the genre table。Okay。And what we've done here is there's no on clauseuse。Okay。

 so there's no on clause。 And so now we're going to see all combinations of all rows。

 And if you recall， there were four things in the track table and two things in the genre table。

 And so we every row in the track table this is the many side。This is the one side。 all rows。

 we're going to duplicate all rows here， so we're going to duplicate that and that right。

 so that's one row and we're going to duplicate again。

 and so there was four over here and two over here， so we see eight total。Okay， no on clauses。

 there's no on clause， so we're getting rows where these two things don't match。

 And so you kind of see how the join just sort of glues these things together in all combinations。

Right， if I had， 20 rows here and 10 rows here， I would get 200 combined rows。

 So the on clauses is really important to throw away non matching Let me do that look prettier。

 Thr away the non matching rows is what the on claws really does。 In this case。

 the non matching rows are going away。 And so then you would only see the matching rows， which is。

What you want， I mean， you hook these things together up on purpose。'd be like it'd be like to say。

 hey， do an automatic on clauseuse for me because you know what I meant because I made it。

 I called it a foreign key。 Why would I not want the ones that are they don't match or why would I want the ones that don't match。

 But whatever in SQL， you just have to say on and then tell tell your matching condition。



![](img/8db46e7d761a042fd0dc3c5978816662_10.png)

And so now if we add that on， it just pulls that back down and shows the matches。

 And then we get rid of the things in the middle。 And now we see this vertical duplication has reappeared。

 but the vertical duplication of strings is not in the database。 but in the U I。

 So this is the data that then somehow is sent out to the user。

 right And so the replication that we want it in the first place in our user experience。 that's back。

 So the join for a brief moment。 So this is not stored this is constructed when you ask for it。

 So it's not wasting space and it's super easy to produce。

 but then it looks the way you want it to look like。

 So it's reconstructing the vertical duplication of string data。



![](img/8db46e7d761a042fd0dc3c5978816662_12.png)

Now it can get complex， but as long as you name things right。

 it's not so bad right And so to reconstruct the things that we wanted before is we're going to select the tracks title。

 the artist name， the album title， genre name going across four tables and we're going to go from the track table join with the genre tables join with the album table join the artist table right that's giving us across four rows。

 these are the fields we want four rows on Cla。Is going there was four tables and three relationships between the tables。

 right， We had this。 We had this。 We had this and this an arrow， arrow， arrow。

 So there were four tables， three relationships。 So there's an onclususe for each of the relationships。

 And theres a join from join for all four。 So there's four there。 And there's three here。

 And you could， after a while， you type these in your sleep。 tracks genre I equals the genre genre I。

 This is a foreign key。 This is a primary key。 and tracks album I is equal to albums album I。

 foreign key， primary key and albums artist I equals artist I。

 Each one of these things is just the way we capture that relationship and walk into that other table When we want that data in a way that matches。

 So this isn't all that difficult to write。

![](img/8db46e7d761a042fd0dc3c5978816662_14.png)

We often sit in PP my amin and type it we get ready， make a syntax error。

 but ultimately like poof out we get， and then we get。 and again。

 you see all this vertical duplication that's happening again。 but again。

 this output of the select is ephemeral， It's temporary。

 It's not stored in the data and it's not wasting any time or any space in the database to construct the data。



![](img/8db46e7d761a042fd0dc3c5978816662_16.png)

But for the user， we're giving them what they want， okay？



![](img/8db46e7d761a042fd0dc3c5978816662_18.png)

Whoa。So that's a lot of stuff， remember。Who's like a week ago when we started this thing。

 Cause we had the U I person come in。 We saw us some vertical duplication。

So we made like four tables connected to one another， boom， boom， boom， figured all that out。

 then we made some create statements that captured that with some constraints in there。

 and then we started inserting data and sticking these old numbers in and keeping track of the numbers。

And then we had to do a join。To bring it all back together。 And when we're all done， we're just like。

 we just started to hear we ended up there。 Why don't we just type that into a Google Doc or something。

 And the answer is speed。Speed， scale。It seemed trivial。

 And that's because I'm using a tiny little bit of data。 But literally in a web application。

 you just can't afford because if you're successful， you're going to get people using your thing。

 If it doesn't matter， it doesn't matter at all。 you're either going to get like nobody or too many。

 So speed and performance is all the reason that we did all this stuff。



![](img/8db46e7d761a042fd0dc3c5978816662_20.png)

Okay， so let me pick up one little topic that I didn't talk about。



![](img/8db46e7d761a042fd0dc3c5978816662_22.png)

Okay， and that is the on deletete cascade。 so let's go back and show you the on deletete cascade。

So remember。How I said。On deletete Cascade， on update cascade， I just throw these in。

This is like saying in this table， we're pointing to a row in another table。

 So here's our row on the table for here， for here。 The question happens is。

 what happens if this number changes。To 9， do we also want to change this to 9。

 Or what if we wipe this throw out， and there's a bunch of rows， because this is a many。

 This is a one。Many one。 If we have a bunch， do we want to get rid of all these corresponding rows。

 And so what we're saying here is if this row is updated， Cascade the changes into this table。

 or if this row is deleted， cascade the changes into the table。

 So let's draw a picture of that makes it a little bit easier。

 And so we have a child table in the parent table。 these arrows are kind of going the wrong way。

 But the cascading is going the other way。 the relationship is kind of like the from to。

 this is the many side， this is the one side， this is the foreign key， this is the primary key。

 But what we're saying here is there is this relationship。

 that is this row is kind of a parent row to these rows called parent child。

 and what happens if I wipe this out。 right， if I wipe that row out， what should happen。

 Pro is the joins would start breaking。 So what we're saying is with on update。

 And there's other other versions of this。 But what we're saying with ondte cascade is if we wipe this row out。

 minusql， you know about this relation。

![](img/8db46e7d761a042fd0dc3c5978816662_24.png)

follow it down and wipe those rows out automatically and instantly。Okay。

 so that's on deletete cascade。 And so after you've done that。

 those rows are now gone because that's all that you've got left。

 And we do that to maintain database consistency。 It's also kind of nice。 You just know。

 I'll get rid of this thing。 and all the child rows that depend on it， they're gone automatically。

 I mean， if you didn't mean to delete it， then don't delete it。Now you don't have to use cascade。

 although cascade is kind of， you know， one of the things is if you say a restrict。

 you don't say on delete cascade， it actually blows up when you try to delete the parent row。

 it says， you know， their children rows here， you can't do it。

Cascade says if you delete the parent row， delete the children rows and set null means that you go up into the child rows and set them all to null。

 which means make them empty。 But that does mean that the join， there's nothing for it to join to。

 So you， as a programmer， get to choose this。 And this is just an example of you informing the database engine of your intentions。

 Like， I would like you to do this for me automatically。



![](img/8db46e7d761a042fd0dc3c5978816662_26.png)

I don't know how hard this is， but I don't care。 This is what I want you to do。

 And that's what you're doing with SQL and create statements is you're giving it a lot of information。

 So that's cascade， update Cascade。 we talked about that。

 But up to now we've done everything that's one to many relationships。

 And now we're going to do many to many relationships。

 which is kind of the other major way of connecting tables together。



![](img/8db46e7d761a042fd0dc3c5978816662_28.png)

![](img/8db46e7d761a042fd0dc3c5978816662_29.png)