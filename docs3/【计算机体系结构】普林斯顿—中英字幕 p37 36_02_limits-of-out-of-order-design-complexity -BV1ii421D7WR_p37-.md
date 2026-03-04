# 【计算机体系结构】普林斯顿—中英字幕 p37 36_02_limits-of-out-of-order-design-complexity -BV1ii421D7WR_p37-

So we're going to be continuing today， talking about。VLIW or very long instruction word processors。嗯。

This is a alternative way。To exploit perism。In a processor， But instead of doing scheduling。

Dynaically， as we've been talking about in out of order processors and supercals。

We're to look at ways to do it statically in the compiler and then architectures。

 which can exploit that。 But let's now start talking about。Very long instruction were in processors。

So we've been talking about these superscale processors， the superscale processors。

Have a fair amount of complexity in them， especially out of order processors。

Where does this complexity come from。And can we remove all that complexity？

So that's what were going to be talking about today。

So here I draw a picture where I have the issue with of a superscale processor。And。

We represent that as W。And then we have。The lifetime of an instruction。So， that's sort of。

Gives you a matrix of things in flight in the processor。 Now。

 these may sitting in your instruction queue。 We're not gonna to count if they actually。

 let's say get all the way to the reorder buffer because by the time they get all the way to the reorder buffer。

 they probably， depending on how you build your processor。

 you probably don't need to continually check those against the other instructions that are coming。

 You've already broadcast that back to either your reservation station or your instruction queue to issue few further instructions。

But if you think about the complexity here of what you're really doing when you try to go issue an instruction。

You're trying to take。These inf instructions。And you have to look up basically against them or in your instruction window。

 all of the instructions when they complete against basically all the other instructions。

 all the registers。 Now， we built some structures that make this。 so you don't have to complete。

All to all check。So example structures that we create to help out with this。 First of all。

 the scoreboard， instead of keeping track of where everything is， sort of our original design。

 where we had portions of or which registered destinations sort flowing down the pipe。

 And then we did all to all compare。Instead， we just keep track of the location and latency of the most recent right to a register。

 and it turns something from a all to all compare into an index lookup based on the register。

So that's a little bit nicer， but。If you think about what's happening in the issue queue。

 we're still doing a as a instruction retires。It's going to basically broadcast the registers that get completed against the instruction queue and try to wake up instructions and see which ones are ready to go。

And that roughly， as I said， scales， Scs like this。

 because you're gonna to be retiring multiple instructions per cycle。And， you know。

 let's say you have a bunch of stuff in the the instruction queue。

 You're gonna have to check against all of those。And this can get painful。 Let's。

 let's take a look at first， sort of the complexity of this for in order machine。

So internet machine is not so bad。L is kind of the pipeline length。You have your with。

 but you just basically have to have a scoreboard to figure this out。 And we said。

 that's an indexed based structure。Now， when you start to go out of order。You。

 you start to have this sort of complexity of all of the results that come back have to be broadcast against either if you have a distributed instruction queue。

 all the reservation stations or if you have a single instruction queue。

 you should check against all of the possible instructions to go issue。And what's interesting is。

One of the big challenges of building these structures is not actually quite what you'd think。It's。

 there's an interesting challenge that you have too many things that could wake up in one cycle。

So let's say you have a single instruction， or say all of the instructions in your instruction queue are waiting on Reg 5 to become valid。

All of a sudden，Instruction， some a， let's say write register 5ing。

 and it it enters the reorder buffer。 So gets the end of the pipe。 Well， now， all of a sudden。

 you have to wake up all these instructions and choose the。

Some instructions that are the width of your machine that can go issue。Also。

 you need to need to make sure that you can satisfy all of the different requirements in the machine of。

Functional unit mixes。 So if you have， you know， say2，2 ads， two multiplies in one loaded in store。

 you can just go pick randomly from there。 You need to pick exactly that mix。

So this becomes a big mess of combinational logic。 And this is why front ends of processors can actually。

 in out of order processors can start to get longer and longer。

 You get more and more stages in there to do this。 And as we talked about last time in like the penium 4。

 there's actually multiple stages out in front there， to be able to do this。 And unfortunately。

 you even have to pipeline that， which makes us even more challenging。So， roughly。

If you look at sort of the out of world control logic here， it's sort of。

Growing somewhere between the width squared to the width cubed。This is， this is not， not very good。

Sometimes there are a couple circuit level tricks that can help you。

 So if you go look at people who actually do full custom logic for designs of processors。

They'll make something that they call pickers。And what a picker is， is it's actually a。

 instead of using straight combination of logic to go compute what instructions is ready to go execute。

 you'll instead have much more analog circuit in there where you'll basically have some custom analog circuit there。

 which is almost like a cam or a content addressable memory， but it's not quite a cam。

 It's more of a。Circuit， which will choose。What instruction is ready to go。And it is， typically。

 you want to have some heuristic that is the oldest instruction。 This is to prevent deadlock。

 So you don't really want to issue arbitrarybitrarily instructions。 arbitrary instructions。

 you want to issue the oldest instruction because you want to make forward progress in the machine。

So what I'm trying to get at here is this is a lot of hardware complexity。

 It's growing as the width of the machine。 And some things actually make this even worse。 So here。

 have a little note here that as you increase the width of your machine。

 let's say you have you got a three wide machine and all of a sudden， you want to go。

 let's say a4 or five wide machine。Typically， you need also a larger instruction queue or instruction window to look across。

In order to find enough parallelism to keep the machine busy。So as you go wider。

 you also typically have to make the machine sort of deeper。

 or at least make your instruction queue deeper to find enough parallelism to feed your functional units。

That's not good。 So as this causes the， you know， these sort of blow up factors here。

 and you can build these things， but they' hard。So are there alternatives？Yes。😊，But's， before we。

 we move on to those alternatives， let's look at the sort of complexity of this in a real processor。

So here we have a die photo or die micrograph of the MIPS R 10000 processor。

This was used in workstations by SGI for many years。It's a。Real out of order supercalar。

And one of the interesting things is if you go look at how much area is dedicated just to control logic。

It's pretty substantial。So in this processor here， here's our actual data path。

 It's relatively modest。Cash， instruction cache， data cache。 Those are pretty big structures。

 You can see those。We have， you know， some other，' the data tags， instruction tags， T， O B。 you know。

 those are big big sort of things。 I that all this stuff here。Is quite large。

 Let's look at what's inside of here。We have sort of next instruction sorts of things。

 We have a free list for the， we had talked about this， right， We talked about the free list。

 for the which register is free， if you will， to reuse in your out of order processor。

We have a big thing and just does registry namer。The we have different queuees here。

 So this is a distributed instruction queue or a distributed reservation station processor。

 So there's one for just dress calculation instructions。

 inger instructions and floating point instructions。But what's interesting to see here is the。

 the percentage of this diet is actually doing compute。Let's say this integer data path。

 the floating point data path， the floating point multiplier is sort of pales in comparison to all the overhead。

So this is just sort of to get this idea across。Another problem with。

Out of our superss or super scholars in general is thinking about how do we express perism。

And I alluded to this in a previous lecture。But it's worth repeating。So let's。

 let's take a look at what happens for code， sequential codes on a out ofor super scar。

We start off here with some piece of C code。We put it into our fancy superscale compiler。嗯。

That generates some sort of data flow graph and probably we also control flow graph inside the compiler。

So it sort of instructions， there's dependencies between the different instructions。

And the compiler right now is trying to find independent operations。

Because it's going try to come up with a schedule。Unfortunately。

You have to come up with a sequential schedule。Because the instruction sets on sequential processors。

Require you to come with some order， even though it's very possible that there is no one。

Perfect order。It's also possible that， you know， you're sort of overconstraining the problem here。

 Why are we coming up with with some， some ordering when。We don't need to。But， you know， in our。

 in our sequential I A， we have to come up with that。We write out to disk somehow or， you know。

 save a file with this， this code。And then we have to go and actually try to execute it。

 And what's funny。Did I get chuckle out of this？Is the compiler new。What the dependencies were。

And then we have our superscalear processor here， which goes and takes apart the sequential code。

And tries to reorder the instructions。And tries to find perilism in the instruction sequence。

But the compiler knew that。 But we had like a breakdown here in the middle that we just weren't not able to express that between the compiler and the processor。

Compilr knew about the perilism。 compileilr knew about all the ordering and the requirements。

It had to come up with some sequential code sequence。Provides it to the processor。

 The processor takes those， those that sequential code secrets back apart。

 does out of order scheduling like we did on the exam in the midterm。And it's gonna， you know。

 we build a bunch of hardware here， which has high complexity。

 as we're talking about in the combination of logic， checking the dependencies。

And then it comes up with some schedule。This is done V our reservation stations or instruction queuees。

 and something is go to fire。 and come with some schedule。

 And it's gonna execute those instructions by preserving read after write dependencies。

 And hopefully， if our superscale processors fancy， we have some register neighbor。

 we can break some of the other dependencies。 Also the right after write and the right after read dependencies and come with some schedule。

 that's high performance。Now， there's no guarantee that this schedule is what the compiler would have done if it was smarter。

Or if it could somehow express perilism across this interface。But， you know， it does something。

what's funny about this。 iss a whole lot of power that's being wasted。

 It's a whole lot of effort that's being wasted in the processor。

 There's a lot of effort of the designers of the processor that is are effectively designing all these circuits to take apart the sequential code sequence and do something useful with it。

😊，So it's a lot of work being done there。Is there a better way？



![](img/8b69f7664ab80a66238ba72ef213bbaa_1.png)

![](img/8b69f7664ab80a66238ba72ef213bbaa_2.png)