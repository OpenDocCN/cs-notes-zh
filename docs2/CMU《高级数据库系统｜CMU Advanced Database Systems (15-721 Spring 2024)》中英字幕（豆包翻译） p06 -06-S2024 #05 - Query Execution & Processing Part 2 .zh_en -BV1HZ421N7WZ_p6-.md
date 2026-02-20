# CMU《高级数据库系统｜CMU Advanced Database Systems (15-721 Spring 2024)》中英字幕（豆包翻译） p06 -06-S2024 #05 - Query Execution & Processing Part 2 .zh_en -BV1HZ421N7WZ_p6-

🎼Carnegie Mellon University's advanced database systems course is filmed in front of a live studio audience。

😊。

![](img/009326a528df86c3d217135b849e249a_1.png)

🎼。🎼So today we're going to pick up where we left off last class again talking about how we're actually going to execute queries and so in last class we discussed。



![](img/009326a528df86c3d217135b849e249a_3.png)

We mostly discussed query processing models， and part of this is deciding what is the sort of shape and the amount of data we're sending from one operator to the next in the query plan。

And then what is sort of the control mechanism that we're going to use to tell one operator to execute right and the distinction here was the push versus pull。

 again bust is a pull based system where it me primarily focusing on push systems and then we talked a little bit at the end how do you actually represent the output of predicates and filters either a selection vector of offsets of position list or bitmap saying what two got satisfied。

So again， going forward it in the semester， we're going to assume that in our conceptual system we're building as we go along is going to be a vectorized push base system Now vectorize is pretty much every system now does vectorize push base。

 its I don't actually know the number maybe less than half is push base。

 still a lot of systems are still pool base。😊，But one of the key advantages that we talked a little bit at the end about pushbase system is that you essentially have this centralized scheduler that has complete control of what tasks are to execute and when。

And this allows you to have fine grain control over when things actually are executing and so there may be situations where if you're running out of memory because too many queries are running。

 you can just pause in a pushb system because you just stop executing tasks stop scheduling them or if you have another if you have an operator that needs to go get something over the network and that's a blocking call。

 you just can deschedule that task and then fired up again when it's available so pushbase model allows more control over exactly what's going on than a pullbase approach。

But again， so not every system will be push based， but almost every OL system today will be vectorized。

All rightSo today's class， we're going to continue where we left off last time talking about how we' actually going to run queries in parallel。

 the different types of parallels that we have， and essentially how we're going to architect the system so that we can allow multiple opera instances to run at the same time。

 either within the same query or multiple queries concurrently。

 and then going forward starting next week we'll see how we actually start paralyzing the individual operators within the query plan。

😊，Then we'll talk about what the operator output looks like in terms of。

How do we reference other parts of a tuple， other columns。

 whether we put everything together or do late materialization。

 we talk about what the data is going to look like going from one operative the next and the spoil is be we're going to use arrow for this。

 evaluate expressions and then we'll just do a quick preview of what adaptive query execution looks like。

 what we focus on in the context of the VO paper you guys read。

 we'll focus on how we do predicate evaluation and let that be adaptive。

 but then going forward throughout the rest of semester and then when we talk about the query optimization。

 we'll see how we do query adaptivity。😊，And this is the hardest one。

 this is one of the hardest things you can do in the database system。

 and you kind of need to design this data system at the very beginning to be able to support this rather than go retrofit it。

 mostly on the query plan side for the expression stuff， you can add this stuff later on。

All right so the parallel execution， the idea is pretty straightforward straightforward， again。

 some of this will be a review of what we discussed in the intro class。

 but the idea is that we want to be able to have our database system run multiple things at the same time to take advantage of the hardware that's available to us。

No longer are database systems running on these mono monolithical machines that have one CPU with one CPU core and no way to talk to other machines at the very least into your single socket。

 it's going to have dozens of cores， maybe a multi socket machine and then now that's basically a distributed system。

 let alone scaling out to multiple nodes So in that environment we want to be able to have the system be able to take one query and fanning out across multiple machines to paralyze the various operations。

Right， and when when sorry， question multiple doesn't matter。 Yeah。

 so this question is multi machines and multiple course。

 for all the things we' we're going to talk about today， doesn't matter words it's a multi threaded。

 multi process， multi nodeode system doesn't matter。Because thinking about what is a multiscket CPU。

 you have to communicate something may or may not even in the same address space。

 whether it's multi process or multi threaded。So if you have the communication channels set up to distribute things。

As you're not calling low level pipes to do IPCs to different processes。

 you can extend that easily to multinode。Right。And we're not going to about what kind of frameworks you could use。

 whether there's framers that hide that abstraction it though？Nowadays。Nevers really fast， yeah。

 especially if he's in the same rack。嗯。Yeah， the CPU is often going to be the la onneck。

thingsIn the last two or three years， things have flipped。Yeah。So again， I mean。

 this is why I just told him the high level approaches that we're talking about here today aren't going to matter whether it's again。

 multi threaded， multi process or multin， right？😡，So at a high level there's two types of parallelisms。

 inter queryry parallelism， and query parallelism， and again。

 I think we've covered some of this in the intro class。

 but we'll go in more detail and each of these。😊，So in queryry parallel basically means that can I have multiple queries running at the same time in my system。

 and there's something up above， like a coordinator or a scheduler that's responsible for figuring out who runs where and at what time。

I did some previous work in this space and when we looked at existing systems。

 most of them them using a really basic firstcom first serve policy， meaning when a query shows up。

 it's assigned some priority based on that， and then it's allowed to run on whatever resources that it needs and then other queries that come out later come later in time willll get resources when they come available when the first query finishes the enterprise systems can do more sophisticated things like have priorities for individual users or connection strings。

 so like if you're a if you log in with some user credentials or you'll be given high priority to other queries。

 but a high level it's still doing more or less first come first serve。So in OLAP queries。

 they're going to have both parallelizzable and non-parleable phases and we'll see what that looks like in a second。

 but the main idea is that we want to keep all our cores。

 all our resources actually running something。 So if there's a point where a query has to coalesize data to a single node like in exchange operator that change operator may be running on a single core。

 so we have other cores available to do other things。

 and again this scheduled component is responsible for figuring out how to take advantage of all those available resources。

So we won't go in too much detail in this class about how we want to do this for inter query parallelism。

 There'll be a separate lecture on。Scheduling queries。

 and then we'll see things like for join algorithms and other things。 How do we。

 how do we handle the cases where where we're distributing tasks cross different nodes。

 So different workers， whether they're in the same box or not， And we need to send data around。

 So we'll cover this a bit more detail later in the semester。

The thing but most will think about when they say query parallelism is introque parallelism。

 The idea is， again， taking a single query and then distributing across multiple resources of multiple workers running at the same time。

 And this is the beauty of a declarative language like SQL that where ideally。

 you don't have to know or care what the。The the system architecture looks like whether it has one node or four node or 10 nodes 100。

 it doesn't matter， get the same SQL query can then be chopped up into different plan fragments or tasks and then let the system distribute it for you。

 So it's not like you have to debug things locally when you maybe debug things locally on a subset of the data and then submit it to the larger machine to run on all the data。

 you have to rewrite everything the SQL in theory should just be able to to translated into a distributed plan or parallel plan on the system without any changes。

So there two types of parallelism， the most common one is going to be intra operator parallelism through what's also called horizontalal parallelism。

 I think one of the executiontion engine teams was asking about sort of asynchronous Io and doing a technique called vertical parallelism so we'll quickly talk what that looks like I'll say also too all of these things are not mutual exclusive you can combine these things together and various systems are going to do this in different ways。

 but again the intratro operator parallelism is way more common。😊。

And then for each of the individual relational operators that are out there。

 there's parallel versions of all of them， and oftentimes that whether or not the operator itself is aware that it's being paralyzed or not。

 depends on the implementation， and if it's not aware。

 then we'll see an exchange operator in a second where you put that above and allow to combine results again not being aware that it may got fanned out across multiple tasks。

So horizontal parallelism says in most common one， the idea is that we're going to break up an operator in our query plan into independent。

Instances of them or operate instances that are basically going to do the exact same function or exact same computation on its input。

As all the other operator instances that it's a copy of。

 but it's gonna to be operating on different pieces of data， different chunks of data。 Again。

 just think of like a sequential scan， I have a if I have 10 parquet files in my table that I want to scan。

 then I can have each operator instance be responsible for scanning just one file。

And they run in parallel， I don't need to coordinate the intermediate results while they're running between them。

 they're both independent computations。But again， at some point we need to put the results back together for other parts of the query plan or the final output we give to the application。

 so we're going to use an exchange operator that's allow us to coalesce these results from the different operator instances and then combine them together and then send it off to whoever needs it next。

RightSo we'll see this technique used in the Morsels paper when we talk about scheduling in a few weeks。

 this idea of an using exchange operator dates back to the 1990s。

 so it's not new but this is basically how a lot of distributed systems or parallel systems are going to operate even if they may not call it exchange operator it still will be some variation of it。

 I'll show you what I mean in a second。So here's the most basic version of doing exchange。

 so we have our table here we want to join A and B and we have this really simple predicate so the first thing we want to do is convert this logical plan into a physical plan and so say we have there's three chunks of data or three partitions on table A that we want to scan so we could have anop instance for each of those that it gets assigned to an individual core or worker and again whether it's a worker thread worker process worker node we don't care。

😊，Lalammbda function， it doesn't matter。And so now we're going to be start building up the pipeline so we know we want to scan a and then immediately after scanning some some vector or row group out of A。

 we want to apply the filter on it。 so again， we don't need to coordinate that filter operation across different workers or different operating instances so that can run in parallel。

And then we want to do predicate sorry projection push down。

 so we'll push that down above here in our pipeline。

 and then now we then feed that into the build side of our hash join。

So now the output of these three operator instances are now going to feed into this exchange operator。

 think of this as like the pipeline breaker for multiple operator instances。

 so I can't do the probe side of the join until the exchange operator gets all of the results from individual operator instances。

😡，What I'm also not showing is how we're actually building the hash table here， is it one hashable。

 three hash tables？Again we'll cover that when we talk about joins later on。

Sometimes it's faster just to build three separate ones and then do another pass to put combine together。

 which sounds crazy， but sometimes it is faster。 Most systems if they're in the same box。

 they'll probably build a single one， so you need latching inside of that thing to protect it。

So you think each of these is now these boundaries here， this is the operator instance。

 so this is the pipeline。 so once we have that， then we go now on the other side of the queryrryplantry。

 again， say we have three filess or B， so we're going to have three different instances that are going to scan B。

 do the filter， do the projection， and then probe the hash table and produce the output。

But now in this case here， assuming we have a single hash table for our query plan。

 each of these individual operating instances， each of the individual pipelines could probe the hash table separately。

So you're going to have three three threads or three workers producing outputs from this join here。

 so I need another exchange operator to take their individual results， combine them together。

 and then produce the final output to the user。So again。

 the pipeline boundary for each audience is it's going to look something like this。Yes。

The exchange will also be running。His question is with the exchange be running on these when of these cores sets。

 it'll be， yeah， think of this as like a。An operator instance that's running and keeping track of the input so that it's getting。

 and then depending on whether or not it actually doesn't work。Right， like in this case here。

 the exchange operator could just be， oh， I got an notification that we've populated the hash table from three operating instances。

 So that actually it doesn't do any computation。 It's just a barrier to say。Okay。

 now we can start running on to other side here in the case up here。

 this exchange operator actually wants to coal us the results and again。

 whether or not that's a physical operator that is just taking buffers and putting them to a final output or somehow we've staged the output buffers in such a way that three threads go right into at the same time。

 it doesn't matter。So the exchange output I just showed you is what is known as a gather operator again。

 so these are the variations of an exchange that you can have and as I said the gather one is the most common one you'll see in those systems and so this terminology I'm showing here。

 this comes from SQL server from a blog article I think 2006 and so this is their terminology but I think it clearly defines the different ways they're going to take data in and send data out so now again not every data system is going to follow this taxonomy。

 but I like it because again to me it seems easier to reason about just saying oh yeah。

 they're all exchanges but sometimes things come in one way versus another。So again。

 the gather operator is just combining results to multiple workers and they're producing a single output stream that it sends to somewhere else in the query plan。

The distribute exchange operatorter takes a single input and then fanss it out to multiple workers whoever actually needs it。

So you can think of this like。When we talk about enemy results。We've talked about before like， okay。

 what if I want to have the output of one query operator be then used as for multiple query operators。

 like if I'm doing like a subquery that appears multiple times to the query plan。

 I want to be to reuse the result for different parts of the query plan in the DAG so the distributed operator would allow you to do this。

And then the last one is to do reppartition， basically have multiple operators producing input to the exchange operator。

 and then it's going to produce multiple outputs to different channels。It seems like macro。拜。

Toortype is just you're reducing them and mapping again。So to say this seems like mapR， sure。

 but what came first， parallel data this is map Reduce。Palade this， yes。

So when would you need the the Ga one seems like the only one that I can think of is going to be useful you need partition and when would you So standard partition。

 BigQu is going to cause us a shuffle。RightAnd so after every pipeline。

 they're going to do this shuffle thing。 and they actually to have a separate service。

 take the inputs。And stages them。 And then the operators the operators upstream can then pull from them。

 And it may be the case that the number of the number of operators， the number of。

Of workers that are that are on the sort of input side might be different than on the output side。

 So having this like natural staging point barrier point。

 you can then scale out scale in the number of of execution engines or opportunities1 bubble doesn't have to be a network。

 but yeah， yes No， it won't happen a single node。 No， it may be the case that the。Like。

 you have a physical plan。 And again， we'll talk about add in a second。 like I have a physical plan。

 and and I have some optimize optimizer estimates with like。

 here's the amount of data I expect to get from these operators below me。 And therefore。

 I know how many operators I' going need to process it above the exchange operator。

 But what if those estimates are wrong and you like woefully underestimate it。

So even on the same box， you may want to scale this in and out up above。

 and the repartition shop operator allows you to do that。Okay， and。ぱすな。

Okay so the other question I had was other than table scans， maybe you have a slide about this。

 but which other functions， which other operators could take advantage of this。

It doesn't seem trivial doing this for every operator。So statement is。

Are there other what type of operators would you have， could these be anything？

I mean my last slide in this case here， this is coming from the scan you need a bunch of my stuff into it。

 and then I'm showing the output of the join goes into exchange operator。

 but what if there was something above like what this is like a nested subquery。

And then there's something else that wants to use it up above， right。Again。

 the relation algebra relation operators allows us to be composed these things in any way they want。

So for all of these， is the amount of data in the same amount of data out or is it copying sometimes or is there any more semantics than？

It sounds like for reition。Can it sometimes be like like？Making disjoint subsets。

 going out where they're copying it。So this question is， is it always maybe nobody say。

 is it always one to one inputs to outputs or could you make duplicate of the output。

 You could duplicate the output right， as I example just said before。

 what if I want to reuse some nstic query computation， Well。

 you know I have 1 thousand00 tus coming in。Logically， I have 10 twoples coming out。

 but physically I maybe I have know double that because it's going to do two different parts of the equation。

 And does that change like the distinction shift like this is just all considering partition。

I all a reppartition if you do that。Because it seems like it to be a logical difference between oh I'm cloning the data to different places。

 I mean you could do that with this one too， right？I another。

 another question is how much computation is actually going on here， could you。

Like is it like sorting， no， could it do？Well actually could it be like sort of like maps like the specific amount of the third operator to like the first thing out。

 it's not a good idea yeah doing that would be a bad idea're just taking a bunch of things in like okayre just going to randomly decide which way it goes you're not randomly citing equal Im sorry it needs to be equal right？

mean the amount of work that goes to each one ideally， but you cant you can't guarantee that。

 right So like again， think of this case here think of like。

 I take some input in and then I'm gonna to hash it on some key and then read it based on that hash key。

 So in that case， again， if I recognize that。Everything'skewed， and it's all going to this operator。

 Then maybe I want to do another round of hashing and redistbut it。

But then repartition operators running on one single node， no， not。Yeah， again， BigQuery。

 this is like， wellll in this semester， BigQury is going to run a hole except like service that just does shuffle that just does this。

So it's the specific implementation of this specific reppartition node that determines it。

 so there's no general。Yeah， so his question is。Like， okay， this is PowerPoin。

 This's boxes with arrows going in， right， I'm getting the idea that like you could have three inputs in or then two puts coming out very that logically you could build this right。

 I sorry， you could build this based on this logical idea and the sophistication of the different implementation are going depend on the various systems。

 Bigque， they they fabricate hardware to make this go as fast as possible。😊，Right。

Microsoft doesn't do that， or other people don't do that。A lot of people actually don't always know。

 Bigqueery is always going to do this。And gives， it seems like it would be expensive。

 but it opens up a lot of opportunities to do a later on。Okay， so。Again。

 you can obviously see how this is just generalization of the other two。😡。

And I'm saying you partition， again， this is Microsoft's terminology。

Google is going to call it shuffle，o。BigQu is going to call it shuffle。

 I forget what thing Databricks might call it shhuffle2。

 if for MattR to the Hadoop world they would this shuffle but the idea is more or less the same。

And the question is， again， the statement is isn't just copying MapRduce all the way around MapRduce is copying databases。

 and I have a paper that talks about that。Yes。We can take that one off。Okay right。

So the last type of parallelism is interop parallelism。 And the idea here is that within a。

Within a single query plan itself， we could have multiple pipelines running at the same time you sort of think it is like an as segmentronous model where we have one pipeline always running but it's producing tus and that tus get fed into some other operator sorry some other pipeline that's always running as well and so you may still need to exchange operators just combine any results from the different segments but if your query plan allows us and not all of them do。

 you could get better speed up because now you don't want to run one pipeline and when that's done then switch over to another one you can start running higher parts of the query plan as soon as you have tus。

Again， when it's allowed， This is sometimes called pipeline parallelism。

 You'll see this mostly in the stream processing systems。

 which I're not going to talk about the semester。 Exles of that would be spark streaming。Not Sam。

Pular is another one。There that one guy who came here for a year。Rising wave。

 right there's a bunch of these systems that are designed to this Kafka is probably the biggest example of this。

Yeah， I I I blanked out on Kafka。 Kafka is the big one。 All right， So say we have this， again。

 this unusual query。 right， it's basically a Cartesian product across four tables whether I with no。

 no clause。 And so in each of these， I can run the。

I can run each of the pipelines just at the same time。

 this one up here and the two ones up the here are going to be blocked waiting for whatever comes out of these two down here。

 right？😡，As this thing is running， it's sending tus up。

 and then it can merely start doing the join on， on other things once once it's available。 right。

 Gu Cartesian product， you're trying to match everybody with everybody。

 So there's no you won't have any false。You won't have any false negatives because you're just waiting for things to come up。

 And as soon as it come as you can start matching and producing the output。 Again。

 this is a stupid example， but it just gives the idea that you could run these things at the same time。

 and you' just it's a producer consumer model。 This things producing tus that it sends up。

 And then that guy's waiting for for those results。But again， this is not that common。Okay。

So now let's talk about the， the paper that I had you guys read and the。

The reason why I had you guys read read the Velox paper is because， as I sort of mentioned in the。

 the second lecture or the first lecture that。You know。

 there's this trend now where people have recognized that the like an OAP execution engine sort of become a commodity and that there really hasn't been groundbreaking。

You know changes in hardware that requires to rethink how we want to want to build everything。

 Certainly there' optimizations and improvements over the years。 But at a high level。

 like it's a vectorized pushbased system。 Well that's what snowflake you know invented 2013，2012。

 that's actually what theidb X100 system was doing back in the day they weren't doing pushbased So there's a bunch of these different products that are out there that are all more or less doing the same thing。

 And you can sort of think of now， instead of if you're gonna to build a new system from scratch。

 although we are doing that here as part part of the class。

 Like instead of having to build all the low levelve details you would need or the functionality for an executionion engine。

😊，It'd be nice if there was just something off the shelf we could use that could provide this basic functionality for us。

Right。And so that's the idea of these sort of these these composable libraries for building database systems and that you could。

 in theory， instead of building everything from scratch for every new environment。

 every new workload， whatever， you can just use these things and modify them and extend them for whatever the hardware or whatever whatever whatever the application you want to support。

 So the V one is probably the most famous one。 again， add a meta。

 which we'll cover in a second Data fusion we're also aware of， which is part of thearrow project。

 which is。😊，Don't feel like it's should be a separate thing， but it's an alert story。

 There's this OAP thing from Intel。 Polers is another one where again。

 they're all just trying to be these libraries you pp down that are ex engines， yes。

I includes the front ten as well。We'll get that in a second， yes。

 his statement is data fusion includes a front end， Vlog doesn't， yes。

But you don't have to use their data fusion front end， you could just use the executionion engine。

Right。Okay。So Velox is came out a meta。 And what I liked about the paper。

 they talked about how the original motivation for this was they looked across the entire organization of meta and they saw people reinventing the wheel over and over again building these custom executionion engines that were at a high level all doing the same thing。

 And it was a bunch of wasted wasted effort where everyone's trying to do the same snowflake style optimization to all these executionion engines。

 And。😊，They would end up。Having different semantics and understanding and data types and other capabilities and would be really hard to sort of transfer any from one workload running on one system to another system。

 Or the one example he mentions in the paper is that they did a survey and they found 12 different implementation of the subting function all of meta where sometimes they they started with zero。

 sometimes they started with one。 sometimes they took null。

 sometimes they threw exceptions like everything was completely different。

 And so they were trying to unify this or having sort of vlos be this again， this low level。This。

 you know， execution engine library that could you could extend for the different categories of workloads or different environments that they want to support across Me and then have。

 you know， a small team make that one really， really fast instead of。

 random people can trying to reinvent the wheel。嗯。So， as you said， in V， it's not a， you know。

 it's not something you just plop down that immediately use。

 There's no front end there's no SQL parser。 there's no query optimizer。 There's no metadata catalog。

 There's nothing to keep track what tables you have。

 It literally is like just just the execution engine that implements the operators。

They have a little bit more things they can do the they have some memory management。

 thread management， they have connectors to read data from different。From different sources。

 but I mean， it's the core the really thing they're trying to optimize is essentially running these operators in parallel in a vectorized manner。

So the input is going to be a physical plan a dagger operators。

 and then it's going to produce some output wherever you tell it to go and again。

 it's not like you just，It's an excuse run， you have to build this in the context of a larger system。

M。So。For all the systems we're going to cover throughout the semester。

 we'll try to do this quick summary to say here's the core features that they have again。

 And then you have this mental checklist and say， okay。

 I have a high high level understanding of what they're actually doing so。

When we talk about Databricks， photons and snowflake and everything。

 we'll try to go the same things like here's the key things that they have based on everything we talked about this semester。

So Vloc gives me a push based vectorized query processing engine。

 they're going to use pre-compd primitives and cogen for expressions in C plus plus again we haven't discussed what this is that'll be the paper you guys read on Monday next week。

 but again just think of like scanning a table where you know a column is going to be in32 they have a compiled version of that they have a compiled version for floats and all the other data types。

😊，They can support capatibility with arrow， which will cover what  error looks like in a second。

 they have some support for adaptive query optimization。

 not the full query plan optimization that we'll see later in the semester。

 but they can do some little tricks as you're running and scan along data to modify how they're going to bio your expressions and so forth。

😊，And then as far as I know， at least when I looked at this before。

 they only support Stmer's joins and has joins。Again， there's no query optimizer。

 there's no networking layer， all of this has to be provided by whatever the encompassing system that wants to include Bells。

Again， as he said， data fusion has more of this stuff。

 but even that's not meant to be a full complete system。So as part of this again。

 because it's not a full complete system， VO doesn't have its own proprietary data format。

 it doesn't own any of the data similar to this data like architecture we've been talking about where we assume thats a bunch of files somewhere on S3 or whatever object store you want。

 and they'll have connectors allow the scan operators go retrieve that data and process it。

 but it's not meant to be at least the library by itself can't control the ingestion of data and so forth。

 like something else that has to manage all that。😡，So they're going the API is the provide exposed。

 have the capability to define connectors that allow you to retrieve data from other systems。

 So connector is a very common term that's used in different systems。

 like you type in your favorite database and type connector。

 you'll see different you know they'll see what kind of kind of capabilities and support to talk to other things so。

The one that's probably the most extensible is like Trino or Presto。

 which Presto came of meta as well。 but they have connections to talk to any possible database you would want。

 And the idea is like it's an API within the system allowed you go talk to some other system。

 it's a database or a file system and then pull data in So you sort。Basically。

 you' a federated database where you make one logical database。

 talk to multiple physical databases and a connectors is how they all do that。

 If you're familiar with Postgres， the foreign data Rapper API is the simple thing。

DuckDB calls them extensions， but the term usually is called connector。

And then they have adapters that allow them to decode and encode the different storage formats that we talked about before。

 so parquet， orRC， Dwarf is the extended version eternal version of orRC from meta。

 and then alpha I think I mentioned before， this is something that the Velx guys are building。

 but the next version of OrRC。So there's a bunch of components that he talked about in the paper。

 some of these you've already covered， some of these I want to spend time on today。

 right so the type system， they're going to support scalrs， sort complex nest types。

 the vectors that they're going to operate on are be arrow compatible with some extensions。

 although of I think the extensions they've added are now in the mainline arrow codes I don't know how overlap there is today。

 or how much distinction there is between the two of them。

They have ability to find functions if you want to have like your own version of substr or whatever you want thats not in the built in VX library。

 you can send that。Then there's the engine that actually runs the operators。

 which we've covereded a lot， connections we've talked about。

 and the resource management would be like memory pools。

 basically above a pool to keep things in memory and pull things out as needed。So today's class。

 I want to talk about these three things because we already talk the type systems in the context of a parquet。

 function API， again， its just almost like a user divine function allows you to say。

 here's this new built in capability。Connecting different connecting different from storage devices or whatnot。

 that's not really new。 And the research management stuff will'll cover throughout the semester。 Yes。

 I was ask you can your question there any you doing that doing the whole memory or is there always a good A to have。

Separate your memory into。Something that you can pull and get back to。His question is。

 is that a good idea to manage memory that in the way they do？With arena pools， absolutely yeah。

 because what's the alternative？Well， I don't think Rus has something like that， but is rust？No。

 the they you said Ru the programming language， but' let you do something similar to the way was asking。

I mean， this is a layer above the programming language。It's a system， they have to manage membrane。

But it's also like a see to first constrained。And it sense that we need to manage memories equal plus。

 you don't need to do it us， this is a good idea to do this always， this a storage。No no。

 it's memory。I mean， the answer is yes。Rus says Ru is prevent you from like。

Handing off memory without keeping track of it， right？But like that chunk of memory。

 you want to be able to like， you don't want to go malloc every single time， right。

 you want a memory pool。あ、いやいや。So this is a layer above the proing language。I if it was like Java。

 like a memory management， like memory management。Quer programming language。

Even then you want to avoid like in the JVM， you want to avoid their garbage cluster。

 you want to allocate your own memory， absolutely yes。Where the data is here。

 we can do anything better than what the OS can do or what the JAM or whatever can do。

So we want to manage everything ourselves。Okay。So all right， the first thing I to talk about is like。

 okay， what is the what is the。What do tus look like， not in the physical level。

 but like that's not true either， but like how are we putting together and sending data from one operator to the next。

 not in terms of what the encoding is， just in terms of like。

OfIncluding all the data we need or some of the data， right。

 So the operator app is going to define what is actually being passed up from one operator to the next。

 whether it's in the same pipeline or not。 again， it doesn't。 It matters， but like the。

The Davisson will be able to decide， okay， at what point do you want to materialize everything？

And how we're going to put things together， it's going to depend on where the processing model is。

 so in the vectorized case because we want to operate own columns。

 we don't want to materialize maybe all the columns all at once because we know we may not need that up in the query plan。

Depends on what， know， is a roast store a comm store。 In our case， as a common store。

 So know we want to do lay materialization and depends on what the data requirements are， meaning。

At what point do I actually need certain pieces of data in the query plan and how expensive is it going to be to go get it again versus materialize it at the point I'm actually scanning the data file？

So let's say in the case here， we want to do this join on RNS and there's this the join clause RID equals SID。

So we know that we're scanning RNS， depending on the number of columns that they have and how wide the table actually is。

😡，We know that we only need certain attributes from those tables at this point here。

 so at what point do we actually materialize the tuole so we can do the join or do the projection above it。

So to do early materialization， the idea is that at the moment you're scanning the data at the leaf node and the scan operators or whatever part in the qua plan。

 you're going to put the entire tuple together。RightAnd this is easy to do in a row store because when you scan the tuple。

 everything's right there and even the PAs model it's all gonna to be within the sort of same row group and close by。

 but depending again how wide the table is， you may not actually want to put it all together because not that's not free。

So if I'm doing this join， again on earlier im materialization。

 then I'm going to stitch together the entire tuple of of the join operator and have that be my output that's going to be sent from this operator to the next operator。

Right。So again， the idea here is that all the subsequentent operators in the query plan never need to go back to get more data because we're passing the entire materialized tuple up above。

In late materialization， which is what the VLS people do and most of lab system do。

 the idea is that you only want to pass up the bare mineral number of attributes you actually need in the quarry plant。

 and at any point you need to get more data， that operator has the ability to go down and get it。

So again， in this case here， doing the join， I only materialize the record ID for R and S and then like a Tple ID or an offset that says。

 allow me to go find the other attributes within the columns below it。

And so that's what gets passed up here in the query plan， so in case of R。

 I'm just feeding up the TL IDD and RID because that's all I need to do this side of the join and the same thing here。

 once I get past the filter on value， I only need to pass up the SID。Right to do the join。

 but now up above here， after after I do my join， I have R IDD because that was passed up to me。

 but then I don't have the creation date on the S table。 So in this case here。

 the operator has the ability to says， okay， I need this other。

 I need this other attribute and it has the capability to ask the system to go fetch it for you and then I can stitch it together。

So in this case， know。You may not always want to do it this， right， it may be the case that。

The cost of going， fetching things from disk again or from the out store could be expensive。 again。

 if it's cash， you avoid that， that I I want to materialize everything early， but again。

 if I have a billion tus and the joint produces one tuple。

 then I'm passing along a billion tus a bunch of columns I don't actually need。

 and let's better do late materialization。So this is an old idea that goes back about 15 years ago。I。

 I don't know whether the first column story stuff did this in the 90s from Cy basic Q。

 But I know Mo Mobi did D B did this。 Vertica do this Like this is。

 this is an old idea that pretty much everyone does today。 right again。

 it's easy to do in the P model or the。In the PAX model or the column store。

 because we can go fetch individual columns as needed and put things together。Yes。

you have a really huge query plan and a column at the bottom it's only ever use again back at the top then do you drop it forSo his question is if you have a really high query plan。

 a lot of steps going up，And there's， there's a， there's an attribute that's used at the top and the bottom。

 And nowhere in between， would you drop an and out of back， You could。

 I don't think anybody does that。Just bit too much bookkeeping， I think。It also here depends on like。

Like yeah， and you have to estimate things， it would be hard to get it right， yes。I know。

We know like which context of materialization pursuing materialization is good in。

 but like in terms of sort actually designing systems。Do like systems。We just want the other。

这个还 approach。So his question is those pros and cons of both of these。

 I'm be phrasing those pros and cons both of these。

 do most systems just pick one to use that or they try to be clever and do a hybrid approach。

 I mean it's sort of similar to what he was saying。 Can you try to figure out like。Can you， well。

 here's an extremely example， like can you try to figure out for any query plan。

 should I use early materialization or late materialization？

I think some systems do the enterprise ones。 I don't know about the open source ones。

 I like I don't know what D DB does。 I think probably what is most common is just pick late materialization and to do that because there's less engineering。

Okay。So now so now we know again we' assume we're doing late materialization and we know that what we're sending up is going to be columns of values。

 it's the bare minimum of what we actually need to process each operator as we go up We now we need to talk about what the encoding of that data。

 those columns actually look like。Right。And the challenge here is going to be for these lakehouse systems or these overlap lab systems that want to read data from。

B of files on S 3， all those files can be encoded in different ways。

 like parquet or whatever CSVs and。That means that you need a way to transform whatever the on disk representation of that data that you're reading into some common format that the execution engine can actually understand and support。

Because you would not want to say， here's my sct scan operator or my joint operator for。

For barquecade data， I have my my s scan join operator for， for orrc data。 like that just be so much。

 you know， so much code to maintain。 It wouldn't be worth it。

So all these systems are going to translate or transform the dis format into some internal representation。

And that's what's going to get propagated from one operator to the next as we go up in the queryrry plant。

So the。So the internal or internal encoding as I said。

 is how the system is going to represent data on the inside。

 This may not be what is then exposed to you as the user as as a result of the query。

 like it may come out as arrow， may come out of the parquet file， whatever。

 But as it's going from one opera to the next， it's going be it's going to be different。

And so just like when it was on disk， we want our columns to be the values within each column to be fixed length。

 because then we can find the corresponding matches across tuples very easily。Ideally。

 we want to be able to move data and use data structures and move them from one upper to the next without serializing。

Right without having to run like in better blocks around that algorithm to like to do three passes to try to encode it。

 that's super slow to do that while we're actually running a query。

 So we want something that that can ideally naly operate on the encoded data。

And move that along without having to deserilize it first。Similarly。

 we be also nice to have zero copy memory access， because that would then potentially allow us to take our internal representation of data。

And be able to share that with external processes。Now this is a new idea。

 this is actually what arrow is really predicated on。

 but think of something like actually DDB does this really well。

 So when you you can use DDB inside like Python code。And almost a data frame API。

 and you can access data that's running in memory inductDB and all it's doing is just passing a pointer because it's the same process。

 you don't need to serialize it and deserilize it to transfer data。

And so if you have the ability to have this common representation that everyone could potentially support。

 then you can do that zero copy memory access。Like that's sort of extreme example。 But thing of like。

I could send data from， from one node to another node over the network。

And if my transfer scheme or transfer encoding scheme is the same as the internal representation of data in my operators。

 then I don't need to serialize and decsalize it as a word of protocol buffers。

 I just send over that data and then soon as the bytes arrive on the other node。

 it just starts crunching them。Even crazer， you can put things down in the FPGA and on the nick and that can start crunching on it without having to decompress it first。

And there's some systems that do that。So this is obviously leading up to what Apache Ar is。

 and so in the same way parquet and OrRC are defined as open source formats for storing data and files on disk。

  Ar is a open source format to describe how to store data in memory。😊，In a common art fashion。

And the idea is that it's going to set the sort of。Encode data in such a way that。

In the implementation of something that operates on A data。

 we'll be able to do all the cache efficient vectorized stuff that we're talking about throughout entire semester。

The one thing that is going to be much different thanarrow sorry parquet and org is that they're also going to be able to support random access more efficiently I can jump to an offset and get the exact value for that tuple without having to decode using RLE or Delta coding all the stuff that we talked about before。

The sequentialial axis is ripping through the columns and processing things。

Soarrows a lot of stuff like it's meant to be sort of this framework that comes with memory management。

 thread management， RPC mechanisms， they have a SQL parsel and a SQL transport layer as well。

 but what I'm talking about here today is just going to be the encoding scheme for the columns for the data or pass informant operator the next。

 again， whether it's on the same box or different box， it doesn't matter。

Do you also have sort of a not simplistic but a basic expression expression engine for evaluating expression trees。

 like simple filters projections so you can't do all of the complicated functions that you would want or could do inveelloox like they can do really basic things like just something there's this column equal to this and so forth。

 and they actually compile it down into LLVM and then using this engine they have called Gendiva。

So errors may much different than parking in org， and again， because they want to be lightweight。

 they only support two encoding schemes。They have dictionary encoding and some variation of RLE。

They're not doing del on codingd， they're not doing all the bitmap stuff that Betterblockox is doing。

 it's just going to be these two things。And so the way they're going to do a dictionary encoding。

 at least the original version was just taking all the strings that are in a column。Sorting them。

 and then the offsets are the codes you're going to embed in the column itself。Yes。

Mr that the second。This is a memory reference。Why do they have expression of evaluation？Yes。

 there's a specification of what the encoding looks like。

And then there's an implementation of being able to operate on it in CL+ laws。And so as part of that。

In implementation， they include the ability to like find know the fine the columns or finding matching tubes or something equals something。

 And the way they're going to execute it， we'll see in a second， instead of traversing the tree。

 they're going compile it down into LLVM。Again， it's hard to say it was debating whether you even to mention it because we haven't talked about queer compilation。

 which is what next week， and we'll see how you can do this for expressions in about a second。

 but again， it's more than the spec， there's an implementation library for it as well。

All right so I should have talk this earlier when we talked about data encoding of how you actually want to represent strings and again。

 strings of variable length， you want to convert them into fixed length values store them in your columns but then what are you actually storing for that value in the fixed length column and then where are you actually storing the variable length string？

So what era originally did was the fixed line data would just be a size and a pointer， so 12 bytes。

 and then the pointer would just be an offset in some blob region in memory。

And it just point out what byte offset you would find the string that you're looking for。

 so the column would be this data up here always 12 bytes。

 and then this other variable length thing that has the actual strings itself。

So it didn't matter what the string was， you were always using this scheme。So in Ve in the paper。

 they talk about how they extended arrow to support this additional storage scheme that's based on something that the Germans did and we'll just call that German string storage。

 So the idea is that if a string is small So it's always going to be 16 bys instead of 12 by if you always have in the header you have the size。

 and then if the string is small， you'll store a 4 byte prefix。In the first four bytes。

 and then whatever the remaining data is in the remaining eight bytes padted out to zeros。

But the string is larger than this in the prefix， you saw have the size， you have the prefix。

 but then you have the pointer now to that blob area where you have the actual full string itself。

So even though in this case here， you have the prefix here。

 you're still going to store it down here because you don't want to have to like。You。

Stitch things together when you're scanning things along。

 you just jump here and get down to everything you need， right。And so this is a really simple idea。

 but this makes a huge difference because now in some cases or some queries。

 I actually don't need to follow the pointers， like if I'm just trying to find all the strings with with start with the letters AN。

 I can rip through my column that are always going to be 16 rightstes and just do the pattern matching on the prefix not even follow the pointer。

😡，RightWhere in the case of above， I don't have anything in my fixeding data。

 I always got to follow the pointer。Right。So again another way think about the the pointer like that's sorry。

Like this thing here， that's the dictionary code， the pointer is the dictionary code。Right。

And mean in some cases you can do there's times where you don't even need to follow the full string to do some computations。

 whether it's filtering， aggregations and all other stuff， you just look at the prefix。

And so I talked this last year and there was no name for this technique。

 I'd just been calling German German style string storage。

 and then other people start using that term too， so this is from the Ar people where says， you know。

 last year or six months ago， this is in October。That says Ar can't do German style string storage。

 Li to some of the same slides。 And then he shows the PR where this comes out。

 But then someone messaged him afterwards， like， hey， what is German style string storage， right。

And this， the paper from the Germans for Ubra where they invented this technique。

 the Germans do amazing stuff。 like， well， I said this before。

 like they love to pack they love to pack like balloon filters and other things and left over bits in different parts of the system like for hash tables even though they're 64 B pointers in X 86。

 Intel actually only uses 48 Bs。 So they take the remaining 16 bits and they put a balloon filter in in your hash table So that just checks to you whether the keys getting gonna exist in the chain that comes after that。

 So you can look at the balloon filter and not even follow the pointer So similar idea here。

 they do amazing stuff。 And then they this actually came out two days ago。 The polls guy。

 they have a new blog articles now they're using this using this format。 And of course。

 somebody's asking again， what does German style storage actually mean right。😊。



![](img/009326a528df86c3d217135b849e249a_5.png)

So this is my fault。就。All right， so the Ubra style string storage or noian style string storage。

 Okay， Dr B does this。 Vox does this， Poler does this。 Ubrara obviously does this。

 I don't know what the hyper did， right。So this is a really simple technique。

 and it's a huge huge win。😡，Am。Yes。So suppose you want to do an exact string match。

 say five or more bytes， then do you do like two past thing where first you like filter out everything。

Not matching in end of the。Yeah， his question is， if you need to match when you say you need all five bytes the first five bytes instead of four。

Would you do a first pass， look at the prefix， figure out what matches then within that do a pass on this。

 Probably yes， actually I don't know what Pols does and the other one systems do。

It would make sense because in that case， you could rip through a column。

 figure out what you actually need to look at。And then in that case， also you would avoid duplicates。

Right because like， again， thing of this as like， I could have multiple。

 if multiple tuples are sharing the same string， then the pointer would be the same。

 So I could just calles them。 I had to do some bookke to figure out， okay。

 which ones actually match the same thing when I， when I pass off the results。But yeah。

 that probably would be a faster way to do that。 assuming there's enough overlap。

But I don't know what people actually able met。But it's a good optimization。Yes。

I this pointer like an often or what？Eially is this pointer an offset，😊。

It could be an offset or within again， some blob region mid memory。I don't know what errors started。

 I don't think it's a。Yeah， inarrow， I know it's a bucket number then also within the bucket because they have different buckets for the verying data。

Okay， yes， but in B， it is just。I think Bells was just a pointer， Yes， yeah。

 but and I was looking at the aerospect， and it's a bucket。Because and。Again。

 think of like you're sending stuff over the network， you don't want to have to deserilize it。😡。

So if it's just a logical pointer， then the physical memory dress doesn't matter on the other side。

So German Sta string storage is really Uto string storage。Okay。

 so I don't want to talk too much about this， I just want to mention it real quickly。

We mentioned substrate before this is a。I it not directly related to arrow but think of this as like in the same way that arrows is meant to be a universal file format or universal encoding scheme for transferring data across different systems。

 substrate is meant to be a open source specification for how to represent query plans。

 relation to outdoor query plans， so in in I think data fusion andductDB。

 I think they have the ability to take these substrate query plans and execute them。So the idea。

 you know， the idea seems great。 Like it'd be something like I can take a something like calcite or some。

 some query optimize as a service service， have it produced substrate。

 And then if my system can then operate on that that query plan。 that's the， you know。

 I just taken and run it。 I have these things be bit more decoupled。

 So this was created by the guy that that did。😊，Apache drill。

 which is a open source clone of BigQuery from Google。

 and then I think he also could have found a Drremio as well。

 but now he focused entirely on substrate。Question， sorry。Okay。Again。

 so when I talk to some of the arrow people at Volon data。

 the problem with substrate is thats for really simple things， it's okay。

 but soon as you start extending it going beyond what they expect and it causes problems。

And I think it's just one dude， just is like doing it whereas likearrow rather large consortium。

 I think substrate is mostly， at least it was at the time， it's just one dude doing as hobby now。

AllDavis we mentioned multiple times and again， the branding seems kind of weird because it's a part of the Apache Aero project。

But it's almost like his own entire separate thing。

 And so I wouldn't be surprised if this thing gets forked out underneath the arrow umbrella comes its own standalone top level project in Apache。

 But it's basically like V， it's vectorized executionion library for operating directly on patchingarrow data。

 It does include a query optimizeizer。 It does include the SQL front end。

So it's a bit more it has bit more features than than Velloox， but at core。

 if you don't want any of that you could just take their query engine。

 So there's already a bunch of systems that are based on this Influx E is probably the biggest one out of all these。

 this is their third Influx E's third rewrite。And now that's a long story。

 but they had the Rige version 1。0 and then they switched。

 they got off SQL when I told them it was a bad idea and they added M that was a bad idea。

 And that was version 2。 and version 3， they got rid of M， they added backsQL。

 and now they're based entirely on data fusion。 Sarah Db can CB， I think they're out of。😊。

At China and then CFal， I think these guys are。Oh， they just got acquired by enterpriseterprise D think two or three weeks ago。

 I think this is a data fusion executionion engine that's designed to run inside a Postgres。

Anyway soarrow has sort of become the defect facto standard， like snowflake supports it。

 like this is a lot of systems are based on this， and then data fusion is one implementation of an engine that can operate on it。

All right， so I want to finish up talking about expression evaluation and then sprinkle a little bit of adapt execution。

 and then that'll then set us up for talking about vectorized execution next week。😊。

So expression evaluation basically says， how do you actually take what's in the wear clauses or joint clauses or the predicates and evaluate them on the data as we're scanning doing our executing our operator？

And so at a high level， you can think of like the。The pars is SQL parsel is going to take whatever in the SQL query and convert it into a expression tree that looks like this and every node is going to represent some operator or opera within that expression tree like so you have for your conjunction disjunctions less than greater than not equal so forth。

 all your athemetic operators， constant values， references to tuples within or a column and then additional functions and you basically translate what's in the SQL query into a tree like this。

 now whether or not you break up like the join clauses in the where clause to separate trees or put them together or how you break up within the enes queries like all of that is left up to the implementation but it's always going to end up looking like a tree structure like this。

Right。And so how you would execute this。 Well， in the naive way is that for every single tuple。

 as I'm scanning my my data， I'm going to traverse the tree， right to do this， you know。

 I would start with the an good on this side， evaluate these things pulled up。

 see whether this equal is good on the other side and do that comparison。😊，But obviously。

 that's going to be super， super slow because。It's a bunch of indirect now I mean jumps and pointers in virtual function tables if it's sleep fl。

 like running this， it's sort of an naive case， which bust does use would be super slow if we're trying to scan through a billion billion tuples。

So。What we want to try to do instead is。Represent the expression in and as if it was like a function call for know within within a programming language。

 because now we can hand that off to a potentially a compiler。

And whether or not that's the query optimizer or a traditional programming language compiler like GCC。

It can do all the standard tricks that we know how to do in compilers for the last 50 years。

Right so say we have a real simple query where select star from table or I missing the from calls where S value equals 1 right again we have expression tree with equal clause。

 S value and constant well ideally we want to have a function that just takes in value as an input and checks to see whether it equals one。

😊，And have just run that function in every single tu。And so we could then compile this now， again。

 using our favorite compiler into actual machine code。 And then now， as we're scanning along a tuple。

We dis invoke that function， instead in traversing the trait。

So that's what that Gandva thing I mentioned in era， that's what they do。

This is what Postgres does is when you turn to the Jit compiler。

This is what a lot of systems actually do。Yes， so it's clear to why this is faster。

 but why is it that is true？Precise。His question is， go back to Bigo。

 why would traversing this tree so slow？So。Think of like， I have a。In my operator， my scan operator。

That all I have is a pointer to some root of an expression stream。

And to make it composable or generic， it's going to be a。It's going to be an abstract class。

So I'm gonna invoke like， you know， run， run function on this expression opera end。 that again。

 as C plus plus。 that's a virtual function table to look up to say what's the actual function I'm calling。

 Then decided this opera。 I'm gonna have two pointers left and right。 Then to call those pointers。

 same thing。 virtualr function table look up。 Then， you know， execute this thing。 Then go down。

 and now I'm copying data up。 That's how I was thinking is that you have like。😊。

So much interaction between nodes absolutely yes but okay。

 so crazy idea what if you did something like a B plus tree and you had everything stored in one big chunk。

 could you potentially get over this cost and I mean it's not not could be as good compilation？

statement is what did you do something like a B plus tree and store everything as one big chunk。

 What do you mean。Waiake。Instead of having。Instead of having to do。

Instead of having the full point of direction， having all the notes it's mal condition。

The entire tree。As like。The same way of B plus trees is faster。

every level you could the tra one flatten it， you mean， yeah， that's what Velex does。sorry。

They flatten it and then they， well，'s in a second。

 Vox has a experimental compiler that will come that will then convert it like the candiva and arrow。

 The candiva thing and the Vox one are separate。So Velx is going to flatten it， as you say。

 then you run along sequentially， along the leaf noses， right？

Postgre if you're not doing the Jit compiler， it'll traverse the tree。

My sequ culture traverses the tree， but a lot of us do that。

 and obviously that's terrible for overlap。Again， in their world。

 they're operating on a single tub for most of the time， right。In our world。

 we want to operate on columns， a ton ton of data。 So not only do we not want to traverse the tree。

 we want to make this whatever this thing we we convert it to the actual function call。

 instead of passing a single value， we want to vector our values trillion。You you wait， sorry。

 because you're going to do this check by。Oh yeah， we're going to book this function a billion trilling times。

 yes， yes。And so we can vectorize this。And I goes back to what we'll talk about next week。

 we talk about a little bit on Monday this week。I can。Because， you know。

 I only have so many data types in my columns and in my constants。

 like instead of having one hardcoded， I could pass one as a constant value here。

 And I would have a version of this check function and a quality check for in 32 in 64 floats and so forth。

 And I I'm just picking at runtime， which is this precomp function I want to use given a vector。

 given some constant。You know， return whether it's something equals something。this is different from。

The statement is is this different query compilation， yes。

 query compilation will differentiate between holistic query compilation where I'm compiling the entire query plan。

😊，This is just compiling the expressions， so you can still have an interpreted engine。H。

Which Velex does and what。Most systems do。But then within that， when I call expressions。

 those are precomplied。Prerick about primitives。And as I said， we want to vectorize everything。

So in the case of Vox， it the example that he said I wouldn't call it the BB tree。

 but I'm sure there's a compiler term to this， you're basically flattening down the tree so that you just execute things sequentially and then you can there to think of like what you're actually executing and alfunction you're making calls to function pointers。

That are precood， as I said， And because we're operating on vectors。

Ofp data rather than single attributes within a single tuple。

 Then that amortizes the jump cost going to that function。

And there is an experimental branch that is being actively maintained in Velx。

 but I don't think it's by default that can convert the flat expression tree or flatten expression from the query plan into some IR that they then convert to sequence plus loss and do fork Zec to compile that into GCC。

Right， which is slow because again， it's like I'， I'm。Synthesizing C plusos code in the file。

 then I forecast that GCC， which fire about all the process and the GCC is going to a bunch of other initialization stuff on its own like it's going to check config files and other stuff right then in composite code。

That's what the first version of a single store MeSQL back 10 years ago。

 they would do the same thing， and of course， in some cases the compilation cost for the query could be like seconds。

So you would only want to do this kind of compilation stuff if you know that the query is going to run for a long long time and that will negate the compilation cost。

 like if your query' is going run for 1 millisecond， your compilation times 500 milliseconds。

 that's not a fair tradeoff。 So you got to be careful when you actually do this。And say of Postcards。

 Postgs they'll have。They have an estimate for how long's're take the query plan to run。

 how long it's to take to actually compile something， and they don't always chip compile everything。

All right， so even without this compilation step， though， into machine code。

 VX does some additional optimizations that I think are kind of cool and worth're discussing。

So the one they're going to do is constant folding。

 so the idea here is that if you know that there is some operation doing over and again on some constant value。

 then just do it once， memorize it retain it and don't repeat it， question yes。Because， like。

Like barring the use of UDs， with these common expressions。The civil operations。

Ha it like anyone looks into like building like a white？I on the DBm， but just like only has。

you always filing these expressions because I don't think that would be too complicated this like L。

So his question is， has anybody considered？Basically embedding a compiler in the data itself and using that to compile like everything or。

It would be like limited to just the simple expressions that are。

Like no UDs because UDFs like make things really awkwardD， think are' saying in the opt。

Yeah so this is where I'm getting at， like thing about describing you， again。

 you learn in compileless class。But in the case of Vello， they're reimplementing that。😡。

And then the lines get blurry of who's actually should be doing these optimization。

 should it be should it be vox because dilemma query optimizer。

 should be the query optimizer above or in your case， could it just be the compiler itself。

 So there is a system out of Germany same school as umbr， She's not German， though。

 which is's at the German school called LoDb， where they convert a query plan to this thing called ML IR。

 which is similar to substrate， but think of like。You know，Me for more general purpose programming。

 and then they run clang or LL VM compiler on that who then does all of this stuff as well。 So yeah。

 people people have done this。 But I think I don't think any commercial system is doing。

 It's that what  Lo DB does Yes difference from like generating let's say C plus plus code versus。

I exactly code So his question is， is there a difference between generating relevant IR versus generating C+ code？

Let's punt on that till next week。So we'll look at an early system called highQ that did generate C code。

 said MemSQL did that。There's pros and cons of this。

 obviously it's going to be slower than just generating L ofIR， the other hand。

 if it crashes you have C code you can look at and figure out when went' wrong。

So we'll come to that later。 But to his point here。

 like I'm here's how to do constant voting expression tree。 That's compilers 101， right。

 So I'm calling this this upper function on the constant Wutang。

To do my comparison against the column， but I'm doing that over and over again for every single tuple。

 so obviously I can just do do this once。And replace it with Wtang。And。

And then I don't have to run them again。Another common thing they do is or at least in Vilocx。

 they do common subre elimination， so if you recognize that you have the same subte in your expression plan or expression tree that you're running over and over again。

 so running string position on a column for for a given constant。

 then I can just do it once and then link up this operator here to get the result from whatever comes out of this thing。

Right。Again， as we said， the lines are blurred between who's actually doing this。

 should it be the executionion engine， something like VelOox， should it be the query optimizeomizer。

 should be doing this。In the case of if you're just having a stand on query optimizer。

 it might be kind of hard to do the constant folding thing for this function。

 because now you need the implementation of the upper function。

So either you call the system that what you're running on and say， hey， here's upper。

 give me with the result of this， but that could be slow or you' reimplement it yourself。

Calci reimbal some of this stuff themselves。Data fusion is called data fusion。

 I don't know what OrRCcaD does from Greenp。Because of my SQL。

 I know for these kind of things within the optimizer itself。

 if they see that something they want to do this constant fold thing or other。

 they want to know what's the value for this operation of a constant。

 they'll convert some subset of the warehouse clause into a tableless select statement。😡。

Within the optimize， go run that query， get back the result。

 and then inject the value into the query plan。😡，RightAnd you can do that because My S can do that because it's tightly coupled。

 But again， if you're trying to build these things as separate stalulone services that'd be hard to do。

 you'd have to have an API to support it。All right。

 so the last thing I want to cover is this notion of adaptivity。

The idea here is that though we haven't talk query app yet。 mean， from the inter class。

 you should be aware of what they're actually doing， right， They're taking a SQL query plan， Sorry。

 SQL query converting to a physical plan。 we can actually then run on a system。

And the way a good query optimize is going to do this is through cost model estimates。

 trying to to predict the selectivity of every single operator to determine how much data they're shoving up from one operator to the next。

 they can use this to determine join ordering， right。And so。

For all the optimizations that we've talked about in this semester。

 like all that is a complete waste of time。 if we're given crappy queryier plans。

 if we choose the worst join order that we could possibly have。

 then it doesn't matter whether we're vectorized you're doing compilation。

 We're running on like fancy GPs， hardware or whatever。

 all that could thrown out the window because we have the crappy queryier plan。

So we need a way to be able to be resilient or robust。😡。

Have the extrogen be robust enough that even if we are given a crappy queryurier plan。

 we can tweak things and make changes as we go along to try to improve the situation。

The challengellenger you may say okay well okay well I'll just make sure I don't have crappy query plans。

 the problem is again in a lakehouse environment or data lake environment。

 you may not have any statistics about your data like someone uploaded a bunch of parquet filess in S3 and then you're told to go run select queries on top of that data you've never seen it before。

 how can you actually start producing estimates。Or if you use one of these connector things that talk to have your Lakehouse system talk to Postgress。

 Postgress may not expose to you its internal statistics。

 so you have no idea what you're actually reading。So we need a way to adapt the query plan while it's running based on the data that we're seeing while we're going along。

And this is what adaptive query processing allows us to do right we're allowing the executionusion to make decisions on its own without maybe consulting with the query optimizer。

 some cases you do， some cases you don't to either modify the query plan structure itself。😊。

potentiallytentially changing join ordering， moving projections up and down。

 or changing the expression tree while the query is running based on the data we're seeing。

So the idea is like similar to in better blocks， they did a little sampling to figure out here's the data I'm about to encode。

 then use that to make a decision of what the best compression scheme to use was while aquaries running。

 we're seeing the data so we can start making estimates about what the real selectivity of our predicates or whatever we're doing is on that data and then decide whether how to modify our executionion plan。

In the extreme case， we just say this is all garbage， these estimates are way off， give up。

 throw away all the results， go back to the career opera and say， try again， you did it wrong。

 here's some new results。😡，And some it seems crazy right that why would I stop a query。

 throw away everything and go back and try to run in with a new query plan， well， again。

 the worst query plan can be orders of magnitude difference between the best query plan。

So it is actually worth to go do that。Very， very few systems do that。😊。

Most of them just take whatever you're given and run it。

 and I think only in academic systems will they be this。completely give up。

So we'll discuss how to modify query plans later in the semester today I just want to focus on what tricks we can do to make the expressions evaluation go faster。

And so again， all the major OAP systems that are out there， the snowflakes， the data bricks。

 the dremels， the Bigqueries， I think redshift as well。

 they're all going to do bits and pieces of this， I don't think anybody really does this one。

 get throw up or throw it away and go back and try again。

 but they'll do some of the things that we'll talk about here。

 but I'm going to focus on on the beock ones。😊，All right so the first trick Vox is going to use is called predicate rewarding this is an old idea that goes back to the 1990s is a paper that did this in Postgres from a long time ago。

 actually from Joe Hellerstein who's now the database professor at Berkeley。

 the basic idea is that if I have say two functions in my wear clauses that I need to run。

 I can decide in what order actually want to run them。😊。

And there may be the tradeoffs between how long it takes to compute。

 one function versus how long it versus selectivity of its operation。

So you decide maybe I want to run the slow function first because that's going to be able to filter out more tuples than the faster function。

😊，And then as you're running， you can decide you how to change the order as you go along based on what the computational time would be and the selectivity would be。

Right。Common prefeing， the idea here is that if within my operator itself， I need， say two columns。

But so I can start scanning one column and maybe do the first half of my expression tree and rip through that。

 But then I make an asynmous Io fetch call to the storage service to go fetch the second column。

 I can start ripping through the first column。 Then in the background。

 it's fetching the second column。 By the time I finish the first column。

 Then I can then start scanning the the second one。

RightWe talked about how to do pre fetchching before in the inter class。

 but that was like prefeshching individual pages， this is like within within for in columns within my。

Within a single operator itself。not an null fast path。

 this technique basically says if I recognize that the null bitmap or that's being passed up from as my input to my operator。

 if I do maybe a quick pop count and identify that there's zero nulls in my column。

 then I don't need to do null checks。And I allied that process entirely。

 and I have a faster version of whatever the operator that I want to run or expression operator I want to run。

when I showed the post question numeric code， there's a bunch of null checks in there， If null。

 then do this， if not nu'll do that， right that's all going to be indirect。

 that's all going to be called brain misres。 So if I know there's no nulls。

 throw that way entirely and run a faster version。Similarly， you can also do。

You can avoid additional checks for string data if you know everything's ASI。So again。

 ASCI is the I guess the original encoding scheme for how we represent strings。

 but obviously that's been extended to UTF8 to support different international languages and larger character schemes like。

Pop emojis and things like that。 So， but if you know all your data within a column is going to be asky。

 you don't have to do the more expensive UTH UTF 8 check， right。So in the Bel paper。

 they just show that if you compare the cost of running different string functions on the UTF8 version versus the ASI version。

 it's order a magnitude difference between some of these functions。This is a really simple check。

 so the idea is that you always run with the UTF 81 first。Then if you recognize that you're scanning。

 hey， this is all ASI， then you just run the ASCI version。And if you get it wrong。

 important and roll back， yes， so other than the pedicure reordering。

 all three of these are something that you do。why you learn the query。

 but something that you would know about the query stuff theres no nulls in this one or that that you can dont ask no no。

 no， no no， you don't know anything。So while I'm running it。

 I'm just seeing asking actor I assume that it's only asking is that？Like for this one here。

 like I'm running， so I'm giving， hey， here's your string column。

And I don't think parquet and org tell you whether it's UTF8 or ASI or it's not even parquet file。

's you're parsing a log file or CSV So if you recognize that hey， this is all ASCI。

 I can run the fast ASCI version。But I need to see some of it a little bit first make that decision。

That's the basic idea， So I think they have a fall that mechanism is important I think if you're wrong。

行两咩先。I think for ASCI。WellIf you see something ask you supposed to be backwards compatible UTFE with what nu nu Yeah。

 but you have the null vector ahead of time。So you just do pop count as any bit set at the one。

 if no， run the not in allll。We're over time here， sorry。

One last trick I want to show is they also have the ability to which I like is if you recognize that whatever operation you're trying to do in expressiontry on a string data is can just overwrite whatever data you're given。

 again， think of like I have my original data files， I've turned from parquet to arrow。

 now I'm just passing around memory chunks from whatever to the next。 if I recognize that， oh。

 I just overwrite the memory of of this column with this data with whatever the operation I want to do on it I don't have to I gonna call mall or allocate memory to put new output in。

 So again， if you're running that upper function， all that's doing is just taking the characters you're given and upper casing them you can write that back over the the original value and reus the same buffer that you then sent up to the next operator。

Right， so they show like if you do the if you do that trick， you shave off another you know。

 another another 25%， nearly 25 to the 40% on your runtime by reuse the buffers right。

 So this is the baseline using the UTF version。 there's the ASI version。

 and then you get even more using。UsReing buffers。That's a nice little trick。 I like that。 All right。

 so just to finish up。 So today's lecture was basically a quick overview here。

 here's a bunch of stuff of how to design your execution engine。 And I'm sure to try to show you。

 here's the broad categories of things you have to think about。

 what what kind of parallel is you going to sport， how you're gonna move data from one operator to the next。

 what that data is actually going look like， how you evaluate expressions and what tricks you can do to optimize them。

 So I'm not saying that everything I showed today is is the complete menu or what's to available to you。

 But now you need to understand。 Here's the things that think about when you build one of these engines。

😊，And again， in my opinion that arrows may the best choice for internal representation is it perfect。

 no， are there improvements to it， yes， but it is actually evolving like they added German the  Ura style string storage。

 they added that last year right so it's not stagnant。Okay， so next class on Monday。

 we're going to talk now how do you actually run the operators themselves and vectorized men are using using Sti。

 So the paper I signed to you is from the Germans。 It's basically a deep dive into how to use A V X 512's features to optimize and vectorize relation operators。

 okay。

![](img/009326a528df86c3d217135b849e249a_7.png)

All guys， have a good weekend， enjoy the unusually warm weather。



![](img/009326a528df86c3d217135b849e249a_9.png)

Steps and six packs on the table and I'm able to see saying I。No short with the cross。

 you know what got them I take off the cat but first I' tap on the bottom。

 go about three in the freeze it so I can kill it， cat full with the bottle babyops！

Because they says the pain out way， you drink get down with the Gods little wash head。

Take back the pack of good。to the Billy De and toil to tell him we guys be a man to get a can of same pie。

