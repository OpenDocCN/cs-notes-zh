# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P113：12_Elasticsearch概览.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/694174f9134977ab614fd6ed7759a728_0.png)

So now I want to talk a little bit about ElasticSearch。

 Elasticse is one of many possible eventual consistency databases that you might use。

 it just happens to be the one that I have， I don't have a lot of experience。

 but it's the one I have the most experience in， so I will use it。

And it's really commonly used to add value to an otherwise acid based。System。

So the history of Elasticse is that it emerged from an earlier open source project called Lucne and the idea was was to replicate the things that Google would do。

 it wanted to be super distributed， it wanted to take a fire hose of input data。

 it wanted to be able to handle terabytes of data at rest。

 do large scale parallel searching really fast， throw cheap commodity hardware at it make it go faster。

 very much an inverted index with value add with languages with stemming ranking and relevance and all that kind of stuff。

 probably far more sophisticated ranking and relevance than Postgres ranking and relevance。

 which is not bad， but it's not great。recommendation engine。

 all the kinds of things that you might want to do in an application that wanted to have Google like features。

 I mean at some point there's this thing that says like every application has as a search box and I think that's a fair statement that every application should have a search box as long as it has information that people might want to find there was earlier project called Apache Lucne。

Which is really the indexing part of the technology。

 Exastic search is a really smoothing layer on top of a lot of otherwise difficult to do。

 and it almost is like when。You're outsourcing to Amazon you know DynamodDB。

 it's like there's something in there it's really complex and the same is true for Elsearch。

 there's something in there that's really complex， but you don't worry too much about that it just it organizes within Elastic search and what happened was what started out as kind of a search box feature for applications has become it's a no SQL database in its own right。

Primarily because the inverted index had to be super performant and updated， distributed。

 and there's a lot of really nice things about it that basically made it almost out of the box。

 really good， no SQL。Or base style database， I am real sensitive when I talk to you about technologies。

 what their license is and Postgres is an open source community。

 one of my favorite open source community just impresses me how long they function in the height of the high level function that they have。

Elastic search is not entirely open source， they use a license called open corere。

 there's a core that is Apache licensed and then there is this elastic company I think it's called Elastic envy that supports it and they're a very large company and very successful company and open corere。

Is there's a whole range of whether I like Open corere or not。

 there are some open corere vendors that I think are monsters that just are open cores bait and switch。

Elastic somehow is a reasonably sized company that has pretty good commitment to open source to the point where I think a lot of people use Elasticse without even realizing that it's not an open source project。

 it's an open corere project。You can certainly build everything I've ever done with Elasticse is the open sourceversion and the problem with most open corere companies if their open sourceversion is lame and then they're like。

 well you should just pay well and that's pretty bad so it's okay I think for elastic to charge for hosting and consulting but as long as we can do the things we want with a pure open source version and they don't show any urge to sort of like deprecate the open sourceversion or sort of bait and switch you I'm okay with that but I just you take care of that yourself you take a look at that yourself。

And hopefully there's enough of an open source community around the open source parts of Elastic search。

 which is the core parts that they're not going to be motivated to sort of go evil on us。

 the kind of the way I talk to you about how I'm nervous about myQL。

 which is not particularly an open corere project is just because they own it， it's a oracle。

So I use Elasticsearch in a project that is called SCaiI。

 which is an open source learning management system， a real open source， not openCore。

 and we used it in a hybrid kind of a situation， so we have database system， MySQL or Oracle。

 MySQLs are preferred for all the kind of transactional bits and grades and memberships and classes and things like that。

 we outsource the file storage for PDFs and things that students and teachers might upload and then we have an Elastic search instance and we feed both the blog posting。

 discussion postings and pages and everything we feed all that into Elastic search as JSON documents by extracting the text and then sending the text in as a JSON document。

And we also have extractors that read through PDFs and Excel spreadsheets and Microsoft Word documents。

 and there are extractors that extract the features from those and then they feed those into a elasticastic search index as well。

 and then we have a search UI that we we talk in the user interface。

We talk to Elasticse when you type something like。Relational into the search engine。

 we find the posts that mentioned relational and the Excel spreadsheets that mentioned relational et cetera。

 et cea， et cetera， so it's a very hybrid system we're not really using it as a no SQL database so that's just sort of a lot of how elasticastic search has historically been used。

U， probablybably the one of the more popular applications of Elasticse is called the elk stackack。

 the Elasticse， logg staash and cabana all。Open source mostly。And this is beautiful。

 they're using really elasticastic search in this case less as a search engine and more as a nosQL distributed databaser。

or our eventual consistency database， log sta is that like logs are the things that all these production servers are generating as fast as they can。

 a lot of data analysis is done with logs， and so log stash has basically received these things and then just blasted into elastic search。

And I talk often about how most database activities read mostly， but this ELK is often right mostly。

 I mean on average it's probably doing more writing and has a higher demand for quick write performance and it does read performance which is really kind of great in that it stresses the underlying Elastic search database in ways that you might not stress it like we don't express it that way in SakchiI because。

How many PDFs get uploaded well couple an hour， which is different than a log thing that's coming out 100 times a second a search can absorb a fire hose of data。

A lot of the early noSQL work was read mostly and so it could absorb it at a certain rate。

 but it just couldn't and it had a great read performance。

 but its ability to absorb rights was kind of a troublesome a lot of magic systems have trouble with rights。

 but this ELK application or this ELK sort of kit，Means that right performance is really good with Elasticse and then there's cabana which is a visualization system that you may run into and once your data is an Elasticse。

 you can create dashboards that just kind of blast the queries out and in this you see multi-reader supermassive performance and nice parallel distributed scattered gather and all that stuff comes into play when you want to basically have ask what happened in the last 24 hours and boom you have a dashboard so this ELK is a really beautiful use of Elastic search as a nosQL database that pushes pushes deep strongly pushes the envelope of right performance and reperformance and it simply couldn't be done with the relational database system and so you just make this elasticse thing bigger and smaller based on the resources you throw at it it automatically reorganizes itself and in there there' is loose seen in a whole bunch of other things but elasticasticse is kind of like the nice wrapper that works。

Around it so you I mean I haven't yet done anything with cabana but I really want to I mean I like elastic search and I like its right performance and I like its read performance and cabana seems like like a no brainer it's pretty d and cool so。

So if you look kind of at the internal architecture of it is it's all based on RE web services and that's why I say it's kind of Elastic searcharch as a wrapper for a whole bunch of complex things that themselves might be difficult。

 so in a sense elasticastic search as your dynamodDB except that you can install it and run it yourself and so you can feed it data at a high rate of speed and you can take data out and get queries and it's all inside completely distributed。

 there's all this eventual consistency， everything's communicated indexes recalculated and everything are all like just magically delicious and we have a beautiful little RE web service API which makes it really easy to talk to it in just about any language because you're using JSON and REwe services and if you're using Python or PhP or Java or whatever this it's really pretty straightforward and the elastic folks have built really cool clients that make talking to elastic pretty easy from a wide range of programming languages。

Of course， given that the data can come in to any of those servers。

 that's how it has really super fast right performance。

It is an event eventual consistency system because the indexes are done sort of after the fact so any of those servers can receive a new document。

 any of those servers can start the indexing of that document。

 then add those to the inverted index and the inverted index itself is widely distributed and then so the newly indexed documents are sent across and exchanged and you know in a few seconds to maybe a minute or so they are all eventually consistent。

 but the indexes are eventually consistent I think that's probably。

I would say probably because it's really based on a search engine， paradigm。

 the distributed indexing is probably the most one of the most advanced NoSQL databases when it comes to distributed indexing。

 because it started as a distributed indexing problem and then kind of wrapped a NoSQL database around a super fast distributed index。

So this gives you a sense of the structure of the URL and the ones we'll be using in this class it's you don't use HtTPS you can you can send the credentials right on the HTP command。

 but the key is is on the end of it there is a。There's two parts of the URL， one is an index。

 you could think of the index， the index is kind of like a table。



![](img/694174f9134977ab614fd6ed7759a728_2.png)

So those URLs that you'll see when you start writing code。

 that's the structure and again it's a rest web service so I'm showing you a URL。That captures this。

So up next we'll just kind of talk a little bit about the programming pattern for El search。

 but then the most fun will be in the actual code walkers。

