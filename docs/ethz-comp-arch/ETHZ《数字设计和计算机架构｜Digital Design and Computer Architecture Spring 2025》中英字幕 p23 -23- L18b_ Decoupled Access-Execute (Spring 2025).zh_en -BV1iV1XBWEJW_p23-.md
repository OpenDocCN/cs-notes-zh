# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p23 -23- L18b_ Decoupled Access-Execute (Spring 2025).zh_en -BV1iV1XBWEJW_p23-

So let me quickly cover the basic idea。😡。

![](img/bf40b88ca19d48bc46686cb8e29b4dd8_1.png)

And next week we're going to talk about Sd and GPUs so the basic idea of theupd action executeor is actually very simple but before we go into the basic idea let's talk about the motivation motivation was Tommoso's algorithm is too complex to implement basically this was 1980s before Pentium Pro nobody implemented it and people suggested that we don't want this much complexity in the systems actually VIW can be positioned in in similar way also right because VIW clearly has a very different philosophy than out of orderic execution and Tommol's algorithm。

😡，DAE has a very similar philosophy， but it doesn't go all the way。😡。

Into hardware extremely simple we're going to see that it's going to change the hardware basically the idea is to decouple opera access or memory access versus execution computation。

 we have two separate instruction streams that communicate through IA visible cues that's the basic idea。

😡，Basically you look like a system decoupled an access execute system。

 you have an access processor and execute processor access processors task is just to get memory data and supply to the execute processor execute processor task is to give the addresses that it needs to the memory processor and they basically communicate through these queuees。

😊，It's beautiful， in a sense， because these are two different types of tasks。😡。

Memi accesses may be balneck by memory， but computation may not be bottlealneck so you keep doing computation here while you're waiting for memory and it may be the other way around also sometimes you may be waiting for long computations。

 but you may be continuing memorym accesses so this way without having the full blown out of work execution。

😡，You don't need to stall between the access and execute processor while the ME operation is going。

 you can do a computation and vice versa。😡，That's the beauty of it and it was introduced by Jim Smith in these seminal papers in the seminal paper inca 1982 and its basic principles are applied in computing systems today。

 but not exactly as it was emission first of all you can see that ISa needs to change over here so communication happens to these cues as you can see these are fiveqes they' are ISa visible instructions visible cues as a result the length of the queuees determine how much latency you can tolerate on the memory side as well as on the execute side so these queuees the good part is these queuees can be very scalable they're not like the tag matching logic reservation stations right reservation stations are hard to scale load store queueess are hard to scale whereas here queuees can be scalable right because it's a FiOq and these are all fiveqs there's also branch queue which you will get to because you need to keep these synchronized as well but basically all of these are5qs。

😡，Okay， so essentially the basic idea is instead of having a single instruction stream that looks like this。

 this is a very famous loop， lower liververmore loop， it does some scientific computation。😊。

You basically have two instructions teams access and execute and it's essentially doing the same thing but whenever you need to do memory access。

 you do it over here， whenever you need to do operations executions and branches you need to do it over here and whenever you need to communicate a memory access result to the execute processor you need to you need to put it to access access to execute queue you can see these memoryaces go to that queue and you can see that the execute engine takes from that queue and could put the result into execute the access queue so communication happens through these queuees。

😊，Okay you can take a look at it if you're interested in more detail so the big advantage is execute stream can run ahead of the access stream and vice versa if the access processor is waiting for memory execute processor can perform useful work if access processor for example hits in the cache and it's not waiting for memory it supplies the data to the lagging execute processor usually the memory accesses take longer so usually execute can perform useful work independent instructions while the access processor is waiting basically the key idea is queuees reduce the number of required registers。

😊，So these are not registers， you don't have to have thousands of registers or internal registers like physical registers and Auto of word engine。

 you communicate through these five OQs， so basically you have limited Autoward execution without the wake up and select complexity and without large physical register files。

😡，Of course everything comes with disadvantages now again compiler is important here compiler was important for VLIW compile is important for models historical Ace compile is important for decoupled access and execute。

😡，You need to have compiler support to partition the program and manage the cues。😡。

This determines the amount of decoupling you can get and people have a lot of interesting compilation techniques for this also。

 not as much as VLIW has done and not as much as work that's going on in syto race today actually。

 but still compile is important。😡，And one other disadvantage is branch instructions requires synchronization between A and E because you're actually taking a single instruction stream and separating it into two instruction streams。

 what happens to branches right it gets they get executed in the execute processor。

 but you need to signal the。😡，Access processor to make sure that the access processor is not on the wrong path forever。

 right？😡，The other disadvantage is multiple instruction streams。

 basically you need to generate two instruction streams or program two instruction streams。

 which may be cumbersome， but later work show that this can be done with a single one by taking the single instruction stream and streaming it dynamically into multiple processors。

😡，And this is an example basically this is the astronuttics one processor what they did was they have a single instruction scheme instruction fetch unit and they basically separated dynamically into an access processor access instruction pipeline and an execute processor execute instruction pipeline basically a versus X over here each pipeline is in order so this is very important Each pipeline is simple in order there is no auto of order execution inside the pipeline the out of order execution capability comes from。

😡，One instruction pipeline doing something basically being asynchronous with the other instruction pipeline until it needs data from that pipeline of course right and you can see that there are access registers and execute registers and these are the cues that you need to communicate between the two streams and you can see that there are multiple instruction streams there's copying unit also you can copy the operation from one pipeline to another pipeline so they're interesting communication things that they added store loads are always problematic as usual I'm not going to go into the details but if you're really interested these papers actually provide a very accessible and nice description of the decoupled access and execute paradigm you can see there's a restartstock unit also for branch handling for example。

😡，Okay so basically branch handling is a big problem so a lot of compilers use loop unrolling to eliminate branches basically loop unrolling replicates the loop body multiple times with an iteration so you may actually have learned about loop unrolling I have to say it because it's a very basic compiler technique to get rid of branches as much as possible because branches always provide problems in terms of in VLIW decoupled access and execute as well systoic array so you want to get real branches as much as possible and the idea in loop unrolling is to replicate the loop body multiple times within an iteration as you can see over here but of course now you're doing four iterations for original iterations within one iteration so you need to make sure you increment the values correctly and that's going to be a problem actually but if you do this now you don't execute as many branches you don't execute as many loop control instructions etcter so you reduce the loop maintenance overhead induction variable increment or loop condition test goes away or reduces by one fourth basically there are by three fourths in this case。

You enlarge the basic block now we have a bigger basic block over here as opposed to a single basic instruction over here about single set of instructions This enables code optimization and scheduling opportunities and the problem happens usually when iteration count is not a multiple of unroll factor so in this case unroll factors four you're putting four iterations into single original iteration but if n is not a multiple of four then you'll have the problems you need to extra code to detect this so you need to have some extra code to handle this and that increases code size in the end but blueonrolling is a very simple compiler based technique to help all of the processor that we discuss today decoupd X and execute being an important one and they talk about loopon rolling a lot actually decoupd Xs and execute and it improves the performance of this astrontics yes1 processor but it's important for you to think about it going forward especially if you're interested in topics like compilation and hardware this is a very basic compilation mechanisms。



![](img/bf40b88ca19d48bc46686cb8e29b4dd8_3.png)

Okay， let me give you the impact of decoupd access and execute in real processor and then we will be done basically the way it's described it's not exactly employed in existing processor。

 but in principle the coupled that access and execute is employed in old processor that I know of。

 for example， this is the Pentium4 processor internally。😡。

I'm not going to go through everything over here clearly。

 but I'm going to point out this part after the instructions are renamed and allocated to the orderder buffer。

 for example and registers， they go through a memory part。😡，And an execution part。

So you can see that this is the decoupling。You have a me part of the processor。

 an execution part of the processor and they're decoupled from each other such that the memory part is customized for memory operations and execution part is customized for execution operations。

 even in an auto order processor like this this is an auto order execution superscale execution processor even that decouples access and execute as you can see so that you can get specialization across different components and you also get basically different auto ordering between these different components they don't hopefully they don't step on the toes of each other if you will。

😡。

![](img/bf40b88ca19d48bc46686cb8e29b4dd8_5.png)

I mean， if you want to look at Pentium4 simplified。

 this is actually another way of looking at it you can see memory an integer decoupling。

 this is from my paper， a simpler view of the decoupled that access and execute in Pantium4 and you could actually extend the concept to different types of execution。

 F execution also FP and into execution as well。😊，Okay so that brings me to the end of decoupled X and execute hopefully you enjoyed the three major ideas that we discussed VIW systolic arrays and decoupled access and execute you may think about where they could be useful going into the future as well let me see if there are any burning questions and if theres once we handle them will be done okay wouldn't thisE be especially useful in combination with VIW because of the packaging approach or is it rather hard to combine the approach so that's an excellent question and in my opinion actually I don't know if there are any process that combine it but my high level answer is yes。

 basically if you can combine the idea of VIW of course you need to give up on some of the basic VIW principles combine them you can basically have part of your VIW bundle as memory bundle and part of your VIW bundle as execute bundle and absolutely you can decouple the execution and execute between。

Different portions of a VIW instruction and you get rid of this lockstep and you also gets partial auto order execution benefits in a VIW engine so your point is actually excellent that's the reason why I like covering these topics together because some of the VIW downsides can be alleviated。

😡，Simply with decoupled access and execute principles apply to VLIW engines that way you don't complicate the hardware too much。

 you do need to complicate a little bit， so you do need to depart from the VLIW principles a little bit。

 but you get significantly higher performance potential。😡，Soex。Thanks for asking that question。

Any other questions？Okay， if I don't see any other， then。Have a nice weekend。

 hopefully I will see you next week when we talk about another fascinating and extremely high impact topic on CD processinging and cover vector processors and talk about GPUs。

😊。

![](img/bf40b88ca19d48bc46686cb8e29b4dd8_7.png)

Until then， take good care， stay safe。

![](img/bf40b88ca19d48bc46686cb8e29b4dd8_9.png)