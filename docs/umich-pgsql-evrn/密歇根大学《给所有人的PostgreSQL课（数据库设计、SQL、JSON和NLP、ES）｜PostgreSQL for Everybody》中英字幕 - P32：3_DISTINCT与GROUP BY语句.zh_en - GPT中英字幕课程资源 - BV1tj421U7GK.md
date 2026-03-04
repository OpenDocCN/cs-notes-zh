# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P32：3_DISTINCT与GROUP BY语句.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/faf533831095090d419e96b183260238_0.png)

![](img/faf533831095090d419e96b183260238_1.png)

Yeah。So now we're going to talk about distinct and group by in a way。

This is another sort of lens in which to look at sort of vertical replication。

And so we talked about vertical replication， we talked in the second lecture about modeling and removing vertical replication。

But not necessarily all remove the string vertical replication and then putting that in separate table。

 and that's what we're doing with joins and data modeling and all that stuff。

But like when you join all this stuff back up， the vertical replication reappears sometimes。

 or it might even just be that there are numbers that have vertical replication。

 so sometimes it's the result of a join all I'm not going to use joins in this example so you get a better sense of what this distinct distinct on a group by R。

But the idea is to remove vertical replications。As the result of a select statement。

 So you do the select statement。 And then you're like， okay。

 I look here and that and I've got vertical replication。

 maybe two rows or three rows that are the same， I only want one。 So that's what distinct is。

 distinct is the simplest to understand。 distinct on is if you have more than one column。

 but you really only want the duplicate replication on a subset of the columns so that you don't care you allow duplicates in some columns and want to remove duplicates in other columns。

 group I is really cool and that when it sees this vertical replication and it's throwing and it's sort of reducing from three to one。

 it's doing something with one of the other columns like it's counting the number of rows or it's finding the maximum of some value in those three rows with identical values in certain columns or taking the sum or average or whatever。

 so the group by tends to be combined with what we call an aggregate function。

 which is sort of taking a set of rows。Squeezing it down to one row。

 but then adding or multiplying or adding or summing or averaging or counting across all these vertical rows。

So。I got some data here。 This data is sort of real data。 It is from my。Race car， so I own a race car。

 my team is named the Sakai racing team， which is an open source learning management system that I work on and so I don't really own all of these race cars I actually only own the first four of these race cars I own a Nissan stanza and three Dodge neoons of various ages but I needed more data so I put some cars that you know who knows how many more race cars I'll have to buy。

I'm not the one that buys all the race cars。 I have a chief mechanic。And he's just like， oh。

 I want that， too。 And I'm like， you know， how about we just make a really simple。

 reliable car so we can have fun racing it and not have to keep working on it。 He's like， no。

 I would have been roller cams and I'm like， well， I'll cause the engine to blow up。

 and then I' have to work on it。 So So I have to buy several racing cars， one that makes me happy。

 And one that makes my chief keeps my chief mechanic。 His hobby of fixing broken racing cars。

 So that's how I have so many dodged neos。 I have two of the Dodge neos。 I sold。

 I gave the Nissan stands it to a guy。 So I don't have that anymore。

 And I have two dodge Ns that are actually race ready。

 And one dodge Nn that just sits in parts in a garage waiting for my chief mechanic and his buddies to go finish it up。

 So。😊，But this lecture is not about racing， this lecture is about vertical replication of data。

And distinct and group by。You see， this is not normalized。

 Remember I said that sort of the whole idea of modeling is to normalize it。

 And we kind of got car models。 And you could normalize this。 That'd be a good exercise。

 its to normalize it。 But now think of this as not necessarily a table because it's a really bad table because that has vertical replication of strings。

 But instead， think of this as a result of a join， a couple of tables。

 And now we've reintroduced the vertical replication。

 but the distinct in the group by happens after the join。

 But I'm just going to make this really simple table。 Hope that makes sense。

 So let's start with the simplest right。 Well。Talk about the concept of reducing the result set。

 so it's like a select happens， does it stuff， including possibly joins to produce this stuff with vertical replication in it。

 and then we're going to do the distinct， take the vertical replication out and create a reduced result set right。

And so that's the idea is you've got right now in this little select， you've got four rows。

 but three of the rows are duplicates。 When you do the distinct option。

 it reduces it down to just two rows。 So don't give me the same row twice。

And so if we were to look at a real query here and we were to say， okay。

 select the distinct model and what that really says。 Now the key now this。

It's a good time to talk about the select statement。 So the select statement often for me。

 doesn't get enough love。 The select statement is an important conceptual part of。

The relational database model。 And if you just say select star over and over and over again and then read through all the records and throw away the data you don't need。

 You're actually kind of throwing away a lot of the power of。Relational databases。

 So it's important that you only ask for the records the columns that you actually need。

 because then that lets the database give you the information you actually need in the most efficient manner。

 And so that's where this distinct。 So if you have two columns。

 the distinct does something different than if you have one column because in a sense。

 you're sort of blinding yourself to all the other columns。 And I want to select distinct in model。

 And that's different than select distinct make model right And so by reducing sort of the horizontal width of your query。

 that's a critical element of why select works。 and how select contributes to the efficiency of the SQl statements that we're going to produce。

 So all we're basically saying is select model， which in effect。

 by not mentioning these other columns， they're not part of consideration。

 because if you did a select distinct on well， I didn't make this very good over here。

 I should change this data。But if you did select statement on model year。

 then these would all be distinct because the year makes them distinct。

 Although here's a couple of mada Miatta 2001， and they would get clased。

 But I'm only selecting model and price because the select is creating a narrowing of the width of our。

 our view that we're taking on this。 And there are And D duplicate gets as you look down， right。

 Nn Nn Nn。 So it throws that away， throws that away， throws Mustang away。 Second。

 third and fourth Miata throws those away。Seect the opal GT。

Part of these are cars I someday do want to buy。 I really would like an opal G T。

But the problem with Opal GTs is if you turn them into race cars， they're kind of classic cars。

 so what do you do ruin classic cars？So， but you got the idea， so select model， change the width。

 but then you have duplicates and then distinct simply throws them away。

 It's a pretty efficient process。This is the distinct on。 And I'll be honest。

 I'm not sure I've ever used this in my whole career in databases， but basically。

 what it's basically saying is that distinct on。Distinc make model。 I mean。

 and so if we think about the width of this query， it make。

Right there make model is the width of this query。 That's the columns we're interested in。

 which means the others are ignored。 And then we're going to do distinct。

 but but we're only going to be distinct on the model。 We want the model be to be unique。

 which means opal can appear twice。 So So if you said distinct make model。 then well。

 actually it's the combination。 So it's whatever。 So it tolerates duplicates in the make is what that does。

So。Now I want to move into group by and instead of giving you some race card data。

 I'm going to play with actually the time zone data and I just play with time zone days because it's already there and it's important to know about time zones。

And so just think of the times zone data as some data that happens to be in a table that I just didn't have to fill up。

Okay， so the simplest of group by。Is you basically say group by a Bve。

 And this is kind of like distinct on areve。Or distinct when only you're selecting areve。

 And so in this areve column， you're going to see no vertical replication， right， so that's the idea。

And then that means that if there are two rows that have this as their value for areve。

 then we're going to count them。 So we want to count the areves。

When there are duplicate values for areve， how many did you get。

I got there's two that look like this。 There's one that looks like that。 There's4 that are IT。

 et cetera， et cetera。 And there's 15 that are plus 05。 And so it's a way。Like a Python dictionary。

 as it were， where you're finding a thing， you're group buying it。

 and then you're doing a count of those things。 So it's kind of like a Python dictionary。

 So the group by is where the vertical duplicates are going to be squeezed out of。

 But in the process of squeezing out， we're going to count the things that are being squeezed out。

And I think you probably make this count star because star means the whole row。

And it really is counting the number of rows that you're fought throwing away。 But in my my brain。

 I'm like。Keep the width narrow。 Don't ask for stuff you don't want。

 I don't think Star really does that， but I just like the idea of expressing the minimum amount of information。

 asking the database to give you the minimum amount of information that it can give you to make you happy。

So。Though wheree clauses works a little weirdly in。The group by。And so here's a wear clause。

 If you go back and you look， there is this column called is or is not daylight savings time。 false。

 false， false， false。 And some of the lines are true。

 And so I can say I would like to do the thing I just did That's this part here， to hear。

 but put a wear clause。So what happens here is this where clause is before the group by。

 it has to be before the group by if you put the group by before the where clause。

 it will yell at you， so you've got to put the where clause before the group pie。

So what what's happening is the where is filtering the records before the group buy so that it's just throwing all the daylight savings time false values out。

 and then that's a set， and then it's doing the counting on that reduced set so the where reduces a result set before the group buy happens。

But that might not be what you want to do。 You might want to only see the ones where the count turns out to be more than 10。

And so， having。Having is like a where clause that happens after the calculation。

You could almost call this where underscore before group by and where underscore after group by。

That's what it's it is Having is just kind of like another。Way to say where。 Okay。

 It really looks the same。 The differences in the having clauses。

You can put this counterre in that having clause， but you can't put it in this square clause and you can't move the square clause to after the group by。

So it's just kind of like this。It does this thing， it does the group by。

 and then in effect it applies the having to the result of the group by。



![](img/faf533831095090d419e96b183260238_3.png)

Quite nice， Qui pretty。

![](img/faf533831095090d419e96b183260238_5.png)

Up next I want to talk about subqueries or subselects。

 this is another thing that makes your database administrator really upset if you use this feature too much。



![](img/faf533831095090d419e96b183260238_7.png)