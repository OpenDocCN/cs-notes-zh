# ETHZ《计算机架构基础｜ETH Fundamentals of Computer Architecture 2025》中英字幕 p03 L3_ Out-of-Order Microprocessor Design II & Branch Prediction.zh_en -BV1Xc19BnET7_p3-

![](img/283ef3c0c88f814f2fda85c77024e5d4_0.png)

So。嗯谢。😊，嗯。对。Oh。Okay， maybe we can start。So what would that say that this I didn't say any side this。

I this for all the that zoom thing。Yeah， sometimes you just need to remove the spotlight and take it back again。

 it would work。

![](img/283ef3c0c88f814f2fda85c77024e5d4_2.png)

![](img/283ef3c0c88f814f2fda85c77024e5d4_3.png)

嗯。やた个。Should I Ho， and testing。嗯，还你接你去。对，不是的，每个组。🎼我睇么出去。🎼，Okay， so let's get started。

So we are going to take a look at where we actually left off in the last lecture right so we saw out of order execution and how out of order execution is handled and I'm Rahul I'm a PhD student obviously not for but yeah I'm going to cover the rest of the out of order execution and then we are going to move to the next part of the out of order execution what we have allluded the control flow how to handle the control flow dependency and to be specific how to handle transportation。

😊，Okay so before let's go forward so as we recall the out of order execution is essentially out of order meaning that we are dispatching the instructions out of order so in order dispatch that we have already saying the out of order dispatch essentially says that the key idea is that okay we are going to move the non-read instructions whose registers are not or the opera are not ready yet from from the independent ones so that the independent ones can get rided and then they can get executed so that's the idea and obviously we are going to the instructions which are getting sideline they are going to monitor the source values of source values from that area so that whenever all the source values of that instructions are ready they are kind of ready to be fired or let's say dispatched right so the benefit that out of order dispatch brings is that it brings the latetency tolerance that means even if let's say for example this case right so we have this added instructions which is dependent on the previous multiplication。

😊，But then there are two instructions which are completely independent to this ad。

 but in order dispatch machines with our precise exceptions。

 as you can see that even if the ad is this ad is independent of the this previous ad。

 but still it cannot get executed because you don't have the per capacity to dispatch this instruction for execution。

 but in the out of hot dispatch what happens is that this ad can go through and as a result what you can see here that okay the previous in order dispatch pipeline finishes this code snippper in 16 cycles versus2 cycles in the out of order dispatch machine。

😊，So just to recap like enabling all the out of order execution。

 we need to maintain like these key four key points we just need to enable so we need to link the consumer of the value to the producer of the value and we do is by reeeming if you remember and then we also need to buffer the instructions until they are ready to be executed and the instructions who are getting buffered who are not yet ready to be executed。

 they need to keep track of readiness of their source value so that happens based on the tag broadcasting and then all the instructions which are waiting they would just simply compare their source ties with the broadcaster tag if there is a match the source value becomes ready once all of the sources of that instruction is ready they can be fired to the to get executed in the functional limit so that's the idea of the out of order execution we have also seen a bit more on the Thomasslo's algorithm last collection we have introduced the algorithm so it was designed by Robert Thomasslo and used in IBM36991。

Processes and then that was you know this is a very good reading if you're interested definitely go through the paper so the difference between what this was implementing and what we use today is the machines that we have today actually has precise exceptions unlikely the machine IBM 31691 that did not have that capacity and the modern out of order processing as we know with the precise exception was actually conceptualized in these two seminal papers。

😊，Definitely very good read if you are interested go check out so I'm just simply recapping right so these are the two hums in the modern out of order pipeline as we have seen so the scheduleer is essentially the reservation station where all the ready nonread instructions are simply waiting and once they get ready they would be schedule to all the functional units out of order so that's out of order dispatch and then we would also have the reorder buffer which is essentially giving the illusion that the programs are also committing in order so that's essentially main giving us the capacity of doing the precise exception and also at the same time it's managing the vom model that instructions should be completed sequentially right so again that's the same picture which you have seen before so register re naming I'm just recalling again so registers are essentially the source。

😊，VueOf an instructions which you are supposed to read and as we have seen in the last lecture also the registered ID can be renamed either you you can actually take the value from the reorder buffer entry or actually you can take it from the register file itself we are going to show it in out of order processor you can actually get the value from the reservation station entry also which reservation is exactly the scheduleula so we are going to use this two words reservation station and scheduleula kind of exibly and you one or the other name kind of stick to the literature but these two words essentially mean the same thing so in this lecture so this table that we have。

😊，We have seen before right so that's the registered in table how it looks like on the so it's actually indexed by the registered ID you have the tag you have the value so tag essentially means that okay where exactly you should get the value from so if the valid bit is set so that means you can actually get across this value itself if the valid bit is not set then you are supposed to listen to the channel on this tag so whenever the tag is ready then you would know that okay the value would be ready。

😊，And we have also seen this the register file as well as the reorder buffer in case of in order dispatch machines with the precise exception capacity。

 so for the sake of this lecture we are going to start without the riorder buffer for now and we are going to see and want to give you an example how exactly the out order dispatch machine works right and then we are going to add the reorder buffer to the machine to show you how the out order dispatch machine with precise exception works and that's essentially going to be kind of let's say the nonopimized version of what all the machines that you are high performance machine that you are actually using in your laptops phones everywhere。

😊，So let's start with the Thomas Sos algorithm so Thomas So do we have any questions from previous lecture any any doubts still now？

😊，Okay so so Thomas then let's start with the Tommous algorithm let's formalize it first and then we are going to see an example。

 so Tomsos algorithm says that okay if the reservation station entry is available before renaming the instruction and the renamed operations meaning you where should I get the data from so thenamenamed operations they are essentially inserted to the reservation station and only this happens if the reservation station entry is available so as you can see easily that reservation station entry itself can be a source of let's say resource dependence which we have also discussed in the last lecture right so if so you know on top of Mos law we have kind of always kept on increasing the number of reservation station entries。

😊，That essentially increases the throughput of the pipeline helps increasing the throughput of the pipeline。

 but if this becomes a critical resource which you don't have available then the pipeline against alls right so there are walks also which tries to eliminate let's say resource dependence。

😊，And then from that specific part okay so as I said like if the reservation station entry is not available then obviously you have to install there is nothing else we can do and but let's say your reservation station entry is there so the instruction is actually waiting there instruction is not ready to be executed right now because one of your either one or many of your social teachers are not available so then what happens to that instruction it essentially starts listening to the common data so its the common data is you whenever one instruction gets executed any other instruction previous instruction gets executed it would actually broadcast the tag to this common database so the goal of the instructions which are in the reservation station is to just simply keep on listening to the bus so that whenever that tag is going through that bus you know that okay what's the value it' contained and it immediately understands that okay if the tag is seen you simply grab the value you would understand that okay now this value is ready。

Now if all of your operations I mean both operations is essentially you know X 86 has like two opera。

 but let's say if you have multiple opera and in all of your opera already at that time the instruction is ready to be executed and then once the instruction kind of gets ready to be executed then it would be dispatched so that's the terminology that we are using so the instruction is dispatched or let's say scheduled to the function unit and it would start its execution okay now once this instruction which was actually waiting in that function reservation station once it starts execution at some point of time it would finish right so let's say it's addition operation it's a floating point division operation whatnot right so after that specific latency it's going to finish once the execution finishes then it's going to again do the same thing it going to arbit a common data was once the data was becomes available it's going to broadcast and it's also going to update the。

😊，In in the register table and it's going to reclaim the reium tag Okay so so let's lets let's give an example and an toy example of this program that we are going to simulate as you can see like there are dependencies right so this is R3 that this instruction is generating and then r3 is getting used in this instruction So there is a true flow depend right and then there is also you know some other form of dependency like this instruction is generating r 10 which is getting used here So that's also flow depend and then this instruction has a dependency within itself so it reads r5 and also right r5 So that's something that we we are going to see like how exactly is happening So let's assume that okay initially the registered area table is completely empty right so all the registers are valid let's start from here all the registers are valid these are the values that essentially says that okay this register contains this value right and then initially the reservation station。

The addition unit is also empty as you can see the reservation station has like three so there are two opera for any instruction source one and the source two for each of the source you have three fields whether it's valid or not if it is valid then what's going to be the value if it is not valid then which tag that you should be listening to the common data so that you would know that okay this opera of that instruction is ready right similarly this is also know true for the multiplication unit so so let's start with you know simulating this toy example right so in the first cycle we fetch the instruction nothing happens obviously fetching is you know its just simple now in the second cycle the first instruction gets recorded so once the instruction gets recorded so it's a multiplication instruction right why it's not coming anyway yeah so。

😊，So it gets recorded it understood that okay it's a multiplication operation R1 and r2 r2 of its source opera and the definition operate is r3 right so thats that's all what we need to know so then what we are checking that okay do we have a reservation entry available it's a multiplication yes we do have a reservation3 Rs entry so then what we are going to do said okay fine so let's check the source check the register table and see whether we can use the value so what's the rename register would be so r1 is r1 available the answer is yes so that means it's valid and the value is1 right similarly is r2 available yes r2 is also valid and the R2 is value is true right so that essentially you know so you are allocating this reservation station entry。

And you're saying that okay this instruction has one valid bit this source is valid and this source is also valid so that means you know that this instruction is actually ready to be executed in the next cycle right all of its opera already so now the last thing that is remaining is that the R3 right so the r3 is the destination register so is r3 going to be it r3 was actually ready before but now I'm actually producing r3 so you need to say that it's invalid now if somebody wants to read r3 where it should go it should go to reservation session X so reservation station X is responsible for this so we are actually using the R Id here right but technically you can actually use anything so as long as you can you know。

😊，Direct anyone who is reading this r3 as a source to that entry is game so it doesn't have to be on Ex but anything as a tag should work okay so essentially what happens is like r3 became rename as x right so as I say like multiplication both the opera already so it can be ready to execute it can be fired in the next cycle。

😡，Okay so now let's see in the third cycle what happens so mu started execution right so E1 and then the second instruction which is the add instruction it started decoding so once we get decoded so that's the execution it started it's going to take six cycles that's a multiplication latency that we have actually shown in the previous lecture slide lets you know we're sticking to the same latency graph so it's going to take six cycle so it's starting from cycle3 so it's going to take six cycles and it's going to finish in cycle 9 okay so youre going to not cycle 9 cycle eight and you're going to see how it happened what happens after it we get finished。

😊，Okay， so from second instruction perspective， what happens， so r3 is the source。😊。

Where is sec what's happening yeah so r3 is the source so it immediately understood that okay r3 so what is r3 r3 is not valid and I am supposed to read the r3 from x right so you cannot do like one of its source opera already got this identification that it' is not ready okay so what the second opera which is r4 r4 yes r4 is ready so r4 we we populated it here and then r5 is the destination so r5 we actually renamed it saying at all。

😊，If somebody wants R5， go and take it from reservation station in 3A。

And this is the addition operation， okay， so that's why we are actually adding it over there。😊。

Okay so now at that cycle also now the next instruction gets fetched and now let's see what happens in fourth cycle mall keeps on executing can this instruction execute the second instruction obviously not because its opera is not available so it just simply keeps on scrolling so as you can see it immediately it checks this logic itself acts as a locking right so it immediately understands sort I cannot execute so I'm just simply waiting that instruction is waiting and the second ad gets decod and you know the animation takes a lot of time but let's say it's doing the same thing right so r2 r2 is ready so it gets a value2 r6 r6 is also ready get the value 6 and your destination r 7 r7 gets renamed as0 and where should you get it from D so that's done right but then this ad both of its opera are ready to be fired so that means in the next cycle this ad can be executed。

😊，Immediately this reservation station， this logic made you understand that okay even if this ad is next to one instruction which cannot be executed but this one can be because this is independent so that's why it can go and execute itself okay so the fourth ad is fourth instruction getting fetched and in the fifth cycle multiplication keeps on happening ad can still not go through the second ad is actually executing started execution so that's going to take fourth cycle so5 plus4 minus1 so its cycle again it its going to finish and we are going to see what happens afterwards okay so this instruction gets decoded what happens is that okay it's an ad instruction so I do have a free r entry what's my source at R8 and r9 both of them are ready so we populated here my destination is at 10 so r 10 cannot be ready yet and who is supposed to get the data from its getting the data from。

😊，Okay so then again this ad can be executed because both of its sort opera already so in the next cycle executing still ad cannot this second ad is still executing the third ad can also execute that's the you know all the sort opera already and then let's say the multiplication now comes in so what happens to this multiplication it says that r 7 so r 7 who was r70 B so I'm populated it0 B here and who is at 100 c so that means none of its operations are actually ready so it cannot obviously get fired and it just simply needs to wait till both of its opera already and then the ad also gets you fetch at by that time7 you know it's going on the ad is also going on the second third ad is also going on multiplication cannot execute the second you know the last instruction gets recorded now。

Be careful on this instruction so this what happens to this instruction so it actually says that r5 right so what was r5 before so r5 was saying where is sec what happened？

😊，Yeah， so so r5 initially was actually 0 a right so it read r5 as a sources。😊。

It says add instructions so I'm going to populate it here so it says that okay r 5 would get 0 a right and you have r 11 R 11 is going to be 0 y so it's going to be 0 y here now the thing is that R5 is also the destination so you need to rename this r 5 so what happens this case so you are renaming this R52 d y because now this is D so what happened here so it essentially its saying anyone any instructions before this a。

😡，Is supposed to get r 5 as 0 a right but the moment this instruction comes in now r5 cannot be read from a it should be read from B which is this one so this is the latest producer of the r 5 does make sense so it's a bit complicated but this is what happens right so that's why it got first it took the older rename。

😡，Then it renamed it so that any subsequent instruction would see the new name。😡，Exactly exactly。

 so are we clear on this one？So now none of these you know operations are。Yeah。

 so none of you have two ongoing ads same time okay okay okay yeah that's no no no so just like any well let's say pipeline stages you can also have a functional and you need to be pipeline so you don't have to be so even if you let's say your ad is taking let's say three cycle latency so think of it in this way so inside the adder you have three stages so at every cycle it would it can take one and the first one which was on the first stage it would go to the second one so what we say actually its my bad that I have not defined it in this way so multiplication let's say takes 20 cycle latency yeah I'm just saying so let's say multiplication takes 20 cycle latency so that doesn't mean that it's completely blocked for 20 cycles so 20 cycle internally it's also pipeline so that at every cycle it can take one more。

我这个。Yeah yeah so so the functional unit is itself is in order but but at every cycle so so think of it in this way this functional in units lat is let's say seek cycle but its throughput is one cycle one instruction per cycle exactly exactly make sense okay so so that's why we have like both the ads you know operating even if you have one added unit obviously if you have two added units you can have yeah I have question entry for every instruction that is。

😊，Yes， you need a Rs entry for every instruction。😡。

Whether it's stalling or not stalling you need R entry for every instruction ideally you need entry only if the instruction is stalling let's say you are taking it out from but just to make the pipeline design easy we are making it homogene is that every instruction even if it's you know ready executing or not ready to be executing all of them are here or here so there are certain operations a of okay。

😡，That's a very good question so so what you are asking is that if instruction is taking a lot of cycles。

 for example。😊，These are arithmetic operations right so they are taking like some arithmetic operations may take a lot of cycles like for example floating by divisions right they may take a lot of cycles。

 but at least you also know that okay their latency is bounded。😊，In some sense。

 floating point division， let's say take 21 cycles it's bounded right so you have a guarantee that it's going to finish after that。

😊，But in many cases in many instructions they may actually have unbounded latency also you don't know。

 for example memory instructions you are loading some data from the memory depending on where that data is right it's in L1 cache it can be L2 cache it can go to main memory it can have congestion in the memory hierarch key itself right the latency is kind of unpredictable right in some sense so what happens is as you can see like the more you know those long latency instructions would get queued up you need queues big so we have actually traditionally increased the size like all of these reservation station size know riding on top of mus law right because we are adding more transistors generation after generation but at some point yes it's going to be complicated like for example let's say for load instructions specifically。

😊，The reservation station entry that you are going to see for load instructions。

 they may get clogged up pretty easily。Does make sense？

We have walks on that to alleviate the resource dependence there。Okay， so yes。Thes。

 are they saved as cashs or registers or many so these are。

These are not going to be memory also with yeah yeah yeah。

 so so at best there can be SM caches but probably these things might not be also SM caches。

 they can be like pure registers also like the fastest yeah yeah yeah yeah they can be registers also like you know the fastest form of memory or maybe they can be SMM but definitely not below that。

Okay so so that's seven cycle 7 as we have already discussed what happens So now the thing is that cycle8 E6 is finishing its execution right so that we already said that it it's going to take six cycles so what happens then so E6 said that okay my wait a sec okay so E6 is saying that okay I have multiplied one with two it becomes two so then it's going to broadcast the tag x with the value two okay so what happens with the broadcast so the broadcast goes there so it says that okay it finds a match over here so it finds a match over there and it it's going to keep on checking everywhere right so that's all the tag matches that are going to happen and every place where it's going to see that same tag it's just going to tell them that okay now you have the value the value should be this so the value is two it's updated here the value is too updated there there is no other match so that's that so immediately when this happen so you get to know that okay。

😊，A became ready， so A can be fired now。It can be it's ready to execute okay so then immediately so at cycle 8 what other thing is also happening so add in this ad is also done right so it says that okay I'm going to add two with six that becomes8 and so now again what it's going to happen it broadcasting the tag B so it's a match over here so it it's invalid so i'm going to update it here I'm matching here matching there matching there oh this is a match so i'm going to update over here there is no match otherwise so that's that so there are two matches。

😊，This place and that place， so I'm going to update so this is going to be8 that is going to be8 and that's that。

O。😊，Okay so so that that's this one the next add it is still continuing and the multiplication can still not go on because the multiplication is this one its one of the opera is still not ready and the last edition cannot still go through and so。

😊，Now you can easily understand right so now this instruction is finishing so this instruction is writing it back to the register file now as I said like that addition which is the previous one it actually got you know got the value in the previous cycle so now it's ready to execute because both the opponents are valid and both values are already ready so it essentially files in the the execution unit it starts its execution this instruction is complete and this instruction is also going to be complete this ad is going to be completed here so this is that no this one is getting completed so that C C is adding8 plus 9 which becomes 17 again it's going to do the same thing it' going to broadcast the tag over here its going to broadcast the tag over there it found out that okay there was a tag so let me go back one more so this was C over here and C was also over there so it updated that okay it's going to be sorry8 plus9 that's 17。

😊，17 gets updated here， 17 updated there。Okay。So you can you can you know do it by yourself now so you can actually see that okay whenever they're getting ready to be executed they're simply getting fired right so now in the next cycle this ad is keep on going this ad is finishing this instruction hall also finished and then this instruction started execution because it both of its opera and got ready before yes。

😊，Many operations at the same time get ready for dispatch because value is now that's a very good question again so think of it in this way So let's say multiple instructions are actually waiting for some data to be coming from memory right the moment that critical instruction which is coming from the memory happen now lots of things waking up so this is what we call waking up right so now they are getting to fire So you have two options not two options So the correct option is that you need to now figure out a scheduling algorithm So which one you need to fire So there are lots of works in the literature that tries to identify critical instructions right so you are going to fire some instruction out of all the ready instructions which are critical in some sense right so maybe you can think of it okay if there is a memory instruction that is already got ready you probably need to fire that one because memory is unbounded and it can take a long time right or maybe you can also say that okay if you have another long latency instruction。

Maybe fire that one or you can come up with lots of youristics lots of algorithm which essentially answers the that question one so it depends it depends on how many functional units have you have right。

Like if you have let's say 10 instructions ready， two of them are a five of them are load。

 but you can only execute three load and one addd you can yeah per cycle so you can only fire one you know add and three loads something like that okay more practical yes how many of these others are usually present in CPU。

Yeah so it depends on you know CPU design from design right so for example let's say so there are these functional units it sits behind something called ports to access these units right so for example in recent intel processes we have if i'm not mistaken 12 ports in total so out of these2 ports three ports are set aside for the load instructions and then remaining ports and non-memory three ports and loads。

Two ports are for stores I guess and then then remaining are for you know Alu instructions arithmetic instructions some of those you know ports are for simple arithmetics some of the ports are also for floating point or vector arithmetics right and the functional units actually sits behind this port so that's how the architecture goes I'll probably show if time permit I'll show one example of intel yes how are so many if you are so many reservation stations in that case within one cycle exactly so so that's so the question that you are alluding to is is coming from this fact that if you have this much of such going on so it's。

It's going to be you know energy intensive right it's also you cannot probably scale it up also so designers have gone through lots of you know tactics to make it work right so one easy tactics is to break it down so you' are not going to have a monolithic reservation station for handling all the instructions you would have as we are showing over here like one reservation station for multiplication another reservation station for at earth another reservation station for loads and and so and so forth so that's one one way the other ways is you can like we were going to show in later part of this lecture that you can optimize this table structures like for example you can easily see the values are getting replicate in multiple places so you don't need to have values why because today's processes are 64 bit processes right so all of these values can be 64 bit so you need to have table that can store 64 bits everywhere So values here values there values there once we are going to add。

Reardder buffer also to handle the precise exceptions in out of of machines then you are going to see you know reor buffer also has values like values everywhere。

 So that's why you know one way to optimize this is to keep a pointer rather than a value so let's think of in this way So if you have thousand24 entries So that would be like 10 bit value it's I one entry but this value would have been 64 bit so that's you have like one sixth off exactly so you kind of collate values in one table and point everything to that table so that your structures become smaller it becomes faster to access Yeah so what happens is then that eventually that that file that everybody is pointing towards which we call the physical register file that part becomes much more critical because now that getting access from multiple places So its probably one of the。

crucialial part of them out of order the core to design with right so you need like we have probably briefly touched on the superscale part also right like we are seeing one cycle is decoding one instructions but in today's process we have superscale eight way superscale let's say eight instructions can be decoded in one cycle so literally eight folks can read all of these structures so。

In one quote， in one quote。Yeah， so the principles the same， but it's heavily optimized。

 obviously that's the case exactly exactly。😊，Okay so so I'm not going through you know too much details of all of these cycles now you can easily guess like when all the instructions are getting executed were ready。

 so this instruction got ready and then they would also you know broadcast the message and it simply keeps on updating as expected here。

😊，Okay so with that said so let's let me quickly you know go through one of the situations so like some questions we have already discussed lots of steps in in the discussion itself like what is needed to have the hardware to perform the tag broadcast and it's also going to be expensive and you know does the tag have to be the idea of the reservation entry as I said that it doesn't have to be as long as you you can point to the producer you are fine with that right and then what can be the potentially critical path so the tag broadcast like what we are discussing it's all of these things they are are the crs of the out of order machine so the structures that you are seeing apart from the memory like memory is obviously the bottleneck if something is after memory is this part。

And civilly optimized。Okay， so so yeah， so one I'm not going through this example for this sake of this lecture。

 but what we are trying to say is that if you see this snapshot，😊。

And you can go through this lecture slide by yourself if you see this snapshot。

 you can actually create the data flow graph data flow graph meaning that oh this ad is dependent on this guy and and let's say okay this ad is dependent on itself and let's say this ad is also dependent on the multiplication actually not this a is dependent on itself but this ad dependent on the multiplication and so on and so forth so you can actually create the data flow graph just by looking at the state of the reservation station。

 the register area table and and so and so forth so I'm not going to go through a lot of details over here but yeah so like we are also discussing many of these things anyway like should should it be centralized or should it be let's say distributed the reservation station for the sake of faster access for the sake of energy efficiency and so on and so forth and。

😊，We have also alluded to this question that okay all the entries are storing data right so is it even you know a good thing to do you can optimize。

😊，For sure， what happens in actual processes？Okay so now I'm just going to give a quick rundown of the out of order execution with precise exception and then we are going to conclude this part of the lecture going to take a break and then come back for the branch okay so as we have also discussed like out of order is essentially the out of order dispatch right but in order dispatch machine also needed a reorder buffer in the last lecture if you recall in order dispatch machine also needed a reorder buffer just for the sake of precise exception right so give the visibility that the programs are kind of completing in order okay so here also we are going to do the same thing so what happens in out of order machine that whenever the instruction updates registered earlier table so we actually pickup the register file what we just saw so。

😊，So there are two register files that we kind of implement in out of order execution with precise exception。

 So one is the。😊，Register really stable that you are actually reading it from the beginning so that was the what I was showing over here。

 so that's what we call front end registerify why it's front end it essentially says that okay any following instruction。

😊，The decode stage you are going to read this register file so that's why we call it front end okay so frontend for the follower instructions front end like you are going to read this register file at the front end of one instruction okay but then there is also another register file which is we call an architectural register file which sits at the you know when the instruction finishes the execution so once the instruction becomes the head of the reorder buffer so it's so all the instructions before this instruction has been committed or retired so now I am the oldest one in the machine so think of it in the sequential way right so everyone from the before me has been committed I am the oldest one now when I'm going to retire Im。

Okay， yeah， so when I'm going to re， I'm going to use this。

That register file for updating so why why do we have this so this is actually yeah so so this is what I said so。

😊，Not always note this thing so frontend register file which we showed before so front and register file always gets updated by any instructions as as we showed right so when you decoed an instruction you know that okay whats its going to the destination going to be the destination gets updated so and so forth but the architect register file which sits in the you know back end of the。

😊，Wwhich is accessed later on in the processor in the pipeline so that always updated in the program mode so what's the utility of this register file it essentially says that okay we are going to see let's say when we are going to flush the pipeline plus the pipeline for multiple reasons let's say you know you have branch miss it's a processor is actually executing a wrong path so you need to flushs the pipeline in a sense that okay every instructions before that instruction is now done。

Now this is the first instruction which is you know problematic now what you would do you would just simply copy this architectural register file to the front and register file and you know flush the other stages of the pipeline and you would be ready to go so as if your processor kind of rolled back。

😊，To a state where it is a precise exception like everything before that is committed and nothing after that is starting execution so that's the whole idea of having two register files so so we have seen this thing till now without the precise exception so now if you have precise exception we are going to add this reorder buffer which is similar to the in order dispatchment machine and this is the architecture register file also so what you're seeing here that see that frontend register file has a valid bit but there is no valid bit here why because at this stage all the values that are in the architectureural register file is going to be correct so there is no speculative value word there is no let's say value that is yet not generated because this register file is getting updated when when the instruction producing this registers are already done。

😊，So they are ready to commit in so that point it is getting updated so that's the。Exposed。

So it's a checkpoint for the machine yeah so have a branch your computer assumes it's correct those prove the entirety of its calculations。

ルせ学。Sa。Yes， so pro because the grant is not。So okay， so branch branch is not handled as an exception。

 but think of it in this way so any instruction that is like simplistic way so any instruction which is before the branch。

😊，Let's say for the sake of the discussion let's say that they are on the correct path right so this keep kept on committing committing committing now you have actually saw a branch or a instruction which kind of raised the exception right branch is not raising the exception we are going to discuss it later on but let's say that instruction came up and it raised the exception so now what you need to do you need to say that okay I need to roll back to a state of the processor where all the the。

The state of the processor should be at such that。😡。

All the instructions before this instruction is done。And none of the instructions after this。

 including that instruction， is starting。So flashback exactly so that's flashback what we call in this thing is it's called checkpoint right so it's think of it like whenever you're making update here so this update is truth so there is the flashback state is exactly exactly temporal it it's updated sequentially yes one by one one by one so it needs to update it and when the instruction is comingting from the reorder buffer so it's the in order part of the machine at the end。

😊，So maybe if I go， yeah， so if you if you go here。

 so it actually happens here so after it got reordered。😊。

Then it would update this architectural registerify。😊，Yes， here it do do do。

So it's written as well as written to an architectural。No no。

 so front end register file is getting written once the instruction is finished this execution。😊。

And then the architectural register file is getting written so so think of it in this way so this instruction finished here。

😊，At this point， it would write the front end register file。😊。

But it won't write the architectural register file till it comes here why because you know this guy needs to be you know reordered in such a way right precise exception says that you cannot commit this instruction or let's say think of it in this way so if the longer one was there and the smaller one was later so smaller one finished before so can you update the architectural register file like that no。

😊，So you need to wait， you need to wait till it happens in order。😡。

So why we are waiting because you know you need to you need a guarantee of precisionness right so everything before that is done I'm pretty sure about that none of the thing after it I'm going to reexec。

😡，So the entire state before is already updated exactly， exactly。So the entire state。

 so the the architectural register is essentially saying that。😊。

Whenever you go into a panic mode that you need to roll back the system right。

 you can just simply copy this to that and flush all the pipeline and then you restart from the instruction that you created the problem。

 you would be fine。But everything before that is already done， it was already reflected here。

 none of the thing after that you are anyway you know restating this thing。Does it make sense？

Oh wait， so the pro then register file， this is what our CPU uses。

So both the things are inside the CPU， both the things are inside the CPU。

 So front end register file is getting updated and read。

Out of order right So whenever an instruction completed execution， it updated here。

 whenever instruction getting decoded， updated here， everything right。

 but the architectural register file never gets updated out of order。

 it would only get updated exactly exactly So it's think of it in this way that this always keeps on you know checking checkpointing like as if you are doing a debug in vS code right So one step one step。

 you would actually say this， not this but as as Yes， yes one line one line one line you are to。

 so think of it this is like a program of visible thing this won't be ever visible to program it whole other storage at the end。

I mean I mean we are not calling it back in either it's just calling architectural register and this is the front end register file yeah yeah。

😊，Okay， so so now if if you have， let's say the order buffer also and then the Rs， you know。

 this is what the machine looks like and that's that。😊。

Okay so I'm going to just finish this lecture by just showing this thing so this is Intel lineco processor which is you know pretty state of the art from Intel side right so that that came out I think sometime last year or maybe yeah sometime on this so what you're seeing over here is a following so that's the riorder buffer you have you need a better eyesight so that's the reorder buffer what's supposed to reorder the instructions and that essentially responsible for you know committing instructions in order what we just showed and then to answer your question right that the register files are also getting bigger and bigger as we discussed right so the register file also is not a monolithic structure they also distributed know divide it so that's a vector register file and you have the x87 where like a floating point register file and then you have the integer register file and then you also have the we already discussed this question。

😊，Like the scheduleer so that scheduleular entries are also you know distributed so they are not monolithic hum anywhere。

 okay， all of this to you know make the processor fast enough to put enough。

Okay so I'm just going to recap everything so as we discussed like enabling out of order execution is essentially like boils down to supporting these four you points you need to link the consumer with to the value of the producer which we do it via registration renaming you need to buffer the instructions until theyre ready which we do it via registration station you need to keep the track of readiness which is doing know happening through the broadcasting and comparing with the source tags and then you also need to you know dispatch the instructions out of order only when all of the sources are ready so that's you know the wake up and should logic okay so with that said this is the end of the first lecture force part。

😊，And。wayay out of time Okay， so so let's take a 10 minutes break and let's come back by310 and we can start from there three not310 let's say312 and we can start from there。

Okay。就算上知票。Yeah。Yes。This one supposed to be 20 minutes。



![](img/283ef3c0c88f814f2fda85c77024e5d4_5.png)

你说事。有。So something time。

![](img/283ef3c0c88f814f2fda85c77024e5d4_7.png)

最啲呢个。我哋叫好 listen。This。6到5。老。Okay so welcome back again after the break so now we are going to see other part of the you know high performance processor design it's a quintesial part and it this is the fundamental part of let's say design which is branch prediction so so the course of this lecture you know I'm probably going to motivate that you know the disease is。

😊，Probably one of the mostquintental part to focus on designing any high performance high performance processor and you literally cannot have a high performance processor if you don't design this okay so let's see so just recall that okay what is the control dependence we have already you asked this question that okay you are executing instructions one by one then the question is that okay what PC that we should be fetching next right so that that's always the question now question it's easy if the fetch instruction is a noncontl flow instruction meaning it's not a branch so that means you know very well that okay it's going to be sequentially the next instruction right。

😊，Life can be harder if your instruction size is also variable like for example like statistics follows this instruction variable instruction link。

 but there are other ISs which have like your static instruction let's say four bytes or something so if the instruction size is fixed then you can just simply say that okay next PC is equal to PC plus4 right life is easy but the point is that if the instruction is whether the instruction is a control for instruction let's say if branch right so it's like if a equals0 that you don't know whether if a is equals0 or if a is not equals 0 and depending on the condition you are going to either go to the next PC plus4 or you may actually go somewhere else right so that's what it's the is the problem like what would be the next PC。

😊，Even this is also a problem that okay whether the fixed instruction is a branch or not because if you recollect the pipeline right the instruction gets decoded in the next stage right so before the next stage is already there you don't know what' iss going to be。

😊，So so that's a problem that branches face so this is you know the common type of branches that you know most of the is kind of support So the first type of branch is the conditional branch whose dele at the F time is definitely unknown you don't know whether it's going to be taken or not taken and then number of possible face address is going to be two right so it's either going to be one or the other and the only stage where you are going to know where the next PC would be is at the execution stage now recollect is that you know execution stage can be like the branch can be resolved like this is what we know by being either resolved so that means the branch can be resolved you would know after the execution at long time after it can be like for example let's say the branch is actually dependent on a load instruction and the load is not yet come from the memory so this branch is also waiting to the data to come back once the data arrives then only you would get to know that whether the branch is going to be taken or not you have written codes like oh if AI。

Well， let's say area of I equals0， then you are going to do this， but it's painful。

 It's painful for the micro architectureiture to do those Okay so now the second type of branch is like unconditional branch it's like always going to be taken right so's that's much easy and unconditional branches the jump address is known at the deco stage's say jump some predefined location So we have instructions like that then we have calls meaning it's always going to be taken so youre calling a function so there is no condition or anything So it's always going to be taken there is only one possible address it's known at deco time also similarly there is written sorry return which is always going to be taken but now the question is that the return can have many possible targets based on the calls so who called it and I'm actually returning there the return is one instruction the return address is。

😊，You， it can be many depending on what the call would be and it also going to be known as the execution itself。

😡，And then comes another you know specific part of instruction like indirect branches。

 or indirect branches， meaning you are saying that， jump whatever this know value of the regis is。😊。

So whatever the content of the register treated as a let's say treat as a address jump there so when it happens so think of you have probably used know switch cases right so switchs this variable condition one condition two condition3 it's actually not if clause it becomes indirect branch an indirect branch know if you actually make it a direct branch you may like if you make it conditional branch you may actually see better performance but if it is indirect branch then it becomes like oh you are loading some data into a register and you are saying that okay whatever the content of the register you are just going to jump there so that's an indirect branch it's going to be always taken but what where you are actually going to be jump to it's depending on know the condition itself and that's also going to be known at execution so so always it's very obvious that different branches are typically handed differently and and so on and so forth。

Now， the question is that you know。😊，We know that we have to keep the pipeline fed always with the instructions right and so if we see a branch instruction how exactly we are going to feed the pipeline。

 the next instruction so that potential some potential solutions obviously one solution is that stall the pipeline okay not going to do anything wrong but till the next address is known stall it and you can easily I guess that this is not going to be the best performing one。

The another obvious answer would be that okay lets let's guess the next page address right so that's the whole course of this lecture is going to be and then there are other know possibilities also like we have branch D slot so it it has been used into some older processor which probably did not go well and then this is also a very interesting possibility fine grade multitrading you can always you know keep jumping on with the different threads and then you you can always you can also try to eliminate the control for instructions using predicated execution。

😊，And this is also a very you know intuitive， but many oftentimes it's not that easy to do like if you're unsure execute everything right so taking part not taking part that's called multipath execution okay so start the pipeline if we do go on like this what happens then so let's let's see a very basic example right so think of it in this way that it's not this is a。

😊，Control so so this example let's let's say that okay you you are not even burdened with the predicting the direction so you know that it's always going to be taken so what happens in that case also so when this in so this is a branch instruction let's say so when this branch instruction gets decoded。

😊，You are not going to know where the next address is。😮。

Unless it's get decoded right so at least this cycle would be a bubble you cannot fetch this instruction at here。

 you can only face this instruction here so even if there is no burden of predicting the direction even if youre always taken branch would have you know 50% of the throughput right so at every alternate cycle you are actually missing so that's a problem right so。

😊，Yes， as I said like stalling probably doesn't work and if you have let's say conditions and I blah。

 blah blah life would be messy so then the next question thing is we are going to predict the the possible target so now before going to the branch prediction I just need to motivate like why branch prediction is a very know critical crucial issue for designing out of order processor so this is let's consider this thing that you know control flow instructions are let's say one every five instructions one every four instructions are control flow and that's a very good estimate now always so the problem is that the next first address after a control flow instruction is not determined after n cycles in a pipeline processor So now the question is what is n right so it actually everything boils down to n now n is essentially the minimum branch resolution latency that means the minimum latency that you have to so that's the latency between the branch。

F and the branch is executed right so that's the minimum now consider this that you know n can be really large if the branch is also dependent on some other instructions which they themselves are not finished right so it can kind of you know get a depend hidden exposed behind a dependency chain。

😊，Now， the question is that if we are wasting for this n cycles and we don't know what actually to do at that time。

😊，In a superscale processor we can actually fetch W instructions every cycle so technically what is happening is that every branch misprediction you are actually wasting n cross W number of instructions slots right so now how important that is so let's let's use it for some know example so let's let's assume that n is 2020 pipeline stages I mean which is very you know I mean modern process may actually exercise even more pipeline stages than 20 but lets let's start with this for sake of know easeiness and then w is the superscalear width which is let's say five instructions per cycle you can fetch decode execute everything okay now assume also that one out of five instructions the branch so that means every five instruction block ends with a branch right now also assume that okay if we have 500 instructions how much time it's going to take so now if we have let's 100 percent accuracy so that means。

😊，Out of 500 instructions we can actually phase de to execute five instructions per cycle so that is going to be 100 cycles no brainer okay so now there is no cycles that we have wasted so the IPC which is instruction per cycle is going to be 500 instructions in 100 cycle so that's 5。

😊，Okay， so now let's say 99% accuracy it's a good accuracy right。

 99% is like pretty damn good accuracy， so what happens then so you have hundred0 cycles。😊。

You have to execute in the correct path why because you have you know 500 instructions to execute in five per cycle so definitely you have to execute 100 cycles for sure。

 but now you have 99% accuracy that means out of 100 dances there is only one branch that you have mispredicted。

😊，So for that one branch， you actually got to know what it's going to be after 20 cycles so that means。

😊，20 cycles you have actually wasted to do something wrong so this is when those architectural checkpoints come into picture so when you actually got to know something then you have to go back you wasted these 20 cycles right so that what happens then that means you are actually completing this instruction program in 120 cycles so that means 20% extra instructions are getting fetched which IPC is boiling down to I don't know 5。

1。2 it is going to be probably4 each kind of okay。😊。

So okay it's not bad I mean we started from five we came to four it's okay so let's go to 90% accuracy if you do the same math100 cycles on the correct path 20 you know 10 branches got wrong so 20 you know cycles each so that's 300 cycles your IPC is becoming 1。

6 right so we are already tanking。😊，Now， if you go even 90% is not even a bad accuracy so but if you go to 60% accuracy and consider this like 60% is still better than a random chance right so if you go to 60% accuracy then what you have seeing is that entire of it is taking900 cycles which means that it's 800% extra instructions you are fetching and in your IP tank below one so it's really problematic。

😊，That even a small change in accuracy can either boost your performance really high or you boost or tank your performance really drastically。

 so that's the crucial part of the branch tradition problem。Okay。

 so that's a whole I hope that I can motivate and it's a very fascinating topic to be， in my opinion。

 yes。Okay so so this is this is know a pictorial example I'm not going to go through too much of the details but as you know what we' are trying to show here is that if you don't have branch prediction then all of these cycles essentially you are not going to fetch anything and if you have a branch prediction it's a correct branch prediction you can actually face this thing in age cycle so even if it a very small program like this you can see there is benefit okay and but then obviously there is no free lunch so if you have a mis predictiondi then you also need to recover from the mis predictiondi which also cost more things but the whole ball game is to stay on the positive side rather than going on the negative side so we are going to make a prediction。

😊，As best as possible so that we don't tank performance eventually， okay。

 so let's start with a simplistic version。😊，Always guess the next PC I mean it's not essentially a branch prediction for that matter you are just simply incrementing the PC right I'm assuming let's say four bytes is the instruction size so that means next PC is going to be PC plus four right so this is a you know it's a next phase at this prediction you can think of it is as like what the process naturally does right so can we make this more effective then the idea is yes you can kind of do some sort of layout in the software etc ce if the branch is supposed to fall through more then going to be taken then you know。

😊，The layout the fall through path in such a way that it would that fall through would always be you know the correct thing to do right like think of it in this way so if you write a loop right for I equals0 i less than 100。

😊，For 99 times it's actually going to be you taken and sorry 99 time it's not going to be taken and only one time it's going to be taken which is branching out correct so it's going to come out of the loop so you can actually put the code in such a way that okay the fall through path is always going to be the correct one so even if you have a naive processor it's just going to go to the correct path itself okay you can obviously make it even better like by using profile guided optimizations like I'm supplying you the binary I'm also supplying you some sample let's say input to the binary that I'm supposed to run this binary in the field and I'm going to when we have compiling I'm telling the compiler Gcc by the way all of the compilers they can do this profile guided optimizations I'm telling the compiler that okay use this test input and do some analysis and lay out the code in such a way so that at the end of the day when the binary hits。

You know marketke hits the wilderness it's going to run as best as possible Okay so we can do that and you know。

😊，We can you know but we can make it even more effective also so yeah so there are other ways to make it effective that okay you can get rid of the control flow instruction altogether so there are techniques like predicates branch and I'm not going to go too much detail into this because you know there are lots of lots of possibilities but i'm just going to give you a broader examples of what all things are here in this domain by the way you are going to have a branch prediction lab after this at the end of this week so I hope you are going to enjoy that lab also。

😊，Yes。😊，Okay so so so what happens you know always next always if you do always PC plus4 it's fine。

 but it may not work also in many cases like what we have already shown here if if you get to know that these things are bad and you actually went through the PC+4 path and it's actually not going to be p+4 then only you are going to get known it here so anything that that happens in the middle it it's going to be flushed if the person needs to go back and it's restart the execution so yeah so we have done similar exercise before so now now I'm just giving you some more variant of that exercise right so let's say you we are making some guess right so the correct yes don't have any penalty you are feeding the pipeline with the correct instructions every cycle but if there is an incorrect guess let's say there is a two bubble cycles bubble so you cannot you have to go back and and then then restart so you lost two cycles。

And so let's say there yeah and then you also assume that there is no data dependency related stalls 20% of the instructions that means one every five instructions are control flow and 70% of the instructions are taken let's say so then what happens so your cycle per instructions we want it to be as low as possible it's not IPC it's a opposite of IP one up IPC so what happens here we are saying that for every instruction which is you know we would start from one as IP sorry CPI every instruction takes only one cycle to finish the pipeline thing but then you would also say that 20% of the control flow instructions out of those 20% 70% of that instructions are taken so for those 70% you you would actually see the next PC to be PC plus4 it would be something else so that would be the wrong thing so for those you know 0。

2 into 0。7 times。You're going to waste two cycles more right so that's you know if you do the calculation。

 then it it comes out to be let's a 1。28 right So you are seeing that you know instead of taking one instruction you know you're seeing cycle point instructions to be one。

 it actually quickly became 1。28 So that's like 28 person it's not bad it's not good it's actually bad 28 person in that sense okay so then the question is can we do better。

 obviously keep asking this question always right the answer is yes。

 so then we not we just not want to go for p plus4 we want to actually predict what its going to be the next address so to predict that next address like p plus4 is also prediction in that sense it's just that it's a naive prediction but now we want to be most sophisticated let's predict something So for prediction we need actually three information at the fetch stage So that's the critical but at the fetch stage itself because next instruction is going to be the fetch。

In the next cycle right so at the first stage we need three information what whether the first instruction is a branch or not。

 why because this is not known at the face stage， you would actually get to know it on the decode stage itself so you still need to know whether this is a branch。

😊，If it is a branch。If it is a conditional branch whether you need to know whether it' is going to be taken or not and you need to know that if it is going to be taken then what is going to be the at right so there are three key pieces of information and we are going to see how exactly we do this three key pieces of information right so。

😊，That this two is。A bit easier to predict in a sense that I'm going to explain let's say we we have this observation that okay。

 if you have a branch it target is it's a conditional direct branch target is actually。😊，So。

If it is taken where it should lead to its fixed， whether it's going to be taken or not。

 that's a different issue。😡，If it is going to be taken where it should lead to its fixed it is actually present in the instruction itself right so you would see instruction like oh if jumped not zero to this address so the address is already embedded in the instruction。

😊，Whether it's going to be not zero or not that's you know it's going to be defined the runtime correct so what we do in this case the cleanest idea is that okay whenever you have seen this instruction before just remember them because you have decoded that instruction before so remember that instructions target address and whenever you are going to see that instruction again you would just simply go there so this is actually good for conditional direct branch but as I have already discussed like indirect branch this is not going to work because indirect branch that the target is also variable at the runtime right okay so so that's so that's a essential idea that okay you are going to say and remember and so that's what we call it is like a branch target before it is another cache structure again。

😊，Yeah I mean you' are going to see caches everywhere so this is just the core part of this yes。

 so youre going to see caches everywhere just to so the critical part of computer architecture is that what happened before is likely going to happen again so it's just simply makes sense to you know keep remembering so yeah。

😊，So what happens in this case so so we actually start with the program counter which is the instructions address right so we have to so for the sake of the remaining part of the lecture let's let's focus on the conditional branches right so what what's happening here that you have the program counter you have。

😊，The BTB which is the branch target buffer you' are looking at it BTB you're going to say that oh what's going to be its address right so that's the BTb is going to do this and the program counter is also going to be used to look up into the direction predict let's say there is a predictor which is a pullolean prediction it's going to be taken or not taking so this BTB is going to give you two bit of two information one it's a target address and another one whether it's a hit or not so think of it in this way if it if it is not hit so that means this branch is not present here。

😊，Then you would say that okay， target address is probably going to be garbage right so or maybe something right so but if it is a hit。

 then you actually also give you this indication that okay。

 this is a branch right because you're only updating this table when you have seen a branch in the past Okay so you you do that for every instruction Yes one cycle you are the entire Yes。

 yes。There's lots of optimizations going on yes the worst case would be if you had the one% chance branching。

I that a transform。And难问他。First。I did not get that word Can you repeat the question so and then yes and so the exactly so what you're saying is that the first time when it's not warmed up so this is what we call warmed up right so when it's not warmed up it can actually go he right so but once it warmed up and that's what we actually care about right because we don't care when your processor starts well technically we don't care but yeah but we typically care like when the process kept on executing and then then you know your laptop is going on it's kind of warmed up already have something going on here。

Exactly exactly so that's the idea so so as I said like if it is hitting。

 then you are going to and this information， whether it's going to be taken or not taken。

 you are also going to put it into and and get logic what does that mean So if it is hit not hit so that means it's not a branch you're not supposed to use any of these right so this logic becomes zero and so this is a multileture which always have p plus instruction size as one input and the other input is coming from the target buffer So if this and so if it is not hit so that means it's probably not going to be branch so that means you should not use this thing and it's just only going to be p+ but if it is a branch then it is going to be hit then you have a option that whether it's going to be taken or not taken if it is taken then you are going to know select this one if it is predicted to be not taken then you're going to be having PC+。

😊，F。我。谁。So what happens there it is actually physically calculating this is equal zero the branch then no no no no so so this this is predicting where you should go if it is if it is let's say taken out if it is indeed taken where it should go exactly and this one is predict exactly。

😊，And then taken so taken is essentially saying that okay whether this branch is going indeed going to be taken or not。

 so think of it in this way so you have a let me tell you so you have a you have a code snippet in something like let's say oh if a of I you are iterating over an array if a of I is odd you do something otherwise you don't so you are initializing every odd elements in that array to be0 let's say correct so if it is not odd you are not going to do that if clause if it is odd then you are going to execute the if clause so if it is odd whether it's going to be odd or not odd。

😊，That's this part。And if it is odd， then youre actually executing a different piece of code， right？

😊，Where you are supposed to start execution is this one？😡，You get the difference now。Okay。

 maybe we can discuss later yeah so so this is the direction predictor it's just a boolean predict it's predicting that whether it's going to be supposed to taken or not taken。

 but even if it's predicting that it's going to be taken or not taken you don' if it is not taken you know that this is going to be the case for sure like you are just simply falling through but if it is taken it can be actually going to somewhere else like I said you have a big if clause and then you have a else clause so if it is not taken then you actually need to go sorry if it is taken then you fall through but if it is not taken you need to jump somewhere so that somewhere is coming from here in a sense so for the sake of you know for the sake of this remaining of the presentation also and for the sake of your lab we actually would focus on this one。

Like it's really you know， in many cases it's actually tough to predict this one right not that this is also easy in some cases like in especially in today's you know server class processes。

😊，There are too many branches which you cannot even afford to store in the BTB like BTB is becoming less so what do they do the obvious question is okay have another BTB right so you have a second level BT it's like becoming a cash right so that's obvious thing but then you know you can also do some intelligence stops over there so that's what they also do this but for the sake of this lecture we are going to focus on this。

😊，Okay， so so now let let's go to a bit more sophisticated advanced predictor and let's see so as I said like。

😊，Okay， so we need three information whether or not the ph section is a branch。

The direction itself and the branch target address so as we discussed that okay this one and three can be done by the BB itself if it is a BTB hit you would know that okay the first instruction is a branch if it is also hit then you know that what would be the branch target address but the second one is a conditional branch direction which we are going to focus more。

Okay， so now now let's see like how we can predict the direction of the branch tradition。😊。

So so there are both let's say compile time solutions or the and the runtime solutions compile time meaning you know it' it's happening entirely at the compiler level the runtime meaning it's much more dynamic it can actually adopt itself and so on and so forth so I'm going to go through a bit on the compile time branches and then then we are going to focus on the runtime one okay so so let's start with you know so these are the some basic it's a very simplistic thing of compile time like let's say branches like for example know always not taken we have already seen that always not taken is like p plus4 right you can say also always taken like you will always whatever your Btp is saying just go there right that's also fine always taken you can also say backward taken backwardboard taken forward not taken can you guess why it's that the case。

Why would someone in their life would come up with this。Okay。

 so backward taking meaning if if a branch is going backwards to the code。

 so you are at some point and the branch is taking you back to the code。😡。

Well zero return might actually return anywhere right so so think of it like you have instructions laid out in the memory one by one and then you have a branch which is actually the target addresses。

 let's say earlier instruction not the later instructions。

 earlier instructions and the forward branch。😊，So。Or。Okay， anything else？😊，Exactly。

Fall loops so if if you have fall loops fall loops are little in this way right so at the end of the loop you would check the condition otherwise go up so that's fall loop so fall loop is literally this is we taken for fall loop like backward always take because we have seen that fall loops are supposed to be like this if you are iterating let's a thousand times 999 times iss going to be going back and only one time it's going to come out which is the conduct right so that's the idea of this and then you can also do a bit more better profile based we are going to see this and then there are more sophisticated version of the direction prediction from the compiler side also like program analysis based and then run time we are going to focus more on the runtime itself so i'm going to go a bit more faster on the static type and then try to quickly go to the dynamic type let's see how much we can do。

😊，Okay， so as I said， like always taken， always not taken。

 both of these are possibility very simple to implement。😊，Pahartic accuracy okay like 3040%。

 you know very well that okay what can happen if you operate on this accuracy okay so but then again like compiler can do some sort of code layout optimization so that always not taken gets a preference and and so on and so forth but that's it's something but then always taken is again like there is no direction prediction right like you're literally saying that okay whatever your BtB saying just go there so it' is like as if assuming that everything is taken but guess what it's actually better than always not taken why because more often than not the way that we as a programmer write code the branches written in such a way that it's actually going to be taken so but again's like of it depends on the code to code but it kind of behaves more better than what always not taken is supposed to do but then again like as we say like the backward branches loop branches。

😊，All like usually taken so if if it is less than zero go back so it's a backboard should be always taken so that's the whole idea。

 but then you know。😊，We discuss all this this that the backward branch essentially the target address is a numerical lower than the branch species itself and then we also discuss this backward taken forward forward not taken which is you know coming from the loop itself okay。

😊，So we can do a bit more more sophisticated like we can go for profile based profile based meaning like the compiler as I say like you give some inputs。

 reference input to the compiler compiler is supposed to determine the likely direction of the branch right and then you know you can instead of having a very global generic view of the rules like oh if it is a backward branch taken forward branch not taken you can actually do a bit more sophisticated it's a part branch you can go like power branch prediction so how it happens so compiler kind of guesses whether this branch is going to be taken or not in the field。

😊，Just looking at the sample inputs that you are providing and then compiler would actually annotate the instruction itself that this is the jump not zero instruction and I'm predicting it to be not taken in the field so you would add that one bit of instruction in the eyesight itself so as you can easily say that okay it requires a bit in the eyes itself right so it's not you know transparent in that sense I to support this situation right but then compiler can do this to some extent obviously not for always but then you know if you have some you know behaving branch like this which is very much dynamic in the end right so there is no statisticalally fixed。

😊，Behavior coming from that branch right so let's say oh it's always true and then taken on and always not taken all let's say if it is just simply oscillating so then you know if you are simply going to say that okay it's going I'm just tagging that branch to be always taking or I'm tagging that branch to be always not taken none of this is going to work but you can clearly see that there is pattern but static compile based methods cannot do this why because it's just simple static things so as we said like also this is another problem so the accuracy depends on the representativeness of the profile input set right so let's say you are supposed to run a huge humongous game in the end right but then you are just simply profiling your binary with a very small game it doesn't make sense so you need to also give it a very representative version of the input so thats why it can work。

Okay so and then we have let's say static advanced prediction you know program based also program based meaning meaning you are going to you know analyze the program itself and we can come up with some heuristics on the program analysis to determine some sort of this statisticalally predicted direction so let me give you on some example of what do I mean by this so so let's say。

😊，Here is some heuristic that we analyzed from program okay so it's an off heuristic it says that predict the branch less than zero。

😊，If the branches of this type then predict this branch to be not taken why because you know we have written codes in like this oh if the no value of this is negative then you know don't enable this part of the code if the no value of this is minus 200 so that means this part of code is disabled right so what we as a programmer the way that we write the programme in general it says that okay if there is a branch less than zero type of code more often than not it's actually not taken okay so that's kind of like a very heuristic again you can easily assume that it's a very crude heuristic you can easily write a code that kind of breaks down this rules and that's obviously true then similarly there is one another loop heuristic also that if if there is a branch which is guarding a loop right so you have a branch which says that okay if that's going to be taken then you are going to execute the loop otherwise not then。

😊，Its it's better to and this heuristic， this paper actually says that， okay。

 then it's better to predict that that branch is going to be taken why because。😊。

They have found out that your programs are written in such a way that you would actually execute the loop in general。

 not specific to the workloads at that time， but in general that's what they say but obviously you as I'm keep on saying that these things are very much dependent on the programs and you this is like a 30 years wow yeah you can see that know 30 years all of these hugeies might not actually hold also so yeah and then then this is another huge like if it is a pointer or floating point comparisons then you predict they are not going to be equal like would be let's say for example let's say oh you are doing a know linkage traver cell and you are trying to find a key in that in link list so more often than not you are actually not going to find the linkist and only one place you are going to find the linkist it's going to end there so if there is a pointer or let' say f comparisons going on every comparisons also makes sense like youre comparing to floating point values what are the award。

😊，Those flooding point values are going to be same more often than not they are not going to be same so that's kind of all the heuristics that they have come up with right so once they have understood this heuristics these heuristics are fed into the compiler it separate so the compiler are going to do this forever so it does not require the profiling so that's a benefit but then the question is that heuristics might not be representative at today's time it might not be good also for the today's time but then also at the same time it needs I support so you need to add that bits over there blah blah blah。

Okay so I'm going to go skip this other type of branch prediction static branch。

 which is a programmer based branch prediction it's know programmer themselves can also annotate this one so that's the whole point but with that's said so let's let's go quickly to the yeah dynamic type of branch prediction so I'm just going to go quickly in the next 10 minutes to give some idea on the dynamic branch which you are going to implement in the lab and that's what going to form the base so okay so what the dynamic branch prediction is it's happening in the runtime it's not happening in the compiler okay so the advantages are that the prediction is based on the history of the branch so there is no statisticalally fixed things statically fixed hints in the compiler itself so however the branch is beh at the runtime you are going to predict in that way so by that adaptation it can actually adapt to the dynamic changes in the behavior。

behavioral changes in the branch and then obviously you don't need to have any static profiling with that you don't need to have any eyes or changes。

 everything you know becomes transparent under the hood。😡。

But then the disadvantages are you need additional hardware as you will see like we will keep on increasing the complexity of the hardware more than ever。

 right so。😊，So the easiest way of doing a dynamic branch prediction is the last time predictor so the last time predictor as it says that okay。

😊，Whatever that done has been done last time it going to do the same again right so if if it is。

Happening like this， so you can easily guess that there are let's say 20 branch outcomes written over here。

😊，So you won't predict anything for this guy but then you are going to predict all of this as taken which is correct and you would mispredict for this guy because last time it was T this time it's not taken so you would mis predictdt for this one but then all of them would be correct so two out of the entire 20 would be incorrect so that's the 90% accuracy right life is easy it's good we are going somewhere right but then the question is that you know but what happens let's say this sort of case right so it it's oscillating T n T T and T0% accuracy you cannot just simply do this okay so so what happens in this case this sort of branch the last time so what we do is a follow so we have the branch program counter which is identifying that branch instruction right we use this program counter to look up into the direction prediction let's forget about this part now because this is just a cache right so we use this branch predictor sorry program counter to look up into the direction predictionor the。

😊，In particular actually remembering one bit of information， what happened to this branch last time？

😊，So it would just simply look up， it would say that okay what was happening last time。

 it we just simply predict that one makes sense， so thats the easiest thing to do for the last time prediction okay。

😊，Now， I mean， we can we can make so so from the from this from this。

State from the state of this bit perspective what is happening is the following right so you have to possibly two states one is predict to be not taken another one is predict to be taken right so that's the state machine that we are designing now if let's say your branch predictor is saying that okay i'm predicting to be not taken or let's say start from there i'm predicting to be taken but then it's actually also taken so you are the next iteration you are also going to be taken you are going to predict to be taken。

Now from this let's say if you you predicted to be taken but then you actually saw it to be not taken then you would come to this one and next time you are going to predict not taken similarly if it is actually not taken it stays over there if it is actually taken goes over there right so that's a very simple state machine for the last time predict but as we said that okay you know whenever it it kind of switches the direction right so from taken to not taken or not taken to taken。

😊，Irrespective of how many times it was taken， Itked just simply switch the loyalty right so it was like let's say taken for 10 times and then only once it was not taken it's just simply switch So so the solution what is the solution let's add histor like let's add saying that okay how many times it was taken and then you would actually so you don't immediately flip your loyalty you would simply say that okay let's see whether it's not taken for two times then only you would go and predict to be not taken all let's see whether its it's not taken three times in a row。

 then only you would change the status So that's what we are going to do here So instead of having one bit of information you would have two bits of information So that's you know the kind of adding some histor let me let me give you some idea like how exactly that happen So this is also called bimodal prediction So this is the state machine of the bimod prediction so let's start with this one so let's say。

These so you are you are starting from let's say this state right so you are predicting taken。😡。

If the brands。Eventually became the to be taken and you are already already here fine。

 but then if you are predicted to be taken， but then the branch is actually not taken。

 then you are still giving it a chance that okay let's still predict it to be taken。😡。

But if the branch is again not taken， then you would go to predict to be not taken right so if this to this is essentially you are giving one chance before flipping。

😊，This to this again， you are giving your flip。😡，But then you can again come back if you see one change right。

 but then if you keep on seeing that okay， it's actually not taken， then you would start from here。

 go here， here and here， and then you would just simply keep on noing here。😡。

So what actually is happening is that these four states is as if that they you know if you are in this state you know that okay this state is literally telling you that it it's strongly not going to be taken similarly this is going to tell you that it's strongly not taken and anything in the middle it it's probably they are going kind of flipping to each other right so they can change the loyalty based on what the outcome is but if there is a historytoresis then they would either saturate here or sattuan there okay。

😊，So that's a you know two bit counter based prediction so as we can see that if you have this prediction so and lets let' us assume that you started with weekly taken so if you started with weekly taken then the first guy arrives you would predict taken and its actually correct。

😊，Now if if you go all the way here right so you would only have one misredition out of 20 so that's like 95% if you remember like the previous one we had actually 90% by accuracy so you improved but the good part is that in this case it's actually improving to we started from zero and it becoming 50% why let's say you started from weekly taken so the first IRs you would predict to be taken and it is actually taken so you're a correct prediction。

😊，Then the second guy arrives so you you actually started from weekly taken。

 you saw it to be taken so you became a strongly taken correct so now the moment you would became strongly taken for this one you would predict taken。

😮，But guess what it's not taken so it's a mispeddition fine so from strongly taken you came back to weekly taken for the third one you you are in weekly taken so you would again predict for were taken。

And this is correct， so every alternate taken would be actually correctly predicted you can you know do it by yourself。

 so that's becoming like 50% accuracy。😊，That's already improvement from the previous yes。

 how many levels make sense realistically。😡，Because I assume adding that's。Can help。

 can help can help but。You can try it out in the labs。You can try it on in lab， yes。

So we actually start with two bit counters， you can go for， let's say three bit。

 four bit counters and then see it in which way in whichgetation it goes。😊，Okay so yeah。

 so but then the question is that okay we started off from something but then we improved upon but is it good enough that you know the answer it's obviously not going to be good enough because you know 80 to 85 you can see the jump in the accuracy so okay so I'm going to go to more predictors and then we are going to stop just probably showing some you know。

😊，Slides on the most sophisticated ones。 So can we do better？ Yes， so what we can do is is like。

So the last time and the two bit counter predictions the one that we just shot it's actually the last time predictability so think of it in this way that it's not realizing know lots of the branches that that happened before like what happened to some other branch what happened to you know what's happening in the program itself so the first realization that you can have is that a branch outcome can be correlated with the other branch outcome I'm going to show in what cases that might be true so this is what we call a global branch correlation and then you can also have a branch outcome can be correlated with the outcome of many of its previous past so not only the past of some other branches but past of itself so this is what we call the local branch correlation so your prediction is actually dependent on your past predictions your past outcomes and your prediction is also going to be dependent on someone else's past outcomes why is that。

So let's let's start with the first one why the global correlation makes sense so let's say you may have actually code like this so if the condition one if this branch is going to be taken or if this branch is going to be not taken then you would know for sure that this branch is not going to be taken right so there is a correlation so similarly if this branch is going to be taken then this one or if vice versa right so both of them cannot be true at the same time right so so there is a global correlation in this sense right so that's all the global correlation so this is a actual program in you spec 92 workload with it which were hard to predict at that time。

😊，You know they can be done with the global correlation so what what we what the idea of the global branch correlation is that okay associate a branch outcome with the global taking not taken history itself。

 so what is doing that you are going to record the outcome of the branches not yourself but all the branches that has happened before。

😊，You see a branch you are going to update a register just saying that okay I have seen taken taken taken take branch another take branch another not taken branch and I arrived here now I'm going to make some prediction so that's what the implementation is going to look like we have the global history register so this global history essentially keeps track of the entire history itself like what happened to the all the branches previously not just yourself but all the branches and we are going to use this global history register to index the table of the branch outcome so let me quickly show you this one so so this is the global history register how it looks like so what does it mean it means that this is the current just the previous branch that you have seen predicted to be not taken and all of the previous branches are actually taken okay so that's the global branch history。

So you use this history to index into a table， this table is going to give you that 2 bit counter。

 it is going to say that okay if this history is the context，😡。

What you should p inside this table also there as I say like it's a two bit counter it's the same thing it's going to say that okay it's going to be taken or not so what you actually what we just simply did is that instead of you know。

Instead of just relying on the last time or the some histories input。

 you actually correlated with the global branch history。😊。

Okay so we will yeah and this was actually implemented in the this two two level predictor was implemented in Indian penium Pro which was you know one of the reason why this process became successful and yeah you have seen the figures like this every time so we would kind of stop here and we would start from the remaining part of the branch predictor from the next lecture and then we will go to some of the topics okay。

😊，Thank you very much。

![](img/283ef3c0c88f814f2fda85c77024e5d4_9.png)

You guys are going to。