# ETHZ《计算机架构基础｜ETH Fundamentals of Computer Architecture 2025》中英字幕 p02 L2_ Pipelined and Out-of-Order Microprocessor Design (Spring 2025).zh_en -BV1Xc19BnET7_p2-

![](img/4c9813a546b06b12bb62a7f9db8bfc5a_0.png)

哦。1二1。是。你次。Yeah。Yeah。实。喂，申。Is so good。sound is okay also。Okay， that's good。Okay。🎼，🎼All的。Okay。

 yeah that's okay， let's see if we use it Okay， let's get started。

So we're here for the second lecture of FoOCA fundamentalmentals of computer architectureect。

Is this room okay for people？I kind of like it actually， so if this is going to work out fine。

 maybe we should just keep this seems like some people are watching online or watching at their leisure。

Which is find by me as long as you learn things， everybody learns things。Okay。

 today we're going to cover a little bit more let's say background on pipelining。

 but probably we're going to go into topics that you have not seen before my goal is to give you a conceptual overview of okay this fell down。

😊，Conceptual order of pipelining， you know how to do that。It's a give with it。

An unnecessary component。不道。Yes。Its a removable instruction in pipelining terms， maybe， yeah。

 does this still work， are you sure？😊，Okay。You know，Maybe it reduces some noise or something。

 but we're not getting into the microphone design today。

Basically my goal is to give you a conceptual overview of a lot of concepts in pipelinelining and then build up to auto order design。

 but I will also go into a little bit of implementation。

 but I don't want to spend a lot of time on implementation because if we actually spend a lot of time on implementation then this lecture can go on for a few lectures okay so I'll throw at you some pictures of implementation you may have seen some pipeline designs before how many of you have implemented pipeline designs。

😊，Not yet， okay， well at least you'll see get familiar with it。

 but this is part of what we'll build on。😊，Okay， so this is okay。

 it's gone now that's good so this is one of the coming it came back I don't know。完去。

Yeah we should figure out how to get rid of that issue maybe okay sorry about that zoom likes you to see that thing I don't want you to see that thing but。

😊，Right now we're doing Zoom。Okay， so this was what we were doing。

 this is a multi cyclee processor that we built。😊，Bilt。

 talk about conceptually and the problem with it was throughput and utilization of hardware resources。

 it was completing instructionary four cycles。😊，And with pipelining we could complete four cycles for one instruction every cycle basically we could improve throughput with this beautiful picture you're gonna to see more of these pictures later but then we started talking about ideal pipelineing unfortunately instruction pipeline is not an ideal pipeline and we're going to talk a lot about why it's not ideal today more than last time first of all。

 different pipeline stages were not the same latency so you need to force each stage to be controlled by the same clock and you would have internal fragmentation in each clock cycle because some stages take shorter some stages take longer so you don't have perfect let's say division of instruction execution into pipeline stages we saw this plus time right okay we also talk about external fragmentation last time essentially different instructions do different things they go through however we force them to go through the same pipeline stages and for some instruction some pipeline stages may not make sense。

😊，For example， an a instruction that doesn't access memory。😊。

Still goes through the memoryac stage right so you're kind of wasting some hardware resources and time doing that。

 but that makes things regular and easy to control。

And today we're going to talk a lot about this independent operations。

 in fact this is going to be one of our major focuses basically instructions are not independent of each other。

 beautiful an ideal pipeline requires things to be independent of each other remember we talk about laundry loads right that's an example but unfortunately instructions depend on each other some of them not all of them and the pipeline needs to figure this out somehow or somebody needs to figure this out it could be the software also if the software understands the underlying pipeline and you still need to ensure that you obey。

 detect and resolve inter instructionion dependencies so that you still get correct results at the end of the pipeline you probably seen this somewhere earlier。

😊，Okay， so these are some of the issues balancing work in pipeline stages。

 how many stages and what is the need stage we kind of talked about that last time this is actually an important area but we're not going to talk about that more we're going to talk a lot about everything else over here。

😊，We need to keep the pipeline correct， moving and full in the presence of events that disrupt pipeline flow and there are actually a bunch of events data dependencies and control dependencies today we're going to talk about data dependencies next week。

😊，After finishing out ofward execution we'll probably start control dependenceencies we probably see branch prediction at some point okay we're going to go into a lot more yeah we discussed that last time today I'm not going to talk about that that much handling resource contention very briefly I'll cover that today handling long latency multicycle operations that's going to be the subject that we will jump into when we talk about exceptions and interrupts and long latency operations are really what limit your performance in the end today for example a load operation takes hundreds of cycles right you need to wait for memory and that' stall the pipeline how do we handle that we're going to talk more about that later on but auto of order execution is one way of tolerating the latency of these multicycle long latency operations。

We're going to talk about handling exceptional conditions and interrupts that are coming outside。

 interrupting the processor， and essentially we're going to talk a lot about improving pipeline throughput by minimizing stalls。

😊，Sounds good。😊，Okay。So what is the cause of pipeline stall， so what is a stall， first of all。

 stall is a condition when the pipeline stops moving？😡，Ideally， pipeline is always moving。

 you're feeding instructions and you're getting instruction results finishing at the end。😡。

That's the ideal pipeline， but at some point you need to stall due to what we just discussed。😡。

And the question is， why does it happen？One reason is resource contention。

 the other reason is dependencies and the other reason is long latency operations。

 so let's take a look at dependencies， it's also called actually all of them can be thought of as dependencies some folks call this resource contention resource dependence as well because you're dependent on a resource。

😊，So these are also called dependencies sometimes they're called hazards。

 I don't like the term hazard because sounds alarming these are things that are natural right when you program one instruction feeds another instruction there's a dependence between them and it has to happen that way right if you don't handle them well they may become hazardous basically you may get the incorrect value。

😊，So dependences dictate ordering requirements between instructions that's the reason they exist and there are two fundamental types one is data dependence an instruction may be receiving a value from another instruction is' producing or another maybe a control dependence an instruction may be executed or not executed depending on the control flow decided by a branch instruction for example。

 we'll see both but today we're going to focus more on data dependence。😊。

Resource contention is sometimes called resource dependence， as I just said。

But this is not really fundamental to program semantics。

 other dependencies are dictated by program semantics。

 but resources are really dictated by hardware resources that you have or don't have or you don't have enough。

 so we will treat it separately。😊，But let me treat it very quickly and then we're going to move on to other stuff So resource dependence or resource contention happens when two instruction in the pipeline stages need the same resource。

😊，We've kind of seen that actually in a single cycle also right if you have a single cycle processor an instruction needs the same resource multiple times。

 you replicate the resource right you can do the same thing here。😊。

So how do you handle this one eliminate the cause of contention， for example。

 you may need to duplicate the resource or increase the throughput。

For example you may need to use separate instruction and data memories。

 caches right because at some pipeline stage you're fetching an instruction it requires access to memory。

 at some other pipeline stage a load instructions is executing， it requires access to memory。

 but these are two different types of accesses fetching and instruction every instruction goes through fetch。

 not all instructions go through data memory access right。😊，But still。

 if both of them need to happen concurrently， you need either separate instruction on data memories or you need to have separate ports so that you can have these concurrent accesses。

😡，Well， if you don't have enough， if you don't want to do this duplication。😡。

The second solution is to detect the resource contention as tall one of the contending stages。

For example， if you don't have。Enough ports to memory。

 you have only one read or write port while a load instruction is reading in the memory stage of the pipeline。

 you cannot fetch another instruction。😡，That sounds bad。

Because now you actually destroyed your throughput of the pipeline。

 you need to stall the pipeline whenever a load instruction is reading from memory。

 does that make sense？😡，So it's possible to have the second solution。For example。

 I basically gave you an example with single read and write port to memory but you can imagine it for the register file also the question is which stage do you stall。

 I think I kind of also gave you the example if you actually if load instruction is trying to read from memory and you have only one port from memory it doesn't make sense to stall the load instruction right because it's older in the pipeline it makes sense to stall the fetch stage so fetch stage should not read otherwise where do you move let's say you prioritize the fetch stage then you read the instruction but you have nowhere to put it because this load instruction couldn't move。

😊，Makes sense， so you need to stall the later stage in general。I'm going through these real quickly。

 but feel free to stop me and ask questions。These are relatively basic okay now let's talk about data dependencies we kind of handle the resource so there are three major data dependence types that is going to be important for auto border execution also one is flow dependence this is really true data dependence read after write dependence really a later instruction is requiring the result of a prior instruction。

😊，We still have a sequential execution model， that's why I say later prior， right？

There are two false dependencies， one is anti dependence， the other is output dependence。

 I'm going to demonstrate these piially right after read right after write。😊。

These are false because they're not I mean they're real。

 but they're not dictated by the program semantics。

 program semantics happens with producer consumer relationships。

 these happen because you don't have enough registers in your instructions at architecture。😡。

Which means that if you're clever， you could eliminate these dependencies。😡。

And that's really the crux of automotiveor execution， as we will see。

 we will eliminate these dependencies in hardware。So that they will not stall the pipeline unnecessarily and we will stall only for flow dependencies。

😡，Does that make sense？Okay， it will make sense hopefully when we get to the concepts。

So basically which one causes stalls in a pipeline machine。

 actually for all of them you need to ensure semantics of the program is correct。

 no question about that。😊，Flow dependenceencies need to be obeyed because they constitute two dependence on a value。

 it's really value communication one instruction write to register two。

 the next instruction reads from register to。😡，You cannot violate that dependence。

Whereas anti and output dependence exist due to a limited number of architectural registers。

 as we will see， there really depends on a name， not a value。😡。

Meaning if you rename the register to something else， let's say an instruction is writing to R2。

 a later instruction is also writing to R2， this is right after right dependence。

 which is output dependence。😡，You could actually change the register that the later instructions is writing to R 5000 if you had it trait。

😡，Because these arts have nothing to do with each other。😡，Makes sense， right？

From a semantic perspective， yes。Well unless there may be there may be some instruction reading from art to in between that's right so I'll show you a picture but we will see what we can do about them so this is pictorially what I said actually here you have a flow dependence this instructions reading from this other instruction maybe I should use this for online people。

😊，So the later instructions reading from R3， this is a true dependence。😊。

You could if you change this to R1， you should change this to R1 else。😡。

If you change the star 1 million， you should change the star 1 million also。😡。

Whereas antidepend here， the previous instruction is reading from R1。

 the later instruction is writing into R1。😊，Now， what you should not do in a pipeline machine is。😡。

Rightrite to R1 before the previous instruction read from tomorrow right that's what you should not do so you should really still obey the ordering。

 but。If you change the second R1 to R1 million， you don't need to do anything to this one。😡。

Because there there' is no significance of this other than the name okay output dependence is very similar so going back to your question over here this is the example you have r3 and r3 there's one thing that I have so that you cannot remove this one in this particular case again if you change one of them to r1 million you should change this one to1 million if you change this one but this one remains r3 makes sense right？

😊，So basically， you can get rid of this output dependence。By reading， again。

 when you actually execute this in a pipeline machine。

 you should make sure that r three gets the correct value sequentially。😊，Because of one9 principles。

 we're not going to break the one9 model。Okay， we'll get to these。

 but hopefully these are clear and hopefully you've seen this before。😊，Okay。

Okay now we're going talk about datadepend handling。

 these are some readings that I would recommend this is actually a very nice paper a bunch of years ago almost 30 years ago right now that talks about the basic micro of processor。

 it talks about data depends etcter， so I'd recommend this one。

 but if you want to also read in more detail some things Harris and Harris 7。5 to 7。

9 talks about these things。😊，Okay， so basically， I think， as I said earlier。

 anti and output depends are easier to handle if you're right to the destination register only in the last stage of the pipeline and in program order。

😡，You should not violate out of order， basically you should not violate right after right and right after readdependencies。

😡，You can think about that， but let's kind of summarize what I just said earlier。

Flow dependences are more interesting and challenging。😡，And we're going to talk about that。

In the end， there are six fundamental ways of handling flow dependencies。

 I'm going to give you a very quickly overview and then we're going to go into some more。😊。

One is detecting the dependence anding the pipeline。

 wait until the value is available in the register file makes sense， right。

 that's the lowest performance solution。😡，You can do something better， detect the dependence。

 but don't to the pipeline until you really need the value。😡，For example。

 you detect the dependence and you figure out that you could actually send the result of the instruction to the previous instruction。

 via a bus， we wire。😊，And that's called bypassing， we're going to talk about that also。

Are these familiar with everyone， Okay， good， we're going to go through that real too quickly。😊。

You can also detect the dependence and eliminate it at the software level。

 is this familiar to people？😊，Basically， instead of designing hardware to detect dependence。

 you design a compiler software that understands how it should schedule instructions to the pipeline。

 and if there's a dependence， it basically reschedules the instructions such that that dependence doesn't cause a problem in the pipeline。

😡，This is beautiful because there is no need for the hardware to detect dependence and we're going to talk about that all。

😊，You could detect the dependence and move it out of the way such that independent instructions can go away it's going to be out of order execution we're going to see that hopefully toward the end of this lecture at least conceptually。

😡，You could predict the needed value， you detect the dependence。

 or maybe you' have not detect dependence， but you predict that you need a value。😡。

And you don't have the value yet because somebody's going to produce it。😡，And。Say okay。

 my value r3 is going to be zero， you execute and then at the end when the value is available you check whether you predict it correct this is called value prediction。

 it complicates the pipeline more， we're not going to talk about as much but it's a way of doing things。

😡，And finally， one of my favorites is do something else。😀Basically。😊，Don't detect。

 but don't deal with dependencies basically maybe that's another way of putting it don't deal with dependencies its you can think of it as bru force basically every cycle fetch from a different thread that's guaranteed to be independent。

😡，And fill the pipeline with instructions from different trendss。

 Sa that you don't need to detect anything in the pipeline control dependence data dependence。

 it's called fine grain multi3ing， existing GPUs employeess for example。

 because they rely on a lot of threads yes。😊，Wouldn't wouldn't that matter also。

Include a lot of overheads or san， for example， in cash。Potentially yes， yes。

 exactly yeah these are actually very that's a very good point because now you have more threads accessing the cache and the data sets may clash in the cache。

 etc cetera。😊，Yes。We may have electronmifying grain multi threading。

 actually you will when we talk about GPUs because GPUs employ this model。

 but this is actually a nice model， I think。😊，Of course the downside， as you know。

 is one of the downsides you mentioned， the other downside is this terrible for single thread performance。

Basically， you designed the pipeline for multi threaded performance in this particular case。

 not a single third performance as we have kind of motivated everything with so far。

But it's still a perfectly valid way of handling things， okay。

 as long as you can tolerate that single T performance loss。😊。

Okay so these were the data dependence types now I'll go into a little bit more detail but I may go fast please stop me if something is unclear this annoying zoom is there but hopefully you can your brain can complete that dependence over there so this is an example of pipeline well diagram you have a bunch of instructions over here H through L and each of them nicely flow through five stages in this case it's a five stage pipeline fetch decocode execute memory and write back to register file。

😊，Assume that you have this instruction instruction J。

 I should probably use this one for online people again， instruction J。

 that's dependent on instruction I。If you look at this。

 instruction I produces its result in the right backstage。

 actually writes back into the register file in instruction J。😡，Gets into the。

Read from the register file stage in this T3。So clearly， if J is depend on I， you cannot。😡。

Continue with instruction J right so what we do is we add a bubble this is essentially stalling if you think about it I'm demonstrating stalling pictorially over here。

😡，In this case， you need to add two bubbles。😡，Remeaning that distance between I and J should be three。

And you can figure this out easily by pipeline structure， instruction type。

 etc in this case I assume there's no data forwarding data this right back happens actually theres some internal data forwarding in the register file but I'll talk about that later on based on your data forwarding assumptions and pipeline structure you can basically figure out how many bubbles you need to add and you can decide this in hardware or software。

😊，Okay。Oh actually this assumes that here in this particular case you if you forward the data this is correct。

 but if you cannot forward the data over there you'll need to wait actually three cycles this is actually the correct one right based on if there is no data forwarding assumption you need to actually have three cycles stall for instruction J and we want to eliminate the performance disadvantage on this straight I'm kind of getting ahead of myself also as you can see this is very basic so what is stall is to make the dependent instruction wait until it source data value is available。

😊，What do you do， you need to stop all upstream stages， meaningstream。

 you need to stop fetch essentially， and you need to drain all downstream stages so that the pipeline is clear and then you can make the pipeline。

😡，Don会等我讲 lunch。It's different from flush well stall is basically you stop fetching into the pipeline and the rest is draining you can think of it as flush yes。

 but you're not flushing any existing instruction in the pipeline。😊，So happens。

 flashes is a specific meaning where let's say you mispredted something and you basically get rid of all of the instructions。

 exactly yes yeah。Yes，You can think of it that way exactly， yes。

 basically you can think of these bubbles as no ops。😊，Introduced by hardware or software。😡。

mean in fact， in the software， we're going to introduce real knobs， as you will see。😊，Okay。

 so I'll introduce some terminology， it's called interlocking。

 but interlaing is essentially the detection of dependence between instructions in a pipeline processor to guarantee correct execution。

😊，This could be done in software or hardware， again。

 no ops can be introduced in software and hardware。😡，In fact， MIPS。

 how many people know about the MIPS architecture？😊。

Getting older and older now if you took DDC you would know very well its the architecture was designed with some philosophy in mind the philosophy is actually make the hardware do as little as possible software does as much as possible so the idea of MIPS means micropressor without interlaing pipeline stages meaning you don't have hardware based interlocking software as all the schedule as we will see。

😊，It's just an aside over here。So how do you approach data detection data depends detection hardware in hardware you can there are multiple methods I'm going to focus on just one method。

 you can have a combination of dependence check logic basically you add special logic that checks，😊。

If any instruction in later stages is supposed to write to any source register of an instruction that's being decoded。

😡，Makes sense this instruction is the decocode stage。

 you compare any of the source registers of this instruction to any of the destination registers of instruction in later stages Reg IDs are compared and you also check of course if this is reading from that register later instruction any of the later instructions as writing to that register so you can design this logic hopefully relatively easily in fact I used to have slides in DDC we have some slides that designs this logic but I'm not going to go into that much implementation。

😡，And if the answer is yes， meaning there is a dependence， you stall the instruction。😡。

And the pipeline in the previous stages， otherwise you don't need stall because there's no flow dependence makes sense。

 right？😡，So if you do this， the advantage is you don't need to stolen anti- and output dependencies because you keep going for anti- and output because everything anti and output are written at the end。

 but the disadvantage is if you want to design this dependence check logic。

 this becomes more and more complicated as your pipeline becomes deeper。Right。

And as your pipeline becomes wider， so they're actually pipelines can become deeper so that you can have higher clock frequencies。

 20 stages， let's say， and you need to check whether any instruction in the later。

 let's say 18 stages is writing to any of the source registers of this instruction。😊，And also wider。

 meaning if you're executing， for example， we didn't talk about this。

 but superscale execution means you can fetch Decode and execute n instructions per cycle where n is greater than one today and can be eight for example。

 if you're looking at whether you're dependent on any instructions now you need to actually look at whether this instructions that you are trying to access the register file with or decode is depend on any of the instructions that are fetched previously or concurrently with you but that are older。

😊，Okay。So dependence checking actually is not as simple。

 but renaming will not be simple also as we will。😊，So once you detect the depends hardware。

 what do you do afterwards？😡，So basically， the observation area is depends between two instructions detected before the communicated data value becomes available。

😊，One option is to store the instructions right away， as we have seen。😡。

The other option is to the dependent instruction only when it's really necessary。

 meaning forward the value to a place， push the instruction to until the value is really needed。😡。

Okay， we will see example of this called data forwarding or bypassing。

 and there could be other options like out of order execution， which we will go into later。😊。

So as you said， as you most of you know data forwarding， I'll go through it again quickly。

 the problem is if you stall immediately， a consumer or dependent instruction has to wait in the decode stage until the producer instruction writes its value in the register file right in the basic pipeline that we kind of see。

😊，But we don't want to stall the pipeline unnecessarily。

 we want to minimize stalls for higher performance， higher outputput， also better energy actually。

 because you're wasting energy if you're stalling。😡，呃。

The observation is that the data value needed by the consumer instruction can be supplied directly from a later stage in the pipeline instead of only from the register file right so design the pipeline such that you have these bypass paths or forwarding paths where the results of instructions can be forwarded between pipeline stages as opposed to everybody reading the results only from the register file makes sense for it。

😡，Okay， well， I kind of said this already already， basically add additional depends check logic and data forwarding paths or buses to supply the producer's value to the consumer right after the values of it。

😊，I'm going to show you examples of this， but again I will not go into a whole lot of implementation we're going to be more conceptual。

😊，If you want to really go on to go into implementation， you can do these in DDC okay。

 so the benefit is consumer instruction can move in the pipeline until the point the value can be supplied。

 so this is less stall like that。😊，Okay now let's go into a little bit implementation。

 don't worry if you don't understand everything， but you've probably seen some similar pipeline at some point。

😊，So how do you stall basically here we have I think five stages， this is the fetch stage。

 this is the decode stage， ALU execute memory right back if you want to store basically you want to disable the latching of the PC you don't want to change the PC and you don't want to change the instruction register so you need to disable latching to those registers。

😊，If you're stalling in this stage and you want to insert bubbles。

 no ops basically to be able to insert bubbles， you need to invalidate these registers。

 so if you're installing instruction over here you want to actually invalidate the instruction for that cycle。

 what do you insert will you insert a bubble essentially。😡，To be able to insert bubbles。

 you actually have a clear bit， for example， or inveild bit associated with the registers。

 we're going to see that also。😊，Okay now let's take a look at this example。

 I think I've already shown this， but in a different way earlier this is our pipeline these are some instructions。

 you can see that this instruction is producing S0 again I should use this the first instructions is producing SEO and all of the other instructions are reading from S。

😊，And clearly， if we let the pipeline move。For this instruction。

 this instruction is going to get the wrong value right because this distraction is going to produce its result on cycle five and you cannot read that the produce result in cycle3 okay。

Basically， if you move the pipeline， you get the wrong value here， if you move the pipeline。

 you get the wrong value over here， only sub reads the correct value because I have assumed some data forwarding over here。

 this instruction， the first instruction writes S here in the first half of the register cycle cycle five and this instruction reads it in the second half。

 that's kind of a trick that you may have seen in your previous pipelines I S okay good。😊。

It's a data forwarding path basically， even though it may not have been said， okay。

 subsequent instruction with the correct value of SG。

 so basically we want to make sure these instructions also don't tweet the wrong value so you need to insert bubbles。

😊，Basically wrong results happen only if the pipeline handles data depends in。

 so this is one way of inserting bubbles。😡，Compile time right the compiler knows the pipeline structure。

 knows the data forwarding pass in this case it's only the register file internal data forwarding in the same clock cycle。

😊，And compiler says， oh， I know what will happen if I actually schedule this end right after a。

 so I'm going to put two knobs over here。😡，That's the idea of compile time scheduling we're going to get back to this when we talk about VIW in VLIW very long instruction where compile will do almost everything this requires a compiler to know the pipeline structure data forwarding path so it needs to be tightly and integrated with a micro architect。

😡，Okay。It could also potentially， in this case， it doesn't work。

 but it could find an independent instruction over here and move it up here。

That's another possibility if you want to get rid of No ops。

 find something independent of all of these and move it up here such that you don't change the program semantics。

😡，So that would get rid of Noops and that would be much nicer than noops clear。😡，Okay。

So data forwarding， I already said this forward the result value to the dependent instruction as soon as the value is available。

😊，We may see data flow architectures actually at the end of our word execution I may talk about that。

 but basic idea really comes from data flow architectures and these are old architectures where data value is supply to a dependent instruction as soon as it's available。

😊，An instruction actually is fetched and executed when all of its op are available。

 we're not going to do the fetching， but here we're going to just supply the data so data forwarding brings a pipeline closer to these data flow execution principles keep this in mind we're going to build some data flow graph later。

😡，So this is an example of data forwarding location in the data pad in this particular data pad。

 for example you can forward data from this last output of the ALU to the input of the ALU such that the next instruction that's dependent can receive it that way you don't need to store this instruction as you can see right because this instruction actually produce its result again I forget the online people this instruction actually produce its result at the end of clock cycle three and you can immediately forward that result。

😊，To the next instruction who will really need it at the beginning of class cycle four。😊。

That's the data forwarding path you need to add。Similarly。

 this instruction can carry the result over here and forward it from this latch over here right back latch to the input of the ALU such that the next instruction can get it at the right time without requiring the result to be in the register file。

😡，And then also internal forwarding we already see so there are three forwarding paths over here as described here。

Makes sense， right？Okay。Now there's a little bit more detail again I don't want to go into a lot of it but basically need to add logic to enable data forwarding that's going to get much worse than out of order execution。

😊，But this is just data forwarding right now if you want to forward the result from last output of the ALU to the input of the AL in this forwarding path。

 of course you need to add maxes like that also。😊，From the right back to the input of the ALU。

 you need to add this forwarding path， again， marks to select which one is correct based on which value that particular instruction here is reading。

 right？And from the register file， of course， so these are three places where an instruction can get its source registers from。

Okay， hopefully that makes sense again don't worry about the details of implantation。

 but this shows you that the data value can come from different places in automotive execution we're going to take it to the next level。

😡，Yes。It should theoretically not be possible that。All right back paths are trigger at the same time。

 right in this case。I mean， it is possible， for example， this instruction is writing to register 5。

 this instruction is writing to register 5 and this instruction is reading from register 5。

 then it should get this value， right。😊，Youngest value， exactly exactly， yes。

 there needs to be that prioritization， exactly。In automotiveward execution。

 things can be concurrent also， as we will see later on。Okay。

 that's a good question There are no bad questions you can ask more Okay so I think I've already said all of this。

 but forward to I think actually this covers with the question you asked forward to execute stage from either the memory stage or the right back stage。

😊，When should we forward from either memory or right backstage if that stage rise to the destination register and the destination register matches a source register？

😡，I think this covers the case you mentioned if both the memory and right back stages contain matching destination registers。

 memory stages priority。Because it contains the most recently executed instructions now data forwarding is not always possible in which case you need to insert anOop or E to in this particular case。

 for example， this load instruction， the first load instruction。

 its result becomes available after it accesses the data memory because it's a load instruction it needs to generate the address in the ALU stage access the data memory。

 this is where you get the result。😡，And you cannot forward it。😡，2。To the next instruction。

 who's the ALU stage over here， right？Now cannot is very strong。You could。

 you could do what I just showed over here。But then that would lengthen your clock cycle right you would wait for a clock cycle to get the result and then forward the result and then you would wait for another clock cycle to execute this instruction。

😊，That would break our principle of。Critical path design， okay。So basically。

Due to pipeline design and instruction latencies， the law instruction doesn't finish reading data until the end of the memory stage。

 but in this case a and instruction needs it。😡，At the beginning of the clock cycle。😡。

Its result cannot be forward to the execute stage of the next instruction unless we want the own critical path。

 which we don't。😊，Okay， so in this case， for example， you need to stall the pipeline。

 you need to detect that there's no way you can forward the data。Unfortunately in MIPS。

 they added a delayed load instruction， meaning that there's a one cycle delay slot。😊，呃。

Low instruction after the load instruction， you always have anob。😊。

Which is interesting to keep in mind。なぜぐらいアイディ？Because what if that pipeline stage was longer and you need five delay slots。

 right？😡，Okay， that ties the Ia to the micro architect necessary， okay。

 so basically stalling is necessary for this me X dependence， there's a stall over here。😊，Okay。

 so this is essentially the stalling and dependence detection hardware。

 If you stall for that Mex dependence， you need to insert a bubble over here also essentially need to。

😊，It has this flash name， I don't like the flash name， but it does have it。

 so you clear this register。😡，And then you need to stall the fetch。

 essentially you insert a bubble over here。😡，As you can see。And of course。

 you need to make sure PC and the instruction register don't move because you're stalling。Okay。

 basically in general， stores are supported by adding enable inputs to the fetch and deco pipeline registers and clear or reset input to the execute pipeline register as we have seen。

😊，Or you can have inV bits， but these are very low level implementation details that I'm not going to go into。

😊，So I already said all of this by based in that picture， so I will not go through it。

 but you can look at it yourself。Okay， so this is what I will talk about control dependence and then I'm going to defer everything to later lectures。

 essentially control dependence is really data depends on the instruction point or program count。

 right？😊，Every instruction is dependent on the previous instruction。

Because every instruction increments the program country and a one known architecture， right？😊。

It's a very predictable dependence， of course， if it's sequential。😊。

But it may become unpredictable if you have a branch that is conditional or indirect。

Okay basically the key question is what should the fetch program counter be in the next site answer is the address of the next instruction of course。

 but this doesn't help us solve the problem all instructions are controlled depend on previous ones I already said this。

😡，Now if the fetch instruction is a noncontroll flow instruction。

 next fetch PC is the address of the next sequential instruction。

 this is easy to determine if you know the size of the fetch instruction。😡，Now。

 some ISAs have variable size instructions， which means that you don't know the next fetch PC unless you decode the instruction。

😡，Okay so that complicates， so the problem is basically you want to fetch the next instruction。

 but you don't know the address of the instruction， right？😡。

So if the instruction that fetches a control flow of instruction。

 how do we determine the next fetch PC we need that PC。😡，In the next cycle， right？

Because we're fetching the current instruction at PC。

 that instruction will move to the decocode stage， what will we fetch in the next cycle？😡。

That's the critical problem we need to solve in the pipeline。In fact。

 how do we even know whether or not the fetch instruction is a control flow instruction？😡。

Because we haven't decoded it yet。So that's the problem with control dependence。

 but I'm going to defer this to later， it's fascinating and there are a lot of interesting techniques that we will cover。

Any questions？Okay， now I'm going to switch gears a little bit and talk about something that's extremely important to preserve the von Neumman model。

😡，Meaning sequential execution， which is precise exceptions have you covered this in prior courses？😊。

Basically， the idea is you need to ensure that every instruction finishes in program order。

 the question is how do you do that？First of all， why do we want that， I guess well。

 one answer to why do we want that is because it's the one Neman model and the W Neman model system。

 right？😊，And that's actually correct， but there are other reasons why you want the one knownman model as so let's take a look at an example。

 not all instructor actually take the same amount of time in the execute stage or the pipeline if you want to design a high clock frequency machine thiss called multie execution。

😊，Basically， you can have multiple different functionals that take different number of cycles。😊。

This's an example because instructions are very heterogeneous。

 so a functional units also become heterogeneous and you can pipeline them or not pipeline them。

 but if you want to have high clock cycle this is a eyeC frequency can it's a good idea。😡。

So after you decode the instructions， some instructions go through this pipeline。

 some instructions go through this pipeline， some others go through these other ones。

 right with multiply load store at they all have different lines。😊，Okay。

Now you can let independent instruction start execution on a different function before a previous long latency instruction finishes execution。

😡，So for example， a previous instruction a multiply starts executing， it takes four cycles。

 and then an ad is independent of it， it can start executing and it would finish in one cycle。

This add you not to update the register file， right？😡。

Because that would violate the sequential semantics。Okay。

 that's the problem we're going to look at basically how do you update the register file at the end over here。

😡，This Zoom is really annoying。There's no solution to this problem， okay， hopefully。Okay。

 basically this is what I showed you instruction can take different number of cycles on the execute stage here we see integer a versus divide I just want to show these instructions and now you have a divide over here on top and then you have an ad assume that we actually write to the register file。

😊，Like this。You means ignore the problem。You basically say whenever ad finishes one cycle later。

 I'm going to update the register file。😊，And this is kind of the execution timeline now you can see that the register file is updated out of work this instruction updates the register file after a bunch of other instructions that come later。

😊，Now this while leads to one known architecture because sequential semantics of the ISA is not preferred preserved remember sequential semantics means that。

😊，It no no。An instruction should be executed and finished。

Before any other instructions started right？😡，Here we're violating the starting part in pipeing。

 but we're violating finishing parts also。😡，Finishing part is actually bad because the software may observe this okay。

 for example， what if divide incurs an exception over here so you execute the divide and you figure out at some point that this is divide by zero。

😊，And。This is bad， the program should not continue， but you update the register file。😡。

Now the programmer should go and debug this because maybe that divide by zero should not happen。

Programmer tries to inspect the register file contents and they have no idea what's going on。😡。

They cannot basically rely on the sequential execution semantics anymore because the hardware violated them。

 right？😡，One way of doing this is basically say， okay。

 I punt on this programmer you don't have sequential execution anymore， figure it out on your own。😡。

That's bad for debugging in general yes and in the past there were having been machines like that IM 3691 for example had imprecise exceptions。

 it was one of the first auto order execution machines we were going to talk about that actually Thomaslo's algorithm but they violated the sequential execution semantics because they didn't invent what we were going to talk about and programming。

😊，That was extremely hard and it didn't it wasn't successful in the end yes。

 isn't that also a nightmare for input output basically anything that's exactly exactly yes it's a nightmare for a lot of things basically input output are essentially interrupting exceptions。

 basically you don't have a precise state to work from yes。Okay， that's good。就 yeah。

This is my favorite example， maybe not the favorite。

 but one example of exception causing instruction， this was one day and I was going to teach a lecture in DDCA and I figured out this was actually a good example on real life。

😊，This cham for some reason stopped moving， it was the exception causing instruction and there's a later instruction in the pipeline that couldn't move because you know it's a delayed instruction into the exception so you need to handle this exception somehow and this got handled a long time later see I'm moving up over here as you can see from Bellevue and eventually I saw the exception causing instruction coming。

😊，Well， maybe this was the other instruction， so okay， maybe the analogy is not perfect。

 but you can see that theres a delight until which the exception is handled。😊，Okay。

 basically exceptions and interrupts， I'll go through this relatively quickly also because I want to distinguish between these two you mentioned IO IO is actually external。

 it could be internal to the program but it could also be external。

 but these are essentially unplanned changes or interruptions in program execution。😊。

If these changes are internal due to internal problems in the execution program like divide by zero。

 this is called an exception。😡，If these changes are due to external events that need to be handled by the processor。

 it's called an interrupt， you interrupt the processor。😡。

Both exceptions and interrupts require stopping of the current program。

 saving the architectural state， handling of the exception and interrupt， switch to a handler。😡。

supplied by the operating system for example， and if possible and make sense you return back to the program execution if it's a fatal exception then you may not return back to the program。

 but the programmer may have provided an exception handler that deals with divide by zero right and then you actually return back to the program。

😡，Okay， there are a bunch of examples of exceptions。

 some of the wide by zero overflow undefined up code。Page faults for example。

 if you have virtual memory interrupt examples， Io device may need a service may need service。

 system timer may expire so that the operating system may need to do some maintenance it kicks out the program right it reschedule something and there are more serious ones like power failure。

And machine check， machine check happens， for example。

 when you have an error in the machine in the memory。

 you detect an error and you may want to clean up the state and figure out what's going on。

Sa you again。8月份。Probably， yes， yeah。Yeah。So that kicks out the kernel potentially yes exactly。

 I mean it may actually kick in some firmware to analyze what's going on right that's certainly possible that could be your exception handler in that case。

😊，Again， this is fun topic。😊，I mean， one could argue that interruptops actually yeah。

 interruptops are interesting because interrupts are not really fundamental to the process right you could actually handle them somewhere else。

😊，The reason interrupts have happened is because we very single core minded and you need to kick out the process that's executing。

Some interrupts， you don't need to kick out the process。

 you can handle them on the site in some other context in some other core， for example。

 right in a multi core context ens actually become a little bit less。Important， in my opinion。

 because you don't need to kick out the process。🎼Okay。

 so there are difference between exception interrupts。

 I think I'll go through this relatively quickly I already said the cause when to handle exceptions are usually handle when detected because and also known to be non speculative let me finish this and then we'll take a break interrupts when convenient usually unless it's a very high priority interrupt of course like machine check。

😊，Power failure。Priority is really the handling priority of an exception is the priority of the process because it's internal to the process。

 the priority of an interrupt it really depends right it may be not so critical。

 it may be very critical depending on whether it's a power failure or not， for example。😊。

Okay I'll not talk about this so let me finish the slide and then we'll take a bit basically if you want to maintain sanity and all some other benefits。

 the architectural state should be consistent or precise when the exception or interrupt is ready to be handled。

😊，This means that all previous instructions should be completely retired。😡。

And no later instruction should be retired。So essentially one Nemon model a little bit stretched right because we're talking about retiring。

 retiring means youre updating the architectural state。

 all previous instructions should update the architectural state or no later instruction should update architectural state。

😊，And we can flush the micro architectural state， that's the good part。

Even though theres some other state other than the architectural state， we can flush it。😊，Okay。

 so a retirement is commit finish execution and update the architectural state。

 so for as an example over here， if I want if this divide gets an exception over here。

 the time to handle that exception is really when you have this precise state。😊，Essentially。

 all previous instructions are done。😡，And no later instruction is done。Makes sense。

It's a clean separation。Okay， let's take a break and I think today we can take a almost full 15 minute break one of the bell rings and then we'll continue with precise exceptions。

 figure out how to handle them and then hopefully jump in out of our execution。😊。

Let's see if you can handle。Apparently， Zoom has a very high priority interrupt that it wants to get serviced。

 yes。😊，Oh okay， that's from that would have been funny Oh you were thinking that's related sir No。

 I was wondering if it's tough screen Oh okay， that would be nice actually I think it's from the zoom though yeah。

 it doesn't look that advanced， you know。😊。

![](img/4c9813a546b06b12bb62a7f9db8bfc5a_2.png)

Yeah。😊，It would be nice， actually。 then everybody could see it probably online as well。

 Yeah yeahoo and I always forget it because nobody maybe some people can see it if I if the screen resolution good Yeah but I mean on zoom it's very small So have a question for like machine checks you said then sometimes the firmware kicks in。

 could that technically mean that if this firmware is compromised。

 you basically execute potentially called machine level exactly it's not a good yeah you need to make sure your firmware is not compromise exactly I mean and those things are less let's say rigorously checked in general from a security perspective。

 executing at the kernel level with firmware is already nasty but that would technically mean you could。

😊，Yeah， destroy the entire kernel potentially yeah， yeah yeah。

 that's why you need to have trusted firm areas， oh it's even it's even more beautiful when you think that the kernel nowadays encryptpts yeah everything。

😊。

![](img/4c9813a546b06b12bb62a7f9db8bfc5a_4.png)

just happened。Its a combination of the macros。中好。Msor and you should go and again。

that's a nastyustic thing it's not I don't think it's a notification per se it's actually you're just yelling at you that it doesn't like just sort thing it doesn't like sharing the screen。

And it becomes， it's more like a privacy thing， I think。

It station persistently pest through with the attacks are moving hard。

And try getting rid of it if it's actually wanted。that's okay， yeah。

Oh noadays still haven't fixed a tough day。Can you， yeah。

 you can hi checkck the camera with it oh god。Sorry， yeah。

 this is this is one of the worst features Apple has ever implemented as soon as you flick open a pair of airports somewhere in the vicinity。

😊，It blocks your screen with this nasty pop up and you cannot disable it。

 even if you disable Bluetooth if you go into how it's okay called airplane mode。

The pop still it appears， I think it gives NFC or something yeah its something must must something like this。

But it's very annoying， especially if it' like disableds camera or if you're writing something in a lesson。

They should really fix that one。Test， test。Ys嗯。Those。Y'all。明。it then how we do the same message。

normal comment。Okay actually copy。I mean， there was this issue， right， that also。

 I think it's better。The camera view is nicely see overlapping the is。I say that this was that。😊。

呃我在 the home shop工多。接的时。Therefore。Because it should slightly feature on the。おす？

Application or a context to a purpose。えそな。嗯。Yeah。嗯嗯。中から loveす newてまの。Orinal fiscal good。ょか。Yeah。

 always was possible go planning and sing to be little an。Yeah， as also its I probably。

Let's say whenmobil mobile it difficult。你啲什。Yeah for。告 just mess。那时头装。半对白。Yeah。Yeah， wasn the mom。

好觉得。Yeah。B is nice so。I forth。都是点。嗯。By。Oh。嗯。好。啊。Yes。No喂。Okay any questions。ThisThat will be at first。

Okay。时。Okay。Actuallyual。Is everything but the sound is also okay。I put it in a different way。

 but hopefully it's still okay。Oh good。オペ池のかテたペのかし。Good， how about now？🎼，Okay， is it good？Yeah。

 I can hear myself， but I don't know about you。Yeah。Online， can people online here， yes yes， okay。

 that's good。Okay， so get let's continue。Hopefully I motivated precise exceptions and interrupts。

 now we're going to cover how do we handle it。😊，But before we go into that。

 I'll give you a little bit more overview of what happens when you have exceptions。

 basically to be able to obey this precise state， have the clean separation of sequential instructions from each other when the oldest instruction that's ready to be retired is detected to have caused an exception。

 that's when you handle the exception。😊，The control logic ensures the architectural state is precise。

 we're going to talk about that， which requires register file PC and memory to be precise。

 meaning no later instruction should have updated it and all prior instructions should have updated it。

😊，It flushes all younger instruction in the pipeline in general。

 it saves the program counter and registers as specified by the ISA。😊，呃。

And we do access the fetch engine to the appropriate exception handling this is the general steps that you take of course IS is may different in terms of how they specify this and if you look at x8664 they have a specification among their thousands of pages where they talk about this yes。

😊，Just a experience what if。I know this is going a bit further but what if we branch predict somewhere and we run into an exception inside that branch maybe it's not even valid yeah you don't do that that's why it says when the oldest instruction that's ready to be retired is yeah so basically you need to make sure that the instruction is not speculative。

If it's speculative， don't you don't want to handle exceptions unless you want to optimize for performance potentially。

Which we may get into later on， right？Exactly， basically。

 you wait until you know that the exception is not speculative and when you know that it has to be handled from a program perspective。

 then you handle it。😊，That's a very good question， basically because we're going to see these issues in branch prediction。

 it always happens in pipeline also， right？😊，Maybe not in the very simple pipelines。

 but especially complicated pipelines Okay， so if you're interested X ISA is beautiful well beautiful for some definition of beautiful。

 but you'll learn a lot by reading IA manuals I should say that because there's a lot in there。😊。

Sometimes not very well specified， but they tell you a lot about how the system operates and how you can optimize performance。

 but it may not be easy to understand， but business basically kind of says what I said earlier okay so why do we want precise exceptions I think I'll go through this relatively quickly because we discussed parts of it semantics of the ISA specified you have to obeyit basically otherwise the programmer may go crazy。

😊，Dataflow actually， we didn't cover it， but dataflow doesn't have precise exceptions， for example。

 it ates software debugging as we discussed， it enables easy recovery from exceptions。

 it enables restartable processes。😊，It enables traps into software like software implemented opcodes etc again you can think about these but I will not go into a lot of detail over here now let's take a look at how we actually ensure precise exceptions this is easy to do in single cycle and multicycle machines we've seen single cycle which makes no sense as we've discussed last time but in single cycle instruction boundaries a cycle boundary and instructions guaranteed to be finished in one cycle there is no possibility of violating sequential execution semantics as we've discussed。

😊，Multicycle machines。😊，Basically you need to add special states in the control finite state machine that lead to exception or interruptop handlers。

 for example， if you detect an exception， you're executing again in a multicycle machine。

 you haven't started the next instruction yet， but when you detect an exception you add an arrow essentially an arrow from one state to another state where the other state is actually handling the exception you jump into the exception handler basically exception handler is part of the state there and you switch to the handler only at a precise state before fetching the next instruction for example。

😊，Okay， if you're interested， you can see Harris and Harris。

But pipeing with multicycle execution complicates things Auto order is going to complicate things even more。

 but let's talk a a look at pipeing without word execution now here instructions can take different number of cycles and this comp is exception handling and have you've seen this before basically if this instruction calls exception if you already update the architecture file register file or memory you have a problem。

😊，So one solution to this is a bad idea。Right similar to single cycle machines basically make each operation take the same amount of time。

 it kind of defeats the purpose of what we have done multicycle execution right so don't do that basically because it's says the same downside of single cycle worst case instruction latency determines all instructions latency。

😊，It's not as oh sorry， not multi， single cycle， it's not as bad a single cycle because your clock cycle is still much better。

 but now your IPC is not good， probably okay。😊，Okay。

 if the memory operation patient takes hundreds of cycles， that's not good。

Okay so people have developed a lot of ideas in this regard in this course we're going to cover only one of them。

 unfortunately we don't have time if you're interested this a beautiful paper that has had a lot of impact on the field that talks about some of the other implementation and there are some other papers that I evolution mention this paper doesn't talk about checkpointing for example。

😊，呃。But basically we're going to talk about reorder buffer before updating the ideas before updating the architectural state reorder instructions。

 that's why it's called a reorder buffer。😡，You can take a more optimistic view of this and update the architectural state。

 but start undoing it when you have an exception that's called the history buffer basically。

 but I'm not going to talk about some of these things。😊。

In modern machines you usually have a combination of reorder buffer。

 checkpointing and future register file， actually we're going to see a map later on history buffer is usually not used because I'm doing something is much harder than waiting and committing when you know that you should do it。

For multiple reasons like because when you're doing you may expose it to some other process that may be inspecting results。

 right？嗯。Okay， so the idea I already said this gave you the idea。

 but the idea of where orderder buffer is complete instructions out of order。

 but reorder them before making results visible to architectural state。

 whenever you're updating memory or registers， architectural registers。

 reorder the results so that you update them in program order。😊，One name orderlet。

So you can implement reorder buffer is circular to in hardware， that's how it's usually done。😡。

It looks kind of like this， this is a a poor man's picture of a pipeline。

 basically after you get the results， you collect them。😊，And if the result is written out of order。

 you write it over here and when the instruction becomes the oldest in the reorder buffer。

 then you update the register file， makes sense， right？😊。

So that's reorder so how do you do this when an instruction is decoded。

 you reserve the next sequential entry in this special buffer called reorder buffer。😊。

So that you actually put things in a sequential order in the reorder buffer， one name order。

 you preserve the instruction program order basically when an instruction completes。

 which could be any order， it could be out of order from the program order。

 it writes as a result into its entry in the reorder buffer。😊。

When the instruction becomes the oldest in the reorder buffer and it has completed without exceptions。

 its result is basically moved from the reorder buffer to the register file or memory。😡。

Makes sense right so basically you're updating register file and I in program order。

 but you're executing auto of order over here internally。😡。

This is not a complete Autoboard execution machine because we're starting instructions in program order。

 we're putting instructions into the functioning it's in program order。

 we're going to change that with Autoboard execution。😡，Okay， so I think conceptually we're done。😡。

I'll go through implementation relatively quickly because this has some headaches in implementation。

😊，So this is the but I'm not going to go into a whole lot of detail and implementation。

 as I said earlier， but if you implement a reorder buffer。

 you'll need to think about some of the headaches that I will mention。😊。

This is a hardware structure that keeps information about all instructions that are decod。

 but not yet retired or committed。😊，And you can think of it as a circular buffer， as I said。

 there' is a pointer to the oldest instruction， basically it's the raw entry reorder buffer a Rob that contains information about the oldest instruction in the machine。

 and there's a pointer to the youngest instruction。😊，Now， if these two pointers are the same。

 then your reorder buffer is empty， probably' flush your machine right they can think of it as a circular cube。

😊，Okay， what's in a reorable firm， basically you have a valve bit， you have a destination Reg ID。

 which destination register is this instruction going to write？😊，Destination register value。

Have you actually produced the value that you're going to write to the destination register？

And you can have things for mes。Okay。So actually， this is a bigger version of it。😊。

And you may actually have other control bits because you need to keep track of whether the destination register value is valid。

 meaning you actually produce the value you've written it into the reorder buffer if you haven't written it then that means that the instruction is still executing right somewhere。

We also store the program counter over here to handle exceptions actually。

 so we also have information about exception。😊，What kind of exception this instruction may have caused while it's executing in the pipeline。

 so it's actually a control structure that keeps track of what has happened to the instruction。😡。

While it's in the pipeline and it's decoupled from the pipeline， you could put it anywhere。

 but you just need to update it at appropriate times。😡，Hopefully that makes sense。Okay。

 so basically it has everything required to correct the reorder instructions back into the program order。

 which is what we have started with。😡，Everything required to update the architectural state with instructions results。

 if instruction can retire without any issues like exceptions or interrupts。

And it says everything required to handle an exception interrupt precisely if an exception interrupt needs to be handled before retiring the instruction。

Make sense right for example， you need to save the program culture that's why you have the program culture over here right to handle the exception because you were going to come back to this assuming the exception handler and circumstances dictate that you should come back。

😊，Sounds good okay。So you need  valve bits to keep track of the readiness of the results as I said and to find out if the instruction has complete execution of course you need some bits also to tell you whether the instruction is writing to a register file register file right so that information also needs to be there it kind of like the control bit that you normally use in a pipeline for example if the instruction is not going to update anything in the register or memory you still have aorderber refer you for it but when you actually retire that instruction you just check for exceptions and don't update anything right there are some instructions like that like no ops for example you still need to keep track of no ops in the reorder buffer or sequential execution purposes right。

😊，Branchches also some branches most branches are like that actually okay。

 so if you do this now we add another stage it could be a stage it could be part of something。

 but I'm going to add a state so you first write the result into every reorder buffer when instruction completion。

And you take that result and write it to the architectural register now right backstage as update the architectural state meaning to it。

Only one， the instructions is the oldest。Now we have a beautiful sequential。😊。

Updates of the architectural state， as you can see。

These instructions finish and they write their results into the reorder buffer nicely。😊。

And they just wait in the reor buffer。Makes that right。Now you solve the problem。No。

 but thumb we created some other problem。Meaning this instruction finish that wrote its result。

 what if a later instruction needs that result？😊，You cannot get it from the register file。

 you don't update the register file until this point。😡，You can stall。Or you just。

Access the reorder buffer to get the result。So basically。

 if a later instruction needs a value that's in the reorder buffer and not in the register file。😊。

Then。And I think this is a bad option， as you can see for performance。

The good option is read the value from the reorder buffer and the question is how this is why I talk about implementation because reorder buffer for structure is not very friendly for reading。

😡，So let's take a look so this is a more general picture so far we read from the Reg file it's a RA structure right nice you can read it cleanly。

 you index it using the Reggistrar ID。😊，It's very easy to design。They have bypas paths。

 you can get the data from there， a little bit more headache because we design combination logic to check whether we want to get the data from there earlier in the lecture。

😊，So register file is nice， it's indexed with H ID。

 which is the address of an empty random access memory bypasspas， a little bit more headache。

 reorderable for even more headache。😊，Why， because this is content addressable memory now。

 because you decoded the instruction， you need to read Reg 3。

Now register 3 can be in the register file， you access it。😊。

But you also access the reorder buffer and you figure out whether you should read the reorder buffer right and what you're searching for is。

😡，The register ID。That is written by any prior instruction to you。😡，Makes sense， right？

And that requires a content aable search because reorder buffer really a circular queue that's indexed by oldest instruction as the let's say。

 lowest number in that queue from a circular queue perspective。😊。

Registertry ID has nothing to do with indexing right so you need to search for the register value。😡。

So it's contentreable memory so this is what it looks like basically again I will not go through a lot of implementation over here。

 but。😡，You need to search， for example。😡，But I will very quickly go through it because we don't have a lot of time but hopefully you understood the problem。

 so if you simulate initially all registers are empty and so we need to have valids in the register file to keep track of whether the register whether the value in the register file is trustworthy。

😊，Makes sense， right？It's stored yet， basically if someone has updated the register file and you can trust it register if the value is not valid。

 that means that somebody is going to produce that value and somebody is inside the reorder buffer。😊。

Makes sense， right？So for example， let me go through it relatively for the first one， for example。

 if you want to multiply RV and R2 initially RV and R2 are hopefully valid。

 assuming this is the beginning of the execution， so you get the values from the register file。😊。

And you create an entry in the reorder buffer for this multiply。😡。

And you write the destination Reg ID as R3 over here， right？And yeah， basically you wait。

 this multiply may take a long time， for example。呃。Now this multiply。

 the next multiply is dependent on this multiply。😡，呃。It will access the register file。😡。

And it will find out that the value is not there right because it should be invalid。

 so it may it will probably it will trigger a search in the reorder buffer concurrently potentially and if the value is ready。

😡，It can get it from the reorder buffer now this is a very toy example because I have only three instructions。

 four instructions probably from the bypass paths you'll get these right potentially。

 but imagine a case where you multiply an instruction has produced its result。😡。

This other ad actually produces the result earlier than the multiply。

It's not in the register file because the result is in the reorder buffer entry2 actually is01。

23 over here， entry2， and this next ad can get it from the reorder buffer even though the previous multiplies may not have finished right？

Assume that multiply takes eight cycles， add takes three cycles。

Then this add probably gets value from the reorderable。😡，Makes that。Okay。

 so this is the idea now this is not good because you what you do normally is you can currentlyly access the register file and the reorder buffer to figure out where your value is and then multix the value that you need out。

😡，So normally what people do is they use in。😡，And now we're going to get closer and closer to out of order execution。

 so ask questions if you have any concerns so we normally access the register file first check if the register is valid and access reorder buffer next。

😊，And we're going to use a nice trick over here， which will get rid of the cap。😡。

The order doesn't need to be content addressable。😡。

Because the register file will give us an index into the reorder buffer telling that this is the reorder buffer entry you want to read from if you want this register at this point。

😊，So if the register is not valid then the register file register files stores the ID of the reorder buffer entry that contains or will contain the value of the register。

😡，Meaning a previous instruction invalid at that register and set。

I'm going to update this register at some point， and I'm in reorderable for NT55。😡，Makes sense。

 right and if a later instruction comes and says， okay， R3。😡。

R3 is going to come from we orderder about 255。😡，And it's not available in the register file。

 so I'm going to go into re order entry55 periodically until it's updated。😡，Makes sense right。

 so this is how you turn reorder over fronte。😡，RM structure that you read。

We've done something else actually， what we've done actually， we renamed R3 to reorder by 255。

Makes sense right Okay， so this will become more and more clear so basically we mapped a register to a reorderable entry register file is essentially a map now。

😡，It maps the register to a reorderablefrontee if there is an inf instruction write it to the register。

If the register is valid， the result value and the register file is good。

 you use it if the register is invalid。😡，You take that ID。

 reorder buffer ID and index reorder buffer and get the value from there。

 you can also get it from bypasspas， but there's other logic that detects which where do you get it from。

😡，Hopefully this makes sense， right？Okay。So this is what Penttme3。

 which was one of the most successful auto order processors implemented。😊，Actually。

 this is not exactly， but they got rid of the data values also essentially you have a register map。😊。

And this register map tells you whether the data value is in the Reorder buffer or is going to be in the Reorder buffer or is in the register file。

😊，Not exactly because they didn't have valves， but we' were going to get to that hopefully。

Hopefully this idea is clear， right？Okay， so this is the renaming oh okay sorry I shouldn't have skipped the slide because it's important we added something to the previous slide so our register file has a each register has a valid bit。

😊，If development bit is one。😊，You get the value directly， you don't need to wait for anything。

 you start execution。If the register value is0。😡，You have a tag。

 this tag is the pointer to the reorderable entry， you check the reorderable entry。😡。

If the value is valid over there， the result is produced。

 you get the value from there and you can execute。Makes sense right now if the value is not valid in the reorder buffer。

 you can check it again at some point or you wait for the bypasspas that depends on the pipeline logic after that point。

😡，Yes， you go first。Why do we need to tag and just transfer direct the value。这个。So exactly。

 I wanted to be clean in terms of， yeah， you can you can play tricks in implementation。

 that's not an exact implementation absolutely。😊，Yeah， the same point the。

Value fields and points zero and otherwise yeah yeah exactly you could also you could you could play a lot of implementation tricks absolutely but I wanted it to be very clean in terms of like explanation。

 right？😊，Okay， yes but does that mean that as an does the entire entry shift upwards No no。

 it's a circular queue what you do is basically if an instruction finishes you move the oldest instruction pointer to the next one。

Yeah， exactly yeah exactly exactly you need you need it's really a circular queue in the end it's as if you were implementing a circular queue in hardware。

 which is exactly what it is Yeah， yeah， that would be terrible Yeah， in general。

 you don't want shifters in general yeah in hardware。😊，Okay。Okay， these are very good questions。

 So now you've seen the renaming。 This is going to be a fundamental part。

 What we've done is we've renamed。😊，A register to a reorder buffer now if many instructions write to R3。

 no problem。😡，R3 will always point to the reorderable entry。😡。

That is going to write to the register the latest。And in between。

 while all the instructions are getting their values， they will get the value from the correct place。

😡，There may be thousands of instructions writing to R3。😡，You can link。They readers。Byい。

AAing the register file in sequential order。Okay， we'll see this more so don't forget the structure。

 so this pen teamium three essentially these are real structures it's a beautiful chip。😊，Okay。

 so basically this is registry naming， as I said earlier。

 output and antidepend are not two dependencies because same registry refers to values that have nothing to do with each other。

 now we've eliminated in them。😊，And I also said earlier that they exist due to lack of Reg IDs。

 names in the ISA。The Reg ID is renamed to the reorder buffer MP that will hold the register's value。

😡，So this is the renaming part architectural Reg ID is renamed to a physical Reg ID。

 you can think of reorderable entry as a physical register。

 but we're going to also separate the data values later on after renaming reorderable entry is used to refer to the register and you don't you forget about the architectural register until you're going to update the architectural state。

😊，At the end。This eliminates anti and output dependencies and it gives the illusion that there are a large number of registers。

 essentially if your order buffer is your register file physical register file right your architectural registers may be only eight in X 86 for example。

 well old X86 it used to be  eight。😡，But your reorderablef could be 128。😊。

Now it looks like internally， you eliminateumd these output and anti dependenceencies completely。😡。

Flow dependencies you have not eliminated， unfortunately， okay， yes。You say it in the。

I think three slides ago that our register。嗯。If you register always points to the latest reorder buffer entry。

 however， if you have a resource accessing that would like to access old entry。

 but reorder buffer apart for entry has already been updated。

Wouldt thatI don't know what old the entry means， so let's say you。

You use to register or free executions in a row。And then the first one changes the it register are free itself。

 the second one would like to access that result then it will be linked to the orderor buffer for ID right yes。

 so it will get to the orderor buffer for ID that the first one updated。

So it's all sequential updates， basically， right？😊，Yeah， exactly yes。Yeah， see。Okay， good okay。

 I mean， you can actually do this example on your own， we don't have time。

 but I'll leave it here So basically what we built is this。😊。

We have an in order pipeline with the reorder buffer that obeys the one9 and semantics completely so on decode stage。

 so this will maybe you clarify everything in the end in the decode stage you access the register file and the reorder buffer。

 you allocate an entity in the reorder buffer sequentially。😊，Check if the instruction can execute。

 if so， you can dispatch the instruction to the execution unit。Makes sense。诶。

Execute instructions can complete out of order， completion。

 instruction writes the result of the reorderro aboveuff， it doesn't update the architectural state。

😡，Now retirement or commit stage or right backstage， rename to retirement right now。

 you check if the oldest instruction has exceptions， if none。

 it write as a result of the architectural register survival or memory。

 otherwise flushes the pipeline and starts from the exception handle。😡。

Now when you actually finish the instruction， you move the oldest instruction pointer to the next one in the reorder buffer such that you check the next instruction in the next cycle。

 etc， hopefully this makes sense。And because you're updating the re orderder buffer sequentially and you're committing sequentially。

 you have linked the instructions appropriately as we will also see in Out of order execution。

 so this will come back again。😊，So we ought to offer some advances and disadvantages。

 conceptually it's very simple， as you can see， implementation becomes a little bit more complicated its canlam false dependenceencies。

😊，The downside is basically re orderder buffer needs to be accessed to get the results that are yet to be written to the register file。

 you could use cam add ID， you could use indirection。

 both of them actually affect you right cam both of them increase latency and complexity but interaction is a little bit better。

😊，Because you can hide the latency of injection as we will see too。

There are other solutions that try to eliminate the disadvantages， for example。

 checkpointing is that very commonly used future file， we will see that later on a little bit。😊。

But again， I will refer you to other lectures for that。

We don't tell time and these are some old lectures that I have if you're interested in that。Okay。

Joll we jumping thought a order execution or any questions？Jam is contact addressable memory。

Content addressable memory， yes。RM is random access memory。

 essentially you have the address and the address is indexed nicely， you decode the address， chm。

 you have the content inside the data。Field of the memory and you to search all of them。😡。

Fields exactly if you're searching the RB for register， you need to compare。 So okay。

 let me go back very quickly just to make sure it's all clear。 So for example， not in this case。

 but in the older case where we didn't have the okay tag。Okay， in this case， if you want to search。

 if you want to find。You're looking for R3， right， you basically need to search which instruction write to R3。

😡，So you need to compare the register ID that you have R3 to all of these destinationation Reg IDs。

 so there needs to be essentially comparators。That's comparing the registeredar ID you apply to all of the registeredgistr IDs。

Or valid reorder buffer entries。😡，And you want to get the latest one。

Because the latest one is the one that is going to produce the R3 that you want。

And this is complicated clearly， right， because it's content， you're searching for a content。

Makes sense。Okay， by adding this tag， we change that searching for content to an index basically。

So you just go through an address decoder them。Okay。Okay， that's good。

 you asked because we're going to do more and more of those content adjustable search and out of execution。

😊，And you can always play tricks to reduce those content that little search actually。

 but you cannot get rid of everything。Okay， so out of our execution is called also dynamic instruction scheduling because internally in the machine。

 we're going to schedule the instructions in order。😊，Different from the compiler scheduling。

 but again， we're going to obey the one Neman semantics in the end。

So just to make sure we have the same terminology， thispatch is really act of sending an instruction to a functional unit。

Renaming with reorder buffer elements stalls due to false dependencies， meaning。😡。

You if you have a false dependency， you can still dispatch instructions right if you have true dependency。

 now you're a problem。Basically， a non ready instruction stole dispatch of younger instructions to functional units。

Nonread means its result is not being produced by someone else。

 right some other instruction earlier in program order。

So this is a flow dependency right we eliminated the false dependencies。

 only flow dependencies remain， but with flow dependencies we saw the pipeline。😊，Now， this is。

Not good。have me use the same picture because it kind of makes the same point。

 you can also think of this thing as a long latency instruction it still the pipeline and there's an independent instruction that has nothing to do with that right and it cannot go because this long latency instruction didn't move somewhere。

😊，If I had a way of taking this instruction and moving it to the site for a while。

 this other thing could go right。Unless there's some problem with the pipeline， of course。

 but basically it's the same thing in the end。At some point。

 stalling is done and independent instructions execute。😊，Okay。

 so we're going to basically try to do better than the previous pipeline。

So how can we do better basically if you look at these two pieces of code， again。

 I'll answer the question over here， but this multiply。😊，Is fetched， this ad is fetched， decod。

 multiply starts executing， this ad stalls the pipeline because it waits for our three year。

Similarly， this Lord and at same thing， right？The ad essentially in both cases。

 the ad stoles the pipeline。😡，Even though the blue ones are completely independent of anything else。

 that's happening。Ad cannot dispatch because its source registergistry is unavailable。

 later independent instructions， the blue ones cannot get dispatched。😡。

And we want to basically bring these into the pipeline。So that they can execute。

But for that we're going to add more complexity， but I should also ask the question over here。

 how are the about two code portions different basically here the load latency is very variable because you may get a cache hit or miss。

😊，So handling this in software is much harder。Handling this in software is easier。😊。

But multiply latency can also be variable， multiplying by zero can take quick。

 multiply by something else can take long， so variable latency operations actually are usually difficult to handle for software。

😊，So I keep this in mind because we're going to talk about software based scheduling models also later on when we talk about BIW。

 for example。In general， load instructions are very difficult to handle because they may hit in the cache。

 they may miss in the cache， et ceter。😊，Okay。Okay， so basically the problem we're trying to solve is in order dispatch。

 also called scheduling， I don't like the execution as much。

 but that's what's caught on essentially if you want to dispatch instructions to execution units in a different way out of order essentially。

😡，We've kind of seen the basic idea before dataflow actually， these are in DDCA。😊。

But none of you have taken the GA yet， but I kind of gave you the idea of data flow in an earlier slide。

Data flow architectures， what they do is they fetch。

Or fire and instruction only when its inputs already ready。😡，Thiss a very different model。😊。

In one Neyman model you fetch an instruction when the program counter comes to it。

It's sequential execution。Here， data flow means。Keep track of which inputs of an instruction are ready and fetch and execute the instruction when all of its inputs are ready。

😡，Very different thinking， as you can see。Very hard to implement from a programmer perspective。

 but we're going to do internally data flow in a oneknowy architecture。

 so basically we will use similar principles but not exposed in the ISA。😊，But before I move。

 there are other ways to prevent these vegetables， compile time instruction scheduling reordering doesn't always work we're going to see theLIW later。

 value prediction could be one。If you can predict the values always correctly， that would be nice。

Doesn't always work and my favorite fine grain multitra always do something else， right this works。😊。

Except it comes at a cost rate， so these two things actually are much more difficult。

 but fine grain multi works that's why GPUs use it actually， but of course it comes at a cost also。😊。

Okay， so a basically the idea of Autoboard execution is to move the nonread instructions out of the way of independent one。

 just like moving that tramp out of the way， right？

Such that independent wants and dispatch and go on the lake。Pipeline。

I think of this as rest areas for non ready instructions like if you're in a highway and if somebody needs to stall。

That person doesn't stall on the highway right， they go into a rest area or some some they take the exit。

And other people can move。We're going to call these reservation stations。Maybe not the best name。

 but this is the name that stuck in history。So basically you move non ready instructions to the reservation stations while the instructions are waiting。

😡，In the reservation stations， you monitor the source values of each instruction in that area。

When all source values of an instruction are available， you fire or dispatch the instruction。

 now you send it to the execution units。😡，And instructions are dispatched in data flow order。

 not control flow order， so instructions are fetched， decoded， renamed。

 put into the reservation stations in sequential order。😡，But they're dispatched in data flow order。

 so internally， the machine is actually a data flow machine。😡。

And then instructions are reordered in the reorder buffer。😡。

So that you preserve sequential semantics。So the benefit is latency tolerance。

 this allows independent instructions to execute and complete in the presence of a long latency operation。

😊，So if one of the instruction is long latency and another one' is dependent on it。

 you don't wait for them， you can actually fetch not fetch。

 you can actually execute instructions that are completely independent Yes。

 you had a question or for do you move all the instruction。😊，And one is story。

You will see basically all dependent instructions can move us。Not just one。

 but all of them can move based on what we will see。Yes。

 so worst case if you have like a chain of dependent you basically go into each task move them into the ROB with the program counter increase program go to the next etc ceter until you get to an entity exactly yes yes I would change the ROB to reservation stations everything goes to ROB regardless of whether they're independent or dependent actually everything goes to reservation stations as you will see also yes。

Yeah。You will see soon no no， these are different structures you will see， you will see。

 you will see， don't get ahead of yourselfselve。😊，Maybe you're thinking of too much of implementation。

 but basically think of these as areas that you provide such that instructions don't stall other instructions right。

😊，You move the instructions to this place such that independent instructions can continue executing。

😡，Think about it that one。Okay， so what's the benefit I don't think we're going to get into the implementation today well since we have only 10 minutes but maybe I'll give you some but the benefit is this basically if you look over here。

 this is in order to dispatch with precise exceptions over here and this is the timeline you can convince yourself that these are the stalls you would get。

😊，Here， if you have auto order dispatch， this instruction， this a。

 the blue instructions are independent on the a instruction。😡。

So the blue instruction can execute and finish。And this next blue instruction can also execute and finish while the previous one is waiting in the reservation station。

 so basically what we want to enable is those waiting on the side。😊。

And you need some space for that if you don't take the instruction out of the way。

 it's not going to occupy the pipeline register， right？😡。

You need to put it somewhere else and that' somewhere else is reservation station。

 Why is it not RobB because Rob B， the way we defined it is really。😡，A control structure。

It's not a place where you keep the instruction， or OB basically keeps track of whether the instruction is ready or not et ce。

😡，When you should finish the instruction here， we really want to keep the decod instruction。

 for example， inside there， and we will see exactly what we keep。😊，Okay。

 so let me give you the concepts， let's see how far we can go into implementation。

 I have a nice animation of execution without word execution， but probably we're not going to get。😊。

So to enable this， you need to link the consumer of a value to the producer。

 and we've already figured out how to do that。😡，Because you want to ensure that when an instruction produces the value。

 the consumer gets that value， right？That's how you can actually figure out whether an instruction is ready to execute and send it to this pageant。

 you need to buffer the instructions until they are ready to execute。

Instructions need to keep track of readiness of their source values in the structure reservation stations。

 and when all source values of an instruction are ready。

 you need to dispatch the instruction to its functional unit， these four things are necessary。😊。

The first thing we've already seen， register naming。

 you associate a tag with each data value and instructions basically keep track of these tags。Well。

 you insert instructions to reservation station after rename it。

And we're going to insert all instructions I gave you the idea earlier with。

Only dependent instructions， but all instructions go through this for a clean pipeline design。Okay。

 this is where things get a little bit more complicated when an instruction finishes its execution。

 it produce a result， this result is associated with attack。😊，This is my reorder buffer ID。😡。

And it's basically broadcast attack。😡，And everybody。That's waiting for that tag captures the value。😡。

Because I you basically broadcast both the tag and the value and if there's some instruction that's waiting for that tag in the reservation station。

 you capture the value that's coming now you know that you got the value from the producer because you were linked to the producer earlier by registry na。

😡，Yes。the is on the which is' exactly multiple instructions may get the same tag because they maybe depend on the same instruction right？

这个意啊。Yeah， that comes while we here。Yeah， you're getting ahead of this yeah。

 that's that's basically when you wake up the instruction right here。

 basically when an instruction finishes。😊，It's broadcast the tag and all of the instructions that are waiting for that tag get captured value。

Now one instruction may have one of the values ready。

 another value is not ready then it's not ready to execute yet al right yes。

 wouldn't you need some kind of control logic for the instructions to detect which tag they should capture yeah I mean the control logic is this broadcast logic essentially you broadcast the tag and then you check yeah there is easy to be comparative basically this actually essentially content addressable memory again yes as we will see。

😊，TheEx yes， we will see that。😊，I don't know what dynamic means， but。😊。

Sa it again the like 50 dependencies well most instructions not have 50 dependencies right we're talking about registers over here usually an instruction is dependent on two registers in general yeah and in fact in fact in fact whenever instructions have like for example this conditional move instruction it's a famous instruction it has three restr prints。

😊，Two data opera， one control our， whether whether you move to the conditionally and this actually causes problems in general。

 usually unary registers and binary values are fine right basically two inputs and one inputs are fine if you actually have more inputs than you to broadcast basically complexity increases with the number of sources you have and also a number of。

😊，How many things you're searching， you will see all of this， but were still talking about concepts。

😡，Don't confuse the concept with implementation， we're going to get to implementation。

Because in real implementations actually things are much more， let's say optimized today。

 we're not going to get into a whole lot of those optimizations。

 but you need to learn the concepts first to implement that。😡。

When all source values of an instruction are already then。

 you need to dispatch the instruction to its functioning。😡。

So basically there needs to be some control logic， more control logic to detect if all sources are ready。

 if an instruction is one source and it's ready then the instruction is ready to go if an instruction says two sources and both of them are ready meaning tags are broadcast or you already read the value from the register file earlier as we will see later on then you can wake up this called wakeup now if multiple instructions are awake you need to select one per functional unit this is your question I think。

😡，If multiple instructions are ready at the same time。

 you need to choose which one to send to a function。

 so there are a lot of issues clearly and hundreds of instructions may become awake in a given cycle right imagine one instruction producing a value and hundreds being dependent and they're all in the machine。

😡，You need to choose， yes。exception again firing firing the sources of become it handled like an exception no it's firing like sending the broadcasting that value is that it back into the cycle to bring it into an instruction？

Would you have to then you'd have to because you have to。

 because I'm assuming there'd be other things already been type scheduled in。

 not necessarily all of the scheduling goes through here。So the whole machine operates this way。😡。

Does that make sense， there's no other way of putting instruction into the execution units。😊。

You'll see it's， yeah， okay。😊，So this is your reading if you're interested you can read about it it's a very hard reading。

 but basically at the time this was designed Thomas So's algorithm was designed the major difference today is we have precise exceptions I'm going to show you in the later lecture unfortunately because we don't have time。

😊，How Tommosos machine kind of operated with an example today we have precise exceptions we've added out of word execution and that made all the difference basically and this was proposed by multiple papers that won the microtest of time award that were written 40 years ago。

 40 50， 40 okay good。😊，Not that old yet。Yeah， so automotiveor execution variants are used in most high performance processor and they all pay based on the same principles in the end。

😊，So if you look at this， this is an out of order execution machine。😊。

Now this makes things a little bit more clear， basically all instructions go to reservation stations over here。

😡，This is you can think of this as the reservation station this is called a scheduling window and we will see how it exactly operates you rename the instruction。

 you put it into the reservation stations and instructions go into execution units only from the reservation stations so all of the principles that Ive shown you concepts there is no other path to get into the execution units you have to go through the reservation stations okay。

😊，And at the end， the results go into the reorder buffer and you write to the architectural state in program mode。

 so this part of the machine is completely out of order execution。

 it operates based on data flow principles。This part of the machine is really control flow and this part of the machine is more control flows。

Yes， otherwise you run the problem that he was running into the head。

Meaning there may be some other path and how do you actually schedule an instruction from other path。

 right？Okay， because I thought using a highway analog。theYeah。

 that doesn't analogy only stops at that at some point， take analogies with a grain of salt。 Yes。

 you could do that， but it's expensive probably。 Yeah that's right， potentially。😊。

They become immediately ready， but it doesn't mean that they immediately go into the execution units。

 yes。Exactly exactly exactly yes， basically all instructions go to the same path。

 but they may become immediately ready， but that doesn't mean that they're going to get scheduled because somebody else may become also ready and you may have a different prioritization policy in terms of who goes first。

😊，Okay I think I already kind of said this so basically actually this is important because in the example next week we're going to rename instruction into the reservation station ID that's the example we're going to follow but I guess after renaming reservation station ID is going to be used to refer to the retry okay that's a good place to stop。

😊，Next week we're going to pick up here， see an example of Outerward execution and let's see how far we can get after that。

 but if you're interested in knowing more you can go through these slides and these slides are actually pretty self-explanatory in terms of how an Outward execution machine operates。

😊，Because I see that some of you are very excited about learning how this operates more。找这个。😊，Okay。

 see you next week， then。不。嗯。然后呢个。

![](img/4c9813a546b06b12bb62a7f9db8bfc5a_6.png)