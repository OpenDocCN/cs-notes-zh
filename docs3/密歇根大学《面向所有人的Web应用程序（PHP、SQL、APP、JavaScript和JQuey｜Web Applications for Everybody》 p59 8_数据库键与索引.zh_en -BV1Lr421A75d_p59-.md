# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p59 8_数据库键与索引.zh_en -BV1Lr421A75d_p59-

![](img/2b43516abacf53e5bc0d36317c8b11fc_0.png)

![](img/2b43516abacf53e5bc0d36317c8b11fc_1.png)

So we just got done talking about whether it's an integer or a character， how long it is。

 whether it's like a GIF image or whatever。 Now we're going to talk additionally。

 not just about what's in the columns， but how we're going to use those columns。

 And so this whole thing of creating tables and defining columns has to do with。



![](img/2b43516abacf53e5bc0d36317c8b11fc_3.png)

How we're going to use these things and now we're going to give it some more detail。

Here we're going to drop this table users and we're going to create a brand new table and I'll focus first on this user ID column and and let me just sort of foreshadow upcoming lecture where we start having two tables and we' got to connect one row and this table to another row in this table so this table has like row 1。

2，3，4 and then this other table has a row that we want to point at row4 so we do this by just putting four in there and so these are called keys and these are called primary foreign keys we'll get to all that。



![](img/2b43516abacf53e5bc0d36317c8b11fc_5.png)

![](img/2b43516abacf53e5bc0d36317c8b11fc_6.png)

And so the mechanism is we find that we want to insert rows into tables and have just some number。

 We don't care what the number is。 As a matter of fact。

 we can let someone else come up with a number。 And that's exactly what auto increment does。

 Auto increment is a way to tell the database。That we're going to make an integer column。

 And so if we look at this user ID column， it's an in， which is short for integer unsigned。

 meaning it's positive only not null， which means it's required。

 and auto increment means please supply it if I don't and the way it supplies it is it starts with like 1。

2，3，4 can we insert a row and the database knows all about this stuff And so just like oh。

4 Next one's5。 I know how to do that。 And so we don't have to in our programs keep track of this stuff。

 And so this is a way to say that。And then we have the two fields name and email vcar 128。

 So which we did exactly like we did before。 And now what we're also going to tell it something about。

 remember I told you about these indexes that were like shortcuts to various places on disk。

 We're telling with these next two statements， something about the data and how we're going to use them。

 So what we're saying with primary key for user I。 we're saying this column is something we're gonna to use a primary key。

 which means we're going to use it a lot。 and you better be able to look it up really fast and you better throw some extra stuff on the disk。

 Extra breadcrumbs here and there so that we can get to that super fast So user ID is a number and we want a very good index。

 and I want it really fast lookups。So the other one， this index。

What we're saying there is that we're going to actually look up with where clauses using this a lot like where I wear email equals C7。

 you must study to you or even a like clause， and we might actually sort this a whole bunch and so we're telling it didn't change what we're going to store here。

 it's changing what we're going to expect or how we're going to use it and then these are like hints。

 all of these are like hints。There are also rules， primary key means it's got to be unique。

 et cetera， et cetera， et cetera。But therere also hints to say， hey， database。

 while we're storing this data later， I'm going to look this email address up a lot。

 I'm not going to look it up by name。 I'm really going to look up in this table by email address。

 So if you're going to make an index， go ahead and make the index on email。

 I don't know if you're going make it fast or slow。

 but I'm just giving you a hint right now that we're going to use the wear clauses with that email and look strings up in there。

 so please be efficient， but you didn't tell it explicitly what you wanted to do。 You just said。



![](img/2b43516abacf53e5bc0d36317c8b11fc_8.png)

Later， I might be doing stuff with this， so let's go ahead and create that table。



![](img/2b43516abacf53e5bc0d36317c8b11fc_10.png)

Let me just copy this， create table statement。And go over here。And let's see what's in here。 Okay。

 we don't have a table so I can make the table if you did just drop table or get rid of it with a little couple of clicks。

 So it's an auto increment field。 This is another column and this is going to be our primary key for this row。

 and then we're going to add an index， a character based index on the name field。And so ultimately。

 if you look at the structure of this table that I just created。

 it works pretty much the same as all those other ones。 We just now have。

 we still have name and email， but you see the little key that's kind of telling us that's a good thing to be looked up on in primary keys。

 that's like it knows this。 And it knows that it's auto increment， et cetera， et cetera， et cea。

 So if I， for example， go back in now。 And I insert a bunch a bunch of records。

 Let's go back to those insert statements。 because。You'll notice that I don't have to put user ID in。

 I just add a con called user ID and I don't have it here or here， so watch what happens come back。

I'm going to insert four records and never specify the user I。

 That's what auto increment does is if I don't specify it， provide it for me。 Oh， and by the way。

 it's got to be unique。 So it just did that。 Let's take a look。Look at this， it just put them in。

I can later， when we do this in PhP， I'll be able to pull this number back out and say what number did you give me。

 But it actually assigned all those things for me automatically。

 That's what auto increment is really powerful。 And when we get to the second major part of this。

 when we start talking about joins and multitable stuff， this is going to be essential。

 But auto increment for now is just a way to make a column， that's automatically set up。



![](img/2b43516abacf53e5bc0d36317c8b11fc_12.png)

![](img/2b43516abacf53e5bc0d36317c8b11fc_13.png)

There's a lot of built-in functions like we talked about now so you don't have to really know in PhP what the date is you just say now and then you say oh created at is a date time field and insert now into there and it works all the time there's cool string functions etc etc I don't teach too many of these other than now because you can go find on stack overflow you're like watch the PhP oh what is the mySQL function to take the first three characters of something and you're like cut and paste you're done。



![](img/2b43516abacf53e5bc0d36317c8b11fc_15.png)

![](img/2b43516abacf53e5bc0d36317c8b11fc_16.png)

So like I mentioned， indexes。 if you don't tell it to index something and you select something。

 it may have to scan the entire table， which is like。 It's like， oh， that's going to take a while。

 If there's hundreds of thousands of records， these things can slow down。 but the index is。

 like I said， a。Trick based on， you know， a little， it's basically a table of contents， right。

 So I'll go back and draw that picture again right。

 So the date is stored here and here and here and here。

 And you got to move in and out and wait for the thing to come around。

 or you store a little bit day cause the index， which is a shortcut。To each of these records。

And this is a smaller amount of data it reads this and says， oh，4， I'll read the index。

 and I'll go straight to4 rather than going 1，2，3，4。 So it's like a set of shortcuts in。

That's grossly oversimplifying These These are amazing techniques。

 and people have done Ph D thesess on how to do this better。 This picture is the simplest of them。

 And so there are whole PhD thesises about how to do this on a disk drive。

 how to do it on multiple disk drives， how to do it on SSD drives。😊。

That's the beauty of database work， is that。Thousands and thousands of Ph D thess in computer science have been written to make this software fast。

 And you just say select， and it all works。 There's a couple of different kind of indexes。

 There's a hash or a tree。The hash is used often in primary keys for exact matches。

And the trees are used for sorting。And prefix matches。But to the1 I showed you before。

 I didn't even tell it what kind of index。 The primary key index was。

 I showed you that in the other end， it's a very little space， exact match， no duplicates。

 but it's super fast for integer fields。 And you'll notice that that primary key that I put on was an integer field。

 The index that I used on the other one。 Either hash or Bere is good for prefix lookups。

 the be tree is best for prefix lookups。 Most people tell you to not even tell it to use hashher Bre and let it adjust sometimes based on the data。

 This is kind of the internal structure of the bere。 So remember， I told you that you know。

 you have data that's sort of scattered all over the place。 Or another way to think about it。

 Let's draw this picture a little bit differently， right， So here is data。And。

 and there's a record here and a record here and record here。

 It might take you some time to scan through it。 So you make this little index that's like a shortcut because you can go randomly。

 You could go sequentially or you can go randomly。 So you have little index and it sort of points to this。

 And these are shortcuts。 So you save， you skip all this and skip all this and skip all this。

 And so Bre are one form of index， not the only form of an index。 But the idea is。

 there's a small amount of data that points to the larger chunks of data。 And so this is。

 this is a picture of what that might look like。 So so you can think of this as little block of data that has a series of numbers。

 The data is basically sorted。 And what we say is we have a little。

 we store a little shortcut to another block of data。

 And anything lower than 7 is stored in that block of data。

 and anything between 7 and 16 is stored in this block of data。

 And I think about 16 is stored in this block of data。So if I'm saying， oh。

 I would like to look up 9， it comes。 it reads this。 Okay， and says， oh， that's， then it reads this。

 And then it reads the 91， which is out here。 And so it takes three instead of， you know。

 however many it would have have had to go the other way。 Now。

 when you insert data in in something like this。Let's say we're going to insert four。

 so I'm going put four in here。 so we're going to insert four。

 So what happens this will get a little messy is4 goes down here and you look in here and it belongs。

 it belongs right there。And it's like， oh， drat。 And so what it does。Is it sort of moves everything。

 Now it might split this。 So I'll just， I'll just say let's split it， right， So do this 1，2，3。1，2，4。

 and then another one that's 5，6。And then what it will do is it'll say。It'll make a five here。

 and then everything below five goes here， everything5 and above between 5 and 7 goes there。

 So it split this block into two。 Now， you don't need to know this。

 It sort of has to adjust these things。 but when it's done adjusting。

 then you still have a fast way to get all this stuff and。Do you really want to know this。

 And the answer is， no， I don't want to know this。 Somebody in computer science figured this all out。

 And actually， this is too simple。 I mean， there's better ways to do this。

 but you don't need to know that you do need to know that bee trees are good for sortdid kind of material and prefix material。

 especially like a string。 if you were looking up names。

 And you're looking up names that started with C H。 You still could find the right spot。

 And then you'd scan through all the C H's， basically。 And so that's what bee trees are good for。



![](img/2b43516abacf53e5bc0d36317c8b11fc_18.png)

Haashhes are a little more complex to understand。 They use clever math。

 They use this thing called a hash function and feel free。

 It's the thing in Python that makes dictionaries really fast。

 And what it does is it basically does a simple calculation based on the key like a thing you're looking up like an email address or a name。

 And that produces a number。 So it runs a little thing。

 it might look at all the characters and addom up or divide by two or do some combination。

 But when it's all said and done， it puts gives you a number， say from 0 to 15。

 And then based on this calculation， you say， oh， this one is3， And so or actually this one is2。

 and you calculate and you go and you can store it in a slot。

 And so this didn't take any talking to the disk drive。

 you just calculate this function So you go right to the same place。 Now。

 the problem with hashing just like I showed you in the last one is you can have more than one key hash to the same place。

 Then you do things like have little extra overflows or you split these things， et ceter。😊。

And so hashing sometimes takes a little more time to get it reorganized。

 but then it's super fast because you don't even have to read the you do the hash and then you kind of read the disc very few times okay。



![](img/2b43516abacf53e5bc0d36317c8b11fc_20.png)

So hashes and be trees are two different kinds of indexes。 As we saw in the very beginning。

 We can indicate what kind of an index we want to put on the various columns。 This is a hint。

 It really doesn't change the syntax that you use， but it's a hint。

 So we've said that this is going to be sort of a hash-based superfa integer-based index。

 this is more of a stringbased sorting prefix lookup kind of index。

 And what's really cool about it is if you forget to put these two things on。

 and you find out later that your application is not running。 well。

 You can all come back with an SQl command to add the index later。

 And sometimes there's even tools that'll watch your database and say， you know what。

 you should probably put a bere index on email。 And like I mentioned。

 some of my colleagues say you should never say what kind it is and let it figure out the best thing。

 this part about using Bre or using hash， you might want to say it because if it's strings probably you want Bre。

 otherwise you want hash。 but you can also just let the database decide that what we're really saying is that I'm going be looking stuff up with where clause。

This is a lot with this email， and so I want you to store that Mr。

 database as efficiently as you possibly can。

![](img/2b43516abacf53e5bc0d36317c8b11fc_22.png)

So this's a quick zoom through SQL and we sort of set up the shape things。

 we set up rules about the data， we give hints about how we might use that data， create， read。

 update and delete， and it's not that hard， it really isn't that hard。

 And so the next thing we're going to talk about is how we make more than one table and start connecting those tables together and that actually is the real performance gain that we get right now we come up with a very formal way to store data。

 but it's not really the thing that makes it go super fast although indexes are cool but joins are the really cool thing and we'll talk about that next。



![](img/2b43516abacf53e5bc0d36317c8b11fc_24.png)