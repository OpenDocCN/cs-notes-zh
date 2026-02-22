# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p28 -28- L23_ Caches II and Prefetching (Spring 2025).zh_en -BV1iV1XBWEJW_p28-

![](img/f9f1b92c80b3f04900590a0444589418_0.png)

I'm speaking something。We have time。ですそす。完有多少。系。你你。🎼不。え？な。Nice stream is on。有。Okay folks。

 so let's get back from where we stopped in the last lecture so。

I'm going to be today's lecturer for you。So that's me。

 I'm a senior PhD student in working with Profesor Molow in the Safari research group。

 so I predominantly walk on micro architectureitecture memory subsystem design with some data driven micro architectureitectures。

 I might be showing some examples in this lecture which you might feel interesting。😊。

Okay so this was the reading for the last lecture also for the cash you know lectures on cash we are going to jog some memory here why do we need caches because you know as we know that we need both fast as well as large memory right so typically these two tradeoffs are kind of at odds with each other so if you make it faster then it becomes typically smaller but then if you make it larger then it becomes slower so we cannot achieve as I said like both of these with a single level of memory so that's why we have caches as well as you know multiplelevel of caches which is then finally backed up by the main memory so that's kind of one example memory hierarchy like we have multiple levels of caches L1 L2 L3 cash and then then followed by main memory right and then then you can think of many other forms of memory also let's say main memory is further backed up by the disk storage and then in many today's commercial processes they can be also have。

you know remoteote memory and many more levels but as you can see that the more you go on the lower like the farther you go away from the processor。

 then you have bigger capacity， but at the same time it comes with you know slower access time that's a high latency so the idea is that how can we make this intact cache hierarchy you know as fast as possible as well as as big as possible。

So recall call that there are some know take terminologies that we had covered in the last lectures block is the granularity of the cash accesses that we have right so and then you know the cache has the concept of cache hit when you are looking for some data in the cache if it is already present that's called cash hit if it is not present then that's called cash may and then we have multitude of design decisions which which affects how the cache hierarchy is going to perform like some of the design decisions are like cash size granularity of the cache management which is the cache block size and I'm going to show you some examples like how cash block size is going to affect the performance of cash replacement policy placement policy everything essentially you determines how the cash is going to behave okay so with that set let's let's you know the goal of today's first part of the lecture is going to be finish the cache that we have started in the last lecture and then。

😊，Going to move to some other form of let's say it and see hiding techniques in the later part of this lecture So let me start with how exactly we design the cache and what sort of parameters that we are looking at and how these parameters affect the cash performance so performance is kind of sometimes it's hard to measure what would be the workload performance if you change any of these parameters like the cache size block size associivity but the easier metric to argue is the cache hit or mis rate so that's what I'm going to show you here so how cash hit mis affects or let's say cash size affects the cache hit so this is one figure likes a very let's say industry looking figure without any numbers on the axis so you have cash access on the X axis hit rate on the y axis as you can see that the more cash sizes you put in the system at some point it it won't give you any further hit rate so。

That point is what we call the walking set side of the workload is entirely fitting inside the cash rate so then if you increase the cache size even more。

 you won't see or let's say you would see marginal improvement in the cache hit rate so so that's what we are saying here that if you have too large of a cache then then obviously you need to keep in mind that the bigger the cache the slower it would become but then if you also become if you also make the cache is too small。

 then it won't explore the temporal locality， it won't exploit the special locality also then useful data would get replaced so then that would also decrease the performance so ideally what you want to do you would want to make the cache let's say as big as or as small as fitting the walking set size so then your life is good then the data that the workload is touching is kind of fitting inside the cache that's the sweet spot that we want to walk on。

What's the definition of the walking set so walking set is essentially you can think of it in this way that the entire set of data that the workload is touching at a specific time interval of that workload so the workload can actually run for a long time but then we are not entirely caring about the end to end workloads data footprint but then at a specific given time what is the data access or what is the amount of data that the workload is accessing so that's the working set set and then that's what we want to fit inside the cash hierarchy。

😊，Now as you can easily guess that there is no single walking set size and life would have been much easier if that's the case and so as I said。

 like the cache size and the walking set side would also vary from workload to workload so here I'm showing some example like how that happens in real workload so on the y axis sorry on the x axis you have the number of ways from one all the way up to 16 so you can think of it in this way that the more you go on the positive x axis you make the cache as bigger and then then the y axis you have the misses per thousand0 instruction so。

😊，Ideally you would like to see as low as possible right So in this case this is one example and that that workload this example is coming from the paper that I'm mentioning over here。

 So as you can see that in this case， if you increase the cash associivity from one to 16 So that means essentially you're making your cache is 16 times bigger this specific workload it does not bulge at all from the misses So the misses are not going to zero the misses are still existing but it's not changing。

 So what does it mean it means that either your workload access pattern is so that it's not the caches are not getting beneficial。

 even though you have make the cache really big or it can be the case that your workloads like walking set size is so big that even a 16 time larger cache is not going to contain。

 So that's why you are not seeing any drop in the misses per but that's one example So there can be another example of the workload So in this case let's say this workload。

Shows like decent you know reduction in the basis right so as you make the caches bigger and then there is another type of working like access pattern that you can see that in this case that you know once you increase the cash size to be let's say four times or eight times of the the baseline then you would see marginal improvement in the cache have a misread because it already becomes near zero right so that's the you know most type of workload access pattern that we kind of see in the workload in the wild also so thats that's just to show you that there is no one single one size fit all strategy so you need to design cash that kind of you know caters all different types of workload access pattern as well as workload demands so that's hopefully you know I can convince you with this okay so now let's see well like what the caches。

Performance， how the cash performance gets affected by the cash block size， right， So， as I said。

 like the block size is the， the data that is you know tagged with the the tag itself。

 And in this case， let's say the block necessarily need。

The block size do not necessarily need to be the minimum quantta of data transfer between the memory and the cache hierarchy like we have covered this in the last lecture also that you can have let's say super cache block with you know tags inside right so that's what we call the subblocking but in this case like for this you know sake of this discussion think of the block size itself is the minimum quant of transfer that we are looking at right so that's the entire block size so if you have too small of a block right so in this case on the let's say lower part of the X axis then you the more the cache。

😊，Block size that you are increasing the more spatial locality you are exploiting from the cache rate。

 So essentially saying that I'm fetching in task 64 byte at once。

 So that means my anticipation is that if I'm touching any cash any data in that 64 byte I'm supposed to touch let's say some few more data in that same 64 byte So that's the spatial locality that we are exploiting in this case So the more you increase the cache block size the more special locality you are exploiting and then you would also expect that the hit rate going to increase depending on let's say if you workload is also spatial locality friendly but then if you have too small of a block so but at some point at some point the more you increase the block size。

 the performance would tap up。 So let me justify like why is that the case so as I say like if you if your block size is too small then you won't exploit this。

😊，Loality you would also have a larger tag over it so that's why the more you increase the cash block size。

 the performance increase that you would see in the beginning。

 But then once you start making the cash block really big then you would have let's say you you are literally probing into the extreme end of the special locality So you are anticipating that let's say instead of making 64 by cash block if you make it let's say two MB cash block nobody is stopping you from making that big cash block。

 but then you are betting on this fact that if you are touching any data in this two MB region。

The other data in that same region is equally likely to get access right that might not be the case for every workload if it is for some workload then it's like you are making a correct decision。

 but if it is not then you would actually see performance drop because this huge block it would take a lot of time to transfer it would also waste energy it would waste the cash space bandwidth everything right so so that's the sweet spot that we want to operate on the cash blocks size should not be too small of you know to exploit special locality as well as it should not be too big to waste the。

The energy and then the bandwidth also。Okay so similarly associivity also has impact heavy impact on performance and then I guess you have seen something similar on this graph in the previous lecture so as you can expect that if you have larger the associivity you would expect to go the cash misses to go low because then you would less you have less conflicts right but then at the same time if you have smaller associivity you would actually end up having more conflicts you would get less access time because now everything is quickly you can get the data quickly you can there is less comparisons to to be made which I believe that we have covered in the last lecture so there less comparisons to be made so that that kind of makes the cash architecture efficient but at the same time you would also see let's more misses coming from the conflicts so here is one you good question that I want to ask you like so associivity when we talk about。

😊，Associivity， many of the computer architecture related parameters are typically set in power of two。

 so do you believe that the associivity needs to be power of two？😊。

Who thinks that it should be part of two？Anyone？Or who thinks that it can be anything other than part of two？

Okay I can see some hands over there okay so the answer is correct that way you can literally have nonpar of to cache so and in fact we'm going to show you some example that even commercial processes that we have today they contain nonpar of two cache so how can you use it like nonpar of two cache from this let's say the architecture that we have looked at before so if you have let's say this is the typical architecture for four way cacheivity so you have tag matching logic on the top and whatever the tag match is then you are going to feed that signal to the multiplexa the multiplexer is going to select which the data that you should be reading from the cache ways right and if you want to make this cache architecture of three way you just simply drop one comparison。

😊，So similarly if you have let's say here I'm showing some another example of eight way fully associated cache right so you have eight way tag massing logic that gets fit into the multiplexer and then the multiplex selects which data block that you want to access but then if you want to make it seven way cache asciative you just simply drop another way so what I'm trying to point it as that associivity is not something that is needed for let's say example indexing the cache right so that's why we don't need to have a artificial constanttrain that it needs to be let's a power of two you can literally make cache associivity any anything which is also not power of two but the caveat is that if let's say in this case if you want to have a nine way fully associative then you unfortunately to go to the next part of two and then reduce it down from there so you need to support a 16 way associative lookup and then you just simply get drop of the assoivity that you' are not using but it's possible this is one example。

😊，know it's a pretty recent micro architecture coming from Intel that's called lime Cove and I'm pretty sure like all the ultra series processor you might be having laptops shipping nowadays they have nonpar of two cash asivity like for example this is 42 48 kiloBs12 way as well as the last level cash that this process has it's also 12 way associated so it's possible。

😊，Okay so with that said I'll go to some some other aspects of the cash performance right So what type of cash misses that we typically look into in real life so so there are three Cs in cash performance so one is compulsory miss capacity miss and then the conflict miss okay so let me define like what are these three misses there is another C here。

 which is called coherence miss which is probably I'm not going to talk about in this part of this lecture but yeah so essentially there are four Cs of cash performance but then three Cs I'm going to show in today's lecture So what is compulsory miss compulsory miss means that you are going to touch this cash line for the first time in your life the program is touching for the first time so you have not seen it before。

😊，That that's going to be missed right so unless you have any speculative technique going on the first access to any cache line is going to be missed because it's not there。

 you would cash it and then subsequent access to that cache line is going to be that's the whole idea right so the first access is to a cache line is is what we call the compulsory miss because we cannot hide it unless we have any any other mechanism which we have I'm going to show you in the later part of the lecture and but yeah。

😡，But then we then we have something called capacityac miss so what do we mean by capacity miss capacity miss as the name suggests is that any misses that are coming from purely by the fact that the cache is not too big okay so this is defined in the following way and by the way there can be cyclic definitions of these two saying that okay capacity misses this we can define conflict ma and and then we can say that okay anything that does not fall into these two category would be capacity miss but then I'm trying to define the capacity miss by itself so it is defined as the misses that would occur even in a fully associative cash。

😊，With optimal replacement policy of the same capacity。 So it essentially says that your。

Associivity is not a problem in for this miss so essentially you cannot reduce this miss even if you make it fully asci because this miss is still there even after making it fully associative and with optimal replacement policy also so capacityac miss is truly lying from truly stemming from the fact that your cash is not big right and then conflict miss essentially is anything that is not between these two right so you can think of a conflict miss as that you have in reality you cannot you might not be designing a fully associative cash that means you are making it associative so that means once you index in the set then only there are a handful of possibilities where you can put the data right if you're putting some the data in some place you are essentially evicting something out who is already there so that's the conflict miss okay so that's three definitions of compulsory capacity and conflict miss。

And there are avenues to reduce each of these mis types as I said like compulsory miss it's typically not easy to get rid of it unless you have any sort of speculative mechanism that anticipates before so that's what prefeting does which is I'm hopefully going to cover in the later part of today's lecture is if you can anticipate at door your program is accessing let's say cashline a a plus2 a plus4 a plus6。

 if you look into this pattern you can easily identify the door there is a stride pattern that is going on so I would anticipate that if you access a plus8。

 then a plus 10 is going to be accessed a plus2 is going to be accessed a plus 14 is going to be accessed and then you are going to fetch the data even before the process that demands it so in that way you can get rid of compulsory miss because those cache blocks which you are predicting they have not been touched by the program before so you are anticipating ahead of time and you're fetching it on the cache so that when the program actually wants it you would。

😊，the cache so that's what prefeting does and I'm going to cover over there。

 So there are avenues to reduce conflict misses also for example。

 the easiest way is to increase asivity， but then asivity also comes with its own drawback of power as well as energy but then there are other ways for getting more asivity without even making the cash actually fully asative then like some examples are here like victim cash randomized indexing which is I'm not going to cover into's lecture but if you're interested you can look it up and then there is capacity like avenues to reduce capacity miss which essentially says that okay we need to we need to utilize the cash pay better so that is directly related to how exactly we are writing our program that's what I'm going to show next so we as a programmer we can reorganize we can rewrite programs which make better use of the。

Liitted cache capacity That's one thing or the second thing that as a hardware designer you can do is you can employ better a replacement policy but a placement policy so that you can utilize this limited cash capacity more effective so yeah so thats that's with that in mind so I'm going to just quickly touch upon that how exactly we want to improve the cash performance so so every improvement in cash performance they have like three fundamental goals so we want to either reduce mis we want to reduce mislatency or mis cost so that means that time that it takes to solve a cash and we also want to reduce the heat lat so the time that it takes for to solve a data well when it is found in the cache so that's the three fundamental goals that we would be working on how can we do we can reduce misread we can make the cache is bigger but then you can easily。

ipate that all of these let's say tradeoffs they would come with own own caveats so as I can show like if you want to reduce misread。

 then it can also reduce performance if let's say costly to fetch blocks are kind of evicted so you wanted to fetch some data put it but that's also evicting some data outside So that's if that data which is getting evicted is costly then you a problem and as I said。

 like all of these optimizations， they are very hard to come up with that improves all of them let's say so thats that's I'm going to show like some examples of how we can improve cache performance by optimizing some of these matrix so reducing misread there are lots of how we can reduce mis more asivity like alternative to asivity as I mentioned but then there are software approaches also and then。

Using mis latency missed cost is also you know there are lots of lots of avenues that we can do and obviously you as a software programmer writer you can write better program if you know that there the cash already exist in your system to make use of you know the cash utilization better so I'm going to show you some examples of how we can write programs to you know if you as a programmer you know that there is cash and then most well like。

😊，Any computing system or most computing system that you are going to interact with in your lifetime it tend to have cache so if you know that this computing system has cache then how can you rearrange your code rewrite your code so that you can make better use of cash so theres lots of avenues to do that I'm going to focus on some of these that I'm showing over here by restructuringing data access pattern restructuringing the data layout like loop interchanging and some blocking I'm going to show examples of what exactly that doesnt mean。

😊，Okay， so first example is restructuring the data access pattern so in this case let's say the the what I'm showing over here that you can actually write or restructure your data access pattern or the data layout in the program to make better use of the cash so for example。

 let's say so in this case consider this example that you have stored your。😊。

Your matrix that the true dimensional matrix that I'm talking about here in a column major order so column major order meaning any element in the same column but different row are going to be adjacent to each other in the memory layout right so that's I plus1 J follows X Ij in the memory layout but then if you go on the row wise then that would be far apart from the memory given that if if your matrix is big in size so Xj plus one is going to be much far away in the memory location than Xj okay so if you know that this is the column major like layout that you have employed would you write this code because this is what we typically write right so we iterate over rows we iterate over columns then and then we do sum so would you do this or would you prefer this。

😊，So if you if you go for the row major access right so you are first iterating over rows and then then iterrating over column so what would happen is that when you go from X Ij to X Ij plus one right so that's what your inner loop is doing you are literally accessing you know memory locations that are far ahead from one another right given that your the matrix is really huge so in that case you would see you won't essentially get any locality out of this program but if you just simply restructure this loop right so if you just make the column column order traverse cell then you can exploit locality from the the cache itself so that's what like。

mentioning here that just you as a programmer， you can rewrite your code if you know that how exactly you are laying out your data as well as how exactly you are going to access that data in the program right so in this case this is called loop interchan。

 but then there are lots of other compiler level optimizations like loop fusion at emerging so many of these techniques the compiler can actually figure out by itself but if you as a programmer you know it's better to make your life easier in that case so that's one example of how as programmer we can write better code so then there is another example called blocking in this case so blocking meaning what let's say the matrix that you are looking at or the data structure that you are looking at in its entirety you know that it cannot fit inside the cache but then if you want to do computation of the entirety of the data structure then you would need to pay the penalty going outside the cache。

Then having long long memory access latency so the idea of blocking is that okay instead of doing the entirety of the computation all at once。

 let's divide and conquer so divide the divide the computation to sub blockss which by itself can fit inside the cache so then you can exploit locality of that entire computation and once you're done then you go to the next block and then do the computation over there so that's's that's what I just said divide the walking set then divide and conquer So there are multiple names of these techniques like blocking tiyling and if you have taken any high performance computing course or let's say GPpU programming then you would definitely know some of these techniques so I'm just going to show you some examples so this is one let's example so you have a image which is consists of multiple pixels and then if you want to operate it on the entirety of the image all at once your image might not fit let's say。

the fastest cache out there， what you want to do， you would essentially say that okay I'm going to block this image and then I'm going to operate on a small block。

 do all the operations and then then go to the next block so that at least the comparisons that are going inside that block is going to reuse the data as much as possible so that's what I'm showing over here so if you want to block it so this is the unblock code if you just simply access the entirety of the image itself。

 but then you can also make a conscious decision theyre saying that OK I'm going to block it and then then access it in a block fashion。

😊，That would improve the cache utilization in this case if it is a GPU memory。

 then then you can have let's say cache that type of memory which you would see reviews out of those memory itself so this is one concrete example which is very much contextual in today's computing system because most of your using on large language modeling or let's say some form of artificial intelligence so and all of these machine learning techniques。

 many form of machine learning techniques internally boils down to bulk matrix multiplication So in this case this is one matrix multi that I'm showing over here So you're multiplying a with a B and then you are generating this matrix right so as you can see that you would access a in the raw major order you would access b in the column major order and that's what you're going to give you the element here so that's the whole point of matrix multiplication but then if if you're storing both of these matrixrices in let's say row major then any one of the access pattern is going to。

😊，Problem in the cache axis right so if it is stored in both the matrices are stored in row measure。

 then A's axis is fine because you are exploiting locality but then B's axis is because you are literally jumping from elements inside the column which is physically laid out very far from each other So what you can do you can say that instead of doing accessing it in a full block manner the entirety of the the matrix all at once what you can say that I'm going to just do a partial blockwise computation So instead of doing an entire matrix multiplication。

 you do a tile matrix multiplication for this tile itself and you would set the tile in such a way that entirety of this two of your source style as well as your definition tile kind of fits into your cache space that you have and then then progressively you would just simply forward on the tile So at every every computation you are going to generate some partial sum。

😊，And then you know， go to the next tile。Projected there go to the next child projected there so that's what you going to you give you better cache utilizationplication which is going to give you better performance。

 So if you want to write any high performance code these things that you need to be careful about okay so with that there are lots of other other compliment lectures that we have in the online if you are interested definitely check out this one so before going further I would just show another example of how you as a programmer can let's say restructure your programme or write better program that can give you better performance benefit by being programrs as cache of it so in this case let's say you have this node structure which is know it's the link kind of thing so you have a next pointer and then think of it in this way this is a let's say databases a database containing huge amount of let's a database of all the person in the world so you have every person name and which school they。

studying and then some idifier to ID that person so now if if you're accessing this data structure in this way that okay you are just simply passing the link is trasing the link is and simply checking that okay if then the key matches right so what happens in this case so in this case what would happen that your node the key property of these node you are touching it every time right so all the nodes you would touch the key property but then the other property like the field that the name and the school you are not going to touch it as often as the key why because you interested only that entry which matches the key itself right so。

😊，So in this case like if you see that these two properties。

 the key and the next is something that is very frequently accessed out of that data structure and the other thing the name and the school they are not actually frequently accessed but if you pack them together if you lay them out sequentially in the the memory layout then you might not actually see the best performance out of the system so what you can do you can just simply say that okaym we as a programmer we know that okay these data points are sorry that these properties are going to be less accessed and some properties are going to be frequently accessed so why don't I just simply break it down into two different data structures that's what we are going to do so would just simply have another data structure called node data which would contain the properties of the node right and then you would just simply point pointer from this node so now what would happen that you would have many of these nodes。

😊，Laid out one after another right because instead of storing this entire two to 56 characters inside the node itself now you have broken it down so only when you are going to find a match you would access this data structure which is fine then on the the link list that you are going to traverse it's now very compactly represented so it can you know get benefit from the spatial locality from the program so that's what know another example of what what you as a programmer can do to feed up your program by just writing better programs I guess。

😊，Okay so and then comes so this is what we talked about how we can you know write better program to you know utilize the cash pay but so that's that's one aspect of let's say improving cash performance by you as a a programmer that you want to write the program but then there is some more things that we can do to reduce the mislatency or the mis cost that the cash is going to the cash hierarchy is going to give it to you so so what is the mislatency and how how this mislatency is affected so the mislatency is affected typically by two properties right so。

😊，If it is a cache miss where exactly is getting serviced from right so think of it in this way that if if if it is L1 data cache miss then you might actually have a chance to get it serviced from L2 if it is L2 miss then you might have a chance from L3 if it is Ls then there is no other or in a traditional architecture there is no other cash levels present then you need to go and access the main and main memory is slow so the idea is that you know。

😊，To reduce the mis latency， we need to understand where exactly the miss is getting serviced from and that dictates how costly these misses are So as I say which cache hierarchy level that this is getting serviced from if it is going to the D then what sort of D access that we are looking at is it row of head is it row of a conflict and we have covered some of these latencies in some previous lectures and you can easily understand that depending on if it is row of a head row of a miss you might actually see different latencies out there and then youd also need to worry about queing delays like lots of requests are going to the Dm then even caches then they would have queuees they would get bumbled up and then you need to arbitrate and all of those latencies would quickly air up and yeah so and so forth。

 And then today's system when you are designing let's say large rack kill server class processor So you are not essentially looking at only one single processor with single Dm chips。

😊，うん。As you normally imagine in your personal computers per you perspective right but then in real case let's say server class data center class processing you have let's say remote memory right so the memory can be coming from shape the different node different rack different remote server altogether so everything kind of adds latetency of each other right and then another critical point of you know the mis latetnt or the misco is that。

😊，If it is a cache miss how much that cache miss is actually stalling the process and that's the moment you would start probing this question。

 then you would start understanding that many of the let's say assumptions that you are making might not actually hold to so one assumption that you might be thinking that okay I'm going to reduce the misses and that's going to give me performance that might not be the case always so why because let's say if that miss is not something that is critical from the processor if that miss is not something that is the process is anyway waiting for then reducing that miss is not going to be helpful so hopefully I'm going to convince you by showing this slide so so think of it in this way so and the positive access on the time so you have three misses coming out from the processor so one miss to cache line a is completely isolated and you would take starting from this point you would take this much of latency to service that myth。

Then there is some other two cache misses coming out from the same processor。

 but then they are coming on the same time right so almost on the same time。

 So that's cash flow B and'2 cash proxy。 So now if I'm going to ask you right so you have chance to save one of these misses only one So which one you want to save。

😊，Do you want to save A， do you want to save B， or do you want to save C？Anyone？So clearly。

 if you see here that if you save B。😡，You you're not actually saving or youre not actually benefiting anything from the processor perspective right because if you save B。

 the process is still going to stall for C so similarly if you save C。

 the process is still going to stall for B apart from those few overlapping cycles。

 most of the cycles are kind of overlap right the non overlapping cycles you might actually save here and there but then most of the cycles are overlap so saving either B or C is not going to be any important from processor perspective because the process is not sty。

😡，But then if you save in。That's actually the critical one because your process is completely stalling the entire latency of the mislatency is kind of exposed to the process so that's what the idea is that so these two access these two memory access that are happening in parallels is what we call the memoryable parallelism so once you start probing this idea that okay you have memoryable parallelism going on and your entirety of like the out of order processor that we have discussed in the previous lectures the entirety of the out of order processor is designed to exploit parallel so you are going to execute as many instructions as possible。

😊，To generate as many memory request also as possible at the same time。

 right So then if you start asking this question that， okay， sorry， yeah。

 So if you start asking this question that how exactly this memory label parallelism affect fit cash performance or better that if you。

Just by looking at this figure that if you start asking question that okay。Is cash。

If is reducing the number of cash misses is always going to give you performance benefit or are they equally important。

 The answer is no。 And that' that's what you know this work tries to argue that traditional cash management policy evenability is optimal policy that we have covered in the last lecture。

 they try to reduce the mis count our implicit assumption was that mis count is always proportional to performance but that's not the case as I showed that if you consider the memory parallelism then that kind of breaks the assumption。

 So here I'm showing some one example。 And this is a very beautiful example in this case。

 So think of it in this way So you have two classes of memory accesses going on So P4 p3 p2 and P1 these are let's say these memory accesses are going in parallel So that's why I'm calling it P series and then you have some memory accesses。

 which is called S1 S2 and S3 which are completely serialized to each other okay and。😊。

let's say your workload is completely going in this loop so it would generate p4 p3 p p4 p3 p2 p1 in parallel and then again it would generate p1 p2 p3 p4 in parallel and then after some time it would generate one S2 s3 sequentially one after the other and just simply going to repeat so if that's the case then then let's consider let's say two replacement policy one is the be optimal replacement policy and another one is MP aware if we want to make the if we can make the cash replacement MLP aware So if you recall what is Valard optimalard optimal simply says that I'm going to evict something from the cache which is going to be accessed way further in time right so that's the victim candidate So what would happen So let's say instead state if you have p4 p3 p P1 inside your cash。

So next time if your processor accesses these four you are going to see hit that's good and then you know belate optimal is going to give you hit so that that's what I showed that your cache state is p4 p3p to p1 and then you started accessing these four these four are hit life is good then once you go to the end of this axis right you have the p4 now you need to you know put this access inside this cache at some point right so you access S1。

😊，S1 is miss right because it's already not present in the cache but now you need to put this S1 inside the cache which one you are going to evict you would be optimal would say that okay which one is going to be accessed forth this in the future so out of P4 p3 p2 and P1 if you go back it's actually t1 that's going to be accessed for this in the future right so it's going to replace P1 it's going to just simply add S1 there so that's what the cache content is going to be after you have seen the access to S1 P4 p3 p2 and then P1 get replaced by S1。

😊，Fine， now let's say then you see S2， obviously S2 is going to be a miss。

 but then you need to put S2 inside the cache also which one you're going to evic you are going to again see out of these four which is going to be accessed farthest in the future obviously that's going to be S1 because S1 P4 p3 p2 is going to be accessed here S1 is going to be accessed here so that S1 is the validityad candidate for getting replaced so validityad is going to replace S1 with S2 so that's your cache content is going to be after this one right Similarlyly if you go for S3 is going to be miss and then your cache content is going to be S3 would replace S2 and then you can argue that once you。

😊，Come back to this access pattern again。😡，You would see three of them are hit which is P4 p3 and P2 but then S3 the P1 is not there so P1 is going to be amiss right so you can know do it by yourself and you can calculate so Bad supplement policy is going to give you four misses which is essentially four stalls and that's what I'm showing over here so that's the edge stalls right and that's what the timeline would look like if you have be supplement policy now let's say if you have a MLP aware policy how does it look like so think of it in this way that your steady state is here so so for example let's say you have the content in the cache p4 S1 S2 and S3 now you are going to access S1 so what would happen obviously you have S1 S2 and S3 so that these three is going to be hit so that's the head and at this point you are going to say that okay sorry if I go back so MLp replacement policy is going to say that okay these S1 S2。

S3 are completely exposed to the processor so I'm going to save these cash blocks as much as possible so I don't care about anyone anyone any of these cash blocks I'm going to pin these blocks inside the cache so I'm going to save them so what would then bedi would do sorry by the ML replacement policy would do once it would see all of these things it would already be there and then then P is going to be only the one which is over there seeing in the cache So now with this cache yet if you are going to look into for this this blob of accesses what you're going to say you're going to see that okay it's the P4 is going to be hit rest3 are going to be miss and similarly if if you progress because then P1 is going to replace P3 is going to replace P P2 P1 then after this P1 your cache content is going to be like this and then once you access this。

Again you you would see only one of them would be hit and rest of them will be missed so I'm just going a bit fasten here。

 but if you you know start arguing yourself like what exactly is happening over here so essentially you are trying to save the accesses in the cash replacement policy which are exposed to the processor。

By trading of misses， which are。You think that it's not going to be exposed to the process right so in this case what what you ended up with you ended up with actually six misses right so in this case like you can easily calculate there are six misses but then these six misses are not happening all individually right so these six misses are only going to cause only two stalls because they are you know overlapping with each other so that's the benefit of performance that you can say that that would actually save their cycles。

😊，So so that's that's one example of let's say parallelism on how parallelism can fiddle around with you know your perceived notion of how the caches should work and how the replacement policies should work also so this is one example of MLP about cash replacement so some other form of parallelism is what I'm going to show quickly and then then we can you know go for the break is。

😊，So this is one the the cache hierarchy that we all knew and love right So three levels of cache and then memory controller so。

😊，Another level of formal parallelism is following so let's say you know that this data is going to be missing the entire cache hierarchy and it's going to go to the D itself so what would happen in in normal case you would access L1 L2 LLC all of these cachees sequentially one of the other and then you would start accessing the main memory at some point your process would start stalling saying that okay I don't have any further space in the processor and that's the performance drop that you are going to see but then if you have some sort of speculation mechanism essentially says that okay you know what that this memory request is not going to be found inside cache is going to go to the the Dm what would happen in that case so you can actually say that okay I'm going to predict and I'm going to start accessing the Dm as fast as possible so in this case we are starting to accessing the Dm right after the L1 data cache。

Access is finished and what you can see that we are actually exploit some sort of parallelism。

 So you predicted that it's going to go to the main memory and you start accessing the D as fast as possible。

 So what did you do you essentially say that okay you while your cache is getting looked up this L2 and LLC caches you actually started accessing the DM So that's another form of parallelism which we are hiding the latency you know that okay D access latency is really long So why can't I start accessing Dm as fast as possible。

😊，So that's the whole idea that if you can speculate。

Then you can you know go forward and access the Dm and hide the latency So this is one form of speculation which again kind of save the stalls。

 but then as you can easily imagine that these things would only work let's say if you can speculate very accurately that okay this is going to miss the entire cache can going to go Dm So that's what something that we did and it has some sort of flavor of let's say some sort of sophisticatedated mechanism which is prediction mechanism which is kind of loan from the machine learning or let's a classical form of machine learning so if you're interested definitely check out these one。

😊。

![](img/f9f1b92c80b3f04900590a0444589418_2.png)

Okay so with that set that's kind of let's say more everything that I wanted to cover for the cash part of the lecture and there are definitely there are lots of more you know prior lectures out there if you're interested definitely check out so there is one thing that I wanted to just announce that there is one more advanced part of the cash mechanisms or cash management for the multico processes which we have not covered and once you started organizing let's say multico cache design then coherence comes into the picture how can you make you know all the copies of the data coherent with each other how can you partition the bandwidth and so and so forth so that part of the lecture we are going to premiere it on YouTube after this lecture of today that would be an optional lecture which you can you know just simply go through at your own pace okay so with that set let's you know get the break here and then we would convene again in。

😊。

![](img/f9f1b92c80b3f04900590a0444589418_4.png)

I guess 215， is that good？高费。😡，肯你不对。なで。

![](img/f9f1b92c80b3f04900590a0444589418_6.png)

![](img/f9f1b92c80b3f04900590a0444589418_7.png)

Okay， so。Let's start from after the break。So as I said like that was 24 a。

 the previous lecture on cash is2 and this one is 24 C so that if you're thinking where does the 24 B go So 24 B is essentially what we are going to premiere in the you would find the premier link in the course with it so that's something that's optional you can you know watch it at your own goal so that essentially talks about like issues in。

Cashching in multi ecosystems， so that that's something that it's a separate。

Okay so with caching and everything was done we are going to nots down a bit on a kind of related topic but in a different domain like a different way of reducing latency memory memory latency it's called crfiing it's something that's very close to my so yeah some recommended readings and it's not only for let's say today's lecture but then tomorrow's lecture also on virtual memory which one of my colleagues is going to cover so that's something that you should be aware of So okay so as I said。

 like the caches and the way that we design and discuss caches still now we say that okay caches are good。

 we already looked into multiple ways to improve the cache performance by increasing the cache size by increasing the cache associivity。

 increasing or decreasing the cash block replacement policies many more so I just quickly alluded to it as well as you as a program or how we can make better use of。

😊，CTo exploit your program。 But then one fundamental thing that the caches cannot solve is it cannot hide compulsory emission。

 So if your program has not seen that memory address before cash is useless right So the first time the program is accessing it。

There is no way that to you know hide it by the cash unless you have some sort of prediction going on so can we do better and that's you know we as an architect we as an engineer also we always keep asking the same question can we do better so the answer is yes what can we do the prefiting right so so what exactly the prefiting is。

😊，So as the name suggests it's prefetch right so essentially we are planning to face the data before the program actually demands for it so you anticipate beforehand and then face the data from the memory down the lane to the faster onship caches So that's the whole idea why because obviously memory latency is high I guess it doesn't need any more introduction So if we can pre fetch accurately and early enough so like emphasize on both of these matrices accurately and early enough then we can reduce or completely eliminate that latency so think of it in this way that okay you are hungry you are going back after your lectures to home and you want to eat something at home So you have two options either you can order after you go to home and then wait for some time to get the order delivered and then you would eat or you can say that okay I'm going to prefetch this。

😊，Foo right so while you are going back home， you ordered something on the fly and then by the time you reach home。

 you would already have the food。 So that's a whole idea of preing now with that analogy。

 you can easily expect that okay if you order it much later in time like's say barely a couple of minutes before you reach home then again you need to wait after you reach home staying hungry and the same time if you order much earlier in the time let's say even when you lecture finish maybe some of you are doing now I don't know so then you know by the time you would reach home then it would be it's already cold so ideally you would want to do it right on the time so that by the time you reach home the food would be already delivered so that's what prefiing is also about you need to accurately predict and you need to predict it on the time so that you can eliminate or completely reduce the latency it can eliminate compulsory cash misses。

 as I said。Can it eliminate all type of cash misses like capacity conflict and the other see that we did not cover in the lecture with the coherence？

😊，It's just a food for thought for you just to think about right so what it can do and what it can't so obviously prefiing meaning it's a speculation speculation kind of involves predicting something so in this case we want to predict which address the program is going to be needed and as you can expect that in many cases it might be much easier to predict this information many cases it might be even harder so hopefully I can convince you why that's the case so as I said like it really works well if the workload has predictable address pattern let's say you are itrating through an array so if it is array iteration you know very well that what's going to happen next which memory location you are going to access next but then if it is accessing much let's say indirect fashion let's say you are accessing a of B or I so then it might be just jumping around in case of irregular memory access patterns predicting what might be demanded by process next is might be harder。

😊，So something that you need to keep in mind of that prefesing does it affect correctness like you have seen some sort of speculation which is we have covered in early lectures which called branch prediction right so and as if you can recall these lectures that branch prediction actually very critical to ensure program's correctness also like if youre predicting wrong when you understand that your predictor was wrong。

 you need to roll back and go to the correct path of execution。😊，But yeah。

 fortunately for us in prefeing a misredation does not affect correctness of a program。

 so what would happen your prefeing technique is predicting some address that your program might be demanding next。

 you fit that data， put it into your you know whatever location that you want to put in。😡。

If it is not getting demanded in the end at very best at very worst that what you did is you utilize the communication link to phase the data which is wasting of bandwidth you wasted the space where you are actually putting it maybe if you're putting it into the cache than you are actually evicting some useful data。

 potentially useful data out of cash that might be causing some pollution in the cache。

 but it's not actually hampering the correctness of the program and and that's actually very important forfiing because just because it does not affect the correctness。

 if you are in let's say situation when you can afford you can actually go and make much more aggressive prediction because you don't have to worry about the correctness of the program so you just simply go aggressively prefi just for in anticipation of improving performance。

So as I said， there is no need for recovery and this is very much in contrast with balance prediction or let's say another form of speculation。

 which I'm not sure whether you have covered value mis prediction but prefeing in this case is not going to affect your correctness of the program now here are some basics of prefeing So in modern systems prefeing is usually done at cacheline grannuite or cash block granularity So you're not going to preface that's say specific part of the data like oh I want that4 byte of information I want that integer from it does not happen like that so whatever your cash block granular。

 whether it's 64 by， whether it's 10 by we typically pre the entirety of the cache flow so that's another anticipation that whatever you're prefeing it's also going to be let's especially localized so you would also access some of it so that's some implicit assumption that we are making and prefiing is a techniques that can reduce both misread as well as mislatency let's say thisread you can I hope I don't need to convince you because if you can。

😊，But beforehand when the process actually demands it。

 it would actually find it in the cache because somebody already fetch the data and put it in the cache so from cache's perspective the misread drops why it's also reducing mislatency because this time that it takes to fetch the data is not exposed to the program because the fetching actually happen let's say behind the programs back so that whenever the data is needed。

 the data is already present so that's why it's also reducing mislatency when that sense and prefet as a technique it's a very general technique which is it's not only applicable for the hardware prefeer and I'm going to show you all like many of these examples that but prefe prefeting can be done by compiler itself and many of the high performance code compilers for high performance code might actually inject instructions I would be showing some of these you as a programmer you can also write your own prefe instructions saying that okay I'm going to access a cache。

A regularly so while i'm accessing let's say the element A of I why don't I pre let's say AI plus you know I don't know AI plus8 right so that's the anticipation that that you know the we as a programmer can also do so that once。

😊，We want to access a of8 A of8 would already be present in the cache so that's what know as a programmer。

 and then there are multiple examples that we can you know dig in which system itself is also genetic prefe and prefiing is a very broad topic actually so it's not it's equally you would find prefeing example in multiple cases。

 not necessarily inside processor， but inside your web browser also let's say a software which is purely running learning from your access patterns So let's say what type of webs you are visiting what type of let's say web links that you are following it can actually prefetch web data。

 The idea is that you as a user you should not be looking at the latency to load of web page So as you can see the entirety of the concept of prefeing kind of broadly applicable to multiple aspect of today's computing systems as well as the UI systems also So any sort of preing kind of comes with four questions and for these four。

😊，Basic questions that you want to answer， what， when， where and how。

What meaning what address and and the context of prefeing inside processor what address that you want to prefe right so what per algorithm that you are going to use and I'm going to show you some examples of it when meaning that when you want to initiate a prefe request as I said like that actually depends that would actually impact。

A lot of。What are the benefits that you're looking of prefiing So if it is early。

 whether it is late or whether it's just on time So that's the wind part and then there are multiple questions that you need to answer is where to preface so and this is a multiprom question so where do you want to place the preface data so you have like lots of design decisions do you want to place the data inside the cache itself do you want to place it in the prefi buffer like a separate buffer put the data like each one of these design decisions comes with its own benefit and disadvantage so if you put it in the cache then you don't have to worry about anything let's say oh I don't the cache is already coherent so or we design the cache to be coherent you don't have to worry about any let's say separate copy of the same data but if you put it in the separate buffer you need to keep that separate buffer coherent by yourself so that's a downside of putting it in the separate buffer but then if you put it in the separate buffer then you are also not evicting something from the cache so you can say that okay even if I'm wrong。

I'm not actually hampering my cash performance by kicking someone out from the cache right so as you can easily argue to yourself that each of these design decisions and the design decisions have vast。

 they are you know each every design decision comes with its own drawback as well as benefits。😊。

So this one where another where is like where exactly you want to put the prefeure 2 so do you want to put the prefecure in let's say beside L1 beside L2 beside the main memory like depending on where you are actually putting it you would see different tradeoffs so what type of patterns that you are looking at whether you can train on the entirety of the memory access pattern generated by the program or you are looking at a filtered access stream and that affects the efficacy of the prefecure itself and then the how part is essentially saying that okay how exactly the prefecture operates so that's kind of very much let's say intertwined with the what part also but then how can how is a bit broaden in a sense that are you generating prefe request inside compiler is you are you as a programmer going to generate the hardware is going to generate if the hardware is going to generate what sort of cooperative mechanisms going on is there one mechanism is the。

😊，Pfis like how exactly that's happening。 So hopefully I'm going to cover some of these or if not all of these in today's lecture。

 and if something spells， my colleague in the next lecture is going to cover it in the next so let's start with the what part。

 So what address to pre as to answer this question you first need to ask what is the tradeoff So and we as an architect we always start answering this question what is the trade So what happens if you prefacet something wrong。

 as I said that it's not going to affect the program's correctness but it's going to waste resource What type of resource。

 you are going to waste main bandwidth。 you are going to probably waste the cash or prefi buffer exactly you decide to put this prefi data you are going to waste energy consumption so you literally fit some data which is not needed by the program So that's was wasted effort and I all of these resource that's going on for your prefi。

うん。Meticulously used by the demands that the program is actually generating。

 so always keep this in mind that even though prefech is not hampering your correct the program's correctness it's taking away resources which otherwise could have been used by the program genuinely so that's the effect that you are looking at right so。

So that's why we need to always keep an eye on the accuracy of the prefeing and accuracy is essentially defined as the total number of prefes that are used divided by the total number of prefees that you have sent。

😊，Ially you would want your preure to be as accurate as possible。

 So whatever prefi that you are issuing is going to be used by the program right how do we know what to pre so that's that's the entirety of the discussion that and that's the ingenuity comes in and even after let's say 50 years of let's say development we still we as an architect and the research is we still actually invest quite a significant amount of resource research resource for developing better algorithm and you can easily visualize that let's say machine learning is actually a form pattern learning so you can think of let's say how you can use machine learning to come up with pattern learning so that you can anticipate access beforehand so all of these things you I'm just giving some food for thought for you so what of sort of pre algorithm that you want to use kind of dictate and I'm just going to show you some know basic access patterns so here is one access pattern and。

😊，The scope of this lecture you always， whenever you see an address。

 it's essentially like asb address it's not a by and。😊，So this is one access pattern。

 aa plus 1 a+2 as you can easily， you don't need a big brain to understand what's going on here。

 it's just simply streaming access pattern right？😊，Something a bit more complicated。

 but again it's very much understandable it's a you know stride access pattern so it's with the stride 42 so you access B you access b plus 42 you access B B plus 42 plus 42 which is 84 and so and so forth right。

😊，But then I'm just making it much more harder for you to analyze the coming up with the pattern right so in this case let's say c c plus2 plus5 plus 9。

11 apparently if you see that okay there might not be pattern but if you see that the first the first the del between the first two is plus2 then plus three then plus four and then two then three then4 so if you start looking at let's say second degree delta right so it's not the first degree delta is not constant as you see you here but the second degree pattern right so it's like plus2 plus3 plus4 and then plus2 plus c plus so how can you exactly analyze this sort of pattern right and understand these patterns on the flyer and anticipate accesses beforehand so all of these are essentially let's say the better prediction the better pattern learning algorithms that you come up with the more patterns the more accesses that you can anticipate much earlier in the future and they can be done all of。

😊，Commercial systems that you are using in your processes like in your laptops as well as phones they most likely have some sort of prefiing algorithms going on right so this is another form of let's say access patterns So if you try to look into delta might not be visible but then if you look into the address that address itself repeats so as you can see like x Y t repeats x Y repeats again and again in the access patterns So if you see whenever that okay x is getting access。

 you know that y and T is getting access next So that's the anticipation and then you can literally you can construct and then see lots of lots of different types of patterns in the program so the whole the design sorry the research in this direction is how exactly you come up with better pattern learning algorithms so that's the what part now let's go to the when part of the prefi so when to initiate a prefi equation as I said like if you pre too early the data might not be used before it's eed from the the place that you actually stored so。

Essentially you anticipated it way ahead in time so that by the time it's actually needed it's already gone so you don't want to do that。

😊，Similarly， if you want to have a pre fish too late so essentially you are not hiding the entirety of the latency so lets you anticipated it very quickly very late and yeah so so your pre is still getting the data from wherever the data resides but by the time your process already demanded it so some part of the latency is hidden but other part of the latency is exposed to the process now the process is stall so that's ideally you would want the prefi to happen exactly on time right so that's what the matrix that we typically use the timeless matrix timeless is essentially saying that okay what part of the latency that you are hiding and what part of the latency is exposed so you want to hide exactly the entirety of it and not anticipated much ahead of the time also。

😊，Okay so as you can see like you can make prefeure more aggressive if you have a prefe algorithm to identify what pre request is going to happen so you can make that algorithm more aggressive more timely by going aggressive so what do we mean by aggressive so if I go to let's say the previous example of let's say this example so if you if you if you see that okay there is a pattern going on B like plus 42 plus 42 plus 42 so if you are if your program is accessing B。

😊，Would you you can pre fetch b plus 42， but then you would easily argue that okay by the time B plus 42 is demanded by the program。

 it won't be arriving to the cache right so it might be not useful right so what you can say that okay you can say that okay I'm going to go aggressive I'm going to say that okay I'm going to either prefe all three of them all four of them or you can also say that I'm going to jump ahead and then pre fetch so once you start looking at B and you know that okay42 is the strike instead of fetching actually plus 42 you would actually fetch126 so that's like jumping ahead right and then from like126 you can actually start preing from there。

So I'm going to show you some examples of how you know commercial processes actually you know make the prefeture more aggressive by you know jumping ahead and then go extract more timeliness in this case。

 So so that's one one example of you know exploiting aggressiveness to make the prefeure timely。

 But if you have， let's say prefe。😊，Happening by the source code itself like where you know compiler is injecting prefe request or you as a program you want to inject Prefe request you also want to pre inject a pre fetch request much ahead than when you are going to access the code right so think of it in this way let's say your code is citrating through an array from0 to one million right so if you're accessing array element of0 do you want to pre fetch a of one。

😊，Probably not so you want to preface， let's say a of 100 so so that by the time  a00 gets fetch from the memory to the cache。

 your program would actually reach to a 100 and then you would need it So this is what what we are calling let's say you can move the prefi instructions earlier in the code if you as a programmer or let's say compiler is injecting this prefi request in the software Okay so that's that's you that's the wind part now there comes the where part of the preing So where as I said like where is multiprong questions So where do you want to pre fetch into do you want to preface from memory to L4 L3 L2 different levels of caches do you want to you know like what are the advantage and disadvantages of putting into different levels of cache right so thatss or do you want even like so。

So this is one like one question that you want to answer that okay。

 if you are fetching the data to let's say bigger caches。

 then you might actually let's say anticipating that okay you pre request even if it's not going to be useful it's not going to cause lots of pollution either because your L3 cache is huge right but if you want to preface the data to all the way up to L1 cache。

😊，You are actually anticipating that your prefe is very much accurate why because El1 is also small。

 so you ideally don't want to kick someone out from El also。😊，Okay。

 so each of these decisions they come with their own tradeoffs where do you want to place the pref data in the cache itself like we covered this cash replacement policies in the last lecture so do we want to treat this pref block in the same priority or a demand block or do you want to say that okay you know what I have seen this prefe to be the algorithm to be not that accurate for this program so Id have less confidence so let's put it in some sort of let's say low confidence zone so what sort of you know techniques that you want to do over here so as I said like pref blocks if they are not they are known to be not needed。

 then you can kind of fiddled around with the LR position saying that okay I want this to be demoted so that if you want anything to be getting kicked out from the cash pick the pref one not the demand one but then you can also argue that okay this is one let's say hat sorry。

One policy if fits all is also not going to be the case but because you don't want to go in this sort sort of let's say pessimistic policy when your prefeure is actually very accurate so there is a tradeoff so you want to have these sort of decisions made on the fly so yeah thats that's something that you need to you know worry about S replacement policy i'm not going to go too much into detail but then the more more important another important question of where is that where exactly you want to know put the prefecture as I said like depending on where exactly you are putting you might be looking at different sorts of access memory access is coming to the prefecary so so let's say if the prefeture is sitting physically sitting beside the want cash。

Anything that is coming out of the processor it's visible to the prefeor right and then it can mind the pattern from there anticipate what's going to happen next fetch it from different levels of cache but if you put the prefeure in the L2 beside the L2 it's physically present beside L2 then you are not seeing all the requests that are generated by the program you' are only going to see the requests that are generated by the program but also missed the L1 cache because that's why they arrived at the L2 so then you are actually looking at the request the prefeure is looking at those requests so the more you would go let's say far away from the code the less request that you are going to look at so you can either look at L1 hits and misses or you can look at L1 misses like if you put the prefeure physically beside L2 if you put the prefeor physically beside L cache then it says only you are going to see L2 misses and all of these reside decisions come with its own drawback like the more so think of it in this way your program is accessing lots of。

the farther away the farther you go away from the core。😊。

You are looking at the filtered access stream so many of those accesses you won't be seeing later on why because they are actually hit by the previous caches so you are looking at then a broken you know stencil think of it in this way like you' are looking literally looking at the broken piece of data and you are expected to make any sense out of the broken piece of data。

😊，When does it work when it doesn't work well so all of these things you know these are something that you need to worry about when when you are doing prefi so as I say like the more complete access pattern that you are looking at the potentially you are going to be more accurate as well as you are going to cover more right but then。

😊，It also needs the prefecure needs to be you know looking all the accesses so that kind of you know makes it makes the prefecure design itself more intensive right but then if you go and this is this is that figure right so if you go further away from the core then you are actually looking at filtered access stream here let's say if you put the prefecure over here then you are not literally going to see any accesses that is unit by the program unless it comes at this level so that's a filtered stream but then you' are looking at the broken piece of information then you need to make better sense out of and so on so so so that's what know all multiprong design decisions that you as an architect you need to decide before having all of these techniques inside and as I said like prefeing is all not only something that is happening inside processor but any sort of design systems can actually make use of prefeing so this is one example that I'm saying that okay let's say your CPU is backed up by two different types of memory one is。

😊，And another one is a face change memory with different characteristic you can also employ prefi mechanisms that moves the data back and forth between these two memories without even processor demanding so that when the processor demands it you would get data right place at the right time so that's the whole idea of prefiing in this case and you can easily extend this idea let's say rack scale computers like when you have let's say server class machines let's say in data centers so you have local node and then you have some remote node and you have some program that is working on this compute node here and the data actually resides in the remote node so what you want to do do you want to pay the penalty when the data is getting demanded。

 it's getting fetch that's one way but the other way is you can actually anticipatefi it before so so just to motivate that the prefiing is a very broad concept that kind of transcends to multiple application domain okay。

I'm just going to quickly go through the how part which is the most interesting part of prefiing like how exactly we can anticipate what going to happen in or what's going to be needed by the program so as I said it can be done by software it can be done by hardware and then there is a third class of prefecure which is called execution based prefising and I'm going to if the time permits I'm going to go quickly through those also so software prefesing。

 what does it mean it essentially means that your ISA the X6s or whatever ISA that you're looking at it has some sort of prefi instructions and it's a responsibility of the programmer or the compiler to use this prefi instruction to explicitly prefits information so it typically works very well when you have a regular access patterns like as I say maybe you're going through at an iterating through an array that's a very knife description of a regular。

😊，But you can make use of software profiing in other aspects also。😊，Then comes hardware prefeing。

 hardware prefeing， meaning that you know we as a software developer or let's say the compiler is probably not generating anything。

 but the hardware itself is generating prefeing。😊，Transparently we don't like it's completely hidden by the programmer right so it memorizes it tries to you know mine patterns from the accesses that it has learned you know learning accesses triess everything and then it generate automatically it fetches the data from you know wherever it resides to the faster memory。

😊，And then as I said like it it's a execution based preing。

 execution based preing is a kind of different class why why because it can actually be implemented both using software techniques as well as hardware tech so think of it in this way that you have a program that is actually executing your code right and then you have a thread and whatever that thread is and that thread is you know it's broadly defined in multiple ways。

😊，So that thread is kind of acting as a pathfinder to your program so it kind of runs ahead of you。

The whole point of that special thread is to do prefe for you so that's the whole idea of execution based prection and it kind of fascinatingly works well。

😊，In most complex cases where you cannot literally find any patterns inside your program itself right so if you look at the raw memory access stream。

 you try to find all sorts of pattern mining algorithms you cannot find a patterns so the option that you kind of rely on then is that okay what if I have a scout a thread a path find a thread that kind of runs ahead of you right in some aspect and it would generate the prefe request for you so that when once your program follows through it would actually see everything already prepared for you so I'm going to show show some examples of that okay so let's start with the software prefeing I'm just quickly go through like how X6 handle software prefiing so this is one example of you know some prefet instructions different you know x36 has different prefe instructions with different hints so that's what we call prefet t0 t0 is one hint t1 is another hint and then T2 and then N so different hints and you can read through this。

So essentially its different so you as a programmer， if you use different instructions for prefeing。

😊，Specific instruction with a specific hint essentially tells you where exactly or tells the processor very exactly to fetch the data。

 So if you said that okay if it is t0， you are confident in some way and you want to preface the data to some cache level if it is as opposed to lets say pre t2 and then there is called preface N which is' called non-tempor saying that okay I want the data but don't put it in the cache so lots of various possibilities are there and we as a programmer we can explicitly light this instructions as well as the compiler can also generate this instruction on our behalf so that's what the software preing kind of folks and I'm not going to too much detail into software preing other point us in this lecture so you can just go through it and then let me quickly go through some example hardware prefi so a very primitive form of hardware prefiing can be called stream prefiing So what does the stream preing does and this is coming from。

😊，IBMs power processor。 How many of you know that IBM has a power series processor anymore。 Okay。

 I can see one hand over here。 Okay， so I yeah， so so these these processor are kind of let's say like like a user grade processor。

 So at some point Apple used to have their MacBooks using IBM power processor and and yeah then they switch to Intel as their vendor and now they designing their own chips。

😊，Okay so so this is one example of a prefe in IVM Power4 processor so what it does it says that okay so your processor is sitting over here right so that's the code and then you have data L1 cache and then L2 cache L3 cache and4 cache so what it says that if your processor is accessing let's say L0 L1 so think of it as a cache line it so cache line zero cache line1 so if that's the case then the prefecure which acting on your behalf of the program。

😊，The moment it would say that okay L0 is getting access。

 it would actually fetch L1 from the L2 to the Dl1 cache okay so that's a front that it's maintaining one cache line front that the prefecure that is sitting here is going to fit the data to this cache level okay then there is another prefeure which is sitting at at let's say L2 which is saying that okay。

 you know what the moment I would see that okay L1 is getting prefetch from the core then I would actually start so it's it's a bulk of four cache lines it's maintaining a four cache line front right so it would say okay I'm going to prefe the next four so which is let's say L5 L6 L7 L8。

 the entire blob of it to the L2 cache so that's like a four at once like so I'm going to do four prefe request and then there is another prefeure which is sitting beside L3 which actually runs。

😊，Four of these four ahead right so that that's like 16 cache lines ahead it's simply saying that okay L5 is getting now fetched from L to L2 so I'm seeing L5 I'm actually going to fetch L 17 to L 20 the entire four of it from the main memory to the L。

😊，So what it's essentially doing is like it's creating a front ladder right so your core is actually only accessing L0 so core is very naive right so it is just accessing L0。

😊，The privileges themselves already primed themselves saying that okay。

Code access L0 so I'm supposed to fetch the entire blob of it to L1 now and somebody down the hierarchy at L2 would say that okay I'm going to fetch another blob of it from L3 to L2 and someone from beside L3 is going to say that okay I'm going to fetch another blob so it's essentially maintaining a fetch front。

😊，The more the code goes the more the prefeer also runs ahead so that's the whole idea of this sort of prefeture so this is a very beautiful paper on on on stream pre fetching if you're interested I would definitely recommend it and this is。

😊，Kind of let's say where it all started right So and as you can see over here and why we actually show this thing at that time。

 So this is V 11780。 how many folks know this process I'm pretty sure that okay okay I'm impressed Yeah so I guess we are pretty even I'm pretty old for this young for this but okay so this paper says that at that time also if you look into the misco in terms of cycle So the more we go and in some cycles and the more we go in terms of instruction so。

😊，If it is you know found inside the core that's one thing if it is going in the cache and if it is going beyond and they are actually sorry in this case my bottom I'm just retracting so they are essentially projecting for the future generation process saying that okay the more you would go towards future generation process this latency gap is going to be even higher why because you are making your processor much faster today so the faster you're accessing on the instructions。

😊，Your memory is not getting any faster so that's the gap that it's getting larger and and larger so that's what they anticipated that okay current generation it's only let's say six cycles so that's the six cycles that the cost of it why because your cycle was at also big at that time okay but then if you make the process even faster that's double or tightentan then you would actually looking you are looking at dual cycle latency fetching something from the D。

😊，the memory， wherever the data resideites， right？In future generation posture。

 that might actually go to 70 cycles。 Nowadays， it's actually going into any guess how much it can be。

Is it 70 more than 70 anything？It's actually lying somewhat depending obviously it depends on what let's say process frequency that you're looking at or what sort of fast memory that you're looking at。

 but it's safe to say that it's much higher than like let's say you70s it can go as bad as its like 500 cycles which is a huge amount of cycle so so this paper kind of anticipates is much ahead of any time and if you can see that that's coming from 1990s so it's transcending from 30 years down the line so that's what this is 40 years okay。

😊，Okay so with that said like there are some prefich of performance metrics that we want to you know introduce like accuracy I introduced it before。

 which is you use prefi divided by the cent prefit。

 then coverage coverage is essentially how many prefitge misses like how many misses that you have prefit successfully divided by all misses。

😊，100% coverage means that you know all the misses that were happening if you don't have the pre is now completely covered so that's the coverage and the timeliness is essentially saying that okay how many onetime pres that you have divided by the total number of use pre so that's you know the first auto matrix that we care about accuracy coverage and timeliness and then you have the second auto matrix like bandwidth consumption cash pollution which I kind of alluded to that what happens in you these metrics are also important。

😊，Okay so here is another example of stride prefeure which I'm probably not going to go too much into detail。

 but the idea is same as let's say a bit more sophisticated than the stream prefecure。

 but then idea is that okay if you can anticipate it with a stride end then you are going to prefetch with a stride end right so the idea is that okay you record the stride between two consecutive memory addresses if you see that there is a constant stride going on then you would anticipate based on that constant so this is one implementation so if if your program is generating one specific load instruction is generating this memory request you just hash it with that load instruction you would say that okay what is the last address that I have seen。

😊，What is my current address So I'm going to just subtract with my last address I would get a slide and I also have you know stored the last slide I'm going to match the current stride with the last slide I'll check that okay if the current stride matches with the last slide if that's the case then I'm going to increase the confidence if not I'm going to reduce the confidence and if if it gets high confidence and I'm saying that I'm like very much confident that any future load address coming from that specific load instruction that specific load PC is's carrying with that same let's say stride so the moment you would you would detect a stride the moment you would start prefiing but as I said like timeliness can be an issue so you want to make the prefi request also at timely so a potential solution can be you look ahead into the stream rate So if you're seeing a then you are going to predict let's say a plus NA plus2 and a plus3 and plus4 and and and so on and so forth so that's one implementation of stride pre then。

😊，Some other implementation can be also memory region based typefeing which I'm not going that branch of detail。

 but then sitefeing is also something that is very much well integrated into like recent processes also like any type of like arm processor X36 processor they have one form of type fetching already to be happening inside the first level of cash okay so that's one paper if this is Anna paper from Intel is quite old but then Intel has also recent papers and an arm also has open source information。

😊，That kind of alludes to the same thing。Okay so with that said there are ways to do even more complex access pattern let me let me show you one example so this is one example so so this is a stride the delta between two consecutive axises so as you can see that if you look into it by itself it kind of looking ha person but if you try to look into more closely you would see that okay sequence of deltas repeat right so in this case let's say7 followed by minus6 followed by 2L followed by6 minus5 and1 so that entire pattern repeat so how can you design let's say this sort of like how can you design pres to analyze this sort of predictors so the idea is like know you instead of just simply learning one stride you would actually learn let's say a history of stride followed by another stride so let me give you an example so let's say oh I'm going to store history like this so if you see delta of7 followed by minus-6 followed by 2L that kind of predicts the next delta to be 6。

😊，Right similarly， if you see-6126 that followed by-5。

 how can you use this sort of information to predict so you can simply say that okay。

 whenever you have seen， let's say67 minus-6 and 12 you actually make a prediction of6 thats going to be your next delta and you have some sort of confidence saying that okay you know I'm 85% confident that that's going to be your next delta so you add this you know plus 6 tried to the current address issue the pre request but then you can easily anticipate that okay this might not be time delay so you need to go ahead in the stream to extract time minutes how can you go ahead in the stream。

 you can say that okay you 6， the predicted value as if that it actually occurred right so you boots you say that okay。

 if you had 7 minus-6 to12 as a previous history if you add 6 as a current so what becomes a current history it's a sliding window so that that becomes 62 sorry minus-6 to16。

😊，You look up the table said okay if that's the pattern what would be the next delta the next delta is minus5 so you said okay I'm going to issue the pres request for these but then you can also keep measuring saying that okay this prediction this correlation is 70% confident So what is the total path confidence you were initially 85% confidence now you are 70% so now actually operating on that path to be 60% so you are giving a 60% bet that okay you are on the correct path that this is what the program is going to need。

😊，You can keep on doing the same thing till let's say your cascaded confidence you know ratio actually drops and to a predefined threshold and then you would stop so this is one example of how you can actually look ahead much into the future and you know just by bootstrapping predictions with your own and and you know make time and predictions okay so with that I would probably you know close today's session from here。

😊，Tomorrow we are going to cover rest of the prefecture。

 which we are going to it's a shame that I cannot cover this because this is my own work and it's going you know my colleague is going to introduce this professor to you just food for thought for you is that you know how because prefeing is a fundamentally a pattern learning problem how machine learning can help in this case So this is one form of machine learning that we are going to cover a reinforcement learning and there are many more over there Okay so that's all of it if we don't have any other questions then let's close the lecture Thank you very much。

😊，Yeah。没事。Yeah。

![](img/f9f1b92c80b3f04900590a0444589418_9.png)