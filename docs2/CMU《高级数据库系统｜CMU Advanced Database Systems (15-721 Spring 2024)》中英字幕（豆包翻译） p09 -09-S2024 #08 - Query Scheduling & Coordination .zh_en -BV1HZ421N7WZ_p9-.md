# CMU《高级数据库系统｜CMU Advanced Database Systems (15-721 Spring 2024)》中英字幕（豆包翻译） p09 -09-S2024 #08 - Query Scheduling & Coordination .zh_en -BV1HZ421N7WZ_p9-

🎼Carnegie Mellon University's advanced database systems course is filmed in front of a live studio audience。

😊。

![](img/ff628513ec0af0c8bc137cb083aa2fed_1.png)

🎼。🎼It's still hot now。We covered Bristol scale， we covered diarrhea， we've covered。

What else behavior interviews， okay， that's how my data is is。Alright。

 so today we're talk about now how do we take the query plans that we've been given and actually start running them on。

 on our system。 So recall that the last couple lectures we've had， we're focusing on。



![](img/ff628513ec0af0c8bc137cb083aa2fed_3.png)

How to actually optimize or build and optimize executionion engine so that we can run sequential scan queries as fast as possible and again the major two camps are going to be the vectorization people with using SIMD and then the query compilation stuff that we talked about last class。

 in the case the query compilation， there was two high levell approaches。

 theres transpoation or source to source compilation。

 that's like you have your C+L plus code emit C+L plus code that then gets compiled。

And then the alternative was from the hyper paper that you guys read was compilation by generating like a load level IR for the actual instructions you want to execute for that query plan and then using something like ASM J or LLVM to compile it。

 And again， as I said， the main takeaway that。at least since the seminal papers and vectorization compilation have come out over the last decade is that most of the systems that we're going to read about near the end of the semester are going to choose vectorization with SID and often it's combination of auto vectorization and with intrinsics。

 but they're going to choose that over compilation just because the engineering overhead to maintain to be able to maintain a J compileiled database engine is super high。

You'll read this in the photon paper from Data because they flly call out。

It's better off having a bunch of people try to optimize the assemD stuff because then you can reach parity to the comp compilation implementationation。

m versus like if you go down the J path， there's a smaller number of people that actually can work on it。

Right。All right， so again， today we're talking about scheduling。

 of how do you take a query plan and divide it up amongst the different workers in our system。

And so again， just make sure that we're using the right terminology。

 we're going to say that a query plan is going to be a dag of operators and then relation operators。

 and then the operator instance is going to be an imation of that operator on some portion of the data that we're trying to scan。

 so we're trying to read a table， if it's broken up to row groups。

 we would have an operator instance be responsible for scanning a single row group and processing that。

And then a task is going to be some computational piece of work that it's going to。

 contain multiple operator instances， typically in the same pipeline that we want to then hand out to our workers to execute。

And then a task set， sometimes called a resource set in some of the papers。

 this is going to be the collection of the tasks that we need the collection of the tasks that we have for a given query that we need to execute。

And the idea is that we know where the pipeline breakers are because where the data system we the one building the query plan。

 so the idea is that convert these pipelines into individual tasks that we can then farm out and execute and so so today's class is really discussing figuring out how do we assign these tasks to workers in our system and I'm loosely defined reason term worker generically but you can think of it almost as either a core or thread or process doesn't matter。

Or node。And then keeping track where the data they need to access is coming from and where is any intermediate results that they're generating。

 where is that going to go？So this is basically what I said the idea of the schedule system is that we want to know for a giving query。

 how many tasks should we use because we want to take advantage of all the parallel cores that we have available to us。

 also the parallel operations within SMD or that's usually below then what we're actually going to schedule for。

 but keeping track of how many tasks we want to use。

 how many CPUU cores we're going to farm them out on，😊。

And then when a task generates some kind of output that needs to go to a next task。

 where should we actually store that？Because in some cases， if it's stored it local to us。

 it may be the test that's going to read it may be remote。

 so it might be better to push the data to where the next test is going to need it。

 but you might not know what that test is going to be。So we'll see this as we go along。

 but the paper I had you guys read from Hy， it's about single node execution。

And we'll see how we tie this all later at the end of the class。

 but the3D implementation of a schedule we're going to look at。

 they're also going to be all single node node systems and so the reason why I'm focusing on this rather than a distributed system because they think the problem is the same。

 It doesn't matter whether it's a single node or multithreaded or multiple nodes each single thread like it really is the high little problem I'm trying to solve is what task we want to run where and where should the output results go。

And the main takeaway is going to be that we're always going to want to do this ourselves。

 especially on a single note and not the operating system。I think in the hyper paper you guys read。

 I think the distinguish between Postgress， Postgress is just letting the OS do all the scheduling because it's justked full processes。

And I don't think they didn't even play games with process priority and so forth。But so instead。

 for the exception of postcast， every data system is going want to do all the scheduling stuff itself。

 So we we can talk about how to do it on single node。 And then we， you know。

 you'll see how that maps to a distributed environment。

There'll be some things we can do in a shipment environment that we're not going to cover today。

 but we'll see this later on， like in BigQu Drreemmel。

 they shuffle they're going to do have a shuffle stage after every pipeline breaker and that allows them to reorganize and recalibrate the workers later on。

 but again we'll cover that later。So what are our goals for building a high performance schedule for a data system。

 So obviously if we want to maximize throughput， we want to be able to process as many queries as possible in our system。

 just sort of keep the thing always running and always consuming results and producing producing output。

We're going to maintain some notion of fairness， and again this is subjective of what fairness means to sort one query to another query。

 but at a high level is that，😡，At the end of the day。

 we need to make sure that no query gets started for resources。

 so even though we may delay the priority and we'll talk about what that means why we want to do that as we go along。

 but we even if you get a lower priority because you're a long running query。

 the end of the day we still want you to complete。And the flip side of this is that we want to make sure that the system seems to be responsive。

That's reducing the tail latency， like the P99 latency of queries if we can。

 but this will matter a lot for short queries。And so the idea here is that we want our short queryries to complete as fast as possible because that's something someone is going to notice right at the short scales of a query execution。

 like if your query goes from 100 milliseconds to 1000 milliseconds， then you would notice that。

So you want to get these short queries out as quickly as possible。

 but if you're like your query is running for 10 minutes and it takes 20 seconds longer。

No one's going to notice that。So the system is going to appear more responsive if you can get the shorterer queryries that more quickly。

And the case of the morsel stuff。They don't have a specific way actually to handle that。

They're sort of treating everyone roughly a thing they were suggesting they in subsequent paper in the Obra one。

It wasn't the hyper， the one that we did there was something in the conclusionm say they would like to do it。

 I don't know why they needed in hyper。They do it in Ura， we'll cover that in a second。嗯。Yeah。

 so I mean， but the morsels one is， again， that sets the foundation for this idea of how to divide up the work and they're going to do a static assignment of tasks to morsels and we'll see anumb of how they can break that theumb one is more sophisticated。

And the last one， of course， is that we want。our scheduler to have low overhead like it doesn't help us if we're running this super complex computation to figure out the optimal scheduling。

 this optimal schedule for all our tasks， if that takes 20 minutes and aqueries can finish up in a few milliseconds。

So we want to have most of our assessment spending time computing queries because that's what people the end of the day really care about。

So I'm going just talk about some quick background at the beginning， again。

 this will be a quick reminder of the things we talked about in the intratroclass。

 but we'll first talk about what is actually a worker or how are we defining the scope of a computational unit。

 where is it actually located in our system， or briefly talk about what data placement actually means in the context of partitioning。

 and that basically is just， if I've already divided the data up in some way。

 where should I put that data。And the two are linked together， but again， we'll discuss that。

And then that's one of the things that the morsel paper spent a lot of time talking about was this notion between local memory and remote memory and a nuer architecture。

 and they were trying to schedule things so that you were always processing stuff that was local to you and the same idea applies in a distributed system ideally our workers on a node。

 processing data that's local to it rather than having to go over the network to some far storage。

And then we'll talk about three implications of schedulers。 We'll talk about the morsels from hyper。

 We'll talk about the follow up in umbra， and then we'll talk about an alternative from SAP Hanna guys。

Am。And then we'll finish off again just putting in the context of distributed architecture。Okay。

And so that the。What would be interesting about the？we about schedule implementation。

 We'll see in Ubra and hyper。 These are， These gonna have like。

Sor of dedicated work poolols that are just like crunching through all the tasks they can。

 whereas in the HaNna one， they're trying to be a bit more sophisticated and have this notion of some worker threads can be asleep。

 some worker threads can be parked and we also see this trade up between work stealing and not work stealing。

 which is another dynamic we have to consider as well。

All right so and this is just a reminder of from interclass that。There's。

 there's this notion of a process model in any data management system。 and this specifies what the。

What a worker actually is going to be in our system。Right so the。

These are the early database systems in the 1980s， 1990s， these were a processbased system。

 meaning every worker was a separate OS process because back then they didn't have P threads like we have now that they weren't really portable。

 so if you wanted to support one Uni versus another UniX。

 you had basically the Poss API specified how to do fork to spawn processes。

 then maybe not didn't have threading。Every modern system now today is going to be multi threadreaded。

 so we'll assume in our system we're conceptually building that be multi threadreaded。

 the only ones that are not multithreaded are ones that fork Postgres because Postgres uses a process per worker。

And the worker is going to be this generic term that means it's just the computational resource that can be assigned a task to execute for some query or something for the internal something for the database system and that it can take some data in crunch on it in our operator instances and then produce output。

And as I said， for our purposes going forward， you consume every system， unless they for progress。

 is going to be multi threadreaded。For some reason in the。

In the early days when I first started at CMU， we took Postgres and we decided to make it multi threadreaded instead of multi process。

I forget why we did that。 But the interesting thing about it is if you ever looked at the Postgs code。

 there's a bunch of pound of fines for different OSs they support like Linux and Windows and Hpos and BSD。

 And we ended up going and using like the win 32 code。

 And was that was at least starting point for us then convert everything to P threads。😊。

We also converted it to C plus+ 11， which I don't know why we did that one either。Yeah， we did it。

 we shouldn't have done it， but whatever Postgre is it's a process per worker。

So a worker is going to be a whole entire OS process， so you can do some parallel execution queries。

 but that's going to across multiple processes and they use shared memory to communicate。

But no you wouldn't build a system like that today。Yes， if all modern systems are。

What was bad idea is do that for Postg？This question is， if all modern systems are multi threaded。

 why was it a bad idea for us to try to do that in Postgres？Looking back on it now。

 I failed to see what the research contribution would have been。Right， we。

Well so we had this execution engine that was written Pfls that was faster than Postgres。

 which is not always hard to do。 said not that hard to do。

 And then rather than sliding it in as an extension using extension hooks that Postgres supports。

 which is timescale does and Sus does Cfo is another one there's a bunch of these data systems that use extension hooks to get overlap that engine inside of Postgres we decided to like fork everything。

 and then the top half of Postgres， we had the top half kept the top half rewrote the bottom half。

 we decided to then just scrap the whole top and rewrite everything because everything was sort of slow for what we wanted to do。

But again。If I had to do it all again， I would have just used extensions。Yes。

 so there's a process model like the term， is that just like multi thread versus process for thread versus like single process that is also？

Its question is， is the process model determine the any the new anthology stuff those are just like。

 is it a thread per worker， Is it word process for。

 It's just a process per worker Like its just like， like is it a what is the。Is it a threat。

 is it a process， is a process pool per worker？The numa stuff is in slow。Okay。

So the other thing we can account for is how do we want to assign the workers to CPU cores？And the。

 the basic two approaches are you could have a single dedicated thread or single dedicated worker be be the only thing that can run on on a single core。

 a single CPU core。 And this prevents like。This prevents contention on that core where like two threads are trying to run at the same time。

 their workers is trying to run at the same time at the same core。

 and they're trashing each other's L3 caches and so forth。Yes。

 so one worker is working on one task or one entire task set or one partition of a task His question is is one worker going to be working on one task or one task set or partition of a task We're not there yet？

But it's going to be one task， yes。And again， the thing of that， like I had to scan this table。

 the table has 10 chunks or morsels， you'd have one worker for each of those 10 morsels。

RightThe other one is going to be you can have multiple workers on perci core。

 and the idea here is that with when one core or thread gets stalled because one worker thread gets stalled because the thing it needs is that on disk can'll fetch a memory or even if it's like a low level L3 cache miss you could have other threads run at the same time。

For maximal performance， this is probably the right way to go though and actually you also want to turn off hyper threading is run bare metal hardware threads because because we're going to be CPUU bound and most of the computations we're going to do in our database system。

 we don't want any contention on the actual hardware itself。Right。

There's other advantages in this for if you do like transaction processing or thing you keep you don't want any stalls but OLAP for both OAP and OTB。

 this going be the better way to go the Hanna guys are going to claim this is better because they're going to have really they're going to try trying to do fine great control what threads are actually awake and running at a given time。

But again we'll cover that later， and they claim that's be better for a machine with a lot of cors。

 I'm sorry， a lot of sockets， yes。4 one。Yes。But why wouldn't you want your course review？

So if you're compute bound。And you're careful about what you're putting in your CPU caches and youre prefeting things ahead of time。

 a core should never be stalled。Right。Again， we saw this with the branch of stuff like if you design the。

The system in such a way that you avoid misredictions and having to flush the pipeline of the CPU。

 then you usually just be crunching through data as fast as possible。

 and you should never have it stalls。Her brancheschessses， yes。Is per CPU cord per？系。Per core。

 but within that you turn off hyperthtting， so it's one1 hover threat。

It's like a socket can have four cores and each core can have two threads because a hyper threading。

So you turn off hyperthing and that's one core equals one hyper threat。

Avoiding contention is more valuable。He's running basically a bare metal。W。

 why don't turn off hyper thread in the whole system。

 like wouldn't you be able to then run little like you have a Ch job running or something couldn't you have that run on the logical what is that Ch job。

 what is this for I don't know you have a server running you have database on the server dominating the CPU it can handle all of the the sort of own all of the actual real threads that correspond to real core and maybe then the background path to the system can run on the unutilized parts of the。

What are these like garbage collection and stats collection or what are these background tasks not even part of the D？

Oh， randoms， like random stuff。Why would you run them in your database server？Well， I mean。

 presumably it's running on an OS right， doing something？Yeah， turn all that off。

 you don't want any of that。No， no。The core of question is why not be happy？

Is there any advantage to turn it off？Is there an advantage of turning it off？Yeah。

 you don't have two threads contending for the same hardware resource。Yeah。呃。I do have a graph。嗯。

My impression was that when you have hyperting on the other logical thread， the Sw core。

 it's going to only use the unUI part。No， what is the unutilized part of the core？

You have a pipeline of instructions。So when one gets stall。

 the idea is you swap out all the registers for this other logical thread， the hyperthread。

 and then they come in and pick up where you left off。Right。But like。Again if for CPU bound。

 there's not going to be stalls like that Yes， so we don't want contention just to summarize we don't want contention because when we have two threads。

If ifF， then we end up because they're fighting to the same hardware there'll be more cash at the other level the statement is if there's more contention。

 if there's more things running on a single core saying with two hyperthreads。

 then they're both trying to do something to men of work and they want things that you bring in the L3 cache or the in your caches and that's going to pollute it and then whereas been better of just laying one thread run to completion。

 yes。For your desktop sure because like you're browsing the web， listening to music， watching videos。

 there's a ton of stalls of that。 Who cares， right， But for the Davidism。

 you're not running random like， you know， Bitcoinin mining on it。 like it's no cron jobs。

 If you care about， know， if you really care about your baby system， right if it was a blog。

 you're running like My SQL Postgre just to service the blog， who cares， sure。

But if it's like a high end data system， like you're not letting anybody's SS into and run random stuff。

Right。啊。So right， so this is this is an older experiment that students did here at CMU where it was just sort sort of toy and memory engine and its it's distinguishing between。

Letting the database system decide where it actually plays data in a nu architecture。

 Does everyone to know what P Nuumma is？Who doesn't know when new is？Perfect， excellent， yeah。

 so so the idea is like， do you let the data system figure out。

 okay this piece of data is gonna to go at this core at this location or this numer region or you let the OS S figure out for you。

 And so what you see here is that before you get to the hyperfetting line。

 you're gonna get better scalable performance better funds when the data system control is exactly where the data is relocated because now data that's local to it。

 you don't have to go over the interconnect， which in some cases is going to be 2 X latency。😊。

So that's why this thing is come。Now to your point， why not leave hyperthreading on。

 this is when hyperthing kicks in and now you see you complete flat liness because a rather one because they're not it's CPU bound computation。

And in the cases when it has to go to memory to go fetch I'm going to fill its caches， well。

 if I'm running another hyperthread， it's going to do the exact same thing and now I'm not giving any benefit。

So here， I'm throwing， I'm throwing more threads at it， but performance is is plateaued。Yes。

 at some point you'll fetch from that。I mean， all of these are， right？All these affectioning from me。

But like， if， if I'm stall， like fetching for memory is so expensive。

 If I'm fetching for memory and I'm waiting for that， then you start running。

 Well what are you gonna do， Fet for memories。 You do the exact same thing I am。

So now you're blocked on the bandwidth of getting things from the dims to the CPU。Plus。

 you're puting your cash。Furthermore， you might， I， I mean， this is。

to talk to the architecture people。 But now you like。

 I don't know how well the Harvard prefe is gonna be because now like。

I would have been better off having one thread rippedrit through a larger chunk of data versus having two threads start different spots and try to prefetch those。

 Again， I think the hard prefeting stuff could probably handle that。

 But it's just making things more complicated。 Where if you keep the system more simple。

 you know we we can get better lose the utilization of what we have。Okay， so hyperthtting。ナイス。

In general， but not for databases。Okay， so we were。All right。

 so the next thing we've got to consider is how we're actually going to get our tasks to our workers and there's basically two approaches。

 either push versus the pool， in the push approach。

 there's some kind of centralized dispatch or schedule component has a global view a view of what the workers that are under its purview or administrative control。

It knows what tasks they're doing and then as new tasks arrive， it's pushing those requests。

 those task requests to the different workers， they always give them something to do and then when the worker notifies if badcher is finished。

 it's immediately going to be given here's the next thing to do。The pullbase approach。

 which is going to be the better approach， which everyone's going to do。

 is going to be that the some schedule a component that's maintaining the queue of all possible tasks that could be executed at any given time with additional metadata of maybe about what data they're trying to access and where' is that located and then now the workers when they need something to do。

 they come to this queue and get the next thing to do。And this is just easier because it's。

It's less coordination of or maintaining state about where each worker is in its computation。

 it just says， hey， here's much stuff to do， here it's a la carte and people can just come and pull things off for the buffet tray when they're ready for it。

Yes， which one has overhead questions， which one has overhead from what take too much time？

ally if you are a you has to go pulled from the queue that probably you CPU cycles and doing that So so his statement is there are actually two parts of it His statement is question is which one has lower overhead if it's the pullbased approach you have every work or thread going to say what should I be doing next on their own and that incur penalty for when they could be running queries Sure。

 yes， in some ways and the second aspect also too is like this cu thing which we'll see in the hyper paper is a global data structure which now you have to protect with latches or locks and then now everybody could be potentially contendant on that。

So。Everyone's still going to choose this just because it you can build this this schedule as a separate service and not worry about exact control or exact knowledge of what every single worker is actually doing because a worker may die。

RightAnd then now you got to figure out like that I told a bunch too bunch of stuff ahead of time and now can't do it where you just say。

 here's everything I need to do。 And then allow each work I thread to then figure out on their own what's the best thing for them to do。

 They're all sort of working globally to solve the problem。 Also less intelligent。

 isn't it the pullbased approach。呃。He says it's less intelligent， but relative to what。To this that。

 because you can have priorities。You can have the priorities in for one。

Just because hyper doesn't doesn't mean you can't。We'll see it in a second。

You mentioned the pushb approach like workers dying becomes an issue。

 how is it also not an issue' right if a pushb approach have workers die， you' got to figure it out。

 actually that' would be approach two and not approach one。You start the deal the point， yes。

 you're right， because you basically need a hardbe to figure out or they didn't come back。

Another way to think about it in the pullbased approach is that you can have the logic to figure out what。

 what。What task at the worker needs execute itself next is basically that logic is being distributed across multiple workers。

Whereas if it's a single centralized service， then it's one beefy box or whatever it has to have been。

 figure this out。I probably say that's the main distinction。Yes。I hope。

W so needs to keep talking about。Her question is， in the pullways approach as the schedule need to keep track of how long each task is going to take。

 yes， hyperper doesn't do that， we'll see this inumb。Her question is。

 can you can you use the same cost model as the query optimizer？U。

So the challenge there is because that some cost models in some systems。

You can't map whatever the cost estimate to like a wall clock time。 you ever looked at Postgres。

 it'd be like， it's some number。It's it's a combination of like。

 is this Sw scan Ram scan have much data than read and so forth。

 so I don't maybe people have tried this， but don't think you can't just take that number。 Oh。

 it's 10 milliseconds or something like that。 Now， the high in enterprise data systems do try to give you cost estimates to say's's the relative cost of the query。

 which is an internal value that you can use to compare different query plans， But inside the。

 But then also can spit out。 I think it's gonna take this amount of time。 So you could do that。

But again， we'll see this in a few weeks。 Cos models are always widely off。 So in the umbre。

 which I keep umb scheding that paper， which I keep alluding to。

 they're actually going to watch how long a task takes。And then use that to figure out。You know。

 to give a Rus estimate of like what discussion time should be for certain things。Okay。

So regardless of how we're going to allocate workers or tasks to to our resources in our system。

 as we said already， that it's important to make sure that the data they're going to process ideally is going to be local to whatever that worker is。

Right， and in the case of the， the hyper paperper， it's an end memory database。

 So local means it's in the same numa region。 obviously， in a distributed system。

 such with in a shared disk architecture， Well the cost of going get data from S3。

Could be basically the same for every single worker node。

 assuming you're in the same data center in the same region。 But once we start caching things。

 which we'll see later in the semester， like every note every compute note could have its own local copy of files read from S3。

And then now I want to when I assign tasks， I want to make sure that the task is assigned to the node that's going to have a local copy of that data。

 Yes， this is also another reason my poll would be slightly dumb because it doesn't know what if it just looks at a global queue and it's like give me the next task yes。

It's not necessary that the data that is needed for that next task is。Dead on next local storage。

 is David is the poll seems dumber because if the work is trying to。

maximizeaximize the locality of the data it needs to access。

 it can't do that in a pull waste approach， why not？Because it's just top know。

 you're not pop from the top what are doing？While the hyper does it one way。

 we'll see this in other ways， in other systems。哎。I mean， you have a priority， you。

 you don't always have the top from the top。Now， if you're doing work dealing you。

You may recognize that the thing at the head of the queue is not local to you。

 but you may want to go ahead and run it anyway because you're available。Hyper does that。

 I don't think Umber does， and Hanna doesn't。The party would be different。Yeah， absolutely。 yes。

 So it's not。 So it's a global cue in that。诶。In that， everyone can see it and manipulate it。

 but it it's not going to guarantee Fiffa ordering of， of the elements of the human。

So that's a priority you。In hyper， it's a hash table， right？Okay， so okay， I've already said this。

 like you could have some data systems will have locally attached storage as a cache like again。

 think of like you spin up an EC2 node， you can get ones with MVME drives that are local to that are really。

 really fast。And so if you use that as a local catch， it's ephemeral so if the note crashes。

 you don't need to retain anything in there。But again， while it's available。

 you can use that instead of having to go to S3。In some systems， again。

 snowflake is probably the most aggressive on this because again they don't want to pay Amazon S3 costs。

 they can also use other nodes as nearby cache。 So if you know this other node as for the data and you're running the task instead of going to S3。

 you could go directly to that node and get it， but they're actually not going to do that because they don't want to interfere with。

Then the other node because it might be going slow。

If you're stealing work that was meant for this other node， it's probably because they're slow。

 so why go start making requests of them to make them even slower？It's sort of the logic there。

And then the numer versus not uniform memory access stuff we've already talked about。

 like local versus remote memory。Yop sorry。Oh yeah， sorry， sorry。 Partitioning in placement。The。

 in the， the inter class， we talk about partitioning this idea of how do you take a data set。

And pick some set of columns or some keys， and then divide it up based on the values of these keys across different files。

 right？And that would allow you to spread out the data evenly， ideally across resources。

So that when a query arrives that can run in parallel， each worker can have the same amount of work。

 so they're all sort of processing things uniformly。

So there's going to be some policy that you're going to use to say。

 here's how I want to split things up， hash partitioning。

 round robin range partitioning and so forth， and then there'll be some target objective you're trying to have for sort of deciding how I want the reason why I want to partition things a certain way。

😊，So one thing could be I want to reduce the amount of network traffic when I do a join。

 so maybe I want to partition my tables on the things the join keys so that the joins can always be competed locally rather than have to do a shuffle or broadcast join。

In our world， in the shared disk Lakehouse environment。

 we're typically going to be doing round Robbin based on files。

Because we're not the ones generating these files， right someone loaded a bunch of stuff in S3。

 a bunch of parrquet orc files， we're not going to have time to go fix them up and put them。

 know partition them and rebalance them according to， again， some some target objective。

 Snowflake will do this， they call micropartitions。

 but I think they only do it for their internal data format。

Meaning like if you do insert queries to put data into snowflake。

 then they can rebound stuff later on。Repartition it later on。 But again。

 if it's bunch of files and S3， you can't rewrite them。 Yes。

 in addition to doing the values is your segment lake。Because we havet much these。

They're picking them based on like the quantity of ones in the files。

ition size or2 I so your question is for if you're doing round partitioning at the file level。

 what is the day students' actually doing， it literally is like file one go to you file two go to him。

 file three go to him that's it they're assumed to be uniform size question they seem to be uniform size。

Typically yeah， I think so yeah。嗯。I mean， obviously you can imagine to generate cases where I have like a bunch of one files and I have one1 terabyte file then that would screw things up and I don't know what they might break that up so forth I mean。

 the way to handle that one also two would be you could assign the same file to different nodes but then you just within that file you say。

 okay row group zero to5 goes this one6 to 10 goes to that one you could divide it up further。

 but I don't think they do that row groups makes more sense。

At least those are kind of like similar in size Yes， I could well again。

 parquets based on the number of tus or because based on the data size。

 but in the end it's roughly about the same yes。系。the same question。Like， is there any reason？

Split at the file level when doing round。Let like split further within a file no I like if we have five files why file 123 why that split is there some advantage to it beyond just like it's easy？

His question is if。Why do it split it based on the file， is there any performance advantage to it？

It's easy。I mean， you maintain less metadata， I have five files。

 I need five entries in my catalog to say where these files are if I start doing subdivision。

Within that。Then at the main more metadata， which some assessment can do， right？You know。

 if you're doing。Rang partitioning， yeah you got to keep track of where the ranges are if it's hash partitioning you actually don't need to do any。

 that's even cheaper， you could just say here's the column， here's the hash key whatever。

 know I want to hash on and decide where it goes。Now， if you're doing consistent hashing。

 which Snowflake does on the file level， then you've got to maintain that data structure to do consistent hashing。

 but we'll cover that later。So partitioning tells you how to split things up。

 the placement policy determines where those partitions are actually going to go。And again。

 the simplest thing to do is basically I got five machines， they each just get one file。

 which's around roing that。You could try to be clever of。You know。

 breaking things up in more sophisticated ways， we can know that this is the easiest way to do it So now in our catalog。

 we say like I have these to have these sizes and this about it。

 whatever I was able to glean when it was imported into my system or I was notified that it existed in S3。

And then I keep track of， okay， this worker is responsible for it。

So any query that shows up then has a task that wants to process that file， again。

 which we would determine in the optimizer with the catalog。Ideally we want the worker。

That's been responsible for that file to process that data。

whether or not that worker has a local cash or not is a matter， it's just we're just saying that。

Rather than everybody read everything， we can get more structured and say this node is going or this worker is going to read this file。

All right， so far we have a task assignment model， basically how do we assign workers to threads or processes and so forth。

 and whether we're going to a push versus pool from the scheduler。

They have data placement policy again。For our purposes。

 on a shared disk architecture and a modern lake house or datata lake system。

 it's going to be at the file level and round robin distribution。Then now we've got to say。

 how do we take a logical query plan and convert it to something that we can then execute？

And I've sort of said this looting as we go along， like we know where the pipeline breakers are。

 that's going to be the boundary for our tasks for the most part。

But then now how do we take those tasks and run them？So if it's an OLTP query。

 this is super easy to do because these queries typically only have one pipeline。

 do an index scan maybe a projection and that's it right there's not many operators in it and there's no dependencies between pipelines there's only one so that's easy we just hand that out and let them run as fast as possible。

But for OLAPque， it's more complicated because we know there's dependencies between these pipelines and we can't to avoid false negatives。

 we can't have one pipeline start running if the pipeline that is dependent ort have been completed to produce whatever the intermediate results that that are needed。

I see you can't always paralyze them。Yes， why does the previous slide say logical query？P。

But how did it say it？LikeBecause they' a lot。Yeah， you can say physically， yes。Yes。

If you just get rid logical， then it's fine， Yes， that's a typo。

Again the logical query plan says scan scan this I want to read this table doesn't tell you how to do it。

 It doesn't tell you if how to do a join。 it says in your join A and B。

 the physical query plan is the actual's like the exact algorithms you want to use。

 So when we create a query plan when we convert a query plan to much a task we' be doing that on the physical operators not the logical ones。

Thank you， I will fix that。All right， so the easiest type of scheduling to do is called static scheduling。

 and this is where again the optimizer out or the scheduler figures out in the very beginning。

 I have this query plan， I have these workers， and I have this data。

 and it does a static assignment of tasks to those individual workers。😊。

And doesn' the simplet way thing was I have one task per core or per worker。

 and they just all run at the same time。You still can assign the workers or the task to workers that based on the data's local to them。

But again， there's no dism， there's no adapting to the behavior。

 the performance of the workers as it actually processes the data。

Some you think of this generic Peco does this？So now the problem with this is that there's going to be some tasks are going to be slower either because the data that the processing。

 it just takes longer to execute whatever the operators that they have on it like you think of like。

I have a complicated wear clause where there's some predicate that is really fast compute。

And but can be very selective on some of the data。 And then the remaining predicates in in that where are slow to compute。

 So so9 out of the 10 files， all the data gets filtered out by that fast predicate。

 So those those tasks run really fast。 But the one unlucky worker that that that has all the data that does satisfy the predicate then has to run the more expensive predicates。

 And then it's just gonna be way slower than than the other ones。

 So now all the other workers have to M waits until that task actually finishes before they can move on to to the next pipeline for that query plan。

So there's no dynamicism in the。In any of the decisions that we're making here。

 everything's figured out ahead of time。So what morels is designed to solve is that exact problem。

How do we figure how do we on the fly dynamically adjust how we're executing or assigning tasks to workers so that if there's unexpected variations in the runtime of tasks。

We can have other workers fill in and start computing things rather than waiting for the slow strraagggr。

So the morsel's term comes from the hypergs because they were just looking for another term to mean chunk of data。

 they didn't want to use partition， they didn't want to use shard， they couldn't use block。

 because the morsels meant to be something bigger。But at the high level， it's still the same thing。

 you don'tm think the same thing as a row group。But I think this paper came out before the road group stuff。

So in their architecture， they're going to have one worker per chord。

 they're to turn off hyperthreading， they're going to have an assignment of one morsel per task。

 so task is a to your responsible for processing one morsel of data。

They're going to do a pull based task assignment， because they're going be this global queue that they're all going to try to pull from and figure out what to do next。

 and they're going to do really simple round run and data placement。And so again。

 they keep track of what p nuummer region each mors is going to be in。

 and they would annotate the task to say this task is going to execute this morsel on this morsel that's located in this numer region。

 then each worker that can decide whether they want to run a task that's processing data that's not local to it。

So they'll have all the operators be parallel and nu moreware that we can basically ignore。

 but it's can think of like having the exchange operators keep track of what inputs I'm waiting on before I can coalesce things to move on to the next pipeline。

So this approach here， this morsel paper came out in 2014 and it's fairly influential and this is actually what DuckDB does as well。

 and they're very upfront about this that they basically took this paper and reimplemented it in DuckDB and we had Mark give a guest lecture for us last year and the spring semester last year and they basically said they're doing morsal driven parallelism。

So again this is not just for。For hyperduct Bs know， widely used and is based on this as well。

 I meant to look out。 I think there's a couple other systems out there that are that are using a similar approach。

AllSo in hybrid， there's not going to be a single separate dispatcher thread。

 every worker is going to be responsible for figuring out what's the next task I need to execute。

So you sort of think this cooperative scheduling where everyone's working together for this common cause。

 this global trying to achieve the best performance of the system。

 they're working together to try to do that， but then the logic to figure out what's the next best thing for me to run is going to be distributed across the different workers。

So in the ideal scenario， they're going to go look in the task unit and try to choose a task again。

 that's going to process a morsel that's local to it。

If there are no local tasks that are available for the current query。

 then they'll go find what's the next task。What's the very next task。

 even if that data is not local to it， because again， that's going to be able to do。

Help mitigate the issue of stragglers， slowing everybody behind。

So now in the paper they're going to ignore a very key problem which I think I've already talked about in their approach。

 and that's going to be the synchronization cost of this global hash table。

 a bit hand wavy saying that it's not a big deal， but then when we see the Umber paper next。

 they basically throw it away and they switch to a more distributed scalable approach。

And in the case of the HaNna paper， which we're covering in a few minutes。

 they closely call out the hyper approach of having this global task queue when you have a large number of cores is going to be a problem。

What is it large number。Yeah， but I think I think it's a。4 socket machine。Right， I mean。

 for the Hanna guys， they're talking like 128 sockets， no more larger。Right。

 they even told me like they had this like before Sigma。

 they would have this like they invite to my database back to come you know season presentations from people working on Hana and they had one of their customers come in talk about how they were running on some beefy box where they were running out of a address space and X 64 because you have 64 bit pointers。

 but Intel only uses 48 bits， they were running out of space address takes of 48 bits。

And its running Ho。And that was a few years ago。 I'm sure people easily exceeding that now。So okay。

All right， so again， the high level idea is going to be that we have some data table here and there's going to be some arbitrary slicing it up horizontally into different morsels。

 and then each of these morsels will be assigned to onesca one numer region。😊。

So what does this look like what we already talked about with PAs？Row groups。Basically。

 the same thing， just a different name。So in there， this paper。

 they claim 100010000s per morel was the right amount of size。

 because that that gave them sort of the right amount of parallelism。And across all the cores。

 if you set it too small， then you always go to the task you and that becomes the bottleneck。

 if you set it too big， then you have the problem of again the stragler just you know。

 it's the only one that can process some giant morsel and everyone gets stalled for that。嗯。

When we built。When we were building our system Peloton here， we did 100 tuples per morsel。

 and then I think in the fall up system with noise page。

 we were doing 10 megabyte morsels because you could play some trick with in slot that do 20 bit pointers。

20 bit offsets but we can ignore that。All right， so now we have a query plan。

 we convert it into a bunch of tasks that we have in our task queue。

 and you start thinking in the task queue， again， it's what the computation of the operators want to do within the pipeline。

 and then it's tagged with what moresels they want to operate on。Right。

 so on each core now that each gonna have a a memory region that corresponds to the the morsels。

 And this is just the table space for for the tables。

 Then there's some local buffer they're going to use is to write out intermediate results。 Again。

 this is an in memoryory database。 So everything's all in memory here。😊。

And then you have it's all in your local memory， then you have your single core。So to get started。

 each of these guys are then going to go into the queue and pull out things that are going to process the data that's local to it。

 and then when now it runs again it's just computing or crunching on the data that's local to it。

 so it doesn't have to go to the interconnect on the CPU， everything can run really fast。

And then they're always going to produce the output back into their local buffer again。

 because they want to avoid the traffic over the interconnector， having right it some remote memory。

All right， so now say this this on CPU3 for whatever reason， it's just running slower。

In this case here， because there's no tasks that are available for this query。

To execute because the next stage， we have to wait for the output of the first stage or the first pipeline。

 So these guys essentially have to stall。 Now， if theres another query in our， in our queue。

 you could start processing that。 But then you get in this contention of like， okay。

 well I only have so much space for my buffers。 Do I to start processing another query that that can then interfere with the data。

 I want to store in my buffers。Because then as you start swapping things in and out， yes。

 these are CPUs。Individual cords。 so like this is all in one CPU， they have their own。

Its click one core。They have L1， L2。And then on the same socket， all the cores share L3。

 and then they have local memory。So I'm I'm drawing the CPU symbol。 I I could put thread whatever。

 like， but think of like one hardware core， y。All right so when this guy then finishes。

 this then frees up all the other guys， you can then go back to the queue and pull out again more tasks。

 and again， because we the last task that they executed for this query wrote data to their local buffer。

 we want to then have the affinity of making sure that the next task that's going to process that data that we just generated in the previous pipeline is going to run on the same core。

Again， avoiding that interconnect traffic。So now in this case here， say this one finishes up first。

So we do have actually a task， we actually could execute。 And so Hyper says that。In this case here。

 when you do work work stealing， it's okay for you to go across the Numa region to go get the data you need because it's better to do that than having idle resources。

Is there like a heuristic cost？Because it obviously costs something。Transition， yes。

 and like you don't。Like you can't ever predict like when that task on。

See our core three is going to like finish so like what happens if like our core three it like finishes？

S operating on that further。😔，So as David as a question is。

Is there a heuristic to figure out when is it actually O to steal， because it may be the case that。

Right before I steal or right immediately after I steal this thing finishes。

 then then I could have processed it。 and then I could have， know， processed the data located。

 And that would have embedded than this guy's stealing。Again。

 when it's on a single node and you're measuring things like the more cells are like 100000 tuples。

 you're getting down to like milliseconds here。 and the additional bookkeeping you have to do to figure that out。

 you would pay a high penalty for that。 a lot of overhead to maintain that they claim it's always better to steal。

In the case of Ha， they're going to do even more bookkeeping and they say don't do any of that。

And it's better。Don't do any steals because the cost is too high。

And I I getting a little confused about how stealing handles partial work。

His question is how could to handle partial work and work still？

Like because like presumably like core three did like get them out of work。The mors it's taking is。

So so every task is one morsel。So this guy' is processing whatever， this one here。

no one can take the same task because it's no longer in the queue。So when this guy。

 when one steals the next task。It's not processing on the same data as this guy。

 it's completely disjoint and separate。So there's no concern of synchronizing about partial results。

Oh yeah， the morsels are disjoint。Yes。Hyper these pipelines are compiled。It wouldduct TB， do they？

His question is in hyper， these are compiled pipelines， inductB， do they have compile pipelines。

 no they do？Have a chain upgrade。呃。W what's normal， yeah， it's a push based model。

But they're doing the vectorized approach of precomplied primitives that they right。Again。

 this is completely independent the query processing model here。

Does doesn't matter whether it's compiled or vectorized。Back yes。His question is。

 do you rebalance the intermediate results？Meaning like， oh， yeah。

If this guy steals a bunch of stuff and he keeps writing to their buffer， it's a local buffer。

 then is it going to run out of space？I don't I don't know what they do， I don't handle that。

At some point， I suspect you would， yes。嗯。Yeah， I don't have a handout， but you could imagine like。

Identifying that， oh， I can't。I'm running out of space， I can't process anything else。

 so either you don't process anything else until the query finishes， right？

Or you could introduce an internal task that then moves things around。

 but the bookke for that would be expensive。嗯。Yeah， I mean。

 that's one of the challenges in MM database is that you can run out of memory。

 I'm assuming I think they just assume that you don't。Yes。Major results。

So the statement question is at some point you get to aggregate immediate results， yes。

But that's the exchange operator that we saw before。And then in that case。

 that you can't really paralyze because this is one thread is responsible for pulling the data from all the children below the exchange operator and then coalescing that to produce the final output。

Okay。So。One of the key problems with U or with hyper is that because one worker is assigned to there's one。

Because there's only one worker per cor and one morsel per task。

 they have to do work stealing because it's almost like this。

It's not exactly static scheduling because they are allowing things to pull data as they go along。

 but they can't rebalance the amount of work that each task is doing。

So in the cases where you're blocked on waiting this last task you need for this pipeline。

Everyone has to stall until that thing finishes， right？

The other challenge I already said is they don't really talk about how they built their lock for your hash table。

 that part's a bit hand waving in the paper。But again， as we as we know。

 like that's going to be on you know， always going to be a contention porn。 lock free。

 it doesn't mean it's magically scalable。 It just means that you're never going to stall waiting for for you know。

 waiting to acquire something un unlock。 You may have to spin until you can acquire something though。

And now you're burning cycles。The other two problems they're going to have in hyper is that the。

They're going to treat the execution cost of every tuple in a morsel to be the same。

And as I said before， you can easily come up with examples where that may not be the case based on what the query is。

 what the predicates are。Right。The other issue is going be the guys。

 I think as you mentioned in the conclusion say， hey it would be nice to have you know。

 quality of service or priorities to keep track of these things， but they simply can't do that。

 It's almost a free for。 Here's whatever's in the， might task you。 And then and then the。

The workers are trying to pull things as fast as pop into just running it。But if I。

 that means I could have a。I could have a long running query。Take up all the resources。

 all the workers。While it's processing， and then I'm actually these short queries showing up。

 and I have no way to easily interleave them and make sure the short queries get processed。

And as we said， that's bad because people are going to notice when the short queries run slow。

So the follow up work to the Hy paper you guys read or an extension to morsels is this paper from 2021 on the new system that came after hyper called Umra Again。

 the background is that hyper was built by Thomas and his team at Tumminick。

They formed a little mini startup based on it， then they got acquired by Tableau。

And it was being used as the internal image query cache for the tablet the app， any time he used it。

And then tableableau got bought by Sal sourcece and so forth。

Thomas then lost control of Hy because Tau now owned it。

 So he went back and started building a new system called Ura。

And he couldn't use any of the source code he had from hyper， everything's writtenrit from scratch。

Because he's a freak and he can。This is the new scheduler that they built in Ura that is meant to overcome the deficiencies that they had in the hyper mortal schedule。

So the key things are that the tasks are not going to be created statically at runtime。

 and they're not going to have a one to one relationship between a task and a morsel。

 meaning one task can process potentially multiple morsels if it still has time available to compute things。

Right。So another way to think about this is that。They're basically going to be slicing up the computational resource based on time。

I have this notion quantum。 So within your quantum， you can keep processing as many tus as you can。

 and then when you run running out of time， then you have to get the CPU back。

 But I still think even though you give it back， you're still tied to the more so you're processing nobody else can take it。

The other thing we able to do to handle。To handle。Make sure that short queries aren't blocked by the longer run queries。

 they're going to do automatic exponential priority decay for queries so that the longer a query is running in the system。

 the lower priority it gets over time。And so again， it'll still be scheduled eventually。

 but its it's not going to be able to execute as many resources and a given time slices as a shorter run query who just arrived in the system。

So at a high level， this is a variation of stride scheduling。

 which I think came out of the 80s or '90s。 Do they teach that here or no， I don't think so。

Did he join OS？No， okay， think of like it's a。It's a sort of a primitive way to do scheduling in an operating system for tasks and processes where you keep track of how long things have been running and how much work they're going to do every time they run。

But in the original implementation， like there's a global， there's a global。You know。

 global priority list， there's global information that you have to maintain。

 and you assume that the workload is fixed， but obviously in a database system queries are coming and going all the time。

 and so we can't make that assumption， so they have ways to fix that。Yes， the second bullet point。

Eially growing the moral size is like to get like a lower bound on how long it takes to execute。

Or I get the task。How do you know how long it passed today？Before you execute it， you don't。

So the question is how do you know how long the task is going to take to you execute it， you don't。

 they just turn on like monitoring on it and keep track of it over time and so when they exponentially growing the morsel sizes。

 is it like they're just adding more data to the morsel Yes dynamically？

Or is it just giving them more morsels instead So you think of like the morsel concept。

 it's just a logical。Concept of like， here's the divider line of like one moresel ends and stops。

 So like if you recognize that each task is is computing each morsel really， really fast。

 then then then there's more bookkeeping。 you have to go back and get more know。

 give me the next task。 sort of increase what the boundary is for the morsels so that eventually the amount of work you do the amount of time it takes the process that moresel is one millisecond。

 you're not changing like given moreel after it's created。

 It's like for future moresels you're gonna make them bigger to better's the statement you're not changing moresels after they're created。

 you' just making future morsels bigger。 Yes， but again，Make sure we clear when we say creation。

 it's just a logical boundary， it's not like I'm copying data and making it bigger。

I'm just saying here's how to cut things off I'm don' you don't go back to somebody's already running。

 hey， here's10 more twos you didn't have before， you don't do that actually changing boundary was we're changing boundary already the boundary other things that haven't been for the remaining parts of the data table some sort small size that with。

Growing until。Like one of them takes longer than。Yes， saving is and he's correct。

 is it just that you start a small size and say， here's the amount of work you're going to do in a task。

 excuse the morsel it be 10000s， but then if you complete that in less than one millisecond。

 then the morsal size， so the next thing you're in to process will be a little bit bigger and you keep making it a little bit bigger until you exponentially bigger until your task takes more than one millisecond。

It might also be a bit of a non issue， but what happens if their starting amount is like takes like。

 for example， like five milliseconds to execute， there's never going to grow anymore， but're also。

However， it takes like a really long amount of time because for some reason they start。

His question is if when you start at1 billion tus per mesol and you're really big。

 could you shrink it， yes？W not， okay， I just like I didn't know if it was a part of like the system design because it seemed like it was only growing。

Yeah， but it's trivial to do， yes。Why do they want to invade？

Why do we want to do one millisecond run？Because it allows you to be more dynamic and not have a know worker just。

Aid this strangle problem。I think they。It's。ItsIt is doing work seal， but not in the。

How does it it is doing work together。Roughly， one a second， why do。

So it's work feelinging in that there's still going to be a global cube。

 but they're going to be clever how they maintain it。

 so when I got to say what's the next thing I want I need to go do？I got to go consider the location。

 the data plus a priority of what the next thing I need to run， right？Like in the morsels approach。

 it was this morsel has to be processed by this core， because it's been assigned to that。

And the work showing part is I'm allowed to run tasks are for data that aren't local to me。

So in this one， they're doing the same thing， but they're also including the priority information about the query itself。

So it is doing work seal。It's a natural， natural is not the right word either。

 It just sort of just happens because the way they're maintaining the cu。So why is the goal to？

says why iss the goal to make it one millisecond per task is to balance it， absolutely yes。

Is the priority like a sign before the cure accident or so on？mean we'll see part a second。

 The question is， is the party assigned when when the query starts， Yes。

 like everyone starts with like one。And the longer you run， then that decays。

How do you ensure that the short running was like finished well？His question is。

 how do you make sure that the short running query is finished more quickly and the long running querys keep running。

The show's only was like you guarantee the show only was like finished？Yes not。

 how can you guarantee it does not get started。How do you guarantee that the long run' doesn't get starved because the stride scheduling will handle that。

 there's this notion of a pass if I haven't。If this sort of global counter。

 this water market keeps ticking forward， and if my query is below that， then I'm La to run again。

And any new query that shows up， the shorter running queries that show up。

 they're going to be assigned a watermark that's above that global one， so they'll be stared out。Yes。

In the morssel based approach the morsels and buffers。

Prioritized like if there was data that could be processed with what is in the buffer that that task was prioritized for that given court Yes So here if the priority is。

will for each worker。The look added you。めました。So the question is in the morsulels case。

 the priority was based on what data I need to access in the morsul and where am I going to write it to。

 what in this case am I not having the notion of locality you do。

 and that would be you have a local priority， we'll cover that in a second。Okay。

So let's first describe how they're going to avoid the， the global。The global T Cu。

And so it still is a global taskcue， but the the state about。

Whether or not I need to refer to it to figure out what actually changed is we maintained in thread local storage at every worker。

 again， assuming we're running on a single node。So there'll be a global task set。

 but all this is just an array of pointers that tell you to go where to go find the information about the tasks that you have for a given query。

And then within each worker， there's going to be these masks that keep track of which slots in my slot array above are active。

 and then change mass and return mass， tell me whether something has changed up above and whether I should go confer it。

And so what they're going to do is they're going to have their different workers across different threads are allowed to go right into the memory of these this information for the other workers as well。

 but they're going to be atomic compare and swap operations just to flip bits or basically ex ors in the single instruction and that。

You know， yes， there's cacheline and validation across interconnects， but that's not。

 it's not like you're copying a bunch of data。 You're just doing one。You know。

 one comparing swap over the network。So my example here I'm going to show that we have four slots that could be active any time。

 I think in the paper they talk about have 128 slots。

 and that's just to bound how much work can be run actually running at a given time。 and again。

 the classical stride scheduling is you allow the number of slots is unbounded。So again。

 the global that slots， these are just pointers to where to go find the metadata in memory about what these queries are actually running。

So let's look an example of when query finishes and when a new query arrives or when a task set finishes。

So let's say that worker1 here， he's running Q1， test at one， worker 2 is running Q2 test at 1。

 so when this thing finishes。We then need to go back up to this task set slot array。

 follow a pointer to go look， say， okay， is there something else I should be doing for this task set for this query and let's say in this case here we've completed all we've processed all the morsels。

So we know that this thing is done。 So then now the worker is then responsible for them taking the next task set and we're putting that back in the queue right but now we need we want to notify all the workers that hey。

 something has changed in this task set queue up here so let's go find out what is because we we want them to pull it and not have to push it。

Because if youre start pushing things， you have to maintain latches to make sure that you're not overriding information inappropriately。

So all we need to do now is just update in this return mask。

 we just do a compare and swap at each thread to now say set a one to this slot。

And then next time the worker comes back around says， okay， I need I need to do something。

 I need another task to you compute on。 It knows that he needs to go check the task you to find out new information that somebody posted about it。

It' it's like a message board saying like， hey by the way， here's a change。

 I'm not telling you what it is， or it's like a new email notification。

 I'm not telling you what it is here， but you know where to go look for that information。

 so now let's say Q3 shows up query 3。 So it ends up getting put into the global task slot in this position here。

 And again， some other thread， like a scheduled thread or a coordinate thread is responsible for then flipping a bit in the change mask for all these。

For all these threads and say， hey， by the way， there's a new query just showed up in this slot。

And the distinguish between the return mask and they change masks because there's some bookkeeping reason you have to do this。

 Yes， well I don't understand。 I thought there was no dispatcher thread。

It's not a dispatcher thread like， hey， here's this task like。

There's something about ball that takes the query that shows up right。

 and somebody's got to then put that in the queue。So whatever that is。

So you could call that a coordinator or a scheduler threat。Right。But whatever that threat is not。

 it's not responsible for saying you're gonna to do this， You're gonna to do that。

 They're all pooling with themselves。 You just need something to flip a bit and say， by the way。

 like we， we added something new。 make sure you go check it out。In back yes。

This question is with the dispatchcher be responsible for flipping the bits and the return mask， no。

 as far as I know， the thread that was responsible for putting the data that compute the result is responsible for flipping the bits on everyone。

It question is， why not let the dispatcher handle that。

 they I got to go tell the dispatcher to go do it。It's just cheaper to go do it yourself。

I still on somewhere we're not doing cautious。His question is why aren't we doing push which is a pool because when the work is trying to pull from the global cost set starts。

 right？There is locking yes， which okay so we can't get rid of that。

 but it's wasting cycles we go and ask and look into the global tasks sets slot said hey。

 what do I need to do and if there is already a threat that's running and changing the bits it might as well keep track of what each worker is doing and then tell her to do some stuff。

So as David is。It's something already responsible for putting things in the global T queue。

Why did just have that thing for songs we're telling people what to do？But again。

 then you got to maintain that you have to maintain the state somewhere。

And they're arguing that it's better to distribute it across the different workers in T L S and have that be and then to do simple comparing swaps to maintain。

 you know， to notify them that the changes that are occurring rather than having a more heavyweight approach of like。

Farming out complex messages that they need to process themselves。It's cooperative scheduling。

 so rather than having one thread be responsible for everything。They。

And potentially that could be more efficient。To do like with a small number of cores。

 but this approach is to more scalable with a larger number of cores。O。Right。

 so then this thing knows that when finishes the task was running， goes back up， looks in the queue。

 decides that。for whatever reason that well get the information looking at the change mass and return Mas。

 what needs update， it updates its active slot now to say， hey。

 there's something in one I could go take and then it decides to run Q3 task at one。

And notice here now on worker2， it doesn't know about the Q3 yet。

 it just knows that if bit got flipped in the first slot and eventually when to go back a look at the test set queue。

 I'll go and learn what that is。So these things can run independently of each other we not having to coordinate across all of them。

Which arguably always going to be better。Alright， so we gonna have a few minutes。

I'll skip the priority to life， but basically think about as like。There's this。

There's this notion of this global pass， just thinking of the number of times I've passed through I've executed things and then I had priorities about initial queries。

 I have local priorities based on how much work I've done for this query and the combination of these things then determines what you want to run。

 but again the high level idea is that as a query runs longer， this priority decays and goes down。

All right， so I quickly zoom through Han， again， this is just a。

This is the other end extreme of complexity。 So thinking like Postgres is the easiest one。

 you just let the OS do it right the HanNA approach here， which again。

 I think it was a PC dissertation as somebody that that worked at S。

 so I don't think this ever actually made it in the real HanNA system。

 especially they rewrote it in the late 2010s。But just the idea is that like again。

I've had a disation to do even more scling on its own for individual threads and not let the OS do any of that。

So this is going to support both workload stealing and pool scaling。

 meaning within on a single socket or a single p nuumomer region。

 I can add more threads dynamically and not have the limitation of having one thread per CPU core。

I can start adding more and more chords if I think things are going to get stalled for a variety of reasons。

And then they have this notion of two different kind of cues of work that're going to have a soft cue and a hard cu。

 a harder cue that's going to be tasked that you don't want anybody to steal that has to run in that socket or that numer region。

So thinking of something like garbage collection for data that' that's in that Numer region。

 you don't want to have that go the interconnect or like a network riging task that has to run on a given socket。

 but the soft queue will be things that workers are allowed to steal similar to the hybrid approach when you're doing scans。

So I've already said this we're gonna to have the soft and hard priority cues。

 but then they can have four different worker pools of threads So you have worker threads that are actively running something inactive ones that are blocked in the kernel waiting for some kind of conditional lock or conditional variable a latch then you have ones that are free that I wake up a little bit to see what there's anything to do and then you have a part threads or you've actually deschedulule them and you hand them back to the OS kernel a sleep or yield and they just sitting down there and then if you need them you can spin them up and the argument here is that it's cheaper go put some threads down in the scheduler in the OS and let them to sleep down there so that when I need them I can pick them up and start running with them compared to having spin up a whole process I'll spin a whole thread if all of a sudden I need more of them。

So let me again let me skip this real quickly， basic idea works the same thing as before that we have a bunch of stuff we want execute for a query。

 but now I'm including some maintenance tasks like garbage collection for a multi Virg concur control because Hanna was MVCC system。

So。These queries here， they have to run， need to run right now。

 but they can go in the soft queue because， again， technically any numasaka and any region can run them。

But then the GCC staff say， we' put that in the heart to queue。

And then the working threads are going to be responsible for executing these active tasks。

 and then the inactive ones again， these are things that't that inactive is blocked on something that in the kernels that we we can't actually start executing them。

 but we expect them to wake up fairly soon。 Free is gonna to be one that are spending all the time looking for work to do and the park of the ones that are heavyweight paused down in the kernel。

So again。The free ones are allowed to pull this all the time and they find something。

 then it's allowed to execute it。So。The Hanna guys are going to claim that in their experimentation with this approach that it was better for the large so machines to turn off all the work dealing。

 you basically don't put everything always in the hard queue and that was always better than moving things across different newmer regions。

I would argue that， I think the the。I like this。 I like having all this stuff manage yourself instead of OS doing it。

And so。For the inactive ones。Again， for its OAP， maybe this is less of an issue。

 But if an O TP system， this， this makes sense。 And Han was trying to sports with OAP and O TP。

 So it made sense to have the sort of different variations and threading。All right。

 I'm going through this really fast。 I want to show you one last thing about in SQL server。

 because to me， this is。This is relevant for high design systems。This is an OSs。for。SG OS？

SQL because the background it's not full operating system。 right。

 So SL S is an abstraction layer in SQL server that they built in 2006 that hides the load level details of hardware and the。

 the operating system from the upper parts of the the database system。😊。

And the reason why they built this is that Microsoft observed that every time new hardware was coming out。

 they had to rewrite all their operating implications to account for whatever the hardware was。

 like you had a bunch more cord， they had to rewrite a bunch of stuff， they had a new region。

 they had to rewrite a bunch of stuff， and so this abstraction layer allows them to hide those lowlevel details and the scheduling and the movement of data can all be managed by this SQL lessoning。

 so it's not a full operating system。Like like the Linux kernel or Windows or Hbox， whatever。

 It's just sort of an extraction there。 But the cool thing that they're going to do is going to do non preemptive thread scheduling inside the D database system。

😊，What's another way for non parent thread scheduling。Coverines。Same idea， right？Where you have the。

 you have a thread that。You're， you're managing threading， multi threading within。

 within the database system itself。 But since， since it's not preemptive。

 like preemptive means the O S can go steal you take and take， you know。

 take your hardware thread and give it to someone else。It's we're all running。

 all these studies are running within the data themselves。 So we can't do that。

 We can't send it interrupt to ourselves like that， right， So that means that in our code itself。

 we're going to have to go put explicit instructions to yield back to the scheduler to say， hey。

 by the way， go check to see whether something else could be running instead of me。😡。

And they did this on Ti back in 2006 before C S and Go and other programming languages now have built on support for COV routines。

So there's a great article here how they built it。 I used to say that SQL S allowed Microsoft to make it to get SQL server to run on Linux。

😊，And I because I again， it abstracted abstracted the the US layer。

The guy that built SQLS then called me and said that's not true。

 actually their attempt to kind of get SQL server running in Docker turned out to be what got them to be able to support it。

 but this is a good article that talks about it again real quickly。

 let me just show you what it looks like So he has some SQL query like this they can set their quantum four milliseconds so say you want to do a sequential scan in this data。

Again， proxi query plan would look like this， eval predicate admit it。

 what they're literally going to do is keep track of the time different parts of the operator while they run。

 and they check to see whether the elapsse time since they started running is greater than the quantum for milliseconds。

 if yes， they yield back。Now， this is pseudocode。 You would not want to do this。

 This is like going checking the system clock is expensive。 Don't do that。 right There's。

 there's harder instructions to hide that for you。 But basically， again， if， if。

 if I know I'm running longer than I need to， I go yield。

 you can do this for other things in your data system， too。

 Like if you're gonna go try to acquire a lock。 the lock's not available。

 instead of your thread spinning and wait and try to cry that lock， you yield back。 But again。

 because the data system controls everything。 we yield back with not just like。You know。

 if you yield to the O S， what do you say， yield， That's it。 In the databases of being say。

 I'm yielding back to the scheduler。 And oh， by the way， I need this lock。

 Don't schedule me until that lock is now available。And when it does， the OS can put you back。

So we can have complete control of everything if we do this ourselves。

So SQL S is probably the first one that did this， there's other systems that do this now。

 SoliiaDB just has this framework called C star， Ph DB does a poor man's version of this。

 basically every time before they read something from disk， they just yield， that's it。

RightAnd then Corabase is an experimental system out of Simon Fraser University that explicitly does built title Co routines。

 And there there's a video from the S to be guys from a few years ago that talks about their C star thing。

Okay， we're well over time。Distributed scheduling， basically all the same problems。

 but now we're over the network。😡，I you laugh， that's really what it is。

 and then we'll cover workless steal dynamic scaling later， but we'll see this snowflake can do both。

Someubsessions can do one source or the other。All right， main takeaway。

 database systems are beautiful。😡，Don't let the operating system tell boss you around。

 Don't let the operating system try to do anything。 We want to do everything our。

 I think the S O S approach is probably the right way to do it。

 I think overkill what we're doing in this class， but。You know it's beautiful。

🎼What's that strong wheel2， Yes， next class， we'll do nothing but hash joins。

 And then on Monday next week， we'll do multipleway joins。

 We'll do a quick overview of performance counters that we talked about。

 There's other question about。 We'll do that next week on Monday。

 And then Wednesday next week will be the the project status updates， okay。😊。



![](img/ff628513ec0af0c8bc137cb083aa2fed_5.png)

St is six packs on the table and I'm able to see saying I。No short with the cross。

 you know what got them， I take off the cat but first I' tap one the bottom。

 go about three and the freezer so I can kill it， cat full with the bottle baby。

Because I said the pain lot sweat， you can get done with the guys in。Take back the pack of drugs。

No same now to T to the sun， Billy Dean to Phil peace to tell we guys。

 be a man to get a can of same time。