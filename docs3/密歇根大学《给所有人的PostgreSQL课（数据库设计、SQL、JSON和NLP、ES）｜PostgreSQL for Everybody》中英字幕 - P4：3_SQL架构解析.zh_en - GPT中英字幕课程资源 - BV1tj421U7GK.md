# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P4：3_SQL架构解析.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/12e0cc48ef0e3bf4b5e51d393318f9a8_0.png)

![](img/12e0cc48ef0e3bf4b5e51d393318f9a8_1.png)

So now we're going to talk about how we actually run SQL commands to talk to the SQL server。

So even though you may be running everything on your laptop or you may be running it in a server with the SQL server。

 running on the same hardware as as you're running your SQL commands。

 the best way to think about SQL is that there is often a database server。

 and so in production systems and in scalable systems， in effect you have a client。

 so this is a client and then you have a server。The client server might might be on the same computer。

 but the key thing is， is to mentally understand that this client is very different software than the server is。

 The server is the magical software that comes from。

Decade or more of amazing software developers who figured out the math， the joins， all this stuff。

 the magic performance。 just let's thank these people who wrote these servers and how smart they are so that we don't have to be that smart。

 Now， if you want to be computer scientists， you can spend your whole career making one tiny corner of this。

😊，A little faster。 And that's what PhDs are written。 PhDs and computer science。 In fact。

 if my master's degree could be thought it's a dot that's so small that you could barely detect it。

So a lot of smart people have made this database server。

 What we do is we basically type in SQL commands and we send them to this server and then the magic happens and there's disk drives and stuff like that。

 data comes in and out。 there's memory it's all cached。

 all kinds of fun stuff and then we get our answer back right And so the way we perceive this is we talk to some kind of a client which forwards the commands to the server。

 which does all the work and then gives us this thing back and so you can have a software that runs in a web browser like Postgrecent bin or that can run as desktop application。

 but I'm going to focus on using the command line。And I'm going to teach you most of this class to use command line everything that I'm going to teach you you could use in the other clients。

 but I like command line in particular because it's easier for me to document and I'm not spending so much time making screenshots。

 but it's also more accessible， meaning that people the visual impairments can use the command line。

 I think a lot more naturally than some full screen software。

We're going to do Postgres on the command line。 The other thing that I'm going to do in this class is I'm going teach you Linux Now most of what I'm going to teach you in Linux would work in Mac OS under the terminal it could work in Windows with the bash shell if you're doing that but I'm just going show you the Linux and if there's a little bit of adaptation that you have to do or if if the output is a little different on Mac or Windows bash or you can figure out how to use Windows native I just think ultimately the world is accepting the fact that on the servers we're gonna to run Linux I mean。

 Linux on the desktop， that's a different kind of religion but Linux on the servers is just done So'm thiss a lot of stuff we're going to do on servers and so I'm not going to hide it and I'm going to teach you Linux so we have a dollar sign prompt it's Linux and I to show you one command sorry I've taught a lot of classes that I just have to say in Windows in Mac Linux actually what I do is I。

Windows and Mac and never teach Linux which probably was the wrong thing Now I want to teach Linux and not Windows and Mac Okay chuck back to your back to the lecture okay。

So。So the client， remember， there is somewhere magically out there on the other side of the Internet。

 a database server。 This client， PQL， is a client that we're going to run locally。 Now， somebodydy。

 either you or us have set up a Postgres server out there。

 And there is when you connect to that server， an account and a password and based on that account and password。

 you get permissions in the server。 So when you first set the server up。😊。

You create what's called the super user and there is the Postgres and Postgres is the super user。

 and that's what we're saying here。 Let's log in as Postgres。

 and then you have made a super user password， Usually that's part of the install process。

 You may or may not have this。 It's okay if you don't。Then we get the prompt。

 and so it's a command line prompt and the pound sign is kind of the UniX old school way of saying you are the super user and you can do things in particular we can create other users。

So this is a joke from XKCD。 I love XKCD in particular because he makes his comics creative Commons attribution which means I can put them in this lecture。

 So this person on the left says make me a sandwich and the person on the right says what make it yourself and the person on the right said S you do pseudo make me a sandwich and the other person says okay So what's going on there。

 So S do is a Linux command to upgrade your session from a regular user to a super user so you might say you know delete these files with an RM command and it won't do it。

 but then you say S do pseudo Rm and it works。 And so this is you know this is basically pulling the whole concept of superus into a human context and this is I've seen have many friends that have this as a t-hirt So you're starting out as a super user like I said。

 you may not be a super user and so some of these commands that I'm going to show you that super users do you may have to have someone。

I'll do them or we may have done them for you already。

 and you know this every time I'm showing you a super user prompt because it has the balance sign。

But this backslash L command is the command to list the databases and this is a Postgres server instance that I just started。

 and you'll see that the owners of these three databases are all Postgres。

 which is the super user and these are databases that you probably shouldn't touch because these database systems tend to store their own database in databases。

 and the reason for that is efficiency because they have figured out how to make stuff in database accessed very fast so in a sense when you make your own database or create a table in your database。

 it stores that information in its own database tables。

RightAnd so and so you delete these and then Postgres is going to start blowing up in a bad way so right now I'm showing you how to see the databases and for now there's no databases you're to mess with at this point these databases will change based on commands that you're going type to Postgres but don't do anything to these don't think oh I'll save myself some disk drive so I'm going to delete the Postgres database well then Postgres will stop working。

Maybe to warn you， I at never even tried， so I don't know what happens because I'm not going to do it。

Okay。So the first thing that you want to do is you want to create your own database because you're not supposed to mess with the ones that are already there。

So this is your first SQL command， and so I'm putting them all in uppercase。

 they don't have to be uppercase。The first thing we see about S， Q L is S。

 Q L is a little wordier than most programming languages。

 And that's because single SQ L statements are so powerful that we want to be able to have the best chance of sort of reading them。

 So we don't just like， we don't call it C U Z for create user。 We call it create space user。

 That's actually one command。 So create space user。 And I'm going to make an account。

And then I'm going to say with password and I'm give it a password of secret。

 and then I'm going to say create database people Now database contains multiple tables with owner Pg free so now I have in my database server I'd made a new empty database and I have access credentials that I can get in to that so my SQl client can now talk to that database as long as I present these credentials and then backslash Q gets me out of that particular session because all I really wanted to do is the super user was create the user and create the database now。

In your situation， you might have been handed a database， user and password。

 and that's enough to connect and start doing stuff。

 And so I'm just showing you this in case you're doing this all by yourself on your own computer。

 how to get the whole thing started。So now we're going to connect to the database。

 And so we're going to say PgSQL start the client under at Linux， name of database， name of user。

 and then you enter your client right So now here you got this database people。Sitting on a server。

And then we have some credentials that allow us to get into that， so that's what we're doing okay。

And now for me， the first thing I was do is like what's here， you know， in Linux I type LS or PWD。

 like where am I at and what do I got？And so the command in Postgres。

 oh you'll also notice we're not super user anymore right And and that's because you want to be careful when you're the super user in a sense。

 you want to type as few commands as you can in the super userer We are now a reduced user so we could have lots of different databases in here with different credentials。

 but this particular Pg free is only can't break any of these things。

 And so you sort of want to keep your credentials scoped as low as you can and not use the super user except to make credentials and then use those credentials to do everything else。

 And that's kind of what we're showing here。 Dt shows the tables but this is a good example of where you see sort of two terminologies。

 Theres Dt says tables and then we hear relations。 So relation is the more hoity2y of of the terminologies and tables is the more like。

I'm a nerd version of those terminologies， so we have no tables and we're not a super user。



![](img/12e0cc48ef0e3bf4b5e51d393318f9a8_3.png)

So let's make a table。So here we go， we're going to make a table。

Create table the name of a table and then the parentthesized list of schema。 Now this schema。

 remember when I talked about the spreadsheet， the schema is our contract with Postgres that says this tables got two columns and it's got two character columns and each of those columns is up to 128 characters long。

 This is the schema we're making the schema here and it's a contract meaning if you try to put 129 characters into this。

 Postgres is going to blow up and you're like， oh， you're so mean Postgres No。

 Postgress is doing what you told it to， you told it that you're never going to store more than 128 characters。

Why is it so picky about this？ And that is because Postgres takes every hint that you're giving it about the shape of your data。

 and it's storing it as efficiently and most compactly and fast retrieval。

 And it's got to solve a lot of problems。 So you have to tell it。

 what and how you're going to use it。 And if you want it to store 129 characters。

 just store 129 characters。 But don't tell you're going to store 128 and have it build a whole structure efficient for storing 1。

28。 And then try to store 1，29 and complain about it。

 Now that we'll see there are plate ways to store this data to say， look。

 I don't even know how long it's going to be。 just give me a space。 and it does。

 And it does that as efficiently as possible。 But if you know you're going to be 128 or less。

 then tell it。Yeah， so that's what we're doing。So we have this kind of column name and then data type。

 comma， column name， data type， and then parenthesesis。

 this parenthesesis here matches the user's parentheses。

 and then you end these things with a semicolon。And so now I made it table。

And I can see the table and I can see， oh yeah okay。

 I've got a table named users it's a table and the owner's PG free Now I'm not super user because so I only am seeing the ones that belong to me which is pretty cool and I can say slash D plus which says show me the schema because sometimes you made a table long time ago and you forgot what the create table was and so you can say showhow me the schema of the user's table and so you'd then see the schema of the user's table。

So up next， we're going to talk about how we take these tables that we just created and type SQL commands to put data in。

 take data out， the actual crud， create， read， update and delete okay。

 so that that's what we're going to do next。

![](img/12e0cc48ef0e3bf4b5e51d393318f9a8_5.png)