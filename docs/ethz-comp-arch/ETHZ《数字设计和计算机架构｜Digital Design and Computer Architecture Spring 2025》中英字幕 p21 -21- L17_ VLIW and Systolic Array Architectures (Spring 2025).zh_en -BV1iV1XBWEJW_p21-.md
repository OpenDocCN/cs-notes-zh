# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p21 -21- L17_ VLIW and Systolic Array Architectures (Spring 2025).zh_en -BV1iV1XBWEJW_p21-

![](img/51312d66a368f99520e4f85509618edd_0.png)

Can you hear me online？ All good， okay。Yeah we have four minutes so。Okay。お。来来始。因。这。🎼，系。嗯。そこれ。Okay。

I think we have1 attendance today。Probably because of the holidays coming up tomorrow。

I assume over the bad weather。I don't know， okay。Welcome to Leture 17。

We're going to study two important paradigms today that are actually used in modern computers。

One is a very general purpose paradigm， as you will see， a very long instruction word architectures。

It is a very principled approach to design computers by making the software complex and hardware simple。

Or the other way around if you want to think about it。

 make the hardware simple as possible software does all the heavy lifting to get the high performance。

 which is a very different approach than what we did with auto order execution right in automotive order execution。

 we said software stay as this。😊，We're going to exc everything in hardware right by scheduling instructions out of order。

Here， the software will be responsible for doing the scheduling of instructions and hardware doing none of that。

And then we're going to talk about systolic arrays。

 which is really the basis of many machine learning exploreators today。

 so hopefully it'll be exciting Okay so weIW architectures so this is where we are we are covering a lot of micro architecture。

 but today actually we're going to cover not just micro architecture。

 but also some hardware software interface， which is the execution model。😊。

And we've covered a lot of approaches to getting more concurrency out of programs and I'm going to start actually by giving an overview of superscalear execution because superscalear executions at paradigm that's very hardware oriented viaIW is going to be a paradigm that's very software oriented I'm going to contrast if you remember this a slide that we used in lecture 15A and we discussed the idea of superar execution it's a very basic concept the idea is to fetch decode。

 execute and finish or retire multiple instructions per cycle as opposed to doing it for one instructions per cycle do many instructions per second and we said that today many processes are eight white eight instructions per cycle。

😊，But of course， to be able to do this， you need to have the hardware resources。

 you need to have the hardware resources concurrently。😡，The fetch Decode execute retired。

8ight instructions per cycle let's say and you also need to in hardware do dependence checking across those concurrently fetched instructions remember we're doing dependence checking horizontally in the pipeline if you have single instruction if you're fetching decoding single instruction if you're fetching decoding executing multiple instructions than a given cycle you need to also do dependence checking vertically so dependence checking needs to happen both horizontally in the pipeline and also vertically in the same cycle which makes the design much more complex。

Today we're going to have a solution to a different paradigm。

 but these are also slides that you have seen in lecture 15A。

 basically to be able to execute or fetch multiple instructions per cycle。

 we need to essentially have a mechanism to fetch multiple instructions per cycle。

 decode and access the register file for multiple instructions here you're using only two instructions。

 AL use enough AL use to execute concurrently multiple instructions per cycle enough force the memory。

 et ce。😊，But of course dependences make it tricky you need to detect dependencies between concurrently fetch instructions and delay the instructions whose data values are not ready so we are very familiar with all of these concepts and superscalear processor makes it harder because you need to detect dependencies but if there are no dependencies between concurrently fetch instructions as you can see over here this ad is not dependent on load this end is not dependent on sub this store is not dependent or then you can get two instructions per cycle that sounds good but if you also saw an example where there were some dependencies between instructions as you can see as a result you are not able to let's say finish two instructions per cycle and your instructions per cycle can go down significantly in this particular case and then I also asked the question in that lecture can you do better can you reorder the instructions to actually improve the performance that you get out of a superscalear machine and the answer was yes the programmer or the compiler can do that reordering such that。

And instructions go in the same cycle， Then you can actually achieve the benefits of a superscalear process。

 But the hardware still needs to be there， meaning the hardware still needs to do dependence checking。

 both horizontally in the pipeline， as well as vertically in the same cycle。 And that's expensive。

 essentially。So that is all review Now what is VIW architectures essentially。😡。

The concept is very different from superscale， its trying to achieve the same thing。

 but essentially in superscalealar， we did everything in hardware。

 we fetched multiple instructions per cycle and checked the dependencies between them and hardware was doing the tough job of actually doing all of that。

😡，In VIW， the approaches。Put that burden on the software， essentially software。

 it could be the programmer， but hopefully the compiler。😡。

Tackax independent instructions in a larger instruction bundle together called a very long instruction word essentially。

 such that they are fetched and executed concurrently so that hardware does nothing。😡。

Nothing in terms of dependence chicken。Software guarantees that instructions that are fetched。

And the same cycle are going to be independent of each other。That sounds good， right？

That'll be ideally great， but we're going to see the downsides of it also。

 so hardware fetches that executes the instruction in the bundle concurrently， essentially。😊，So。

 essentially。This is not only done in the pure RealIW model， you don't do adjust vertically。

 but you also it across the pipeline stages， meaning horizontally in the pipeline。

 such that hardware doesn't need to have any dependency checking。

 you eliminate depend checking hardware， you put that burden to the software。

 so software exactly knows the micro architectural structure of the pipeline。

 it knows there are so many stages， it knows how many cycles each instruction takes takes。

 it knows how many instructions， the hardware is capable of fetching concurrently。

 and does all the depend checking， instruction scheduling in those pipeline slots。😡。

That sounds like a beautiful model if it works， of course， right？So the idea is hardware is simple。

 it doesn't do complex things， software is complex。

 it does all the code scheduling to keep the pipeline full and fully utilized。

 both at the horizontal and the vertical dimensions。😡，So this is the philosophy， simple hardware。

 complex compileilr。😡，Very different from what we have seen so far。

 this is why this is one one of the reasons it is actually a very interesting and important paradigm。

The big things come when people think differently。If everybody' is thinking the same。

 big things will not happen。 Here's an example of big things happening when someone thinks differently from others。

😡，Okay so this is my pictorial depiction how this works essentially what you do is you have a program counter。

 it is still a sequential execution model， once you get to that program counter。

 that program counter really encodes multiple operations。😊。

So you cannot address these individual operations individually whenever you get to a program counter。

 you fetch a very long instruction word that contains multiple operations and in this case。

 four operations。😡，Add load， move， multiply。And you fetch them。

 compiler guaranteed them that they're independent of each other。

 there is no dependence between them because compiled at the analysis of the code and re orderedder things。

 and then basically you fetch them and you directly supply them to the processinging elements。😡。

That sounds beautiful。Now there is also something else processinging elements compiler also knows which processinging elements is where。

 so I've said it knows that let's say this processinging element is capable of executing load instructions but none of the other ones is capable of that it could be possible the processinging elements don't need to be heterogeneous they can be don't need be homogeneous。

 they can be heterogeneous then the compiler knows I can put a load only in this position。😡。

In the instruction so that when the hardware featuress it。

 it directly has a wire and routes the load to that location as opposed to having some sort of shuffling network where you need to shuffle instructions from one location where you fetch it from to the crossing element that may be far away。

 so hardware actually gets simplified for multiple reasons。😡。

As you can see not just dependency shaking， but if you actually expose the structure of the pipeline。

 where are the processing elements， assuming they they have differences between them。

 then the compile can actually help you reduce the hardware cost and this model was introduced in this beautiful paper。

 very long instruction word architectures and the ELI stands for enormously long word instructions 512 and it was 512 because this was 512 bits。

😊，So far we've been talking about 32 bit instructions， right in MIPS。 This is 5 12 Bs。😡。

So if you think about a MIPS instruction， this could be the8 instruction， no， not eight， right？

Is it 16， 16 instructions， yes。And we're going to see people have tried to design machines that can concurrently do 28 instructions。

 for example， it's beautiful， you can exploit parallelism very nicely。

And hardware doesn't become complex。 Okay， so let's go into a little bit more detail。

 I give you the key idea。 The rest is detail and also a little bit analysis and also a little bit history。

 I'm going to give you a lot of history of this。😊，paradigm we thought this paradigm was not working。

 but it is actually used in modern machine learning Explorators today also to supply work to some other units so a lot of the paradigms we study are used in different ways today and it's actually quite powerful okay so basically you have a very long instruction word that consists of multiple instructions packed together by the compiler。

😡，Again， anything compiler can do with this programmer can do also。

 you can do it to yourself if you have a VIW machine， but it's very tough for the programmer。

 of course， right you need to do all the analysis that the compile do so packed instructions can be logically completely unrelated。

😡，You will see what this means when we actually talk about CD vector processors or GPUs next week。

 or not next week， next next week， you can rename next week to next next week whenever I say that because clearly next week we don't have lectures。

 but basically in that case in a GPU for example are vector processor。

 the instructions are the same you fetch one instruction。

 but you actually encode many operations on different data elements here the instructions are very flexible。

 it could be very different from each other。😡，So the idea is to have the compiler to find the independent instructions and statically schedule them。

😡，Or pack them or bundle them into a single VIW instruction in the same single cycle and also do it for across multiple cycles such that the pipeline is completely full so that you don't need any independence chicken。

😡，So a traditional or purest VIW characteristics are like this， you have multiple instruction， fetch。

 decode， execute， retire， you have multiple functional units。😡。

So hardware becomes complex from that perspective。😡。

But hardware is simple because there is no dependency checking。

 all instructions in a bundle are executed in lockstep， meaning。😡，If all of the instruction。

 all of the instructions are kind of scheduled such that they finish at the same time， if possible。

 we're going to see that this is going to be very difficult with memory instructions when you do a load for example。

 if you have one load in the bundle，😡，That may need to wait because it may take a long time， right？😡。

So when that needs to wait， all of the instructions need to be so you stall the entire pipeline。

 and this is going to be one of the big downsides of this paradigm。😡，And as I said earlier。

 instruction and bundle are statically aligned so that they can be directly supplied to the functional unit so that you don't need to route the instructions from one place to another。

 we already discussed that earlier with the picture。😡。

So let's take a look at what these bundles look like。

 so again this is actually a very similar quote to the superscalealar code that we have seen earlier。

😊，What the compiler does this compiler analyze the code and make sure that instructions in a bundle are independent of each other。

 so this ad is not dependent on load， that's bundle one。

 this end is not dependent on sub that's bundle2 and this store word is not depend on or that's bundle fee the compiler also does it between instructions such that for example。

 an instruction doesn't depend on the load because if you remember in the pipeline structure that we have seen if there's an instruction in the bundle2 that's dependent on the load over here you cannot you need to have a stall right because you cannot forward the data value there is this load stall that you need to obey which discussed when we discuss pipelineing so the compiler makes sure that the instructions that come after a bundle where there is a load are not dependent on the load for example so compile needs actually do the scheduling both horizontally and vertical。

So this is how the instructions get executed and in this case there are no dependencies that sounds good so you get ideal IPC which is two the question of course is what if the compile cannot find an instruction to put in a bundle because there are a lot of dependencies in the code the compile was not good enough in its analysis etc。

 then you basically had a no operation right， no output。😊。

Which means that you waste some of your utilization， potential utilization of the pipeline。

 And this is going to be another issue with this paradigm。 So one issue is if this load。

Needs to wait for longer because load latency， as we will see later in the memory lectures。

 load latency can be very long。😡，If you hit in the cache， as we will see in caching later。

 it could be one cycle， but if you miss in the cache， it could be 1 hundred0 cycles。

The compiler doesn't know whether it load whenever it generates the address。

 the data will be in the cache or not right so the compiler schedules the instructions assuming that it hits in the cache but when you execute it if it misses in the cache。

 then that bundle will wait 100 cycles。😡，Okay， and this is going to be the difficulty in dealing with instructions this way。

😊，Because。Compared as everything， hardware cannot do anything。

 whereas if you remember in the out of order execution model that load weights。

 but other instructions can be fetched and executed right here you stop that bundle stops so no one else you can get executed。

😡，Okay， that's the downside of static scheduling。So I'm giving you the downside and upside so as you can see。

 we're going to summarize them later。Okay。So basically that's what I said。

 lockstep all or non execution， if any operation available instruction stalls。

 all concurrent to operations installed， no later operations can continue in the pipeline。

 why to keep the hardware simple。😡，This is exactly the opposite of Autoword execution。

 Autoword execution one some stalls， there are other instructions you can try to find and execute。

 right？😡，That sounds good， but there is a trade off here。So in a truly VLI W machine。

 the compiler handles all data dependence really distorted， as we've discussed。

 hardware doesn't perform any dependency checking ideally。😡，But unfortunately。

 if you have a variable latency operation like a load， sometimes you hit in the cache。

 it's one cycle， sometimes you miss in the cache it's 40 cycles， sometimes you have to go to memory。

 it' 00 cycles， loads are actually very problematic in modern machines as we will see in the memory hiarche lectures。

 you cannot know essentially how long an instruction will take so it's very difficult to schedule things。

😡，So that's going to be the Achilles heel of this so in codes that where you can analyze really well fitting into your cache this paradigm works really well that's one of the reasons it's actually employed nicely in some cases when you need do matrix vector multiplication for example in modern machine learning workloads because you can analyze some of those codes really really well。

😡，Okay， so I'll also talk about some history， Josh Fisher was the main person who developed this idea。

 and you can see the title of one of his papers， like parallelel processing。

 a smart compile and a dumb machine。Very different from what other people were doing at the time。

So philosophy is actually somewhat similar to reduced instructions at computers that we had discussed。

 we discussed that instructions at complexity is something that you need to consider when you actually design an instructions at architecture。

 if your instructions are complex， your hardware becomes complex because you need to execute them if your instructions are simple。

 your hardware becomes also simple right in a sense VIW philosophy is very similar to that risk philosophy so let's talk about that。

😊，Except VIW adds multiple instructions in parallel as well okay I don't know anyway。

 I don't want to deal with it right now。There's some thing over here that I'm going to later fix。

 but risk philosophy was initially developed by IBM John Cock who's a touring award winner actually。

 he basically said compilers should do the hard work to translate high level language to simple instructions。

 ideally controlling。😊，Complier basically could translate an instruction to control S。And of course。

 the compile should also re orderder simple instructions for high performance。

 so risk processors have a similar philosophy。😡，Hardware does little translation or decoding as a result。

 hardware is very simple。😡，The LIW essentially says takes it to the next level。

We also want to fetch and execute multiple instructions。 So in the vertical dimension。

 I compileed as the hard work to find instruction level parallelism as well。😡。

Hardware stays again as simple as possible， each instruction in a bundle executes a lock step so these two things are actually similar to each other and they had a lot of influence in the field clearly so why do we want to keep hardware simple this is kind of obvious but let's reiterate because if you have very simple hardware it's easier to design it's easier to verify today actually verification cost of a modern processor is a lot of the time 60% of the cost maybe more than 60% 70% of the cost is verifying that it works correctly。

😡，People design the processor， implement it， and eventually they need do a lot of testing。😡。

Both online and offline to make sure it works and that's actually very costly so if you have a very simple processor it's a lot easier to verify easier to design。

 it's also low power， hopefully it's also higher frequency。

 you can make the frequency very high right。😊，Okay。So this is from Josh Fisher's paper。

 I think I've said everything over here， but maybe。

To say that each operation in a bundle requires a small。

 statically predictable number of cycles to execute。So this is good to think about。

 statically predictable means whenever you're in compiler， you know how long the instruction takes。😡。

That's not the case， unfortunately， for especially memory instructions。

But that's also not the case for some other instructions if you do some optimization， for example。

 I'll take a multiply instruction。😡，Does the multiply instruction always take n cycles。

 let's say n is eight cycles I just picked。Basically the answer is depends today， why。

 because if you're multiplying by zero， you can have a shortcut in the circuit that says， oh。

 the answer is zero because one of the opera is zero you could do it in one cycle with any quality checker。

😡，So sometimes a multipllyier takes one cycle， sometimes a multiplier takes eight cycles。

 depending on the data value， the question now becomes。

 is this statically predictable can the compiler predict whether a multipier is going to take one cycle or eight cycles？

😡，Probably not compile and you analyzeize the data values。😡，If the data value is predictable。

 that's good。😡，Absolutely， but but if the compile doesn't know the data values。

 which is the common case， then the compile cannot do anything。 It cannot statically predict it。

 essentially， it will basically need to say， okay， it will basically need to assume some。😡。

If it assumes one cycle， then it basically schedules the dependent extraction after one cycle。

 but then it's assuming that multiply is always operating with an up end of zero。

 which is probably not a good assumption， right？😡，If it assumes eight cycles。

 when the multiply has an upper end of zero， it did all the hard work and it didn't really yield any benefit so that's the difficulty basically when you do the scheduling at the compile level you don't know the latencies of all instructions and especially load instructions are the culprits。

😡，Okay， let me give you some history also so Josh Fisher actually developed this idea and then he basically went up and start his company and he built seven white。

 28 white wheel IW processors， Bob Bro was doing similar things at the same time and he built his own company。

 these are actually very early competitors let's say to complex processors at the time at the time the complex processor were similar tech E to6 like VX。

 it was one of the complicated and top notch processor。😊，And later， transmitmita Crut。

 which we mentioned earlier， it basically had the same as an idea， oh。

 I want to execute complex codes。😡，But I want to actually have a very simple hardware。

 so I'm going to translate the X86 binaries to internal VLIW process now you know what that VIW means you have a software translator that optimizes the code that figures out how to turn that X86 binary into VIW process such that the hardware stays simple software is complex。

😡，This is ISA translation that we've seen and we're going to look at that later。

And more recent later actually people have designed digital signal processors and embedded processors。

 and these were the most successful commercially until the latest machine learning excators。

 let's say， and these folks actually did embedded processinging and a lot of the code over there is relatively aestheticly predictable。

😊，That's one of the reasons they were successful Intel actually also had an innovative project in the 1990 s they basically when when they were moving from 32 but X 86 to 64 but x86 they also wanted to change a lot of things in the instructions to architecture。

 they wanted to move to a VIW type of engine but they said。😊。

This was not fully VLIW it was based on some of the VLIW principles。

 in fact it violated the most important one in a bundle you could specify dependencies so the compiler can put dependent things in a bundle but the compiler says oh this instructions depend on this instruction because compiler can do some of that analysis clearly right so this simplifies the hardware because hardware doesn't need to check the dependencies because the compile is telling them。

 but it's not perfect VLIW in the sense that not all instruction in a bundle are independent of each other。

😡，So Intel actually tried hard on this one， so how do they encode dependencies a few bits in the instruction format specifies the explicitly which instruction and the oneguard depend on which other ones so again I will not go through this but this was actually something Intel pushed a lot but unfortunately it was very difficult to move the software world to this sort of paradigm as a result Intellect abandon this even though it was a very innovative project to change the nature of X to6 let's say。

😊，Okay， so that's some history。 We're going to see a little bit more history。

 but let's talk about the tradeoffs。 I think these are actually hopefully clear。

 There's no need for dynamic scheduling hardware。 So you have simple hardware。

 This is at advantage clearly。😡，No need for dependence checking in aIW instruction。

 you have simple hardware for multiple instructions。

 you're not renaming all of that hardware complexity goes away。😡。

No need for instruction alignment after fetch to different functional units， simple hardware。

 basically advanceds are all simple hardware as you can see， right？😡，And simple hardware。

 in turn has benefits that we discussed disadvantage is now the burden is on the compiler。

 complex compiler， essentially。😊，AComp is to find an independent operations per cycle。

 not only that it actually schedule the operations inside the pipeline also so that the pipeline doesn't stall and if it cannot do that at any point at any slots it has insert a norm。

😡，So basically there are a lot of no ops in a VLIW instruction when the compiler is not successful and there are many workloads where the compiler is not successful。

😡，Because compilere doesn't have perfect knowledge about what's happening in dynamically。

So if you have no ops and instruction， you lose parallelm and then code size also increases because you need to encode noOs now right。

 you need to encode all of the operations that the program needs to do plus no ops， right？😡。

So if you add 100% no ops your program size becomes double right and if your code size increases then you have other issues like now your caches need to become larger or you get more cash misses。

 ettera， so there are a lot of issues you don't want high larger code size。😡。

There's another disadvantage because your compiler is so tightly coupled with the micro architectureecture。

 in fact now the compiler， the micro architectureure itself is what the compiler is optimizing directly for。

 whenever you change the micro architectureure your compile needs to change also。😡。

And this could be any small thing in the micro architect also right you change a latency here。

 you change another latency there and the compiler。

 what the compiler did may not be very good for performance so as your execution with instruction latencies and functional units change。

 you need to recompile code to get the best performance or even to be correct in some cases right？😡。

Potentially。So this is very different from superscalealar processing。

 which is completely transparent to software right you don't need to do anything in superscalealar processing and if you do out of order on the top of superscalealar。

😡，You schedule the instructions dynamically。 and as a result， you can get good parallelism as well。

Okay， and then the lock step execution， this caused independent operations to stall as we discussed。

 as a result no instruction can progress until the longest latency instruction a bundle completes and if that's a load you're in trouble because the load may be taking hundreds of cycles。

😊，Okay， so these are actually the big disadvantages that unfortunately hurt VLIW paradigm and as a result it wasn't successful in the general purpose domain。

 so today you don't see a lot of general purpose processor that are VIW all of the amount of out order super scaling。

😡，But in other domains it was very useful and we will see what those are quickly so essentially you simplify hardware but you require complex compile techniques and the so compile approach of EIW has several downsides thats reduced performance。

 no tolerance for variable or long latency operations， loads。😊，And loads are extremely important。

 as we will see when we talk about the memory lectures。

 most of the execution time of modern prosterors is spent on accessing memory。😡。

If you don't handle loads well， if you cannot tolerate their latencies well。

 your performance will tank。😡，Okay， and then there are two many knobs in many workloads it turned out that you have a 28 H white machine。

 for example。😡，Maybe you have four IPC。So your machine is huge。

 but you're not getting enough parallelism because you cannot most of those instruction slots are used for not。

😡，And then the static schedule is intimately tied to micro architecture。

 meaning code optimized for one generation can perform poorly for next。

 even though the machine improves。😡，If you don't recompile your code。

 meaning if you don't spend time on your compiler to do a better job。

 your machine will not be utilized well this's again very different from improving your let's say increasing your instruction window size and out of order execution immediately you get benefits hopefully whereas here you need to recompile the code。

😡，Okay， so these are the downsides that made VLIW not commercially successful in the general purpose domain but。

😡，The huge upside that's why there we have two pluses over here。

 everything is downsizeized and upside okay most compiler optimization that are developed for VLIW are used today。

 so if you're using a compiler tank VIW paradigm。😡。

Because those are the optimizations that were enabled and went into all of the processes because people said。

 yes， these are designed for BI only， but it's good for superscalealar as well。😡。

So people adopted all of those compiler optimizations。

 the beautiful compiler optimization I'm going to show you a couple of them and they not only improve parallelism。

 but the enable other code optimizations as well， so by scheduling code in an intelligent way and ignoring some。

 let's say not commonly executed code， you can do optimizations that across commonly ignoring uncommonly executed codes you can do optimization that causes a commonly executed path so it can actually reduce the complexity of frequently executed parts of a program。

😡，And this is what's employed in dynamic compilers， but also a lot of static compilers today as well。

 so you're going to see some of the dynamic compilers that I kind of threw at you in earlier lectures。

 but hopefully they' all become a little more clear this way。😡，And then there's also another plus。

 VLIW is actually a very successful paradigm and parallelism is easier to find by the compiler as a result in some limited special purpose domain like embedded markets。

 digital signal processor in some GPUs， early GPUs。

 and more recently in machine learning excccerators where you can actually analyze the code nicely。

 and you can steadily predict some things you can actually get benefit from realLIW。😊，Makes sense。

Okay， so let me give you an example of these compile optimizations because this is really the big benefit of the LIW that's generally employed essentially without many of you knowing it perhaps。

 or many people even using compiles not knowing it potentially。😡。

People who are developing combined know it， of course。

But basically this is an example again from Josh Fisher's seminal paper these are basic blocks you can see a basic block is essentially a piece of code with potentially multiple entries and multiple exits right it ends in a branch you enter the basic block and you branch out and you go to another basic block this is a control flow graph of the code it looks like a mess initially。

😊，But if you profile this code at compile time or dynamically。😡，Maybe you figure out that， oh。

 these are the， this is the path I usually take in the program， this is a frequently executed path。😡。

Okay。So if you identify that， this paper also introduced trace scheduling this well another paper introduced trace scheduling before this or other reasons actually。

 but for realLIW it works really well， the basic idea is basically you。

Find out the frequently executed path， How do you find out the branch is 99% going this way。

 the branch is 99% going this way， 99% this way， 99% this way， 99% this way。

 so probably you're going to execute this code very frequently。

 dynamically assuming your profile is representative。😡。

Let's assume that now what you can do is you can optimize the code along this path。

Meaning cut the connections， you cannot exit from here when you enter this code。

 you can exit from some places， perhaps， but essentially you look at this look at the set of basic blocks in unison as if they're going to execute。

In this path， you optimize the code and you do some things that would be incorrect if you actually got out of this control F in dynamic execution and you make up code for it。

😡，Essentially， you optimize the code as if this is going to execute in unison。

 but you also add exceptions， if that's not the case in dynamic execution， you take the branch。

 for example， outside， you add some makeup code that undos things you think that you did because you thought the court was going to execute in unison。

😡，Makes sense， right so this increases the code size because you need to add a lot of this makeup code。

 thiss actually called makeup code。😡，You basically make up what you've done undo code also undo blockss。

 you actually undo what you did that you shouldn't have done hopefully that makes sense， right？😡。

So now your quote is really optimized for this path。

 but it's also correct if you actually get out of this path， you can get out of it。

 but now you have to pay the penalty of undoing stuff that you did。😡，You shouldn't have done okay。

 so that's a beautiful idea it's called trace scheduling and this is the basis of a lot of compiler optimizations。

😡，Compile optimizations can be done。Without this， but this enables compiler optimizations。

 and the main reason is you don't need to consider branches。😡。

So a lot of compiler optimizations are hindered because okay you want to move some code from here to here。

 but there's a branch there， I cannot move that code right if that branch goes that way yes I can move it。

 but now I'm assuming that branch goes that way so I can move code freely within that block， right？😡。



![](img/51312d66a368f99520e4f85509618edd_2.png)

![](img/51312d66a368f99520e4f85509618edd_3.png)

So this makes the compile very powerful。😡，Okay so that's this is why this paper is very recommended。

 even though we don't talk a lot about compilers in this course。

 this is actually the really basis of modern optimizing compilers okay we have seen some of this compile optimizations before like basic block reordering if you remember right we reordered basic blocks when you discussed basic block reordering we reordered basic blocks such that did not take branch prediction。

😊，Is good， right， is's effective。 It's kind of similar to that， right， except in this case。

We are relying on branch prediction。 So if the branch is executed such that you mispredted you flush the pipeline here。

 instead of flushing the pipeline， you're relying on the compiler if you actually go out。

You do some other stuff。To undo what you shouldn't have done， okay？

Okay so let me give you one other idea， there are a lot of ideas this is a very important paper also it was published in 1993 by Wenmehu's group essentially there's a problem with trace scheduling that hinders code optimization you can do better essentially people always ask can we do better in compilers so we've seen a lot of hardware can we do better let's see a compiler can we do better。

😊，One of the problems with trace is you have a single entry， but you have multiple exits over here。

Okay， no， no， sorry you can now multiple entries multiple exits。

 so you can basically enter the trace from somewhere here。And you can exit the trace anywhere。

So it's multiple and3 multiple exit， which actually hinders some of the compiler optimizations。😡。

But superblock says that if we can combine frequently executed block such that they form a single entry multiply the larger block。

 which is likely the executed as a straight line code。

 basically you cannot enter from somewhere else。😡，So if you look at this as the trace and you exit and then you can enter again and you optimize this path。

 but the optimization of this path is hindered by this entry into the code Superblock says once you enter this thing。

 you're not going to enter from somewhere else again， you can exit， but you're not going to enter。

So this reduces actually branch mis predictions very well I' will not go through that。

 it enables aggressive compiler optimization and code arguing within this super block Of course the down size are increased code size。

 more recomplation and profile dependence let me give you an example。😡。

So this is our messy control flow graph， each of these end with a branch and these are the probabilities of which way the branch goes so after a 90% of the time the branch goes to B 10% of the time you go to C。

Okay， so essentially you figure out which what is the frequently executed path and this is a frequently executed path。

😊，And then you identify this trace now this is a kind of a trace a frequentlyly executed path and you have the probabilities over here as you can see 1990。

 9090 is a low probability by the way， ideally you would like to get to fire， but that's okay。

 this is a trace。😊，It has multiple entry points， you could enter from here， for example。

 enter from here， and then it has multiple exit points， you could exit from here here， here。

 and then you could of course enter from here at the top。😊，Now。

We want to eliminate the side entries Basically when we exit the trace。

 we don't want to enter it again okay or we don't want to enter the trace anywhere in between you just want to enter it from the top and execute that straight line code and we can enable a lot of optimizations because there's no incoming branches to be able to do that this work introduces what's called a tail duplication it basically duplicates the basic blocks after side entrance so remember there's a side entrance over here there's another side entrance over here and then they both execute F afterwards so why don't you actually have another copy of F like that these whenever you enter this code you don't。

😡，Enter the trace again， you basically go to some other place in the code and execute another copy of it。

😡，That's the idea， basically。Essentially this transformeds a trace into what is called a superblock in this work now thiss a superb meaning I don't know you can take issue with the name but that's what the people named and that's what everybody uses today essentially you have a code with a single entry points and multiple exit points but you cannot enter anywhere other than the top now this enabled a lot of code optimizations internally as that paper showed let me give you one example。

😊，So this is my I ignore a lot of the branches I just look at the operations over here right the first operation is multiplying R2 and 3 putting into R1 and then 99% of the time you go to this multiply essentially you do the same thing if you realize but 1% of the time you increment r2 by one so you should go this way 1% of the time。

😊，Okay， so if you do a super plug formation， this is what you do， you form a trace。😊。

You eliminate the side entry here， meaning you duplicate this one， put it。

 if you exit from here 1% of the time， you execute this and you also execute a copy of this。😡。

So that you don't enter back。Now， once you eliminated that entry back， this code。

You can reduce the strength of this operation。 Why， because you already calculate this。

Youre right these multiplies are the same the realization is that you can eliminate you can basically identify the common subject expression this is called common subject expression elimination r two times three is a common subject expression between these two operations they're both doing R2 to times three。

😊，So you realize that this already computed our times three， so I'm just going to move。😡。

R one to r 3D for this so I reduced the strength of a multiply to a move and moves are much cheaper than multiplies okay so even this three instruction code which is very beautiful I think demonstrates the power of optimization this couldn't have been done if you entered back right if you actually didn't duplicate this multiply instruction over here if you actually did the ad and entered back you couldn't do this optimization because you don't know which one。

😡，The use， right。So you can see now the power of optimization right。

 and this is applied this to a large block， it becomes actually much more powerful。😡。

Okay so if you're interested this is a paper on super blocklock formation and we have some lectures on static instruction scheduling that are old when Mehu's group did a lot of work on optimizing compilers and they're responsible actually for a lot of improvements in compilation they're also responsible for convincing Intel to do IA64 in part which was a great experiment but it didn't pan out well but that's what researchers are for that's what progress is for right you got to do experiments and sometimes it fail I most of the time fail and it didn't fail I think。

😊，Okay， so there's also hyper blockss if you're interested， but I'm not going to talk about that。

 So people actually kept improving these things。 there's more on top of this。

 This was an early compiler。 So people actually worked on compiler this is。😊。

Josh Fisher student John Ellis when Josh Fisher was a professor at Yale University before he said I'm going to do my startup and do a lot of good things。

 let's say he basically his group designed this compiler so a lot of the optimizations in a compiler actually goes to memory essentially identifying which。

😊，Instructions are independent of memory operations。

 which memory operations are independent of each other。 So memory becomes a huge problem。

 essentially。So if you look at all of these compilers that are developed。😡。

A lot of the time is spent on identifying which memory operations are dependent on each other。

 which memory operations are how long latency potentially。

 so that's why we're going to talk a lot about memory later on。

 figuring this out in a compile is very， very tough and that's one of the difficulties of VIW in general。

 it cannot handle variable latency or memory operations very well。😡，Okay。

 so there are lectures over here and this is a compact version。😊。

Now let me I think we still have good a couple of minutes and you can ask also ask questions if you have questions。

 but basically I I'm going back to ISA translation。

 so what we're talking about is an ISA actuallyIW is an ISA and also a micro architectureitecture。

 it's really a paradigm of execution act。😊，You don't out ofward execution， for example， is not ISA。

 it's a paradigm of execution， but it's hidden， it doesn't touch the ISA right here we're touching the ISA and the hardware right across the stack and the compiler in the end。

😡，So if you can do that， you can actually do a lot of ISA translation and you can get some of the benefits of the VLIW without having the downside potentially and people have tried that essentially you can a program this is actually an old site also from another lectures。

 you can program a visible ISA a virtual ISA and you can convert it to implementation ISA。

 you can convert complex instructions to simple instructions as current proceduress do as we've discussed right or you can actually start with a scalar ISA like X86 and convert to VLIW ISA。

😊，So we've seen earlier that Intels and AMD's X86 implementations translate X86 instruction to programmer invisible micro operations in hardware。

 right？😡，So that's one sort of I I say translation completed on hardware such that。

The difficult instructions make you don't need to implement them directly in hardware。

 you can actually convert them to simpler instructions in hardware。

So that makes the hardware simple by adding more hardware。😡，That makes part of the hardware simple。

 Okay， but what else you can do， you can actually do take X86。

 a complicated IA and translate them to some secret。More open source doesn't matter。

 but secret so that if you want to make a lot of money。

 let's say secret we YW instruction and software， so that's what transmittter did。😡。

So there are trade offs over here， of course that some of which we discuss so this is what I showed you in the past a little bit。

 but now this makes a lot of sense these folks said basically we're going to compete with the best X to six processor at the time。

Again these are very motivated folks， we're going to design the best system at the time。

 but we have a very different idea， we're not going to do things in hardware。

 we're going to take X86 code， we're going to design some software that can translate it with a lot of code optimizations。

 all of the code optimizations we talk about and many of we didn't talk about that the code morphing software and it's going to spit out via YW instructions and our hardware goes is going to be very simple and beautiful。

😡，So we can design this hardware extremely fast。😡，And we're good software designers so we're going to design this code morphing software fast also。

 and then we're going to compete with X8 to 6 and this was actually a pretty interesting competitor。

 unfortunately didn't pan out also because this software has a lot of overhead and also it has a lot of the downsides that we talked about。

 but they did actually produce processor and in the end they were power efficient but it's not necessarily very high performance。

😡，But again， this picture that I showed you in the past， people actually do it in real life。

So this is the transmit approach essentially you take X86 and translate it to VLIW with in this case they used a software translator。

 which was actually very efficient but not necessarily high performance。😊，Okay。

 if you're interested in this， there's a beautiful paper， White paperper by Transmita， Alex Kleber。

 who developed a lot of their compiler technology， wrote this white paper and that talks about a lot of the code optimizations that they do and a lot of support that they added to the hardware so that they can actually get the code optimizations to be very highper。

😊，So what has been successful， more successful， let's say is a bigger company doing this internally without competing with anyone。

 let's say so this dynamic binary translator is essentially a code optimizer。

 it basically translates x8 to6 to some internal army instructions not be a YW necessarily。

 but it does a lot of code optimizationals。😊，So a lot of companies internally do it。

 sometimes they write papers about it， so that's Apple and V actually does that also。

 So these code optimizations that we discussed。They are done in those code optimizers basically。

 you can see that all their are instructions and you go into an optimizer。

 that optimize actually optimizer is actually software and it's using a lot of the concepts that are developed by VLIW processors。

😡，Some of them actually have hardware support as well internally。Okay， but if you read， for example。

 here， code designing a hardware processor with a dynamic code optimization software system creates both additional validation。

 exposure and benefits， the DC system can be upgraded in the field to address functionality。

 performance or security issues。😊，There's a very nice summary of what a dynamic code optimize can do for you。

 you can actually upgrade it in the field also， but again keep in mind that if all of that push for VLIW didn't exist it was going to be very difficult to develop those compile techniques as quickly as possible so even though weLIW paradigm may not be the dominant paradigm today。

😊，It has had a whole lot of influence in real systems， and its influence is going to continue。

 as we will see in the next lecture。So again we are talking about ISAs。

 this is a lecture that's kind of out of place， but we are also talking about execution paradigms。

 once you're talking about execution paradigm some execution paradigms are really spanic cost to stack so VLIW is one of them sytolic carries is going to be another one of them as you will see soon。

 but it's going to be a completely different one。😡，Okay。

 there's more lectures if you're really interested。But if you're not interested。

 you don't need to look at that。Okay， any questions， we're done with VIW？🎼Yes。

 please if they were different but very similar， we could just。そ。So yes， in the compiler。

 you can detect some of those。 you can do vectorization。 Yes。

 we're going to talk more about that when we talk about GPus。😊，But yes。

 an intelligent compiler can figure out how you can vectorize operations as well。Okay。

 I think let's come back when the bell rings and then we're going to talk about systoic architectures。

Yeah go。

![](img/51312d66a368f99520e4f85509618edd_5.png)

![](img/51312d66a368f99520e4f85509618edd_6.png)

![](img/51312d66a368f99520e4f85509618edd_7.png)

あ。Yeah。佢是过为呢。See you。Okay。疲ります。过。最好。Okay。二。啊。Yeah。Yeah。🎼，🎼我你想。Yes。Yes。

Okay I think let's let's get started before we move to systolic area architectures。

 I should mention one thing because everything we discussed earlier like compiler are doing optimizations we were looking at for example。

 how often is the branch taken or not taken how does the compiler and all that information it profiles the code essentially it puts some input data and basically checks based on some input data sets what fraction of the time branch goes taken or not taken。

😊，So clearly these optimizations are dependent on how good your profiling data sets are right。

 so keep that in mind we discussed this earlier when when we do any static code optimization。

 you're dependent on the input or profile guided optimization you're dependent on the goodness or representativeness of the profile input set。

😡，So keep this in mind a lot of these optimization are depend on profiling where the compiler runs the code。

 figures out which path is a frequently executed path and optimizes it。

 but if the frequently executed path differs from the frequently executed path if a frequently executed path when you actually run the program optimize program differs from the frequently executed path that the compiler thought whats frequently executed to optimize the program。

 then these code optimizations may not actually provide benefits in some cases they may hurt performance。

 but the compilers also are very careful in figuring out when they may be wrong。

 so they actually try to optimize the code in a way if they're not sure this profile is not going to be very accurate。

 they try to actually be less aggressive in the compile optimization so people actually realize this problem and they actually do a lot of work to avoid profile inputs that representative this issue。

 you cannot avoid it completely of course but you can take some caution。😡。

To fix that issue potentially。And of course， a dynamic code optimizer figures this out。

 meaning it optimizes the code and dynamically while running the code。

 it adds some checks how often did this frequently executed path actually was not the frequently executed path and if enough times it was wrong it goes back and reoptimize the code based on the changes in the dynamic execution so if you have a dynamic compiler you can adapt to these at of course compilation overheads that come at runtime for this very reason hardware designer。

 if you' were designing the compiler and the hardware together hardware actually can be designed to help the dynamic compiler hardware can actually keep some counts do some profiling internally and share that with the compiler saying that compiler you did something wrong potentially so it can actually co optimizetimize the hardware and the software together so that you keep compiling the code but the hardware is profiling the code internally without actually software overhead and they're communicating with each other so that the entire execution becomes better and better。

😊，So if you look at for example， transmitter that was a vision and that they tried to implement and that's true for the dynamic code optimizer at M mediadia for example。

 or Apple， so it's good to keep this in mind if you're designing software and the hardware together you can do a lot of interesting optimizations。

😊，Okay so let's jump into sto area architectures but before we jump into that I should say this because we work with a lot of bachelor's students and they do a lot of interesting work in fact some of our papers have people who contribute in bachelor studies so if you're interested in doing research in the areas that we work on feel free to email us or talk to us you can email me C Muhamd with your interest you can also take the seminar course and our more advanced computer architecture course of course doing the readings helps but basically the key who we're here is talking with us if you're interested in doing research at some point of course taking this course is a very good beginning and if you enjoy it and if you actually do well in the concepts etc so there are many exciting projects and we welcome everyone in general all over the world it doesn't matter if you're a bachelor's student or a PhD student but of course with a PhD student you have more background probably but we do a lot of work on many topics which I'm not going to talk about but some new execution。

😊，I's like in memory computing is very exciting， we may talk about that later。

 but everything essentially we touched on in this class and more， let's say。

Some of you may want to do thesis at some point and we offer bachelor's thesis also if you go to this page you'll see some examples。

 but don't think that that's comprehensive， that page doesn't get updated very often because we're too busy doing research so if you're really interested in doing research in these general topics just contact us even if a topic may not be listed in that page and this page over here is our publications。

😊，Okay so I would also maybe publicize the bachelor's seminar if you're interested in these topics again I would suggest taking the bachelor's seminar course next fall or later。

 essentially this a rigorous seminar on reading papers and presenting them and reviewing them and discussing them and we emphasize a lot of critical thinking and brainstorming on cutting edge as well some really old papers for example the topic that I'm going to discuss systoic eras was presented by one of your fellow students a few years ago and that fellow student did his bachelor's thesis with us he actually worked on some in memorymory computing paper and that in memorymory computing paper got published at an Aswa conference in 2021 I think it's called Sdy I mean you can look it up so he actually did a lot of very interesting exciting early work based on this development and he's a co author of the paper so if you're interested you can take that's just one example there are many examples okay so you can look at the link over here also and this is our group so you can learn more about us also。

By going to our website looking at our newsletters。

 so we release a lot of these newsletters almost every year。

And you can see that based on last time prediction June 23， July 24。

 so the next one should be August 25， I guess。Let's hope so okay， okay。

 so you can also learn more about our research through videos。😊。

Okay and we're proud of our PhD postdoc and other alumni， not everyone fits here。

 but a lot of people who get their PhDs and postdocs and also masters。

 they have become thought leaders in academia as well as industry and you can find more information about them online as well so you're an ETH student you're at a privilege level that's higher than let's say outsiders so if you're interested in doing this you don't need to apply because you're not coming from outside we know you better probably we can talk to you directly and we can discuss with you so talk with us but if you're an outsider meaning you're not here taking the course in person it's the best way for us to get to know you is by you apply。

Okay， with that， let's say brief advertisement， we can move to more execution paradigmdise。😊。

So basically what we're going to do is we're going to cover systolic arrays。

 hopefully we'll cover everything， but hopefully we'll cover the basic important things。😊。

And I'm not going to cover decoupd access executes because it's a very short paradigm。

 but we're going to release a premiere of like a 10 minute lecture if you're interested。

 you can look at it。😊，And next week， well， rename next to next next， next next week。

 we're going to start CID processing vectorinary processor， GPUs。

 which are clearly extremely important today。😊，So these lectures are going to wrap up the essentially different execution models that people have developed over many years。

😊，This doesn't include some of the execution models that we will talk about after we cover memory like processing in memory。

 all of these are actually very processor centric execution models in the sense that you have processor。

😡，Yeah， memory。Memory's job is to just。Serve the needs of the processor processor says load。

 memory says yes， sir， here is your data。Prosor says store memory says yes， sir， or yes， ma'am。

 and here's I store the data。Me cannot speak。Procesor says everything。

So if you think about this as a very unfair model and also a very imbalanced model in the sense that memory cannot do anything other than obeying what the processor says。

 right？😊，So all of these models are like that。But there's a very different way of thinking about systems where memory has a say。

Processor says。Okay， memory， can you do this for me， I have a function， Can you execute this for me？

And the memory says。Yeah， I can do that for you。So you don't need to do you can execute the function that you can really execute。

 and I execute the function that I'm really good at executing。😡。

Because that function requires a whole lot of data。😡，And in the processor。

 you execute the functions that require a whole lot of computation， not a lot of data。😡。

So that's the notion of memorycentric paradigms， which is processing in memory， for example。

 you put computation inside the memory devices such that memory devices are a lot more intelligent and they actually take part in the computation as opposed saying yes sorry。

 yes， ma'am all the time， right？😊，So that's the idea of processinging in memory which is not here。

 but we may talk about it as， and this is something that's unfolding right now and we're doing a lot of research on that topic to enable it so that maybe 10 years later it's taught in classes like this and we're free of just this proscentic paradigms。

 but we can be a much more memorycentic。😡，And just to give you one more motivation for why we're doing this because there's a huge data moment problem。

 you will see that in later lectures， and also procentric is very against nature right if you think about how brain does computation。

😡，In the brain， memory， communication and processing is all a mesh together。

 There's no huge distinction like what we have in our systems today。

You don't move the data huge distances so that you can actually do processinging in the brain。😡，Okay。

 that's just to give you some different motivation。Okay， but now let's go back to procent。

 but a very different procentic paradigm， systolic architectures， this was developed by H Kong。😊。

Well， there was a professor at Carnegie Mill University where I was from actually。

 I was a professor at， so this paper is a very highly recommended paper that talks about the syic paradigm and I was teaching these lectures。

 I introduced these lectures at CMU because they were not being taught so I thought this was a really important paradigm it has to be thought it's very principled and it's going to make its way to real systems at some point。

 2009。😊，Still 30 years like after H develop this paradigm and now that you're listening to it in 2025。

 I can say it has made its way in a major way to machine learning accelerators because it's a very principled approach that it makes sense。

So it's good to believe， it's good to have some fundamental principles。

 even if it's not employed anywhere today， it may be employed somewhere tomorrow。😡。

So it's good to always have that mindset that is open Okay so I'm going to also recommend these papers。

 these are from Google where they actually use systolic arrays to implement matrix multiplication in a very efficient way so that and a lot of machine learning is matrix multiplication and they actually employ this in all of their data centers as well as age devices so it's very cool that this sort of architecture has made its way。

😊，Next week we're going to talk about deep Pes， which is another architecture that has actually been very popular but。

😊，Patients for that。 Okay， so systoic array， systolic arrays are on the special purpose end of the spectrum。

 right This is if you think about CPUs， VIW superscalealar out of order。

 They're all on the general purpose end。 we've been talking a lot about this general purpose paradigm。

 And you've seen this slide before general purpose means you can execute any program。

 it's easy to program and users， but unfortunately it doesn't get the best performance and efficiency on any program on machine learning。

 it's okay， but it's not as good as something that you specialize for machine learning， for example。

 that's true for video， etc。😊，So we're going to talk about GPUs next time you've been programming FPGAs。

 you could argue the order et cetera over here， I'm not going to do that。

 but there are also special purpose machines designed specifically for some applications like the most special purpose machine is where you take a program。

And't do anything but burn it into the hardware， meaning burn it into circuits。

 do what the program does， and you make sure the circuit is doing exactly that and nothing else。😡。

So that's an application specific integrated circuit very inflexible。

 but it's extremely efficient and high performance for that particular piece of the program， right？😡。

So it's usually difficult to program and use and it's inflexible limited set of programs normally people don't do that as much today because they need some flexibility but they could actually customize the circuit so it can do a matrix vector multiplication for example right something important some important journal as opposed to a full program but still that special purpose right its cannot do everything very well so we're going to look at a special purpose system today viaIW as a general purpose paradigm syto is going to be a very special purpose paradigm。

😡，Okay， it's an execution model actually， sytolic array or an execution model。

 they implement what is called sytoic computation as we will see and it's a very general computation but your program needs to be written that way。

😊，This is different from the Wal Neman model， different from the data flow model。😡。

So are were going to forget about。Any of thats we're going to have a different model right now。😡。

But it's going to be more specialized than what can be enabled with one norm and data flow。😡。

So they were initially designed as special purposeerators and they actually remain as a special purpose accelerators and the main reason they were designed is actually convolutions。

 we're going to see we're going to define convolution， how many people know about convolutions。😊。

Okay。Where have you seen it and。It is CNN CNN okay yes convolution neural networks， for example， Yes。

 convolutions are there before CNNs existed actually convolution is the operation that you do on images。

 for example， but yes CNN made it popular and I'm going talk about that also briefly without going into a lot of detail but convolutions filtering paing matching special purpose matrix vector computations and image vision processing signal processing pattern recognition these all do convolutions and different filtering type of operations convolutions actually a filtering operation as we will see soon。

😊，Today they are used heavily in machine learning， systolic arrays these are specialized machine learning exccelerators。

 and their general execution models model can be generalized， as we will see later in this lecture。

 it can be generalized to a way of thinking about programming actually。😊，Okay。

 so let's talk about the motivation， we're talking about 1970s。

 the motivation of H Kong was to design an accelerator that has simple regular design。

 simple hardware， this is what it shares with VIW for example。

 keep number of unique parts small and regular。😊，High concurrency。

 we want extremely high performance at that time energy was not a big concern。

 but today energy is a huge concern and that's why Google's TU has these systolic arrays。

 not just performance。😡，Balanced computation IO， meaning as we will see soon。

 the HC Kung realized and he did a lot of work on this topic and this is one of the reasons why we're compressing in memory as well。

 but he said that if you have a processor that just keeps doing load store， load store， load store。

 you're not balanced， meaning you have a lot of computation power in the processor。😊。

But memory is very slow and has low bandwidth， so need you're basically in bottleneck by memory。

So let me design a hardware accelerator that's not bottleneck by memory or balances the computation bandwidth and the memory back。

 and we will see that in a picture。😡，So the idea is very simple here。

 You start with a processinging element。 This processinging element could be very， very simple。

 as we will see， it could do just multiply and accumulate， multiply an at。😡。

Because we're going to be special purpose， right， we're not going to be general purpose。

 but it could be a general purpose processinging element also as you generalize the paradigm。

And then you replace that crossing element with a regular array of crossing elements。

 it could be one dimensional array， two dimensional arrays， multidimensal arrays， et ceter。

 well we're go to start with one dimensional， and you carefully orchestrate flow of data between the crossing elements。

😊，Suchuch that they collectively transform， they read from memory one piece of data。

 and the first processing on takes it transforms it。😡，Passes to the next one。

 that one takes the transform data， does something to it， does some operation passes to the next one。

 and you keep passing the data between the processing elements。 Eventually you write it back to them。

Okay， so it's kind of systolic in that sense。So the benefit of this is you take a piece of data。

 you read from Memi and you do a lot of computation on it before you write it back to Me as opposed to doing a single processinging element load store load store load store load store load store so that's the idea over here and this is a beautiful picture from AC Kung's paper basically he says that this is a pressing element。

 it could be again as simple or as complex as you imagine it。😡。

But if you're doing you're fetching one piece of data over here and then operatinggrading on it and writing it back to memory。

 you're limited by the memory bandwidth over here， your computation is basically limited by how fast you can get data from memory。

 but if you take the same data element， do some computation。

 transform it past it to another processing element， do some computation。

 transform it and pass it to another processing element and keep doing that。

 you can actually increase the operation little capacity because you're not bound by memory bandwidth anymore。

😡，Makes sense basically you're still bound by how fast you can get the data from memory。

 but you're operating， you're doing more on the data that you fetch from memory by chain these pricinging elements together and you can see that this number is 5 million operations per second with some assumptions here because you have six pressing elements you can do 30 million operations per second。

😡，Okay， so this is a forward looking approach as you can see and why is it sytoic because he basically gives the analogy。

 memories the heart。😊，Data is the blood and processinging elements are the cells。

 memory pulses the data through the processinging elements and eventually data or blood returns to the heart。

 right so it keeps circulating this blood。😊，Okay， that analogy at some point bakes down。

 but it's good analogy。That's why it's called system。

So basically data flows from the computer memory in a rhythmithic fashion。

 hasing through many processinging elements before it returns to memory。😡。

And I already said the similar to blood flow， different cells or processinging elements process the blood。

 many veins operate simultaneously simultaneously similar to a body right and this can be manydisal just like veins can be manydimensal so there is no reason this could be linear this could be two dimensional as we will see in fact for matrix multiplication you want two dimensional arrays。

😡，But you could actually change these at arrays as we will see also。

 so it's actually a fascinating paradigm。😡，So why did he do this basically。

 he was trying to design special purpose accelerators？With the requirements that I said earlier。

 simple design， high concurrency， balancing IO computation matters。

So Ive already said a lot of this over here and this is the picture， so you may say okay。

 this looks like pipelining in a sense， yes， you're pipelining these processinging elements。

 that's actually true。😡，Another way of thinking of this is pipeline parallelism you're exploiting some pipeline parallelism。

 but it's not the same as a pipeline that we've seen in earlier lectures very different right here the processing elements are doing the same computation for example。

 you're not pipelineing instruction execution essentially these are individual processing elements they could actually be individual course if you generalize the paradigm I mean generalize the paradigm we'll talk about that and array structure can also be non- nonlinear and multidimensional it doesn't have be linear like this you could have actually a true dimensionmensional array。

😡，Prossing element connectionss can be multidirectional different speed。

 so now it doesn't look like pipeing anymore clearly and processinging elements can have local memory execute kernels。

 so each processinging element can be executing multiple instructions for example we're going to start very simple we're not going to do that yet。

😊，But essentially the difference， a huge difference from pipeing is the pipeing as we developed。

 I don't know how many lectures ago，5，6，7，8， hopefully it's ingrained in your thinking right now。

 all is this pipeing， you basically take an instruction in pipelineing and divide it into stages right different stages。

 execute different pieces of the same instruction here you're doing the same operation。😊。

On different data elements and you're chain the processinging elements such that the operation that you're doing on the data is based on transformed piece of data and you're not directly connected to memory。

Okay so hopefully that's clear now let's talk about some systolic computations and I'm going to also diverge and talk about neural networks a bit。

 It's not going to be a neural network course if we talk about neural networks in this course is not going to be ending but I'm going to motivate it also so convolution it's a very fundamental operation it was there long before deep neural networks it was especially used in filtering pattern matching correlation polynomial evaluation for especially image and vision processing task using robotics for example right and if you're designing a robot you need image processing and vision processing and you want that to be very quick and very fast and convolution was a fundamental operation machine learning more recently came about and well at least a modern form of machine learning neural networks more recently came about and we're going to have a story about that also and you get up to hundreds of convolutional layers that do a lot of convolutions essentially these operations are very common in neural networks what is a convolution operation essentially it's a filtering operation you have an input sequence。

😊，X， a vector of x， and you have some weights， vector of double W。

 and you compute this essentially polynomial evaluation。Y I you compute a x of y y 0。

 y1 y2 based on this notation y1 y2 y3， y4， etc ceter， and each y is computed this way again。

 you don't need to memorize exactly how it is， but this is based on mathematical principles etc ce but this is the computation that we're going to try to accelerate in the end you can excite other computations also but this is a good example。

😡，And if you look at a convolutional neural network， this is a picture of Lette。

 not so deep neural network， but it's one of the deeper neural networks when people started developing deep neural networks it's five stages as you can see and basically whenever you do some image processing to recognize part of the image you apply some filtering operation to it so there's some convolution that you do and then you basically do a lot of convolutions to try to figure out what this is and then you do some sampling。

 more convolutions more sampling and then some computation and eventually you say。

 oh I think there's an A so this is basically how neural networks work at a very high level we're not going to go into the details of it。

😊，But this is essentially a convolution operation on an input versus output so if you look at this input this is one input for example。

 to a convolutional layer， it's a two dimensional input as you can see and basically this gray box over here is the filter。

😊，You apply this filter to all of the parts of this input feature map so that you can produce an output feature maps this is what this is doing is the convolution and this convolution kernel can be different based on its values depending on the weights that you use for example。

 and in neural networks you learn these weights so you try to figure out what are the best weights to actually use so that I can actually identify this image using multiple different layers。

😡，Okay， so basically what this is doing is right for example。

 as it moves through the input that's called an image because this was developed for images initially it basically does some computation of the three by three kernel to the three by three portion of the input right and then it generates every single element of the input as you can see hopefully that's clear right this is basically that polynomial that I showed you put into a picture okay without showing the calculations exactly。

😊，Okay， and this is a maybe nicer one and you can actually essentially you're doing multiplication of these kernels with the input layer so that you get an output layer and you can see that there's a matrix multiplication going on over here。

😊，Okay， so if you're interested in this there's a lot of information clearly on neural networks。

 Young Liquin one of the pioneers in this field has his webpage that talks about how these work。

 I'm not going to talk about how these work at this point。

 but essentially this' is a very fundamental operation that is you used in many layers and you could implement this in different ways。

 essentially you could implement this convolution layer using matrix multiplication。😊。

And that's what we're going to try to accelerate a little bit。So if you look at this picture， oh。😊。

These are the input features input matrices， these are the convolution filters with weights x W and then we want to compute the output features。

 so what you do is you take pieces of the input feature like this is two by two elements and then you multiply it。

😊，With this filter and then you take this other one multiplied with this filter。

 and you take this other one multiplied with this filter。

 and then that forms an element of the output。 Again。

 this is the definition of the computation pictorialized。 And if you do the calculation。

 you will see that once you multiply this matrix with this matrix， the result is 2 to to 7。

I hope I got that right and once you multiply this matrix with this matrix you get the result you take dot product basically sorry I should say dot product you take the dot product of this with this you get7 because you multiply this one with this one this two with this one and this one with this two and this one with this two right and you do the same thing over here and you get an additional three and you do the same thing over here you get an additional two over here so you should get 12 and this is 12 and you can verify the rest it just simple computation right。

😊，So this is one way of doing it and we're going to implement something similar to this。

 but you could also lay out this filter in a horizontal vectorized fashion so this filter right now is collapsed into a vector 1122 as you can see and then 1111 and then 0110 and then you also put the other filter over here now this looks like a matrix it's really row of different vectors weights and then you multiply it with the input features that are unrolled essentially you can see that this belongs to this。

😊，No， actually， this is that's not correct。Essential， you take some of these over here。

 four of them over here， unroll them and。This collectively is this this collectively is here and this collectively is here and then you basically now have two matrices and you multiply these two matrices together and multiplying two matrices together is really you multiply this row with this row so that you get a dot product of those and you basically do it for all rows and columns。

😊，So you can see the same thing done in different ways。

 so this is where GPUs will be very useful because this is really you do the same operations on multiple different data elements with huge vectors。

 we will see that with vector pressing tomorrow， not tomorrow again rename tomorrow to next week。

 next next week and we're going to see how this computation is done using systolic arrays today but the realization is that you could do these very efficiently and at high performance with GPUs。

😊，And just to give you a history of why this is really important today and why actually courses matter in universities。

 some people， some smart students who took a parallel processing course program GPUs at University of Toronto。

 and these folks basically said， oh， we can accelerate neural networks using these GPUs。

 and they started training a deep neural network with 1。

2 million images and they participate in this imagenet competition。😊。

And they want the imagenet competition and they wrote this paper。😊。

Which is probably known how many people know this paper？a lot of you may know this paper。

 if you know this paper that means something， essentially this is the first paper that showed that with a deep neural network。

 you can classify images or identify images much better than what was previously done before with shallow networks。

 or what shallow networks。😡，But the reason they were able to do this was actually they learned how to use GPUs and how to actually translate a neural network to a GPU and optimize it。

😡，Okay so that's a nice story， I think I like it because it shows the power of smart people applying what they've done to a totally different domain that's being taught than what's being taught and then later Google developed its own let's say Google network model this was called AlexNe because the first author is Alex and you may realize some people Jeff Hinton for examples's you realize that also yeah see it's famous for for multiple reasons let's say okay but Google later developed their own deeper neural networks and later other people developed deeper neural networks from Microsoft for example but just to show you before this Alexnet paper came about the competition had a lot of error rate though these are images basically that are fed to you know these images you basically tried to identify these images automatically using some mechanisms using some software before with shallow neural networks the best approach had 25。

😊，An error rate。And these folks essentially revolutionized the thinking by having deeper neural networks。

 and there was a huge reduction， like almost10 point reduction in the error rate。😊。

You may say1 point does not matter， but this is what started all over this neural network。

 let's say revolution。Sometimes hype also， but there's clearly a benefit over here， right， And later。

 so a10 point matters。😊，Don't underestimate 10 points， right， and it's su 10 points。 actually。

 if you do the calculation。 Okay， so and then later， people。

 this is similar to branch prediction right， little advances that actually matter a lot as you can see。

 And later， people developed were at many layers。 and you can see that this is 2014。

 this was the first convolution neural network。 The previous ones were not doing convolutions。 Okay。

 you can read about them also。 but for example， this one is a 12252 layers。 This is 2015。

 And this was the first one that actually outperformed human level recognition of image。

 You could argue that okay， these images are limited data。

 and there are other more difficult images humans can do better， but this is limited by the data。😊。

So that's why convolutions are important because they fund their applications， for example。

 in the modern world in 2012， let's say。And if you look at a neural network today。

 the blue parts are the commvolution layers， for example， that's AlexNe。

 Lineette is actually simpler， it has two convolution layers。

 but as you add more convolution layers you can actually get more accurate and that's what people have shown and here you can see for example 152 layers。

😊，A lot more computation， of course， right and a lot more training， right？😡，O。

And we're not talking about Ls yet， but that's the subject of a different thing。 Okay。

 now let's go back to this convolution and how it's done using systolic arrays I've already talk about everything now we're going to actually execute this。

😊，Polynomial of the evaluation using a systolic areas。Again， we're going to the 1970s。

HD Kongung's paper， one of the papers did this， and this a sytoic area over here。

 basically what we're computing is assume that you have three xs， the directors are of length three。

Y1， y 2 and y3 are computed this way， weight1 times x1， weight2 times x2。

 weight3 times x3 added together。And then y2 is computed this way and y 3 is computed this。

So HQ said this can be done with this chaining of pressing elements and carefully orchestrating data such that。

😊，Where inputs come at the right point so that you can actually do this computation and then outputs go out at the right point so that you can actually capture the result that I need so let's take a look at that we're going to start with a very simple processinging element that looks like this。

Weights are hard coded， let's say put inside there initially you could also program them。

 but what this processing element does is it has two inputs to outputs as you can see x input is coming from the left。

And the next output is going to the right， and X out is equal to x n。Essential。

 the processinging element's job is at the beginning of cycle takes X out at the end of the cycle gives it to the next output。

 right You're passing the data。 essentially， input data， input data is X。😊。

And the outputs are going this way， so essentially y output gets input at the beginning of the cycle and then y output gets output at the end of the cycle such that the next element gets in the next cycle。

 and essentially y output is equal to y in plus weight times x in， so it's a multiplying accumulate。

 you multiply the weight with the x in。😊，And add to it， Y in。

The output coming from the previous element previous to you and then output the data to the left So it's doing a multiply and accumulate right it's multiplying the y input with a weight and then accumulating it and then giving it to the next element okay now we're chain let's chain these elements So we have three of these elements here one of them starts weight1 the other stores weight2。

 the other stores weight3 and we're going to orchestra state the data flow input data flow like this such that you basically pump in x' at some point x1 reaches here and then there is some empty slot over here x2 reaches here and then basically you separate the x such that in x is supplied every other cycle okay。

And then the outputs come this way。 Y1 comes here。 So basically， when x1 reaches here。

 y1 also reaches here， and that processinging element gets triggered。

 and what it does is it computes。As we said here you basically don't pass it anywhere because they they get dropped so you don't use this output because there is nothing else after this point。

 but y1 is computed by multiplying x1 with W1 over here and then next cycle y1 goes here。呃。

And it's X1W1， right？And the next cycle， you have x1 w1 over here， and then x2 moves here。😡。

And again， y1 becomes x1w1， which was coming before plus x2 W2。

Right and the next cycle one moves here and the next three moves here。

 so now again you hopefully got it， but basically the multipier operations is y3 x3。😊，You add to it。

 whatever you computed as y1 before， which is Wx1 x1 and WX2。

 so eventually y1 goes up here computing this thing。😡，Okay。

 so and you can also think about what others are computed over here。 for example， when x1， yeah。😊。

So Y2 comes later over here and you actually do similar computations on Y2 as well， okay。😡。

That's not shown over here， but you can imagine y2 being pumped over here we're going to show see another example that does matrix smallplication hopefully this is clear right this is beautiful inputs are coming in one direction while the inputs are coming crossing elements are doing the operation and outputs are going in the other direction。

😊，There is no instruction here we got rid of all the instructions， forget about all of the MIPS x86。

 there's no none of them。😡，This is a very specialized processor for doing convolutions。

Is this beautiful？Yeah， so you can see now the instructions are gone， all of the overhead is gone。

You can focus all of your effort to do incomevols。And that's the power of specialized hardware。

 as you can see， right， you don't waste any of your power or computational power or energy on doing anything else。

 but what you really want to do。😡，Assuming this is what you really want to do。 Now。

 feed to it something else。Like I don't know， a database access， good luck。

 it's not going to execute that for you。😊，Right okay so hopefully this is clear now this is again from the paper and later in some other figure in the paper。

 HTum shows that you could actually get a higher throughput by implementing the multiply and add separately as opposed to doing a  fued multiply and add operation I will not talk about this in detail but this is based on pipelining principles that we have seen you could actually get higher throughput a little bit extra cost because you need to actually la some of the intermediate results when you do multiply for example you less the results and then you do that。

 but this is actually amplifies the computational power of the systolic array without some additional hardware cost。

😊，That's the idea over here， but I will not go into this。The paper is beautiful so you can read more。

Okay， so basically， hopefully it's clear that。😡，To be able for this to work。😡。

You need to figure out what your computation block is。

 and you also need to carefully orchestrate the data when data elements are input to the array。

 both inputs and outputs。😡，And when the output is buffered when you actually capture the output at the end。

 so this is important so this gets more involved when things become more complex when every dimensionality increases for example。

 as we will see， but for matrix multiplication is going to be okay when processing elements become less predictable in terms of latency for example if they're not doing just multiply and accumulate but they're doing some memory access as we will see they're going to be very difficult but let's take look at matrix multiplication first so another example of systolic computation。

 this is exactly the reason that's use for example TPs。

 if you want to multiply two3 by three matrices。😡，The matrix multiplication is you take this row take a dot product of it and store it and be 0 to0 you take this row take a dot product with the second column that's01 this row with the third column that's0 to okay hopefully you know that we're going to use this crossing element essentially r is the result that we're going accumulate and this is again a multiply and accumulate you basically multiply m and N and add to it to R initially R will be0 and p will be passing m from left to right and Q will be passing n from top to bottom。

😊，And this is a sytolic array that does this computation， assuming these processinging elements。

So it's a 3D by 3 matrix at the end and the results will be stored in R of each element and this is how we supply the data elements inputs a zeros。

 B zeros， a1 b1 etc and this is the time at which each element goes into the array so let's take a look at time zero a0 zeros here B0 zeros here at that time you compute a00 times b00 store the result over here。

😊，Right。And then pass easy0 zero here and then easier zero zero goes down here。

So initially you give0 over here because you want this processinging element to compute something when a00 comes over here so you orchestrate the data such that the data that's coming for the next row arrives when what you need from the next column arrives over here so when a B00 arrives here a10 arrives here and you multiply a10 and B00 and that's what you exactly want right a10 B00 and then you basically keep accumulating results over here so hopefully it's clear I will not go through the entire thing this is something actually this was one of the homework questions for you to study I will let you figure it out but it's very easy to figure out as data moves in this processinging element does computation it adds to what it has accumulated before whatever it comes for example we had a00 b00 when a00 most here b00 moves here a10 most here a1。

0 almost here and you add to a 00， b00， which was stored here， a 01， b10， right？

And that's exactly what we want a 00， b00， a01， B10。

 and then next cycle a02 comes here and B20 comes here and you add to whatever was stored over here。

 a02 times b20， which is really a dot product of this vector with this vector。😊。

That's beautiful and you can convince yourself that。Everything works as expected。 And in the end。

 in these cells。You get C zeros that are calculated mathematically with matrix matrix multiplication。

Okay okay so that's beautiful。 you could do more。 you could have actually a multidimensional systolic arrays。

 which is interesting。 I'll let you read the paper if you're interested。

 you can combine sytoic arrays together， I will go through this relatively quickly also but essentially you can pour more powerful systems for example。

 this is an example from the book not from the book from Hs beautiful paper you have a historicaltolic array over here again orchestrate inputs it's capable of producing least square fit to all the data that it's seen。

 you can think of it as sensor for example， sensor is getting a lot of data from something from some camera is's trying to basically figure out what it is and if least squares fit as what you want to do to that data。

 maybe you can actually approximate that function that you're seeing whatever the data elements are you could do for example。

 anomaly detection using these very specialized circuits as opposed to using CPUus or GPUus that are heavy handed assuming you can design these circuits and you can design them you can see that sometimes you may need to add some buffers etc so that you can communicate but these are beautiful essentially if you want specialized systems。

😊，That are very energy efficient。 You can do that by making the ssto array bigger， more powerful。

 et cetera。Okay， let's talk about advantages。 So a big advantage。 This is very principle。

 It efficiently makes use of limited memory bandwidth， enhance computation to I bandwidth available。

Specialized， so you could actually be very energy efficient and in very high performance at the same time because don't you get rid of a lot of the overheads。

 no instruction fetching overhead， no instruction decoding， no instruction， nothing like that。

 you actually reduce the memory overhead also control over is gone。

 you're spending most of your effort on data processing。😡，Okay， so essentially efficiency。

 simple design， high con performance， so you're doing more with less memory bandwidth。😊。

Downside is also specialized， clearly， this is not generally applicable because computation needs to fit the processing elements。

 functions and organization。😡，So you can generalize this though so you can actually have each pressing element to store multiple weights。

 weights can be selected on the fly you can actually do very adaptive implementations。

 let me give you an example quickly if you take this further each pressing element can have its data and instruction memory and data memory can be storing some results some constants and if you actually generalize the model each processinging element can be its own core right it could be a core that's a general purpose core now this becomes like a programming model of the course and this is called a pipeline parallel programming model I call state execution and I'll give you an example of this so basically for example it's a very general model you can take a loop you can divide into three stages let's say for some reason stage A may be doing something stage B doing something else state C can maybe be doing something else and they may be operating on similar data set stage A is always operating on this data state B is always operating on some other data St is operating always operating on some other data you partition the program。

And in a single processor you may execute them like this a0 b0 c0， the first iteration， A1， B1， c1。

 the next iteration A2， B2 c2， the next iteration， but with three processors that are chained together in a systoic manner。

 p0 p1 p2， p0 starts with a0 and then moves a1 well and then at the same time P1 does B0。😊。

And then it needs to be2 and at this point you can see at this time P0 is executing A2 P1 is executing B1 P2 is executing C is0 assuming dependencies allow it。

 of course right and this is one way of parallellyzing programs which is a very powerful way pipeline parallels now this is very this is a computation model now it's not just a hardware model it's really a computation model of program and this is systolic computation and this is also called pipeline parallel so at some point pipelinelining and systolic looks similar。

So I've already given you this， so let's take a look， you can actually have course。

Threats can execute stages on different course。 course can be specialized for the computations that execute on them。

 That's key。So this could be general purpose course， but it could be very。

 very specialized for ABC as well。 Let me give you an example with something that's actually done。

 So video pressing is one example。 you take pieces of a video do different stages on it and then output And if you have lots of videos coming in。

 which is the case in YouTube， for example， you're doing this on huge data sets。

 And if you divide it into course like this， you can be extremely efficient。

 and then you can design a hardware accelerator for video encoding and decoding which Google does also in a pipeline parallel man。

 this is where we will stop I guess next， next week， we're gonna pick it up probably from here。

 we'll talk about TUs and then we'll talk about GPUs。😊。

Hopefully you'll have some rest and a good time during the Easter break， have a good break。

 I'll see you soon。まり。Okay。

![](img/51312d66a368f99520e4f85509618edd_9.png)