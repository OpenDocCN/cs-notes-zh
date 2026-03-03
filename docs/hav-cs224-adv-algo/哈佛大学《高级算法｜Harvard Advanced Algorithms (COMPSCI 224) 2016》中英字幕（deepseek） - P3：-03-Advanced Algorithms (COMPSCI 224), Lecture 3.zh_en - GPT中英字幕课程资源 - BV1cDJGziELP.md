# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P3：-03-Advanced Algorithms (COMPSCI 224), Lecture 3.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

![](img/9b2c96183a98c9b8e0ce08b5f9d33096_0.png)

I guess I'll get started。So。The last thing I'll talk about is also in the word RA。It's hashing， okay。

So I'm going to cover us today， hasshling。嗯。And we' see it we'll see。Lad balancing。

We'll see KY independence。I will see the dictionary problem。🤧う。嗯。And here we guess we'll see。

 I'll just review perfect caching。Very briefly。And then I'll cover linear probing。

So who took CS 124 last semester？Not a lot of people。So I covered this last semester。

 I guess I'll say some more about it this time。 but who has seen perfect hasching。

W who has not seen perfect cashing？Okay， sorry yeah。嗯。Then I'll look at the retrieval problem。

 I'll define what these things mean。And here we'll look at cuckoo hashing。呃。And blue mirror filters。

Well， I guess somewhere in here I should have。Five actually comes before for， it's a membership。

 and that's boom filters。And then if we have time， I'll just say a little bit about。

Simple tabulation hashing。But not much。Becauseuse I don't think there'll be much time at that。

Tousin bloom filters。Okay。Okay， good。Let's just before I talk about what。Problems， hashing solves。

 I'll just say a little bit about。What hashing is？So I imagine that。We're going to have some family。

H of functions。Remember're on road Ram， so we're mapping。Let's say。By this， I mean。

 let's say zero up to u minus1。Mapping what0q minus-1 into。诶。Zero to m minus1。Okay。And。嗯。

There's some set。S， which is a subset of U。And the size of S is n。ok。Such that。We want。嗯。

Some H in this family， we pick。To， you know， behave。Nicely。

We'll see what that means in applications on S。For example， nothing in S should collide。

So the picture to have in mind is we have some n items。I1， I2。

 I'll just usually call these items1 up to n。Even though they're arbitrary they're arbitrary n items in the universe。

And we have some hash function H。Which sends them。And let's think of it as like， say an array。

Of size M， this is cell 01 up to M minus1， and each item gets hashed somewhere。

And there could be collisions。Okay。Good。So now that I've said very vaguely what hashing is all about。

 let me say something about one of the problems that hashing solves， namely the dictionary problem。

Or before I even get to the dictionary problem。Let's just say for example。

We have jobs and we have machines that handle jobs or servers。 Okay， so let's say it's example。

 It's not really a to example。 It's a real one。U。We have。You know， end jobs。That need。To be。Assigned。

To M machines， let's say。And each job。Or do you I have a scribe for today？Yeah， great， so each job。

Has some job ID， let's say。In this range in this universe。Okay。嗯。So if we know all the jobs up front。

 what's one reasonable thing that we might want to do。

 let's say that the M machines are all identical， none is faster or has better hardware than the other。

 We'd want to evenly spread the jobs across the machine so that each job each machine gets roughly n over M jobs。

Okay， if we know all the jobs ahead of time， we could just do that。

 we could just take the first N ofM， send them to one machine， the next N ofM。

 send them to another machine， et。But if these jobs are coming， let's say， dynamically online。

 then we just need to send somewhere， well， I guess even there we can。

We can just send it to the least load machine， but let's say that。

We don't have- you know that requires some global picture of what's happening。Across all machines。

 And let's say that we want to do something just on。Without that global information。

 one thing you could do is just send it to a random machine。Okay， which is。

 let's say hashing it to some machine。Job has some job ID in you。 so when a new job comes。

Have it processed。Let's say a new job， J comes， J is in one to U。Comes have it。And。Processed。

By a machine。H ofJ。we might want to understand。How well does this behave， meaningan does any。

Does any bin get overloaded， Does any machine get overloaded， Okay， we'd like。

 we'd like it to have N over M， but maybe it'll have much more。 So this is called。Usually called。

You know， the balls and bins。Random process。Where we have end balls and we're throwing them randomly into M bins we want to understand how this behave。

Behaves。So。So this is some form of load balancing across machines。And we'd like to say。

We'd like to say。The probability that。There exists a machine。Receiving。Bigger than K jobs。

Is something small？So the question is what goes here and what's K？So is the setup clear any evil？

Let's say if H is a totally random hash function。So before I analyze that。

 I want to prove a certain tail bound， who here has seen the turnoff bound？Okay。So。

Let me prove a theorem。Suppose。X1。X， N。Our independent。Where Xi is either zero or1。

 these are independent random variables。And the expectation of X is P。

Meaning it's one with probability P and Z otherwise。Then。

Where if we let x be the sum over all these eyes of Xi。The probability。

That x minus the expectation of x。It's bigger than， or let me write it like this。

The probability that X。Is bigger than1 plus deelta times its expectation。Is that most E to the delta。

 I can even say。Is at most e to the delta over 1 plus delta to the 1 plus delta？

To the expectation of x。Okay。So。How do we use that to analyze this thing over here？Malls and bins。

So let me look at one。One case。Suppose， for example。That M is equal to n。

You're servicing these end jobs using end machines。So on average。

 you want every machine to have exactly one job。Then。The probability。That there exists a machine。

With more than some C times log n over log log n。Jobs。Is that most one over some polled？

And how do we prove that？Using the turn off down， for example， but we're going to see， I mean。

 the turn bound is overkill， but I just stated it。Because it's useful as a tool for other things as well。

So our people lot people with me。Allright。Feel free to interrupt me at any point。

So there are these Xs here。 So X I。 So focus。On some bin， on some machine。Let's call the machine T。

 machine number T。And define X as being1。If H of。I is T and zero otherwise。

 meaning that job I got assigned to machine T。Which implies that x is the number of jobs。Assigned。

To machine tea。And that thing over there tells us that the probability that the number of jobs assigned to machine tea。

 the probability that that's bigger then。So I'm going to apply this with Delta being this log n over log log n。

So what's the expectation of x， it's 1。The expected the number of jobs that land is one because there are end machines and jobs。

So there's  one plus log n over log log n。Which is basically which you know。

 if you adjust this constant C is basically like C log n over log look yeah。So in this case。

 Delta is really large， so one plus Dlta is basically Delta。So the problem is that X。

Is bigger than C log n over log log n。Is at most。嗯。E E over。So again。

 one plus delta is basically Dlta being slightly sloppy， but what I'm saying is fine。诶。二。Over。

C log n over log log n。To the。Again， to the basically Delta。C login over log login。Okay， so this is。

 let me say this is e over k to a K。Okay。And。1 over K to the K is1 over poly N。

 exactly when K is roughly log in over log log n。Okay。嗯。I don't know if people have seen this。

 but kind of the simplest way to see that is to take logs。Okay， so。The solution。To。

 K to the K is some polynomial in N is。Log in over log log in。K is this， and why is that？Take log。

 so this says K long K。Is。Is equal to C Law N。Okay。And。Kind of if， if you pick。

 if you pick K to be if you pick K to be a small constant times this。

 then you'll see that basically this will be too small。

If you pick K to B at large constant times this， you'll see that K K long K will be too big。Okay。

 so the right answer is that k is somewhere in this vicinity。 and this is at most。

One over ended the C prime。Okay。So the probability that。Machine T is too overloaded。I iss this？

And by union bound。This implies。That the probability that there exists a bad machine。

 meaning an overloaded machine。 Let's say there exists an overloaded machine。

Is that most the sum from T going from 1 to n？Of probability。That T is overloaded。

Is that most1 over n to the c prime minus1？This is just n times Z。Okay， so if you do this。

Hashing business then with high probability。With probability， one over a polynom N。You might fail。

 but with high probability， probability1 minus this， you won't fail。

No machine will receive more than this number of jobs。Now， in terms of proving the turn off bound。

 I'm not going to do the full proof。 there are proofs everywhere， basically on Wiki。

 even I'll just sort of tell you how it goes， but we'll see how to prove some other things that are。

It's not particularly difficult， there's just a trick in the very beginning。不。So。

Raise your hand if you've seen Markov's inequality。对。So。

Let me just remind you of Markov's inequality。So before I write this， okay， so Marks inality。

It says that， if x。Is a non negative。Random variable。Then。For all， let's say lambda bigger than zero。

 the probability that。X is bigger than lambda is at most the expectation of x over lambda。Okay。

That's Markov's inequality。And then the proof of churnoff。I you just say？

The probability that x is bigger than this value here， lambda。Lambda this thing over here。

 1 plus delta expectation of x。That's equal to the probability that E to the T T is I haven't said what t is。

 but E to the T X is bigger than E to the t lambda。This is true for any positive T。Right。

This is bigger than this， if and only if this is bigger than this for positive T。

And then you apply Markov， this is at most e to the minus t lambda times the expectation of e to the Tx。

And then you just need to bound to this thing。Okay， so I'm not going to do that in class but。

That's basically how that goes。And when you bound it， you get this。 Oh。

 when you need to choose T and you choose。When you end up actually doing calculations。

 you'll choose t to be the natural log of  one plus delta。I haven't justified that at all， but。

Look up a proof on wiki。Okay。Now。I mentioned the turnoff bound。Is slightly overkill buds。嗯。

Because theres a much simpler proof。嗯。Namely， what did we say above， we said that。

You said that the probability that there exists in overloaded machine。

Is that most n times the probability that。Machine  one。Is overloaded。

I just mean all of these probabilities are the same。So it's just n times the first one。

So really it all came down to bounding this thing。Okay， questions。Okay。

So what's one way to bound this probability？Well， what does overloaded mean it means that there are at least K items that map there。

Right。So this thing。Is equal to the probability that there exists k items。Mapping。To machine one。

Which， again， by union bound is。At most， the sum。Over。Seets。T of K items。Probability that。T。

 all maps。To one。Okay。But what's this probability？Let's say H is totally random。

 it sends each person to a totally random place。So what's the problem that everything in this set got mapped to one？

1 over end of the K， right I said M is N。So。Probably that the first guy in team map site have been one is one overren。

And then second guy again， went over n， et cetera， and they're independent。

 so get one over n to the K。So this is equal to the sum oversets。

T of P equal k of1 over end of the K。And how many sets of size K are there？And choose K。

 So this is equal to。And choose K。Over。End of the K。Okay。And this is at most。One over K factorial。

Right。Just if you write out what N choose K is， you'll believe me。Okay。And。I mean。

 K factorial is not really the same as K of K， but it almost is， I mean。

 one thing you can say for sure。Is。K factorial is certainly at least K over 2 to the K over2。I mean。

 some people can get fancy and say sterling or something， it's not really necessary。

So this is at most。1 over k over 2。To the care over two。So now we're back in the previous situation。

 right， whenever you have like one over。When over x to the x。 and you want that。

 whenever you want x to the x to be n or something， x should be log over log log n。

 So K over 2 should be log n over log log n， which means K is like log n over log log n。

So you get basically the same thing。So again， this becomes one over polynomial and N。

 So there's something。so that's all I really wanted to say about。About load balancing。

But now I want to say something about QY's independence。So the proof that used the turn off bound。

 note that in the turn off bound， we needed that the Xs are all independent random variables。

I didn't actually prove the turn off bound for you， but at some point in the proof that gets used。

Whereas here。We didn't actually need that。The random variables are all independent。 right。

 What are the random variables here， so。嗯。So what is this。

 I can write this as a product of indicator random variables。Basically， this thing。

 if you use the same notation for Xi。This thing is the same thing as。呃。The expectation。

Of the product over I and T。Of。Xi。Okay， do with me？X I is one。 So let's say here machine 1。

 X I is one。 If item I got hashtag。Machine one。So this product is one only when all the machines hash to one。

 so the probability that this product is one is exactly the expectation of the product。And really。

 what we used is that this thing is equal to。Well， you say we said it was 1 over n to the K？

Why did we say that， Because if these are independent。

 the expectation of the product is the same as the product of the expectation。

 that is equal to the product。Over I&T。Of the expectation of X。This here was 1 over n。

 and then we got 1 over n to the K。So in this proof。If you're careful about writing it。

 what you'll find is that。😡，You don't actually need all of the hashings to be totally independent。

You just need。This property。Meaning that if you look at any set of K items。

And look at where they hashed， that behaves as if it were independent。

which is a weaker property than saying if you look at all n items， they behave independently。Okay。

 so。So KY's independence。So we say， so the definition。Is that x1 up to xn R。KY is independent。If。

For any。Set of indices 1 less to I1， less than I2， less than IK。Okay。The random variables。X I1。

 X I 2。X IK。Ourre independent。Okay， so if you haven't seen this before。

It might look surprising that this is different from being independent。 you know。

 what's an example of something that's K wise independent but not independent。

Who's seen KY's independence just so I have a sense。Okay， about half。And okay。

 so that's KY is independent in terms of random variables。 But we're talking about hashing。

 So what do I mean when I talk about KY independent hashing。So also， another definition。A set of。

Tash functions。H。Is a key wise。Independent family。对。For all。Let's say i1， not equal to I2。

 not equal to， not equal to Iu。In。I'm sorry， IK in U in the universe。

 so if you look at any K values in the universe。And look at where they hash to。Okay。Oh well。

 actually let me write it like this。 I already said what KY's independence means over there。

The set of random variables。H of x H of0， H of1。H of U -1。RK was independent。Where。

H is drawn from this family uniformly at random。So that's my random experiment。

 I have this family of functions H， capital H。And I draw one at random。

And I write down U random variables， which are just the evaluations of that function everywhere。

And this set of n random variables should be KY independent， as I defined over there。

 That's what it means for this to be a KY independent family。So for example。The set of all functions。

Is a KY independent family？For anyK。Okay。嗯。But you can come up with other families as well。

 He so let me you an example。 So now definitely feel free to ask me a question。I feel like。

People are looking。That means suspiciously。A nice thir， by the way。は。😊，嗯。Yeah。So。Example。嗯。H。Bing。

This set of all functions， I said。From U to M。Is。Is a K wise family for all K？

IfWe're all K that it's at most of you， otherwise it doesn't make sense of。

You random variables and you're saying they're two U is independent or something So another example。

Is that you？Equals。M。Equals P prime。And H。Is。The set of all functions。H of x， where。

H of x is equal to the sum I going from 0 to k minus 1。Of。AI X to the I。You know my P。

The set of all degree k minus-1 polynomials or degree yeah， degree K -1 polynomial。

And there are some advantages here， I mean one of the primary advantages is just the space it takes to store a little H。

Right so at some point in algorithm， you have to represent little H。In your code。

If you have a totally random hash function。You know。

 how many bits does it take to store a function from this family？You log M， right， you log M。

So for each of the elements， you have to say what it maps to。

A number up to M takes log n bits to represent， so this is u times log M bits。Whereas here。

You know thing this AI is in the set range from 0 to p minus1。And again。

 I said to that you and M are both。Are both this。 So what here what is the。Here。

 how many bits does it take to store？To store a random hash function。K -1 log P。 Yes。

 I'll even say K log P because they are actually K coefficients。 There's the the constant term， too。

 But yeah， K about K log P。 So K log U。So this was like U times log M。

And let's say here you andem are the same， So think of this as like U log U。

 whereas this is like K log U。So if k is a constant， if you're working with two wise independents。

 which we will at some point or constant wise independence。H here takes log U bits to store。😡。

It here it takes the Ubits to store or U log you。 So this is way more expensive to store than this。

Okay and。So now the question is， just going back to that example with load balancing to prove that result。

What independence did we need。So there。嗯。There was not the case that u was equal to M。Okay。K。

 and what was K？Yeah， log in over log log in so you can get away with know weaker hash families to accomplish that。

Yeah。Okay， except there's this annoying thing that over there， M was not equal to U。

 it was equal to n， and n is probably much less than U。So let me just say something about that。So。

Imagine that。So here's another example。Which is just H。So now here。

I dont want to say so don't want to say that u is equal to M， but I'll say。M is equal to P。

 and that's prime。好人。And， you know， for any given number， there's a prime that's pretty close to it。

 That's within a factor of two of it。 So it doesn't really hurt us much by assuming that M is prime。

Okay。But you now you can be very different from M， which is really what we need over there。

 You know here M is not U， it's n or it's something。

So here we can just define H to be the same thing。H of x。Such that， you know， H of X is the sum of。

AI， X to the I。Ma P。Mar end。Okay。So。Oh， by the way， so。Before I do that。

 let's just go back here for a second。Why is this a KY independent family。

 Does anyone have a guess or does anyone see why this would be。Yeah。Yeah， okay， yeah。 okay。

 So if you put it that way， yes， so。So you're saying basically that the certain matrix。

 So there's something called a vandermon matrix。 and it's。Non singular。 Okay， but yeah， okay。

 that that's true。 But I I want to say it in a way that， you know， it doesn't scare anyone。 So okay。

 so let's， let me just say it like this。 So the answer is polynomial interpolation。Okay。

 so the basic idea is look at any K indices。 I look at any K different values of x， X1 up to x K。

Okay。And what I claim is that kind of all。All evaluation。 So let's say that。So。So look at。You know。

 some x1 up to Xk。And look at h of x1 up to h of x K， where H is totally random。Right。So。

I claim that kind of every。Every possibility happens exactly once。So if you look at。

H of x1 is equal to。Y1。H of xk is equal to Yk。Okay， and you ask。

Can I choose coefficients to make all of these things happen？Yes。By polynomial interpolation。

And this is true for every single Y1 and YK。And how many possibilities are there for these y went up to YK they are p to the K possibilities？

And how many possibilities are there for the coefficients。

 there are repeated K possibilities for the coefficients。

So each setting of coefficients gives a different setting down here。Which means that。嗯。

The probability of seeing this。For any settings of the Y's is exactly1 over P to the K。

Which is just like the totally random case。好。So now if you move over here。😡。

It's not going to be true that it's1 over m to the K。

Because when you take mod P and you take mod P mod M。There's some like wraparound issue。😡。

So we know that。This value is like a totally random value from 0 to p minus1。

But a totally random value from 0 to P minus1 is not the same as a totally random value。Moern，2。二喂。

What's going on here？呃。Oh， no， no， no， no， no。Thatdly， I know what I did。还谁？

As was confused for a second， U yeah， So u equals P but。P does not equal M。Okay。

 that's what I went to say。Good。It's still true， though。

 that these random variables are KY independent。But it's not true that。

The probability of this happening is when of repeat of the K。In particular。

 if you just look at one item and look at where does it map to。Where it maps to。

 it's not going to map to someone with probability1 over P。Or1 over M， sorry。Does anyone see。

What I'm talking about。嗯。Yes， M is less than P。 Think of M as less than P。Yeah。

 it won't matter too much， but yeah， you can think of M as listen P。So let me just draw a picture。

If M is less than P， so here's M。And here's P。Okay。So if you give me a random oh yeah。The first。Yes。

Okay， I like that wraparound。ai wait， what do you mean by the first inbox or overflow？

We can think of。Time P。A multiple of P plus and junk。 Yeah， yeah， okay， Yeah but the still。Thanks。

 but those getting out affected。It's the same reason if you have a random variable on you。

A randomom variable in the range like one2 pay， you can just tru it。Right。Wait， okay。

Maybe I don't know if this is so let me rephrase the spirit of what you said， I think maybe so。

So the point is， if you have a random value between。

 So this we know from before behaves completely uniformly， not just independently。

 but uniformly in 0 up to P -1。Which means that we get a random value somewhere in here。

But a random value is somewhere in here。 Well， you know， it's sort of like。

There's a random value from， and we're taking it mod。 So here's a random value mode。

Here's another value random value mod。 Here's another random value mode M。 but then there's like。

There's some point left over， the leftover is where。It doesn't quite go up to N。😡。

But the point is that。It might not be true that a random， that this thing， that this expression。

Is uniform in 1 to M？But， nothing will get。Kind of more mass than a one of M fraction。

 Everybody will be between roughly 0 and 2 over M。Okay， so what I can say。

 what I can say is that at least kind of for all。For all x1 and up to x K and also y1 up to YK。

The probability。That H of x1 is equal to y1。H of xk is equal to YK。And certainly at most， you know。

2 over M to the。To the K， not one over R but two over M。

 that's something like that is definitely true。我人。And this too is even better if P is way。

 way bigger than that。 if you have lots of wraparounds before the slosh。Okay。

 so we said that we can get away with。Log in wise In。 Oh， and I guess another thing I should say is。

Notice that this is really still good enough for the application。Right。

 if you look down here with the balls and bins thing with the random jobs， I mean。

 with jobs randomly mapping to machines。It won't be one over end of the K anymore。

 but it'll still be like2 over end of the K。And then if you go through the calculations again。

 you still get roughly log in over log login。Okay， so。This thing is usually good enough。

I'm sort of scared by people's faces okay。Right。So the point is imagine that P was just like m plus1。

So there's like some wraparound。And then one more item。Okay。

So we know that we're getting a random value between 0 and p -1。

 So we're getting a random one of these values。And then we're taking it modM。

So are we getting a random value mode？😡，Not really because。You know。

 this and this modM are exactly the same。So this value is like twice as likely as all the other values。

But that's really the worst case。As you wrap around more and more and more kind of。

The the items even out in terms of how likely they are。

But kind of this factor of  two is the worst case where there's one item that's kind of right after the。

The wraparound。Does that make sense。o yeah。Yeah， I mean， this too is very much slopper than。

Then what I could get away with。No， I think I really did mean m plus1 when P is m plus1。

And then let's say that all of these， all these yI's are zero。Okay， or one or something。

 all these YIs are one。Then。All of these really are something like roughly。

Two overM as opposed to one overM， and then you get two over with。Yeah。How does that bound？

Sorry why does what give you what？嗯当。This。Oh， because。

When you look at this jobs to machines business。Kind of everything。 at the end of the day。

 everything hinged on bounding this。 We have a set of K items。

And what's the problem that all the items map to the same bin？And that's exactly this。

So this is item one。 What's the problem that have mapped to that bin。 So in this case。

 all the YI are even the same。So let's just call them all Y was the probability the first item map to Y。

 the second item map to Y， all of the map to Y。So we won't get whatever over end of the K。

 but we'll get。Something close。And then that's good enough to give the same answer。Yeah。Not sure。呃。

Oh。When you say repeatedly apply it。You might potentially need。I'm just thinking like I mean。

 so the way I'm thinking about this。嗯。This is essentially the same as you generate a random number of。

がの？Okay， a number from。You like generate a new random number and do。Oh， like rejection sampling。

 okay。SoWhen I was thinking is like if you have something too high， well。

 you still want to put something。Yeah can you just repeat it back？You have something。Yeah， I guess。

 I mean， if P is way bigger than M that well， first of all。

 there are n different hash values that you're interested in。So， I mean。

 are you going to reject if like any of them messes up and if so。

That's probably pretty likely to happen， so you'll be spending a lot of time。

In't that's efficient if you。But then you picked fresh AIs just for that one。Like the same。

 the same H， the same AIs are being used for everyone。 And the go and the plant， you know。

 the reason we're doing this is because。We want to reduce， say。

 the amount of space it takes to store this hash function chain。

So if you're storing different H's for different x's， then you're losing outom thinking。

Whatever you get out of age， like feed it back into it。你 should。We should be increasingly more。

Whatever you get out of H feed back into H。嗯。Okay， then。Unless you hit a fix。もだ。NoYeah。

 but I don't know how to。Well， yeah， I'm not， yeah， I'm not sure。 Oh， but okay。

 so actually one thing that I also wanted to say is， you know， I said。

 it might not even be obvious that there are KY independent hash families。

 which are not just all functions， right。So it， I mean， I don't want to say， it's。

 it's not clear that， say you could get a two wise family or a three wise family， et cetera。

 which isn't just independent。 So why is this， Why is this， Why are these random variables。

 not independent random variables。Why is this only KY independence and not？Fully independent。

If you pick a random H like this。And you write down H of 0， H of 1， et cetera。

 why are these not fully independent random variables？嗯。Yeah， if you pick any K。

 the next one is determined again by polynomial interpolation。Okay。

Okay good so that's all I want to say about Q as independence。

So let me now start talking a little about the dictionary problem。So。dictionary problem。Oh。

 and I I meant to say this at the beginning of class。 But Pet1 is up。 It's been up since Friday。

 and it's due。Monday at 11，59 PM。 So yeah， I've had bad experiences with Pets to do in the morning and then people don't sleep so。

Dicary problem。I think I mentioned this when we were。Looking at venom de Boaz last week。

And I just stated that there's a solution， I didn't say how you do it。嗯。

So this is a data structural problem。So there is update。There are two operations update。呃。KV。

Associates。Let's say K， key K。With value V。And imagine that， you know。

 these are both in your universe， K and V are。In your universe。And then there's query。Return。X。

Return V。Associated。With K。Return the value that's associated with this key。2。Pretty okay。

Or if there is nothing associated with it， you report， oh there's nothing associated with it。And。

I covered this in 124。I'm not going to I'm going I'll say it again。

 I'm not going to go through the analysis again。If you really， if you want to read more details。

I'll augment the notes to include。Links to what you can read。

So how can you solve the dictionary problem， Let's say， you know。

 there's the dynamic and there's the static dictionary problem。 So dynamic dictionary， let's say。

You can do hash。Hash tables with chaining。And the basic idea there is you have。Your N items。嗯。Well。

 actually， let me not write it like that。So。N here， as I said， so we have an array。

Let me call this array A。That's of size M。And each element of the array is actually a pointer to a linked list。

I would say a wub linked list。And each element in this linked list is a key and a value。

And what you do。Is when you see okay， so when you do an update。Okay。OhAnd you pick， you also pick。呃H。

From this family。呃。From。A two wise family。Okay。And。K maps。To H of k。

So the basic idea is you initiate this array A。嗯。So， initiate this array A of size M -1。 I。

 all the linked lists are just empty。 So these are all null pointers。And when you see a key K。

You hash it using H。 H is drawn in the beginning at random from a two Eye family。You hash it then。嗯。

You look through the linked list。To see if K appears in that linked list。If it does。

Then you change its value。 So let's say that this is your K。 you just change its value。

 If it's not here， then you append it to the end of the linked list。With its new value。

And a query is similar， so if someone queries K， you hash K， you look in that linked list。And。

You look to see where Kmp is， and then you got to put the associated value。Okay。

So what's the running time of an update or of a query？I mean， don't tell me。

 don't tell me in terms of。呃。Don't give me the final answer， but just you know。

 say something sort of。What's that word？When you say something vacuously true。

 what's that called again？Yeah， yeah。 tell me， you know， something like that。 Very good。

So what's the running time of an operation？对呀。Yeah， it's the length of the link list that you map to。

Which is a random variable。😡，Because H is random。Okay， so。Run time of an operation。Is a length。

A linked list。At H ofK。And can show。The expectation over H of the length。Of this list。At HK。

It is a constant。Okay， so this gets expected constant time operations。If， of course， if。

Let's say M is at least n。I mean， has to be something for this to be true。

 you can't just have like good。An array of size one and everyone's in the same linked list。Okay。

 so Ill put， I'm not going to do the analysis， but I'll put links to things。And。Also。

 I'll give a link to perfect hasing。嗯。I'll give a link。But now I want to do linear probing。Okay。

 so this is called hashing with chain。That's one way to do dynamic dictionary。

But there's a way that's very popular。Which is called linear probing。Okay。

 and the reason it's popular is because it's very cash friendly， so I'll tell you the scheme。

So in terms of， you're not going to beat O of one time， so that's not how it's better。

This is better and real machines。Because of prefeting， I guess， are people familiar with prefeting？

Okay， so pre， you know， just。I'm not an expert in this， but from what I do know。Prefeing is the。

 the following。Architectural trick。So。You know， in your computer， there's memory， there's cache。

 there's disk， et cetera。And。Whenever。Whenever there's a cache miss and your system has to go and fetch that from memory and put it in cache or fetch something from disk and put it in memory。

It also tries to grab things that it thinks that you probably will also look at next。Okay， and。

One good guess at what you look at what you will look at next is， you know。

 the next few elements in memory， like the next consecutive few elements in memory。

 because if you're looping over an array or something， you're gonna look at those next。

 So prefetching means like， you know， your machine will actually grab those things before you even look at them and then put them in cache for you。

 And then when you look at them， Oh， they're already in cache。 Now I don't have a cache miss。 Okay。

 so sequential accesses are very fast because of things like prefeting。Okay。In real architectures。

Sequential。Accesses。Are much faster。Implies linear probing is good， what's linear probing？

So linear probing， let me write that array A。 and I have a hash function H。

I'm not going to say what kind of family it's drawn from yet。 maps one to you into。

Mapps the universe into into the into elements of this array。The idea is as follows。You know。

 I'd like to just store。I'd like to distort the value of keyK in H of K。So let's say this is H ofK。

Id like to just store the value there。But， you know。

 the problem in which we had to solve with chain is that there can be collisions。

 Other people might also hash there。So what do I do in linear probing？If this is full。

Then I just keep walking。Until。Until it's empty。So I'll store。The key and the value there。

And that's linear probing。Okay。So first you hash it。

And then you keep walking sequentially until you find an empty spot and you put it there。

So I think linear probing was invented by。So。It was first suggested。By some folks in the 50s。嗯。

I don't know the actual。Jnal or anything， but Samuel Lad。And。And what 50？54， right。O。Right。

 but this was。Thats a while ago。This was。they didn't improve anything about it。

 they just suggested it has something to do。And it was analyzed。First， analyzed。By Don Canth。In 1963。

Assuming。H is totally random。So script H is the family of all functions。

 its the same thing as saying that is totally random。In fact， he showed that if you choose M。

If you choose M to be something like1 plus epsilon times n。Then he showed that。The expectation。

 the expected， you know， time。Per operation。Is like one of rhsson squared。Okay。Oh。

 and then let me say more。One more reference。嗯。So。There's a big breakthrough， I guess in '07。

 but the journal version was in '09。呃。Said that。H being just five y's independent。Implies。

Expected time。Is constant。We're here like M is at least some constant times n。And one more reference。

Parocu。And Thor。In 2010。So they wrote a lot of papers together， so let me say ICalP 2010。

4 wise independence。Doesn't guarantee。Oh， one time。

So they constructed a family script H a four a fourY independent family。

Such that if you did linear probing where your hash function was drawn from that4 Y family。

 then your expected time would be about log n。Not constant。But with any five wise family。

 it's constant。So。Now， this doesn't mean that。嗯。Right， just be to be clear。

 it doesn't mean that four wise independence， any four wise family doesn't give。

 It doesn't mean that for all four wise families， you don't get constant。

 It means that there exists one4 wise family， which doesn't work， okay， so。In particular。

 I guess we'll probably see it in next lecture just because we're running out of time。

There is a family that's。Not for wise independent。 It's not even4 wise。

 It's only three wise independent， but it still works very well for linear probing because it has some other properties。

 so。嗯。Okay。So。Let me think about what I want to say， so I want to analyze linear probing。

It looks a little weird， like why would you Y is five？Come about。

The reason and I'll just say it in words before we do it。 The reason5 comes about， actually。Patroku。

 I asked when I saw this and I saw this， I asked Peraku why 5 wise。And he said， well。

 when you condition on one element where it lands， everything else is4wise。 So that was his answer。

Yeah， so but you you'll see what he meant very soon。In fact， there's。

 there's a slightly simpler proof， which I， I think I'll do first that shows that seven wise words。

And it's again， the same reason if you condition onwin， everything else is sixwises， okay。😀u。😊。

Okay so。So claim。If M is at least some constant times n。And H。Is7Ys independent？Then， you know。

 the expected。Let's say query time。Which is the same as update time because it means it's the same procedure basically is a constant。

Okay， and this is the same， you know， I still， I basically the way I'm gonna do this。

 it's I don't think it's actually in this paper。 They just show the five whys， but there was a。

 you know， I saw some lecture by， by one of these pays。Ross was pay and。

 you know he just showed he showed first the seven wise thing。 I think it's a good warmup。

Before you get into five wayss。Okay。So。As you can imagine from this picture。

It's all about these runs， right？What do I do？I hash k。

And then I run over a few entries and then I'm done。Okay。So if I。

Let me stop calling it K and let me start calling it X。Otherwise， I'll confuse myself later。

So I hash X。And then I keep going until there's empty spot I and I'm done。And。So the question is。

How many non empty spots do I have to touch before I find the empty one。And in fact。

 so the way we're going to prove this claim。Is。We're going to say， well， first。

 we're going to say that basically， this thing is the length of that run。

 the expected length of that run is going to be a constant， as you might imagine。Okay。And got so。

So lemma。Well before the lemma， let me give a definition。Definition。Given an interval。I。Of。

Cells in this array A。I'm going to define L of I。As being the number of items that hash to eye。

The size of the set。I such that。H of I is in L。Okay。And then， also， a definition。L L I is full。If。

L of I。Is at least the size of eye？So if we have some interval of length K。

We say it's full of at least K things hash there。No， question there， anything。Oh， I defined it。

 so this is this thing。By definition。LevI is。Oh， yeah， yeah yeah。Sorry， yeah。Yeah。

Not the function that。What little HR。So here little H is a function that maps the universe into0 up to M minus1。

Does that answer anything。Any other questions。Okay， so what was I going to say？Okay， good so lemma。

If you know， some。Query on x。Makes K probes。Then H of k H of x。Is in。Some full。Interval。Of length K。

Okay。proof。So。Let's say this。This is H of K。H of x。And it's。It's occupied。So if it's occupied。

 the person who's occupying it came from somewhere in the past。I mean。

 he might have come from here itself。 I mean， he might have hashed here himself or he hashed somewhere in the past and then had to walk forward。

But the point is， he walked from somewhere。And the fact that he walked there means all these things are taken。

😡，And then now H of x is going to walk forward a little bit and eventually go here。

This is H ofx's final destination。And so that must all have been full。

And what I'm telling you is that this thing here。This thing here has length。K， you probe K things。

Now， remember that， the definition of full interval is that。

All the items had to actually hash to the interval， not wind up in the interval， right。

 that's the difference。O人。But the point is。All these。All these locations are full。

And they were all originally hashed。To somewhere here。Or later， so you know。

 one of these windows is full。I mean， I just。I think that's the definition of hand waving。

 but I literally just I was like this。😊，Yeah。Not necessary that面도。Oh， I see what you mean。 Oh， yeah。

 yeah， you mean this， this could be way in the past。なと。Oh， I see what you mean。I'm sorry。

Our items are unique。No no， the keys are unique。The keys are unique。 That's true。 Whoa， actually。

 that's a very good point。 You're saying everybody。

 this could be way in the past and everybody hash there。So。That's not。I like that least Ka。 Oh yeah。

 yeah yeah。Sure。Yeah， I think that fix it。Now are you happy？Okay， sorry。啊，O。Okay。🤧。So， then。

The expected time。You know， it's an expected time。Let me say's a query。Thanks。Yeah。哎呀。有咩。大好き年で。どこさ。

Intervals could be wrap around too。Yeah， intervals also wrap around。 Yeah， that's a good question。嗯。

唔。The expected time to query X is。Say。By that lemma。Is most the expected。Number of full intervals。

Containing X。没人。Which is。呃。Which is equal to like the sum over k。

What's at most the sum from k goes from 1 to infinity。Of。So how many？And the sum overall intervals I。

intervaltervals I。Where I has。Lngth， exactly K。And H of K is an I。Of the probability。

That eye is full。啊。嗯。Well， K can't actually well， okay， sure this thing？I think they are equal。Okay。

 and how many intervals of length K are there that contain。That contain H of x。Theyre k of them。

So this is at most， now this is at most。K from 1 to infinity， there are K of them。 K times the max。

Over I。Of length K that H of x is an I。Of the probability that I is full。You still like troubled。

Yeah， cause。嗯。Are still trouble？Maybe maybe I should be troubled。I mean so。Right， so you know。

 what do you really need to show？Ultimately， we want this whole thing to be o of1。

So there's really kind of one thing I see that could help us here。

 which is to show that this thing here。Is let's say o of1 over k cubed。If this were1 over k cubed。

 this whole sum would be sum of k1 over k squared which converges。Which is a constant。Okay and。

And we're going to show that this is true using sixY independence。Okay。And I mean。

 the reason sixYs comes into play here is。Well， three is six over two。So。Yeah。So let's say here。

Is equal to 2 n where there are linear probing。Or some maybe I'll need to increase the two to something else。

But so tell me， what's the， you know， what's the expectation。 So I full means that。

K things map to this length K interval。But that's not really that likely。You know。

 how many things do we expect to map there？If M is2 n。Let's say， oh， I should say。 So what is N。

 N is like the number of。Different keys。That are active right now。That are associated with something。

Okay。So what's the expected number of people that land in this interval of length decay？Ca or two。

So we're saying that。You know， this guy。You know， is deviating from its expectation。

By a factor of two。So you could handle that， by the way， using turn off downs。 Remember。

 we proved turn offdowns that were beginning the class。This is exactly the setup of turn off bounds。

 You could say， you could set， you could define your random variables from turn off as X I being one。

If item I let mapped in that interval and zero otherwise。

 and then the sum of the X is exactly how many people map to the interval。And then you want to know。

 is this much larger than its expectation， And there's some decay we proved using the turn。

 and that was the turn off bound。Yeah。経済？Oh， right。

Let me say it's camera as independent and furthermore， it's like almost uniform， which we could get。

I think also， you know， when people usually define care independence， they。

 they include the almost uniform in the definition， which maybe I should have。Okay。うんふん。So。

This thing we could handle using turn off fanss。So， you know， we need to。

So the probability basically that i is full。Is that most the probability that？L of I。

Minus the expectation of L of I。Is bigger than one half the expectation of Lbi。Something like that。

Or bigger than camera too。Well we which is one have expectation of， yeah。Yeah。

 people see what I'm saying here。That's careavver too。 So we had to deviate from our expectation by。

 oh， by the expectation itself。So the expectation is K over2 and we're K。

 so we deviated it from the expectation by K over2。And。Could use turn off。But needs independence。

So let me just write what we'll do next time and then we'll leave because we're out basically out of time so next time。

Were going to remember I told you how you start the proofture off。

You do some function on both sides of inequality and you do Markov。

So we're going to do the same thing there， so the probability。

That the expectation of L the probability L minus its expectation。Is bigger than the expectation。

Well， that's the same thing as if you raise both sides to the sixth power。Okay。

And that's at most by Markov。This thing here remembers K over2。That's care too。To the minus-6。

Times the expectation of。LI minus expectation of L。To the sixth。In archive。

And then you bound that and you get that this thing is going to be。Whenever K cubed， when you do it？

Okay， so next time， you know， I don't know if it's really worth。Doing this computation on the board。

Expanding something of the six power is just pointless。 You know， you can believe it。

 Maybe I'll just do one term of the expansion just to show you that it's meaningless。 But， you know。

 this idea of。Raising things to large powers and then doing Markov is called the moment method。

 and it's something you should be aware of。Okay， and， you know， it。

 it makes some intuitive sense why you would do it。 And the reason is。Kind of。So。

It all boils down to the expectation of this thing。 And if this random variable。

 if if the random variable is very concentrated about its mean。Then taking it to a large power。

Is not so bad， But if it's not very concentrated。 Like， if there's a big chance of it being far away。

 then taking it to a large power kills you， right， So this behaves well for concentrated random variables。

So if you think your thing is concentrated。You take a large moment， and then you compute it。

 and then you hope that it will show you， yes， I am concentrated。 So that's。

I don't know if that was too vague but。It's going to be aware of this moment method。 In fact。

 you can even improve the turn off bound。By the moment method， you just take。

This seeks to be something very large。But。Maybe that'll be an exercise I know， Okay。

 so that's what we did。