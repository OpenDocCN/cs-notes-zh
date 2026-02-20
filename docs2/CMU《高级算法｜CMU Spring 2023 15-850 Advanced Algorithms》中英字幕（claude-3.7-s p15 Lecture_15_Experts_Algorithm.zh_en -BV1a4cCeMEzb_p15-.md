# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p15 Lecture_15_Experts_Algorithm.zh_en -BV1a4cCeMEzb_p15-

So， today。啊。We'll be studying the so called expert algorithm。

And this is the starting of this area called online learning。Even though our focus is not on online。

Problems yet， it's not on learning problems yet， but still this the general idea behind this， this。

This problem and the algorithm is very powerful 1。 So I wanted to tell you about this。

 So we'll talk about the so called。Weed majority algorithm。

And the weighted majority algorithm has a closed cousin， which is called hedge。

And we'll talk about both these things。 And then we'll talk about。What you document。Bandit。Problems。

So I'll define the various problems and stuff like that and you'll see hopefully you'll see how these things come together。

😊，So the the main setting is the following。 So it's called the expert problem。

And in in the exports problem， there are n experts。

And experts just means there are end people who have opinions。

 they don't have to be experts in any quantifiable sense of the word。 They just have opinions。

And what you what happens is the process on every day。You know， add the B。The following happens。要 c。

Predictions from the exp。From Egypt。The experts make a prediction think of this as market going up or down。

 the weather is going to be rainy or sunny， whatever。😊，对。啊。Now， you make。A decision。

Which is based on these predictions。And let me just， O。And then you see the actual。奥特。

So there's some event that youre trying to predict。

You see what these experts predicted you make your own prediction。

 which Ill call a decision just to not confuse it with these predictions and then you see the actual outcome。

😊，And then a mistake。Just means。That decision。At time T that your decision is not equal to。你 out感。嗯。

That's what it。So it's the event that what you decided is not the actual。

So you decided it's not going to rain， it rains， you made a mistake。

You want to minimize your goal naturally is to minimize the number of mistakes you make。

And this is the process。So this happens every day。You want to minimize the total number of mistakes you make。

So。I know that some of you have probably seen this before， but feel free to chime in or。呃。

You know think about this afresh as though you were seeing it for the first time and for those of you who are seeing it for the first time。

 this is awesome。😊，对。The setting clear。在 didn。So the way I always like to think about this is。

Let me just introduce some notation on every day you're going to see some predictions。

 and I'll just stick with the notation in the course notes， even though they aren't the best ever。

The一 of第。Is。An element of some universe to the end。

So there's some universe of possible predictions that can be made。 And this is just a vector。

 It just says what predictions did expert 1，2，3 up to n make， You make a decision。😊。

I don't even know whether I have some notation for this thing。ok。啊。You take some action。Let's。

 let's let me just stick with decision。啊。I'll call this A sub D。Which belongs to you。

You observe the outcome， which is o sub T。Which also belongs to you。

 And this just says iss the indicator of whether 80 is not equal。It， I don't know why。Right，嗯，跟。

So the the first question to ask is。I know， suppose that exists perfect text。question心。

If they again a perfect expert， can you give me an algorithm that'll make few mistakes。

Had everybody seen this problem before。And some of you have。嗯，yes no。O对。对。

So what's the algorithm that there is an expert who never makes a mistakes。

What should they do or what should the algorithm do。对。Good， so so here's here's attempt one。

 you know， pick expert one， keep following them until they make a mistake。

 As soon as they make a mistake， you know that they can't be the perfect expert。 you throw them away。

 go go on to expert 2 and so on so forth。 So you have your entire roster of experts 1，2，3。😊。

Up to capital n， you are following export one until they make a mistake。 you。

 you scratch them off in a。 youre like， and I've been leg down。My Godd a feet of clay， et cetera。

 et cetera。 We go to export2 and for。😊，喂。So you follow an expert until they make a mistake。嗯。

And in the worst case， export N is the expert who is the perfect expert youll make at most10-1 prediction at most n0-1 mistakes。

😊，Okay。Geting do better。Yeah。啊应该。嗯，哼。😊，O。But of course， if I， if you decide to follow this algorithm。

 I could make you make n minus minus mistake。😊，Because， you know。

 the first day you picked export one， whatever they predicted。You， predicted that。 And I would say。

 I'm sorry， that's not the one。Everybody else was correct。So I could make you make N -1 mistakes。

 You followed this algorithm。 So you should change the algorithm。我知不道。给完了吗。You randomize。 So you。

 let's say， pick a random expert。And。对啊。But every time we take。Good。个人。So啊。

How many mistakes will that make in expectation。So every time his proposal is every time you pick a random expert。

😊，And you follow them。 If they make a mistake， you stress them out。How many mistakes will。再讲呢LL make。

没什么。I'm sorry。他们一些。Harmononic series， why。Why。So the proposal is this algorithm makes log and mistake。

Is that correct。Actually， I don't know the answer to that。So let me。

 let me postpone that for a second。 And somebody give me a deterministic algorithm that makes approximately log many mistakes。

 Yeah John。Big the majority。Pick the majority opinion。the majority opinion is wrong。

You are throwing away at least half the expert。 Okay， so good question。 So now the question is。

 what is the size of the decision， You know， how many how many outcomes can there be。Yeah。So。

It makes sense to pick the majority。 So suppose Ill say， suppose。The set of possible outcomes。表。

the set of possible outcomes has has larger size， then you know， we'll have to worry about that。

 But let's say that the set of outcomes is of size two。

 Then now what I can say is I'll pick the majority opinion。😊，If the majority opinion is wrong。

 then I'm throwing away， at least。A one over U fraction of the AC。Yeah。And in particular， if you is2。

 then I'm throwing away half the X。If I look at all the people who said market's going up or down。😊。

I followed the majority。 my majority was wrong。I throw it half the expert。对。All these can be handled。

 but let's get you back。So right now we are still in the perfect expert。So in this case。

 what's happening is every time an expert makes a mistake。嗯。Every time each expert， each mistake。Hos。

Or better， the remaining experts。Therefore， the number of mistakes。I that most。L these two often。

Every time I make a mistake， I throw an expert。It's probably half yes。Fairness。Is this best possible。

Can you do better。What are we really doing。Basically， lets imagine that there is a single expert。😊。

That' that's correct。Essentially， you know， if you， I'll give you 50，50。

I'll say half the experts will say up， half the experts will say down。😊，Whichever choice you make。

 I'll say you're wrong。I'll throw away that half of the experts。And then I repeat， right。

 So I will make you pay log based to a。 It's really binary research。This is bad。对。And you， clearly。

 the lecture can't be over。 So suppose now I ask you the second question。Suppose。Best expert。Next。

Capital and。So given that you have this algorithm。Can you suggestion algorithm。For。

 for the setting with。There is an expert that makes M mistakes。 sayy M equals  one。

There is an expert that makes one mistake。I'm sorry。I could clone the experts in what way。I'm sorry。

Oh， I see。Okay， so， so so crossing out their hearts means they have one less life。So， good。Good。

So one way of viewing this is， you know， let's run this algorithm。 you every time I make a mistake。

 I throw away half the experts。 What can go wrong？Working girl。not a trick question， you said。

I'm sorry the right。What's the right expert？The best expert。 I don't even know the best expert。

 I'm just running this algorithm。 Who knows what's what's happening。 You know， so far， as long as。

 you know， Im every time I'm making a mistake， I'm having the number of experts。😊。

Who cares if I throw away the best？I'm not making given any mistakes。

 I'm making only log based to offend mistakes。😊，It just follows the algorithm。 What can go wrong。

Yeah。can see if it's a bad exploit。今天。no， no， no。 So So I'm just running this out of them for the moment。

So so I had n experts after a mistake and over 2 and over4 and over eight。😊，不放收。哦。啊哼。😊，そですよ。

Fair enough。 So what might happen is I might have a single expert in my hand or all the experts in my hand just made a mistake。

😊，I want to throw them all away。 I have very experts in my head。So this algorithm。

 as long as I have an expert in my hand， I haven't made more than log mistakes。😊，What am I doing。

 I started with an experts every time I make a mistake， I halfal the number of experts。

So the number of mistakes I can make is that most log n。Until I throw away all the eggs。

Now we're doing。其实都快闭咗噶啦。You get a divide by 0 error。

 so that's a problem and I don't even know what to predict next。😊，So let me bring everybody back。

And that's like giving hearts to everybody。giving lives to everybody。Player 0。

 you have seven lives left。诶これ。But the good thing about this algorithm is I don't need to know anything。

 you know， I just。I start off with experts。 I have each time I make a mistake。

 I end up with their experts， and I say， oh I made a mistake， sorry guys， I screwed up。

 I don't have any experts。 Everybody come back。😊，How many mistakes been dishared on make？

Ill make at most and I'm being very pedantic out here I'm not going to be you know such so pedantic for the rest of the lecture at most m plus one。

😊，Longiness， do off。And。啊上去。M times log base2 of and。嗯，没笔。Let let me just say this。

And maybe technically， I should have it。I'll make so many mistakes before I throw away the last expert。

Then I bring them back in， I'll do the same。And then in the last round。

 I might not have made the last mistake。But here， not important to all the plus ones am in。

Whoever said that was pretty much correct。嗯。And this algorithm。 So， so this is。

 let me just write this as M。Loob， and。And it's locked based to。Now the question is， well。

 for M equals。0。This algorithm is about correct because really， it's a one plus M here。And clearly。

 you need to make any mistakes。Because the best expert makes some mistakes。 Oh， by the way。

 notice that this algorithm need not need to know who the best expert was。How many， you know。

In in hindsight， who's the current best expert and stuff like that。 Who cares。

This algorithm is doing its own thing and making mistakes。So now the question is， can you do better？

And that's really the rest of the lecture， can you do better？Fair enough。Yeah。第思。嗯。

Both asympotics and constants。We care about everything。再次。Next， okay。Next attempt， right。啊。

you remain all that that's actually good。你没问。Okay。所以呢。给你说。We're not using the fact that like it。

And experts eliminate themselves by this。对。你定开时。Good， good。

 so one thing that's happening is as soon as I throw an expert。😊。

I'm not counting whether they're making mistakes， you know， when they're off stage。

And then bless you。 And when I bring them back， I forget how many mistakes they made before。

So Im not looking at the running history of how many mistakes people are making。

I'm just being very milded。Yeah， one mistake youre out。And thenoo， I throw away everybody。

 Everybody come back， you know， welcome back to the fourth。Self， we are toorup。

And that's that's the main idea。 And so let me tell you the the algorithm this is known as what is this known as。

This is known as， okay， so now that I've written M， I'll call this。Multicls。Waits。Thats MW。

 or I can write weighted majority。😊，那是谁买我。The algorithm is the following。嗯。When。O。Start。喂。😔，嗯。

Each expert。看。ね。WI。Eals one。诶等。嗯。You know， from this point onwards。

 I'm only looking at binary decisions at time T pick。嗯。Pick outcome， outcome。 No， take decision。

Which is the weighted majority。There's some weight on experts who are predicting zero。

 there are some who are predicting one。😊，You look at which one at higher weight， pick that。And then。

呃， after。Observing。The outcome。The weight of the expert。

And maybe I'll say the weight out here is weight。忘了。And the weight。Is updated as。那。

The current weight。Ds one， half。嗯。Yeah， just right。嗯。Dmes 1。F o。Equals。Whatever， if export direct。

In this round。And one half。So if the exploit made a mistake， half made。

That's a long way of writing online。Everybody' got weights。At each point in time。

 look at the experts who predict  zero， look at their total weight。

 look at all the experts who predict one， look at their total weight， whoever is higher weight。

 go with that。😊，And whenever an expert makes a mistake， just happen。全プ。Algorithm， correct。

 algorithm clear。😊，And correct means connected and I have the behold。你可车。嗯。The first of。嗯。

Claim I'm going to write in this weird little alcove out there。How many mistakes is this expert。

 How many mistakes are we making。Actually， are there questions I should first。Ask。

Every time an expert makes a mistake half their weight。

 listen to the weight to majorityiate every time。So far， so good。快醒。

In the question of people are born。You can't be bored。 This is like the most amazing thing have。

Actually， you don't know what the theorem is。 Let me write down the theorem。 And then I will。Okay。

 claim the number of mistakes we make。嗯。Of the。Areect most guesses。Im sorry。老。

So you won't be able to do better than M because the best expert makes M。😊。

So you cant do logM for sure。Because， you know， if every expert makes 52 mistakes。

 you can't do better than 5。So you would hope。To get n plus log n， this is the best you can do。

This algorithm will do slightly poor。We give you 2。4 times this with number 2。

4 is irrelevant it just comes out of the calculation。没。You'll see why。这算。看。Questions。嗯。Your。啊，哈。

So in the universe side is not being a tool that log of n。

 at least naively will become log base U of n。😊，But we could do better than that。 I think you could。

 you could start playing around with。You could take every expert and you could break them into little mini experts。

😊，You could say， oh， this expert predicting that choice is one sub expert。

 best expert predicting that choice is another sub expert and so on so forth。😊。

I think you can do better than log base U of F。But let me， let me pause on that maybe， you know。

 you can think about it we are doing the analysis。So you see what I was saying。

 I was just saying for every expert in every outcome， you could think of that as an expert。😊，嗯。啊。

But let's just look at， let's stick with binary outcomes。And this is the claim I want to make。

And in fact， the proof that I'm going to give is。Again， approved you should。Memorize。

 not really memorized。 You should know why this is how this works。

This is the proof I I've used at least 10 times in my life，10 times in research papers in my life。

It's like， oh， I'm stuck in a corner。 Oh， maybe the expert gave me。Actually。

 not experts just multiplicative way， just society。😊，这是人民休院。Instead of waxing little。

 let me show you the proof。And the proof is we are a potential function。

So what I'm going to track is I'm going to track the potential。What's the potential at time T？

Is the sun。Of weights。Of the exports at time。I equals12 x。The total weight in the system。

So what's the initial potential？It's just end， right？그种。不的。Great。Let's make two observations。

 so this was observation one。Ob the one， I can even告。Observation do。How does the potential change？

How does phi of T plus one relate to p of T。没好。没。对。Suppose。Okay。

 so look at the the potential at time T plus one。This is。

I want to say this is at most the previous potential if。😊，Algal does not。Make。般 mistake。

I didn't make a mistake。 The potential can only go down。 It doesn't really matter。Like at every step。

 the potential can only go down。If I did make a mistake。If I go mix。意識。In this case。

At least half the experts， half the weight is on experts remaining。

And that half will go down by half。So， three quarters。嗯。P。

And the point is every time I make a mistake， this potential drops。

So the only thing I have to do is show that the final potential cannot be too small。Wifi。

So can somebody give me。嗯。好。Lower bound on the final potential。Yeah。是。The best expert。

Made M mistakes。Their final potential is half to the。Other experts have weight。

 which is not negative。To the best。Whoever this best expert is I don't know。

 but this is one of the people， His weight is at least half the PM。😊，What塞。

Because you need to say that。后悔。I'm sorry， No， it could be the case that every other expert made like a gazillion bazillion mistakes。

 their weight is essentially0。😊，It is one expert who has made any mistakes。你再嚟咯。

Maybe it's strict inequality， but I don't care。即。Putting these things together。

I note that the final potential is half to the end。The the final potential。Is。String quarters。

To the number of my mistakes。 So let me call that Al。For。Times the initial potential。

 which was the applicant。I started with the total weight of capital land。Every time I made a mistake。

 I went down by three quarters every time I did not make a mistake。I went down， but whatever。

Everybody good。不。Now， what do you do， You take logs and do algebra。我。

So let's at least go one more step and then at some point I max out。I take log base 2。So。

 this is negative。啊，So this is呃。Log base two of one2。Times M is less than equal to。A of times。

 log this。Two of three quarters。Plus， log based tour。Lg base2 of1 half is negative  one。

This is some some garbage。 I don't really know what that garbage is。

 Does somebody have a computer open。嗯。What's log based2 or three quarters。 And just ask Wolf for。

Minus m is less than equal to。F times out。Plus， long day through again。I said I won't do algebra。

 but I hear I am doing algebra is at most。M plus log base2 and divided by c。

It'll turn out C is like one over 2。4 or so。你这每个。哦，这个那个就。他面卖给。It's going to be negativeOkay。

 in any case， this is 2。41。Times n plus log history。Not important what the constants are。

Will improve the constant anymore。But I just wanted to give the entire proof。Because， you know。

 as I said， this is the proof you should just， it should come， you know。

 you'll be able to rediveve it next time you need it， just redive it。 There's nothing happening。

No rocket science。Actually， the rocket science is all in here， you know。

 every time an expert made a mistake you have that way。😊，Just this simple idea。没 good。

Everybody happy。I like betters， its like you think that the other ones are like not really really bad like the the upper the lower seems very。

 very。Absolutely， so so actually in this case， the right so if you make assumptions you can you can do all kinds of good stuff but。

😊，You know， you can come up with examples where essentially， you know， this is， yeah， okay。

How should we improve this？还可能。Pranandize， which actually， you know before that。

 what are the various options we took。😊，Average case all that is you know in this model。

 in this model， no randomization， deterministic。😊，嗯。Determine a mistake。呃，对。

You can try changing the half weight。 Yeah， so you can try changing the half weight。

 Why are we being so。Brutal as well。 You know， earlier， we were saying， oh， if you。

 if you make a mistake， I will multiply or weight by 0。Now I'm saying half， why half。

 completely our choice， right？I could say， oh， if you make a mistake。

 I'm going to multiply or weight by1 minus x。T。对道。You can change。 So if you multiply by。

1 minus epsilon。嗯。Up to constants， I'm cheating a little bit。You'll get something like one plus no。

 two times one plus epsilon times m。Plus。好到。Love and。我我的不行。

You start trading off the two pieces against each other。 I mean。

 the proof is essentially changing in one place。 This will become one minus epsilon to the M。

This will become。嗯。嗯。嗯。Yeah。1 minus epsilon over 2。To the a， et cetera。 You know， there's some。

 some little proof that will change。 It's an exercise。You work at it， you get the。哎。Whatever。

 take my word for it。It's then the lecture months。Question。If啲。Optimal number of mistakes is like。

50%。This is only guaranteeing 100% mistake。The best expert makes mistakes half the time I'm making a mistake every single day。

Not so great。If if capital M is like 10%， I'm making 20% mistakes， pretty good。Question。Okay。啊。

Can we， with a deterministic algorithm。Can we beat the factor of two。

I should move away so that you can actually stay ready it。Suppose I was a deterministic algorithm。

Can you show。That if the best expert， can you you can you give me an instance where the best expert makes M mistakes。

 but I would make two M mistakes for sure。不是。Good， so in this。In this case。

 the deterministic algorithm is making M mistakes。😊，Yeah oh sorry。

 So the best expert in making M mistakes， I'm making two M mistakes plus change。到了。No。

 hear're saying it can。Yeah， okay， you know， so I want to claim no deterministic algorithm can be can show me this kind of bound with 1。

9 instead of two。嗯。行。My claim is no deterministic algorithmal can be a factor of two。In the second。

杜问。Okay， so so here here the。2 times M M the number of mistakes made by the best states。Yeah。就不是好。

Yeah， forget the log。他过的。冇。A algorithm is giving us， you know， something M plus login， whatever。

 So I'm saying， you know， give me instances where。Just let's say the。So， so here is， here is the。

Here's the situation。There's two experts。One of them says。Yes， every time。And the other one said， no。

 everything time。ok。They're really boring experts， but they're experts， as I said， you。

Experts don't need to be right or anything。Your algorithm makes a prediction。I see you wrong。嗯。

Whatever prediction you make I say outcome was exactly the opposite of whatever you。😊。

Here I am using the fact that your algorithm is deterministic。😊。

So I can figure out what outcome to give to make your algorithm be wrong。Yeah。You have an algorithm。

 it is a deterministic algorithm at every step it makes a prediction I say oh actually the outcome was the opposite of that。

😊，How many mistakes did you make after T time steps？听。You are wrong every single time。嗯。

At each point in time。One of the experts was correct。放这一个出租房。

So the best expert made only T over two mistakes。You can make it like the first expert only week。0。

 and then the second expert hold。That's exactly what I said。 That is exactly what I said。

 The first expert always says， yes， the second expert always says no。😊，There are only two outcomes。

One of these experts must be correct at least half the time。Well， you are incorrect。

Every single one of the time。You made twice as many mistakes， at least as the best takes。

No deterministic algorithm can give me a factor better than two。嗯。What do you think。

So we should dry the glass。The idea that you guys have all been chaing at the better or randomization。

 lets get to that， but there is a good reason why we should randomize。😊。

The deterministic algorithms are inherently limited。对。

So let's take a twonet break and then we come back and we randomize。好。前面 have been on。不会。Okay。Yeah。

Thank。ok 好。这。Oh， nice。Good。Good， I'm happy with that， we're making。

They're making ICPC practice easier。Okay， I'm going to leave this suck， I don't know why。Okay。

 well actually。哦这里。I just wanted to ask about this potential argument。Why do we call it a potential。

 What does it have in common with？Okay。Can you say a few words sort of characterize okay， so， so， so。

 so what's a potential argument， that's a very good point。 So in general， what's that。Its oh。

 I like that。 Now， that's the other kind of potential。 It has a lot of potential to it。😊。

So in general， a potential argument is a very sort of loose concept。😊，But。

So here is one formalization of a potential algorithm that you have a you have a function。

 a potential function， which is a map from。The stakes of your system to some real value。嗯。

And in an ideal situation， you show an argument something like this。

So you say that at every point at each。ステプ？D。Your algorithm。Suffers a certain cost at time。嗯。

What you can do if you can fail this cost at time T plus the change potential at time T。

And the change in potential is just Pt plus 1 minus。Is less than equal to。There let's。してね。Then。

You can sum this over all times。And the whole thing， you know， telescopes。

So you can say that the sum of the costs。This is the total cost of your algorithm。Plus fee。快轮。Minus3。

应该系。有在生日。On。Okay。The total cost plus the final potential is at most the initial potential。Now。

A good potential， I mean it a good is again very subjective thing。 a good potential， lets say。

 would be perhaps one where the potential is always non negative。😊。

So then you could say even after dropping this， my total cost is at most the initial potential。

And now， if you could bound what the initial potential was。You can。

you have a bound on your total cost。And very often you guys have seen this in your undergrad algorithm course。

 maybe at some point， I think of this as like a bank bank account。😊，At every point in time。😊。

Whatever my cost of my algorithm was， I can withdraw enough from the bank account to make sure that I don't pay more than。

What a withdraw。啊。And so what I， you know， my total cost must be at most my starting back。好。

Now this one and you can take this argument and you can change it around。

 suppose I could show that this is at most some quantity a， lets say at every time。😊。

Then this whole thing becomes plus a times 1。And often this is called the amortized cost。家。And here。

By just taking log of the fee。 So you know， this is。

 this is one formalization of what a potential Hill。 If you take log of this fee。

Then you will be able to see that this log of this fee often you know， has has has a property。

 something like this。Because what you'll be able to show is that， let's say。

The cost of the algorithm。At time T， so cost T of the angle。

Cosity of the algorithm is the mistakes it's making，01。对。Let's say。And I'll have to figure this out。

 Long of fee。E plus1 minus。Lvo。B。O。I want to say is less than equal to 0。Why， no。

 there's some constant sitting。嗯，哎说。s look at thisす。嗯。

Cost of the algorithm is right as the normal one。Log of P T plus one。 So so let's look at。

C P plus one over C P is less than equal to one， right。This is for sure。 potential only going。

So this just means log of this。Is less than equal to P。

So this means this minus this is less equal to 0。The cost， O。If if I didn't suffer a mistake。

 then0 plus something less than equal to 0 is less than equal to0。😊，So， zero plus。

Alpha times less than equal to 0 is less than equal to 0。 O。Suppose I did suffer a mistake。

Then what did I have， I had three quarters sitting out here。Loer。Which is some negative point。Yeah。

Which I called。Let's say see。Yeah。So log of this minus this is。Al four times C。Its less than equal0。

 Just make your alpha large enough that this negative quantity kills this one。So， this is true。

And now， if you just sum up the cost over all time。

 itll come back in exactly this form where they log sitting in front of the file item。拜。

And that's exactly。So yeah。In general it it's this sort of looseui idea that you know there is some potential and it's changing often we can put it you know sort of people often use Laov functions which have a very similar idea it's again a sort of map from the state to a value and you track how this change happens。

冇得啊。Lly， this is the idea。The vet helpp。Okay， other question。Yeah。没有。啊哼。😊。

giveive some other examples。 maybe next Friday's lecture， Ill give you more example。But。

 sort of loosely。Okay， like， for instance。Let let me let me tell you more。I promise that anymore。啊。

 other0块钱。Yeah， I'm trying to think of what would be。嗯。I wasn't prepared for that question。

 I've used it enough times， but you know， still I。So black。啊。

Can you the randomized vital majority algorithm。And the randomized weighted majority algorithmism is exactly this。

 so maybe let me motivate the randomized weighted majority algorithm。😊，More than。

So the algorithm basically says， look。Suppose。Half my experts are correct。

 half my experts say zero and half my experts say one。

The problem with the deterministic algorithm is they have to choose。If I say0。

 the adversary will say no， no， no， you should have said one。39不0。

So what I should do is I should write。At the very least， if this seems to suggest there is a 50。

50 chance of picking a0 or1。😊，I should， you know， I should randomize。And how should I randomize。

 so I'm going to write down the randomized weight in majority algorithm。

And then we can quickly analyze it and then so randomized weight to majority it。By the way。

 the weighted majority， alism， randomized weighted majority。

 all these are papers due to little stone。😊，And Walmont。嗯。Truly like groundbreaking papers。

 But it turns out that the ideas had been around in previous work of Hanan， again。😊。

Providence of these ideas is a mindfulfield， right I don't want to。

So let me tell you the random weight neuro algorithm So the algorithm says。😊。

The initial weights of all experts is fine。Ex time。第。😊，啊。Bick。Export。系。With probability。It's weight。

Over the building。Actually， you know， here's what I could do。

 I could just say how many experts said wait one。What is their total weight， say it's 60%。

And then 40% of the weight says 0。Im going to say one with 60% probability and0 with 40% probability。

But that is the same as this algorithm that I am saying at time T。

 pick an expert I with probability this much。😊，放咯。Theres suggestion。你是在在哪个？

This is what I'm going to do。And then。I w to say。The weight。At time t plus one of I。

Is rate at time P。hi。Times one。哦。Gs。1。If I。各れ。再近啲。And1 minus epsilon。Ifア？As。Let me already optimize。

 you know， instead of picking half and then optimizing it further， I'm just going to say， look。

 if you make a mistake， I'm going to have you know， reduce your weight by one mile。😊。

And I'm going to pick an expert at China， according to。对。Yeah。

 so this is the random I waited majority hours ago。

And let me write down the theorem corresponding test。RWL。Mix。啊。Let let me just write it。

Let me cut out the English and we just write the expected number of mistakes。哦RWM。Iect most。So for。

Any epsilon， let's say at most one half or something like this。 You know。

 I just need epsilon to be small just to make sure everything converges。

 The number of experts is at most。参います。Apsilon。Ds。A， the best expert。Plus。Order。long。And。不。啥。系。

So if the best expert is making， you know， 51% mistakes， you'll make 51%。嗯。

best expert is making 49% mistakes。 You are making 49 times。One plus epsilon percent。Plus。

 but there is this initial period。You know， in some sense， this is like a write off you're making。

Even if the best expert is making zero mistakes， you will make login。

Which we said was binary research， right， You can't do better than that。

So you should really think of this as a situation where the best expert is making。😊。

Mistakes at some positive rate or something like this。As M gets very large， this term will。

Kind of die out。 And you are really making that X plus change。嗯。And this is the guarantee。

And in fact， you know， I'm not going to prove this one because let me give you a slight generalization in factor。

😊，Much more convenient reworking of this。Of this statement。Which will be used。But first。

 let's just stand at this angle。This algorithm starts off with weights。just for a moment。

 ignore that there are two portions of this algorithm。There is。This step。

Where I'm making a prediction at every time step。And there is this weight update portion。

Notice that the weight update is independent of the predictions。The predictions are happening。

The weight updates are happening， these are important because this this will determine how much I am paying。

This is important because my weights have to change。But notice。That the。Predictions that I'm making。

Are independent of the weight updates？Yeah。They're independent in the sense that even if I hide this thing。

 the weight updates are going to behave exactly the same。ok。嗯。A little piece of notation。This。Wait。

Of the IF expert divided by the total weight。I'll just call。B ID。么で。

It's the probability of picking export diet。哎， by the way。This is equal to WT。

It's the weight of the expert at this time。Divided by what do you know about the。Thenominator。Yeah。

 it's the potential。Just just know I'm making little observations。What's the expected loss？开单地。Is。

The sum。Over。All experts I。哦 b i d。Dys。Well。I could write this as loss。Of the expert at time。

The loss of the export is one if they made a mistake in zero if they did not make a mistake。

I'm just reworking this。你看。I going to start rewriting this as an inner product between a vector。

P sub T， it's a vector。Diaams。A loss vector that time。

The loss lecture just has ones which experts made mistakes， zero， zero。Okay。So。

 the expected number of mistakes of the random weight majority is the sum over all times t。

Of TD times the lost。Is that most。1 plus epsilon times the number of mistakes made by the best text。

Okay， what is the best expert， the best expert of min overall I？Some overall。Ts T was L T。

This is the number of mistakes made by the IF expert。

Main overall I is the number of experts mistakes made by the best expert。😊，嗯。系。

Instead of writing it this way， I could just say。😊，For all are。This guarantee holds true。

Its re working。Instead of saying the men out here， Im just saying this inequality holds for each and every expert。

😊，And hence， for the men expert。嗯。This guy， let me write it slightly differently。

Some over all times t of L T。Times。The the I basis sector。And if I want to be， you know， slightly。

 I should。嗯。I just making sure the losses are always say， I don't know why I'm being pantic about it。

208。Fish。嗯。This is just a restatement。Of what we've seen。Yeah。

This is the expected loss at time T summed overall time T this is the total expected loss。😊。

I that most one plus epsilon times the loss of the IF expert。Plus， login over。

And this is true for every。😊，So this guarantee holds with respect to every expert and has the best。

Yeah。Yeah。We are going。Why am I doing this？Because， let me。Let me raise a little bit。Let me write。不。

So heres the general game。At each time。你啊个怎。Please。A probability vector， Tt。Belonging to。

 let me define an object。Delta n， this is a probability simplex。This is the set of all。

This is I'm defining this to be the set of all excs。

I going from one to capital n such that the Xs are non negative and sum Xile。It's one。

It's just a probability something。So this is P is a probability vector。😊。

The algorithm plays a probability vector。The nature。Or the adversary。Please。Aloment。嗯。0，1。

Notice the slight difference。 iss no longer0 comma 1 to the n。vector between there and one。In fact。

Let's stand the life。Loss vector between negative1 and 1。You play a vector。 the world plays a vector。

Los。Andcur。Is equal to the inner product we think。This is just the inner product I'm just writing it in this bracket notation just because。

 you know， little dots are difficult to write on。😊，You got you play a vector。

 the world play the vector， they inner product your loss。😊，I call this is a dot product。你看。Tem。

For every epsilon， less than half for every eye。I mean， whatever。There this now them。That exists our。

For every epsilon， there exists an algorithm， I guess I should say， such that for every eye。

 the total loss。😊，That I suffer in the dot product game。Is at most one clcepson times the best loss。

Suffered in the dark product can。Plus， login over。Actually， for this mediation。

 stick with this because otherwise I need slightly more nuance。😊，So the dot order game makes sense。

Clearly， clearly， I should make sure。You see why it generalizes random migrated majority。

And this is the theorem that we are interested in。嗯。Okay。maybe we'll prove this next time。对。对。Yeah。

What should I say？啊。现在一个。你ち。没关。Exact then just。See， suppose nature says， oh。

 you know what every expert is going to suffer a lot for us。😊，In this case。

 it's hurting itself as well。😊，Because remember， I'm comparing myself to the best expert in some sense。

 if every expert is suffering a loss， it's like nobody is suffering a lot。😊，嗯。

So the real question is。The way in which the adversary can make this side be small is they should be good experts。

😊，But if they are good experts， I'm going to start finding that。And that's what this。

 this whole sort of algorithm will do。 Okay， what's the algorithm。 Let me give you the algorithm。

Everyone should never leave the class in suspense， right？

I don't know why I raised this because that algorithm was pretty much the same as the previous algorithm。

😊，I want to write down this algorithm， which I'll call。I'm sorry。Oh yeah。

 so the adversary plays this， this is the loss incurred and we see。😊。

There variant where you don't see Lt。You only see the value of this inner product。

That's called the bandage setting。I was I was too optimistic and hoping that we could do the binding setting。

 but it doesn't。But in this case， we see the entire vector。

 We see what losses we would have suffered。诶。So let me write down the multiplicative weight algorithm。

Yeah， multi which algorithm is。All weights。Start all the weights start off。 You know， basically。

 I'm going to write the same algorithm again and again this thing。 All the weights start off at one。

Always remember that T TI is equal to WTI divided by sum of WTJ。They're going from one grant。Always。

哎。😊，Back time。T， I need to give a vector PT， right？Pt is defined in this way。

And then I see the losses。You know， see loss vector。Then， define。W T plus 1 I is equal to。

1 minus epsilon times Lp。Hi。なて。Notice that if the loss is 1， I' am multiplying by 1 minus epsilon。

If the loss was0， I'm multiplying by one。And I'm just linearly interpoating between these three。

This algorithm is the same as the previous algorithm。Theres everybody who makes a mistake。

 their rate goes down to19。But now the mistakes need not be binary。 They're all one。It be somewhere。

I made a half mistake。My weight goes down by1 minus half。This algorithm is often， yeah。

 it's called multiplicative weights。😊，It has a close cousin。

And I personally like the closed cousin a little bit。The close doesn't say is WTI。

Gets W T plus 1 I gets WT I times E to the minus epsilon。哎啲。诶。なのです。Like for small values of x。

E to the x is approximately12 of x。So e the minus x is equal to1 minus。Next。This is e to the minus x。

This is one micro。So morally， they are the same。Technically， some approximations will happen。

 one will become easier。 in some cases， one will become easier than another。😊，对。This algorithm。

 this this closed cousin is called hedge。😊，Multipulative weights hedge。

I don't really make a distinction unless somebody forcess me to。At the same algorithm。

So the next time well prove。This guarantee for this one。 And then we'll go on the click。

The only actual difference between pen and multiic rates is like when the loss is not just CR。Well。

 even in this case， it's like e to the minus epsilon versus one minus epsilon。😊，第二个。是个。I'm sorry。

 just slightly so， so， you know， morally there is like whatever you can prove using this。

 you can prove using that with a little more sweat。😊，哎，喂。Yeah， sort of in that tiny range。

 naturally really。So， at least I don't know of any。Quallitative difference。It's all a minor little。

Details。嗯。The next time we'll prove this。 it's the proof you've seen， you know， it's the same proof。

 There's only one proof in the book。Im going to write down a potential and the potential is going to be the same potential。

 It is the sum of weight。😊，And I'm just going to track that。

 Im going to see how the potential will change。😊，The potential will change in predictable ways。啊。

活掉是怎样。I'm out of time， guys。 I hate to be a cliche and T you for five minutes every time。

 So this time I will just but the trend。😊，But let me stop here and see if we guys have questions。

By the way， you know， if I， if I haven't made this clear， I I think this， this。

 this sort theorem is a miracle。 It's it's like， you know， how can this be true。

 You are as good as the best expert in hindsight。😊，You know， plus。

 plus this garbage stone which we need to deal with， but log in over epsilon。

 You know can't be that bad。Yeah its， you know， and the proof is so simple， it's doubly a miracle。

 sometimes these are miraculous theorems which have gravy proofs。😊。

This proof would fit on the back of a postcard。Yeah。This being a graduate class。

 you guys do remember postcards， maybe。诶。Anyway oh so Wednesday Mother Susan will give a lecture I'm traveling。

😊，So so be nice to him。 And Friday， I'll be back and then well take it from。

 So Wednesday will be a little break。 It I think There is a lecture， but it's a different。😊。

