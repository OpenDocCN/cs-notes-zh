# 【计算机体系结构】普林斯顿—中英字幕 p26 25_05_introduction-to-out-of-order-processors -BV1ii421D7WR_p26-

![](img/a082a143029494fba14a073267706ae0_0.png)

Okay， so now， now we get into the fun stuff out of order processors。Up to this point。

 we've been doing simple in order stuff。 We've been hinting it out of order。

 But now we're gonna start looking at。Truly out of order machines。

And we're gonna introduce a bunch of new structures that you should not have learned about up to this point。

 You may have briefly talked about a scoreboard， but we're going start talking about a bunch of other structures。

Okay， so， so let's talk about different portions of a pipeline that can be in order versus out of order。

The front end。 So what do we mean at the front end。 The front end is instruction。

 fetch and probably decode。This is pretty hard to do out of order。Because you w to know， I mean。

 unless youve actually sort of can predict the future， it's pretty hard to know。

 So most machines we gonna to be looking at have the front end being in order。

 So I O here means in order。 O，0，0 means out of order。Issue。

So this is the stage in the pipe that actually says。

All the operas already ready go start executing the instruction。Well， there some。

 some things that can be in order。But you could probably even get more performance if you try to do that out of order。

So probably not today。 But next lecture， we're actually gonna talk about how to have the issue be out of order。

Right back。So， this is。Writing to something that looks like a register file。

But not necessarily having hit the commit points of the processor。

So this means that things are no longer in flight in the bypass network。

 It's been committed to a register file。 I won't call it the register file， just yet。Well。

 you can do that in order of order excuse me you can do that in order out of order。

Different choices there。And then， finally， commit。So this is saying， yes。

 I actually want these instructions to actually commit。 And I'm basically， after that point。

 you're not able to roll back the machine state to a previous state。

 And we're to look at machines where that's both in order and out of order。

This is sort of a gentle introduction to out of order execution。

 And we're gonna be building some different architectures。

 And this name here just is sort of a naming of5 architectures。

 we're gonna look at as an introduction to out of order。 So I 4 is in in in。 So in in。

 in order in order， in order in order， I 2，02 is。In order， in order， out of order of out of order。

 into out of order in order is in order， in order out of order。 It just。

 it' the number just means how many stages in a row are。The same as the letter before it。Okay。

 so I want to briefly touch on some nomenclature over here。

And you shouldn't know what these things are yet unless you went and read Shen Lapati。

 which I highly recommend scoreboard。This is a structure where we keep information about what instruction is ready to execute。

Reorder buffer sometimes gets merged into a lot of different meanings。 But typically。

 when we execute instructions out of order， this is a place where we can go and actually reorder them to commit them in order。

And we resolve all the dependencies。 so we don't actually commit out of order。Store buffer。

This is something where we'll actually。Hold off storing the memory until the commit point。

 because we don't want to write to memory too early。

Becauseuse that would be bad because then that would effectively be committing。 So yeah。

 this is what important thing to remember about commit points is if you commit too early。

What is an important notion of a commit here。 Well， it's any state that you can't roll back。

 So if you do a store a main main memory， that's commit。 that's really hard to roll back。

 unless you somehow can keep all that state of what was in that memory location before that。

 But people typically don't do that。 Instead， you'll actually sort of have a buffer。

 which keeps track of all the stories you're trying to do。

 And every once in a while or when you actually do a commit of the instruction。 at that point。

 and only that point do you store a main memory。And finally， we'll be talking about the issue queue。

 which is a， if you are issuing。Out of order， this is a structure which allows you to determine when it's safe to go and issue instruction or not。

And this is， what's important about this is， is it keeps all of the dependencies the read after write。

 right after write， write after read dependencies in check。 That's what that structure is doing。

 So we're gonna look at some of these structures today。Okay， so a motivational code sequence here。

And a motivation for out of order execution。Here's， here's a simple code sequence。 And let's。

 let's take a look at some of the read after write dependencies for this code sequence。

Here we have a right to register one。And a read of Reg one。So that is a a dependency there。So。

 instruction 0。Has。Instruction 2 is a dependence。 So we'll draw a nice arc there。

Let's see what else happens here。 Reg In 2 writes to register 5， and that gets read in In 3。

 So that's a dependency arc there。Okay， interesting enough here。Instruction one。Isn't dependent on。

Instruction 0 and In 2 and instruction 3 are not dependent on that。So。

ThatWe can just put in a separate little bucket here。嗯。Instruction 4 here。 Let's take a look。

 Register 12， Reg 11。Ah， it reads Reg 11。So， it's dependent。On instruction 1。嗯。

5 is dependent on the output here 12， so it gets put。After  four and likewise，6 reads Reg 12。

 So it is dependent。So we have to start to think about， if we have an out of order processor。

 we can choose the order of this instruction sequence in that instruction sequence。

 And if we have a multi issue or a superscalear out of order processor。

 we can even think about how to execute these completely independently at the same time。

 and we can get performance from this。Because we can find perilism。

Inside of a sequential execution stream。So one， one important thing here to realize is today。

 we're gonna be talking about how to。Dynaically， in hardware， schedule。This and this。

 at the same time。 and we're gonna using this is a motivating example in the V I W or the very long instruction word lectures。

 We're gonna be talking about some software techniques that can determine when to execute this and this at the same time。

 and architectures， which can take advantage of that where these software has determined that these two things are completely independent。

Okay， so an important thing to realize here is that。Why does this， Why do these even happen。

 Why do we end up with sort of nondependent instruction sequences in a program。

This is like a philosophical question。Should this even。why is this possible？So what， what do。

In order， instruction semantics or excuse sequential instruction semantics force you to do to instructions。

For you to come up with an order。You need to come up with some order。

 I need to write an paper in some linear order or store in my memory on my computer system in some order。

 An important point here is that in。The instruction set architecture of a sequential computer。

By definition， the instructions need to be serialized。This is a limiter。

 This is a problem in sequential machines。You need to come with some order。

So there is no way to express。That this and this can execute at the same time。

In a sequential in order machine。Or sequential machine， rather。Unless you do it something like this。

 you need become of some order like this， this is expressing the perilism， but it's hard。

 the hard us to go and figure out where that perism is now。

You could think of an alternative instruction set， which is not sequential， but instead is a graph。

Of different dependencies like this。 And people have built those sorts of machines。

 They're not very common。 They're typically called data flow machines。 And we。

 if we have time for it， we'll have one lecture about that at the end of the term。

So there are machines that allow you to express。This and this are not dependent on each other。

 And maybe sometime in the future， they do become dependent based on some branch or something like that。

So you can， you can think about that。 But in a， in a sequential processor。

 you need to quote with some ordering。 And this is a limiter for these machines。 So effectively。

 let's say the compiler， the compiler optimizations。

Knows that this and this can execute the same time。 By definition， if it can generate this code。

 it knows those two things can execute the same time。 Unfortunately， has no way to express it。

And that's a bummer。Very long instruction word machines。

 which we'll be talking about a little bit in the future， allow you some ability to say。

 I want to execute。 Let's say this and this at the same time， but it's very limiting。

Data flow machines allow you to do much more complex sort of graphs of instructions and say。

 this is depend this instructions is depend on this instruction。 And that's all I really need to。

 to say。 And so effectively， sequential machines have over constrained our designs。Okay。

 so let's start evaluating our first。Out of order in order machine。So I  for。

 this is actually an in order machine， but we're going to be analyzing it as a motivator and then sort of a slippery slope。

 if you will， into true out of order machines。😊，So here we have fetch decode。

 execute memory right back。 same five stage pipe。 I mean name things a little bit easy to make it easier here。

 This actually follows a nomenclature that's in your labs where the execute stage has an X and the decocode stage。

 the。😊，The is not I D， but instead D， but。This should all look relatively similar。

 I took out all the sort of exnes bypassing and other stuff in this pipeline。 So it's a sort of。

Carracature of， of， of a real pipeline。Okay， so let's say， you know， we want to do supercals here。

Let's say we want to start adding multiple pipelines to this processor。

So we're gonna take the same processor pipeline。 and we're gonna split it off and have two pipelines here。

 We're gonna have a memory pipe and an execution pipe。 This looks similar to our A And B super sc。

 But for today， let's focus on a in order， in order。😊，In order， in order machine。

Where these two pipes cannot have。呃。Different instructions in the same stage at the same time。

 So we're gonna to look at a。Single fetch。嗯。Processor here or a non a single issue processor。

 if you will。But as a motivator， we'll see why we're doing this as we build up。

 It's a more complex out of order things。 Most of these things hold， actually。

 for the multi issue variance。 But your head will hurt a little bit less。

 if you think about the in order variant or the in order single issue variance first。Okay， as I said。

 yeah， things get a little more complicated。s let's take that same pipe that we had from before。

And add in a four stage multiplier。So now we have an execute stage。A single execute stage。

 which actually has some work in it。 So this has A L U inside of it。The memory， let's say。

 has two stages。 This does the address computation。 This is the actual memory access。

 And then here we have multiply， which takess us a long time。 It's pretty common。 Multiies is a big。

 complicated beast。So its four stages of multiply。 And then out over here， we have the right back。

Okay， so that's， this gets us， this gets us thinking。 And we want to start to。

 to think what these things。Look like。On the inside。So the first question is。Do we want to bypass？

This pipeline。And how much pipelineing。Or how much bypassing do we need？E order pipe。

3 pipes or three functional units。 we'll call it。1，2，3。But。We probably still need to bypass。

Can we bypass out of right here？Out of。Why 1， does that make any sense。

So the multi is not done till here。So it makes no sense to bypass out of there。

Do we need a bypass out of here？I would hear。Here。Okay， a lot of bypass locations。So。This starts to。

 you can see the bypass exploding very quickly in this sort of pipeline。And， you know。That's。

 that's pretty， pretty， pretty much to be expected。 if you don't bypass。

And you have to wait for everything I'd say to get back to here。 your。

 your clocks per instruction of your machine goes off。

 and we sort of go back to that simpler machine we had seen in earlier classes where you have to wait for instructions to go all the way the end the pipe。

 And that's a bummer。Okay。So that's， that's what we just said。

 I did want to introduce this term functional unit。So， functional unit。Means。1 execution pipeline。

 So this is a function。 This is a multily functional unit。 This is the memory functional unit。

This is the execute function unit。Okay， so now we're gonna start introducing some extra structures and start talking about some extra structures。

 which will make our lives easier when we start to have multiple pipelines and complicated things are happening。

The first thing I want to introduce here is the architectural register file。Or A RF， for short。

So the architectural register file is where we keep。

The canonical state of the machine that has been committed。Hence。

 it's called architectural register file。 If you see me say。

Register file that may or may not be an architectural register file。 It may have inf values。

 But the architectural register file is the committed state in the machine。

So we draw that sort of at the end of the pipe here。

 because that's where rights happen to this register the architectural register file。

 as shown here by this W in the nice time or the nice pipeline diagram。 we have W。

And we try to read it。At the issue stage of the pipe or the register fetch stage of the pipe。

I did want to say that when we went to go do this， we added an extra stage here。

 So we went to a six stage pipe because we're assuming that we bypass everything。

 and we want to have a little bit extra time。 And we'll see for some more of the complex pipes。

 we'll start to put stuff in this decocode stage before right now。Decode does decode issue stage。

 does some instruction steering to which functional unit and not a whole lot more。

So that's what's in our architectural register file。 We read it here。 we write it there。

That makes sense。We may have to bypass some inf values around。

But those are not in our architectural register file。 Those have not been committed。

 Those are just inf， speculative values。SB， what's SB here。It's the scoreboard。So。

What does a scoreboard do， So we're gonna show some pictures of scoreboards。 But for right now。

What our store scoreboard is going to allow us to do is it's basically to be convenient side structure where we're gonna keep track of where。

Different values are in flight， in these different pipelines。All of this data。

 if you go back to our earlier pipelines， was there。

 We had sort of the instruction registers that went down the pipe here， which in the control。

 which kept track of what was in each stage。The scoreboard。

 is a convenient place to put all that information and centralize it all。

 So when you go to build a pipeline like this， you know。

 you don't want to have have to pick off of random locations in the pipe。

 It's easier just to sort of memorize that data in one location in the pipe in the。

 in the scoreboard。And when we start to go out of order。

 we're actually going to store some information in the scoreboard。

 which gets very hard to pick out of other locations。The scoreboard。Read and write and write What。

 what happens here。 Well， we read it to figure out。What？Where。

 where we go get the bypass information from。 So in this， we're not gonna use that calculation。

 We use the before， but we're gonna read it to figure out where the bypass information is coming from。

 And we're gonna write it when we actually。Issue the instruction。 So we actually issue instruction。

 We have to update some information in there。And then。

As the instruction goes down to the end of the pipe， If the instruction actually commits。

 we also need to do something in our scoreboard。If the instruction doesn't commit or takes an exception。

 we also will have to do something at the end of the pipe。 Well have to clean up the scoreboard。

So let's look， let's look at a scoreboard。 Here's our basic scoreboard。This is is for a。

Long multi pipe。 The pipe we just saw。And we're going keep track per real register。

 R 0 in MIps is a dead register。 So we're not actually gonna a register which has no dependencies going through。

 So we're not really going to talk about that。So， P。So we have one bit in here。

 which says if theres a right。Pending to that register。F for functional unit。

Keeps track of which of the three functional units we should be going to pick off the value from。

 So this is important when we go to do the bypass calculation， what's going on。And then。

 we're gonna to have。A shift register for each register， if you will。

 where we're going to inject a bit。And every cycle we're in to clock it forward。

And this is going to tell us where to pick off。The value。 So this tells us where。

Which pipeline to look at out of 3 and the data available tells us in the other dimension what stage in the pipe to go pick off from。

 So if you go look at what functional unit you are and cross it with this information。

 you should go figure out。Where to go do a bypass from。Okay， so every cycle。Logically。

 you can think of these bits shifting to the right。So it means the data， if is a one here。

 that means the data for register one is going be valuable in four cycles。In the。Somewhere。

Probably the architectural register file。 If you implement this relatively simply。

Let's the other things I want to say about this。Maybe we covered us all。 Yeah， so you。

 you need to use。The functional unit and the data available fields to figure out when to bypass and where to bypass from。

And then。If， if the， the pending bit is just a0， that means go look in the architectural register file。

 do not go pick it off for the bypass network。Okay， now we get to into a fun example。

 buyer motivating example that we saw beginning a class。😊。

So here we have that same instruction sequence we saw at the beginning class。As we know。

You can try to execute some of those things either at the same time or out of order。

 But for right now， we have an in order in order， in order， in order machine。

But let's look at what the scoreboard has to say about this。So on the， on the bottom of this graph。

 we this chart， we actually show the scoreboard。And red。Deotes。That。The value is ready。

So let's take a look at something here。 So in cycle 3。We start executing。Instructions 0。

 instruction 0。Is it multiply？So what happens？Is。It was in sorry， so I want to actually explain this。

 here's cycles。D means what's in the decode stage of the pipe。

 what instruction numbers in the decode stage of the pipe。

 I is what's in the issue stage of the pipe。So0 on cycles instruction 0。

 the multiply enters the decode stage， then goes to the issue stage。

 And then it moves to the execute units。 So it actually gets put into our scoreboard。

And what happens is it gets put in for。Register one。Into its scoreboard， just for register  one。

 And that just marches down the pipe every cycle。 So every cycle， it's going to move to the right。

And now， if you look at the。Pipeline。If you look at the functional unit and you know。

 it's a multiply。And you look at。Where it is in the pipe， you can say， oh。

 this is when the value actually becomes ready。So we now know exactly where in the pipe。And when。

 which， which functional unit and when that value is ready。

By looking at the functional unit and the bits in the scoreboard。If we look at something。

 let's say next instruction here is an ad。Instruction 1。It moves here。

 and then it just goes down the pipe， and it's ready basically the whole time。

We don't have to wait for。This value become great because the execute instruction。

 you can basically bypass out of the execute unit， and it's almost always ready。

That's why it's read the whole way down。And you can sort of see here that register  one。This is。

 this is when that scoreboard entry is valid。 And this is when the Reg 11 scoreboard entry is valid in time。

Okay， so let's look at。Our first real。Read after write dependence。So here we have a multiply。

 which is dependent on R1。As you can see， that instruction is going to sit in the issue stage until。

Why 3 happens then that gets bypassed down here。 I， it gets bypass down here into the issue stage。

And then that instruction can issue。 If we go look at the scoreboard， that corresponds to。

This becoming red。 And then we can go and actually issue instruction to to here。

 And we've basically bypassed that value。And register 5， which is the destination。

Of instruction tos multiply is valid。So this is， this is relatively simple pipeline design here also a simple processor。

But what's nice here is you can use your scoreboard to keep track of when things become ready without having to go and which pipeline to go look in without having to sort of look at intermediate bits in the pipeline。

And it's going become much more important as we go to sort of out of order machines。Okay。

 before before we move on， is everyone to understand how to look at one of these diagrams。

 because you're gonna have to draw these。Later， in the course。Ah， so thoses a great question。

 so let's look at this picture here。😊，So you only have one entry。Per location in the pipe here。

 So you're， you're saying we only have one of these entries。 We have multiple bits going down here。

But we leave one entry here。 So what happens if you have， let's say。

Things have issued two different functional units。With different latencies to the same destination register。

That's， that's a very important question。What's going to happen。

You're going to fill in with this functional unit。The newest instruction that gets issued。Location。

Because from a bypassing perspective。That's all you need to know。So that's， that's like。

 that's a very point。 You don't need to know。From a bypassing perspective。

 something that was older in program order。 We only need to bypass the newest value。

One thing we do need to do is make sure that we don't have a right after right hazard。

So what that means is we're writing something later in the pipe than earlier in the pipe。

 That doesn't happen in this pipeline。Because we pipe everything forward。

 We don't actually have right after right hazards in the right backstage。

 The next pipeline we're gonna to look at does have a right， right after right hazard。

And that's going to require us to think a little bit harder about the scoreboard。Exactly， yeah。

 so we're gonna have， that's， that's sort of the next pipeline diagram is we have a much more interesting scoreboard。

 actually，2，2。😊，Not the next pipe， but the pipe after that that is going have a more interesting。

Scoreboard。 One interesting thing to note is strictly for what we've talked about today。

 You don't even need bits。 You don't need to track to。Different rights to that same register。

Because you only need to know the most recent right to the register。

So one way that I've seen people build scoreboards is instead of having bits marching down here。

 you just have a encoding like a log base 2 encoding or a binary encoding of where to go look in the pipe。

For the newest value。And then you just increment that or decrement in every cycle or something like that。

 So you， you just have， instead of having shift registers， you could have that。

 And that's strictly enough for this。 The more complex pipes we're gonna to look at。As Promo said。

 we're going have to track。Both the location。The functional unit in the pipe and what stage in the pipe it's in。

 So youre， you're saying， how do I know that this is not ready until 4 or something like that？ Okay。

 so that is a subtle point is that。If you know what functional unit。

 if you know the functional unit latencies， you just look it up on the table。

You don't need to actually track that information。 There's just some piece of logic， which says。

For a multiply， if the functional unit is multiply， then we can't bypass till here。 If it's an ad。

 we can bypass from here or there or something like that。 So you don't need to track that in a table。

 It can just be part of your combination of logic in your decocode unit。Or your issue object。

Does that you don't， Yeah， you don't， I'll say one more time。To see。This。

 like this is this example here。 We have a mall that writes R1 and something which else is supposed to read R 1。

 but we end up stalling here。In this table， the way we know that is we know the functional unit。

And because it says multiply， we know that we have to wait until it gets to hear。

Or rather probably here instead of trying to pick it off earlier。If it， if it said A L U。

 then we could have it pick it off earlier。 So we don't necessarily have to encode that。 That's。

 that's why in this picture here， things turn red on some of these earlier than others。

It's that functional unit information， which encodes that。

You could even think about having that functioning unit bits。Encoding some number， like you said。

 some people design scoreboards like that。Okay， so I just wanted to briefly introduce this。

 And then we're gonna break next class。 we're gonna to be talking about in order front end。

And issue out of order right back and commit on these pipelines。 looks pretty similar。

 except some pipeline stages that are taken out here。And this makes you think harder about。

When to go read the scoreboard？So we're actually going use this decocode stage to do some stuff with the scoreboard。

And。Then we're gonna start talking about truly out of order machines。

 where you have these other fancier structures like weorder buffers and store buffers。 Okay， let's。

 let's stop here for today and pick up next time。

![](img/a082a143029494fba14a073267706ae0_2.png)

![](img/a082a143029494fba14a073267706ae0_3.png)