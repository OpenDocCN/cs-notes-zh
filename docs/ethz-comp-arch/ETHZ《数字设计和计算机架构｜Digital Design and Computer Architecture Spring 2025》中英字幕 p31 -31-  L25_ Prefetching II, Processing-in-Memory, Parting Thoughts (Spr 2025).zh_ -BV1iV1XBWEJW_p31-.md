# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p31 -31-  L25_ Prefetching II, Processing-in-Memory, Parting Thoughts (Spr 2025).zh_ -BV1iV1XBWEJW_p31-

![](img/42ca74b47661a64c9efa6c5c7d898f49_0.png)

对。哦。干嘛呀？So我。Yeah。我那是。Is all good online？Can you hear me。Good， is it good， okay。So。

I think this is also not new good。あそ。对。Okay。Right。S。即。我有。我啲你啲死。我的。啊。还 you个。你可他意思。Yeah。可呀。不实。错。嗯。感心我了。

Yes。好的。嗯。😊，所以。因为这个经。🎼Yeah。嗯。嗯。🎼嗯。嗯。O。I think this is our last lecture。Is it a holiday today。

 it's not right？But are other classes going on？Yes。Are some canceled？No， okay， okay， that's good。

 not not that I'm intending to cancel the class today， but。

I'm curious because I heard that some are can。Okay， so we're going to。😊，Do our last lecture。

 let's see how far we can cover， I'm going to finish up prefetching。

 but before we do that I'd like to mention again that if you're interested in this material。

 this is our last lecture in DDCA but this's not the end of computer architecture clearly if you would like to learn more we have a master's and PhD level computer architecture course usually senior bachelor' students also take it。

😊，We have a seminar and computer architecture course that we discussed and you can also consider doing research and computer architecture so this' is a very exciting area。

 I decided to work on it after my first class similar to you where I learned about computing because it was so interesting to design better computers So maybe some of you are interested in doing that we also have a fundamentals of computer architecture course that's a senior level。

 but it's a mix of really DDCA and computer architecture。

 So if you're taking DDC it's better to take directly computer architecture I would say。😊，And also。

 how many people filled out course evaluations here？Okay。

 I would recommend everyone you want to fill it out because we want your constructive and positive feedback tell us what you liked and what can be improved there are people who don't necessarily like this course I don't want them to fill out the evaluations only there are people who like the course they should also fill out the thing and usually there is a balance right a good evaluation is usually balanced you need to have both strengths and weaknesses if all you do is complain that evaluation is not necessarily great if all you do is rave。

😊，It's good to also I get some feedback on what we can improve。

 so it's good to have a good balance over there。Okay。

 so I would recommend people to fill out the evaluations。Okay。

 I'm going to skip a lot of these slides because this ties nicely with what I said。

 if you're interested in doing research， I've already said what you may want to do in computer architecture and there's a lot we've covered this a few lectures ago。

😊，And you can learn more about our group in many different ways as you can see right Ive already went over some these slides and we're proud of our students。

 we added one more PhD graduate to this list since you last saw the slide a few weeks ago and also if you're online you can join us by applying okay now let's go into the material of the course which is prefeting。

 we're going to start with prefeting or we're going to continue prefeting but as a reminder you have an extra credit assignment which is MDds law you know that and these are some of the readings。

 some of which include prefeting actually at least partially。😊。

Okay prefeting you had a lecture two lectures ago Raul gave an overview of what is prefetching。

 et cetera， I've been working on prefetching for 25 years at least and this is a very exciting area。

 this is an area where you can actually do a lot of changes to the processors today so that you can improve both performance and efficiency greatly。

😊，I'll give you some of my personal experience also over here the basic idea is really to preload the data。

 bring the data into the caches or a buffer before the processor needs it it's example speculation mechanism you speculate because you don't really know whether this will be needed by the processor or the program and somehow you figure out that or you guess that it will be needed and you fetch the data from memory so that you cover the memory latency and we covered a lot of questions over here which I'm not going to go into this is just to jog your memory what do you prefetch what addresses to prefetch what is your address prediction algorithm that's important and it could design it in many different ways in software hardware will'll see a couple of other examples today when do you initiate a prefet request how do you make the pre-fetch timely because if you're too latent pre-fetching you generate the correct address but the processor is going to request it right away like in one cycle later so you don't save anything you need to save hundreds of cycles if you want to actually have a big impact on。

Fors。Where do you place the prefetch quest， do you put them into caches or separate buffer and where do you place the prefetcher。

 which level in the memory hierarchy， these are actually different kinds of where。

 but they're all important questions， so there are a lot of questions that affect the memory hierarchy。

and last lecture we covered virtual memory， it's also good to think about what kind of addresses you use to prefsh use virtual addresses or to use physical addresses。

 you run into different tradeoffs that way which I'm not going to get into but these are things that you can think about there are a lot of choices basically。

How is the last question， how does the prefeture operate and who operates it。

 does the software operate it， does the hardware operate it。

 does the programmer do it does the compiler do it or is it more thread based execution based or is it some sort of hybrid existing prefecs are all hybrid in the end and we're going to cover an example of execution based prefeure。

 which is really part of my PhD thesis so I'm quite interested in this area as you can see we're going to discuss that a little bit。

😊，Okay， so there are a bunch of prefeting issues we discuss some of these at all of these。

 but we're going to see some more today。😊，Again， this is an overviewuse site。You see。

 you've seen some simple prefes。 Let me talk about another prefeture that Rahul actually developed during his PhD studies。

 we're going to call it the self optimizing prefeture。

 One of the issues with many prefes you have seen earlier is they're not。😊。

They're very much dependent on the designer's decision designer needs to figure out what are the things to look at。

 for example， you want to figure out the deltas between different addresses these are strides and you want to predict the stride right that's one example to predict a stride you need to look at a cache block address that's a feature right in this case you look at one feature and you design a prefeture based on this feature in that sense it's not very flexible right in this work we asked the question can you actually have a more flexible and configurable prefeture that can consider many features and using those many features that can learn how to prefetch so we're going to use machine learning in the design of this prefecher we call self-opimizing prefeture Pthia is the name I'm going to give you the basic ideas how many of you have seen reinforcement learning。

😊，Okay， some of you， not all of you because you haven't taken a machine learning class yet。

 but I'll give you a teaser， let's say reinforcement learning is essentially we're all reinforcement learning agents as humans。

😊，I for example， I there's something hot in a stove， this is my favorite example。

 I put my hand on the stove。 I get burnedt， I quickly figure out that under that condition。

 under that state， I should not take that action because I got a very negative reward right my hand is burned。

😊，I put my hand on a stove that's cold。I don't get any reward or punishment or negative reward or positive reward。

 So I learned that when the store is called， I can take that action if I want to。

 but I don't get any reward， right。So it's good to think about this right basically based on our interactions with the environment。

 we agents， autonomous agents， as an agent， I interact with the environment and based on my actions in a given state。

 I get a reward or a punishment punishment is usually a negative reward。😊，And over time。

 based on a lot of these interactions， you figure out under what state。

 what actions you should take so that you maximize your reward。😡。

I didn't take any action to initiate that one， but there's something going on apparently maybe they think it's a holiday okay。

 so reinforcement learning generalize this concept essentially you think of agent so you can build a computer or you can build anything it's essentially it's an algorithmic approach that enables an agent to learn what action to take under a given state or situation to maximize some numerically reward value okay so an agent interacts with the environment。

😊，Observes the state of the environment， and based on that observation decides to take in action。

And at some point， it receives a reward。Based on what it did。

And it can associate it's the state action pair with the reward。 That's the idea。 And over time。

 it figures out。Under which state which action it should take so that it can maximize a long term you want。

 there's a lot of math that goes into it I'm not going to talk about the math。

 but this is the key insight essentially。😡，So there are multiple types of reinforcement learning which you may learn if you actually take a machine learning class。

 one is called Q learning， in this case you have Q values or quality values for every state action pair。

 you may have a table for example， this table stores for a given state action pair if you take this action at this given state。

😊，State is usually represented as a set of features right these are the values of these features if you take this action in the state。

😡，You were likely to get this reward value based on what I learned in the past。

And based over time essentially the agent or you can think of this as the expected return for taking an action estate over time the agent learns or updates these Q values based on the reward values that hit by doing actions in different states basically the agent is really exploring the state space by taking actions it's a beautiful paradigm。

 it's a very general paradigm it's much， much more general than neural networks， for example。

 in my opinion， although you could combine neural networks with reinforcement learning as well okay so given a state you select the action that provides the highest queue value。

So basically we're going to design a prefeure that operates based on these principles so that we can feed any state value hopefully hardware constraints will come into play so it's not going to be as easy but we're going to formulate a prefeting as a reinforcement learning problem in this case our agent will be the prefeure and our environment will be the processor and the memory subsystem essentially we could observe anything over there。

😊，But again， if you want to actually build a table that stores state action pairs or quality values associated with state action pairs。

 your state space should be small enough， your action space should be small enough and otherwise your tables can become huge。

 right？😡，Okay， you can encode this table as a neural network also and today theres deep reinforcement learning。

 but then your latencies may increase essentially so basically prefecure observes the state in this case we're going to restrict ourselves a little bit。

 it's going to observe features of memory request to address a， for example。

 which program counter generated that address， which load instruction， what was the delta。

 what was the last n dels that you have seen until you came to this load instruction。😊，Okay。

 and then based on that， it indexes a table and this table says pick this action among all of these possible actions that you can take in this given state。

 pick this action because this action has the highest Q value and we're going to specify the action as。

Prefetch from address a plus some offset。 So we're limiting ourselves again， right， The action is。

Picking that offset， should I pick offset， zero，1，2，3，4，5，6，7，8。😡，And then there's some limit。

 and each of them has a quality value associated with it for this given state。Makes sense。 I'm not。

 I didn't tell you exactly how to update these values。

 but there are a lot of mathematics or statistics。 And machine learning in the end。

 is completely statistics。 There's a lot of statistics that goes on in updating these values。Okay。

 and then after it takes that action， it gets a reward， it observes with， let's say， for example。

 it's prefeched， it records this information， it's prefeed address a plus offset5 for example。😡。

Addres was let's say 5000 if you prefetch address 5005 cash block address and then you get a reward reward could be oh this prefetch was accurate。

 but I was a little bit late so you get a reward for that reward value for that saying that you don't get the complete reward but you get some reward that indicates that you're late so hopefully under the same state you'll take a better action next time so that hopefully you'll be early next time makes sense so you modulate your behavior based on the type of reward you get over time again this doesn't happen immediately。

😊，So it's a beautiful learning paradigm as you can see you can do this online。

 you can do this offline， train the tables and then store the table but online learning is much better because you can adapt to the dynamic workload as well as the dynamic conditions of the system which may have varying memory bandwidth for example。

 the memory bandwidth may be low and this reinforcement learning agent may learn to be less aggressive if the memory bandwidth is low because it generating prefetches that are under very bandwidth constrained environments as a result it's not getting it's being always late it may over time learn not to pre-fetch for example。

 if your very bandwidth constraint because you don't have enough bandwidth to actually sneak in this prefetch while demands are also going into the memory system。

So there are a lot of benefits to doing this online， as you can see right。Okay。

 so let me give you a couple of examples of this。 I think I've given you the basic idea。

 which is really what I want you to get out of this。 Now then devil is in the details。

 devil is always in the details whenever you want to implement something and you need to go into figuring out what is state so you can express state as a K dimensional vector features。

 features could be anything actually， anything you could imagine could be a feature。😊，For example。

Whether you're sitting over there today is a feature clearly it's not going to affect the offset that much。

 but it could be a feature that you considered， but in the end that's going to be eliminated based on the enforcement learning agents updating of the Q values so you don't want that feature actually。

😡，You can see that an example right anything can be a feature in the end。

 but it'll be eliminated well you don't want the unnecessary features because they affect the size of your tables internally or size of your neural network。

😡，Okay， so basically more reasonable features are control flow features and data flow features。

 this is basically based on the domain expertise of the designer。😊，And the designer may think， okay。

 some control flow features may be interesting， for example， program counter of the instruction。

 load instruction that generate the status， program counter， the branch。

 last branch that I executed because this gives you an idea of where you are in the program path。

 right？😊，Last three program counters again this gives you a little bit more information it could be multiple things and you can imagine many different control flow feature it could be what was the last return address you executed this gives you an indication of where you are in the call stack of the program for example right。

😊，And then there could be data flow features， what is the address of this cache block。

 what is the physical page number of it， what is the delta between two cache block addresses that you've seen recently or last time。

 what is the last four deltas again you can imagine many many things okay so a reasonable designer who's designing this sort of prefecure I would say would go and figure out okay these are a lot of features that I think maybe affecting the offset that I'm going to generate。

😊，Accurately and let me actually put all of these features and figure out which ones are most important and for this there is an automatic procedure called feature selection。

 which is a very heavy process there's a lot of simulations that you need to to figure out which features are really important but you can do that we can basically readed out the important features and from the unimportant ones but you do this offline you do all of this offline and eventually come up with some features I think I'm going to show you a couple of features for PTia and the paper describes more what is action action is again based on the designer designer based on their domain expertise says' I'm going decide on an action。

😊，Now prefetching is a little bit interesting because prefetching is unbounded right or for a given address you see address A and then you want to generate address B to prefetch address B should be somehow related to address A。

 but it could be anywhere in the address space， right？😊。

So here we're going to limit ourselves to close by in the address space if you've seen address a。

 we're going to say， okay， this prefeer is going to be prefeting something spatially close by within the same physical page actually。

😊，So we're going to prefetch and offset O。So essentially if you're within a page。

 let's say you have some 127 actions in a range that looks like this offset goes from minus 63 to plus 63 and there's also a zero offset that means no prefet is generated it so prefetcher can over time learn I don't want to prefetch because for some reason I'm not accurate so I always select the offset as zero right then you don't generate a prefetch but it can also learn over time which offset is actually which offset comes from a prior address that you seen。

😊，Okay and then there's also some pruning because if you actually have 128 actions it's also expensive in terms of hardware so we prune it a little bit and there's I'm not going to go into that in detail。

 but you want to basically find the let's say most interesting offsets that are happening a lot in the workloads that you train this prefeccher with so there's an offline training aspect to state selection as well as action selection。

😊，Okay， what is reward， this is actually one of the most difficult parts。

 basically this defines the objective of the prefecher。😊，What should the prefecture customize for？

So in this work we tried to encapsulate two different types of metrics。

 one is whether the prefetch is useful， usefulness includes accuracy， lateness。

 whether it goes out of page for example， and also system level feedback how much memory bandwidth is used and how much does this impact performance there could be also cash pollution you could also include energy but we really look at memory bandwidth usage because it's really a first order concern I've designed many prefes that in real processors and memory bandwidth usage one of the most important system level。

😊，Let's say characteristics or values that you need to take into account when you're prefet。

 because if your memory bandwidth is oversubscribed。Even if your prefes are accurate。

 you don't want to oversubscribe it even more by injecting more prefets。😡。

If you want to oversubscribe it remove something else from your cues but that's also a tough thing to do okay so this is an important concern so this is our Pia configurationation so using automatic design space exploration we narrow down state action and rewards to make the prefetcher implementable in a real processor using real constraints like clock frequency cycle time how long it takes to generate a prefetch。

 how many cycles etc。😊，So in the end， we end up with two features， PC plus delta。

That's basically the program counter of the instruction that generated the address that we're trying to prefetch from as well as the delta。

 the previous delta that we have seen at that program counter。

 and also we have sequence of last four deltas globally that we have seen in the memory access tree。

😊，Last force strides basically so this is useful for indexing the prefecure using the state and then there's some hashing exoring etc cetera that goes on to really represent the state of course and then there's action we basically have 16 prefetch offsets ranging between these values including zero so we basically prune that space also and these are the rewards i'm going to explain the rewards a little bit more maybe later actually not not really in this class because it's not that important but for example。

😊，If the prefeure is accurate and timely， you get a plus 20 reward。 It's a very high positive reward。

 That means you did the right thing。Keep doing the right thing in the state by taking this action。

Of course， if that right thing becomes the wrong thing because the program changed behavior。

 you can also learn that over time as well。😡，If the prefecture is， for example。

 inaccurate and the bandwidth usage is extremely high in the processor。😊，Basically。

 you did a very bad thing first of all， you were wrong in what you were prefeting and you did the wrong thing at the wrong time。

😡，Meaning the bandwidth usage was very high， so you actually get a very negative reward。

 as you can see， this's like touching the hot stone， right？😊，I get a negative reward。

 it's not as bad as that。But it's kind of like that bad for performance right And then there are different kind of reward levels as you can see。

 right if you did the wrong thing at an okay time， you get a negative reward。

 but not as bad as doing the wrong thing at the wrong time。 in this case。

 if you're inaccurate and the bandwidth usage of the system is low okay， you did the wrong thing。

 you wasted some bandwidth， but you didn't hurt anybody probably right that's the idea over here。

 that probably is probably because there's cash pollution effects that we don't take into check account over here Okay so that's the idea basically and you can actually configure it the nice thing about this sort of mechanism is you can change the states potentially online you can change the rewards potentially online and if you。

😊，Put a little bit more work into it。 You can change the actions also。

 so you can configure it potentially without changing the hardware。😡。

If you want to actually design a slightly different mechanism with a different reward structure。

 like a more conservative prefeer， for example， or a more aggressive prefeture。

 you can change program their reward values without changing the hardware。😊。

It can be programmble that's one of the advantages of this sort of generalized reinforcement learning based mechanism。

Okay。So there's more detailed overview which I will not get into but I'll give you an example because this now shows you like what it looks like kind of in hardware。

 so we have a Q value store， as I said we use Q learning。

 this is table-based mechanism and there's actually a lot that goes into the design of the store which I will not discuss but basically it records Q values for all state action pairs and then there's an evaluation queue this is basically a50Q of recently taken action so that we can evaluate what we did with this action。

😊，What reward should we assign based on whether the process actually requested the cash block that we asked for？

So when a demand request comes in， you put it in the evaluation queue and you actually extract features。

 state features from that demand request and also the processor。😊。

And then you look up this store Q value store for different actions。

 so if you have 16 actions for you get 16 values in the end for this state。

 what are the Q values of these 16 different actions and you pick the action with the maximum Q value that tells you an offset and you generate a prefetch for address a plus that offset。

 right？And then you send it to the memory hierarchy， which gets the data。

 you insert the prefetch action and state action pair into this evaluation queue so that you try to figure out。

😊，Whether you did the right thing or the wrong thing and what kind of reward value should you assign to this state action pair so that you can update the table accordingly so you need some time。

 you need to give it some time so that you observe whether the prefetch was useful or not useful because processor is not going to immediately use the prefetch it may then you know it but it may actually take some time for the processor to generate the demand request to use the prefetch you don't want to miss that because that's really important if you actually prefetch something that the processor is also going to generate and you did it at the right time that's really important information。

Okay， at some point。The evaluation is done and you update the Q value store。

 you update essentially the Q value associated with the state action pair。Okay。

 it's beautiful as you can see， and then when the prefetch fill comes in you basically set the fill bit meaning that prefetch is done and if the pret processoror requested and you know that processoror requested after the prefetch is done。

 if the processor requested before the prefetch fill bit is set。

 you know that the processor requested before the prefetch fill is done meaning the processor needed it before prefetch completed so the prefetch was not timely enough right so you can actually figure out this information。

😊，So it's beautiful in deep reinforcement learning。

 what you can do is you can replace this Q value store with a deep neural network。😊。

Deep reinforcement learning has been used actually for many games， for example。

 and I think Algo is one example people figured out that using deep reinforcement learning you can beat humans using in the go game。

 but anyway we did not go for deep reinforcement learning in this case because we're very time critical you want to make this decision within some number of nanoseconds。

😊，At most speakerconds。You don't want a lot of multiplications over there right made to expect your multiplication this is basically pure simple lookup tables essentially lookup tables you can think of it that way okay there are also other interesting things over here in reinforcement learning if youre think about reinforcement learning you don't want to really like humans for example generalize right they see different states and different states may be similar to each other and by doing appropriate quantization of the state values you can generalize out of that so by actually doing good quantization meaning collapsing of the orining of the state values for given state value and also doing designing your tables carefully you can actually learn much better and again these are interesting details that you may learn if you take a reinforcement learning course。

😊，Maybe you'll learn in a reinforcement learning lecture in in a more general learning course there's a lot here okay let me give you some results and then we're going to move to other stuff and prefetch any questions so far。

😊，Okay， does this sound interesting？Okay yeah， a lot of people aren't just so basically the results are good that's a takeaway there are a lot of prefes people are designed using heuristics like human design prefes I mean this is a human designed also but。

😊，Humans if you look at other prefes， humans dictate the policy that the prefecture follows here。

 a human designer designs the prefecture because they have the domain expertise。

 but they don't dictate the policy， they don't say given the state this is the action I'm going to take the prefecture figures that out。

 that's the major difference。😡，RightI think designing it completely using machine learning is a different issue I don't know if it's possible to do or used to do。

 but that's another direction to follow here the human designs a prefeure prefes figures out the policy in the past human designs are prefeure and human dictates the policy so it's not very adaptive as a result all of these prior prefets which are state of the arts at the time perform low so on the x axis you have number of cores on the y axis to performance improvement over no prefetching on these workloads it's a very large number of workloads you can see that Ptia is better than any prior。

😊，I' prettyfe。Okay， gain increase with core count also this is another interesting thing to look at here we're looking at on the x axis bandwidth。

 meaning GM mega transactions per second， how much bandwidth is available to the system to the core and the y axis shows a speed up over no prefetching and again prior prefets and then Pthia you can see that Pthia is good at all bandwidth configurations if you're very bandwidth constraint。

😊，You can see that other prefettureers actually lose performance on average across many applications。

 So for example， this prefecture， and it turns out the AMD threader。

 that particular version had the bandwidth value that's very constrained。😊，诶。

Because it's designed for mobile systems that don't have ample bandwidth， let's say。

 And you can see that if you turn on the prefeture， this particular prefecture。

 you lose 20% performance on average across hundreds of workloads clearly you don't want that。

 And that's why。In many cases， what happens is if some system designer thinks the prefecture is not going to be useful。

What they do is they turn off the pre。So there's a chicken bit which is actually changing the prefecture。

 whether you turned on or off in the bios for example。

 and you basically turned off so I imagine this right you design a prefecture at a micro architect。

 you did all the work。😊，Eventually， it's useless。Because no people don't use it right PTI is a little bit better in that sense because it can adapt to the memory benefits so it's a little bit better in this bandwidth configuration in some work codes it's much better in some work code a little bit worse so there's more room for improvement so that higher bandwidth configurations the benefits are of course higher as you can see as prefeure because prefe there's room more room for prefetch。

😊，O。Okay， so this is all open source， if you're interested in developing prefes you can actually build on it a lot of people actually have built on it in the scientific community and if you're interested Rahuul actually has a longer video。

😊，And this is the paper。Okay if you're interested so this is prefetching。

 this is reinforcement learning applied to prefetching if you're interested more on reinforcement learning this is a book I would recommend very strongly an updated versions purely online as you can see as you can see they actually talk about some of the applications one of them is Alphago which is one of the most successful applications we actually did a lot of work on reinforcement learningbased memory controllers and these folks they had an earlier version of this paper of this book that I read actually and after reading it we said oh we can apply some of these concepts to a lot of things in system design and we applied it in 2008 we have an ISCA 2008 paper on reinforcement learningbased memory controllers and the authors of this book really liked it so they actually included as one of the applications optimizing memory control。

😊。

![](img/42ca74b47661a64c9efa6c5c7d898f49_2.png)

![](img/42ca74b47661a64c9efa6c5c7d898f49_3.png)

Which is very nice also， right as you can see。😊，The prefecure came after this book was written。

 so maybe they will include it in the next version。

 so it's good to see more applications and these are the actually the authors who won the touring award。

 was it last year or this year。😊，Nobody knows this year or last year for reinforcement learning。

 basically it's an award that came a bit too late in my opinion。

 because I think this is a concept that's really important。😊，Okay。Any questions？

Okay so in real systems， there's a lot more in real systems that I'm not going to cover。

 but I'm going to flash some things so that I can get into some other prefe that I'd like to talk about we're running a bit late。

 but real systems actually have many of these hardware prefes so I have hybrid hardware prefes use multiple prefes to cover many access patterns This leads to better prefetch coverage。

😊，Potentiially better timelines of the prefes so they can prefetch early right but then this leads to more complexity now yeah many design an optimization decision how design each prefecture every prefecher has a design decision basically it's more bandwidth intensive if all of the prefetcherers are prefetching。

 how do you control that they don't do damage to each other as well as to the system in terms of performance。

😡，Yeah， basically prefeers also interfere with each other。

 you need to manage accesses from each prefeure。呃。In multicore。

 if you have multiple course that are actually accessing memory。

 this becomes also interesting because now there are multiple different issues like prefetching shared data becomes an issue。

 if you're sharing data between one processor and another processor。

 do you prefetch it do you not prefetch it， it's a good question basically because you may get coherence misses。

 cache coherence is an issue， which we didn't talk about in this course。

 but we will talk about it in the advanced course if you're interested in it。😡。

Prefetching efficiency becomes a lot more important in this case because you have many core and you have limited memory bandwidth again and bus bandwidth becomes more precious。

 cash space becomes more valuable because you're sharing the caches and the bus with many different cores。

 so you need to be a lot more careful essentially。This is one of the reasons like if you look at GPUs。

 GPUs have many， many， many core essentially connected to a limited cache space as well as limited bandwidth。

 so they demand a lot of bandwidth because they're vector processor some processor and as a result prefetching in GPUs are very tough in general so usually they don't do pre-feting in GPUs but we have also done work on prefeting in GPUs and shown that under some conditions you can actually get very good benefits if you are doing this carefully。

😊，So there are benefits to prefeecting even in GPUs with a lot of bandwidth requirements。Okay。

 there's also one course prefetes interfere with other course requests because there could be cash conflicts at multiple levels。

 bus contention， and you've already seen a lot of these concepts like the bank rank channel。

 Rob for contention。So you need to be careful with what you do when you prefetch。

 you need to throttle the prefets。😡，Meaning if you think the prefecher is causing damage。

 not improving performance， et cetera， by monitoring some metrics， you say， okay， prefeer。

 be less aggressive or turn off for now， and then you try again， right？😡。

Reinforcement learning does that nicely， but there is also a heuristic based mechanism that you can do you can design and essentially all processors that I know of have these heuristic based mechanisms。

 they actually design a prefecure， that's good using some heuristics some of which you have seen earlier in the past if you want to learn more about it。

 take the advanced architecture course and then there are many prefes in the system so they have to design also a heuristics to control the prefecture。

 meaning the prefecture should be aggressive at this moment， not aggressive at this moment etc。😊。

So you can see the complexity of the system even with prefeting rights。

 and then you saw it in cacheching。So we actually designed a lot of heuristic mechanisms。

 so this is one of them I'm going to flash some papers if you're interested in this area we're not going to talk about that。

 but basically you can control the prefets in a coordinate way。

 you need to be careful about shared resource cash management for example。

 you need to be careful on how you design the memory control that wants to have a prefetcher because now memory control gets requests from prefets as well as demands how do you prioritize between them sometimes prioritizing prefetch requests over demand requests is actually reasonable because prefetch request goes to the same robot buffer that's open and you can service that quickly before switching to another demand。

So there are a lot of interesting things over here that again， we don't have time to talk about。

 but it's fascinating， I think， and these are actually real problems that you run into when you design a real processor。

 whatever that processor may be， CPU， GPU accelerator。😡，Okay， any questions？No question。

 so I'll jump into execution based prefetion。Let's see。

This scenario area that's close to my heart because as I said， I did my PhD on this topic。

 at least a type of execution based prefecure。So basically。

 execution based prefectures work interestingly， differently from what we have discussed so far。😡。

The idea is to execute or pre execute， execute early。

 meaning a piece of the program solely for prefeting data。😡，That sounds nice， right。呃。Basically。

 you only need to pre executeec code at leads to cachems。If I can identify it， of course， right？

So basically I'm going to define speculative thread。

 speculative thread is a pre executedcut piece of the program that can be considered as a threat。

 it can actually be a real threat at some point if you're doing it at the software level completely。

😊，The speculative thread can be executed on a separate core separate processor on a separate hardware context like in fine grain multi threadreading right。

 a different hardware context is used for the separate thread or on the same thread context in idle cycles during cache miss when the main program stalls you put in the speculative thread that does prefeting and when the main program comes back you basically switch in the main thread and hopefully the specative thread that prefeting that brought。

😊，Useful cash blocks into the cache so that the main thread executes faster。

So to show this nicely you can do this for branches also I'm not going to cover that but you can do this for loads so let's take look at an example this is the main program over here in the middle we're going to look at only the load for now essentially you design a speculative thread somehow this thread is a pruned part of the program that is solely there to prech。

😊，And then you fork at some point early before you get to the load long before you get to the load。

 once you fork， it executes some instructions that would generate the address of the load。

And while the main three is executing， normally the specululatorulator executes somewhere and gets to the cachem。

 it generates the address of the load。😊，And essentially， starts the cachem early。

 and this cachem completes before the main thread gets to the load。 It's beautiful。

 So you're basically overlapping the latency of execution in the main thread。😊。

With the latency of actually prefeting using some other thread to prefetch for this load。

 does that make sense？So it's a beautiful idea， it's a little bit expensive in the sense that you need to generate a thread。

 you need to actually execute it， et ceter， but people have applied it to branches also which I'm not going to talk about and loads and these are some beautiful papers that talk about the idea。

😊，So let me talk about my idea， this is actually implemented in many processors in some form also today。

 but we wanted to make this actually relatively easily implement and in hardware easy implementation is really important we call it runhead execution。

😊，Let me give you our motivation at the time and our motivation is prefetching still but there's another motivation for this because our benefits are going to be similar to a large instruction window so you've seen auto of order execution lecture 15 right and in out of order execution we had an instruction window right you could buffer some number of instructions that's determined by your reservation stations etc if your reservation stations are full you cannot get more instruction into the process。

😊，Let's take a look at an example of what happens when you have a load instruction that misses the cache。

 we you have only an8 entry instruction window you basically get a load instruction。

 misses the cache takes hundreds of cycles， and then you have a branch instruction that's dependent on this load instruction and then let's assume that you correctly predict it and then you fetch instructions on the correct program path。

😊，That you can execute， but you cannot finish because of precise exceptions。

 Remember the precise exceptions lecture here from 13 to 14。Okay。

 now you're stalled because you don' have you cannot get any new instruction into the pipeline。

 I already said this these actually out of program order， but cannot be retired。😡。

Now younger instructions cannot be executed because there's no space in the instruction window。

 as you can see， so this load instruction cannot be fetched。😊。

Or cannot be put into the instruction window and execute it。

 even though that may actually be a cash miss， right， But we don't know that。 We cannot。

 We don't have any space in the processor to put it in。

So the process stalls until the altus is serviced this alimus。

So basically long waitency cashms are responsible for most full Windows stole this is what we observed this other people have observed also so we did these studies with Intel many studies across many workloads and if you have 128 entry instruction window which Pen toium forehead at the time we' were talking about 2001。

😊，呃。This picture is very similar today because applications are even more intensive today。

 essentially most of the time the processor is fault。😊。

Its doing computation in the screen portion only 30% of the time let's say and most of the time the stalls are due to long latency cash misses because you're going off off chip and you need to wait for a long time and if you had a larger instruction window this is what the picture would look like if you magically increase your instruction window size to 2048 16 times this is what you get you get a lot of performance improvement more than 30% as you can see this is execution time average across hundreds of applications。

And your stall time reduces still your L2 cache are responsible for most of the stalls。

 but most of the time you're computing。😡，Computing doesn't mean that you're doing useful work。

Because there may be branch predictions that Green Park trendss。 But that's not our target over here。

 And as you have a very large window， branch predictions become more and more important。Okay。

 but this is a good this is what you can do with simulation if you have a good simulator that you design you can actually do studies like this okay this is what I get in real system and you can validate it with a real system but you can increase the size of the structures and say if I had a 2048 entry window this is the performance improvement I would get across 150 applications almost I would get 30% performance improvement which a pretty significant improvement across many applications and these are actually all of the applications that Intel used to design its processor within its let's say good times Intel is not in good times today but in 2001 it was good times let's say。

😊，Okay， so basically the problem is if you have out of order execution， so out of word execution。

 it requires large instruction windows to tolerate main memory latencies。😊。

And as main memory latency increases， the instruction window size should also increase to fully tolerate the latency。

😊，And you could try to build an instruction window and at the time。

 for example at Intel there was a lot of push for building very large instruction windows we took out a very different approach basically we said that this is possible it's good to do research at this area but it's very expensive in the end。

 maybe we should handle these long latency missile in different way。😡。

So if you want to build a large instruction window。

 it's hard to get low energy consumption because you know from Out ofward execution that you need to have a large tag matching logic。

 big load store buffer， if you want to have short cycle time。

 again large instruction window doesn't help you because wake up and select logic becomes longer。

 register file access becomes longer， bypass latencies for forward forwarding data becomes longer。

 and all of this makes the design more complicated。😡，And it's very hard to get essentially low power。

 short cycle time and low design and verification complexity as you increase the window size in fact。

 it's hard to get any of these if you increase the window size because increasing the window size affects all of them。

😊，So our idea was to do something different and I'm going to give you what that is basically it's described in this paper。

 it's a technique to obtain only the memory level parallelism of a large instruction window。

 we're going to give up some of the other benefits， but we're going to be much simpler， let's say。😡。

The idea is when the oldest instruction is a long latency cash miss。

 we're going to take a checkpoint of the architectural state， meaning the register file。

 we're going to copy the register file program counter somewhere。

 it can be easily done actually not that hard because it's done already four branches today。

 and then you enter a very speculative mode called run ahead Mo。😡。

The whole purpose of this run ahead mode is to speculatively execute instructions。

 we're not going to retire instructions， we're going to forget everything we've done at the end。

 speculatively execute these instructions with minimal stalling， meaning if you get a cachem。

 you're going to basically mark the destination register as invalid so that you don't actually execute those instructions。

The purpose of the pre execution is to basically go look ahead in the program or run ahead in the program and discover instructions that lead to cash misses。

😡，These are good prefes， right。Long latency instructions or instructions that you don't want to execute。

 it could be anything because we're purely speculative。

 We're not satisfying any contract with the programmer here。

 We basically checkpointed the state we're going to get back to that。😡。

We're doing it completely transparently to the programmer you can say basically I'm going to drop this instruction because it takes too long to execute this instruction and it's not going to satisfy my purpose which is generating prefet right we're going to mark them specially with special bits called inmail bits in the register file in the store buffer in the cache if you want to design that and you drop them。

😊，Now dropping these instructions makes space for other instructions that's the key realization right these long latency instructions you don't execute you can get them out of the machine now you can bring in other instructions into the machine that you can execute that's the idea this enables room for later instruction in the window essentially when the original mist that caused entry into this mode returns。

😊，What we do is we restore the checkpoints， we flush the pipeline and resume normal execution as if nothing happened。

Basically， that instruction， load instruction caused entry into any head mode because it took a long latency cache miss。

 we go back to exactly that point， except hopefully there will be a lot of stuff in our caches that we prefeched。

 Okay， let me give you an example， Ily what you want is perfect caches never stall right due to long latency misses。

Ideally， you always compute。That's not that's what you want ideal。 If you have a small window。

 What happens is you compute， you get a cache miss， long latency cash miss。

 the proor computes a little bit， and then at some point it stalls because it cannot bring in new instructions。

And the stall is long as there some point， the mist returns back and you go back to computation again because you can actually bring in new instructions into the processor。

 but then soon after especially if it's a memory intensive workload。

 you get another cache miss and then soon after processinging stalls and your stall is very long right。

😊，So run ahead， gets you in between， as we will see， you compute。😊，You get the cash miss。

Soon after this cache has becomes the oldest instruction in the window。

Which means that you can actually checkpoint your state in a nice place as we've discussed in state recovery right precise exceptions。

 it's a precise point at that point and at that point you enter the speculative processinging mode called run ahead mode where you drop instructions that are long latency。

 you certainly drop this load because you're not waiting for it anymore you want to go ahead so that you can catch you can fetch other stuff into the window and at some point you reach load two because you're executing the program basically speculatively and this load two generates a cachem。

😊，And you can start that cache miss early， and after some point， the first mystery turns back。

 we restore the checkpoint， flush the pipeline。And we start from load one and now load one hits in the cache because clearly we service the miss。

And we start computing again。During some point， the second miss。

Completees and when we actually reach load two in the main execution， not in run ahead execution。

 you get a cash hit because you completed the second miss。😊。

And then you do some more computes and you save a lot of cycles compared to a small window。

 The idea is basically， instead of stalling。For a long waittency cash miss。

 keep specully executing the program so that you you can discover other cash misses and so that you can service them in parallel in the main memory。

 Of course， this works nicely if miss one and miss2 goes to different banks in main memory， right。😊。

Even if it doesn't go to different banks， you still reduce the latency of the mess。Okay。

 so that's the idea basically， I already said instead of stalling during an L2 cachem。

 you specul the processor speculative pre executecuts the program far ahead into the instruction stream without stalling for long latency instructions。

😊，These pre executed loads as well as stores， independent of alous instructions generate very accurate data prefets。

 in fact， the accuracy of this is very high because you're really executing the program。😡。

In our results， we see that 95% accuracy is actually very common。

 it's fascinating right it's very hard to get 95% accuracy with a prefecture that you design。

This is true for irregular access patterns also a prefeture may not be able to capture some of these patterns because some of these patterns are they don't necessarily have predictable deltas right it may be that you're executing like a graph you're going through a graph and you actually or multiple graphs and the addresses have no relationship to other。

😡，Okay， also you get instruction pre-feting benefits。

 we not talk about instruction prefetching as much。

 but instruction prefetchinging is a problem also you try to access the instruction cache。

 you get a cash miss， what do you do well， the processor stalls immediately right because you cannot fetch the instruction so in this case we're actually executing the program and instruction in the predicted program path are pre-fetch into instruction cash。

😡，And also there's another benefit which is interesting。

 you actually train the tables of prediction structures like hardware prefecure。

 branch predictor and this benefits from this future information you're kind of scouting actually when some or now oracle implemented run ahead they called it scouting for good reason because they were actually scouting the program this speculative thread is really scouting what's going on before the main thread reaches it right as you're scout you go and you explore the environment before before your let's say people come to that place and you try to make it nice for them okay so let me cover the advance and disadvantage and then I'm going to give you results but before will finish after will finish the first part of the lecture after we've cover the advantages I'm going to go through this quickly because I already said a lot of this so basically they are big advantages to this you have very accurate prefetches。

😊，It's simple to implement much， much simpler than actually increasing the window size。

 which touches a whole lot of structures here， you're not touching a whole lot， you're touching some。

 but very little changes。😡，No waste of hardware context。

 you don't change hardware we're really using the main thread context。

 although you could implement it by on a different context also like IBM power 6 did。

 they actually use a different context to do run ahead execution no need to construct a special purpose thread for prefetching the program is a threat you just eliminate some instructions you say I'm not going to execute these instructions in this mode。

😡，Okay， so of course there are disadvantages， there are extra execute instructions。😊。

Hopefully they will provide benefit if they don't provide benefit， figure out not to execute them。

 so there need to be throttling mechanisms for Re ahead also。

Limited by branch prediction accuracy because you're really executing the program if your branch predictor is wrong at some point。

😡，You may actually， And if the branch prediction is dependent on a value that you don't have because it's dependent on a cash miss。

 you basically。Cannot continue on the correct path anymore。 This is not necessarily terrible。

 but not good， also。You cannot prefetch dependent cash misses。

 which is a problem which we may talk about and the effectiveness is limited by how many cash misses that you have under the shadow of one miss basically if you can get to the next cache miss quickly that's good if the next cash misses。

 let's say a million cycles later。😊，Runite execution will end before you get to the next cashness。

So it's good to think about these。So a prefech distance how far I had to prefech is limited bio memory latence。

Okay， so this is actually implemented in multiple processor。

 but we're going to talk about that after we take a break so sorry today is a short break。

 so we're going to be back a little bit after the bell rings 10 minutes later and then we're going to continue prefeing and then we're going to do angue。

😊，Okay。That's your punishment for coming at what is this day， holiday？

I I guess a lot of people think it's a holiday day， is that true？Or effective holiday。Okay。😊，そ。走。嗯。

嗯早点。这个还出。Oh。这过程。对。そ。这快这。这次。そなんで。Thank。对。我。然好说。没有。Yeah。Yeah。Yes。てす。我。啊，有。Okay。

 I think we can get started。自前是。So now you've seen another prefeure。

 the first one was reinforcement learning based， this is a complete different prefeure。

 as you can see。😊，Now let's take a look at some results， as I said。

 this was part of my PhD thesis and I improved this mechanism a lot during my PhD and we did some of the early works with Intel so we used a lot of their traces or workloads。

😊，I'll go through this relatively quickly， but if you look at it， these are real。😊。

Results with real very very assimilulatorators that are very close to Pentium four at the time and you can see that if you don't if you turn off the prefecture you lose a lot of performance the blue baseline is baseline with a very good prefeure it's a streaming type of prefeure that Raho has covered two lectures ago if you do only run ahead you're actually better as you can see。

But maybe not as efficient and if you combine prefeure and runhead。

 you're 22% better in terms of performance compared to just the prefecure。

On average across 147 workloads this is actually a pretty significant number okay that's the average and these are all different workloads like floating point integer。

 et cetera multimedia okay so compared to large windows the result also looks not bad basically this mechanism gets the performance。

😊，Of almost a 384 entry window without having to build it。Basically。

 you start with 128 entry windowd and you add runhead execution to it。

 you get the performance of almost a 384 entry window， which is not bad， right。

The reason you don't get the full performance or a better performance is because a 384 entry window doesn't speculate。

 I mean doesn't speculate like we do at least it doesn't whenever you execute an instruction you keep the results in the window right and you write them back here we make a passover the program in the speculative mode and we forget all the results we never save any of them and we execute we re- executeecute all of them again after the runhead mode ends。

😡，Okay， so there are a lot of interesting trade offs。 And we also said that， oh。

 can you do this in order machines and the ideas again。

If you have an in order baseline this' is actually a good picture to see because you've seen in order processors and then we look at out order processors right if you look at this low blue baseline line it's an in order processor if you add running ahead to it you get a lot of performance almost 40%。

😊，But this this red one is out of order baseline， nor run ahead。

 so you can see that there's a big difference between in order and out of order。

 This is why we have out of order execution processes today。

but if you actually add run ahead on top of the out order processor。

 you get 20% or so and you can see that basically the benefit over an in order processor is much larger if you implement run execution on an in order execution processor。

 which doesn't have any latency tolerance。😊，You get higher benefits because Auto word execution processor already has some latency tolerance and we discussed an outward execution that's the main benefit of an outward execution processor。

 so adding run ahead on top of that provides performance benefit but not as much as it would if you actually did or run a ahead execution on an in order processor which doesn't have any latency tolerance。

😊，Okay， so this is fun， I could keep doing that actually this is nice because Sun rock was an in orderder processor。

 they implemented a lot of the concepts that we were working on inside their processor and they showed essentially the same thing。

 basically on an in orderder processor configured similarly to what we have configured run ahead with。

 you get 40% better performance。😊，At the time 512 kilobytes was a big cache size we're talking about it in 2002 or so even though this presentation was later。

 we actually revealed some of the things later this is actually a very interesting thing they designed SunRck for commercial workloads and they have this picture in one of their works they vary L2 cache size on the X axis and normalize the instructions per cycle performance on the Y axis no scout is not no runhead basically scout is if you do runhead execution and you can see that at some point you get 40% better performance and given cache size you get better performance by adding run ahead but there's another way of thinking about a system right you add something and you remove something else。

😊，And that's the idea here， for example， run aid execution with only one megabyte cache size。

 you have only one megabyte cache and run aid execution。

 the performance is equivalent to a system with no run aid execution， but eight megabyte cache size。

So they say this is their slide again， by implementing run execution。

 you can buy seven megabytes of space。😊，That sounds good right so you can see that there's a tradeoff between caching and prefich Cas are not very efficient as we have discussed in caching lectures。

 in fact there are studies that show that in caches more than 80% of the data that's resident if you look at your cache in the processor right now more than 80% of the data that's inside the cache is not going to be used。

😊，By the press。Very inefficient。You have these large caches so that you can capture that little amount that's going to be a reuse Okay very interesting。

 So people actually do a lot of cash optimizations。 Okay。

 so here you can see that if you implement run execution processor with I don't know 4 mebytes caches。

 you can buy 16 12 mebytes。😊，Of cash space。Okay there's more。

 this is our paper I'm going to to tell you a little bit more story over here because if you guys are interested in research。

 for example， I think it's good to think about research in general and I have my story of course with many papers but I'm going to give you this story so this was implemented the sunr this is sun paper So actually went even more they actually did some interesting things where they did run ahead and they also tried to preserve the results。

 they complicated the machine a little bit more but this it's an interesting paper a bit hard to read but you can see their results and then eventually they were both by Oracle and Oracle actually for some time nurtured their pro design team but eventually they we're going cut it so they don't exist anymore very sad but it happens IBM implement a version of it which is also interesting which I'm not going to talk about in detail but they implement prefeting and run ahead they compare both just like we did and video implement a version of Rhead also they actually showed a lot of really good results。

😊，Let me see if I want to highlight anything。Yeah。I guess maybe this one implements a run head feature that continues to execute microco specul after data cache miss。

 this execution can trigger additional cache misss that result in the shadow of the first miss。😊。

Blah， blah， blah， where's the result。So these and other features help Denver outco outperform cortex by more than 2。

6 sex on a memory readed test， so basically their goal is to overcome the memory latency so these are real results from real companies as you can see。

So there are also enhancements which I'm not going to talk about otherwise we won't be able to talk about the next things。

 these are actually works in my PhD basically what are the downsides whenever you have an idea。

 the idea may be very good and we actually believed in this idea。😊。

There was actually kind of multiple temps in the research community and also within companies。

 one camp said we want to make our processor more and more and more and more complex。

 we were on the other attempt as you can see we don't want complexity that much， we want simplicity。

 but we want some intelligent mechanisms to actually cover for these long latency cash messages that's the idea over here。

So we kind of fought against the stream， if you will。

 you' swing upstream right it's not an easy thing to do。 So if you have an idea， first of all。

 you need to be convinced that the idea is good。😊，And if you're convinced that the idea is good。

 you push for it right even if none of the world， nobody in the world is pushing for it。

 so this is very important that's why change happens。

 that's how change happens basically you got to believe in the idea。

But also you got to realize the idea may not be perfect right and that's the realization basically there are other things that need to be improved for this idea to make work in fact we improved some of these and NVIDdia picked up some of these ideas like energy inef they were concerned about that also basically runed execution performs a large number of instructions speculatively we said that okay let's figure out when this doesn't make sense in some cases when you're executing a large number of instructions speculatively。

 you're also getting a lot of benefit by doing that so it makes sense but there are some cases where you're executing some of these instructions and you're not discovering any cash misses。

The idea is basically add some hardware structures to figure this out。😡。

Figure out when runite execution is useful or not useful and turn it off or make it less aggressive when it's not useful that's the idea this is called deficient runite execution。

 it was published in 2005 and NVD actually picked it up in their results I don't know what exactly what is this SunRck or IBM did but I believe they have some efficiency mechanisms also。

😊，There are also other issues one is ineffectiveness for a pointer intensive application I'm going to mention that a little bit if you actually have a cache miss depend on other cache miss the address of the first the data that's being loaded why the first cache miss is going to be used as an address for the next。

😊，Load instruction， You're not going to get that data because it's a cache miss。

 right So can you actually predict things when you're doing pointer chasing。

 this becomes a problem because once you get a cache miss。

 you don't know the address of the next node。😡，If you don't know the address of the next node。

 you cannot fetch that next node and you cannot fetch any other node after it。

So this is a very tough problem in general， and we actually have a limited solution to this。

 which is predict the address。😊，Predict the data that's going to be loaded by the first cache miss right and we have a way of doing that。

 but I'm not going to discuss that。 I'm going to show you a picture on what this could enable soon。

 Okay， and then there are also other issues like irresolvable branch mis predictiondis If you're in the speculative mode and you have a branch mis predictiondiction you go on the wrong path and if if this branch is depend on a cache miss。

 you cannot resolve this branch because it's marked email mail it because its until you don't have the data value to execute that branch yet As a result you stay on the wrong path until the end of the run ahead mode right It turns out this is not that bad。

 but it's not as good as being on the correct path。

 Why is it not that bad Because if you're on the wrong path， you're not doing any harm。In the end。

 this is all speculative right。You may be doing some harm by getting some wrong things that are not going to be used into the cache。

 but our analysis， we analyze this a lot actually at the time。

 our analysis shows that you can actually， you'd better be executing on the wrong path than not executing if your goal is to optimize for performance because the wrong path actually provides benefits because you're on the wrong path。

 but some of the prefetches that you do over there is useful for when the main program executings on the correct path as well。

Because of because the program structure is that way right so you may actually mispredt the hammock branch so you have a branch over here if else and then eventually there's a merge point in the program and you mispredicted the hammock branch。

 but eventually you're on the correct path right even though this is the wrong path technically because your data values may not be correct but you're on the correct path and you may still prefet things that are actually useful for the other path right that's the idea basically so there's a lot of analysis that we did in hindsight we should have done a security analysis at the time。

 but you were not thinking in that direction because if you did a security analysis on the wrong path we would have discovered perhaps meltdown inspector much earlier then they were discovered in 2018 so a lot of these papers have very rigorous performance analysis of the wrong path but not the security analysis side channelnel analysis anyway these are some papers you can take a look at them if you're interested and let me give you this one this is actually fascinating to me and I think this is one of the hardest problems that we have in microproor design which is。

😊，If you have pointer chasing， if you have addresses that are dependent on each other。

 how do you handle them so for example。😡，If you look over here。

 this load two is executed in our head mode， but it's in。

 meaning it's dependent on the data that's generated by load one。

 it's using the data that comes from load one as an address。😡。

This happens when you're doing pointer chasing clearly right and load one you don't have the data that's the load that calls you entry into run head modes so you enter run head mode。

 you execute a bunch of stuff you cannot execute this load two because you cannot compute this address because it's dependent on this and then you exit flash the pipeline you enter run ahead again for load two it turns out and then you execute so you do a lot of execution here that's useless if you were able to do something smart with this load one meaning predict its value accurately which is possible actually in some cases。

This load two can compute its address。And it would generate its myth。

And it would paralyze the miss so basically you would save a lot of cycles if you are able to correctly predict the value that's being loaded by load one。

😊，Again， I'm going to tease you， you can read the papers and you also save specative instructions。

 it's not just you save cycles， you also save a lot of work that's going to be potential that could be potentially useful actually。

 but you don't need it basically if you actually do the right thing over here。😊。

Okay again I'm not going to tell you exactly how to do that if you're interested in that this paper is a longer version it's basically depend on the memory allocator。

 if your memory allocator is allocating things nicely。

 you can predict that address nicely in a graph based or linked data structure so in this paper we show that you can actually change your memory allocator and you can actually get very good results but if your memory allocator is allocating things randomly then there is no relationship between this load and this load or this load and its address okay that's enough hint for you。

😊，Okay。Any questions？Sounds cool， right？Yeah， it's good to do a PhD that's really adopted by industry。

 doesn't always happen。 And that's not always the goal。 So if you do a PhD， if you do research。

 your goal should not be immediate adoption by industry。 if it happens， that's good。

But the goal may be okay sometimes some ideas take time right right now， for example。

 we're doing work on pressing in memory which probably we're not going to get to and my students are doing teases on pressing in memory even like 10 years ago they were doing that。

😊，It's not adopted completely yet， although there's a lot of sign for adoption。

 but maybe down the road， it's going to be adopted， right。

 So you got to believe in the research and you got to actually do the right thing in the research to。

Explore a new idea because maybe no one is exploring that idea。 In fact。

 when we were doing some of the pressing and memory research。

 no one was really exploring the idea as much。 And as a result， you're kind of alone right。

 You may feel alone。 but that's fine。 I think right that's what an innovation means If everybody was doing the same thing。

 that wouldn't be innovation right You should be doing something different to actually leap forward。

 So it doesn't have to be adopted immediately。😊，Okay so let me give you so this was actually selected as a test of time award in HPPC 2021 like these major conference give test of time awards and HPPC gives a test of time award for a paper that's published between 18 years to 22 years ago and we got this award in 2021 18 years after publications and we were actually asked to give a presentation and we basically in hindsight wanted to give what we had in mind so I said a lot of this actually in the early 2000s there was a large focus on increasing the size of the instruction window and designing bigger more complicated machines so right it was actually a different way of thinking more than the implementation maybe the thinking was important right it basically said cheap the out of order course simple and small。

😊，At the expense of some benefits。But hopefully this is still a good tradeoff right Use aggressive automatic speculative execution solely for prefeting right and this is actually synergistic with prefeting and branch prediction methods。

 This doesn't hurt any other method that's designed in the system。😊，So at the end。

 a lot of interesting and innovative ideas ensued after we published this work。

 but we also recognize like while we were doing this work。

 we discovered this paper that was published in 1997。

Like four years before we actually started this work actually almost five years。

 this is actually a somewhat forgotten paper but we did our due diligence and we actually looked at all of the literature and we found out this paper and we said okay this looks very similar and it's actually very similar except it's done on a different constraint a very simple processor let's say but they do show some benefits and even though our internal name for our idea of scratch mode execution。

 we changed it to what their terminology this is also doing the right thing in my opinion right we don't want to create new terminology for some existing thing in marketing you may want to do that we're not marketing this is science right in marketing maybe you create a new terminology and sell something although in the end it maybe to discovered but here we basically found out that okay scratch mode execution the reason't what scratch mode is you go into this mode and you scratch it away afterwards right and these guys called it run ahead and we said okay runhead is also good。

😊，So we took Gr ahead， so we called it Gr ahead。And we had a lot of conversations with Jim Dunes actually who really liked our work and who's happy that his paper got more attention after we did this work。

😊，Okay， anyway， there's another inspiration， there's a beautiful paper actually if you're interested in this。

 this is the paper， one page。😊，It's in the wild and crazy idea session in 1998。😊。

And it says MLP as ILP no， it's a very provocative paper in the sense that it says basically we should not be caring about a few cycles here and there。

 the key thing is MLP memory level parallelism， meaning memory is hundreds of cycles。

 don't put your effort as much into a few cycles here and there。😡，Which makes the point。

 I think with four words over there MLPS ILPino， and it actually it talks about a bunch of interesting ideas。

 maybe these are some things we should do， including build very large instruction windows and also something like running ahead don't stop speculation because the oldest instruction in the machine is are cash miss。

😡，Thats ceter， well clear there are ideas here。So what our paper did was actually to demonstrate that idea fully。

 okay。😊，So in this talk I also said my architecture especially memory is critically important and fun and impactful。

 so I encourage people to look into these issues and also when it was very interesting because there was a great example of harmonious industry and academia collaboration between Intel and where I was at at the time at UT I think fundamental problems will always remain fundamental。

 cash misses， branch prediction， control flow， data input to the processor。

 we're not going to solve these completely。😊，And they will require fundamental and creative solutions it's becoming difficult to come up with these solutions because there's been a lot of effort that's being done but that doesn't mean that people cannot come up with with a different way of thinking。

 you cannot come up with a completely creative way of solving the problem That's why I think it's good to push more with creative and critical thinking How can I solve the problem as opposed to how can I have chatt GT summarize this thing for me right's because it's not going to come up with something new maybe right I don't know。

If you can get it to come up with something new thats would be interesting so this is a citation for the test of time award you can read it I'm not going to talk about it because we're running out of time right now。

 but it's actually a very good citation in my opinion okay so what I would say is basically to you whatever you do it doesn't have to be research follow your passion because that's how you can actually make an impact and make a change in the world and we had a lot of pushback in Renet within Intel and outside the community also but because they were saying essentially this will idea doesn't work we should always build large instruction windows。

😊，We didn't necessarily believe them We believe the data but also realize the downside of the approach and make it work right so if this requires resilience。

 of course， that's why these are very good qualities to have if you're actually swimming upstream。

Focusing on learning and scholarship is really important because anyone can say oh this idea doesn't work right but in this course you've seen it's about the tradeoffs right any idea has a positive and negative you should consider the tradeoffs and in the end you should evaluate the idea。

😡，I can say， well I don't like this idea， yes that's true。

 I don't like some ideas that doesn't mean that they're bad ideas or wrong ideas。

 they should be evaluated in the context that they're going to be employed in and in that context they may be good tradeoffs。

 right？😡，Building a very large instruction window machine is good in a context where you actually。

Can bear that cost， for example， right， That's not necessarily a bad idea。

 It's an idea that works in some context， right， It's good to think about that。

 right under some workloads， et cetera。 in the end。

 that requires a learning and scholarship approach as opposed to dogmatic approach， right。

 You sometimes see this dogmatic approach in industry or even in academia， right。

 this idea will never work。 We have this a lot with crossing in memory。

 D manufacturers will never implement it。 Ro hammer is not a problem。 Well。

 D manufacturer is implementing stuff right now。 So you can see actually， these things right， Okay。

 So in the end， the quality of your work defines your impact。

 I would say And all of you individually and collectively can make a good impact of the world。

 assuming that you have a good mindset， good focus and good goals。 The key is basically having that。

😊，Good mindset， good focus， good goals， and they're very sharp。

Keen focus on doing something important， let's say。

Okay so there's more on run execution as you can see I can talk a lot about runed execution there are a lot of interesting details et cea。

 and there is actually more work I don't have it in these slides but I think we have it in this fall 2024 lecture there is actually more work going on on run execution where more recently people have figured out how to parallellyze instructions in run ahead mode so that you can get vector level parallelism。

😊，And one of the works was actually won the best paper award in the microcro conference in 2023。😊。

So my thesis was 2006 and we're 2023 and this sort of work is still reading best paper work so I'm happy and proud of it as you can see。

 so there's interesting work that people can uncover if they look at the problems slightly differently and if I try to solve real problems。

😊，Okay， and then we have a lot of talks if you're interested you can look at that I also have much more recommended material on prefeting we're going to finish the prefeting part of the lecture if you're interested there's a lot more on prefeting and we have a lot of lectures but again we don't have time if you're really interested you can take the。

😊，Computer architect， your course。And that brings us to the end of the first part of the lecture。

 any questions？No， okay， now we need to switch the second part。Let's see if I can do it。Well。

onicika is writing her next paper。

![](img/42ca74b47661a64c9efa6c5c7d898f49_5.png)

Apparently， I'm not that。Okay。I think I should be able to it no。The question is where it is。

There it is。啊截图。It's very hard to see things here， Okay， that looks good， right？Something wrong。

It's good。

![](img/42ca74b47661a64c9efa6c5c7d898f49_7.png)

我给我自。But I want to you pull up this place now， you slideshow。 Okay， it Okay， like this。 Okay。



![](img/42ca74b47661a64c9efa6c5c7d898f49_9.png)

Okay， is this good， I think it's sharing。 now right， That's good， yeah， okay。😊。



![](img/42ca74b47661a64c9efa6c5c7d898f49_11.png)

Yeah， we haven't figured out how to do this to yet， at least I haven't。

 but if it's sharing there now， it's good。Okay， all good。Okay。No questions on Runhead。

Does it sound interesting？Okay， for some people it does。 That's good， yeah。Yeah。

 I think all of you guys are capable of doing very interesting things like the salsa clearly I'm proud of this right。

 I mean and I think people who are doing a PhD should be really。😊。

Focused and they're excited about what they're working on they should be really solving that problem that's what a PhD is all about right you stay up all night try to make it work。

That sort of drive is really important， otherwise what's the point of doing a PhD I would say to many people。

 but I think this is the kind of thing that you could do as an entrepreneur also right if you're an entrepreneur you should also be very keen focused on making things work in the right way。

Okay， so we don't have a lot of time to finish this。

 but I want to give you like an epilogue of this essentially yeah， zoom。😊，Zoom tricks。

So let's I was hoping that we will cover pressing in memory。

 but unfortunately we will not be able to cover press in memory。

 can you can read a lot of papers or you can watch a lot of our lectures。

 a lot of our materials all online。You can look at it， but let's see how much we can cover。

 but I want to give you basically an overview review of what we have covered so far and what we have not covered。

Including pressing and memory So essentially this was a slide that I present in lecture one。

 I think we've covered a lot of this basics principles and precedes， essentially。

 hopefully I've given you a principled view of computer architecture in many lectures and I've also given you like precedes meaning a lot of examples from the real world right a lot of the concepts。

 essentially what。😊，Essentially， every lecture we've gone through is implemented the real world。😊。

In different ways in many different machines， maybe I'll get to that again and hopefully we've learned how a modern computer works underneath more importantly hopefully we've figured out how to evaluate tradeoffs of different designs and ideas because that's what matters in the end right and you implemented a principal design a very simple microprocesor。

😊，It's unfortunately maybe not satisfying to some of you。

 but this is also a bachelor's first year course right if it was a later course you could implement a more sophisticated pro right？

And you again in the labs you learn to systematically debug increasingly complex systems that's what the labs are all about and hopefully at least part of this lecture enabled you to have a base and fundamentals to develop new designs and also evaluate them if an idea is thrown at you for example。

 if somebody talks about processing in memory and you've never been exposed to it I want to do processing inside the DM chip you can think about some of the tradeoffs right now right。

😊，Maybe it'll take some time， but you can think about it， right。

 or you can come up new designs on your own。😡，And。I think my focus is usually on basics。

 principles and precedents and how to use them to create and implement good designs。Okay。

 we discussed these goals also， hopefully you're at a better point right now that where you can design better hardware。

 hopefully because of that knowledge you can design better software also。

 you know what caches for example， you know not to trash your caches when you write software。😊。

You can design better systems。And hopefully a lot of these actually have realized and most importantly again。

 hopefully you can solve problems better think in parallel and think critically。

 these are the things that I would like to really inject when I actually try to teach。

 let's say right， because thinking critically is really important in my opinion if you if because knowledge can be forgotten right knowledge is knowledge。

 can it can be forgotten， it can be releart。😊，It can be learned without a lecture。

 it can be learned by actually going， I don't know reading books right。

 but critical thinking is a bit harder to get， it's important to actually show that with tradeoffs and examples。

 I would say。😊，Okay， thinking in parallelism also important。

 but I think that's what you learn by designing hardware， the hardware is because hardware is。

 as I mentioned to you in the first lecture hardware is inherently parallel right。

 a lot goes on in hardware， if you really want to think in parallel you design hardware。😊。

And then you go into app parallel programming， once you do parallel programming parallel programming will be easier in my opinion。

 after you actually do design hardware because everything goes in parallel and hardware。😊，Okay。

 so you come a long way， we've start from transistor as a building block and built up the virtual memory and system software mechanisms and in the meantime we talked about logic design in the first part of this course and then talked about execution model。

 ISA， micro architectureiture， and many execution paradigms that don't fit into this line。😊。

And then we talked about memory system， memory he cache on prefeting， including this lecture。

So they covered a lot actually， you guys are quite accomplished right now， in my opinion。

 it's not easy to cover a lot of this material， but this gives a very good overview of the system。😊。

So I think maybe I'll talk about three key takeaways first of all one what will we covered as real and used in real systems if you look at things like VLIW for example it's used in real systems today in many systems actually even though VLIW folks also went through a huge naysayer。

 let's say push is Josh Fisher for example or Bob Bro when they were design the VLIW Pro。

 they said this people said this will never work。😊。

Maybe under some conditions in network work that's true。

 but they figured out at least not necessarily them actually they went through it the hard way because they were trying to do this as a general purpose paradigm and general purpose programs it's very difficult to make it work for the reasons that we discussed in the VIW lecture but over time people figured out how to make this idea work or in under what conditions to employ this idea so VLIW is employed and a lot of processors today including early GPUs embedded proceduress and actually TU as we have discussed very briefly。

😊，So basically a lot of these ideas enabled many big things， automotive execution for example。

 I don't tell you about GPs and systoic arrays clearly these are things that have enabled the machine learning。

 let's say the second machine learning summer that's going on we'll see if we get into another winter in machine learning which we might with this hype because if something is overhyped you can easily get into some winter it's good to be at the more let's say balanced point to understand upsides and downsides but this hardware is really enabled machine learning for example but then enabled many other things also like flash memory enabled this thing in my opinion because what do you do with this thing other than taking videos。

😊，They have to be stored somewhere。Okay， I'm joking of course right you can do a lot of other items and that has also been enabled by what we've discussed the takeaway second takeaway is principles we covered actually apply broadly。

 a lot of them are can be applied to real life as we've discussed in many conditions locality for example heterogeneity or even prefeting right there are many principles that can apply broadly but they also apply in systems so we discussed prefetching within the context of a processor but prefetching is done in systems quite often。

 if you have a distributed system for example you prefetch from one location to another location。😊。

This operating systems， for example， they learned actually when I was at Microsoft in 2006 or so。

 people were developing machine learning based mechanisms to decide what should be prefeched into main memory before the user requested。

And the idea was to identify the user usage patterns in the operating system to figure out which applications are launched when under what conditions and predict that an application is going to be launched and bring that from the disk to main memory。

😡，And they actually employed this in， I don't know if it's still employed。 I don't use Windows also。

 but this sort of mechanisms can be employed in many different systems， as you can see。

 that's a form of prefeting。 That's a form of machine learning based prefeing。 Also。

 they didn't necessarily use reinforcement learning， but they had some mechanisms。

 So a lot of the principles are applied broadly。 If you go to a networking course， for example。

 A of the principles are applied broadly。 It's good to think about that。😊。

And the third takeaway is probably the most important one that I already said。

 which is trade off analysis and critical thinking that hopefully you are exposed in this course that what my goal is apply even more broadly。

😊，Maybe you don't figure out how prevering applies to the real life。

 I do think it applies but hopefully tradeoff analysis， critical thinking。

 you go to the industry or you your own company or you do consulting somewhere even if you don't go into research。

 these are really really important skills right you have to critically think to analyze that problem and that problem you can actually innovate and solve it in a very different way by applying this tradeoff analysis。

😊，Okay， so just to again， remind you we're done with all this， I've actually shown this slide before。

😊，In earlier lectures when we were done with these。

 but we're done with a lot of micro architect chair pipelineing out of order superscale execution。

 we're done with execution paradigms so you know a lot of these interesting paradigms and you may figure out where to apply these you're familiar with many processinging paradigms and there are tradeoffs associated with all of these processinging paradigms and you can probably decide which one to apply under what conditions or which combination to apply。

😊，It's good to think about that。 We've done also now this slide you didn't see before because this is when we are actually done with memory。

 we've actually covered a lot on memory also you can never come cover enough in memory memory is endless let's say because there's a lot more to cover。

 but we covered at least the basics and fundamentals and also quite cutting edge things and you're very familiar with the memory systems。

😊，And hopefully you can make tradeoffs of many different memory system design ideas because this is the bottleneck basically in today's systems right memory system。

 everything else is very very interesting and you have to make it work and you have to have it there and you have to be cutting edge over there。

 but this is the bottleneck in the end， there's a lot more we can learn in this area actually。😊，呃。

And also you're going to see more memory in your future courses， like if you take system programming。

 for example， you'll see a lot of virtual memory over there from a more software perspective。

When we discussed virtual memory， we said that it's the most successful hardware software cooperation idea that has been around since 1950s。

 It is true actually， it's the most successful hardware software cooperation idea except it has not been rethought as much So you will see this in systems programming from a software perspective I think virtual memory is a mess It's a very interesting idea very。

😊，Good for the time it's developed， but we haven't evolved it enough。

 so we really need a lot our research to make it work better today。Okay。

 so basically it's good to think about how do trade offs span and affect the hierarchy。

 so because we've seen this hierarchy many times it's kind of one of my favorite pictures as you can guess。

 it's good to take a expanded view of computer architecture。😊。

So this is also what I hopefully promised at the time hope take this at a learning experience don't think about the exam we may talk about that later well you'll need to take the exam yes。

 but long term trade off analysis and critical thinking and decision is make these are things you cannot learn with an exam in my opinion you can never learn。

😊，These things are an exam unless exam is geared towards completely thinking。

 which is not the case in many systems in general， okay。Okay， I think I kind of said this before。

 but yeah what we saw changed the world and endure the test of time actually a lot of ideas if you if you go through a lot of lectures。

 you'll see actually at least 50 ideas in all of these lectures。Which is fascinating。

 and it will be more important。 You may not all be future architects in the end。But hopefully。

 your development and thinking can greatly benefit from what we have covered， concepts， trade offs。

 principles and critical thinking。 There are facts we covered。 but there's a higher level of。

 let's say。😊，Thinking that is associated with the facts， right， which is a trade off analysis。

 principles， critical thinking and the concepts。😊，Okay， I think we've discussed this also。

 I think my goal with this course was to activate these agents。

 let's say understanding learning and critical analysis because I think these are lifelong things fact you can forget that you can readlearn。

😊，Hopefully I made my point， but if I haven't made my point。

 somebody else made the same point and I like this。

The value of college education is not the learning of many facts。

 but the training of the mind to think。Does anybody know who made this point？Nobody。

And there's no channel here that tells the person's name， unless you go and click that。

 if if some of you is fast enough， well， I guess today you can do it you easily take a picture and you directly go there and then you can figure out what this is perhaps right。

😊，But this is the person who made this point。He also like philosopphes a lot about like how to。

Like in education etc ce， but basically I'll read this sector because I think it's important it's not so very important for a person to learn facts for that he does not really need a college。

 he can learn them from books and I completely agree with this today not books right today you have a lot more YouTube right people can learn facts and also this course online the value of an education a liberal large college I would actually scratch the liberal arts part is not it doesn't have to be liberal arts in my opinion but there's a context in which he said this it was giving somewhere yeah it not the learning of many facts but the training of the mind to think something that cannot be learned from textbooks so it's good to think about that right。

😊，It's good to pause and thank you like for every class that you take。

 what are the things that you could have learned from the textbook completely and what are the things that you couldn't have learned from the textbook？

I thought about it when I was a student like you。Okay。

 I'm going to give you a couple of quotes also because we don't have time and we probably were going to end with these quotes actually。

 well there's still seven minutes。😊，Okay， I'll give you one more quote because I like these actually because these these are actually quotes that challenge and they also show that you've got to be a little bit pushing the boundaries right。

 because if no one's pushing the boundaries， then you're always stagnated。😊，Now we read this on。

 the reasonable man adapts and man is basically in general， it's a mature person。

The reasonable person adapts himself to the world， the unreasonable one persists in trying trying to。

 there's a two missing over here， they're trying to adapt the world to himself。

 therefore all progress depends on the unreasonable man。I was are the ones who push the boundaries。

 right， to a question。But those are the ones who have a hard time because they question right if you look at like philosophy of science。

 there's this book， I think I mentioned this in one of the lectures earlier like first lecture。

 Thomas Coon， the structure of scientific revolutions， Anytime somebody questioned the status quo。

 they got into trouble。😊，God in Lo， for example， right？One example， right？

Who turns around to It's good to think about it that way right for this debate， He lost his life。

 let's say it's not good， right， there the questioning actually leads to some unforeseen consequences potentially。

 but it's an important thing to do that's how things become better right because of him actually we're in a better state right now in my opinion then some yoyo who said that oh okay。

😊，You should not question this。A dogma， right？Okay， this person is George Bernardchll。

 do you know George Bnonchaw？Okay， it's a very famous Irish。Person who won the Nobel literature Pri。

And he actually has beautiful place。Playwrights， I should say， but also a person。

there also people right， well， that's not true actually anymore。with chat GT。

 I think you can have playwrights， will they win the literature prize？

Maybe ifve chat GT values chat GT， yes。Okay， so this is another thing that this person said progress is impossible without change and those who cannot change their minds cannot change anything and it's good to actually question all of these things right Okay I'll give you one more oh I should have played the game but I forgot to animate。

😊，I'm not going to read this， I'll let you read it， but it's also a let's say critical thinker。

 let's say it's good to think about this critical thinker。😊，呃。Have you read it。I like this one。

 Nothing is at last sacred， but the integrity of your own mind。 There is nothing sacred。

Only thing that's sacred is integrity of your own mind。

ButYou got to believe in it and you got to do the right thing to actually have that happen， right？

Everything can be questioned， basically， saying as long as you have integrity in your own mind。啊。

I like this， I don't know， maybe you don't like it， but it's maybe it makes you uncomfortable。

 but it's good， I think uncomfortable is good。That's why it's he saying with the first sentence。

 right， be an unconformist。Okay。Okay， what did we did not cover。

 we were going to cover what we did not cover in the last three minutes。😡，An overview。

 so computer architecture is very rich basically there's a whole lot over here。Okay， many ideas。

 much creativity， many trade offs and problems。As things become worse in many dimensions。

 both at the lower levels and higher levels， you basically need to think about the middle levels more computer architecture more。

 it will become more important essentially， and this is clearly already very obvious。

In machine learning systems right and also hardware security like Ro hammer。

 et cetera we've discussed， but there's also a broader hardware security novel like execution paradigms which we do not cover processinging in memory。

 so I have this lecture intelligenttel architecture for intelligenttel machines。

 but you can find many other lectures also。😊，So that's why we work on enabling fundamentally better computers。

 there are a lot of topics that we do not cover like energy efficiency。

 there's a lot of aspects with memorycentric architectures。

 there's a lot more in security reliability， safety， how do you get low latency architectures。

 how do you make an architecture predictable right predictability is important。😊。

How do you design architectures to be more intelligent and evolving by humans， maybe， right？

 We've seen an example of this glimpse of this today with the Pthia。

 like machine learning assisted architectures。And then how do you design architectures for different applications and make make them adopted。

 So this all requires actually some of the things that you've learned in this course and across the stack。

 I already said a lot of this over here and。😊，Maybe I will end with these basically in the end where we have a huge data problem today and computer architecture are not handling data well。

 data is really overwhelming our components。呃。We've seen this with the memory lectures right I'm not going to repeat all of that。

 So we need to solve this problem basically So for that， we need more intelligent algorithms。

 intelligent architecture， intelligent system designs all the way from algorithms to devices。

 This is actually the processing in memory part， more data centric execution。

Do the processing inside the memory cells， for example， do it in digital logic or analog logic。

 We didn't talk a lot about analog over here， but analog computation is very interesting because it's very energy efficient。

 Don't move the data。 Just do the processing where the data is。😡。

Another thing you can do is taking advantage of vast amounts of data and metadata because there's a lot of data that's flowing through the system and we're not using that as much as I said earlier。

 people are designing systems with a lot of heuristics。

 but if you actually design a reinforcement learning based prefecure or memory controller。

 it's much better， it's much more data driven basically。And also。

 I will not talk about this much because we don't have time。

 but our systems ought exploit different properties of data。 For example。

 data is a lot of characteristics， proxiability， air tolerance， compressibility。

 all this information doesn't get come from the higher levels to the architecture。

 You've seen a lot of architectures。 none of them say。This data， I can reduce the width of it。

 and I will still be okay， right？😡，Or this data is really secure and critical and I should really treat it separately from everything else if we have this information if we communicate to the underlying hardware we can do much better so I will end with this slide basically we can do much better essentially by designing data centric data driven and dataware architectures and if you're interested in that we have papers on that too but。

😊，I hope you enjoyed the course。 It's not ended yet。

But the lectures have ended now is the time to actually probably prepare for the exam for some of you。

 some of you maybe it' will acete the exam without preparing。😊。

or fail I don't know but I would still recommend preparing for preparation what we're going to do is we're going release some sessions we're gonna to have some inperson sessions also sometime in July or I don't know when the exam is when the exam mid Augustt okay sometimes in July or August and also there will be some sessions that we will release online that you can go through certainly doing the homeworks will help homeworks are actually based off on a lot of the lectures because for example。

 if you know how a GPU works you can actually solve some of those problems and we may modify the questions clearly so that it tests your understanding right so it's good to solve the optional homeworks and certainly also past exams those are good preparation for the exam also in these sessions we're going to go over some past exams as well as optional homeworks So those are very good ways of preparing the exam in addition to going through some of the lecture material that may appear in the exam who knows？

😊，Okay。Any questions， burning？All right， I will see you maybe in some other course in the future than or earlier in the exam。

Take care， have a good summer break。Although you won't get a really nice break because you always have the exam in the back of your mind。

 I wish the exam was also earlier rather than later， but maybe some of you don't miss that。

 I don't know， I always like having an exam ending the like not as a professor。

 but also as a student， I would prefer my exam to be done as opposed to me worrying about an exam two and a half months later。

But that's how it is， you cannot change that， you can control what you can control at this point。

Okay， have a nice summer break and I'll see you at the exam， August 15th。Take care。



![](img/42ca74b47661a64c9efa6c5c7d898f49_13.png)