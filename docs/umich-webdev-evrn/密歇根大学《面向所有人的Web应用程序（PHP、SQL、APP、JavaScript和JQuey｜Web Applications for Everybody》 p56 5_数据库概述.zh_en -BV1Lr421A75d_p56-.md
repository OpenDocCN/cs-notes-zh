# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p56 5_数据库概述.zh_en -BV1Lr421A75d_p56-

![](img/f00d7ad751f8a85a536c238db13bba44_0.png)

![](img/f00d7ad751f8a85a536c238db13bba44_1.png)

So welcome to our lecture on relationlational databases。 SQL is a beautiful programming language。

 I sure hope that before you start this lecture you already know how to program because。

Once you learn SQL， you might not want to learn any other programming languages。

 and unfortunately you can't just do everything in SQL， I think that's kind of unfortunate。

But I want to take you back a little bit in time。 The notion of storing data。

 the first computers computed， right， they computed。

Trajectories and weather and computations are sort of like inside the computer。

 But when you start doing things like banking and things like that。

 the data doesn't fit in the computer， and you have to have some way of storing larger amounts of data than the computer can hold within itself。

 And so there was a time。 you may not believe this before we had disk drives。

And so we had tape drives。 Now， some of you were so young。 You don't even know what a tape is。

 but we used to have these things called cassette tapes。 and you'd play your music。 And。

 and if you wanted to go to another song， you'd have to fast forward and have to spin for a while。

 you couldn't just hit the next button and immediately go。

 That's because music players have random access memory， but tapes did not。

 meaning that you had to physically movement。 You could store a lot of data on them。

 but you had to physically find the right place。And so imagine the problem that you're facing is that you're a bank and you've got a tape drive。

 which is sequential media that youve got to read one thing at a time， just a loop。

And you have all of the accounts and all the current balances on that account。

On those accounts at the end of yesterday。 And then today， people put money in and took money out。

 And then we need to come up with the new account balance at the end of the day。 And literally。

 if you go back to the 60s and the 70s， this is what happened。

 your bank balance might only be updated once per day。 because we couldn't store all the stuff。

 And we didn't have spinning disk drives that do this。

 So here's a really cool algorithm that we used back then called sequential master update。

 And the way it worked was you would have all of your records sorted by account。

 So the lowest account number is first account 1，2，3，4，5。 But they' in sequence。

 you can't just bounce around in here。 And then you would sort you know 1，23，4。

5 would be the accounts， and then account 3 and account 5， account 3 is -100 and 5 is plus 100。

 So how is it that you can read this data and then produce a new data because you can't rewrite this in place。

 because as soon as you rewrite this， you start to destroy its data。 So this was the trick we called。

Sequential master update， you can go read up on this on Wikipedia and what you would do is you would write a program that would read the first record。

Record one， and it would read the first。Transaction， and that'd be three， and I would say， well。

 we haven't got to three yet， so one just gets copied， so we put one on here。Then we would read two。

And we compare it， we still have three， and then we copy two to the output。

 and then we would read three。And now three， we would be able to combine the subtraction and put the new balance for three up。

And then we would read to the next。5， we get number five， account5， four would get copied。

5 would be brought in and modified， and then a new five would be changed。

 And you can kind of see how this thing you could have thousands and thousands of transactions and thousands and thousands of records all in order。

 And at the end of the run， you would have all the new balances on a new tape。

And then what you would do is the next day is you would take this tape and you would make it the old tape。

 Actually， what you often did is had like five tapes。 So you rotated a last week's tape。

 last month's tape， we used those as backups。 But this notion that we had to take time to work through data sequentially。

 And if you've written Python programs in any of my Python classes， you say。

 go and like one second later， unless you ran some of the later stuff like the scraping or the email stuff that might take days to run。

 And this took a long time because you physically had to move a tape across。

 And so this might take two hours at night or three hours at night。

 and this whole concept of sequential master update。

 But the problem that we were solving was we needed to have permanent storage that was lasted longer and was much larger than the storage inside of computers。



![](img/f00d7ad751f8a85a536c238db13bba44_3.png)

But， of course， that was only for a while。Ultimately， what we ended up with was disk drives。

 And the key thing to a disk drive。 if you tear one apart。 And eventually， we're going to have SSds。

 which are even more random。 But the idea of a disk drive is always spinning。

 And if you have a disk drive on your computer， you can kind of hear this worryring noise。

 And you had this head that moved in and out。 And so instead of having to read all of the data sequentially。

 what you could do。Is if you needed to read this piece of data right here。

 you would move the head to the right location， and then you would wait until it came underneath the head。

 and then you'd read the data。 So if you think about the disk drives。

 there are often like 7200 revolutions per minute。And there is like， you know。

2 millisecond access time。 And that's how fast this head could move back and forth。

 This goes around 7200 times per second。 It's not take much to calculate on average， to get from。

One piece of data read herere to a different piece of data read here。

 It is the time it takes to move the head and the time it takes to wait for it。

 And with with the speed， the revolutions and the speed of the head。

 you could kind of calculate that。And so databases came out of the notion that whileow we didn't have to wait till 10 o'clock at night to update the data。

 we could store an account record here， an account record here， an account record here， and you know。

 a thousand times a second we could go read and write an account record。And the question， of course。

 wasn't just how to do it because that they're simple ways。

 but you'd still have to read all the data and then read all the data round and round and round and round and around。

 And it would still take like an hour to read all the data。 So think yourself。

 is there a way to sort of skip ahead and know every record。

 We have a little table contents that's right here。 And it's a little thing says record 1 is here。

 Record 2 is right there。 Record 3 is here。 Record 4 is here。 Record 5 is there。 right。

 And so I can say， I don't have to read all of them。 I can just say， I want number 5。

 I look up in the table contents。 and I jump over there。 That's called an index。

It's like breadcrumbs， a way for you to go back where you were。 And so instead。

 when you write the records， you'd write a little tiny thing about where they're at as a way。

 a shortcut to get to them。 And you had to read the whole index。

 But the index was generally small compared to the amount of data that was being indexed。

 and we'll talk about that as we build these things， What gets indexed， what doesn't get indexed。

 how what rows and columns。 But this was all about how to make the best use of this amazing new technology to make it so that you could check an updated bank balance within a second rather than within a day。

😊。

![](img/f00d7ad751f8a85a536c238db13bba44_5.png)

So relational databases are a technique， so when we were figuring out how to best use this random access storage。

We're computer scientists。 we would argue we would say I have an idea。

 sort of like the picture I just drew for you。 or another one I'd have a different idea。

 And so there was in the 60s and the 70s， a debate as as to the best way to make maximum use。

 And there was things called index sequential and network databases， et cetera， et cea， et cetera。

 And out of that debate came a standard。A standard way of thinking about it。

 And it's really quite ironic that the relational databases is a rather theoretical。

 not practical thing。 And I'm kind of a computer scientist。 And so I'm always'm always。

 it always appeals to me to do basic simple things。

 And I know when I first saw my first relational database。 I'm like， this is way too fancy for me。

 This will never work。 I give me something crude and practical。

 And I can just sort of code and do the thing I want to do。

Those first relational databases were pretty terrible。 But then as they got better， I'm like， oh。

 wow， this is so magical。 And I don't even want to begin to know how this magical stuff works。

 And so that's what we get。 There's powerful underlying mathematical theory that makes relational databases work。



![](img/f00d7ad751f8a85a536c238db13bba44_7.png)

Now， our our view on to relational databases is a language。

 And so instead of you knowing how that data stored on the hard drive。

 you are going to talk to a very complex and powerful piece of software called a database server。

 So my SQL is this database server。 And it knows where all that stuff is at。

 It's got indexes hundreds of millions of hours of computer science when into writing My SQl or oracle or some of the database system。

 But what we did is we end up with this really simple but beautiful， elegant way to say， hey。

 this is the data I want。 You are a genius。 You go figure out how to get it to me and get it back to me as fast as possible。

 That is SQl structured query language。 SQl is a interesting。Bit of computer technology。

 And I've got a video interview that I did with Elizabeth Fong of the National Institute of Standards and Technology。

 I encourage you to watch the video。 But the short summary of the video is。

 is that while the US government in the form of Nist can take some credit for S， Q L。

 what Liz will tell you is that the vendors were sort of fighting amongst themselves。

 and they were fighting with the government。 And what they're trying to do is each of them had their favorite idea and they're telling the government。

 you should adopt our favorite idea So because those other companies's favorite ideas are really bad。

 And other company say， no， no， no， their favorite idea is bad， you should adopt idea。

 and the government who was buying lots of technology basically said， look。



![](img/f00d7ad751f8a85a536c238db13bba44_9.png)

We are not going to pick vendor A over vendor B。 What we' are going to do is you are all going to get into a room and you're going to agree on a way for us to talk to all three pieces of software。

 We're not going to tell you what that's going to be。

 But until you come out of that room with one agreement。We're going to not buy any of your products。

And so that's how SQ L happened。 The industry came together， as Liz will say in the video。

 she will say that it was the perfect time and that it wasn't too early。

 meaning that all the vendors had good ideas about what they thought was good database。

 And it wasn't too late， meaning none of the vendors had sort of by Hooker crook become dominant。

 And so SQL is this magical thing。 And again， I told you before， I just loved this language。

 And it came out of this really interesting consensus process that was convened by the US National Institute of Standard of Technology。

 but not created by the National Institute of Technology and Standard Nist。

 So SQl is this abstraction。 It wraps complex software。 Lots of storage in a very elegant thing。

 And some of you maybe used Microsoft access or something。

 And you've even typed a select statement or an update statement。

 And you didn't even realize that you'd learned a programming language。 And like I said。

 it's one of the more elegant ones。 And what it does is it basically says。😊。



![](img/f00d7ad751f8a85a536c238db13bba44_11.png)

The things we do in databases are we put stuff in。We delete stuff。 We update stuff， and we read it。

 Crud， create， read， update， delete。 It's in order。 So it sounds better。 create， read， update。

 delete Selectlect is the we don't call it read。 We call it select。

 But crud is the idea of the four basic operations of databases。 And S Q L said， look。

 let's make these four operations that are so common and done all the time。 super simple。



![](img/f00d7ad751f8a85a536c238db13bba44_13.png)

Nothing about how it's going to be stored， Nothing about where it's stored。 Just what do I want done。

 Delete that row。 Get rid of it。 I don't know how。

![](img/f00d7ad751f8a85a536c238db13bba44_15.png)

Just get rid of it。And so if you read database documentation because of this background that was sort of a mathematical theory that underpinned all of SQL。

 you'll read documentation that it's like there's two SQL， two ways of describing it。

One is like what we nerds describe it as like its thing with rows and columns and tables。

And then the math people would say， well， it's not exactly rows and columns and tables。

 it's relations in tuples and attributes， and connections between relations and tuples and attributes。



![](img/f00d7ad751f8a85a536c238db13bba44_17.png)

![](img/f00d7ad751f8a85a536c238db13bba44_18.png)

And and while I'm making fun of the mathematicians。

 the mathematicians are the ones that make it go really fast， right， We programmers' like。

 that's slow。 oh， now it's fast。 thanks for the math。 right， That's how it kind of worked out。

 I mean， I love the math， even though whatever。 So what I'm saying is if you're reading documentation。

 You'll see me talk about rows and columns and tables because I'm a nerd。

 That's the easy every every person's view of this， rows columns and tables。 But if you read stuff。

 and you see relations and tuples and attributes， you know， don't feel bad。

 don't feel like somehow you don't know what's going on。 You know。

 And so you can read this sort of more highfalutin version of the language of database。

 and understand it really is fancy ways of talking about rows and columns。

 And I like to think of a database。 And some of you may have already used something like access that really gives a very spreadsheet like view on a database。

 right， rows and columns。 tables are kind of like tabs， right。

 you got these tabs at the bottom of a spreadsheet。 We got rows and columns。😊。



![](img/f00d7ad751f8a85a536c238db13bba44_20.png)

![](img/f00d7ad751f8a85a536c238db13bba44_21.png)

Now， the one thing that's interesting is one of the things that we've kind of come as convention and spreadsheets software even kind of knows about this is we use the first row as actually not data。

 this is data。And this first row is metadata。It's not much metadata， but it's not real data。

 it's metadata， it's a data about the data。First column is title， second column is rating。

In database， we are going to do this a lot。 We're going to call it schema。And we're going to be very。

 very precise about what each column is， how big it can be， what kind of data can put in。

 what's the character set of these things， and so we actually write very complex statements about what's in a column in a database we'd say this is an integer that can be no more than 2 billion。

So less than it's an integer with a sign that's less than or equal to 2 billion。

 and that's what we'll say rating is。 And so we put a lot of detail in。 But again。

 it's still kind of the same thing as the first row of a spreadsheet being the metadata about what's in each of the other rows。



![](img/f00d7ad751f8a85a536c238db13bba44_23.png)

The database system that we're going to use in this class is free minus QL。

AndThere's also a version of kind of a forkca MyQl cover or IDb。

 that's also roughly equivalent for this class， but it's not the only one。

 And there are really good database servers。 Oracle is probably the largest commercial enterprise scalable database that lots of companies and corporations use。

 Myql is kind of like the database used for lots of the web， then there's SQL server。

 which is Microsoft if you're Microsoft shop。 Every time we've talk to just about everything will be just fine if you're using Microsoft and access is kind of a light tool that it helps you write SQL often and there's lots of other databases like Postgres is another very popular open source SQLL。

 HSQL。 if you took my Python classes， we played with SQLL in those classes。

 But now because we're walking working on building web applications。

 we've switched to using the MySQL database server。



![](img/f00d7ad751f8a85a536c238db13bba44_25.png)

So that gives you sort of a bit of a history and a context about SQL and then coming up。

 we're going to start talking about typing some SQL and just doing some work。



![](img/f00d7ad751f8a85a536c238db13bba44_27.png)