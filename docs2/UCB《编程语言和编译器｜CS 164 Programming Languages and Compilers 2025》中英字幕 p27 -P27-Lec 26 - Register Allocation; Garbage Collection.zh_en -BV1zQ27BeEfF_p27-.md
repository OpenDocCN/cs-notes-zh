# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p27 -P27-Lec 26 - Register Allocation; Garbage Collection.zh_en -BV1zQ27BeEfF_p27-

![](img/e62751841bd14a3f7682204d0ca31d5b_0.png)

All right， we're going to start with a humming activity today。

 Did everyone have a good break come for us？Hm for no。Oh， damn。 sorry。 that sucks。 Wow， some。

 sometimes I guess our breaks are not as good as we might desire。

 but I'm glad for those of you who did have a good break。😊。

And hopefully following up on this week in the next couple of weeks， you'll get a really good break。

I know I promised y'all Justin today and unfortunately Justin can't join us so you're stuck with same old me。

 same old same old today， so it's just going to be our usual session。

 I'm sorry you're not getting an exciting new lecture but the good news for y'all is that we have some very exciting topics today so we will have some fun content。

😊，Okay， speaking of humming activities， did everyone watch the lecture where we started talking about IRs。

 the one that comes right before this， humm for yes。Hum for no。

Oh okay I was worried that we were gonna have to do a lot of you too and it was really gonna slow us down。

 I think we're gonna be okay。 so we're gonna dive back in on some of that content and then we're gonna use it to get to the sort of purpose for having introduced that IR。

 which is you're interested in doing register allocation。

 So let's take a look at sort of where we left off。

 I'll give us a little bit of a reminder of sort what we were up to。😊。

So we talked about sort of one of the IRs that's very popular right now is this LLVM style IR that looks something like。

This right， we're seeing some sort of common structure。 we learned the idea of what a basic block is。

 and we learned they're all starting with a label， and then we get a bunch of statements that're all going to run in a row。

 right， as soon as we see a jump， that ends the basic block。And then we say， okay。

 we've got this thing going on where this particular type of statement has something on the left it has something on the right。

 We do seem to have this extra syntax that we're using when we're talking about specifically storing things in the heap or accessing things in the heap。

 but anything that's about storing stuff in a stack in a register that's all been sort of abstract it away It's almost as if in this IR。

 we've just got this sort of infinite magical supply of all the registers we might ever want right if we take a look。

 I'll just sort of draw some little boxes around here。 That's sort of what's going here。

 right we've just got all of the sort of magical， infinite supply of registers that we might possibly。

😊，That's sort of where we left things。 Are there questions about this before I keep bringing us along the road to register allocation？

Feeling kind of okay about LLVM style IRs。Great。Yes， this is a great question。

 So one of the things that we might think about is how these basic blocks are connected。

 and specifically if we ever have the situation where we have multiple arrows coming into a single basic block。

 we're going to need a p node and so basically this is basically just saying， okay。

 if we are coming from block L2， then the value that we're putting in T5 is going T3。

If we're coming into this block L4 from L3， then the value that we're going to put into T5 is going to be T4。

RightBecause we don't get to just go in here and say T5 is4， T5 is5。

 that would be against the rules because we can only ever have one place in the program where we write into that register。

 register， big scare quote。So we only get to write into T5 once。

 and so this is our special thing that we introduce in order to make it。

 so we are only going to write into T5 once。Sot of good。I love this question。

 Will we ever run out of the Ts。 So in this representation， right in this I， No。

 we get to just go and go and go and go and go， right， we are eventually， of course。

 we're like we're interested in this representation of our program because eventually we are planning to actually produce standard style assembly instructions just like what we've been producing all semester。

 And so eventually we are going to have to reckon with the fact that we don't actually have infinite registers And the thing we will do in order to reckon with that is register allocation。

😊，So yes， we are definitely moving in that direction。Okay。So。That's sort of where we left things。

 We've figured out that， you know， when we are， let's take a look a little bit down below here， yeah。

So we figured out that okay， if we are specifically doing loads and stores into the heatap。

 then we have our one way of working with it right， so we have those sort of load and store。

 but everything else， all the other things that we might be doing to sort of temporarily keep a value around。

 we're just using our sort of magical infinite supply of tea。

So that's sort of what we're paying attention to here。 And so if we had unlimited registers， right。

 if we actually had that situation， fantastic， right， we would never have to put anything on a stack。

 ideally， writing into memory is more expensive than just keeping something in register。

 if we could just keep everything in registers， that would be ideal for us we would love to do that spill out onto the stack because sometimes we don't actually have enough space for that。

 And so that is sort of the imaginary world that we're in here we're saying ourselves okay well。

 I'm pretending that I have infinite registers and you know memory X is expensive So I'm just trying to avoid it。

 this is not an intermediate representation thats actually tied to a particular hardware right and this idea that writing into memory versus writing into a register that that is always going be more expensive than writing to a register。

 that's not tied to particular hardware we were always going to have some cheap place to store things and some expensive place to store things And so this broader idea of I'm going try to maximize my use of the cheap place to store things and avoid using。

Expensive place to store things。 that's sort of the underlying core of what's happening with register allocation。

 and that is not about a specific hardware that's general。You're going to have the cheap places。

 you're going to have the expenses。So that's sort of what we have in mind here。

And so this representation that we've all just sort of gotten comfy with。

This is exactly the right representation for doing register allocation。

 Reg allocation is typically the very last thing we do during compilation。

 You can see that we're we're like kind of close to assembly instructions， but we're not quite there。

 There's obviously some less transformation step that needs to happen before。

 It looks like what we've been generating。So in this case right like in general we're going to have more than seven registers right so we could go ahead and put each of these values in its own register and that would be totally fine。

 but say this is the prefix of something much longer or say we're on some weird architecture and it has fewer than seven registers then all of a sudden we have to look through these Ts and say。

 okay， which of those is going in which register。That's one of the things that we're going。

So let's start on how we could figure that out so we are going to do a particular program analysis called liveness analysis so if you ever take a program analysis class you are going to learn that there is basically four quadrants of program analyses and one of the axes that you will care about is whether it is forwards or backwards so this is backwards meaning we're going to start at the end of the program and work our way backwards if it was a forwards analysis we will be starting at the beginning and working our way forwards。

 this is backwards we're not going to do that。So okay， we are working on a backwards analysis。

 let me just write backwards。And the thing that we are going to try to do as we start at the bottom and work our way towards the top is think about this idea is going to be a little bit fuzzy to start with。

Think about which of these T， whatever values we care about。RightSo if we start right here， right。

 T 6 is sort of the implicit return here。 So we're gonna go ahead and start by assuming that， okay。

 we do need to care about T 6， probably any work that we would need to do in order to actually build up towards having T 6。

 We need to make sure that we do。 We've got to make sure that all goes off smoothly。 So okay。

 T 6 seems like the right starting point。 That is the thing that I am sort of thinking about making sure that we can actually represent that somewhere。

 We are definitely gonna want to represent that somewhere。 And what I want you to do is let's say。

 let's write that right here。 I will。Clear some things out so we just have a little more space。

So let's go ahead and write T 6。And then if I look at， actually， let's write that a little bit lower。

 I'm going to clear out more space， I'm sorry。So if we're looking right at the end of the program。

 right， the thing that we care about afterwards is that we have T 6。 Now。

 if we go back before that last line runs。I can look at that last line in order to figure out which of these values I actually care about before that last line。

 right so I can take a look and say， okay， it looks like the values T2 and T5 are the ones that are going to be used for creating T6。

So if I am looking at this sort of prior line right before that very last line。

 the values that I am expecting to need。Are going be T 2 and T 5。

And we are basically going to keep working backwards with this style of reasoning。

 So here's one thing I want to point out， I did not write T6 here right so I could have put T6 there but in fact no T6 has not appeared at that point right by that point in the program that doesn't exist yet So yes。

 I care about T2 and T5 because eventually we're going to need those to construct T6 but T6 does not in fact appear there right we can go ahead and get rid of it because we know that having T2 and T5 is going to be enough to construct T6。

So what I want you to chat about with someone nearby for about 30。

 40 seconds is if we look one line before that and we're using the same kind of reasoning。

What should I write next to this line， right？ What are the little T values that should get mentioned next to this。

Go ahead and go。Alright， so I'm going to take us through that line prior。

 So in the same way that the last line that we did。

 we actually removed T 6 because it was getting defined。

 We can actually do that same deal here So we can say， okay， well。

 this is the line that is telling us what we're going to need in order to do T 5。

 So let's go ahead and remove T 5 from our list， right。

 So we can imagine ourselves basically starting from this list。

 but we're going to go ahead and kick out T 5。Because that is actually we are going to be able to figure out that if we have T4 and T3。

 that is going to be enough for us。So let's keep T2 in there， right。

 because we still need T2 in order to get this down here。

But at this point we can go ahead and write T3 and T4。

 and we are not actually going to need this T5 thing anymore because we can see。

 let's grab out our little highlighter again。 We can see that T4 and T3 right right there are enough to actually get us T5 so that can actually replace what we previously had right there。

Are there questions about that set。So I've been saying care about right， sort of a vague notion。

 sort of as programmers we can look through and sort of reason， think about that。

 The actual term for the reasoning we're doing is live right。

 So a variable is live if we are going to need its value later。

 if we are planning to read from it later in the program。

 So that's what we're doing right here is liveness analysis。

And if we actually keep sort of going back through this process。

 we can just keep taking it back all the way， right。

 So here we're going to go ahead and this next line， where we can actually take out our T4。 right。

 we can take a look at that。 And we can see that we're not going to need that anymore because we can see that that's just going to be a readum。

 So what is going to appear in that next line。 Well， it's just going to be T2。

And T3 right we don't need any other values coming in in order to get at T4。

And let's go one line further back。We know that we're going to need T 1 and T0 in order to make T2 so we can get rid of T2 and put in T0 T1。

 Still got to keep。 oops。 No， I skipped ahead。Ignore， ignore， ignore。There we go。

 Okay T3 is the one that we're actually defining there。

 So here it's this one and the things that we're going to need in order to actually construct T3 is T2 and T1 right so let's go ahead and get T1 and T2。

😊，Okay， so go ahead and take 30， 40 seconds to discuss with someone nearby。

 what do we put next to this next line that I have just drawn is between this line and this line。

All right， I want you to go ahead and hum if this is going to include T0。

How if it's going to include T1？How of it's going to include T2？T 3。T for okay， Yeah， all right。

 those are all coming later。 Obviously， Yeah， so this is gonna be T 0 and T 1， right， so we can。

 again do our exact same reasoning。 We can look through and see， okay。Well。

 we're going to go ahead and have T2 actually being defined so we're going to x that out right。

 we're going to not actually bother transferring that over it stays in the old set。

 but we don't need it in the next set， and we are going to have to add in t0 and T1 because that is what is required for actually producing T2。

And we can go ahead and wrap this up with saying that okay。

 at this point we only need t0 and before that very first line we just have the empty set， right。

 so nothing particularly exciting there。So okay， I sort of took us through this liveness analysis thing a little bit out of nowhere。

 right， Like we were talking about register allocation。

 Then all of a sudden we were doing this backwards analysis。 So why are these sets right。

 these sets of values that are going to be needed later that are going to be used at some point later in the program。

 Why are these sets interesting to us， if we are about to do the decision about which of these values should go and which register。

 I'm gonna encourage you to chat with someone nearby for about a minute。

 Why do we care about these sets。And I'm encouraging you to sort of think of each of these lines as one set。

All right， I'm hearing folks say it out there。Basically， the reason we care about these sets， right。

 the set that we see at each one of these lines is it means that we know there is at least one point in this program。

Where all of those values have to exist at the same time。

I want you to take a moment to look through this program and persuade yourself that that is true for any of these lines。

 any of these sets of values， we have the specific spot in the program， In fact。

 where we know that all of those values have to exist have to be stored。

 have to be present and available。At the same time。Just take 20 seconds to persuade yourself。Now。

 if we know that we need all of these values to exist again， to be stored at the same time。

 what does that mean， well， it means that they had better be in different registers， right。

 we better not be trying to put all of those that appear in the same set into R8 or R9 or whatever right and so some of them could be on the stack that's fine too。

 but we definitely had better not be trying to save them all in the same register。

And so this information is exactly the information we need in order to figure out which values should not go in the same registers。

 We're gonna then have to do a little extra work in order to figure out， okay， we register。

 should they go in， but it's not actually going be that much work。

 So okay if you think about what would happen if we actually violate this right。

 say that when we make T3， I'm gonna pull out our pointer again。 when we make T3。

 we go ahead and put that in R， and then we make T4， we put that in R8。

 why is that going to be a problem Well it's gonna be a problem because right when we get to this line。

 we're going try to read T4 from R8 and T3 from R right So hopefully it's clear。

 why this is a conflict for us why this is clobbering values that we actually need。

Does that idea feel pretty okay to people so far？Okay， cool。

 so now that we know that we don't want any of the items that sort of share one of these lines。

 share a set， we don't want any of those to be appearing in the same register。

 let's now do that extra work that it's going to take in order to figure out which register we do want them in。

So this is an interference graph。 This is going to be an undirected graph。

All of the nodes in this graph are going to be the temporaries in case it wasn't clear from now。

 the reason I've been saying T in front of all these the reason they have that T name is because these are temporaries。

 And so the nodes will be temporaries。 The edges will represent conflicts or interference。

 So let's write。T0 what does T0 interfere with， Anyone want to shout it out？T1。

 right so we can basically just go through and read down this list right So if I'm looking at the empty set line。

 Well， okay， that's not telling me anything。 if I'm looking at t 0。 okay well。

 that's not telling me anything。 that's a set alone。 And as soon as I get to this line。

 all of a sudden， I am seeing a conflict。 So in fact。

 let's highlight these rows as we go to indicate which ones we have actually already represented in our interference graph。

 So we've already handled that that。 And now that。So let's get to that next one， Okay。

 we're seeing that now there's a conflict between T1 and T2。All right， so let's go ahead and say。

 all right， well， that's not looking like those can go in the same register。 Let's mark out that。

 I it okay， if I just cross it down instead of highly I should hide。Avoid。

The issue of not being able to read it。Alright， next。

 we're gonna go ahead and have T2 B in conflict with T3。

 I'm gonna write this in a slightly funny way because I know what's coming up next。

 but hopefully that's okay for everyone。 So let's go ahead and write that off to this side。

 And we can say， okay， yep， T2 and T 3， those are gonna have a conflict。

 And now we get to this next one。 And now all three of these are actually in conflict with each other。

 right， So every single pair that we see represented in that next line is actually experiencing a conflict with all of the the items。

 right， So let's go ahead and mark that out now that we have that sort of three way。 misalignment。

 those but better not any three， any of them from that three be in the same register。

And then we can also say， okay， it looks like T2 and T 5 are going to have a conflict。

 So let's draw in T 5。Better not have those in the same register。

And then finally we see T6 and this is off to the side somewhere， right。

 and that's not actually a conflict with anything。So okay， this is the interference graph。 Again。

 this is not quite everything in order to get registers， right。

 we don't actually see from this graph what registers we should put everything to。

 But once we have gone through our liveness analysis。 And then for each of those lines。

 right anytime we see a temporary， we draw a line from that temporary to every other temporary that shares a set with。

 right， then we can do graph coloring。 So if you all remember from your last fun theory course when you did graph coloring right。

 the original idea was when you were like coloring in a map and having a sort of bodies of land being colored the same color would be confusing for the map viewer。

 right So we're doing that exact same thing， except we're saying that things that have one of these edges between them better not go in the same register better not be colored the same color。

 the colors are just gonna represent registers。 So let me introduce a couple of registers for us。

 let's give them some colors。 let's。😊，I have RAXB blue。RAX。Let's do yellow for R8， why not。

 so here's yellow oops。And I never do remember to switch to the highlighter when I want the highlighter。

 okay。That can be R 8。And then let's do green。And that can be。はい。Okay， fantastic。

 we have our registers available， we don't yet necessarily know that this is going to be enough registers。

 but we'll see later that that is in fact going to be enough registers and we'll see why and how we can figure that out so let's start by just putting our first value in a register doesn't matter yet。

T1 still unconstrained except that it had better not be blue， right。

 so let's pick one of our other colors and we'll use that。Great， no problem。 Now， at this point。

 T2 is not actually touching anything that's in blue。

 so blue could be perfectly fine for us for coloring T2。 Great。

 so now T2 is going to be stored inside RAX。 But now we get to something a little more complicated because we see that T2 is in conflict with both T3 and T4。

 So we're going to have to make sure that neither of those are using the colors that we've actually used before。

So let's go ahead and get that colored in so that everything is in a different color inside that triangle。

And then once we go off to T5， well it better not be blue， but it can be any of the others， great。

 let's put that in yellow and T6 again， it's not actually in conflict with anything we can put in wherever we want。

Great， we have now successfully done register allocation。This is a really good time for question。

I think the question here is about which specific registers we put it。

 So like maybe we are trying to， Okay， al right， let me back up a little bit so。

This doesn't get us out of sometimes having to use the stack。

RightSo there is still the possibility like say we have like 26，27。

 whatever temporaries or 26 27 colors of the graph rather。

 right like it's a really massive thing and we don't have that many registers。

 we still end up having to use the stack。 So the main thing we're trying to actually do is trying to use registers as often as possible and trying to use those stack slots as infrequently。

So that's the main thing that is going to make one register allocation better or worse and like the main reason why we were bothering to do this is you saw how often in the course of the semester。

 we were preemply putting things on stack to make sure that we were going to be able to do it without clobbering stuff。

 this is a way of trying to make sure that as often as we can。

 were going ahead and putting things in registers。So that's the main thing we are trying to arrange here that as often as we can be using。

 right， you saw how it sort of pretending to prefer blue， like every time I could use blue。

 I was using blue， right we're trying to do that exact same thing but for registers。

 We don't care which register。 that doesn't matter。

 but we're trying to be using the registers and we're trying not to be using the stack slots。

Does that kind of make sense。Or maybe， okay， your question might have been another question。

 So folks familiar with graph coloring might remember that it is， in fact N P hard。

 Do folks remember that Yeah， okay， so it turns out， yeah， huge caveat。😊。

badad news about about graph coloring。 It is N complete， which means we really， really。

 really can't do this efficiently。 at least not until someone proves that people N。

 but assuming that if not equal to N， then there simply cannot exist a polynomial time solution for actually graph coloring in the general case。

 So what folks actually do is basically solve this with heuristics。

 So as with so much of the optimization work we've been talking about people figure out， okay。

 what kinds of interference graphs are getting generated for real programs。

 Let's figure out something that is optimal for that kind of graph。

 Let's figure out something that just perform well， heurically for that kind of graph。

 there will be greedy algorithms， There will be all kinds of different algorithms if people are using in order to do this。

 despite the fact that is N。I don't remember which of those first two questions was here， please。

I see。 This question is， say that we have a situation where we have two programs that are running not just in an interleaved way。

 but are actually running at the same time。 and they might have to share registers。

 I that the question。 So generally in the situation where that is happening。

 everyone has their span of registers So first of all。

 the most common thing is that you like run this program briefly stop it， read everything out。

 pop in the other program。 have， So let like that's the thing we're normally thinking about But even say that we are in the situation where yeah。

 there are two programs that are going at the same time and are in fact， both E registers。

 What's going to be happening is that this one gets in span。 This one gets its span。

 So you can still use this exact same approach。 In fact， it is nice to have an approach like this。

 there's of factoring out the decision about which registers to use because it's all sort of constrained here。

 you just give it the list of things that's allowed to use instead of having something like what we've been doing where we've been hard cuttingtting R8 and R。

 But again， I do want to encourage to remember that the normal thing if you are running things concurrently not。

Current， but if you're running things at the same time。

 usually what that actually means for us for programs that are running the same time is that we run this one for a little bit。

 then we run this one for a little bit we。Quion。Okay， cool。嗯。One quick mention。

 usually we will set aside a register for loads and stores from the stack。

 And then some of the conflicting temporaries do get put on the stack。 So again。

 just the rate that we're trying to be fast is by avoiding doing too many things on the。嗯。Oh。

 real quick。 how would we generalize to going between basic walks？

 So yeah here we've got going between basic walks。 Basically all you do is figure out which temporaries are going to go between them。

 so we would just label each of these edges with which temporaries are going between right and we know that we would still have to get those and then we go through the exact same process。

Nothing too wacky。嗯。Now would be a really good time to come up。Workheets。

 and then we will work together on our graph coloring slash register allocation activity。

 and then we' switch to garbage collection。 really we're doing the whirlwind tour today。😊，Oh。

 and also real quick， we usually do not do registered allocation across function boundaries。

 so normally across function boundaries we just go ahead and pour everything out onto the stack and then once we're back in the function we can read everything back in。

We're looking at the activity that looks like。That looks like this。But don't worry。

 I will show what we were just doing again in a moment on the。Whiteboard， in case that is helpful。

An solution。That's a really interesting question I am not aware of any compilers that actually do。

The like full on optimal， like let's solve the MP complete problem。

That's not to say that no one's ever done it， it's possible， I mean。

 there are certain situations where we know that we are going to run a program just。

many times and we don't care how long it's going to take really to compile it we do it once it's like yeah。

 it would be feasible， it can get really long though。

Make sure you're looking at this particular activity that you see up here。

 and then I'll show us what we were just doing on the board a moment ago so you have an example to look at。

Everyone looking at this one？Excellent。All right， there's our little example to look at。

I'm not going to give you long for this one because this is going to be fast。

 you know how to do this， you've seen this。I recommend that you do the exact same thing we did where you start by filling in the little sets on the side of the。

The basic blocks lines。And then draw the interference graph。O to the right。Do we ignore？Okay。

 so this question is。Basically， about the definition of liveness。

So liveness is about tracking which values have already been introduced that are going to be used later。

So use that definition。Feel free to chat with folks nearby。Com if you're ready to do the set filling。

 if not the other part。Home if you want more time even for writing out the sets。All right。

 I'm going to assume we all sort of want to get on the same page with that。

 and then we'll draw the interference graph after that。 So starting from the bottom。

 we're for sure going to care about T9 right again， we're thinking about what is that implicit。

T9 is where we're going to start。And we can go backwards when we can say， okay。

 well T9 hasn't been introduced yet at this next set， but T7 and T5 have。

 and we know we're going to need those right those are the ones that are being used immediately afterwards in order to produce T9。

 So T7 and T5 are both definitely live。Now， we have this next weird line， right， So T 8 is not in。

Let me get there。ing it's not in this line， right， so anything that is used to produce T8。

 we don't care。Like that is not important to us， so even if this was using a bunch of stuff that would not necessarily make it necessary to us here because we don't care about T8。

 so we don't actually see any change here， so let's keep that at T5 and T7。Next up， we can see that。

 okay， well， T 7， we do actually care about that。 So we are going to have T 4。

Still T5 left over from there， right and T6 in the mix。So okay， T4， T5 t6。

 the next one it's going to be a big one， we've got T4， T5。

 T2 and T3 right so T2 and T3 are going to be used for creating T6。

 so T6 we get to actually take out from there， but we do have to actually keep in T2 and T3 in order to produce T6 and then T4 and T5 are still just brought over from the line after。

Okay， great。 We've got that。 Now we're ready to go ahead and see that T 5 just ends up being one。

 so we can take T 5 out of there。 We'll have T 2。D3。4。Got the exact same thing happening with T 4。

 fantasticantastic。 Let's do T 2， T 3。 It's a pretty weird program。 Obviously。

 we can see that there's some some wacky stuff going on。 And then the same thing going on with T3。

 So T2 is gonna be the one that've got there。 But now we can see suddenly it grows back out again。

 right So we had gotten it all small。 But now look it's getting bigger again。

 So let's go back one and we can see that t 0 and t1 are the things that are actually going be needed for creating T 2。

 So that's what we've got there。 And then we can see， okay， well。

 t 1 is just getting created from a constant。 So let's put t 0 in there。

 And then if we get back to that very last line fantastic。 We've got the empty set。

Everyone have something more or less like this written down for the sets。Fabulous。

 we have done our liveness analysis。 Let's go ahead and start writing out that interference graph。😊。

And then， you know， start shouting at me when you've done it。Actually。

 had everyone already written the interference graph， you want to hum if you've already done it。

Hum if you have not yet。Oh， great。 okay， right， let's just go through it。 fantastic。All right。

 so let's go ahead and start by， you know now that we have actually done our live analysis now we can just consume it going forward。

 that's totally fine。 So okay， we've gone ahead and like this one like whatever。

 we don't have to do anything。 T0， let's just write t0 Great， we've got T0 in there。

 Now for the next line suddenly we actually have to do something right So we've got T1 there and we have to have the conflict between them。

😊，We've done that。T2， is there any conflict between T2 and anything we've written so far？ No。

 so T2 is just going to be down here， great。T2 does have a conflict with T3。

I' gotta gotta represent that and now we can see okay T2。

 T3 and T4 all have conflicts with each other， so let's put T4 down here and I know a little bit about what's coming up so let me like draw those lines kind of big but we've already got a T2 and a T3 conflict represented there so we've already sort of got this triangular conflict going up。

Okay， great， actually you know what， I don't want to draw those once big。

 I'm going to go ahead and draw draw those small the way you have in the past。

And we leave the next ones to be big， Okay， great， so now we've got T2 T3 drawn as sort of the standard triangle。

Got that。 Let's add in our T5。 Okay， and so this is the one where it's going to get a little bit annoying because we need。

 we already have T 2， T3 and T 4 all having conflicts with each other。 That's already represented。

 But now T 5 needs to have conflicts with all of them。 So let's give it the conflict with that。

And also with that and also with that， great， we've done that line。

And now we can see that T6 needs to have a conflict with just the two， so let's actually draw T6。

Here and it can be in conflict with T4 and T5。Great， we've done that。

 Now we're ready to do T 5 and T7。 Let's draw T 7 down here。Got that in conflict。

 same deal with that line， nothing changes， and then T9 is just off to the side。

I'm going to go ahead and do a graph coloring of this。

 It is totally fine if you all get a different coloring of this as long as you make sure the two neighbors right two things connected by an edge never share the same color as long as you have done that we are good to go so let me go ahead and I'll do t0 in blue。

Next one can be in yellow， great。 That little subgraph is fine。Let's do T2 in blue。

T3 had better not be blue， and T 4 had also better not be blue。 Let's go ahead and。Orange。

At this point， we can go ahead and we can have T 6 be blue。 That's no problem。

 but T 5 had better not be either blue or orange。 Oh， we have to add a new color。

 Let's give T5 green。 This makes sense right because we can see that T5 has to be not the same color as T4 or T2 or T3 or in fact T6 but。

呃。So okay， if we， we sort of go and look through the the things that it's in conflict with， right。

 it's this， which is blue， it's this， which is blue， it's this， which is orange， it's this。

 which is yellow。 So we'd better not have it be any of those colors。 right。

 We have to have it be something else。 And that's where we got our little green。

 And now let's go ahead and round it out with T 7。Which T7 can go back to being blue and T9 can be blue。

Do we feel comfy with our graph coloring？Fabulous。😊。

Okay we are going to take our five minute break come back together at 434 at which point we're going to swap over to garbage collection if you want to do the other side of your worksheet。

 here is how you would actually start writing out the basic block for this function right you can see that we have this special little notation for using the argument to our function。

 that's what we can see right here， if you want to fill out the rest of the IR down there。

 easy go for it， if you want to write the CFG fantastic go for it。

 and then we could draw the inference graph interference graph。But if not， take your stretch break。

变话有。The drama that I was see7。Would this be an okay representation of the graph？気持ちいし。

Is everything as long as all the edges are still in there。 It's totally fine。

 but it's hard for me to check that real quick So's see T 2 is in conflict with。

 it should be in conflict with T 3， T 4 and T 5， Great T 3， T 4， T 5， great。 That looks good。

 We want T 3 to be in conflict with T 2， T 4 and T 5。I mean， basically。

 these four are en conflictlfect with each other。 Yes。

 all four of those need to be in conflict with each other for tags in。 but yeah yeah。

 that looks okay。 have cross like that。That's equivalent， right。

 like the where we put it as if it's on a canvas or in a drawing doesn't mean anything。

 That's totally meaningless。 What's meaningful is the edges between notes。

So like the set of notes has to be the same and the set of edges between those node have to be the same。

 not something all this procedure and go。We just don't have time down very last week and we have multiple topics it would be in the IR layer。

We would actually go ahead and generate something that looks exactly like this。 So like。

 we would not go directly the way to assembly the way we have been right this whole time。

 we've been going basically straight down to assembly instructions where we have hard coded in。

 This is the register you would read from。 We would not do that anymore。 Instead。

 our code generator would admit something that looks just like this。

And then we would have the second step that would do this process。 Yeah。

 so this process would just be the register allocation。 And it would basically go through and say。

 okay， like for this temporary， we actually want that to go into this register。 And therefore。

 this is the actual concrete assembly instruction。 Would this be kind of the。Aimization stuff。

 it would make sense to do this and then do side loading。

This this would be the last step This is the thing that we do right at the end right like we've done all the transformations of the program structure that we want to and now we're ready to make those concrete instructions because right up until this point we benefit from being able to pretend we of all the intemporaries that we want we're doing all these various different things right the IT level like this is a little bit in terms of sort of。

Low levelness。 This is basically between the AS T， right， if you think about what an AS T is doing。

 right， like it is an abstract syntax tree。 It is abstracting away some things， right。

 It's hiding the fact that there were parents there were semicolons， whatever。

 So it's abstracting away some things， but it's still pretty close in structure to what the programmer wrote。

 like it has a lot in common with the source code。It really is a syntax tree， whereas this。

 this is getting down to something much closer to the instruction。

 So this is the thing that you want to actually have as your representation at this stage that you do。

Regstrister allocation。 It just doesn't。 It's a lot harder to try to do it beforehand。

 whereasas all those other optimizations that we're trying to do。 most of them are。

At the AC level so this isn't to say that you can never win any optimizations after this。

 so like people optimization you could absolutely do after because that's those one Do you remember peoplehole optimizations which is basically saying。

 okay， here's a window of this many assembly instructions and I'm just going to figure out if there's a shorter sequence of assembly instructions that would do the same thing。

So you could do that kind of thing after。This is something that we would get after having had the AST of manipulating the AST。

 it wouldn't make sense to do this before and then do a bunch of AST transfers。

Would it be possible to。我没钱。makes sense to do like an optimization like people and then do this optimization。

 And then if you do people optimization again， you would benefit would there be benefit。

OrAnd any of the optimization。Doing traditional people optimization on this IR is not possible。

 right， People optimization really is about having concrete assembly instructions。

So maybe you could come up with some sort of comparable people like how much deep do you want to go with optimization？

Yeah， I mean， you could come up with yeah some alternative optimization that would also like try to think sort of abstractly but like before you know what registers are actually being used。

 it's pretty hard to do that analysis and figure out oh， actually the sort of sort of。

 So like you could come up with something that would bear some similarities to people analysis。

 people optimization that you could do on LVMIR and I want to be clear L MIR is absolutely one of the representations that people use to do a bunch of them。

Like there are a bunch of other optimizations that you would do on this representation。

Probably wouldn't look a lot like people optimization though。But like， absolutely。

 like there are whole compilers that are built around。 Okay， we'll have just our front ends。

 and those are all popping at LVMR。 We'll have our backends。

 Those are all going from LVMR into the hardware they I actually care about。

 And in the middle on the LVMR representation， I'm going to do all kinds of wacky stuff that intended to optimize it。

 So absolutely， this is one of the representations you could use for doing。Orizations。Make sense。但是。

All right， I'm going to go ahead and bring us back together。

 I'm just real quick going to give you like if you had gone through this activity。

 here is basically what it would look like， I'm actually going to draw it out in a slightly friendlier way so this is sort of this is what you would actually get in terms of the IR representation。

 but I'm just going to represent the control flow between the basic blocks。

That will give you a sense of sort of how this would fit together I don't think it will be super surprising right if you remember how the if thens were structured when we saw the original thing and remember these of course are directed edges。

 we have sort of this outer if that's being built up right here and then once we get to L3 we're doing this inner if and so we have L3 can go to L4 or to L5 and then we can go ahead and bring them back together to sort of the implicit L6 right L6 is basically an exit。

That's what we got there， and then we can go ahead and have L2 also go to L6 because that's just the end of the outer if。

But we are not going to spend a lot of time on this because we now want a cover garbage collection。

 so let's open up the books on garbage， I'll leave that up there for one moment if anyone wants to copy it down。

And then we'll swap over to garbage collection。AhYeah， so if we take a look at let me。Show， okay， so。

Where would be a point where we would actually need a feed node here。So say we actually have。

 let me bring us back to our old one。 So in our old one， where was it？

So here we have this situation where we had this T 5 thing。

 right And T 5 had to take on a particular value based on whether we went down one path or the other。

That's the situation where we。If we're just going down different paths out whatever。

 but if we're going to have to go ahead and resolve， okay。

 did we get the value associated with T3 versus the value associated with T4。

 all of a sudden then we need it。Yeah， really good question。

All right I'm going bring us into garbage collection land。

 So here we are thinking about garbage collection。 for those who read this story earlier。

 I think it's funny just to think about how recently garbage collection was still sort of a wacky idea that people were finding really weird and really interesting。

 And you know if you're reading sort of an old classic P paper。

 it's funny to come across a story like this where they they were doing their demo and all of a sudden the garbage collector ran and I printed out a bunch of data about the garbage collector and they hadn't talked in the talk about the garbage collector so everyone thought they had been。

Okay。So here's a program we've been writing the entire time。 We've been in this class。 Okay。

 not the whole time。 But as soon as we introduce pairs， we might write something like this。

 And so basically， what's happening right， is we're going ahead， we're making a pair。

 And then as soon as we've actually made the pair， we go ahead and read out the right hand side of it。

And that's all we ever actually use。 right， We go ahead， we grab out the right。

 So what would happen if we actually are using this to think about， okay。

 what's going to happen on the heap。I want you to go ahead and just reflect with folks for。

 I don't know， a moment。What would happen。Okay， this is not super interesting， but basically。

 we're going to go ahead and we're going to make a pair right in our first available slot on the heap。

 which is going to be these two blocks because remember we always have both the left and the right represented。

 And so what would we put in there。 Well， we would go ahead and we would put in， you know。

 to the first item， the left item。 and then whatever we got back from the readum， I don't know。

 Maybe we get。Or I don't know， well， this would actually be the runtime representation of two。

 and so that would actually be。And this would actually be 16， whatever。

And so we'd have that all stored in there。 but then if we are doing this program where the very first thing we do is grab out the right。

 then all of a sudden this is actually the only thing we care about right and we've just got this sitting around here but because we never ever。

 ever take RDI back down from right because we left we've done that we put RDI to 16 right we never actually put RDI lower so this value would just be sitting here forever for no reason right for as long as we're running the program。

It's kind of weird， it's definitely something that I remember we were having questions about at the time of like。

 hey。It is really strange that we're just incrementing RDI and incrementing RDI and incrementing RDI。

 and we just throw garbage on there。And so what are our solutions that we could take to this problem。

 There are a couple of different things。 So those of you who have ever programmed with the language like see。

 you might be familiar with the idea that okay， we can make the programmer。

 tell us when they are done with some memory so we can go ahead and say， all right。

 like you're in charge of this programmer。 you have to tell me when you are sick of using the heap for this。

 and you're not planning to access this anymore。 you can go ahead and make your calls to free。

 and that will actually mean that we are gonna to go in and we're gonna remove that from the heap and make that space available for storing something else。

 That would be fine。 This can be fairly error pro right So if you go ahead and have programmers do this。

 they will make errors in both directions。 they will forget to free stuff and then they will end up leaking a bunch of memory。

 They will free stuff before they're actually ready to free it。

 and then we will actually go in to read the thing at that memory line we'll have all kinds of problems So you can run into trouble both directions。

 if you leave it up to the programmer And so a solution that some folks thought up and that has been useful across the。

Languages is garbage collection。 So this is our whirlwind tour of garbage collection。

We'll start with the basics。Basically， the basics is let's have our runtime。 Remember， runtime。 Z。

 our same old program that's in charge of so many things about what's happening sort of in the actual execution period of our program。

 We can have the runtime be keeping track of heat memory that we're not using anymore and freeing it right。

 saying， okay， let me just go figure out what's not in use anymore。 and I will just say it let me。

Now。That is blousing over a little bit， how complicated it is to figure out what is no longer in use。

 and so all of the fun magic of garbage collection comes in answering that question。

 how do we figure out what is no longer in use？So the ideal， right。

 if we were sort of in our dream worlds， the ideal would be we go ahead and figure out by analyzing the program what memory is never。

 ever， ever going to be used again。Now that analysis is incredibly hard because program analysis in general is incredibly hard。

 so what people actually do is they say okay， let's do something conservative but that's going to get rid of a lot of it right so let's figure out any memory that is not reachable。

Right， so it's still possible that there's gonna to be stuff that's in memory that is reachable that we're not ever going actually use again。

 right， We for some reason， we still have a pointer to it。 We still have a handle to it。

 but we're never actually going to use that pointer。 We're never actually going access that memory。

We are gonna go ahead and leave that in memory， which is a little bit wasteful of space。

 but we're never gonna have the opposite problem， which is a much worse problem of getting rid of something that the user is actually going to use later。

 And so by doing this， we do something that's a lot cheaper compared to actually analyzing the entire program and figuring out what is still going to be used。

 And we get to go ahead and do this process in a way that is safe。It's okay。

 we might end up leaving be some memory that we won't actually need in future， but it's okay。

 that's still safe。So this is the cosic mark and sweep garbage collection。 This is basically just。

 okay， we're going start at the roots， right， So roots is basically just， you know。

 there's some parts of our storage that we know might be pointing into the heap right So we're gonna do some kind of analysis on our storage based on knowing the semantics of our language and how we store pointers into memory。

 We're going to go ahead and do some kind of analysis， starting at those roots。

 And we're going to go ahead and traverse into the memory。

 So we start by just following all of those pointers into the memory。

 And we start marking everything that's reachable。 right So the very first thing that those handles into memory point to fantastic。

 those are reachable。 Anything you can reach from those places also reachable。

 And then we basically do after we have finished going through that reachability analysis。

 we go ahead and we just sweep through the memory linearly， we start the top。

 We go through to the bottom until we have figured out， okay， this one was marked reachable。

 This one wasn't。 This one was marked reachable。 This one wasn't。😊。

Then when we get to the point of needing to use heat in future， instead of just saying， okay。

 whatever is the next slot after what we've written before， we grab something out of the free list。

 right so this thing， this garbage collector is now going to be responsible for keeping track of what segments of our he are available and what segments are not and when we actually need to use memory。

 we're just going go ahead and grab something out of the free list。

Freelist is actually a lot more complicated than you might initially assume， right， basically。

 you can go through and you can do this thing of keeping track of the things that are two words long。

 the things that are four words long， things that are n words long。It gets a little bit complicated。

 so I am going to also introduce us to some alternatives here。

But what I would first want to do is make this a little bit more concrete。

 So here we go I've done a sort of simplified version of the kind of picture that we would produce from our programming language I have not tagged things with the usual tags and so that's a little bit wacky because actually the way that we would figure out roots would be by knowing the tags。

 But what I want you to do with folks nearby right now is figure out on this diagram。

 what are some roots， what are some things that are stored either in registers or in the stacks that look like they are pointers into our memory。

All right， what do't we think about this， Does this look like a root。

 does this look like a pointer into our memory， hum， if you think yes？How if you think no？Okay。

 interesting， so to me， this absolutely looks like a pointer into our memory right I'm thinking。

 okay， it looks like we've got a representation of this function that maybe we're about to call and so I'm going go ahead and call that a route right This is telling me that this closure store right here is something that I am still going to need access to going forward。

 maybe in fact I'm about to call that function So if garbage collection has been called right here at this point in time during this execution of the program where we have this state。

 I'm going to say okay， I better not actually like to read this from memory。

 I might be about to actually use that closure。So okay， let's not actually delete that。

 let's get rid of。What about this， hum if you think this is going to be a root？

How if you think this is not going to be a root？Yeah， I agree。

 So this is weird because this is certainly something that is pointing into the range of our heap right like we know that this next slot would be something that be sort of within the heap because we sort of know what the range of addresses are And so in many ways this absolutely looks like a pointer into the heap。

 but we know that we are specifically using RDI in order to represent the next free space on the heap and so we know that we should not actually treat that as a root and we should not actually treat what's in there as reachable。

So I'm going to go ahead and say， okay， that one is not going to be one of our roots。

 or we'm not going to put that in a box。What about this one， How do you think this one is a root？

Hum if you think this is not a route。Yeah， I agree so this is a root right so we can take a look at this and we can see yep。

 it looks like that is pointing us to a pair which seems to be situated right here。

 so I would go ahead and call that a root。So if I went ahead and did my reachability analysis based on these two roots。

 well， I'm going to go ahead and follow this one first， right， and I'm going to go ahead and say。

 yep， it looks like this thing that I can reach from there is reachable。

 so I'm going to highlight that in green。And then I would follow this route right here。

 and I would say， yep， it looks like everything here is reachable because that's what that pair is。😊。

And then I'm gonna go ahead first， you know， I have to now do my next step of my reachability analysis where I say。

 okay at each of these points， right， I would look at this。 And I would say， okay， well。

 is that itself a pointer into our heap。 No， it looks like that's an address for an instruction。

 right， so we're not gonna need to actually treat that as a pointer into the heap。

 I this a pointer to the heap。 No， that's the number 16， I this a pointer into the heap。 No。

 that's the boolean value， that's the boolean value false。 So okay。

 I've done now the mark part right， go ahead and cross off having done mark。

 I'm now ready to do the sweep。 So let's switch to our red highlighter。

 and let's check for each of these。 Okay， is this first one， I that actually going to be reachable。

 Yes， I had better not free that。 So let's go ahead and not free that。 What about this one。

 I that reachable， That is not reachable。 I can free that。 Let's highlight that in red。

 We can go ahead and free that up， And now something else can use that。

And then I'll check the next line and it's March check the next line and it's March。

Questions about how this worked in this sort of simplified case。

How do we know we're never going to increment？How we know we're not going to check。Addres oh， oh。

 I love this question。 Okay， yes， so this question was， hey。

 what if my programmer chose to then like add8 to RA X right like the program for some reason is going to do that and then it is going to access this great question。

 So if our programming language would allow that kind of thing to happen right if it is saying I am committing to closures being stored at a particular space on the heap and you're allowed to go in there and mess around like grab them out not by name。

 but by doing this kind of manipulation with the pointers， then absolutely we're out of luck。

 we better not free that。 Yes， that is a great question。 But if our programming language says no no。

 no， like the way you're allowed to access way you're allowed to access closures is by name。

They okay。Kind of makes fun。Like the待。Great question。 So this is basically saying like hey。

 we've got this pair stored here and we need to actually look at all of the pair so we are taking advantage of yes knowing what the thing is that are stored there and again knowing of our language if this was in fact a pointer to another pair right which could have happened right so well I think it would have gone this direction it would have gone the other direction but say that this was actually a pointer to this pair then yes we would have checked this too and we would have also marked that this was reachable。

Is that the question。Yeah， so we are absolutely taking advantage of knowing the semantics of our own language and knowing what's allowed within it。

There question over there。Okay， I'm going to complicate this story a little bit。嗯。

So finding our roots。 Oh， okay， yeah， So one thing that's a little bit annoying is you saw up there that all of a sudden。

 we have this sort of one blank space。 right， There was the one spot that we were able to mark red and say。

 yep， free that up。 We end up getting this sort of like Swiss cheese pattern in our heap。

 which is not ideal。 We don't really want to have all of these right。

 Like this is why we end up having to keep this free list。

 And so there are some alternatives that people have come up with other ways of doing garbage collection。

 One is stop and copy。 This is the way that I think is most natural for us to sort of think about making our compilers still work really very similarly。

 but actually still having garbage collection would be we keep two semi spaces。

 We don't have just one big space that is our heap。 We have the two semi spaces。

 We're always keeping one of them empty。Does mean that we're needing two times the memory compared to what we can actually use。

 And basically， in one of them， we're going ahead。 We're just like writing into it like normal。

 And then at some point we say， okay， I'm ready to go ahead and actually run garbage collection。

 I'm gonna figure out which things are still in use。

 And all of those are going get copied into a continuous portion of the other semi space， right。

 And then the other。Through out， we keep adding to this one until we run out。

 we go ahead and do the exact same thing and we start in the next time space。Not too surprising。

 probably once you see the idea， but are there questions about that。

So one thing that I think was maybe actually sort of the underlying question here。

 but maybe not maybe it's just related is how do we actually know what is a pointer。

RightSo if you remember way back at the start of the class when we were starting to represent numbers and we figured out that。

 hey， actually Oaml only has 63 bits available to us inside these ins like it's so weird。

 we've got 64 bits of space。 but we've only got these 63 what's going on。

 Why is that happening It turns out that what's happening is Ocal is actually using one of those bits in order to represent whether a given item is a pointer or not and it's using tag0 for things that are pointers so that it can basically just use it exactly as the address it's not having to take a bit on and off all the time。

 So it's just going ahead and going straight to that memory address when it's got it as a pointer And then if it's a number。

 it's got the one in there instead。 so that's why Ocal's representation is actually losing a bit so it can do garbage collection for us and it's actually labeling which things are pointers with this In Java。

 you've got the tag bits in the me。Data。See， I think it's actually the most interesting case for us。

 right， because we don't know， we don't know。 There are things we can do， though。

 to make some educated guesses。Okay， yeah。 So obviously。

 what we just saw does require that we actually know the locations of roots and pointers。

 we need to actually be able to find that also inside heat allocated objects。

 So once we have done that first step of our reachability analysis。

 we've got to go ahead and go through all that object， whatever that may be and say， okay。

 this part of the pair is pointing to another thing that is also in the heat price， we've got to go。

Pohysitionians of somes change during execution， that's also something we have to think about。

So basically， your highlight becomes responsible for keeping track of where roots are and what things are going to be roots or not。

嗯。This is where we come back to the fact that， for example in。

We don't have any of the needed information right like C was not designed to work with a garbage collector。

 it was just designed to sort of let you do your own thing to do free as the programmer to go ahead and sort keep track of all of this as the programmer and do that reasoning。

But。Is actually possible to make a garbage collector for C if you want。 And， in fact， there is one。

 It's called the Boem collector。 They've gone ahead and made it for C and C plus plus。

The trick is basically that you guess， right， you just try to be conservative。

So if something is in the range， right， like we know where our heap starts and ends， right。

 if you remember in our runtime， we went ahead and we said grab us out this many bites and we can go ahead and at that point know where our heap starts。

 where our heap ends。If you see any value that actually is in that range。

 just assume that it is a pointer right assume that it's a pointer and assume that it is just going to mean that we are going to access that memory somewhere down the line。

 Now， this also means that you might just have a number that happens to be in that range right。

 it's just for you know random reasons， ended up being in the range that is also the range of the addresses of the heap and that might also appear to this analysis as though that is a pointer into the memory that you actually need to preserve whatever appears there。

That's fine， right， That means that you're not going to delete something that otherwise you could have deleted if you had a better analysis。

 but that's still safe we're leaking a little bit of memory。

 but it's not going to be too much memory because that's not going to happen all the time and we're actually going to avoid doing the much worse thing of deleting something that we should not have deleted。

That all kind of makes sense how they can guess by just knowing the range of memory addresses for the heap。

Feels more or less good。Good， all right。Other garbage collection variants that are useful to know。

 generational garbage collection is basically just keeping the knowledge in mind that often we sort of use the he thing where we're using it very briefly。

 and then we're basically done with it。 And we put something else on the when we're using it briefly and it done。

 But then we have a few things that are longlived。 This is basically keeping track of that and saying。

 okay， we're gonna have this one that is for the things that have been staying and staying and saying。

 And we're gonna garbage collect the young memory really often。

 So we're constantly clearing that out and trying to keep that low。

 And if we find that after doing that process many times。

 we've got something that's sticking around a lot。 Okay。

 we're gonna go ahead and shift that over into the old garbage collection。😊。

Another thing that's often actually taught in classes but is actually super rare in practice is reference counting garbage collection。

 and this is basically we can just track throughout execution of the program how many things are pointing to a given item on the heap and if we get down to zero。

 great， we free it at that point。This gets complicated because， of course， you can have cycles。

 if you've got a cycle you're not really going to get out of that。 So it's also super expensive。

 So again， this really doesn't get used in practice。 but it is interesting to know about。

 And it's interesting to think about。There is also。Increasingly。AndRecently。

 this is sort of something that's thinking about being sort of an intermediate ground between manualm memory management and automatic memory management like garbage collection。

 it does have some downsides right it's easy for the programmer and that they're not having to think about it but it is unpredictable right if we think about the silly demo story at the beginning where all of a sudden it ran in the middle of a big demo and like it can be expensive if you have something that has really intense realtime guarantees and your garbage collector starts at just the wrong moment now suddenly it's two or three milliseconds slower than you intended to be whatever that can actually be a problem in some settings and so the unpredictability of garbage collection can be bad。

And so another thing that folks will do is recognizing that full on manual memory management is very painful and very error prone。

 will'll say， okay， I'm going give you the programmer a region to play with right whatever you want into the region。

 go ahead and fill it up， don't worry about like when you are gonna free any individual thing。

 But once you are done with everything you are trying to do in that region at that point。

 go ahead and just knock it out， we'll take care of freeing it up for you。

 and then you can have that space back。So that's another sort of intermediate position。

Do we have time to actually do our activity？Oh dear， okay。

 I will show us the answer to the activity at the very beginning of next class as we are sort of waiting to start class。

 but this is also a good time for questions。Oh great question。

 So this question is is garbage collection run at the end versus in the middle So you don't need garbage collection at the end because at the end。

 the program is done right once the program is done， you can free all of that memory。

 Nothing else should be playing with that again maybe written into the file system but the heat that's over right in the same way that the stack is over like those parts of the storage that are just like the thing that the program is using those go away when the program is done so you don't need garbage collection at that point。

 garbagebage collection is something you do if you need to make sure you're not overloading the memory during the course of the execution of the program and you're gonna need to free up some memory in order to use it for something else later in the program。

也没吹。Which is why that unpredictability can be a huge issue。



![](img/e62751841bd14a3f7682204d0ca31d5b_2.png)