# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P9：8_PostgreSQL表操作实践.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/36bfd0991d9e24819b29e90868ada550_0.png)

![](img/36bfd0991d9e24819b29e90868ada550_1.png)

So now we're actually going to type the SQL commands that actually work with the data that's in the tables。

 and so we start with insert SQL insert。And again， we have this situation where it's kind of wordy。

Insert into。Its kind of the keyword， name of table。

 and then a parentthesized list of the column names。From the schema， the word values and then。

There is a one to one correspondence。There there's two here， there's got to be two there。

 one to1 correspondence between the values and the way you go and then you put a semicone at the end of each line。

 and then you would type these into your PGSQL and that would insert records。The delete command。

 talking again to PgSQL says。Delete from。Users is the name of a table， where clause。

 you're going to see wear clauses on a lot of SQL commands。And the reason is is that。

SQL is not a procedural language。 I've already mentioned that。

 And so there is no real concept of a loop in SQL。The delete from implies loop。

And if you don't say where if you take this off。It would be like， delete all the。Rose。

Delete all the rows from users if you took this off。

You could imagine it sort of it implies that delete all the rows from user This is kind of like a loop。

 it'd be like four blah， blah， blah in rows do something。

 but you don't say that because delete has kind of an implied loop around it。

And so if you don't say that， you just emptied out your entire user table Li。

 you emptied out your entire user table。 So you're like， oh， wait， wait wait。

 I didn't really mean to do all of it。 So really all I meant to do was delete all the rows from users where the email equals this。

And so it's kind of like a loop plus an if statement。 So delete from users。

 where is a loop plus an imp statement loop through all the rows and users。

And then if email equals1 you study you delete it， otherwise skip it now。

There is no way that it would be efficient to write that loop to read all that table and then delete one line。

This is an abstraction because that's not how it's done in a database。 It's got some complex place。

 It's got a little data here and a little data here and some index over here that points to this little bit of data。

 And then it just like goes and changes this to delete it。And instead of reading tons of data。

 which there might be like a million records in users， it doesn't read them。

If we're doing sequential master update， literally a delete could take four hours because we're copying all of it to the new one and we're taking。

All the records except one and copying them， and that could be four hours。

RightThat's not how it works in relational database。

 How it works in relational database is there's some complex structure on disk that you have no idea what's going on。

 And there's some little mark that happens。 And that's that。 And then maybe a week later。

 it cleans something up。 You don't even know。Did I mention it， I love SQL， I do love SQL。

Because you don't have to write loops and you don't have to any of statements。

 but you do have to write wear clauses， otherwise you delete all your rows。Update。So create。Update。

Delete create， delete。Update， read， I'm doing in the wrong order。 Crud is the right。

 We're getting through cut right now。 So update。Update the name of a table。

Update the name of a table set as an SQL statement。 This is the column and the new value。

 So these and you can actually have comma separated of those name equals Charles， email equals。

 etc cetera。 And then you got to be careful because this like delete is an implied loop and so you need a where clause so it doesn't that you can literally update every column in a database if you want。

It's rare。But you might update them to like set of to null or something like that。

 So you have a wear clause that says this goes through this implied goes through all of them。

 And then there's some if statement that when this is true， then do it。 Now。

 the interesting thing is， is if there were two records that had email equal C7 U E to you。

 It would delete both of them。 I mean， update both of them。 Okay， so this doesn't just do one record。

 it does every record where this is true。Like if I said， where email has an at sign in it。

 then it would get rid of all them because it would match。 So it's not just one。

 This actually will return。 if you run it， it'll return like one row updated。Or。11 rows updated。

Again， you're asking for something to be true。When this is done， the following is true。

 all the users that email of c7um。edu have their name set to Charles， when this is done。

 please magically do that for us。And don't make us tell you how to do that。Retrieving is select。

Now that you know these all these， you'll probably use select first， so the select command。

Kind of implies this wear clauses being here， right？Select where email， Select star。

 you give it a list of columns could be name， comm email。

 Select star says give me all of them from and select our keywords。

 and then there's a where clause because again， this has like an implicit loop on it。

 Select has an implicit loop on it that runs over and over and over and over again。

 So select star from users just says get me all the users。 right。

 Select star from users where email equal see7 image study to you。 Again。

 there's an implied loop around the select。 And the where clause reduces that。 Now， again。

 it doesn't actually read all the data。 It's got clever indexes， and it finds it fast。

 And maybe it it takes very little disk access or maybe it's already in memory。 You don't know。

 We don't care。We love SQL。Sorting is an important part of these things so you can use the order by select star from users order by email that basically says I would like this ordered you can it's a sending order normally and you can say DSC for a descending at。

DESC toward the end there， and then you can descend it。You can do wild cards the wild cards。

 So this basically is looking for things that where the name has the letter E in it anywhere because the percent signs function as the wild cards this wild card the way I've got it unless you put some very special indexes on here this actually probably would force what's called a full table scan。

 which means it's really going to have to retrieve the records because it can't build an index。

 all those wear clauses， it could build an index a short circuit and I keep talking about index I'm going talk about index I'll sec but I'll just I'll talk about them right here So let's just say going back to this like sequential thing where you got like a terabyte of data right。

And。And the index is basically like a little set of shortcuts into this。

 you could think of it as a set of shortcuts to say jump。

And so can the index is smaller than the data so you kind of can jump and then you can look for a little bit of data。

 That's kind of how an index works。 The problem with this like is that there's no good way unless you make a very special kind of index to take advantage of an index。

 so this has to do a full scable scan， which means it has to pull all the records to check the where clause and read all the way through the data from beginning to end and so later we're going to talk about query optimization and query planning where we'll say。

 oh you put because at the end of the day， Postgres can look at this and say。

 do you realize that because you asked for that， I got to do a full table scan。

Cause it will tell you that and it can look at some of these other ones and it can say， oh。

 that doesn't take a tail scan at all。 That uses the index。 Actually。

 that one will take a full table scan， but let me go on a different one like this where clause。

 the where clause， where email C7。 Eu the query planning will say， I've got an index for that。

 And this is very efficient。 And so you can tell when your application starts to slow down。

 you can ask for help from the database and say， hey， what are we doing。

So that the light clause is actually really useful for some of the data mining kind of things where because it's a wild car。

 you're like， oh， let's go look around。 It's a little slower than a wear clause。

 a wear clause that has an exact match， although for some indexes， I'm so obsessed。

 I for some indexes， if you have like quote blah blah blah， blah blah percent at the end。

 if it's a prefix look up。Then it can actually use indexes to improve its performance。

Part of why we' even use database in the first place is to go fast。

 and that's why I'm always talking about performance， performance performance。 again。

 go back to the 50 terabytes to log in and somehow it happens in under a quarter of a second。This。

 this limit in offset clauses are how we do like paging。

 So if you're like going through a long list of things and it's like this is one to 25 next。

 and then it's like this is 26 to 50 next， So this actually is well supported in databases so you actually don't have to take your server and your database and somehow retrieve all the rows and then only show the first 25 you actually ask for the first 25。

 So just don't give me you know， do your magic thing that it's very good at using index， etc cetera。

 and give me only 25 rows back as compared to your application code throwing them away。

 And you can use this offset that says skip ahead a certain amount and then give me the next 25。

 Now I'm making these short because all my examples are short with 45 rows。

 but the only other thing to make sure dimension is that these offsets go from row 0。

Which is like Python list。 So that's not all bad。 You just got to remember it。

 So that offset one is really the second row， not the first row。

But these are super efficient and really necessary for looking through long lists。

Counting is another common thing。 Counting is more efficient than retrieving all the rows and then looping through the rows and counting them。

 You can say， look， I just want to know。 So count stars as just count me the rows in users。 Now。

 the interesting thing is it might actually read all of users to do this。

 but chances are good that it actually knows somewhere in its own internal structures。

 how many rows there are。 So it just tells you the wear clauses might actually require a little bit of a little bit of data to be scanned。

 But not so critical。 So you can count them， which is a lot cheaper than actually retrieving them in sending them back to you。

So this is the stuff I showed you so far。嗯。You're like。

And I took I went to college and I'm taking a database class and that's it。 and the answer is yep。

Sort of this is the core of SQL。 The core of SQL is beautiful。 It's simple。

 It's really easy to understand。 It's， its， it's， in a sense。

 easier than learning how to write programs far easier than learning。

 people look at SQL and they're scared of it。 now you shouldn't be scared of it because it's just like this。

 you know， you have this little syntax that allows you to like。



![](img/36bfd0991d9e24819b29e90868ada550_3.png)

Reach it and grab things and poke things and pull things out and delete them。

 and it's a really beautiful abstraction which goes back to the notion in the '60s and the '70s when they defined SQL。

 they said， look let's give something that's simple for the programmers to use that hides the complexity and that's when this abstraction is most powerful now。

We have not yet begun to do complex things。 We've only done single table and it gets a little trickier and more interesting。

 and I think fascinating when we start exploiting relationships between two tables because that's really where things work the most。

So up next， we're going to talk about data types and Postgres of the different kinds of things that you can express when you're building a schema for your table。



![](img/36bfd0991d9e24819b29e90868ada550_5.png)