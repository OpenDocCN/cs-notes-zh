# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P2：1_关系型数据库发展史.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/5c5e71af4f5906ee27f4b90c419211d0_0.png)

![](img/5c5e71af4f5906ee27f4b90c419211d0_1.png)

Hi and welcome to relationlational databases in this class we're going to teach you about Postgres Postgres is a really cool database。

 a lot it's both open source， but it has a lot of features。

So you might wonder why it is that we are so obsessed with teaching about databases and for those of us who've been around a long time and started。

Like in the 70s when I started， it's quite amazing how fast databases are。

 We just use these things so much and we take them completely for granted。

When you log into a system like your learning management system。

 that system probably has 50 terabtes of data， and you type your name and your password and。

Qu of a second later， it knows what classes you're in and what your notifications are and and all these things and。

And you probably don't even wonder how it is that it can go through terabytes of data。

In a quarter of a second。And it wasn't always that way。

 And so I like to start with a bit of a history lesson talking about what things were like before databases。

 and honestly， you kind of have done this kind of work if you've learned Python and you've done simple data mining and we said。

 read this file and do something。So the problem that we have is it's not so bad to read a file。

 although in the old days， we had to use magnetic tapes。

 let's see if I got this right Yeah magnetic tapes。 so this right here is a magnetic tape。

And in the old days， we didn't have spinning disks that could hold all the data for an organization。

 The memory of the computers was small， the disk drives are small， And so we stored data on tape。

 and the problem that tape has is it's a linear thing。 And if you're looking at the tape here。

 it takes seconds or minutes to move to look at the data here。

And so the biggest delay that we had if we had to store a lot of data。

 was the access time to go from one piece of data to another piece of data。

And so we had to still solve the problem like if you're at a bank of people sort of depositing and withdrawing money from the bank。

 and then your database is on this sequential media。

 this tape that takes perhaps an hour to go from one end to the other。

And so we came up with this idea that we would put all of your old data on a tape sorted by account number。

And then we'd have a printout in each bank that had your balance as of midnight last night。

 and you would come in and you would do a deposit。 They would fill a load deposit slip and you put your account number on it。

 and you might take out of withdrawal。 They might check the little piece of paper to see if you had the right balance had enough balance to withdraw it。

 but then you'd end up with these transactions。 and these transactions are the daily activity。

 And then what we would do， as there's this thing called a card order。

 we would literally punch them on cards and then we would physically sort them so that they were in ascending order so that the lowest account number was at the beginning of the cards and at the beginning of the tape。

And then at night， after the bank closed， we would have all these things sorted and we would mount。

One of the tapes on one tape drive。 And then we would kind of pull it through the computer。

 I think this is a card reader here， pull it through the computer， and then write a new tape。

 So that's what we would do。 And so this new one。 But we took advantage of the fact that the data was sorted。

 and we kept the data sorted forever all the time。 So the way it would work is。

A program would read one record from the tape， and it would read one record。From the cards。

 from the transactions。 And it would compare them。 And if this card record was greater than the first tape record。

 which most likely was， it simply copied the record。 and then it went to the next record。

 and that would read the next record。 And at some point。

 it would copy enough records to the point where it got to your that first record and these two match。

 at that point， you update and put the new record in。

 and then you advanced to the next transaction in your input data。

 And you'd see that then you advancing through this you're advancing through this when they match。

 but you'd never go farther。 you'd never go ahead， you always look at the current transaction。

 So if you think about the amount of data that actually had to be stored inside the computer's memory at any given minute。

 this could be hundreds of thousands of records。 this could be thousands of transactions。

 But literally the amount of data you had to store in your computer。

In the memory of your computer was one transaction。

 one transaction from the tape and one transaction from the input。

And we called this thing a sequential master update。

 And the way it ultimately worked was you would do this sort of blending of these things。

 They would be sorted， and then would end up with a new sorted one。

 And then you would take this And the next night， you'd make that be the old sorted one。

 And then the next day's transactions。 And so we had we'd have these tapes lined up in tagres。

 And this was last night and the night before and the night before and the night before and the night before。

 And then there's the to mor day after tomorrow。 And back up of two weeks ago。

 And that's how we handled data that needed to be modified and searched。



![](img/5c5e71af4f5906ee27f4b90c419211d0_3.png)

Okay， and so。That's the way it was but。Of course that's not true today today we have disk drives or even faster we have SSDs。

Solid state disks that are even faster。And so the key thing that happened in disk drives or solid state disk was that your data is still sort of permanently magnetically stored somewhere。

 And there's a series of rings here on this disk drive。

 And you could had this little little servo that would move the head in and out。

 And so if you look at disk drives and， you know， disk drives are become more and more rare。

 there was the amount， the speed at which the head could move and the rotational delay。

 And so the revolutions per minute of a disk drive。 and the access time。

 Those are the two things that we categorize disks。 And so as these became more common。

 and the size of disk drives got bigger， way faster than the memory。

 And so you literally could store all of the account data on a disk drive now。

Ds were faster than tapes， and you could imagine that the first thing we would do is we would do like a sequential master update so you'd have like your old data somewhere。

 then you have your new data and you'd read through it slowly but surely and read all the transactions。

Except that you're not really taking advantage of the fact that this literally can move from and if you look at all of your data。

 right， all your data sitting here， you could move from here to here。

In in a hundredth of a second or you know， several thousandth of a second。

 So you didn't have to have any delay。 And the distance here didn't so much matter。

 It mattered a little bit if it was kind of coming around， but that's a subtle optimization。

 meaning that you could literally， if you could think of this as your one terabte of data。

 this whole thing， you could hop anywhere， no matter if it was close， or it was far。

 the cost to go from one piece of data to the next was the same。And so then， the question comes。

How would you build software so that now we can make it so that your account balance is updated the instant you take the money out or make the deposit。

And sequential master update is not best idea， although sorting still turns out to be important。

And so in the 60s， as these technologies and then the 70s， as these technologies became common。

 a lot of companies started building notion of databases。And we've ended up with the results of。

Decades of research in these amazing pieces of software that we call relational databases。

 and the relational databases are， instead of reading the data sequentially。

 you know how to properly bounce around in those data。

 And so we come up with this data that ends up being stored as a network of data on these disk drives that you can bounce through really fast。

 And so's it is an amazing thing。 it's grounded in mathematics。

 and there is mathematics that make these relational databases like that are the reason they work so well。

 but it took a long time before we had software thats sophisticated enough to meet all the needs。😊。

Now as these databases evolved in the 60s and the 70s。

 there became like vendors and these vendors were sort of powerful。

 like IBM and Buroughs and on others and companies some companies that don't even exist anymore and they came up with strategies for building a database and each company sort of had brilliant people who were building really cool databases。

 and then they would get something cool working， and then they would try to convince everybody to use IBM hardware or Buroughs hardware and if you bought IBM hardware。

 you had to use the IBM database and if you bought Burrowoughs hardware。

 you had to use the Buroroughs database and it turned out that they didn't really have a common model so IBM might try one strategy and this is not necessarily because they're bad it was because they everyone was researching it。

So at some point， there was the need to standardize on databases and the standard that now we use and take for granted that came out of the National Institute of Standard and Technology NISist is called SQL structure query language or some in old days。

 I think they called it simpleple query language and the interesting thing and you can see this video with from Elizabeth somewhere else in this course。

 it was perfectly timed， meaning that the vendors had built things that they knew were good。

 they knew good ideas and they had good ideas and there were different ideas from different vendors that were all pretty good。

But yet， they had not gotten so mature that they were just going to fight each other。

 And so the National Institute of Standards and Technology basically said to all the vendors， look。

We're not going to tell you。 You know more about databases than we do。

 We are not going to tell you how to build a database。

 What we're going to tell you is we're going to stop buying your software， unless。

You come up with a standard and we' have help you with meetings and we'll run the meetings and take notes。

 And eventually there will be this standard。 And this S QL， the structure carry query language。

Came out of that standard。And if we were present at the beginning of it。

 it's not something that's SQL is a beautiful thing。 I mean， it is a beautiful programming language。

 is it is my favorite programming language。 And when I'm not allowed to use it because I'm using an object relational mapper or some magic thing that makes SQL easy。

 I'm like stop it， SQL is beautiful。 And the reason that SQL is so beautiful is that it's nonprocedural。

 it's the most powerful language that I've ever used， that's nonprocedural。

 what's the difference between a procedural and nonprocedural language。

A procedural language you say start here， do this next， do this next， do this next。 Oh wait。

 go back up， do this next， do this next。 go back up。 okay we're done here。 now oh skip this part。

 do that all that sequence， all that like I call it like GPS navigation with turn left turn right go straight。

 That's procedural。 and actually that's how computers really work and so at some level you still have to write procedural But what SQl does it says。

 you know what I've got these tables， this stuff over here。 please assemble it to me。

 I don't really care how what you do first or second。 It doesn't matter。

 All I want is I this is what I express the fact that this is what I want And then the database system completely optimizes that and it it is an abstraction。

 our expression of what we want is very different than the action that is taken by the database system to assemble that and it can actually watch what I'm asking for and it can optimize later and move things around and some database systems do that。

 they。Fure out the pattern of usage and then reorganize the data so that the kind of things that I'm asking for are handled more efficiently and so the key thing about SQL is it's not the way that they build databases。

 but it is the way that we talk to databases and it's high enough and abstract enough that every one of the database vendors is able to build a really cool implementation and they can sort of compete with each other and build a better implementation。

 so if Postgres is better than Oracle or Oracleles better than Postgres， they can fight。

 they can compete but then we simply use SQL to talk to it now。The SQL turned out to be quite early。

 And so there's a few extensions。 and we'll see those things。

 But a lot of the core SQL is either the same or very， very similar。 So the the critical core bit。

 and we'll talk about this a lot， is called Crud。The critical notion is that there are four basic things that you a system to store data is you're going to create some data and put it in it。

 you're going to pull some data back out， you're going to change data， and then you may delete data。

 and so they've said that's the thing that we are going to focus on making fast and simple to express。



![](img/5c5e71af4f5906ee27f4b90c419211d0_5.png)

So as I mentioned， databases have a mathematical basis。 The relation is like a math terms。

 So relational databases is like。I hear that as like databases that have the theory of math built into them。

And if you read database documentation， you can tell whether they were built written by someone who's kind of a software developer or someone who's kind of a software theory person。

 so they'll say things like the theory people will say things like relations and tuples and attributes and people like me who are programmers will call them tables。

 rows and columns。And。In there is the truth and don't feel bad if you see weird words that describe something to you that seems very。

 very familiar。

![](img/5c5e71af4f5906ee27f4b90c419211d0_7.png)

So ultimately I said earlier that the data is modeled as a network。

 but it's also modeled as a connection and so it's not just like a road system。

 it is more sort of an abstract connection point the combination of a row and a column is got data at it。

 and we have attributes and rows， a columns and tuples and relations。

We're not going to worry too much about that because we just use this software and it's magical。

 I I talk about this a little bit just to say to appreciate those that came before us that built this wonderful software that we're going to take advantage of。

As a programmer， I think of this as just like a spreadsheet。

 The tables are like the little tabs across the bottom。

 the columns are are the attributes and the rows or the tuples and in a spreadsheet we commonly have that first row。

 have some metadata about the rows And sometimes even if you're sorting a spreadsheet。

 It's like do you want to not sort the first row because it sure looks like the names of things。

 And that's actually something that we do inside of databases as well we call that the schema。

 and it's much more formalized then hey， let's use the first row to represent the metadata about what's in the row。

 But really you can think about these things as a large spreadsheet as a software developer and that's the beauty of the abstraction is that you just sort of say。

 you know what this is Oracle is a multibillion dollar company and they spent decades building something really fast。

 I'm going to pretend it's a big fast spreadsheet And that's how it makes。



![](img/5c5e71af4f5906ee27f4b90c419211d0_9.png)

Our lives's easier as a software developer。So I've already mentioned Oracle。

 There's a lot of different database systems out there， and I've taught most of these。

 and Ive used I've used on this screen。 I've used every single one of these at one point or another in my career。

 and that's one of the cool things about SQL is that you learn like 80% of it。

60% of it and literally in all these things。 It's the same。

 I've taught SQL light to use in Python I've taught my SQL to use in my web applications for everybody class and I'm teaching Postgres。

 and I've used Oracle professionally and I've used SQl server professionally and Hsql used in an open source project。

 So everything on it I have used every one of these。 and so SQl server。

 I'll start from bottomom SQl servers for Microsoft it's one of Microsoft's very strong products and so don't feel bad if you end up on Microsoft。

 I usually feel bad when I'm using Microsoft stuff。

 but the Microsoft SQl server as a solid piece of software。 my SQL。Used to be my favorite。

 but Oracle bought it。 And so it's technically open source。

 but there is a certain fear in the marketplace that Oracle is potentially going to like bend it towards commercial and say well。

 here's the crappy open source version。 And if you want the speedy version that you have to pay for。

 they haven't done that yet。 Oracle is the is the gold standard。 It is large。 It' commercial。

 It's enterprise scale。 It's very tweakable among all these。

 It's by far the most annoying and complex to maintain。 I I。Dislike Oracle。 I mean。

 I've run all these。 And every time I touch Oracle， it's like。

 oh I got to write myself long documentation about how to do the simplest of things in Oracle。

 I'm sure if you're an Oracle expert， you're like， oh， but it's so easy。 I'm like， yeah。

 the other to me， Oracle is harder than all the other ones combined together as far as I'm concerned。

 But in commercial situations。 It's what's going on。 Now。

 Postgres is the 1 Ive I'm teaching most recently。 As a matter of fact， right now。

 I've never used Postgres professionally。 I've never used an open source project。

But because of the questions that have been raised by my SQL about my SQL。

 I think the market is gently drifting toward Postgres SQL。

 and so companies that I know are going to Postgres because it's free and open source and it doesn't have the cloud the way my SQL does。

 and it has a lot of features kind of like Oracle， and so historically Postgres has more features。

 Oracle and Postgres always had more features。 My SQls catching up。Okay， that's a long story。

 My scale is catching up， but in the catching up， they might end up being you might have features that only come in a commercial version of it。

 So it's like。Let's just use Postgres SQL going forward and so that's why I'm teaching you because what I want to teach you in this class is some of the more advanced features that are part of Postgres SQL and I want to teach you an open source project product so where you're in Postgress SQL。

 it's all open source， there's unlikely that it'll be anything but open source going forward and it's a very feature risk rich database。

So coming up next， we're going to talk about SQL architecture and how it is that we can start writing SQL statements。



![](img/5c5e71af4f5906ee27f4b90c419211d0_11.png)

![](img/5c5e71af4f5906ee27f4b90c419211d0_12.png)

![](img/5c5e71af4f5906ee27f4b90c419211d0_13.png)