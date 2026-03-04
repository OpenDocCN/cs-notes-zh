# 【计算机体系结构】普林斯顿—中英字幕 p28 27_02_i2o2-processors -BV1ii421D7WR_p28-

![](img/4ff536cd424a95557f6fd0895ec0c5fa_0.png)

So in this processor， we're going to have basically three pipelines here。A long， multily pipeline。

A memory pipe that say takes two cycles and then a short ALU pipe here on the top。

We have a scoreboard， like we had before。And this is going to track where data is available。

In the pipe。Where data is available in the pipe。And the architectural register file is sort of seeing at the end。

 So this looks relatively similar to the in order issue。In order， right back。

 in order commits a processor。But there are some interesting things here。

 If you compare this picture here to this picture here， we just dropped all these pipeline stages。

So that's pretty cool。 We don't have to bypass out of there anymore。

 We can just sort of shove the data in the architectural register file。

 And if we preserve read after write， right after write and right after read dependencies， things。

 things should be okay。😊，But let's see if we can actually do that。So let's first。

 look at the scoreboard for this in order issue in order fetch in order issue out of order。

Execute and write back in out of order， commit processor。So the。

 the scoreboard looks very similar to the in order in order， in order， in order machine。嗯。

And we can use it to track。Structural hazard on the right back porch。And this is really important。

 if you try to。Have， let's say， a multiply and then add after it。

It's possible that the multiplying ad if under pipelinelining might have to go use the right back port at the same time。

 So you get a structural hazard。 and we're going to show a pipeline diagram of that happening。In the。

 in the next。Slide。We still don't actually need。To have a more complex scoreboard。 So briefly。

 someone asked in last lecture， in the scoreboard， do we need to track which functional units each value is going down the pipe。

We still don't need to do that for this relatively simple pipe because for a right after right dependence。

 we're basically just going to stall。If you want to break that requirement。

 then you need to start tracking more complex things in the scoreboard。

 And you may even want to have something like a register re， which we're gonna talk about next class。

 And that's gonna allow you to basically。Break a right after right dependence dynamically in the processor。

So an important point here because these pipe stages are different length now。In our scoreboard。

We had。Different places where the bits where where the entries in the scoreboard could be。

 But now if we go to execute an instruction， which is long。

 we're gonna put it in one in sort of the first entry in the scoreboard and's gonna march down every cycle as as tracking the information as it goes down the pipe。

But if we're trying to， let's say， execute a ad instruction。

It doesn't actually have to wait four cycles to get into the architectureural register file。

 so we can actually insert。Herear a one。 And then it just marches down the balance of the pipe。

For particular。Location， and this is what I was saying that。

Because we're not going to allow right after rights。Hazards on a particular register。

You're never going have a case where there's basically multiple inversely ordered bits in。This table。

 if you had that， you would actually have a more advanced scoreboard。

 and I'll show a picture of that a little later in today's lecture。Okay。

 so let's go through an example of how to use the scoreboard。

And how to walk through a in order issue。In order to fetch in order issue out of order， execute。

 and write back an out of order commit processor。So here is the same code sequence。

We had in the previous example case。 So we're going to be using this throughout all of the class。

Let's， let's take a look at this and sort of see how this pipeline diagram happens and notice a few things。

 First， let's take a look at some read after write hazards and what the pipeline has to do。嗯。冇。R 5。

 R1， R4。This reads R1。Well， our one is created by us multiply in instruction0。

So it actually has to wait。To get the bypass here from。

Instruction 2 is going to have to wait to get this value。So you can see here。

 it's basically just stalled。 And what's happening here is you're in order issue。

 You can't go try to issue subsequent instructions under that。Later in today class。

 we're going be talking about pipelines which actually have out of order issue。

Such that while this is waiting around， you can think about trying to go and issue the next instruction that's not dependent on that previous instruction。

And by doing that， we get more performance because we can basically be reordering instructions and trying to use our functional units and use our ALUs as much as possible。

But right now。We have a。Bypass coming out of。Y 3 here out of this multiply down into the register file access stage of that next multiply。

 So that's sort of one thing that's going on。Let's take a look at another。

Read after write dependence here， so。Another read after write dependence is actually。Register 11。

Gets written here。😡，And red down there。Well what which do you think special for this so。

So of marches on the pipe。 the right happens here。 Let's see where the read。For this instruction。

 In 4 tries to happen。 Well， the read tries to happen there。Well， at that point。

 the data is actually in the architectural register file。 We don't have to worry about any funny。

 funny bypassing or anything like that。And you can sort of work through the rest of the。

 the things going on here。 But there's a few other things I wanted to point out in this picture。

First， because you have different pipelines。You can actually see that。

 let's say this ad here is writing the architectural register file before a previous instruction。

Writes the register file in program order。And this has some， some consequences。

 some large consequences when you're starting to think about， if， let's say this instruction here。

The multiply that preceded the。Ad took some sort of fault or took some sort of exception。

Because now you've basically changed the architecture register file before anyone before that other instruction has finished and that other instruction didn't actually finish。

So what does， what does that mean，One other thing I wanted to put out in this picture。

 which is a really interesting case is。Right here。So this ad instruction here。It's dependent on R 12。

R 12 gets created here。😡，And basically at the end of this stage， it's ready to bypass。

So if we look down well say， well， this instruction here。

 we don't even try to read from the bypass until here。 So that value is ready。But for some reason。

 this instruction stalls。Can anyone see what's going on with that instruction？

All of its inputs are ready。It's ready to go。It's a party to go to。But it doesn't issue。 Okay。

 so that that is what's happening here。 I that if you were to remove this。I stall stage here。

This would get pulled forward。 And now you'd have this writing and that writing at the same time。

 So we actually have a structural hazard on the right port of the register file there。

So you have to stop。Okay， so let's take a look at how that shows up in shows up in the scoreboard。

So when we go to sort of look at this。 So what's what we have here is we have cycles。

 There's 18 cycles across the top。Or actually， just 19 cycles across the top。 the first one，0。

 but I would draw that。If we look at， let's say this cycle here， instruction 1。Which is this ad。

Is in the。I stage。So it's in the issue stage of the pipe。So it's looking for its opera ends。

 basically。And。What's going to happen？Is this。Add。Needs to check to make sure that it's not gonna to conflict on the right port。

Of the previous mall。In this case， it doesn't actually happen。

But when this instruction moves to here，This is what I was saying is that it doesn't actually put ones in the for location and sort of marches down。

 Instead， it's going。Start here at the following two cycles to go before it writes the register file。

 because the pipe is shorter。So it has to check this location and says， well。

 for my register that I'm trying to write is anything else currently。

Scheduled to go right that location in two cycles。And our scoreboard can answer that question。

If there was a one in this box。Yes。We would know that there was a mall or some other instruction that had long latency。

That。It would be a conflict。 So with this instruction， we were to move here。

This one would also clock every cycle， and moves down our scoreboard。

 It's going to conflict at that point。 And we're going to know we're going to have a。

Rightite hazard on the register file。So we can sort of see those things happening in our scoreboard。

And then we， we could also use our scoreboard to actually detect that real case。 So this case here。

 this last instruction， this last ad， we're gonna to see that show up over here。

So let's try and find that。Okay。We have。Instruction 6。It wants to basically move forward in the pipe。

But it checks this location here and says， okay， or in this cycle here。

 In 6 basically should be in the issue stage and doesn't move out of the issue stage。

 It's it's sitting in the issue stage。It looks in this location。

 which is basically two cycles till the end of the pipe and sees that there's a one there。

The the box is trying to indicate that。 So it looks there and says， oh， there's a one there。

 That means I can't issue this stage。 and I need a stall。 and we get this stall showing up。

These other boxes are here to donate。Here to represent the other ads that are happening。

And the other malls and things。 So we actually check these other location。 actually。

 these are just the other ads。 These are。 we're gonna check for this ad here。This ad here。

 this ad checks here and sees a conflict。 So it has to check again the next cycle。

That's why there's four little boxes vertically on that chart。嗯。

Other things this is just a different representation here。

 You can see R1 is being written and it has a long la in the pipe。

 This other register has a shorter other register has a shorter liveness time because in。

 in our scoreboard， because it's a ad instruction。Okay。

 so do we have any questions about that before we move on to a more complex pipe。

So this is assuming a fixed latency for every instruction that is correct。

 or at least per pipe or functional unit in the pipe。 You can definitely have functional units。

 which have。Variable laency。 So an example of that is sort of two good examples of that。

 One is something like a divider unit。 Sometimes people build divider units so that you keep dividing until you're done。

 And it's sort of a way to shorten the length of a divide。 So that sometimes has variable length。

 Another good example of this is something like a load。That misses in your cache。

And out of order processor， you have to wait for the load to come back。Good ways to handle that。

 actually。 in a scoreboard。 Sometimes scoreboards will just have an extra sort of special bit on the side for each destination register。

 which says。This register is just out to lunch。You know， it's in some long variable length pipeline。

 I don't know what's happening on it。 Don't try to bypass it。

 Don't try to do anything special with it and just wait for it to come back and bit clears。

 So processors I've built。For these variable length instructions。

 will typically just have an extra bit for maybe the different functional units。

 like one for maybe the divider and one for the。Load miss case or something like that。 such that。

 you know， if that exceptional case happens or if the load misses or if you go and take a divide。

 which has a variable length， because divide can take anywhere from like two cycles up to like 20 cycles in some pipelines。

And in every， everything in the middle， you'll just mark a bit saying this register is not ready in the scoreboard。

 And then if someone tries to go read their register， it just knows a stall。

So it's just a slower performance sort of way to deal with that。 But that's。

 that's a tough tough case to handle。But a scoreboard can help there。

 and it's sort of extra information in the scoreboard。Okay， so。Like I said， we had this out of order。

Commit processor。 It's doing out of order right back， and it's doing out of order commit。Oh。Well。

 out of her to write back， maybe okay。We maintain our right after right dependencies。

 So we're not actually going to end up with incorrect state in the architectural register file because of that。

But something bad can happen is what happens if we go and try to take。An exception。

So let's say we have our same instruction sequence that we've been looking at up to this point。

And here。We're wandering around。 We're going down the pipe。 And this instruction here。

Take some sort of fault。 And it's figured out at the end of the pipe at our commit stage。

 So the multi goes all the way down to the end。 We end up with。

I the multiplies don't take a whole lot of great faults。 But let's say it。

 it takes some sort of exception。 What， what is， what is going happen well。That instruction is dead。

 All the other instructions are dead。 it took a fault。Unfortunately。

We already wrote the register file。等当等等等。Yeah。Okay。

 so now we end up in our trap handler or our exception handler or interrupt handler。

 And all of a sudden。Register 11 is this wrong。 It has the wrong architectural value。

So this is one of the reasons why people should have tried not to build out of order commit。

 It gets gets。 It gets tricky to have out of order commits with precise exceptions。 Now， there are。

 there are some ways to do it。So， one way。Is limit the types of instructions。

So if you have an in order issue。Out of order to commit， Out of order write back。

What you could think about doing is， you know that this doesn't write until this point here。

So what if we resolve all of our。Previous， let's say， all of the previous。Exceptions。

 if we move our commit point earlier in the processor。

We can actually make this work and have precise exceptions。 So if our commit point， let's say。

 is in the either memory one stage or first stage of the multiplier or something like that。

At that point， we haven't ridden any other state here that's wrong。😡，That right back hasn't happened。

 so we can still kill everything down。Unfortunately。

 that means that you can't have an exception happening here。

 here or anywhere else sort of like later in your pike。So that's， that's a problem。 So you。

 you can limit the types of exceptions， push your commit point early and still have an out of word commit processor with precise exceptions。

But that even is tricky。 So， so this is a great question。 So why can we not have two commit points。

Some processors do have to commit points。And some processors will have。

 it's called sliding commit point so that you try to commit things sort of early。

 And then if something else。For certain types of instructions， you can move the commit point later。

But typically， you want to have a commit point in one place where you say。

 after this point in the pipe， all of the state is past this has been committed and those instructions cannot be rolled back and those instructions cannot be undone。

But there are examples of things where people will have a sliding commit point。

 I've actually built a processor which has a moving commit point。 but it's。

 it gets tricky because what it basically means is certain types of instructions cannot execute after。

Certain other types of instructions， because if they do， you sort of violate that。

 that sliding commit point。 Like this example here。IfIf the fault can be taken here。

 there's no way to solve this problem。But you could have something where a s commit point where if you have these a mall followed by。

 let's say an ad， you can actually sort of slide the commit point out。

So there are processor ideas that you can try to have a sliding commit point， but otherwise。

You have to， you have to check that gets quite a bit complicated。

 I don't really want to get into that today's， let's leave there for a sort of advanced topics。

 discussion。 But in， in what we're gonna talk about in this class。

 we're gonna say we want to have one commit point。 and we want to say one place in the pipe is the canonical location that past that point。

 all the data。That is in flight is， has executed and is committed。

And we need to know sort of one location for that。

![](img/4ff536cd424a95557f6fd0895ec0c5fa_2.png)

![](img/4ff536cd424a95557f6fd0895ec0c5fa_3.png)