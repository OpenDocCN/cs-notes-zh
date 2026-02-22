# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p26 Lecture_26_Online_Algorithms.zh_en -BV1a4cCeMEzb_p26-

嗯。Maybe let's get started， guys。So welcome back。😊，We just saw two lectures on approximation algorithms。

And we will see one more lecture， at least when we talk about sum of methods。

A couple of weeks from now， but for right now let's just switch gear server so slightly and talk about this area of online algorithms。

😊，which is similar to online learning， the export algorithm that you've seen earlier in the sense that it's trying to deal with uncertainty in the data。

 but on the other hand it's a slightly different perspective on the same problem。😊。

So let me explain what I mean basically in online algorithms theres。

The dominant framework is one called competitive analysis。Compare detailed analysis。

So loosely in this， what happens is that。Every you take， you know， the algorithm。

Takes a sequence of decisions。Without knowing the future， without。Norwing in the future。

And this is in response to。Some requests or something like this in response to。Requests， let's say。嗯。

And then。We look at。Competitive ratio often an algorithmism。

So the competitive ratio of an algorithm is。If you look over all possible inputs。

 so this is a max over all possible inputs。Of the cost。Of the algorithm。On input I。

Divided by the optimals。Slution on input。So basically I'm saying。

 look at the cost it would have taken if I had known the input upfront。😊。

And look at the cost I suffered because I did not know the input up front I'm not I'm placing no restrictions on the algorithm。

 the algorithm， this is just a information theoretic object。😊。

The algorithm is allowed to take however much time it wants。

 it just doesn't know the future when it's making a request， it's making decisions。

And we'll see in a moment what this might look like。And I'm doing the worst case overall possible。

So this is not the comparative ratio of an another。

So this is just something which doesn't know the future， something which knows the future。

 so it's an apples to oranges kind of comparison。😊，And we are seeking to minimize this quantity。

In general， that's the goal， of course。The way I've written it， this is a minimization。

 so this is called minimization problems。😊，Or math innovation problems， you know。

 I might have to define it slightly differently， but let's not worry about that。😊。

So you the best way to illustrate this is perhaps to give an example。So， this is。不。

So let me give you。One example of this。有啊。So here's， here's here's an example of a problem。

 It's called。List access。The problem is the following。I have n elements。

And without loss of generality， I can call these one to up to n。

And are present in a they are lined up in a list。In some order。

The boxes and circles are the same I just got tired of growing boxes， circles are faster to go。😊，2，1。

6，3，5，4。对。I have two kinds of operations that happens。Fine。X。And。

That's actually one kind of operation index。So every time I ask you to find an element in this list。

哎。😊，The cost of this。Is the position。哦 x。In the current list。So at this point in time。

 if I ask you to find the element5， it's a position file， you'll pay file。😊，Find the element one。

 it's in position two you'll pay  to。Okay。😊，What can you do， So your algorithm。Ha to， you know。

 it has to start from the beginning， go down this list until it finds the element and then say， aha。

 good， I found it。😊，诶。You might find it convenient to reorder the list as you go along。どこれセンス。

You could do internally， so so。The the data structure only ask for one operation。

 you could make this fancier， you could have inserts deletes。Well that's all jazz。

 I'm not worried about that right right now this one operation it's fine。😊，系。Internally， you can。说。

Neighboing everyone。At a cost of one。You might say， look。Im not so。

 I don't like the fact that three and six you know in this order， I want to swap them。一 got笑 one。

Okay。😊，So you can reorder the list at a cost。So these are the two kinds of costs you might incur this is like an internal cost for your own bookkeeping。

 this is an external cost。😊，You want to minimize the total cost。

And you want to compare with an algorithm， you know， so you might want to say okay。

I want to figure out what my cost is。And of course， I want to figure out， you know。

 given any sequence of requests。😊，It might be the case that the optimal algorithm does something completely different which also does you know fines and swaps and it might incur some other cost you pay costs swap。

 but you sort of already。😊，Like you have like a global picture of what the list looks like being extra to like find additional things in the list absolutely so here is how you should think about it so that this find is not really just a fine basically I'm doing some operation on this。

😊，So I really actually need this position。😊，Now you could say， oh， maybe I have an array。

 maybe I can keep all this in an array， that's a different data structure。😊。

Different set of possiblevo。And we could model that， we could start studying that。

 but right now we are just studying this one。😊，But when after when you decide whichwas to make go the entire contents absolutely absolutely yeah。

 so let's say you know the entire content yeah， you don't have to go around and say， oh。

 where is six where is five。😊，So you should really think of this just for the moment as not worrying about you are this sort of omni omnipotent thing。

 but really you have to go down this list。😊，In this way， and it go swaps。

 you actually have to pay one。The people usually use the dependent analysis framework for like online learning like cognitiveator discrete problems and use like the regret and limitation framework for more continuous studies so I would say the distinction is slightly different I mean it often is the case it happens you know what happens that what happens is exactly what you said but really perhaps I would say。

😊，What regret minimization does is it doesn't tend to keep track of state。

The decision I took at time T and the decision I took at time T plus one could be completely different。

😊，Really what's happening is I am playing a probability vector P。I get some lost Lp。

And this is my loss of time day。PT has nothing to do with PT minus1 is that the fact that it' is similar to PT minus1 is my decision。

😊，I could change my decisions every time drastically。Here， there is a notion of state。And very often。

 that's what the difference turns out to be， it's just your。Usually oh。

 another difference is in online learning， we look at additive guarantees。😊。

Here we look at multiplicative guarantees。And in fact。

 that's going to be a common distinction between these two settings here we won't be able to get targeted。

People like so I mean it depends on which which group of people you follow right you're following the regret people of course you're seeing a lot of regret no。

 you're seeing a lot of regret research but there's a fair bit of competitive analysis going on it's just a different set of problems。

 different group of people。😊，Though I must say one thing that there are ideas which are in common to the two areas。

And so what's happening is basically continuous optimization seems to be underlying both these areas。

So more and more people are realizing， oh， these tools can be used for both these areas。😊，And yeah。

 if I have time， if we get to that， if I stop lavering。

 I can show you a result that will imply in competitive analysis that will imply a result and regret。

😊，So is there are connections out there。Other questions。Is the problem here。Okay。

 so let me just to make sure you know， it really helps me and it will help you hopefully to see a few strong ans。

😊，So here's an algorithm。呃，都牛。哎。😊，Never do swaps。Whenever a final comes。

 just go down this list and find that element。Is this algorithm， I mean。

 what is the competitive ratio of this algorithm？😊，对。我在。For energy the number of that。一是这样了。

if you just keep wearing the last element so let's say you keep quoting the last element。

And you do this tea kinds。What's the cost of？The best solution。

 also what's the cost of your algorithm？And he has。What's the cost of the best out okay。

 and the cost of that is？No， weighty。Oh， interesting work。对。Excellent， thank you。So。This goes to。

N plus T。There's an endcomp developer。Perfect。Let me do another one。Soed by。Rerequency。

You've seen some number of requests so far。Why don't we keep this list started by frequency？Yeah。

 for the previous one， why is it not just Tn over T because we're like maxim over。Oh， never mind。

 yeah， so like like how do we not know that there's an input that's even worse？

Everything takess at least one and I know that。So you can't have end unless。佢系系。对。

Are you happy with M perfect？Two related things to say about this I don't completely i'm not sure about either。

 but one is that so the true reason circuitency seems not right so one is that the current。

State of the list but let's say the intuition on that sort frequency is the elements which have been requested before are likely to be requested again you have no guarantee that that's true absolutely and similarly I think any deterministic strategy you could always just keep requesting that element at the end of the list is。

Good so actually。Here's the question。Suppose I start。

Requesting why is it not the case that I'm going to pay in every single time， right？

then you could request five， I request five。So you might say， okay， let's do the follow。

 let's start with the list one， two， three up to one。I' going to request n first。

 so this is my list initially， I'm going to request n first。😊，So you're doing sort by frequency。

Now you'll bring end to the beginning。And then you'll request n minus1 next。

So I're going to have more n and minus ones here。You request N minus1 next。

 I'm going to move n minus1 maybe to the you know， something like the front that list。

I'm going to the N minus2 next then on。My algorithm is paying n every single time。

The malance cost is clear。And the question I have for you is so the request sequence that Noah suggesting is n and minus one to one kind of repeating。

😊，That seems like a possible。Request sequence to be worried about， right？或 for this案个。没有。嗯。

're ordered in reverse order。哦，有这个就是。い系。So is this the request frequency of one animal？😊。

Or is this Earth square frequency or whatever？Maybe it's not that bad。 Okay， so why not。

 Why don't you have to be very wrong told。Well， well。

 you you wouldn't like when you're sorting by frequency， you don't need to swap them at their time。

 so like sure， but let's even say I swapwamp them at their time。

What then that's a problem no no no why is is it a problem。Let's stick。So what's happening。

 we are saying， oh， every time。The adversary requests the element at the end of the list。😊。

And we' to bringing it to the beginning。I'm paying in every time and T steps TN。But actually your。

过呃嗯对就体。Okay。But now my question is on this request sequence， what is the optim？😊。

Could you have done any better？Not much better， I think。I mean， it requires a proof。

But you can show that on this request sequence。😊，You can't be doing much better。Why。

You see what this equation sequence is， right？I'm requesting all the elements of this set one by one。

😊，My claim is no algorithm can do much better。On this request sequence in this。Why？

So here's the deal， right？Look at this request sequence。Oh。

Suppose you were not changing anything at all。Then half of the requests are to them。

Back half of the list。So for half the time period， for half the time。

 you'll be traveling at least half this list。Now， if you were indeed， you know。

 if you were trying to do swaps， then you have to do swaps in order to bring these elements to the front to the list。

😊，It's not a proof。I'll give you a proof in just a little bit。

But I want to convince you that on this request sequence there is nothing you could have done。

You would have paid， you know， this is your route。And when you want to divide by optt。

I want to say opt to at least omega of。And so the behavior of this would be a constant。

I'm not saying this algorithm is good， I'm just saying this request sequence is not a problem。😊，Yeah。

😊，In的。I feeling like satisfied stuff what。I would love to have concentration sometimes I won't be able to get concentrations。

 but the ideal thing would be getting a concentration。😊。

We do care about what the constant is and in fact sort of the first papers that studied this problem actually tried to really pin down the constant and they showed that the constant could be you know something like two and it could be better than two。

 we won't show two we might show a four but。We'll get to the randomization in just a little bit。

 hold that thought。😊，But right now， I just want to understand some algorithm for this problem。

In the problem clear， do you see why this input sequence is not bad for this album。

This input sequence is not bad for any algorithm I want to claim。Do you at least feel like this。

 you know， you have a sense of why this input sequence is。

Like is's going to pay pretty much in every single step。明得。If not to ask a question。

 you can just say I don't understand that and I don't see。

If you're okay with me proceeding just a little further。

 let me proceed a little further and we'll come back to this。😊，By the way。

 solve by frequency is indeed a problem。😊，For exactly the reasons No I was mentioning。嗯。That。

So the frequency is not an indicator of what the recent requests were。So here's what I could do。啊。

Let me try to construct a bad example。Very quickly。Good。

So let me suppose I started off with the list one throw。Okay。😊，I'm going to request one。Some D times。

Then I'm going to request two。Also three times。Will you do anything？No， you won't do anything。

 one was more frequent than two。And maybe I'm even viewing Toens's idea。

 I'm not going to swap to anyone1。So basically， when 1 t times I paid one every time。

Two teachers I paint two every time。Why， because I'm not going to swap one into。

The frequency of one was higher than the frequency of two。S dance。

I'm not going to do anything because one in two had higher frequency at every single point in time during this request。

And three times。I we to keep going all the way to the end because， you know。

 all these guys had been already requested t times and this has been requested less than t times。😊。

What should I have done？对对。Quest。So， I pay， basically。😊，One times t，2 times t and times t。

That's pretty much like。N squared times t。Where is。As soon as I start started seeing the toes。

 maybe I could have moved two to the beginning of the list。😊，So I would have paid。

T for and for each request。Plus at the beginning of every phase， I would pay n。

So I would be un squared all the time。Give or take。So this would be my cost of art。

Does this make sense as soon as I saw the first two I could have moved the two to the front of the list。

😊，As soon as I saw the first three， I moved three to the front of the listing in one。

So that pays n squared and then for every request I pay one， that's n requests。Thank对。

So this is a factor of N office。Same as。This is analysis。So sort by frequency is not great。

 do no swaps is not great， you can come up with other ideas which are。😊，Unfortunately， not great。嗯。

But thankfully， there is an idea which is great。😊，呃。There's somebody who has not seen this before。

 I'm stopping you right there。Whos not seen this before？Suggestionあ。Based on what we just discussed。

这是。Yeah， so recent frequency becomes。😊，How recent。Is the question to ask。

So we are going to do an extreme version of this algorithm。😊。

And we're going to sort it by very recent frequency， how very recent just the previous request。😊。

So this algorithm is gone。😊，啊。When you access an element， move it to the front。

Doesn't get much simpler than that。Move to the front of the list。Flame嗯 hit。

This is due to actually our own Danny slater。And冇大见。AndD。As。Guesssses and how good this algorithmize？

Yess。我。Okay。😊，So this is that no matter what other algorithm you might be using。

 it it must pay at least a quarter of the cost it can react。😊，喂这位。This theorem， if you believe it。

 proves that on this sequence。You must pay a linear amount on average in every step。

Because in this MTF is going to pay。And every time。So the best algorithm must pay。

10 over four on average。对。That some of is the easiest proof I know of the fact that that sequence is very expensive。

 but any out。Okay， so let me prove this to you。😊，对。It's a nice proof。

 perhaps it gives some intuition for the model as well。Okay， so here's what I'm going to do。

I'm going to maintain。This is another one of these themes that will come again again through the class Im where to maintain a potential。

Okay， so let me just say a hour algorithm。MDF。B is a benchmark category。Here's what I will do。I will。

Write down a potential。Which is a function of our algorithm state and the benchmark algorithm state。

😊，And I'm going to show。That alcohol times。The change in the cost of our algorithm。Plus。

 the change in the potential。Is at most four times。The change in the cost of。Okay。😊。

So if I show this at every single step。😊，Then I get that total cost。Plus the。

Final potential and minus the initial potential。Is at most four times the cost of B。Again， you know。

 this is a standard analysis I'm then just doing it again， I'm just saying with the final potential。

😊，Is going to be non negative。I'm going to set the initial potential。You be0。And then you're fine。

 you know， this is a positive term， so cost of pay is that most for of cost of pay。Or competitive。

 or any other outcome。This word I'm want to prove。I'm going to prove this fact。

Quite very he is a vector cover than might be。Sud it could not be an algorithm。

 he also knows the future， absolutelyute， but it's an algorithm because it has to do all the finds at every point。

It's not's not online， it's not online。够了。Okay， so I have to tell you what the potential is。😊。

So what's the potential？It's the number of elements。嗯。Number of。So a is a sequence of n elements， B。

 the sequence of n elements。PAB is twice the number of inversions。

Is the number of elements which are in the opposite order。In A And B。

Every element which is in one order in a and the other order in B， is called an inversion。Yes。

Pair of， it's like a difference in state between A。😊，哎。So I want to say at the initial situation。

Both the algorithms will start from the same list to feel。Initial。Is going to lose him。

And see at any time。The number of inversiongs is a non negative quantity。

 it cant be it can't be less。Fair enough。But。Now I need to show this。对。So let's do the photo。

So I wanted to say。So suppose I get a request。好的。Findd。So I get a find of X。And in my mind。

 I'm keeping to。this is just I'm keeping in my mind A and B， I've just got this request。😊。

X is sitting somewhere in a。X is sitting somewhere in B。I find X。No。First， let's say。Bペ。

We incur some cost or actually maybe I don't need to do it this way。What are algorithm going to do？

Our algorithm is going to take x and move it to the beginning。😊，So it's going to take。

All these elements。It's going to put x before all the green elements。嗯。Let's take these elements。

And break them into two parts。S is the set of all elements is all the elements。😊，Before。X in both。

A andB。And p is the set of elements。Before。X and a。But not in。So this is S union T。O。😊。

So let's just do a good thing。Cost of our algorithm is what？I have to go from here。Till X。So that's。

The size of S plus the size of P plus one。Plus。I'll have to move X to the beginning。

The size the fast， less the size。你个。😊，And basically it paid this distance plus one to get there and then this distance for the swamps。

So this is the change in the cost of A， but change in the potential。😊，Okay。

 how much has the potential？Suppport then move X to the beginning。The only elements that matter。

Are these green guys and X？These are the only people whose inversions are changing。

Let's look at an element， little SN S。S is sitting somewhere out here too。S and X。After the swap。

 so if I if I， you know， this was the before picture and let me draw the after picture。😊。

As a sitting somewhere。S and X。These guys were in the same order in both AB。

Now they're in the opposite order。So the potential is increasing by the size of s。

But on the other hand， T was sitting somewhere out here and T was sitting somewhere out here these guys were in opposite order earlier。

 but now they'll be in the same order。😊，In being okay。They used to be。You know。

 there was an inversion。But now they live intend in worship。

T is the elements which were before x in a。But after that，What's that minusty？

And this whole thing gets multiplied by  two。Because we had a good sitting there。might said right。

 I know there's nothing much more to do， you know， this is the sum of this it is delta times oh。

 okay， so the sum of these is。😊，The T's go away， so I'm left with four times the size of S。😊。

Plus one， if I want。There're the one。There is a cyber fast， cyber fast， two times cyber4。

also might beling so for the moment， let's just say that these shuffles I'll account for in just a minute。

Good。But let's just say we did it shuffled earlier and then we were in some situation。😊。

And now does its move？And then after that， B will move again and we'll account for that in just a moment。

So， I just did this， the cost of a plus the chain in potential is four times the this thing which is at most。

😊，Four times the size of F plus one。But all the elements in S were sitting here。😊。

That's a lower bound on the cost of half four the cost。我不。对。No sweat。O。😊，So this is。

This change in potential per step change in potential is controlled。And then finally。

 I have to worry about exactly what Tulsson said， which is you know what what's happening to the swaps。

😊，So now。This this was when my algorithm did its thing。Now opt does its thing。When opt does it stay。

 the cost doesn't change at all。My cost doesn't change me。What is opt doing？O is doing swaps， maybe。

But if optt is doing swapbs， it's paying one here， so that's four times1。

And the potential is going up at at most2， it might create a newversion。

So this goes up by two and it's four， so that's okay。😊，And you can see the looseness in the analysis。

 you know， there was a you know， in this kind of second swaps we were doing potentially is changing by two but paying forward。

 this money is being thrown away。😊，We shouldn't throw away money， we should save it。

 So if you save it if you are smarter， you'll get a better constant and that's what the paper does and I'm not going to do that。

😊，Because that requires a minimal effort。是。在这个区。And it feels a bettereration。I think it's true。

 but don't quote me on that we。There's also1 of all sort of finicky details about exactly what is paid for and what is not paid for and paper really goes crvy on that。

😊，嗯。系呀。I stop before I get to that point。Okay， but in any case， so I mean。

 one reason I want to throw you， I want to show you this analysis is because it's sort of clean。😊。

It shows you several of the issues that come up， it shows you an important technique again。

 you know potential functions。Very useful。嗯。And it shows you this sort of issue of。

It not important it is not enough just to show that my algorithm pays a lot there could be instances where my algorithm pays a lot but opt also pays a lot so my algorithm is pretty good。

😊，So I had to show an instance where my algorithm paid a lot， but opt did not pay a lot。O。😊。

So then let me哎， maybe。Let's stop， yeah， two。啊。Let me， let's take a tune that breaks here。

 let me sip of water and stuff。 and then we'll talk about。You know。

 so I then't talk about ski rental。 We will'll talk very briefly about ski rental because it's almost like a。

 you know how you get onto flights right， and they say， oh， they escape exits are， you know。

 there and you know， everybody knows it， but people say， you still have to do it ski rental。

 you still have to do。😊，It's like the dance that everybody does It's actually like when you call our support customer support line and they say。

 please listen carefully because our options have changed no they have not changed I'm sorry but but on the other hand。

 everybody has to say。😊，So I'll tell you about ski rental and then we'll do something else。是。

the definition of the Bur redization。So regret minimization would say。啊。My cost。

Rost of a will that most or at least。No， at most。高速 b。Plus。Regret so it it's usually you know。

 these are these linear type costs and this is like the best expert in hindsight。😊。

And is the the regret。 This is the additive term， is' usually the regret。Good。

 the other difference is usually because we are asking for such a strong guarantee。

 this is usually the best fixed decision in United made。😊，So for instance， we made things like， oh。

 P LT。Tumbmed over time， this was a loss was at most。Beat starve。

L T under the T is under the T plus the。This P star was a fixed decision in I。

 it's the best export in I。Usually in competitive analysis， we are looking at dynamic。😊。

No or benchmarks。B was moving every time， what's that？they do try to capture this。

 but then what would pay if you paste something in terms of the number of switches。😊，Absolutely。

 it's called switching regret shifting regret I keep forgetting this Yeah I guess right so so the thing is that number of switches times the you know。

 the scale of the problem or something like that。😊。

And once you start to allow unbounded number of speeches。That's when you start to get， you know。

 the two problems become start become very similar to each other。And I can talk more about that。

What is modern research for independent analysis？Okay。

 modern research and comparative analysis look at。So let me tell you about a problem that's a modern research and computer in comparative analysis question。

That really a problem that's still open today。We don't know what the answer is。啊啊。Yeah。

One big difference， I mean， in general， what happens the difference between。😊。

Regret and comparative analysis is also。在的。A lot of these problems。

When you're studying combinatorial problems， it's kind of along the lines of what you were saying。

Regrt analysis and combinatorial problems is。😊，I often think of it as somewhat coarse。And。

For these linear problems it's it's very fine it's we really understand these things。

 but for combinatorial problems it's somewhat coarse and。😊，This is where of。

Comparative analysis is much more sort of fine grain， but so here it go。It's called。Yesそ。

It's a problem that's been studied for a long time， but it's still open。

 theres still interesting things that are happening on this very simple problem。😊。

Let me give you the simplest way。You have the line。You have paid servers on the line。

Let me just indicate the crosses。By drugs assembly line。At every point in time。

 a request will arrive somewhere。😊，You have to move one of your servers to that。

You move this server to that request。You pay the distance。That's it。一不管。Mim mine the total distance。

To minimize。In distance all。Well in the case everyone。Here's a candidate algorithm greedy。

Move the close the server。To the location。Is the greedy algorithm good？

My claim is the greedy algorithm has unbounded compared to ratio。😊，Oh。喂。Let's see it for two servers。

Here at two service。嗯。I get a request at this location。

The greedy algorithm will move the closest server。I get requested this location。

The greedy algorithm will move the closest circle。Grey algorithmm will keep moving the server back and forth。

 what it should have done it should have just moved the other server over and taken care of it。

So the greedy algorithm will pay one every time， whether you could have paid， you know。

 10 settled issue right there。😊，So you should be in at least smarter about。对呀。So。It's known Okay。

 so so here is an algorithm。 it's actually a acute algorithm。 Let me tell you about it。😊。

And it works for any number of service on the line。So the algorithm says， suppose I have a request。😊。

Suppose， yeah， suppose I have a request。It seems too service。

It's got this sort of cute little picture that you can imagine there is a fire out there。

 two fire engine see it， both of them start moving towards。😊，This guy was moved。

This guy will start moving and as soon as this guy reaches， this guy talks。😊。

So both of them move an equal distance towards it until one of them reaches it。😊，Now， of course。

 if the if the so it moves that， now of course if the request comes here。

 there's no reason for anybody except。the chosenけも。 so this is called。😊，Doub down。嗯。

Double cover is a competitive with a is the number of。Of service。No， this is tail。

So Ca Boston right now， let's imagine， case more。Ex。This is a good result。

 but it's not as good as we would like it to be。过去。Does there exist？up玻璃 lock。嘅。咁快嘅病。Yeah。哎。Good。

 good， good。 I should have said random。You can show that deterministically you can't do better than this。

Deterministically best。do better than so for small numbers this is been studied quite a bit and there are specifics results no I don't oftenhand remember the results。

So啊。Rightて。Grandomized is where the action is for a lot of these problems。定为即啊。

Its than probability proportion and you could try that so for instance， in this algorithm。

You could say， oh， if I get a request here。😊，I want to move this server with three quarters probability and this server with one quarter probability。

😊，You'll get back double cover， right。You get the same performance at Teleca。

Memory less algorithms can't do better than key competitor。So you got to be memory full。

We were to keep track of what this what requests were close to this， what was the history， things。

 things like that。😊，Yess。Maybe maybe。But you don't want to remember too much from the past。

Because I could imagine all the action happened here and then all the action moved there and you are like。

 oh no， no， no， you know， I should keep server out there。😊，You're got to forget to。

And this is where the state really clear。😊，So this gives you a sense of what like。Re有 know， so以 so啊。

4our years back， one of the。Best papers at the stock conference was about the case server problem and they used some ideas from continuous optimization to actually get good algorithms not for the line for general metrics。

For the line， the problem is much easier， I would still like to understand the line I don't know how to understand。

As I would like to get an algorithm。I can't do better than log K， I can show a lower amount of log K。

So for logs， okay， so log square k I think they can show up for general matrix I don't remember if they show it for the line。

😊，Good to higher dimensions do you pay other exponential。But this problem。

This problem we pay we currently pay polynomial in the dimension。

It's not completely clear whether we need to。We would like to understand that。

 but we don't understand。We don't understand whether there should be any dependence on the size of metric space。

喂。Other questions。So this is called the case I mean whatever caseover problem。

 the caseover problem is fairly general。😊，Let me give you one special case of the case of a problem。

 which is interesting， which we understand completely。😊，Pretty much complicated。

So here's the situation， you have endpoints in the metric space。😊，And you have， again， case service。

So it's a finite metric space， but all points are at distance one from each other。

So all these points， it's called the uniform metric。😊，哎。😊。

This actually hearts back to the beginnings of this work。😊。

Why did people start studying these kind of problems because they said， oh， you know what。

 I have a computer and my computer has a main memory。😊，With end pages of the neck。

And I have a smaller cash。有てページですね。The way my CPU works is that it whenever it wants a page。

 it first looks at the cache。😊，And if the page is not in the cache。

 then it goes to main memory and gets the page here。My cash can only hold key pages。If if it's cool。

One of the pages needs to be evicted from the cache。

And a new page needs to be put in and the question is which page should you evict from your cache？

Now you can think of these endpoints as the end pages in memory and the cache。

 the pages and the cache are where the servers are sitting。😊，The servers are sitting at key pages。

 you need a new page， you need to move one of your servers over。

 you need to evict one of the pages and bring a new page into the cache。😊。

So this problem is called the paging problem。And for the paving problem， we know。Beay competitive。

Deterministic algorithms。And this is best possible。And we know。Xケ competitive。

Randomize algorithms and this best possible。Oh， it's， I should have mentioned the harmonic number。

 it's one plus1 over two plus。😊，完了的。No conscience， no nothing， this is it。By the way。

 this is work that Danny did， you know this is this is all stuff that Danny sort produced。

 so this was in the 90s people figured this out。😊，But the general problem has be much more difficult and maybe because at that time we were not looking at techniques。

P from continuous optimization， which are proving to be very powerful out here So you know another reason why。

We should know this stuff。So， in order to。Let me give you at least a sense of what's happening here。

So I'm going to study a variant of this problem in a very， very， very special case。

I can tell you the algorithm， but you it's easier to analyze this， okay。

 let me tell you this algorithm， but I'm going to tell you an algorithm。😊。

Which is two times the harmonic number comp。Not important you can improve it right who cares about the content right now？

Maybe people care， but right now I don't care。So here is an algorithm。啊。So it's called。Marin。

Remember， I want to do page anyway， so I want to keep pages in my cache。

I want to get rid of old pages。So here is what I'll do。I'll say I have eight pages of cash right。So。

 when。The request。Is not in the case。因为。And。Unmarked page， pages are marked or unmarked。😡，不 guess。

Okay。😊，Bring， you know。Bring。The request came through the cash。Market。Firstls。

 bring the request into the cache and then mark。The request， okay， so I shouldn't say。Mard。

The request， bit。So the request was not in the cache。

 we evicted a page and brought the requested page into the cache。😊。

Now you always mark the requested page。And then you could save when all pages。

 what happens when all pages are marked when all pages。😊，And see Mark。翻埋过嚟。咩。

This is a deterministic algorithm。😊，This deterministic algorithm is key compared。😊。

Prorowth potential function。I could make it randomized， how should I make it randomized？

vic the random and marketing。Uniformly random among the page。Rand my is algorithm。

This rhized algorithmism is two times harmmononic number compared。😊，Third again， nice proofs。

 several nice proofs。Not to。In fact， today。Maybe we'll do a baby version of this thing。

 but it'll show you some of the ideas I want to show you the ideas more than the sort of actual analysis。

This algorithm kind of makes sense， you know， whenever you request a page。

Whenever pages have been used recently， you mark them。And then when all pages have been marked。

 you say， okay， well。Inner pages have been marked。It means， you know， okay。

 so so let's look at this when all pages in C being marked。

 what can you tell me about the pages in the cache？😊。

These pages have been so look at the a time when all pages are unmarked。😊，Then as you request pages。

 you mark them。😊，If all pages have been marked。😡，And a new request comes in。

I know there have been key distinct requests since the time the first land marking， right？

Which means the optimal solution must have also。Got to suffer at least one page fault。

So whenever all pages are marked， it's somehow proof that look optim must have paid something。😊。

It's okay， I paid whatever my my sins are washed away。Because， you know， opt paid something。

 whatever I paid in this phase， I paid in this phase。I'll charge that to one have to pay。

I'm waving my hands， but it's not I'm not waving my hands too much。 this is how the proof goes。😊。

So this is this is like paging and Beijing goes back ways KL also goes back away。

 but we still don't understand it。😊，嗯。Let me tell you， okay。

 since since you asked maybe we won't talk about S inter。😊。

So let me tell you about the different product。And this one I it's a favorite of mine and it's perhaps my only result that I'll talk about healthcare。

😊，Yes。This one I like the sort question a lot is okay， I'll turn up。😊，So this is called。借边。

Pn functions。What's the problem？I got any step。A convex functionals。F aB六。Exl定。

Is mapping de dimensionmensional space to the res and let's say non negative reels is revealed。

I need to pay。I need to play， sorry。As an algorithm， I control a point。I play some X。And our this。

what's my cost？My cost is F of。But。This is where we heart back to this notion of state that I keep talking about。

😊，Back。Changes in disnce grasping something。Euclidean normallys。Or simplicityity。

I would be exactly in the online convex optimization regime where I know rating desent gives me good regret Karen。

😊，But now I have state。I used to you know have 32 data centers open at these locations。

 but now I need these other cycles data centers open whatever there is some motivation no I won't for as we said we wantt for motivation。

😊，Its这。Good。With this problem， you can ask the question。😊，So let me give you a lower part， okay。

 let me give you a special case of this first。😊，啊。Special case。Number one。Taving bodies。Cing。光历。

Whatです。At this point in time， FT。Is actually an F of x。

Is the indicator of some convex body KP of things。Theres some con body that is revealed to you。

You are very inside the convex body and infinity outside。

So what does this mean in order for you to have any reasonable chance at being comparative。

 you better move your point xt minus1 and this is like say K 2 xt minus1 happen to be outside you better move it into the conve mode。

😊，Through your costs。Will be either0 or infinitefinity you don't want infinite cost of course。

 so you make this you make sure that Xt lies in K。And so you are really paying for the movement。

So this just means， therefore， you know， must。Have。Exreizing。And really you want to minimize。嗯。

Veryair enough。Csing Congress。Con experience。Let me show you。Hello吧。I'll tell you guys。😊。

You start at the origin， so this cube is the plus minus1 cube。哎。

So this is minus1 and1 through the degree。You started the origin。I'm going to tell you guys。

I'm going to make you move to a corner of this cube。Which corner I'm not going to tell you。

I want to slowly make you pay for it， right？Step one。I give you a face of this view。Now， you know。

That you must be at one of the corners， one of the two to the d minus1 corners of the cube on that phase。

Which one you don't know？获利管染者。You want to move to the center of that。Because， hey， you know。

 as soon as you show bias one way， I'll make you go the other。😊，Worst case， right？

And then I'll show you a line out them。A D minus two dimensional path to phase。

What are you want to do， we want to move to the middle of that。Then finally。

 also your corner you move there， how much did you pay？1 plus  one plus 1 d times。

 how much should you have paid？Square root点。这个 lo帮。You know， add。P it is the。O this。我有病。

Ratio of square root。 So the comparative ratio is at least square root。

So is this for any what anyhow？I every have to project good。

 so basically here's what I'm saying that let's just look at the last step。

 suppose you were sitting at the middle of a square。😊，I told you， well， eventually no。

 I'm going to make you move to either this point or this point。😊，Right now you， you know。

So what are you going to do， you know， I'm saying your only sensible thing is to move to the middle。

As soon as you give me a slight bias one way， I'll make you move to the further viewpoint。😊。

So this is like a mid Max argument I'm doing out here I'm you know not being precise。

 but you know you can make this precise just as soon as you show a bias one way it's like I'll make you move here。

😊，Yes。So positive real is。😊，Otherwise the problem becomes that you know this quantity if this is negative。

 this could cancel this out and then you get into you know multiplicative versus addative issues。

 so that's why positive is important。😊，Other questions。

Will the lower bound of squared root be for any output。Ill ask you a question， open question。

Does that exist？An algorithm， a square would be compared to either。We don't know。So recently。

 some students and。And I and then another of work by。No。A student at Stanford。We should。

But你 convert to话。This had been open for quite some time。Be sure to make back。U。Not going to give you。

No， it is the bad right now。你。We can。D is the best right now。

 There there' is one slight difference that you can do。 You can do square root of D times log of the。

😊，Request sequence。Lent。So if the request sequence is short， then it's square root D。

 but if the request sequence is allowed to be unbounded， then this can go off。😊。

Infinity then we will be the best right now， so it's the main of these two things。诶都嘢。

How the can the of both world can you have some cleverutter these two so there are of standard tricks which maybe in the next homework。

 but in any case I can tell you more about it some other time that can achieve the best of the two maybe losing a little constant factor somewhere。

😊，Yeah， maybe next homework there'll be an exercise about this thing。

 how to combine two algorithms to achieve the best of the two goals。Nice trick。O。So。😊。

Let me tell you。An algorithm for a special case of this conx changing and this will allow me to teach you one more geometric fact。

And it's not really a geometric fact， it's an object you might have not known existed before。😊，走啊。

So I'm going to ask the following question Oh， by the way， remember this。

So here is a thing called nested。Conveex for。And the problem is going to be the following。

And don't think of this in terms of comparative ratio， just think of this as a standalone problem。

 so if you zoned out， you can come back。😊，And。This is just completely self content。😊。

X0 is the origin。When why is somebody calling me。Okay， sorry， then I can take the call right。嗯。

All the game is happening inside the unit ball。In D dimensions。诶。😊，X0 is the origin。Now at each time。

I'll see。A Kt， which I know is a subset of Kt minus1。

My convex sets are just getting smaller and smaller so K1 could be looked like this K2 looks like this K3 looks like this K4 looks like this。

 whatever。😊，The convices are getting smaller and small。Fair。对。What's the best， okay？啊。So， you know。

 we must produce。XP belonging to KT。And we want we just want this。

 don't worry about competitiveness and stuff like this， we just want that the total distance move。😊。

Is at most。Some function of dig。You should think of it as the following the or you started from there。

 the best solution would would be to project this point onto the smallest of these ks。😊。

That's what the optimal solution should do， that will cost it most one。

We want to pay some function of d times 1。Think of it this way if you want。

 or just think of it this way。😊，I'm going to make you travel some trajectory on the unit board。

This trajectory， I just want its length to be bounded by the functional P。What's that。Oh， sorry。

 look is what。And what help。三。没那个。嗯。The are okay， I say it， but I didn't。你ment。

Everything's in dimensionment。对。你就是。How do you use an episode？空调唔闭。这条科学。啊。

I don't see why you have to place the effects。你为什么。So you were sitting inside K5， let's say。

I show youケ6。You happen to be sitting X5 was there。Which point would you choose in X？W just。5，6。

So K6 is this I get， you know， I see K6 not get to K6 oh I'm getting access to K6 I'm seeing K6。

 this is K6， this little box is K6。😊，Which which point in K6 do you want to choose the x6？

It was like if I know where he sit， I just doesn't make I put next slide inside。No。

 the next five is fixed， right？要说机费。Let me say thisす。Iソケワ。Now I will say， Jo。

 what point do you want to give？Which point in the K1 do you want to give？就问 x y ok。This is K2。

What point would you like when said back？没个。What's the news？Bally average mass。

 average mass thankfulctualy。Yeah。X， I'll give you x31 right。Okay， good。So here's an outlook。

At each point in time， move to the center。Backact。😡。

The length of the sequence could be much larger than one。😊，Here the proof。

I start off with a box something like this。Where is theroid， the centralroid algorithm？😊，I leave you。

A body which looks like this。Where's the sroid？Because the body is sloping。Most of the masses here。

The centroid will be somewhere over there， especially in high dimensions。嗯。

I'm going to level out the body。Where is the central， the central is。

I'm going to give you a sloping thing again。Because it's high dimensions。

 youre going to move all the way back。😊，You want to keep moving back and forth。

What should you have done？😮，She just gone straight down， right？The centroid has unbounded cost。对。

Okay， so we tried central right。And I do realize that we are out of time。I'm just going to tell you。

Greedy。Actually works better than centroid surprisingly I did not expect that I expected centroid to work well and greed not to work well。

😊，The greedy gives you a partner。That's just the part。Of at most。呢都 be啲。It requires the theorem。

 I don't know of an elementary proof for this。So， let me give you。One fact。

In the last negative three minutes。Here is here is the theorem so this final thing is not mine。

 I had a slightly more complicated algorithm。😊，But this final point， this final thing is not mine。

 it's due to some other group of people。Oh。There's something called the Ste point of the convex body。

I didn't know this， many people don't know this， so I'll give you a definition。

So the time point of the conve body looks like the following。

 so let me just let me show it to you for poly。呃。9。サビ。

Minimum of not quite so that's another notion of center， but here is the notion of center。😊，Look at。

The normal cones at each of these points， so basically I'm drawing this is the normal to this line and this is the normal to that line。

😊，So look at it this way， pick a random direction。😊，Uniformly。

And go as far as you can in that direction。If you went in any direction along this arc。

 you would end up here。If you went on。Any direction along。

ThisThis side you would end up there and similarly you would you know。

 I'm just running the normals out here。哎。Take the average of these points。

Proportionally to the volume of this normal coin。I me give you a point on the inside。

This is known as the Steinup Point。And here。Can your compute is efficiently exactly I don't think so。

 or I don't have a Shap hardness for it。😊，But but you。

 it seems so close to the centroid I think I should be able to prove a sharp hardness for it。

 but just the same way as volume sampling gave you an approximation to centroid volume sampling and gave you approximation to start。

😊，And the tatem is。If you take Xp to be the standard point of KT。This will give you this guarantee。

If we had more time I'd do the probe， it's very beautiful， but I don't， so let's stop。😊，系。

Will continue in two weeks。 Remember， next week， there's no lecture。I have to lose some。Was that。

No lecture。We will come back in the week after， and we'll post in Piazza as well。

