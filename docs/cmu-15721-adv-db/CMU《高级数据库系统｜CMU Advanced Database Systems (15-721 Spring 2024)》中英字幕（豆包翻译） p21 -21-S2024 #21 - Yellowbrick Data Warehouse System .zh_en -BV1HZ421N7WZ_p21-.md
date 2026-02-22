# CMU《高级数据库系统｜CMU Advanced Database Systems (15-721 Spring 2024)》中英字幕（豆包翻译） p21 -21-S2024 #21 - Yellowbrick Data Warehouse System .zh_en -BV1HZ421N7WZ_p21-

🎼Carnegie Mellon University's advanced database systems course is filmed in front of a live studio audience。

😊。

![](img/b466eae44cb6a69937df0fea4bf1b657_1.png)

🎼。🎼All right， so today we're gonna talk about yellow brick。 And to me， this is a very。

 very fascinating system。 you know I recognize that they're not a really wellknow company。 And I。

 you might come give a talk two years ago。 And then I told the CO。

 like you guys got to write a paper of all this great stuff。

 end up being the side of paper you guys are reading。 And it just， it's wild， right。

 It does a bunch of stuff that nobody else does。 And I think it's a good way to think about what。

 you know。😊，Like for you guys to say oh like yeah you can just write your own PCIE driver right like insane things like that so from a assistant system perspective I think it is super fascinating but before we jump into that again for the administrative stuff。

 this is last week classes again the final presentations for the projects will be next Thursday in this room and 9am and then if you go to this post Piazza that I put out last night there's a poll there select what you want for breakfast on Thursday and there'll be information a link to the course website that says what's expected or what the deliverables are required for when you show up on that day okay。



![](img/b466eae44cb6a69937df0fea4bf1b657_3.png)

And the presentation will be 10 minutes。as those we look at what a lighthearted thing meant to have fun。

 And then the final exam， I'll give it out on class this Wednesday。

 and then it'll be do the same day on the final presentation。😊。

I haven't decided whether I should do show with a PDF or email me PDF or print it out。

'll probably do PDFs， but I'll clarify on Wednesday okay。Any questions about any of us？Yes。Quest is。

 how long is the final exam？诶啊。It's take home， right。So if you do it why watching TV。

 maybe takes longer， not。But it's， it's not， its， again， it's not questions like。

 what does this paper say， What does that paper say， because that's like。

 that's just rope memorization。 It's really internalizing the the various things we've talked about and then seeing it in different contexts and。

 and then applying to to new situations。 That's what I care about。We， any other questions。All right。

 so。Right， mind our last class， last Wednesday， we talked about D D B， which is a fascinating system。

 Its being widely used， but it's obviously not a。Sort of scale out Oap system as we talked about this entire semester。

 And then someone came up someone suggested， oh， can't they on the mother duck stuff。

 can't they take the fragments and scale it out across multiple nodes again。

 looking back on Mother duck， as far as they can tell， they're not doing that。

 they rather scale vertically than horizontally in for D D running on the cloud。All right。

 so today to sort of lead us out into the discussion about yellow brickrick。

 we haven't really talked about specialized hardware for databases。

 but there are databases that are run on GPUs， databases that are run AGAs。

 yellowbrick is actually one of them and then we'll see in Redshift next week。

 they'll have their own because it's Amazon， they fed their own hardware are called Aqua where they have custom silicon that they're using。

 at least I think they've discontinued it though， to accelerate queries and we'll see how they're doing that。

 but there's a long history for databases going back to the 1970s where vendors have tried to rely on hardware accelerators to make the database system go faster。

These are in the 1970s and80s， these were called data use machines。 Think of like again。

 custom fab and custom chips to make queries run faster or network communication run faster。

 The challenge in the 1980s was that if you built custom hardware by the time you designed it fab and put it out for customers。

 the next version of the motortor is 60000 or Intel's next CPU came out and all the benefits you got from custom hardware were defeated And so people haven't really tried to custom other than the major cloud vendors。

 there's not a lot of people fabing custom hardware today。

 typically you see people leveraging Fgas and GPUs Com hardware accelerators。

But another way to PO sort put together datas and sell them on Prem are what are called appliances。

 and basically think of like you're buying rack units where even though maybe using off thes shelf hardware。

 like SSDs or CPUUs and so forth， but it's set up in tune and configure such a way that the data has been designed to be optimized for it。

So as a bunch of vendors that'll sell you big rack units that look like this。

 Oracle is probably the strongest one in this game with something like Exadata or their data's appliance。

Allright， and again， it's like you buy the hardware from them。

 and the data system has been optimized and tuned specifically for the machines you're running one versus like just downloading the binary。

 setting up and hope you hope you configure it correctly on the。whatever however you're running on。

So this is how yellow brick started right yellow brickrick was an appliance， so this is from the TTO。

 the author of the paper you guys read， he gave a talk with us CMU a few years ago and he's had a screenshot here of like this is the yellow brick appliance。

 like obviously the things with yellow so a bunch of SSDs and bunch of CPU and then the system was designed specifically around it。

😊，And one of the things they did that was really fascinating is again。

 it wasn't just off the shelf or it was all off the shelf hardware。

 but it wasn't just like CPU disk and memory， they actually used FPGA accelerations built inside of it to do things like。

do hashing for balloon filters， do decompression of the data coming off the disk。

To do transposing from the data from rows and columns。so in the paper you guys read。

 that was the cloud version。And the reason why I'm bringing this up like。

 I think you can still buy this onprem hardware， this appliance from Yelbrick。

 the reason why I'm bringing this up because the motivation of the paper of why they did all the insane engineering stuff that they did was they were trying to transition their system from an on-prem custom hardware to a cloud setting and still get all the benefits of acceleration that they were getting when they were running their own silicon。

So that's the background of what yellow brick is。 So even though again。

 the company and the product started in 2014， I think the cloud version came out in 202021。So again。

 I find this system very fascinating to me like when I first started learning about it， yellow brick。

 when they came out of stealth， it reminded me also like when I first saw a clickhouse。

 when you read the things that they were like oh， we do this。

 this and this and this and this and it's like this is insane。

 They're doing so many different things。 And that was back when they were just doing FPGA stuff and then when the cloud version came out and they're like。

 oh yeah， we're doing kernel bypass with this and custom device drivers for that， like that's insane。

 you almost wonder sometimes whether it's actually true and then you meet the people understand what's actually going on and then you see that it is it is actually all real。

And it's unclear whether the。The other major data spenders， specifically the Amazons， the oracles。

 the Microsoft， whether they're doing the same kind of low level systems optimizations that Yelbrick is doing for some things I know that Microsoft makes heavy use of running FGs or down on the NIs to do filtering and other things but again。

 I don't know whether anybody else is doing the amount of work that they've done。

 and certainly it's risky like if're like a brand new database startup to say hey。

 I'm gonna to write PCIE drivers is is not something I would actually recommend。

 but they pulled it off。All right， so it's an Oab database system。😊。

That was originally designed for a sort of classic shared nothing architecture。

 And then when they transition to the cloud， they obviously had to switch to a shared disk architecture and they're going to deploy a clientside caching mechanism thats similar to what we saw in snowflake So everythings in C slot。

 it started off as a fork Postgress 9。5。 So they're still going to use the Postgres front end for the ODBC JBC wire protocol still going to use the Postgres parser and the catalog and basically handle all the incoming SQL queries。

 But then once you get past the the parser they still use remnants of the Postgres query optimizer。

 but they're going to inject their their own optimization passes in there to handle yellow brick specific things。

And then they hand it off to the compiler， we'll get to that in a second。

So the other thing about it in this paper is that， and we sort of speculated it before when we talked about Drremel or or snowflake。

 like， oh， I wonder if they're using Kubernetes or how they're actually running the actual worker knows themselves。

 they're heavily based on Kubernetes。 like all the components in running inside of the system are going to be set up as services running。

In in Kubernetes， and again the paper talks about how they were surprised to see that even though they were running containers。

 they still couldn have the low level control over the system hardware that do the kind of optimizations that they want to do like that was still all available to them。

 even though it was running in containers。So again。

 everything we'll talk about today will be the cloud version。

 So we're not going to talk about the FG。 We're not going to talk about the other the custom stuff they were doing on the。

Well in the onprem version， it just be all about the cloud。Alright， so here's again。

 high level overview of the key aspects of it going similar to the taxonomy we've used for the other systems we've talked about so far。

 So as I said， startup off has shared nothing， but now it's a shared disk system which is got go to compute and storage。

 They going to be a pushbased vectorized query processing。

 They're going to make heavy use or the entirely doing cogenerational query compilation using the translation method we talked about with highQ So they're gonna to take the query plan and convert it into C plus code and they go ahead and compile that。

They're to do compute side caching similar to we saw in snowflake。

 they're going to have a separate row and column storage opponent。

 and this has allowed them to do ingestion of new rights in a row ored manner and then the background process is going to convert them into a tax columnar format。

The resort merge joins， hash joins， they also support nest of loop joins。 And as I said。

 they're going to rely heavily still on the Postcode query optimizer but impose or install their own additional optimization passes for。

You know， for。You know， for for yellow brick stuff。 And， and then again。

 I can say this multiple times that faster， like cocaine level and seeing system engineering from optimizations。

So we're going to talk about all of these， but I think these two ones are probably the most interesting ones。

 least the ones we can talk about the most for most publicly available。All right。

 so the nomenclature they're going to use say that there will be a data warehouse instance。

 and that'll be the the front end service of the。The database system that's going to manage all the sort of have the complete purview of the worker nodes and other additional services running for single customer。

So the front end piece is going to have again that portion of Postgres that's going to take incoming connections。

 do the parsing， the plan， the optimization， it also is where they're going to run the roast or portion of the system。

But then they're still going to use Postgs actually for the catalog。

 They're just going use PG catalog inside of the Postgs keep track of where what data is available how to map the shards to the files to to different nodes。

 They're gonna make heavy use of caching for this and other nodes because the hit up PG catalog for every single time we want to do a request would be too slow。

And for transaction management as well， which we're not really talk about。

 but they try to mimic of trying to follow Postgre's style at NCC to do transactions。

The worker nodes again are going to be single containers and as he describes it。

 they're pretty lightweight or dumb， they' just given the task of here's the Kaal query and they go ahead and run it and know how to move the data back and forth between the hardware and the different nodes。

But they're always going to maintain their own local cache using MVME drives to write things out as needed if they have to spill to it。

 and we'll talk about that in a second and then there' are separate additional services that are running background tasks or maintenance tasks。

 leave for compilation， they run analyze in these background tasks， bulk loading。

 they actually do a bypass of the row store so you can just take large filess and dump them directly to the column store。

So the high level architecture looks like this。😡，Again。

 so this is the front end and then get the worker notes and then the object store is just S3 or whatever Azure has。

Quier shows up， it's going to go through this Postgre front layer again do all the parsing planning there。

 and then it's going to hand things off to the scheduler and the compiler service。

 we'll talk about each of these in a second， but they have a centralized scheduler that then's going to hand out the task to the different worker nodes and then every 100 milliseconds they're going to coordinate and synchronize and say what task should we work on next？

And these guys are all running as co routines， compiler service we'll see in a second and it's just converting the query plan into see sauce and go ahead and compile it。

 but they'll do some tricks to make this run faster in parallel with LLVM。

Schedule hands out the task to the worker nodes， assuming that the worker nodes， caches are empty。

 if they need any data that go out to the opt store and get it stored in its local cache。

 they'll do an approximate version of LRUK， which we'll cover in a second to decide when to evict things from memory or things from the cache。

And then they can also move data back and forth between different worker nodes。And then as I said。

 if you're doing a bulk bulk loading of like I have terabytes of files。

 I don't want to go through the row store and then have it get compactive to the object store。

 you can have this bulkloader service just right directly out to the object store all in a transactional manner。

Yes， so the paper says that yellow brick is assured shirt and nothing to do。Yeah。

 that part's a little bit confusing。Again， historically， it was a shared nothing in the system。And。

I think they're incorrect because these are caches， right。

 the primary location of the database at rest is over here。Now， the ignoring the row store。

 but doesn't really make a difference。 And then they talk about how， okay， well。

 any time I need to get data， I go fetch it from the object store， right， They're not So it's like a。

It's a right back cache instead right through cache， meaning I get data。

 and I want to get it to the object store。 and then I pull in and then I fill my caches as needed when I run queries。

 If it was shared nothing， then I would not never have to do that because I would always populate this stuff here I it would the decision be that we take the data from the while the queries running it never goes back they'll use as like intermediate。

So his comment is like。Is it the case where they will never have like。

 is it the case that they have to spill a disk if they run out of disk space on the worker nodes。

 then they don't write to the opt store as far as I can know from the paper。

 they don't write it to the Op store right， And they'll use back pressure to say， okay。

 we can't process this as fast as possible。 So everyone sort of slows down that way。Again， like。

Historically， it was a shared nothing system when it was on Prem。

 what they described in the paper smells like snowflake and snowflake is a shared disk system。

So I think that's incorrect。so again， the insane parts of here for these guys is that all this these lines are drawing here。

 this all been custom stuff， either custom drivers or custom API limitations or custom protocols to talk either internally the client between the work nodes and also within the object store itself。

But the， the， the outbound stuff going back to the client。

That's just going to be the regular GBC wire protocol， ODBC wire protocol that postgs has。

So I've said some of this already， they're going to be heavily based on Kubernetes。

 so all the different pieces that I'm showing here， they're going to run as separate microservices。

You know。When I think a microserv， I think that something like a Lambda function comes in and comes out。

 like does some processing goes away。 these things are always running， so。

 but they're using the term microservices， basically they've broken up and things are running separately。

And so they're going to leverage Kubernetes to do all the state management of like what machines are up。

 when one goes down， how to do failover， how to provision new machines。

 all of that is going to be done through Kubernetes。

 So that's sort of a control plane the backbone of the system itself。

They don't write from scratch the way like Snowflake and others had to do。

 there's going to leverage Kubernetes for all of us。嗯。And as far as I know， I mean。

 I'm not saying they're the only system running Kubernetes。

 but there's only these paper that publicly talks about how they're using Kubernetes to organize a scale out system like this。

But if you already using Kubernetes。It's a painting asset set up。

And so they don't want you to have to write the helm chart to figure out how how to solve the positives and whatnot。

 so they're going to hide all of the Kubernetes operations behind SQL。

 which is fantastic so you can call create Cu or create Inense or whatever and not all done through SQL and then it's translating that into the Kubernetes commands to apply the changes。

😊，It's nice， obviously not groundbreakingly but it's a quality of life feature that I like。

The other thing we're going to do that sort of goes against the way you're expected to run or operate Kubernetes is that when the worker pods come up。

 they want to make sure they have a one to one mapping between a worker pod and a worker node because when a worker pod lands on the node。

 they want to take over everything。And again， this is why I'm saying it's not truly like a microservice where。

Because this worker po it's going to allocate all the memory that it wants and you want to run forever because you don't want to have the spin up cost of starting stopping a worker pod over and over again。

And again， the paper talks about how。They thought it be trouble。

 They have trouble with the worker node， the worker pod， taking control of all the hardware。

 at least through the container。 And that seemed to work。

 But if you had two containers running at the same node。

 they need conflict and trying to get the hardware。 And that would break things。

 So that's why they have a 1，1 mapping for the。For the worker po and the worker node。

All right so the execution engine is the pushbased model we've talked about before。

 they're doing vectorized query processing when they're operating on columnbinar data， but as I said。

 in some cases， they're actually going to convert things into row store or row orient data。

 essentially doing early materialization in some cases。

 so all the scans we vectorize based on columnbinar data， but then if you feed that up into a join。

 they're going to convert it to a row store， they call it a transpose operator。

 they're going to they they inject a transpose operator in the query plant to convert it before you pass it up into the hash joint。

And likewise， when they send data from one vote node to the next。

 they're going to convert things into aoriented manner because they want to send smaller chunks to make sure that the。

The data you're sending over all sits in L3 cache on the other side。

 and you can process things very efficiently。 And then when。

 when the overarching themes willll see over and over again is that the goal of of the system that they designed it that when you want everything be sitting in L3 as much as possible。

Right， it's， you know， it's not like when we talk about other systems like， oh， yeah， you know。

 keep things in memory， don't go to dis。 These guys are insane。 They want to keep everything in L 3。

 And so that's why they're doing all the custom optimizations that they're doing。

 And if architected the system says that。By converting to a row or。

 you know that all the data you can need to process a single tu bowl before you can move on to the next two bowl is going to sit in L3。

So as you said before， they're going to do holistic query compilation。

 doing source source translation of generating the C plus loss。

And this has be done through a separate service。Now it was debating whether we should we read Redshift first versus this paper because RedSshift is basically going to do the same thing。

 right， they're going to do Cogen into C+ loss， and they're going to have a separate service that's compiler service that you send queries to and then you get back the binary。

But yet， I wanted to cover。I wanted to cover the yellow book optimizations first before we talk about redshift。

So， so this idea is not novel。 again， what they're doing as a standalone service。

 This this is what Redship is going to do。 But one of the things that's interesting about this is that they talk about if you have a query plan and use generate you know。

 plan fragment as like a giant， just one giant file， then the。

Core compiler component inside L of VM is single threading like you can compile multiple files at the same。

 same time in parallel。 But within a single thread， it can only compile a single， you know。

 single piece of code。 So they're going to artificially break up a the。

Qury plan into different fragments， let them be compiled separately into in multiple threads and then going stitch things back together doing just dynamic linking。

 It's similar to the plan stitching itself we talked about when we talk about adapt depth of query optimization。

 they're sort of breaking things up into those smaller chunks。That may not be a single pipeline。

 but again， you can pile those in parallel and then put things back together。

The compile of is also going to maintain a cache so that if they recognize that I've seen this fragment before。

 I have a cache version of it， and it's the right version of the runtime of the database system and the right hardware and any other depend you may have。

 then it can reuse that and give you that shared object instead of compiling from scratch。Again。

 we'll see this again in redshift。 Redshifts insane。 They have a。It's not the same。

 but it' it's amazing。 they have a cache for your database。

 So if they see the same prank over and over again for within your database， they'll reuse that。

 But they also have a shared cache across the entire fleet。

So like if some other customer has a table that has an integer column and a string column that you know。

 and then you're doing a lesson than on it。Their query， you know。

 they might have a Kaala version of a plan fragment that processes that data。

 and you have the same basic layout。 The names of the top columns may be different。

 or the distribution might be different， but who cares like the actual data itself。

 the underlying physical representation of the data is the same so I can reuse that plan cache。

So we'll talk about what Amazon does in next class。I think in this version。

 because they don't talk about whether they can cash things across different customers。

 I think everything's still isolated to a single customer。

Amazon will be more aggressive in reusing things。All right。

 so the optimizer itself again they're just going to rely on the Postgres stratified optimizer。

 a bunch of rules to do predicate pushdown and other optimizations and rewriting。

 then you switch into the dynamic programming section where they're doing the join ordering and then at least in Postgres they have pop out of that they do some final cleanup but they're going to inject they're going to have their own cost model extensions to Postgres and some additional passes they'll do to do additional optimizations based on again the yellowel bricks architecture and one of the things they're going to introduce is more aggressive file filtering or data file filtering from the object store。

By doing lookups and Zoom maps and other things like that。

 identifying these are the files I know I never need to read because my predant can never be satisfied。

The other thing， though， that's going to be different than all the other systems we' talked about before is that。

They're gonna to have their own managed service or start to managed storage。

 So unlike in Drreel and data bricks and snowflake， at least snowflake， you know。

 once you add iceberg， they are not， they are not going to let you just have a bunch of arbitrary files and S3 and then write whatever SQL queries you on top of them。

 You have to bulk load them import them into the yellow brick system。And be managed by Yelbrick。

 And at that point， Yelbrick can then run analyze on it and collect statistics as if it was a regular database system。

Not a lakehouse。Okay， so the current version can't take arbitrary files in your data lake。

 everything's got to be loaded into the system， then at which point you can collect statistics now when you're bulklet too you can collect some basic things like know some Zoom maps and whatnot。

 but they'll do like a heavyweight analyze pass。like a single node system to go get histograms。

 heavy hitter listings， they make heavy use of hyperlo log， number null values， or sync values。

 all these things they're going to maintain， store that in the PostGres catalog on the front end service。

 and then their percentage to the query optimizer will be able to use them in their cost model estimates。

Again， that's different than everything we've seen so far。 And as far as I can tell。

 they don't have any the adaptive optimizations that we've seen in Drreemmel and snowflake and Databricks。

They're going to assume everything is going to be whatever the plan that you get out in the query optimizeizer。

 that's it。And they're not going to adapt them the fly。

They' near the classic opposition we've seen many times before。

 they'll do the sideways information passing for the balloon filters on the build side of a hash join。

 so as I'm building a hashable we build a balloon filter and then I can send that over on the probe side to do early filtering that way。

😊，So that part again， other than the。From a non lakehouse system。

 this is sort of a textbook implementation of how to collect statistics in your query optimizeizer。

I think I asked them too when they gave a talk of like。

And sort of related to what you were bringing up， I was like， well。

 how good is your  query optimizer and how often do you make changes because。

There's things that's missing because the Postco optimizer doesn't know about yellow brick stuff versus like the Postco optimizer just does something stupid and you got to add rules in or add changes to the optimizer's logic to account for to avoid bad plans。

And they mentioned that what they're doing is basically adding hard coded rules per customer。

 that's their ideal situation。And that they， as far as I know。

 they haven't pushed any changes back into the Posts mainline branch。Again。

 when you're a small startup。Actually I don't know how big they are， medium sized startup。

 pick and choose your battles， and they chose to optimize in low level OS stuff versus the query optimizer。

 although again， they claim that this is what they're focusing on now the most。

Now that they've gotten sort of the OS level stuff taken care of。All right so。TheAs I said before。

 the yellow brick， even though it's a shared disk system。

It is it is going to have its own managed storage， so you tell it here's my S3 bucket so I can store stuff and then yellow bricks is going to be in charge of reading writing data into those files and then they're going to be using their own proprietary format。

I know they're doing dictionary coding， I don't know the other additional optimizations that they're doing。

And when you load a file or sorry load a table and adding data to it。

 you can specify the sharding key or the partitioning key， in anticipation of doing joins。

 you're also going do local sorting attributes so within the file itself you can have them sorted on a single column。

 so they won't be globally sorted across all the files， but within the file it'll be sorted。

So the files themselves they roughly about 100gabytes with two megabyte chunks。

 and this two megabyte number is going to be special for us later on。

Keep that in the back of your mind so you sort of think of like the row groups are two megabytes for these guys。

They as I said， they do support bulk loading， parquet files。

 I don't think they support orC or other formats， but you can't。they can't take。They how it says。

 they can't support all possible variations of the things you can do in parquet。 Like I know they。

 they claim they can't do nested data。 They say they can't break up your Json information and store that as columns that we saw in Dremmel。

 And there' are certain data types that they don't support。

Again there's going to be this row store which the original version was just Postgres so when you inserted new data。

 it landed in this Postgres version， they were running in the front end， that turned too slow。

 they got rid of that and now they had their own customer row store and then every so often the background task is going to go through。

 pull things out of the row store， put it into columnar format and then write that out to S3。

They also allow you to do transactional updates on the column story data as well。

 which is something we haven't really seen in the other systems。

 this is what iceberg and Hoy can handle for you in the front as well as Delta Lake or that's the database one like you can do update insert update deletes on those data if you use the frontends。

 but in yellow brick you can go directly and call insert update delete and then they maintain basically a log record of like here's all the changes that were made to change to a data file so that when you read it potentially need to skip and then periodically they'll go through and do compaction of combined multiplemod files together and try to。

Purnt out the old data and reduce it down to smaller false sauces。

So the technique they're going to use to assign files to workers is going to be different than what we saw in Snowflake。

 recall that Snowflake was using consistent hashing basically the ring approach to figure out what file belongs to one worker node for the local cache。

 and then when the number a worker change node goes down or you add a new node。

 you could reorganize the mapping of files to worker nodes without having to reshuffle everything as you normally with sort of naive hashing。

So yellowel brick is going to use another technique that's very similar called rendezvous hashing。

 Who here is， I don't think we do they teach rendezvous hashing in distributed areas or distributed systems。

Okay。It's a variation of consistent hashing that actually came out before。 It's a lot simpler。

It just consistent hashing is more wellknow more popular than Rndezvhing。

 But there are some systems like Druid or patchy Iite。

 which is a key value store and memory store that do use this。 The idea is really simple。

 The basic the basic idea is like you have you have whatever you want to hash。

 So say for us the files like the file name。 and then you you have the worker node you you want to assign them to。

So all you need to do is just hash each file by some key multiple times and then come up with a rank list of the assignment of a file to a worker and then you just pick whatever one has comes first based on some we so say I have three files and say I have three workers。

So I'll take the first file here， and as let's say。

 I pick the file name and then I append the worker the worker identifier to it， and I hash that。

 and I'm going come up with some number。Right。ButAgain。

 somehow the number corresponds to how important it is for this file to be on this worker or it to be random。

So now I have a rank list of the workers and then I end up picking whatever the first one is。

 and then I do the same thing where the other ones come up they rank rank ordering。

 and then the first one is the one I'm going to assign them to。Right。So for this。

 I don't need to maintain any sort of。Immediate global state or routing information between the different nodes。

 because long as everyone has the same hash function， the same hashing protocol。

 everyone compute this。 Yes Why is different。Better than just hashing。

Paching the file name of then like the modo the number of workers， what if I add a new worker？Right。

 it's the same reason why' solving the same problem because system hashing。New file comes along。

 do the same thing， hash it， come on of the list but now to his point what if I come along with a new new worker node because I want to scale out or a worker node goes down I got to take one away so say I had a new worker worker four and so if I hash for the first one it just ends up being in the end of the rank list so nothing changes because it was assigned to worker one that's still a highest priority so it stays there。

Say for this one， worker 4 ends up between3，3 and 1。 again， nothing changes。

 it stays there for this one， a worker4 is here， these guys slide over， nothing changes。

 but for this one here it becomes the this has the highest priority so now when I add this new node。

 I need to transfer file 4 ownership to from where was it2 to4。

And they didn't have to reshuffle everything。Same idea as existing hashing， yes？The question。

 how often is this check for each individual node， or if the topology of the cluster never changes。

 you don't need to rerun it。Because the hash function is not going to change。

So it's it's only my membership changes in the cluster。What's the。百。So question is。

 what's the drawback of using this versus consistent hashing。

 So consistent hashing is going to have faster lookups。 It's going to be a login。Right。

 versus this is O N because I got a hash ends the number of notes。 got。

 I got to hash it for each each one。 well， that's a hash function。 It's not that expensive。

 when you're doing on a profile。 that's not a big of a deal。

This is much simpler to implement than consistent hashing。

 and consistent hashing is going to have a slower initialization and a slower rebalancing。

depends on the number of。Of node I would have in the ring for kiss and hashing。Right。

This is simple simple and easy。 And if it's consistent hashing is better for， I think， also if the。

If the topology is more volatile， people are coming going all the time。Which， again。

 for distributed to the database system where people paying thousands of dollars。

 the nose aren't flipping on and off all the time。So this is fine。Yes。

How many flowers can be a thank。So question is how many files can be assigned to a single node。

 So this gets at to this weight thing here what I'm not really talking about， but like。

You could have the weight be based on the。Based on the capacity of a node。

 if these are heterogeneous nodes and one machine has。

 more compute capacity or storage capacity than others。

 you could skew it such that it's given maybe a higher priority sometimes versus more likely to give a higher priority than other times。

Right， so like another way to handle that is you could have virtual node and say like。

Everybody gets one， but if you have a big machine， then you'll get two virtual nodes。

 So I'm more likely to get assigned to that larger node。

 There's various schemes you can use to balance things out。我还是你。Two different ball。

So you actually assigned to。This question is， what happens if you have two different files that are hash to the same worker。

 that's not a problem Who cares。Like they gonna have thousands of files and like 10 workers。 So。

 of course， you can have workers， multiple files assigned to the same worker。 same thing we saw in。

Innflake， their files are 100 megabytes。So if I have a 10 petabyte database。

 then I have a lot of files。Again， it's a easy trick， it's in the '90s。

 it's a simpler implementation than。Then consistent hashing， it just surprised me when I read this。

 I'm like， oh， okay， yeah， because most systems would do consistent hashing as we saw in Snowflake。

And I think that's because it's just， is there a similar to how？For distributed consensus protocols。

 pick they'll pick raft or paxos over view stamp replication。

 even though view stamp replication came first， but they're all fundamental equivalent， yes。

I think a hash function is a future change。経験で。Where do you really mess up the output。

 really change it drastically right right now so that kind of ensures that you kind of have an even distribution。

And you're just doing regular hashing， but not here。Prepenending like this work I identifier。

 How do you make sure there's no not going to be a queue in like。

Like maybe one worker gets assigned to them。A lot more pilot than the other one。

Can me some kind of skill like that。His question is how do you ensure that the hash function doesn't introduce SU？

嗯。I mean， the hash function， like hashing， putting the work ID as a suffix to the file name。诶。

Thatm not going to introduce SU in any meaningful way。Right。

 and think we're not hashing on the context of the file。 We're hashing on like the name， identifier。

So that string itself with a good hash function to be。low collisions。And again。

 think of like thousands and thousands of files， it'll be okay。The thing that they care about again。

 was solving the problem， the classic trap he walked into like， okay，If I had a new node。

 if I'm doing naive hashing， I got to rebal everything， this avoids that problem。And then obviously。

 if you drop in a worker goes down， youve got to reign things， it's just the reverse of this。来。

So that's the core architecture of yellowelick， as I said。😡。

It basically looks a lot like what we talked about so far。

 And you see bits and pieces from snowflake， bits and pieces from Drmel。And and the other systems。

And they're doing like the highQ query compilation。

 they're doing the vector Y vectorized query processing， the hyper push base model。

 you can see again， all the papers we talk about through the semester we're just seeing these patterns repeated over and over again。

Yes the system no running on。He to his point， yes， like he said。

 the other stuff aren't running in containers。That you know about like so Hyno。

 right because hyper was a So system， highQ was before containers are invented。

 but like is Dremmel running containers， yes。Yeah， it's running on board。Right。

 but the paper doesn't really talk about that。 Is snowflake running on containers。I don't know。

 we'd have to go email， he ask them。They running on their own。さ。They have their。

They have their own machines。snowflake。 No， snow snowflakes running when do us or whatever cloud plumer。

Yeah， so you can get baremedal instances， but do you want to have again？Going back to。I seen before。

Like there's a bunch of stuff Kubernetes is going to do for you， like fault tolerance， provisioning。

 system state management。 what nodes are up。If you don't use Kubernetes。

 you' got to roll that all yourself using like SD or bookkeeper or zookeeper or whatever right。

 But Kubernetes， like Kubernetes just runs the SD， right， like it just does it for you。

So like all of that， you don't have the right。 if you just rely Kubernetes。

 And the big thing of the paper talks about is for all the low level optimizations that that they。

 that they implemented， which we'll talk about next。The containers did actually not impose a problem。

Which to me was was that was surprising。Okay。So I've said this many。

 many times the entire semester that the operating system is not our friend， it is our enemy。

 right every day when you're database you wake up， you're like， oh man。

 I hope I don't talk to the operating system。It's going to always going to cause problem， right？So。

If now。We want to build a database system where we avoid the operative system as much as possible in the extreme case。

 and the ways that we haven't really talked about before。And and we basically one of our。

 our database process is to boot up。Maybe tell the OS like oh yeah， give us some this。

 give us that and then push it aside like and drive off without it and not know not ever talk to it again。

 What do we need to do to actually achieve that and that's what this paper describes how to do this。

So they have basically built a unornal for their database system where upon boot up。

 the database system talks to the OS a little bit， makes six to 10 system calls， get some memory。

 get some allocation to talk to the hardware， yada， yada yada， installs whatever drivers it needs。

 and then that's it。😡，At no point， will we ever have to go back and talk to the to the operating system for anything。

Which is the way it should be in life。嗯。And so they list a bunch of things that they do， which again。

Some of these things you probably would not do now， like build on custom memory allocator。

 we talk about that a little bit。But。But like all the other stuff， again。

 is basically how to interact with hardware and manage our own runtime environment of the system。

 We don't want to use the obvious system for any of that。

And they'll talk about in the paper or another public that they've given about the performance benefit that they're getting by re implementingpleing a bunch of the stuff that the operating system is trying to sort out a general purpose implementation。

 but they're going to have something that's highly tuned for their database system。

And the re pattern， I'm going just say the word over and again custom because they custom this。

 custom that custom because And again， they're trying to avoid the O。

 they end up re implementingplementing a bunch of the OS functionality inside of their database system。

 But if you want to get the extreme performance numbers that they're going to get。

 you have to do this。So they rely' make heavy use on asynronous architecture using cover routines and they want to do this because they want to maximize the hardware utilization。

 at no point do they want any thread to stall， like I said。

 because it's got to get something from memory， they want to keep everything in CPU caches。

Which is is not easy to do。 Its very impressive。第。You see this kind of architecture also too outside databases。

 this is all what the highfi trading guys are doing like the quants and things like that。

 those guys are super hardcore about performance and they're basically doing the same kind of thing where they whatever the trading system they're building for event notifications or triggers or all that is going to run in user space and they don't want the kernel the OS to do anything so they're applying a lot of the tricks that are being done in like the Wall Street world in the Fintech world。

 but for database system。All right， so the first thing we're going to do is build our a memory allocator。

So they have a custom nuerware allocator that sometimes they say they say there was lat or lock free。

 Other times I think the paper says it does minimal locks。

I would assume they're taking some blocks in there or some lashtes in there。

But what's going to happen is when you boot up the data system， it goes to the OS。

 doesn use an M for mallOoc， like they allocate all the memory they're ever going to want。

And then manage all that in user space。 And I're gonna en it in。

 in the kernel to prevent it from getting a victim written out the disk。

 they keep all the memory pages pin pinned in memory and never written back to disk。

And then when they hand out allocations to， to queries while they're running。

 they're going to do one trick to make sure that like。Well， theyre。

 they're only gonna run one query at a time the entire cluster。

 We'll talk about that why in a second， but they're gonna make sure that the。

 the chunks that they're allocating are， are contiguous as much as possible to avoid fragmentation。

 So you don't want to have like。one query allocate a one megabyte chunk and then you starts freeing up little bits and pieces inside of it because then you can't reuse it until the query finishes。

 so you're going to hand things out in larger chunks and try to keep things aligned nicely。

So they claim that their allocator is 100x faster than the Lipsy Malek。That's not surprising。

 And when I asked them when they gave a talk， like。

 what if you compare against like J E Maloc or TC Maloc。

 I forgot the other one is from Microsoft it's called me Maloc。

 which is supposed better than the J E Maloc now。 And they they haven't done experiments。 But。

 when they were building this in 2016。They were getting 100 x 10100x faster than Liipy malet。

In addition to this memory allocator， every worker's also going to have its own bufferable manager using all the techniques that we talked about in the interclass。

But for their， for their eviction policy， they're going to use basically a primitive version of L UK。

 where it's basically2，2 Qs， two linked lists。 We'll see in a second。

 And this is basically the same technique that my is doing。Yes。In location。

His question is is this is a arena allocation， Yes， where the arena is a query？

Postgred Schs is at a pool， like a memory pool with the query， same idea。

But the key thing is when it boots up， it gets all the memory， Where like Jane Malick and other ones。

 I think they do it criminal we care so about。We had a question， What。

 its only question like question， why do I care about how fast it is。

 if it's only once the beginning， It's 10 x password at runtime。

 So I I do the giant memory allocation in the beginning。 And then they their own custom allocators。

 like when you call。😊，Sa called new whatever， right， And then you got to get some chunk of memory。

 It's going through their code getting from this giant chunk of memory that they've already pre allocateated。

Yes， so。Sa the all the。Sorry， each of the cluster is like running one query。

That one't create at a time， but they can be like。So the paper says that。

Or either I'm conflating papers or talks in the way there they have。 some point， theyre。

 they're saying that they're only run one query at a time in a cluster。

But they talk around their memory allocator that like they keep track of memory on a per query lifetime。

 So that part sort of confusing。 I agree that like if there there's only one query running。

 then you just give all the memory back when a query is done。Right。

And this is what they said sort of says。 I don't， I don't know exactly what they're doing。

S have a question or Patrick or no， oh no。Right。So。I want to go back to this thing。

 huge pages here here sorry， yes。If everything think from the US at the beginning。You don't。

 you don't get more。The machine has say the machine has 100 gigs。You take 99 gigs。That's it。

So I say this idea is not novel to them， So some of the embedded databases that run on extreme hardware。

 I I think I mentioned extremet DB， they're running on like low level embedded devices like in those real time environments。

 or realtime operating systems。When you boot up， you have to get all your memory at the very beginning。

 you can never go ask for more again for the O。 The OS actually doesn't allow you to do that。

Right because they don't want like you know the missilell be flying and then you try to do malloc and a malloc fails and you have to handle that So they allocate all the memory in the beginning There's another system out of South Africa called Tiger beetle。

 they do the same thing system boots up， they get all the memory in the beginning and never call Maloc again。

Everything's happening in user space。So from a system design spectrum， it's actually a good idea。

 right， as I said like thinking how many times you called。

How many times if you called malloc or new inside of your code C+ plus+ or C code。

 you're not checking to see whether that memory allocation fails。Right。Yes， you're laughing， yes。

Again， like a lot of code is written like that。 if you're trying to make something super photon and resilient。

 especially like for embedded devices， you can't， you know。

 you don't want your car calling Malik and failing and then drive you off the highway。

So for safety reasons， they do all this allocation up front。

And they're doing this for performance reasons。said now when I call。

 I want to get memory from this allocator。If the allocation is going to fail。

You could have the allocator implement something to like， okay， I know I'm running this query。

 It's asked for this memory。 I can't get the memory that it needs。 You know。

 you could alert another part of the system to start spilling other things up the disk。

And we saw something similar in photon， right where photon had a centralized allocator sitting in Java that could in Sp SQL that could then recognize that you can't allocate the memory you need and then decide who to start freeing。

You can do the same thing here。Okay， so quick show of hands， here here knows what the huge pages are。

No， okay， so that's not bad。 So less than half， but more than I thought one， okay， so。

This is quick divergence。 I don't think we teach this in the inclass， we probably should。

 So you know when we talk about pages in a database system。

 we said that like there's a hardware page that's typically 4 kbytes that's the smallest size that you can guarantee or the largest size you can guarantee the hardware to write out something atomically then the OS has its own page size and the database system has a page size and in an LTP system like Postgres in SQL light and MySQL。

 know we're worried about making changes in the pages and running out so we don't want our pages to be really。

 really big。嗯。But now in the read only system。呃。You know the 4 kilotte page size is actually kind of small。

Sospecially if we're processing terabytes of data。So， the。

The reason why this is going bad for us is because。

The CPU is gonna to mean its own translation look side buffer using some portion of your L1 cache that basically is a mapping from like a virtual memory page to a physical page。

 And so if I have all these 4K pages as I'm ripping through， getting a large chunk of data。

 then that TLB is going to have a bunch of misses because it has to go fetch things that that aren't going to fit。

Right。So。With huge pages， you can tell the operating system that instead of allocating things in4 kbytes。

 I want to allocate memory in larger chunks。So in Linux， it's going be two MBgabytes or one gigabyte。

嗯。And so now on the actual physical hardware， these blocks have to be contiguous。

 but now I can address a block in or page in my TLB with a single virtual memory address can now point to two megabytes instead of four kilobytes。

So that's less pressure on my TLB， and that means I'm going to have fewer L1 cache misses in my TLB。

 and I can rip through things much， much faster。So you don't get this by default in Linux by Linux default。

 you call Maik or allocate something in M， you're going to get4 kilobytes。

 but you can pass flags and say， I want this to be using huge pages。So there's a paper from Google。

 which I think is two years ago for their custom memory allocator that found that when they switch over to huge pages for Spanner。

They got a 6。5% improvement just for switching the huge pages。Again， Spanner is an OTP system。

So it's not like you doing huge massive table scans。 It's still doing point query lookups。

 but that's a pretty big win for just changing this flag in the O and Linux。

So huge pages are going to make a lot of sense for an analog system like yellow brick and others that we've talked about。

 And so that's why they were setting the page size within a file to be two megabytes because that aligns with the two megabytes size you would get with huge pages in the US。

And also too， it's small enough where it could sit around in your L3 cache because that's going to be tens or dozens of megabytes。

 So these chunks can sit in your L3 cache on your CPU， and you can process it very quickly。

 without going out to memory。So for this reason， that's why they're using two megga size and they're going to turn on huge pages for in the operating system。

And the other papers don't talk about this， but I guarantee other systems are doing something very similar。

Okay， so half of you heard of huge pages。How many of people have heard of transparent huge pages？

Nobody， good， excellent。Okay， so。Do not do this。I'm putting this warning here So you don't。

 you don't forget remember this。 Okay， this is the worst thing you can do for databases for memory。

 Do not do this。 Okay， if you do this and I'm dead， I I'll haunt you we'll figure something out。

So Linux had this feature called Transparent huge pages。 I came out in。I think 2007。

 but it wasn't on default for a while and what this does is the OS in the background starts looking at your pages in memory and says。

 oh， I see that these guys are being accessed together very frequently and they're both four kilobytes。

 let me find a bunch of ones that I can stick together for your process and to make a2 mebyte page。

And then I underneath the covers， automatically hide that from you that now the virtual memory address go。

 you know， now points this 2 MBby pages instead a bunch of 4，4 k pages， right。

And then it can go even bigger， like he finds a bunch of2 MBgabytes。

 It'll try to put them into one gigbyte pages， right。So they turn this on by default。

Some point in the。2010s， and then they revert it back in a bunch of things because this is a terrible thing to do。

 because what happens is。When it's trying to do this reorganization。

If you do a lookup now on that address in memory， it's going to block your process because it's doing this reorganization and reorganizing things。

Now， further also more， like if， if now that。If you're doing a bunch of small rights into these files。

 which are getting for oh， that system we're not really doing。

Now you're going to have invalidation of the memory across this one Gby file。

 even though I may have done a small change。So this is a classic example of like the operating system getting in the way from the database system。

 don you definitely don't want to do this， but they thought like okay for most applications。

 this is okay， but from a database perspective， this is actually terrible。😡，Now for OLAP。

 if everything's read only， maybe it might be okay， like verticicas and OLAPP system。

 they say you can turn along if you run newer Linux distros because's the stalling has gotten much less。

 but pretty much every single data out there will tell you to make sure you turn this off。嗯。

So like if you just Google like。

![](img/b466eae44cb6a69937df0fea4bf1b657_5.png)

Transparent， huge pages， right。So here says much here's what it is。 Here's how to turn one。

 But then scroll past all this。 Then here's all the Davisvis vendors saying， hey， don't do this。

 Mom I'm gonna to be disable trans huge pages。 P cap or T B。 Why we disable it Oracle， disable it。

 Splunk， disable it， right。😊。

![](img/b466eae44cb6a69937df0fea4bf1b657_7.png)

So。This is terrible， do not do this。😡，All as I said， this is cancer for databases。But for。

 for regular huge pages， we， we， that's okay because we can control that。 And again。

 we know that the access pattern， the query that we're running for this particular data。

 we might be fetching from from the object store。 that can be in， you know， in2 by chunk。

 And that's fine。 And we'll get the win from it， okay。😊，Yeah， this is kind of like， you know。

Read N C17。 So we'd probably don't want to teach it to the undergrads。 But for you guys， it's okay。

 but don't do it， okay。So going back to the Buffo manager。

 as I saying they're doing approximate L UK and they don't say this explicitly。

 but it looks from their description that smells a lot like what Mysco does so in the way Mysco does the eviction policy。

 they actually just maintain a single linked list of pages as they're being accessed going from newest oldesttis。

 but they're actually going to maintain two heads into this linked list。

You'll have the young list and then the old list so the young list would be the ones that are like are recently been added and recently being accessed over and over again。

 and the old list are ones where once you access it the first time you put it in this old list so that it's more likely to get evicted and the idea is that if I read it once。

 but then never read it again， like it would happen in sequentialial scan flood。

 then it's more like it'll it'll get evicted more quickly than it would otherwise with a regular LRU。

But then when if it gets accessed again， when it's in the oldest。

 then it gets promoted to the young list， because it's more likely to be accessed again。

So here query1 touches page one， page one is not in our buffer pool。

 so we go ahead and put it here at the head of the old list， evicC page8。

 everything slides over and that's fine。Qury 1 goes away， but Q2 shows up， queryry 2 shows up。

 it acts as page1 again。 We recognize that it is in our old list。

 So we go ahead and now promote it to the front of the new list right and everything sort of slides over。

So then， I don't think they're。They're not。I don't know whether they're maintaining the oldest in the young list。

 but this is basically what they say， like every time you access the file the first time in the cache。

 then it's put in this sort of special place where it's more likely to get evicted。

 but then if it's accessed again while still in the cache， then it gets promoted to the regular LU。

Right。prettytty， pretty standard trick's and it's simple。All right。

 so the next thing they're going to also implement is given to the OS is the task scheduler the thread scheduler。

 so everything's based on cover routines and they're going to do basically co multitasking with non preempter threading where the task or the threat can go get something task to execute if it needs something。

 then it'll just relin control of it and return back to get the next task to work on for that particular query。

So for this， it smells a lot like the Microsoft SQL server SQL OS， but in that world。

 they were doing like I think five or 10 millisecond quantums in this one I think they're doing 100 millisecond quantums where they have this centralized scheduler for the cross the entire cluster that they have to then do a heartbeat and synchronize with every 100 milliseconds to say。

 are we all doing the thing， the right set of tasks the right operations right now？

And as I said before， they want to have all the work all only one query can run at a time in the cluster and that all of the threads on a single worker node will be executing the same task。

 just on different pieces of data at the same time so that all code address the code space。

 the code memory for the actual program， the instructions。

 all of that's going to reside in the cache and you're not pingpononging back and forth by running different tasks they're all basically running the same code just in different pieces of data。

 and you're going to maximize your cache usage。this is basically what I said before， because again。

 they want to have everything to be able to process on L3。Yes。

 so so this goes back to like the having multiple queries on the same thing。Sorry， are the tasks？

Let's say one to one with queries or like this is a query you have multiple tasks。

E question like a task one in one queryries orque a multiple task。They can have Mo tasks。

 certainly like different fragments on， you know。Yeah second thing。

 which part of this is coop because this seems like an interrupt driven？Scheduller right。

 so every 100 millisecond is going to immediately switch to a different query like normally it's not every 100 milliseconds I switch another query。

 every 100 milliseconds。呃。Right， but it may be like the， the， I have。I have 10。

1100 millisecond chunks or cues of data。 so I could still be working the same task as I'm processing a query。

 right。So every100 mill like， you go back and you go back to the。

 to the centralized schedule and say。what's the next thing I should do？And it may be like oh yeah。

 keep running the same task he's running， but here's the next set of files you should process on。

That sounds like a normal。Interrup driven scheduler。

 I think if there's something you need that's not there， you。

 you'll yield back and get the next task for yourself。I think that's the difference。And。

It goes back to like do you keep all the memory link？On the same worker， sorry。

 all the data on the same worker， what a context which happens。Con like like a。

OSOS level context switch or query query context switch。

 like do you need like grab data from somewhere else or is it just like five sets of query data on a single worker？

I'm sure what you're asking， so it seems like we have like look at， we have four tasks。

Let's say they're different。Is on the same worker。Again from what they say。

 I think it's the same query。But it could be different fragments of the same query plan， right？

So how come you can only execute one query at once if you want to maximize。Right。

 so to his statement is that he's correct。Why would you only want to execute one query at a time in the cluster if you want to maximize your research utilization because。

You know there's points where I need to call that bunch of data。

 and I'm not going to have all the query， know all like and that's to run as a single thread。

 I don't know how to handle that。So， I think that。I think what they probably do is。Actually。

 I'm specling， I don't know， but you can imagine like I know at the last stage I got to just combine the results back to it。

 you know， combine the results back to a single。know， results set from multiple threads。

 that single thread in， I could have my worker start running out the next query。But I don't know。

现在还具表了3。李个。What if you installed？It isn't harm mill like it's a long time， Yes， but I think。Again。

 again， they don't talk about this。 But I think the， the， the centralized schedule could be like。

 here's taskask 1，2，3。And then each task might take， you know。

 some 10 milliseconds or 2 some some subset of 100 milliseconds。

 So it's not like every100 milliseconds。 Okay， we're all doing the same things。 You could say。

 you know， here's enough work to do  for 100 milliseconds。ButI don't know， the paper doesn't specify。

Okay， so they claim that with not the potentialized schedule part。

 but this the thread schedule on the node itself。That it's 500 x faster than the Linux thread scheduler。

Again。It doesnn't surprise me。But it's。But again，500 x faster than what， like the the。

Your querys not got to run 5 x00 x，500 x，500 x faster。

 It's more like the portion that that you're spending， the time you're spent on。Scheduling itself。

 they've reduced that down by 500 milliseconds， but is the context 。

Yeah kind of like a normal context。い上です。thanYeah 100 nano。啊。But again， like that's like。

 how to say this。 It's Ammda's law， right， the slowest part of your query isn't the context switch。

It can be if you're flipping around all the time， but like it wouldn't be that bad。

So the other crazy thing they're doing again is that they're going to run the build their own device drivers。

 so they're going to have custom N and VME and custom NickI drivers that are all going to run in user space using their memory allocator。

 and they want to do this because they want to reduce the kernel copying of memory going from the hardware from the hardware to the device to the OS to user space。

So everythings going be down， running on their own custom drivers。

And then they have their own custom network protocol that they build。 And there's a byproduct of。

 the reason they had to do this is because when it was onprem。

 they were running with a Finna band using RDMA and they were getting insane numbers because it' it's in F band。

 but it's expensive， but you don't get， I don't think you can now。

 But at the time when they were switch in the cloud。 I don't think。

I think you could get that on Amazon。 I don't know。 but so instead of relying on TCP。

 which they found was too slow that they built their own network protocol based on UDP and did all the reliability checks themselves in their driver。

 and to get things from the NI up into user space as fast as possible。

 they're going be using the DVDK。Where they're actually going maintain the cues on the hardware themselves。

 every thread worker threat's gonna to have its own receive and transmit queue they're gonna to pull asynchronously to see whether there's any work to be done。

 and then this part's a bit confusing， but they talk about how they have what I'll call partner's CPU thread partner thread CPU running in another worker that if that thread ever needs to send if I'm a thread that needs to send data to another worker。

 I just can't send it to any generic mailbox on the other side。

 I'm own to send it directly to that CPU there's some orchestration has to be done coordation has to be done to recognize that okay this data press this CPU and this worker at least get processed by that worker on or that CPU on that worker and so they route things sort in the correct way。

They talk about how they introduce， again， a distribution operator。

 that's basically the shuffle stuff that we talked about before。 And in that case， again。

 I think it's。呃。I don't know how that would fit into this model unless you're doing the shuffle locally to read stupid things。

 And because you know that the the memory address for this worker that's responsible for some portion of the data is going then be sent to the other worker or the other thread on the other node that I know is going to be able to process it。

 So there's， there's a little。Extra work they had to do to make make the make this guarantee。

 But now if you have this where you know that my， my CPU can only write to the to this other worker its on its。

When there's one Q， then that can reduce the amount of latching or locking up the dew on the hardware device itself。

They also built their own client side， their custom client side S3 library。

 because the one Amazon gave them was too slow。 And again， they used the DBDK for that。

 And they said it was3 x faster than when Amazon did。So again， when they gave a talk。

With us a few years ago， I， I don't think they showed these numbers and I asked them about it。

 like how much， much， much better are you getting if you use DDK。

 And so this is running the TPCD S workload and on different cluster sizes。

 And they're showing like if you do regular TCP versus their optimized DK version it's around roughly about 20% improvement on。

In over Ego TCP。You know， that's not like mind blowingly， faster。

But I think paper talk about there was one query。 It was like 70% faster because it was transferring a lot of data。

 So obviously， it depends on the workload。 It depends on you know， how much is cash， of course。But。

Again， these guys really care about performance and it's 20% matters。I also asked them to， like。

 you know， between the the custom S3， all the PC Ie driver the custom drivers and all the the allocator。

 the scheduler， like which one has the biggest win and they didn't have an answer。 Like。

 if you were to build a new company and to pick one of those techniques Which one should you target and they didn't have an answer because they said a lot of the stuff they built。

2015， 2016， they haven't really gone back and revisited it。

And I think other things like the memory allocator， like JE Malk or email TC Mal。

 those gotten a lot better， and it may not be worth it to build it from scratch now。

Cost a lot of money， so is this UP？Slower。's just a cost saving His question is InA ban costs a lot of money。

 but you can only get them on Prem is UDP is this UDP thing they're doing。

 are they doing this because it's cheaper？I think no。

 I think they're doing it because' because if you just use like out of the box， O S networking stack。

 it's gonna to be slower。 So like by building something custom。They get better performance。

 I don't think it achieves the the Infin band performance， but it it's。

 it moves you closer to it because 20% investment than TP doesn't sound like。K。Again。For。

 for inter doesn't sound like crazy like， mean like you think you could do better or Well T does like so Yeah。

Itd be much higher plus the DVDD to do kernel bypass anyway。I mean， it depends on the query。 Again。

 there's one query in the in the TPCD S workload where they were getting a 77% improvement because that thing transferreded a ton of data on average。

 it's 20%。可呀。你 you。If you recently me right， I mean， even if they。So your question is。

We to ensure that reliable。Yes， sos confess is like， how do you show reliable delivery。

 Do you have to still do sequence numbers， Yes， but。Like so。I， I can， they don't say how they do it。

 but you can imagine like， okay， like， I know I need to send 10 packets。

 So when I start sending you data， if you're like， here's one of 10，2 of 10，3 of 10。

 And if I don't see like 4 of 10， I go back and ask ask for back exactly。But but yes。

 they are re implementinging something that looks like TCP， but TCP sends Xs for everything， right。

Like， here's a packet。 Did you get it， Yep， I got it。 All right， Here's the next one。 Did you get it。

 Y， I got it， right， And this is like。Okay， I should have sent you 10。 Did you get 10， yes。いやあだよ。

Like some instruments。Youや。8ight。Because。Re need the best choice。Again， five years ago。

 it was the only choice for EPBF。Right。Or say you can go back to like 2016， 2017。

I think' there's papers around even 2020， the show like。嗯。In the Linux networking stack。

 we just hammer the hell out of it。50% of the time it spent men copying in the kernel。

 So DBTK will avoid that。So now if you want to reduce them or round trips I have to do。

 you'd have to use them this UDP thing。And you can only do this for eight or no communication。

 like obviously Amazon's not going to know your funky UDB protocol when you start talking S3。

 you have to use what they want for that， but you can use DBDK to get that data up quickly as possible on the client side。

A members。Inineer。So David is he's skeptical is worth engineering。 I'll do this。 Let's。

 let's we can three more slides。 we can revisit this， yes。Other questions。Allright， so as I said。

 I like the paper because they actually have benchmark results。

 which I think they're the only ones they actually do with absolute numbers， not relative numbers。

And so for this， they're running all TPC DSS， scale factor one， so it's not that big。

ButTVC does has 100queries， and they show the the total runtime of the workload。

 And so you can see they compareance yellowb， snowflake， Redshift， Bigqueries， synapse and Databs。

 Again Redshift will cover well cover on Wednesday。 Synapse is from Microsoft and Azure。

 We were supposed to cover that。 and then。Whatever diarrhea。Anyway。So so so。Off the bat。

 you see like， again， for this workload， the facets。 But again， like。

All these systems abstract away what the harbor actually is you say I want 10。

 you know I want my data warehouse to have 10 units。 What does that mean， right， What is the disk。

 what is the CPU， what is the memory， So all that's abstracted away。 So you can say， okay。

 what's the cost to actually run this per hour for these queries and then you divide that time it takes to run the workload by the cost per hour and you can get what is actual cost of actually running this thing。

And in this case， yellow brick is you know significantlyally cheaper than the others。 And yeah。

 we're talking like $2。 but like this is like for a workload that took 900 seconds think of like in a real enterprise system。

 these queries are running all the time。 your things running all the time。

And this was start to add up。 And like I said， scale factor1 is not that of big of a size we do it。

Alright， so do we trust these numbers as much as we like looking at them。No， maybe。Maybe， why。

 why maybe？What's CP。Is itCDS with TVCA numbers？I mean TBBTDS is more complicated exactly。Simpler。

That what I was thinking， maybe they've chosen TVC strategically。really display what there is。

But when it comes to me。Everyday analytical queries that are probably simpler than TCDS。

把 savings answer。Okay。Yes， maybe they didn't account for loading。

I said maybe you didn't cover loading the data like we saw a snowflake。

That one I'm last worried about。I don't think they would be that。about。は。😊，So what I'm looking for。

 I I I don't think they would be that naive。So like， yeah， this is。

 this is T PCC D S for a different workload。 But we just said their're query optimizer， you know。

 they inject rules and make sure they generate the right query plan， right， So， okay。

 I'm not saying they they， they play tricks， but like。

You don't know what the query plan looks like this， maybe for whatever reason。

 Redshift or synapse just picked a crappy query plan or in this case here， synapse is $6 an hour。

 maybe this is just running on fewer machines。Because made the next one up 0$12 an hour。

 but maybe that would cut time down to what Ebert can do。

So the main takeaway from all of this is that there's so many different factors in databases that it's really hard to be able to say from one workload is one better than another。

 now maybe say okay， the TPC thing that I made fun of before。

 that solves this problem because that can guarantee you have a level playing field。

 but that accounts for just are you running the process correctly。

 it doesn't explain why things are actually better than another。RightBecause again。

 yellow brick is going to do haiku style C plus compilation of query plans。 Well， guess what。

 Redshift does the same thing， right， Snowflake and BigQury aren't doing in compilation。

 Databricks doesn't do that either right anymore。 unless you're running as Part SQL。

 or how do you know that this is running photon and not not regular part SQL。😊，So again。

 it's nice to look at， it isn't necessarily tell the whole story and obviously。At the end of the day。

 you really only care about not TPC D S numbers care about like what your workload actually can do。

Am。And so which leads me to my finishing comment， like it's very impressive what they did right and I'm saying there's I have not come across another system that does all these optimizations the way they have。

 And if you're like a brand new startup today and say， hey。

 I'm going to build a brand new system and you would。You know。

 I would not go the path that they went down to like。You know。

 implement all this low level hardware stuff that they did， but again， it's fascinating。

Some things you wouldn't do anymore。 I don't think you would want to use DBTK。

 I think you' want to use BPF， and that could give you most of the same benefit。

 either your ring might help in other situations as well。

 And I don't think when they talked to us they were doing that。But。

The key thing that matters and relates to the last slide is all of this， all these optimizations。

 this O S level stuff they're doing does not matter if you pick crappy query plans。

 If your joint orders are just wrong， then who cares that you're doing kernel bypass with custom PC I drivers because your your query plan is just gonna be absolutely terrible。

And that's， that's going to be the most， you know， I think that's the most important part。ok。Alright。

 so next class is the last lecture。 We'll do Amazon Redshift。 And then like I said。

 I'll give out the the final exam for you guys to take home and that'll be due next week。

 And then I have office hours today， but not on Wednesday because I got a flight for Seattle for。😊。



![](img/b466eae44cb6a69937df0fea4bf1b657_9.png)

Legal stuff。Okay， yeah， I can't do it。

![](img/b466eae44cb6a69937df0fea4bf1b657_11.png)

Can， you got a bounce to get the 40 young spot， get a quick。

 take a sip and you'll be picking up models， ain't no puzzle like cousin because I'm more man I'm telling the 40 young my short' got four can。

Sts six pack on the table and I'm able to see saying I on the way。

No short with the clock you know what got them， I take off the cat but first I tap on the bottom。

 don' about three and the freeze it so I can kill it。

 cat full with the bottle baby whoop don' fill itca they know to say they' pain out we you drink't get down with the guys little wild pass。

 take back the pack of nuts。Don same now to trick to the Billy Dean to Phil teach the tell with weak guys。

 be a man to get a can of thing time。🎼。