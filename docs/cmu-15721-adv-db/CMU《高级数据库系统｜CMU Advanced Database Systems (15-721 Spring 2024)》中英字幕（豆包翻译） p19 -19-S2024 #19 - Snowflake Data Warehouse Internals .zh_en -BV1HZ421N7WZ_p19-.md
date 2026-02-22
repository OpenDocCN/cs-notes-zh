# CMU《高级数据库系统｜CMU Advanced Database Systems (15-721 Spring 2024)》中英字幕（豆包翻译） p19 -19-S2024 #19 - Snowflake Data Warehouse Internals .zh_en -BV1HZ421N7WZ_p19-

🎼Carnegie Mellon University's advanced database systems course is filmed in front of a live studio audience。

😊。

![](img/49e856a34f381d1149cd43adb9ca93a3_1.png)

🎼。🎼So today again， we're continuing down the path of to talking about real world systems that are implementing the concepts and ideas that we've talked about。

 so before we jump into today's lecture， again some administrators stuff that posted some of this on Piazza but I won to put it all in one place now so the final presentations for the project is going to be when we have our scheduled final exam。

 I think it's in this room the scheduled to start on Thursday morning at 830 a。



![](img/49e856a34f381d1149cd43adb9ca93a3_3.png)

That we're not doing that。 Let's start at 9 AM and we'll do or donuts and or bagels。

 we can decide what we want to do and then the written and final exam that will be given out the April 24。

 which I think is next week next next Wednesday again that'll be a。

It'll be a prompt to asking you a question about the doesn encompass all the ideas that we've talked about throughout entire semester。

 So it's not like multiple choice questions like what does this paper say， What does that paper say。

 because anybody go figure that stuff out。 It's more about synthesizing the ideas again。

 that we of all the various things we've talked about and applying it to a new situation。

Which is again， the main thing you want to get away get out of this course。

 in addition to all development stuff you guys are doing for the project。

 but like how to take all these ideas and see how they fit into the bigger picture of some some data processing your data system。

 okay。And again， that'll be due when we the same day we have the final exam。

 you just show up and hand it to me。And then we'll do what we did allow last year。

 you can use JTPT to help you answer the question， but obviously if you if you're stupid and copy the prompt or copy the output and put it right into your response without checking it。

 you can losing be problems。At least last year， when we put the question is it said I invented stuff。

 which is not true。 I sure it's not true。 So be mindful of that。Okay。

And then we'll also do what we did last year is you can， again， you're not penalized for this。

 you useGPT because why wouldn't you can it's。That' the way things are going。

 but we'll do a William will set up a Google form that I can't see and you just tell us whether you use chattGT or not。

 and then I'll try to predict whether you did or not okay。W， it's fun。Okay， any questions。Okay。So。

Do you know what is？You ever heard a scroll language？Okay， all right。Second。All right。

 I'll explain afterwards All right， so again， last class we were talking about Datarex phototon again that wasn't a fullfledged system that was an extension library that you would add that the Datab people added into Spark the Java code running Spark SQL would then evoke through J& I and that was a C+ C++ vectorized engine that would try to offload the computational expensive tasks when you're running query in Spark SQL and push that down to C++ and they showed pretty significant performance games。

😊，So today， again， when we talk about snowflake and。And we'll see this also in redshift。

 these are to be full fledged systems that going to look and smell a lot like Drreemel and other systems we've talked about throughout the entire semester and yellow brick as well。

So just like before we jump into snowflake， it's important to sort again to take a step back and understand what the landscape in the database world looked like at the time that snowflake came on the scene and a lot of this is repeating the things that we've talked about throughout entire semester So again in the 2000s。

 that's when we saw these special purpose of specialized OL systems that were built just to run kind of OL curve we talked about in the entire semester that they sort of came on the scene and for the most part a lot of them were pushing this idea of a column store it's a little before the vectorwise came along in the later 2010s。

 but everyone sort operating column stories compressed data and then vectorized showed how to do vector processing all these things So of all these verica and green P the two biggest ones MonD we've talked about and we'll talk about again ductDb byductDb。

 the early version ofductDb was MonDb。Which is a fork of this system。

 And we talked a little bit about that。 back why we covered an an master Park cell we'll see again when we talk about Redshift because Redshift wasn't written by scratch on Amazon。

 They bought a license to the park cell source code。

And we'll see the transition that going from a shared nothing system that par Excel was into into what Redshift is today。

 So for all of these except for vector wise Mo to be， these are all forks of Postgres。

And they ripped out the storage layer and rewrote a lot of stuff to make it up its own analytical workloads。

And at the same time when this is all going on， Hadoop became popular。

 everybody was trying to shoveel a lot of data on HDFS and it's data lakes before data lakes before that term came to prominence hi we talked about Presto and Paula and Stinger。

's actually stinger， we didn't talk about it's basically the same thing as Aala or actually。

Same thing is high， if it's SQL on top of maptepro and to dope。

So all these systems at the time in the various forms theyre supporting analytical systems。

 but their primary distribution model， like the company， the vendor selling the database system。

 the primary way that you got access to these various data systems was by downloading it and running it on Prem。

 So meaning you would buy a license to the source code or sorry。

 buy a license to the database system， but then you would provision the hardware and you would responsible for running it on your local machines。

 right。This is pretty much how you around A systems for decades prior to this。

So as we talked about last week， the Dremel paper comes out in 2011 and shows that okay you can build something in a cloud of native environment to run on a bunch of files that are sitting on these object stores。

 longer the storage are no longer natively managed by the database system。

Facebook also starts building Presto in 2012。 again， Park sales。

 we said this we'll discuss this next week。 we talk about Redshift。

 but A of us buys a license to Park sale in 2011 and then releases it in 2013 as redshift they actually beat snowflake to the market by a couple months where put snowflake。

😊，So I think it was written from scratch and and Redshift was was was based in Park Excel。 Park。

 I mean， I'll cover next week。 Park Excel was basically going bankrupt and they were hoping that Amazon was going to acquire them。

 Amazon does acquired the source of the license。 And I forget who。

I think Action bought in a B park cell。 So it's still around， but it's basically a zombie database。

So around this same time， there's a VC firm out of Silicon Valley called Sutter Hill。

 where they decided， hey， we're going to build a new cloud native database startup。

 so they got these two guys that were very prominent engineers at Oracle and then the vectorwise developer from the paper guys read Marzzen andsowski from Vewises going under at the time。

 so they got him， they buying these three together， gave them a ton of money and said go build。

You know go build a cloud cloud data warehouse， you know we'll call it snowfl Sutter Hill is different that most of the VC firms you' probably been familiar with like the Andson Horowitz。

 the Kle of Perkins， Graylock and so forth that their models is are like I have an idea and you go to them and you pitch them and say。

 hey， give me money to go build at startup。Sutter Hill is basically like putting together a boy band at a record label。

 You say， let's get some good looking people together， get them in a room， We'll give them money。

 and then they put out the albums。 right， So they're dictating what we should build。

 So that that's how snowflake sort of came about。 And so again。

 obviously Snowflake was super successful because here we are talking about it。 you know。

212 years later。 So， again， all these guys are super nice。 Marcson is。😊。

He's much younger than these two French guys here， but this just show you how hardcore they are about databases。

 probably just as hardre as I am， so this is actually Marin's leg。

 he has a snowflake tattoo after they win IPO right that's a dedication to databases I knew all that form。

All right， so what is snowflake？Snowflake is gonna be a managed OAP database system written S plus that is only going to run on in the cloud。

 And again， like this seems obvious today。 but back then 10 years ago， 12 years ago。

 this was this is sort of unheard of for database systems and certainly the snowflake guys have told me they got a lot of pressure in the early days like。

 hey， we great system know can we download run it on prem。

 we don't want to run in the cloud and they said no。😊。

And then eventually everyone just moved to the cloud， and that's where you。

 if you're a new database startup today and you don't have a cloud you know。

 a cloud offering with some exceptions like DDB， then although we'll see Mother Duck next class as well。

 like it doesn't you know， it's very hard to gain gain traction， right。So。

Everything everything's being written from scratch and the paper guys talk about like they you know。

 they considered like， oh should we go take things from like Hadoop or go take things from Postgres like other systems that have done and they decided that in order to have complete control of everything。

They wanted to write everything from scratch。They're going to be doing a shared architecture as we talked about before。

 and then one thing that's going to be different than we saw in Drreemmel。

 and I think the photon paper doesn't really talk about this。

 but Spar Sel doesn't really do this is that they're going to do aggressive compute side caching on the worker node themselves。

😊，RightSo since， again， they're not the cloud vendor。

 it costs them real money to go get things from S3， which is obviously also very slow as well。

 They want to do as much cashching as they can on their side or knows that they they're already paying for to avoid those those lookups to S3。

Right。the other interesting thing is that rather than doing what most people do it today。

 like taking the Postgres SQL dialect， the grammar file and using that as the basis to start your what kind of SQel you're going to support。

 they wrote everything from scratch。And it kind of looks。

 if you ever look at the documentation of sort of like， kind of looks littleac oracally。

 little Enprisy， right， And again， I think that's， that's。

That' sortt of the lineage of coming from the two French guys coming from Oracle。

So I I always have to say this obviously there's not any impropriety。

 but Snowflake actually sponsored this class in 721 before they went IPO。

 a lot of my best students went there and still stillwork there。

 so like a sheish stood literally here and presented presented the snowflake architecture back in the day so if you want you can watch the guest lecture from back then and last year when I was putting this lecture together。

 I had a bunch of questions like it's a close to system。

 you can't always infer exactly what they're doing based on the blogs in the documentation So I actually had a phone call with the sish。

 this is Sunday night the day before the lecture while he was like cooking in his kitchen。

 he's answering all my snowflake questions。 So the combination of what we're talking about today is from the documentation。

 the paper you guys read there's another paper as well and some blog articles and then asking a shish while he's cooking spaghetti what does snowflake do。



![](img/49e856a34f381d1149cd43adb9ca93a3_5.png)

![](img/49e856a34f381d1149cd43adb9ca93a3_6.png)

He's a good dude。Okay， so again， here's that high level bullet points of all everything that we care about in snowflake that you know。

 related to other systems， right， again， not surprising。 shared disk to storage。

 again they were the one of the first systems to commercialize this and pursue this But again。

 that' that's building off a demmline done， building off of what。

what HS and do were doing at the time， their new pushbased vectorized query processing relying on precomplied primitives similar to vector Y and X100 again。

 not surprising Marin was the guy who built vector Y。

 they're not going to do any cogen except for for serializing and desilizing the moon of data from workers with another they' using LLM for this it's very limited thing like I had some data I need to serialize to binary format。

 ship that over the wire and send it to another node again this is like 2013。

2014 before Apache arrow so to make this work fast they would have this little cogenn piece that could。

That you could compile it to send data over。And somewhat similar to what protouff would actually do for you as well。

They're going make they're going separate the table data from the metadata。

 and we'll talk a little bit about this because that opens up some opportunities from other optimization and' certainly different than I mean。

 now it's sort of commonplace because run something like hive catalog or whatever。

 Datarick has they a unique catalog。 but this is certainly different from a single node system。

 There's not going to be an explicit buffer pool and every single node。

 They basically have A or U cache aside when move things in and out。😊，But really nothing fancy。

 like everyone else， they're going use packs columnar storage because again。

 they started before parquet and orRC were like a big thing that they are now。

 they're going to have their own proprietary storage format that they'll have for managed data。

 but now since the last five years or so， they're supporting all the open source file formats that we'd expect。

I think they can do Somer's journal， but primarily most of the time they could pccas join as we talked about was always me better。

 and then they have a cascade style query optimizeizer that again tries to leverage the adaptive optimizations that we talked about before。

 so we're going to mostly focus on these things that put all sprinkle in discussions as we go along for the other topics。

So the first thing is， what does the architecture look like？So they are。

 obviously again they're going to run on disated storage。

 so this is just using an object store to leverage that。

 And again the paper talks about how they made this decision early on when designing snowflake。

 should they actually spend time building the storage layer or should they just give up control and use S3 and let Amazon handle that for them and part of that decision was it's from engineering efforts。

 you can only do so many things when you first start building a new system they decided they would rather focus on the execution engine and leverage clientside caching or workerside caching or computeside caching to speed things up and just just let Amazon handle all replication and storage their ability guarantees you would need because I think that turned out to be a smart choice。

 I think originally Vi Vi they only support S3 and now they support all the other major cloud vendors for their storage。

So they're going to have this notion of， yes。Sort of like because they're using Amazon or these other companies and they have their own databases。

 won't there be sort of conflict of interest， like they can do something this to snowflake？

His question David is if you're running on Amazon， Amazon has a competing product。

should you be afraid of Amazon trying to do something to screw you over？

But I mean Snowfl's a big company too， right， Yeah。How to say this？

Think about from a publicity standpoint， how terrible that would be for Amazon。 be like， hey。

 we just like screwed over our biggest competitor， one of our biggest competitors。

 like that would immediately panic all the other companies that are relying having at Amazon and make them go。

 go elsewhere。From business from a business standpoint， like a short term gain。

 short term benefit but for long term problems， it's just not worth it。

Now there are some companies we've talked to， at least in the startup where they should have tell us we don't run on Amazon because we can consider them a competitor and so they have to run on GCP or something else。

But again， Amazon's not stupid， they're not going to let。You know， I don't think they would。

I'd like to think they would not make decisions like that。Now， so I will say， though。

 the way Amazon is going to get around this， So even though they may not make。You know。

 they they may not make S3 slower because they recognize as a snowflake query or something。

 that would be terrible， right， and not scalable。 though。

 they can do other things like not so much for， well， actually， for retroshf， I'll see this。

 they can add hardware accelerators and other things above S 3。

That's running on the same data center that maybe Snowflake can't easily do to accelerate certain things they do this for aurora as well。

 they push down they have a layer above EPS that does transaction up propagations to replicas for Postcus MySQL that you just can't get if you if you're an external to Amazon。

So there's other optimizations you can do。With regard to adding support for Azure store Google positive storage later。

 he said right， that something， and you're referring to like internally they were using S3 just or all。

For all they managed storage。They switched over to a mix of the three。

 are you saying something more like？で。sorpache iceberger I can use。His question is。

 like when I say they add a support for like， say Google Cloud So or Azure， does that mean that？

Like like if you're a new customer you show up and you start storing data into snowflake that it'll spread it across the different data centers。

 no， I think you tell them when you sign up like I want to run an AWS， I want to run on this。

 but it's still managed through that。So who's them？So it's snowflake's manage storage， yes。

So you're just saying like use this other one。So why would you ever choose to use one？

Like why would you use other cloud vendors。 I mean。

 there's companies that like we've talked to like they were at a Canadian grocery store that like we see Amazon as competitor。

 We don't run on Amazon。 we've run on Google。People have various reasons。

But you can't integrate it with existing data。An object story。No， we'll get to that in a second。

 we're leading up to like the original version of snowflake was like， okay。

 we're we're gonna store things on S3， but the data we're storing actually inside the buckets on S3 is our proprietary data format。

Because at the time， that's how everyone built these data warehouses。

 Now Drreel was doing its own thing， right， but you know。

ItWas't wasn't until like parquet and other things came along that people realized， oh yeah。

 I can have my disparate system generate a bunch of these files and I want to be able to scan it with my database system。

That precipitated them having to support external tables or other things to be able to read data from S3 that wasn't ingested through the front of the data system。

 Ra iss going to go through the same transformation as well。出倒す。So question the question is。

 at this point， why does snowflake not build around S 3。Above my pay grade。 I don't know， right like。

Yeah you have to start building data centers， itd be expensive。I mean， they're not stupid。

 I guarantee they， they did the back of the envelope calculations。 like， like。

 like does this actually make sense or not， Right？ I think next Netflix do something similar。

 They realize that like。I think they were running on Prem and then they went they switched to the data centers。

 Like their big companies always trying to figure out is it cheaper to do this。 But think of it。

 if you're like Snowflake， Snowflake is a huge company， right。

 but it's not as big as Amazon and how many data centers is snowflake building。One a year。

 maybe I don't know。 Amazon's probably spinning up a new one like every every few months， right。

 So at economies at scale， they can just do way more efficiently than anyone else。

So the interim data between the two virtual warehouses is that being sent to I know there's no in memorymory shuffle。

 is the reason for that that they don't have control over they don't have the hardware accelerators and so they decided。

 hey， they're all easy to instances， might as well keep in memory to share data between them。

Your question is， I mean we haven't got there yet， your question is why are they going to allow worker node to talk to each other rather than going through that shovel phase？

I。I think it's from just a philosophical decision that like that's how they want to build it。

 rights there's pros and cons of both of them right actually， this is a good discussion。

 where you can have this now。 like you know the shuffle phase。

 it's nice because here's this abstraction layer that I can just write things to know it'll have some fault tolerant guarantees that they're not going be able to do right So there's that。

 But now there's a whole other service I got to run with additional nodes and it's essentially now making other copies of data。

So this pros and con， there's no free lunch。As far as I know。

 obviously Snowflake only runs on the clock， but there's companies out there that actually also want maybe have some database on。

Move barloads。Is there a big market still for that or is it just everybody？

This is not exactly like architecture。 His question is like。

 is there still a big mark people running own prem database， yes。But like。

The sales cycles for those things are just way different。Because you got to like。You。

 go out and you know go fly out there， talk talk to the customer like you know。

 take them out of dinner and that kind of crap， go golfing， you know， like things in the 80s。

 whereass like snowflake and the Davis has sources model like。

 hey here's our website just give you your credit card and you're oven and running。Right， so again。

 like that for small startups short， you can do that。 But like， yeah， obviously。

 know banks can be like， oh， just， here's the credit card just do it。 Yeah， no， there is。

 there is a huge market。 I think that。I mean， just there's everybody。

I think the market of people going to the cloud is that。

That percentage that pie is growing at a much larger rate than people spinning up stuff on prem。A。

Again， it's not just from terms of like， don't think of this like the cost of like。Oh。

 if I ran it on Prem， I certainly can run it cheaper than what Amazon would charge me for machines or right。

 But then like， then you got to pay for humans to go actually and manage those things。

 So there's like pros and cons， all these， right。Okay。

 so so the abstraction they're gonna they have data storage。

 they're gonna have this notion of a virtual warehouse。 again。

 this is how they first designed it where you basically say I want to you don't say exact number of nodes。

 say I want compute capacity say here's some virtual data warehouse that I can give me an end point where I can start sending data into and run queries on then so when you turn on a virtual data warehouse。

 whether or not you're running queries， you're always paying for it and we'll see how snowflake will leverage that when they do the flex compute because they can steal all cycles from these warehouses in 2022。

 they add a support for serverless deployments So now basically the virtual data warehouse spins itself down if you're not running queries。

 but obviously they charge a premium for that because now you're using more shared infrastructure at the cloud services layer instead of spinning that up yourself。

😊，And then the cloud services layer is just the catch all phrase for the front end of the system that encompasses all the things that we've been talking about entire semester。

 some coordinator， scheduler， the catalog， the query optimizer。

 all that is the entry point for queries。LLC at the end of the semester or sorry in the class。

 the catalog is interesting because they're going to be built on another data system called Foundation DB that provides them transactional semantics for doing updates。

So now within at the compute layer， they have a notion team， a worker node and a worker process。

And again， this is from 2012 to 2013。 So a worker node， at least in the original version。

 is just an EC C2 instance， right， This is V Docker， is for Kubernetes， like Docker is 2012。

 Kubernetes is 2014， but in 2012， you know， you you had raw EC2 instances。

And so on that instance this is where they're going to maintain this local cache on the attached storage device of that instance。

 so they're not reading， writing to EBS， it's always running on a local now be a local SSD， right？

And this cache should be a combination of intermediate results that you're generating for a query while it's running as well as some of the persistent files that you may be reting from S3。

 so the idea is that if another query shows up read the same data that you just read from S3。

 I can read it from my local cache which is be faster and cheaper than having to go do a round trip look up on over S3 or whatever the doctor store is right。

Again， we'll see this in a second， the way they're going to manage this。

 keep this everything consistent or spread data out evenly and be able to scale up and scale down without having to reshuffle everything as you would in a shared nothing architecture。

 is that they're going to rely on consistent hashing to keep track of what worker node is responsible for what persistent data in their own cache。

And then within the worker node， when a query shows up， they'll fire off a whole new worker process。

 literally a spawn of a new process in the OS， and that's going to be executing whatever the task are for this query。

 and it can rewrite data to the inmate results and other workers out the S3。

 and then when the query is done， the process ends and goes away。Yes。

 it's like a tangential question。EBS volume as the root device， right so is that not like a local？

His question is on ECT， you can have an EBS volume mounted as the root device， yes。

 you have to anyway because you have to have like AMI image that's just been up but you still kind of a locally attached SSD that you can then use MVME or whatever 2012 before that。

 but that you can then read and write locally。 That's just another mountain in the file system。

And that's we way faster than E， BS。Okay。I actually I don't know whether they switch over to Kubernetes now。

 we'll see in' tell about yellow brick， the paper， they're all land on Kubernetes and they make a big deal about how they're designed to run in the Kubernetes infrastructure。

 I assuming now they're not dumb they're doing something very similar these days。

 whether it's exactly Kubernetes or something else，It doesn't matter。All right。

 so when a query actually starts running。😊，They're going to be doing a pushbased vectorized execution again using the precomp primitives with template C plus slu based on the different data types that we've talked about。

 We've already mentioned that they're only doing Cogen for when they serialize and deialize data going from one worker node to another and as he mentioned。

 they're not going to do explicit shuffle between stages and instead the worker processes are going to be allowed to send data directly push the data directly to the next node who's going to process it。

Or they keep it locally and keep processing it if they're going up the pipeline as further。As needed。

Right。So that means now if the worker node has all the intimate results。

If it crashes or there's a failure， there now isnt there isn it's not replicated or it's not being stored as an external service from the worker node。

 so that means the computation is lost。And unlike in Dremmel and Spark where if one worker goes down。

 then the coordinator then just invokes a new owner or hands off that task to another worker。

 what Snowflake would do which is kill the entire query。And then to restart it from the beginning。

And that's actually how the people built overlap lap systems back in the day。

 I mentioned this before。 in with MapR， they were， know， they were storing things。

On disk as they went along， but they had the ability to kill tasks。

 react few things and do basically partial retry。And in the snowflake world。

 they're not going to add any of that infrastructure because that's additional engineering complexity。

 They're just going to make the decision， okay， well， one worker failed。Okay。

 just kill the whole thing。 and restart start。And who pays for the restart？customer。

Right so obviously， you know， they're not killing nodes randomly， right。

 They have a blog article where they discuss like， okay，If if a worker dies。

 they have to identify is this something that we did or is this a transit network failure right in some cases they can actually automatically roll you back to a previous version of snowflake and rerun that query the query see whether that solves the problem。

 the tricky thing also too is like if now you're ingesting new data。

 you want to make sure that the query when reruns like is it seeing the same data that I had before。

Question or。These grase fails like。His question is how often Macqueries fail， I mean， not that often。

Right。Exact， they have a blog on the G link。 I don't。 I don't know the exact number。

 but it's not like。You， one out of 10 is some， some， some way smaller fraction again。

 because it's like， you're not running。Again， just going back to the Ma produceduce world。

 like Hadoop was talking about， okay， we're gonna run this， this query or this map produceuce job。

10 of of like cheap pizza box machines like the one one unit rack machines。 And in that environment。

 Yeah， one of them is going to go down。 ifque is going run for an hour。

 certainly one's going go down。 but like not only these queries running so fast。You know。

 they're running on a small number of machines anyway。 So the likelihood of a failure is quite low。

Yes。なとでけ。Doesn't come scale in terms of what。Yeah， so question his statement is like。Sament is like。

 okay， if， if they， if I'm saying like the more machines you have， the more likely one's gonna fail。

 does that have some upper bound， how many machines you would need。Again。

 it's so fast that I don't think you need thousands of machines to process petabytes of data。いかまします。

it was so slow that because it wasn't any query appr and it was just doing this dumb map reduced shuffle map shuffle thing over and over again。

 no matter what the query actually was doing， it had no notion of like pipelines unless someone wrote everything inside of the single map job。

诶。Again， I think whereas at the time， other parallel database systems like the verticals of the world。

 they were running on， they need fewer nodes to compute the same results in less time。

So one thing Snowfl does do。Even though on the shovel phase， they can do work stealing。

 and it's similar to the morsel stuff we saw before where instead of a coordinator like in Drreemel recognizing that this guy's running slow。

 this task was running slow， let me kill him and let fire test themselves， the workers themselves。

 the worker the worker processes excuse me， they're looking for work to do and so they recognize that for all the input files they were told at the beginning of you need a process for this stage of the query plan。

If it runs out of stuff to do， then they can go do quick lookups on other workers running at the same stage as they are and see whether they're falling behind and go steal files from them。

But and to avoid burdening the other worker node with sending the data from their local cache cache data to the guy that's gonna steal the task from them。

 they always go out to S3 because the idea is that if the node is already running behind because it's slow for some reason。

 if now another node says okay， yeah， you're running too slow。 give me the data that you have。

 that's not just gonna to make it even slower， make things worse。

So they make the conscientious decision that the' is going to go out to S3。

 even though they pay for it， even though they have a local cash version。

 they'll go out to S3 because that avoids slowing things down even further。

And then when the stealing worker goes， gets to S3。

 it can put intermediate results in this local store just like before。

 but it's not going to maintain the persistent files and its cache。😡，呃。Beyond the worker disted。

 because again， there's some higher level organization through this consistent hashing that's deciding what worker node is responsible for。

 what file on S3。So， you the next time the query runs that it reads the same data。

 it wouldn't go to that node anyway， would go back to the original one。Yes。

 so you said that the intermediate results are stored in a local district right so how can you get from S3M unless you？

So end what when you from another note working。Something to results。だけの。So how can you get。

 David is like're。If it's processing data from， it's not processing like the original precision files instead it's reading from。

It's reading from the intimate results。 How can you go to Es3 and get it， because you。

 you could go to the other the worker that it got it from right， and retrieve the data。

So then you just have to start from。The big name。Yeah， no， so like though。

If the worker node got work node slides here or diagrams， if worker node X is running behind。

 but it got its data from worker node Y， now worker node Z is going to steal that data。

 it can go to worker node Y and get those inmateit results， or if it again。

 if it's3 persistent files， it would go to S3。I think the worker knows can also spill S3 as well。

 like if you just run its face entirely， then the fallback is to store things in S3 as well。啊。

好子 work可。They broadcast cost to ask。His question is。

 how can a worker know the progress of another worker and identify that they're running behind， I。

 I don't know whether they talk to the coordinator or they talk to the other worker， right。

But like it's not broadcast because like。There'll be'll be like a heartbeat that thats that broadcast it so often and say。

 hey， look， I'm still alive。 But he wouldn't say like， and here's my progress as I'm going along。

 So he's either the coordinator or the the worker you say。You know， give me something to do。Okay。

 so so snowflake is going to do work stealing and again what I like about this paper is they describe like here's why we did it this way and they go a bit more details than Dremel and Databricks do。

The other interesting thing they can support as well is what they call flexible compute。

 and the idea here is that because you know the original model of Snow was like you define this virtual data warehouse that sort of sets up the number of compute node you're going have at the beginning and that those。

Unless you're using serverless， those machines are always running。

 so maybe the case that for some query shows up， you're actually under provisioned。

 you don't have as much compute capacity you actually need to run the query in a timely manner。

So what they'll do is they'll recognize。Prior to running。

 they'll look at the query plan and identify， is there any part where I think the query plan。

 this portion of the query plan is going to take a longer time than I would want。

And can I then hand off the task for that part of the query plan to other node that actually the customer is actually not paying for？

Basically， think of other other idle customers that have compute nodes that are' not using。

 and that can farm out part of the query plan to those other nodes。

It's a windm situation for everyone because the query runs faster。

Snowflake is not spending any more money because the the customer are already paying for the the E2 instances anyway。

 and the the， the customer that you're borrowing machines on。

 they don't even know that their machines are being used in this way。 and that when they run queries。

 they can leverage the same spare capacity as well。So let's say again。

 say you say we have on this side of the query plan here on the probe side of this join。

 it's what to do with some large scan。So snowflake can then split this up。

And to sort of subplans that are going to be combined together with a union all。

 And so here we have the portion of the query that's going to run on on the customers。

 the customer initiate the query on their data warehouse， their compute nodes。

 but this piece over here， is going to run on the spare hardware again idle machines running running running in the snowflake ecosystem。

So， but because these machines aren't controlled by the customer that's invoking a query。

 you can't write any intermediate results to the local disk because at any moment。

 the customer could the customer who owns these machines could start running a query。

 and you got avic all this right away。 because it doesn't look good if like， hey， you submit a query。

 me give me 20 seconds。 I gotta finish up Joe's Joe's query。

 people get pissed right So what they'll do is instead of writing the data to the local storage。

 But instead insert it as if it was a table back into S3。And then now when Im to retrieve it again。

 the query operator above it is just reading from S3 like it was a regular table。Right。Actually。

 going back here。 this is actually。This is actually from like。

 So this is another example of the sway information passion stuff we talked before。

 So they have this， you build a hash join。 you a hash you to do the join and they have this operator of a join filter。

 That's passing over the balloon filter from the build side to the probe side。

 they explicitly call it out as a separate operator called join filter。😊，RightAgain， so this is just。

Because it's a managed of service you're not running on prem， right， There's elasticity to the。

 the resources that are available。 And again， they smartly recognize， okay， these machines are idle。

Right now， let me use them to make queries run faster。And this is again。

 all transparent to the customer。You can also use this for for basically query result caching。

 almost not exactly a materialized view because it's not going to automatically refresh。

 but since you're writing out the output of this query plan fragment into S3。

 you can then update the catalog and say， okay， we over received the query plan fragment again on these files。

 here's some materialized result for it that you can then reuse。😊，Yes。Concerning for customers。

 like typically customers don't want to be at anywhere near。St is。

Isn't this wouldn this be concerning for customers？

Because they don't want their data to be mixed with their data。 One is they have。

They have sort of compute isolation because， as I said before。

 the worker process kill gets killed after the query。 So it's not like whatever you're running。

You know， your whatever task you run for this query wakes up and can now start seeing the next customer's data。

 right， It's a managed service。 So it's not running arbitrary code。 It's all snowflake code。

 So if you're trusting snowflake with your data anyway。

 you can trust them to write the the compute side of things。Okay。啊。Yeah， it's not。

 it's not that bigger secret。 And to your original point， I I， I don't think it's not。

 I don' think it's a be concern， right， And if you really， I think you can opt out of this and say。

 like， I want to run in a。だく。RightThis is not。 this is not。 this is not controversial。 It's not code。

 Yeah， it's running snow code。 you shouldt be no。Yeah， there's other things to be worried about。

And again， it's like it's like it's like the give of penny， take a penny thing， right。

 So like right now my my data warehouse is idle。 So yeah。

 if someone else can take advantage of it sure。 But then you know， when I need it。

 then I can leverage somebody else's。And it all works out。Yes， question this is not unique。

E think of examples。I mean， so， so。There was a system in the 80s that actually I worked on called my predox。

 this thing called condor and it was called a cycle scavenger。

 It's basically if you had a bunch of machines in your computer science department at night。

 it would recognize that no one's touched the keyboard or the mouse and then it would start running compute heavy jobs on the machines。

 and then you came back the next morning when you started using the mouse。

 there was a little small pause why it evicted the jobs but then you got additional resources。

So that idea of cycle scavenging is not new。Specifically for databases， again。

 I think what's different about this is because it's in the cloud。

 It's a single giant pool of all its compute capacity。

That snowflake has under its control that you can do this。Amazon does it differently， right。

 Amazon has spare EC2 resources， they try to sell Mal as spot instances at a low price。

 but of course， anytime you could get evicted。Because someone else wants to pay higher price。A。

In terms of databases doing something similar。I'll have to cut this， right， not exactly the same。

 but like。Yeah， taking advantage of id resources is a known thing。 Or Carl， also， too。

 like think of the data system， like， maybe not so much for the O S。 Actually。

 we'll see some micro partitions。 Like， there's all background jobs you want to run anyway。

 And you do this when you have downtime。Right， so it's the idea is not far fetched because， again。

 because they're in a cloud， this opens up opportunities that we'd not be able to get。

Easily otherwise。Okay。So as I said before， they're going rely on some object store originally S3。

 But of course， there's downss of this because it's gonna be slower。

 you have to go make requests over you can't do kernel bypass You got to go over the network。

 make an HtPS call to their API。 That's got to get encryptpted and decrypt when it comes back。

 That's expensive。 Well'll see next week we talk about yellow brick that they're super hardcore about this and they wrote their own S3 drivers that use kernel bypass go as fast as possible talking S3。

 I don't know whether soon does it。It something similar。

 but you can imagine they have a lot of money that they could。

So instead what they're going to do in Snowflake is that instead of having to build their own their own office store or their own storage layer。

 they're just going to build their own caching layer on the worker nodes and make that as fast as possible because now the benefit is they do a really good job caching。

They end up paying less money to Amazon because they're making fewer requests to S3。

 but it also makes the queries run faster because now you're not going to S3。

 So it's like a win minute situation for everyone， except maybe Amazon。

 but like they have enough money Like you so I think this was a smart engineering decision for them to do its a separate layer of No the question is is it a separate layer knows that extra to cash no。

 the worker knows themselves each have a local cash。And then if that cache fills。

 they can then spill S3 if it's like an Em result。Right。

And then they're going to prioritize this paper talks about。

 I don't think the paper you guys read talk about it。

 They're going to prioritize the persistent files。Sorry。

 they're compize the in results keeping that local versus going out to versus maintaining the persistent files because the inmate results are eemeral。

 You want to be able to get them out really quickly and make the equation faster And so you want to use as much as your local storage your local cache for those inmate results。

 And they're not doing anything fancy。 They just talk about how they're using LRU to do cache from replacement policy。

 and that's good enough for for their environment。 Yes let's say traditional manager。

 But it's still sort of instead of like S3。Its question is like。It's， is， it's not like a pure。

 It's not a traditional B manager where it's two layers， either in memory or on disk。

 It's multi layered。 Yes， it's either in memory on disk or S 3。

 And I think they talk about at least in this paper on 2020。 This is before。

There's a sort of persistent memory work devices that Intel was putting out。

 and that was sort of seen as as another layer like you had you had you had DRA memory。

 then you would have persistent memory like optane， then you had SSD。

 you would have then the S3 Intel cut off the optane。 So that's not a thing anymore。

 but they talk about how you know having sort of。A holistic view of a multi level cash is something that they're thinking about doing。

Okay， so again， the original version of of snowflake or I guess by default， when you put。

 when you put data in snowflake， they're going to be using their own proprietary storage format。

 And again， this is before proque， before orRC。 But at a high level， it's going looks。

I've had students tell me that it looks basically equivalent to parque and OrRC it's using PAs。

 it's columnar storage， you know it's doing dictionary encoding。

 I think they're doing run length encoding so there's nothing dramatically different or special about what they're doing there other than it's proprietary to to them like you couldn't they're not going give you like a binary file in the format because they wouldn't have there's no readers externally for these things。

But then one thing they're gonna to do is for any data that shows up。

 they're going to break it up into what they call micropartitions。

 And I think this is roughly like a。Is look a into like a rogue group that we talked about in parquet。

And so the original data for micropartition range up to 50 to 500 eggs。

 But after doing all the compression stuff， including I think they run like a block based compression like Spy or LD standard。

 they'll get each micropartition down to 60 MBby。Then in the background， they're going to。

They're going to periodically check to see whether the clustering of these micropartitions is actually ideal。

 and they can reorganize them and resort them based on how what joint key people are using or what access key people are using for queries。

 So there's this extra work that they're doing in the background to optimize the storage when it's in their proprietary format。

And that's different than we talked about in Databricks and SparksQL and Dremel where they just assumed that people are putting random files on S3 and they don't have an ability to go rewrite them and modify them and reorganize them。

 and they had to run the query on directly as the files as they existed， whereas in snowflake， again。

 using their internal format， they can use the extra cycles to do to speed things up。

But we'll see how they can。knowThey had external tables and things where they can't do this。

 and I'll talk a little bit about how they handle that。

So now one of the thing that is interesting about Sfl's proprietary format is how they want to handle semistructured data。

And so they have three types that are specific or unique to to snowflake， variant， array and object。

 variant basically means anything like。Any kind of Json hiarchy or something that XM L think like thats is as the sounds。

 It's just an array of values of a arbitrary length。 And an object。

 I think is is equivalent to do generate case of variant where like it's a single level。

 single level hierarchy whereas variant can go any arbitrary length or depth， right。

So in the case of the Dremmel paper， they talked about how they were trying to process all these protobuff files that were internal to Google。

 well if it's a protobuff file， you have the schema。

 you know the data types of the data the fields that are inside of them。

 so they know how to convert them into the proper binary format。

And doing this shreddinging or breaking out the separate columns as we talked about。

In the case of databricks and photon， they didn't have the schema for these files。

 So the way they would handle that is that while the query was running。

 that they would do this runtime adaptivity where they would switch what version of a。

Of a primitive they would use to say， oh， I know I'm processing UniIcode data or ASI data or date data versus there's random numbers。

 and so they were trying to learn why they were running the query what the data type actually was for the different fields。

What snowflake is going to do is's different is that they're going to try to figure things out upon ingestion。

And again， this is when you use their proprietary format。

 you're calling insert into the database or you're bulk loading some file。

 so as they're processing it and putting it into their internal format。

 they're going to figure out what is the data type for different fields。Right。

And so they'll do things like。You， if you identify a string a year， the month and the day。

 well they would parse that and recognize， oh， this is actually in the proper date format。

 so then they'll convert it automatically into whatever the binary date format or timet format is。

But they're always going to maintain the original unparsched version of all of the strings in your JSNF or whatever it is in case they get it wrong。

 like if someone puts a poop emoji in there and you're processing it and you got to fall back and say。

 okay， this is actually not what I thought it was。Right。So again， this is interesting。

 this is now you start to see the difference difference between these different systems。 know。

 Drmel is doing it in one way。 photon does another way。 Snowflake is gonna do it upon ingestion。

 And at the high level， they're all doing vectorized query execution upon on an object store。

 but the low level details and the nuances of them are gonna to be slightly different。

 So I'm not saying that this is a good idea or a bad idea。 I think if it's proprietary storage。

 And you can get the data as it comes in。 Yes， you should definitely do this because now you don't you don't need to redo this over and over again to figure out what the data type is while you're running the query。

😊，And so you just do this parsing once， and you get all the advantages of compression andcoding that we talked about before。

Yes， so is this switch to the drama the question I asked in the Dr lecture。

 which is that they were doing expensive because that。Its performance game is mainly because of this。

They conversion doneSo repeat your question the Drreel one was what thatel storage be didn't have to be in a specific format could be there's extra costs and Yeah so his question is when we talk about Dremmel。

 Drreel talked about how。Rather than have people put data into a proper schema form where you know these like data types。

😡，And and set all that up ahead of time when you load the data。 And then that way。

 the query runs faster。 from engineering and time perspective from a human side。

 they would better just people to store whatever files they want。 And then at runtime。

 the query engine will figure out what the data type is。 Yes， So this is the opposite。

 This is like you got to give the data。 Actually， it's not exactly the same because like it's Json。

 You can throw any Json you want in。But then they're gonna figure out why。

 when you load it what the data type is。 So at a high level， they're achieving the same thing。

 They're saying like， okay， throw whatever data at will figure it out。

 Snowfl is gonna figure it out when it's when it's inserted。

 Drm will figures it out while it's running。But again， if it's parquet files or whatever。

 random JSON files in S3， and it's not in your proprietary format。

 then you got to do what Dremmel does or photon does。You kind ideally eat both。

 But if you know which your data is not going to be inserted directly into your file format。

 you need to do what Drreemel does。Alright， so the consistent hashing something we mentioned before。

 again， this is how they're going to use to this is how they're going to organize the system to figure out what worker nodes are。

 you know， quote unquote， responsible or the owners of a micropartition file for a table。

And we covered consistent hashing in the interclass。

 the basic idea is that it's a ring of a bunch of nodes。

 and you can insert a new entry into the ring and only move the files from its predecessor and not reshuffle everything as if you were just doing sort of naive hashing。

So that means that when a query shows up， the catalog is going to look at this hash table。

 figure out what work are responsible， what files， and then when it hands out the task。

 it tells them， okay， here's the files you need to process and it knowss which ones can compute that data and it knows that the likelihood that they'll have locally cached data because the worker that's responsible for some persistent file is the only one that can maintain long-term cache of that data。

And you add new compute nodes， which they say their customers do all the time。

 then yout you don't have to get everything all over again from S3 or pass every work all their files around。

 you can just go retrieve things in a more fine grain manner。So this part is unique to snowflake。

 I think this part is clever。 and this is the right way to do this。

 If you're going to build you know， sort of a no lap system like this。

right so the query optimizer is going to be unified cascade style doing top down optimization if you go read I think in the paper you guys read and then if you go read the documentation。

 they're going to refer to the query optimizer as the compiler as I said before。

 that's a remnant of like the vernacular from the 1970s because when people sort of built a first C compiler taking a high level language like C and converting it to assembly。

 same idea in SQL you're taking a high levelvel language like SQL and converting it to the machine code or the XQl code of a database system。

So for sga reasons， Snowfls and called there thing a compilepiler。So。They're not going to rely。

 just like Drremel and databricks and photon， they not。

 they assume they're not going to have good statistics。Either because。I mean。

 in paper you guys read is before they had external tables， but like if it's external tables。

 you knew nothing potentially about the files， but even if it's data if you insert it in your proprietary storage。

 they assume that all the stas are going to be garbage and can be changing and become stale over time that they're going have their optimizer or try to operate as much as possible make decisions as much as possible without relying on high quality statistics。

So they use some of the heuristic based techniques we talked about before。

 like if it's a star schema， do certain things versus other organizations of the schema。

The optimizer the big goal that it's trying to achieve in the beginning is trying to decide which micropartitions are files that it can throw away as soon as possible before it even starts running。

And again， if you have some basic stats， like some zone maps that'll screw up in the catalog。

 you can say， well， I can look at my query plan， I can look at my preds and decide。

 these are the files that I know can never have the data I'm actually need I could ever need。

 and therefore go ahead and skip it。And like the other systems we talked about。

 they're sta going to rely on runtana activity to adjust their query plans as needed。

And we'll look at one example of what they're doing。

So if you go through and insert data into snowflake using their again。

 that ends up in the proprietary format， they are going to have some basic stats。

 but it's going to be simple things like zone maps Min Maxs and ranges within within these column。

 they're not going to maintain any histograms， and they're not going to maintain any sketches。Right。

And the data is you only get this when you're using their they in proprietary format。So theres again。

 some really basic information。 and instead at runtime。

 they're going to have triggers to decide should they adjust things as needed。

But one of the challenges that they're going to face is that。 And this。

 this is a bit of a nuanced topic that only comes up if you're actually building a query optimizer is that。

If you need to figure out what micropartitions you need to skip based on the statistics that you do have。

 then now you got to start reasoning about what your expressions look like to decide whether they satisfy or not whether a micropartition could potentially satisfy any data that may be used by this query。

😡，RightSo simple things like know where column greater than 1，2，3，4。s a single column by itself。

 Yeah， you could use the Min max ranges in your zone maps and you micro partition to figure that out。

 But when you start doing more complex expressions， like column 1 plus column 2 is greater than 1，2。

3，4。 But now you got to kind of need to evaluate this thing and figure out what is actually what actually is。

😊，Right。Or if you have like a function like this， truncate the date， extract the year。

 and see whether it equals 2024。If you're just looking blindly at without understanding the semantics of what this is actually doing。

Like， how could you actually ever reason about this， We got to go execute this， this function。

So what you really want to do is be able to rewr it into something like this。So they talk about how。

They have rather than have sort almost two separate code bases。

 one for like expression evaluation that's used at runtime for， you know。

 for queries and expression valuation within the， the optimizer itself。

 they try to leverage that same code base to be able to reuse them。

So that you always had guaranteed you have the same semantics。

 except that you need to be be mindful that you're not actually processing real data or even sampled data。

 You're trying to reason about what what's actually inside of what expression actually you could possibly do。

And again， this seems like。It seemss like a trivial matter。

 but from an engineer perspective it's actually quite difficult because you have to deal with the null semantics of what data actually could be。

Right。Like in the case of。I know once it' like My SQL。

 what they do is when they see like a nested query， in some cases。

 if it's a nest a query that should produce a scalar， though inside the query optimizer。

 they'll literally stop query optimization， go run that query。😡，Right like  one plus one equals2。

 run that query in the executionion engine， get back the result and then inject that back in the query plan。

 and then you don't then you have the constant value。 That's an extreme case。 But again。

 that's because they don't have a way to evaluate the expressions directly within at least these a few years ago directly in the query optimizer you can only use the executionion engine within know within MysQql itself。

 So again， to avoid having to go run some queries go figure out how to plan this query。

 they have a way to。To repackage the， the expression valuation engine to something that can be leveraged on top of。

statisticsistics。Again， I I don't know again， I'm being bit hand here。 like， this is hard。 Trust me。

啊。And the cost model team to surely tell you this。Okay。

 so the one adaptationtomization that they're going to do that I don't think is unique to snowflake。

 but they make a big deal about it， that's kind of cool is to be able to do aggregation pushdown。

So after they figure out the joint order using some basic heuristics based cosmo estimates in the query optimizeomizer。

 they then want to decide when is it appropriate to push down aggregations below the joints。

And you want to do this when you recognize things that the amount of data that I may be processing for the join can be reduced significantly if I do a partial aggregation right below the join。

 and then sum things up again down below。So in this case here。

 they could recognize that this aggregation could actually be partially computed on this side here on the probe side of this joint。

And then now when I do the join， I'm just joining on the aggregation key rather than all possible keys that are coming out of this table scan。

So in this case here， I push down the table scan aggregation child and then update the top one to aggregation parent。

And you can do this for some things very easily， like it's a mini max， you know， in that case。

 like there's not， you don't worry about duplicates， but for some accounts and averages。

 you need to account for that。 And so the aggregation is at the top。

 The parent one is a bit more tricky to do。And so the way they're going to do this is that they're always under the right conditions。

 the query optimize is going to inject these these special pushdown aggregation operators into the query plan。

 but they're going to be disabled by default。And then just like before。

 when we talked about adapt query optimization， they're gonna have trigger mechanisms to say if the amount of data coming up through me is larger than I anticipated or than it should be based on some cost model that that they've generated。

 then it'll go ahead and just enable that aggregation plan node instead of being a pass through。Yes。

 two questions yes， want to do this question why why do you not always want to do this because the aggregation maybe be competing may be expensive。

 right depends the number join key or the group I keys。G key group by key F in a table or column1。

And the number sync values column one is。Is's equal to the number of two bowls。

Your second question was。You want to live with that。What are databaseway systems？

So question from one of those days is just I think Drmel might do this。Um。

The blog article mentions this， I'll wait in a second。It question。

 how do any join if they don't have sketches or details to citizens？嗯。Again。

 I think it's you have a rough estimate of the。You have a rough rough estimate of the， the， the。

 the data might be coming out of the。The table scans based on the number of micropartitions you can prune in statistics Now how they do estimations on the output of the join that I don't know。

 And like I said they might probably do what Drreemmel does is like， oh。

 I recognize I have a star schema Let me have all the dimension tables be like the build side of a hash join and write up the fact table as the last pipeline。

Like a simple trick like that would be provide huge benefit。

 But I don't think they're reordering the joins at runtime。 I don't think anybody does that。

I thought they were doing distinct value。Please that's what Is in the paper。

He says I think they're doing distinct value estimation。 But like after the join。

 like like the stats are all garbage。Am。So Snow snowflake loves talking about this optimization that they do。

 And there's a blog article about it from from last year and actually written by Bowe。

 who was my student who took 7，21 applied 2016，2017 and went off and built this piece in。😊。

It snowflake， that's pretty cool。And I think， again。

 I think this blog article mention that like there's a couple other systems that do this。

 But I don' I don't know if they name names。O。Al right， so that's the。

That's the high level overview of what Snowfl does。 And again。

 the idea here is that you instead comparing or track some of the。

 the nuances that they're doing that can be different than than Drmel and and photon and。

Red shift and yellow brick， the that we'll cover。 And I'm trying to highlight the parts I think that I think are interesting。

So I want to go back to this thing I mentioned at the end of last class。About how。You know。

 databricks came out with photon and made a big announcement。 I had the sigma paper。

 And then they also announced that they had。That they they had。They had audited TBC DS numbers。

 and they were the fastest implementation ever。 So in addition with this。

 they put out a blog article announcing the paper。And announcing that they have the new world record in audited TPCDS and in this blog article。

 they include this graph here where they compared databricks against Snowflake and this was being run by researchers at the Barcelona supercomputing Center and running on what was called the power set of TPCDS。

 I think of like a selected subset of the TPC the 100 TCDS queries that it meant to be representative like pushing a database in really hard so this blog article came out with November 2021。

And then two or three weeks later， the snowflake ski came out and they start going on about how the database skies didn't run snowflake correctly that the results are our garbage and don' don't trust what they're saying。

 Snowflake is actually faster and not as expensive as what database is saying like that databases ran on the enterprise version of snowflake。

 but because they weren't using any the enterprise features。

 They could have run on the regular version of snowflake and cut down the calls quite significantly And these are the two founders。

 The two French guys that I mentioned at the beginning， right， The two guys that came from Oracle。😊。

So they came out and thinking， all the database numbers are garbage。Well， two days later，flake sorry。

 the Data guys came out again and they go now we stand by our numbers and the snowflake guys are being disingenuous and that what's really going on is that。

These are results that Snowflake is publishing for their data。 So in the Snowfl blog article。

 they gave you like here's how to go sign up for S snowfllk account and go access the TPCDS data and run this experiment exactly yourself to see why the data numbers are garbage。

 So that's what this result is here。😊，But what the database guys are saying， though， is。

The the data set， the data they've actually running on in the snowflake results are when you use their internal proprietary storage format and when they've already run that micropartition rebalancing optimization that we talked about before。

So， the data has been。Not cooked， but prepared because it's been ingested through the system and they've done the extra steps to get into a form that is ideal for them。

And that if you just take the raw data that you're given from the TPCDS data generator and then run that without any additional preparation on snowflflake。

 this is the result that you're getting and this is what they reported from the Barcelona data center。

 whereas in databricks if you don't do any preparation， this is what you get。Right？

So in the official TPCDS documentation， you actually have to include the preparation time of the data in your time measurements。

 so like if you think about this like if my  query are going to run for a minute。

 but I spent 24 hours compressing the hell out of them and reimize as much as possible。

 I have to report the 24 hours plus the one minute。😡。

And so that's what the database guys are arguing that， like。

This time here doesn't include whatever that preparation is。And then if you throw raw files at it。

 this is actually what you're getting。Right。So I like to be the， the， the， the Switzerland。s。

 I like to be Switzerland of databases。 I want to get along with everyone。😊，So。When this came out。

This off the cut as well。 You know， I would say for databs。

 they for this was a big win for them because。Prior to this。

 certainly Spark SQL was not as sophisticated and as advanced。you。

 compared to photon and other systems at the time， but this showed them put them in a different light showed that okay you can use data brickricks as a high performance data warehouse and put someone the same equal footing in a sort of competitive market space against snowflake and other systems around at the time。

So this was a win for Dataricks， I think，2 this is 2021， yes。During the pandemic。Okay。

His question had they come out with any comparison since then， no， I don't think so。

There's always been some kind of like for these guys fought。

 then like the time series days these people fought over benchmarks， right。

 there's always some battle between these various systems。Why is it hard to learn data stress like't？

Run the numbers in benchmark data。So question should why is it hard to rerun the databasebricks ones？

I mean， like。Just put the TPCDs。Data there and just running it。Yeah。

 so if there's raw files on parquet and if you say zero preparation。

That would be an apple of the opposite comparison， right？But here's where things get weird。

 Like not weird。 but like it's a wellknow fact that over the years。

 the various data vendors have various optimization tricks that are specific to the TPC benchmarks。

 So if you recognize， yes， a wellknow thing。 recognize that， oh， in TPCC。

 this is a very common thing。 Oh， you're accessing a the new orders table or the warehouse table。

 I know what benchmark you're running。 And they'll do like。

 they'll give you certain query plans or do certain optimization that you would not normally get。

Right。Oh， hes like， like the Volkswagen。 It'， it's not that bad causeuse they like。

That was polluting the environment， that's worse。Actually know， there go。 They did' the Vol Z。

 other than like polluting。 like， yeah， like Volkswagen， their cars would recognize， oh。

 I know I'm running the emissions test So they ran at a more optimized manner。

 But then when it was out in the real world， it was polluting a lot more。😊。

Like theres tricks you can do in T PCCC。 I don't know what the tricks are like the analytical workloads And TPCC。

 for example， like the。You， you call Cate index on the warehouse stable。

 but like there's only 00 warehouses。 you don't need a full fled B plus tree。

 just do a sort sort sorted array。 that's going way faster than because the number of warehouses don't increase when you run that benchmark so you make a static array and do really fast lookups。

Right， but like， if， anybody else would not get that optimization。 So there's。

 there's wellknow known tricks like this。嗯。Okay。So let's finish up。This。

 we talk about image many times。 Again， snowflake sort off at being proprietary storage。

 the world of of data lakes has has evolved or has expanded。 And so over the years。

 they've added support for accessing data that's not directly in there。

TheP format it first started off with this thing called Snowpipe was basically it was a Kafka endpoint。

 the Libbu ingest data that in Apachearrow format that then actually did get written to their proprietary format。

 but in 2021 they added external tables。 I actually don't know what this actually looks like because the documentation say oh。

 it's this data format or whatever so I don't actually know what they're doing other than I know they can re in the hi metadata catalog but then re parquet files they've added support for iceberg in 2022 which we talked about last class it's basically parquet files with additional metadata to keep track of the scheme of information and do simple updates and inserted updates delete on those files。

And then in 2022， they also announced support for what they call hybrid tables。

And this is a service that I think is still called Unistore。

 And it's basically a full flashged transaction transactional database system。 that's a row store。

 It's running inside the snowflake ecosystem that you can do。😊，You know，Quries。

 SQL queries on and run TPCC and other transactional workloads。

And what will happen is the data will get inserted in a log structured format as a row。

 and then in the background they'll then run compaction and convert it to columnbinar data stored in the Sflic proprietary format。

Right and so when you now run an OB query， it's basically the fracture mirrors approach where query shows up。

 you have a table iss being cleared as a hybrid table and the execution engine has to recognize， oh。

 some of the data I can get from the column store side。

 but I also need to merge with some data that I have on the row store side。

And it provides a single viewpoint for all of this。So again， this is in response to like Delta Lake。

 actually， I think they support Delta Lake now as well。

 but the idea of like ingesting data from different sources if you know， it's one additional thing。

 a way to access， put data and sort of like you can run your transactional application on top of this。

So snowflake is a great OLAP system。啊。How can they build a transactional system that that's just equally as hard that's fault tole。

 reliable and safe。 How can they build a transactional data system at the same time。Well。

 let's just say you have a transactionactal data system you're already using for other things that you can then start using it for other parts parts of your system。

So famously， Snowflake runs that are cataloged on this thing called Foundation D B。

 Who here heard of Foundation D B before for this class。😊，3，4，5， small。 Basically。

 in the NosQL days in the early 2010s， there was all these NosQL systems that were doing key value stores that didn't do any transactions。

 and Fation D B said， well， we're gonna be a transactional key value store。

And I think they were backed also by Sutter Hill。 And so basically they got the two boy bands to put out to work together and Snowflake decided to use Foundation B early on as their catalog。

 It's one less thing theyd have to build because you need a transactional catalog。

So the challenge though is that。😊，Found B got bought by Apple in 2015 and and it was always closed source because what happens is Snowflake had in their contract with foundation Db that if they get acquired to go under。

 they get the source code and the esc service they would get access to the source code because again by this point。

 2015， Snowflake was huge not as big as it is now it was grown quite rapidly So Apple buying the main thing that runs try a catalog service would be a huge problem。

 So they got access to the source code and they kept maintaining that over the years。

 and then when Apple then open source Foundation Db。

 they then had to spend time to get it merge back together and follow the open source version。

 And now right now， the number one contributor to foundation Db I think is Apple the number two is Snowflake。

 But for legal reasons， the snowflake people can't commit code directly into foundation Db。

 only Apple employees can do that。 but they literally show me on Slack， they say， hey。

 commit this to the Apple people and people they'll do it for。😊，I don't know whether that's changed。

 that's what it was a few years ago。 Foundation， we don't time to cover this is a very fascinating system。

 Their testing infrastructure was insane。 they had this basically deterministic testing infrastructure where they could introduce faults from like the disk。

 the network and whatever show that thing was could fail over it was fault tolerant。😊。

They the guys that built F HGB have a new startup called antithesis。

 where theyre now they're trying to sell the infrastructure that they built for found HGB do testing for a distributed database basis and that。

Isn't itS basedIt question is， how do you make a key value store transactional LS based？

It doesn't matter。 your statement is， how do I make a key value sort of transactional。

 But I wasing that they probably useCC to make it。 I had to go look， I don't remember， but like。

The fact that it's a key value store versus relational database does not matter。Begin， put， put， put。

 put， commit。 It's all the same。Right， that's basically what NDB is doing underneath the covers。

 N B is a key value interface or on a B plus3。 My SQel does the higher level stuff。

 But like it's doing transaction and all that。 wirere tiger， Ro Db， it's all the same。

 It doesn't matter what's key value stored or not。Okay all right so this is again a crash course on what snowflake is again I think it's a very fascinating system and even though again it's 12 years old now。

 I still consider it to be a very much state of the art Now the yellow brick guys are going to go way overboard with some of the optimization that they're going to do we'll see that next week but again in terms of like a disaggregated storage lakehouse system that does vectorizedque execution what snowflake provides or did back then is is common now。

 but it's still state of the art， although you can see sort not cracks in it。

 you can sort of see how there's aspects of it that are sort of remnants of being designed 12 years ago。

 whereas like。😊，Again， whether or not they're sort EC2 images， I don't know， but this。

Adding support of external tables after you've already had the proprietary storage。

 that's not how you would build a system today。If you want to do lake houses or data lakes。But again。

 it， I still think it' it's still a very fast， very good system。

The other challenge that guess from from a snowflake perspective。

 you look at Vel look at data fusion。 The core， you know。

 the core engine itself is become commoditized。 So it's all the stuff above that snowflake does the snow park。

 the snow pipe stuff。 All that is separates them from the competitors because that's the user experience and the adapt of runtime that you。

 is gonna matter rather than just like how fast can you do vectorized scan。

Al rightSo next class on Wednesday， we're gonna read the duct D B paper。

 I think the paper I had you guys sign is like it's the demo paper。

 So it's like it's two pages of four。 yeah， so there isn't a canonical ductD B paper out there。

 That's the best we can do。 But we'll cover the mother duck paper that came out this year。

 But I don't think that one discusses the court architecture。

 But I'll go through like here what duck D B internals actually look like And that's based on public talks and other documentation they've given。

 And this is gonna be slightly different than everything we talked about for because like we're making a big deal about these Oap systems that are running on lake houses。

 And now we're talking about an embedded in process database system。😊，But again。

 we'll see how they can read data from S3 and other things as well， okay。



![](img/49e856a34f381d1149cd43adb9ca93a3_8.png)

Hi guys， see you。

![](img/49e856a34f381d1149cd43adb9ca93a3_10.png)

to get the40 out get a quick take you'll be picking up models ain the puzzle because more man of telling the 40 and got。

St is six packs on the table and I'm able to see St I on the way。No short with the cl。

 you know what got them I take off the cat but first I' tap on the bottle。

 don' about three in the freezer so I can kill it cat full with the bottle baby。🎼Cing老 pay love way。

 you get他们 the god。Take back the pack of th， andvo to some same nerve to trigger to the ths。

 Billy Deans affiliateil chief to tell him to we go， be a man to get a can of same time。

