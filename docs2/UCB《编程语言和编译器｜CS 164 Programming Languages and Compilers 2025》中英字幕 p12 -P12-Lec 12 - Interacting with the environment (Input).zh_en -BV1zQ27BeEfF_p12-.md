# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p12 -P12-Lec 12 - Interacting with the environment (Input).zh_en -BV1zQ27BeEfF_p12-

![](img/07aaf0bb71274df79471f6e41cfad2ab_0.png)

Alright， hello， everybody。😊，So welcome back。 today。

 We get to talk about a very exciting topic in the form of input and output。

 Before we dive in on that， I do want to take us through some stuff based on the drill。 So。

 as always， massive thank you for answering the drill。 Super helpful。😊。

The things that have've been coming up most in this last round of drill feedback is stuff related to how we're using memory。

 especially I think a lot of confusion or questions around sort of what goes in the stack versus what goes in the heap。

 So we're going to take a moment now to sort of reflect on what we're putting in the stack versus what we're putting in the heap。

 via a sequence of activities。 So let's see。If we can。Switch there。 That's not helpful。Let's see。O。

Alright， let's see。 How do we。Microphone。Well， allright， we can see。The question。

 while I play around with it。 This is our question almost around with how we actually see it so we can see it bigger。

 But right now， what I'm gonna ask you to think about is， when do we subtract 8 from the stack index。

 So when do we go through the process of saying， okay， stack index。

 Let's make it one iteration smaller。Go ahead and discuss with folks nearby for about 40 seconds。

And this question is not just a line number， although I think it will be helpful to look at a particular snippet。

 you can see that snippet off to the right， where it's one of the places that we're maybe messing around with the stack index。

 But I'm asking for the conceptual answer。Alright， so conceptually。

 when do we decide to subtract 8 from the stack index。What would make us decide to do that。I like it。

 Okay， so when we have actually used one of the slots， right？

 So the specific answer we got was when we started evaluating the second expression。

 And so in this case， that's exactly right， right， the， the thing that we're doing here in addition。

 is first， we are going ahead and saying， let me get the value associated with the thing on the left。

 Then I'm going store that in the stack。 And then I'm gonna get the value associated with thing on the right。

 Now there might be other things that would cause us to actually use a slot in the stack。

 But conceptually what's happening here is once we have chosen to actually store something in the stack。

 once we have chosen to actually use a slot。 That's when we go through this process of saying， okay。

 let me go ahead and make sure that my next compile ex call it's gonna have a different value for stack index。

😊，So we all comfortable with the idea that we update the stack index。We make it smaller。

 We make it point to a a higher spot on the stack when we have used a slot。Feels good。😊，Amazing。

 alright， so I'm gonna now have us think about。When do we add 8 to the stack index， And again。

 it may be helpful to look at the little snippet of the compiler I've included。

Go ahead and discuss with someone nearby。All right。So when do we。😔，Add。To stock index。

So I guess the simplest form of this question。Do we ever add to the stack index， Humph for yes。

Home for no。That's exactly right， right， So we never actually do addition here， but。

When we come back out of a prior call to compile X， right when we're。

 we're exiting a nested call to compile X， we may have a lower value there。

So in the case of the program that I have off to the left here。

 when we call compile X on the first operaand， we pass in our original stack index inside that call to compile X。

 we do go ahead and subtract date。 We do go ahead and use a lower value of the stack index。

 But when we come back out to that first call to compile X， right， the outer call。

 we will be back to having the stack index at the original starting point。

So even though we don't actually add to the stackg index， we do indeed come back to having。

ADifferent higher value for the stack index。 We go back down the stack。

Are there questions about that about the fact that we can actually get back to having a higher value for our stack index。

Even though we don't actually explicitly see addition with the stack index。Alright。

 sounds like we're feeling okay。 Oh， was， was that a question。No， we're good， okay。All。So， now。

A somewhat related question。We， we ran into the issue when we were working with pairs。

We realized that we didn't know。What size our pair value is going to have， right。

 So it could be that it's a pair that has。You know， a left operaran that's a number， a right operaan。

 that's a number。 And it's only going to take sort of two slots of our heap。

 Or it could be that one of those items， the first or the second is， in fact， another pair。

 And so then maybe it's gonna take four slots。 Or maybe it's gonna be a pair of a pair of a pair of a pair of a pair we didn't figure out。

What is going to actually be the size of a given pair。

 And this was a problem for us and ended up causing us to decide to put it。In the heap。So， why。

Why was it a problem for us。That we didn't know the size of the pair at compile time。

 Why did that mean that we couldn't put it on the stack。

Go ahead and take 40 seconds to discuss with folks nearby。Alright， so what are we thinking。

 Why do we think it might be a problem that we don't know the size of our pairs at compile time if we want to put them on the stack。

Yeah。Exactly， yes。 So this answer was， hey， we are updating this stack index at compile time。

 We are tracking where we are putting things on the stack。

 The exact offset inside the stack at compile time。

 So if we don't know the size of the pair at compile time， Well。

 how do we know what values to bake into the assembly， right。

 we are using that stack index to actually change the values that we put in the assembly。😊。

If we suddenly don't know how much space a pair is going to take， we're out of luck。

So taking a moment to sort of reflect and think about the situation we have here。

 The stack index that we're passing around。 that is being updated at compile time， not at runtime。

 It isn't the assembly that's keeping track of where in the stack we are putting things。

 It is the Ocal program that we are running in order to produce the assembly。

 That's the thing that knows where in the stack to put things。 So if we don't know at compile time。

 right at the time， we are running that Ocal program。 What size the thing is going to be。

 How do we know what to put as that second argument to compile X， right？ So if we take a look at。呃。

This， right， How do we know what value to provide there if we don't know at compile time。

 what the size is。Are there questions about that before we do one last little memory exercise。

We feel comfy with the idea that we really need to know the size at compile time。

 if we want to put it in the sack。Awesome， all right。

So this is something that we have thought about a little bit。 but I want us to take another moment。

 So there's this other thing where we have been storing stuff。Right， which is these registers。

 And sometimes we seem to be putting things in registers versus sometimes we seem to be putting things in memory。

 which is to stay the stack or the heap。 So how are we making that choice。

 When should we put something on the stack。Versus in a register。

Go ahead and take another minute to discuss with folks nearby。Yeah永康。Alright， do we have some ideas。

Yeah， so I think this is actually a pretty reasonable one for us to not really have a solid。

 concrete answer here， because basically， there is no one true answer。So in general。

 we prefer to have things in registers where we can operate on them and where access is faster。

But we only have 16 registers to play with。 so we can't always put everything in there。

 even if we would like to。In practice， in production compilers。

 figuring out exactly what to put in registers versus what to spell out onto the stack is super important。

 So folks would probably not put in concrete registers like we are doing。 Instead。

 they would put in some kind of virtual register。 And then another pass would come through later and do register allocation。

Deciding which things go in registers versus which go on the stack is happening at that stage。

 And this is actually a really nice application of some of the graph algorithms that y'all may have learned in priorriar courses。

 And we will talk more about register allocation later in the semester。

 So around the last month or so， we will talk about it。 But for our purposes right now。

 all we need to know is that we can't put everything in registers because sometimes we will have more things that we need to save than we have registers。

 and we don't have any assumptions in our compiler that we won't clollber various registers。

 So if we're going to be making a recursive call to compileex before we use the value。

 it is probably a good idea to go ahead and store it to the stack instead of into a register。

 that's sort of a practical thing for our own purposes， especially as we are building up homeworks。

But if you can persuade yourself that you won't be colboing the register you're using。

 then it is okay。So that is sort of our rule of thumb for when we will be using registers paired with the limitation that。

 okay， even if we are the smartest compiler writers in the world。

 we aren't going be able to put everything inside registers because we probably want to be able to deal with problems that are are pretty substantial programs that are pretty large that will need to save more than 16 intermediate values。

 given that we want to do that。 We're gonna run up against the limits eventually。

Are we feeling pretty comfy about registers versus stack。RightIt's sort of wacky， right。

 because if it fits in a register， presumably it' 64 B， right， And so we know the size of it。

 And so then we might be thinking， okay， Sta versus register what's the choice there that it really comes down to。

 We'd like it to be in registers， but we can't fit everything。Okay， cool。

 So let's go ahead and do one more activity in this general theme。

 This is something that we talked about last week。 But I'd like us to go ahead and think it through one more time。

 So when is data getting removed from the heap。😊，This is the only code in our current compiler that modifies R D。

 I。Go ahead and discuss for 40 seconds。Alright， so the simplest form of this question。

 does data ever get removed from the heap， Hu for yes。Humfer no。Yeah， I completely agree。

 So this is something that we talked a bit about last week。

 But I did want to make sure we revisit it。 As of right now。

 the way we have currently set up our compiler data never gets removed from the heap。

 At least in our current implementation， we will eventually talk about how to do something smarter。

 But for now， what we store in the heap， the heap can only grow。 it will never shrink。O。

So these are the things I wanted to make sure we talked about before we moved on from thinking about stack versus heap based on the questions that were coming up in drill。

Are there other questions on these general themes of how we're using memory before we dive into our main content for today。

Okay， cool。 If questions come up， bring them up there。



![](img/07aaf0bb71274df79471f6e41cfad2ab_2.png)

Alright， so we have a fun one today。 Let's switch over to。😊。



![](img/07aaf0bb71274df79471f6e41cfad2ab_4.png)

Our slides。So here we are。 We have been been thinking for a while about the programs where we aren't actually interacting with the environment。

And now we're going to go ahead and start thinking about some things we could implement。

 So these are the three that we will be implementing over this week。

 But I'm actually going have a start with readum， which is going to be today's topic。

 So let's go ahead and say that this is going produce a number。Provided。By the user。

So that's what we should see when we go ahead and put Readum inside our programs。



![](img/07aaf0bb71274df79471f6e41cfad2ab_6.png)

So I'm gonna now take us to the compiler where we're gonna think about。



![](img/07aaf0bb71274df79471f6e41cfad2ab_8.png)

We' are gonna think about。Why we can't do a particular version of the compiler。 So here we go。

 We have a version of the compiler that looks quite a bit like before。

 But let's pretend we've actually gotten rid of。All of this stuff， right。

 our normal stuff that we're used to。And where previously。

 we had done something like this where we'd had， you know， all these various things we could do。 Now。

 we have replaced our previous calls to compile X with this call to compile value。

Where what we're actually calling it on。Is the result of calling our interpreter。On the expression。

 right， So we call inter inter X。And we call that。Pass it into compile value。

 compiled value is going to go ahead and take as input of value。And then if it's a number。

 it's going to put the value of the number inside R X。 If it's a booolean。

 It's gonna put the value of the boolean inside R E X。 If it's a pair。

 it's gonna to go ahead and do some heat manipulations。

 but it's going to put the pair on the he in the appropriate way and modify R X in the appropriate way。

And this is。Our weird new compiler。So what I'm going to ask you to discuss with folks nearby for about a minute。

Is。Is this a good idea。Like， should we do this。And then。

What could we add to our language that would break。This very efficient new compiler。

Go ahead and discuss for betterment。你赵成英。没有哦。So just to give us a simple example of the kinds of outputs we will get from this compiler here we have a fairly complex program。

 right， we're gonna go ahead and map X to 4， and then we're gonna to use it inside this edition。

 And here's what we see when we actually produce assembly。With our new， our new compiler。

 here's what we come up with。So okay， continue discussinging。Alright， so this seems like a really。

 really efficient compiler。 In fact， maybe even a maximally efficient compiler。

 It's hard to imagine a program that gets this result more efficiently than this。

 It's really just doing it。So why do we write compilers， right。

 Why aren't we just writing interpreters and calling it a day。

 Interpreers seem to be much easier to write。 So maybe we should just go with that。

What do we think are there。Some programming language features we might want that would break this。

What we got。User input， yes， theme of the day。 This is a great answer。 Yes。

 it turns out as soon as we want to operate our program。😊，On different data， different inputs。

 or how a look， right？ In fact， it turns out that any side effect means that this approach is not going to work for us。

 So if we think about it， anything lets the program interact with our environment at all。

 Even excepting just input。 We often don't want to run a single computation over and over， right。

 That's sort of a boring thing to do。 It's not that we never do that。

 But that's relatively uncommon in general， we want to run the same program。

 but over different data or with different user input or based on the time of day or based on current info from a web server or we want to have some kind of a side effect that's gonna to affect the state on our machine。

 maybe we want to move around some files， maybe there's some other stuff that we want to have happen。

And so today， we're gonna go ahead and actually add interaction with our environment。

 which is gonna mean that our hyper efficient compiler actually isn't going to work anymore sadly。

 And so we are gonna have to actually comment out this highly efficient compiler since we don't want to use that。

Yeah。Why is writing to our terminal output not considered interacting with their environment。

 Great question。 So in a sense， it actually is， right， So it is， in fact。

 changing the state on our machine。Now。Is it changing it in a way that requires us to actually change the assembly。

Yeah， so that's the only reason we're able to get。Yeah。

 so it turns out there are some side effects that we could continue to have。

 even if we go ahead and say， okay， I can gonna use this fixed assembly。

 The things that are actually gonna be most interesting for us are gonna be the cases with us。

Other questions。So I guess this maybe also gets the idea of what other things could be happening other than input and output or or reading from other sort of human produced sources。

 And there are， of course， programming languages that let you represent pseudo randomness。

 And so say we want to observe a distribution of values rather than just one value， right。

 Anything where we're baking in a single value， but we want to observe multiple values。

 is's going turn out to be a problem for us。Alright， so let's go ahead and say。

 let's go back to using。Our original version。 So we'll call this。Compile， weird。

And we'll go back to calling this compile。And that will get us back to using our standard one。

So I'm gonna have a start， as we normally do， by modifying our interpreter。

 So let's go ahead and get this implemented in there。

And this is gonna be pretty easy for us because as we usually do。

 we're gonna get to sort of lean on what O Caml does。 So let's do let input channel。Lis breath。

 standard in。So we're just gonna go ahead and use standard in for our purposes here in class in the homework。

 you are gonna end up actually implementing all kinds of different input outputlet things。

 But for today's purposes， we're just gonna go ahead and and read in what the user actually types at standard in。

 So let's go ahead down here。And。Do。😔，Beno。And what should happen， Well。

 we should go ahead and make a number out of something out of what。 Well。

 we're probably gonna want to go ahead and actually get some input in from the user。

 We are seeing this right， yeah， okay。Input lines。 So we're gonna go ahead and read in one line of input from the input channel that we chose。

And then we're gonna go ahead and say， allright， I know that you think that that is a string。

 but I want this to be an int。 So int of string。 And that's how we're gonna to be able to create our number。

Let's go ahead and make sure that this all looks good。So far so good。

 it seems to be waiting for us to actually provide some input。Okay， great。So。So far， so good。

 But it does turn out that this makes some things a little bit wacky。

 So let's go ahead and try another program。Go ahead and take 20 seconds to predict if I make this program and I type in one。

 and then I type in 2。 What would you like to see as the output。 Take 20 seconds。So just the watch。

All right。So who thinks we'd like to， in that case， see pair 1，2， home for pair 1，2。

Who thinks any other answer。Yeah， so I gotta say， I agree。

 My expectation as a programmer is that I would see pair 1，2。 But let's go ahead and try it。Wops。

That's a little wacky。 So up until this point， the different order of execution really didn't matter because we actually didn't have any way to write programs with side effects。

 which means we couldn't actually observe which order these things were happening in。

 A side effect is where it doesn't just evaluate to evaluate。

 it also does something that affect state reading from the environment running to the environment。

 This isn't quite true in homework you did implement division。

 And then if you divide it by0 division by zero throws andarrow。

 So it might have been possible for you to observe in those area in cases whether the interpreter was different from the compile。

 But now we have this other side effect， where we're reading from the user。😊。

And so now it's a big deal because these are programs that should succeed。

 And it matters that the compiler and the interpreter agree。

 And if we actually take a moment to think about how the compiler constructs values。

 we can take a look at pair。Let's see， pair。We can see that it is going to go ahead and first construct the thing on the left and then construct the thing on the right。

 whereas we can see that we have not actually constrained for the interpreter。

 whether the thing on the left or the thing on the right is happening first。 And in fact。

 Ocael has chosen to do the thing on the right before the thing on the left。 In fact。

 different Ocal implementations are allowed to make different choices here。

 All of the ones that I have interacted with do actually do the right first and then the left。

This is probably not what we want。 So we're going to go ahead and actually constrain it a little bit more。

Are there questions on how it suddenly matters that we are。

 are doing things in a particular order now that we have side effects or we feel pretty comfy with that。

Okay， cool。 in that case， let's just go ahead and actually change pair so that we constrain it to do things in the order that we want。

 So let's do let L。And then we can go ahead and put。The left over there。TheRight over there。

Let's make sure everything works good。All right， we have constrained it to do the thing that we were expecting it to do。

So so far， so good。 But definitely it it is actually changing some things now that we have added in our side effects。

😊，O。I do want to briefly talk about what people mean when they so the， the idea with a pure language。

 right， a pure versus a language that has side effects。

 Usually pure is suggesting the idea that there are not side effects now。

It is a little weird to say that， because in general。

 we're not super interested in programs that don't have side effects。Right。

 so changing the value associated with a name that is a side effect， reading from the user。

 writing all of that as a side effect。 Even when people talk about pure languages。

 they're not saying that everything the language is pure because that would be really boring， right。

 All the stuff we care about is actually side effects interacting with the world is what we want to do with almost every program。

 So even for pure languages， that's mostly just saying that most of the things you do in that language don't have side effects or that the things that do have side effects。

 those are wrapped up nicely， So Ome is actually a really nice example of this。

 Most of what we're doing doesn't have side effects。

 We did introduce gensim for making symbols and that used counter。

 which was a reference and updating that was， in fact， a side effects。

 because it changed to the state。 We have been reading from files and that's a side effect。

 But most of the stuff was pretty cleanly separated from most of the code。

 which was side effect free。So in the same way that we had to change pair， right， like。

 it could have the exact same issues with， with plus with minus， right， all of a sudden， all of the。

 the operarants to all of those could be readum， right， could be some way of taking an input。

 and the order in which we do things does suddenly matter。So hopefully。

 we're feeling pretty comfy with that before we move on to our compiler。Awesome， okay， in that case。

 let's go ahead and copy over。Some of this， to compile。Let's go ahead and put it right after pair。

We're gonna do something that looks a bit analogous to what we did。 I guess it was last Thursday。

So last Thursday， we said， okay， when we want to have an error。

 while we're gonna be able to do this thing where we actually jump to the runtime error function。

 turns out we can do something relatively similar。 So let's go ahead and add in。You and't。For。Readom。

We don't need any arguments。We do need a slot where we actually store whatever the thing is that we read in from the。

 from the user。And then we're gonna have to go ahead and grab in。Number。

 we're gonna put it inside our particular spot that we want it to be， right。

 So we want to go ahead and put it inside our。And then we better do it ahead and do our numb shift to get it into the representation that we want。

So to me， this looks like something that will successfully read in a number。

 Go ahead and put it into a spot。 Go ahead and do the math that we need to do in order to turn it into our runtime representation。

 and then put it inside R E X because as we recall。

 what happens with the return value in C functions is that that it goes into R E X。😊，So。

 let's go ahead and。Make ourselves our new runtime。Oops。嗯嗯嗯。Alright。

 let's go ahead and take our five minute break while I wrap up our syntax。

 and then we will make our new rundown。 See you all together at 4，20。Yeah。😊，Hello， hello。P chicken。

Registries that we're using。You're kind of like going back to。First started。We started using art。

カルシて。Why。We were looking at it。It seems like it's the first state Ba。

 but is it like kind of arbitrary like could be used like part 9。 Yep， this was totally up to us。

 right， We were like， we got to put it somewhere。 All right， it's empty。 Let's go。 Okay。

 that was as as deep as that one。 So we can literally choose like any other。Well， yeah。

 so open register。 that open is doing a lot of heavy lifting that， Right， because we make。

 make sure that we're not clobbering anything that we're already using for something else。

 And in particular， there are a couple of registers that we are now using for something specific。

 So RP， we'd probably better not not overrite R I， we've not overrite right。

 So there are certainly registers that we want to avoid clobbering。 But with R D I is。Specifically。

 for heat。We made the choice。 All of these are just choices that we've made。

 Every single register that we have chosen to use for a particular thing was just our choice to use it for that particular thing。

 except R。So I guess an extension of that is。So right now， everything we're doing is something。

We were to。T to taking like。Like more than two。Would we then you。Ms。Expressions。Great question。

 So what would we need to use multiple registers， right， Say we had an addition of 17 elements。

I guess we could just boil it down to。Where we。If no operation。I mean。

 we are certainly already using more registers than two， right， So like。

 we are storing stuff in them that we want to have access to on the regular。

But we can always spill off the stack。 right， There's。

 there's always the option to put things in there。 If that's your question。

 I'm not totally sure I understood the question。 Its just simpler to keep things on this。Like store。

Oh， okay， I think I understand。 No。 So in general， So for production compilers。

 we actually are making a massive effort to try to store everything in registers that we can。 right。

 So again， we're doing this the process here where we're actually hard coding。

Because it is much faster to access registers than it is to access memory。 And so the。

 the thing that people are doing when they do register allocation is trying to figure out， okay。

 what's going to be the way that I can keep the most values inside registers so that I have to spill off to the stack the least often。

こます。It would be much more efficient to just use registered。 Yes， absolutely。The purpose of this。

 Well， we will end up talking about register allocation， but it will be down the line， yeah。到不在。あ你。

All right。So we've gone ahead and fixed my bad spelling。 and we've made our new runtime。

 And now we're ready to finish putting stuff into the compiler。 So let's go ahead and， well， first。

 let's make sure we actually have access to this thing。

 So in the same way that we made sure we had access to error。We can do。Extern。Ridnm。😔。

And then we'll be able to actually access it in here。

 And so let's also take a look at how we used error previously。

 So what we did previously was inside insure numb and inside insure pair。

 We had this jump to an error， depending on certain conditions。And so based on that。

 I'm gonna propose a way that we might try to implement our readum。 So let's go back to a readum。

And let's try something here。 So let's go ahead and try out a version of this， where we say。

What do we think？Go ahead and discuss with folks nearby。Is this a good idea。在那个。All right。

So let's think a little bit about this。 So this does look relatively similar to what we did when we were jumping to error。

But some things are a little bit different this time， in particular。

We're gonna want to retake control， at some point。So what are some issues that might happen if we just do this jump like this。

Does anyone want to shout one out？Yeah， so what is there that is actually telling this program how to get back here。

 right？ So if we take a look at what we've been generating this whole time， right。

 we can look inside program do S At the end of our entry this whole time。

 we've had this R instruction。And this red instruction， what it is actually doing。

 is looking inside the， the base of our stack and saying， okay， that return address。

 Let's go back to there。That's what's actually been happening inside this return instruction this entire time。

And so when we're doing this thing where we're just jumping， right， so。

We're just jumping to a particular label。 we're sort of expecting to sort of keep going， keep going。

 If we just go ahead and jump to。 read numb。Well， it's just gonna keep going， right。

 There's nothing there that tells it how to get back to us。 What other problems might we have。

So I'll say， we're certainly expecting。Some of our registers to keep track of particular values。

 right， So for example， we are being really careful not to clobber the RDI register。

 which is where we are keeping our he pointer。If we're just going ahead and giving control over to a C function。

Glad to do whatever it wants。 It could absolutely overwrite what we have inside R D I。

 Overwrite what we have inside any of our registers。That's totally fine。 In fact。

 we are relying on it to overwrite one of those registers， right。

 The whole reason that we are actually doing that call out to read them is that we are hoping that it will clobber what we have inside R E X with whatever value it gets back from the user。

 So we are expecting it to be messing around with our state。

 And if we don't save off the parts that we're going to need while， we could get into some trouble。

Go to take another twice seconds。 Have you brainstorm。

 What's another thing that might go wrong if we just hand off control。To the C function。

 and don't do anything else。So do we have any ideas of what else might go wrong if we just pass off control to our C function？

Maybe this drawing gives us some ideas。So we've been doing this thing the whole time where we said。

 okay。You know， the。The caller's return address is going live right here at RP。

 So we better avoid messing around with anything at RP-0 or anything lower， right， We've been saying。

 okay， I know not to mess around with anything beyond that point。

But say we go ahead and just leave RSP pointing here。Well， that sure is gonna look to the。

 the function that we're calling as though it's allowed to mess around with any of this stuff， too。

 right， So it comes in and it's gonna go ahead and say， allright。

 I want to use this for some other value Z。 And I'm gonna overwrite that。

 I'm gonna use this for something else， right， and it's allowed to use all of this。😊。

So we're going to have to make sure that we also protect our stack， right。

 because it is going to have that same model in mind of I had better not mess around with what is at RP-0。

 but it's happy to we mess around with anything beyond that point。

So those are some of the things we're going to have to do。And in fact。

 this is going to introduce us to a useful idea。 So up until this point。

 we have thought about using the stack， but we have never actually changed RP。

 right We have just kept RP pointing to the same point this entire time。

 which is to say the point pointing to our caller's return address。And so basically。

 this is because all of。This stuff that we are playing around with here。This is our stock frame。

And basically， the stack frame is the part of the stack。That we are controlling。

 We could go ahead and actually save more stuff inside here。

 in which case we could grow our stack frame。 But once we have gone ahead and actually called something else。

 say maybe we might want to call that read nothing， let's go ahead and change our color。

Then inside there， we're going to have to have our return address。

And then it can store whatever stuff it wants to store， and that will be。The readnam。Stack frame。

And then， in fact， that can go ahead and call some other things， right， So then we can have。

Let's change our color again。 That can have the。Read numb。Red adder。

And it can source some other stuff。 And all of that can end up being。

 I think scan F is the thing we actually call it。 That can be the scan F。Stack frame。And basically。

 when we're saying stack frame， we just mean the part of the stack that has been written into by a particular function。

Are we feeling comfortable with this idea of what is a stack frame before we move on to how we're going make sure that we are using it。

 right。feeling pretty good。Amazing。Okay， so how can we make sure that we're not going to blow away what we've been doing on the stack。

 How are we going make sure that we're gonna to actually get back control to our program that we are in charge of。

Well， it turns out that there is an instruction that is going to help us do this。

 So let's switch back to looking over here。

![](img/07aaf0bb71274df79471f6e41cfad2ab_10.png)

![](img/07aaf0bb71274df79471f6e41cfad2ab_11.png)

And we're gonna have to stop using this jump thing。 Instead， we're gonna want to use。

The call instruction。 Now， this is a little weird because we are talking about calling functions。

 and we're gonna be talking about the call instructions in assembly。

 So we'll be very careful about how we talk about it to try to avoid confusing ourselves， but。

Let's think about the things we're going to want to do before calling。

 And then we'll think about what call is going take care of for us。

So one thing that is not going to take care of is protecting the registers that we want to predict。

 right， We are still in charge of saying， you know what。

 I need to keep around this value of RD I because that's how I'm keeping track of what is the next available slot in my heap。

 So let me go ahead and make sure that we save that。 So let's put。

Into the next available slot in the stack。 Let's go ahead and put in there the。

Value that we currently have inside RD I。So that's going to save that off for us。Now。

 what else are we going need to do？ So to make this next choice。

 we're going have to know a little bit about how call actually works。

 So let's go ahead and look back。Over here。So what call will do。Let's go ahead， and draw ourselves。

A little drawing。P of those， and make ourselves。An RP。 So currently， RP is pointing here。

 We have never updated it。What call is going to do is it's going to increment RP by exactly 8。 right。

 So it's going to say RP points here now。And then。It is going to put our next instruction。Right。

The next instruction that we want after the call is's going to put that in the next slot。

So we've gone ahead。 We've done this sort of increment。 And then it's gonna say。

 this looks to me like where I can put。Next。Instruction。Address。Right。

So that is what it is going to be in charge of doing。So based on that knowledge。

 we can decide exactly how much we want to update RP。

 leavingaving RP where it is probably is not the right idea。

 but we can go ahead and actually update it。 So let's go ahead and look back at our compiler。

And we can say， I want to go ahead and change what's in RP。 So let's do add。Reg， RP。

And here I'm gonna ask you to go ahead and brainstorm with folks nearby for a moment。

 exactly how much should we update， Oops， sorry， RP， not R XP。Exactly， how much should we update。

What we have inside RP， What is information we can use to think about how much we should update RP。

Go ahead and discuss with folks nearby。Oh。嗯西。で。Alright， so hopefully。

 we all landed on some idea of it's probably gonna be the stack index， right？

 So if we look at what we're doing， right， what we've done is we know that the stack index is always representing the next available slot for us to write into。

 We have just written into it。 right？ So we know that right now。

 it is actually pointing us to the last use slot。And that is exactly what the call instruction is inspect to see that RP is pointing at the last slot that actually got used。

 So because our stack index is normally pointing to the next slot we can use。

 And because we have now just put something inside that next slot。

 we are now in the situation where it is pointing at the。

 the last slot that we have actually taken advantage of。Now。

 it does turn out to get slightly more complicated because it turns out that C functions on X 86。

64 require that RP is actually a multiple of 16。So we do actually need to slightly further adjust RP。

 We might need to leave sort of one blank slot if we have not landed on something where we'll actually get a multiple of 16 after the calls update。

This is kind of an unsatisfying thing。 Like， basically， what happened was the。

 the folks building GCC， like we made this decision at some point that we're gonna promise that everything is 16 by aligned to try to solve the next design problem down the line。

 They didn't think about it。 Everyone kind of things it's wasteful。 But it is what it is。

 And we can all just make sure that we sort of leave a slot empty if we have to in order to make sure that things end up being 16 by aligned。

So that's what we're doing with the aligned stack index。 But basically， normally， we're gonna be。

 right， say we have landed on a situation where we're gonna be in the 16 by align situation。

 Then we're just using stack index。 So conceptually。

 what we're doing is just going ahead and making sure that we are going use the。

 the last used slot as the， the thing that we point to for RP。Are there questions about that？

 I know there was some funky math in there。We're feeling pretty okay about the last use slot being where we're pointing RSP to。

Fabulous， al right， so let's go ahead and use our little helper function that we made up there。

 So align stack index， stack index， which again， all it's doing is using stack index if it can or aligning it so that we'll have a 16 by aligned thing in order to make C happy if necessary。

 In fact， it not even that C functions themselves have to all be 16 by line is the whole thing anyway。

 we have to make sure that that 16 by line。 So now we're in a pretty good situation。

 And now if we go ahead and use our call， it is going to avoid clobbing any of the stuff that we've put in the stack。

 So that's good because it is gonna be in charge of actually updating RP。

 it is going be in charge of putting the instruction of sorry putting the address of the next instruction that we want to run into the appropriate spot on the stack and is going be in charge of then actually making sure that return is called in order to transfer the instructions back to us。

 Well， it's really， the people who made the compiler for the other function that are in charge of emitting return in the same way that we are in charge ofting return for us But assuming a return does。

 in。App in that program。 Then we are gonna to go ahead and get our， our control back to us。

 So now I'm gonna to ask you to spend about a minute thinking about once return does， sorry。

 once return does actually return control to us， What do we want to have happen next， right？

 So we may need to now restore some state。What should we do to make sure that we can keep running things as usual。

Go ahead and discuss for about a minute。是的。Alright。

 so what's the first thing we're gonna need to do once control gets returned to us。

 What would we like to do next。Anyone want to yell it out？Yeah。

 so it sure seems like the last thing we did sort of before our call was change RP away from what we are expecting it to be。

 So we had better change that back， right， we really want to make sure that we're gonna go ahead and actually get back the value of RP that we're expecting and that we are able to actually interact with because otherwise。

 say we're gonna go ahead right， let's do that do this up。 All right， we've done this up。

 we go ahead and actually subtract off the exact same thing that we added on。

 We just want to get back to the way things were right。

 because we are expecting that all of our our offset that we have saved in our symbol table。

 for example， are relative to that original RP， So we'd better go ahead and get back to that original RP。

 yes。Yes， great question。 So this question was， what exactly is the instruction that call is going to write into the stack as the。

 the next instruction that we're gonna want to read， we're gonna to want to do。 And it's this one。

 right， the one that appears after the call instruction itself。

 So we will get the address of this subtraction as the。

 the thing that should get the control return to it。 Yeah， great question。All right， what's yeah。

Great question。 So this question was， is the C function allowed you to use the heap at all。

And so this gets back to， how do we actually create that heap， right？

 So if we take a look at what we did inside the runtime。So let's take a look inside the runtime。

 So even though we have this sort of abstract model that what's happening is， okay。

 the heap lives up here and it's just， you know， going down and the stack lives down here ands just growing up。

 What's actually happening。 In fact， is we carved out a particular spot that we want to use as our heap。

 And in fact， lot， a lot of programs are doing the same thing， right。

 because you're probably not running just one program on your computer， right。

 Everyone has their spot of memory that they're allowed to play with。Right。

 and so this is exactly what's happening here where we have said this is ours to play with。 And。

 in fact， the C is not going to be allowed to mess with it。Yeah， so that could run us into trouble。

 right， because say it started overriding the stuff inside there。 We would be in huge trouble。

Is there a question over there， other questions？Okay， cool。Alright。

 so that's one of our changes made。 What's another change we might want to make in order to restore our state。

I love it。 So let's get the value of RD I back from the stack。 right。

 We're basically just walking back the things that we did before the call。

 Let's just go ahead and and walk those backwards。 So let's go ahead and put inside R D I。

 Are we seeing the right thing， We're seeing the right thing inside R D I。

 Let's put what we saw previously at the stack address， We went ahead and saved it off there。😊，So。

This is what we want to go ahead and put back in。Are there questions about how we did this。Okay。

 cool， let's make sure everything is up and running。

And then we'll run through a quick example on the board because I know this was。Complex。



![](img/07aaf0bb71274df79471f6e41cfad2ab_13.png)

So far， so good。Let's do our pair thing。Allright， so it looks like we've got read numb up and running。

Are there questions about that before we take a。A quick run through one of our examples， one of our。

 our assembly examples。Yeah， what's up。嗯。Great question。 So this question was。

 say we're gonna call a function。 and we know that the function is going to actually take some inputs。

 What do we need to do in that case， So it depends on the compiler that's in charge of the function。

 right， So say that this is a function that we've implemented inside our own language。😊，Depends。

 What did we set it up to expect， right， How are we expecting to get arguments communicated to us based on how we have implemented our compiler。

 On the other hand， if were going to go ahead and communicate with， say， a C function。

 then we had better understand what the C compiler is we're doing in order to do that， right。

 So that is exactly the， the information that we would need to get out of the compiler。等着。

Great question。Al right， cool。 In that case， let's go ahead and run through one of our examples。

And in particular， there's something kind of new and exciting in here。



![](img/07aaf0bb71274df79471f6e41cfad2ab_15.png)

Which is。This。So this is the instruction pointer， right？

 Theres no magic sort of making things happen such that we step through instruction by instruction。

 What there is is a register R IP that is always pointing at the next instruction to execute。😊。

We already sort of know the three main things that something like a move instruction does， right？

 But basically now we know sort of the final thing that it does， which is bumping up R IP。

 So our first instruction wouldn't actually be at 0， right。

 So like the fact that that's there is really just for convenience。 It would just be some address。

 right， some address， wherever it is in memory that this program is actually living。

 But what we'll do on the whiteboard is just use that because it will make it a little easier to follow。

But these instructions are at actual addresses。 So we would actually have sort of standard address looking things here if we were being fully realistic on the whiteboard。

 right， This would be a 64 B。 something that is just saying， okay， this particular spot in memory。

Questions about R IP before we fully dive in or we're feeling all right about R IP。

So this is sort of one of the， the last sort of layers of abstraction that we're peeling back is there's no sort of magic taking us from the first instructions of the second instruction to the third。

 Instead， all that's happening is we are actually keeping track。

Inside here of what's going to run next。Okay， cool。 In that case， let's go ahead。And run through it。

So。As we like to do， we're gonna go ahead and start off by。

 this is basically the exact same instructions that we have seen。

Just now in our in our implementation for readum。 So we're basically just seeing the very simplest version of this。

So let's go ahead and start by saying， okay， whatever we have in RDI。

 which is to say our heat pointer， we want to save it on the stack。Now。

 it turns out that what we have there right now is just。This， right。

 So that's what we actually have inside RD I。 This is pointing to that。

 So let's go ahead and just save that here。 And I'm going to use the highlighter to highlight。

It's going on there because I know that this is a lot to keep track of。

So now let's be very concrete about what we mean when we sort of put this little dash here to say that we've done that。

 What that means is we can go ahead and cross that out and put one。So okay， so far， so good。

Now we are ready to update RP right because right now RP is pointing to here。So， again。

 I'm going to use our highlighter。 Let's go ahead and use。Blue highlighter，64， meaning 64。

So now what are we going to do well we can go ahead and actually update RP。

 So let's cross out what we have here， and let's say 56。And now again。

 we're going to go ahead and update RIP to point to the next one。

And now we get to things that are a little more complicated， right？

 So now we're ready to actually do our call。😊，So what happens when we do our call well。First。

 it is going to increment RSP。Right， so it's going to say not 56 anymore。

 Let's go ahead and overwrite that。With 48。 So that's the first thing that call is going to do。Next。

 it's going to say， okay， I am going to put our next instruction that we want。In the slot。Right。

 so if we take a look at our next instruction， again， I'm going to use our colorful highlighters。

We can see that this is our next instruction。And so we can go ahead。 and in particular。

 we will use three as the next thing that we want to run。So that will go into the slot at 48。 Now。

 why is that the specific place that it's going， It is just because that's what we currently have inside RP。

 right， It updated RP to make sure we're not going to cler anything。 And then it said。

 that looks like the place where I can。Okay， at this point。Control transfers。So something else。

 right， control has now moved over to read them。 Read numb gets to do whatever it wants。

 So let's go in here with another color。And it's gonna come in and say， okay。

 now this has this thing in it and has this thing in it。 And we don't have that anymore。

 We have some other thing in here。 And well， R IP we'll see later。

 And RP maybe has been changed a bunch of different times。 right。

 We might have all kinds of different things happening over there。

But then we're gonna go ahead and hit a return instruction， right。

 Because if we take a look at how we actually implemented readna。We can take a look。Inside here。

 and we see that we did， in fact， choose to return。

 which means there was probably a red instruction that was generated by the sea。



![](img/07aaf0bb71274df79471f6e41cfad2ab_17.png)

![](img/07aaf0bb71274df79471f6e41cfad2ab_18.png)

And so then what return is going be in charge of doing is basically walking back the stuff that happened sort of in the interim。

 but only the stuff related to RP。So what it's going to do and here will'll change back to another color。

Let's go ahead and cross out whatever we had in there before。

 It is going to go ahead and put it back to。56， right。

 because it had been in charge of putting it to 48。 and it knows that when it found it， right。

 when the call instruction found it， it had been at 56。

 And so that's where we're gonna actually get back to is 56。

And the other thing that it's gonna to do is actually update what we have inside R IP right。

 So it's gonna say whatever else has been happening in the interim。 Let's go ahead and ignore that。

 And now what we want to get back is exactly what we see right here at the the thing that for it looked like the bottom of the stack right because it had RP pointed there。

 So it thinks the bottom of the stack is there。 So it's going to say， okay。

 what I want to have inside R IP is3。And so that means that the next instruction we're going to run is。

So at this point， we're ready to go ahead and cross that what we have in RP again。

 So now we have chosen to o an instruction that is going to actually turn this back into 64。 Well。

 that's where we had it in the first place。 and that's where we're going to expect to be able to find stuff。

And， in fact， we are going to take advantage of that just a moment later， right。

 because the next thing we're going to do， right， we've done that。

We've gone ahead and changed it to 4。 The next thing that we're going to do is say， okay。

 let me look in the space in the stack where I expect to see the value that I want to use in RD I。

 And so we're going to go ahead and read back that 0。

 So we're going to be able to cross out this and get back or 0。And then we can go ahead， do。

I tried to take that really slow with a lot of highlighting because I know that this is sort of one of the more complex things we're adding。

 this reasoning about the instruction pointer。Are there questions about what we just went through？

We're feeling pretty okay。呀，不错。Where did the three come from on the stack， Fantastic question。Yeah。

 so what happened was we went ahead and we went to our call instruction right。

 and our call instruction， one of the things that it's doing in addition to actually updating RP is it is also in charge of writing the address of the next instruction right。

 the next instruction after the call into that slot in the stack。So it says， okay。

 my RP is pointing here。 I'm going to go ahead and put in the address of the next instruction after the call right here。

 If we look at the call， we can see that the next instruction after the call is through。

So that's exactly how we got that。反正。Other questions。Okay， cool。In that case。

 I don't think we're gonna have time to go through an example where you' all are doing a worksheet on your own。

 But we do have some time to go over some questions to understand to to basically check our understanding。

 So let's think about what we did inside the compiler。



![](img/07aaf0bb71274df79471f6e41cfad2ab_20.png)

So here's sort of the， the two things we did to restore the state。

Would we be okay to swap these two instructions， Go ahead and discuss with someone nearby。嗯。Allright。

 so what do we think。

![](img/07aaf0bb71274df79471f6e41cfad2ab_22.png)

Hum， if you think it's totally fine to reorder those。Hm， if you think it's not fine to reorder those？

Yeah， I totally agree。 So if we take a look at this example， we can see exactly why， right。

 So that would be reordering this line versus this line。

 And we can see that this is actually relying on having the value of RP that we're expecting。

Because before， let me change our our color of our marker here。

 before if we' gone ahead and just use this value of RP。

 which is what we had before doing our subtraction， if we use this value of RP。

 And we went ahead and grabbed off what was 8 above that， right。

 We would just grabbed this random instruction pointer。

 This would not be a good thing to use as the value for for our heap pointer， right。

 it would end up in this case， just sort of sort of starting weirdly， right， we get offset。

 that wouldn't be so good。 So we really do need to make sure that we are actually using RP only in the way that we are expecting to use RP。

 we can't just have random value showing up in。So okay， we can't swap。

Let's remove those little annotations。So here's another question for us。

So we know that call is responsible for restoring RP for us， right。

 That's sort of what happened here。 That's part of how call works。

 But all the rest of the registers we use， it could blow away。 And sort of right here。

 we drew it blowing away R 8。 So why is it okay with us if R 8 has just been overwrittend。

Go ahead and discuss。All right， we're coming up against the end of class。

 so I'm going to go ahead and talk us through this。Basically， this is just a choice that we've made。

 right， We haven't stored anything in R8 that we're planning to keep around。

 We haven't set up compile X with the intention that we're always going to be storing。

 preserving what's in R8。And so we have a ton of things that blow away R8 right。

 a bunch of our things that we've already implemented blow away R8。 we've said over and over。

 we have designed like pair， for example， that blows away R8。

 we have designed our compiler very carefully to emit code that will put the value of the input expression into RX。

 And that's kind of the only thing that we rely on Like there's a few more So where we're going ahead and keeping track of RSP。

 We're going ahead and keeping track of our key pointer。

 like there are things that we are planning to not cloer that we are planning to use in a particular way。

 but in terms of registers where were storing not this sort of state tracking stuff。

 but where we are storing values the only one that we have chosen to sort of plan to persist over and over is RX。

And so this function is allowed to use whatever registers it wants。

 And all it has to do is guarantee that what we get in R A X is right at the end。

And we will have that same guarantee when we call up to see。

So we're not allowed to assume that any of those other register values do get preserved。

 That's why we've been using the stack is to save off things that we need for a moment。

 but which might get overwritten if we leave them in registers。

 So that's one of the key ways that we end up using the stack。And so this idea。

 the idea that there's sort of no magic under here。

 And it's all just us making promises and keeping those promises and making design decisions。

 That's one of the really cool and also really scary things about compilers。

 The machine really is not watching our back。 It doesn't know what we're doing。

 It's just getting the instructions that we give it。 and then doing what those instructions say。

 So this makes compilers both really cool and really hard。😊。

So I want us to hear think about an example that actually came up during the break。

 which was really awesome。 I'm glad that folks were asking。 So thinking about an example。

 we were using RDI to store our heap。😊，So， why。So basically， we're not using it anywhere else。

 So we can。 It's kind of as simple as that。 It happens that C uses it for the first argument， right。

 for passing along the first argument。 But we don't have to。Right。

 we need to know that when we are actually calling a C function。

 when we are trying to interface with a C function。



![](img/07aaf0bb71274df79471f6e41cfad2ab_24.png)