# CMU《高级数据库系统｜CMU Advanced Database Systems (15-721 Spring 2024)》中英字幕（豆包翻译） p17 -17-S2024 #17 - Google BigQuery _ Dremel .zh_en -BV1HZ421N7WZ_p17-

🎼Carnegie Mellon University's advanced database systems course is filmed in front of a live studio audience。

😊。

![](img/1a5954df15769f59c1cfbeef9fd601e7_1.png)

🎼。は再见。Just get through this， get out early， and go see the clips。

So at this point in this semester we're going to start reading papers about individual systems。

 so obviously the paper you guys read today was Google BigQury。

 but the purpose of this part of the semester is now to examine and look at how companies were building real systems based on the technologies and methods and techniques and algorithms that we talked about throughout the entire semester and the goal of this is to one learn how we can read the papers from in industry。

 some it's a little bit marketing heavy， some of it will be actual true systems discussions。

 but basically understand they've apply the things that we've talked about to solve the real world problems and also for you to then be able to interpret it。

😊。

![](img/1a5954df15769f59c1cfbeef9fd601e7_3.png)

Realibrate maybe how they describe certain things based on the fundamentals of what we talked about so for example sometimes you'll see systems talk about technique ABC in slightly different language that we talked about but then you know because we've read certain papers oh that is really describing this。

😊，not to pick on Drmio， but we'll see Drmemia in a second。

 they talk about having these things called reflections， like what the hell's reflection。

 I' never heard of that before， you'd go kind of read the documentation a bit more， oh。

 its just materialized views。So the idea is it now you had this core background knowledge about how these real assessments were actually built。

 and that you can cut through the BS and understand what's going on。They call reflections。Yes。Okay。

 and then and then also too， now you also have this， this internal catalog you to build to say， okay。

 well， in the good papers， least essentially in the Databricks1， they'll talk about， oh。

 we had this problem。 So we solved it this way。 We had this problem solved that way。 So again。

 when you got in the real world， you' be able to see how， you know。

 apply the same lessons you've learned from reading these papers and other systems to different situations。

 And of course， it's always nice to understand that like I didn't just make the stuff up。

 everything we talk about the semester is， is real。😊。

So they said we're going to start off with Google Dremmel， a Bigque today。 Wednesday。

 we'll talk about the Databricks， spark SequL and photon， and then snownflakeduct TB。

 yellow brick and redshift。 So because of whatever the stomach virus， we had to drop the last one。

 and I decided to drop the Microsoft paper， instead of the yellow brick one because as he was asking that before。

 the yellow brick one is wild because they do all sorts of low level system optimizations and they report real numbers in their papers whereas these other papers。

 you're not going to see that。😊，嗯。Part of because these big companies don't want any numbers they report in these papers that used against them in like a judo marketing move by their competitors。

 But yellow bricks， they don't give they put all the numbers in。 It's awesome。Okay。

So the reaccurding themes we're going to have throughout the entire the papers we're going to read are again。

 all the things that we've talked about this semester。

 So obviously the resources seggregation is separating compute storage this is the Lakehouse data lake model where a bunch of data on S3。

 whatever object store is， and then we're putting query engines on top of that。

We're also going to see the challenge of dealing the lack of statistics。

 The Bigque paper certainly talked about this， we'll see this over and over again where it's a bunch of files that were uploaded into the object store。

😊，Outside of the control of the database system。 So now you get the query shows up。

 you want to start planning on it。 Well you a cost based optimizer。

 what are your costs going to be based on if you don't have any statistics。Obviously。

 everything is going to be columnar， but we also going to handle the nonreal data， the JSON。

 in the case of the BigQu， it's the protocoltobuff files。😊，And then vectorized execution。

 as we talked about before， again， these are like this thing is pretty much standard in every O lab system today。

 So none of the papers are really going to talk about any unique unique aspects of what they're doing。

 which is it'll always be that。All right， so let's talk about now the setup for Google's Dremmel BigQu paper。

So。Maybe not in， you know， for， for the。For people that are younger here， maybe not now。

 you don't think of like Google as the hot like tech company， like maybe like open AI is， know。

 is what everyone's excited about these days， something like that。 But then in the 2000s。

 Google definitely had a sizable influence on how people thought about and design and developed database systems。

 And even to this day， I would say their。😊，Their pushes maybe or influence in Min is not as strong as it used to be simply because the technologies have been spread out proliferated much farther。

 now obviously LLms the hot thing。 But back then， pretty much any time Google put out a paper a research paper that said。

 hey， here's this system we built internally at Google that everyone read it。

 everyone got really excited and then people started building open source clones of these things because because the mindset in some ways was while Google super successful。

 Google can operate at scale if we need if our company wants to be successful that we need basically the same stuff that they're building because Google didn't release their things as open source。

't at least in the beginning didn't release their things as services They was like hey。

 here's this paper written by Jeff Dean and others who obviously very smart people that everyone was like okay they scrambled them to reimment everything。

😊，So this is sort of an incomplete list of a bunch of the database systems or data systems that Google has developed up over the years that have been very influential。

 and that's sort of subdivided into to two groups at the top here。

 you have all the No SQL systems because again。😊，Google was was the， you know the。

Without maybe coming out and saying， hey yes， we're a No SQL company。

 but they certainly were at the forefront of the vanguard of the NosQL data movement。

 right And you saw this in the paper you guys read。

And then there's all these other these systems in the late early 2000s you late 2010 late 200s early 2010s and going forward where Google realized oh SQL is actually a good idea and then started adding started building systems around this again in the paper you guys read there's this paragraph right here。

 that talks about how the conventionalism Google was SQL didn't scale and then again。

 everyone else sort of follow along this bandwagon and was designing systems based on some of these early ideas longgos probably one of the biggest ones where people were saying we don't want to use SQL SQL doesn't scale we't want to joins then now the titus turn。

 And so the Drremo guys talk about how they see themselves as the ones that actually made Google sort of made SQL cool again or important again or matter again in Google。

😊，So a lot of these systems have sizable influence in a bunch of different other data and other data systems and as I said。

 a lot of these things started off as early research papers that Google put out and typically the way industry companies put out papers is。

😊，It's usually about two or three， maybe even four or five years behind what actually the state of the art is。

 so like they'll build a system， you know get it up and running。

 file the patents for it and then they'll write the paper by the the paper comes out again it's a couple years old。

But Matt produced， obviously， was very influential。 you know， made Hadoop， made Sp。

 Big table was cloned his H based cumulative hyper table。

 And so what level D was was this deal when they actually did open the source and then got forked off as Ro D and B Db was more common now。

😊，And then there's other examples down here。And there's a few other like parillas from YouTube。

 again， there's just the paper that's not what source。

 there's a couple other tests I could list there that I sort of forgot or just having have room。Yes。

 why is the we just look at Dr and not the other ones？body。So why why are we looking at this one。

 not these especially why why we， why do we care about Drreel this class and not these other ones。

 Because Dremel is the only one that's doing analytics on the old lab stuff。

 Megastore was a early charter version of My CO do transactions。

 The test has started my SQ at a YouTube spanner， I want to know about transaction。

 These are all transactional ones。 Napa is sort of getting into the realm of like doing analytics。

 but it does。😊，Well， we can talk a little bit maybe next class。

 the context is like Delta Lake or iceberg， but NAP is all about like。

I'm doing Drreemmel style analytics on historical data。

 but I'm also incorporating newly ingested data。 And I can make a trade off between how much I'm gonna to read from the only paper cost of like the road road data I just just inserted versus like historical data。

 And then Delta Lake iceberg， they're all doing something similar there。 Yeah， But again。

 part the reason again， question why before using Drmel， this is a very influential paper。

 this is pretty much how every you know， lakehouse engines be built today。Yes， what do you mean？

So I have an asterisk for Coroach D and TiDB home marketing。

 because when these systems first came out。The cock D guys certainly worked at Google。

 but they didn't work on Spanner。 And then Had guys had nothing to do with， know， with Spanner。

 Spanner was like the hot thing for like， know transaction database。

 So these guys were maybe they explicitly they didn't say it， but others are saying it。

 and they didn't correct them， that these are open source variants of Spanner。

But the case of cockchroach Gs and T that's not the case because Spanner relies on this true time service with like GPS clocks and atomic clocks。

 part of the true time hardware service， cockchach G is doing everything in the software。So again。

 certainly now they're not going to like say that they're the opensource version bannerner。

 but if you could use Google opensource。Spanner， you probably get cockro B a tidy B。

Cs about something， so he said that lots of like every lake house is based on。あ ideas。Yes。

 I also know that data groupss。みたてこ。You think is more。

So his question is I'm saying that all these lakehouse systems are based on the high level architecture of Drremel。

 but then the database guys， they're the one that branded the Lakehouse term。

 but that's just marketing again。The trino guy saying no no。

 it's not a lake house you want an ice house， so it's just marketing。

 but the idea of a disaggregated storage， a vectorized execution engine that can read data that it's never seen before。

All that comes from dremel。There's other aspects， though， I think， like， you know。

 in case of snowflake， like snowflake was doing the vector execution or actually more like vectorwise。

 vectorwise was doing the paper guys read with like all that vector execution stuff like that's preent everything。

 And that' that's common now in a lakehouse system。

 but they weren't calling in the lakehouse back in the day。 It's just a marketing term。 Yes，😊。

Releasing general。Those in favor said ae。Sorry， the original was 2010。Yeah， it BLDB。

I so the original paper is like 2011， right， I think in the paper， they say it came out。

 it was like a side project in 200s。Six or something。The 2%。 Yeah。

 I think I'm putting the day here based on。yeah， so maybe they date。

 like like this is when it was first known。 so the paper you guys read is the10 year retrospective of the original paper。

 The original paper is 2011。 But I think that paper mentions that somebody was buildinging in 2006 has originally a shared nothing system。

Right， it was just like the Tesla time award given to ELDb 20。Yeah， whatever I'm multi by year。

 but again， in the paper De says they started it earlier。Well。Again， MaA。

 I know these guys are building this since。😡，2017， 18。But I was under N。

 and I couldn't say that would like， the paper came out 2021。 This is the Napa。 No。

 it's because you're it does like you justest。You get。

 you ingest data and it gets appended into the system。

 I don't know whether that ingestion process is transaction or not。

 And then they have this notion of like， do I care about when I run run queries， I specify。

 do I want to run fast as possible。 And then maybe and then but give up like reading the freshest data or do I give up。

 Do I want to read the freshest data and， and pay a little more extra money to get get faster。

 like they have like sort of。You have the objective function like in terms of triangle。

 not just cost performance， but also like freshness。Okay， yeah。Again， we， for this class。

 let's focus on Drre。 they gave a talk。A year or two ago during the pandemic with us about never。

 it's a good talk。All right。All right， there。 Ive already said 2006， right， So again。

 this was a side project。 I Google like 20% time， like one day a week。

 they were they were allowed to work on this。 And the idea， the。

 the original problem they were trying to solve was。😊。

There's all these artifacts being generated from different tools and services all throughout Google that are showing up on GFS and an internal file system。

 and the idea was they want to be able to run queries on top of this data。Through SQL。

 rather than writing this CQ clause map reduced jobs again。

Going back to like the mid 2000s and Google saying that they don't want to use SQL。

 everyone's writing these Mareduce appss。 Hadoop， the open source version of Mapreduce was in when Java。

 the Google version was all in S plus pluss。 So you have the right now S plus pluss code to do scans and joins and on data。

 It's terrible。😊，Right。OhYeah， so， so the idea was they wanted to be able to just have a bunch of files sit around on。

 on disk sorry in in share storage and。😊，And in just it， although the first version actually was。

 was a shared nothing system， meaning like you had to ingest the data into the system and then it got internal。

 you know， got cataloged。 And then the 2010 rewrite was。It should be late 2000， not 2010。

 they rewrote it to now be the disag storage where is reading data directly off of Google Ph or GFS。

Right。And then this was the first paper came out in 2010。

 and then it was got commercialized in as Bigque in 2012。

And the reason why I had you guys read the follow up paper rather than the original paper because the original paper doesn't talk about the shuffle service。

Where this one does， and that's actually a key thing that separates Big queryry from other systems and allows them do some interesting optimization that other systems can't easily do。

They many know what a Drremel is that's part of a database。What is his hand gesture？Yeah。

 it's a tool， right， So there's a foot in the paper。 It's a brand of power tools。

 primarily used of speed to post to torque， right， It's more or less than the minutetro。

 It's just like a rotary like drill， like a grinder， user things。😊。

I'm always surprised that like their lawyers let them put out like a paper that says， hey。

 we have this， we have this internal service for our multi billionllion dollar company。

 and we've named it after another company， right That's asking for a lawsuit， but。They did it。

 And again， but then the commercial version they they know smartly renamed it as BigQu。

 So all the documentation you'll see online for what Drel is actually doing， know。

 it'll be called BigQu。 But for whatever reason， the papers are still referred to it asmel。Al right。

 so this notion of ins sititu data processing。 we've already covered this many times throughout the semester。

 It just means that I have a bunch of files that are sitting out in some storage that's separate or not under the control of the database system and something else is gonna to be putting files there and people then want to run queries on top of them。

 So obviously， I need to be able to have a way to know what the files are some kind of catalog reference it to some table or some logical identifier。

 if you want to read。😊，This collection of data table food， whatever you want call it。

 Here's the files where to go get it。 But other than that， the。

 the database system doesn't necessarily need to know anything。Now when we read Snowflake next week。

 Snowflake had what we'll call managed storage where you ingest data into the data system and then Snowflake is responsible deciding how to chop it up and where to store it and understands everything about it and the new versions of snowflake now they have to support this lakehouse architecture。

 so they now support reading data from iceberg files。Same thing with with Redshift。

 They originally started out being a shared nothing system。 Everything was old managed storage。

 Now with Athena， you can read files on S 3。 Yes，fl they also charged the ETL cost between moving that data into their。

This question is， does snowflake charge the ETL costs from getting data from from remote storage into proprietaryrietor storage？

Sure they do， right？Because they have extra steps that they have to do。

His question is does it make it much worse product extra something to do？Well。

 with pause for that and never now， right？Again， it's not always like cost matters。

 but performance matter。 like， there's so many different factors to say， like， is it a bad product。

 And I want to time they cop out， they like， you suck you know， corporate masters of it。

 Im saying like。Depending on different scenarios， that may or may not be a good idea。But fact。

 they do support it。 Now， that's a good thing， right。Am。And as we've seen throughout the semester。

 all these systems when you have a bunch of files in some format。😡，You。

 we've seen this in the teams working on the caching server， the Io service here。

 You're going convert it into arrow or some other internal format， then process it anyway， right so。

You knowW who pays for that cost depends on the pricing model。So again。

 this idea of Demel what they were trying to do was。you know reading files where they exist， right。

 this is what we mean by data lake or the lakehouse stuff， and there's just a marketing term。

 but Drm' was doing it long ago。And in the paper， they point out that one of the key reasons that they went with this。

 trying to support this capability of just reading files where they exist is that it was better to have that their users were willing to sacrifice performance of having natively managed data。

They would rather sacrifice that performance in terms of the flexibility or the ease of use。

 meaning like I don't have to define a schema， then load the files into my schema。

 then run queries on it because there's a human cost to that labor costs it's rather just yeah my queries is going to run a little bit slower because I'm reading bunch of files that maybe not be in the best format for my database system。

 but that's okay because I can just get to it really quickly。And from my perspective， yes。

 I think this is right off。 And then SQL is typically the right abstraction you would want to do this。

So for all the systems that we're going to look at for the next two weeks。

 we're going to use sort of the same kind of summary page like this。

 we're going to hit all the high level aspects of the system as it relates to all the things we talked about throughout the semester。

😊，So again， a lot of this is going to be table stakes because just things that you would expect in modern。

Lake House or OAT engine be support。 So shared diskag storage that's to be expected。

 factorized query processing。 As we said， the these papers aren't going to say anything deep about it。

Other than， I know that BigQuery is using intrinsics。Because we asked them。

 the paper doesn't say that。 though。 The shuffle based distributed execution we'll get in the second。

Well， Google is gonna to have their own proprietary format called capacitor。

 we'll see that in a second。 although it's not a lot of details about it。

 but it's basically going to look like parquet and org。

 and I'm sure people are generating parque and orc files internally at Google。

 But for this common storage they're gonna to use all the tricks we talked about zone maps， filters。

 dictionary and rly compression the only index they support in in Bigquery。

 the service is inverted search indexes to do like like regular expression lookups on strings。

 theyre only going support hash joins and then they use a combination of heuristic optimizer and a。😊。

I'm a very light call space optimizer when you have some statistics that usually they don't。

 and they're going to rely heavily on the ability to adapt the query plan while it's running based on the data it sees。

So we're spend most hard time talking about this because this is going to allow us to do things that we couldn't easily before and this also is the transition to what we've been talking about in the entire semester where we would talk about how do we build the single node execution first and then now now start glue it together and these systems。

 especially with the shovel is one way to start gluing it together。So when a query shows up。

 the database system is going to convert it to a logic plan and then divide that into stages。

 roughly correspond to pipelines but not always necessarily。

 and then within the stages it're going to have multiplepar tasks that I'm going to distribute it across the workers。

And one key aspect of their query plans is that they need to guarantee that every task you would execute is going to be deterministic。

 meaning if I execute it over and over again with the same data。

 I should produce the exact same result and it's going to be item potent。

 and this is going to allow them to have the ability to restart a kill a stagggler a task that's running slow。

 and then re- executeute on the task on another worker and be guaranteed to produce the same results。

So think of things like。If I have a random called the random function in my query。

 I need to guarantee that no matter what worker I run on， when I invoke that random function。

 I get the same sequence of values or timess another one too。

Deemminacy has in deacy in terms of how long it's going。呃。Yes， deter yes。

 deter in terms on how it going on and also producing the same result。So thats item important， yeah。

Alright， so there'll be a root node or the coordinator that's going to be responsible for。

Deispatching all the tasks， they talk about having a centralized schedule。

 but the coorinators really is sort of setting things up and then handing things off to the scheduler。

And what's interesting they talk about。 and we'll see this， I think。

 also in the snowflake paper as well， is that。If you have all the workers going out to the catalog and the metadata sort and say what was the files that I need know when they start executinging the task。

 then you could have thousands of workers， all of a sudden flooding the catalog all these requests。

 So instead the the root node is going to do a batchsh request to the catalog to get all the metadata about the files is' going to scan ahead of time and then embeds that analog logical plans。

 So now when you hand the task off to the workers they don't have to do look the catalog。

 they have everything they need to know how to process at the beginning。

Every worker knows is going to have its own local memory and local disk。

 and then if they run out of memory while they're processing that given task。

 they'll be able to spill through that disk and spo it back in as needed。

But then also we'll see in a second， they're going to write out the results to a remote memory service。

So thiss look a really simple query plan do doing a lookup to get the number of articles in Wikipedia with my name in it。

Pavlo， there's some other asshole Greek singer named Paavlo too， and he might be on there。

I used to me when I was younger， like you just Google Pavlo， I would come up first。

 Now this other guy is， but whatever。 All right， So we have a attribute false。

 bunch of day we want to access in the first stage of the quarter says， okay。

 I'm gonna fire a bunch of these workers This is when I'm doing a partial group eye。

 And then these workers are in responsible for pulling the data that they need from from the shared disc storage and then doing what processing on it。

 And then now the output of these workers are are not going go to the next stage of workers instead they're going to go to this inmemory shuffle service。

 So all the worker node are going be writing out their data to this think of this like an in memorymory key value store that that's partitions are scale out horizontally。

😊，So I can hash whatever the data I'm looking at and decide sentence to what shuffle node I need。

And then now the shuffle node can then send additional metadata about here's the data I saw for this first stage for this query to the coordinator。

 and the coordinator cons on the fly how many workers that it should use for the next stage。

And then it spins up， you it submits that request to the schedule the schedule then fires up these workers。

 and then these guys are going to pull data from the M memoryory shuffle so they're not going to communicate from a important worker to the next across the stages。

 they're always going to use this in memoryory shuffle as an intermediary。Yes。Two questions Yes。

 is the memoryle single thing like question is it is it single note or scaled out， scales out out。

 Second thing， Why have that Why not just make them like Mauce does it。

 which is you can the workers talk to。question why am I doing this。

 like why have this extra step to go to this piece versus having the worker just。

Pull the data from the worker。 right， theres， there's performance implications of like， if。

 if now we're thought if， if。I can kill all these guys and then reuse them the test for other things。

 And this thing is just maintaining the server， you know， maintaining the data。 And then， you know。

 otherwise' got to keep this thing around so that make sure they get all the data that they need because what happens if like。

 save one of these guys down， go down。 then I got to go back to the previous worker and get the data again。

And then as I said， we'll see in a second having me a step that then get all the data I need from this first stage。

 then I can decide what to do in the next stage because I've seen the data because I now have it in a sort of central location that I can pass along to the coordinator。

Does it live for longer than just one cycle， Maybe you give that memory for a very long time。

 The question is， does do I keep this memory around for a very long time。

 would mean like what the content and memory or the service itself， The service is always running。

But I mean in the context of the memory， in the sense that so we're waiting for all of those three workers to finish right before so that we can then erase that in memory shopel that we have of there。

So when you get to the next stage， at what point is this get blown away。

 the coreator would come back and say， all right I've completed this stage， everybody's got the data。

 you still need to get past this stage because again。

 these guys could crash and you need to go fetch it again。

 but once you know that nobody else is going to go back to the data you you can blow it away。

Another thing that needs be like a shitdown of memory and also yes like the worker can die。

 but this can die too but it's just a key value store。

 There's no techniques to replicate this and scale this stuff right It's even crazier。

 They actually fab custom hardware to make this go as fast as possible。Oh， yeah。It's awesome， yes。

Keep track of。The question is， why not keep track of metadata rather than streaming all the data here。

 But where are you keeping the data here， right？ That means these guys can't go away until you've gotten the data over there。

So in Matt produced， the idea was that intermediate data gets flush to death。

Any immediate result might be too big in size。明。Me is。できな。that works。

Ark also does like isn't that the improvement of our mapping？So you had two things。 One is in Hadoop。

 you would write to local desk here because you might run a memory whereas in this case here can like it's just so massive that you're not gonna run out of memory。

 This thing can spill it just。 We'll see it in a second and actually spill a GFS cossus the Google file system。

 And then your second comment is isn't isnt what Spark is doing Spk Spark still。

 I think maintains the shuffle data on the worker nodes。 does the same thing happens off。😊，map。

Yeah it seems to be happening between green back。Which is。Obviously， I'll say this is not a。

 this is not。Like。Dreemel or even Mareduce Hadoop didn'tvent this idea of this shuffle sta。

That's distributed database is parallel do from the 80s and 90s， right。

 What's unique about BigQury and dreemel is that they explicitly do this every stage， right。

 Snowflake that has a shuffle。can do shovuffles as well， but they only use it as needed。

They do this for everything。Yes， are there disadvantages to always doing it like what if you want the data on the？

His question is， are there disadvantages of doing this。

 what if you always want data in the same worker？This is what I was saying before。

 I think I said back here。The they call it stages， they're not always pipeline breakers， though。

 In some cases， you can have the。The second stage kick off。While this stage is still running。

And you can start processing ahead of time。Right， so so that's one advantage there that you could start doing this。

 You could have this thing get fired up and start reading the data before these guys even finish。

 right， from a software engineering standpoint also， too， that now you no longer have to in in。

 embed logic of how to like。Scale up， scale down or do other optimization we'll see in a second。

At at all your workers， because now it's just like， it's just a codinator says， okay。

 I need more workers do it this way or move the data this here and there。

 And from a software engineering perspective， like the worker implications is much more simple now。

RightSo again at the end， the last stage you're doing a certain limit， one worker can handle that。

AndAs far as I know， these are just containers running in Borg， which is the precursor to Kubernetes。

So they're meant to be stateless， so these things can get killed and swapped out any time。W。

 iss that why they're doing the MM shuffle because they're supposed to be stateless and they don't want to keep them alive something stateless alive。

 It I his question is like is that why doing shuffle because these things are stateless。

 you know keep them alive。Potial， I mean it's one of the ideas， yes。But again， theres there's。

There's database query plan advantages that we can leverage if we have the sector stage。

 We'll see you in a second。So the shuffel is basically a producer consumer model。

It just a way to send the in results from one stage to the next， using again。

 using this dedicated end I'm saying this in the paper talks about like this M service is used not just for。

For Dremel， I think Drmel is the main consumer of this service。

 it's used other services within Google as well。RightSo again。

 the workers just send their output to the shuffle nodes。

 and then if the shuffle nodes can run out of space， they can spill to GFS if necessary。

 And then the it's just like a， know get and set API。

 So then the workers to the next stage is because they get get get and get more data from the shuffle nodes。

So in this case here say that all the workers are consuming data from the previous stage。

In this case here， it could be from the distributed file system， the data I'm readinging。

 or it could be from the shuffle service itself， and then they're processing the data and they're doing Nwa traffic on the outside going out。

And if I run my memory， I can always spill to the shoot file system。😊。

And then another key advantage why you want to do this is that I no longer have to do sort of the end to end communication or end to end communication between the one stage to the next because this data is going be gonna to be partitioned that I only need to send or get the data from a subset of the workers rather than sending it to all the possible workers so without the shuffle service without having to know exactly what because the coordinateordator is going to tell us here's the data you need。

 here's the shuffle is go get it from without that potentially have to pull all these guys that say do you have any data that I could be consuming。

So from that perspective， this is way more efficient in terms of communication traffic。

And then I think also too， they can pull from the Jupyter file system rather than having and go and get it from the shovle service if anything gets put to the desk。

So again， the shovel is basically just like a checkpoint in the query query plan。

And so this part is actually unique， to dremel because historically parallel distributed databases didn't do checkpoints and they weren't tolerant within the query itself。

 meaning like if I had a two hour query that was going to run and one node happens to die partly through。

 then the whole query dies and I got to restart because from the database systems perspective。

The disc was so slow that it was just not worth it to do write out in results。Whereas Hadoop。

 as he mentioned， is doing that for between every shuffle was always writing things at the local disk and replicating out things on HFS。

 and that which is really slow because but that was Google's model of like were running on cheap pizza box machines that thousands machines that could die any time whereas from the parallel database system perspective。

 it was better to design the system assuming you're running not10 dollar rack machines but like high end machines that aren't gonna crash that often so you get better performance butre not fault tolerance to if one of the node go down So the inmeory service allows them to get that fault tolerance by taking a checkpoint between the different stages of the query plan。

 but because it's an in-meory service， it's in memory， it's not gonna as slow as writing to disk。😊。

Now， with MDM E drives， maybe maybe it's less of an issue because this got really， really fast。

 But you know，10 years ago that， this obviously was a big concern。

So you get fault times because any time of node crashes， you know。

 you just get the data that you need from the inory shuffle and run the task on another service because idpotent。

 you can run it again without any side effects。 if task is running too slow because the worker node is for whatever reason slow。

 the big query guys told me that one of the big problems they faced is sometimes they'll land on to run a query on a node where another container is like doing encoding for YouTube and they can look at the traffic and actually node is YouTube and slow down the query。

 So if you have a straggleler， then you can go ahead and just kill it and assign the task to another worker that can run faster。

And then also to， as related to， it's in allowed because we have this explicit stage like， okay。

 we can take a step back， look at what our query has done so far， look what the data looks like。

 and then decide at the next stage do we need to scale up or scale down the number of workers we need to process the query。

😊，So look put these examples here。 So the workers are running。

 they' they're producing data that they're sending to the shuffle nodes。 and say。

 for whatever reason this node is just falling behind。 It can't keep up so。

If we decided to go ahead and kill it and has reassigned the task to this other worker here。

 who again， is just getting the data either from the distributed file system。

 it'll be there or from the shuffle service。Which again， will always be there。

And then once I collectged all my data in my imageory storage sorry in the shuffle storage。

 I post some information to the coredator， can look at the statistics of what the data actually looks like and then decide based on what the SLA requirements are for for the query。

 do I have too many workers and not enough workers and then can if I want to I can regenerate add more and then I don't have to move any of those data around。

😊，I just reassign what work is going to mean what data from the shuffle service。Yes。

I just want to clarify what you mean by checkpoint。

 so I think you said that the shuttle service only still。So checkpoint， meaning that yeah。

 very clear。 Yes， so it's not a checkpoint in that we think about in like the intro Davis class where I'm taking all the contents of memory I'm writing at the disk。

 Think it like it's， it's a， I don't want do word staging point because these are already called stages。

 But it's like it's a。😊，Pause is also not the right word because it's not like you're stopping anything。

 but it's a。W's another word for checkpoint。It's kind likeSa point is very sound explicit either。

 It's sorry to say again。It's still in memory。 Buts it's， it's more from。

 from a logistical standpoint that like I， I can before I start executing the next stage。

I can decide。Do I need to change my query plan or change my topology of a query plan or the number of workers I have in the subsequent stages because I've seen the data that got generated from the previous stage。

Yeah， so so checkpoint， I don't mean that like everything in here always gets written to the disk because they want to keep things in memory as possible because for intermediate results。

 who cares about like， I don't need the data beyond the query I'm trying to run right now。

 there are some papers about I reuse data structures from point to the next sort of like a mini materialized views like if I hash table I build a hash table for a join。

 kind keep that hash table around from one query to the next。They're not doing that。

 literally is just like。I get all my data in this location。

 I can then have a global view of what's going on and decide where to go next。What they do next？Yes。

 are different lakes shovel mills or in different。His question is。

 are different shuffle nodes stored where， sorry？T different flowers from。I mean。

 this is just in memory。 Think of in memory hashable。 have two Yes， Oh yeah， yeah。

 question is like are these， yes。 So think of this as like。😊，嗯。Like I produce some work。

 my task process and data， and then I have a key on the data I hash。And I modify by the number of。

Yeah。It's just think of like a。Consistent hash evil。It's a distributed file system。

Does this also exist on the same worker node， it's completely separate？

This is completely cyber service。 This is a cossus GFS。 this is their estimate。

So I guess from the perspective of the work is they don't care if it's a memory here。

How do you care about memory because you want to be hand it to the person as quickly as possible。

 whoever asked for。That's the whole point of these， these are large memory machines。

These still built on top of about。This is this is Google。 It's not S 3。

But like you say it was deadest three， that's what。it's another store， right。I thought wanted person。

 I think。So to estimate that at least metada is built on My SQL。But again， that's。For this。

 we don't care。Okay。So。I keep alluding to it， Okay， now that we have this。

Staging area in the memory shuffle store。And we now in collect statistics about what the got we we've gotten from from the previous stage。

 we start making decisions about what we want to do。 But in the very， very beginning， obviously。

 we don't have any of that information because we did some a bunch of files we may may not ever scan before。

 think the paper even says like a large percentage of the data that the gemmal queries of processing or files of the data has never seen before。

So there's no statistics， so how can we actually try to generate an optimal query plan without any of this？

They also talk about the ability to do queries against other data sources or data database systems and this is oftentimes called connectors。

 and we'll see this in other systems as we go along。

 but the idea is that I have a single logical view within Bigquery Drmel to a bunch of different disparate database systems and now when I run my query。

 I can say like go read this Postgres table and then the system is responsible for then writing the corresponding query to go against Postgres and get the data that it needs。

 but at that point。😊，If we're running a query on another date know， our query gets generated to it。

 gets converted to another query that runs another system。We have no statistics， we have nothing。

Right， the worst case scenario we we'd be doing like a select star against some other table and then do processing once we get it into our system。

 That case scenario， we， we can do some kind of predicate push down to the other system。 but again。

At this point， again， you don't have any stats。So the way Dremm is a new query optimization is a stratified approach with a rule based optimizer and a cost based optimizer that only。

That only does basic analysis of the cost basease one only does basic analysis on the data that're trying to access。

If you have actually some， some information already about it。So for the rules。

 as all the classic stuff we talked about doing predicate pushdown， primary key Far key hints。

 some very basic joint ordering， they have custom rules to constraint propagation for star schemas。

 like you could propagate maybe the constraints from a dimension table into a fact table。

Or like if you're doing。the system will detect if you have a star schema。

 so a fact table with all the dimension tables， then when it generates the stages。

 it knows to always generate the hash tables， build the hash tables on the dimension tables and then have this single pipeline when you write up the fact table all the way up and just do probes and all these hash tables so they have basic rules to check these things。

 but then they only trigger the costbased analysis and optimizations if you have some stats which they only generate if you have a materialized view。

But most of the queries are not materials use are not the common case。

 they have to deal with not having any statistics。So instead。

 to avoid any kind of bad cost amount estimates that we saw before。

 they' were going to apply adaptive query optimization techniques。

 and they're going to do this relying on that shuffle stage as a way to say， okay， stop。

 let's look at what's going on and then recalibrate as needed。

So we'll see various other techniques that are used to adaptive query optimization in snowflake and data bricks and so forth。

 They're not gonna to be as aggressive or all encompassing as some papers that we discussed。

 They're not doing plan stitching， but they're also not embedding those sort of trigger plan nodes that decide to go to this query plan versus the other。

 They're going be more like change the the number of workers they may have and maybe change the。😊。

What joint algorithm they want to use based on the data that scene， but not like to recalibrate。

 reorganize the entire query plan。So。When we can do this， because we have the shuffle。

Staging point where we can look at the data've collected And the idea is we want to fix things as we go along。

 So obviously， we've already seen haven't changed the number of workers in a stage。

 Look if I recognize that the data showing up is much larger or smaller than I anticipated。

 because maybe there's a very selective filter that I didn't anticipate was gonna throw most of the data。

 then I can scale on the number of workers that I have at the next stage。😊。

You can decide whether you want to do a shuffle or a broadcast join based on the data that shows up in the shuffle phase。

 we'll see that in a second， I also can change。They have talk about。

 You can change what what the implementation of the operator you're going to use。

 This one I don't fully understand what because they don't talk about in the paper。

 but like they have notions of like， I have a。I could have an operate implementation for small partitions or large partitions。

 I'm guessing that things like unrolling loops and things like that if you know you're only going to read a small number of data in each partition。

And then dynamic of partitioning is a way to maybe split data up more if you have a hot bucket again。

 based on the data you've seen。 I'll go through these two examples。All right。

 so say I have a query here that's going to read data from table A and table B。

 and I want to do a join。So on the very first stage。

 I'll going to have a bunch of workers read data from table A and a bunch of workers read from data from table B。

 and again， maybe there's some filter I push down in these workers that would start pruning data。

And then these workers are start submitting all the results from these scans into the shuffle stage。

I think you think of like internally， we're just build a history counter that says how much data we put into for the partitions at these two tables and say for whatever reason table A is much smaller than we anticipated so in that case here maybe we don't want to actually do the shuffle join where we're repartitioning the data on the join key we could recognize that this data is actually small small enough to fit on every single node and we can change what join want to use So again。

 say the original idea was that we were going to do we're going to hash the data and then send it to individual workers。

 they're pulling from this， but I'm showing the arrow of like is the data flow。But again。

 if this thing is super small， then I can just change it to a broadcast join where now the will every worker will go get the entire contents of table A from the shuffle service。

 and then I still do the shuffle on B， partition it up， but now when I join B with A。

 I have all the data I need to do the join locally。

The other choice is to do dominant partitioning so say that I have I'm scanning my data and say again for whatever reason partition1 is much smaller than I anticipated sorry tape partition2 is much larger than I anticipated so this thing is going to spill a disk and that's going to be slow so what I can do is as I'm running I'm passing statistics to the coordinator and then I can say okay great two new partitions。

😊，That's my biological daughter。哎， sorry。啊。So so the coordinator says， okay well。

 this partition is going to run out of space。 So now go send a message to the work and say。

 all right， anything you're to partition you're going to send a partition to。

 hash it again and send it to these two new partitions I just added。

 It's basically recursive partitioning from the grace hash joint algorithm we saw in intro class right。

😊，So then these guys keep running and they start filling up data from these two partitions。

 And then when this stage is done， I introduce a new task in my stage to reppartition that then goes from trees data。

Sorry。This is not professional，I go read the data from partition two。

 and then it just rehashhes it ands it in partition3 and four。Right。This one for the two joints。

One of them always needs to be a broadcast it's just which one you want to make Yeah。

 when doesn' it always be a broadcast？So， yeah， you can do shuffle joints just like everything gets reppartitioned on the hash key。

The alternative is to do just a broadcast one where one of them gets broadcast to everybody。

 and then you don't have you just scan locally。Actually， yeah。

 so on the stage I'm missing if you do a broadcast join。

 you don't like I do broadcast A then I don't need to do partitioning on B。

 so you go ahead and kill these workers here。😡，And then in the next days。

 they're just going to read the data from the directly and table the files。Yes。

 I'm missingarrow to draw that。Yeah， that's how you do blog。

Because the idea is like one small one you could send around everywhere and you leave the other table where it originally resided。

All right。So as I said before， they're were going to rely on an internal deative file system called Collossus。

 originally we started off with GFS， but then they switched to Collossus to do scaleallet storage。

 again， just think of it's like an object store like S3 and the other ones we've talked about and the idea is that this is an external service to the data system。

 you just let them manage all the storage for us。So the paper also talks about how they're going to rely on a file format called capacitor。

 which is internal to Google， this link here or take you to a blog article that mentions it。

 there isn't much documentation about it， it's not open source。

 but it more or less looks like OrRC and parquet， when you talk to them， the Google people， right？

One thing that the capacitor does do that Org and parquet do not do is that you can do predicate pushdown and partial query evaluation or expression evaluation within the access library itself directly on the data。

 so in S3， again you can do some pushdown of some whereca on select for select statements on the parquet files or parquet and CSV files or JSO files as well。

But it's pretty limited。 and certainly in the case of like。

 if you just access parquet through arrow files， like it decompresses everything as you're iterating of the data。

 whereas this thing can do filtering directly on compressed data without decompressing it first。

There's another file format called Art that for the YouTube parcilla system that has similar capabilities。

 but a high level this is this is just going to look like park Aorg。

Except that you can do better earlier filtering。And we saw before how they're going to handle repetition definition fields to deal with nested data。

 like think JSsonN data， but again， it's Google world so it's protocol buffers。

These file formats capacitor are going to be self describing， meaning again， just like Park Aorg。

 there'll be something in the footer that says here's the schema that you expect to see。

And then they talk about how the metadata in the schema is just stored as columnar data as well。

 so even though I may have 10，000 attributes in my file。

 I don't have to deserilize the entire thing like you would have to do in parking in org。

 I can just do do all the optimization you to look up on columnar data。

Directly on the metadata and define find the things that I'm looking for。Again， this is not。

This itself is not like mindbingly amazing， but it's certainly better than what's in parquet and what's better than an orRC in the current state of the art。

All right，The last interesting thing to talk about in this paper is similar to what we saw in the Velelloox paper where they talked about how。

Demmel was one of the big first systems Google built that brought back SQL。

 and then once SQL became in fashion again at Google。

 there's a bunch of these different random projects that people started adding their for SQL。

 but the problem is all these different internal projects have their own dialect of SQL。

And so there was effort in the late 2010s to unify this across the entire corporation by having a single SQL dialect called Google SQL that all these systems would then incorporate。

 so that way you didn't have to deal with the weird nuances of one SQL dialect to the another across the entire corporation。

 everything was always the same。A。So， the。This， again， in the Velox world。

 they talked about how like theres all these like substrate functions。

 And everyone was re implementinging the wheel over and over again。

 and Vx cement meant to standardize those implications。 the same idea here。

So Google SQL itself is not open source， but there's an open source variant of it called Zeta SqL。

 Who here has ever heard of Zeta SQL。Nobody。 Okay， so this thing here supposed to be the open source version of this。

 And the idea was like， okay， yeah， here's， you know， people could start building。

ZtasQL compatible database systems。That would then smell a lot like Google SQL。

 So like if you're comfortable with running on where this one off system based on Zeta SQL。

 you can easily transition your application over to BigQuery or Dremmel Spner as well。

So this thing is basically， as far as I can tell， it's dead， like like there's new updates。

There's some updated like a month ago on Github。 But like it says at the bottom。

 it's not officially supported by Google。 There's much of pull requests and issues that aren't being responded to or answered。

 right， So as far as I can tell， this thing is dead。 Like。

 and there's only one database I know that actually supports statussqL。 It's called Apache beam。

 which is like a stream processing system， but nobody else is actually using this。Am。And to me。

 this is interesting because。Again， Google。Wasaz or Google still is huge。

 Google still is very influential in the tech community。 But if they're putting out a Sal dialect。

 they say this is what the standard should be。No one follows it this shows you。

That the sequL marketplace is so diverse and fractured that like no one company。

 even a major tech giant can sort of bend bend the physics or bend the world to the whims。

The last time this was actually done was IBM， IBM came out in 82，83 and said， okay。

 we're putting out a new data system。 and it' can be based on SQL， SQLs the standard。

 and everyone sort of got line and follow along and SQL became what it is today。

 But now things are so diverse that I don't think you could ever do that again。

 The closest you can get to I think a true， I mean， there's the SQL standard of the IoQL standard。

 But as I said， nobody actually follows that。 The closest you can get to a dialect that is based on is Postgres。

😊，Because everyone takes the Postgres parsseel of the grammar file and uses it like DDB did this。

 a bunch of other systems did this。Googleoogle， you know。A。I'm not saying they tried and failed but。

You， no's means that as equal。O。So。There's， again， since the 2011 paper， as I mentioned。

 there's a bunch of systems that have come out that are。Some cases， like wholesale。

 they even't claim。 it's a copy off of the architecture。

 but other ones is's more likely to say that it's inspired。 So I want to go through these four here。

 And then what's also interesting about this is that there in the last three or four years。

 there are now separate shuffle as a service components or architectures or systems that you you could then use。

That maybe don't exactly replicate all the capabilities of the dremels in memory shuffle service。

 certainly not using hardware acceleration， but now that again。

 there's of separate projects that do nothing but shuffles。Which I think is kind of cool。

And so we'll talk about the ceboard one from Alibaba because that ones。

 that one's the farthest along uniform and， in the Uber one。😊，I mean。

 I'm sure they're still using this。 Uni is still and again， Apache incubator project。 So so early。

 But far as now， this this is the big one。So again， let me go through each of these systems。

 and I'll cover this one and we'll finish up and go out for the。For the eclipse。Alright。

 Apache drill is， again， this one。Claed to be can straight up copy。

 like Drreemel is a drill Apache drill， right， No imagination there。

So this started as a right after the Dr paper came out as a way to build up a query engine on top of HFS。

 And this is started at a tech company called Map R。 was。In the late 20 early 2010。

 there was three major Hadoop companies or mapR companies， there was Clouddera。

 Hortonworks and MapPr。Clauda and Horwork are based on the open source version。 Hadoop， the Java1。

 Mapr had their own proprietary sleep health version。 that was meant to be faster。

 And so Mar built a。You know， built， built started building Apache drill。 actually。

 this was is in Java。So what's interesting about this is that。

They are going to do query compilation using this thing called Genino。

 which is basically it's some kind of embedded Java compiler where you can give it Java code and it converts it in process。

So this project is not dead， but certainly the number of commits and engagement and usage of it has gone down。

 Ma produceuce or sorry Map R was on the market a couple of times。

 finally got acquired for not much by HPE and the HP announced in 2020。

 they're basically stopping all the development on this。

 At least HPE is not paying for the developers to work on this。

 but other people are still still working on it。 So I would say that this is not。You know。

 there's better alternatives now， especially in the open source world。 But， you know。

 this was the first one that sort of came out directly after the gremel paper came out。

 Did do the shuff the memory shuff。 I think this one did in memory shovle， yes。Again。

 with not the hardware。The next one is Presto Db。This was started at Facebook。

 I wouldn't say this is like directly inspired by Drreemmel because I think they were working on this。

They were already working this when the dremal paper came out， but they were building。

 Facebook was building this to replace hive， which was a。Which is a way to do SQL on top of MaRduce。

 it would take your SQL query and then convert it literally into mapRuce Java jobs and run those and obviously that would be super slow because MaRduce was slow。

 But the idea again， same motivation that they have a bunch of files， certain data lakes。

 in this case HtT ofs where I think Facebook has their own internal distributed file system and they had a way to do a bunch of connectors。

 different storage systems， data systems， similar to Dremel。😊，And。few years ago。

 Facebook announced that they're getting off of the Java based runtime engine and they're switching everything everything。

 the Vel The Velox paper talks about this project called Pro Prostiimo。

 this is one of the targets they were building VelX for to replace the Java engine with the Ss engine in Vellog。

There's also another version of Presto called Trino previously called Presto SQL。

 So the first version of the project was called Presto。 then it was called Presto DB。

 and then there was a fork called Presto SQL that then I got renamed a Trino and this was done by the Starbust guys that came out of。

😊，At a vi。Carre data。No， they by asterada they hard by astroadata and astraada acquired。

As if the project called Hadoop DB， there was a company called Hadapt。

dap got acquired by astraada and then astraada got acquired by Ter data。

 And then Ter data spun out this as Starbust。 There we go。

 And so they didn't like how Facebook wouldn't give up the control of the source code。

 Like hive came out of Facebook。 and that's Apache project。 For whatever reason。

 Presto was still not Apache project。 And it wasn't Facebook wasn't giving up control。

 So these guys forked it renamed it as Trino。 And I think this went to the cloud。😊。

Computing foundation。 and then Facebook then converted。

 gave up source control and gave Presto D B to the Linux computing foundation。

 right to not Apache with these these other similar kind of foundations。

 So what's interesting about this in Presto or Presto D B。

 Facebook is again trying to get rid of the Java stuff and place of vox。 Petrino guys。

 they're very explicit saying they don't want to give up Java they have a blog article or they had a podcast a year or two ago。

 And they talk about here is explicitly that like they rather spend the time trying to make。😊。

The the query optimizer better than than try to spend a much engineering effort to replace the executionion engine with something like Vello or even data fusion。

I hive the query engine or is that hive is the query engine。

 the same way the Drmel ofs query engine pressors query engine train as the query engine？

So how are Preston High connected？The question is， why， how is Presto hive connection。

 Facebook first built hive because they were like， okay。

 they had all all this map produced stuff infrastructure。 map produces slow。

 And people are writing Java code。 You're running queries instead of SQL。 So then they build hive。

 which is a front end query engine that can take your SQL query and convert it to a map produced job and run that。

😊，That's slow because that produces in the Hadoop model slow。 So then they said， okay。

 let's get to that and let's have build keep HFS over the should file system and let's build a query engine that takes SQL and can run the actual query plan as directly as SQL。

 That's presto。😊，Simmon to Drreemel。And that one also has the membership shop。Actually， Presto。

 I don't know。I just look at better， I don't know。Good question。Alright， another project， again。

That was definitely definitely inspired by Dremmel。

 which is a thing called Eala that came out at Cloudderra。And so。This。

 this was founded by people that Cloudderra hired from Google， who didn't work on Drmel。

 would used it and were inspired by it。 But， the key thing that they did。😊。

That they didn't that an Aala did， I think it still works this way that。

Rather than have the the query engine the workers pull the data from the shared storage and then do the processing。

 you know， on on the worker nodes。They want to do more。

 they want to do more predicate pushdown than you can do on S3 or GFS at the time。

 So what they would do is that on the straight file system。

 you actually install a little execution engine down there。And I think this is all written in Java。

 So this is like the JVM。 So the work could then do predicate pushdown。Another another pushdowns。

 And that would run that part of the query directly where the data was being stored。

 So this was HDFS at the time。 So then like on your HS node。

 you also install this Apo Xr node who could then take the queries and process the data locally before sending it back。

So that's not a true disaggregated storage， the way that we've been talking about the entire semester。

 but they did this because they weren't be able to do the predicate push down。

I think they also did query compilation， but they did they compiled it actually take back this was not Java。

 this was in C++， and I think they were doing like predicate compilation on like where causes and they could do that down there。

😊，And like CSV parsing and other things。We'll see more about Aalla next class when we talk about databricks。

Right， because。Cloud Airero was the big big Ma Reduce company。

 and they were pushing imp pollen very heavily。 but then everyone started asking for Spk。

So they also had to start supporting Spark， but then sparks like， hey。

 let's add SQL and Cloudder didn't like that because they want to keep able to buy in Paa。😊。

And then the Spk guys do this one trick， we'll see you next class of how they got SQL into Spark。

Basically， they'd embedded it instead of having being a middleware。

Daabbricks basically destroyed cloud air，We'll discuss this in more next class。

Dremeo is probably the of all the open source ones we've talked about。Again。

 directly inspired by Dremel。And actually is backed by a VC backed company。

 actually founded by Seme alum， I think he did his master's here。

 but he wasn't my student as far as I know。As I said before。

 they're doing all the things that we talked about very similar in Drel。

 But one of the things that we're going to do to speed things up is direct rep to access what they call reflections。

 But as far as we can tell， they're just materialized views。 they're doing on Java based codegen。

 I think for the entire query， not just the warehouse causes and vectorization。

 as we talked about before。😊，All rightAnd then the last one is Apache Clibron Sallibor。 This again。

 just shuffle as a service。 came out of Alibaba。 The idea is that in Spar and Fllink。

 you can actually specify what shuffle service you want。

 Like there's a default built in one where the worker nodes send the data directly know to other worker nodes。

 But you can actually have use this as a standone service as the intermediary。

 And it can do all the things that we talked about so far， like。😊。

I can spill a disk when I run out of memory， they can actually do block compression of the data when they put it down the disk and so forth。

 and again it's just a key value store that's fault tolerant。

 And I think this one is using raft internally， there's another one the uniform that's based on the suitookeeper it's just a key value store but is only meant for moving data back and forth between the different stages of queries。

😊，All right， so to finish up。Dreel is is very， very influential， as I said。

 in the combination of vector wise for like the single node query processing。Plus。

 the Drmel for like overall architecture。 not everyone does the shuffle， as we'll see go along with。

 I think the combination of these two things gives you what what what we call a a modern lakehouse。

 And although the shuffle stuff seemsful wasteful， it is actually gonna make things better because I keep。

😊，I can keep as much memory as much as possible， I can disconnect the warm workers at one stage or the next right there are a bunch of advantages to this。

 not just performance， also from engineering because it simplifies the implementation of all the workers。

And this is another good example， too of。😊，Sort of the projects you guys are working on based on。

 it's like by decoupling the system architecture and and having one group just spend as much time to optimize as one piece that then can be taken advantage of by other parts of the system。

 I think that's the right way， to build a modern cloud native system today。Okay。Alright， again。

 next class， we'll talk about sparkar Sple and photon。

 This is going to be different than the Drramo paper because the Drmo paper is the entire system。😊。

The， the photon you're gonna to see。 It's gonna look like velelloox， right。

 Its be something you embed inside the JVM of for this the spark runtime rather than。

Being in a sustainable system， okay。

![](img/1a5954df15769f59c1cfbeef9fd601e7_5.png)

All right， so that's stop now and let's go and check out the clips。



![](img/1a5954df15769f59c1cfbeef9fd601e7_7.png)

St and six packs on the table and I'm able to see saying I on way。

No short put the cross you know what got them I take off the cat but first I' tap on the bottom。

 go about three in the freezer so I can kill it， cat full with the bottle baby don feeling it。

 co they nice says the pain nice way you can get down with the guys in wild head。

Take back the pack of drugs， itvo to some love to T to the drugss。

 Billy De is the silly takes to tell weak Go， be a man and get a can of faint。

