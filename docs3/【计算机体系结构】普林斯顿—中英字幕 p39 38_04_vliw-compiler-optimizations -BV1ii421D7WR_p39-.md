# 【计算机体系结构】普林斯顿—中英字幕 p39 38_04_vliw-compiler-optimizations -BV1ii421D7WR_p39-

![](img/15334243c7bceeb5a66254ed2e8e02dd_0.png)

Okay， so。Very long instruction words。Processors still want to have high performance。

And we took all this hardware that was in a out of our superscale。 we sort of threw it out。Well。

 somebody's got going to make up for it。And what makes up for it is a very， very。

 very smart compiler。So we put a lot of emphasis on the compiler in these sorts of architectures。

 and the compiler really has to do the scheduling。It has to do all of the。Depenency checking。It。

Probably has to avoid all the different data hazards。And this is just sort of just getting started。

We're going to talk mostly next lecture about all of the。

Different optimizations that compiler can do to try to approximate what a out ofvo superscaler can do。

But by doing it statically。So its a pretty cool trick。 If you take all that hardware。

 you put in the compiler， you run it once。😊，And then。Every time you go to execute the code。

 you don't have to go and rec calculateculate all the dependencies。Sounds good。Okay， so let's see。

How we execute some code here and what is the sort of performance aspects to executing loop code on a very long instruction word processor。

So， here we have。A very basic。Aray。诶。Increment， we're gonna take every element of this array。

 We're gonna increment it。By the value C。On our， we run into our compiler。

 And here's a sequential code sequence。 This has not been scheduled yet for V I Ws。

Or for our VLIW architecture over here。So we load some， we， we load the value。

 We increment our counters。 We actually do the floating point add。We store the value back。

 We increment the。Aray index。 And then we， we loop。Seems simple enough。

Let's see how this gets scheduled here。Well， because the architecture and because the compiler knows about the latencies here。

 let's say this load here has a few cycles of latency。So its can actually schedule this ad later。

And the ad， is a floating point ad。 This has a couple cycles of latency also。

 So it schedules the consumer。Of that result here， this F2 later。And yeah， I dont know。

 it can sprinkle in the array editions and the counter editions kind of somewhere free。

 It has lots of open slots。 But let's say it's scheduled at the same time as the load in the store。😊。

So this is pretty cool。 We are actually executing two wide parallelism here。😊。

And we didn't need all the extra overhead in order super Sc。Oh。

 and humans go to the branch somewhere。Okay， so first question here。

 how many floating point operations are we doing per cycle， Are we doing very well here。

 It looks looks pretty poor。We have one floating point operation here， just this ad。And we have 1，2。

3，4，5，6，7。E cycles， yeah。So we're having 018 or 0。125 floating floatingting point operations。

Per cycle？It's not that great。 we do have some perilism。 You know。

 we're excluding three instructions here。It's better than nothing， but we're。

 we're not really using the machine very well。 A ofor superscalear would probably try to take instructions that are below here。

 maybe intermix them， try to reorder a bunch of things and try to run faster。

So what's the technique to go faster well。One of the big， as I said。

 we have a lot of emphasis on compilers in this unit。

One of the things the compiler can do is it can actually unrollve a loop。So here we have our loop。

 we unroll it four times。And now we're going sort of take the loop overhead。

And we're going factor it out since it only happens1 every four times。 that sounds good。

You're try to do some more work here per each iteration in the loop。

But things get a little more complicated。 What happens here if N。

 big uppercase N here are terminating value。Is not a multiple of four。Well。

 we need to do something about that。We probably need to check sort of before we go to execute here。

 whether we're， we're doing okay or whether we're actually our multiple 4 conveniently and is big enough。

 We probably can run as a multiple4 for a long period of time。 And， and it's only the last iteration。

 And we have to clean up。 But we need to generate some cleanup code。

 And the compiler is responsible to do this。So these compiler optimizations do take some effort。Okay。

 so let's look at the scheduling now。Of our loop unrolled code。

We can do a bunch of loads up front here。So we've inter intermingled these loops。

 And what's kind of cool is we can actually pull out。😊。

The loads and sort of throw them to the top and the stores and push them to the bottom and then put all the ads sort of in the middle and maybe sprinkle the array updates somewhere else。

 And when we go to actually schedule that， we're gonna do something similar。

 We're gonna have the loads execute first。Execute the floating point ads。

 have the P point stores and have the result。But what you can notice here is we're actually starting to get some overlap。

Because we've unrolled， we can overlap this load and the first floating point。Addition。

Because we've effectively covered the latency of our functional units。

By putting other loop iterations during that time。 So if you look at this schedule versus the schedule。

Back here， we've just sort of taken these dead cycles。

 and we've put the other loop iterations in those dead cycles。In this loop unrolled case。

 we're incrementing these counters and the indexes。Not by 4 anymore。 We're incrementing by。

 however many times we've loop unrolled times the offset。 So we're incrementing it by 16 now。

Does that make sense？Because in， in。This code here。We were。Incrementing R2 by four。

Because that's the size of a single value is。4 by。 So we have to sort of move our rate index over by 4。

 But now， because we're batching up all this work together。🤧嗯。

We actually have to move the index by a bigger value。

 So we're moving it by four because we've unrolled four times times the size of the data value。

 which was 4。 So we're moving it by 16。AndAnd one of the nice things here， if you look。

 is in both the lows and the stores。We're using our。嗯。Register indirect addressing mode here。

To add in some offset。 So we're actually offsetting， let's say，12。Plus。

This base register of R1 to figure out where we're actually doing the load from。

But's sort of a convenient way that we don't have to compute a bunch of addresses。嗯。Okay。

 so going back here。We can see we're trying to overlap。Actual operations with other loop iterations。

Well， that's really cool。So we're starting to get some performance here。

 so let's look at the performance。So I'll ask the same question here。

 how many floating point operations per cycle。Well， hopefully， hopefully it's higher。1，2，3，4。

Divided by 1，2，3，4，5，6，7，8，9，10，11 cycles。Okay， so that's0。36 is a lot better than 0。125。

So this is good。Lup and rollinging is helping us。But is this。

 is this everything or could we do more in our compiler。

So these four compiler people came up with even a fancier idea。Which is called software Pilining。

So uses a term we've seen before， pipelining。But does it in software。So the idea here is that。

 instead of。Just。Having。1 loop。Unrolling the loop and then overlapping the iterations。

 we're actually going take multiple of these schedules and interleave them。

And try to fill some of these empty slots。So let's， let's look at this。

 We're gonna have the code unrolled four times。 This is the same piece of code we had in the previous slide。

And we're going to draw our schedule that we had before。

 So here's the schedule we had before in purple。Okay， that doesn't look so bad。

But now we're gonna schedule it with another iteration of the exact same。Four time unroll loop。

Sn here in greed。So， we've。Just overlap this with。This other。诶。Iteration loop。Well， are we done here？

Well， not quite， you still have some open slots here。So let's try to overlap。Even another iteration。

As shown here in red。Now， the fix up code that you need to have。To do this correctly。

 it gets more complex。Becauseuse all of a sudden now。

 you're basically overlapping multiple iterations。 But as long as you don't modify some value。

 as long as you don't do a store。Speculatively or a store。

 you're probably okay because otherwise you're just doing loads， doing extra loads， doing extra work。

 You're doing extra work， and you're filling slots。

Thinking that you're not gonna have anything go wrong or thinking that the index variable N。

 if you will， is multiple4 and large， and you're not at the end。So's。

 let's put some names to these things。So we call the beginning here。The run up。The prologue。

Here we actually have our sort of。Actual iteration。 And you can see that the sorry。

 this is in green that doesn't show up very well。 There are instructions here。 Theres ads。

It's pretty full。 We're actually doing a lot of work。On our VIW machine here。

And then the epilogue here is the， is when we're done。 This is when we're falling out。

 We're sort of at the the last loop iteration of the outer loop， if you will。So let's。

 let's do some math and look at the performance of this。Okay， so let's in question here。

 how many floating point operations。P cycle。Oh we go look over here， we have one， two， three， four。

And we have four cycles in our， in our tight loop case。That looks pretty good。That's cool。

We just got a bunch of performance。But we had to do a lot of compiler optimization to make this work。

 But we were able to use the perels in the machine。

And we're able to overlap three different iterations of this loop。

That we also did a software transform to unroll at four times。

So this is called software pipe planning。 And I have a nice picture here and sort of show what's going on visually。

So we're gonna have time。On the horizontal axis， and we'll have sort of activity of how many instructions are executing or something like that on the vertical axis。

 or shown here as performance。When you run multiple loop role iterations。You have。

Sort of some startup。 you have the actual， you ring the loop， and then you come down from that。

And that's， that's better than having a lot of startup and sort of come down with a very small luiteration portion here in the middle。

But when we go to look at software pipeline， we can overlap basically one iteration loops execution with。

Or one loop start or with。The luiteration of another。Loke。And we can actually execute。

Sort of our prologue。Exece multiple iterations， very tight。 And then have our epilogue here。Yeah， so。

Our software pipelineing， we're only paying the startup and wind down costs。

Once for the execution of a loop and not every iteration of the loop。So that's that's fun。 at school。

 We're getting performance。Only the world was dense loops， life would be easy。Alas。

 the world is not all loops。If we just had a processor， which just did。

Dense array calculations and all of our problems in the world were just dense array computations。

 Life would be really easy， but they're not。A lot of times， code has lots of branches。 It has。

 if then else clauses。And here， we sort graphically show something like a if then else。

 So we have some piece of code。 It makes a decision。

 either executes the code on the left or execute the code on the right。Based on。A niF statement。

So this is the， if true statement， and this is the else clause。And data dependent。Branches。

Are a problem， typically for very long instruction word processors。Now， why is that？嗯。Well。

 in an out of order processor。You can try to execute code sort of around the branches and move instructions above the branch and below the branch。

 But if youre doing static scheduling。When you hit this branch。

And let's say it's a hard to predict branch。You can't really do anything because you've packed a bunch of instructions next to each other。

 and they need to execute atomically。So something you can like sort of move code up and down across that branch。

The super scer can do that because it has this instruction window。 It has a bunch of techniques。

 a bunch of hardware to be able to do that。 But in our VA W processor， that's a problem。

So I wanted to introduce a compiler， an important compiler， nomenclature here。

Which is important for this class， it's called a basic block。So what is a basic block。

 A basic block is a piece of code， which has single entry in single exit。 So this is a basic block。

 It has。One entry and one exit。And why is。Single entry， important。 Well。

 if you can jump into the middle of this piece of code。

The compiler cannot necessarily reorder the instructions inside this block。

And if you have multiple exits， and say you exit here。

The compiler can push instructions below that exit point。But if you have a basic block。

 the compiler basically knows that these， this instruction sequence is going to execute effectively。

Effectively atomic， but not actually atomic。 I mean， you can。Have other things going on inside there。

 But from a compiler perspective， it can reorder the instructions around here to get better performance。

HO。So loops， loops are easy。 We can software pipeline。 We can unroll。Squaquirely code， if then else。

 spaghetti code， ball harder。So the compiler guys came with some fancy tricks。

To make VLIWs work better。And to take advantage of some of the code motion that a out of our superscaler does。

But in the compiler and not in dynamically in hardware。

And one of the more famous ways to do this is something called trace scheduling。

 which was John Ellis's。Who was one of Josh Fisher's students thesis work？

AndThis was in the Bulldog compiler out at Yale。So。What you do is you profile the code。

And you come up with the probabilities。That these branches go the one way or the other way。

So when I say profiling， this is not a something that hardware is doing at runtime。

 This is something that you do with the program。While you're sort of still back in the compiler stage。

You take the program。 The compiler goes and runs it on some input given a given input set and comes up with probabilities of which way things go。

 And then what you do is you come up， you take this。Profile information。And you come up with。

Some guess at what is the most probable one。And we're going to circle that here and say。

These darkened edges are the most probable sort of path through the squirly piece of code。

 given this is the entry point。Now， this doesn't mean。

That you can't have branches that sort of branch out of this。But if you do。

 you need to have some fix up code。Because what we're about to do is we're gonna take this entire sort of。

Big swath of code here。We're going remove all of the branches。

And we're gonna schedule for our VA W processor as one big monolithic。piece of chunk of coat。

And by doing this， we can move instructions。 Let's say， that are down here。

Which there's open slots to execute in the early portion of this code sequence。 We can move them up。

 And likewise， you can move things that use the result of long latency instructions up here and push it down across branches。

So our out of our superscaler does this with branch speculation。

But our compiler can do this on our VAW processor， using trace scheduling。But when we do this。

 we have to be careful because it' is always the possibility that while unlikely。

You can still branch the other way。So typically， the way this is done is you have some form of fix up code。

 If you branch away， you have to sort of fix up anything that was after the branch that made a committed change。

 if you will， to the the processor state， you sort of roll that back somehow。

 So we're basically in software doing the rollback case from our outer vote super scar。

So instead of taking the architecture register file and copying it to the physical register file on branch mispredict。

Instead， our compiler generates a code sequence which does that same operation。

If you were to branch away here。And we'll roll back only this。

 only the certain registers that need to be rolled back and only the memory state that needs to be rolled back。

 So that's pretty cool is that we can basically take a lot of the functionality that was done in our auto our supers and put it into software using trace scheduling。

😊。

![](img/15334243c7bceeb5a66254ed2e8e02dd_2.png)

![](img/15334243c7bceeb5a66254ed2e8e02dd_3.png)