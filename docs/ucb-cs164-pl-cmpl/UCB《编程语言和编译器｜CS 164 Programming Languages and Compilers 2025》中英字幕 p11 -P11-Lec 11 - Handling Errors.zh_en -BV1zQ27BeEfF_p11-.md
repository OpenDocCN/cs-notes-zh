# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p11 -P11-Lec 11 - Handling Errors.zh_en -BV1zQ27BeEfF_p11-

Alright， hello， everybody。 Let's dive back into programming languages in compilers land。

 I think we've got some fun stuff to chat about today。

 something we've been kind of leading up to for a while。

 So just as a quick reminder of where we're headed today and sort of what we've been thinking about this week I wanted to remind us that we've been thinking about the heap。

 right， we got introduced to one of our new cast of characters， the heap today。

 we're also going to be bringing in some thoughts about control flow jumps。

 We're also going to be thinking about what correctness means for us。

 and we're gonna bring in a quick discussion of static types and dynamic types。 Finally。

 real quick types and type checking。 So that's what we're thinking about today。

 but before we dive in on all of that I want us to quickly remember where we were on our last session because we hadn't quite finished it and we're gonna have to go ahead and wrap that up but also because it is helpful for us to review things on multiple days。

 So let's go ahead and think for a moment again about what。😊，We had decided to do with pears。

 in particular， we had decided that the thing we were going to do was store pears on the heap。

 So let me erase some of these things that we had added on here。 Can I maybe。

Let's see if we can get rid of that and。That。🤢，O。So what we had decided we were going to do。

Was we were going to go ahead and store the item associated with the lefthand side of our pair。

 right we're going to put that in the first available slot on the heap。

 So whatever is the next slot that we have available to us， we'll put that there。

 And we decided whatever is associated with the second item in the pair。 Okay。

 that's the thing we're going to go ahead and put in the second available slot on the heap。And then。

Because right at the end of the day， we have to have something that represents our value。

 We have to have something that represents it inside RA X。 We said to ourselves， okay。

 the way that we are gonna to make sure that even though RA X is 64 B。

 And even though this is clearly taking up2 64 B slots。

 The way that we are going to go ahead and get something into RA X。

 which again is only 64 B that represents the pair。

 the way we're gonna to do that is by basically storing a pointer to the first available slotlaughters。

 the slot associated with that first item from the pair。

 So that was the first available slot at the time that we started storing the pair。

 and it is the place where the pair will begin。 and we will know exactly how we have it laid out in memory。

 so we will know to look at those 16 by right， the first 8 by being that first value。

 the second 18 B being that second value。 sorry， the second8 by being that second value。

 we will know that that's what we've got to look at in order to find our pair。😊。

And then we had figured out at thetherearian there。

 We didn't get quite around to actually implementing it in our compiler。

 We had figured out that we were also going have to go ahead and apply a tag at the end of that。

 because we figured out that because all of the addresses where we might start storing a pair。

 were're going to be multiples of 8， right， because， again， we're only doing these 8 by at a time。

 because they're gonna be multiples of 8， the last three。

For all of our binary number representations of those addresses。

 the last three little slots were always going to be filled with zeros。

 And so if we just left it untagged， our compiler would say， yup。

 that looks like a number because as we may recall。

 those last two being zeros indicates to our runtime that we are dealing with a number。

And so that's where we had landed。 And in fact， we figured out that this was pretty convenient for us that it ended with those three zeros because it meant that we are able to go ahead and put a tag there without actually overr any of the stuff that we need in order to actually get back to the memory address we're trying to reach right。

 As soon as we start messing with this bit。 now we're overwriting something that we're actually going need in order to find。

 you know， this slot。😊，Are there questions about this overall scheme where we mostly remember what we were up to on Tuesday？

Okay， cool。 In that case， I'm going to bring us back to compiled dot Ml just to see what that looked like in。

😊。

![](img/486d356379c8e4a4335b389f05134692_1.png)

Our compiler。 And do remember that we didn't completely finish implementing it。Oh。

 I didn't plug that in。 well that will make it a little slower or won't it。

 so let's plug that in and then we can see it。

![](img/486d356379c8e4a4335b389f05134692_3.png)

Success， slow success， but success。 Okay， So here we go。

 This is what we had done to implement pairs so far。 We said， okay。

 the first thing I'm going do is I'm gonna to get the value associated with E1， our left item。

 I'm going get that into R X。 fantasticastic。 Now， I'm going to go ahead and save that in the next available slot on the stack。

 Just temporarily while I go ahead and get that second value。

 So now I'm getting the value associated with E2， which is to say the right item of our pair。

 fantastic， we've got that represented inside R X。 Let's go ahead and grab out the thing we saved before the thing representing E1。

 let's put that inside R8。 so that now we have our two values of interest inside R X and R 8。

 we are now ready to move them into the heap。 So we said let's go ahead and say wherever we have our next available slot in the heap。

 right， So remember that we are using the register R D I to keep track of our next available slot on the heap。

 So we said whatever sits at that spot。 That's where I want to go ahead and put the first value。😊。

RightSo I'm going to go ahead and take E1 and put it at that first available slot on the heap。

 And then the next thing I want to do is take whatever is associated with that second item。

 the right item。 And I'm going to put that in the next available slot on the heap。

 which is to say the original slot， but plus 8。Once I've done that。

 I'm going to go ahead and indicate by updating RDI that we should not overwrite the things that I just put there。

 I'm going say the next available spot on the heap is now 16 lower。

 That's what we've got right there。 And then this move is sort of the interesting thing。

 This is where we're doing something that's a little bit different from anything we've done before because what we're saying is that now what I'm going to have inside R X that represents my value is an address。

 right So yeah， it is still just this 64 bit thing that's sitting in there。 But it is an address。

 I know that it is an address。 It is pointing to a particular spot on the heap。Questions。Okay， great。

 So now we're going to do our first understanding check。 I don't think it will be super surprising。

 given what we've just talked about， But let's double check。 So here we go。Oh。

 we got a lot of stuff in here。We're going to compile and run our first little pair here。好。

We've got a wacky number there。 I want you to discuss with someone nearby。

 Why do we have this number， I was expecting to see pair1，2， what's going on， Turn to someone nearby。

Alright， to help us make sense of us， I'm going remind us of the changes that we made to the runtime on Tuesday。

 So there's only one really big change， but we have several smaller changes to support it。

 So if you remember what we used to have inside print value was just this， right。

 we knew that the two types we could have were the numb type and the bo type。

So we have now added a new one， right？ So now we know that we can have this pair type。

 And so if we go ahead and we， you know， zero out everything except what we've got at the the sort of three right most bits。

 And then we check if that is the pair tag。 That's the situation where we say， okay， got it。

 we are dealing with a pair。And now stuff gets a little bit wacky right because previously every time we got a value as an input to print value。

 it was that value itself that we wanted to print in some way。

 right And now this has changed because in fact， we know that that is an address right And so what we are going to do is we're going say yeah。

 yeah， this is a 64 bit thing， but I actually know that this is a pointer to another 64 bit thing。

 And I want you to treat it as a pointer to another 64 bit thing and then this last star is saying and in fact I want you to go to that memory address and bring me back whatever is there。

And that's how I'm actually going to get the value associated with the left side of the pair。

 And I do the exact same thing for the right side of the pair。We again。

 have to take out the pair tag， but pair tag plus8 this time because we're going to go ahead and go to that second slot where we have stored the second part of the pair。

And so then we go ahead and we do sort of the normal stuff where we're going ahead and printing our actual values。

 But it's for these values that we've gone ahead and retrieved from the heap。 Now。

 what is the heap for us， Well， if you recall we did this thing where we said please go ahead and malloc me some space If you remember sort of the last time you fought the Java heap right and you said。

 oh， it's not giving me enough space， this would be the place where you would change that right this is exactly the kind of place where you change that。

 you'd bring this number a little bit higher because this is just saying get me this much memory。

 I'm going to do something with it And so when we go ahead and provide this argument to entry。

 remember that entry is the thing that we are actually implementing with our assembly when we go ahead and provide that argument to entry。

 what's happening is because you know I know I went I look at the C implementation。

 I know that what it does with the first argument is it puts that value inside RDI I know that what this is actually going to do。

Is put this pointer， this pointer to the space that we are going to treat as our heap。

 right the first available slot on that heap， it is going to go ahead and put that address inside RDI。

 And so that's how I've gotten everything set up in such a way that then once we are actually executing entry。

 I can trust that that first thing that RDI is going to point to is going to be the first available slot on the span of memory that I'm going to be treating as the heap。

😡，So I think at this point， we probably we look at this and we say， well。

 it really looks like it should be able to print out a pair。Right。

If I'm going through and I'm going ahead and looking at， you know， the heat mask。

 I'm I'm sort of just taking a look at those last three bits。

 And I'm seeing if those last three bits are， in fact， showing me the pe tag。

 I should be printing out something that looks like a pe。But it turns out we're not。 So， again。

 let's take one last look at what we haven't compiled M so far and see why。

 Why do we not actually see a pair right here。30 more seconds to discuss。All right。

 does anyone want to yell out what I've done wrong， why we're not seeing？Pair represented。

We didn't tag it right。 So if we go ahead and just leave that memory address inside R X。

 which is what we're actually doing right now， right， all that's happened is we've gone ahead。

 We've put some things inside the heap。 But then we just copied over whatever was originally in RDI。

 So the address pointing to that first available slot。 We copied that inside R X and just left it B。

😊，And remember that our compiler is expecting that anything that ends with two zeros is a number。

 That is the number tag。 And so when it is going through the runtime and saying， okay。

 let's look at those last two values。 And let's see if those are both zeros。 The runtime says yes。

 they are。 And we go ahead and print it out as though it is a value。 So this is actually。

 the address in the memory on my laptop where we have stored the first item in that pair。

 That's what this number actually represents。 So let's go ahead and fix this up so that we can。

 in fact， show it as a。😊，Pair， instead of just as this number that actually we know is the address。

 So let's go ahead and add on that tag。Okay， so now let's make sure that has fixed up our issue。

And it has we now have a proper looking pair where we are hoping to see a pair。Okay。

 are there questions about that。Yes。Great question。

 Do we need to remove the tag when we use that pointer， Absolutely， right， Otherwise。

 we're gonna go to some weird spot。 that's sort of that plus2， because our pe tag is2。

 So if we go ahead and look at what we are doing in the runtime。

 what we are actually doing right here is when we are saying。

 please go to this spot and memory and get me back whatever was in there。

 We first subtract that pair tag。 So yeah， that is exactly what we're doing。😊，Oh yes， sorry。

 let me just scroll up and show。The tag。 So this looks pretty much a lot like what we had for numb and bo。

 The only difference is you can see that these are actually。

 I've called this heat mask instead of pe mask because we are going to have other things that we store on the he eventually。

And we're going to use the same mask for those。Other questions were feeling pretty good so far。



![](img/486d356379c8e4a4335b389f05134692_5.png)

Okay cool。 I want to have us do another couple quick reflection questions。

 So we have now fixed our implementation for pair。 It is now good。

 So one thing I want to ask about is we do this thing where we get the value associated with E1。

 We put inside R E X。 And then we temporarily store that value on the stack。

 So why is it that we don't at that time just directly put it into the heap。😊。

Go ahead and discuss with someone nearby for about a minute。Okay。

 does anyone want to suggest a reason why we might not want to immediately stash this value in the first available slot on the heap？

I love it。 Yes， so that's exactly the deal， right。 So say that instead of moving it temporarily onto the stack。

 say that instead we immediately wrote it into that first slot of the heap。 that could be fine。

 We could then also update R D I to make sure it wouldn't be overwritten。

 And then we could go ahead and use whatever other parts of the the heap we end up needing in order to actually get the value associated with E2。

 right， say that E2 is itself a pair。 We might be writing a bunch of other stuff onto the stack。

 or sorry onto the heap。 That could be fine。😊，Could be fine。

 but we'd have to do a bunch more bookkeeping。 And we would have to change the way we are laying out pairs right now because right now。

 we are saying that， okay， it's gonna to be the thing on the left。

 followed by the thing on the right。 If instead， we have the thing on the left and then a bunch of other stuff。

 And then the thing on the right， we have to do some other bookkeeping。

 We'd have to do some other wacky stuff。 So this is just a design decision。

 but it's a design decision that lets us do the scheme we came up with where we make sure that they're side by side。

O。I now want to go ahead and have us real quick implement left and right。

 since those were the only parts of pairs that we hadn't actually finished up last。Episode of CS 164。

 So let's do that real quick。 So at first， this looks probably pretty straightforward。

 We're doing our usual thing。 We're getting the value associated with E inside R X。

 I want you to go ahead and take about 30 seconds to discuss with someone nearby Now that we have this nice sort of memory address tagged memory address inside R X representing our pair。

 presumably it's a pair Now that we have that in R X。

 What should we do in order to grab out the left thing。

Guessing we're going to want to move something into red rocks。Alright。

 hopefully we all came up with the idea to go ahead and take advantage of that memory address that we now actually have inside Re racks。

 So let's go ahead and do that。Remember that we have to take off that pair tag。

And then we should be able to go and go into that slot in memory。

 right So this is just saying I want to go ahead and access a particular spot in memory。

 The spot in memory that I want to access is the address that is currently stored inside R E X。

 But first subtract off that pairt。 let's do a little offset from that。

And we're going to do a very similar thing to implement right。

 But instead of just taking off that pe tag， we have to take off that pair tag and then add 8 because remember that's going to be that second slot。

So let's make sure everything looks good when we run it。All right， we're getting out our left item。

 let's make sure we can get out our right item。We can。And we have now， in fact， implemented pairs。

 and even depending on how we actually choose to use them， we can have lists， right。

 So this is basically a list of two followed by one。O。We have pairs implemented。

 do we have questions？Oh， can we have a pair on the left side， absolutely， let's do it。So。

 I think this is。This question。So let me go ahead and do it with the proper syntax， no problem。Yeah。

 so we can also use this to represent trees， we can do all kinds of wacky stuff。Okay， cool。

 I'm gonna to have us walk through some examples because I know， you know。

 the heap is still kind of new to us。 So let's go ahead。And take a look at the generated assembly。

For some sample programs。So here we are。 This is the exact same program we just saw。

 We're going to go ahead and grab the leftmost item of a single pair。

 I'm going to highlight it for us to represent which part is related to which part of the program。

 It turns out most of this is going to be related to one part。

 So the part that's actually related to left is just this bit at the very。

 very end and all the rest is going to be related to actually constructing our pair that we are going to access。

So let's highlight all that bit that way。ok。So the very first thing we're gonna do。

 we're gonna get our runtime representation of one inside R E X。

 I feel like that's always the first thing I say， right。

 So our runtime representation of one is actually4。 So let's put that in there。 Fastic。

 We are now gonna go ahead and store that a little bit， to reuse later。

 So let's go ahead and put that over onto the stack So we can reuse it later。 Great。

 Now we're ready to overwrite what we had in R E X。 Let's put 8 in there。😊，Fantastic。

 we've got eight in there。 We are now ready to go ahead and move what we had just sewed away in the stack。

 Let's put it into R8 so that we can play with it so let's put that back into our register。

 so we can actually do stuff with it。 And now we are ready to start building up our pair in memory on the heap。

 So now we're going access the position currently stored in Rdi so we can read from Rdi。

 that the next available slot is this one right So I'm just going draw a little line to represent that that's how we're figuring out where to put it That's how we're figuring it out。

 So let's go back to our original color and let's put whatever we have in R8， which is to say4。

 let's go ahead and put that in the first available slot on the heap。

 And then let's go ahead and put what we have an rex， which is to say 8 in the next available slot。

 So that is our representation of our pair。 but we're not quite done with pair stuff because so far what we have in rex is still just the value 8。

 That is not what we should have in there。 So let's go ahead and copy what we see right here in RdiI。

 Let's copy that。Into R X。 So now we've got zero there。 Great。

 I'm going now like just for convenience， just to sort of write it out for us so we can think about us。

 write it out in binary。 But remember， I'm just writing things in binary versus decimal just for convenience。

 But so there we go。 We've got something written out in in binary that's going to represent what we actually have in R X。

 So this is just that， right。Great， now we are ready to actually tag it。

 So let's or it with that tag。 And so now what we'll have coming out the other end is this。

We are now ready to go ahead and increment RDI to make sure that no one overrites what we have put in here。

 right， We no longer want the future， the rest of our program to be messing with those slots。

 So let's go ahead and say so by crossing out what we currently have in RDI and writing in 16 instead。

Okay， we have now completed our process of making a pair stor it in memory and representing a representation of it inside R A X。

OExcept did we tag it。 Yeah， we tagged it。're。 We're good。 Sorry for a moment here。 I was like。

 did I run the wrong version。 No， we're good。 We have tagged it。

 We can see that the pair tag is showing up right here at the end。

 And so now when we go to actually do the thing associated with grabbing out the left item。

 What happens。 Well， we say I want to move something into。

 the thing I want to move intox is remember that these square braces indicate accessing memory So the way that we're gonna access memory we're saying find me whatever is at a memory address associated with this computation。

 So what is this computation。 This is saying whatever is inside Rx。 So this value right here。

 go ahead and do that minus this value So let's take off that pair tag basically。

 which is gonna bring us back to this。 So go ahead and do that computation。

 and then based on seeing the square braces there， go ahead and treat that as a memory address。

 and bring me back whatever you。d at that memory address， which is to say the value for。And so now。

 when we go ahead and update R X based on what we found at that memory address。

 we're crossing out that。 We're getting four， which is to say our one time runtime representation of one。

We have questions about how that played out or we're feeling pretty okay。

Maybe we'd like to see an example with multiple pairs in the program might help us think about yeah。

Supposed to like。So this question is saying when this was the value that we had stored in RA X。Right。

 when we were at。This spot right here。And we had this green highlighted value inside RX。

 What did that represent。So that was the memory address where we had stored the pair。

But we altered it， right， because remember the original memory address was just 0，00，0，0，0， right。

 because we can look at what is the memory address where we stored it。 And it's just that right。

 It's that value。 It's that item that we had stored in R DI。 It's just that address 0， right。

 And so that's what we had stored in there。 And we said， okay。

 this is looking like a good representation of our pair except that we had better actually put that pair tag on there so that we know to treat that as a pair。

😊，The address of the left element of the pair， exactly。Lovely， okay。

 let's go on to one more of these examples to run through。

 unless are there other questions about this one before we， we see another one。😊，Co cool， all right。

 let's see another one。So here we've got one where we've got a nice nested pair。

 And so we're gonna to see how this actually gets laid out in memory。

 which I think will be quite good practice for us。 And in fact。

 I'm gonna give these some little names just because I think that's gonna。

 going help us think it through。 So let's call。😊，This pair。A。And let's call this sort of outer pair。

 Let's call that B。I think that will be helpful as we're talking about it。Okay。

 so let's start going through。 Please， please， please。

 I know I'm not looking up while I'm writing these out。

 but call out if we need to pause and talk about one of the steps I'm taking。 just yell at me。

 So okay， the first thing we're gonna do is put4 inside R A X。 our traditional opening。 Great。

 we've done that。 We have represented one inside R A X。

 Now we're gonna go ahead and staff that away for a moment。

 So let's go ahead and put it over here on the stack just to save it for later。

 We have now completed this part of our program。 right， That's what we have done so far。Great。

 we are now ready to start messing around with that second pair， which is to say pair A。

 the one that I labeled pair A。 So let's start working on building that up。

 We're going to go ahead and cross out what we previously had inside R E X。 We'll pit 8 in there。

 And now， again， we just want to stash this for a while because we're going to go ahead and do some other stuff。

 So we'll put that in the next available slot on the stack。😊，At that point。

 we're ready to grab the right most value， the right value of our pair A， our second pair。

 So let's go ahead and put that inside RAX。Great， we've got that。 And we are now ready to say。

 let's start working with these。 I'm ready to start putting things into the heaps。

 So let's retrieve what we had put away on the stack。

 Let's retrieve that and actually put that into R8 so that we can start messing with it。

 So let's put8 right there。😊，Great， so now we have one of our values associated with the pair inside R E X and one inside R 8。

 We're ready to go ahead and put them onto the heap。 Now。 Now。

 notice that we are storing pair A on the heap before pair B。😊，Right。

 so when we had that little thought experiment earlier， where we said。

 why don't we just go ahead and put that first value directly on the heap。

 This is sort of the thing that we had in mind when we made that decision。

 So let's go ahead and put what we've currently got inside R 8 in the first available slot。

 So that's gonna be 8。 and we'll put the thing that we have inside R X and the next available slot。

 That's going be our value 12。 And so now we have gone ahead。

 And at least as far as the heap is concerned。 We have represented our first pair here。

The problem is now just to get some representation of that pair into R E X。

 So let's go ahead and proceed with that。 So now we're going to say， okay， whatever is an RdiI。

 So this value 0， right， the place where we just stash that pair。 That's what's an RI， R DI。

 Let's go ahead and put that inside R E X。Great， we've got 0。 If we go ahead and give the。

 the tag onto it， we'll end up with something more like。Something like that。 great。

 And now we're ready to go ahead and say， okay， don't overwrite what I've put in there so far， right。

 so I now want to move R DI to point to here。So that's the change that we've made right there。

Questions so far， we have now finished representing pair A。Hopefully。

 that looks a lot like what we saw in the last one。 But， of course。

 now we're about to make another pair that also references this pair。So far so good。Alright， cool。

 Let's keep proceeding for now。 So now we're saying， okay。I've gone ahead and gotten the value。

 Right， So we're back into thinking about this larger pair。

 And what we're thinking about now is we've gone ahead and gotten the value that represents this right region of this pair of the outer pair。

 So this is the rightmost thing from the perspective of pair B。

 We've got something that represents that inside R X。 interesting， weird。

 We've got this address thing that actually represents the right of the pair。 Co。

 And so now we want to go ahead and retrieve what we had saved off to represent the left side of that pair。

 So let's go ahead and grab that back out of the stack。 We'll cross out what we currently have in R8。

 and we will put in4。Cool， we are now ready to build up our second pair in the heap memory。

 So let's do it。 So let's go ahead and take what we have inside R 8， which is to say the left thing。

 let's go ahead and put that right here。 That's the next available slot on the stack。

 If we look at where R DI is right now。 It's pointing to 16 right， So that's this spot。

 So this is the next spot where we can write。 We can't be writing up here anymore。 We use those。

 So weve got go ahead and read off of RD I to figure out where to put it。 Okay。

 we've put four in there。 We are now ready to go ahead and put the representation of the right hand side inside the next available to slot。

 And that is gonna be this。😊，Right，We've got this value that represents the pair itself。

Just being represented right here。Okay， great。 So now we've gone ahead and we've represented a second pair here in memory。

 right， so this all represents an additional pair。At this point。

 we're gonna go ahead and move a representation of that second pair pair B。 Let's move that into R X。

 So let's cross out what we currently have inside R X。 Let's write what we currently have in R D I。

 right， That value 16。 So we'll have 16 there。 I'm gonna be honest。 I'm not gonna go wait。

 now I can do it。 Okay， so let's go， let's do our little binary thing。 Let's write this out。

 So this should be O B1，1，2，3，4。 That's the binary representation of 16， right， think it is。Yes。

 that's the runtime representation of that value。 fantastic。

 So we have gone ahead and move what we have inside RDI into R X。

 Let's just quickly make it clear that those are the same。 Now， let's go ahead and tag it。

 So we'll end up with this。😊，Okay， great。 we've got it tagged。

 And now we're ready to update R D I to make sure we don't overwrite this pair， right。

 We have to make sure that any later he usage is going write down here and not up here。

 So let's go ahead and cross out what we currently have in R DI right in 32。 And now we are done。😊。

Do we feel happy with these cute little pes。We like it。Okay， cool。

Let us do one more little reflection about our pairs before we move on to our next topic for today。

 So I'm going to show us the compiler again， and I'm going to show us all of the parts of the compiler where we interact with the heap。

And the question that I want you all to think about together with folks nearby is。

 are we ever going to。Move back up the heap。Are we ever going to reclaim some of this space？

That we are claiming for our pairs。Go ahead and discuss with folks nearby。All right， hum。

 if you think that at some point we are going to reclaim some of this heat memory。Home。

 if you think we are not。Yeah， I totally agree， right。

 We can just look through and see what happens to RDI。

 and we can just read that off based on how we're interacting with that。

 And we can see that what's happening here is we are adding a number to RDI。

 So we are increasing RDI and we never， ever decrease it。

The only thing that happens is we keep saying， okay， I've used the slot。

 I've used the slot I've the slot。 I've used the slot and all of those stay around forever。

 This is very different from how we're using the stack we're talking about how in the stack。

 okay once we're done with this value that we save it on the stack。

 we're going ahead we're overriding and we've seen us reusing these stack slots。

 So this is quite different from how we've been using the stack And in fact。

 when we had that question about why do we need to know how big the thing is in order to put it on the stack。

 that was a big part of why Whereas with the heap， all of that is going to get tracked at runtime。

 So it's totally fine for us to not know in advance how much space we're going to need。

 We're just going to go ahead and keep updating RDI to do that。Now。This kind of weird， right。

 because yeah， we want programs to be fast。 But another thing we often think about is we want them to not use too much space。

 This seems like this could end up being a lot of space。 And so eventually。

 way towards the end of class at I think the last month or so somewhere。

 we're going to talk about our strategy for fixing this， which is to say， garbage collection。

Now garbage collection is always a tradeoff between spending time on it。

 right you spent a bunch of time on garbage collection versus spending space on it right so right now we have picked one extreme end of the spectrum。

 We are spending literally zero cycles on picking up garbage。 however。

 it does mean that we are spending a lot of space on it because we're just leaving all of all this he stuff that we put on there around for the whole rest of our program。

But we will circle back around and do something smarter。

 garbageb collection is actually one of the really cool areas that we get to talk about in class。

 because this is one of the areas where we still don't really feel like we have solved it。

 We think there are may be better ways for us to do。

 And so there's still active research on how can we do better garbage collection。

 Something like parsing like， everyone's kind of figured that out。

 We're not really worried about that。 But garbage collection It seems like we can still do better smarter stuff。

 So this is a cool area for us to talk about later。😊，So far， so good。Okay。So。

We are going to be doing some new implementation stuff real soon。

 But in order to decide what implementation stuff we are going to do。

 I actually want us to contemplate kind of an interesting program。

 It wasn't super interesting before we implemented pairs。 But now that we've implemented pairs。

 It is kind of interesting。 So let's go ahead and consider this program。

So what I want you to do with folks nearby right now。Is predict。

When we run this program with our compiler， what output are we going to get。

 when we run this same program with our interpreter， what output are we going to get？

Go ahead and discuss。All right， go ahead and hum if you think the compiler is going to say true。

How if you think the compiler is going to say false？Okay。

 go ahead and hum if you think the interpreter is going to say true。

How if you think the interpreter is going to say false？Alright， let's go to our answer key。

 Let's find out。 right， So here we go。 We've got our compiler。😊，Okay， false。 I think， you know。

 we all predicted that this all makes sense based on what we've just been talking about right。

 what's going to happen is we'll go ahead， we'll construct this pair。

 We'll put it at a spot on the heap。 The thing that represents this will be an address pointing to that pair。

We'll go ahead。 We'll make another pair。 We'll put that someplace on the heap。

 We'll go ahead and construct something that will represent that。

 That will be something that's basically an address pointing to that other place on the heap。

 Then when we do equality， right， we can see that equality。

 we're just going ahead and using our little。Compare instruction， right。

 just using our little compare instruction， which all it is going to do is subtract the one from the other and see if it's 0。

 So when we subtract the one memory address from the other and see that it's not 0。

 there are different memory addresses。 Okay， We say that looks like that is not the same thing。Cool。

 let's try it with our interpreter。Do the exact same program。Ha。Well， that's pretty weird， isn't it？

RightAnd so if we remember what our interpreter was doing in order to implement it， if you recall。

 we talked about the difference between single equals。

Right structural equality and double equals physical equality。

 And I talked about the fact that we are not really going to be using O Camll's physical equality in the context of this class right And so what we just implemented over on our compiler was exactly that right。

 physical equality。Where we're going ahead and saying just like what are the two addresses that we're seeing。

 are they the same？Whereas what we are actually using in the interpreter。😡。

Is this structural equality？So now， finally， finally， finally， like I sort of。

 I talked us through those cases where there were cases that the interpreter was not giving us an answer。

 And then we were。 And I was like， that's a little bit alarming。 But technically。

 our definition of correctness is just sort of correctness for the cases where the interpreter is giving us an answer。

 But now we have a situation where the interpreter is giving us an answer。

 The compiler is giving us a different answer。 This is a bug。

 We have now found an actual instance of a bug。 So we've got to fix this。 What do we do。

 I want you to discuss with folks nearby for about a minute。 What can we do，All right。

 give me some ideas。How can I fix this？I love it。 Yes。

 so the thing that we should actually do here is obviously match what the interpreter is doing。

 Like we've always talked about it as our interpreter is our reference solution。

 We are trying to match its behavior。 The thing that we should do is make sure that our equality is traversing through the pairs。

 maybe recursively because you've got to keep going going if they're nested and figure out if we've got the same values。

 turns out doing that is incredibly painful right now。 But in a couple of weeks。

 we are gonna have functions。 And at that point， that is actually what we're gonna do。

 What other solutions do we have before we get functions in a couple weeks。😊。

I will say if that solution is exactly what actual scheme implementations do， right。

 actual scheme implementations do exactly that。 They go ahead and they traverse through using functions。

要。Yeah， so the other thing we could do instead of like changing our compiler to match our interpreter。

 we can actually change our interpreter to match our compiler。

 It turns out that might be a little bit harder than we might originally think。

 So I'm going to run a couple of programs just to sort of show why that might actually be kind of complicated right So here if we do let's just use Ocal's physical quality right here。

Okay， great。 true does seem to equal true。 On the other hand， what if we do， remember， we have our。

 our little value type。 So let's go ahead， do Boolean true。好。So that's kind of weird。

 So even trying to do this thing where we actually force the interpreter to behave like the compiler could actually be kind of wacky。

 In fact， we've just learned something right here， about how ocael is implementing the types that we introduce right clearly。

 Ocael has actually stored this one somewhere on the heap stored this one somewhere on the heap。

 And then when it went ahead and did that comparison， it said nope， not the same spot on the heap。

 weird， right in contrast to what we did when we implemented booy and true and booley and false So as we had these are the bits we're going to put into the register。

 And so then when we go ahead and we compare our representation of true to our representation of true。

 it says yep， those are the same bits， good to go So actually even getting this to line in the other way is going to be a little bit wacky So the solution that we are going to take in the long term is in fact。

 going to be to traverse the pairs in order to do structural equality to match what we have in the interpreter。

 but in the short term before we get functions， the approach we're going to take is to limit this two numbers。

 very unsatisfying。So it is going to mean that we have to do some interesting new implementation work。

 which will be our topic for the last half hour here of class before then please take your five minute break and I'll put some thought provoking programs up on the whiteboard until then。

Hello。Absolutely。That。We ran that on the internet。So we didn't actually use the interpreter to run this。

 We were just creating a value that had type value and then just using O Caml's physical equality directly on those。

 So we didn't run like interpret X or interpret anything。 We were just comparing what would happen。

Does that make sense， Yeah， so those are the kinds of values that we would be passing around inside our interpreter。

 but we didn't actually use our interpreter to do that。Yeah。

 that's why if we just went into here and changed this to a double equals。

 it would not actually behave the same way as our compiler even then。

Because our physical equality isn't going to be the same as oh candles of physical equality thumbs up。

Alright， let's come back together and consider these interesting programs。

So these are interesting because of how we have defined correctness for our compiler。

 So what we said way back when was when our interpreter produces a value。

 when our interpreter doesn't err up。Then the compiler is obliged to produce that same value。However。

 there are a bunch of programs for which the interpreter does not produce an output value。 in fact。

 all of these are examples of cases where the interpreter does not produce for us an output value。

 And so according to sort of our contract with ourselves。

 the compiler is allowed to do whatever it wants for all of these。 right， This is undefined behavior。

 the compiler can do anything。 and that's totally fine。However， even though it's sort of allowed。

 according to our definition of correctness， I'm personally not finding that super satisfying。

 I would love it if the examples that we've got right here if they produce an error in interpreter land would also produce an error in compiler land。

 but currently they might not。 So what I'm going to have us do is go through these one by one and knowing that the interpreter produces an error I want you to go ahead and predict what the compiler is going to produce。

 so go ahead and consider the first program first。😊，Feel free to chat with folks nearby。All right。

 does anyone want to register a guess， What is the compiler going to give us for this？

I hope this one isn't surprising。 I don't think it'll be super surprising。



![](img/486d356379c8e4a4335b389f05134692_7.png)

Let's go ahead and see it。 So here's what happens when we compile and run。 It says yep。

 that should be an exception， right， it doesn't know what to do with this， right。

 We're going go ahead and raise this exception right at compile time， right。

 You can imagine we're going through our compiler。 We're looking for the case where what we're seeing is a list where the first value is hello。

 right， We go through， this hello is this hello。 No， none of these seem to be hello。

 I have no idea what to do with this。 Okay， we're gonna to go down that last case where we raise bad expression。

So okay， I'm feeling pretty satisfied with that one。 Let's consider program 2。

 discuss with folks nearby。

![](img/486d356379c8e4a4335b389f05134692_9.png)

All right， did anyone want to register a guess， what do we think？



![](img/486d356379c8e4a4335b389f05134692_11.png)

I love it。 Yes， bad tag。 That is exactly what we see， right So if we see。

 we go ahead and we run add1 false。 we get back this weird string that says bad value。

 which if we recall what we were doing in our runtime。

 we were going ahead and we were checking if the tag was the number tag。

 We check if it's the boolean tag。 We check if it's the pair tag。 If it's none of those。 we get this。

 this thing that says， I don't recognize this tag at all。 And so what's happened is we went ahead。

 we got our runtime representation of false。 We ended up messing around with it in such a way that we screwed up its tag。

 And now it doesn't even look like a boolean value anymore。

 We get this wild thing coming back when we run it through the runtime saying bad value in all caps very scary。

Not super nice。 Don't like to see that。Okay， questions about that or we sort of remember， yes。

Should we allow this now， technically， again， according to our definition of correctness。

 absolutelyute， right， So this is undefined behavior。 Our interpreter said， hey。

 we don't have an output for this。 So compiler gets to do whatever it wants。 right。

 So technically officially sure。 however， it is really easy to trip up your programmers by doing stuff like this。

 So it is kinder， kinder if we do something to catch this kind of issue。 So technically yes。

 aesthetically no。😊，Okay， let's consider our next example。



![](img/486d356379c8e4a4335b389f05134692_13.png)

Going to highlight a similarity between these programs。All right， we got any guesses。

 what do we think？I'm hearing four， let's find out。



![](img/486d356379c8e4a4335b389f05134692_15.png)

Oh，4， this is horrible。 We did the same bad thing， but we did it in a way that that value never made it out to the runtime。

 so we don't even get that runtime error that we were getting before。 This is dreadful。

 We're just getting the value 4。So this is a weird thing， right， Like we've technically， again。

 allowed。 But boy， this feels bad。 We really would love if we。

 any time in the program that we encountered this thing， even if we never try to print it out。

 if any time we encountered this bad behavior in the course of actually running our program。

 We really， we should probably complain。 right， That would be nicer。 that would feel better to me。

 So right， let's consider that very last program。😊。



![](img/486d356379c8e4a4335b389f05134692_17.png)

All right， What do we think， What are we going get out the other side on this one。



![](img/486d356379c8e4a4335b389f05134692_19.png)

I'm hearing false。

![](img/486d356379c8e4a4335b389f05134692_21.png)

Oh， no， it is false。 This is terrible。 This time， we're doing the bad thing。

 We're continuing to immediately like that same value。 We do another bad thing to it。

 And we get out something that looks like I just a value in our language。This is dreadreadful。

 This is terrible stuff。 We don't like this。 This is not satisfying。 So， okay， today。

 we're going to go ahead and start looking for this kind of issue。 So let's open up。



![](img/486d356379c8e4a4335b389f05134692_23.png)

Our compiler， In fact， let's actually start in our runtime。 It turns out because we have this。

 this nice runtime available。 We have a pretty convenient way for us to start raising errors。

 So let's go ahead and make a little error function。Right here in our sea runtime。

You can see this right， Oh， you can't see this。 sorry， sorry， sorry。



![](img/486d356379c8e4a4335b389f05134692_25.png)

Now you can see it right。 Yeah， great。 I'm so sorry。 You gotta yell at me when I do that。

 So we're starting to to write out this little error function。 fantasticastic。 Let's print out a big。

 scary thing that says error right now， This is gonna be the only error that we can make。

 This is not the most usable programming language you'all have ever seen in your lives。

 I was the programmer。 I'll be pretty annoyed that this error。 It's not really telling me a lot。

 But there's enough for our purposes you'll have something nicer for homework。 Okay。

 so we're going ahead， we're printing out error。 It looks scary。 It looks alarming。

 And at the end of that， we say that's it for you。 program is over done。😊，This is the。

 the function that we now have available that lets us do errors。 Okay。

 so now let's go ahead and actually compile our runtime。Great， we've compiled it。

 We have it available。 Let's start actually being able to use this in our compiled program。

 So if you call way back when， where was it， Yeah， here it was， We did this thing where we said。

 okay， I'm trying to make available。 this entry thing。

 because I know that some other program that is to say the runtime is going need to access it。

 We're going do sort of the opposite thing here， where we say。

 I need you to know that there's this external thing error available。

 even though I'm not actually going be providing it， because remember our runtime is providing it。😊。

Now， real quick， I want you to guess with folks nearby in 20 seconds。

 why is error the string that we are actually providing here？20 seconds。Have we got it？

What if I named this function。Hippopotamus is a word that I do not know how to spell。

 Is it that My spelling is very bad。It just has to match what we put in here。 Right。

 So we're only putting an error over there because error is what I put over here。

 That's the only reason we are doing that。 Okay， great， so that matches。

 now we are ready to actually use this error thing some time。 So okay。

 we've been playing around with these add one examples。

 Let's go ahead and actually see our implementation of add one and see if we can take advantage of now having access to that to fix what's happening right here and add one。

 So， okay， we've gone a representation of some。😊，Into R A X。

 I want to make sure that that thing is a number。 Here's maybe something that I might do。

 And let's see if you are happy with it。So maybe I go ahead and what we have inside RAX with the numb mask。

Right， I say I'm interested in those last two bits。 Cool， We're ending。

 Let's go ahead and do our comparison， right， I want to see if what we have there is。😊，Our numb tag。

 I think that makes sense great。 And now if， if， in fact， it is not the number tag， right。

 if it's anything other than a number， I want to go ahead and jump to error。So。Look at this。

 Reflect on this。 Consider this for a minute with the people nearby。 Are we happy。 Is this good。

Al right， Hu， if we are happy。How if we are not happy？Yeah， I have to agree。 So on the one hand。

 right， the thing that we were coming here to fix。Is looking pretty good， right？

 We've gone ahead and we tried to use add one on false。 It gave us our nice little string air。

 very alarming looking。 lookss like we've done something wrong。 That feels great， however。😊，Hang on。

 That should be 9。Go ahead and discuss for 20 seconds。 What we do wrong。Alright， so hopefully。

 we figured out that in the process of。You know， saying let's just look at that number tag。

 We actually， we blanked out the whole rest of the number。

 And so what we ended up with was just the runtime representation of 0。

 That's really not what we want to be doing。 We want to go ahead and leave what is inside R A X untouched so we can eventually actually add one to it And we want to go ahead and do this check in some other register where we're not gonna end up messing with the actual representation of the number。

 It's not okay to just blow away what we've got inside R A X。 while we do this check。😊，So okay， this。

 once we actually run it， assuming I haven't messed anything up should work。

 Let's go ahead and make sure that copying it all over to R8 and doing it over there looks good。

We've got nine。And we're still complaining if we try to use false。 So that is looking pretty good。

So okay， right now， we've only done this inside Add1， but this is going to be pretty reusable。

 So let's make ourselves a version of this that we can just use over and over again。 So let's do。

And sure， numb。Right， because we want to ensure that it is a number。

 We'll go ahead and decide where we want to actually be doing it。And。

It should look a lot like that list that we saw a moment ago， except let's go ahead。

 And instead of always running it on R X， let's go ahead and copy in sort of whatever one we actually provide is our argument。

 And so now if we go down to add one， we can just use that。

So let's go ahead and have that be and sure none applied to。RX。And right now， only add one has it。

 but we can go ahead and do the exact same thing down below in sub1。

I want us to now consider how we would do it for addition， right？ So remember。

 if we go ahead and look at what's inside in Sherum。

 we're going ahead and blocking out everything that's an R 8， right？

 We are going ahead and actually messing around， blowing away whatever's in there。

 So let's go ahead and look at plus， And I want you to decide， can we use in Sheum here， if yes， how。

Discuss for。W a minute。All right， I think it looks okay right there。 right。

 We don't have anything inside。 all right that we're worried about there。And， in fact。Even down here。

 we haven't put anything inside R 8 that we're worried about blowing away there either。

 We do eventually start using R 8。 But as long as we're not currently storing anything inside R 8 that we're worried about overriding。

 we should be good to go。 So let's just test and make sure that it's true。

But we shouldn't run into any problems with using this。 So let's do。嗯。All right。

 it's now raising our error as we desire。And it can still do our normal edition， all looking good。

It turns out we can use a very， very similar approach to check for whether our arguments are pairs。

 So let's copy this over。Let's do。Insure pair。And the only thing we're going to want to change is instead of comparing to the numb mask。

 we want to compare to the heat mask。And the pair tag。

 And so let's go ahead and use that at least one place。 Let's maybe do it for left。

 Let's go ahead and do， and sure pair。Applied to RAX。Lovely， let's make sure that all looks nice。

And we'll do。Pair， let's do left applied to this pair。Great， that looks normal。

 what if we apply it instead to the number nine？Not so good。 Okay。

 so this is basically looking like what we wanted it to look like。

I am going to go ahead and string these checks throughout the class compiler sort of on our own separate time because it's pretty boring to watch me just sort of repeating the same process for all the different things。

 But even with that said， right， I am going to go ahead and do that work of sort of using these little helpers a bunch of places。

 we're still not quite where we want to be， because if you remember way， way， way back when。

When we made our little differential testing setup up， we had this setup where， okay。

 we can go ahead and run this on programs that do， in fact， produce values。

 But what if we do something like add one false here， right。

 which we intentionally want to produce an error， right， That is important to us now。

 What happens if we do Sorry， I didn't actually save this before， So let me actually。

Make sure that we can test that。 Test the test。Oh， it aired out because we did， in fact。

 test it on a program that errorss out， right， not super good for us。 We run into trouble there。

 So let's go ahead and fix that so we can actually use this even for things that should error out。

 So let's do let's mess with our interpreter first， actually。

Let's do something that basically just catches the errors。Program， string。String is output。

And then try interpret program in the normal way。But if we get a bad expression。



![](img/486d356379c8e4a4335b389f05134692_27.png)

Great。Go ahead and make it do the same thing that our compiler will now produce。

 We're going to do a very similar thing with the compiler。So。Here， where we had compile and run。

 we'll have compile and run error。And。Pile and run。That program。

 great now where our diF test was doing previously just the plane compile and run。

 Let's have it instead do compile and run error。Interp。air。And。Test this all out。again。

And now it saysGreat， so we are evilly able to deal with the situation where this is going to error out and we're able to see that both the interpreter and the compiler will air it out。

Now。Obviously， this is not the be all and all of errors。 As we already discussed。

 I would personally be pretty unsatisfied with these kinds of errors if I was a programmer with this language。

 but this does let us start to strengthen our claims about the match between the interpreter and the compiler。

 and therefore our compiler's correctness I do want us to consider one other program here before we wrap up for the day。

 So I want us to consider。If true one。Hello， hello。

What I want you to discuss for the next one minute is what will our interpreter do with this and what will our compiler do with this。

 Go ahead and discuss。All right， hum if you think our interpreter gives us one？Hm。

 if you think our interpreter does anything else？How if you think our compiler gives us one？😡。

H if you think our compiler does anything else？Fantastic。 We've all landed on the same answer， right。

 oops， open interpreter。Great， our interpreter says that's one。 looks like one to me。 I'm good to go。

 What about our compiler。Nope。RightAnd so what's happening here， right。

 This is this weird situation where this is going to error in the compiler， but not the interpreter。

 sort of the opposite of what we were talking about before。

And the reason is our interpreter is going through and saying， okay， well， what's the condition here。

 Okay， it looks like it's true。 I'm going to go down the true path and it never bothers to process anything right on this side。

 it doesn't ever look at hello hello There's no sort of first pass where it goes through and make sure everything is okay in the program。

 It's just tackling the parts of the program that it actually needs at any given time。

 And so it never bothers to look over there。 Where's the compiler， in fact。

 has to go through and generate assembly for the whole thing right。

 which means it also has to traverse this path and say I don't know how to produce assembly for this。

 And so I want you to all reflect over the course of your Thursdays。

 I'm sure this will be your favorite thing to think about on a Thursday。

The errors that we were raising today are they being raised at compile time or run time。

I'll leave you with that fun thought。 I'll see you all。 real quick。

 I am not actually gonna be here next Tuesday。 Our lovely T A Ia is going to bring a video recording of me teaching the same class in the past and play that for you。

 I tried to bring in a couple of guest speakers to to lecture for me instead。

 But they both fell through。 So instead， you get me from the past。😊，I will see you all soon。

And I'll be back next Thursday。

![](img/486d356379c8e4a4335b389f05134692_29.png)