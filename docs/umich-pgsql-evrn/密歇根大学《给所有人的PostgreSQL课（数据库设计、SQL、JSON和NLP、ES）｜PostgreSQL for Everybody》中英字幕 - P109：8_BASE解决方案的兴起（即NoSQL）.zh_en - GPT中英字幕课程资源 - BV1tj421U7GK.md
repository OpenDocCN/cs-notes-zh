# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P109：8_BASE解决方案的兴起（即NoSQL）.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

So now we're going to talk about how sort of some of these early cloud experiments turned into sort of the NosQL movement。

So the base style databases is you got a fast network， you distribute it as wide as possible。

 you don't have any central locks， you have lots of fast， low memorymory CPUs， lots of disk drives。

 not necessarily per CPU but lots of disk drives because you have lots of CPUs。

 you know you basically use data sharding and the indexes are more about figuring things that where things are at。

 you end up with documents， not rows and columns， things like the friend list is just a document that the friends right？

And another thing you do is instead of like coming up with a schema of exactly what your application wants to do that has rows and columns in one database。

 you're just like it's kind of a document and there's some key value pairs and if like on a Tuesday I want to add another key value pair。

 you got a kind of nice migration， you just add another column it's says if you had a schema but you could change it anytime by just inserting into a column that didn't exist and then they're all text right and and a way to think about this is it schema on read。

 you just write the document and then you can sort of。

Read the document and look for values that you expect to be key value pairs that you expect to be there。

 so that's kind of like this next generation， no SQL， no schema。

 but there is a schema as we'll see when we with play with these kinds of things we'll see that there are schemas。

 but they're kind of late schemas， they're not early schemas when we're doing a acid we must have the schema from the beginning and you've got to be real careful as we evolve it。



![](img/28cb2b42cab5764a12a430abf972fb3f_1.png)

Another trend that was happening during this time is JSON and we talked about JSON and JON's really awesome。

 it's a great way to just represent key value pairs， it just is wonderful。

 there's fast pars in every language and again I've never built one but just imagine。

How awesome you could compress JSON if you really wanted to and one thing about databases that it loves to do is squeeze stuff into less memory so you can cache more and everything and so just imagine like the keys of JSON becoming just numbers Oh it' just iss really cool compress it save storage。

 save data transfer everything just awesome a JSON is a cool format。



![](img/28cb2b42cab5764a12a430abf972fb3f_3.png)

It seems simple in the beginning， but then you realize that JO has touched everything and it's really a beautiful thing。

So in this timeframe， a series of open source NoQL databases started to come out a thing called CouchDb。

Was funny， a cluster of unreliable commodity hardware， which is exactly what I was talking about。

 right？MongoDb often came out along with a node system， which had JON storage and it was。

As we moved more of the application into JavaScript and started using AjaX and JSON。

 and even then microservices， the Mongo Db was really sort of very much part of that movement。

 Cassandra is the Facebook engineers who you know figured out how they built Facebook and they kind of built some open source like Facebook like capabilities。

And there's like Apache Hadoop， these are open source solutions in this nosQl space and then Elasticse。

 Elasticse came from really trying to replicate Google's search。 It's less trying to be a database。

 although in later later years folks are like I can use this as a no SQl database and its indexing ability is superior So it was using indexing technology because in a way a lot of no SQl databases are a relatively simplistic document store layered with a really powerful searching capability and inverse index and all the stuff we've talked about except just specialize on that like there is no regular index。

 There's only inverted indexes then we're going to do that really well。

 and now you're kind of like Google Google search is just a really awesome inverted index but。



![](img/28cb2b42cab5764a12a430abf972fb3f_5.png)

All the engineering in Google is not how to store the documents。 it's how to build， maintain。

 understand and make good use in a scalable way of the inverted index。

 So there's a whole bunch of these no SQLs that come out。

There's also a bunch of software as a service， and this is a really interesting trend that。

 in a sense， you use DynaODB that comes from Amazon， we don't even know how it works。

It is the stuff that Amazon uses for itself， so they're eating their own dog food as it were。

 but what's cool is instead of you having to install MongoDV and hire a person making $150。

000 to run your NagoDB cluster， you just use dynamoDB and pay $10。

000 a month for the amount of bandwidth you're pulling in and out of your dynamoDB。

It seems expensive to pay $10，000 a month for a database， but if the option is to pay 150。

000 for a software developer and frankly you need two or three of them if you're really going to be serious about it and that's going be half a million dollars to have enough software developers to really run Mongo Well Amazon starts to look like a super bargain Google had big table。

 I used big table when I used app Engine and I've actually used DynamodDb found it a little bit slow so I just use Elasticcache instead I used it and I stopped using it。

Google Big table， I used that and I went through a heavy app engine phase in 2008。

 2009 I wrote a book on Google App Engine， I used big T。

 you could see how big table could be used to build a Gmail like application or to build a web crawler but not necessarily any other applications and I kind of。

Had my time with Big Table and kind of walked away from it。

 I was frustrated with Google's and Amazon， frankly's DynamoDB。

 I could not do performance analysis because it was too magical。



![](img/28cb2b42cab5764a12a430abf972fb3f_7.png)

Now that doesn't mean you shouldn't do it and I know plenty of people that have good experience with Dynamo DB don't know so many people that use big T heavily and aszure Microsoft is always catching up。

 always catching up， but that doesn't mean that Microsoft is bad it just means they're catching up one advantage of coming late to the party is that you know what everybody else did。

 you can look at the open source stuff then you can save yourself a lot of time。So of course。

 Facebook is。Jillions of dollars right， and so every startup decided that the way to make money was to build a single cloud scale。

 truly second generation cloud scale application and just make money because that was what Facebook did and YouTube did and Google did and I want to be like them。

And and so there's a number of trends that were happening during this time。

 the emergence of client side applications， which are JavaScript， you know， backbone。

 angular Re and view， just each one is sexy for two to three years。

 and then there's a new one that comes out。Breaks all that stuff and they go like oh that thing that was cool last year is not cool。

 this is my cool thing now which is cool it's evolving and frankly I think there's a technology iss going to wipe them all out called web components I hope to see that one of these days that we don't talk about those anymore and we just use the browserbased web components but' that's a slow process to take all the cool stuff a back angular react and view and sneak it into the browser itself。

Also， the emergence of No JS， which is JavaScript in the server。

 which allowed people to learn the JavaScript to the client and JavaScript in the server and certainly the JSON Exchange and AJX was all happening。

And then you just pick an OSQL database like MongoDb and node and way you go and the startups。

 they don't know any better， they are starting， they have no customers and they write code really fast and a thousand people use it and it runs fast and then。

They find that when they get to 100，000 it all falls over and so that's the problem。In 2012。

 if we look at the Gartner hype cycle， we saw that no SQL databases were in the technology trigger。

 which means they're all talked about， talked about， talked about。

 moving up to the peak of inflated expectations and things go kind ofoo that's cool to we believe it solves all the problems in the world to like it doesn't solve any problem and then things get better So this is 2012。

 the timeframe that I'm talking about。 And so what happened actually sometime like I think 2016 is they stopped mentioning no SQL databases because it really。

doesnn't mean anything， so noiseki databases， which is how it kind of started all this。

 it doesn't mean anything base style databases does mean something。

 meaning the eventual consistency databases。So if you look at the data management hype cycle you see a whole set of things that are kind of like the progeny of noSQL like SQL interfaces to Hadoop document store databases。

 SQL interfaces to object stores so that the whole notion that there was going to be this no SQL revolution and SQL was going to go away that's kind of been replaced by these cool nonac databases are cool for certain kinds of applications and so that would talk a little bit about we talk about the start of the NoSQL movement and and or the maturation of the sort of true adoption of the NoSQL techniques。



![](img/28cb2b42cab5764a12a430abf972fb3f_9.png)

So I had a friend who founded a company and built it up and then eventually sold a company called Verite and they had a problem。

 they were going to expect about100 terabytes of information because it was a cheat checker that wouldnt read papers and see if they were borrowing from Wikipedia or whatever。

 it was going to be cloud， it was going to be multitenant。

 it was going to be single instance really a secondgeneration cloud。

 they started out with MySQL like everybody does， as a proof of concept。

 but they did not want to then build so much skill and how to shard。

And so they grabbed an open source NosQL database， Cassandra， and they leased a bunch of hardware。

 they went because they knew they had to play with the disk drives and play with a memory。UmAnd。

It worked great until it didn't， and then they had to bring in somebody who was a cassandra expert and that was super expensive and it really didn't fix anything。

 and so the problem with all these choices of NoSQL scales forever， it doesn't。

All it is is you don't know when it fails right it nothing scales forever and the problem is is that we have things like Postgres which are decades old and then we have something that's just like a year and a half old。

 you're going to run into the problem that's the problem with these especially in 2013- 2014 and that's why it was going up into this over expectations。

And the consultant failed， they had all this hardware， they had to just。

Dis card they had to throw all their cassandra code away。 They had to throw all their hardware away。

 They moved it all into Amazon， and then they switched to Amazon Dynamod Db and all of a sudden it started working just fine And then they just started writing checks to Amazon because they were going to write checks to consultants and get bad results with Cassandra or write checks to Amazon and have it work。

 Now the key to Amazon dynamoddb is it's not magic， you have to learn how it works。

 But once you learn how it works， you let Amazon upgrade it and do it andter tune it and whatever。

 And if you are a big enough company， you hire like an Amazon helper and from Amazon and they like can look at your stuff and say you can fix it this place。

 this and this。But the use of the NoSQL database allowed this startup to compete against a much larger firm that was using their own hardware and just it was really a much larger firm that was building their own data centers and all this stuff and sharding themselves and they doing their own sharding。

They were too were not agile because of those choices that they made and so they were able to compete and even though their Amazon bills were expensive it was way cheaper than their competition and so it's a really good story of no SQL but it's also a bad story of No SQL and that is be careful of what you just read on a website to adopt a technology and that's just a case study。

So that's sort of the rise of NoSQL and the modernization of the modern interpretation of NoSQL is really just like these are really cool document style databases that have their purposes but。

The asset vendors have not stayed steady and we will talk a bit about the reaction to the rise of noSQL next。

