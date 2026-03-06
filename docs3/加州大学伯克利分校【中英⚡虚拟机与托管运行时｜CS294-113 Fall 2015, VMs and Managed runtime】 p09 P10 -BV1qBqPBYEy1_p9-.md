# 加州大学伯克利分校【中英⚡虚拟机与托管运行时｜CS294-113 Fall 2015, VMs and Managed runtime】 p09 P10 -BV1qBqPBYEy1_p9-

O。Thank you。Okay， so today we will un Raapppa。On the optimization staff。

And as I was putting in the slides today。This week I was thinking this is kind of the whole。

 the point of the course is this section， right， it's kind of been building up to get to here。

So that you can understand this material because this basically will give you。An overview of。

What's been discovered to be very successful in production and that's aimed several different production virtual machines that are widely。

So this kind of catches us up with a state of the art of production development and the rest of the course is really stuff that's still in research but hasn't yet sort of made it out of production yet。

 some promising stuff， but nothing that's yet。Proven like this stuff it。

So today I'm going to finish off the kind of， you know， we started on some optimization technique。

Now finish that off with a discussion of in li。And then we'll look at how all of those things are brought together through adaptive feedback driven optimization and teeth compilation。

So last week we looked at splitting and customization。And。Some of the thing I can't remember。

 but this is the biggie inlining is the biggie in terms of optimizations done dynamically。

Because it does two things， you know at first people thought it was a biggie because it removed coal overhead。

 but actually that's not the important part， that's nice。

 but the important part is that it makes your compilation unit that much bigger and your compiler has that much more to analyse。

And exposed to optimizationization techniques and you kind of want to get as much in your hand as possible when you're optimizing that so that you can squeeze as much。

啊。I said that， so inlining， obviously you can only inline if you know what you're going to call。

You don't know what you're going to call and call on。

So that's why the static binding stuff that we were looking at last week。

 the inline caches and other techniques and allow you to say， oh， I think I'm calling this。

That's why that's important it turns out that again that was just kind of on the road to get in here along the way that seemed like an important optimization technique but it gives us the ability now to start making guesses as to what we actually want to inline and that's really important because it makes a huge difference if you do it wrong however you know you can really expand the code for no good reason so it has to be done judiciously so the combination of this optimization either optimizations and the adaptive feedback framework will give us a way of doing really good inline。

It's really interesting to note that if you go back in the literature and look at stuff in the '80s and '90s about inlining in static compilers。

 there were a bunch of people who tried it and more or less when you look at those papers they kind of go in it makes things a little faster but it doesn't really seem to make much difference。

And that's because without the dynamic behavior。It's really hard to know what to inline and when to stop。

And so it's really easy to do it wrong but ining the wrong thing or over in line or under in line。

 whereas the observation gives us a much better hand us to what we should be doing。

So what's the big deal of this is recording， by the way， in the Cham？

So the big deal is that we get to take a bunch of IR for the thing we're inlining and the IR that we're inlining into and connect those two up and start doing the analyses across them so we connect。

 you know this is now in the context of an optimizing compiler。

 not in the context of a simple J and this isn't a compiler goes and I'm going to teach you how to write an optimizing compiler。

Oh of course I'm just going to talk about the application in this context。

So you you have control and data flow analysis techniques you can now connect all of those up together。

 you can do in particular the trick of when you see control that was previously sort of an openenddie thing like throwing an section or a nonlocal return from a closure if you can inline that into the lexical context or you can inline it deep enough into the handle now you can just turn that into a goes right suddenly those things become really。

 really cheap。哦。And especially in the context of a closure written language。

 right once you inline the closure into its le context。

 you don't really need closure anymore so that makes a bunch of stuff。Much more tractable。嗯。

And of course it opens the doors to further optimizations。

 including more inlining so once you've inlined now you know the call of the thing you've inlined and you can keep inlining and inlining and inlining。

So nothing， I think works better than an example。So I'm going to run through a long example。

And this was lifted out of one of the early self papers and I'll give you a bit more context after we've gone through an example。

 but this basically takes all the stuff we looked at last week， customization， splitting。

 primitive handling on common branches and traps。In combination within lining and take something that's a pretty abstract and you would think fairly inefficient piece of code and transforms into something that's pretty much as good as you can get。

Through just the repeated application of these techniques。So the example。We have this method。

In self called sum2， so you send sum two to a number with another number， usually integers。

 and it just adds up all of the numbers in between。Very simple。 And the implementation of that。嗯。

Botoms out in a loop that looks like this basically it starts by doing what we walk through it more closely。

 but it bottoms out in this loop， which is a wild loop。In as it's normally expressed in。

 that you have a loop with a wild thing and a couple of closures and inside the closure。

 you're evaluating the body of the loop。Blocked by executinging its block and then incrementing the control variable until we reach the end。

Now， if you compile and look at the bycodes for that， you see this。RightThere's no go tos。

 there's no loop here， this is just push a closure， push a closure。

 send a while through none of this is control flow at the language level。

 is control flow only when you've beenline down and got down。

 you know got to the bottom of where you're actually doing stuff。

So generating a loop from this is a non trivial exercise because there ain't no loop here， right。

 this wild troop could do anything， you know， and you can redefine it。

So let's walk through the example。So we start off with the sun to call。

And the method for that looks like this。So if sum two tick an upper bound。

 it has a sum variable initialized to zero and then it just executes a do from self。

 which is in this case one， throws through the upper bound。

 adding some adding index onto the sum and reassigning some fairly straightforward。

And if we look for the。The code for。To do， which is the first thing we're going to execute in there。

like this。So to do just says， okay， I'm doing the more general loop in increments of one。

So first thing we do is we inline that into there。Sop aman up with something that looks like this。

So after our first inline step， we've done this。We look up。

What that method does too by doing and now we're getting some real control structure here except because it's expresseding en closures。

So here， this isn't exactly the same as the current definition of this by the way。

 this is the well fruit of the paper 20 years ago， if you look online， it's slightly different。嗯。

So all this does is said， well if we're stepping by zero that's probably not a good idea。

 that's an error， we're stepping by less than zero then we're stepping down and it has a different version of the loop where it decrements by the light that just as the spaces type。

 otherwise then we have that loop that I showed you on the other slide which is just going to step through the control variable executing the block that's on the inside。

 which is this somepl index block。So we're going to in that。

And when we've done all the subution things we， it was something like that。

First thing to look at there is the test at the beginning， one equals zero， now you might think。

 okay one equals zero false， easy no， no equals is another message， right， equals as a message。

Defined on numbers takes another number and that tests calls an underlying system primitive。

 which is the real definition of integer equality and if for some reason that says I can't do this like for example。

 the argument isn't a number， then it calls a failure part of this defined at this point。

So we're going to inline that。And because we're calling the primitive。

Then the compiler knows about the premise here。It knows that has no side effects。

 So it can call it compile time， and it can get back the faults。 So now it can。

Why that next inlin step will resolve that out to be false and so now we end up with false。

 if true or false， and we have to go through the same process。

If true or false is not built in control structure。It's a definition。 and the definition。

So it's a definition on two singleton objects， one is called true and the other is called false if you send it。

To true， then the true box gets evaluated if you send it to false， the false box gets evaluated。

 so to deal with this。Control flow， we have to inline again。有呢。

Gets us down through one or two steps I we'm going to start aligning things otherwise we'll be here a long time to this where we've now taken the false block。

And we're just evaluating it by sending it value。That turns out to be another invocation of a primitive which is closure evaluation once we've in line to that we can combine that with a literal and say well closure under our value is the same as the code within closure and we can go rid closure brackets so we're now down to that level and we're going to go through exactly the same steps for one less than zero I'm going to lie all the intermediate steps so now we're down to the inner loop and we've in line and folded our way down to this。

So now we have to deal with the the wild true and wild true is defined。

As a closure that loops infinitely。Inside it tests the condition and if the condition turns out to be true。

 we evaluate the body of loop， if it turns out to be false， we return from this method。

So the Uarrow is a return here， and it's a return。To the caller of the thing of this message。

 right So that would be this because this is what's evaluating well true。

 So this's return with be count of all of this looping and closure analysis has come back out to right here。

是。Once we've outlined lined that。This isn't really a block with a return now it's really a block with a return。

To this point here。Invocation of loop and so that。Come very replace with a ghosthead。

Because that's where it's going， We can get rid of that walking Island。So next step then。

Is to deal with these blocks so we have it sameim as before a block with a direct evaluation message by looking that up and inlining。

 we can remove the bracket so I'm going to do that in one step。Dont we get down to this loop。

And now we have to deal with the loop method and the definition of loop。

On a block is simply execute the block and then invoke this primitive。

 which just restarts this method so the restart can be put in any method and it just restarts the method it's in black。

So that's like a girl who's the beginning。So when we've in line to that。In there。And。

To transform the restart into a go to， we end up with something that looks like this and I'm writing the non selfie stuff in italics to indicate you know。

 something else is going on in the underlying IR。Okay， so what do we do with that Now。

 we're going to look at the。Comparison operator。And here's where we need to do our guesswork now because the comparison operator。

 if we looked at that one， we don't know what the type of the argument is。

 so we can't sit can't just fold that and say oh we know it integer arithmetic。

 we have to do some speculation here so this is where we split that comparison operators knowing that comparisons are usually on integers。

And we we split it into two cases where we're going to。Text。

Receives see whether it's integer tagged and if so。

 then we have to do the comparison with the knowledge that's an integer。

 otherwise we still have to do the full send。Well， we can do that again。

 now making a guess about the type of upper bound and include that test and now what we're going to do。

Its。の step。We're going to have two tests。So we're going to speculate。

That test whether both of those things are integers， if they are that we can do for integer。

 you know the version， this is like the C version where the in here is D tagag there。

And that's the C comparison operatorss。 Otherwise we're doing the full。The full send， knowing that。

Recer is an end but we don't， the argument is otherwise it's neither of those cases。

 then we still have to do the full thing。Well， we had the splitting technique last week where we could take a control flow and duplicate after the merge point onto the end of those and so we can do some of those tricks here in particular。

 we can see that，That comparison。Compar only is setting the variable which is used in control flow。

That can be rewritten。And where we couldn't rewrite it is。As control flow。 So we move the。

The control the tax into control flow， we set a little lane。

Which is now going to communicate the outcome。To the end， and we can now stop doing。呃。

Uncommon analysis down here， because we're going to speculate that this branch and this branch are uncommon。

 This is the only one we care about。So we can connect this one to the it's used down here and start repeating the analysis。

In particular， if we move that code。For the true and false cases and into the true and false cases the controls law we now end up。

With that again， I'm aligning a couple of steps here where we're inlining the tests and discovering it really is control flow before we copy up here。

The pace is accelerating as I' going through this。So now we've got to the point where we have control flow on the common path。

 we still have self messages here。For these arithmetic operations。

 but everything else now is just control for or in commonumbent traps， which will。

 which will eventually， the inent traps will go into interpretation or de optimizeimized code to resume execution。

So now we can analyze those。That's another example where we can say。

 let's guess they're both going to the ends， in fact we already have。

The fact that this is an ink from this initialization and with a flow analysis。

 we could show that that propagates round and we already know I is an ink。

So we can fairly safely put in that。嗯。Rewrite and because self has arbitrary precision arithmetic after the are arithmetic。

 we have to test for the overflow。And deal with that and convert to a big end if it happens to be a big end。

We do the same for the eye， get I plus one。That's easy because we're in the method。

That can be customized on small ends， so we know I is a small end。

The only thing we don't know is whether it's going to overflow or not。

 so we have to do the same kind of thing that we can transform it into an addition and an overflow test。

And now we've kind of got to the bottom， we just have kind of a ragged control structure and if you clean up the ragged control structure。

And reorder a little bit。Well， one more step， we know this guy has an integer tag because we're customizing on small。

 so that can be highlighteded。Now we're down to this for the Ha tag here。

We can convert that into an uncommon trap and move it out of the loop。 so we push。

 pull the guard out。So now weve do a little test。And the trap。And inside the liver。

 we're just doing arithmetic and testing。And with a better of cleanup of control flow。

 we end up with this。And if you look at this now， this is kind of as good as you' going to get。

It's the only things that are happening in here that are not in the equivalent of what the C compiler meant are because we don't know the type of the incoming arguments that we have to test for about。

And we have to check for overflow because the language deals with arbitrary precisionism。

So we're going to back out and regenerate。And if we did get the overflows， then we'd recompile。

 these wouldn't be uncommon traps， we'd didn't line the call to the transition of times。

But it's really pretty good at this point。So it's as the paper points out。

 it's kind of as efficient as it can be， given its's dynamically typed and overflow here。

And that's from 19。89 paper， I think， by Craig Chambos。And this all worked， this is not made out。

 the compiler actually did this。In practice。 so during your mininging steps。

These little things where you have to evaluate like one less than zero。Take one lesson zero here。

false。So do you have to have a general partially evaluator to do that？

So because it bottomed out a small talk self primitive。Which you could tell by the underscore。

 that has a fixed meaning which is built into the VM and which the compiler can in principle know about。

At that point。You can just call that， It also knows which of those things side effect for。

So it knows which ones it can call safely， the integer wallss obviously can call safely because they have no side。

And so it doesn't have to have a general partial of valuevalrs he just has to know。

 can I call it safely pile time？To get the right answer and the answer for that case is yes。

 so it does。Yes， what are the cost of these uncommon traps。

 Like is there a separate piece of code for each of these uncommon traps or do they all point to the same thing。

 So each one of these would be a trap instruction， and they have to be different because they have to have different。

Continuations in effect because if you trap out of here。

 you're in a different state in terms of what you know about the world and if you trap out of here so associated with each of these there are data structures that tell you what's going to happen。

 what needs to happen and that will get to that I'll go into some detail how that works。What else。

 and here's the reference。I just lifted the code down fairly direct。嗯。是吗。So additional comments。

There's a lot of compilation for not much code。Right。

 so one of the things that we want to really be sure we're doing is we're not doing all this optimization if this thing's only going to get called once because that's never been to pay off right that's a lot of transformations on IR。

Is going to be probably。Many， many tens， hundreds of thousands of cycles in doing that analysis。

You know， for if we're all we're doing is sum one to five， it's not going to pay off。

 So we look at how we make that decision。Shortly and that you know。

 the remaining sign branches are really there now only to deal with the safety issues and to transition to the compiler。

And do think。Do the conversions。 Let me see if I can。D two代。

I'm going to switch the mirroring because I don't have to stare this screen。Whi。O。

I'm Sc to the bottom。What I will do。建。The terminal。但。Inist。You can see my tube。我们就下。Just right here。

Okay， so let's fire the cellium on this example unlike the others is going to be all off the command line。

Not in the environment。Which is fairly unusual。You're all hackers by now。Next shot。Okay。

 so now we're in the self。System。哎呀 check。ち私で。Oops。Okay。

 so I'm going to turn on using one of these primitives。你。Logging of compilations。

So this is basically a simple boolean set deep in the guts of the VM that whens on。

Every time the VM compiles， it will print out a little。想有。Quite a few just in dealing with。The。

Loop of the。Evaluation of that thing in the。Okay， so I'm going to head a return a few times and make things stabilize a bit。

And now。A run example。6。向前。Let's do 10，000。And that showed。Itive us a bunch of compilations。

And if we look in here。Somewhere not list。Ho is there some too。

 So the neck is the non inlining compiler。 That's the equivalent of a simple gen。And the sick is the。

呃。for simple in learning compiler。So that got actually got invoked after a bunch of iterations to recompile some too。

There we go compilation count took two milliseconds and did a whole bunch of optimization。

So thoses the dynamic compilation take now I actually want this really optimized before I do the next step。

 so I' going to turn the compilation off。We drowning lot。And then I'm going to do。

A whole bunch of those。心车。单位上。WeS up running。And while that's run now in that control C。

 which will interrupt。Executions， and now we have two self level processes in here。

And we can take a look at them。 So I'm going to look at process0。I'm going to supend it。

Now it's lying there。Tone in the， in the heatap。Was to look at。And I can。呃，是。

As is a little shorthand that says take this number you notice when it prints stuff out it put little handles in numeric brackets。

 so if you want to talk about the object you can just do as object on that number and there's a little table of stuff it printed out so you could talk for things that came out with earlier prints。

So I'm on that， I'm going to invoke the primitive print。🤢，Process stacks and a process。

 a self process。And we see。The stack of the interrupted process， which somewhere up appear。

Should have or sun to near。So， here is。The top level expression， there's a do see the。

The code in this version is slightly different， it doesn't have a look at directly in the top level it breaks out subcase with these。

And there's all the ifs and the values。 And so this is sort of what you would see。

From an interpreter stack of what， you know， it looks as if we're doing source level execution here。

 interpretation step by sta execution， and you can't really tell。That it's compiled in any way。

All you can do is see all the code， but。It's long more of a trick。生气了，我为着吃啊。

We can turn on the wizard now。Yeah。When we turn on a wizard mount。And do that print again。

We got wizard information。Okay， so now each line。Is annotated with two hex numbers and the hex numbers are the address of the frame in memory。

And the return address from that frame。So if we look and obviously I you know I hit control。

 see some arbitrary points that we may have got unly and not have much of a stamp here， but。

And we'll see what we got。To the top of this。So we've got。

Every time these numbers of the sand were in line。We' had one friend。S can。

That's the top of this current scan。That guy was in line into that guy。

 which was in line into that guy， which was in line into that guy。

Which was in lined into that guy and so on and so on。And so on。很奢望。嗯。

Wheres the transition There's the transition， So those2 another%%。Okay。

I've done this a bunch of times， not recently， but in the past。ButAnd whenever I do this。

 usually I find about 10。10 frames collapsed into one。

Itself and you have to do this massively aggressive inlining to get rid of all of that closure control structure and expose the actual underlying real control structure to get efficient code。

And this compiler was the first to sort of do this massive， really aggressive inlining。

 there's almost no optimization other than inlining。It's just minor stuff。嗯。

knowSptting and customization because no， there was very little in the way。

 classical optimization in the system。O。You guys have a really nice IR too。弱べさ。哎啊。

This particular system had a very simple IR that was very close to South bycode it was not a very sophisticated English which was why it didn't do a lot of sophisticated low level optimization。

As well， if you look out， send the hotspot server compiler。

Then that has a very sophisticated SSA line。IR called C Nows， in fact。

 was a reference to the paperPo describing that in the click reading。

And that uses this much lower level IR with much more aggressive optimization in south。

 it pushes a lot further than south in terms of optimization。Inse。

 because it did the inline and that was like 90% of the game was right there。

 you could probably make it a bit faster through heavy duty optimization。hy rise I have to graduate。

跟完成。O。So。Important thing then。Assuming we can now cranamp the handle on these optimizations is to pick when and where we apply them。

Because if they're implied incautiously。Bad things happened， we can't do it。

In a just in time environment because we don't know enough。

 if you you're running the compiler at the point of first execution。

 all you know is this code is going to be executed once， you don't know any。

 you don't have any type information you hand apart from the arguments being flow passed in。

 you don't have any patents to go off to guide your inlining， any history to go off。So， instead。

What we'll do is we'll run unoptimized for a while。With a simple compiler or an interpreter。

 and then selectively discover hotspot and apply an optimizing compiler。And。

And that's the advantage is that we can observe what's going on and gather the information that we need to make the decisions very。

 very carefully so remember this graph。From a couple of weeks ago tiered comp of simple compilation when you have an interpreter with kind of constant performance and a compiler where you put them upfront investment in and then you get it back。

 well imagine now you we're expanding the a so instead of you small integers now we're talking hundreds of executions。

And what we're going to introduce now is a second level of compilation， so this is the interpreter。

This is the jet， which on this scale， you know there's a tiny little blip here due to jet compilation。

 but otherwise it just looks like a straight line。Now what we're going to do is wait until that's run for a while before kicking in the second compiler and the goal is for the second compiler to amortise its effort by meeting。

Somewhere down the line。Theji compiler and delivering better performance and this can be repeated many times right you want each of these things to have a shallow or in shallow or slow。

But you don't want to do it if you're never ever going to go out this far。

 it's only going to execute in this example a0 times。

 you don't want to execute the want to pay the price as compilation。

You want to wait until you're reasonably confident that it's going to run a lot and then kick in the compilation and if that turns to run out a lot。

 then you might want to kick in another compilation and another and dial up the optimizations if you have them implemented。

In south， there were almost no additional optimization levels。

 the only additional optimization level was to inline even more aggressively。More or less。

Slight simplification there， but in Hopot or some of these other VMs。

 then you can dial the optimizations because there are things that you can like Cliff talked about last week。

 graph coloring register allegation for a Se scan。When you're out at the far end of the far reaches of this and you really want to squeeze out the last code piece of performance。

 then you want to dial in the graph color rank calicator so you' going to take a long time to do its job to you end up with very tight code as a result。

So to do this well， we need to know where we're going to exp the a。

 so what we're going to compile and then nu of stuff。Dynaically。

 that gives us optimization opportunities that we didn't have statically because if we had them statically。

 we should have done them statically。The whole point of doing this dynamically is that you gather extra information that allows you to do a good job。

So what I'm going to describe is more or less 20 years old from south。

With a couple of little variants that I'll describe as we go on。And it's been deployed successfully。

 you know， Hosp is now 2。你有全体算。嗯。So it all relies on prediction。And this rather shaky assumption。

Shaky in theory， robust in practice。That the past is a good predict of the future。

It turns out that that's the way people just happen to write programs and they don't have stuttering phase changes just at the point where you think things have stabilized that things actually tend to settle down。

But it is an assumption right， and you can't easily write programs that violate this assumption and have terrible performance。

So what can we use for predictions well there's a few things it turns out that it's very simple based on what we've got so far。

 one is you want kind of a heat map of your code， you want to know where the things are being executed so that you know where to apply the optimization so if you know something that been executed n times for some value of n。

You're going to assume it's going to be executed a lot more than any and you can even use a series of thresholds to increase your confidence level so you can set different levels at which you say。

 okay， it's been executed a thousand times I'm willing to invest， this level of compilation。

 it's been executed a million times I'm willing to go that extra step further。嗯。

Last week we looked at polymorphic inline cachehes well the great thing about polymorphic inline caches is that they give you type information as to what was actually involved as long as it's not megamorphic。

You get a nice accurate picture of the observed types at each particular call size。

 that's really helpful。We can make some under assumptions about program structure based again on what we think programmers are going to do。

 a fairly safe one is to say。You know， loopops are more worthy of optimization than the code around them。

I don't think is a particularly bad thing the others。

I'mNot so sure are such good ideas in retrospect and that maybe you should just use the measuring tools available I'll describe instead of making assumptions。

 so one is you can assume exceptions are going to be exceptional。

 but sadly there are programmers who write exceptions and assume they're going to be cheap。

And they're just going to be penalized if you make this assumption right。

 it's just going to be sucky for that。So if you think exceptions should be fast。

 then you can do other things， you can do measurements on how often they happen to figure out whether you want to。

嗯。Deal with them especially in and similarly primitive types。

 you can make assumptions about the frequency of those things。

 but every once in a while it'll be wrong， so it's better to measure， I would。

How do you measure what you encounter us？So we're going to place counters in the compiled code。

 so as we emitm code。We're going to have。Site specific counters， so of a variable。

 a little piece of code that as it passes through that arc in the control flow。

 it just loads the counter increments and stores it back again and maybe does a test to see whether you've reached the threshold。

 but the important part is the incrementation。You put one of these at the entry of a method so you can count how often the methods have been executed。

 you put them at the loop back edges or loop dominators to give you some picture of the he of the internal loop structure of a method each of the counts is site specific and they're just incremented by the generated code now the testing to see whether you've reached the threshold you can do two ways you can either put the code in line to do the testing but then you're paying for it every time you go through the code。

Orhy you can just have a separate thread that over looks at the counters。

You know because they're in memory， you not interrupting the running program and you know。

 the thresholds are not super precise， you know，1 thousand1 thousand and 10001。1100， you know。

 it's not going to make that much a difference。To test sit completely synchronously。

 So you could do it either way。And the thresholds because they don't even need to be precise。

 you can cheat， you know， they have to be sort of statistically approximately right。

 but not super precise。 you might even。In a multither system。

 not even bother locking when you using increments， right。

 you might lose some increments due to racist， but。Something that's hot， it's going to increment。

If it's raising， then it's going to incr fast。So that's counters now another technique。

Which is used is to convert them from being。Count from measuring absolute values into rate measuring devices。

 because what you really probably want to do is execute code。Even。

Optimized code that's executed frequently。You could imagine having a piece of code that's executed。

Infrequently， a few times a second。But very regularly。 And， you know。

 that might not be worth optimizing because the payback on the compilation might be errors in the future。

On that。 so what you really want to know is stuff that's executing a lot right now more recently。

 and so one technique that's been applied。Is to have a background thread which goes round the counters so it knows where they all live。

 and it just regularly divides them by a constant。So if you think of the simple case of division by two。

 it's like having a half life right， the current value of the count is whatever it counted since the last division plus half what counted in previous division plus half of what counted in the division before that etc cea。

 etc cetera， so sort of recency has extra weight in the counts。

And that turns them into this sort of exponentially decaying red measuring device。

 which turns out to work out pretty well。嗯。This isThe only description I could find of this is in or PhD think this。

It was in Southway but it never seemed to make it into any of the papers as far as。Now。

 if we take the counter idea。And the inline cache and polymorphthic inline cache idea。

 combining those two together， we can then use the combination to build a histogram of。

Invocations by type any call sign， so we count on each of the outgoing arcs from the inline cache。

 how often that transition was made。And that gives us a type histogram。

 so just to give you a pictorial。Few we looked at this last week where I had appointed point to the look at routine。

 you know， in the in cash and I patched it to the the different methods as it was executed。

 what we're going to do instead this time is when we first，Bind instead of binding directly to the。

The call E， we're going to insert a little stub with its own counter。In between。

 so our inline cash is going to go to the st and the stub is then going to vector through。To the。

 to the thing。 And every time we go through the the stub increments， it's chm。 So this is a nice。

 easy way of having a chtor without。You know if weSo what would be the problem with putting in Cam here？

你话。It's not size。Yeah， exactly this would count all ins from all places whereas we want to count the implicationss from this specific site。

 now we could you know generate a whole bunch of code with null out stubs here。

 but you know that's going to be some very space and fiction so instead this technique of just generating these little stubs on the fly it seems to work fine so we keep back executinging that and it count and but eventually it misses and we generate a pick。

And now the pick linked to the counter instead of the method and the new counter for its second case with its own count。

 and then we start running through there and that's going to build up the profile of those two types until we miss again and then we generate a third one and a third stuff。

I Mr。So a fairly straightforward technique。It's a little bit of dynamic co generation for these stops and you need to have your code cash be able to manage these guys as well as these guys。

part of the generous code。fairlyly straightforward yes。

 do you rely on the endr to go involved in direction？Well， so yeah， we'll see what we do with this。

So this is， this is the way we're going to instrument when we're in the early phases of that sort of climb up the hill。

 so either while we're running interpreter， if we have an interpreter。

 we can instrument together this stuff。Or we can have a simple compiler that generates。

It's this stuff just for the point gathering it so the when they're optimizing the pilot kicks in it and then look at all this data。

Okay， so eventually， you know， imagine these things sprinkled through the system as the code is running all the count increasing you have counts in the method headers you have counts in the loop bodies eventually some count is going to trip and it's going to trigger a recompilation so something's going to overflow or reach a threshold。

And now you have to decide what you're going to do。

 what you're going to recompile and it turns out that this is far more critical than the counting part。

 it's easy to get the counting right and if the numbers are off by a bit it doesn't seem to have much。

Of adverse effect， but deciding what to compile。And how to compile is really important。 So， you know。

 one bad choice would be， okay， we tripped in this method。

 we're just going to recompile in the method that we trapped。

And that's bad because we're not looking at any of the surrounding context。

 we're not using the information of how we got there to figure out what we should be doing。

So in particular， what we want to do is make our you know it takes time to pull up a compiler and get all of its data structures ready and in mixed up。

 especially if we're going to do optimization， so we want to invest that wisely on and as big a piece of code as makes sense。

Just the Goldilocks effect right you want just the right size， no not too big not too small。

 but too big is actually better than too small because too big can always be broken up into separate subcompilations。

 but too small you're just not willing to have any optimization opportunities。

So what we can do now is we can look at the invocation encounters in the inline caches as we walk down the stack。

To see what the profile looks like down from that loop， so we start with the current frame。

We can walk up to see where it was called from。That gives cells the return address and the return address will be right after the pick that was invoked in the pick we'll see the frequency of what that picked did。

we can go from that guy to his collar and look at the frequency of that edge， so in effect。

 when you've got the stack you see the frequencies of the collar edges in that stack。

And what you want to do is walk along those until you see a serious discontinuity and there's two kinds of discontinuities。

 one where it goes up and one where it goes down。Where it goes down is probably the outermost edge of a loop。

Right so。If we look at that code that we were doing before。You know。

 if I hit control CA happened to hit here， and suppose this was the one that triggered the compilation is actually the first block inside the loop。

 so this it will be the one that triggers the compilation。You know， on the sail。

 we had a thousand0 diseration counter that was tripping。

 if we looked at this we'd find this guard was called from there a thousand times。

 this guard was called from there。A thousand times， but after that it's only once。

 so we can tell from this that the loop is here， this is where the hot area is。

So we want to use that to walk up the stack until the frequency gets so low that it doesn't seem like it's worth compiling。

But we've gathered enough information that we can now consider all of that for compilation。

 So at the top at each discontinuity， we've got a method which we'll use as the room of our underlyinging tree。

 That's the thing that will be the thing that gets in。Below that there might just be one。

 but there could be multiple ones below that。And what we want to do in something like self。

 what youd want to do is not stop here necessarily。

But you want to look also at the home context of these closures because you want to inline all the way up through there because that has a big benefit so even though this stuff is only executed once。

 we can inline all the way up to where this block has its home， which is here。

And to win it where the sunbleock has its home， which is here。

 then we'll get a big benefit because we can eliminate all closures and faster。

So that's what we're going to do when we'm going to chop up the stack。

Into multiple compilation units。One at least but possibly many。😡，And then from there。

We're going to look at every single inline cash coming out of the root method。

To look at the frequencies of the implicationss of that root method， so all the things it calls。

 how often they're called and which types， so that will give us a way of deciding how to do with the first level in lighting。

 everything that we find that's invoked a lot。On a specific type， we can do inlining。

So every can col is evaluated and if it looks good。Oaks can use it often enough and the size。

 you know， usually what you do is you pile until you reach some limit。

Or you look at the costs of the inlining， you know。

 if you're mininging something that's massive that might not be a good idea。

 but it might still be the heuristics here are very， very hard。But you want to walk down the stack。

You know， gathering this inlining tri and in line， pulling in all of the things that that are worth inline this is a。

Thiss a real black eye to getting this right if you look at the code of the inlining heuristics in any of these VMs。

 they're impenetrable they just look like a complete a hoc collection of decisions。

Because what's happened is over the years， you know。

 each little variant has been tweaked for some case or a benchmark or whatever。

 And it's really difficult to。either give sort of a principled underpinning for how these things are structured or to understand how it works One of the things we recently did in Oracle was I had an intern look at replacing that heuristic with a decision to regene by machine learning。

 which was kind of an interesting technique it held a lot of promise actually there's a reference to the paper in the bibliography。

 but there's the scope here for making this more。They are easier to develop the more robust。

Okay so for each inline method we're going to evaluate its call in turn until we you know we max out something we decide either it's not worth inlying any further on we've got such a big thing that we're going to compile that maybe we can't register application on it or whatever again it's a bit of a black up because you really can only evaluate the decision after you've done the inlining but almost waste time inline things that you' then decide you're not going to inline so trying to decide and to predict to evaluate something as a candidate without actually doing the work and paying the price is really difficult。

Okay， so finally， for each of these compilation units。

 we have a tree of methods that we're going to is our inlining tree。And then。

Once all of those are connected in the IIR， we can then run all the classical optimizations on them so comments of expression elimination。

 all that usual stuff and we can use the type and invocation counts on the internal edges to make decisions as to what where we're going to allocate the resources you know if we're going to preferential allocate registers down one particular path versus another or we're going to place some things so that it falls through so the slower things are out of line and the fastening of the fall through and we can use all of that data to drive those decisions we don't have to be using guesses all the time as in aesthetic static completion environment。

And then the last thing we're going to do。Is inject these things called safe planes。

which need to be there either to facilitate the garbage collection。

 which we talked about a couple of weeks ago， you know the ability to be able to find all the pointers at selected places in the code。

 or of debugging and deoptimisation， which I' like to explain in。shorthor while， I don't know。

A couple of。Optimizations that are useful in this context。

So one goes under the fancy name of class hierarchy analysis typically used for static type of languages like a Java and the idea here is a very simple idea。

 it's kind of amazing you can drag this out into a paper。

 but the idea is you know we have a hierarchy， suppose we have a method here。

 a P that calls another method M on this we look here。

 well there is only M there is no override so we know that this call must be calling that method。

You can do this， you can add type Greek or M this and make it into a fancier thing。

 but the gist is at any point can there be only one candidate that it's calling if it's that candidate then it's got to be that right in statically type language you don't get type errors so can't be a type error and dynamically type language it can be a type error so you can't do this。

But in a statically type language which we can eliminate a whole bunch of virtual calls and devitualize them into simple calls based on this observation now there's a catch here。

 which is if you're in something like Java as the program's executing I might load a class down here which suddenly has a definition of am and now。

Now that optimization was no longer valid。And we to do， we have to make some changes。

 but that will be the point of the deoptimization of we cover。In a few slides。

The other thing that's really useful to do when you have a big enough code region is escape analysis and the idea of escape analysis is we're going to take the region of code that's under consideration。

Look for the allocations of objects in there。And try to see if the object does not escape。

The that code region and if we can determine that the object you know never has any references leak out of that code region。

 then we don't need to do a full allocationation we don't need to put it in the we can just put it on the stack or we can call an explicit free thing if we want to get rid of it or in fact we we can go even further than that So so the current state of the art is to do what's called partial escape analysis and that basically analyze all the paths and says damn these paths it does not escape。

Dam these it does， so down those paths we're going to put the code that makes objects and converts the things to the real objects。

 but down the other paths which we know from the statistics are frequent then we're not even going to allocate the objects。

So here's an example。Here's a piece of Java。So in this code， we make a key。

And we compare it to some static。And if it's true， we return some other static value that we've got。

 otherwise we go on call some more general code and we can see from this that if we go down this path。

 this key does not escape right， it's made， it's tested and then it's discarded。

So the escape analysis optimization can rewrite this code into something like this。

 so this it starts first by inlining so take those things that were called before so assume for example that this is a synchronized method。

That's doing the comparison。We're going to inline it with the synchronization。我ね。

We're going to inline。the construction。So we have explicit allocation and construction going on here。

Now the escape analysis can look down this and say， okay， I make this thing here。

 down this path I'm going to dispose of it。I know I've never given a pointer to it to anybody else。

 so no one could possibly be accessing it so I can remove the synchronization because I'm the only one who has it。

And now down this path。The other path I have to generate。For the allocation。

 so this is what that gets transformed into。So we grabbed the。The reference from the static。

 we did the comparisons on which return without ever making the object， it's just not there。

This idea of taking the。嗯。Object and deconstructing it into its component fields and just using those as if there were scalrs。

 it's called scalar replacement。So we've done three things here， we've removed the allocation。

 we've done scal or replacement， and we've alllighted the lock。All of those are benefits of。

Escape analysis。This example is taken from a recent paper。On partially scale analysis。So we。

 as I said， heat allocations， the stack allocations， although knowing practice。

 nobody ever seems to do this much， usually you just go to if you can all the ways to scale a replacement。

嗯。Either way， you're reducing load on the garbage collector。

 there's one less than from the garbage collect have to re claim and you get to lie locks as well。

Okay， so I think。Take a break there。Patrick will talk a little bit about the GC exercise and then we'll look at de optimizationim after the break of rain。

Or scalar replacement， do you have to do part lighting as well because before you pass？Yeah。

 so it sort of relies on you seeing all the component fields and have them manipulated down the。

No escaping path。So if you ever have to pass a reference to the object， well。

 then that's an escape and you can。You then you have to really make the object impossible。

What you want to do is in。All of the stuff and the nomakating pack。

So that sort of all of the field accesses are extraordinary。系。For10 minutes。We just。かこです。原来是。あ。

So hopefully the jet is going， all right。I'll talk about大 little bit。

So this is going over the garbage collection。Are there optimizations assignments？

So the garbage collector， you implemented a compacting， precise garbage collector。那的当然是没有的。

You get decent performance out of it。So when you profile this2。On average， you guys are getting。

Like 2。4%。Spent a garbage collection。Comp配 to。Pros pretty。So I went through the code for the GC。

As far as I can tell， so Mario went over this trick for Se where。In your heap。

 you have these dedicated words。To tell you what type。And I。

So you just get a random pointer to within the he。You don't know whether it's one of the specials or whether it's an actual。

I point it to something else。So if you tag these tag wordss。

Then you can start at any arbitrary place in the heapve。And sc forward from there。

Does that make sense？If you use this trick， the generational GC is actually not that bad。

It's actually pretty straightforward。て言れだ。We receive that again。Okay， so。

The problem right now with your heat layout is that。

Imagine I want to scan all pointers between address here and here。Okay。

So you jump to that place in your heap。And now you have to decide。Is this a pointer or not。

 because it could be a pointer， but could also be one of these special tag words。

And some other systems， they Google a map so that you can backtrack to the tab word and then you can start jumping in the appropriate sizes。

So， that's tricky。So instead， you could just mark。Is tagler。With some special bits at the end。

So then you can jump to a random pointer and you can say， is this a tag word or not。

 well just check the bit。So you can scan any address range of it。that's a very， very nice turn。

Why is this particularly required for the generator？You find that。If you try。

 being able to scan random parts of the heap， is's something you have to do。

Because you have to process the remembrance set。And the remembered set marks if you use card marking it's just a card is marked。

 which is an arbitrary you know like 512 byte chunk and leap without respect to object manner。

 so when you start one of those things like you're in the middle of an object probably so you need to find。

The boundary is near so that you can walk up through。

Do you have a question how did you that you should like keep the tag？

Because it's possible like jumping in a deeper the middle of punch。And这。And how can decide。

It is a middle pointer。Sorry， not the middle of a pointer。

 you have a pointer to the middle of the heatap。OkayYeah， but the middle he could be like part of。

It could be part of an object， yes， it could be in the middle of an object。

Right so you just need to know， are you in the middle of an object or are you at a tag？

So make sure you mark the tagboard special。Make sense。

So it's basically just a tag that's special that you can decide it's the tag of the beginning of an object。

In itself， it's called a mark word。Because that's where the GC would write。

 it's not bent as well in the same， but then what if there's an in in the object field。

 that's the same as those。Which is soph design， there are no raw ends。明该。

But for the rewriting like for thes say you're still jumping to an arbitrary point but it's not a it's war aligned Yes。

 yeah you're always worn word that's yeah that's important don't do arbitrary bybeers like this。哎。

Okay。And got you guys to measure some of the memory allocation statistics。TheThere still the two。

On average average， you guys are getting about 95% into our locations。

Why it differs between different implementation I'm not quite sure because deterministic program。So。

If you think about。How bad this is this is really shameful right， so he requires 32 in integers。

What are we actually using for a 32 bit integer we're using a 64 bit pointer because we're on a 64 bit system。

 64 bit pointer goes to 128 bit strap。V 64 bit is a tagr。The second 64 iss the value。

So here's six x over when you should be using， I can answer your question as to why it might be different。

 some people would allocate a nu logic every time some people might allocate。

 I have only one null object。Yeah， okay。 that's probably。Iが。ok啊。So like I said， average。

 you guys are getting 2。4% overhead on Sokeka2， so who thinks garbage collection is still slow？

It's a garbage collection。You have。嗯。The collection time is proportional to the number of live objects in the heap。

Plus， you get。So you get do above allocation。So。Compared to。Nive C++ implementation。

 we call new and delete all the time。The garbage collector will beat that heads down。为什么？

There's a few specific circumstances。Where you can play clever trips with a memory and you can beat a gar。

So if you know this entire region is going to be。Done with， you're never going to use it again。

Then you can delo， you can just throw it away。Wheres garbage collection can？

But if you don't say any fancy tricks， if you just rely on new and delete or free analoglo。

I don't think you'll ever be a go。ははい。Okay。Okay， so there there's a fun question on the about touch iron it gave you a code snippet and I asked you to see what's wrong with it。

 how many people actually read this question before you？Inmplemented the garbage collected。No okay。

 I but I still made up。Good for you。Mi Toug and I had a very personal relationship。

really happy until nice。Yeah， so everyone pretty much got it。Apart from the offensive staff。

This is some value， you call H。this age island is not safe。

 it could spawn another garbage collection， which means that whatever thing you pop is now garbage。

So what you have to do is you have to get the link first。嗯。Call H on the link， which may。

Relocate all the pointers and then afterwards then pop the two items。Because after that。So。

When I was designing Fi， I knew this was going to be a problem because I run into it all the time。

 so this is Fi the only place where this happened。But in a real system。

 stuff like this is everywhere。That's a real family。

There's another thing you note it's not just about popping this from the stack。

Worrying about the fact that the garbage collector might collect it。

 even if you were to just get a reference to the length or diminish value gap。

 that reference will get over。啊。Because of the coffee like this that， it's not just a pot， repeat。

 it doesn't general better it can。So very， very subtle about。Yeah， can you keep another like least。

S but there was pub。 Yeah， and then you also， when you do a garbage card， you also scan that。

And then whenever we finish this operation， you couldnt this。 Yeah， so often。

 often when you put in real system， you have like a separate list called your additional route。 Yeah。

 and then there will be an API called。Add root， meet root。Okay， and then I use with this。

But then if you forget to add root。There's a possibility。Yeah， and if you forget to believe it。

Then no crash happens。 You just slowly run out of。はそごん。但是现在。Yes。So in C plus plus VM。

A trick that I've seen use is to define a new C++ type。Which。

The constructor takes the pointer that you want to register。

It links that cell into a linked list for the garbage collectedor to find them and then use the automatic destructor that C++ will invoke at the end of a method to clean that thing up when you lose the stack and delink it from the list so you can't forget to remove it from the list。

さ。I'm sure you the code。A couple of minutes to name that that's pretty nice。

What if what if you can scan the implementation languages footprint print stack and see what's on that and then that's actually on that stack then you can work circle Yeah。

 so if if you can scan the implementation， the host languages stack。Then this becomes much easier。

Assuming it will give you to type it for。And then it's true。In general。

 have you have no idea how they lay it out。It's possible in general。However。

 there are a few systems that do it conservatively。So， you scan the。

You scan the host language stack and if you see anything， any number that points into your heap。

 you assume okay， this is probably a pointer。And do that。

But Mario can tell you it falls of conservative we'll go into。Conservative。

I'll stick a nice through the heart that next week or the week after。Okay。嗯。next question was。

 you guys implemented in the bikeout interpreter？How hard is it to do it in the AS here？

The answer that most of you got is that it's super hard。

 it's much easier to do in the bycode interpret。And this is light。 So this is the A interpret code。

And a lot of you have code that looks kind of like this， so this is for the set expression。

So the first thing we need to do to。To evaluate the set expression as we need evaluate。

The thing we want to assign， right？So。This is actually not the greatest example。Okay， let' let's say。

 let's say set takes two arguments。じですが。So they have to evaluate expression one and they have to evaluate expression two。

 right？Now， when you evaluate expression2。It could run on GC。And your reference to expression one。

That is where the Aln is living。So in the bike interpreter。

 this expression one value is cached in your operating staff。

And the AS the interprettrover of this expression one is cached in your CS。

Which means if you want to discover all you really you to scan to sees that and we just ran into the same problem。

Okay， so that's why it's much much harder using it AS。Okay。

 then I went through a few just performance characteristics。

This one is you allocate one gigantic array at the beginning of the program。

 you do a bunch of operations on it。And the program ends。

So they array raised live for the direction of growth。So if you run this program。

 what happened is you might have a bunch of very。Short lived objects that trigger garbage collection all the time。

Well what happened is this humongous array will be copied back and forth。So its a clearly。

K of a waste of time。So often systems。Actually deal with allocating large objects and small objects different。

And they set different thresholds for large small hubs。Alternatively， you use a generational GC。

Then the array will probably be put into the bolt collection fairly quickly。

 and then you won't touch it anymore。So the prime example before with the generational duties。嗯。

If you allocate a big array with just integers in pho， maybe you're doing like。

Number of crunching code。Then。First off， it's not a simple array， it's an array of pointers。

So you have no locality that way。Second of all， every time your garbage collector runs。

You have to use scan through this array。What you wouldn't need to do if you actually had a prim over re。

So。My hypothesis is that this is。This is probably why Java has primitive types。

I do with the raise though， nicely， I want to assume a lot more about the implementation skills of the language designers that I'm willing to give them credit。

😀ふふ。😊，ちだ。It would be a good reason。いベ。ふ。😊，Okay， so the first few people got not that many people got this one。

So， this one is。You run your program and your program manipulates many long list linkus。

So for example， let's say I write a loop and I just allocate。Many， many， many。Lnkless concepts。

Then because we're using phone allocation。All of these conss are one after the other。

 they're all contiguous， so before garbage collection， the list is still very nice。However。

 your garbage collector basically does the breath for traveral。It's using the free space as a queue。

 essentially。So if you have many， many link lists， what's going to happen after you're running a garbage collector well it's going to take one element from the first list。

Followed by an element from the second one， followed by element from the third years。

And after sponsor all of them， let's go back with another element。れ anotherアない。

So all your lists are precisely interleaveed。So it's about the absolute words that can happen。

It's worse than that。Yeah absolutely。Yes。So there are that first G algorithms to deal with this。

 but I don't know if hots bug uses any。It's not common because of the stack issues。

So did you go depth first then。Build a stack and unless you're going to do pointer reversal thing。

 which you can't do concurrently。Yeah， than I don't think they were going。

If you go to generational and GC， I think it's also not that big of an issue anymore。Ohello。

Because the mark sweep， well， old stuff will only get with walls。

And then it just gets compacted after here she。Anyway anyway。

 so this is what I think I was about here。あ。that so。How do you solve this？嗯。I mean。

 if it's not integrated， it's。Lis of objects。So your collector I known does a breast first trim yourself？

So you could write a collect and do a depth for traversely。In general， when will read Java code。

 You don't have a restriction of whether you can do link advantages。That's a garbage。Repeat that。

 for example， how does like Java do the garbage。Make place。Java just does the same that you guys do。

そだ。😊，So which means if you have an increase in Java。It's unlikely to be contiguous。

So we have a link with some Java， you basically assume。You have no locality。新人趣覚たんです。

There are some GC techniques that try to reorganise during compactions。

And then we'll try to move things that are referenced。Close to each other。So not bread first。

 but some other scheme because D first also isn't ideal。

 depth first has its own problems with things like hasht。Something like a hashover。

 you want to go breakfast first at the level with the keys， but then depth first beyond the keys。

 so there are tickets。嗯。啊。So before this complexity， I told you， your scavenging garbage collector。

 takes time proportional to the number of lilacs。Okay。So。If your program allocates， likes the do。

If it allocates gigabytes upon gigabytes of data， it no2 allocates， I think 16 gigabytes a total。

When benchmark。Because they're all very short lived， when the time the garbage collector runs。

 there's very few live objects。So the collections nearly。So that's very important。

This is not true for all garbage collection techniques。So， reference counting。

Every time you create something。You every time you store to something increment as reference cap every time you。

Delete something in decckerments reference。So reference County is general proportional to a number of allocations in the site。

There are a lot of allocations at the times。And naive Mark sweet。

The sweeping phase normally crawls through your heap space。

So naive actually the general proportion to the size of it。Not of course since the size of the life。

Okay， and then when you're designing an FFI for PhA。If you pass out a pointer to a feeding object。

If F runs a garbage collector， then this pointer。Is meaningless。So。

There are two problems that you have to be aware of， first of all。

One is the one I just top about when the garbage plug and afinia runs。

How do you signal that this pointer has changed to C？The second problem is。

When the garbage collector runs， how do I know that C still requires this object？

So don't market It debt。So C has to somehow tell it， is this a root or not？

And this is the decision we just。嗯。有嘅得傻先傻笑。Okay。And then the next assignment was we did the tire from this optimization。

So there's way less memory allocated in total。Probably。

No one should require a garbage collection call anymore for I want megate people。

So I hope everyone's still stressed tested。さでね。嗯。One great thing about this optimization is that it alleviates the strain garbageage collector。

 but also if you look at how the arithmetic operators are implemented。And also much cheaper。

 whereas before required several memory loadbes of memory stores。

Now most of the print operations can perform directly on the TA representations。So。

That's going to be a big savings right now your call slot operation is still dominated by a lookup。

But when we move past that after we do inlighting。And this will be very beneficial。

Inmplementing multiply。There were two different ways you can do it。The better way is the first way。

If you do it this way。So F is basically a shift operator， shift left by three minutes。

So if you do it this way， then both of them。嘅 modified。And then you shift the back down。

So if you overflow by these three bits。As you need。And the shift back downs。Okay there's this one。

 you shift it down first， which doesn't lose any information。

 and then you do the multiply so you get an next to three visit。嗯。

This one's just a bit hackcking trick for doing the compression operations。

So feeding requires when to do a compress operation， if it's true， it has to return zero。

 if it's false， it has to return no。Okay。And we use two to represent nu。And zero represents。

So I gave you this this instruction， G， and you give it a creditdicate。And this models。

 like on the XA6 processor， there is a expression called set E or set LE。

And it will give you either one if the comparison is true or zero。パス。Okay。

 and a lot of processors have these instructions。And what we don't want to do is you don't want to line a bread。

Do the comparison， if it's true， then move zero to some register。And if it's false they move。No。

 it's very to say。avoid Russianions， right。So。Here's a long way that I came up with。So。

You call the comparison operation。This gives you。0。If it's false， and one if it's true。

We mean need to somehow flip that the things out away。Sa xO with one。

And then you need to just shift it into the second。So that's the way that I came up with。

And then I notice that some of you。Came up with a even better solution。Which is。If you know that。

If you know this operator a compile time， less that。You can actually just compile that into。

A greater than equal， too。What's by by two。So I thought I was extremely clever。つけはょか。Okay。

 so those areでます。嗯。For the chat people。Have some questions。 What if they want to emphasize is that。

For now。You're not really writing at just end time。Right。And ahead of time。

As then you're going to take in the program。I'm going to generate every instruction for every。好了吧。

When you start the program。And then you execute。After you get this working， then later。

You can delay generating instructionss until after the function is called。

Or even after the function is called a few times。And that's just bookkeeping。And I think。

 there's nothing too difficult about it， but it's。Something I do later。

Is there anything particularly tricky that people are running into for the jet？O。Aper and tagg prim。

 how do BMs like passport use taggged integer， especially if they're like for example tagged lungs。

 if there's 64 bits， then you can JavaScripttically there's no tagging at all。

If you look in VA a VA8 tags because JavaScript is untyped， sell as sagging。

That's right because but then for example the semantic said just could be 61 bits wrong using 4 I'm not in self small integers are 30 bits to 32 bit system。

 so 30 bits is a small integer range they I think use 64 bit arithmetic or low it tags 32 bit ins。

 yeah， so JavaScript numbers are floating point， basically。

 but it tags the cases that are integers and uses integer tagged operations on those to make things fast。

So it does have to do floating point all the time。あ。61 bit integers are kind of weird。So。

Most of the systems I know that use tagging。arbitraryrbitary position。YeahSo up for some point。

 it just throw into an into box。Which is okay， so for correctness it's nice。For performance。

 debuggings kind of。no you' right because the program number crashes。

 it just runs slower on the other hand， you know there are no wolfflow。Freush。

There's a common mistake in。あ64。So， you can have 62 weeks。Does't have to be 61。It depends on your。

You're using last two bits， that's fine I think in the assignment I just said three bits a。

 so you have6 minutes。Three is common on the 64 bit system of the pointers eight by。

you got the throwing bits at the line over point。So。Com。Talked about all of these things。

You might want to do。In a tiered compilation system， some of which like。

Inlining based on class hierarchy analysis， you might have to undo。

If program changes or if your assumption becomes invalid and so。

Dynamic de optimization is kind of a cat all technique to deal with that。 Its this fairly big。

Power tool that lets you when implementing speculative compilation。

Assumptions and then sort of record when you've done those and back out the event that you got it wrong。

So。So Java class loading is a good example of that。

 if you optimize based on the current state of a hierarchy， you can make assumptions that。

We're becoming validated when a new classs learn。And in general。

 you want to make spectacular assumptions because without some amount of gasing。

You end up with very suboptimal code。So we need this way of。

Recovering the state of a computation so suppose we have。A method。

 something like this around Methadm。The cold food。After setting a couple of local variables and then food called bar and bass。

 passing on at those variables and BaS is just going to do some simple addition。

Let's assume this middle call to bar is some big， horrible thing that we don't want anyone。

So when we compile this。It's perfectly reasonable for the equivalent machine code for M。

 which I'm going to call M prime。To be a call to bar and a return set because we see the three and the four we can do the propagation and the inlining of the constant folding and all of that stuff。

And finally， we have the seven， you know， and the inlining tree together would look something like this。

 so we've got ba line into full in line into end。So that's all well and good。When dont we run that。

On the stack， we're going to get a frame for M prime。Which says， okay， we're going to call to Bob。

 so we run this， we call Bob。A call something else。

And let's suppose there was something else we in either a language with class loading or worse still a language with reflective programming operations like Smta herself。

And that rewrites this method to do a multiply now。Which is fine。

 right you can do that when you're debugging and you can do that into that debugging in both languages and would support these kinds of techniques。

 but in some languages like Salforce Mo talk， you know， it's supposed to look like an interpreter。

 So while we're out in here， we can call Eval or some other operation that redefines methods。

 And now we're in the middle of this frame。 We're about to return 7。ok。

But seven isn't the right answer anymore， how do we get out of that？

And that's whatam dynamic de optimizationim is it gets， this situation gets us out of this。

And it's just a systematic way of doing that。So what it's going to do is it's going to take this frame。

For the two， for the optimized method， and it's going to rewrite those strands to look as if。

We were executing in the de optimizeimized， interpreted of simple g compiled version of this and replace them such that when we come out with this。

 instead of being in this method at this point， about to return 7， we're actually in。This method。

 at this point。I can come out with the call to bar and we're going to call Ba and we're going to do the multiplyier and get the right。

And so to do that， we need to recover the frame and we also need to recover the variables remember we had two variables here。

 we just go optimized the way because。They would never need it。Okay， so how do we do that？

So what we're going to do is we're going to insert something that looks like save points in the code the points at which we need to make these transactions and save points have some relation to the GC save points。

But kind of a generalization of that technique。GC save points us so that we can just find the pointers that we need to live information。

 the roots that are on the deck In this case， we need more than that。

 we need not just to know whether something is a pointer or not a pointer and if it's a pointer the value。

 we need to know all the values， so it's not just pointer information it' scalealar information too。

And we need to know which。Values those things represent in the execution so the common technique is to have a canonical representation of execution so if you have an interpreter。

 the interpreter is the canonical representation that's the thing that's kind of ground truth that says you know what you would do that's the reference implementation if you like or if you have a simple non-inlining nonopimizing compiler you can use that too because there's a simple one to one correspondence between the locations of things on the stack and the values in the original source program。

whichever it is， I'll assume interpreters for the most part。

 we're going to take the program and we're going to remap it as if we were always executing。

In the interpreter， and that's called a deopimization。

 we're going to take the optimized frame there and we're going to map it back into an unoptimized。

And we need to figure out where we're going to do that and what we're going to do。

So each point where we do that， a DOs point is a value of the native PC。

 this is a program case that corresponds to some source program location。

So those program locations usually indicated by a virtual PC or a bikecode index into a bikecodeing method and what we're going to do is we're going to。

 for those two points， we're going to connect them with a data structure and enough information that we can take them running optimized form and convert it into the unoptimized form at that point as if we were in there all the time。

So we need to keep track of the stack of inlining points at every deoptimisation points or any particular point because of all of the optimizations we did before。

 that point could represent a method in line into another method in lined etc and so we need to keep track of that and within any method that induces a tree because of each inlining point you could have multiple inlinings take place within the top level method there are multiple inlinings so there's multiple points across the method and down each inlining points so we get a tree of these things which if you read the de debunking dynamic。

Through dynamic of the optimization paper they're call scope descriptions in that paper。

 more recent stuff calls them frame stance， but it's basically a description of what the interpreter stack frame would look like at that point。

And so it has all the variables and for each of those variables。

 it has another data structure that says where to find it in the opt sta， is it in a register。

 if it's on which register， if it's on the stack， what's the offset from the frame pointer that you have to look at to find that value That's all you need。

Now， some of the values have got optimized out completely。

And they're just constants that just got folded for those who are just going to keep the constant value as if it were there。

 but in the descriptor， it's not on the stack， it's just in the descriptor as a little。

And if we're going to do debugging。Or we're going to allow reflection on the frame。

Which allows us to look at all of the variables。And we probably want to keep values that the programmer thinks are there that are otherwise dead just so that we don't confuse the programmer。

 so when you open a debugger on a method， you know if the method has the use of a variable。

 but the variable doesn't get used beyond the halfway point。

 the compiler is probably just going to remove it at that point。

 it's not going to keep the value red。But for debugging。

 we want to keep that value around to give the illusion that it was there all the time for the debugging or to do the transition into an optimized code。

But if you don't need embugging or reflective access to dead values， when they're dead， right。

 they were dead before， they're still dead。So you can remove that if you want。

So where do we put these things Well obviously we're going to have to put them to any point that we explicitly know that we're going to recompile so for example if you have an uncommon branch or an uncommon trap there's basically an entry into the runtime system that says I give up here from the point of view of this version of the compile code take it from here and do what you need to do and at that point you need to recover all of the states the runtime system can pick that up。

 recompile or reinterpret a whatever would going do so that's easy。

You also need them at any place that can invalidate and optimizations。

 very language specific as to where these go， an example in Java is you have parts in Java code where you reference a variable of some type that you haven't loaded yet the class hasn't yet been resolved and the resolution can cause classes to be loadeding and loading of the classes can invalidate optimizations。

 so a point where you have class resolution that hasn't yet taken place that's going to have to be a deoptim point because you don't know what that's going to upload load it might invalidate your optimizations but languages have a places where that has to happen。

Just like the GC save points， you have to have them at call sides too because you have to be able to deoptimize something that's on the stack。

when it's not at the top of the stack， everything， you know。

 except the top of the stack is going to be a cold sign。And implicitly。

 you get them for free of method entry because the point where you enter a method。

All of the variables are in known locations by the calling convention， you don't need an extra map。

 it's there sort of by calling convention as the ways of find them。

So those are all the places you need and then an additional one that most systems employ is to put a deoptimization point in any loop that might be unbounded looping or very long looping so that there's an opportunity to deoptimize that stack frame before it runs for minutes or days or something。

If the loop is banded or shore。You know， guarantee or it has one of these other things。

 it has a coal site in it that can't be avoided in the loop and you don't need an extra de optimization point you can do the deal of the call when the call enters the method the thing that's being called。

So you sprinkle these thingss through your IR based on the rules。

Notice we've also got GC save points that we need as well and they often coincide because they produce best with the same information。

 the GC save points information is just a subset it just saying here are the pointers okay you know I don't care what they're called I don't care about the names of the variables and I don't care about the variables that don't contain pointers here are the pointers and where theyll live on the stack and then the registers。

So they two are very strongly related and often a safe point for GC will often be a deopt point too。

 but there are different purposes and they don't have to be completely coincident and in particular from the point of view of implementation。

 deoptimisation are rare events and so reconstructing a stack frame in an optimized form is something you can do fairly leisurely it doesn't have to be done in the blink of an eye because it's probably going to trigger a whole bunch of compilations and they take a bunch of time too so DOs are rare and  querying that structure you know it has to be general。

 but it's probably too slow for GC because GC has scan stacks regularly in fact。

So usually the G info is just kept in a separate， more summarized， and more easily access。

So how do we do this， let's consider the easy case first where we're just deoptimizing。

The top frame on the step， we have a frame， it has a bunch of variables。

 there are other variables in the source program。But they've gone from this and this is in fact the optimization by inlining their several other frames。

 so what we're going to do is we're first going to copy this frame off onto some other the piece of memory so that we can start unpacking it。

And in its place we're going to make the replacement frames。

 So at the point that we're suspended at that safe point。

 we're going have a chain through the scope desk tree that ends at this point of the tree covers a whole bunch of safe points in the code one particular leaf is the point at which this is suspended So from that tree we pull out a stack of frame descriptors。

 frame descriptors tell us which frames we have to generate， we look at the methods。

 the methods tell us how big the frames have to be where the variables are going to be。

 So we put right onto the stack the frames corresponding to that slice of the tree。

And then what we're going to do is we're going to copy across the values using the name descriptors in that tree to locate the values here or the cached ones that were optimized away that are in the debug information that we're accessing to do this so that's going to take those and the other things and it's going to sprinkle them through these frames so you know some are coming from elsewhere I' not sure and some are coming from here and we're going to put them in there and now we're done right all we've got to do this point is right in the return address。

So this guy， you know， the return addresses of the intermediate calls and went up。不是不是可送上。Okay。

 so how do we deal with the frames that are not on the top of the stack well there's a cheap and easy trick here or the bugstail where this one is。

Notorious。So instead of trying to deoptimize the frames below the top of the stack in place。

 which we can't do because the space， you know the unoptimized ones are usually bigger than the optimized equivalent frame so we can't you know we'd have to sort of stretch the stack out as we were building it we can just pun and not do that now we do them when we return into those frames。

So what we're going to do is look at the return address that's going to go into a frame that we wanted to optimizeimise and instead we're going to direct it off to the sign into a little trampoline。

That's going to catch that return and say， aha， we're about to return into this optimized trend。

 but before we do that we're going to deoptimize it so we only have to deal with a top of stack case。

So again a little movie sequence， of course we have these three frames on the top of stack and we want to de optimizetimize all of them first thing we're going to do is de optimizetimize the top one into its constituent frame we're going to let the program run before that we're we're going to patch the return address into a little deoptimization tramly and we're going to let the program run and eventually those frame will pop off the stack and return。

when they return， they return into the trampoline and then the trampoline can rewrite the one that's now on the top of。

The beat frame and install another trampoline to deoptimize C when we get back to there。

 we run those those pop off its stack。And。Eventually。

 we rewrite those into a de optimize and got way down and if we never return down to here because the process term minutes or whatever I'm done any work。

 the optimizing thing。How do you feel about making？The optimized frames have a minimal size of。要完。

That would be very wasteful well if it depends on your language and the level of aggression you turn to tick in lineing。

 but in the self system， it've probably increased as tax size tenfold。

The non trivial and then you have to record the holes so that the GC， you know。

 if you're going to do stack scanning， you have to know sort of where the stuff is still。

So you probably couldnt use the trick bar actually there's a bigger problem which is that how big did you make it because you have an inlining tree right。

 you're going to make it the depth of the biggest yeah that's the only one that would work you'd have to do the full analysis of the tree and work out the worst case even though you might never call that。

 you might not go down that path where those in light trained live， so it can be。对呃。

So district probably applies to some particular applications of deopim right because for example。

 if you want to use deopimization forvo a debugger。

 then you would want to be able to walk the entire stack at the point that you pause Well what you do is you do this kind of deopimization and。

Yeah， if you want to look at frames than the top one， then you have to deoptimize the whole yeah。

 you basically sort of artificially pop the stack off and build those frames。Yeah。

Well you can also use。If the debugger is only going to inspect normally debuggers， you can't。

Change the flow of control， except at the top of the stack。 You can in inspect and change values。

 And this still gives you the ability to do that because you still have the full。

Descriptor tree for every point。In the stack， so you could still find a value and display on the screen。

And if the person set changes the value， you can put it in there。

 but what you can't do is sort of respond to code change that。So normally。

 if you look in systems that do this， when you change the code deepen the stack。

 then you know it has to。It has this delayed effect on the stack frame。Yes。

 so when I run my job programs。They run about。see what。知道我系。When you say debu mode。

 do you mean why are size like？诶。I guess I click the debug button because the way it's meant to work with hottpot is you should be able to do full debugging even on an fully optimized implementation through this trip。

So you go in and you set a break point and the break point at the point at which it hits the break point。

 then it de optimizetimizes what it needs to do to give that There is another level of。

Debugging and I'm trying to remember the details which turns on extra stuff that might be gathered for you and that might be what's slowing you down。

 but I'd have to look carefully at what the button did。

On which flags will be set and the other source is probably just the initial compilation。

You mightight have also done several optimizations initially before it be gotten。types。

And if you want to be bugging， you want like line by line and it's possible they have。

Freases optimizations。 Well， that's the whole point of this that you don't have to。Right。

 what about the other initial？Well if youway went from source to whitecode。Oh。

 it doesn't usually do anything with bikecode。From source of bikecode never does optimizations。

 It doesn't attempt to undo those when you stop running debugging。

Because there are none that are transformative in the way that you lose anything。

Right there used to be if you look back at the early version of the GDK there was a dashO option which would do things like inline final Seors and getters。

 but the problem with that is when you change one of those things now it's inline and you get bycode and so you'd have to do this on the bycode down so they took that out after a couple of versions。

 I don't think there's anything now。In the bycode， on this not on the oracle one anyway。

 I don't know whether or anything else like that， I don't think so， not in the bycode。No。

 from the pilot to the bike cover。I sorry， from the from the Java to the bikecode。

 there should be optimization dont so。Don Java programs that run Dbug would also have to listen on particular report for messages。

And。Yeah， so when when you start， when you start， well so it。So if you start the thing up。

With a debugger attached， there's a separate agent that starts up that listens for the debugging。

 but that shouldn't affect the performance of the other threads if you turn on some of the monitoring option。

In the debug interface， like for example， you want to profile allocations。

 well then all your allocations are going to get de optimizetimized into things which are accountable right it's not going to generate the profile encode in line。

To do all of that so if you turn on a lot of observation。

 then it gets a lot slower but that's sort of what you'd expect maybe gets more slower than you would like but you're going to pay a price there one way or the other but if all you're doing is set in a breakpoint it should run at full speed up for the break point。

Okay。わましたけ。嗯。So there are a few refinements that this is basically of the scheme that was described in '94 and a thesis that has's been implemented a few times。

There are a few refinements since then， one in particular I'm going to mention is when you do a deoptimization。

 you know， that's usually。The point of de optimizationim is the function of the code you generate and how you get into it。

 but you don't necessarily have to resume exactly that point。

You can resume any time before that as long as you can track the effects and redo them。

 so in particular many operations in code are just going to affect registers or stack variables。

And they're not going to affect memory locations， you know you're not going to do a store or something like that and so you can start you can resume execution further back than the deopt point and replay the stuff which is not going to have any adverse side effects and one of the reasons you would do that is because these deopt points require this data structure is going be maintained off to the side and they also constrain optimizations because you can't flow a whole bunch of stuff across these points so you want few of them as possible and you want them to have a lot of flexibility so this particular paper that I've put included in the literature it attaches the framet to the last side effect so they're attached to side effecting operations side effecting here meaning stuff that's not described fully by the framet of stuff in memory。

And those things can move around as the code gets reoptimized and when it deoptimizes。

 it deoptimizes back to the last side effecting branch there and rolls forward from there。

So that gives them the ability to eliminate and merge a whole bunch of these descriptors and compress the size and do more optimizations without having to be overconstrained。

So that's a useful refinement。This is a。A similar trick that's based on the same idea。

 which is to optimize in the opposite direction so you have， suppose you have a long running loop。

And when you execute the loop at first， all the methods are unopimized。

And halfway through you trigger a counter and you invoke a compilation of the loop and it's call leaf。

 but the loop's already on the stack right the frame is already there。

 you don't want to wear until the method is re executedecuted that contains the loop。

You want to replace the loop in situ with the optimized version of the loop and continue forward from there。

 and that's kind of the same thing in the other direction。

 you're going from unoptimized frames to an optimized frame and trying you're pulling in all of the with unoptimized frames and stuffing it into the optimized one the program counter that corresponds to the place where you did the recompilation and you suspend the frame so it's sort of the same thing but in reverse with the frames。

 but the technology is exactly the same So it's a fairly straightforward extension it's called on stack replacement it means that when you run particularly a long-running microbech that the benchmark is optimized as it's running rather than within until the next execution of the benchmark because usually microbechs is just a loop with a handful of small operations in。

And if you wears it until the loop ran again， the benchmark would be over。

 so that was the original motivation bud。Re observers do have loops that run for a long time and we want to be able to。

So that's the extension to that in the literature I've included a reference to a paper by IBM in the Halllapeno Jg system where they had a very nice technique for transitioning from optimized code to reopim but optimize differently code。

To avoid the step of running through unoptimized。Going from un optimize code to optimize code also happens。

Callor function。Yeah， so when you call you find whatever。

 you know you use whatever lookup technique you've got。

 whether it's an inline cache or a log global lookup or whatever。

 and you find what's considered to be the the current version of the code and that might be an optimized version。

 yes。seeWell， that's the easy one to handle because。You know， you can read。

Direct that link to anything you like as it gets recompilled。

The difficult case is when the code is already on the stack and executing。

And that's what you need to on stack replacement to replace the frame with the optimized frame。オ。

So the last thing I want to cover is some of the mechanics that have to go behind all of this to make it work so one of the things we're doing here is we're taking end methods and we're deciding okay。

 we don't want to use that anymore it's somehow invalid because one of the assumptions it made during the compilation is wrong so we want to get out of it and we don't call it again。

And so we have to do a bunch of work to make that happen The first thing is you want to find all the places that it's referenced and retarget those references to the newer version of the method or to a st that you know invokes a compiler or invokes lookup or whatever to find that version of the method。

 the easy examples a global lookup tables because there's a reason to navigate based on the name of the method and the type to find the pointer。

嗯。Inline caches are and ps are going to be you know prolific and only a lot of them in the system and you don't want to search through the mall you're want to find the ones exactly the reference the end method you're flushing you may also have references from the camp stubbs that I showed in the earlier slides you know those will have calls。

And if you optimized a away of a virtual dispatch， you might have direct calls from one method to another in some states。

 you have to find all of these things and patch them to call the other thing or to call up a lookup。

And so。Another component of EVM is going to be a dependency maintenance mechanism that tracks all of these things。

 so for any particular end method。You want a list of all of the things that you have to change when that thing gets invalidated when you're going to flush it。

In self。This was used a C data structure called an N method link which was a bidirectional link。

 it was astruct with pointers it was a ring， in fact， all of the entries were on the ring。

And so you could go around the ring in either direction and find all of the things that you needed to nuke and nuke them fairly quickly and you see those embedded in all of the scope descriptors and the inline caches and everything it's used universal for the dependency change。

You also have to track every compiler assumption that can be undone and all the independence is all that。

So you know， if you've inlined based on a method being the leaf method in a tree。

 then that assumption has to record in all places you've inline that method。嗯。

Another trick that's useful here because that will get you all of the links。

 the optimization will deal with your stacks， but you don't want to get into all methods if possible。

 another trick that's common is to just plant a trap at the entry point of a method that you're。

That you've invalidated so that any new entries will hit the track and get attached for deoptimization this stuff gets。

 as you can imagine fairly hair when you want multiple threads and some of them are running and some of them are not because what you're going to do is you're going to go through all of the threads in turn。

 suspend them scanless act looking for a thing that needs to be thrown away。

 deoptimize potentially lazily as we're doing you know so you're queuing up a bunch of deoptimizations off to the side and the stubs to do all of the work。

Going through the threads and meanwhile a of are executing and meeting calls right and what you don't want to do is get in a situation where the work you're doing you know is being done behind your back by something running and triggering the compiler and do more enlightening of the same thing that you're trying to hum in line。

So it can be quite a little bookkeeping task to get all this stuff straight。So。

To show you this in action。Another demo。Let's switch back to。So。Again。2，2，9。一百。嗯。IllStart up。てやす。た。

Ch。Os。请分的。Scrolled off some。行。Okay。I'm going turn on。The spine。littlettle window into。Inner workings。

 So you remember I showed you this when we were doing the GC is the he。

And the generation will collect it doing its thing。Do we get scavengers？Off to the side here。

 I didn't point to have this lesson。 This is the code cache in itself， it's called the zone。

And so this block here is the area where compiled code lives at this end。

 the non inline code grow from this end at this end there's the in fact this is a lie。

 they don't really gross one each other they're inter that this is just the graphic depiction of the amounts。

 so this is the inlined code this is the unoptimized code here is the space for the polymorphic inline caches and the other stubs and then there's spaces for the dependence of chains and the debug info and you can see we've got some stuff there and as I run。

We should be able to get more it it compiles more and do random things。

WhatRandom thing can I do to generate。That's open effect try a million there we go so so there's sorry。

 what was that a million a million well， that's only just going to make， you know， one method。

This playover has a whole bunch of classes in it that hopefully it should have given us。

A reasonable amount of code after that。's still not huge amount。Okay， now。Remember。

 I talked about dependencies and inlining。 So let's get。温度唔多。Number 3。

And let's find where it implements plus。So search for。我。And plus is implemented from right there。

 So we see the definition of plus itself here and what this does is。It's going to try and coerce our。

Small integer， the argument。 sorry， it's going。So this is in small land。

What's that doing a small receiver Anyway， there's。

 there's an inting here and a prim to do the addition。 And if not。

 there's all the type conversions and the。And那。And they're dealing with errors and all of that stuff。

Now a lot small total。I can go in and change this。So， let's say， we are。We decide。

Some large number has different addition behavior， so we're going to say if self is equal to1，2，3，4。

5，6。Then。Whatever we add to that。We're going to return on 42。Okay， now。This is integer plus。

 right this has been in lined。A lot of places。So when I hit the green button here to accept this。

 it's going to generate this code。Get an end method out of this and then it's going to have to find all the places where I inline plus。

 flush the code and deoptimize all those frames。Lasly， of course， it's not actually deoptimizing。

 it's just planting the return address pointers and then start recompiling again because the hole will flush a lot of code。

 so watch these bars because this is the compiled code when I do this。嗯。And if I hit this button。你谁啊。

对。Okay。If you don't believe it。I can do。1，2，3，4，5，5。Plus。It's not too big。do you expect。If I do1。

 two， three，4， five， six。It right。そ。嗯。So everywhere in the system that's doing intra0 we think now is compiled in a special case for 12。

3，456 definition zero。Can we change the definition of classic。Yeah sure it will not do well。

 I picked an integer that deliberately I think is unlikely to be an active use if yeah I'll break if you like。

 I mean that's fine。If we change that to zero anything was zero。Well whatever you like， I mean。

 you know surea I don't expect the button to come up when I click this。

 I don't expect this screen to continue redrawing Imagine we're going to see a stack dump from here as things go either that or very strange graphics。

あ。De。So what does with for sexes。But never actually。要ば。When me build the difference。All right。

This was a classic case。是。Just a terrible bug to hide。😀。

One day somebody is going to be pulling theirarrow out。Okay。

 so that's that's kind of all of the pieces hopefully you've got a kind of coherent picture now of how these systems work I mean there's a lot of detail and it would have been nice if you had you know a year of laps to build one of these I was actually hoping we might be able to get to building a simple day optimize of but didn't happen。

But you've kind of got this picture now of how you gather， you know。

 you do a simple compile or an interpretation， you gather data and you've seen the mechanisms for gathering data。

 once you've gathered the data and the counters trip。

 now you have a framework for figuring out how to compile and what to compile and how to make optimization decisions based on the history of the system and how to generate good code and if you make a mistake in generating codinging that you assume something that turns out not to be true。

 you've also got a way of backing out of that。And so what we'll do in a couple of weeks is we'll start looking at a system。

 develop my group of Oracle labs， which kind of packages all the stuff up in one framework that you can reuse so you can reuse the pieces without actually knowing how to having to deal with implementation of any of the individual components and you can implement a language on top of the system using all these techniques。

 so the last exercise is going to be a fe implementation in that system。Using all this stuff。

 and I'll explain some of that in a couple of weeks time。嗯。

I should give a caveat as to what we've lost。What we've lost in all of this is on route to our good peak performance through good compile code。

It's pretty hard to know how anything is going to behave。

Because in the middle you're going to get some very strange mix of un optimizeimd and optimized code and optimize decisions that have to get undone as the program involves。

 etc and so it's very hard to know how fast anything is going to run anymore in a system like this if you write a small loop and it's a good compiler you'll know you'll get good code but in a big system with a lot of code it's really hard to understand where the performance is luckily our machines all run gigahertz and not megaHtz and so most of this stuff is hidden that the covers by the performance of the system the fact that that you when that was first demonstrated that trick of redoing the integer plus。

 there was a pause of about five seconds and recompiled enough to get going again now it's like a blink of an eye youre doing the same amount of compilation but it's probably know 100 times faster than it was20 years。

Okay so to make this all work properly， you know's implement the mechanisms。

 but then there's all the engineering to sort of tweak the heuristics and make sure that the system is relatively stable in the face of changes in the early selfsst the very first one prior to this feedback technique used all the optimization techniques but the compiler was open loop it would see a piece of codeence says。

 I know what to do with that and go off and compile and compile and compile and compile compile and sometimes it would do great and sometimes it was hopeless and you could never tell which you were going to get unless you were running a benchmark in which case it was great but anything as soon as you stray off the benchmark。

 the performance was all over the place and the compiler pauses were you just staggeringly long sometimes like minutes are sometimes of compilation So the feedback technique has given way of grounding that out and stabilizing things but this cost of predictability because we' got。

It's kind of Heisenbergingham system right now the stuff you don't run never gets compiled the stuff you do run if you look at it a lot I'm curious know what this code is I'll stick in and an'll open run it a million times well the performance is fantastic because it ran a million times and the compiler you know really optimized it but if it's in between those。

How do you know what you're going to get， It's very， very knowledge。Hard to know。

 that's what we've lost。That is it for today next week we'll have last back here from Denmark。

Hes the architect of a bunch of VMs of great commercial significance。

 He was the one who initiated Hotspot and Google V and DarA。 He'll be talking next week about Dar。

And we'll have a Q&A with him on anything you like。

 so I'll post a call for questions on the Piazza and the week after that Col Friedri bolts is going to Skype in from Germany he's the lead implementer on the Pipepe Me tracing system now not only do you not know what meta tracing is we haven't talked about tracing yet。

 so there'll be a reading assignment about tracing coming up to give you some background for that。

And。We'll talk about yet to come in the few weeks we've got left。

 Theres a discussion of meta circularrcular V Ms， which is an attempt to。

Write all this stuff in a higher level language and make it easier because kind of。

As you've seen by now， there's a certain amount of rocket science in making this stuff whole work。

So we want to try and take that out that was the first attempt doing in a higher level language and then we'll look at truffle and growl。

 which are sort of the current state of the art of that in my group and we'll have an exercise around there。

And perhaps I will have a look at some of the issues that get introduced into all of this when you go concurrent。

And you have multiple threads because there's a whole bunch of it's more like a laundry list of problems than solutions。

Because the solutions is just sort of obvious these stuff。Okay。That's it today。

And we'll release the rules for。We should we should yeah， we should。 Yeah。

 So we're going to I'm going to give you a GC bought a surprise and any other kickknacks I could find in looking onacles。

