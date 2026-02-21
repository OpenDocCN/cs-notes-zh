# ETHZ《计算机架构基础｜ETH Fundamentals of Computer Architecture 2025》中英字幕 p05 Lecture 5_ Prefetching II (Spring 2025).zh_en -BV1Xc19BnET7_p5-

![](img/5861a82bae60e02b9c4b2af158ce56df_0.png)

Good。Oh good live stream。Speak to。Hello， can you guys see me？Okay good。No。

 we still have three minutes though， I'll wait。This fell as usual。被上诉。是。嗯。是。不是。嗯。🎼Oh。🎼Yeah。🎼Yeah。

Okay。O good。Okay， I think we can get started well， if I don't fall here， that'd be better。

What of cables。Yeah。Okay， we're going to continue a very fundamental topic。

In alignment with the title of this course， fundamentalals of computer architecture。

 which is prefeting。This continues to be a very fascinating topic。

 which I think will continue to be that way for a very long time， I think。Just to jog your memory。

 we were covering many questions and prefeting what， when。

 where and how you're familiar with all of these right now， again， just to jog your memory。

And we're doing prefeting in the memory hierarchy， but we also discussed last time that this is really applicable to large scale systems where the memory hierarchy may extend。

😊，To somewhere else， if you may have memory modules that are far away。

 right disaggregated memory that's far away。And this is also a concept that's applicable to systems in general because you may have data that you want to fetch from somewhere in general。

 and if the latency of fetching that data is a polyne for the user， for example。

 fetching that data early to a closer place that's faster could be a good idea。

And we see this for example， on prefetching things over the network when you're accessing some web page。

 in fact some browsers do intelligent prefetching， if you actually access a web page。

 they try to figure out which links may be used which links you may actually click on next and they may actually start prefetching those links into the computer。

 so this is called web prefetching clearly and people employ these in distributed systems like the web。

Okay， and we were discussing this within the context of micro architecture and architecture。

 and we discussed software prefeching a little bit。

 we were talking about hardware prefetching today we'll pick up on some of the ideas that people employ in hardware prefeters。

😊，And then we're going to talk about execution based prefetchers， hopefully it'll be fun。

 and all of these are employed in today's systems basically with hardware prefeting being， let's say。

 the more dominant way of doing prefetching， we have a lot of prefets and hardware today。😊，And again。

 just to jog your memory because we may talk about some of these today。

 there are three major metrics that are used to cover prefeting or evaluate prefeting accuracy。

 coverage timeless， I'm not going to define them again。

And then always think about the additional bandwidth consumption that is caused by a prefeure because bandwidth is very valuable today and we don't want to waste it too much and cash pollution which could be induced by the prefeure in the end as I said last time the real metrics are execution time execution throughput of a single application or multiple applications and energy consumption。

 but these are auxiliary metrics that are important to potentially optimize your system so that you get good performance and good energy makes sense right？

😊，Okay， if my execution time is not good， of course， I don't care about accuracy potentially rate。😊。

Okay so we were talking about hardware these are the last slides that I covered in the last lecture we were talking about stride prefetching。

 I will not cover that again， but this is a very simple prefeter where you detect a single stride and record it and basically if it's stable so you build some confidence in the stride and if it's stable you use it to predict the next m memory accesses using that stride and there are multiple ways of determining the stride when it' instruction based you basically detect the stride based on the program counter and this determines your implementation also we discuss this briefly and the other is memory region based where you can actually detect the stride by partitioning memory inter regionsions and figure out whether you have a stable stride in each region。

😊，And we said that stream prefeting， the stream buffer is a special case of memory region based strip prefeting where the str is essentially one。

😊，Hopefully that makes sense， also right。Okay， and we discussed some tradeoffs between these two which I'm not going to discuss again。

 you can refer to the last lecture and both are employed in existing systems。

 so if you look at these are actually some seminal papers that introduce the concepts this is from SC 1991 as you can see this is a program counterb or instructionbased strip prefetching paper and Intel employees a version of this。

 a variant of this to prefetch into the L1 data cache。😊。

And this is the stream prefeing paper that we discussed last time。

 which also introduced some other concepts like victim caches， which we're not going to talk about。

 but if you actually take the DDCA course， we talk a little bit about that。😊。

Which is also employed in existing processors。Okay， this is where we stopped last time。

 any questions so far from the last lecture？Does this sound all interesting？Yeah。

Maybe you can there will look better prefes than what we have today。

And they will have impact because if you do up something good in this area。

 you can immediately have impact in hardware as long as you produce hardware， of course。

 at some point。😊，Okay， so this is what I was where I stopped last time。

 so okay you can detect strides， you can detect streams。

 but one of the issues that we have in real systems or real applications is that，😊。

You don't have perfect stridees。Meaning sometimes you have some locality in a particular region of memory and you don't have a very good way of capturing that so people have designed prefes that I call as locality-based prefets these are actually very interesting prefets that are a bit thin with intensive and it's actually the best description of it is really in our feedback related pre-fetching paper I'm going to give you the basic idea very quick i'm not going to go into a lot of detail and implementation because we're going to look at other ideas also here the idea is maybe I'll use that thing I don't know if people can see it or should I move it this way。

You can decide I'm going to。Do this one， but it's better described this way。

 this is directly copied and pasteed from the paper。So you divide memory into regions again。😡。

And based on the memory address， this is not a program counter， this is a memory address。

 you determine a region and based on a region， if you get a miss in a region。

 let's say this is region X。And x is really the top ands of the address， right？Okay。

 this is this is the first time you're writing here and I don't know if you can see anything or。Okay。

 people who are close bike can see better probably。But basically。

 you monitor what kind of access does go to this region Okay， so if you get a miss， for example。

 in this region， let's say address A goes to region X。If you get a miss。

 you start tracking something unless let's let's let's zoom out this thing。 What are you tracking。

 You needs be say， oh， I got a mis on address A。😡，Now I'm going to look， let's say， I don't know。

 a minus M I just made up， these are all congur values。I'm going to create a， let's say。

 window in which I'm going to monitor accesses。😡，And then let's say you get an access to。

A plus3 okay that's a miss that could be a mis or access doesn't matter well depends I guess it depends on how you design the prefecure but let's assume that it's an access then now you have an idea that okay maybe what I'm doing is I'm doing some sort of locality based accesses to address a first and then a plus3。

But I'm still not fully confident so I'm going to continue monitoring this thing to decide what direction that the processor might be going。

 and then let's say you get an address to access to address a plus8。

Clearly there's no easy stride over here， but now I have a confidence in the direction。

 so maybe my direction is let's say positive right it's growing， the access address are growing。😡。

I could still wait， maybe after some point I get access to address a+4。😡，Okay。

 now I'm even more positive that I'm kind of doing some growing this way。

 maybe some access are reordered because a lot of order execution， et ceter。😡，Now， at some point。

 the prefeccher says， okay。😡，I think the processor is going this way， so I'm going to。

Set the direction in this region to be like positive， meaning growing this way。

 and then I'm going to do something to actually monitor this positively moving region potentially right。

So I change this region to maybe a to I don't know， actually。

 it depends on how you design the prefeture， but one of the decisions that you may make could be。

 I'm going to actually prefetch everything over here。😊，Let's this a very aggressive decision clearly。

 and then I'm going to move the region that I monitor， so let's say I have IA A+ M。😊。

So I prefetch everything in between thinking that I'm going to access this part。😡。

And thenm I keep monitoring AA plus M okay， now you're confident that there's something happening in this region。

 so you start prefeting in this region and you kind of fill the buffers such that you pre fetchtch a bunch of things。

And then if you get another axis in this region， let's say address a plus1 and you say okay。

 maybe I did the right thing， so I'm going to prefetch more address a plus m plus 1。

 and there's a plus m plus 2。Okay。And then at some point。

 you move the window in a sliding manner such that you keep monitoring the region that you actually that that you think the processor keeps streaming towards。

Does that make sense， So this is the basic idea of not stride it。😊。

wayay of capturing some locality in the stream that the proor is moving towards and this actually employed in real proors。

 I've actually designed part of it when I did work at Intel for example。

 and these are quite effective。😡，If you make the decisions right， okay。

 I think you're going to switch to that。So there are many design decisions over here clearly what I just described is very bandwidth intensive rights prefetching everything。

 so you can decide for example I'm going to prefech the last five things but I'm going to still monitor these things and I still move forward you can augment this with some stride detection right maybe you look at some potential strides over here and prefetch only those strides that you see。

😡，So呃我。Now you have the basic idea， there are a lot of design decisions。

 these are some results from Intel this is when people used to write papers about their processors。

 they don't exactly describe this prefecture very well in that paper but I know that it's this sort of prefecure and what you get as significant performance improvement as you can see。

😊，And people have improved this with better stride detection， better prefeting feedback techniques。

 and we have actually described this sort of prefetcher in this paper and also described ways of throttling。

😊，Aggressive prefetures because this could be quite aggressive if you set the parameters to be aggressive。

Makes sense。And there are many variants of these techniques you can find in patents。

 if you're interested， you can ask Rahul about that to make this more accurate， to make this better。

 to make this， for example， one thing you could do is throling right if you figure out that your prefetchers is not being very accurate。

 you can throwl it to be less aggressive， meaning prefetch less， make your windows smaller。

 making your window smaller is also enabling you to be less aggressive for example。😊。

So there are many techniques that people have developed on top of these。Okay。

 so that's one example of an relatively effective prefechction。😊，What about others。

 so we've discussed complex basically we've discussed simple patterns。😡。

If you've discussed this locality based prefetures， which is not on this slide。

 we can do complex regular patterns right if you look at this what about prefeting this sort of access patterns right clearly this is prefechable if these are the deltas from the previous address。

 it's not a single strike， but it's a repeating delta pattern so you do address basically deltas from the previous address is always123。

1，231，23 right。😊，And then there are irregular patterns which may be much more rent。

 this is where execution based prefeting is going to really shine in the end。😡。

Let me give you another example over here， this is a Delta pattern。

 deelta meaning Delta from the previous address that you've accessed。😡，And this is a real workload。

And you can see that this deelta pattern has repeatable portions， this portion is repeating right。

 Yeah， plus seven minus6 plus 12，6 minus5 dot dot dot， and that repeats over here。

And you could capture this pattern， there are various ways of capturing it again I will not go into the implementation details there's you can think about ways of doing that。

 this complex but predictable and this is one paper from Intel and Texas A&M that talks about it。😡。

And the key idea is given a history or signature or pattern of stripes or deltas。😡。

Learn and predict what's right or what deelta might come next or what deltas might come next right？😡。

You don't have to do a single one。So for example， if you see pattern 7 minus 6， 12。😡。

You predict six will come next if you see pattern minus612，6。

 you predict minus5 may come next and it can increase the ground la of how many things you predict next。

 of course。😡，Okay， and then again， you need to keep track of confidence somehow， so for example。

 this the history of stride， this is your prediction， you may have some confidence over here。😡。

At some point you start prefetching， but your confidence becomes lower and over because you actually prefetch based on the delta patterns that you predict right。

 not necessarily what you see and at some point you decide to stop because your confidence is too low。

 right？😡，Again， there are multiple ways of doing this， I'm not going to go into the details of it。

 but there are a lot of interesting papers that talk about this。

 so this is called actually a Delta correlation prefeture。😊。

It's really a special case of what I'm going to discuss next at correlation based prefeching。

 so people did not come up with Delta correlation initially these are relatively new concepts。

 let's say you really correlate the dels what we're doing is really if we see a pattern of deltas we say that oh it's correlated with the next pattern of deltas right next one delta in this case right？

😊，But people actually started with addresses， and I'm going to talk about that next。😡，Any questions？

Okay， so this is， you can consider the following history of cash block addresses these could be deltas also by the life。

 but I like the addresses here because the originally it was proposed this way。😊。

And the way it's originallyly proposed is very difficult to implement。😊。

Because it requires a lot of storage of addresses once you go to Dltas you're actually much cleaner that's why a lot of pros today do deltas okay but let's take a look at addresses this is ABCD clearly there's some pattern over here right after you're referencing a particular address。

 some addresses are more likely to be referenced next right。😡，And you can guess right？

And then you can actually form a graph called a Marco model that examines this stream of accesses and forms a Markco dependence chain that basically says。

 what is the probability of addressB coming after UC address A？😊，Clearly。

 you can form the sort of gas。Like easy， basic question broadly。For example。

 this says after you see F， the probability of seeing E is 50%。

With's 50% probably you're going to see。After you see address E， you will always see EA。

 so that's a very strong connections over here as you can see so maybe you can predict you can always fetch a after you see E。

 maybe you're too late。😊，But it's possible。Okay， so this is actually proposed by this IsA 1997 paper。

 similar ideas were actually around with technical reports also at the same time。

It's a beautiful paper， I recommend people to read it。

The idea is to implement this and record the likely next addresses after seeing an address。

So for example， after use。So once you saw address A， the next address were BCT， record them。

 if you see address A again next time the processor access it， prefetch BCCD。😡，Makes sense。

 just assuming that the processor is doing something like this。😊。

So if here you can see after I see address A， I access BCD。

 I record this correlation and next time I see address A， I prefetch BCD。Fine。

 maybe it'll be useful here， right？Okay。So it gives you an example。Okay。

So you can to increase coverage， of course， you may want to prefetch more addresses。

 clearly this is not good for us accuracy as we have discussed last time。😡。

But you can also improve prefetch accuracy by using multiple addresses as keys。😡。

So as opposed to prefetching BCd after seeing only a， maybe you say okay， after seeing A B。

 I prefet C right clearly there's an accuracy versus coverage tradeoff over here。

 your accuracy will hopefully improve because you wait until you see A and B。😡。

And you prefetch only one in this case C now you correlate。

 you say that addresses A and B are correlated with C coming next。

 so there are clearly many different design choices over here， how many addresses do you use as key。

 how many addresses do you use as value or something to prefetch and do you use addresses versus deltas when this paper propose it it was all addresses。

😡，Okay， so these are also called Marco prefettures Delta or correlation prefetures。

 and more generally address correlation prefes they're correlating on addresses。😡。

Let's take a look at this particular prefetuate the advantage of this prefetuate can cover arbitrary access patterns right now you're not limited to strikes。

😊，Any arbitrary pattern could be covered over here like linked data structures。

 even streaming patterns right， if you're streaming or striding。😡。

You can still cover it as long as you go back to that pattern， right that's the key。

 so that's going to be the disadvantage。😊，But it won't be very efficient in covering the street str pattern because with a strip prefeer you say。

 oh， I see address a and then the strus plus 4， that's very efficient in codingding。😡。

Here you encode the same thing as A a plus 4 a plus8 a plus 12 a plus 16。

 and for each of those you have a correlation table lengthing。

 now you can see how expensive this can get right。Delta correlation that fixes that by the way。

 if you do address correlation then you have a separate entry for all of those。

 if you do Delta correlation，😡，After plus four， you see plus four， for example。

 right to correlate that way。So that's the beauty of Delta correlation。

But Delta correlation will not be able to do arbitrary as much。

 right you still need to predict the predictable delta as where if you look at addresses。

 you could be arbitrary as long as you repeat that thing。Okay， so essentially， if you do addresses。

 correlation table needs to be very large for high coverage。

 recording every mis address and subsequent mis addresses is infeasible in the end。😡，Infeasible。

 I mean， there's nothing that's infeasible。😊，It's all about a cost in the end。

 right everything can be implementable at some cost， infeasible in the sense that it's very。

 very costly。😡，Right。It's kind of low timelineless because look at is limited since a prefetch for the next access or miss is initiated right after previous。

 but there could be ways of overcoming that as we discussed。

 and these can also consume a lot of memory bandwidth。

 especially when Marco model probabilities are low。😊，Okay， and maybe。Very importantly。

 it cannot reduce compulsory misses， right？This is， again。

 you cannot reduce compulsory misses if you're doing address correlation。

But you could reduce compulsumous if you're doing Dlta correlation。

 so what does that mean what is compulsoryous， essentially you have never seen this address before the processor has never touched this address。

😡，And you want to prefetch。Clearly， with the address correlation。

 you should have seen the address before so that you could correlate and then you could predict it。😡。

Marco prefetures as they're proposed， unfortunately they cannot cover compulsory misses。

 but Delta correlation prefettures， if you're actually correlating on Dltas。

 you could cover compulsory misses because deltas are deltas。

 you don't have to see the addresses associated with the deltas。😊，Okay， so hopefully that's clear。

 but this is actually interesting to think about because initially these were not implementable。

 but once people moved to the Dlta correlation。😊，With some tradeoffs， of course。

 as we have discussed， they became a lot more implementable over time。

That's the interesting thing about evolution of ideas， but I still credit these old papers。

 199090s papers for the original idea， right these are correlation based prefeting papers。Okay。

Any questions？We don't want to。Maybe we'll have a better way later， don't worry about it now。

 I'll try to be more careful。Okay， so let's talk about some other ideas that have impacted processors I think these are implemented in existing processors right in fact people have done security attacks on these things recently this is another idea that when it was proposed it was people thought it。

😊，Maybe it's too intensive to unimplementable， but now we see it in processors。Okay。

 basically the idea over here is to design a specialized prefeture for pointer values。😡。

And the idea is actually very creative， I think you identify the pointers among all values in a F cache block and issue a pre fetchtch request for it。

😊，What does this mean you basically have some hardware and it's proposed in this paper originally。

 you well maybe I will say you basically have some hardware that scans the cache block。

 you bring a cache block into the cache and you scan it。

 you say you have some hardware that scans it and figures out which values over there are actually pointers。

 meaning addresses。😊，That you could later dereence， right？😡。

And then you go and issue a prefetch request for some of them or all of them。

Some or all will depend on what confidence mechanism you have。That sounds good， right。

 of course this requires for you to know what are pointers。😡，If the software encoded those。

 if you had some tagging in memorymme and the software said， oh， this value is a pointer。

 this value is a pointer， this value is a pointer， it's easy to do。😡。

But this is a pure hardware based mechanism， and the idea is to identify pointers dynamically in hardware。

😡，And the way they identify the pointers is by looking at examining all pointer size values in a cache block。

 64 byte cache block， maybe your pointers are 8 bytes right。

 let's say you look at all of the eight byte values in an aligned manner。😡。

And you check whether the top， let's say， 12 bits of each of the eight bytes matches the top 12 bits of the cache block iders。

😡，Now， what does this mean， You look at it in the virtual address space， of course。

 so it basically you basically check whether the。😊，Whether the eight byte value looks like a pointer。

😡，If the top 12 bits matches， that means maybe。😡，This virtual address that I use to access this cache block。

😡，Is also a virtual address， maybe this8 byte value is also a virtual address because the top 12 bits of the virtual address that I use to access the cache block matches with the top 12 bits of this value。

😡，I think this is very clever， it may not be perfect。

 but it's a clever way of identifying pointers and hardware。😡，Not perfect。Okay。

 so the huge advantage of this is。😊，Now you don't need to record anything。😡。

And literally this is true， except for confidence if you want to have some confidence。

There's no need to memorize or record past addresses， right？😡。

Because you just scan the cash block that you're bringing or you scan the cash block that are in your cache if you wish。

 and you can be more clever， I think there's roomoom for more creativity and innovation in this area。

😡，It can eliminate compulsory missile so' never seen pointers， basically。😡。

Downside of it inscrimly prefetches all pointers in a cache block。

 at least the way it's proposed in this work。😡，So okay， I think I've already said this。

 you compare address size values within a cache block。With the cache blocks status。

 if the most significant fewbits match， then you declare it's a pointer。😡。

So let's take a look at this this is done in the virtual address space。

 potentially you could imagine doing it in the physical address space。

 but your mileage probably would vary right so basically you bring a cache block。😡。

So you access L2 cache this is the virtual address that you access the L2 cache with。

And then you bring the cache block associated with that address into the cache。

And then you basically look at all。😡，Pointer sized values。And then compare。The top 12 bits。

Of those values that you see in the cache to the top 12 bits of the virtual letters of the cache block。

 and in this case there's only one match as you can see over here。

And then you issue a prefetch for that address。And then when that cash block comes back。

 you can do the same thing for that cache block。😊，And then prefetch a point when that cash block comes back。

 there could be multiple， you could basically keep doing this in a depth first manner， right？😊。

And that determines the aggressive of your prefeure。

 that's one thing that determines the aggressive of your prefe。

 the other thing that determines the aggressive of your prefe is how do you determine the pointer addresses and which of these pointer addresses do you actually generate prefets for？

😊，Okay， so that's a beautiful idea， as you can see。😊，And again， it was not。Not exactly。

 at least not publicly implemented when it was proposed。

 but it iss implemented in Apple systems today。Maybe more systems also but。They cannot be disclosed。

Okay。Okay so this is clearly we have done some work in this area also this is part of Iman Abrahimi thesis essentially one of the issues here as we discuss is hardware does not have enough information on pointers and how they're used semantics of those pointers right but software does and it can profile to get more information and the idea here is relatively simple it's a bit more complex than the original idea。

😊，You'd have the compiler， compiler profiles or analyze the code and provides hints as to which point your addresses are likely useful to prefetch。

😡，And hardware uses these syns to prefetch only like the useful pointers as opposed to indiscriminately prefetching everything。

😡，And where this idea is really useful in my opinion is having some semantic information。

 you don't even need to do some profiling， you just need to have some information about the semantics of the code。

 so for example， if you look at this code， what this code does is， it does a hash lookup right？😡。

It's you basically determine a bucket in the hash table and each bucket in the hash table is a linked list。

😊，And。Assuming that your linked lists are long， which is usually the case in hash tables。

 each bucket has a long linked list。😡，You can just by looking at this。呃。Again， semantically。

 say some of the pointers are going to be more likely to be accessed than other pointers if I look at this。

😡，I'm going to access the pointers to the next node more likely than I'm going to access pointers to the data。

😡，Makes sense， right？Because as the property of the hash table， you index hash table。

 you're looking for a key。😡，The probability that a key matches is low。

 it's not going to match all of those hopefully。😡，Because you usually have a single single location matching a given key right so if you have a million entries over here which is probably not a good hash table but okay1 thousand entries not bad maybe maybe you don't do a link test fine but the basic idea applies to other data structures also you don't want to prefetch these in general right you do want to prefetch these because you're probably going to do some pointer chasing on the next addresses for the next node okay that's the idea basically。

😊，Either the compiler or the programmer or someone who understands the semantics of the program can mark these pointers。

 first of all it can identify the pointer， and these are all pointers and it basically has a hint at saying that prefech this pointer if you're doing a content accessibleable prefetch that's the valuable thing for you and don't prefech these。

😡，And if you okay， I'll go through these animations， some of these are broken。

 This is how things are laid out， for example， this is。A way of laying out the linked list over here。

You have clearly keys， data one pointer， data two pointer and the next key data one pointer。

 data two pointer and the next。😊，Con a baseline content addressable content directed prefetcher may prefetch data one。

 data2 and next。A cash lines is pointed to by these。😡，So it can prefech six things。😡，Over here。

Hopefully。A more efficient one prefetes only the next， right？

Maybe this next also I assuming it doesn't belong to something okay， and also you can profile more。

 right？Okay， so many the matches over here are broken， sorry。😡。

I don't know what happened to these animations。But hopefully you got the basic idea。Not your fault。

They've been broken for some time and I couldn't fix up。Okay， any questions？

And this is a paper that describes essentially this idea。

And I think this is a very good direction in the sense that this enables。

A more intelligent way of prefeting right here you don't hardware actually has some capability to do prefetching。

 but it's directed by the software。😡，It's more complex clearly because software needs to provide more information。

 but if you have the ability to do that。😡，That's great。And in some systems。

 if you coes the compiler and the hardware together。You actually have the ability to do that。Okay。

 now let me give you basically today's systems are a combination of many prefets。

 so we have hybrid hardware prefettters， clearly a single prefetcher cannot cover all different patterns。

 so we use multiple prefes to cover many different memory access patterns。

 very similar to hybrid branch predictors that we have seen in earlier lectures。😊，Clearly。

 this way you get better prefetch coverage。😊，Potentially a better timeliness。

As opposed using a single prefeture to cover everything right unfortunately you get more complexity now you have many design optimization decisions like which prefeture to prioritize for example and how to throttle multiple different prefes by the way this paper talks about some of those issues with multiple prefes。

😊，诶。You get more bandwidth intensive prefeting because if you have 10 prefets trying to cover 10 different patterns。

😡，It's clearly more bandwidth insa than a single prefecure， potentially。😊。

And also prefetcherers can interfere with each other， they can content。

 they can pollute and you need to manage memory access from each prefeure so there's a lot of work actually that covers。

😊，This I'm going to flash some papers later on because we don't have time。

 but you really need to manage the prefetures in the end？Thoughts， anything to add your？

No not yet okay now I'm going to talk a little bit about your holdss work because people have more recently been looking at machine learning during prefettures also these are called self optimizing prefettures。

 but this is one example where I published this paper a few years ago at microcro。😊，Essentially。

 we're going to use reinforcement learning to guide the prefetcher to decide which offset to prefetch after you see an address and reinforcement learning is。

😊，An algorithmic approach to learn how to what kind of action to take in a given state or situation to maximize some reward。

And we are all enforcement learning agents as humans， essentially we interact with our environment。

 we do something and we get a reward or punishment。

 and based on that we change our action accordingly， right？So the next time， in the same state。

 you take a different action， perhaps to maximize your reward。So you observe the state as an agent。

 you take an action， you get a reward， this could be immediate or delayed in prefeting。

 it's usually a delayed reward actually。😊，And you store some true quality values for every state action pair。

 you can generalize the state， of course， right you need to quantize a lot。

And this Q value indicates the expected return for taking an action in a given state。

And given a state， you select the action that provides the highest Q value。😊，Okay。

 so essentially you can consider the prefeture as the agent。😊。

Now the designer needs to design whats figure out what state checked。

 the state could be the features of a memory request address A， for example。

 the program counter right。呃。We're going to talk about this a little bit more and then action could be anything in this particular case。

 the action is restricted to a prefetch from address a plus offset so the action is what is the offset that you're going to prefetch from okay？

😊，But you can imagine different ways of doing this also， not necessarily based on offset。

And then you get a reward based on the action you've taken。

 did I prefetch the right thing that is used by the processor at some point。

 so you need to figure out whether what you've done the action actually was useful to the processor。

😡，For some definition of usefulness in this case， you think about what is usefulness right does the pro needed is one。

 the other thing is timelines potentially right so you need to keep that take that into account and you get a reward value based on that right。

😊，And there are other things also that you may need to consider like pollution， et cetera。Okay。

So you design the system， so what is state， let's take a look。😡。

So this could be any K dimensional of vector features of course the more dimensions you add。

 the harder it will be to keep the state and also make decisions so in this work we have several control flow features as examples program counter of the instruction that generate the address。

😊，え。Last branch， for example， bench program counter。

 last three program counters that you've executed， kind of an indication of the path you're following in the program。

 it could be many other things that you can add over here， right？😡。

And data flow examples could be the cache line address that you're accessing。

 the physical page number， the deltas that you've seen recently， let's say。😊。

Now there could be many things。And I think in the end， don' we don't have all of these。

 but the paper describes exactly so what you do is you basically。😊。

Decide what could be useful and then eventually figure out what are the state with a lot of simulation。

 eventually figure out these are the state features that I want to use based on which ones provide the highest performance。

 for example， some optimization value this requires a lot of iterations in simulation of course right or training let's say to figure out the state。

😊，It's called feature selection in the end， a lot of it can be automated。😡，But in the end。

 someone needs to come up with the features and I think there's a lot of potential over here in coming up with different features that people may not have considered so far。

That's a hint for future research。对。Okay， so action action again action is also what you want to do in this case the action is restricted to selecting a prefetch offset O given a demand access to address A。

😊，So the action space is also further restricted within a page。

 so you may have 127 actions in this range over here for a machine with 4 kilobyte page and 65 byte cache light。

 and you can also decide to have a zero offset which means that you generate no prefech。😊。

Maybe none of these offsets are useful， you don't prefetch if you're doing random access。

 for example， hopefully this prefetcher will default to no prefetch rates。

 always selecting address you。😊，And then you can prune the action space by， for example。

 figuring out what offsets are more likely in programs， of course。

 once you start pruning the action space， your adaptability reduces in the prefech because you may actually remove an offset that's actually needed by a program right。

😡，Okay。But again， you can imagine other actions， for example。I don't know how to implement this。

 but you can imagine an action that selects a memory region to pre fetchch from right potentially plus enough。

😊，It's good to think about these things because theres a lot I think there's more opportunity in this direction and prefetching。

Okay and then there's a reward which defines the objective and in this case there are two metrics that could well there may be more metrics that could be considered。

 but prefetch usefulness is one metric that is considered， whether the prefet is accurate。

 late out of page， and then some system level feedback。

 how much memory bandwidth is being used currently， how much cash pollution is being caused。

 there could be energy。😊，We don't consider everything in the paper， but some things。

 as you will hopefully see in the next slide。The system level feedback that PTtaA uses。

 this particular paper uses memory bandwidth， but again， you could configure things to be more。

 let's say。嗯。take into account more things not just maybe bandwidth with users right it could be interference also directly some interference measure of interference okay so this is the basic Pia configuration over here again these are designed based on automatic design space exploration if you're interest talk through a whole more or read the paper and these are the two features that are decided on at the end PC plus delta and sequences of last four delta so you can see how important delta is over here。

😊，So Delta correlation is still like in effect in driving this sort of learning based prefection。

And the actions are pruned to 16 prefetch offsets。It turns out these are the office that are。

 let's say， maybe more popular in programs。😡，呃。And of course。

 the benefit of pruning these things is multiple right if you prune the state and actions now what we're trying to do。

 remember the bigger goal is given a state， you want to decide which action to take。😊。

So for every state action pair， a quantized value， you need to have an idea of what is the expected return。

 expected reward， which we're going to get into。😡，Meaning that you have a state action pair that you use to index some structure with。

 it could be a table， it could be a neural network。In this case it's a table， regardless。

 if your state space is large and action space is large。

 that thing will be more complicated than hardware， you need more space to store it。😡，Okay。

 that's why pruning is a good idea， but pruning always has the downside of maybe you're missing something over here and maybe also you're missing something over here。

 you're not going to prefech up。😡，Okay， these are the rewards。

 I guess I don't tell the rewards over here， but for example， if your prefech is accurate and timely。

 you get a large positive reward in the basic configuration。😊，呃。If your prefech is inaccurate。

 you get a large negative reward， right？😡，So if you're interested， you can read the paper for more。

 I don't have all the slides over here。But reward function is also important so in this particular case it's really important to design all of these I think。

 but reward function is really important， so if you want to make the prefeure let's say more aggressive。

😊，You may want to。Reduce the negativity of the rewards that you receive if you're inaccurate， right？

Because that says that if you're inaccurate。You're not punished that badly。

 meaning your rewards are not as negative， so you can be a little bit more aggressive。

Does that make sense so by changing the reward function you can customize the prefecture for different levels of aggressiveness and potentially you can customize the reward function to the workloads that are executing this is easier to customize this may be also potentially customizable actually I think all these these two can be easily customizable this may be a little bit harder to customize but you could imagine having a configurable prefeure that all of these are customizable and then you select based on the workload that's executing。

😊，I'm giving a lot of future work ideas to people who are thinking in the right direction， let's say。

Okay。So I will not go into this detailed overview， but this just to give you a flow of this。

 this is a table based。😡，那。Reinforcement learning mechanism， it's very。

 let's say classical reinforcement learning is's not deep reinforcement learning。

 which is also interesting， but deep reinforcement learning requires neural networks。😊。

Whereas we want to get a Q value relatively quickly。

 but it's still good to explore potential neural networks in this case as well。

 so the idea is to have this Q value store which requires a Q values for all state action pairs in a quantized manner。

😊，And then you have an evaluation queue which is a5 a Q of recently taken actions。

 what are the prefes that you generated using this prefeure and you put them in the evaluation queue because you want to have some idea like on whether the processor is going to use them at some point。

😊，So when you get a demand request， you put into the evaluation queue and then using the demand request。

 you generate a state vector， which is essentially。These two features。And using that state vector。

 you look up this Q value store， you index it， there's a indexing mechanism using some hashing， et。

And then。Based on all possible 16 actions， you figure out which action would give you the maximum Q value。

😡，And clearly we're going to update these later on so that you keep this is online learning in the and you learn online。

 which which in a given state， which action to take and those Q values are updated。And based on that。

 you generate an offset value， which could be zero。😡，Meaning you don't generate a prefetch。

And you insert the action and the state action pair in the evaluation queue so that you can later update the Q values associated with the state action pair and the reward that you determine based on the usefulness and the memory bandwidth usage of the prefetch。

And when this gets to the top of the5 or Q， you evict the entry and update the Q value store。😊，Okay。

So when a prefetch fill comes， you set the fill bit。And clearly。

 you check whether it's used or not by the processor。O。

This is also all open source so you can actually build on it in your lab actually， my next lab。😡。

I don't know if people are going to use PTia， but they could compare to PthA because it's all open source with the same infrastructure。

So your next Linux lab will be on prefeting。But you will not implement Pthia because it's all open source。

 there would be no value in implementing that， you'll implement something else。

But you can compare it to Phiia。Okay， so let's take a look at the performance of this。

 essentially this shows the number of cores and this shows the speed up over no prefeting。😊。

One a number of workloads average， and these are some prefes， some of these are offset based。

 actually all of these are offset based and spatial right？

And essentially you can read about those also， there are papers。

 there are nice papers that are written on this topic。

 and you can see that PTot performs at the time 2021， all of those prefets。😊。

And performance benefits increase with core count in the end， so at higher core counts。

 you get better performance。Okay。This is a more interesting graph， perhaps in general。

 it's good to look at what is your memory bandwidth that's available。😡。

to a workload and how well are you doing based on available memory bandwidth so this is clearly a scenario where things are very constrained memory bandwidth that's available to a single core is very low。

 but there are real systems that look like that I guess AMD thread report。

And this is our the baseline that we use， which is like more forward looking than existing CPUs over here。

 and you can see that different prefes。As bandwidth becomes available。

 different prefets perform better over the baseline baseline is no prefetching as bandwidth is lower most prefe is the great performance as you can see Pthia is kind of on par with baseline。

😊，But as bandwidth becomes PTia is better than all of the other prefes。

 but this is a good example of the bandwidth available。

 so with better management of prefes you can actually pull these prefetures also higher potentially right that's the goal of that feedback directed to prefeting paper and a lot of the feedback directed prefeting papers that were written in past years。

😊，Okay， so。And as I said， this is all open source， you can find online， you can modify it。

 you can develop better ideas compared to it。And if you actually come up with a good idea。

 you could publish it and you could actually impact real products。

This is real actually this is not fake have we have done this many times I've worked on prefetching for many years from actually my first one of my first projects was on prefetching like figuring out how to how to modulate a prefecher like this and I have a patent on that topic but many ideas that we have developed have been actually incorporated in the real products I'm going to talk about something else soon that's also incorporated into products but there's potential for real impact and relatively quick impact。

😊，Here and also the interesting thing is relatively quick impact usually comes from non fundamentalal ideas。

😡，In my general opinion， here you can actually have a fundamental idea and you can still have relatively quick impact。

 So it's not like you tweak some software with well known mechanisms。😊。

And you get very good performance that's easy to do clear， that's many people can do it。

 but as a researcher， your goal is。To balance。The tweaking you do and the impact that you get right tweaking you do should probably be fundamental if you really want to have a longer term impact on things。

 you can come up with a fundamental idea and you can actually have a real impact on products。😊。

We can think about that a bit。Okay， so Rahul is all here giving a talk， but you can talk to him。

About the ssa。Okay， I would also recommend before we take a break， I would also recommend this。😊。

Book on reinforcement learning， I think this is the second edition these guys actually won the touring award this year finally I think they well deserve it。

😊，呃。I guess you win the Turing Award when you're 90 years old like Harry Su。

 but essentially it's a beautiful paper， not paper book that talks about reinforcement learning and all of its bells and whistles and I definitely recommend it and it's also fully open source。

 but you can get the PDF。😊，And one thing that I like also。

 in addition to many other things over here is but they actually feature one of our papers optimizing memory control as one of the nice applications of reinforcement learning is a paper that we didn't describe。

 it was an ISA 2008， which is self-opimizing memory controllers。

 essentially using reinforcement control to design a memory controller。😊，Okay。

 this is a good place to take a break， we're going to continue with prefeting and feel free to come up with questions so we're going to start I guess when the bell rings。

😊，Okay。Yeah。I don't know if it's possible。Yes， maybe it's from here。Yeah maybe。整天都又不知道。lookで。Oh。

 yeah， maybe we spot the laptop yes also sorry。disconnectThat one okay， I think right。don't tripYeah。

 I don't trip on that one。 I took on this one yeah。I think yeah I saw it's much better。

 I could still trip on it than if I move over there。

 but I think the likelihood that I'll move over there is lower now Yeah， well。

 probably I won't do it for the rest of the you know。😊。

But at least it's better right now because it's much lower because it was higher earlier。

 but I can step on it like this， which is fine could could remote okay， Yeah， I don't think so。

 I mean， ideally， you have to connect to this without the table right。

 remotely if this was do capable， for example， what it's That's too much to expect from here。😊。

Because if we if we need closure， it's less than than maybe we dont drink。

I think it's fine right now it's much better than before thanks。要还是要加还。

I replied to your mail last night and I also recommend your recommendation。那 also the。

The interaction， they see that。嗯 so诶 apart from。The and now the， so maybe。rememberAs someone else。

So you mean this it also on your， yes， yes， the name it doesn't contain test。That's aMa doesnt Okay。

 that's someone else。 you'll figure it out Okay， that's a scalable graph processing paper。😊。

Okay you cut the other。配份 simple分。we can discuss more thank you。对呀。谢续。

But control snow has switched this year。Work three。I yes。I yeah。我不以前。The word election。对。

That's what we talked。Because Okay， yes， and I just want to do a confirm you if you think that my course。

 Yeah， I think it。 Yeah， looks good。 And we can always modify。 Yeah。

 later also of course become available or not available。

 seems like a good first start based Okay interested computer architecture architecture。

 Yeah big question was like the easy thing for me to choose like we have a lot of cheap design I already gonna do all of that。

 So the question is， what do I do couple of that。 So combine them and actually get something useful and that's what I wanted to ask。

I mean there are certainly compilers course okay， so I't take a look at that don know if take a look we can modify that's probably the only one to that at this very interesting but I think theres so much more around it can talkm。

Does't seem to change a lot。So maybe this is an issue different。



![](img/5861a82bae60e02b9c4b2af158ce56df_2.png)

And the number of perceptron right now I'm I'm at 2048 perceptone 62。

ItsThis is long and the training threshold I support for this， which apparently。这条。

ちょ to tell from it out。Whether maybe something wrong with this next one， but I don't think。

 so this one。あ最。Reception of weights， I update。Yeah want to is。嗯，哎呀嗯。That should probably also work。

I am I看。One bit to my branch is 6 per bit。Is an indicator whether the set should be trained or not for。

So either it is with is set， which is just set on based on。You。My prediction is。

Both the training thresholds。Wait， actually one second。say。I think that is a mistake。

It should be below Okay， I think I pump。How long my PC at think about minutes。

I'm running it on all course Okay Ver。hot better。Wait， let's see it。

 prediction has to be below loaded for training threshold or about the negative the。我 don wrong。

So you activate twin， that's just two apps。嗯。I。那下来这些。It was definitely wrong before。

So that might have been an issue。呃 running the MOP。It's true I means。

It's slightly above the past two results。based on almost all papers that I've read。

 it should be slightly better。So it's not slightly， whatever its slightly。

 it's like to do a lot work。But I'll just run somewhere。因为。

But that was a big mistake probably question。Check你说。Yes。谁。Okay。我。怎么。产比方这个。嗯。放思。还是出前过。没。Register。

wouldnn't be possible development。O。我。It was similar to the。Well真。that's a prediction act in the as。

That make you better。そ。accuracy is less50% above5 %。Since they got。

of the absolute of the prediction is。the training threshold so maybe that's threshold。

It was better before。not is value。What I want to do。はいゆ。

the papers they know they if the prediction and they trade if the prediction was was I see I see So this is and I I is prediction。

 I had to function because the train sure。After the after the section。

 Im doing that I'm doing Im still I still have to branches。For the GHR because otherwise violence。

 causality。So what I almost actually， since I have to win give insert certain。イで branchです。

I've leveraged the long to of the branch history in the kids at these。Yeah。

 private training will only be done at the so here you see J HR。If I案でょ。And it cost it's 260。

It should only refer to。To our false space。谢 the。も。现在只有都CMSB。大就。Oh good， okay。Or if to predict。

Where得帮我瞅一下。嗯没有好意。🎼，🎼Yes。しく大いす。Thank。知道。Okay， let's continue。



![](img/5861a82bae60e02b9c4b2af158ce56df_4.png)

So now we are exploring some ideas and prefeting and we discussed a reinforcement learning paper。

 let's see if this works， okay， not the paper， the book。Okay。

 as I said real systems have hardware Pfes that are hybrid and I've already discussed all of these I'm not going to talk about that。

 but there are some issues that happen in real systems that we will not go into a lot of detail on because we don't have a lot of time and we have only 14 lectures in this class right is that the right number 14？

😊，Yeah。If this were a more intense class， we would maybe dedicate more time to prefetching。

But it's good to think about prefetching in multi corere also because real systems need to deal with this。

 for example， if multiple cores prefetch share data。

 then you need to handle coherence misses and coherent states。😊，And。😊。

prefeting for those become could potentially become more difficult because predicting the patterns of sharing。

Could be something else， right， It's in addition to the strides。

 there's now you need to deal with some other processor accessing the same data， right。

And maybe potentially writing to that same data， which could invalidate。

A data item that you prefeched into your cache， so you could actually prefesh the data item correctly。

 but only for that data item to be invalidated from your cache。😡，So it's kind of waste bandwidth。

 even though you are accurate for some measure of accuracy。In a sense。

 but you're probably not accurate because you're not going to use that in mailline later on so it's good to think about this basic but there are a lot more issues that get induced with prefetching shared data and also when the system grows larger this problem becomes even bigger if you want to maintain coherence we talked about for example the IBMZ series system a few lectures ago that's a huge system with gigabytes of caches with many processors in a multi chip module and this cache coherent essentially so these issues become much more important and efficiency also becomes more important in systems like that because especially if you have many course accessing a limited memory bandwidth plus bandwidth becomes more preciouss and cache space becomes more valuable so you want to actually not waste those things on useless prefetching。

Or useless us anything in general。And also there's the interference problem which is one course prefetches may interfere with other course requests。

 you can have cash conflicts at multiple levels， you can have bus contention at multiple levels。

 you can also have conflicts at the DM main memory level and the bank rank channel row buffer that could reduce your bandwidth。

Even if you're not even if you're accurate actually right you may actually one of these papers that I'm going to mention show that even if your prefecure is accurate。

 it may displace things from your cash that are。😊，Useful for some other course。😡。

Then the question becomes which one's more important right and if you don't take that into account carefully you may actually lose performance。

 even if your prefeure is accurate， it may change which row is opening your row buffer and that row could be useful for some other application。

 for example， and now your bus bandwidth reduces significantly。😊。

So these are all real issues that you need to deal with。Even when you design an accurate prefeture。

Okay， of course， if you're inaccurate， this becomes much worse， but even if youre accurate。

 you still need to deal with it Okay so this is one of the papers that talks about the bandwidth efficiency that we briefly discussed。

😊，This paper coordinates the controls of multiple prefectures， Iman did his thesis on these topics。

 so these are his papers。And you need to also take and take on prefetches when you're actually sharing resources across multiple course and tweak prefetes very carefully。

 otherwise your performance improvements may not be very high and you need to design the memory controllers such that they're aware of the prefetches and it's accuracy so that you don't actually for example do the increase the row buffer conflict significantly again I don't have time to cover all of these these are very very interesting papers and ideas there's more ideas also and there's more but I'm not going to cover all of them because we don't have time。

But there's still a lot more interesting issues in this area。

 and even though it's explored in some way。Both workloads are evolving and architectures are evolving so there's more to do in this area and in my opinion actually there's a lot to gain because memory system is a place where if you do the wrong thing。

 your latencies increase significantly。😡，In corere， for example， if you look at coremic architecture。

 people have worked on it for many， many decades。😡，If you do the wrong thing。

 your latencies may increase by two or five cycles， fine in the memory system。

 if you do the wrong thing， your latencies increase by tens of nanoseconds quickly， right？😡。

So you need to be a lot more careful and also this shows that there's a lot more potential right。

 because by doing the right thing， you can actually save a lot more latency。😡，Any questions？

Now I'm going to switch gears and talk about execution based prefiting。

 we're still going to talk about prefiting。😡，But this is a topic that's really close to my heart because I did my PhD on this topic。

 a particular version of execution based prefeure， but let's talk about execution based prefeures in general。

 The idea is very simple again， it's hard to do， but。😊，Essentially。

 you pre executeec a piece of the program solely for prefeting data。

Piece of the program may not be doing justice to it because。😡，You may actually prune the program。

 you may actually write a completely different program to prefetched data for your main program。

 but essentially you pre executeec a thread or something that you execute solely for prefeing data。😡。

you can prune the program so that you only pre execute the code that leads to cache misses。😊。

These pre executed programs are usually called a piece of programs can be called a speculative threat because this is really a hardware context。

Essentially， it's a thread。It could be visible to the operating system or invisible to the operating system that's a different question and this can be executed in different places。

 it could be done on a separate processor or core， it could be done in a separate hardware context if you are multithreading for example simultaneous or fine grain you basically execute this speculative thread on some other context while your main program is executing and hopefully this speculative thread is generating prefets early such that main program never experiences any cachem that's the ideal case。

😡，It could be on the same thread context if you have idL cycles， you're stalled。

 the main thread is stalled for some reason， likely because of a cash miss。😡。

And then you switch to the speculative thread， pull it in。

 and you execute it so that hopefully you'll not be stalled next time right for another miss。😊。

This could be done in software or hardware， all of these can be done in software or hardware essentially so this is a new it's not this is an old idea actually these are some of the early papers that talk about doing this for both branches and loads these are the major two major issues as we discussed right when we start talking about branch prediction control flow and bringing data into the processor are the two major issues that we deal with today。

But you could do the same idea for branch prediction， for example， let's take a look at it。

 this is the branch。There's some code that I clearly confused the condition for the branch if you're able to prune that code。

 figure out which instructions actually。😊，Potentially affect the outcome of the branch。

 you could fork a speculative thread that executes somewhere。

 and that provides a prediction for where this branch should go。

This could be perfect potentially if you have all the data values and all the control flow。😊。

Potentially determined over here because there may be some instructions over here that are not needed for the branch right your code executes a lot of things。

 Some of it is needed for the branch only not needed for the branch。

 This thread can perfectly predict what happens in many cases， you cannot perfectly predict because。

😡，Theres some other dependency and you need to predict something like a value of a register so that you can actually execute the thread nicely so you supply a prediction and when the branch is fetch you use this prediction okay there needs to be some changes to the processor of course。

 to supply a prediction from the speculative thread to the branch predictor or fetch logic。😊。

Okay so the same idea can be done for the load， this load。

 the address is generated by a set of instructions， essentially a set of dependencies。

 you prune the program and you figure out which instructions generate the address and you can you fork a thread and this thread can be speculative。

 meaning it executes speculatively without generating any exceptions etc。

 and hopefully it generates the address of the load much earlier than the main program accesses that load and by the time main program access that load the cache the data value is already in the cache。

😊，Makes sense， right？You could do this for any other instruction also that could be performance critic。

 And these are beautiful papers that talk about it was called assist execution initially and。😊。

This is a nice paper that talks about it as simultaneous subordinate microting which is a mouthful in the end it's called helper3 it's really a helper threats the thread is a helper thread it's helping the main program。

😊，Okay。So I'm going to talk about an idea that I worked on for many years during my PhD these and if you're doing a PhD I would recommend doing something that excites you quite a bit and also impactful and hopefully also a fundamental I believe I had the let's say right conditions and I satisfied all of those conditions so I'm going to talk about runed execution I'm going to motivate in a different way because。

😊，In the end as you will see later on the motivation that we had was prefetching yes。

 but we had also some other motivation which is really building a large window so that we could capture a lot higher benefits of auto of word execution right we've covered out ofward execution one of the things that we discussed is you have these windows where you have a number of instructions of the machine and that number of instructions in the machine determines the complexity of the machine and you cannot have thousands and thousands of instructions in the machine because your machine becomes very complex because you need a large physical register file large load store buffer large issue queuees large scheduling windows everything。

😊，So if you have a small instruction window， this is what happens in many machines。

 you get a cash miss on this load， takes hundreds of cycles。😊，诶。If you remember in IBMZ series。

 the latest processor 750 clock cycles。This is real， that's a lot。😊，Okay。

 and then this instruction is dependent on it。😊，It may be perfectly predicted， by the way， but fine。

 and then there are a bunch of instructions that you fetch that are independent and you can execute them nicely。

 but you cannot retire them in out of order execution。😊，And then you wait for that load to finish。

 right？So that you can。Do something else now your instruction buffer is full instruction window is full。

 but you cannot retire in or your machine stalls after at some point so but if you add one more entry in your instruction window maybe you could fetch this instruction that would cause a cache miss right so younger instructions cannot be fetched or executed because it could be fetched but could it could not be executed because you don't have any space there's no space in the instruction window and the processor stalls until the long latency cash miss is servic。

😊，And long since the Kams are responsible for most Fi doing those stall this was actually shown many times。

 this is our data with Intel at the time， basically we simulated essentially all the workloads that they used to design their clusters with at the time and we found out that。

😊，Reasonably size window at the time， under 28 entry would lead to。

Stalls for more than 68% of the time， so most of the time you're basically waiting。

And most of these are caused by long latency cachemesis。

 and we also did some ideal studies that show that if you actually are able to increase the size of the window to 2048。

😊，You would reduce the stall time significantly。And you would also improve performance。

 as you can see by this much， like 30% or so execution time， again。

 average that across 147 workloads。Now this green is interesting。

 it's good to think about that green right it says nonst time for a good reason。😊。

That's not necessarily useful execution， right， actually。

 a lot of it is wasted for benchmark predictions， especially here。😊。

Green means you're executing something， you're not stalling。

 but that doesn't mean that you're doing something useful。😡，Okay。

So there' is more breakdown that you can do in this so a large window is not necessarily good if you don't have a good branch predictor to supply the large window with instructions good instructions okay so basically this is the problem that the way we formulate the problem if you want to have out of order execution it requires large instruction window to tolerate today's main memory latency 500 cycles or so let's say。

And as main memory latency increases， the size of the window should also increase to fully tolerate the memory latency so that you don't stop。

😡，And building a large instruction of a challenging task。

 as you have seen when we discussed Autoboard execution because。

Espec you would like to achieve all of these today， low power， low energy。

 but the tag matching logic that you have seen in automotiveboard execution and the load store offers actually go against that significantly actually these are some of the hardest parts of the machine to design。

😊，If you want to achieve short cycle time， you've seen all of these wake up select。

 those are not easy and also design and verification complexity becomes hard。😡。

So the idea is very simple， the way I think about this is a technique to obtain the memory level parallelism or prefeting benefits of a large instruction window because large instruction window provides multiple benefits to you right in the end what it provides is late as a tolerance whenever you have some long latency you get better benefits。

 you tolerate that latency by executing something independent。😊。

The question is where is the latency coming from where are the long latency operations that pro executes memory is clearly a big portion so we want actually prefetching benefits。

 but there's also computation latency for example， if you have long latency floating point operations out of order execution helps you to tolerate that also right here we're going to forego those we're not going to get the benefits of tolerating long latency computation operations that's a different topic。

😊，Okay， so we want to get the benefit so and the idea is when the oldest instruction in the window is a long latency cashm。

 we have a mechanism in hardware that checkpoints the architectural state and enters a special mode called what we call runed mode in this mode the purpose of the machine is just to specly execute instructions。

😊，Without worrying about any correctness。😡，So it doesn't stall。Well it can stall for a short time。

 but with minimizing install， meaning the purpose of execution is to just to generate prefetches。

 if it's， for example， gets to some wrong code， it can ignore it。

 it can drop anything at once because this execution is not going to be reported to the software we're not going to update the architectural state we checkpoint the architectural state meaning the register file and we're not going to update memory over here if you see a long latency instruction including the first instruction that caused entry into the mode。

 you mark it as invalid valid and drop it。😊，Another option is to predict the value of that instruction and drop it right so it could do many things and my thesis examines many things in this particular first paper we discussed basically marking as in mail meaning I don't have the data value of this instruction and I don't believe I'm not going to get it anytime soon so let me drop this instruction in program order so that I can make space for other instructions in the buffers of the Auto order execution right。

😊，Okay， the key is basically enable room for later instruction in the window。😡。

So you can decide whatever is in mail， you can say， okay， any instruction that is not going to。😡。

Compute or lead to the computation of an address that will lead to a cachem is going to be invalid for me if you can figure that out。

😡，Okay， when the original mis returnss， you restore the architectural checkpoint。😡。

A program counter of the instruction that caused entry into this mode。

 you flush the pipeline as if nothing has happened。And you resume normal execution。

And you start executing instructions and retiring them normally。

Makeakes us just as you would so basically instead of stalling what you do is speculatively execute instruction。

 let me give you a pictorial example， ideally what you want is never stall right perfect caches from a memory memory latency perspective everything hits in your caches and your computation is nice。

😊，Again， green doesn't mean that you're doing useful computation。

 some of it is wasted for branch predictions， right？😊，Small window。

 at some point you get a load miss soon after your buffers become full。

 you get a full window stalled and you stall for a long time。😡，And then the miss returns。

 you can execute， and then you get another miss and then you stall for a long time。

 and this is why you get 70% of the time wasted on stalls。Okay， run it basically says。

 I get a cash miss。😡，Soon after that cachem becomes the oldest instruction in the window at that point I have a clean place。

 remember precise exceptions， I have a clean place。

 I got a cacheist on the oldest instruction which means I retired everything before it and I didn't retire anything after it including this instruction so I can checkpoint the state register file。

😡，In fact， the Reg is table。And enter the speculative execution mode。

 runhead Mo where I keep doing what I just said。😡，For instructions that don't have their data values available。

 including the load that cause entry in this mode， I mark as' invalid。

 and the next cycle I remove that instruction from the window， essentially。😡。

And all of the dependencies are propagated just like an out of order execution。

 although those inals are also propagated。😡，like in out of order execution so instructions become invalid when they wake up if they source an invalid value right so it's beautiful it's data flow principles。

 as we have discussed in addition to propagating the tag and the data you also propagate an invalid。

😊，With instructions。Again， another way of doing it is basically you don't propagate the invalid。

 but you predict value。对。Okay， so hopefully。By doing this， you get to another independent cache miss。

 load2 miss。😡，Quickly as opposed to stalling and you start that axis in parallel with the Or Miss and when the Or Miss returns。

 you state you flush the pipeline， you restore the architectural state。

 meaning we execution from the load one。And now you execute load one。

 it should be hit because you just fetched it。😊，And M two returns before you actually need taxes。

That sounds good， right， that's the idea basically。So we use the stall cycles， instead of stalling。

 we do some speculative pre execution。Okay。So I think I've said all of this。

 so is what is the benefit of this， essentially these pre executed loads and stores independent of the alim and structure to generate very accurate data prefetches。

😊，For both regular and irregular access patterns， so your access pattern you're not you're not dependent on your access pattern。

 you're really executing the program as if it would execute right。

The only condition is hopefully you have the cache misses that are independent now if you predict the addresses of the instructions that you drop。

 then maybe you can actually prefetch those data structures， linked data structure traverses。

 etc ceter， but that's the subject of an improved version of run execution。

 which is I don't know chapter X in my thesis， but anyway。😊，And also there are other benefits。

 not just data prefeting， but also we didn't talk a lot about instruction prefeting in this course。

 but instruction prefeting is also also an issue in existing processors， I believe less so than data。

 but if you have instruction cache misses then you cannot do anything for the program that's also good to consider if your're data cache misses。

 you may do something。😊，But instruction catchmes。You don't know what to fetch right。

But you can pre essentially， instruction on the predicted program path are prefeession to instruction cash and other cash levels。

😊，And also you train the hardware prefecture and branch predictor tables using future access information essentially during this mode it's also good to think about this way because maybe there are some future ideas that could be done what you're doing in this speculative execution mode is you're peeking into the future。

😊，As opposed to stalling， you kind of have a peak into the future by executing instructions and you're generating prefetches for both instructions and data。

 but you're also potentially generating information that you didn't you would otherwise not know if you were stalling it's good to think about it that way can you use this information for something else。

😊，呃。That's always a good mindset of a researcher， what else can I do then what was previously done right？

So I I like that peeking into the future part okay so with every idea that says advance and disadvantages。

 of course so as we discussed there you get very accurate prefets for data and instructions accuracy is not a problem it's report in the paper more than 90% in general because you follow the program path。

😊，It's simple to implement because you're really taking advantage of the Autoboard execution machinery with some changes of course。

 you need to touch a lot of parts of that machinery in the end。😡。

One upside of the way we implement it this， which is different from some other people who implement it is there's no waste of hardware context basically we use the main thread context for prefe it's very fuugal right you could imagine doing exactly what we just described on a separate thread context right。

😊，Meaning launch the specative thread on a separate thread context by copying the Reg file program counter。

 and you could do that。And also， the big advantage compared to some other helper thread based mechanism is there's no need to construct a special purpose threat。

😊，You just use the program。😡，That sounds good Of course to say there's a disadvantage over here because you the program can be doing。

You may not be able to get to the next miss quickly because the program can be doing a lot of stuff that's not related to the next miss。

😡，So you could actually improve this and later works actually improve on。Essentially， a lot of these。

 the disadvantages。😊，So disadvantage is extra execute instructions because you specully execute instructions to generate prefetches。

😊，If there's especially no benefit from that， meaning if you don't actually generate a cash miss that you're going to use in the future。

 you're wasting energy without gaining any benefit and we actually identify this problem and lean later works we improve that which I'm not going to talk about。

 I will flash it later。😡，Just like a large instruction window。

 it's limited by branch prediction accuracys， meaning you're executing instruction into the future or in a large instruction window also。

 if you want to keep fetching instructions， you better have a good branch predictor。😡。

As we discussed because。Especially。If you have a cash M， for example， you have a cash miss。

 you cannot service right now。😡，And you have a branch that's dependent on it？

If that branch is predicted correctly by your branch predictor， no problem， that's good。😡，Now。

 if that branch is not predicted correctly， you wouldn't know that because you don't have the value。

😊，So you will be on the wrong path until the end of this runhead execution。Which may not be bad。

In the sense that wrong path can actually generate useful prefes。

 we examine that in a lot of papers later on， wrong path can be useful for pres。

 but it's better to be on the right path than on the wrong path on average。😊，Okay。

 so there are a lot of interesting things over here and you cannot preface depending cache misses。

 but laterwork can actually do address prediction， and also the effectiveness is limited by available memory level parallelism。

 meaning if you don't get to the next cache miss during these cycles where you do pre executionecution。

 you essentially are not going to get a lot of benefits。😊，And there's also another thing。

 so this is the program level or cash memory level parallelism level thing。

 but also a prefeched distance like how far ahead you can get in the program in runed execution is limited by how long you stay in run ahead mode。

 memory latency。😊，Okay， so there are a lot of interesting things over here。

 but in the end we put good results， this is actually all of those 150 workflows。

150 or so workloads that we studied with Intel。😊，And this shows that the only prefecture is the locality based prefecture at the time that Intel was using。

 you can see that it's quite effective actually。😊，So that's our baseline only right is actually better than that。

 but maybe not as bandwidth efficient well， no not necessarily not as bandwidth efficient。

 but maybe not always better if you actually put runhead on top of the prefe you get about 20%。

 which is not bad。😊，And this actually at the time we showed that this is actually almost the same as building a window that's three times the size of what Intel used to build at the time。

 it's also good right， you don't have to you have much the cost of re execution is much lower than building a 3X size instruction window。

Okay， and then you can do this the idea is independent of in order versus out of order。

 so you can do this on in order machines out of order machines and in order machines clear you get better performance benefits because in order machines fundamentally have much lower latency tolerance that's the reason why we move out of order execution right out of order execution main benefits latency tolerance in order。

Less latency tolerance， but you could have prefettures in the northd。Okay。

 so the good news is people replicate our results， these are people from industry。

 this is from Sunrack they actually wrote papers about it and I showed you this graph before。

 but if you look at this graph scout is reite execution their term for reite execution their machine was in order so they actually in an in order machine they implemented it and they said they get 40% better performance。

😊，Which kind of matches the 40% we have over here almost 40%， this is a nice replication， let's say。

😊，But they also argued that you could actually design much leaner machines。😡，In a different way。

 in that case， they don't have an instruction window to deal with， but they have huge caches。

 they basically said as opposed to having huge caches。

 we can have processors with run execution and we can buy a lot of megabytes and we can put more processors。

In the same diaea。So this is the beauty of good prefetching ideas right it doesn't only buy your performance。

 but it gets you to a better space in terms of hardware efficiency so that you can actually improve your parallelism in the system。

 because if you look at caches unless you do incache processing or processing in memory your caches are useless for computation right。

They're there to satisfy， we're going to talk about pressing in memory， pressing in caches。

In memory processinging changes the gate。That's why it's so fundamental。

 I think also maybe by7 megabytes is not。Just about megabytes right anymore。

 if you can do computation over there now you can use that as parallelism also。😡，And that's， I think。

 a good way of thinking about systems， maybe we should be doing computation everywhere so that way we don't get into the straight off。

😊，Computation versus data storage。Okay， so there are a lot of interesting things over here in the end。

😊，In addition to the fact that it's always good to see your results replicated by industry almost exactly the same amount。

😊，These are different workloads， by the way， these are commercial transaction processing workloads that they use。

😊，Okay， I think I already said basically you can both improve performance and reduce hardware costs。

😊，So this is the paper that we wrote， I'll talk more about this is the paper that Sun wrote。😊。

Some wrote actually other paper that I'm not going to talk about this actually they tried to use so what they did runed execution looks into the future right and these guys actually try to exploit that by looking into the future you generate a lot of results also and they actually designed an architecture that。

Without going into full blown out of order execution。

 just using reite execution you actually also incorporate the results into the machine and they showed even better results than rendered execution on top of in order execution。

 I think this was a bit more complex architecture but they had a good idea it's a hard to read paper。

😊，It could be written better， but they had very good ideas， I think。Unfortunately。

 they were bought by companies that don't value things。You can guess who they were bought by。

 perhaps。Actually， they tried to be fair， Oracle actually tried to keep their processor group。

 they ate it a lot， but in the end they slashed it。

Just like Samsung we saw right in the Samsung Exos paper。

 there's no author from Samsung you though the title is Samsung Exs Proster why is there no author from Samsung because there's nobody in Samsung to write that paper。

Yeah。Okay， but this was a very interesting， very new ideas， basically。😊，Okay。

 IM power is also implemented and they have nice papers that talk about。

Comparing conventional data prefetching， I like these。

 And these are actually good papers that talk about like different prefetching mechanisms。

 I like this one from Amvidia because amvidia again， normally doesn't write any papers today。

 if you think about it， they have their technology conference where they don't talk much about talk about much interesting things in my opinion。

 I don't know。 was there anything interesting。😊，Maybe， maybe at the high level。😊。

At the hardware level， there's some hardware。😊，Yeah。

 but basically they designed this SOC where they had a CPU an arm CPU。

 and it was actually superscalealar in order。And they had a lot of other ideas also。

 but they did implement Runhead over here also， and basically they say for example。

 when it complements the hardware prefeure because it's better at prefeting non- strideed streams and it trains the hardware prefeture faster than normal execution to yield the combined benefit of blah。

 blah， right？😊，These actually numbers are also similar to what we have seen。😊。

Let me see if there's anything interesting。Anyway， he can read it to an hero。Okay， any questions。

 so this is an example of execution based prefeure that has had a lot of impact， I think。😊。

These are some of the papers that we've written because we didn't stop there right because there are a lot of issues like how do you actually make it more efficient that was one of the works。

 how do you predict the addresses of cash misses that would lead to other cache misses that's also important and I think there's more work to be done in this area。

😊，How do you actually handle the wrong path so we had a bunch of stuff on the wrong path。😊。

Because you spent if you and this is also important for large windows because you spend a lot of time on wrong path。

 what we should have done in these works is actually figure out the security aspects of speculative execution。

 we looked a lot into performance aspects， but if we had actually looked at security aspects。

 maybe we would have seen inspector and meltdown earlier。😊，Okay， anyway。

 so basically these are some of the issues， you have energy inefficiency。

 you can have a large number of instructors that are speculative executed。

 efficient runite execution， which is actually what is really implemented in NviDdia I think because they reference that paper multiple times it basically figures out under what conditions runite execution is useful or not useful ands it's basically prediction mechanism to decide whether you want to go into this run speculative mode。

😊，Okay， I will not talk about some of these other ones， but I've discussed some of the problemss。

 I'm talking to talk about this one because this is runed execution and modern context。

 this is written 10 years after I wrote my thesis。😊，Well， these are some of the papers you can read。

Yeah， in continuous Rennehead， especially if you have a modern processor with large instruction windows。

 it turns out Rehead by itself， as we described with all the bells and whistles。😊。

Its not as effective， it's still effective， it still improves performance。

 but it covers only 13% of potentially reed reachable misses with some definition of reed reachable basically and if you can pre executeecute everything。

😡，Because run execution in trouble tends to be very short， 60 cycles on average。

And run it ends after the mist that caused it is serviced。

 so there's a lot of analysis in this paper and this becomes shorter and shorter as your reorder buffer size increases because your reorder buffer size increases that means you have more latency tolerance。

 you don't stall for as long。So how do you make reite effective under these conditions？😊。

And the idea is no surprise probably for those of you who may go into my mind and think of my mindset。

 basically do reite in the memory controller， don't turn in the processor。😊。

Free the processor from doing Renite。Basically keep runhead going even after a long latency cash miss is serves。

 identify chains of instruction that lead to long latency cache misses and there needs to be some hardware for that。

 keep executing though each chain of instruction in a loop in a runhead mode using some specialized runite execution hardware this is called continuous runite engine。

😊，And this way， this hardware keeps staying in running a ahead mode until someone decides this is not a good idea anymore。

 so there could be throtling mechanisms， some throtling mechanisms could be time based throtling or a number of instructions based throtling。

 or it could be accuracy based throling， etc。😡，And this is located in the memory controller。

 essentially you have the processor， the processor ships these chains of instructions to the memory controller and the memory controller doesn the run ahead and it keeps fetching instructions into the processor caches and the processor can continue right now。

😊，Which means that you could continuously be in run ahead mode， that's why this's called continuous。

😡，There is no distinction in the sense that you don't need to have a long latency cashm to switch to another mode。

 this memory control can be doing independent prefetching。

So it's a specialized engine for a prefetching using some run head mechanism。

 you could execute any code over here， but people have used any code and this is also completely a programmer transparent。

😡，Okay， I think in this particular case， we will stop executing the chain after a fixed number of instructions and we see significant benefits because you don't stop running ahead when the cash miss returns。

 you increase the coverage。😊，Of Rehead reachable misses from 13% to 70%。

 and you get a lot more performance gain over the best runite implementation。

And there's more work that has happened on Rahead， Millo actually did a lot of work after that。Again。

 I will not go into the details， but I think this is a good way of。Doing Rehead in modern systems。

Then the question is， of course， how do you distribute the prefeting responsibilities across the entire stack right that's another question that's really important and people deal with it when they design systems right where do you design the prefetch？

Okay so there's more work in this area this is and it's very it's fascinating to me that there people generate ideas。

 I like a lot of these ideas， this is not the latest work。

 but this is one of the work that won the best paper awarded micro in 2023 and the idea over here is to do runhead on vector operations meaning you have some scalar operations but they're all vectorizable and you vectorize those scalar operations again automatically to pre fetch many independent loads concurt。

😊，Again， I will not go into the detail and there's more ideas in the paper。

 but I recommend people take a look at it， and I think there's more potential in this area still。😊。

Any thoughts？Does this sound fun？You've covered a lot of ideas。

 but these are some of the ideas that are closer to my heart cleared。

So I will give you some actually context to this because when we were doing this work at Intel。

 especially Intel was the leader at the time， don't think about Intel as today's Intel。

 today's Intel is I don't know what they do at the time they were the top of the line place AMD was not not let's say competitive at that point。

😊，Things change clearly if you don't innovate right or if you don't maybe innovation and delivery at the same time you can innovate but not deliver you can deliver and then not innovate if you innovate but not deliver you're vulnerable immediately if you deliver but not innovate。

 you're vulnerable a little bit longer term， if you don't do either of those you're dead probably immediately。

😊，So I don't know where the thing is， ideally you would innovate and deliver right both of them and your delivery is really delivering something that you really innovated a few years ago。

😊，That the Intel was at that point and at that time there was a lot of debate basically there was a huge focus on increasing the size of the instruction window and if you read papers at that time people were trying to okay。

 let's make instruction windows that are thousands of entries etc。😊。

That's kind of one today because people figured out， I think， especially Apple figured it out nicely。

 but still it's expensive， I mean it's not cheap。😊。

But they actually do tricks that are not also disclosed so designing bigger and more complicated machines so our thinking was different Basically we said let's keep the core simple and small and let's focus on where things really matter in NSS there's nothing new here and it's common case design right。

😊，Yet don't forego some of the benefits like non memory related stalls。😡。

But get the benefits of prefetching， use aggressive automatic speculative execution solelyy for prefetching right。

And this is synergistic with prefeting and branch prediction methods。

 and the good news is I think in addition to having impact on industry。

 this also impacted a lot of thinking。😊，A lot of interesting and innovative ideas ensued。

 and I showed you a paper from my 2023， people still think that these are worth best papers。

 which is good。But I should also say that while we were doing the research we discovered there are other people who did some similar work and I will acknowledge those。

 this's actually a very nice paper which doesn't get enough credit in my opinion shouldn't get more credit。

 it actually does a limited form of runed execution。

 it was one of the reasons why it doesn't get credit as probably was published at ICS as opposed to ISA let's say。

😊，But we did give credit， in fact， while we were working on it。

 we used to call Rene execution scratch mode execution。

 because what you do is you go into a mode where you scratch everything， right？😊，In fact。

 if I was the first person writing this idea， I would probably call scratch mode execution。

 I don't know where when it maybe。Better I don't know。

 but we changed everything to run ahead in the end So if you look at our code its says scratch mode。

 but the paper says run ahead after we discovered this paper。

 but I recommend you take a look at that。 This is actually a paper that does run ahead on a four stage pipeline so it's a very small pipeline。

 but it still shows benefits。😊，In this another paper that I recommend to people。

 this was an inspiration to us， this is from Andy Gloe who actually had a lot of ideas and who worked at Intel and AMD。

 et ceter， but basically he wrote this at the time where people were actually proposing really wild and crazy ideas at S+ S plus had the session on wild and crazy ideas。

 it still exists him but。😊，I don't know if it's as wild and crazy as it used to be。

 I guess it's on the eye of the beholder but basically he argued that we should not be designing procedures for extracting ILP meaning simple results for computation operations but we should really be generating a lot of memory level parallellism and he has a lot of ideas over here but I'd let you read that so some of these actually have been explored in papers some of these have not so there could be some other research ideas over here and he could create endy glue if you come up with something。

😊，Okay， so I think。Essentially I think my architecture is critically important still in my opinion。

 there's a lot of fundamental things to be explored， it's harder than some other areas。

 but I think there is a lot of impact that you can have today and when it was also a great example of harmonious industry academia collaboration。

 this should exist more， although industry is becoming more and more closed sometimes but let's see if that changes。

😊，So maybe this was a good point， I actually delivered this when we won the test of time award for this work。

 but I think working on fundamental problems is actually important because they will always remain fundamental。

Hpes come and go。But fundamental problems remain， I think。

And also if you combine hype and fundamental， that's even better right you take what's really important today is what's hyped and then you do something fundamental with it。

 that's important。😊，Okay this is the citation for the Test of time award and I agree with everything that they've said。

 so this was a good committee that said basically it opened up new avenues on dynamic prefetching。

 we describe it， spawned off a new area of ILPN H MI architecture research and still it continues that's a fascinating part。

😊，In fact， there was a paper， I think， in last micro 2024 from the same guy who won the best paper award in 2023。

So I would say follow your passion basic， if you're a researcher。

 a lot of people actually criticize it， ran out execution at the time， for example。

 because they wanted to build these large instruction windows。

 if you look at large instruction papers at that time I'm not criticizing it。

 I think people should explore many many avenues at the same time。

 but it's very complex I think building I still think actually building a large instruction window we should do better。

😊，That's why I kind of am annoyedy at our Oracle for killing the Sunrack project after buying Sun and then doing nothing useful with it for many years because they had some different way of thinking and they could actually do something based on this runite execution idea that's completely different。

😊，Now， I think we're still doing large instruction windows that may be reite implemented in some parts of the machine。

 but still large instruction windows are being built， but they're still inefficient。

There's another inefficiency we will talk about little later lectures， which is how we handle memory。

This is all proscentric still。Okay so it's good to basically do a high quality work based okay there's more on runite execution which i'm not going to talk about because there are a lot of details but my thesis covers a lot of details I rewrote actually our HPCA paper。

😊，Because I didn't like the writing three years later I rete it complete before my thesis。

 so if you cannot find the exact paper in my thesis because a lot of is rewritten。😊。

And we have some videos if you're interested。There's more on pre-fetching also which I'm not going to cover。

 we go for example in some of these lectures we go a lot more into pre executionecutionbased prefeting。

 there are other forms of pre- executionec-based prefetching that I didn't cover right how do you form the pre executionecution thread if you want to do this in software for example。

 and there are software methods， for example， it's a nice paper that talks about how to form the slices that lead to branch instructions and load instructions that degrade your performance。

😊，How to design it， they do it by hand over here， but later works do it by compiler。

 they could do it statically， they could do dynamically in hardware。

 there's a lot of work in this area that I will not talk about。😡。



![](img/5861a82bae60e02b9c4b2af158ce56df_6.png)

So but you can find a lot of information on prefeting online。



![](img/5861a82bae60e02b9c4b2af158ce56df_8.png)

And that brings us to the。Last light。Any questions？Thoughts， new ideas。You idea to change the world。

Okay， if there's nothing。Maybe you'll have those ideas next week。Okay。

 so you'll have fun with your prefeting lab， I don unfortunately you're not going to do execution based prefeting。

😡，And that's one of the downsides of some of these prefeting based competitions actually。

 or a lot of them are focused on a particular form of prefeting。😊。

And they don't contain some of the other ideas that's true for the championship parent prediction also right there a lot of them are focused on building a hardware that predicts。

 well what about building something that executes？😊。

And I think there's a lot to be done in that execution part。😊，Okay。

 I'm done and we're almost done in time also， but we're a bit early。So I'll see you next week。

 next week we're going to start covering some other execution models。呃 then。

Essentially Auto order execution and these will still stay important like prefeting。

 but we will look into other execution models。😊，Okay， see you next week。



![](img/5861a82bae60e02b9c4b2af158ce56df_10.png)