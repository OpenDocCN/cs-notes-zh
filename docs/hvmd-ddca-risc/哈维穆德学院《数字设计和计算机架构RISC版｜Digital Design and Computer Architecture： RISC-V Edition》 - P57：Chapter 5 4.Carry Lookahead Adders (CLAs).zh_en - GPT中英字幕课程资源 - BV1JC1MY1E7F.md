# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P57：Chapter 5 4.Carry Lookahead Adders (CLAs).zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/9f55db7e773cf6c4a796c32056ee58e4_0.png)

So now we want to look at how we can speed up this process of having that carry ripple through each of the one bit adder as well。

 rather it not， right， that's the slow path。 we want to actually figure out how to speed up that path。

And so the next kind of adder that we're going to introduce the carry Look ahead adder or the CA。

Speed up that path by basically calculating some of the carryouts ahead of time。

And so we're going to compute the carryout for CAbit blocks or for example。

 four bit or8 bit or whatever number of bit， for blocks and use what are called generate and propagate signals。

Okay， so let's talk about what these generate and propagate signals are。

So column I produces a carryout。So right we have our different columns by either generating a carry out just of its own self。

We have， for example， if we had 11 and a sub I and B sub I， it would generate that carry。

No matter if a carry came in or not。 So it either generates a carry or propagates a carry in to the carry out。

 So propagating means， well， now it depends on if there's a carry in。 so。

 but if a carry in were there， it would propagated to the carry out。 So， for example。

 a sub and B sub I were 0，1 carry in a carry came into that column， yep。

 it would get propagated because。At least one of those is one。Okay。

 so we can calculate these generate and propagate signals for each column。Okay。

 so we have generate signal for column I you know we just kind of talked about this already。

 A subi and B sub I both have to be one to generate a carry in a column。

That will generate a carry this。01 for a subi and B sub I。This case generates a carry。

 this one does not generate a carry。That one depends on now whether there's a carry in or not。Okay。

 so we can write that G sub I， this generate signal for column I is equal to well。

 both a sub I and B sub I being one， so a sub I and B sub I。

Now let's talk about propagate a columnable property to carry if a sub I is one or B sub I is one right we can have this case。

01， if carry comes in， yep that gets propagated to the output。Here's。The other case， a sub by。

 b sub by， yep， if carry comes into that， it will get prop to the output and then we have you know the kind of redundant case would generate one plus one yeah。

 carry coming in is' definitely going to generate a carry out on that or you know。😊。

We actually have an overlap case there。So。😊，We can write this as P sub I is equal to。

A sub I or B sub I。 So comb I will propagate a carry coming into it if。Either。

A sub I is true or B sub I is true。And so we can write the carry out C subi of a column in terms of these generate and propagate signals。

So we have our original equation， right， we're going to get to carry out c subi of that column。

If A and B are true， okay， there's the generate signal or we wrote this before as A and C or B and C。

Just。Factoring out that C sub I minus-1。 This is the carry in。It's that column。This is the carryout。

And so we can see that A and A sub I and B sub I。When the column generates。

The carry within that column。Or。It propagates。A carry that came in。Pece of eye and the carry in。

Which is C sub I minus1。And so we can rewrite that equation as G sub I or p sub I and the carry in。

 which is c sub I minus one the carry out of the prior column。Okay so。

So far with generating and propagate， you know， well。

 it hasn't really been an advantage yet because this looks， yeah， this， I mean。

 this is a similar equation。 we haven't sped that up。At all there。 So it really takes。

Takes helps us have an advantage or decrease the delay when we calculate。

 propfagate and generate signals for cablebit blocks。 Let's talk about that now。So before we do that。

 let's do a quick calculation of column propagate and generate signals。

 remember a column is going to propagate a carrier that comes in if A or B is true。

And a column is going to generate a carry independent of a carry coming in。

 it's going to generate a carry out if both A and B are true。Okay。

 so we can calculate propate and generate signals， propate signals for this edition。

Where we have a sub 0。Or B sub0。 Yep， that's true。 A sub A sub1 or B sub 1，1 or one， yep。

A sub2 or B sub2，0 or1。Yes， and the last one， A sub three or B sub three。 Yeah。

 that one's also all ones。Okay， and then we can do the same thing for generate， well。

 when are A and B both true in this case only in column 1， so a sub1 and B sub1 gives us a one。

Or generate signaling get that one we would generate a carry out no matter if there's a carry coming in or not。

And then all of the other columns。Would not。 So do you sub I。All the other columns。

Would not generate a carry in and of themselves。And we can do the same thing for， you know the。

The addition on the right， piece of I， well， it's going to be one here， one here， oh， zero。

Cause neither of the。Of the bits that were adding together and B are true or one。

If we had a carry on coming to that column， I would just drop right into the sun。

 but it would not get propagated to the carryout。And so we have a zero for that column column two in this case。

And ones for every other case for the propagate signal piece， the column propagate signal。

For the generate signal， we have。Both A and B being1 and column3。And。Column 0。Homes 1 and2。

Would not generate a carry in of themselves。And so we can type that out and we get that same result that we just calculated and we can see that。

 well， yes， if we can calculate now the carry， using these column， propagate and generate signals。

 we're going to get to carry out。😊，If。Remember this is carry out this C sub I。

 if we either generate a carry within that column or we propagate a carry and we do have a carry in。

C sub by minus1。And we can see that as you know， as we add these together， if there's a carry in a0。

 one plus one， well this one generate a carry， so that's how we got that carry。😊，Carry out G of 0。

Was one。Pce of0 was also one， but carry the carry in in that case was 0。 So this carry。

Out of column 0， season 0。That one right there。Was because of。The generate signal。Generate or。

Proropgate and carry in while our carry in。This is C sub -1。 So our carryion to an entire。

AddR is called C sub -1。Okay， you can， you can look at the other examples to see， okay。

 let's see this one how to carry in。And so， we had。G of0。 See， See out。

Con 0 c0 is g sub 0 Well that's 0 or。Piece of0。 Yeah， that's one。And。Cus of minus one yet。

 we had a carryion in this case， we happened to， you know we just chose that。Carry on to be one。

And so that's how we got this carry out， that's what caused this carry out C sub zero。Remember。

 that is the carry out of poem 0， carry in。Column1。This is column one。Coaln 0。2。😔，Okay。

 so there are column propates and generates。And now we're going to start looking at our block。

Proagates and generates。So we're going to use our column propagate and generate signals to compute these block propagate and block generate signals for KB blocks。

So。We're going to compute if that Cic group。Would property to carry in。To the carry out。

 if it gets a carry in。 So if it had a carry in， would it propagate it。It's to carry out？

You don't know if there's a carion or not。If it had a carry in。

 we want to compute whether that K bit block。 So for example。

4 bit block would propagate that carry to the output of that four bit block。

And we also want to compute if that cable block would in and of itself generate a carry out。

Of the block。So will it generate a carryout just you know on its own？

Or will it propagate a carry if there's a carry in。

 we want to calculate those for these caveVt blocks。Okay。

 so let's take an example four bit blocks we're going to talk about a block propate signal and this nomenclature can be a little bit confusing at first This is actually a single bit or a one bit signal so P3 to0 is a one。

😊，Bit signal。This is our block propagate signal It's going to tell us whether that entire four bit block would propagate a carry in to its carryout。

Okay， well， how do we calculate that， Well， let's see。 let's give some examples。

 So here's a four bit block。0，1。Let's just， yeah， so we'll do something like that。😊，Okay。

 with that prop carry， we dont know if there's a carry in， but if there were one。

 so let's say there were a carry in。I our carrying into that block。Would it generate a carry out？

It definitely would right if we calculate our column propagates piece of eyes， piece of zero。

 piece of one two and three， yep that would propagate。

 that would propagate that would propagate all of those columns would propagate so it's kind of like a relay game where okay that this column propagated it。

😊，The next column， that column also propagated it to the next column。

 This column also propagated it to the next column。 This column then propagated it to the output。

Here's our carryout of that four bit block。Because it got propagated through all of the columns。

 each of those four columns。So here's another example。

 a counter example where that didn't it wouldn't get propagated。 So let's say， for example， we have。

嗯。This column right here。And let's just change it。 We'll change that bit， that B bit here。And say。

 okay， well， here's a3 to0 and here's B，3 to0。 and let's say we changed that bit was zero here。

I highlight it。Oh well， so now that piece to buy that propagate for that column。InThis case。

 column 2， right， column 0， column 1， column 2。 That piece of y is now a0。 It's what happens。

 We saw a carryion that got propagated。 So we're saying if a carryion comes in， what happens。 Well。

 here's our carryion， It's still coming in。We still get that propagating it， that column column 0。

 column 1 also propagates it。 What happens to column 2，1 plus 0 plus 0。

That fall right into the sunbit。And so now that column no longer gets propagated and are carry out。

Is 0。So in order to propagate a carry。We have to have that。Through a four bit block。

 we have to have the propagate individual column propagate signals be one for each of the columns。

Proroppagate zero and propagate one and propagate  two and propagate 3。

If one of those drops the ball， like we saw here。嗯。Right this column kind of drop the ball。And said。

 hey， a carry coming into that is not going to get propagated。 So that entire four bit block。

Will not propagate a carry from its input to its output。It has to have。All of the propagates be true。

 so now I've changed it so that it would propagate a carry in。So it's carry out。Okay。

 but regardless of what the bits are， we can calculate this remember this is still a one bit signal。

 this block propagate signal， want to know if that entire block would propagate a carry into the out。

😊，To the output， to carry out by saying， well。P0 and P1 and P2 and P3。

 all of those prop signals have to be true。Okay， so now let's talk about the generate signal。So。

Here's some examples similar to the ones that I just went over。That one would propagate。

 and this one would not because。As we see。This column right here happened to be a similar one。

Drop the ball and we that carry not it profccateates the output。Okay， so block generate signals。

So now independent of a carrying coming into our block， we want to know。Well。

 does this entire block generate a signal in and of itself， generate a carry out in and of itself？

So let's see some examples well， how could it generate a carryout？

Independent of what the carryion is to that block。Well， this most significant column。

This is column number three。Here's our column numbers。C number 3， what if it， if those were both one。

 So we have a 3 to 0 and B 3 to 0。 this case， we have a sub 3 and B sub 3。They're both one。

 Does that generate a carry out。 Sure it does right，1 plus one。Qu。😔，To0， carry the one。 Okay。

 so there's one case。 So we could say this， remember， this is a single bit signal again。

 G3 to 0 looks like a 4 bit signal， but it's a1 bit signal that says， hey。

 I want to know if this 4 bit blocked。From 3 to 0， generate a carry。 Well。

 one way for it to generate a carry is if， well， how do we， what happens in that column， Well。

 that's G sub 3 is going to be one。Well， there's one way。

So if the generate signal in the most significant column is one。Yep。

 that four bit block is going to generate a carry no matter what。Okay， well， that's good。

 is that the only way？Think of some other options here。Well， what about， let's go to column 2。

 Let's see if column 2 generated a carry。So G2， that generated a carry。😔，Would that be enough？

Let's see 1 plus  one would be 0。 And then would it would generate a carry into the next column。

 column 3。But what if column three were this。What if column three were like that。

That's not going to make that entire block。Produce or， you know。

 kind of generate a carry within a self。That would have to be right column 3。

Would have to propagate it。So now we're talking about our propagate signal， 01，10 or 11。

Those are our options。This case would have to have G2。Being true and。P3。Its generated in column 2。

 and that。That carry that got generated in column 2 would have to propagate through column 3。

There's another way we could do it。We could generate a。Carry within itself。

Generate in column two and then propagate through the next most significant column like this。

If we showed there， okay。It's pretty good。Any other options here？Wo。😔，What about call。

 let's go to column one and see what happens there。So we could generate a carrying column1， right。

 we get A and B， both being one。A sub1 and B sub one that would generate a carry。So yeah。

 we're sure that would generate a carry over to those next columns。

But what would have to be true in order if this block to generate a carry within itself。

 Well those would then have to。Proaggate P2 through P2。And then， the P。3。Then we propagate that。

How is the output。 Okay， so that's another case。 So generate in column 1 and prop date through column 2 and column 3。

Okay， so at this point， guess what the last case is。Well。What if we had a。enerate。

 we generate it in column3 in column zero。So we have it one on a sub zero and B sub zero。

 So we generate in that column， well， in order for that carry to get it get all the way to the output。

Has to propagate， right， We know we're going to generate a carry。In that column。

 so Steve said zero is going to be true because guess what it generated right。

 it's going to generate that。That that carried G sub 0 in this case is one。

But we better make sure that that propagates all the way through。 So we get 1，1 in that zero column。

 but we better in columns 1，2， and 3。Get a propagate。

G0 better propagate through column 1 and propagate through column 2 and through column 3 to get to the carry out of that block。

 So here's some examples。What's gonna。It is going to generate and column  zero。

 and now it's going to propagate。嗯。Through the remaining columns。And make it to the carryout。

 So here's our carryout。Of this4 bit block， or in this case， C of 3。

And here's a case where it wouldn't， right， so that there's our last our last case we had。Well。

 it generates of。of that four bit block。 remember that's a one bit signal。

So generate for the block for this four bit block is well either generated in column 3 or generated in column 2。

 procade through column 3。We're generating column1。Profate through two and three。

Or the last case generating column  zero， propagated through one， two。And3。

One of those propagate signals， let's say propagate two， for example。Z， that one comes in。

 drops down here and never gets propagated。To be output。Okay， so we can write that。In words。

 carries generated， these are the way to generate a carry out within that four bit block by generating carrying column3 or column2。

 procate through column 3， or column1， propagate two through， two and three。

 or column zero and pop proate through the remaining columns1 through three。

And we write this you know， like we just wrote it before。

 and then we can also you know write it in a different way。

 which you'll often see we'll show it in circuit form by factoring out。This P3。Okay get G2。

Or G1 G P2。Or G0， P1， P2。 And then we can factor out this P2 right there。

 We're going to get G3 or P3。And G2 or G1 or the back of that out。Happy to。And。G1 or。G0， P1。Okay。

 and that's usually easier for us to build。 and we can build that with two input gates here。

 And so this is just。The same equation。With。Terms factored out these two equations of the。

The same logically。This is the way to think about it。And then we can optimize it。

And that second equation。So now let's look at block， generate signals。 So a carry is right。

 we're gonna generate a carry out by either generating column 3 or column 2 and propagating through column 3 or a blah。

 blah， blah。 So let's see what happens。 So this one there's this block of4 Bs。😊，Generate a carry。Yep。

 it does because G3。This left must column is one。We get a one here。And in fact。

 independent of what happens if there's a carry in or what else happens to the prior columns。

No matter what one plus one，0， we're going to get that carry out。Of that 4 bit block。

 I're going to get C sub 3。 carry out of column 3。Okay， because it was generated in column 3。 Well。

 here's another case where we generate it in column2。Here's column 2。

 and we propagate it through column 3， so 1 plus10。Carry the one， and it gets propagated。 right。

 this propagate signal， P of three equals 1 and G sub  two equals 1。

And so we get a one here and it propagates it。Through column 3， and then。We get that。

COr that actually generate a carry from that block。ok。And which will be C of three。

And then here's another example。In this case， we have column one。Generating the carry。

So we have column one has G sub 1 is equal to one， great。

And it propates through the next column so1 plus10。

 We don't actually you need to do that addition because we already already doing any in terms of prop generate。

 but just to show the analog and for column2。P sub 2 is equal to one cool。

We see P sub  two is equal to one because A or B， A sub two or B sub two。Is one。

And here we have P of two is equal to one。 Co。 So it's going to propagate that carry that came in from column1。

But then what happens？So propagated it。Right  one plus1，0， carry the one propagates it here。

What's wrong with column 3？P of three is0。And so that carry that was generated in column one never makes it to the carry out。

And so in this case， right， there we have G sub1， yep， that's one。And one。

 got prop through column two。But piece of three。It did not propagate the carry。

 And so now we have right， we 0 here or0 or 0。Or 0。 And so this。Group of format blocks。Does not。

Generate a carry within its four bit block， G3 column0，0。If you look at this， this does not。Generate。

I carry。And so in summary， we have block propate and generate signals to where we want to know， hey。

 what is the entire block？Prop Gator carry that came into it in this case。

 c sub I minus1 would it propagate that to the output， Well。

 if all of the propaggate signals are true， it would。Would it generate a？

Carry out within you know independent of the carry in to that block。Well， we derived that equation。

For。😔，G3 colon 0。 again， remember， that's a 1 B signal。

 And now we can write the carry out of that block in terms of these block propagate and generate signals。

 So Cid 3。Carry out of that block。Is going to be one if。We generate a carry within that block。

Or we propagate a carry。And。There was a carry。So let's take an example adder that's a 30  cubit adder that has four bit blocks。

So we have our block property signals made up of our column。Proper eight signals added together。

And our。Block generaterate signal。And then we can produce our carry out。

Of that block using our block generate and block propagate signals。And it carry into that block。

But here's a schematic of our 32 bit， carry look ahead at her or CLA。With four bit blocks。

 And so we have our， our numbers， our inputs blocked into4 bit groups。So A，3 to0， B，3 to zero。

A 7 to 4， B 7 to4， and so forth。Okay， so each of these four bit CLA blocks right here。

 we're going to expand that。And look at what's inside of each of those， each of these blocks here。

So each of these has， well， this looks familiar。There's our ripple cartter。If carry in。

 but you'll notice something strange about that ripple carry or。 what happened to its carry out。

It's not there。 The carryout of that block is actually being calculated。Byai。This circuit down here。

So this circuit on the bottom is calculating our carry out of that four bit block。

And so the sum bits are being calculated。Bai。Our ripple carer on the top using the carion。

 so the carrion is still rippling through there to produce the sun bits。

 but we're kind of fast pathing the carry out calculation here。On the bottom。And so you'll see that。

 well， here our column propagates and generates。And we're using that to calculate。Our block generate。

Right， this is G sub 3 or P sub3 and。The rest of that。系有。😔，And here's our block。Proroppagate signal。

Being generated by using our。Call on prop gates and generates。

 So we're not showing the gates here for。These calculations。

 but we know that G sub3 is a sub3 and b sub 3， so that would be an and gate。

And this propagate signal is an orgate。A of three or B of3。Okay， so those gates aren't shown。Okay。

 so so how does this work， It seems like thiss a lot of page down there， too。

 So did we really make it faster well。Let's look at the big picture here。 So what happens at first。

 So all of these， So A sub 3， B sub 3， A sub 2， all of those A's and B's are available at time t equals 0。

One gate delay later， either an ant gate or an or gate later。We have all of these signals available。

All of our call propagates and generators are available。After one， either and gateway regenerates。

Or two input orgate delay。For propagates。And so those are available one gate delay later。

We get all of those signals。Tea。😔，Tea gate， right， T and or orgate。Okay。What happens next， Well。

 after we。That one day delay。Then， well， this is， this isn't the critical path， but this is。

We go through one， two， three， four， five， six。6，2 input foot gate delays。So6，2 input gate delays。

Later， we're going to get。Or all of our。Block generate signals。 So not just G3 to 0。

 This is for all of them， right， G3 to 0。G7 to 4。G11 to 8。G blah， blah， blah， blah， right。

 all of these block generate signals and turns out the property signal property that block property signal is just calculated faster。

Okay， so we get you know one gate delay to get to here。1，2 input gate delay。Yeah。six。

Two input gate delays to get to。Are all of our all of them， not just for this block。

 for all all of these blocks。Profiate and generate signals。

And now we can calculate the carry out of that of that block so we can say， well， I have this signal。

And I have my。Right， I have my block generate signal， my block property signal。

 Now it's going to take just a。Well。Two gate delay。

Two two input gates delay to get through this and or the way of calculating。This block。Carry out。

 So this will be this carry out is going to be C sub 3。And then it's going to be C sub7。

That's going to be the next one， season 11。That's going to be the next one。Ceason 15。C，18。嗯。

Next we C 19。C 19。You， reset that。C 19。C 23。And C 27。And actually， C31。

So then we're going to calculate just through these two input gauges because times t equals0。

 we start here。Tequals0。Tals one gate delay we get here。One plus。Six gates。

 so to equals seven gate delays， we get to all of our block propagate and generate signals and now those can speed through because we have all those these are happening in parallel。

 we get all of our block propagate and generate signals for all these four bit blocks and now it speeds through and calculates these block。

😊，Carryouts， C3， C7， C 11， C 15， and so on。And so let's this look at this graphically。

And that's all we need， right， because so C， this is that first C。Speeds through here gives us C3。

C3 goes out。Here， right from that block。It becomes a C into the next block， C3 produces C7。Great。

 C7 comes out， goes into the next block。😊，All these signals are already generated。

 so they're just waiting for the C7 and this block。Carry signal to come in， C 7 goes out。

 produces C 11。See 11 comes in right， the next blog。Quickly produces this two gate delay。Produces C。

15。And so on。Okay， so。Talk about these steps， let's review on step one， compute the column。

 property and generate signals。Compute the。Block， propagate and generate signals。

 in case for four bit blocks， but generally for k bit blocks。

And then the C and propagates through eachbit propagate generate logic。And， you know， meanwhile。

 these the ripple cararys。At the top are also producing the sumbits。

And then the last step is actually we have to you know。

 right even though we get that carry pretty quickly for that leftmost or most significant。

4 bit block or cable bit block。 We saw have to compute the sum bits。

 That's what we're really interested in。 We're just dealing with the carry because that's the slow path。

 So we still have to actually ripple through that last。Cabit block。To compute the sums。And so。

We're going to compute our G's and P's or generate some prop gates for columns using and and or gates。

G surviveize。Pacea bi。And then we're going compute for each of the。

Cait blocks this happens in parallel right， this happens in parallel。

 this happens in parallel that's where we're gaining here is we compute the column and block generate andropate signals in parallel。

😊，And then we're going to。Speed through。These。Last two gates。To quickly calculate these。Block。

Block carry out signals， C sub3， C sub 7， C of 11， C 15。And then this last one， right。

 we finally get our last carry in here for that last block。Or C 27。Comes in here。And， well。

Now it has to。 We still need to。Rriipple through these lost for some adders full adders to get。

A actual sun beds， right some。For last for last four bits。And so here is that picture again。

It's going to take， well， let's， let's figure out the delay。

 So it's going to take one gate delay here。So T gate。

 one gate delay plus six gate delays to get to our for all of them， remember not just for this block。

 but for all of these。We're calculating these in parallel， so it takes one plus 6，7。

And then it's going to speed through。Two gate delays。So we got， you know。2 plus 2 plus， blah， blah。

 blah， for each of those。 And finally， guess this last block。

And we have to do the flat latter delay for that。 It's okay times。Tea full ladder。That last block。

And so we can calculate the delay， it's a little more complex。

 but we have well the delay to generate the。ProThe individual call propagate and generate signals so TPG what we're calling this。

 we know that's just one gate delay。One，2 input gate。Either an an gate or an or gate。

The delay to generate， the block profits and generates。What's this next。Amount。

And we know that that's six to input8 delays。In this case， because we have a four bit block。

 but maybe it'll be different for different caveB blocks， but in our case。

 six two input blocks are input gates。😊，And then。N over k minus1， we had 32 and 4。

 so 32 divided by 4 is eight。in-1， we had seven and or gates。And so it's going to go through those。😊。

Right， those first seven。 and then when it gets to the eighth block。Right， that's great。

Go through those and or gates when it gets to the eighth block。

 we get our C in this case C27 coming in。So it's going to go through seven of those， one， two， three。

 four， five， I let and draw them。6，7。And finally， when it gets to that last block。

The critical path is going to be through。Are full ladders。So we're of K full ladders as we generate。

Rriipple through those last four adders。And generate the sum。And so our equation is。

Delay of a carry look ahead at her the critical path is TPG plus TPG block。

Plus n over k minus1 in our example was7。Through the and ors， calculate those。

 make the final calculation for the block carryouts。And then the rippling through the last。

Group of Kbit blocks to produce the sumbits or K times T flat。

So an Nbit carry head adder is generally much faster than a ripple carry adder for n greater than 16。



![](img/9f55db7e773cf6c4a796c32056ee58e4_2.png)