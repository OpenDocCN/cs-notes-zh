# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p22 22_05_02_数据库工作原理.zh_en -BV1Kt421V7EE_p22-

Hello and welcome to our lecture on SqL。 So this is a very， very short introduction to SqL。

 I love SqL。 I was talking to a student the other day and they were like SQL is my favorite language and I said I have to agree that SQL is my favorite language too。

Because SQL is so beautiful， you don't even need to write loops in SQL。

 we write loops in languages like Python just because we have to The problem is is that SQL is just is perfect but its not the way we could write something as complex as Linux or Python and so SQL is not really the way computers think we have these things called database engines and these database engines make things work really。

 really well and so SQL is a great way to organize data but a lot of work has gone into keeping that data organized and making it at simple so it's like there's this abstraction and it's a lot of work to make that abstraction work。



![](img/9b576f4b7514796060a00160051b8dd2_1.png)

So I want to start out with a little bit of history sort of before databases， and you might think。

 well， before databases。How could that be， well， it's in the old days and if you watch old computer movies featuring computers。

 see pictures that have these you see pictures that have these tape machines in the background and they're spinning and the spinning of the tape machine is the sort of physical manifestation of computation。

And it had to do with the fact that in the old days computers did not have enough data to store all of their data in the memory or on a disk。

 we didn't even have disks in the early days， in early days tapes were what we had and we used kind of an variation of audio tapes and instead of on audio they contained data zeros and ones。

And so the way things would work in the old day so that you could have a database as it were was the database was all of your data recorded onto a tape and the key thing to a tape is that it was a physical thing and so you had to rewind it。

 go forwards and backwards。Most of you probably never even seen a casette tape or annatere tape or a real to real tape。

 but it's a physical long。thousand0 foot piece of plastic and to get the date at the end you had to spin it until you got there and so it wasn't what we call random access。

 which means that in a random access， whether it's memory or the disk drive。

 random access allows you to get to any place roughly in a monthly fixed amount of time whereas if you're close to something on a tape。

 you can get to it very quickly if you're far away。

 you got to go bo and then wait and then come back。So this led to a pattern where。

Every night we would create take the tape from yesterday's account bounces。

 let's just say we're a bank and we're people coming up the window putting in money。

 taking out money and then what we would do is we would put all of the transactions sometimes on physically punched cards and then we would sort them right and let's just say we have 26 accounts and you know person C shows up with a little you know you know ads $10 in person F shows up and subtracts $10 and et et and then what we would have at night we would get these all sorted and then we're physical machines that would actually sort these and in the earliest of days and then we would have the old balance A。

 B C， D， E F sitting on a tape in order sorted in order。



![](img/9b576f4b7514796060a00160051b8dd2_3.png)

And we would start a process after the bank closed where we would read the first record off the tape like a。

 we would read the first。Transaction off the the cards， and we would compare them。

 and if the tape was。Earlier than the transaction or lower。

 we would just copy it so we'd copy it and then so the B would compare to the C and B would get copied and then C would come across and then we'd realize that the C data we would have to update the C data and add $10 to the balance and then we'd write that and you'll notice as we're writing this we are sorting its ined order then we would copy D we have nothing for D and it would just get copied we would copy E we'd have nothing for E and it would just get copied and then we would have oops forgot to put F on this picture we would have F and we'd subtract 10 and we would copy it and then we would be done。

 we would be done with the kind of stuff that we had to do that night and then what we would do is we'd have this new updated data that was all sorted in account order and then the next night we would move the tape the new would be the old tape and we would do it over and over and over again and sometimes these processes would run for four or five hours because the tapes were longer or it got to be multiple tapes and so。

of computing was done sort of after the banks closed at five o'clock。

 then a group of people would come in， we called them operators and they would mount these tapes and run these jobs and just sit there and watch these tapes spin as the data was being copied from one to the other。



![](img/9b576f4b7514796060a00160051b8dd2_5.png)

![](img/9b576f4b7514796060a00160051b8dd2_6.png)

And so yeah， that's pretty cool， thankfully that's not how we do it anymore。

 the thing that made it so we don't have to do this is the invention of disk drives。

And disk drives are magnetic media， just like tape drives。

 but the difference was as they were on these spinning platters and so what you could do is the data was in series of concentric circles on these platters and then you had a head that could move in and out rapidly and so the speed at which you could access data was a combination with the speed at which the head could move to a certain cylinder and you had to wait until the data came around and so sometimes you would have a know 5400 revolution per minute so that means that 5400。

5，000 times per minute。

![](img/9b576f4b7514796060a00160051b8dd2_8.png)

Which is 100 times a second， can I get yeah 100 times a second？Yeah，100 times a second。

0 times a second， you'd wait hundredth of a second for it。

 And so this is way better than waiting like。

![](img/9b576f4b7514796060a00160051b8dd2_10.png)

A minute and a half， two minutes， and even 10 minutes to spin up a tape。

And so the problem was then we're like， okay now that we have this wonderful technology。

 we can store all of our nightly data on a disk because it's enough space。

 how do we build technology to make really good use of this and a lot of research。

 a lot of computer science， a lot of vendor research went into understanding how to best use this new disk thing。

 I remember talking to people like because we used to use a floppy disk which where they were much slower so they didn't go 5400 so it might take a quarter of a second to move the head and it might take almost a second to spin it around。

 which was still way faster than 10 minutes right so it's like about a second to get to anywhere on the floppy disk。

And we would build。Approaches to storing data and you we would start with this physical thing and you' would hear it grunting and moving and grunting and moving and then you would come up with a better way to store the data and then it grunt moved less and your thing would go faster so this was like a research thing it was like。

It was good old days when computers actually made noises and could change your code inside computers。

And the first thing of course we did was just took those sequential master updates and put them on。

 but that turned out to not be the best and that was sort of the research is not just how can we do what we used to do on data that couldn't be random accessed。

 randomly accessed and instead say let's take advantage of it and so a lot of research。

 a lot of vendors there was a lot of very expensive software that people bought to say， look。

 you you're a bank and you really and truly want to you know how this works。And so what happened was。

In the 60s and 70s， the computer vendors were fighting and they would come up with a technique。

Which compared to our current database technique was just trivially simple。

 but it took a lot of work back then。And they would fight with all the other computer vendors and they would say our index sequential mechanism is better and vendor2 would say our networked approach is better and then they would sit and they would sort of struggle with each other and then the poor customers would be like。

 I don't even know what you're talking about and so then they would just buy the stuff from the vendor who took them out to golf or the best lunch or took them out a trip to Florida and then they would just adapt to whatever that vendor did。



![](img/9b576f4b7514796060a00160051b8dd2_12.png)

And so it was really kind of scary because we were moving into a place where you were locked into a vendor and then once you're locked into a vendor。

 you're in bad shape， and so the US government in particular had a ton of money and were buying tons of computers。

 both you for normal data processing and for strategic things like you know。

Military stuff and so they were buying tons of computers and they knew that these vendors if they got to the point where they locked them into a single vendor。

 that the vendor would just be able to dictate the price and so the federal government through NIST。

 the National Institute of Standard and Technology decided that databases needed a standard。

 they needed a way so that we could talk to any database from any vendor using the same technique and not have to。

You know do one vendor and then if you switched vendors you had to completely rewrite your software and so they didn't the NIST didn't specify how this abstraction the standard was going to work。

 they just brought the vendors in and said we're going to stop using your software if you don't come up with a standard。

And it was a perfect time because even though the vendors thought they had everything was perfect and wonderful。



![](img/9b576f4b7514796060a00160051b8dd2_14.png)

there was a lot of upside and in particular there was this concept of relational databases which back then was more of a mathematical theory of a better way to store and retrieve data than it was a practically implemented available technology and so SQL and this is Liz Fong who I went and I did an interview at NIS she talks about the early days it's a great interview the early days of how this SQL standard really made so much sense and really fixed the industry and got the industry working really nicely and I recommend that you take a look at this video just so you can kind of see。



![](img/9b576f4b7514796060a00160051b8dd2_16.png)

Now what SQL basically said was is that let's not worry so much about where that data is actually on disk because the earlier database approaches were we programmers would know that there was cylinders and positions and we would place things in certain ways and we would make indexes and we would look at the indexes ourselves。

 all kind of different things or we would read to one place on the disk and that would have an address of the next place we're supposed to read on the disk and。

They said， you know what， let's not worry so much about the physical storage structure on the disk。

 but instead。Let's come up with a language by which we can express what we want to。read write。

 update and delete on the disk and a really simple language and then we can build a piece of software that there's could be many disk formats underneath that and then we could all sort of just use this language and you could buy vendor A and use this language and vendor B and use this language and then you could even benchmark it and say here's a bunch of stuff in this language which vendor can run this faster and so the NISist also had a series of benchmarks TPC or some of the benchmarks。



![](img/9b576f4b7514796060a00160051b8dd2_18.png)

And so what they did is they basically made it so that this was like a beautiful and simple language and it's what we call SQL。

 I think at some point it was called the simple query language and it is the language that we used to talk to databases and the interesting thing is what SQL allowed us to do really in the 60s and '70s when it first came out was to talk to the oldst databases like index sequential and network style databases。

 and as this new form called relational databases which had like this awesome mathematical underpinning。

 but was implemented badly in the first time， we could just say。

 oh weird kind of is when the performance of relational databases got to the point where it was as good as the other databases then we could just switch and we could talk the same SQL。

 so it allowed an amazing innovation over a 10 or even 15 year period where the abstraction allowed us to improve databases。



![](img/9b576f4b7514796060a00160051b8dd2_20.png)

In a wonderful way， without really having to change how we as programmers use them。



![](img/9b576f4b7514796060a00160051b8dd2_22.png)

Pretty dang， Asome， I'll be honest。And so I've been talking about this idea of relational databases and relational databases。

 and I'll admit that when I first saw relational databases in the early 1980s， I'm like this is crap。

 because again， I could hear floppy disks and I knew that we were moving a thing and I had so much awareness of what was going on and I loved that awareness。

And the relation database is sort of like that hid what was going on behind this layer。

And it turned out that whenever I used it， it was slower because it wasn't yet clever。

 and so relational databases started out as a mathematical idea as the theoretical best way to represent networks of data。

With columns and rows and connections and joins， and we'll talk about all that eventually。

And it was a beautiful idea and the mathematics was right。

 it just took a long time to get to the point where it turned the superior mathematics of relational databases worked out better than the highly cleverly optimized previous generation database systems。

So there's a lot of common database systems that you'll run across， some of them are open source。

 some of them are commercial， Postgres and MySQL are open source。

Postgres is probably the more intricate complex and rich Oracle is an intricate complex and rich database that's available for lots and lots of money and Microsoft has a database called SQL server and all these databases that we're seeing evolved in a sense after the SQL spec existed so they just kind of built SQL there was legacy databases that kind of learned SQL and there's lots of other database SQLite is what we're actually going to use with this course and it's super cool。

 super fast and on your cell phone you probably have 40 copies of SQLite and in your car you probably have 40 copies of SQLI because it's a real tiny embedded database it's not really good for production scale when you got 100 users simultaneously hitting the website Postgres MyQL or Oracle or SQL server are really kind of online multiprocessing real multiprocessing databases but SQLite is great because it's really simple。

stores everything in one file， we can move the file around， et cetera。

 so I love SQLite and in this class and in this thing we're going to talk about SQLI。

 but everything we talk about applies to all of these different database systems。

So the first thing that you've got to do when you are going to work with a database is you' got to come up with a contract between you and the database as to what the shape of the columns are。

 how wide the columns are， what kind of data you're going to store in this and it then informs how the database software is going to structure that database like on the disk and part of what you're doing is you're allowing the database software。

 minusQL or Postgres or SQL light to super optimize it storage， I mean it's so much smarter than you。

 something like Oracle or MySQL or Postgres probably represents a billion dollars if not more of research and development about the best way to store and retrieve data and you just don't even need to know any of that。

 you just say look， I'm going to have these columns it's going to have 100 characters of text that I'm gonna to have an integer and then a flowing point number than 3000 characters of text and you worry about all that detail。

But the key is is if you just say， a I'll start anything I want。

 then it can't optimize and so there's this thing where you have to make a contract at the beginning and say this is exactly how I'm going to lay out the data as I talk to the database system and then。

You can figure out how to lay out the data in the actual disk and so that's called the schema or the database model and building a database model is itself a cool thing so if you're given building a complex application you have these models and have connections and well eventually talk about all that stuff。

 but it's a critical thing to say that that's a contract between you and the database software so the database software can optimize the storage of the database now once you have given the schema then you can write queries that。

know depend on that schema， so you might have a column called email and a column called name。

 and then you can insert data into the database using that schema。

 you can retrieve data using the schema， you can change data sort of somewhere deep inside the database。

 and then you can delete data。Hang， I sec。Whoa， hi there， what are you doing down there Oh dang it？

Sorry， sorry， you are a bad creature。아게 돼。I was wondering what that noise was。Come here， come here。

 come here， I got to introduce you to all these folks， come here。During。You。Are not。Behaving。调啲写一下。

This is Shelby hi Shelby this is Shelby， this is my puppy。

 I'm trying to keep her out of the cage and let her sit and get by my feet and she's got some two toys hi Shelby。

This is Shelby and she is interrupting， you're interrupting my lecture。But you're cute。

 so put chew in on a pen， chew on your two toys that I gave you， okay。

 let me get through this lecture。Okay， you can get down。Just quit you an honor。Sorry about that。Dog。

 dog interruption。I was just hearing chewing noises and I thought I took everything but then there was one pen on the floor and so the pen。

 poor pen meets Mr。 Puppy oh well。Okay， where was I？SQL CR， create， read， update， and delete data。



![](img/9b576f4b7514796060a00160051b8dd2_24.png)

And so our next step is to actually do some SQL and create a database。

