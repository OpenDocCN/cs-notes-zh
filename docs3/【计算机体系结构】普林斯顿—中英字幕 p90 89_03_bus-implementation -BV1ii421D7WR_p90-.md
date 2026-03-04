# 【计算机体系结构】普林斯顿—中英字幕 p90 89_03_bus-implementation -BV1ii421D7WR_p90-

Okay， so let's change gears here and start talking about implementation of。

Different types of coherence and cash coherence systems for multi processor systems。

 So the first thing we're going to start out with is small。Sysymmetric multi processorcess。 Now。

 why do I call these things symmetric multi processors。 Well， in a symmetric multi processorces。

 everything is the same distance away from memory。 So we have processors across the top here。

They have a shared。CPU memory bus here and memory sitting over here。

And these processors are all equallydist away from this memory。

And this shared memory bus here also goes and communicates with the I O bus。

 where you have things like disks。Graphics， controllers， networking。

 and any processor can do any I O， and any processor can communicate with memory and their。

 theirre symmetric。Now。Let's zoom in on what this bus looks like here。

 because it's going actually influence our design。 And I want to point out that buses are only one design that you could come up with for a multi processor system。

 You could also think about having。Point to point， interconnect。

So what I mean by that is one processor connect to another processor directly， but then。

A third processor connects to the first processor， but not， not， not vice versa。

 So you could have some sort of routing needed。 And this is what you'll see when we start to talk about large multi cores or large multi processorcesor systems。

 But for today， we're going constrain ourselves to thinking about。Small symmetric multi course。

 where all the processors。Are equally distant away from memory， and they sit on a shared bus。

 So let's take a look at what a shared bus looks like。So， here we have。

A diagram representing a multi drop memory bus。And let's start off by looking at all of the different signal types that you need in this multi。

 multi drop memory bus。And before we do that， let's describe what multid means。

 So multid just means that it's a shared medium。It's a shared wire that all of the processors。

 So here we have processoror 1， Proor 2 and main memory connect into this bus。So it's just a wire。

 And then you have taps coming off the wires。 And this is why we call it a multi drop bus。And。

When you go to look at this， theres some sort of positives and negatives of the multi drop bus。

 The positive here is that you don't have to route。

 if you wanted to have one processor communicate main memory or read main memory， it can just shout。

 saying， where is address dress 5。 And main memory can say， I have that。 And here is the data。😊。

But the downside to this is Proor 1 and Proster 2 can't go shout at the same time。

So as we start to add more processors， something like a shared multi droprop bus might become a problem。

 And we're going talk about this when we start to get to large multi processorces systems or large parallel systems at the end of this class。

But let's， for now， let's， let's focus on multi drop memory buses。

 And let's look at all the different wires you're gonna need here。

So we'll start off at the bottom here。 So in the bottom， we just have a clock。

And this is basically driven externally。 You don't need any Proster  one， Pro  two。

 or maybe memory is not going be driving this。 This is just something they all receive to keep everybody synchronized。

Now， we's start at the top here。Arbitration。What does arbitration mean， Well。

 arbitration means you need some way to determine who is allowed to shout or who is allowed to utilize the bus at a given time。

 So these sets of wires。Are going to be used to have。One of the three things， for instance。

 on this bus。Determine who is allowed to use the bus or shout on the bus at any given time。And。

How do we go about doing this， Well， its a couple different ways you can go build arbitration logic。

 One ways you could actually have what's known as a pull down bus。

 So let's say you have a wire per processor。Or wire per entity that wants to communicate on this bus。

 And when you want to go use it， you pull down a wire。 And there's some fixed priority。

 If you see that processor  one is pulling down that a wire。 And Pro 2 is also pulling it down。

 One always wins。 But usually that's not the best thing to do because then you might have you're required to basically have some sort of fixed priority。

 Instead， you could think about having a。Request and grant system。 So in the requesting grant system。

 let's say you have。A chip， which is an arbitrator。And you have， let's say， three entities on here。

That have three request signals， request 1。Request 2。And request three。

This arbitrator can try to do something like a round robin scheme or try to influence some sort of fairness。

And what would happen is at the beginning of a memory。Bus cycle。

 you'll actually have whoever needs to use the bus。 that cycle will all。Let's say assert their wire。

 assert their request wire。And then。Arbitrator will take it all in and take it all into consideration。

 It might have some state inside of here。 And then it will tell only one of the entities on this bus with a grant signal。

3 grant signals here。 it'll only insert one of these grant signals and make a decision and say。

 you know， processor  one wins or processor  two wins， depending on which wire here gets asserted。

 So multiple people can request， but only one wins。

So the first thing you're gonna want to do to try to use this bus is you actually try to。

Arbitrrate for the bus。 And there's a set of wires for that。Okay， what happens next， well。

On the control wires， you're gonna to say what you want to achieve。

So you might have a request that says， I'm going to do a read。On the bus。 Now。

 we haven't yet said where we want to do a read of， because if you look at this multi drop bus。

 we have wires for that。 We have an address bus。 So you first will say。

 I want to do a read and want to do a read of address 5， we'll say。

Then in a traditional multi drop bus。You'll actually wait， so you'll assert。The arbitration。

 the control， the address， and you'll be waiting around。 You'll say。

 I went to do a read of address 5。And then main memory will say， I have address 5。

 and it will assert onto the data bus here will say the data for address 5。

 And the processor  one can read in that data then。Now， what's。

 what's some downsides of doing something like this well。As you go to build this multi droprop bus。

 you're basically going to reserve the bus the entire time that you are doing one memory transaction。

And you need to hold the bus the whole time while you do the arbitration control。

 address data and wait for the day to come back。 And that could be a long time because main memory might take a long time to return data。

And， and this is， this is a problem。 So what did people think about doing， Well， they applied。

Ideas from processor design and said， maybe we can try to pipeline the bus。 So note。

 I'm gonna flip back and forth here for a second。 the title of the slide changes， but the content。

 the content doesn't。So this pipeline bus actually looks the same。So it has the same data。 But now。

 instead of arbitrating and winning the entire bus and holding the entire bus for a long period of time。

 Instead， we subdivide all these different categories and actually pipeline the access to them and use them only when they're needed。

So we can actually take a look at this as a picture here。 And we can see， for instance。

 on a pipeline bus， you might first， let's say processoror 1 is trying to do something。

 It'll assert processor 1 onto the arbitration lines。 And let's say it wins。

And then in the next cycle， it'll assert。That it wants to do a load。And then in the next cycle。

 it asserts。That the address。And then finally， let's say the main memory returns the data quickly here and returns the data。

Over here very quickly。Now。Why is this good， Well， because it's pipelined， the next cycle here。

 someone else can be arbitrated for the bus。The cycle。

 after the load or the control data signals are used here。

 someone else can be putting a different transaction on。Likewise， in the address here。

 the next cycle， someone can be putting something here and data can becoming the next cycle。

 So you can basically not have to hold all of the wires for the whole time of one memory transaction。

 But instead， you can pipeline those transactions。And this is just to give you some idea of how the physical implementation。

 the wiring of small symmetric multiprocessors work。 In reality， they're a little more complex。

 So something we're not going to talk about， but that you'll see people do when they go build these pipeline buses is they'll actually do whats called a split split phase transaction bus where instead of。

 let's say， waiting for the data to come back。For instance， in this example here。

 it's very possible that the data from main memory might take a couple cycles to come back。

Instead of just waiting there， which would slow down your pipeline。 if you have to stall。

 for instance。Instead of doing that， you can issue a request。 And then sometime in the future。

 the main memory might arbitrate for the bus again and then return the data。

 So that's why it's called a split phase transaction。

 So there's multiple phases to one transaction So the first phase might be request the data where you might have to use all of the portions of the bus。

 And then the response for the the data will be the main memory abitrating for the bus saying that it's going to do a data response and reasserting the address and then giving the data back。

 So you can see that that's a better way to use the bus because you don't have to hold the bus for a long period of time。

So one of the challenges this is that you still have everybody trying to scream on the bus at the same time。

 And if you were to take everyone in this room and try to scream all at the same time。

 we would not be able to understand what what each other is say。

 So that's why we need arbitration here is to if you will sort of pass around a token。

 So only one person can speak at a time。 But if you want to have multiple people speaking at a time。

 we'ret have to go look at more complex systems and we to talk about that into two lectures。



![](img/37b32669ca5a8b8c6700b8ea2f3d1a62_1.png)

![](img/37b32669ca5a8b8c6700b8ea2f3d1a62_2.png)