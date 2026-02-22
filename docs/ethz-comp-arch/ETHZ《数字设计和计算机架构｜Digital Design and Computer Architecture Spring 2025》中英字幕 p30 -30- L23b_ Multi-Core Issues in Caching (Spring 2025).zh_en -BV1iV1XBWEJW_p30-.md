# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p30 -30- L23b_ Multi-Core Issues in Caching (Spring 2025).zh_en -BV1iV1XBWEJW_p30-

Okay so let's talk about multicore issues in caching I want to spend some time over here because multicore imposes a lot of other interesting issues in caches and as we discussed all of our systems are multicore right so in this system for example L1 caches were private I believe L2 caches were also private L3 cache was shared across processors so even that's a design decision that you need to make right which caches are shared by which course。



![](img/8be4e782363a66df0a301bed30de1758_1.png)

And then do you design higher level caches that are shared， et cetera。

 so you're used to these pictures right now， I will mention this cache over here because its very interesting this is a shared cache that's on a different chip。

😊。

![](img/8be4e782363a66df0a301bed30de1758_3.png)

![](img/8be4e782363a66df0a301bed30de1758_4.png)

So basically they've decided to add these other， let's say。

Other chips that are bonded on top of a processor chip and the whole purpose of the other chip is to cash and there are a lot of actually really interesting technology issues like how do you align the interconnects in this chip with this chip over here so that they can actually communicate with each other nicely so there are a lot of fabrication and reliable tissues over here that we take for granted right now but these are two different chips bonded together on top of each other and the whole purpose of the second chip is just caching basically。

😊。

![](img/8be4e782363a66df0a301bed30de1758_6.png)

Caashching for all of those cores that are in the other chip， and there are many cores over there。



![](img/8be4e782363a66df0a301bed30de1758_8.png)

Okay。So basically cash efficiency becomes a lot more important in a multicore or multithed system if you have a single thread accessing the cache that's nice。

 you can manage it， but then if you have 10 different threads or 20 different threads or 100 different threads accessing the same cash。

😊，Now you want to be a lot more efficient。 The same is' true for memory bandwidth。😡，Actually。

 memory bandwidth is even even more important potentially。

So that's why there have been a lot of research in multicore systems or caching for multicore systems basically memory bandwidth is at premium。

 you don't want to go to main memory， you want to basically ideally hit in caches unfortunately doesn't happen and also a cache space the limited resource across cores and threats so both space and bandwidth are problems。

Then the question becomes how do we design caches in a multi core system， there are actually many。

 many interesting design decisions over here。😡，re theyShould they be shared or private across cores or threats。

 we're going to look at this one。😡，How do you maximize the performance of the entire system as opposed to just a single threat that we've been talking about so far？

😡，How do you provide quality of service to different threads。

 how do you provide predictable performance if some thread for example needs really hard deadlines because it could be a GPU for example it needs to display a frame on video frame for example on the screen and if you actually skip some things that's not going to be great for the quality of service provided to the user it could be a safety critical thing also basically there are a lot of interesting issues over here should the cache management algorithms be aware of the different threads accessing that right we have not talked about this so far but maybe yes。

😡，And how should space be allocated to threads in a shared cache。

 assuming that you actually want to do the space allocation across different threads？😡。

And then there are other issues like if the bandwidth is is at premium and if the space is at premium should you actually start compressing the data that's in your caches。

 it's actually I think an important area and people have been looking at compressing data inside the caches。

 compressing data inside the memory so that they can actually store more data。

 reducing the redundancy and waste in the data。😡，And also how do you do better reuse prediction and management than cachehes。

 we've been talking about reuse prediction and management。

 but do you need to do better in all of these。😡，And there may be other questions also。

 but let's take a look at one dimension of this， which is basically should the cash be private or should the cash be shared across course or a subset of course right you could generalize this so a private cache a cache belongs to one core。

 which means that a shared block can be in multiple caches。😡。

Whereas a shared cache cash is shared by multiple core。

 basically the L2 cache over here is shared by multiple call as you can see and if there is a block that's shared across those different core。

 it doesn't need to be replicated across different cache essentially if the cash is shared。

 a block is in only one place essentially so you can see there's one immediate advantage of a shared cache。

 it reduces the replication across different private caches right。😊。

So I'm not even talking about L1 caches as we discussed yesterday。

 L1 caches are really tightly coupled with the core， so the design decisions are。😡。

Usually oh it's obviously private right because it's part of the core right whereas L2 cash is out cash so maybe it's not private。

 maybe it's shared today some L2 cash are private some l2 cash are shared but L cash are almost always shared today well I should probably say always shared okay so basically this is the concept of resource shared so if you look at the private cash over here you're dedicating the cash to the core。

😊，And each core has a cache associated with it L2 cache。

But if you look at this other shared cache you're sharing the resource。

 instead of dedicating a hardware resource to a hardware context more generally。

 we allow multiple hardware contexts to use it so it could be core it could be thread because we have making a multi threadreading within a core also right so it's good to think about this。

😊，Essentially that's the concept of resource sharing and the resource sharing can be many things it could be functional units that are shared。

 it could be the pipeline that I shared if you remember the fine grain multi threadreading。

 we shared the pipeline， we shared the functional units。

 we share the entire pipeline essentially across different trends。😡。

It could be the caches as we've discussed， but also it could be the buses。

 memory interconnects and storage， a lot of those actually are shared across threads because they're too expensive to replicate。

😡，Busesses are expensive， memory is expensive interconnects and stored are expensive to replicate。

 so you do share them across different threads Cas are some of the caches may not be too expensive to replicate。

So what is the benefit of resource sharing， why do we share resources because it improves utilization and efficiency that leads to higher to put higher performance。

 why because when a resource is left id by one thread。

 another thread can use it right there need and also there's no need to replicate share data。

 these are two different things actually。😡，I've given you an example of instruction versus data caches yesterday right if you actually partition them。

 it's the same example basically you have two different cores core1 and core2。

 if you actually have private caches of 64 kilobytes each one core may be using one kilobyte of its own private cache another core may be needing 127 kilobytes。

 but if you dedicated 64 kilobytes and partition that across different cores。😊。

The core that needs 127 kilobytes would be unhappy。

 the core that needs only one kilobyte would be happy but it would be underutil its cache。

 so youd basically waste space because of this if you had a shared 128 kilobyte cash for both of them both of the cores would be happy and you would not be wasting space right and you would not be increasing the execution time with the same amount of resources so basically that's the advantage of resource sharing it improves the utilization and efficiency and hopefully that improves performance in the end and also there's no need to replicate the shared data which we also discussed which we're going to discuss when we talk about。

😡，Cash Co hand says well。But there are other benefits which one benefit is it reduces communication latency data shared between multiple threads can be kept in the same cache in multithreaded processors。

 for example， if you have a shared cache， for example you don't need to go to some other cache to get the data that's shared with someone else as we will see in cashquas you may need to do that actually it's in the shared location that everybody access that from that shared location it could be in the L2 cache but you could also think about this in the L1 cache right in the L1 cache you have multiple threads and multiple threads are sharing a cache block and they can access it quickly from the L1 cache。

😊，Okay and also this is compatible with the shared memory programming model because in shared memory programming model different threads actually communicate with each other using load and store instructions one thread stores to a location another thread reads from that location have you guys seen the shared memory programming model。

😡，Any courses， parallel programming， not yet。Somewhat， okay， who has not seen it？Okay。

 some people have not seen who has seen it。Okay we see almost 50。

50 over here who may have seen it but doesn't remember they have seen okay that's good it's good it's good that you're honest but in shared memory programming model memory is shared across different threads logically and also physically normally but whenever a programmer writes a program a thread can do a store to a memory location and another thread can see that store and load from that memory location that's how we can synchronize between the thread for example。

 we're going to look at that in cache coherence also and this is sharing of a cache is very compatible with that model right that model says there is a single memory and anybody can see that memory read from that memory right that memory it doesn't talk about replication of memory cache is private cache are essentially replicating pieces of that memory locally next to the processor。

😊，So it's in a sense it's not from a principled perspective it's not compatible with that model。

 of course it's compatible in the sense that this is all under the hoodr。

 you're still obeying the shared memory programming model from the software perspective。😡。

Okay so these are actually the advantages， but unfortunately resource sharing has disadvantages as well。

 one of the major ones is it actually results in contention for shared resources when the resource is not id another thread cannot use it basically because somebody occupied that resource。

😊，That's true for any kind of resource， it could be cache space， it could be bus bandwidth。

 it could be some memory space， it could be some storage space。

 basically if the space is occupied by one thread another thread needs to reoccupy it if it actually wants to use it。

😡，And this leads to reduction of performance， it could reduce each stretch's performance。

 it could reduce some threat's performance if you're lucky maybe it doesn't reduce anyone's performance because the block you're evicting is not going to be reused by the threat that occupied earlier。

 right， for example， right？😡，But usually at leads to some performance reduction for some threat or all threats。

😡，Basically threat performance can be worse than when it's running alone。

 and that's actually true in many cases。😡，There other issue which is different from this performance this is performance degradation。

 but resource sharing if it's not controlled leads to performance isolation or eliminate performance isolation。

 basically you get different amounts of cash space for example。

 allocated to you based on who's running together with you in the shared cache share you may be running with different application at different times so you optimize this beautiful application that you wrote it very nicely。

 you fit it in the cache in the L2 cache。😡，You thought you would have and when you run it with application A。

 you get that amount of cash or your performance is great when you run together with application B。

 that application B is very aggressive， It kicks out all of the cash blocks that。😡。

You need to have in the cash because you optimize your program and your program's performance is terrible。

😡，So this elements performance isolation， the programmer was programming or optimizing for hardware assuming that it would get some amount of cash right。

 but you didn't get that amount of cash because the resource was shared across different threads and the program has no control over that clearly the system has control over which threads are scheduled with each other and as a result all of your optimizations are essentially useless let me put it that way。

😡，So that's the importance of performance isolation。

 you may optimize your program and you may not if you get performance isolation in the resources。

 meaning that you actually get the assumed resources in hardware。

 then your performance is predictable across different rounds。😡，Okay。

 so this is the downside of not having performance isolation because you get very inconsistent results in terms of performance。

And also this creates quality of service， which is related to performance isolation。

 so if you don't control this sort of sharing， you can have unfairness or starvation。

 essentially some thread may be hogging the resources and another thread can be delayed indefinitely if you will。

😊，We're going to see examples of this maybe in a later lecture but I'm going to actually show you an example with the caches so so we could keep adding some more over here。

 but basically you need to efficiently and fairly utilize shared resources if you're actually doing resource sharing if you say I'm going share the cache you need to have mechanisms to do this efficiently and fairly such that you get quality of service and you get performance isolation if it's needed for the programs again we're not going to go into how to do this I'm just foreshadowing some of the problems that exist in modern systems in fact some processors quality of service mechanism incorporated into them right now Intel for example as a way of partitioning the cache across different across different applications and some amount of control on partitioning the memory bandwidth as well this didn't exist actually 15 years ago etc。

😊，Or even more recently maybe 10 years ago Okay， now let's analyze this private versus shared caches from this resource sharing perspective。

 as I said private cash cash belongs to one core， shared cash cash is shared by multiple core。

So what is the advantage of shared cash， you get high effective capacity anyone can utilize the big cash right that's good。

 you don't basically you don't have this fragmentation inside the cache。😡。

Because you dynamically partition the available cache space。

 there's no fragmentation to static partitioning and if one core doesn't utilize some space another core ca。

 so this is nice clearly。😡，And it's also easier to maintain coherence。

 We're going to talk about that because a cache block is in a single location， right。

 It's not replicated across caches， which means that if one cache one processor updates it。😡。

It's fine， everybody sees that update because it's shared， right so that's good。😡。

And we're gonna to see coherence a little bit more so the disadvantage just actually we have not talked about this。

 but if our resource is shared， you cannot customize it to the to a single processor for example whereas if you have a private cash you can customize it you can couple it nicely tightly with the core and it can actually have very high throughput whereas it's shared you need to have some sort of network to communicate between the cores to the cache right assuming the cache has a lot of banks for example to service so basically you get slower access in the end and as we discussed cores incur misses by evicting each other's blocks essentially these are misses due to interco interference if you will。

 and some cores can destroy the hit rate of other cores basically depending on the access patterns again one core may have very nice locality in the cache but it may be using I don't know 10% of the cash shared cash a very small amount of cash it may need a very small amount of cash the other core。

Maybe streaming through a memory and actually it needs 10 times the size of the cache。

 when they actually share the cache， the second core actually kicks out all of the blocks that the other core would otherwise have if it were actually running alone in the system。

😡，So basically that's what happens， I'm going to demonstrate this pictorially as well and essentially guaranteeing a minimum level of service or fairness to each core becomes harder because of this sharing。

 how much space do you provide， how much bandwidth do you provide。

 you to answer these questions actually when you're designing the resource。😊。

Okay let me give you an example basically if you look at this example， we have two cores。

 very simple thread one is running on this score and when it's running。

 it demands almost all the cash as you can see L2 cache。😊。

That2 is running on this other core and it demands some of the cash。

 let's say when it's running along。😡，And when they run together。

TThread1 occupies most of the cache because it may have a very intensive access pattern right and as a result。

 Tread2 gets much less than what it really needs to get high performance。

 maybe it gets nothing almost right because T1 actually can be very intensive in terms of memory accesses so it could be generating 10 requests at the same amount of time T2 is generating one request for example it could be1 hundred0 actually it could be very。

 very widely different as a result T2's performance may be significantly reduced due to this unfair cash sharing and this's a real problem in existing systems that's why you need to design the resources to be shared assuming you want the benefits of sharing。

 but also allow you should not allow this to happen in existing systems。😊，Okay。😊。

I could go on and on， but unfortunately we're not going to go into how to do that basically resource sharing and partitioning are at odds with each other sharing improves resource utilization for example better utilization of space partitioning provides performance isolation or predictable performance because it dediicates space to a single thread or single core the key question is can we get the benefits of both and the idea is basically design have sharing in the resources but design mechanisms in those shared resources such that they're efficiently utilized controllable and partitionable so you need to have mechanisms to do have controlled sharing essentially and the hope is that this way you have no wasted resource which is a problem with dedicated space partitioning。

😡，And you have quality of service mechanisms that you added to avoid the problems that you have with Sha。

😡，Okay。Unfortunately， you're not going to get the perfect upsides of both。

 but you're going to get most of the benefits of both if you do this。😡。



![](img/8be4e782363a66df0a301bed30de1758_10.png)

And again， we don't have time to go over this， these are more advanced topics。

 but you can look at future slide or take courses， etc。



![](img/8be4e782363a66df0a301bed30de1758_12.png)

Actually， there's a lot more over here I don't have time to cover， but these issues exist。😡。

Whenever you have shared resources and in modern systems resources inside the core are shared across threads。

 so there is resource sharing inside the core， there is resource sharing outside the core and outside the core after some point everything is shared across many threads imagine you have thousands of 1000 of threads and they're really sharing a me and memory bandwidth is limited。

 this is what we see in today's multi corere systems and GPUs for example or machine learning accelerator so basically there are a lot of issues that you see today。

😡，Okay， so let me give you another dimension over here。

 which is cache coherence how many people have learned about cache coher。

 let me ask you the same questions。😊，How many people have not learned about cash clears。

 how many people may have learned about cashques， but they don't remember。That's okay。Okay。

 so let's learn about cash clears because this is important so basically we have the shared memory programming model。

 as we've discussed， threads and parallel programs communicate through shared memory。😊。

Tread  zero writes to an address and thread one reads from that address。

 This implies some communication between two。 This is how you can communicate between threads and also processes right processes are actually larger entities which may contain many threads。

 So this is one example。 This thread is running on pro0。 It's writing to memory location A。

 This thread is running on pro one is printing memory location A。

 So there needs to be some communication as you can see over here。Now if this is the model。

 each read that happens should receive the value last written by any processor right otherwise you'll have inconsistency in the program and there needs to be some proper synchronization between the threads which we're not going to get into that's a higher level concern basically the programmer needs to synchronize these threads such that。

😡，There should be an agreement among the threads as to what does last written mean right you use locks。

 barriers， et cetera， to do this synchronization， which we're not going to cover here。😡。

So we're going to cover the issue with caching basically if you have memory location A that's cached in either processor。

😡，We have a problem basically， because the processors may not see the updates of other processors unless you do something special。

 which is called cash coherence essentially。😡，So the basic question is if multiple processors cache the same block。

 same cache block， how do they ensure that they all see a consistent state for that particular cache block right so we have two processors over here Pro one Pro2。

 they have private cache is cache 19 cache2 and there's some network through which they communicate to main memory and we're going to look at this particular cache block x whose value is initially 1000 right？

😡，So let's take a look at what these proor to， let's say proor 2 loads x into some register or part of x into some register。

 let's say the value it loads is 1000 that's nice the x is x get cache。😡。

What does that sound over here， Am I doing this or？No， it's just the tick tick sound。Then no。

 maybe this is too close。Okay， so basically this。This location X gets cached in this cache。

And let's assume that processor1 does the same thing， it loads x into its own r2。

 and this location gets cached over here。😡，And then Pro 1 does something else。

 it basically updates location X。😡，And this update gets reflected in the cache。

 it's the right back cache， let's say。Now you have inconsistency， right。

 main memory is not updated and this cache is not updated。😡，Then the question is， what should？

This processor load when it loads x， should it load 1000？Actually。

 the easiest answer should not load 1000， but this also depends on something else which I don't want to get into which is a memory consistency model but。

😡，Intuitive answer is really， this should not load 1000 right。

 because well you got updated before you actually。Should read 1000。

You should really get the most up to date value。😡，Assuming the program is synchronized in a particular way。

😡，Make sense， right？That's the intuitive answer。There is a much more complicated answer that requires you to really understand memory consistency。

 but that's something you should really look at in advanced courses。Okay。

 so a basic idea is how do you actually ensure that this processor doesn't load the wrong value？😡。

That's the basic basically。 Well， the first idea is basically whenever this processor does a right。

It broadcasts that it's going to do a right to that block。😡。

And everybody who has the block and their cache invalidates the block right this is this is a very basic cashques protocol。

 It's a broadcast based cashques protocol。 You should not write to this block until you're sure that everybody has invalidated the block。

😡，That's one answer， the other answer is while youre writing to the block。

 you also write all of the other caches blocks。😡，Basically。

 you broadcast the fact that you're writing and also the data that you're writing here。

 update your cache block because I'm writing to it。😡。

That's the idea so that's the idea of a broadcast based protocol。

 a processor or cash broadcasts its write or update to a cache block to all other processors。😡。

And another processor or cache that has the block either invalidates or updates this local copy of the block。

 right？😡，So then the question becomes we invalidate to update we're not going to get into that that's a more advanced question。

 but if you invalidate that's enough basically and if you ensure that there are no race conditions meaning that someone else doesn't read the old value of the block before that right actually happens then this should be okay okay that's the idea basically and this works nicely if the processors are connected through a medium or caches are connected through a medium where broadcasts are immediately visible to all of the other caches which essentially a wire right which a bus in this case okay。

😊，That limits the scalable of these protocols in general。😡。

So let me give you a very simple cash coherent scheme， I'm not going to go into detail。

 but because it implements whatever I said basically whenever a processor writes to a cash block。

 it sends a broadcast message saying that I'm writing to the cash block and everybody else email is a cash block if they have it in the cache。

😡，So all caches somehow observe each other's rights and read patients if pro their writes to a block。

 all others inate the block。😡，So a simple protocol with some assumptions you can study this long year own。

 local processor can do read or write to the cache block and based on those actions。

 bus read and bus ride are broadcast on the bus for the block。😡。

And this is what the protocol looks like， it has two states because it's a right through cache。

 it doesn't have a dirty bit。😊，That's the simplest protocol So basically you have a Val state or in Val state if a processor。

😊，Rightites to that cache block， it has to be well hopefully then it sends a bus ride signal。

 this is the input， this is the output。😡，And whenever processoror sees a bus ride in its valve state to a given block。

 it makes a block in weld right this is a very simple state machine that you're used to right now and that's the idea basically with these assumptions this is a working coherence protocol each and you didn't really increase the number of bits that you have in the valve bits。

 let's say normally in coher protocol you actually need to increase the number of bits if you will because you may need to track modified for example an exclusive etc。

 but we don't have time to discuss all of those。😡，Makes sense， right？Okay。

 let me give you another coherance protocol we'm not go into a lot detail。

 but I have to cover this because modern protocols are a combination of both。

 they're both broadcast based， but they're also directory based。

 so the idea in the directory is have a middleman have a middleman arbitrate updates to a cash block or request to a cash block and that middleman is called the directory。

😡，That middleman is logically centralized， but of course， if you want to scale a system。

 you don't want centralized components， so that middleman is usually physically distributed。😡。

Across different memories， but we're not going to talk about that， essentially。

 imagine a central directory that keeps track of which caches contain every possible cash block。

Every cash before doing something to the cash block consults this directory and ask for permission。😡。

Basically， I want to write to this Ca block X。😡，Can I do it？

It basically goes to the directory in this case it's next to the main memory but directory can also be cached actually next to the caches。

 so that's very fascinating， you can cache the directory that provides cache coherence so caching is so powerful because this is actually huge this thing is huge and if you take the computer activation card you'll calculate the size of it and you'll see that it's huge but basically whenever you're writing to x Proor  one wants to write to X Proster 1 says I want to write to x directory please give me permission and the directory says okay。

😊，Let me see who else has x because it has a bit vector that keeps track of which other caches in the system actually have X。

😡，Which means that you need to have a bit vector or some data structure for every single cache block in the system to keep track of who has that cache block in their caches。

😡，As assumings that you have that data structure， director says， oh。

 I think I know that Ca2 actually has Ca block， I'm going to send a message to Ca2 and ask Ca2 to invalidate that cache block。

😊，And after it receives responses from all of the caches that have the cash block。

 saying that they've been malated the cash block directly tells Ca1 or2er one， go ahead。

 you can write it， you have the only permission。😊，Or the only copy。

Makes sense right so this is basically a middleman clear this middleman is costly because you're going through a middleman there's an indirect and as a result the latency of the square scheme is much longer than the latency of what we have discussed over here right here some one processor broadcast everybody sees you don't need to go through any middleman so that's much lower latency。

😡，But this is not scalable because if you want to actually have 200，000 processors。😡。

Connect to a single bus， good luck with that。Even more than 16 is not easy， unfortunately today。

 but we have today multiproors that are on the orders of tens of thousands right that are connected to each other and that's why well this is the reason why we have things connected assuming you have cache coherence of course right so I will not go into this detail but whatever I describe applies an example mechanism looks like this for each cache block and memory use store p plus1 bits in the directory。

😡，And that's costly now imagine doing a calculation of this what's the size of the directory if P is the number of processors that you have in the system if you have tens of terabytes of memory。

 if you have cache blocks of 64 bytes， you divide 10 terabytes by 64 bytes and multiply by p plus1 that's the number of bits you have in the directory。

😊，That's actually lot larger than your cache is actually in fact。Okay。

 but assume that you have it somehow， you have one bit for each cache indicating whether the block is in the cache。

😡，That local cash or local processor in this case processor and cash can be used interchangeably because we're assuming a processor of private cash and we also have another bit exclusive bit saying that a cache whose bit is set has the only copy of the block and can update it without notifying others。

😡，So there could be optimizations that you can do basically， you can。

 this directory can grant permission to a cash that's requested to update a cash block saying that。

Okay， you have the cash block， you can update it。😡，Until I take every York furnish。

And you don't need to notify me while you're updating this because I guarantee that no other cache had this block has this block right so basically you can do a lot of interesting optimizations with the directories。

😡，So on our read， the directory， the cache sends a message to the directory and the directory says the cache is bit in the directory entry for the block and arranges the supply of the block into the cache。

😊，If it was updated by some other processor， for example。

 it takes the data block from that processor and gives it to the processor that's reading it， right？

😡，And on the right， the directory makes sure that it invalidates the block in all caches that have the block and resets the bits of those caches in the directory entry for the block because it's going to give the cache block to someone so that someone can update it。

 right？😡，And we have an exclusive bit associated with each cash block in local caches so that the cash can know to update the exclusive block silently without notifying the directory。

 so if it got permission for this cash block from the directory。

 it sets its bit called the exclusive bit in the tax store。😡，Saying that， oh。

 I'm accessing this block and the exclusive bit is set。

 which means that I know now that I'm the only cache that has the copy in the system and I can silently update it without going through the trajectoryy。

😡，Okay， or I can read it also without going to the， right？Okay。Make sense。

So now you know the two basic coherence methods， it's important to know why I think this much if you want to know about optimizations you'll have to take the future courses and this is。

 for example the state machine for each cache block that's implemented in Pentium Propro it's called the Mei protocol the protocol that I showed you was Valald in Vald。

😊。

![](img/8be4e782363a66df0a301bed30de1758_14.png)

Actually， with the directory， we looked at an exclusive bit。

 Mei is there are four bits basically four states in well state。

 exclusive state shared state and modified state for each cash block basically exclusive means basically I have the only copy of the cash block so I can write to it。

😊。

![](img/8be4e782363a66df0a301bed30de1758_16.png)

O。