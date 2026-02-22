# CMU《高级数据库系统｜CMU Advanced Database Systems (15-721 Spring 2024)》中英字幕（豆包翻译） p13 -13-S2024 #12 - Database Networking Protocols .zh_en -BV1HZ421N7WZ_p13-

🎼Carnegie Mellon University's advanced database systems course is filmed in front of a live studio audience。

😊。

![](img/115c8db2b302299415f04b0cd0914410_1.png)

🎼。We're all going to die， okay。ButIn me，'s two databases。 all right， So today's class。

 we're going to talk about networking protocols。 And then this will be the we're sort of hitting the。

 we' call the second， third。We're finishing up sort of the second third of the semester of the materials。

 so this week and then for the next two weeks we'll talk about query optimization。

 and then after that we'll go through and start reading the papers for major systems and understanding how they work and putting the things we talk about this semester start seeing how they're going to be applied by the companies and the people building these various systems。



![](img/115c8db2b302299415f04b0cd0914410_3.png)

So last class was all about how to take userri functions that the application developer has written because they want to embed logic they would normally be in the application and they wouldn to embed that directly inside of the database system and evoke it through a query。

 And the idea was through inlining techniques we can convert the UDF constructs into to SQL relation algebra and then have that be exposed to the query optimizer to figure out what the intention。

 what the user userri function actually wanted to do。😊，Right，So this is the example， again。

 of pushing the application logic into the database system。 So as I said at the end of last class。

 today's lecture is about。How would you sort of do the opposite of get data out of the database system and bring it over to the application so the application can process it and do it at once？

So we'll first talk start off with talking about what these different databases access the APIs look like。

 and then we'll go into more details of what the network of particles look like。

 and that was the paper you guys were assigned to read about actually what do the bits look like and how it's inefficient for in modern application scenarios where data scientists maybe working pandas or some Python notebook and we' just want to go to do a select star and get a bunch of data out and then do all the processing on the client side。

😊，So we'll see how the major data systems today， the existing protocols are insufficient or just not design for that kind of workload。

 the answer is going to be the end it's going to be Apachearrow is the solution。

So the paper you guys read came out before thearrow database connectivity library stuff was defined。

 but they basically are reinventing the same thing and then ADBC and Ar would do the same thing。

But we'll burn up to that。Then we'll talk about additional optimizations we can do on the server side to make things run faster at the networking stack or potentially for other parts of the system by either doing kernel bypass or user space bypass。

 and then we'll finish up quickly just talk about okay what are some additional optimizations we could do on the client side if we know our Python program or whatever it is is talking to a database system and it's going to put some data into a data frame？

So I would say some of the things we'll talk about today will be applicable for backend communication between the various database like the workers in your system like you know if it it's a parallel system and one worker needs to communicate with another worker or needs to communicate with the optimizer service or schedule service a lot of these things we'll talk about in in that environment will still matter。

 certainly kernel bypass stuff could help or user bypass stuff can help。 but like the。This is really。

 we're going to mostly focus on how do we actually expose data to the client and how to make that money efficiently。

But we'll see when we go through the discussions of the video world systems where there are some optimizations we can apply in the back end。

All right。Last class I showed a really quick demo of opening up the Postgres terminal and writing a SQL query and hitting En and then getting back some results。

😊，So that's sort of like a basic access method to the database system where youre San SQ query and you're getting Mac results that are meant to be printed out on the screen。

Because it's meant to be interpretable by humans。But most queries aren't going to run like that。😡。

Most queries are going to want data in typically a binary form because it can be fed into some kind of application code that wants to do some additional processing on it。

RightSo like in my example of the terminal， that's just plain text。 And actually。

 in that case of Postgreds Postgres is actually then I'm going to send plain text data over the wire back to to the client。

 We'll see one system in particular actually does that no matter whether it's talking to an application or a terminal。

 but most systems are going to be doing binary data utilization。

So you wouldn't actually want to write your application by just like piping out to PsQL or whatever the command line terminal you want to use instead you're going to write your application using one of these different methods and aren these aren't mutual exclusive like you could depending on your application maybe it's written in C sharpp or C plus fl you would use this if it's Python you use that and so forth right so various systems are going to support some of these but we'll see when we go through it that。

The thing that we're really going to care about is this like the low level network API of again how we're going to put bits on the wire。

 and then all of these methods， except for maybe the last one can hide all that， right。

So the first one is like this this is sort of this is a proprietary API that the system exposes to you typically through like a C library and it's like。

You wouldn't when to write this re applicationplication。

 This is like if you're writing a driver for these other ones here。

 you would use kind of these kind of things。 and you could look at the documentation for like MysQL and Postgres they all have information about the API for like in the low level C library like how do you open up a connection。

 how do you send a query， how do you do authentication and so forth and you can use chattBT to write this kind of stuff you basically say write write me C program that uses LibpQ。

 which is the low level C API interface that you would use program in Postgres， but again。

 typically don't write programs like this you'll use some other abstract you use the higher level extraction like an OM like writing Janjango Act record。

 Ru and rails， SQLize and noJS on the covers， they may be calling the API。

 but use the application program or aren't writing coding as these things。😊，So。

 I want to focus now on these two， the Python came later in the '90s。

You'll sort of see how things get built up over time and a lot of things we'll talk about for JDBC as a pickle for whatever pick your favorite library。

 pick your favorite programming language that has a specification of how to do database with connectivity and they would basically fall through the same thing。

Because the big idea of what these APIs are going to do for us is that in theory。

 instead of programming against the low level like CAP， like these things。

 instead we could program against these technically database system agnostic APIs and then if we decided change what database server or database system we want to use。

 we would have to change our any of our application code。

 of course that's not entirely true if you're writing rawSQL because as we said many times the SQL dialect could be different from one system to the next。

 but we can ignore that。So the history for this goes back into the late 80s， early 90s。

 basically prior to something like ODBC。It was just these libraries that all the various database system vendors provided。

 So things weren't portable。 you would writing again to a lowle API talk to the database system that was very specific to the one database system you were using And so there was people identified early on that'd be nice that people writing a lot applications It' be nice to have a standard way to do database connectivity and Squeries giveback results。

 So I think the first attempt was in the late 80s from Cyibase that had something generically called Db library that was meant to be like an open source standard I don't meant be the standard everyone can implement that didn't go anywhere。

 And then Microsoft team built with this other company called S Tech in the early 1990s and they put forth this thing called ODBC And so now pretty much every database system that you can think of today is going to have an ODBC implementation even it's actually not a relational database system and doesn't support SQL like Mongo DB has an ODB。

😊，C implementation right because again， at some point you have to put it in the query command that you want to send over and ODBC doesn't know doesn't care that whether it's SQL or not。

 here's the thing I need to send to the server。 But there's other APIs how to like you know iterative result sets。

 bind parameters to values and so forth or values to parameters and so forth。

So at a high level it looks like this。So the ODBC is made based on the device driver model。

 it's sort of similar how like the hardware works and PCs where if you buy like a graphicras card。

 the vendor that sell you the graphic card， they're also going to provide you with a driver that you can install in your OS。

 to communicate with the hardware。 So the same idea。

 the database system vendor is going to be responsible for providing you with a driver that you can use based on the ODBC spec。

 then then communicate with the database server。So if the application wants to run runs some queries on the database。

 they go to the ODBC driver， and then the ODBC driver is responsible for sending the request over to the database server。

 getting actual result， and then marshalling it back into the form that's required by the ODC spec。

 then expose it to your application so this can mean things like if my client is expecting everything to be 32 bit integers。

 but the database server sends me back 64 bit integers。

 then the driver is responsible for converting that and cleaning things up。

It also can do other things like there's certain features that are in the ODPC spec that the database system doesn't support cursors。

 for example， like Postgres doesn't support cursors， like true cursors。

 then the driver can emulate that basically like send the query over。Gaive you back a cursor to it。

 and then you're iterating over the results that are cached on the client side。

 So you can do a bunch of stuff in the driver。So the thing that we care about today is。

 is this piece here， right， the request going out and the response coming back。

 They were' to call this the wire protocol， the never protocol of the database system。

 So this is what we we' we're gonna to focus on。Yes， do commands receive？ for example。

 like where do they get ined into the？Do they run through the query optimize does it just like get converted to SQL and go through everything So the question is like like if I have a SQL query。

 where does that get like converted to a plan？My understanding is when you're using ODVC or' using standard calls。

 they don't really like。They like there'll be a。Like prepare statement command and you put a string in that'll be whatever the flavor is sequel。

 the Navy says in sports， andt be' there's no way that can be universal。Across every data systems。

 but like the API called to say here's the query I want to run and then you then execute it。

 get back result， now iterate over the result set and give for each row second give me the second attribute and I wanted that as an integer。

 all that standardized。But the sequel itself just goes over the wire， and then all the parsing。

 the planning， the optimizing， all that happens over here。😡，Again。

 this is basically going to be calling typically the CAP that I I mentioned before。😡，Right。

 so let's talk about， so again， this was the first one， the big one that really took off and again。

 in the late early to mid-90s， everybody was supporting ODBC at this point。

And then Java comes along mid 90s and then Sun recognized that if you were to be able Java applications in the enterprise they need to be able to talk about database systems or talk to database systems so they had to support something similar to ODBC but for Java and at the time again ODBC was very much Windows specific。

 but since then it's sort of generic and it's expanded。But again， but at the time， you know， it was。

 it was his way aesthetic and for。And for C of those applications。

 so it wouldn't work in the Java world in the same way that rust is the hot thing now。

 Java is the hot thing in the mid-90s the idea was you write your program once and the GABM can then run it anywhere like that was mind blowing people back then。

Go was the hot thing 10 years ago。 There's always some kind of fad。 Allright， so。

JDBC comes along and you can sort of think of this as like again。

 it's basically the same because ABC just now it's for Java instead a C。

 but because they were trying to bootstrap this new connectivity API to an existing ecosystem。

 a bunch of database systems that already spread to ODBC and they want to be able to people get up and running for any possible data system as soon as possible。

 they have different variations of how you can build a or how to build a JDBC's library or API or implementation of it。

 and they have various methods to like bridge the gap between what was available at the time versus what came on later。

😊，So。The four approaches are the first one is that there is no native JDBC implementation。

 a Java implementation of communicating with the data system。

 so instead what you provide is a basically a bridge or a raper in Java that then invokes ODBC。

 like the actual shared objects， the C code that then that communicates with the database system so this was meant to be like again if you have a database system that doesn't support DBC yet。

 you could just wrap something around ODBC and use that。

The next approach was that you would have JDBC calls and make J and I invocations down into the C code of the CAP and have that go over the wire tookook the database system and again this is because think of like taking the bytes。

 putting into buffers， all that was done in C and then the thing was just copying the data into Java。

Another approach is basically you have a separate middleware。

 like a separate server running that the JDBC thing then would talk to。

 and then that middleware then would use ODBC to talk to your database system。

 so it sort of extra hop to make the call you needed。😡。

And the last one is obviously going to be more ideal is that you have a pure Java implementation that that makes the JDBC calls that you provided from the application directly into JDBC。

 the Ven civic wire protocol commands。RightSo every single data system at this point is going to have their own native Java JPC implications。

 but again thinking how many times you come across something like in rust or some cargo you want to use and there isn't a native implementation that's just calling in the C。

 that's really the top thing up there。So the top one has been removed and the one this is the best one。

 and this will be the most common one， at least for the most major database systems today。All right。

 so as I was saying， the thing we care about is what's being sent over the wire to communicate from the client。

 whether it's ODBC， GDBC or whatever it is to the database server and so every database system for the most part is's going implement their own proprietary wire protocol typically over TCPI and it's going to use that again to send the bytes back and forth and acknowledgements and get take queries in and get responses back if you're running on the same box and in it Linux。

 you can use Uni domain sockets to get fast performance because you're not going through the full TCPIB stack and the OS both on the client side and the server side you can do this in Postgress but again。

 if you're running in the cloud， the database server is some far away location you're not going be able to do this。

Those systems do， I'm not aware of any system that uses UDP to communicate between the client and the server。

 TCP has its overhead because you have to send the acments and back and forth。

 right where UDP you sort。Throw it over hope it makes it。

 So no system I'm aware of will do this from between the client and the server。

 We'll see one system later on yellow brick， though'll actually do this between the use UDP to communicate to the backend servers。

 because it's just so much faster。 And they basically have to do their own retry and acknowledgecments on their own。

 But in that case， because they're trying to get the best performance possible。

 it was worth it for them to implement this。ProsGres uses UDP to communicate between the stats collector and the different workers。

 but again that's all in the back on the same box， it's again， not between the client and the server。

So typically what way happens is the ways you would communicate with the database server is that the client comes along。

 connect to the database system， there's always going to be some kind of authentication process or even you're given a token that because you've authenticated with something else。

 or you do username password or whatever the mechanism is。😊，Ideally。

 you want this to be using SSL or TLS， because you don't be able to sniff your packets。

Then you send over the query。 the data system will then block that connection。 Well。

 that's not true because you can do asynchronous stuff， but it'll run that query。

 and then soon it starts getting results， it serializes them and sends them back over the wire。 Now。

 some systems can do cursors， for example， and start sppooling you some of the results。

 even the query starts running。 the query is still running。

 But So far as I know most of the cloud systems is like like once you get all the results。

 then you can sending things back。😊，Obviously it depends on the query too。

 like if the last the root node in the query plan is like an order buy with a limit on it。

 you need to see all the data before you need to start sending anything up。So again。

 the thing we care about this today is this sort of step here。

 and we'll talk a little bit at the end of what we can do to maybe speed that piece up faster。

So I would say also too， the， the paper guys read the。

They talk about how this part is actually not that big of a deal。😡。

We spent the whole semester so far to talk about how to build a fast database system。

 and how to run queries really fast。And， you know。Obviously if you're reading peabbetes to data。

 I' sure that's going to take a long time， but in the paper you guys read and then this other work that came out on this thing called connector X。

 this thing is actually the most expensive part。It' sending that over the network impact to the client。

Right， again， the query themselves aren't going to be that big。

 Like the biggest SQL query that you can get at at top is going to be like 10 mete。

 We have like the sQL string。 So that's not expensive to send。It's sending the results back。

Is going to be。Because would be various steps along the way because you have to copy it in the form that that the client or network protocol wants。

 And that it may not be the same as theyre natively stor in the database。 Yes。

 would aQ query the question is， how would a SQl query reach 10ga。 Yeah。

 so this is the example actually comes from Google。 They told me that they had。

it's not hard to imagine either right they have some dashboard where you can click a bunch of checkbox of what you want to visualize and all that's doing is just concatenating search options in a giant in clause and then before you know it you' got 10 megabyte sQL string。

It's rare， I'm not saying it's common， but you can imagine something something like that。

We didn't really talk about tricks of how to the ends go faster。You basically， in that case。

 if your're in clause is huge， you basically build a hash table on the expression itself。

 then you use that to probe when you do lookups， it's like you're doing。

It's like you think of like inclos as like almost like materializing at another temp table。

If it's huge， if it's big。Other questions？Okay。So if you're going to build a new database system today。

 you have two choices。😡，You either can implement your own wire protocol by scratch。

 and then in which case then you have to write your JDBC， ODBC client libraries。

 the drivers to support talking to your data system。Li。The more common thing to do now though。

 is just use an existing wire protocol from an existing database system。

 because then you can just inherit their driver ecosystem for free。Right？It's not enough say like。

 okay， I speak the wire protocol。To say you're compatible with with another database system。

 like if believe that's the bare minimum。 If you spoke the wire protocol the。

The client drivers don't know or typically don't know。

 don't care what the SQL query looks like sort of related to his question。

 like they're not parsing on the client side to see。

 are you really sending me a Postre know Postgres compatible query。

 They're just sort of sending the text over。 So if you want to be able to support more the ecosystem。

 then you have to support of a catalogs and other functionality。

 But the bare minimum you would need is just to say I need the wire protocol。So it's about 50，50 now。

 it didnt didn't use to be this way。 but the two most common wire protocols that are going to be reused is My SQl and Postgres。

 My SQl used be number one， Postgres is actually becoming more and more popular。

 that's partly because there's's a lot of databases that are like forks of Postgres where they keep this sort of the top app。

 including the network layer So you speak in the wire protocol。

 And then they rewrite the bottom layer。 that's sort of neon does and redshift and others too。

 The third most common wire protocol is actually red Redis this is because it's so simple it's like text based like get and sets and simple things like that。

 But again， if you support these existing protocols。

Someone can run against your new data system without having to re their application or change what driver they're using because you just piggyback off of the existing driver implementations。

Snowflake interestingly， did not do this。 I think it's a different time。 Snowflake decided。

 were going to write your own wire protocol from scratch。

 including their own SQels diallect from scratch。 they started on 2011，2012。

 I think if you're going to build a new system today， itd be a hard decision to do that。

 because there's just so much stuff you can reuse if you speak the Postg wire protocol。So again。

 so the paper I had you guys reading I read was about how to get you know how to improve the wire protocol between these different database systems and they sort of focus on four key design decisions。

 obviously also the background of this paper is that this is from the MonadDB light project which was a precursor toductDB。

 So Hans and Mark who are the authors of this paper。

 as part of the work they were doing of make MonDB be embeddable。

 they realized all the problems they were having of getting data in and out into like pandas and R programs even if you're still running in the same process So this is sort of what led them to throw away the code and start buttingductDB。

So this， again， it's the same team， but beforeduct B became a thing。And again。

 this paper is focused on doing large data exports。 So it's not complex queries。

' doing you know a bunch of joins and much of sophisticated aggregations。

 It's more or less like select star queries or。You can getting a subset of the comms projected out to then be able to feed that into a panda or Python program to do additional computation or training machine learning models and so forth right So this paper is really about how to get data out of the server into the client。

So。Now， whatever， again， whatever optimizations we're going to have talking about today。

 you're going to have to also implement them in the client driver。

Because if you start compressing things on the server side， send that over the wire。

 if the client doesn't know how to decompress them， then the data is useless。Likewise。

 if I convert from a row oriented format to columnar format。

 if the client doesn't know that you did that transpose， then it's all useless， right？And so。

Typically， client drivers are being very conservative。

 and they're not going to want to have a lot of， of， of。Extend the capabilities in them。

 because now you have to support that for every single possible language you ever want to support。

 So if you， if you have like the C API and you just wrap that around the various different programming languages。

 then that's fine because you just sort implement it once。 But as I was saying before， ideally。

 you want to have a native implementation of your client driver in whatever programming language you're running in。

 So you don't have this copying over between like C or to whatever programming language you want。

 right。And so if now you have all these additional features in your client driver。

 well now everybody who every programming language that implements your client driver has to implement the same thing and that becomes sort of could become problematic because it're fractured。

 people don't implement all the same capabilities， right。

So there's a tradeoff between how sophisticated we can be versus what people are actually going be able to do on the client drivers。

 Furthermore， in a modern scenario， we haven't really talked about Lambda functions or serverless applications。

 but a very common scenario now is like the communication with the database server like I spin up a Lambda function。

 which is say some Python thing that is run。 it connects to the database server does authentication。

 send some queries， getback results and then does some minor processing and then goes away。

 So in that case you're paying for the compute time on the serverless function and you don't want to have a bunch of expensive desitilization if you have a very sophisticated。

😊，You know， a client protocol。And again， the answer is going to be Apache arrow is going to be the right solution to this。

 that's the risk spoil them。 All right， so we'm going to go through these four major pieces of1 by one and see what the trade uss are again。

 not just for performance， but also again from the engineering side on the client。😊。

So the first one is going to be kind of obvious， because this why we started off in the semester。

 row store versus a column store， and ODBC and JWBC are by their nature are row oriented APIs because they were developed in the 1990s。

Early 1990s before columnar databases were a thing。

The paper of columnar database is the first one in column St is like 82，83。

 but that's a theory paper， there was a Swedish system that was technically a column store。

 but like in the '70s when no one's ever heard of that。

 sbase AQ is probably the first one that came along was a true column store implementation。

 but that's like 9798 So again ODBC comes along in 1990 column St aren't a thing。

And most of applications people are writing are like business applications that are like going。

 fetching one order record or of single entities， single information。

 so it's inherently row oriented。So in this world， what's going to happen is the server is going to take all the tus that' getting part of output。

 And even though on the server side， it may be storing them as a column store。

 it's going to stitch them back together， materialize them back together because the client protocol。

 the wire protocol wants it in a real oriented manner。

Because then you write applications and of pseudo， JDBC， stuff like this。

 you're going to iterate over the results set and get one tu at a time and extract out the data you want row by row。

But if we switch to a column format。Then this technique could be bad too。

 because if I ever need to get multiple data for a single tuo across multiple columns。

Then I have to write some weird code of like iterate over the columns and iterate over the next rows and try to put。

 you know， stitch things back together。 Again， this is not real code。 This is some pseudocode here。

 right。So the solution is basically the same thing we talked at the very beginning。

 We want a pack space model， because。Because now we can operate over batches of tuples and although we're going to be sending them the data out in a columnar fashion。

 we'll group them together in row groups or small enough chunks where all the data we would need for a single tuple will be close together。

Right。So this is what arrow does， as we talked about， and so arrow。😊。

Has a thing called the Aero database connectivity， and it's basically like JDBC or ODBC。

 it's a specification programming API for to how to interact with a database system。

And operate over getting back vectors。And so if now your database system supports ABC。

 which some systems do， like snowflake， for example。Then now I can make requests。

 send a SQL query over to the database system and get it back in native arrow form。

 and then I can integrate that and use that in my application any way that I want without having to do any copying or decilization because it's already in a vector format。

😡，So we're not going to go through what like ADBC is not everyone actually supports it。

 but this is going to be this is basically what Hans and Mark are going to propose， like， hey。

 be nice to we have this vector based API and this is what came out later。

Because the paper you guys read predates ABC。Okay， so now if you want to begin assume we're sending things back as vectors。

 how we want to support compression？And this basically is going to smell like again。

 all the stuff we talked about before in storage of this trade off between having general purpose or naive compression or just taking blocks of data and throwing GZip or snappy at it versus having a more lightweight encoding scheme that's specific to the actual data that I'm storing。

So again， the easiest approach is to do just GZip or snappy or Z standard。

 and this is basically you do all the same wire protocol construction of the packets of messages that you would normally do。

 but right before you send it over the wire， you just run GZip or snapap you want it to compress it before it sends it over and the client basically does the reverse of it。

So this is not that common。It's not owned by default for most systems。

 but I know for like Oracle and actually Nofolk might be owned by default。

 but like a real low light compression， but Oracle， my SQL and BigQuery。

 these are things you can go at on after the fact。😊，Bigqueery is doing this over HTTP。

 so I think it's part of the HT's client protocol adding GO。Right。Oracle added this in， I think 2013。

 My SQs had it， I think for a while， there was a patch to do this and add this in Postgres in 2018。

 but that didn't go anywhere， so Postgres doesn't support this。Right， and then the。

The the next approach is again， doing all the stuff we talked about for。

 using dictionary encod or lead， Dl coding frame of reference coding。And again。

 the idea is that like you， you， you recognize the the data type of the。

 the data you you're sending back over the the for the response and you just run this compression scheme。

 whatever you want on it。So。Nobody does this because again it would be except for arrow because ifarrow does dictionary coding like that's the only encoding scheme that I think supports out of the box。

 So if you get data back as arrow if we already dictionary end but they're not doing the Dlta andcoding or at least of as well again。

 nobody does this because as I was saying before， you would have to have all your client drivers also support this as well。

And typically the way it works is like when your client connect to the database server。

 it's like when you do like an SSH handshake， you say here's here's the features I can support and the client the server then picked the sort of the bare minimum they would have so you could have like a bunch of older you know。

You have a bunch of clients showing up with old driver implementations and then not support any of these things。

I think it's part of the reason nobody does this， and again from the engineering side。

 you have to support this all the different implementations。Yes。

I it really either or can't you have both these from where random a paper thought you have？

And then you doYeah， same as like it's not exclusive， like you could do both， yes。

And then furthermore， depending on what how you like serialize the data。

Like if you're just doing text andcoding and you pad things out， then this one's gonna make a big。

 big， big difference versus like this， right， Yes， so they're not music exclusively。

But I'm saying nobody would。As far as I know， other than Air ABC。

 nobody does this because I was saying the drivers have to support it。嗯。So。Basically。

 everything I'm saying here is all things we talked about earlier when we talked talk about getting things on the object store run from disk。

When the communication channel between the storage or between the client and the server is slow。

 then heavyweight compression is going to be much better because we're willing to pay that trade off of spending more CPU cycles to compress the data down to small smaller sizes。

Because then that'll speed things up as we send it over， right？And obviously。

 the larger the chunks of data we're sending over， the better compression ratio we'll get。

Next is how do we want to send how do we sort serialize and encode the data we're sending over So the first approach is the most common one we do binary encoding and this is where you're basically sending the data from the client to the server in the same lowable binary form that it's being represented in your database。

 at least ideally not always the case though and in this case here the client is responsible for dealing with any Indian issues like if the data is being stored in little Indian and your client for some reason is running on a big ending machine then the client is responsible for doing that conversion because the idea there is the database server is just trying to get you data as as fast as possible and the client can then since there's more clients than servers typically you can spread out the computational cost of doing that conversion across all the different clients。

So another question is going to be， okay， if we want to use the binary encoding。

 how are you going to decide what serialization scheme we're going to use and in the paper you guys read。

 they argued that rolling your own serialization format is better than using existing libraries because these existing libraries bring a bunch of other infrastructure or other things that you may not actually care about that add additional computation overhead and storage overhead space overhead for the packets are sending back。

So what do I mean to this so like you can write your own sization format to like how to take result set of three attributes and integer floats and whatever and pack them down into the byte representation that then send the wire or alternatively you use one of these libraries like codeta buffers。

3 after flat buffers is the newer one， the better one cap and Proto there's one of these other ones that basically provide you the capabilities to define the schema of the messages you're sending and serialerilize it out。

So one year， somebody asked me like why doesn't any if we're gonna to be sending back data through protobuuffs。

 why did just store protobuss natively， And I was like nobody does that。

 that sounds like a bad idea turns out somebody does do it because they email me later on。

 there is a system I think it's like a toy project called Profene Nebe where the wire protocol sends out protocol buffers and internally storage they're storing everything as protocol buffers as well because it's just bytes So in that case you don't do any desilization or resillization when someone requests something because you just send over the stuff you've already stored as Protobuuffs。

I'm not saying it's a good idea， but it does exist。Am。The other challenge also too is with protobus。

 that's least that one is these separate enough from GRPC where you don't have to bring in all the infrastructure for GRPC and thrift as far as I remember。

 you bring in their threading models of thread pools and I think buffer pools as well。

 this brings up way more infrastructure， if you choose to use this。Flat buffers it's like proto。

It's a。It's pretty simplistic and it's just the serialization format。

There's other things that these guys provide you as well。

 which may be useful because they can find like keep track of the versioning of your messages and so forth。

 So like over time if if you expand the capabilities or the internal data members of the packetouts of messages you're sending when you send back results to take queries in。

Protobouff will keep track of like the different version of this。

 you know version of the API you're interacting with。All right。

 the other approach is to do text encoding。And this is like the simplest thing to do is is you take no matter what the data is。

 and you run the equivalent of like two string or stir on it to convert it from the binary form to a string form。

 and then you just send it over as variable length strings to the client。😡。

And this one is nice because you don't know worry about IndianN is because some ASCI or UTF8 format。

 the client then takes your text and converts it back to the binary format and they can put it in whatever form that it wants。

Right。For missing values， you could have a separate bit mapap to keep track of what values are null。

 and only need to be， they destroy the value null， or literally the string null to represent you have a null string。

 right？Yes，呃。Yeah， yes， what you need。to make an ASI and then reverse it with A2 I， yes。

So is this a good idea or a bad idea？😡，Yes。Did you have a stringing your database？It's the word no。

As he points out， what if the string of literally is just null， what do you do？I don't know。

 this is no need Africa they did。This is other than his how do you store know？啊。

Thiss is a good idea or a bad idea？Why， he says bad idea why。

What is his hand gestures close the size of the data？啊哈。Why do this Why't we just say， okay。

 this is the start of the stream， this is how long it is， treat the next couple of bites。As a string。

 like why do you need it translate it？By what does the encoding here do？So like encode me like this。

 if I have a 4 byte 30 bit integer，123456。When I send it over the wire to the client。

 I'm literally going to convert it into the string， the ASI string， character 1， character  two。

 character 3， K to 4，5，6。😡，And then I'll do what you said。

I'll store the length of this string in front of it。Or I can do an nu termination。

 but every piece of data that I'm sending over in a record is going to be a string formula。

But in binary you're like what is the difference？What is the difference？ Well， again， So like。

 I can store No， no， no。 So like like。This is storing like this is a， if you look at the bits。

 this will be 32 bits to store this number number Yes。

 this is going to be each of these is going to be， say one bite to store store the character one。

 the ASI character  one。Right？Any you have to store the size or the nu Terminator。

 or keep it fixed length， which is the next one。So good idea， bad idea。You know， it's Ben's point。

It also seems that instead of compression they've gone。Yeah。

 so to compressing he's going in the wrong direction， but then do if you put G zip on top of this。

 it's going to compress the hell of do fantastic。😊，Potentially， yes。指つけらんか。

I mean it's a little more complicated。Yes， why would Jesus book better on approach to than？

Because there's be more things to compress。There's more bits。答是拿。We'll look at the results on sec。

 give me a sec。That doesn't make any sense because you are。was that。

 if you run on the byte4 byte versus you run it on six legs？

And which one be smaller His statement is like， if you compress the 30 bits or this versus whatever the six bytes plus the null terminator or the length。

 like is that thing ever going to be smaller than this now？😊，You might be able to do a dictionary。

surely the database knows better about how to serialize and do serialize stuff rather than just always doing the same。

His David is the data says' know better how to serialize us rather than just always doing the same thing。

 in theory， yes。Would you want to spend the time on the server side to do that， figure that out。

All right，We'll come back to this。If you roll your own。

 so those systems are going to do do binary coding。

 but roll their own and not use one of the existing libraries。

 But then it's all the stuff we talked about for when we talk about data file formats。

 we we have to do the null mass， keep track of data types the sizes of the data and the messages。

 That's fine。 know， we knew how to write that stuff because we had to do it for storage anyway。

Right it's just more work。 whereas like putto aboveuff。G givesives you bunch of stuff for free。

 but it all things and see you pay a cost。this one we already talked about how are you can represent actually the length of strings。

 you could do the C style， have the nu termator byte at the end。

 and then can the client just scan along it finds nu termator and says okay I have all the data that I need this makes it harder then potentially do jumps into fixed length all sets。

 as we talked about before， if you're trying to do store things sending things as vector batches。

The most common ones we like like prefix prefixes， which we were talked about before。

 And then some systems， I think this was I think minute to B。 they're just going to pad out the。

The string with additional characters。To， to be whatever the the max size of the action could be。

 like if I have a， if it's a bar charge 16， I have a bunch of four character strings just gonna pat out the rest with a bunch of spaces。

 Yes， Sa yeah his question simply it's appropriately gonna be the best， why。😊，It's fixed length then。

If you are batting， you're batting probably you with zeros， so Jesus can take care of that。

If it's fixed to it， you can jump around much faster。

The statement is if ifs if it's fixed width and padding one to zeros， G zipper can compress that。

 But then also too， now everything be fixed length， you can jump around as needed。

 don' don' So again depends on it's all things damage depends on what the query wants to do with it And further also too。

 if the column is like a var chart 1024 and have a bunch of one character strings in it。😊。

Then that's wasting a ton of space。Question be。you tell me， why would people do that。

 People are stupid。 You see all sorts of crazy things in real databases， right。Yes， approach。

 does it have any advantages？The question is perch1 have any advantages， on the server side。

 you can reuse Li C's string functions。啊，No alternatives at all。

So when we bought our first system like my second or third year second year at CMU， we did this。

 and then of course， then we go over the wire protocol because you're speaking the wire protocol。

 pros didn't want an alterminator， we didn't have to copy the string and add the length in front of it。

Even if you have like one characters in the back shadow。这他是个。

Won't Jesus take care of that if you're batting everything？So statement。

 even if you have the VarA 1024 and you pat it out。

 the small strings won't GZip handle that for you if you use GZ。Okay， yes。It takes time。

 but it also if you use it， even snappy Z standard would be fast。

 but like you got like not all the data systems that report that。

 I just said Postgres doesn't support this。 Posts wire protocol itself has no notion of compression。

You can hack it by tunneling all your traffic over SSH and compress that， but that's the extra hop。

 and that sounds crazy。But like the posters why protocols， as far as I know， at least in 2024。

 does not have like a flag to say this is going to be compressed。My my sequel has it。 Oracle has it。

 other systems don' do not。So again， sometimes ones can be faster， sometimes twos can be faster。

 no system is going to do both。No service is going to try to figure out， okay。

 based on what the data looks like and what your query looks like。

 I'm going to give you one versus the other because again。

 that's more engineering overhead that youve got to support now on the server side and on the client side。

 and it's just not worth it。😡，This will be the fastest if your data set size is small。

 if it's all chartr1s。This is to be the fastest。Because you don't store the length。Okay。

 I'm gonna show I say also too， like as all things we talked about for， these aren't independent。

 right， Like， if I if I choose one of these， that'll affect whether， you know。

 how what kind of compression team I want to use that's very similar to the stuff we talked about when we talk about data on disk。

So I'm going to show two graphs here。So the first is going to be what happens when we just send one tuple。

😡，From from the database system to the client and the idea is here just to look at what the overhead of like just all the infrastructure around the messages of sending the query and getting back the result So and for all these systems except for hive。

These are all going to be using ODBC， Hve is going to be using JDBC。

 and I think forget the reason why they did that。So here's the numbers。Right。

And they're listed in order of performance。 So the first thing to point out here is that。Here's。

 here's Mo A B。 that's using the text encoding thing that we talked about before。 you know。

 they're sending over converting all the the， the binary data into string form and sending that over。

 right， All the other ones are using binary encoding。

But yet Mo IDDB is what the second fastest or third fastest。Right。Why。Power of Jesus。

It says power G zip。Was that seems to be without？No。

 that's probably because she's one two decent really help as well， right？So is G happening him here？

So let's why the other ones are slow， right So this one is hi。

 right the reason why that's according to the paper， why that's slow is they're using thrift。

 So thrift is going do know， copy things in and out of thft buffers。

 So that additional ma copies to get data onto the thrift on the server side。

 And then on the client side copying out of their buffers as well。

 And then thrift is also gonna sending over a bunch of metadata about what the the structure of the of the。

😊，What the structure or the message is going to be， they're sending that over as well。

 so the size of the packer， the message for send the same tuple as all those systems is' just much much higher。

😡，DB2 is the second slowest because。Theyre actually， I mean， Oracle does this as well。

 but for some reason it's more pernicious than this one。

 they're actually also basically reimplementing acknowledgeknowledments on top of TCPIP。

 So TCPIP is already going to be doing like you know sending acts back。

They're going to be doing that as well， above that to make sure that like， okay。

 I got your message for this in Davis server for this I got this packet。

 I'm ready to give me the next one。So the protocol itself is just way more chatty because。

For some reason， they're they're implementing， re implementing this idea of， you know。

 of acknowledgements。 Yes， his question is， is it based on UDP， I， I have no idea。Also too。

 like since it's a proprietary protocol， they can't see the implementation on the server side。

This is what in the payment they speculate how is it possible？To be so slow。Like for one people。

 how many bits is that？Oh for TBCH。it's less than， less than， less than a kilot。

So say how I think also too like。This is like I think this is end to end time and not like just sending the message so like this is like sending the query and then high basically converts the query into a map reduced job。

 then it dispatches that， gets back the result and sends it back so I think it includes that。😡。

But I have the double check。And this the client， clients on the same machine as a server。

I see what else they say the minimized query execution time。

 they would query query multiple times so the data system would cache the query plan and the result。

 so I think back what I said it wasn't running the about job。

 it literally is just like how to get data in and out as fast as possible。😊，Right again。

 it's one second。网。How's not a great system。 I'm not。 Yeah，s not There's a reason why you're。

 you know， Facebook dished in and we wrote， wrote Pretzto。

Right Hve was a stopgap solution in the late 2000s。When。

And I was sort of part of this the Hadoop came out the Matt reduced paper came out from Google。

Yahoo took it， sort of reimed the ideas as Hadoop。 Hadoop was like the hot thing。 and was like。

 this is amazing。 This is how you should be doing analytics and and big data stuff。

 The relational database people， which I was a part of， we were like。

 you guys are all doing it wrong。 You're reinventing stuff that was then in the 90s for parallel databases that distributed databases。

😊，And then decative languages like SQL is a good idea， processing data on partition tables。

 that's a good idea。And then people realize， oh yeah。

 writing these map produceduce jobs in Java sucks， would be nice if we had SQL。

 so then they built high， which is basically a translator from SQL。

 and it would then cogen a Ma producedduceed Java program。So yeah。

 you're making your face I'm not saying it's a good idea。okay for this game。

 they were surprised by how slow DB2 was， again， as you was saying， it's such a small amount of data。

 but again， I think the protocol is just so chatting， right？All right。

 so that's not look we send more data。So for this one we're going to send a million tuples from TPCH and what they're going to do is they're going to scale along the X axis。

 they are' going to officially slow down what the network latency is between the client and the server。

😊，and so the first line I want to show is just for MySQL with G zipip and MySqL without G zip。😊。

So this basically corroborates what we talked about before with storage。

 getting things again from S3 or the object store or whatever， when the networks really fast。

 you don't want to compress the data because the CPU cost of doing that additional compression is just not worth the penalty or it's not worth it because the network is so fast and so that's why you see this gap here when the network really fast。

 not using compression is the better way to go， even though you are sending more bytes。

But then even though we are log scale here， but as we get to a slower speed。

 so 100 milliseconds for for the latency， again， we're log scale， but the。

The compression one actually is slightly better。Because in that case the。

The CPUO is not the dominating factor of getting the data out。

Its the pressure ever has bad when trade off never gets fast。

 So now we bring back all the other ones。Right and they all basically conge or sort of moving along in the same way as expected。

 right the time it takes to get the data out of the database server goes up as the network gets slower。

 But what it's surprising here is that you can kind of see that case of oracle。

 they're one of the faster ones when the network gets fast。 but then as the network gets slower。

 they're now the second slowest DB2 is always the slowest。

 hive actually beats hive is actually beating DB2 when the slower network。😊，嗯。

And soacle is Oracle is a proprietary protocol， we can't see the implementation of it。

 but they speculate again， just like in the case of DB2。

 Oracle is also sending their own acknowledgecments back and forth and just becomes more dominating cost when the network gets slower。

So again， all of these except for hot except for Mon to be are。Or I。Our binary protocols。

 but Mo to be is actually what the。Is the third best after My SQl and My SQl Gsza。

Because it's simple， yes。It's a benefit from。And those apply to honor。His question is。

 is do you get the same benefit of compression for the other as my SQL， I assume yes， like oracle。

 you could test it。I would say yes because the Oracle wire protocol。It's。

The actual bits themselves may be different than what MySQL is。

 but it's a binary based protocol like MysQL， So itd probably be out the same。hy donよ。给我们追究。

Excusion why do they only turn on Jesus from my， I don't know。Yep。Okay。

So I'm gonna to show another result from a different paper。

 This is a paper we wrote with one of my former former masters students， now Ph student at MIT。

 and then with West McKinney， the guy from Apache Arrow。 So for this one。

 this is from our older system Peloton or noise page。 And it was the idea was how fast can we get。😊。

The line item table of the order line table out of TCC， roughly7 gigaby data。

 how can fastly get it to the client So the client isn't doing any competition on it。

 It's just how fast can you get it。And so。Our system supported the Postgss wire protocol。

 So this is like this is the default， like Postgs wire protocol without compression row based。

 This is how fast you can get the data out。 So natively。

 our system was storing everything as as Apache arrow tables。 So that in our system。

 you could do transactions。 then over time as as the data got cold and you weren't modifying anymore。

 it would just then flip some bits around。 and then it would be naly starting Apache arrow。😊。

So this next bar here is what you get from what they were prop posing in the paper you guys read of like。

 here's the vectorized version of the Postgs wire protocol where you're sending as a PACS format rather than as Rogue orranted。

But then the next approach is using early precursor to ABC。

 the arrow connectivity stuff where this is like natively sending out the Apache arrow data in its form not doing any translation just natively shoving that to the Python application and so it's faster because there's no conversion over to convert it into a different form。

 it's exactly for what we're sending the data we're storing natively a memory。

 we're those bytes right out。And so now the last one is RDMA， I'll cover what that is in a second。

 basically this is like a network accelerator to do kernel bypass to literally get the data out of memory。

 put it on the NIC and send it out without having to copy things into the CPU first。um。

And I forget we use。I think we used to fan a band for this one， but again。

 this one also is just sending out native arrow blocks rather than doing the conversion。So， again。

 even though the paper you guys read didn't didn't implement， you know， didn't have。

arrow at the time to send it out。The performance difference I think， would look like this。

So heres what I'm saying， something that AD received is shoving data out as arrow is the right way to go if you're building a modern system today。

Yes is there。It's question， is there a cost to convert whatever Postgres is into arrow？I mean。

 certainly yes。150 that shows the cost of。はいコスプス。No。

 this is the cost of converting arrow into a Postbu compatible protocol that sends things in a vectorized format。

This is like， I don't do any copying， I just literally shut the bitetes out。

And the paper talks about it like to do。To do something like this， to rewrite your R protocol。

 it'd be very unlikely that you're storing that data naly anyway。😡。

If you just have convert things to arrow or have things already be arrow internally。

 then that's a better way to do this。That's why you see some systems。

 like the intermediate results going from one operator to the next of the query plan or how they exchange data between the different workers。

 if everything's an arrow， then you have the infrastructure to shuthove the data like that。Okay。So。

These experiments are show here。We talked about how like， okay， the network protocol。

 you could press things， Is it how are you encoing the serialization format。

 how much metadata you're standing around。That was what we focus on。

 but that isn't always going to be the major slowdown of sending things over the network。

RightAnd as I said many times， the O is gonna to be a problem for us。

 It's always going to trying to ruin our lives， make things harder for us。

 break up our marriages and whatever right And in particular。

 TCPP stack is' just gonna be super slow and ideally we want to try to avoid it So why is it slow Well the networking implementation is based on this model of interrupts Sore they're assuming these interrupts gonna to come along And that's how it's gonna trigger things like hey bytes are ready to go in and out。

 and you do a context switch like all that becomes super expensive。

 Then you get data coming on the niI。The OS wants to copy that in its own internal kernel buffers。

 And then before it hands you that memory， it's going to copy into your user based buffers。

 what's that face。I that which wrong？So sorry。Yeah， this sucks。 Yeah， This is terrible。 Furthermore。

 right， so the kernels got under the threads coming down and they're handling the interrupts。

 They're handling things coming over the necks and hardware and so forth。 Well。

 those have to be scheduled。 They have to maintain their own latches for their own internal data structures。

 All that is going to be problematic， right。😊，So we want to figure out a way that we can avoid the O S as much as possible。

 Yeah， we need we need the O S survive。 We need to give us some memory and obviously schedule us。

 But after that， we want to avoid as much as possible。

 And that's going allow us our run to run faster。 So what I'll talk about next is gonna be focusing。

😊，Primarily for networking stuff， but this also applies for disk。

You want to avoid the OS for disk as much as possible too。

All right so the first approach to me what I call kernel bypass and the idea here is that we want to be able to get data directly from the hardware。

 in this case， the NC， the thing that the network interface。

 we want to get that into our database system running in user space into our memory up there without having to go through us without doing any copying ideal without having to talk to the OSTCP IP stack right。

And so there's， there's three different ways you can do this。 There's the DDK， RDMA。

 and then I O you ring is is the。I's going to be the newer one， right？So。

The way to think about this is like。Linux is a time sharing system。

And that means it's going to rely on these slow， expensive interrupts to again。

 tell it when there's something new showing up and take away some know。

 take away executing some thread to go that now the kernel thread deal with whatever that that interrupt handler。

 right。And all these additional threads on the inside。

 they're going maintain their own latches and all those things are gonna to be problematic for us。

 Now， Linux has gotten a lot better in the last， I mean。

 the 10 years or the 10 years has gotten way better for handling with。😊，You know， larger core counts。

 has's got way more scalable than it used to be。When there's contention。

 no matter how great your code is， everything's always going to fall over。

 it' going to avoid as much as possible。let's go through these 1，1 one so the DVDBDK。

 the data plane development kit， this is from something from Intel so it's a set of libraries that allow your user space program to interact with the NIC directly。

 there's an equivalent for in the storage world called the SDK。

 the storage plane data kit also from Intel and the idea here is that you treat whatever the hardware device you're trying to interact with as a raw device meaning you're responsible for like reading the low level bits in the memory space of that device and interacting with it this goes against the Uni philosophy where everything's a file no matter whether it's a file on disk or it's a hardware device you interact with these things that's files F reads and so forth but this breaks this model entirely。

😊，So now because now the O is is we're removing the OS from from the low level layers like 3 and 4。

 that means that in our database system， we're responsible for doing a bunch of stuff that the OS would do for us。

 And ideally， we we could do this better， but not always。

 So the most obvious thing if we're doing this using the DK to do networking stuff。 well now at。

Since there isn't the TCPI， the OS S isn't running the TPIP stack for you on the device。

 we have to do that in our database system。If you either write it by hand or you can use an open source library like Ftack that basically reimples in userspace TCPI。

 like sending the sequence numbers， sending Mac X， like all that we have to do ourselves。

 the OS isn't going to do this and Harvard doesn't do it。

But the advantage is that we don't have any data copying because were now we're getting literally raw buffers of packets。

 we have to manage what those are off the device。We're not calling a read， Ex me。

 there's no cis calls。 Everything is done， again， reading directly into memory。

So this sounds amazing， right？Well， it's not that common， right， As far as we know。

 there's only two systems that actually implement or used DK。 The first is Scalia DBs。

And they have this framework called Cstar that they're built on top of。

 Scalia D B is a reimpleation of Apache Casandra and C plus plus with like Co routines and D BDK and some other optimizations or Casandras entirely in Java。

 And then yellow brick will cover later on。 They also used this as well。

 But we had the Scalia D B guys gave a talk with us a few years ago。😊。

During the pandemic and they mentioned how in the Cstar they yes to use Co routineineGDK。

 but DDK for them has been a total nightmare to deal with。

 and I think it's turned off by default at this point。

 I saw the yellow brick CTO a few weeks ago at Cder and as far as I know。

 they're still using DDK for their implantation Again we're doing this they're doing this though in the back end not between the client and the server。

Right whyhy is this so hard， well again， because you have to implement a bunch of stuff that OS normally do for you。

 give them limit it yourself， and we tried this in our system。

 we had one of my best masters students try to use FStack to speed up another project we were doing to make a Postgres proxy run faster and we couldn't make it work。

The engineering cost is just way too high。So to。It's a bit crude。

 But this is one of my favorite tweets of all time。 So this guys talking about SBDK， which again。

 that's where the storage plane datat。 But the DBK certainly applies here。

 So all this kernel byss stuff is fantastic。 You think you're gonna get to big win。

 but it's like pain your pants， because you're cold。 And then you regret it pretty quickly。

 This is the guy real。😊，Is it okay。Thank you。は。Okay。

rightSo the next approach is to do R and this is where you have a it's like MVmeE there's an API that the hardware provides allows you to do right directly into the hardware device and get to access things on a remote machine as if it was local So for this one's a bit more tricky because now if you're reading writing to memory addresses on a remote machine you got to be sure that what you're actually reading is what you're expect to read So there is a bit more handhaking up to do to set this up。

 So this typically again something you maybe want to use on the client in the server。

 you want to do this on the back end。 but if you can pull this off， then you you get a huge win。😊。

So it used to be you could only do this on a Finna band， which was was sold by Melanox。

 I think the video bought Melanox recently or some at some point， video， they have Mvy link as well。

 but like。And then Rocky is basically R may over。Cverged Ethernet or something like this is more common now。

RDMA is not used that often， like the only system I know that does this like the sell you is Oracle for Exadata again。

 but that's like you buy the whole rack， you buy the rack of compute and the rack of storage and they're using RDM to communicate the compute and the storage you you can get RDMA on Amazon but you would only need to be able to do the communicate between your own machines that have that and it's a lot more work to get that set up。

Yes， this works。The client knows exactly what address data stored on the server。 Yeah。

 just says me0 x 1，24 Yeah so statement is， and it's correct。

 Like the way this works is that the the client it not to be again the application could just be the thing is gonna talk to some of the machine has to know what memory address it wants to read assuming has permissions。

 And then the request is give me the contents of that memory。

 So the hardware knows how to go up to memory， get whatever you want and pull it back down。

 And it doesn't notify the CPU that it's done that。Yes。Is there a security problem？

The question is there a security problem for this sure， but？You know， you run this in your VPC。

 you' letting you're not letting you don't expose this over the public Internet。Again。

 if you're buying exadata， these things are like millions of dollars， you're running this on prem。

 it's a locked cage， the traffic is just between these two things。😡。

All right so the last one is IOU ring， which I think some of you guys are familiar with。

 but this was an extension to in Linux to sort of clean up their asynchronous AIO API that allows you to do asynchronous request to hardware device either storage or network it originally storage and then they add a networking two years ago and basically the idea is that you have these circular buffers where you submit a request and say I want this data from this storage device or this hardware device then you get like a callback you provided it to say okay when it's available in my buffer。

 let me know so you can make bunch of these requests I don't think it's not entirely bypassing the kernel。

 it's just you're not paying overhead and making the cis call to and block waiting for the data so you make the request to do whatever to read a write whatever the memory that you provide the OS the OS does it for you in a kernel。

And then once it completes the task you have it to do。

 it puts the result in a queue and then gives you a call back， right？So。

 these is a low laency way to avoid the overhead of a full cis call to talk to hardware device。

 but you're still relying the O S to do the low level marshaing of data in off the device。

 Yes correct thought there was no。 I just check the completion。

The library has four different ways to do it， so you can either be pulling like keep checking or you can also log if you want to you can also have。

There's much of these libraries， and you guys look them up for rust。In Linux or in CBOSOSs。

 they provide different program APIs。I don't know which one's the most common。That was one I do。

So as far as I know， very few systems do this， although you guys are。Well， there's two more。



![](img/115c8db2b302299415f04b0cd0914410_5.png)

Yeah。The first one is Ques EB。So they talk about in was the 2022。

 how they added IUU ring and then for this one， Que EB is a Java。

 the top part of that is Java and needs J and I to call it down CP++ code。😊。

Tiger Beale is another one。And they're using Iing。 But this， this is for transactional stuff。

 This is actually written in Zig， not rust。 And so I think there's some library in Zig that made this piece of thing to do。

 but。It's interesting Yeah， and we talked to somebody recently or yesterday who was like。

 the imba fast lanes and Zig because the Sdy stuff was way better than than rust。

The engineering one though is Clickhouse。So they came out with a blog article in 2021 about， hey。

 they're adding Iu ring an asynchous Io to a clickhouse。

 there is a we had a guy give a talk from the Postgre team about adding IUu ring to Postgres。

 but that's going be I think years away because they're rewriting the whole storage layer in Postgres。

 And I think they're finally give over to the pagec， which is nice。

 But there's this blog article talk about hey hey look here's what IU ring can do for us gonna be a big winim。

 he submitted the pull request。 but then when you go look at the pull request， lo and behold。

 you come down here and here's one the original developers of clickhouse and current CTO。

 He basically says like yeah， tried to adding it， but it was marginal improvement and it became an engineering nightmare。

 He says it came so complicated that even an experienceds engineer。

 the author of the code cannot figure out why there are rare hangs and queries。

 they found through their testing。😊，So that was， so the blog article was 2021， this post is 2022。

 but then in the release of posts of Clickhouse in February 2023。

 here's the same dude giving a live stream talking about how they've now added IU ring so they did end up merging this code and they're touting how it's the magic pill to make IO less slow in his webinar。



![](img/115c8db2b302299415f04b0cd0914410_7.png)

But then you go look at the pull request again。And this is just a few weeks ago or a few months ago。

 he's posting here， I did not observe IOU ring to be much slower。

 but also I have no big expectations because I wasn't able to find cases when it's faster because he's responding to somebody up above that talks about how IOU ring when you enable that makes his queries one slower。

So。ID啊。😊，Yes， go ahead。None of them are as synchronous， they're all built to be synchronous blocking。

the rest of the framework is nice like the query execution code itself。

Is blocking yes how would they ever get any？Performance other than batch system like batching and then。

You I， I need to read these 10 blocks， go batch a bunch of stuff。

 go process someones that are available。 And then in the background， you know， when's available。

 I could process that。 I think that I think it what're doing。 I don'， I don't know about quest E B。

QutDB is written by HFT guys out of London and those dudes all sorts of like they know how to make Java really fast。

 I don't know how they implement theirs。And Claudeelson did it， but they did it badly。没。

Because you're using MMM， and then they switches to I green so of course。Yes， so you should。

 they have a crappy M limitationation and then they're like， okay， it's basically like like。

If I chop my leg off and I can barely walk， but I sew the leg back on now I can walk like it's yeah。

 got it。

![](img/115c8db2b302299415f04b0cd0914410_9.png)

O。All rightSo I think I don't want to comment。I think that the jury's still out。

 I think that this is still pretty bleeding edge， but interestingly when you guys come up with。

Alright， so Im going to quickly talk about two last things。

So these are all sort of user sort of kernel bypass methods。

 but there's another alternative is instead of trying to。Avoid talking to the kernel。

 what if we put things in the kernel that we would want？To avoid copyping up in the user space。

So it's take time let me skip this So this is a technique called user bypass。

 It's not a new idea like people have done kernel modules and extend OS kernels for decades What makes it different now is what we'll see in the next slide but the idea here is that。

😊，Instead of trying to bypass this part here and pull bunch of this logic up into the database system。

 what if we can put database system logic down in the kernel and so that when data comes in。

 we can process it or do whatever we want on it as quickly as possible without having a company user space and then if necessary。

 go back down to the Harvard to send things back immediately。

So this makes sense when the data that's coming in with the network or whatever it is。😡。

Doesn't need to be retained for a long time。Like if it's a。

If it's like a say an acknowledgement message and let need to keep track of that I got it。

And I don't need to retain it， then this technique of pencil potentially would work。Right？

So because you avoid all the overhead of copying buffers of sketching additional threads and making system calls because everything now is just running inside the kernel。

 which is always going to be faster。So。As I said， kernel modules are one way to do this。

 but like if you' ever written a kernel module before， you can dash HBT。 It's a pain in the ass。

 It's super cumbersome。 If you crash what do you get， Col panic。

 you take everything down and then in some scenarios。

 you can't even load kernel modules for security reasons like the horror won't let you enload an unsigned unsigned kernel module right。

So the thing that has changed make this actually viable now is something called ETPF。

At curiosity who here has heard EPPF before， other than people that hang out my student mat， right。

So BPF is's tell what BF what EPPF is， BF it stands for the Berkeley packet filters。

 so this is like in the early 90s they had it was made for BSD eventually made Linux but it was a way to specify like packet and forwarding rules and filtering rules like through a DSL you then load into to the kernel and so EPPF。

Not really about packet filter anymore， but it's basically a way to take write safe code that then gets verified and then load that dynamically as if it was a kernel module on the fly and the reason why I'm saying sort safe is that they give you a limited API。

 which you're allowed to actually do in these kernel module programs that you're running you can't call maloc you can can't sit in an infant loop forever because theyre ideally they're trying to avoid you taking down the kernel and breaking everything So you write your code。

 your B program in C code you run it through their compiler that generates bycode that then runs through a verifier and literally does basically branch expansion that figures out all the different possible paths。

 you could go down in your code and counts the number instructions that you would execute and then throws an error and throws back and rejects it if you have many too many instructions。

Right。So this is a wild thing because again， this basically allows you to extend Linux。

Without having to re Linux。 So， so this is heavily used it like Netflix for like observability to be able to。

 you know， get metrics about what processes are running and and get kids this data out。 But as。

 as the。Since Matt's been working on it here， the API is expanded。

 So there's a lot more things you can start doing now。

 you can basically run an entire database system down in in your kernel。

Whether or not that's a good idea or not， that's what his research is going to figure out。

 but are the idea that can we start thinking about what part of the data system that we're spending a lot of time on moving data back and forth being the OS of the hardware and the database system。

What can we start pushing down？So I'm going to show one graph from his paper where he was reimplementing the Postgres wire protocol proxy so I think on proxy was sit in front of Postgres the client connects to it and the proxy maintains available connections to the data system and just forge your packets along that so in this scenario here。

 packet shows up to send a query request。😊，And then the proxy just looks at it says， oh。

 needs to go to this server and this sends it。 It's all it's really doing。 It's not。

 it's not doing any computation on it。 So we're comparing its P G bouncer， which is the most common。

 most common proxy limitation use for Postres。 Odyssey is out of the indexex。

 And this is like doing runs in user space， but they're using like。😊。

handandwritten cover routines written in an assembly where the assembly overwrites the stacks of other threads to put inject like what the next thread to run is very impressive。

 but it's very complicated。And then ours is based on it's a fork a PG bouncer where all of the authentication stuff happens up in the user space like SSL was setup up and things like that。

 all that or user password stuff all happens up there， but then when packet show up just to them。

 all that's done down EPPF。😊，And so the main takeaway here is if you run on a really small machine。

 you're getting pretty significant performance improvement because you're not paying the penalty of copying things back and forth between the kernel。

So I'm not saying BBF can be solved for all the things that we talked about today。

 but I think this this is。This is going to be a better solution than something like DBDK。

And potentially IO U for some things， but not everything。はい。I've got one minute left。

 let me just banged through this real quickly。Soon we do all the optimization to get things out of the server back to the client。

😡，Clients got to do something with it and put it into the format that the application needs。

 And as I said， if it's JDBC， OBC， like that's copying things as a oriented format。

 thats you know the overhead is not gonna to be that significant。

 But if it's the scenario where it's a data scientist trying to get things out of the data system and put it into pandas。

 then that's going to be slow。So this here from this is an experiment they did where they took pandas ran a SQL query through panda's SQL API that went to pose with MySQL。

 got data back and then converted it into a data frame。

 Data frame is like the table abstraction in pandas and a bunch of other Python systems So in this case here the chart showing that the query part is not not that。

It's nott take a long time relative to all the cost of actually copying the data off the bits we've got from the server and converting it into the data frame。

 Again， A0BC with arrow solves this problem because if if your Python code can interactly natively operate onarrow data。

 then you don't have to do this conversion， but if your system doesn't support the ADBC。

 like my Postgres， then you have to pay this penalty。

So the gist of what they're doing is that they have this thing called connector X。

 it is using Pols and a couple other systems I think as well like Moin。

 and basically your SQL query shows up that you write in Python you then also provide some information on how to split that query up into subqueries or partition queries like range partitioning and then you send out multiple queries at the same time from different threads that are going to get a portion of the data that you would want to put into your Python program and then each threads then going to populate the data frame at different chunks。

So instead of taking one SQL query， get back a giant result， and then one thread populates the table。

 they take one SQL query， rewrite it by adding additional expressions in the wear clauses。

 then send that out and parallel， get back multiple results， and then the threads put it together。

I just want to bring this up because it's an alternative， if you don't an ADBC。

 that this is another approach to do this。All right， we're well over time， so I apologize。

Netwing protocol matters a lot， kernel bypass can make a big difference， but it's a pain ask to use。

 I think EP ofF is going to be something that's going to get a more uptick in the next 10 years or so as EP ofF gets more expressive。

Okay， so next class will be on query optimization， and we'll have three lectures on that。

 And that'll be again， the， the core material we need to understand before we start looking at other real world implications。

 And I know I haven't posted the。😊，The updated the reading list because I don't know what paper to read for the first class because there really isn't a good one。

But， we'll figure something out。 but I'll be the reading list tonight， okay。



![](img/115c8db2b302299415f04b0cd0914410_11.png)

Any questions？Stpped the six packs on the table and I'm able to see St I on the way。

No short put the cross you know what got them， I take off the cat but first' tap on the bottom。

 don about three in the freezer so I can kill it， cat full with the bottle baby don' feel it because they nice and says the pain nice way you drink't get down with the guys in。

Take back the pack of goods。Look to some now for T to the front， Billy Des f to tell weak guys。

 be a manic get a kind of faint God。