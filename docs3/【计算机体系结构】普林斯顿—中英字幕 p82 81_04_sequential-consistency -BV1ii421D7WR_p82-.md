# 【计算机体系结构】普林斯顿—中英字幕 p82 81_04_sequential-consistency -BV1ii421D7WR_p82-

![](img/fe1263a67da19858d120cf4905860a71_0.png)

Okay， so let's introduce。A model of and introduce some semantics to describe。

Ordering of memory operations between different processors。

One of the most common ones that you're gonna to see is called sequential consistency by no means the only one out there。

 This is a very strong。Ordering。嗯。Compared to any of the processors you guys run on your computers today。

 this is extremely strong。 Nonene of your computers actually implement this strong and ordering。

But it's a good basis to think reason about and reason about parallel programs。

 So we're going to study sequential consistency。So up here we have。1，2，3，4， or5 processors。

 one big memory， still very basic model。We have not introduced any caches or anything crazy like that yet。

Because that makes all these things a little bit harder。Either cashs are out of order。

And what sequester consistency is， is。The idea that。

You take all of the instructions in all of the programs， executing on all the processors。

And you guarantee。That the execution sequence。That is seen。By all of the processors。Is some valid。

In order， interleaving of those instructions。Of the。Relative processors themselves at the beginning。

 So to give you an example。If you have processor one。And processor2。pressssor  one goes， one， two。

 three， four。And processoror2 goes。Excuse instruction 5，6，7，8。

You're guaranteed that some interleaving here is what happened in sequential consistency。So。

 let's say。1 and two happened， and then five happened， and then three happened， and then 6 happened。

 and then 7， and then 8， and then 4。That is a valid， sequential consistent order。Likewise。

 another one that is easier to reason1，2，3，4，5，6，7，8。

That's valid in sequential sequential consistency， likewise。I don't know。 we'll say。5ive，6。7，1，2，3，4。

8 is valid。Order what is not valid。Is going to be something like。5。1。I don't know。3。To。F， seven。

 eight。6 missing one，5， No，5，6。No six， okay。6ix in there。Because we've reordered。

One of the individual address sequences。2 and 3 should be ordered。So。This gives us some guarantees。

 So the， the basic idea is that。It's an arbitrary order preserving interleaving。

So each processor addresses are preserved in order。

But they can be interleaved between the different threads arbitrarily。Okay。

 I want that to sink in for a second， anyone have questions about what the model is。Or。

Why this is a good model。G， I'm going to ask a deep question here。Why is this？

A model that almost no one ever implements。So the reason no one actually does to try to do this is as all the things we had talked about we were talking about out of order processors。

 you want to try to reorder your loads in stores。For performance reasons。

And the second you try to introduce something like cash into your processor。

 this gets very hard because。Communication becomes a really bottleneck。

You might have one processor that did a， for instance， a store into its its cache。

 and not everyone has seen that value update。So unless you actually want to have one monolithic memory that you play all loads and stores against。

In some interleaved， yet in order relative to the processor order。

And everyone sees that exact ordering。You're not going to want to actually implement that。

 and that's very hard to do。Okay， so。Fun example here of sequential consistency。Let's look at。

Two threads， T1 and T2。And two variables， actually， we' have four variables here。X， Y。

 x prime and y prime。X prime and y prime the outputs here。So we do stores to those。

At the beginning of time。We are going to say x and y are initialized to0。And10。Respectively， as show。

Okay， let's， let's talk about what are valids sequential， consistent。Outcomes here。For。

X prime and y prime。Now， this is not actually easy to detect right off the get go。

 I I want to know which of these four。 okay， I think the answer is on your sheet， but go。

 don't go look at it。It's not actually easy to detect。Which one is sequentially consistent。

 Which ones not sequentially consistent。So let's， let's walk through a few innerleavings here。

To see what happens。Okay， so we're gonna have threadread1， threadread 2， X， Y。N X Y primes。Let's。Say。

 we execute。T1。Then T2。In time， so we're going to draw time this way。So， we do。

We do the store of one。We do the store word。Of 11。 and then we do a load word。Why。A store a word。

Why prime。Load word。X in a store word of x prime。We do this store here。At the beginning of time。

 as I said， x has 0。And why。Has 10。We do a store here， and this is going to be storing to X。One。

 so we're going to update the value x there。Then we're going to store 11 to y。Okay。

 so 11 gets loaded there in time。We do this load。 nothing， no， nothing changes。

We do a store here to Y prime， and we look at what we got when we did this load。Of why， we loaded 11。

And we're going to store。11 to y pride at this point。Then we do a load of X， which has one in it now。

And we do a store to x prime。It's going to have one， so to sum up， we have 11 and one。Okay。

 so that's this one。That's a valid output。And what's interesting to see here is。

Even with this strict memory model。We're going to end up with different possible outcomes。

 There's not only one possible outcome。 There's actually multiple possible valid outcomes here。Okay。

 so let's。Look at another。Let's use the， the same columns at the top here。 And let's say we have。

These two splits so that the first store happens here and the second store from T1 happens there。

Still sequentially consistent because they're being ordered inside of the respective threads。

And there's a global ordering that everyone sees。Okay， so let's， let's go through that one。 So we do。

Store word。Of one。Then。We execute in thread2。Load word of our 1， why。Sttorward of R 1， Y prime。Okay。

 so let's go to the store here。 The store is going to， well， actually with fish writing here first。

Load word of our2。From。X。Store word R 2 X prime。 And then finally， we。We finish off here。

 writing the store word of one。To x。Okay。Oops， I did thats wrong yep。That's what we're going to do。

Storeward is going to happen here， first。And remember， we started out with 0 and 10 and 0 in x and y。

 So the store word of one is going to happen and it's going to update x to be 1。We do this load。

 and it's going to get 10 now。And we store 10 into Y prime。We do a load word here。Of x。

And we're basically going to store that back into x prime。 So what was x。

 We look back in this column。 Most up value was1。 Okay， so we come over here and we say that's one。

 And then finally， we do a store word of 11 into y。Okay。Or to why。Should do。11 into y。

 But what's the output here？Well， the output is1。And 10 in this value。The store。Didn't do anything。

I mean， it updated the value of y。 but it did in effect。Y prime or x prime in any way shape perform。

Okay， so that ends up being。1 in 10 is valid， sequentially consistent。Output。

Let's try a non sequentially consistent。Execution order。And see what happens。Let's say。

 which is a good one to execute。There's a couple different ways to get this。 Let's execute。

This instruction here first。So the stored to why。And we're going to reorder that with the store to X。

And we're going to execute thread two in between those two operations。So。We use store word of 11。Tai。

So we out of， let's say T1 is executing out of the border processor here， for instance。

Then we're going to execute all of thread 2。And well， let's allute all thread2 in order。

And then finally， we're going to come back on thread one here and do the store。Of let's say， one。

To x。Okay， so x and Y start out with 0 and 11 Er0 and 10， rather。Store of a lemon to why。 Okay。

 that's going update。This to be 11。We're going to load y now。So we're going to load this 11 into R 1。

Then we're going to store out to Y prime 11。Then we're gonna to load， let's say。X here。 Well。

 x is just the initial values。 So we're going to get 0 into R2。

 Then we're going to store out 0 into x prime。There。And then finally， here。

 we're going to do a store of1 tox。So what's our output well。Our output is0。And 11。And。

But we had a non sequentialequly consistent。 This is a non sequentialequly consistent output here。

 So there's no way we can work through all the different possible combinations。

 But the only way you're possibly going to get a0 for。

X prime and 11 for y prime is if you execute non sequentially consistent。Execution sequence。

 And this was a。Because we flipped the ordering。Of these two instructions。That made this not。

Sequentialally consistent。So we have a big X over it。

We could work through all the other possible combinations here。

 but there's actually another interestingly enough。

 there's actually another way another interleaving that gets you the same non sequentialequently consistent output from a different sequentially consistent ordering of these instructions or a different non- sequentialequly consistent ordering of the instructions。

So that can't be true。Okay， so。What this is really trying to say is that in。

Our processors we looked at up to this point。We've had。Some arcs。And。

An example of an arc here is that if you。To a load into R1。

And then use the value of R one to do the store。 Sorry， these should be。Order flipped for MIps。

Compatibility。YeahI flipped in there I missed here， okay。For this store here to happen。

 it needs to wait for the value of R 1。So it's just simple read after write dependence。Likewise。

 here， you have a read after your write dependence。And it's a question of consistency。

You could have other dependencies。 So， for instance。

 if you do a load in a store and they's the same address， that needs to be an order between those。

 which we've already talked about in this class。What we've not talked about。

Is additional sequential consistency requirements。 So if you want to have additional sequential consistency requirements。

What it looks like is。Every memory operation is dependent。On the prior。

Memory operations in its own threat。So we're going to draw that as this red arc here。

And you can sort of see it here。 But also， this is dependent on this。 And this is dependent on that。

 that's been on that。 But sort of through transitivity， they don't draw the arcs。

So something to think about。Okay， so we got a question that comes up here。

 I think we already asked this question， but。Does a system of caches and underwater processors。

Provide a sequentially consistent view of memory。Answers probably not。It's pretty hard to do。

 You could potentially try to build a processor which is out of order and， and do this。

 But we talked about。Breaking。And reordering all of these instructions in and out of order processor。

So we're going to try to think about。What is the t model。

If you cannot go for full sequential consistency。You're asking。

 is it the job of the compiler to guarantee this ordering？Okay。

 so what we're actually talking about here is the hardware。

Breaking the ordering and just reordering things randomly that the compiler could possibly never even try to control。

That's the， the programmer is at fault there。 The programmer should not be assuming that。

 The programmer assume assumes some， basically， programmers try to assume something like sequential consistency。

And what we're saying is that none of the hardware out there implements sequential consistency。

 So the programmer。Can't assume that。 It was a bad assumption on the programmer's perspective。

So the compiler， for instance。The reason why the programmer assumes that is because it's kind of the rational thing to do。

 It's like the， the reasonable， rational thing to do。

 But it's really hard to go implement something fast under those constraints。

 So instead what people do is they try to come up with something weaker than that。

 which still gives the programmer some semblance of programmemability。

 And that's what we're gonna be talking about the rest of today's lecture in next lecture。 is what。

 what are those semblances of rationality， we can give the programmer。But this is one program。

 and this is another program。 Or this is one thread。 And this is another thread in the same program。

But the compiler cannot guarantee this ordering because the out of order processor will just move things around disregard to the compiler。

 We already talked about the。Out of our processors。

 moving loads past stores and stores past loads in the hardware。So。

And what we're saying here is if you want to actually implement full sequential consistency。

All those optimizations that the hardware and out of order processors want to do are invalid。

We don't want to really do that。嗯。Okay， so that's sequential consistency。



![](img/fe1263a67da19858d120cf4905860a71_2.png)

![](img/fe1263a67da19858d120cf4905860a71_3.png)