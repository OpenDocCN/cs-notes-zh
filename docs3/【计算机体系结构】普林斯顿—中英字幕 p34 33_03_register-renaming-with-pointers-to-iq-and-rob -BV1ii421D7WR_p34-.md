# 【计算机体系结构】普林斯顿—中英字幕 p34 33_03_register-renaming-with-pointers-to-iq-and-rob -BV1ii421D7WR_p34-

![](img/9f477d8badc83267dfb91e32eb24f1ae_0.png)

Okay， so let's take a look at what we have to add。To our pipeline。 So we have our。In order。

 fetch out of order issue， out of order right back。 and in order。

 commit processor that we had before。Noe， it had variable length pipes。 It had a reoror buffer。

 It had a future store buffer。 It had a scoreboard。 It had an instruction queue， So it had all the。

 the structures we talked about last time。And now we're to add two more structures to it。

And we're going modify the structures that are there slightly。 But let's。

 let's talk about what this is going do。 So the first structure we're going to add。Is a free list？

And the free list is going to keep track。Of physical registers that we can go use。

So the physical registers will probably have more physical registers than we have architectural registers。

But you need to keep track of which ones are free to be used。

 because we're gonna basically be allocateating and deating from the number of physical registers。

Quickly。While， as we execute。The other structure here， we call the rename table。

 Sometimes this is called the。Rat， which is the sort of the Intel nomenclature for this。 or actually。

 the， the rat is。Either this table or the table that we're discussing in the Thomasmau algorithm variant of this。

 But they're very similar。 And what this table does is's going to map from。Architectural register。

To the most up to date version in our physical register file。 So it's going to say。

We have instruction that's sitting here。At our decocode stage， where do we go find the value。

Cause this gets complicated。 We're gonna， we just renamed everything。

 We have different names for everything。 It's in some physical registers。

We need to go figure out what that value is。 And that's what this table， table does。

We're also gonna add two fields to the re buffer。 I' talk about that in a second。

And we're gonna want to increase the size of the physical register file so that we can get more performance。

 If we have the same number of physical registers as we have architectureural registers。

And we need to have at least one physical register for each architecture register。

 We we're not gonna to get any more performance from having a re register renaming step to our pipe。

Okay， so this is kind of for a completeness where everything gets written in the pipe in time。

 Two things I want to point out here， the。Free list gets updated at the front and also gets updated here at the end and the condition that you need to delocate a physical register a physical register gets a little complicated。

And， but we'll talk about that。And the rename table。

Gets read up here because that tells you where to actually get the value。

It also gets updated here when we actually admit an instruction down the pipe。

And we also want to update some pending bits when it get to the end of the pipe so that it knows whether to go sort of pick up from the physical register file or the architectureural register file for rollback issues。

Okay， so let's jump into these data structures and see what we add。Okay， as I said， we， we。

 we're gonna add stuff to the reorder buffer。Here， now。

 our previous reorder buffer looked very similar to this。

 We had some state whether things were pending， free or were finished。

 where we said dash dash represents free。 and F means finished。

 It means the instruction got the end of the pipe and is way to commit。

We had a bit that says whether they was after a branch。

 you might have multiple these bits if you allow multiple branches in flight。

 a bit that says it's a store or not。A bit that says whether it writes a register。So this， this says。

 well， the destination is valid。 And that's， that's important for us to know because when we get the end of the pipe。

 we need to know whether to actually commit some state into the architectural register file。

And we have a field here， which we have before， which was the。Physical register file specifier。

 So this tells us where to go read from。That's， that's all， that's all good。

 But now we add some extra extra bits here。 The first one。Is a architectural register file specifier。

Okay， so this gets a little complicated。 What， what what are we thinking about here。

 Why do we need this。Well， when we get to the end of the pipe。And we're gonna to do commit。

If you go back and look at this picture here。In the commit stage。

 we take something from the physical register file， put it into， and the rear buffer drives this。

 It says， okay， copy that into the architecture register file when the commit occurs。Well， not。

 we've renamed everything。So it's not an identity map from physical register number to architectural register number。

 So we need to know where to actually go right in the architectural register file。

And that's what this does。 Just tells us。Where to go， right？ So this is where we read from。

 This is where we write to when this instruction。 Let's say it's the most recent instruction here。

 This turns to finished。It's going to go commit。 We read the value from here。

 We write it into the value pointed to by here。And then we have one other field here。

 which is a little bit odd。 We have the previous physical register。Why， why would we need that？

 That doesn't make any sense。 It was the。What， what is this doing。

 So this is something we actually read out of the renamed table at the front of the pipe。

And what it's going to tell us is it' going to tell us。Let's say this was register4。

This is where we be in flight。Physical register is。

 and this is the previous physical register that held the value of Reg 4 before we did the update。

And the reason we need to know this is when we hit the ends of the pipe。

We need some way to delocate physical registers。And we're going use this to track that。

 And we'll give an example in a minute。 But what this is really gonna do is it's gonna to say， oh。

 we wrote to。The new value of register 4， which means that the inf value。

 let's say it was register  for physical registerister 27。

And the new one is physical register 30 or something like that。 We need to delocate physical Reg 27。

 And we can do that when we reach the end of the pipe by committing this instruction out of the reoror buffer and cleaning up all the state。

Okay， a quick picture here of the， the renaming table， the renaming table。

This is indexed by register。P tells us whether we have a right in flight。

So it knows that that value is not in the architectural register file。And Preg here just tells us。

Where're in the physical register file to go find the value。

And this is really important when a subsequent instruction that's looking for the value shows up。

 And once to get that value before it hits the architectural register file， it looks here。

 This tells us， tells us， oh， it's pending。It's going to be here in a little bit。

Together with this and the scoreboard， we might even be able to bypass it early。In， in a good day。

 in a bad day， we have to wait for to get to the physical register file。

 but's a lot better than having to go pick it out of the architectural register file。And finally。

 we have a free list。 And this is literally just a bit per physical register。

 which is very different than a bit per architectural register。And it's just going to have。

 let's say， we have big N。Physical registers， or I't know， we have 256 physical registers。

And we have a bit sane whether that register has been delocated and it's ready to be used。

For future registry naming or whether the instruct or whether there's a instruction。

Using that physical register or it's way to commit to the architectural register file。

 This will tell us that information in this table here。

 And's just a bit that says whether it's free or not。 pretty， pretty simple。Actually。

 before we go on here， I wanted to。Make it， make an interesting observation。 Where。

 Where does this register renaming become really important。Well。

 if we go look at something like the original Intel architecture， they had8 registers。

And if you want to run high performance code， you have to reuse those registers pretty quickly。

So they got registered limited very quickly when they tried to build faster and faster processors。

 So they had to introduce registernaming quite early in the Intel microarchitect implementations。

 and they had many， many more physical registers than architectural registers very quickly because 8 isn't gonna get you very far。

 They， they can have like about 100 inf instructions。And。By definition。

 you can't have that many inf instructions if you maintain right after write stalling effectively because you're。

 you're gonna have to rewrite some register。 It's kind of like a。Piggeonhole problem。

 If you have more than 8 instructions， least one of those instructions is gonna to cause and right after write dependency。

 you're gonna to install a pipe。 So they'， they're not gonna go have。

 let's say more than 8 in flight instructions pretty quickly if they did not do registertry naming。

 So they did register re naming very quickly in their pipelines。Okay。

 so this gets us to the YI chart here。Let's walk through a basic case。

 what's in all these different tables。As we execute our basic simple code here。On the top。

 we have the four instructions， two malls and some ads。 This was our original test case。 Note。

 there is all these dependencies through Reg 4。 we need to worry about。

 There's both you have to write。Right after read and right after write dependencies。

We're going to execute it。啊。Quickly here by pulling， as you can see， this ad。

Fires early or issues early。TheThe final ad。And this is really driven by the registry naming。

So let's， let's take a look at what what happens here。 And， let's try to interpret this。

 Here we have cycles。 cycles are also across the top。Of the stage。We show what's in the decode。

Issue right back and commit stage of the pipe。 we leave out the execute stages because this is too much to draw here。

 and it's drawn at the top in different form。Let's first look at the renamed table。

So we're at the rename table。 or we're actually gonna say we only have for， for clear this here。

 Let's say we only have 7。Architectural registers。But we're going to have， let's say。

10 physical11 physical registers。So we' have more physical registers than architectural registers in this example。

We start off and we say， okay， register  one。 if you want to go find architectural Reg 1。

 the values in physical register 0。And we could basically just， you know。

 we just come of some allocation。 And the circles mean that it's not pending。

 It's not in flight in the pipe。 That's sort of the base case。 Everything is。The， the。

 the pipe has been relaxed。 Everything is， is allocated。

 And we just do a basic allocation here at the beginning。Now， as we go to execute。

 some interesting stuff starts to happen。First thing' is gonna happen is were actually going to。Here。

Isue this instruction， which writes Reg 1。We need to rename this at this point。 Register 1。

 we have to rename to something else。So in this table here， if we look， we register， we rename Reg 1。

To physical register。7even。Okay， that sounds good。What happens next？ Well， we next sit here and we。

 we try to execute this instruction here at this mall， and it goes and tries to read register 1。

When it goes to read registerister one， though。We can go look at the readingname table and say， oh。

 well， that's actually in flight。And it's in physical Register 7。So if we go look over here。

 we can draw this and say， oh， that value is actually in physical Reg 7。

 and it's currently not ready。 maybe and， but， but P 4， the other input。Register 5。okay， yeah。

 Reg 5 got renamed to P4 is ready。So it's ready to go。Okay。

 let's one other interesting thing that happens here is we can see that as we go to allocate this。

 we have to remove it from the free list。😊，So this list here is a list of all the free registers。

 We start off with four free registers， and we sort of narrow it down as we start to do rights。

And at some point， we run out。So I wanted to make an important note about this is that when we run out。

Of physical registers， we're going have to stall the pipe。Because we can't do any renaming。

 We can't issue more instructions at that point。So that's， that's really， that's really important to。

 to realize is that when you build your machines， you have to have enough。

Physical registers that you don't run out very often。 Now。

 it's possible that you could still run out。 So let's say you have hundreds of inf instructions and you only have。

 let's say，64 physical registers。 you might still run out。

 but the probability of that happening might be relatively low and the your utilization and。

 you know， you sort of bake into this， your CPI， your CPI may not be less than one or may not be low。

 So， you know， the probability that actually happening。 You may not worry about too much。

Another cute little story here is there's actually been some interesting bugs in processors around the free list。

 So there were some alpha processors where they actually leaked free list entries in their register file。

😊，So what happened is if you ran a certain piece of code for a long enough period of time。

 all of a sudden in this processor just ground to a halt because it was not able to allocate more physical registers and it ran out。

 It ends up with fewer physical registers than architectureural registers。

 And the machine just stopped。 And this was a sort of wellknow bug in， in some of the early alpha。

 I think this was actually in the first out of。I think， when where was this。

 I think this was in the 21，2，64 had this problem。They， they fixed it。

 and they pulled those chips off the shelves。 And you know， that's。

 that's a really bad thing to have happen in your processor。 kind of embarrassing。But as I said。

 if you run out， you're not gonna to build the issue more。 But in this case， we。

 we made sure we had enough。 So we're not actually going see any stalls。

And let's look at how things get on the free list here。Because that's a little bit interesting。

In a reorder buffer， I said we had extra fields。If you recall， we had the previous。

Physical register that this was allocated into。So if we go work。At this instruction。

Which is the first instruction we go to execute that mall。R 1。Wast P0。

So when that instruction commits。We actually put P0 onto the free list。

And we're gonna look at a case in a second why you can't do it earlier。

 because it seems like you should be able to basically delocate physical registers earlier。 You know。

 no one's probably gonna be reading that value。 Why can't you just， you， get rid of it early。

But we'll look at in a second a test case that that that's， that's a problem with。Let's see any。

 any other fun insights here。That's， that's about what I wanted to get across from。

 from this diagram。 as， as the code continues on， we end up with more and more free physical registers。

One， one thing I did wan just to walk through this to understand this a little bit。

 Let's say we have。This instruction here， which is our， let's see 1，2，3，4。

 It's our last instruction that we execute。Let's go see you。What it's doing here？

So it writes architectural register for。 So we have to store that in the reorder buffer because we need to know where to go to do the right。

嗯。We had allocated P10 to that。😡，And we did that。Right here when we actually issued it。

So we pulled it off the free list。And the previous thing that I wrote was P 8。

 So when in that ultimately commits。P8 is going to end up back in our free list。So that's，'s。

 that's a nice little thing。 the circles。Just show when the values are no longer pending。

So they actually are not in the pipes anymore。And you can see that continuing here。

This instruction here。Which is。The second multiply， when it commits。It's going to free up P 3。

 So P3 ends up on the list。 P 5， P5 ends up the list。 P 8， P 8 ends up on the list。

And then when we see true。Read after writes。For example。Right here。

We need to make sure to pick up that correct value。And we do that by looking up in the renamed table。

 So let's go find that in this chart here。 So instruction 2。Is let's see what it's doing here。

 So that's going to be right here。 it's waiting on the 8 to become ready in order to issue。

 So it's sitting in our instruction queue。 And it's just gonna stall。

 It's gonna stall all the way out to here。Or it's installed the right there。

And that's when it comes out of the instruction。 Okay， so let's look at。

Freeeeing up physical registers。 And what is a good policy for freeing up physical registers。

So we're going to have a different piece of code here。 we're going to look at。

It's going to be just a bunch of ads。And we're going to look at。This code has some。

Read after write dependencies in it。Namely。Our one there。And let's say we try to go execute this。

 while we， we're gonna。Here's some execution order。嗯。We're gonna look at， or sorry。

 that one there is what I' meant to go point out for the re after right。We have。

right have read dependency here。 So let's look at some execution order and see what happens。

Let's say， we allocate。Physical register is 0。At the beginning somewhere for register one。

And then when we do the commits， we free it up in our free list。Well， lo and behold。

 another instruction in time comes along here and allocates into physical register 0。

And it goes in writes to it。 and we like free it up there。This instruction here。

Which we had renamed and， or we， we had renamed our 1，4。 and we go to try to read this value。

Goes to do the read， and it looks in physical register 0。 and it gets the wrong value。嗯。Yeah。

 we don't。 we don't want that。 So what's， what's a good policy here。嗯。Let's say， instead。We don't。

Free up a physical register until someone else goes to write that。Physical register。

 or our subsequent instruction goes to write that physical register。

Because then we know that physical pressure is in use or could be in use by other readers of that value。

So if we look at this case here， let's say we write physical register 0。

And then we allocated different physical register， Read。

 allocate physical register 2 for this right here to register 8。And then， we delocate。

When we go to overwrite Reg  one。So， by doing that。We know when this R 1 gets written。

 that no one else can possibly use that physical register。

That is after this instruction in program order， because we overrote it。

 So that value is no longer visible。So that's， that's pretty， pretty nice。 So that's， that's the。

 a very good heuristic or a very good way to get this correct， as you can just。

Keep the physical register alive until you rewrite the physical or you rewrite the architecture register。

 that physical register。Maps 2。 And then at that point。

 you can remove it from the number of allocated physical registers input on the free list。

If you do it early with an out of order execution pipeline， you know， bad， bad things can happen。

You can go read the wrong values。Okay， so this brings us to a couple optimizations on register renaming。

Biggest one here。Is you can try to combine the architectureural register file and the physical register file to save space to And the insight here is if you go to try and combine these two things。

 you can store。The architectural register value and the physical register value in the same physical storage location。

If that fiscal register is no longer pending。So if there's nothing in flight to it。And。

You don't have to roll back。 And if you're gonna roll back to the same value anyway。



![](img/9f477d8badc83267dfb91e32eb24f1ae_2.png)

Why， why keep extra space for this。1， one change you need to do here is so you're going to remove the architectural register file。

Buthi you still basically need to know when you go to do a rollback。Of some speculative。

 So you take an interrupt or you take a branch mis predict。

 You still need to know where to go roll back out of。And we're going to do that by， let's say。

 having a second。Renaming table here。Which allows us to keep track of just the architectural state。

 So we have a speculative renaming table that we have an architectural renaming table and just has pointers in it instead of actually the values at the end of the pipe。

And what's also nice here is instead of copying values。

 we don't actually have to move something out of the physical register file into the architectureural register file。

 Instead， we have to update a pointer in a table now。And we did the copy。

To potentially also make rollback easier because we just have to update some pointers now instead of actually copying an entire register file。

 which can take a while or requires lots of ports or something else。

 So you can have a little table there to just do this remapping for you。And as I say。

 you can typically get away with less space than having for the same performance than if you were to have two separate structures。

One of the downsides is you， you might need to have more。Depending on how you implement this。

Your architecture register file and your physical register file are now together， it may be bigger。

So your regitry file access might be a little bit slower。 Something like that could be。

 could be a downside。Versus having in two separate partition structures。

