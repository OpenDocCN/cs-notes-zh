# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p17 -17- L14_ Out-of-Order Execution (Spring 2025).zh_en -BV1iV1XBWEJW_p17-

![](img/d75a2d2d05bae1ba71eef0f24a7544ab_0.png)

Okay， with that said， I think we're going to start perhaps one of the most exciting topics。

 we've kind of been building up to it in this class， out of order execution。

 this is a way of executing instructions out of their original program sequence。😊。

And it's a very influential way it's been used in essentially all computers today。😊。

Even though some people started saying that we're not going to use。

Sophisticated hardware techniques to actually execute instructions we're going to。

Hunt all of the difficult things to the compiler。They've all come to use out of word execution today after 10 years。

 20 years， they figure out。No you have to use hardware to actually accelerate instruction processing by doing things out of order so you'll see the importance of this into the future also we'll cover the basics。

 there are a lot of optimizations that build on what we cover unfortunately we' will not be able to cover all of those optimizations clearly today's out of order execution engines like what's in my pocket for example。

 or what's here are very very sophisticated engines and I will show you a picture of I guess kind of what's in my pocket somewhat reverse engineered as the very last slide of this lecture。

Does that sound good？

![](img/d75a2d2d05bae1ba71eef0f24a7544ab_2.png)

Okay， cool。Okay， so this is where we are basically we've covered a lot of pipelining precise exceptions yesterday we set up for today。

 we talk about the register renaming。😊，Renaming the registers from the architectural register space to and micro architectectural namespace。

 which we called reorder buffer yesterday today we're going to use that concept。

 but today we're going to finish out of word execution hopefully and I will release a premiere of load store handling unfortunately we don't have time to really cover load store handling but for your own benefit you can watch that and see that's really the most sophisticated part of the machine today how to handle loads and stores。

It used a lot of content addressable memory you got introduced to content addressable memories yesterday unfortunately that part is very difficult to eliminate content addressable memories from okay these are your readings。

 I think you've seen a lot of these but except for this optional one this optional one covers a state of the art processor in 1999 a lot of the principles remain the same today today there are a lot more optimizations and next week we're going to cover branch prediction which is essentially how to keep the pipeline full in the presence of conditional branches and this paper covers this paper covers a lot of interesting ideas in 1990s let's say of course we're going to look at much more advanced ideas this week。

😊。

![](img/d75a2d2d05bae1ba71eef0f24a7544ab_4.png)

Okay， this is where what we built up to yesterday， we built an in orderder pipeline with reorder buffer with multicycle execution units。

 as you can see， and we did that by using a reorder buffer。

 we did the instruction reordering precise exception using a reorder buffer I'll go through this just to jog your memory。

 but basically in a pipeline like this in the decode stage。

 the instruction access to the register file and the reorder buffer allocates an entry in the reorder buffer and you check if the instruction can execute。

 meaning if the source registers already， if that's the case you dispatch the instruction into the functional unit。

😊，Okay， if one of the source registers is not ready for whatever reason。

 you cannot dispatch the instruction， that's a non ready instruction thats basically stops the pipeline。

😡，And instructions can complete out of order， which is good and when they complete they write their results of the reorder buffer first。

 which is micro architectural， they don't update the architectural state immediately。😊。

The architectural state gets updated in program order when the oldest instruction doesn't have any exceptions and it's completed。

 it write， there's some control logic that writes the result to the architectural register file or memory。

😡，Otherwise， if there's a problem with the instruction。

 the control logic flashes the pipeline and starts from the exception handler or if you're handling an interrupt at that point in time basically this is an in order dispatch machine dispatching means sending instructions to the functional unit and out of order completion machine you complete the instructions out of order and you retire instructions still in order in program order as specified by the sequential semantics of the program right this is also called an in order execution machine because in order I like in order dispatch better because you really dispatching an instructions to the functional unit in program order but you're also starting the execution of instructions in program order basically you don't start the execution instructions out of the program order out of sequence if you will today we're going start the execution of instructions and functional units out of order。

O。😊，Okay， so let's move on so this is what we've covered。

 we basically said that register renaming eliminates the right after read and right after write dependencies which are not real these exist because there are not enough names in your register file in the architectural register file and we're really the only dependencies that we really need to deal with our flow dependencies so in order to deal with flow depend is what you really need is to make sure that the dependent instruction gets connected to the producer so we can think of as this instruction is producing the value of R3 and this instruction is consuming the value of R3 you really need to connect the producer to the consumer when the consumer comes into the machine the consumer needs to know where to get its value from。

😊，Okay， here you can get rid of these dependencies because they're not real dependencies。

 you can rename this R1 to something else r 1000， let's say or reorder buffer or something。

 some reorder buffer entry number as a result this value has nothing to do with this value which makes sense right we've discussed this multiple times and that's true for this output dependence also basically we have seen yesterday again that the output and antidependencies exists due to lack of register Is or names in the ISA instructions at architecture and they're not real dependencies because the same register refers to values that have nothing to do with each other。

Meaning there is no producer or consumer relationship between these two instructions they're just they just happen to be writing to the same register that is allocated to the value that they're supposed to produce。

 but from a communication perspective between instructions。

 there's nothing between these two instructions， right？😡。

They just happened to collide in the namespace， if you will。

 and basically we eliminated this problem， this collision in the namespace by renaming the architectural register ID to the reorder of entry yesterday。

 and you remember the illustration we went through we're going to go through a very similar illustration today。

😡，Basically we said that register ID the architectural register is renamed a reorder buffer entry ID。

 you can also think of this as architectural Reg ID being renamed a physical Reg ID and after renaming reorder buffer entry ID is used to refer to the register basically you don't you don't need to hold on to the architectural register ID until you update the architectural register state at the end of the machine and we will see that and the benefit of this is now this eliminates anti and output dependencies so that when you're dispatching an instruction in a multicycle execute machine early on you don't need to stop。

😊。

![](img/d75a2d2d05bae1ba71eef0f24a7544ab_6.png)

So basically， you can dispatch instructions by eliminating anti and output dependencies you don't need to stall at this point。

😡，Okay。😊，So as long as they are ready， of course， as long as these instructions are ready to go。



![](img/d75a2d2d05bae1ba71eef0f24a7544ab_8.png)

Okay， and this also gives the illusion that there are a large number of registers because of ISA you have limited number of architectural registers because of the instruction and quoting is limited。

 but now you can expand the register space by renaming that architectural register space to a much larger physical register space or micro architectural register space called the reorder buffer yesterday。

😡，But you will see today that this reorder buffer is actually just one place where you can rename architectural registers。

 you will need a larger name space and you will need to pro space for it。

 it doesn't have to be the reorder buffer and we will see that today we will introduce the concept of reservation stations and we will basically rename the registers to the reservation station IDs。

 it could be any namespace actually in existing processors it's the physical register file and we will also build up to the physical register file in a little bit。

😡，Okay but yesterday we saw that you rename the architectural history ID to the reorder of entry ID and this is how we did it。

 I'm not going to go through this example again， but remember that if an instruction is writing to r0 for example。

 it sets the vel of the r0 to0。😊。

![](img/d75a2d2d05bae1ba71eef0f24a7544ab_10.png)

The value becomes not useful for future instructions at that point。

 but you also the instruction when it's being decoded。

 sets the tag to the reorder buffer entry ID of the instruction because every instruction gets allocated or reorder buffer entry。

 so this tag at that point refers to the renamed register。

 so register zero is renamed to this taggged which happens to be the reorder buffer entry of the instruction that's producing that register。

😡，And we said that yesterday， if all of the instructions in the machine are writing to a particular registeristtry。

 say register3， there may be 16 definitions of R3 in this particular reorder buffer because there are 16 entries as you can see as a result the register may be renamed 16 times and the later instructions will get the correct value because instructions are being decod in order they will see the taggged that is updated by the latest instruction that's writing to R3 that's the beauty of the in orderder decode okay so every instruction that's going to source r3 will get the correct definition of R3 or correct location and the reorder buffer that's going to produce the R3 value that this instruction is supposed to take because of the in orderder renaming that's happens in the beginning or in order decode so basically this is the new name you can think of this tag as the new name of the architectural register。

😡，Makes sense， right and internally in the machine， you don't need to know about R0。

 R1 R3 R4 anymore， you just care about this tag。😡，And this tag can be used to communicate the readiness of a value。

😡，So for example， if an instruction that's producing R5 has a tag 16 reorderable French well it doesn't exist over here。

 we'll say tag 14， reorderable French 14， it can say I'm producing reorderable F 14。😡。

Anybody who wants to order buffer T14， compare your tag to it if it's what you need。

 then get the value that I'm sending to you。😡，So this is how we're going to accomplish communication。

 basically。No more register architectural register names and you're going to see that soon Okay。

 and this is also one slide we covered yesterday， we're going to go back to this today also。

 but basically you can think of this as a renaming table and Intel called this the register alias tableEssential you have a bunch of architectural registers。

😊，Some of them are in the architectural register file and some of them are in the reorder buffer and you basically have pointers from this register alias table to the definitions of the registers that you're supposed to get okay so this is very similar actually this picture is very。

 very similar to what I've shown except Intel has decoupled taken this taggged and only the tag is over here basically。

😡，So what I have done is basically tag and values together and Val bits and then a separate reorder buffer。

 but Intel has pulled out the tags over here and we will see the reason for this also later on。

 but it's essentially the same thing these two pictures are essentially the same thing the values happen to be separated over here in the retirement register file that Intel calls。

😊，Okay， we'll get back to this picture and we'll get back to a more advanced picture also。😡。

Any questions this is kind of a relatively short review。

 but also I wanted to motivate something that we're going to discuss today also so now we're going to talk about auto order execution which is really dynamic instruction scheduling thiss also called dynamic instructions scheduling because the scheduling of the instructions is done by the compiler right when you get the program compiler does some reordering of the instructions etc and that's a static schedule now we're going to violate that schedule internally to decide which instructions should dispatch to the functional unit in which order。

So let's take a look at this pipeline that we have looked at earlier。

 basically remember dispatch is the act of sending an instruction to a functional unit。

 I ignored the reorder buffer allocation over here。

 but I will have it over here later I'm going to eliminate reorder buffer to explain things more simply but we're going to reconstruct it again hopefully basically we use renaming with a reorder buffer to eliminate stalls due to false dependenceencies basically if you do renaming when you get a false dependence。

 you don't need to stall because you eliminated that dependence right。😡，Now。

 the problem still remains that if an instruction is not ready。😡。

If if there's an instruction that's being decoded over here and if it doesn't have the values that it needs or any one of the values that it needs。

 unfortunately it cannot go and get dispatched as a result result no other later instruction can get dispatched so basically an instruction stalls if it's not ready。

😡，So we're going fix this problem today and I'm going to use or abuse the example that I used earlier so if you look at this instruction this tra over here it's long latency for whatever reason I don't care if it is an exception maybe it's long latency because it's doing something important right unfortunately this instruction stalls the pipeline there's another independent instruction it's going somewhere else let's say it's using some other functional unit it's going to use some other functional unit unfortunately it's cannot enter the pipeline because there is this long latency instruction stalling the pipeline I think it's very similar to this concept and then there are other instructions so one way we could have enabled this instruction to enter the pipeline is bypassed right maybe put this instruction somewhere else and we're going to do that essentially。

😡，Of course， it's much harder to do in the tram lines。

 But if you unless they have parallel tram lines or somewhere to buffer。

 So if you have somewhere to buffer this tram like a bigger area， then other trams can bypass it。

 right， And that's the idea that we're going to do today。 Okay。

 so you can see the consequences of stalling。People start walking as opposed to taking the trap。

But finally， the independent instruction is thispatched and is executing over here。

 but we don't want it to wait if we know that an instruction can actually go ahead。😡。

Earlier than an older instruction， we should enable that instruction to go ahead so that we can get high performance right that's the idea。

😡，Okay， so that's the problem we're going to solve today。So basically can we do better。

 can we do better than what we have built up to yesterday？😡，And the idea will be yes。

 how can we do better before we discuss this， I'm going to talk about some alternative ways。

 so let's take a look at this example code。😡，Both of these codes are actually very similar to each other。

 if you' are observant you will see that the last four instructions are exactly the same。😊。

Addd instructions is dependent on the multiply here。

 add instructions is dependent on the load instruction here。

 and all of these three blue instructions are independent of the a or the load。😡。

But basically when you finish the first ad it stole the whole pipeline because it's waiting for this R3 to be available right。

 assuming that multiply takes a long time and mu load takes a long time okay if it takes one cycle it's not going to stall the pipeline because but unfortunately the pipeline may be long so it depends on when you actually generate the value so basically ad cannot dispatch because its source register is unavailable。

😡，Because its depend on the multiply or the loads。But later instructions also cannot get dispatched。

 basically blue instructions， these poor blue instructions have nothing to do。😡。

They're not waiting for the result of the ad or the multiply， but unfortunately。

 they cannot get dispatch because。😡，There's nowhere to put them let's say or nowhere to put the at so we're going to fix that problem basically so I should also mention that these two quote portions are different in the sense that load latency is actually very different potentially right load latency is quite variable it's actually unknown until run time and this causes more problems so multiply latency may be known it may be all multiplies take four cycles or eight cycles。

😡，But load latency will depend on where you will service the load from will it come from the L1 cache L2 cache L3 cache main memory will it get a page fault as we will see but we will see all of those later on starting with lecture 20 or so so' hold on to that so loads are going to cause us a lot more headache basically in the future that's why we're not going to deal with loads today at least。

😊，We're going to deal with an example of multiplies。

So basically I think you start thinking about this basically。

 this is easier for the compiler to potentially try to schedule and avoid this stall。

 it's still not that easy， but compilers job is a lot harder over here basically because compiler has no idea potentially that this load is going to hit or miss in the cache。

 okay。😡，So whenever you have memory access。Things become a whole lot worse， let's say。

 so that's why I think a big focus today in modern systems is to figure out how to deal with memory in a much better way。

😡，Okay， so let's talk about preventing these dispatch stalls。

 you have this instruction that's not ready at it's not ready because it's dependent on a prior instruction that doesn't produce its value yet。

 how do we prevent these stalls？😡，So basically the problem is really in order dispatch or in order scheduling or in order execution。

 the solution that we're going to pursue is really out of order dispatch basically figure out some way of all。

😡，Dispatching these instructions out of order。 Of course。

 you need to make sure that everything still works correctly。

 That's why we're going to add a lot of hardware。But we've seen the basic idea before， actually。

 if you remember the data flow。😡，Data flow says that fire and instruction only when its inputs already ready。

 it's essentially the same thing。Start executing an instruction when its inputs are already ready。

 in fact， start fetching the instruction when its inputs already ready。😡。

So dataflow takes this concept to next level， so what we're going to do in this lecture is build an internal data flow engine。

😊，Inside a control flow machine， meaning。From the programmer's perspective， it's a oneknow machine。

 but from the micro architectureect perspective， it's actually going to produce a data flow graph of a program。

😡，And then and actually I'm going to go through an example where I will show you that by just looking at the internals of the state of the machine。

 you can reverse engineer the data flow graph of the program that's executing。😡。

I think that's very beautiful basically， and we're going to combine these two concepts。

But we're not going to make life harder for the programmer telling the programmer you're going to program in data flow。

 We're not going to do that。 Programr is still going to program using sequential instruction stream。

😡，Okay， basically， you will use similar principles as data flow， but not exposed in the ISA。

 that's the same thing I said in a different way。😡。

But we've also seen any other ways to prevent thesepat stalls。 Can anybody some name some。

We've seen three ways of actually preventing dispatch dolls。Without calling them thepat dos。

 of course。😡，Anybody？Yes。So data forwarding helps， yes。It didn't come the first way， okay。

 think about it， maybe some other things。Yeah。So I've given you this one， right？

Compile time instruction scheduling reorging。So if the compiler is able to schedule instructions such that the value of an instruction is always ready when the instruction starts getting into the pipeline that could work right but that's a very tough problem。

 people have tried to actually work on this problem for decades and decades， it's still not enough。😡。

But this is still possible to do in some cases， especially if the code is regular。😡。

Maybe related to data forwarding， you can predict the values。This is a top problem also okay。

 if you can actually predict the value， for example， if you go back over here， this picture。

 so here for example， the compiler could have reordered these blue instructions earlier than the ad。

😡。

![](img/d75a2d2d05bae1ba71eef0f24a7544ab_12.png)

And tolerated the latency of the multiply， right potentially。

So that's the compile time reordering if the compile can do that usually there's not enough parallelism that the compile can expose value prediction says don't do that。

 but predict the value of R three that's happening here maybe you don't have the value of multiply okay。

 predict that it's zero。😡，Is that a good idea， how do you predict it， not so easy。

 basically value prediction doesn't always work？😡。

![](img/d75a2d2d05bae1ba71eef0f24a7544ab_14.png)

But have you've seen one idea that really works very well， anybody？Your last chance。

Really works very well under specific circumstances。Find grain multi three。Basically。

 if you dot find grain multi trading。There is no problem。 There iss no dispatch stall。

 If you have enough threads， all of the instructions are independent。 They're from different threads。

 but basically， the pipeline never stalls。 right， That's beautiful。

 But this requires you to have enough threads。And also。

 if you really care about the performance of a single thread， this is useless for you， right？😡。

IfIf your goal is to really improve the performance of a single thread。

 you cannot basically resort to multithreading， unfortunately fine grain multithreading at least so if we've seen actually all these ways the first two can help the performance of a single thread but usually they're not very well applicable。

 the third one is very useful when you have lots of threads but it's actually hurtful when you have a single thread。

 it's actually because because you're fetching from a one thread every n cycles where n is the number of pipeline stages that you have。

😡，Okay， so that's why automotiveward execution has been very successful basically。

 none of these methods work。😡，So the idea of about over execution is very simple。

 I've kind of hinted at this， move the non-ready instructions out of the way of the independent ones。

 basically add some hardware buffers and if an instruction is not ready no problem move it somewhere else。

 in fact what we're going to do is do it more methodically every instruction is going to go into a buffer first and then we're going to schedule the instructions out of those buffers。

😡，Makes sense， these will be called reservation stations and we're going examine which instructions are ready and which instructions are not ready。

 and then we're going to schedule the instructions or dispatch the instructions from these buffers Okay that's the beauty so you can think of at the beginning of the pipeline we're going to add a big buffer called reservation stations and all of the instructions are going to get buffer there until they are ready to execute。

😡，You can also think of this as rest areas for non ready instructions or reservation station if you're driving on the highway。

 when you need to stop， you don't stop in the middle of the highway， right？If you do that。

 you may have a lot of trouble with people behind you。

 but that's what we were doing in the pipeline earlier。😡，Somebody needs to stop。

 this multi instruction is taking a long time， it needs to go to the restroom or whatever。😡。

Stops right in the middle of the highway and everybody else gets backed up。Well， go to the rest area。

 right， wait over there， so that's the idea basically。😡，But again。

 we're going to be more methodical every instruction is going to go there because otherwise it may be it's a a bit harder to deal with some things。

 but we're not going to go into that basically in this resting area waiting area。

 instructions are going to monitor the source values。😊，Basically。

 is my value ready is the register that I'm sourcing ready。

 and if both of them are ready if it's a binary if it has two registers。

 then the instruction becomes ready。😡，When all source values of an instruction are available。

Be fire in data flow terms or dispatch the instruction to the execution units。Its beautiful now。

 right？So basically instructions are dispation data flow order， not control flow order。

 so that's the key realization we can dispatch instructions and data flow order。

 so the big benefit over here is latency tolerance。

 meaning that if an instruction is taking a long time， it's not going to stall the pipeline。

 independent instructions can execute and complete in the presence of a long latency operation which could be a multiply as I showed you earlier。

 which could be a load as I showed you earlier， which could be anything actually。😡。

As long as it takes more than one cycle， you can tolerate that latency if this mechanism is able to find independent instructions in the program and people have shown that actually theres a lot of independence in the program。

 there is a lot of instruction level parallelism， if you look at a larger window of a program。

 this instruction level parallelism may not be easy for the compiler to discover。😡。

That's why hardware is more easy to discover because compiler may not be able to safely determine which instructions can be executed before which other wants。

😡，Because if it moves the code from one place to another place it's really potentially violating some semantics in the program right here we are not violating semantics in the program we're just deciding which one should execute early or late we're not moving code anywhere the code is exactly what the compiler produced and the compiler can say I'm not going to change the code that the programr dictated right？

😡，Okay。😊，Everything's clear。Okay， so basically let's take a look at this pictorially。

 this is in order dispatch machine with precise exceptions that we've built。

 this is the code that I'm showing you redme is dependent， so this is dependent on the multiply。

 this is dependent on the multiply but the blue ones are independent as you can see here in this pipeline。

 you execute the multiply， multiply takes four cycles in this particular case as you can see when you decode the second a。

 you stole the pipeline right。😊，And the next instruction stalls， everybody stalls after that。

With auto of order dispatch and precise exceptions， instead of stalling the pipeline in the first ad。

 you put it into an area where it waits。😡，And then you keep filling the pipeline and you figure out that this instruction can execute。

 right， It executes， generates its results right in the reorder buffer。

 And then the next instruction can also execute。But this instruction also goes to weighting。

 so you can see that by just looking at this piece of code。

 you can reduce 16 cycles of execution time to only 12 cycles。😊，And that's a lot actually。

 that's 25%， right。Immprovement and in large pieces of code empirically people have shown that out ofor executionction actually gains 30 to 50% performance improvement compared to a very aggressive in order dispatch machine sometimes even higher my PhD thes。

 for example， shows that it's much higher。Okay。So okay。

 what do we need to enable automotive motor execution So there are four things that you need to enable One is you need to make sure that the correct data value semantics are obeyate。

 meaning the consumer。😊，Overvalue needs to be linked to the producer so that the consumer gets the correct value or a correct definition of a register and this is done we are register renaming as we will see。

😡，Then you need to buffer the instructions until they are ready to execute。😡。

Because you need to prevent the dispatch stall and you need to provide some place hardware to keep these instructions。

😡，While the instructions are being buffered， they need to keep track of the readiness of their source values as we have discussed。

 and we're going to talk about that a little bit more。😡。

And then when all the source values of an instruction are actually ready。

 we need to dispatch the instruction to the function unit。😡，So these four things are necessary。

 and when the instruction actually produces its value。

 it's actually going to broadcast the taggged such that the consumers can get the value after it executes。

😡，So the first one is accomplished， linking of the consumer to the produce accomplished using register renaming that we have seen。

 we associate a tag with each data value and we're going to see that more today。😊。

Offering of instructions until they're ready is。Acomplished using reservation stations。

 you insert instructions into reservation stations after renaming it has a historical name unfortunately it's called reservation stations。

 some process called these issue choose。😊，I kind of like reservation station better it not like a resting area。

 a resting station， if you will。😊，While how do the instructions keep track of the readiness of the source values。

 basically an instruction that produce a value broadcast tag or the name of the register。

 when the value is produced， instructions that are waiting for that tag。

 compare their source tag to the broadcast tag， if there's a match that means that the instructions is waiting for that value。

 then the source value of the instruction becomes ready。😡，Okay。

 and when both source values of an instruction。😡，Are readyy or when all source values because some instructions wait for one value。

 some instruction wait for two in rare cases three values， but if all values are ready。

 then the instruction wakes up。And if multiple instructions are awake。

There needs to be some logic to select one instruction to send to the functional unit。

 So theres there needs to be more arbitration because multiple instructions can wake up at the same time。

Makeup meaning ready， become ready， there's all of their source already。😡，Okay， so that's the idea。

 basically， does it sound good。Now we're going to implement this in hardware and this is clearly going to cost us something。

 it's not going to come for free。 we've had register renaming so that's not going to cost us。

 but all everything else over here is going to cost us。😡，And the cost is a lot。

 that's why people have optimized this over the course of multiple decades。😡。

So I will also mention that this registerstry renaming this algorithm is one way of doing art order execution it's the dominant way today。

 it was invented by Robert Thomas Soula who was a chief architect at IBM。😊。

In IBM 369 mass floating point units， and remember， if you remember。

 I mentioned this as an example out of order machine。😊。

And you can read actually this beautiful algorithm that we're going to go over in this paper。😊。

The major difference today is IBM 31691 did not have precise exceptions。And as I mentioned。

 it was not successful because of that。😡，So this was implemented in 1960s， in fact， when these folks。

 these engineers wanted to implement it， they said it's too costly to support precise exceptions so can we do imprecise exceptions so they went all the way to the IBM's boss。

 big boss。😡，And they reluctantly said， okay。And that was a good decision for progress of science。

 but that was not necessarily a good decision for business in the sense that IBM did not make a lot of money out of these machines。

 let's say， because people could not program it。😡，But I mean it was actually they were the leading company at that time in doing Out execution so the major difference today is precise exceptions basically what we did yesterday is really critical for the success of this sort of machine because you need to re orderder the instructions at the end。

😊，And this is provided by later works that actually showed that you can do autoor execution with precise exceptions together I'm going to essentially describe things without precise exceptions first because it's easier to discuss。

 but then we're going to talk about precise exceptions a little bit more but yess these lecture is directly applicable to today's lecture actually so as a result Autoor execution variants are used in most high-per processors today starting with Intel Pentium Pro and then AMD followed up with K5 but almost all high performance processors today use。

😊，So this is how things will look like basically we're going to decode instructions we're going to put into the reservation stations。

 this is called a scheduling buffer， if you will abstractly。😊。

So this part of the pipeline is still in order， and then we're going to dispatch instructions when they're ready in out of order。

 so this part of the pipeline is completely data flow。😡，Driven。

 and we're going to reorder instructions at the end， write the results into the reorder buffer。

 but you can see that when instruction finishes， it's going to broadcast the tag and the value so that dependent instructions can get the tag and the value they're waiting for。

😡，That's how we will actually communicate the readiness of a value when an instruction venture is going to broadcast。

 oh， I'm producing I'm producing this physical Reg X， and if you're waiting for physical Reg X。

 better capture the value that I'm sending。😡，Okay， so that's how we will communicate。

 this is the data flow communication internally。😡，So there are two humpss over here。

 one is the reservation stations， which is the scheduling window and the other is a reorder buffer。😊。

This is also called an instruction window or active window。

 basically reservation stations hold instructions that have not been scheduled yet。

 the order buffer holds all instructions that have not been。

Retired yet that are not updated the architectural state yet。 I like thinking of this as a。😡。

Camel like this。If you want to remember a pipeline out over execution pipeline day。

 this is the scheduling buffer over here， and that's the reorder buffer。😊，Of course。

 it doesn't work this way in a channell I believe， but it's kind of a pipeline also anyway。

Okay so that's the general organization this is from your paper that I've assigned a lot of things will become more clear today。

 but today's basically the purpose of me showing this is existing processors do this space because this is the renaming and dispatching for example and these are the reservation stations over here they called instruction buffers and these are the functional units and then they have separate register files we're going to get back and then there's a reorder and commits over here as you can see today we're not going to talk about the memory interface it's going to complicate things and that's the optional lecture。

😊，And Tommosoul's machine was kind of similar， except it's looking at just the floating point units over here。

 we're going to look at something like that like Tomoso's machine actually。

 we're going to look at multiply and at over here。😡。



![](img/d75a2d2d05bae1ba71eef0f24a7544ab_16.png)

Okay， and you can see that this actually had impact in the real world。

 even though it was commercially generally not very successful。

 IBM 3691 was used in supercomputers at the time in 1960s for space exploration， for example。😊。

And you can see that at the time computers used to be huge right now。

 this thing is more powerful than the entire room。It's amazing， right？Okay。

 so recall once more we're going to rename registers basically I've already gone through this slide multiple times I'm not going to go through this。

 but basically a register ID is going to be renamed to reorder buffer ID or reservation station entry ID for the rest of this lecture。

 I'm going to use reservation station entry ID， not the reorder buffer entry ID。😊，After renaming。

 we're going to use the reservation station ID to refer to the register。😡。



![](img/d75a2d2d05bae1ba71eef0f24a7544ab_18.png)

So basically for this we need a register rename table called their Reg As table and you've seen this already I've kind of reordered the fields over here。

 but basically you have register zero to register 7， this says whether it's valid。

 if the valid bit is set the value in the table is correct。😡。

You can it can be trusted basically otherwise tag specifies where to find the correct value。

 that's the name， that's the new name tag is a unique name for the value to be produced that's how you do renaming and recall from precise exceptions lecture here we essentially have the same thing。

😡，Register file or register aliaS table， you can think of it that way we're going to separate things more later on。

 but let's start with so this lecture so let's let's now go through an example in this lecture we're going to look at the register file or register alias table right。

Tag is the pointer to the reservation station MP that will produce the value。

 so I'm going to introduce reservation stations over here soon， and for simplicity。

 we will ignore the reorder buffer。😡，We'll add it later， but adding it is relatively easy， actually。

 we're just going to ignore it for now。😡，So Tommoso's algorithm， this is actually a full definition。

 maybe I'll go through this relatively really quickly。

 but basically first you check whether a reservation station is available before renaming。😊。

And rename an instruction only if a reservation station is available。

 only if a buffer is available so that you can put the instruction base， otherwise you stop。😡。

While in reservation station， each instruction watches a data called common Data bus where the tag of its sources。

 when tag is seen it grabs the value for the source and keeps it in the reservation station when both opera are available instructions ready to be dispatched I think I've kind of said this before you dispatch the instruction to the function unit when instruction is ready and after the instruction finishes in the function unit。

 there needs to be some arbitration for this common database。

 we will see that orient to multiple common databasees as I will show you。

The instruction puts the tagged value onto the common database， it' called a taggged broadcast。😡。

Register file is connected to the common database bus as well as reservational stations and register contains a tag and they the latest writer to the register as we have seen if the tag in the register file matches the broadcast tag。

 we write the broadcast value into the register and set the value。😊。

And then eventually rename tag needs to be removed so that some other instruction can get allocated to the reservation station。

 Okay， so this is one quick overview of the algorithm that we're going to look at。😡。



![](img/d75a2d2d05bae1ba71eef0f24a7544ab_20.png)

So if we're going to do the exercise， we're going to execute this sort of algorithm on this code。

As you see as you can see this code as a multiply， and then it says an ad over here。

 this ad is dependent on the multiply because it's sourcing R3 and then it is a bunch of instructions that's independent of the ad。

 but there are depends internally between the instructions， for example。

 this last ad is dependent on this multiply。😊，We're going to assume the ad takes four cycles。

 execution， multiply takes， I think eight cycles， six cycles execution， sorry。😊。

If we're going to assume one adder and one multiplier。😡。

So if you actually need to do the calculation， a non pipeline machine， that takes 50 cycles。😊。

Non pipeline machine says you have four ad instructions and two multi instructions。

 each of them takes， let's say seven cycles versus 11 cycles and it's 50 cycles that's an approximation basically because you can actually make the non pipeline machine nicer without the clock cycle without the clock boundaries but。

With this assumption， it takes 50 cycles， we're going to look at an in order dispatch pipeline machine with imprecise exceptions。

 no forwarding and forwarding， and then we're going to simulate an out of order dispatch pipeline machine with imprecise exceptions。

😡，No reorder buffer， as we said， we're going to use forwarding。Okay so let's take a look。

 this is an in order dispatch pipeline machine without forwarding so you can see that this is the first multiply the second ad is dependent。

 so without forwarding it needs to wait for the previous value to be written into the register file and then it gets decoded as you can see so if you actually go through this yourself which you could it takes about 31 cycles。

😊，So basically in order thispat pipeline machine without forwarding is much nicer。

 let's say than the nine pipeline machine， right， 50 cycles worth 31 cycles， this is cycle count。😡。

Clock cycle is a totally different issue。 I'm assuming that they're all equal for now。Now。

 if you actually do add forwarding to it， this instruction can start executing after the value is forwarded from the prior pipeline stage。

 depending on some forwarding rules， if you will， and you can actually reduce it to 25 cycle。

I'm not going to go through these， but you can actually do these with calculations yourself。

 and we actually have a lot of exercises similar to this。So can we do better basically。

 can we actually reduce this 25 cycles， this is what we have built so far。

 can we reduce this 25 cycles further？😡，And the answer is yes， basically if you use auto order。

 dispatch auto word execution， it's going to look like this。

 so basically this instruction is going to wait over here。

 but this next instruction can be dispatched and executed。😡，While this prior instruction is waiting。

 so if you'd auto order dispatch pipeline machine with forwarding， we will get down to 20 cycles。😡。

This picture is actually a little bit slightly misleading because you don't really need the right backstage actually。

 so it's actually 19 cycles if you have this imprecise if you're going to use what I'm going to describe you don't really need that so it's about 19 to 20 cycles which is not bad。

😡，So the key difference is going to be here， independent instructions weight， as you can see。😡。

But here the independent instructions can execute， okay， so let's see how this works。😡。

Now in prior times I would use the blackboard but now we have a nice animation over here。

 so we're not going to use the blackboard we're going to use the animation so this is going to be our first auto order machine simulation now let's first set up the stage so this is our register file initially we're going to call it the register A least table you can see that all values are valid and the values are the same as the register numbers if you will or now just for fun this is the program we will simulate which is exactly the same as what I showed you over here it's in a different slightly different font。

😊，And these are the reservation stations， so these are things that I've not introduced so far。

 but let me introduce them， so this is we're going to assume one adder and one multiplier。😡。

We're going to assume theyre pipeline， so you can start one instruction every cycle in the adder and multiplier and the principle of pipeing applies to functional units also。

😡，If you start one instruction in one cycle， if the add is， for example。

 pipeline over four clock cycles， you can start the next instruction in the next clock cycle and they could be executing in a pipeline adder。

DonWe didn't talk about how to pipeline ladder， but the principles are very。

 very similar to pipelineing an instruction processing engine。😡，So okay。

 so this is the reservation station for the ad units。

 which we're going to assume two sources for a clearly。

 these are different reservation station entry numbers， AB，CD。

 and each reservation station entry has for each source a valid bit is the source ready。😊，Attack。

If the source is not ready， who will be producing it。

 which tag will be broadcast and which tag should I be looking for？😡。

And the value if the source is actually ready right for and you have two sources you know so you have value valids tag and value fields for each source。

 so if you look at this is very similar to the register file， right？

So basically register files store some values here we actually copy those values over here and wait for values that are not available yet。

 and we're going to do exactly that。😡，And that's true for the multiply unit it also。

You have valid tag and value for source one， valid tag and value for source two。

And when an instruction starts executing in the adding adder units。

 we take the value two values that are better be ready for execution。

And then we actually take the destination tag that we're going to produce。 so for example。

 if this instruction over here starts executing， we're going to broadcast tag A。Saying that， oh。

 this is the value the instruction at Re station entry A is going to produce and anybody who's waiting for a is going to capture that value。

Does that make sense so we're going to rename these registers to reservation station entries that are holding the instructions that are going to produce the values of those registers that's the idea very similar to the reorderable for except this is the reservation station。

😡，That's true for over here。 also you can see basically add and multiple execution units have separate tag and value buses。

 So we're going to be able to broadcast。One tag and one value per cycle from this unit and one tag and one value from this unit as well。

😡，And you will see that it's going to be a mess because。These tags， when they're broadcast， need to。

 let's say， follow my what is this cursor need to be going to。These tags。

 you need to be comparing this。And then you need to be comparing these tags to the broadcast tag and then these tags to the broadcast tag。

 and then these tags to the broadcast tag and these tags to the broadcast tag。

So if there's any instruction waiting for the tag you're broadcasting and if it's not valid。😡。

Then it's itd better capture the value that's also being broadcast。

 so values are also going to be broadcast this way， so there' will be long buses。😡。

That are going to go over the entire machine。 And you will see this soon。And that's the cost。

 it's expensive， actually。And if you're doing two broadcasts per cycle。

You don't have only one set of buses like this， you have two sets of buses。In existing machines。

 there are more than eight，10 functional units。So if we do these broadcasts every cycle。

 eight or 1 instructions， let's say， potentially。😡。

So existing machines are much more complicated than what we're going to simulateim。

 but these exist basically， you can see how existing machines are so powerful。😡，Okay。

 is this all good now？I' have not started the simulationim yet， I've just set up the stage。😡，Okay。

 initially reservation stations are invalid， so I don't show the invalid bits for the reservation stations。

 but there needs to be a separate allocation mechanism for reservation stations。

 which reservation station entry is free or not， I'm not showing that over here。

We're just because we're not going to actually deal with that in this particular case。

 we have a small program that fits in the reservation stations right now。Okay。

 so this is this setup of the stage， any questions？Now we're going to simulate， this is cycle zero。

 clearly the no instruction has been decoded。😡，Let's fetch the first instruction in cycle one。

 we fetch this multi instruction， nothing interesting really happens because we just fetch the instruction right。

The interesting thing happens when we decode that instruction。

 right Now we're going to decode this multiply。😡，Now what does decode mean we've already gone through the algorithm。

 let's go through the steps， multiply gets decoded and allocated in the reservation station x yx because this is a multiply reservation station and this is a multiply so that's the function of a decoder and x happens to be free so let's allocate it over there now what does that mean。

😡，So okay。We basically need to check if the reservation station is available。 in this case。

 we assume it's available。 Yes， that's good。 So if we allocate multiply there。

 The second step is we access the Reg table to get the sources。The exit with the first source R one。

R1 is valid， that's good， so if we can trust the value tag doesn't matter because it's valid， right？

Looks nice， right， We basically copy the value bit saying that the source is ready and the value is one tag is we don't care again。

 it could be any garbage value doesn't matter。re going we're not going to check it basically。

We do the same thing for the second source。So okay。

 before I said that step three is put the source register into the reservation station X right I just showed you showed this to you for the first source。

 but we do exactly the same thing with the second source， it's valid， the value is true。

So we basically copy the register file entry or register Atable entry to the source two over here sounds good。

Now。We also need to rename the destination register， which is r3 to x， just like we did yesterday。😡。

Basically， Rt is not valid anymore because multiply is going to produce the value of r3 and anyone who wants the source。

 who wants to get the value of R3 better capture the tag X when it's broadcast。😡。

That's what this means basically so anyone who's going to read r3 now is going to get x as attack tag so basically this is r3 is not renamed to x its new value will be produced by the reservation station that's identified by tag X。

😡，And anybody who's going to consume that value is going to refer to that as x。

 and we'll see that way soon。😡，Okay， that sounds good now the other realization here is that multiply in the reservation station X is ready to execute in the next cycle because both of its source are already ready right so there needs to be some other logic that detects this this is called the scheduling or readiness detection or instruction wake up logic again I'm not showing you but there needs to be some other logic to detect whether who which instructions both source are ready and which one should be selected out of them okay。

😡，Okay， so that was cycle two， which was a little bit more painful than cycle one， as you can see。😊。

PCycle8 will be the most painful for us as we will see soon。

 so cycle three we figured out that multiply can execute that logic that I mentioned figured out that this multiply can execute let's start executing it multiply and reservation station x start executing。

😊，Basically， you need to check the readiness wall source already。

 you need to wake up the instruction， there needs to be some logic that does that。

 and then you supply the values and the tag it's going to produce， which is going to be X， right？😡。

So this multiply is going to take six cycles because it's ready。

 it'll be dispatched to the multiply units， but after six cycles it's going to produce the value as well as the broadcast attack everywhere as we will see and that's going to be cycle8 I think。

😡，Okay， so concurrently。In the decocode stage， we're going to decode the second add instruction。

 Let's say look at how that happens。 Add gets decoed and allocated into reservation station A because it happens to be free。

 as you can see decoding is very similar。 So add sources are3 as its first source You take valid bit is0 it's not ready yet tag is X value I don't care。

 Basically this means that。I'm waiting for the instruction that's producing it which is in reservation station X right this source is not ready but Re St X is going to produce it and when it pursues it it's going to broadcast the tag and the value and I'd better capture that okay the second source is let's say net that went very fast the second source is our4 it's very similar to earlier cases basically it's valid the value for but this ad cannot execute because one of its sources not ready so it's going wait。

😡，Basically， we do the same steps for1，2，4 in the prior slide for add and we rename also our five to8。

So now R5 is going to be produced by the instruction that's in Re station A。

 which happens to be this a。😡，Okay now anyone who's going to source our5 later on。

 which you will see this one of these instructions， I think this one。

 it's going to refer to value a or tag A。Okay。So adding in Real station A cannot execute in the next cycle because one source is not valid。

Sounds good， It's fine。Now let's take a look at the interesting case over here in cycle four。

 this multiply here is happily executing adding in reservation station A has to wait because one source is not valid。

😡，Now we can decode。The next act， let's take a look at what happens。Decodeote again。

 we take the first source register， register two。It's valid and the values two。

 we take the second source register， which is register6， it's valid。And the value is6。

 now this can execute， right？It doesn't matter whether the previous instruction couldn't execute。

 it got out of the way。That's the good one， good part。

Now we also need to rename while we're decoding this a instruction。

 rename the destination register R 7 and we even name it to B because we allocated as a reservation station B for it okay so this register register7 is in weld and it's renamed to B now add in this reservation station B is ready to execute in the next cycle and then wakeup logic determines this。

😊，And we will see that it's going to start execute， it will start executing out of order。

 or it'll be dispatched out of order through this functional unit earlier than a prior instruction。😡。

ok。😊，I'm ignoring the fetches because in the fetch state you don't do anything useful's useful for this for the purpose of this picture okay now let's go to cycle5 in cycle5 multiply is still happily executing over here this first ad is still waiting now the good thing is the second ad we're able to execute it and that's the big benefit of automotive of execution right now this was not possible in our earlier pipeline designs here the wakeup logic determines that this ad in the reservation station is ready because both of its source already ready one source is two the other source is six after four cycles it's going to broadcast its taggged B and the value that's going to compute after four cycles。

😊，Okay， and whoever is waiting for B， this one， for example， is going to capture that value。😊，Okay。

We're going to see that。And then we the next instruction。

 I'm going to go through this relatively quickly because the process is very similar。

 You can see that the next instruction sources R8 and R9。😡，Okay， and yeah。

 we went through it very quickly as you can see， we basically take the register file。

 register table entryR8 and R9， they both happen to be valid and the values are eight to nine。

 so this instruction in reservation station C is ready to execute in the next cycle also that's also independent basically of prior instructions。

😊，So that's good In cycle6， this multiply S executing still because multiplication takes long。

 This ad is waiting。 The second ad is executing because it's start executing out of order and now this third ad can also start executing That's the good part again。

 right this is enabled by out of order execution again this third ad starts executing again we don't show that over here because you can guess So the reason it can start executing is multiple one is out of order execution machinery that we added and the second is add is pipeline。

😊，Because the previous ad is in the moves to the second stage of the pipeline adder and the second ad moves to the first stage in the pipeline adder。

 okay so there's pipeing happening Adderal alternative is providing a second adder of course。

 right like we have done in the earlier parts of pipelineing if you remember with the dryer right？😡。

Okay so we decode this multiply， this multiply is interesting because neither of its sources are ready。

 so if you index the register file R7， it's not valid。

 but it's going to be produced by B tag B and R 10 is not valid but it's going to produce by C so neither of its sources are well so you cannot actually start executing it and we rename r 11 to y because that's the reservation station entry that's going to produce that value so it's0 y so you can see that the register file is a lot of invalid values right now because we actually put a lot of instructions that are going to write to different registers into the reservation station and they have not produced those values yet。

😡，Okay， cycle6 is done now cycle 7， let's take a look at it quickly multiply is executing ad is waiting。

 the next ad is executing， the next ad is also executing the next multiply cannot start execution because it's not radiant as you can see to00 and then the next ad is decod if you look at this next ad it sources r5 r5 is invalid and the tag is d。

😊，Wait a second no， no no sorry Okay， something interesting happens here I should I should have animated nicely when it sources r5 r5 is invalid and it's going to be produced by a right so we actually put it over here and then R 11 is invalid and it's going to be produced by y so this is going to be0 y。

😊，And we need to rename our5s， so it's reading our five old value of our5。

 and it's going to produce a new value of our five。😡。

So it's going to read the value from produced by a for r5。

 it's going to produce a new value for R5 coming from reservation station and3D。Okay。

 so interesting thing happened to R5 basically。Okay。

 so nobody will get the wrong value over here because we're always updating or renaming the registers in program order。

😡，So also at this point， all six instructions are decod and renamed as you can see。

 not what happened to R5， it was renamed twice first it was renamed to a。😡，Which is here。

 which happens to be this instruction that's producing one value， one definition of R5。

And then it was renamed at the end by this instruction to D。Okay。😊。

So all of the instructions that are in between these two renaming of R5 are going to get the first definition of R5 because they're referring to A right。

 because they were renamed using this definition of R5。😡。

All of the instructions that are going to source R5 after this ad are going to get the value from D。

 okay？😡，Okay， but we don't have such instructions because we're done with the instructions right now。

 let's take a look at cycleite so cycle8 is the fun part because some instructions are completing right now。

😊，So in cycle 8， multiply in RSx is done， or we're going to assume it's going to broadcast this tag in this particular cycle。

 that's the assumption over here， it could be a different assumption in some other machine。

 but basically this multiply is done its value the result is2 because it's multiplying1 times 2 and it's going to broadcast that value as well as the tag now let's see what happens with the broadcast of the tag x。

😊，So x is going to be broadcast to all of the fields that have taggged in them。😡，Now we're animating。

 you can see。Some of them are actually capturing X， right？

So whoever is waiting for x is highlighted over here with yellow this Reg3 is waiting for x because it's going to be we after that。

 it's imet and the tag is x， this instruction is waiting for x because it was renamed that way。😡。

And it's going to capture the value。Now the value also broadcast concurrently。

 this happens concurrently actually， but I'm showing it serially because we have bandwidth problems。

 let's say our animation problems。😡，So we broadcast multiplies results and anybody who was waiting for x captures the value too。

😡，Okay， so basically that's how we communicated the value by broadcasting the tag and value concurrently。

😡，Any location in the machine that had a valid that was invalid and waiting for that tag captures the valid。

Okay， so register 3 became two and valid and this source one in reservation station entry a became two value became2 and valid。

😡，And now this。This entry， this ad in Re station A is ready to execute the next cycle， right？😊。

There's some logic that determines that that's the wake up logic so that's beautiful this is how we communicate the value。

 thiss also how we communicate the dependence so if we're communicating two things at the same time dependence dependence instruction you can execute and the value here's your value。

😡，Okay。😊，But that's subtle。Unfortunately it also happens that a in reservation station B is also done here because of the length of the instructions。

 basically it also needs to broadcast and it needs to use separate tag and value buses to do the broadcast so this is the ad that we're talking about it's adding two and six as you can see after four cycle is done the values8 and it's going to broadcast this tag B same thing。

😊，B gets broadcast to all of the locations。That have the name tag there and if it's invalid。

 it becomes valid soon after the value gets in。😡，So it turns out that instruction is also waiting for B over here。

😡，But basically， you have to broadcast it everywhere that may be potentially waiting for the attack。

😡，Now you can see the logic complexity and the wiring complexity。

 right these wires need to run around everywhere and the logic that comparison that I kind of show is really a comparator。

😡，And we've seen that compar to， equality checker， essentially in lecture combinational logic。😊，Okay。

 so we also broadcasted value， of course， and everybody who was waiting for tag B captures the value8。

😡，Now that looks good， our Reg seven becomes eight。This instruction。

 one of its sources becomes valid， but unfortunately the second source is still invalid invalid so it cannot execute so it needs to wait for the second source okay。

😡，Okay， so nothing else that's interesting happens in a cycle 8。

 let's say the other instructions is executing， multiply the other instructions are still waiting。

 okay， cycle nine。😊，This write back doesn't necessarily need it basically because we actually already wrote back the results of multiply which was actually updating what did we update sorry we updated Reg3 right yes register3 so this write back is not strictly necessary but in a reorder buffer maze machine you need to actually put it in the reorder buffer somehow but that could also happen in the prior cycle but I'll keep it for complete list for now so if you may have questions about this right back keep it for completeness over there。

So this new the second instruction starts executing right now because both of its sources became valid right。

😡，So it gets sent into the are you functioning it。And this next instruction also does right back。

 This instruction finishes and it broadcasts and updates it broadcasts。😊，Yeah。

 I think I don't animate these further because it actually takes a long time to animate everything。

 but this instruction if you remember it was actually this instruction in Re station C。

 it broadcast Tax C so everywhere with tax C captures value 8 plus9 which is 17 so this will become 17 and this will also become 17 in this cycle and it does。

😊，That's good。And then this like stillating， still waiting。

 so multiplying RSY is not ready to execute the next cycle right because both of its sources are ready over here and the wakeup logic determines that。

😊，Okay， now you can keep the animation going further and further。

 You can see that instructions are still executing and when an instruction finishes。

 it broadcasts its tag and value and updates things So this was this ad over here right well。

 I guess this was。😊，The ad that's doing r3 plus r4 r5 which is this one it broadcasts the tag A and everybody who's waiting for a gets the value and is still not ready to execute as you can see that instruction over here okay so I'll go through this relatively quickly at this point。

 but basically when an instruction finishes it broadcastes tag and value and anybody who's waiting for the tag and value gets that updated and checks for readiness in the next cycle。

And for example， here in the cycle 15， this multiply becomes finally broadcasts tagged y and the value 136 and everybody who's waiting for y and 136 captures it。

 and now this instruction becomes ready to execute over here which happens to be this instruction。

And if you actually follow its execution， eventually it broadcasts tag in cycle 19 and tag is D and the value is 142 and now at the end of the execution of all of these instructions。

 all of these are valid as you can see。😊，Because we're done with the program， this toy program。

 and all of these should be delocated， but we didn't show the deallocation of the reservation stations。

Does this make sense？So that's the beautiful part and if you don't ignore the rights over here it's 20 cycles as promised okay。

 so now you know how whatever execution works right it's not that complicated once you understand the concepts of renaming and value and dependence communication。

😡，Let me handle some questions here and then we're going to take a break actually we should probably take a break。

 but let me cover these questions very quickly so what is needed in hardware to perform tag broadcast custom and value capture basically you need to make a value valid and wake up an instruction for this you need wires comparison on logic basically a lot of hardware and this expensive hardware。

😡，Does the tag have to be the idea of the reservation station entry？Basically。

 I said that this is not necessary as long as you can link the producer to the consumer with a。

Correct and common tag that's fine it could be the reor entry actually actually over here you just need to connect the producers to the consumerss accurate in this case we happen to use the reservation station MP。

 but it could be any unique name that enables linking of the producer to the consumer it doesn't need to be even anything specific to the hardware specific to any buffer it could be some namespace basically that you happen to allocate and decate。

😡，What can potentially become the critical path well this is actually what people have optimized over years and years tag broadcast。

 you broadcast the tag， somebody needs to capture the value and they need to wake up that loop is actually very long。

😊，Because the wires go through essentially the entire machine internally and there are competitorsators all over the place。

 and then you need to actually also determine the wake up so this is also called a wake up tag broadcast wake up and select logic and this is one of the most critical parts of the machine internally。

😡，How can you reduce the potential critical paths， more pipeing and prediction？

And existing machines do all of this basically existing machines are very sophisticated。

 they sometimes even predict which instruction is going to broadcast this tech。😡。

And the reason they do it is because they for example， loads， we didn't discuss loads over here。

 but how do you decide when a load is going to broadcast this tech going to hit the cash is going to hit in the first double cache iss going to missing in the first double cache。

 so it actually complicates the scheduling logic significantly。O。So basically， this is our example。

 you can draw the data flow graph of this Ebo code clearly， right？😊。

But when we come back from the break， I'm going to give you just this picture。😡。

We actually constructed this picture， this is in cycle 7 at the end of cycle  seven。

 we have exactly this picture earlier when we actually done the simulation by just looking at this。😊。

You can construct the data flow graph。And you can start thinking about how during your 10 minutes of break。

 you can also provide the executing code in sequential order。

 so we're going to start doing that after the break。😊，And in the end。

 we'll have something like the space。Okay so let's take a break until 1520 well no 1530 1520 would be less than one minute。

 1530 and then we'll be back construct related to reservation station thelocation so let me cover that first so in this example that we went through the machine simulation I did not show you how the reservation stations are delocated。

😊，But they have to be delocated at some point， and it makes sense to delocate them when an instruction has broadcast its tag and value。

 it doesn't make sense to use them afterwards so you can delocate them at that point。

Unless that was done speculatively and modern machines actually done speculatively。

 so they really need to keep the reservation stations for longer than that。

 but we didn't deal with that， but you need to decate the reservation station so that incoming instructions can be allocated into the reservation stations because if an incoming instruction that's being decoded cannot be allocate a reservation station until you need to install the pipeline。

 right？So the size of the reservation stations and how you manage that is important for performance in the end。

😡，You can think of the size of the reservation stage as how many instruction can you buffer before you stall。

 right？😡，If the size of the reservation stage is actually 2000， for example。

 you can buffer 2000 instructions before you can stall。

So the longer this is the larger the reservation stations are， the larger your latency tolerance is。

 so it's actually important and people are trying to increase the size of the reservation stations today。

😊，In modern machines are actually much larger， but the real the reservation stations that are most critical are load and store reservation stations。

 which we don't deal with here， but you can watch the optional premiere lecture about that。

 which will give you an idea of how complex the load and store reservation stations are。😡。

You need to deal with addresses， for example， in load and store， which we don't deal with over here。

 we deal with registers， just dealing with register is a lot easier than dealing with large memory addresses。

😡，For multiple reasons， if you watch the lecture， you will see because registers are statically determined。

 but the address of an instruction， address of a load instruction is determined dynamics。😡。

Remember the base plus register calculation， you determine the address dynamically so you don't know which instructions are dependent。

😡，On that instruction， right here we know exactly what the registers， it's beautiful。

 but with memory， it becomes very， very messy。😊，Okay， I'll leave it at that for now。

 so we handle these questions， so as I promised， so if I give you this code。

 you should be able to draw the data flow graph， that's a forward problem。😡，I'm not going to do that。

But I'm going to do it in a reverse way， basically this was the state of the Reg A table and reservation station in cycle7 in our simulateimild program。

 and if somebody gave this to you and asked what code is in the machine right now？😊。

You could actually draw the data flow graph and that's what we're going to try to do right now very quickly I have the answer in the next slide but I'll do it over here quickly so that you can see and these are actually good problems also for exam if you will。

 I know you're not studying for the exam just for the exam but these reverse engineering problems are actually a good way of testing understanding of the concepts because you really need to understand how the machine works I think to figure this out。

😊，Okay， so let's try to switch。So this is basically cycle seven。Just to remind you。

 this is our cycle seven。And now we're going to draw the data flow graph of this thing。Let me see。

 I have lots of colors and low colors。I start with pink or purple pink。Okay， so how do we do this？

It's actually pretty easy but。😊，Okay， can you see that Okay。

 I can fit two things we're going to do this。So what is a data flow graph data flow graph is a bunch of nodes right。

 so first of all， if by looking at this picture， you know that there are one， two， three， four， five。

 six instructions in the machine right。😊，We're assuming that theyre just somebody needs to tell you that they're just decod。

 but not they're just recoded and renamed， but nobody start execution or something like that basically。

So all of the instructions are we need， so if we have six data flow notes somehow， let me draw those。

 I don't know， maybe color code them。😡，Okay， I don't want to do the color codinging right now because they're going to be connected in different ways and you can start anywhere actually because in the end this is data flow actually let me start with I don't know。

 let's start with this ad this poor ad， so this is the pinky instruction。😊，That refers to this。

 So what do I know about this instruction， source one is tag X。 I don't know the register number yet。

But I have a pretty good idea that this could be the register number。it' probably is。

And source two is。Vals and values for。I know where it's coming from。

But I may have a good idea that it may be coming from here， right， register four。走。

Does that make sense？Maybe I should just say that there's a good idea。

 maybe this is Reg four and maybe this is Reg three。I'm probably right。

So somebody is going to produce X right so this ad cannot be the first instruction that's executed assuming the machine is correct。

 so let me go to X step。😡，Maybe I started in their wrong place。

 I don't like this color because it's too similar。Okay， let me go to X。

So I should also say that I should not should this is an ad right， What do I know about this。

 is's an ad and it's going to produce a。And what's it。嗯。

It's going to produce something who' it's going to produce a tag that's not in the register file so somebody overwrote the register that this is writing right so I know a lot of information as you can see just by looking at this reservation station entry。

And now that tells me also to look at this reservation station entry because it's going to be the input of this instruction that's in this reservation station is going to be produced by this reservation station and let's take a look at that it's going to produce X。

😊，And I know that the x is going to get connected over here， that's good。

And one of the inputs is one。And the other input is two。 and they're both ready。 That's good。

 And I kind of have a suspicion。By looking at the register file that they may be actually R1 and R2。

 right， maybe the R one。Maybe the star two， right because there's no other one or two value over here。

 right？😡，It's constructed that way。Okay。😊，So now I know these data flow notes， the sum multiplies。

 okay？😡，Now， who am I going to go next？路。What should we do， should we do this one。

 this looks interesting， I think。Let's do another at。Because both of the sources are ready， actually。

 So let's put this ad somewhere over here。 again， I don't know much。 I'm not thinking that much。

 One source is 2。 It's ready。 The other source is 6。 It's ready。

 How do I know thats these valid bits， right。And again， I have a suspicion that， oh。

 this could be R2， this could be R6。What do you think？And it's going to produce。B。😡，And B。

 probably going， it's renamed R7。In to be right， I'm going to do that。 Let's see。

 let's keep the question mark。 You can validate the question marks later， right， Okay。

 so this looks like this is independent of all of these over here。 Okay。

 let's go to another instruction。Another color。Thanks for getting this because this is a lot of nice colors。

Okay， another color what should I start with， I want to start I don't even do this one because I know that both in both inputs are valid right So this is another one。

 This is another ad， as you can see。And then this ad， can you see that， okay， barely？

This ad has eight over here as one input it's ready， nine over here as another input it's ready。

 and again I have a suspicion that this could be R8 and R9。😊，R nine， okay。

 and it's going to produce the tax C。And the C is probably our 10。Okay， that sounds good also。Okay。

 now let's go to something else。Let's go to this multiply Can you still see everything I don't like this color again。

Even with all of these colors， as you can see， we're running into。

Color collision or maybe it's because my the grand larity of my eye in determining colors is not very good okay。

 we can push this up。Okay， now we're going to try to figure out about that instruction。

 this is a multiply for sure， one of them is B， the other is C。Oh。

 look at that this B can come over here。And this see。Can come over here。

 it's kind of a messy data flow graph， but it's a data flow graph， right？😊。

And both of them are not ready and what are they are  seven and are 10 probably right and we already kind of guessed that are seven。

A 10 now it's getting more solidified， if you will。 Now， let's take a look at the last one。Last one。

 last one， orange。Last instruction is this。第。😊，And。What is that is an ad， where should I situate it？

嗯。A and Y， who's producing Y Oh oh， I forgot something in the previous one， sorry， that's why。

So is also this is producing Y， which is if you look at the tags over here， R 11， right？Okay。

 now the last one I kind of have a guess it's going to get a and y a is being produced by this one y is being produced by this one。

 it's a add instruction。So it's going to get connected like this。That's the beauty of colors。

 You don't。Overlas the lines， right。 So this is a， Y and the Alpatus。B。Which is R5。O。😊。

So now we actually have a data flow graph， this is the full data flow graph of the program that is in the machine。

😊，It makes sense， right？And I just grew the state of flow graph by looking at stuff。

 I didn't even think about it right I started with some with the second instruction actually I didn't start with the first instruction that's in the program now you can start reordering these instructions and find the instruction sequence and you can verify verify which registers but eventually you'll come up with this thing but basically the first instructions is multiply multiply r1 r2 and the result goes to x x is r3 we forgot that kind of but you can also verify from here r3 and the next instruction maybe be this one although we're not sure because this instruction is completely independent right？

😊，So this instruction can be anywhere， so if we don't know the complete instruction ordering over here。

 but we can guess some orderings。😡，So clearly this is before this one and this is before this one。

And this is before this one， and this is before this one， and this is before this one。

Right so based on the dependencies， you know the ordering。

 but you don't know the complete ordering of the instructions。 Again。

 I don't want to go through this and come up with all of the instructions since I want to cover other stuff。

 but you can basically write to all of the instructions that we have over here。 Let's do that。

 This is multiply we accounted for。 And then this， what is this This an add。😡，Are two， are six。Oh no。

 this R two is not correct， so you're got to be careful of that one， right？😊，呃。Yeah。

 actually it it's correct I think yeah add our2 r6 r7 yeah sorry it's correct。

 but maybe the ordering is not correct as we discussed and this ad is let's see I should have color coded these but sorry and this ad is over here add R3 R4 and the result is a what is a so that's the part we don't know。

😊，How do you figure that out？I'll let you figure that out。So somebody got renamed。

And tag A is kind of lost。I need to figure that out somehow， what is this。

 what register does this correspond， I'll let you think about that。

But basically there's something over here， okay？And then you need to actually go through these instructions。

 this is add R8， R7。R 8 r9 and the result is our 1 over here we accounted for this one did we account for this one yeah we account for this one except this nation and then this one is this a multiply another multiply I don't know if you're seeing this I think you're seeing it but。

Does the multily， what are you multiplying R7？Yes， and then our 10 over here yes。

 and then the results is our 11 so it's going to be very similar to what we find out and then the final ones over here this is。

呃。Wait a second。This is an ad。One of the inputs says a， I'll keep it as a。A。

 and then the other input is y， which is R 11。And then the result is our5， okay？

So then the question is， what could A be？Can you figure out it's star5？Anybody？

Remember that our five got renamed twice because we actually simulateimatedd this before。

And actually， you should be able to figure out that it's R5 why because all of the other instructions。

Have produced their values and they're being used， but this is overwriting some value。

 it must be reading actually the same value that it's overwriting。

So you need to do this by process of elimination。Does that make sense？Okay。😊，Okay。

 I'll let you figure that out。 But this is your data flow graph。 and unfortunately。

 not the perfect ordering because our real ordering was。This one， right。

So I couldn't really decide the ordering of this instruction because this is the data flow graph。

Right。Yeah， now this also proves that。This machine is a data flow machine internally。Internally。

 what we have is a data flow machine executing a data flow graph。😊，O。😊，Hopefully this was clear。

 can you can actually do this on your own， and I would recommend doing that on your own。

But now we'll have to move any questions Okay so now we've constructed the data flow graph。

 this is a much nicer version of that data flow graph， let's say maybe not as colorful。

 but what we've done is we reverse reverse engineered the data flow graph of the executing code sometimes not perfect。

😊，Because we cannot reorder the instructions exactly as I showed you I got the reordering wrong between these two instructions because there's no dependence relationship between them I cannot figure out that relationship unless somebody tells me some other information right okay so basically there are a bunch of other questions over here we discussed one of these how is the reservation station entity allocated。

😊，Should the reservation stations be dedicated to each functional unit or global across functional units that's another question basically and this is actually interesting because this goes into should a buffer be centralized or should it be distributed and there are tradeoffs related to this if it's centralized it's a huge buffer everybody goes through it。

 the dynamic utilization of the buffer may be good。😊，But if it's distributed。

It's just now each of them are smaller buffers so actually the latencies may be easier to handle。

 energy may be lower， but now and also you can specialize the buffer to the functional units。

 for example， load instruction require addresses a instructions don't require addresses right so you don't need to store the address inside the buffer for ad reservation so you can specialize but unfortunately when you have distributed buffers the load balance becomes a problem so everything you're executing the machine as ad instructions you may not have enough ad reservation station right because you've distributed the buffers across the functional units so there are tradeoffs over here。

😡，Another question is， should reservation stations in order buffer store data values or should there be a centralized physical register file where all data values are stored？

This is a loaded question because we're going to build up to this actually。

 so values are going to become problematic as we will see。😊，Timing is also problematic。

 I'm not going to deal with timing exact when as an instruction broadcast is tagged。

 when do you know this information？😡，When should you broadcast the tag and when should you broadcast the value。

 should these be done concurrently or in a serial manner， so there are many。

 many design choices that we're not going to tackle over here。

 but existing machines actually tackle in very， very interesting and nice ways。

 there are a lot of tricks you play to make this more efficient more lower latency and less costly。😡。

But again， we don't have time and this is the first course you're taking on the topic。Okay。

 basically we did this exercise that's great。 Hopefully you can do it on your own and I would recommend that an exercise for you to do the same exercise with precise exceptions。

 It's not going to be that different frankly， you need to add every orderder buffer stage into。😊。

The pipeline， but it's not going to be that different。

 it's not going to change the timing that much also。😡。

But let me talk about Autoward execution with precise exceptions， what does it require？😡。

So the idea is very similar， use a reorder buffer to reorder instructions before committing them to the architectural state。

 just like we did yesterday。😡，Yesterday we added this machinery to a multicycle execute pipeline machine in order dispatch here we have auto order dispatch with the reservation stations。

 right？😊，So an instruction updates the Reg El table when it completes execution。😡。

This is also called a frontend register file so I'm going to describe something to you that is slightly different that is employed in all processors today almost all processors so basically an instruction updates the Reg Alias table where it completes execution this basically says that where can the prior instructions get the value from this is called a frontend register file and we will see this with an example。

😡，An instruction updates a separate architectural register file into tires。

 when it actually is the oldest instruction and finishes without exceptions。😡，As I said earlier。

 in other words， the architectural register file is always updated in program mode。

 so there are two register files， front end register file architectural register file and frontend register files updated when you actually broadcast your tag。

😡，And the architectural register file is updated in program order from the reorder buffer， okay？😡。

On an exception， we flush the pipeline， copy the architectural register file into the front that register file。

 so that's the beauty of having two register files front end register files used for renaming。😡。

Backend or architectural register file， Intel calls that the retirement register file is used only for updating the architectural state in order when the oldest instruction finishes execution okay and whenever whenever there's an exception。

 you need to synchronize the architectural register file with the front end register file。

 front end register file is speculative because lots of instructions in the machine。

 but you're flushing the machine。😡，So basically take the architectural content of the register file and put it into the front end。

 so it's a very simple copy plus the flush of the machine， of course， right？😡，Okay。

 so basically this is our initial auto of order machine we did not have a orderder buffer。

 we're going to add a frontend register file used for renaming and then reorder buffer just like we did yesterday and then architectural register file you can see that the frontend register file has valid bits and values。

 architectural register files doesn't have any valid bits because it's always valid everything over there is always valid it's just updated when the program finishes or retires instructions。

😊，Okay。Does that make sense？Okay so this is really the auto order machine with precise exceptions。

 you need to have reservation stations for scheduling。

 you need to have a front end register file for renaming。

 you need to have a reorder buffer to update the architectural register state in program order any have an architectural register file to keep the architectural register values。

😊，Again， to make sure that we are on the same page， architectural register files architectural state。

 it's updated when an oldest instruction retires。Front end register file is。The front end state。

 the state that is seen by decoded instructions， when an instruction is decoded。

 it's renamed using the front end register file because there are lots of instruction in the machine that are potentially updating the registers。

 right？😡，Architecture register state what's visible to the programmer。

 the programmer can inspect this one， but they cannot inspect this one。😡，Okay。😊，Okay。

 so that's basically this picture in a lower level detail， if you will。😊。

And that's the camel that I like showing you。Okay， so there are many。

 many interesting questions over here。 You can optimize this a lot。

 but one question that's actually very bothersome is。

There's value applicationplication all over the place， so these are values。😡。

So you have values in the front end register file， you have values in the architectural register file。

😊，valuealues get replicated into the reservation stations， as you can see。

 whenever you actually rename an instruction， you copy the value tag and value into the reservation station or some other reservation station and then values also get replicated in the orderorder buffer because you need to take value that you're producing and put it into the reorder buffer so that you can later put it into the architectural file。

😡，So if the sizes of these structures are relatively large。This value application can be huge。

 actually。😡，So imagine reorder buffer on the order of thousand。

 let's say today we're marching toward there， imagine reservation stations on the order of  thousand also。

 so 2000 times 64 bit values。So in some cases， two of these values， as you can see， right。

 So 64 bit values are actually quite large。 So it's actually a huge amount of value replication。

 And imagine a worst case where。Every instruction is sourcing and writing to register three。😡。

But that's actually basically the same well maybe not writing to every instruction sourcing Reg three。

 let's say that's the same Reg three replicate all over the place right if no one's writing to Reg3。

 but everybody's sourcing Reg3， they're all replicated over here， right？😊。

So basically you're kind of wasting the values， so people have found out a solution to this by consolidating the values in a physical register file。

They can centralize the value storage。And everything else can all point us。😡，So for example。

 the front end register file， not file anymore， it doesn' have values front end register map。

Has the rename registers， this is how you rename the registers and pointers to the physical Reg file。

 register one points to physical Reg file 8。😊，That's how that's the latest definition of Reg one that you can get from an instruction that's in the pipeline。

Register 10 points to physical register file four， for example， okay。

 and the value is only here basically。That's true for the architectural register map also here。

 the architecturally registerister one is4 than physical Register 12。😊。

That's the architectural state of the machine architectural register7 is stored in physical register eab et cetera。

 and reorderable for entry also has reorderable for also has pointers。😡。

So this is how you can get rid of the values， values are only in the physical registers that are centralized。

😊，And everything else stores pointers to the physical register file。

Now this is also nice because this is your rename space now your rename space is the physical register file you can have a physical register file whose size is 1024 and those are the names you have for renaming the architectural registers too so a lot of machines work this way today because they don't want to replicate these values all over the place because values are expensive for multiple reasons right they take up space but they also consume a lot of power each value is 64 bits today。

 sometimes even larger and whenever you're broadcasting the value is huge tags are actually much smaller if you think about a tag if your name space rename space is 1024 registers。

😡，The size is only 10 bits， the value 64 bits， does it really make sense to broadcast all those values and make the system very energy and efficient right because every broadcast takes energy。

😡，Power also that's this is why this is really important and people actually get rid of the replicated values。

 So basically in the end， this is where we build up to modern out order execution with precise exceptions。

 Most modern processes use the following they have a order buffer to support in order retirement of instructions。

😡，They have a single register file called the physical Reg file to store all registers。😡。

Both speculative and architectural register， speculative meaning the value is going to be produced by instruction of the pipeline。

 but they may not be updating the architectural registeror because there might be an exception。

 right？😡，And later we'll see branch mis prediction， there might be a branch mis prediction also。

 potentially。Integer and fee registers are still separate。

 we've kind of been saying that also there are two register maps that store pointers to the physical register files just like I described there's a frontend register map that's also called a future register map that's used for renaming it's called for futureture because it's not really the architectural state that's updated it's future instructions are coming and renamed using that it's also called renamed register map。

😊，And then there's an architectural register map that's used for maintaining architectural or precise state。

😡，And this design avoids value application in reservation stations， reorder buffer， etc ceter。

And that's basically the design that we have seen over here。

So how does this actually impact the reservation stations。

 so let's say I didn't show you the reservation stations over here。

 but the reservation stations also don't have values anymore。If you look at this。

 this is the reservation station for a unit， multiply units， you add value and the physical Reg ID。😊。

Which means that you need to access the physical register。

register file before you access the functional unit actually。

 because what happens is whenever someone broadcasts a tag， they update the physical register file。

They don't with the value， they don't update。😡，The value over here because there is no storage of value over it。

 okay， we've just moved the value storage to the physical register file before an instruction gets dispatch is functioned。

 it needs to read the value from the register file。😡。

So this is how the pipeline changes at decode or rename。

 we allocate the destination physical register to a destination architectural register。😊，Again。

 at Tchodermin， we read and update the front end register map， okay， just like we did earlier。😡。

And then we wait， we put the instruction into the reservation station。

 it waits until both of its sources become valid。Before execution。

The instruction acts as the physical register file to get its source values。And then after execution。

 it accesses the physical register file to write its result values。

 it's still broadcast the destination physical register as attack。😊。

SoBut the value doesn't get broadcast， value just gets supplied to the physical register file。

 it doesn't get broadcast， what gets broadcast is this next is a physical Reg tag。

 which is much smaller as we discussed right？😡，Even if you have 2048 registers， that's only 20 bits。

😡，Getting to 64 bits is huge， right， You need to have two 64 registers。

 which is very difficult to have if you know that number。Okay， so at retirement。

 we update the architectural register map with a destination physical register if the instruction is oldest and it didn't cause any exceptions。

😡，Okay， and this is a modern processor， basically Pentium3 was like what we discussed yesterday。

 Ne or Pentium  in Intel。😡，Essentially is what we described right this is the frontend register map。

 front end rat as they call it， it points to some registers in the physical register file and this is the retirement rate or architectural or backhand register file。

 it points to some other physical registers。😊，They may be the same if the architectural register did not get renamed with an instruction that's producing a new value of that register。

 right？

![](img/d75a2d2d05bae1ba71eef0f24a7544ab_22.png)

So this is essentially the same picture that I showed you over here。Yeah。

 this picture except in a different way， and they have a orderderable for of course。

 to keep the status and do their re orderordering。

![](img/d75a2d2d05bae1ba71eef0f24a7544ab_24.png)

![](img/d75a2d2d05bae1ba71eef0f24a7544ab_25.png)

Does that make sense？So this is actually well this is Intel Pentium Pro so there was value replication Pentium Pro but that replication got eliminated in the Intel Pentium4 and most modern processors are like this let me quickly go over some things I' that we're going to conclude but basically these are the major concepts and out ofward execution we link the consumer of a value to the producer using register renaming this associates a tag with each data value we buffer the instructions until theyre ready this requires inserting instructions into the reservation stations after renaming。

😊。

![](img/d75a2d2d05bae1ba71eef0f24a7544ab_27.png)

Inside the reservation stations， we keep track of the readiness of source values of an instruction。

 which means that instructions broadcast the tag when the value is produced and instructions that are waiting in the reservation station compare their source tag to the broadcast tag if there's a match source value becomes ready。

 and when all source values of an instruction are ready you dispatch the instruction to the functional unit。

😊，What this means you wake up and select and schedule the instruction so I think we've kind of summarize these concepts these are nice I'm going to start with the later slides but I'm going to cover some things before I actually cover these slides I'm going to cover these next next time I'm going to ask you these questions later。

But let me actually show you some real designs so real designs are actually like this if you go through these designs。

 these are the reservation stations you can figure out these are the memory reservation stations。

 memory schedulers etc ce and there's a register file as you can see after you get scheduled you access the register file this is Intel Pentune4 and then you go to the functional units you can see how many functional units there are right even in something that's 22 years ago you get two to a bunch of functional units as you can see。

😊。

![](img/d75a2d2d05bae1ba71eef0f24a7544ab_29.png)

![](img/d75a2d2d05bae1ba71eef0f24a7544ab_30.png)

So this part of the machine is actually quite complex they don't show everything this is my simplified version of it from my own paper this is alphapha 21 to 64 if you're interested in reading you can actually read the paper that describes how the software is a bit cleaner more cleanly explained this has four integer execution units over here but essentially reservation stations over here and then you access the register file after the reservation stations。

😡，MPS was designed such that you never do something like this in hardware。😡，Remember。

 MIPS is called microproor without interlocking pipeline stages。

You didn't even want to detect dependencies， compiler should detect the dependencies。😡。

But you can see a modern MIPS， 1996， about 15 years after it was really introduced first time it's using Auto order execution。

Because they quickly figured out no way we're going to get the same performance。

 If you want to compete， we've got to do autoor execution like everyone else。

 So that's why this concept is very powerful。 That's IBM Power for。

 which is one of the first multi core machines it used Autoor execution。Again。

 you can read these slides they're not that important。

 but it basically has 100 instruction windows I'm going to mention this soon IBM Powerify is similar this is AMZ Z2 more recent。

 it has much bigger windows。😡。

![](img/d75a2d2d05bae1ba71eef0f24a7544ab_32.png)

And I'll conclude with this slide is again these are not official AMD or official Apple things。

 but people enthusiasts go and benchmark these machines and they try to reverse engineer what is going on in the machine and according to the reverse engineering of some people over here you can read them if on unte you can see that they guess that the reorder buffer on this machine is about 630 instructions and the integer physical register file is about 350 and Fp physical register file is 380 again this is there you can see that the load and store are much smaller 150 or so because this is actually the most complicated part of the machine。

 but you can also see how many instruction execution units there are right we had a toy example where we had a one supplier and an adder but you can see this machine easily has more than 1520。

😊。

![](img/d75a2d2d05bae1ba71eef0f24a7544ab_34.png)

O。That's the end basically for learning more about the even more complex part of the machine。

 please watch the lecture we're going to premiere and look at the backup slide you're not going to be responsible for this。

 but it's really fun to look at it I would say with that have a nice weekend。😊。



![](img/d75a2d2d05bae1ba71eef0f24a7544ab_36.png)

![](img/d75a2d2d05bae1ba71eef0f24a7544ab_37.png)