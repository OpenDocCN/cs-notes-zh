# CMU《高级数据库系统｜CMU Advanced Database Systems (15-721 Spring 2024)》中英字幕（豆包翻译） p18 -18-S2024 #18 - Databricks Photon _ Spark SQL .zh_en -BV1HZ421N7WZ_p18-

🎼Carnegie Mellon University's advanced database systems course is filmed in front of a live studio audience。

😊。

![](img/8ff74da2af18b304241c00cc4244a57d_1.png)

🎼。🎼ですか。Thisラ。🎼U。All right， so last class we were discussing。BigQury and Drel。

 that system architecture。 and as I said， the。

![](img/8ff74da2af18b304241c00cc4244a57d_3.png)

You know the Drel work was served as a foundation or a blueprint for how people build a lot of modern overlapAP systems everyone's going to have bits and pieces that Dremel has and there certainly has been extensions to the of our architecture using other systems。

 but at a high level that's the approach when people say" you're building a modern OAP or lakeout system。

And when we see snowflake next week it sort of spark today。

 it's going to look very similar bits pieces。So。To just understand the Databricks photon paper that you guys read。

 we want to sort of first talk about the history of how sort of Sp came about and what led them to building the accelerator to the the way that they did So again if you flash back to maybe like late 2000s when MatRduce was taking off at the same time there was this project called Spark at a UC Berkeley where they' were trying to build a better version of the sort of Maproduceed Hadoop model。

 and some parts are very similar like separating computing and storage HDFS Hadoop had HDFS and then the extra excuter nodes but then they also had support to do of iterator algorithms the way you couldn't do very easily in Hadoop that allowed you to take multiple passes in the same data within your program。

So when they wrote SpPAark， they wrote in the Scala because that was the hot thing that was the language I most excited about around this time。

 2010， now it's obviously rust， right before that it was go， before go， it was Scala。

Pythonons always been there right So because because Spark has written in Scala。

 it means they're gonna run the JVM。 Now pretty much all the papers we've talked about this entire semester。

 most of them are written in C+ plus+ Rus is becoming more common now。

 but it's been C+ is the main thing we've been focused on。

 But there's still a lot of database systems that are out there that are going to be written in Java mostly because they come around from the late 2000 early 2010 and we've avoided sort implementation discussions about the programmingb languages using these systems。

 but for today's paper as you guys read about like because spark has really written in Java or Scala running the JVM that matters and that's gonna restrain what they they can do in their implementation。

So the first version of Spark that came out only supported this really low level API based on these sort of RDDs or resilient distributed data structures think of this the output of some task computation was put in this RDD wrapper。

Later on they added a support for the data frameme API for even higher level abstraction and programming language。

 and this is sort of I think when sparkark really started taking off。

 so instead of running your pay programs or accessing data frames in Python。

 you could run this now and Spark and distribute it。But again， but at this point， again。

 the early version first version of Spark did't S SQL。

 it was all that again these other programming languages。

 so once you start having some kind of computational framework that can process large amounts of data become popular。

People were going to start asking for SQL， and that's what people wanted in S。

So for the first sort of support within Spark was this thing called Shark and is where they forked Facebook's hive middleware that took SQL queries and converted them in that produced jobs。

 they forked that and then took SQL queries and then converted it into Spark programs。

 using the Spark API。Right and this was limited because support the capabilities of this approach was limited because it was you can only use SQL for like the initial invocation of the program or the query you wanted so so it wasn't like you could take the you couldn't intermix like Python code or the Sp API code with SQL in different parts like you couldn't take the output of a SQL query。

 feed that into you a scholar program that then took the output of that and then feed that all within the same program into SQL's only you you couldn't mix the SQL and API calls at the time。

The other challenge that they faced too was that Srk was based on Hve and the Hve queryry optimizer was really designed for picking the best query plan to generate MapRduce jobs。

 and so they had to try to contort it to make it work in Spk， but Spark had a more expressive API。

 you do more things in your program than you could in just MaRduce because MaR only exposed two function to map and Red。

And so， so the queries that they were generating through this through shark were not as efficient as one could build if written by hand because hives optimizer just wasn't wasn't aware or didn't know about the other things they could do with。

With know Spark programs。RightSo again， this was a stopg solution the initial approach to add SQL support in。

In。In in Spark， I think I mentioned last class also as well， like there was this。

Other system called Aalla that came out of Clouddera and Clouddera was actually the ones shipping the most spark in the early days。

 because people were asking for it， it was part of the Clouddera distribution you would get。

 but then when people started asking for SQL support in Spark。

Cloudderra wouldn't provide them shark because they wanted the people to use Cloud use Apola instead because they made money on that。

 right So even though this was available， again， as a sort of add on to Spark。

 it wasn't available in Cloudderra's Cloud error distribution of it。So then in 2015。

 the Databs team put out Spark SQL， and this was native integration of SQL directly in the Spark runtime。

And now in this case， when you download Spark， you've got Spark SQL。

And so Clouddera couldn't excise it out when they ship Spk， they also shipped Spar SQL with that。

 and that basically undercut any any need to use Aala and it sort of like it was like a Trojan horse basically helped destroy or not destroy like because Cloudists are around。

 it helped undermine Clouddera and you Databricks became big company is now Clouddera got they went IPO。

 but then they got reverted back to private equity。 and I think Databricks。

Help facilitate that in some ways。Another problem was。

 despite the name of having Cloud in the name Clouddera。

 they didn't have a cloud offering a map produceuce of Hadoop。

 Amazon was making more money on Hadoop than Clouddera was。

 even though they had like thevent of Hadoop there and a bunch of other people that were key contributors to it。

But that's an aside。So the way Spar SQL worked was that they would still rely on some the row based architecture or the feeding data in from the lower levels of the query plan。

 but when they pass data from one operator to the next。

 they would at least now start storing it in columnar buffers or vectors。

They would support dictionary encoding R lead， pit packing compression， stop all the talk we before。

 and now they would also introduce an in memoryory shovel phase to go between the query stages or between the different pipelines。

😊，The way this actually would work was。They weren't doing full query compilation。

 the way we saw in hyper， they would just do compilation of the wear clauses and they would do this by converting the wear clauses into like sca ASTs。

 and then there was an internal method in sclet that then generate the basic compile this into the JBM bytecode and then you could you could link that in and invoke it within it。

 So they were doing partial query compilation to help speed things up。 but there was。

There was other challenges that they were going to face。

So I also point out too if you read the Spar SQL paper， they had this little blurb here。

 they talk about for their inmemory shuffle in the original version of it。

 they just relied on the OS page cache to keep things in memory and then only use that dis when necessary。

 but then know you'll see in photon， they got rid of that because the OS would just messing everything up and this became non scalable。

 So there's another good example like you don't want to let the operating system ruin your life or do anything。

😊，do anything for you， you won't let the basis system do everything by itself。

 because the overhead of like the cis calls， the overhead of like the journaling and the file system。

 like all that was causing problems。So the other challenges of this is that the。呃。

Converting things into this scholar or converting like doing cogen for the wear clauses and then compiling that came to be a challenge because there was a sort of limit of how big the program could you could Cogen inside of。

directly side of the JPM， and they were finding that when they were run SQL queries。

 they were becoming CPU bound。Rather than disc bound。

 and theres a too much computational overhead of doing this approach that it became problematic。

 And again， this is 2015，2000， say， maybe 2015， 2020， disk are super fast now。 But at the time。

 you would expect your data warehouse or O left system to be always disc bound。

 not CPU bound nowadays the pendulum sort of swung the other way。

 the CPUs are coming the bottleneck and not the disk。

 But when they were building this the disk was not sunung down。 was it was the CPU。

So in the photon paper， they point out a bunch of observations about the spark SQL attempt and the first one I already。

 as they said， that the workload was becoming CPU bound just because there was so much computational overhead of everything that they were doing。

They had to be， you know they spent a lot of time trying to work around the JVM in that sort of memory managed environment and doing things like I don't know much you know about like Java programming。

 but like when you allocate something like you call a new object， that goes in the heap。

 the JVM's garbage clutch keep track references to it every time you run a garbage clutch pass。

 you check to see whether anybody is still pointing you to it and you can free the memory there's no like direct mallet call in in the JVM So the way you get around this。

 you do offheap memory you basically within within the JVM or Java code， it's like an unsafe in rust。

 you can allocate memory to some outside region， it's still owned by the process。

 but the garbage culture isn't gonna to go look inside of it to see if anybody can free any memory。

So they had to do a bunch of engineering effort to move stuff off heap so that the garbage collector wouldn't slow them down。

And that becomes just sort of problematic， it's a lot of engineering effort just to get around the internals of the GVM。

The other challenge that they faced was the doing the J compilations piece was particularly tricky because。

In order to get the best performance out of it， you had to have people that really know how to the internals of the JVM and they found they had trouble scaling up the engineering team to be able to optimize the Spar SQL engine because it's really unique people had experience actually in the internals of the JVM versus like most of C developers can jump in and start writing code or anything。

Right。The other limitations of how big again， the codegen code itself could be。

 so the paper mentions and the photon paper you guys read that if the table had more than a couple hundreds of columns。

 which are pretty common， sometimes， then the JVM would just say。

 this is too big to compile and throw it back to run the slow interpreted mode。

So they were basically dealing with this， this remnant of the early 2010s of like， okay。

 let's build this on the GVM because that's how how people were building scalable know。

 big data systems at the time。 But then when as the Harvard landscape changed as the demands of what what people wanted to do with the data system changed。

 they were sort of hitting the upper limits of what the GM support。 So they had a。

Come up the way to overcome this。So this that's the background for the paper you guys read for photon。

 So as I said last class， photon isn't a standalone system like Drmel or snowflake when we re that next week。

 right， but rather it's a library that that's meant to embed inside of an existing database system。

Like Spark or the。Spar runtime in the word they called the Datab runtime。

 But it's even more low level than the V paper we read before， where at least Vox was providing a。

You know， not a full executionion engine， but pretty all the pieces or components we need for the executionion engine。

 like thread pools， all the operators and so forth， it's even photon is even smaller than that。

 It's really individual what they call kernels or task or operators that you can then put in at a really fine grain within the query plan itself。

 but all the threading， all the memory management， all of that's going to be handled by something else in this case here it's going to be the databasebs runtime。

And we'll see alternative approaches to accelerate Spark at the end where they're not going to do the way do it the way photon did it。

 where' like again， just injecting the photon accelerated operators within the queryplan at specific locations。

 the alternative approaches we'll see will just。Take the physical query plan。

 ignore all those spark and run at somewhere cells using like data fusion or a whole other database system。

So the idea here， the high level design goal of photon is that they wanted to integrate with what they'll call the Databix runtime。

 the Spark runtime Data runtime is the proprietary version of Spark。

But they wanted to be able to integrate it with。The the DBR without throwing out all of of the existing infrastructure and that that as over time as they expand the scope or the capabilities of what photon can support。

 they can then just incrementally add those pieces into override the ones the database run time again。

 without disrupting any of the users。You don't want the。

You don't want someone to run a query you know one week and on an early version of photon that maybe doesn't have certain tasks implemented and get one result and then next week they run the exact same query and the exact same data。

 but now photon has been upgraded and now they are getting back different results I say they want to avoid all of this makes it completely transparent to their users。

Other than they charge you more for it。啊。So。Right， so they want to support all of the semantics and capabilities of the earlier SQL engine and the data frame API。

 but again without having any。Any changes in actual results or high level behaviors？

And then they also want to be able to handle the。Again。

 the legacy artifact that the spark runtime is going to be handing out individual rows one at a time and convert it to a column oriented or vector oriented implementation to speed things up。

Right and so the basic ways it's going to work is that queries are going to some portion of a query we'll be able to run in photon。

 but if we recognize that for what the query actually wants to do。

 we don't have a photon accelerated implementation of that task or operator。

 that would just fall back to the slow path of the。You knowOf the original Sp on time。

So we'll talk about the second， how theyre going to do this。

 but the way you do this in the JVM is you're using what's called the J&I or Java native interface。

 it basically allows you to have Java code then invoke S plus code。

 like the thread that's running the JVM now goes down to your S plus code and can do whatever it wants。

And the paper they talk about， the overhead of making that JNI call was roughly about the same as doing a virtual function lookup in C+。

I think it's like 23 to 25 nanoseconds per call。It's not free。

 right but it's not like you know because we're just being passing around memory buffers and memory pointers in the same process。

 it's not like we had to copy things in one process to the next。So for the paper you guys read。

 what's super awesome about it， at least for me， as a professor that I like。

 is that when you look at the author list， there's a lot of CMU people here， right？

So Prashaant Menin was my number one PhD student that actually worked on Cogen Que compation stuff。

 so he worked on this system， You Carsh and Arvin， they were masters students here。

 they took 721 same class you guys took here and they went off to Databs。

 Ryan Johnson did his PhD at CMU I think he graduated in 2010 so before I showed up but I'm pretty sure he took 720 and 721 and T8 at like 2006 the earlier version of it and there's a bunch of other people in the。

😊，A bunch of other people in the citation list， the bibliography of the paper。

 like you know Aliison Wang， my former student， they ci a blog article when she's said Databricks working with stuff。

 So there's a lot of CM UDB alum at Databricks working on this project， which is super cool。😊。

This is basically why you should take this class， but we're already into like whatever the 12 weeks so you're here。

Alright， so here's the high level overview what photon is gonna have。 Again。

 some of this will be in the context of the overall spark system like shared disk and discag storage。

 the seative computing storage。 But the ones that we're one where we're going focus on is the pole based spectrumized execution and then the pre primitives。

 We'll see how they're going to do shuffle based distribution， just like in Drel。

 nothing really radical there。 they do short merge and hash joins。

 And they also talk a little about how they're doing query optimization and。😊，And add。

So the over architecture looks look a lot like Drreel right We have some distributed file system。

 We have a query shows up。 It gets sent to what they call a driver。

 but Dremel called the coordinator。 you'll see snowflick next week。 they'll call this， I think the。

The compute service or something like that at a high level again。

 it's some node that's responsible for taking the query， generating the query plan。

 handing it off to some schedule， and make sure the task get executed， right。

So in the first stage here， the X is fire up and then they'll start pulling data from the distributed file system。

 they'll do some kind of computation on it， and then they're going to start writing it out to for the shuffle phase。

 but in the default version like if you just download Spark。

 they're going to do a local in-memory shuffle store。

So I mean they're going to write to basically a hash table and that's local to them and then other workers can pull from them in the next stage。

 But as we also saw the last class， we have the ability to also write out to a remote shuffle service like Uni or Apache Soliborn right for our purposes。

 it doesn't matter。And then in the second stage， again。

 the excutrs and the next stage are going to be pulling from the previous stage， and again。

 if it's not a remote service， these guys have to stick around until these guys fire up again。

And whether or not you can be clever and say， okay。

 well this guy is going to be on the same thing as this guy started to re my local memory。

 that's outside， that's done sort of high level scheduler。And then we fire it the next stage。

 produce the final result and send it out。And again， at high level， this looks a lot like Drmel。

 pretty much all the systems will see。 They may not always have this exact shuffle implementation。

 but basically， it's gonna to work the same way。 Like you got to get data from your the previous stage。

So again， the thing we're talking about today is the photon piece that's going to run inside here on every single executor。

 it's not like a standalone service， not like a standalone process running。Everything's going to be。

It's running inside of the implementation and then being vote by the Java code。

So photon is going to do a pull based vectorized engine。

 and they're going to leverage what they call in the paper operator kernels。

 But when we talk about vector wise， them they call them primitives。

 they're basically the same thing right， some precompiled code that can do a small computational task on a vector of data。

And they're gonna since these are gonna be written in C plus plus。

 they're gonna to be templated based on the on the data type and they would have different variations to deal with。

 No， I've been doing a less than or greater than whatever the computation or task I want to do with these things would be all。

Genrated ahead of time， then compiled into the system by the developers。

 We're not doing cogen on the fly for anything here。

And so the way that they're going to avoid the costs of jumping these pointers to these functions are either going to be just amortizing across multiple operating on multiple tuples within a single vector。

 as we saw in vector was， but they're also going to do something they call expression fusion。

 we'll see in a second， where they actually can combine multiple primitives。

 if they know that they're being used continuously or continuouslytiguously by a bunch of queries。So。

Part of the reason I had you guys read this paper other than like Databricks is obviously a huge company。

 and this is a pretty interesting system is that it's actually a really good paper。

 It's one of the better industry ones。 will'll read the semester and read mostly overall because most the industry papers that are out there they just say like hey。

 this is what we did to do like how great we are and they'll describe the details of what they did。

 but they don't really discuss what led them to those engineering or decisions where as in the photon paper。

 although they don't provide numbers for like we tried this， we tried that。

 but they have nice little andotes of the things that they considered and looked into before they end up making the final choice that they presented in the paper So the one that they talk about that's really important is how why they decide to build a vectorized engine that is based on the vectorwise model the X100 paper rather than just in time engine just trying compilation engine like hyper。

Even though they had already done that in Spark SQL。

And what they talk about is that they found that the。You know。

 their developers are spending most of their time writing the tooling you would need to if you have a J engine to deal with a Jit engine。

 like debugging it， profiling it， understanding what's going on because you basically， again。

 when you crash in one of these compile engines， you just land in assembly。

 there's no lineage information or provenance to say。

 what part of the code in your system generated the code that crashed。Right。

 so they had to write a bunch of tools to to figure these things out。

 whereas if you go with the pre compilelied， you know， primitive approach with， you know。

 based on vectorwise， then。At first， the engine may not be as fast as the Cogen system。

 but you can just iterate it over and over again and more people can work on the project without having specialized training and you can get nearly the same performance and sometimes beyond what you could get in a hyperstyle vectorized engine。

So that， that little you know， tidbit in the paper I thought was really interesting。

 And I agree with them at this point， having gone through the experience of building a hyper style compilationit compilation engine here at CMU。

 you know， I wouldn't do it again because。Although the student you guys here in 721 is super smart。

 there wasn't a small number of students that actually could work on it。

 even I struggled with it because it was like when you crash， you just。

 you know you land in an assembly。Or we tried to build an interpreter to help us walk through the op codes and understand。

 Dubug programs。 But what are we doing， We're building an interpreter。

 We're building in debugging tools， rather than just writing the code to make the system go fast。

Right， so again， that piece of that piece of the paper， I think I thought was was really important。

 And if I was building a system today， I would， I would maybe well I wouldn't。

I wouldn' have to deal with JVM because you shouldn't use the JVM to get better a new system。

 But everything else they talk about， I think is， is still relevant。 Don't worry。

The paper also mentions that the auto vectorization works pretty well because most of the prims are pretty small。

 but when necessary， they do write some intrinsics to just sort of force it to use S in right places。

So all their operators are going to support this next function that's going to produce some column batch and they're going to choose to keep track of what tuples are relevant or still active as they move up in the query plan using a position list。

Remember we talked about before， I think we talked about Vox and the execution engine begin the semester position list is just a vector that keeps track of what offsets are still valid in your batch of vectors as you're passing along because some may get filtered out and then rather than compacting the vector you just pass along the dead tus。

 but need to keep track of which one those are still active so this is just literally an offset within the batch of columns that you're looking at。

And recall that the alternative approach was to maintain a bitmap of active row。

 and it just as zero to say whether it's active or not at a given offset。嗯。

And so the paper talks about how they consider both approaches。

 but that they found that the position list just was except for the extreme examples where you're passing along all the tus。

 that this is prefer and this performed better than the bitmap。

And then they if you follow the citation here and the paper says recent work confirms our conclusions。

That's our paper right that we wrote here by Amadou， who was a 721 student。

 He's now a pitch student at MIT， with Todd Mauorory and other people know W， Lan and Matt， right。

And so this is ominous' master's thes that he basically did a brute force search of like just trying out all different combinations of position vectors versus the bitmap under different workloads of different combinations of different hardware using CinD and not Cindy。

 And he found out the position list is better。Overall。So this is an artifact of721， which is cool。

So as I said before， they're not going to be doing the hyperstyle codegen query compilation。

 And it also means we're not going to do the hyperstyle operator fusion where you have multiple operators in your pipeline and you combine them together。

So。They're going to do this for two reasons。 One， obviously。

 they're not doing copilation because they want to use primitives precomp primitives because it's easier for engineering。

 But another interesting thing they talk about， which I had not consider before before reading this is that。

In order to make it understandable for their users。

 like debuing information and profiling information that they have to show them。

 but like here's why your query ran for this amount of time。

 if you do the hyperstar operator diffusion， it's very hard to convey to the user actually why their query might be running slow or where they're spending most of their time。

😡，So all call this vertical fusion。 So within the query plan。

 you're sort of vertically combining the different operators。

 and they're instead going to go choose something called。You know。

 expression fusion or or horizontal fusions， when I call it within a single operator horizontally within of that。

 I want to fuse things together。 So I'll go through examples of each these one by one。

 but it first you know prefers to see this again from hyper and see why and why they don't want to do this。

So this is that query we had before in hyper you can see all the different pipelines here and in Hy they're going to doing a push based model and they want to fuse together all the operators within a single pipeline。

So if you focus on number four here， it's the scan on C and then you probe this table and probe this table。

 so it's basically three， four of loops nested together。So one is this be difficult to do in a。In a。

using primitives， I guess it's not difficult to do。

 just like you have to pass around batches that you wouldn't go by a single single tube at a time。

 But now if have to tell a user like here's the query plan operator that took the most time within your query plan。

 you can't show them much of these for loops because they're not know what any of this is because all they do is I wrote some SQL query Here's here's a query plan that looks like a query plan in every other system and now you need a way to excise out exactly like how much time I spent in one for loop versus another to map them back to the different operators。

 and that's not really。Something you can easily do。Right。So again， for this usability reasons。

 you be able to convey to users what's actually going on， you can't do this approach。

So instead they're going to do again what they call expression confusionfusion。

 the idea here' is that you can see you have two primitives being used over and over again。

 one after another within an operator， you just generate a single primitive that then can encompass both of the computations that the primitives arere doing。

So the example they have is you have a query here doing a look up on some date between some range。

Well， I take the Paina operator and can write this to be a less than equal to and a greater than equal to with a conjunction clause。

So without expression fusion， I would have two separate functions。

 two separate primitives for each each of these two expressions。

 and then you just take the intersection of the offset list and figure out what actually tus match both of them。

 right？So again， instead of having to make two different function calls over and over again。

Expression fusion just says I'll cogen or not cogen I'll create a single function that does both of them。

 and it's templated based on the type。 So I could， I could do this。 You know， these are for dates。

 but I would Cogen ones for all the possible data types。And then now for the expression that I have。

 now it's just a single line of code that does both of them。And so。In the， you know， in the。

 the vectorwise paper you guys read， that's from like 2006。 Of course， that was an academic project。

 But even vector wides that in the early days was meant to run onprem。 It wasn't a cloud system。

 So you， so in that world， you have to kind of guess。

What your kind of queries are user running and which one should be combined together。

 But when you're a cloud company like Databricks， you see all the queries。

And you just do analytics on top of that and figure out what things are being used together。

 And that guides you decide， using your own data to decide how you want to optimize your own system。

We'll see another example later on when we talk about Redshift。

 all these systems are really designed for doing read only workloads。

 but in Redshift they looked at their own logs， their own telemetry。

 they found there's a lot of here running update queries unexpectedly。

 so they spent a lot of time making update queries go fast and they wouldn't have not known to do that unless they looked at their own data。

So these database systems as a service providers are in a unique position that is much different than how people have built systems。

 database systems over decades， because now they know exactly what queries people are running and can decide how to optimize things again rather than guessing or worst case you never having to talk to people。

 which is always the worst。嗯。All right， so the next interesting thing that they're going to do with photon is how they want to manage memory。

So Spark already has a memory manager， already has memory pools。

 and because again photon is not a Sanone system， you got to run it inside of Spark。

 you just don't want to mallic anywhere inside of the CLL code because again。

 thinking about trying to run this as a service for users。

You need a way to keep track of what what that who's using the memory And so rather than rewriting a C+ memory manager and have that run alongside the Java one。

 you just rely on the existing memory management。 the Java based memory manager。

 it can basically allocate blocks of memory， you can keep track of it as if it was you know。

Any other memory in the JVM， and then hand those pointers off to the C Fs code to be able to use that。

So they're going to rely on all that， the memory manager in Java。

 and they they get the reporting and all the infrastructure you need to keep profiling and other stuff for free。

Er thing that they do though， is。And I like this paper because again， none。

 none of the other papers are going to talk about this because， again。

 they're running in the lake House environment。 They're running on files that they've never potentially never seen before。

 They don't have accurate statistics。 So they need a way to be more adaptive and dynamic to deal with。

Certain operators needing more memory than maybe they originally expected。

And so the way they do this is that rather than having every operator implement the capability to spill memory to disk on its own。

 they instead have the。WhenWhen you need memory or you're running out of memory。

 you just go the operators goes and ask for more。And now it's up for the memory manager hanging up in Java to figure out how to give you that memory to avoid the cr and failing and who to take the memory from。

So what they do is they basically get a list of all the currently running tasks。

 how much memory they've allocated， they find the one that has the least amount of memory that can satisfy the request for this query that's running。

 and then they tell it to release it and get the memory back so they can hand it to another operator。

So all the operator implementations have to have support for。

Spilling the disc and sort of pausing and coming back and catching things from disk as needed。

 and then that way everything is sort of seamlessly integrates and not worrying about running out of memory or keeping track of memory in different locations。

And again， we had to do this and we'll see the other ways to handle handle this。

 We have to do this because we don't we don't know how much memory you know， sorry。

 how many twobo may be coming out of a one operator because they don't know the selectivity of any of the filters that may be running on it。

Okay， so the paper you guys in the photon paper itself， you guys read。

 they didn't really talk about query optimization other than maybe maybe this last one here。

 but there is a earlier paper in that in the Spar SQL paper， they talk about their query optimizer。

 this thing called catalyst。 and then we had them come give a talk with us a few years ago and describe what they're actually doing。

 So I'll talk a little about what catalyst does， both in the context of Spark and then originally for SparsSQL。

 but then I'll talk about what they specifically added to catalyst to work with something like photon。

So again， because they don't have a robust query cost model。

 they have to be very adaptive and and make the best of of a situation where they don't have accurate statistics about。

You know about what the query is actually be going to do We'll see in a second how they're going to handle this or trying to improve their lot by using something like Delta Lake so they can see the data when it actually arrives and collect statistics on that。

 but again in the worst case scenario， if you're accessing a bunch of files on S3 you've never seen before you have to handle that。

So it's a cascadets optimizer where they're going to have predefined stages that are sort of handwritten or crafted by the engineers similar to what we saw in SQL server。

 where you sort of run from one stage to the next and do the transformations as needed。

And so as expected， they don't have logical， logical transformations。

 logical physical transformations， but what is unique about catalyst compared to like the textbook definition of cascades is they're also physical to physical transformations。

And this is where they're going to inject the photon logic because they have a physical plan that's generated by the previous age。

 and that could just run in Spar SQL as is。But then they go back and do another pass and say， okay。

 where can I inject the photon operators as needed？

So SQL server does something sort of similar to this。

 which we didn't want to talk about where it'll run through the regular cascades optimizer。

 generate a physical plan， and then some the engines that beyond just SQL server or different variations of it that support distributed queries can then do another pass where they convert the physical plan to inject like distributed operations。

 so they'll convert a single no physical plan to a distributed physical plan。

And they'll do that in this extra last step here。So again， there theres。

There's nothing really different for these first two stages here。

 This is the one that's relevant to photon。So the way they're going to do this is that they're going to do a additional pass over the query plan。

 but rather than do the normal cascades top down， they're actually going to go bottom up。

And they're going to convert it to a photon specific physical plan。

And the idea here is that you want to identify in which operators that are in the original physical plan that would normally run in Spar SQL can be replaced with the photon s operators。

 but now we need to make sure that not only were going to have a lower cost。

 but part of that cost calculation is going to be reducing the number of times we switch back and forth between JVM to N s+ plus。

And so if you're going from the bottom to the top， there's most of the times in most queries。

 there's more data being data passed from one up to the next at the bottom。 So you start down there。

 try to get into the photon engine the most as possible and avoid weird transitions of like halfway through going back to S plus then coming back to the JVM。

 you want to try to have the longest stride going up of just being entirely simple plus slot。

And so this happens during query execution sorry query optimization before you do any execution。

 because again， at this point， you know that the system knows that I have these operators that are written in photon and I can replace those sparse equalL ones with those This is not something you need to figure out at runtime。

So this is an example from the paper or another talk， so this is to say the original plan here。

 something real simple， scan a file， filter， shuffle， and then produce some output。

So you'll start from the bottom and top， say the file scan， for whatever reason that's still in Java。

 and then you know that you can place the shuffle and the filter steps with the photoile implementations。

 so this side we're running in Java so we use J&I tovoke down into C++ and they have some landing area that they call an adapter and that's responsible for converting things from the row store that's coming in the Java world into a column store。

And then you do all these vectorized processing up through photon on this。

 and then when you got to go back out to Java， they have this transition stage or transition operator that's so responsible for converting the data back into the form that's expected by the Java code。

So these adapters and transitions， these are you know， they're not hardly expensive。

 but you're basically pivoting and copying and moving data around。

 so you want't avoid having to do this as much as possible。

So this is all the Javava stuff and it's all this stuff， so again， they take this physical plan。

 they take a pass through it and decide where can they inject the photon specific capabilities。

All right so the paper also talks about how the two styles that addivity that they have and they have they preferred them as sort of macro micro which is their terms。

 so the macro of the queryry limit at adaptivity is the stuff that we talked about before where we can take the statistics that we've collected while we're running the query at the shuffle stage and decide how we want to modify the next stage accordingly by expanding or reducing the number of workers potentially moving things around is switching from a shuffle joint to our broadcast joint and so forth and that's basically all the stuff that that we talked before with Drmel。

But then they have this other style of batch level add， where within an operator。

 like as we're actually running the query plan itself。

 we can decide within a single tubal batch or a vector like。

Do we want to change what implementation of that operator we want to use based on the data that we're seen？

Right and this is something the photon just does for you automatically。 on the inside Wat's running。

 This is not something that the queryat has has to be aware of。

So this is gonna to be very similar to the Vox optimizations that we saw way back in lecture 5。

 where like， I'll show examples of this。 but like identifying my。

 I thought my data was going to look this way， but actually looks another way where like there's no nulls or they're askingI instead of you know Uniiccode。

 and I can switch and permute。😊，What， what operator implementation I want to use。

In the case of the photon one， you got to have the primitive the variation already precompiled。

 obviously because you can't switch they're not coj on the fly。So。

And so this is basically what I said， the query level optimizations again。

 before each each shuffle stage know after the shuffle phase completes。

 you can decide what what you want to change later on and we've learned to tell what shuffle for broadcast joins and current ad Drel for optimizing skew joins。

 the idea here is that you。You recognize that the data doesn has a different distribution。

 and you can change the number of excutters you would have maybe for one side versus another。

And then they're also going to be able to handle overflowing partitions。

 but can do something slightly different than we saw in the Drrem case。

 Remember the Drmel case was you recognize that a partition starts filling up and then you stop and and you do another roundcur of partitioning and you start writing tus to other to other partitions instead are overflowing it。

 They're going do something slightly different。 Ill show in the next slide。And again。

 all of this is because in the lakehouse environment， we don't have any real statistics。So。

The way they're going to do overflowing partitions is that。

They actually can't expand the number of partitions。

 and I don't know whether there's something fundamental about Spk。

 why you can't do this or is this is a design choice of why they this path or wouldn't have this path。

To avoid a problem of a partition running out of memory， running a space。

 they just allocate a lot of partitions more than you actually think you would actually possibly need。

So say my worker is filling up the partitions， and then I have these three partitions that are underutilized。

Because I've allocated so many of that。So what they'll do is they'll recognize before the partition phase completes that these three areut and they make a new partition and they have these guys just write their data into it。

😊，A。And then just carry over the two other ones and then mate， oops sorry。

And then he blow the memory away from the priest partitions。3 and four。

So it's sort of like achieving the same thing as Drel did， but like taking from a different approach。

Dremo is adding partitions dynamically on the fly。Spark is actually taking partitions away。

So the end result is still the same。 It's just they're doing this in a slightly different manner。嗯。

I don't know whether one is better than another because at the end of the day。

 you still have to have an extra step to move data into the new partitions。In the general case。

 you had that reader operator had to run after you've done them for crystal partitioning。

 in this case here， you had to funnel these guys into the new one afterwards。

So there's no free lunch。 It's not like one is， you know。Entirely better than another。

 I think that there's some aspect of， again， the spark engineering。

 the spark runtime that requires them to do it this way。Rather than take them away later on。

For the bachelor of add， again， a lot of these are to look like the stuff we talked about in Veelelloox。

 right， The first one is if you recognize that you're doing you're processing a string column。

 but the data is all ASI characters instead of UniIcode。

 you can switch to a faster implementation of your string functions because you're dealing with one by ASCI characters instead of。

know up to4 byte Unicode characters， right there's more variability in UniIcode and so that means more branch predictions than the CPU so if you have the sort of fast fast version。

 you just use that。For if they recognize that the vectors that they're passing up from one operator to the next within photon are。

 are pretty sparse， then you just compact them down to smaller memory sizes。

 And this will help when you do like a probing on a hash table because now all the data will be co the relevant data will be coed together and it's。

With all within a single cash line and you can put things out more quickly。

Or do the pros more quickly。They also can leverage the templated nature of the primitives by identifying that they have no nulls in a vector and avoid having to check the null vector and likewise if they have no inactive rows。

 they can avoid that lookup as well， so this is the code from the paper and so again it's a template of a sequence plusus function where you have a booleion that tells you whether you have any nulls in processing this or you have and whether you have any active rows that active。

So this is like this is the template of function， you always write this code as is。

 but then at compile time you would pass true or false to either of these and you make different variations of the same function。

Then at runtime， you can say， okay， well， if I know that I don't have any inactive rows。

 then I would invoke the all active ones， and then this will just get thrown away。

 the check gets thrown away at compile time because you know that it's a compile time constant that this thing is always true so you just pick I right so you just sit row in X I and you don't have to do this look up in the position list So it's low low optimization but if you're doing this for billions of tuples over and over again or billions of batches definitely have a big savings。

Likewise， for the has nulls， if this thing is always true。

 then you know you don't have to do the lookup in the null off。So I think they。

 I forget what numbers they they talked about for these。 But for this compaction1。

 I think they do this where joins and they get like a 1。5 x speed up on the probes。 Again。

 that's just the probe， there's almost much other stuff you're doing in in your in your in when you run a query。

 But that's， you know， that's a。😊，It may not be the highest poll in the 1。

 but that's a pretty significant speed up of just doing the sector step。

I forget what the numbers they save for for this one here。All right， so I'm going show one graph。

 this is what they report as the improvements you're getting with photon enabled in databricks and Spark versus in SparSQL and for TPCH a rather large data size sc factor 3000 so across the board you would see the red is just faster in some cases the performance is quite significant like for Q1 here for other ones maybe less so I think Q1 is the some of those one just ripping scanning through so in that case I'm assuming most of the operators when the query plan are all floated into the to photon。

Right。And again， the way I think in databricks， I think this is still true。

 I think they charge like 20% more that you specify whether you want your job to run as a photon accelerated query restes like the regular Sp SQL and they'll charge you more for it。

Because you're getting better performance。It's kind of a wind minute for it them。

 I mean they had to spend engineering time to actually build the thing， but like。

Your queries going run faster， so it's going to use less compute resources。

Pably uses about the same amount of memory， but and you pay them more for it。失礼？Its a smart move。

So this is TPCH， TPCH is a precursor to the original OLAP benchmark came from the early '90s in the paper as well。

 they talked about getting official TPCDES results。

 so TPCDS is the successor to TPCH it's like think 2006 and so they made a big deal and this came out in 2021 in this paper and everything that they had official TPC results so this is their webpage or TPCC。

 the transaction process and council's sort of like the independent arbiter referee of database benchmarks。

RightAnd so TPCH， TCDS， those benchmark specs are defined by this consortium and then if you want to have be the official leader board。

 you go get certified by the TPC people to say your implementation matches the spec requirements and then you can be listed here so Dataricks got listed in 200021。

 they're still listed stone number one for running on 10000 gigabytes for TPCDS and they beat the previous one was。

Was Alibaba from  2019。 so it's not just the performance you're getting for the query itself。

 like how many queries per second you can do。 they also check to see like how much you're paying for this if you had to pay as a service。

 right。So Databricks was supersted when this came out。

 they made a big deal about it the bunch of these articles when this came out talking about how Databricks has official TPCD results that have been audited and how they're gunning for snowflake so the bunch of articles at this time for this one here they actually asked me for a quote and I wrote I said at the enterprise level maybe some CIO is going to care about what your official TPC ranking is but they don't make sales that way。

This is actually not the full quote。What I said after this was and only old people care about TPC results and they cut that off。

And so what do I mean by this？I mean， how many people you've heard of TPC and TPCD because you're reading the papers and seeing these things。

 you may not know that there's actually a consortium that is is the one that's defining these things。

 So this comes out of the 1980s。 It was founded by Jim Gray and a bunch of other these people because at the time all these different data as vendors were putting out their own making up their own benchmarks putting out marketing stuff that says look how much faster we are than everyone else。

 But then you couldn't reproduce the results because the source code wasn't available。

 the environments weren't reproducible So it's really hard in terms of performance。

 say one system is actually better than another in different ways。

 And so the TPC consortium was meant to again， sort provide a level playing field for everyone to understand this。

But like。It mattered a lot， certainly in the 1980s and 90s， I would say it matters less these days。

 although we use TPCH and TCDS all the time， there are good workloads to benchmark systems。

 but to go and get the if you're new startup to go get official ranking， get audited。

 it's a laborious effort that probably just not worth it。

 as I'm saying like no one's going to care look I have officially audited TPCDS results。诶。

Like nobody cares。Because it's a lot of work actually they told me they had to go drag somebody out of retirement to go do the auditing for them because nobodys around to do it anymore。

 right。So there's another website like Clickhouse has has this thing called Clickbech。

 I can show that next class。 There's， I'm not saying the benchmarks themselves are worthless。

 I'm saying like going through the effort and get officially audited is probably not doesn't mean as much as as it used to anymore。

 And certainly now with all these cloud database systems as we'll see next class when we talk about snowflake。

 It's getting the。You know， getting the。ForBe able to do Apple to apple comparison from one system to the next is hard to do because there's just so many different layers to these systems these days that it's hard to say am I running the exact same hardware。

 I would get from one vendor to the next。Because instead stufffl you don't say I want to run on this instance size on EC2。

 you just say I want this compute capacity， same thing with Azure and other cloud platforms so you actually really know what hardware you're actually getting it sort of hidden from you。

So again，I'm not saying that the benchmarks are useless。

 I'm saying going down the path that that Databricks did to get officially audited。

I I don't think it was the， well， they have a ton of money that can do this。

 like if you're a new D startup， it's not the best use of your time。Again。

 we'll cover benchmark Wars more next class。With snowflake。Okay， so photon is proprietary。

 So Spar is open the source。 But as I said， the database is runtime itself， which includes photon。

 is not open the source。And so you can only get the acceleration that we're talking about here if you go pay Databricks money for it。

 but they're not the only game in town to try to accelerate Spark。

 And so there's a bunch of other accelerators that are our open source from various companies that you can you can then use to get。

Pton like improvements。 But what's interesting about them is that rather than doing the fine grain integration that photon does with they're replacing individual operators and deciding at runtime when to call into JVM versus。

Versus into CS code。As far as I know， all of these systems are just co-oping or taking the entire query plan。

 ignoring the spark run time entirely and running it on a separate engine。

So the probably the one that's most popular not the right word。

 the one that's probably the most well known is Apache glutein。

 this is usually previous it was called gazell。 I think was Intel and Alibaba。

 But now it's an Apache project that Intel's running。 And the way again。

 the way it works is that you take the spark generate some kind of physical plan。

 And then you have the different mechanism to take that query and run it somewhere else and and by converting it into substrates。

 you can run it onarrow F Gs they have clickout support our vox again， they're not doing the。

On a per operator basis， they're taking the entire query plan， running it someone cells。

 but you're still accessing running the query through the sparkark front end through that expected interface。

There's another one that actually just came out two months ago from Apple。

 So actually this is this is this is as this was showing a bunch of different backends thatll run this。

 This one from Nvidia。 Rapids is like their coutabased library that do data science stuff right。

 and it's obviously meant to run their GPUs。 Blaze is out of a Chinese company that runs data fusion。

 And there's new one here called Comet from Apple that came out to two months ago。

 That's all entirely in data fusion。嗯。There's been other attempts。 gluten is know。

 multi data systems plus belocks， but data fusion assumes to be the one that everyone is leaning towards to accelerate spark these days。

And I don't know what， I mean， Databricks is obviously the biggest sparkar vendor。

 I think Azure from Microsoft， I think they're promoting the rap as one。Just speed things up。

All right， so the last thing I want to talk about is。

 as I've been saying multiple times and we'll see throughout from now and the end of the semester。

 is we don't have statistics because we're running them data lakes and adaptivity will help for certain things。

 but ideally if if we have adaptivity plus better statistics， then that's the best world to be in。So。

What has evolved and come out over the last couple of years。😡。

Since the first dremel paper came out of， instead of just assuming that everyone's going to dump their files on S3 and your engines are to go try to figure out。

 try to make sense of it later on。The idea is that what if you provide a service or mechanism to allow people to ingest data into your lake house or data lake and as that data gets ingested。

 you then can collect statistics about it， keep track of it in your catalog other than just like I have these files here's where they are now you can look at the data and keep some track of statistics and you can use that now in your query optimizeizer for your cost model。

So the photon paper， I think they mentioned the Delta Lakes stuff。

 but this is an open source project， but this is specific to Databricks where this is there- it's a standalone service but it sits in front of S3 and spark where you provide a basic interface to send data into your lakehouse。

And all it's really doing is just taking your updates， writing them to some log file。

 and then in the background there's this compaction process that runs， grabs the log file。

 converts it into parquet， and then writes that into back to S3 or whatever your object store is and then when it does this conversion to parquet。

 that's when they compute statistics about what's actually in the file store that in their catalog。

 and then now the query optimizer can access it。So no longer you just some other service could in much of data and then plopping it down to S3 is a parquet file。

Delta link will drain the parquet file for you， because it actually has to scan the data and put it into the columnar format of parquet。

 that's when they collect the statisticss。So they're not the first people to do this。A。It actually。

 one of the first versions of this was from， from Caldera as an extension to impala。

 this thing called Kuddu。 And it was basically the same idea。

 although I don't think they were writing exactly to Parquet。

 I think they they had their own proprietary format。 But same thing。 you had this， this。

This system that could do fast updates into a distributedscript file system。

And they collect statistics about when the data was being ingested。

 and they would then store that in catalog and then feed that to the query optimizeizer that you can then access through impalA。

This one again， I think in Delta like I think you could run SQL queries on it。

 I know in in iceberg you can using other systems， but this one was like a really low level like get in set interface to do these things。

And then if you ever wanted to run SQL， they would tell you to overrun it on Aalla。Right。So again。

 this was 2015， well before Delta Lake came along as a way to can help sell Aalla from Cloud Airero。

So again， same way like I think we everybody everybody to say this in the same way Databricks is like the huge company。

 like database data company now that was Clouddera 10 years ago。

But most of you probably never heard of cloudai before we started talking about it here， right？

As you who here is our to cloud out report this class。Nobody。That was the hottest company。

 they were huge。And it sort of shows you how。Show you how quickly things can change in technology。

All right， there's other alternatives to this， Apache Hootie， what came out of。

 I think it was Uber in 2016。And a lot of this text is basically saying the same thing that I said for Delta Lake and Kudu right it'ss a service where you can ingest data。

 I think Hoy can support parquet and orRC files generating those。

 but they're in a classic statistics about the data as it arrives。

 sort it in a catalog and then expose it through different sources。

And so this is actually the diagram they have on their homepage and it shows you exactly what I've been saying like here's all your front end stuff like you have these updates coming in from your operational databases upstream for your application。

 they're feeding into Hoy， the updates to the log， it'll write them out what they called Lakehouse platforms。

 but this is basically HDFS S3 are the Google Cloud St and so forth， right to your object store here。

😊，And then you update the catalog。 I think that''s Amazon gluelu。 I forget what that one is。

 that's hi， the hive catalog， H catalog。 you update the metastore， the catalog like。

 here's what my data looks like。 Here's the statistics about it。

 and then you have the various query engines that we've been talking about。

 be able to read from the catalog， figure out what's in there。

 use the statistics that they generated， and then process the data from that the service has generated。

😊，So that's how these things fit into this。 right， We've been talking all this stuff back back over here。

 This is just a way to get the data in to the system rather than writing it directly to the object stores。

The next one again that we've been talking about that the catalog teams have been working on is Apache iceberg。

 This one came out of Netflix in 2017 and again it's basically the same thing as I just said。

 you're ingesting data into the system， collecting stats。And exposing it to the query engines。

 So we'll see next class， when we talk about snowflake。

 this is the only way snowflake is actually going to。

Be able to support ingesting querying data that isn't stored in their managed storage。

 So they added support for this in 2021 because prior to this。

The only way you could query data and snowflake is you had to insert it into snowflake。

 But now with iceberg， they can actually。Feed that into their own system。

 I forget whether they do wholesale copies or they can access the data where it resides。

But we'll see the same transition with Redshift where Redshift only had managed storage。

 they weren't spreading iceberg and then they added support read arbitrary files alpha S3 later on。

그니까。So again， I think photon is a really interesting system because again， rather than is like， what。

Oh yeah， yeah。It's true So photoja is a really interesting system。

 but you see like to the lengths that they had to go to like dealing with the legacy code that were that they had to support and from a business decision。

 I think it's the right move to like don't throw away which is already working and you're making a lot of money on for your existing customers improve it by being more fine grain and how you integrate the new technologies and new capabilities based on all the things weve talked about throughout the entire semester But certainly if you're going to build a system from scratch today。

 you wouldn't want to go down that path of like taking some JVM monster and trying to work around it。

 it does make sense to build anything in Javava these days。 yes， Javava is getting better。

 the Gm is getting better， the new garbage collector that just came out a year or two ago way better than it used to be there are a proprietary JVMs that you can get something like a zul that's faster than like open JDK or the one from Oracle。

 this is all the high frequency traders use but。If you're trying to run something at scale。

 you don't want to pay a license for every single node to use that proprietary JVM。

 so building in something in rust。Steeven's last Zig is probably going to be the right choice。嗯。

Not the JVM。But again， there's a lot of systems that are in this pattern and we solve this with when we mentioned Presto and Trino。

 right， Presto， the one that is out of Facebook， they're replacing their Java runtime with Velelloox。

 and again that's a wholesale replacement with the entire query engine rather than the fine grain thing that photon does。

 whereas the Trino guys are just going to deal with they decide they're going to stick with Java。

Legacy code。All right， so again， next class on Monday where we'll talking about snowflake and the snowflake architecture is going to look like Drmel。

 they're going to be the paper you're can reference from 2016 is be more about the managed storage that they provide where like the data controls everything。

 but then we'll talk about how they integrate with iceberg。And。

 and be able to handle updates in the new versions of Snowflake。 But again。

 the high level architecture is going to look look the same iss going to smell a lot like vector Y and X 100 because one of the cofounders of Snowflake was the guy that wrote X 100。

At a CWO。So we'll see a lot of similarities of through systems。

 except that the vectorized stuff we talked about was running on Prem or the paper you guys read about running in the cloud as a service。

Jacob got a bounce to get the 40 else get a quick take sister。

 you'll be picking up models ain't puzzle because I more man I telling in the 40 I got Thor can。



![](img/8ff74da2af18b304241c00cc4244a57d_5.png)

St and six backs on the table and I'm able to see St I on the way。No short with the clock。

 you know what got them I take off the cat but first I' tap on the bottom。

 go about three in the freezer so I can kill it， cat full with the bottle baby。

Cing life says the pay life way， you drink get down with the guy。Take back the pack of blood。

Go' get you some same no to T to the， Billy De and toill takes to tell weak Go。

 be a manic kid a kind of think time。