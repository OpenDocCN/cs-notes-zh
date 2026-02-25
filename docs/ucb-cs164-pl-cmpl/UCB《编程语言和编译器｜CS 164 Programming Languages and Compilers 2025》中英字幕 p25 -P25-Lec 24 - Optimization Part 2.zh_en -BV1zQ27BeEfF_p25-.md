# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p25 -P25-Lec 24 - Optimization Part 2.zh_en -BV1zQ27BeEfF_p25-

Hello， everybody。 Happy Thursday。😊，So today， we have very exciting stuff on the menu。

 We get to continue our exciting optimizations from。

 I guess it's two sessions now that we've been thinking about optimization。

 So we've learned two of them so far。 We'll learn a third today。😊。

And then we will dig into even more optimizations， but we will do it with the lens of what else can we do optimizations on other than our As Ts。

 where we've been doing our optimizations so far。 And we will learn about one really expensive but really valuable optimization that we can make if we are working on a separate intermediate representation other than the A T。

 So we will be building towards that。 We probably won't get all the way through that until Monday。

 But basically， we get a lot more fun optimization stuff today。😊，So。

I'm going to go ahead and have us dive in on our our optimizations that we were thinking about last time。

 So if you remember， we took a look already at constant folding。

 we figured out when do we think it is safe to apply this， When will we not break anything。

 And we figured out when we can statically determine the value of a given sub expressionpression。

 and we can go ahead and actually sub that value instead。

And we thought about when do we want to actually apply this， when will it make things better。

 and we decided just always， right， if we can calculate the value associated with the whole sub。

 we'd always like to just replace it with the value。And then we talked for a while about inlining。

 and we figured out that we can do this safely when we're in the situation of dealing with nonrecursive functions or recursive functions where we know the argument statically。

 we also need to actually know what function it is。 Otherwise。

 we're probably not gonna be able to figure out what body to sub there。

 And we figured out we also need to be not using any free variables in the body if we want to be going around and sticking the body elsewhere。

 because otherwise， we might go ahead and try to stick it in somewhere where we don't even have access to the values that' are actually free inside that function。

And then we also thought about， okay， when do we want to apply this。

 And we decided we mostly want to do this when we're not gonna blow up the code too much。

 So that's going to be cases where we are dealing with short functions that have few static call sites。

And then we were about to turn to our third optimization。 So as with our second optimization。



![](img/61ade704665d282a7d90a2f85fdae687_1.png)

We were gonna go ahead and start by looking at an example。 And again。

 I have structured this example with the idea that it will probably give you some suggestion of what a a relevant optimization might be。



![](img/61ade704665d282a7d90a2f85fdae687_3.png)

So I'm going ask you to go ahead and turn to the folks nearby and think to yourself。

 what is a change that you might make to this program， It might make it more efficient。Alright。

 does anyone have any ideas for me？ What would you like me to do。I love it。

 Putting X plus  two into a let binding。 It sure seems like we have this one expression that's just showing up a bunch of times。

 means that we're doing this work over and over and over again。😊，That doesn't really seem necessary。

 So let's go ahead。And sub a new little lightbin here。

 I'm probably gonna mess up the number of pers for that。 I apologize immensely。

 Let's go ahead and do Y。 Let's set it equal to plus x 2。

 And then in these places where we are trying to do plus X 2， let's just replace it with。Wai。

And then if I'm not mistaken， we need one more print at the end， we should be good to go。

Do we all feel good about the change we just made there， We feel like， okay。

 that kind of makes sense， right， We saw the cases where we were doing that same work over and over again。

 That seemed a little redundant。 Let's go ahead and only do that work once。😊。

Feeling pretty good about that。Okay， yeah， so this is probably a performance written， right。

 rather than doing the computation three times。 just do it once。 It's not that this is， you know。

 necessarily expensive， but this is still， you know， this is gonna save us some work。

 like maybe two additions。I briefly last session mentioned rematerialization where we are getting rid of aette and just recomputing。

 This is the opposite of that， right， So optimizations can run in both directions。 Alright。

 I'm gonna have us look at one more example。 And what I want you to decide。

 So I didn't actually tell you the name of this optimization。

 This optimization is called common sub expressionion elimination or CE。

 it really pretty much does exactly what it says on the tin。 right。

 We see this common sub expression。 We go ahead and eliminate it right， So CE。

 So now I'm gonna ask you to go ahead and turn to the folks next to you。😊，And decide。

 can we run comments of expression on this program。Alright， let's do our vote。

 Go ahead and hum if you think， yes， this is safe。 Let's do it。Go ahead and hum if you think， na。

 let's not。Allright， I love it。 So it seems like we came down on the side of yes。

 And that's absolutely right。 right， So if we think about it。

 this is actually even potentially a much bigger win， right， looking at it。

 we're seeing that this could be a really quite long computation。😊。

And so this is getting us back to the idea of constant functions。 right， Okay， so let's。

 let's talk through this。Random fun side note， it turns out this is basically just summing up the numbers up to X。

 So a fun fact about GCC。 It actually knows that there is a closed form solution for this particular calculation。

 So if you put something like this through Gcc at the highest optimization level。

 What you'll get back is just x times X1 over2， which I think is really cool。 We are not that fancy。

 We are not gonna do that。 But I do think is really cool。

 So back to our thing back to common sub expressionion elimination。

 we talked about the idea of constant functions functions that on a given argument are always going produce the same value。

 In this case， we only do that read numb once， So it's just gonna be that same value。

 we can go ahead and feed that same value to some to three times do the work three times or we could go ahead and just feed it once and get back that same value associated with our let binding。

😊，So that's what were gonna do。 So this is， this is sort of the weird thing， right。

 because sum two is complex， but it is constant。 So we actually can do this optimization。

 And in fact， we're gonna get a big win out of it because this is an O of x function。

 So this could actually be a potentially quite big performance win。 So3 X performance win。

 We like it。😊，嗯。Special note。 So technically， constant functions are actually a subset of pure functions。

 But for our purposes today， we can just use these as synonyms。

 but we can sort of dive in on that if folks are curious。 But in the meantime。

 I want to go ahead and talk about our third program。 So go ahead and discuss with folks nearby。

 Can we run common sub expressionion elimination on program number 3。😊，Alright， let's do our humming。

 So let's hum for We think， yes， let's absolutely do CSE here。😊，Hum for no， we think let's not。Yeah。

 I completely agree， right， So one of our， one of our things that we promised with all these optimizations is we had better not change the semantics。

 We'd better not change the meaning of the program。 And， of course。

 if we do something here where we say， let me go ahead， do let。I'm gonna mess up the print again。

 Let why。Read。Plus， X， right， because remember， inside read plus， we have that read numb。

 So we call our our read plus。And then inside here， we're just going go ahead and reuse。Why。😔，Oop。

 sorry。Yeah， okay。 that was not the right replacement we have to do。Wai。😔，And then inside here。

 we do why。And said， here we do why。 Okay， that's the right replacement。 right。

 So what has changed is we have gone from calling read plus three times and getting three separate inputs from the user to now only calling read plus once right。

 and getting that one input from the user and then reusing it across these three calls。

So that's certainly not what we want。 That is going to actually change the behavior of the program。

 So we are not allowed to do common sub expressionpression elimination in this case。

 So this is going to help us think about our two questions of when can this optimization be applied and when should this optimization be applied。

 So let's move on from looking at in lineing to thinking about it for common sub expression elimination。

 And what I want you to do is talk to the folks nearby for about a minute about question number one in question number two。

 So when can this optimization be， and I'll here insert safely。



![](img/61ade704665d282a7d90a2f85fdae687_5.png)

![](img/61ade704665d282a7d90a2f85fdae687_6.png)

When can it be safely applied and when should this optimization be applied。

 When is it gonna give us the biggest boost。Alright， so when can we go ahead and have this fire。

 have this change our， our program。When the expression is not dependent on program state， yeah。

 I I think we're in the， in the right area there So it's when it's not going to have side effects。

 right， So we're not gonna be going ahead and， and reading in anything from the environment or putting something out in the environment。

 Yeah， so I love it。 Okay， great。 So let's go ahead and write that down， so。When。Expression。

Has multiple。Mable。Identical。Side effect。Free， right， So that's what what you were saying there。

 constant。Subexions。With apologies， as always， for my dreadful handwriting。 Okay， I like that。

 So that looks really good for question  one here。 What about for question 2。

 When do we want to apply this， When is it gonna help us。A little less certainty。

 Let's go ahead and discuss for about another。 Oh， yeah。Love it。 So when the expression。Expression。

Requires。A lot of computation。And this is sort of getting at the general idea of。

 of sort of when we're gonna save a lot from it。 So I， I'll add on one additional note there。

 which is， if the expression。Curs many times。All right。That looks good to me。

 So I'm now feeling pretty good。About our three optimizations that we've learned so far。

Do we have questions about them。If not， I'll just ask you questions about。

I'm not sure I totally understand the question。 So this question was。

 how would we handle free variables？ Maybe， maybe let me try sort of a reframing of this question。

 This question might be about scope。So it might be saying。

 say we're inside a scope where X is bound to 3。 And then somewhere else in the program。

 X is bound to 4。Would I want to do common sub expression elimination in that situation。

 Is that maybe the question。Maybe not sure。So the reason we were thinking about free variables for inlining is because of inlining being caught up with functions。

 right， the whole idea with inlining was， okay， we're gonna go ahead and take this body of a function that we saw somewhere else in the program text。

 We're gonna take that body out and put it in some other part of the program text。

 And because so much of the way our scoping works is based on， okay。

 what is bound within this section of the program， right， the fact that we are using lexical scope。

That is actually a huge deal to take something out of its context where we originally had it and put it somewhere else。

 So that's why we had to think about free variables there。Does that make sense。Great question。

2 thumbs up。 Two thumbs up。Great question。 So this question was。

 how do we define a lot of computation。 And the answer is different compilers will define it a lot of different ways。

 So there is no one true definition， right， I've talked a couple of times about the fact that real compilers are built with a lot of benchmarking。

 So you get people to send in a bunch of programs that they really care about having them be fast。

 You run those through your compiler。 You see how different thresholds end up affecting their downstream performance。

 You decide if you are happy with that downstream performance。

 So different people will operationalize this in different ways。😊。

Different compilers will make different choices based on their different audiences。

 based on the different kinds of programs that people are most likely to be writing with that language。

 So there is no one true answer。 But yeah， sometimes people will。

 will use various proxies for how long you will actually take。

 Sometimes people are really trying to have cost models representing， okay。

 this is likely to take X amount of time。 So people will do lots of different things。因为你说。

This is a great question。 So this question is， it seems hard to figure out what things are side effect free as absolutely right。

 So there are certainly languages that make it easier versus make it harder， for sure。

Even in what we might consider relatively functional， relatively pure languages。

 it can still be actually quite difficult。 So this is very hard to do。

There are compilers that will choose to pour a lot of analysis time into this。

 Toally reasonable choice。 This is absolutely something you can do。

 There are various program analyses that are designed to figure out this kind of thing。

 thumbhumbs up。 There are also program analyses that will just be very conservative。 So they'll say。

 I don't know about this section。 I give up。 I'm gonna go ahead and be on the safe side and not do it。

Either of these is a reasonable choice， depending on the audience that your compiler serves。 But。

 yes， it is super hard to figure out。Not not always， but in the general case。

 especially for languages that wed sort of tend to class towards more imperative。

 it can be difficult to figure out what is set。But we are about to actually think about another representation of programs that will help us think about that question。

Other questions。Yeah。Totally， yes。 So this question was。

 is there a simple heuristic we can use for the amount of computation that a given sub expressionion will will require In general。

 folks tend to use A S T size as an approximate proxy for is this going be， you know， X。

 Y Z number of instructions， Of course， that doesn't count sort of。

 are we gonna run through a multiple times。 I can， But like as a starting point for do we believe this is expensive if the A S T is bigger。

 Probably the computation。There are lost，Alright， I'd like to ask us a question to help check our understanding of optimization。

 So I'm gonna draw us a little picture。So， let's start。With a program I'll call it program zero。

And then I'm gonna run a couple of optimizations on it。 So say that over here。

 I run constant folding。And I get program 1。And so over here。

 I run CSE common sub expressionion elimination。I get program three。Now。

 the fact that I have named them that maybe suggest I'm going to do some other stuff。

 So let's also go ahead and run CSE on program 1。Get up program， too。Over here。

 let's run constant folding。On program 3 and get up program 4。

I'm going to ask a couple of questions here about the differences， if any。

Between program 2 and program 4。 So my first question， I'm gonna ask you to discuss this。

Can program 2 and program 4 be different in terms of correctness。

 Can the order of applying these optimizations。Affect the correctness of these programs。

Go ahead and discuss with folks nearby。Alright， what do we think， Do we think， yes。

 the order can affect the correctness。Do we think， no， the order cannot affect the correctness。

I completely agree， right， The， the contract we entered into as we were starting to design optimizations was we are not going to change the behavior。

 We are going keep the meaning of the programs the same。Therefore。

 whichever direction we order these， we are gonna be expecting that we're getting out equivalent programs。

 equivalent correctness。 So here's my follow on question for you。

Can program 2 and program 4 differ in terms of performance。Go ahead and discuss with folks nearby。

All right， do we think， yes， this could affect performance， H for yes。Do we think no。

 this cannot affect performance， Home for no。I completely agree。 Well， Danielle。

 you're really on top of this optimization situation。 So yeah， absolutely， right。

 If we go ahead and we run constant folding， we could certainly reveal some opportunities to do common of expression elimination。

 Maybe that means that we end up with a faster program too than faster program for。

 On the other hand， we could absolutely find that by doing common of expression elimination。

 we actually find some more opportunities to do constant folding。

 Maybe then we end up with a faster program for than faster program too。

 right One of the weird things about the way optimizations work。

 is that applying them can absolutely reveal opportunities to apply other optimizations。

 which is the reason for sort the approach that we talked about last time when were often sort running optimization than running concept folding again。

 optimization concepting again， there are particular optimizations that are just so useful and we just keep running them over and over again。

 And that's because we're revealing opportunities。 And the order very much can matter。

 which is why we even care about that phase ordering problem that we talked about。

 which is the question of how should we actually choose to order our optimizations。😊，All right。

That was the discussion I wanted to make based on A S T based optimizations。If we're feeling pretty。

 oh， yeah， please。I think there are may be a couple of different questions wrapped up in there。

 So I'll maybe。Or maybe try to separate into two。 One is， do we have a definition of optimal。

And one is。Are we changing the asymptotic worst case runtime。Of our programs。Okay。

 so I think this question is， say we have some kind of a cost function。

 something that we can apply to a program to give us some sense of how fast it is going to be。

 whether that is just running the program or or some other model that we might generate that will go from program to estimate of performance。

Say we have that。 Can we think of this as searching through a space of equivalent programs in order to find the program that has the best cost。

So this is a super reasonable way to think about this problem。

 It is not the way most production compilers think about this problem。

But I will point you to a couple of different spaces of P research that think about the problem in much this way。

 So this is a relatively common way for a category of tools called program synthesis to think about generating programs。

 the basic idea there is that you have some kind of a specification。

 So something that the program needs to fulfill and you are trying to produce the best program for some definition of best that actually meets that specification。

 So say you have an executivecut spec。 So a specification that is just a runable piece of code and you want to find an equivalent piece of code within some given search space。

 you are searching it in some manner， there are many different ways of searching it。

 you are trying to find the one that is best for some definition of best。

 That's program synthesis land。 I also briefly mentioned equality saturation when we talk about the phaseing problem last time。

 and basically what is happening there。 is we are representing at the same time。

 all the different equivalent programs that we've found so far。

 And then eventually were going sort of extract out of this particular specialized data structure called an egraph。

The one that actually represents the fastest program or the program that maximizes some other cost function we have developed。

 So there certainly are things that are thinking about this in general。

 the way most production compilers work is we will apply rewrite， We will apply another rewr。

 We willll apply another rewrite in some kind of a fixed sequence often again。

 because we are expecting to have deterministic output of our compilers。

 So the expectation very much is that it's not going be， oh， I'm gonna search the space for you know。

 a minute。 And whatever I come up with the best thing I come up with after a minute。

 that's the thing I'm going go with， or even necessarily like you could do something that's going search up to a given depth。

But even that， you know， you're gonna get some， some sort of weirdness there。 So in general。

 things that are thinking about it more as search， we normally think it's program synthesis。

 things that are thinking about it more as a sequence of rewrites。 That's more like compilation。

 But there is a fuzzy line between。Awesome question。 I'm a program synthesisth person。

 So I love this area。Other questions。Okay， cool。In that case。

Were going to shift to thinking about a really quite useful optimization called register allocation。

 So all along， as we have been building up our in class compiler。

 we have been deciding right there in our cogen what registers we are going to use for a given operation。

😊，Or whether we're gonna use this stack， right， all of that has been right there in codegen。

And that is a totally fine way to do it。 Obviously。

 we were able to actually write a compiler in that way。

 But we were also frequently mentioning this fact that storing things in registers is very。

 very fast。 Accessing registers very， very fast。 We like to do that。😊。

And then storing things on the stack， storing things in the heave， right， generally going to memory。

 not so fast。 We don't really want to do that if we can avoid it。

 But we've actually been doing quite a lot of that the way we have set things up right now。

 And it turns out that there is actually a way for us to do better。😊。

But the way for us to do better is to do something called register allocation。

 which typically operates on a particular intermediate representation。

And this representation is gonna be a little bit weird because right now。

 we have been thinking about optimizations on A S Ts and A S Ts， if we sort of think about it。

 look relatively close to sort of the syntax the user wrote， right。

 It still kind of looks like the program as the user provided it to us。

As we start moving to the particular intermediate representation that I'm going to present today。

 that's actually going to look quite a lot more like instructions。 It's gonna be more low level。

So we're gonna get introduced to intermediate representations right now。

 And then we're gonna to use the background we get from that on on one particular intermediate representation or I R。

 We're gonna use the background we get from that in order to actually learn about register allocation。

 So let's go ahead。And dive in。That was sure a blank screen。 Okay， there we go。 Here we are。

We are in intermediate representation land and what's happening Inter intermediate representation land。

 Well， we've gone ahead and actually thought about a way to change our pipeline。

 So throughout so far， we've been dealing with this pipeline。It has worked。

 We've gotten everywhere we needed to go。 And we've been able to do all of this optimization where we're messing around with our A S Ts。

 right， We're going back and forth。 We're going back and forth。😊，But then down here。

 we can see that we have one new thing， which is we're going ahead and transforming from the A S T to an I R an intermediate representation before we transform to instructions。

 In fact， if we zoom in on here， often what's happening in real compilers is well transform from I R 1 to I R 2。

IR 3。Kind of weird， right， Because， again， we've been able to do everything we actually needed to do in order to get working programs up to this point without introducing an I R。

 So let's take a moment to reflect on some reasons， so。Reasons。Number one。

 I've already sort of referred to it。 It turns out it is going to be convenient for us to do some optimizations on this representation。

 So let's say optimizations。In particular， optimizations。

 where it just is more natural to do it on this representation。

 rather than on a representation that looks closer to the program text， the incoming program。

But number  two is actually something a little bit different。

 So it turns out we might have multiple different surface structures。So what do we mean here？

Surface structures。What I mean here is we've sort of thought about it already， actually。

 in the context of your parser homework。And so what you did in your parser homework was you said。

 okay， we've been working with this one syntax for our language this whole time。

What if we wanted a different surface syntax。What would we have to do。

 And you managed to go ahead and recreate the front end of the compiler in order to actually redo all of that work for a new syntax and then go ahead and actually represent the programs in the same A T that we were using for the original syntax。

And that worked because basically， at the core， it was still the same language。Right。

 it had a different syntax。 It looked different， But the language constructs that were available。

 the programs that users can write。Those were all the same。Right。

 so that allowed you to actually use that same A S T to represent it。 But what if。

We had a totally different。Representation is totally different programming language that we were trying to actually。

Represent using the same intermediate representation。 right。

 What if we are gonna go ahead and try to compile C to the exact same A S T that you were using for that homework。

 That would probably be pretty hard， right， Our， our language is touring complaint。

 So we could do it， but it would be pretty painful。

 You probably wouldn't want to do it as a compiler writer。 You would probably instead。Rather。

 have something maybe a bit low level， something that maybe looked more like instructions， which。

 after all， we can compile many， many， many languages down to。 In fact。

 all of the ones we've come up with so far。 So we can go ahead and say。

 what is some other representation。That we could actually compile to other than just an A S T。

 And sort of the reason for this is kind of right there in the name of A S T， right。

 It says abstract syntaxtry。 So certainly we are abstracting out some of the details。

 Maybe we're abstracting away some parens， some Sal colons， that kind of thing。

 But it still says syntaxtry right there。 right， That thing is still pretty close to what the user is writing。

😊，And what we want now， if we are really going to try to have a very different surface syntax is something that's maybe a bit lower level。

 not so tied to the particular language features that are available in the language。

And so here I'm going to go ahead and ask us to think about。

What are the things that actually make us change what's happening on this front side here。

 So if you remember way back when we talked about the fact that this is。The front end。

Of the compiler。And the thing that is going to make us change it， as we've just discussed， is。

Different。For different。Input languages。Right，So if we're trying to put C and we're trying to put O Caml and we're trying to put scheme and we want all of those to be producing the same I R。

 we're gonna want to change that front end， right， So we're gonna want to change the Lexir。

We're going to want to change the parser。And now I'm going to ask us to think about， say for this。

Last hub of it， which as you may recall， is called the backend。What might cause us to change。

The back end。Go ahead and discuss with folks nearby for about half a minute。Alright。

 what do we think， What's gonna make us want to change。The back end。ま you。I love it。

 What if we are targeting a new hardware， right， The thing that's making us change the front end is if we have a different input language。

 What if we have a different output language， right。

 That's the case where we want to go ahead and change what's happening inside codegen。

 what's happening when we actually make instructions。 So maybe as we've been doing this class。

 we've been working with X 86。 But now we want to try risk 5。

 where now we want to make something that's going run on your phone。

 which is probably running an arm processor。 Maybe we've generated some fancy new hardware。

 and we want to be able to run on that。😊，So that's the case where we want to actually change the back end。

 So this is going to change。 It's going to be different。Different for。对。😔，Output。Lang。Or， of course。

 we might say hardware。O。So if we pick an I IR， we can basically play Legos with these components of the compiler。

 You grab one Lego for the front end， depending on what language you are compiling。

 You grab another for the back end， depending on what hardware you are targeting。

And then all of a sudden， we've actually simplifies the process of compiler writing quite a lot。

 because if you think about it， say if you have 100 different languages that you want to compile from。

And 100 different hardwares that you want to compile to。

 if we tried to just make the compiler for every pair of those， thatd be what 1000 compilers， right。

 If instead we take this process where we sort of split it at the I R。

 we can instead do this thing where we have 200 front sorry。

100 front tos to pick from 100 backends to pick from。

 We just have these 200 compiler components that we're gonna snap together in various different ways based on what is the language coming in。

 What is the language going out。So this lets us save a ton of work。 because now。

 instead of having to write separate cogen strategies for all of C， C plus Ha school， etc cetera。

 we can just write separate tokenages or parsers。 And then we can reuse codegen。

 And so this is how a compiler like Gcc actually works。

 And this point is actually pretty unusual to do something like what GCC does。

 where it actually is a single compiler that， supports multiple different languages。

 That's a little bit weird。 Gcc is the main one that still does that But it is still common to define an IR。

 So that we can then reuse those Legos an improvements so that we make for one language on one hardware we can actually be reusing across these multiple different compilers。

 And so that's the deal with if you have heard of something called LL VM。😊。

The IR that some of you may have been most likely to hear about。 So it is not a compiler it itself。

 It is an intermediate representation that many compilers use。 In fact， these days。

 if you're writing the compiler， one of the really common things that you would probably do is you would go ahead and just write your your lectureer and parser compile then from whatever you get out of your parser to not all the way down to instructions。

 but to L VM， and then let L O VM be in charge of taking it down to all the different pieces of hardware that you might actually care about。

Okay， so this makes things much more manageable for us， right。

 We get backend for a lot of different architectures， basically for free。

 if we do something like use the L O BM I R。I do want to talk us through multiple different Is before we dive in on a little more detail on what an IR like that might look for might look like。

 So let's go ahead and talk through a couple。 So this is going to be similar to what we'll talk about today。

With GCC， there are actually several。 So in particular， some are specific for individual hardware。

It's very weird。 It actually， G C uses different levels of IR at different levels of abstraction。

 It even has some Is that are specific for specific architectures。 So like。

 here's the I R that we're gonna use just for X 86。 that kind of thing。 a little bit wacky。

Within O Camel， we have this interesting thing where it basically goes from O Caml。To F lambda。Sorry。

 Lada with the capitalol elderder。To a thing called C minus minus。

 So F Lada is basically just O Ml without the types。

 We need to keep the types around long enough to type check it。 But if you remember， it is， in fact。

 statically typed。 So once we've done that type checking， we can actually throw out all of the types。

 We don't need those anymore。 And so if you ever take a look at F Lada you'll see that actually looks really quite a lot like the language that we have actually implemented in class。

 So would probably look super familiar。 So we've basically implemented that language and then C minus minus C。

 but without a lot of features that make C complex and hard to analyze。

Another thing that some languages do。 and we're not really gonna dive into detail here is they will actually treat C as basically an I R。

 right， We've been going all the way down to assembly instructions。

 But another way you could imagine doing this is just going ahead and compiling to C and then letting the C compiler taken care of actually converting all the way down to whatever hardware you care about。

 you can basically， in that circumstance， C， C， as though it is an I R。嗯。

But now I want to bring us back to this one。 So this is gonna be a really fun I R for us to think about and is going to let us get to the the point of understanding what is happening with register allocation。

 And the first thing that we're gonna need to introduce， I'm sorry。

 Are there questions about that before I introduce us to that I R。😊。

Are we feeling pretty good about our Lego approach where we stick together front end and we stick together at back end that allows us。

 to save a lot of time and energy。😊，Amazing， we love the Legos。I mean， honestly， at this point。

 y'all are all such big experts on sort this process of taking programs through all its various different representations。

 right， We have this this pipeline that we've all been looking at for so long。 like， okay。

 here's the version that is just the string。 Now we have turned it into the tokens。

 Now weve turned into the A C。 Now weve turned it into the generated instructions like youel are absolutely experts on this sort of multiple equivalent representations of programs and programs that transform other programs。

 So this makes sense that seeing an I are seeing one more representation that is also equivalent。

 Maybe isn't hugely surprising。😊，Okay， cool。 So I'll go ahead and take us through。Some of our。

 our I R features that will be useful。 So this is going to be based on L VM。

 It's going to show some properties and concepts that are common for Is。

 and it's gonna be useful for us to understand how we actually do register allocation。

So let's take a look at the first thing we need to understand in order to understand this particular I R。

 And that is the concept of basic blocks。Now， I think just from seeing these two basic blocks。

 So that's the two things in the boxes， you will start to get an idea of some things that basic blocks are going to have in common。

 So I'm going to ask you to go ahead and chat with folks nearby。

 What are some patterns that you are noticing， What are some features that might be common across basic blocks。

Alright， so I'm going to go ahead and highlight some things that I'm noticing。

 And then we're gonna dive deeper on number two here。

So the first thing that I'm noticing as I look at this is that they start with the label。

Second thing I'm noticing， it seems like they have a sequence of a particular style of statement。

 And that's a little vague。 So we're gonna circle back around to that one。 Let's go ahead and say。

 they have。Sequence of a particular。Style。😔，It was statement。

AndThen they seem to end with some kind of a jump。Now。

 I'm particularly interested in number two here。I'm going go ahead and highlight some additional things that might be helpful for us to think about what's happening here。

 Let's go ahead and take a look at what's happening on the left over there。

Versus what's happening on the right。 I'm going to ask you to go ahead and keep discussing with folks nearby。

 What are we noticing is true。About these middle statements。

I'll leave some things for us to discover later。Alright。

 so the first thing I'm going to call out here。So we have these temporary variables appearing over here on the left。

 the things that I've highlighted with sort of the pink there。And we only ever assigned to them once。

Now， this constraint， where we only ever assigned to them once。

 This is called static single assignment or SSA。 Let's go ahead and say static。Single。Assignment。

A lot of Is use SSA。 And we'll see an example of why it's helpful。

 This is actually very easy for our language since we don't have variables that get mutated。

 But for many languages， it takes some work to actually transform programs into this state where we are avoiding overr。

Okay， back to our statement。 So what we have on the right。Is all a very simple kind of expression。

There's no nesting allowed。 We can assign a constant。

 We can call a function on arguments from the temporaries。

 or we can call an operation where the arguments are temporaries。 Now， what is an operation。

 actually kind of a tricky question， Usually， it's something that we know we can compile into approximately one instruction。

This is where we have to make some sort of assumptions about what the hardware will support。

 So we do want to keep these operations super simple in order to make sure that we are actually able to represent this assumption well on the various hardwares that we might care about。

Now， I want us to look briefly at our example on the right。We have the start label。

 We end with a jump。 We have that covered。 We're still doing our operations on temporaries。

 but we also have these two extra things that'll highlight in orange。 We have our load。And our store。

This is how we explicitly access memory。And here， I specifically want us to notice that the addresses also live in our temporaries。

And the other thing I want to mention here is that the temporaries are unique across the whole program。

 right， So remember， SS A aesthetic single assignment。

 the fact that the temporaries are unique across the whole program is part of that property。

Obviously， this is gonna be somewhat different from compiling straight to assembly。 right。

 when we're trying to compile to this， it is gonna look somewhat different。

 We've been doing all of this stuff where we are directly putting in the the various stack locations。

 We're directly putting in the various registers。 Compiling to this is going to look a little bit different。

 So how's this going to work。 Basically， we want to translate， say。

 a let from our language into the basic block。Here， right。

 So let's go ahead and actually do some highlighting based on what is going to appear。 So I'm gonna。

 I'm gonna sort of run this as though I am the compiler。 Okay， so let's go ahead and start。

LetsStart with pink。 So what do we want to do for this？ Well。

 we're going to go ahead and make sure that it is represented in one of our temporaries。

What about for our read nu， Well， let's change our color。 Let's say here's read numbum。

 Let's go ahead and put that in one of our temporaries。What's gonna to come next， well。

We can see that we've got to go ahead， and actually。Do this operation。

 That's fine to fit all in one line because that's gonna to look like approximately1，1 instruction。

 So let's go ahead and outline that。 Now we can start to get a sense of how this is actually working。

 Okay， we want to get the two， and we gonna go ahead and do that。This is all looking。Quite similar。

 I think， to what we do inside our compiler with the exception that we are leaving out some of the details we would have needed in the compiler。

 in particular， the particular X 86 instructions that we're going to use， where specifically。

 we are going to store things。And then there's some stuff that's still a little bit weird。

 So if we take a look at。Our X here， right， So this is all getting assigned to X。

 We're then using X down here， we can see that even though we no longer see X in the text of this program。

 this basic block， we are still able to take advantage of something like a symbol table。

 because we can see that even once we've done this， this assignment right here。

 We do actually know how to use it。 So you can think about， okay。

 there's probably something inside there that is basically representing the symbol table representing what temporary variables we're using in order to do stuff。

But it's nice that we don't actually have to worry about ever clobbering our temporaries， right。

 It's almost as though we suddenly have infinite registers。 And we can just keep saying， okay。

 a new register， a new register， a new register， right。

 So that is giving us some things that are a little bit simpler compared to what we've been doing。

Are there questions。About what's happening in our IR so far before I introduce us to the next key part of it。

Okay， cool。 Is now a good time for a break。 Yeah， let's go ahead and take our five minute break。

 We will come back together at 4，35， and then we will learn about control flow graphs。😊，So quiet。

It just that it's pre Thanksgiving。 We're all just tired。Yeah， okay， that's it。Allright。

 let's go ahead and dive back in。So。We left with a program where we only needed one basic block to represent it。

That was looking pretty good。 We were starting to understand how okay we could sort of go through and in the same way that we sort of went through piece by piece of the subree in order to build up a program in our assembly。

 we might do much the same thing here with sort of the big crucial difference that okay。

 we're not saying any particular spot on the stack or any particular register where we want to store things。

But otherwise， it was looking fairly similar。 But now here we are with a program that is going to require some jumps。

 right， So we've introduced this if here。 And it looks like we are gonna have to have some jumps as a result of that。

So this brings us to control flow graphs。 Our basic blocks have to be connected。

 So almost any realistic compiler is going to have control flow graphs as an I R at some point in the in the compiler。

 It's just such a useful representation。 It makes a ton easier to do a lot of the things that we care about doing。

So let's think not just about these basic blocks in isolation。 Like。

 it is interesting that we have the multiple basic blocks。 And， of course。

 we remember our sort of constraints on what basic blocks were shaped by。

 We remembered that if there is any jump that had to appear at the end。

 And so we've had to break it apart in order to do that。

 we couldn't just keep going with more statements after I actually had had hit that jump。

 And so we've had to break it down into L1 L2 L 3 L 4。 So every time we see a jump。

 you can see that we've gone ahead and started a fresh basic block。 So there's no jumps internally。

 no labels internally， only those statements， any time we hit a jump， we make a split。

I want us to walk through sort of what's happening inside。 So in particular。

 I want us to see where things are ending up。 So I'm not gonna bother with the changing colors because I think we'rere mostly caught it based on how our compilers work so far。

 we can see that we have this0。 Okay， we have this0。 We have this readum， We have this readum。

 We need to check if they're the same， because we need to check if they're the same， right。

 And that's the point where we hit our if。 So that's sorry the point where we hit our jump。

 And therefore we have to actually make our little split。

 And then we can see that things get a little bit interesting， because， of course。

 as soon as we hit a jump， we're gonna end up in different basic blocks。

 which means that there's actually gonna be a separate basic block for if we go down the true path。

 right， for。4 versus if we go down the false path，5。

 so we can start to see some structure building up。 And， of course， if we take a look。

At what's actually happening sort of inside these jumps and inside this fee thing that we haven't seen before。

 we can see a little bit about how these blocks are connected。 So let's go ahead and say， okay。

 here's this L 2 thing。 That seems like that's pointing to L2。 Here's this L3 thing。

 That seems like it's pointing to L3。 Here we've got this jump to L 4。

 Here we've got this jump to L 4。 We're starting to see something about how it's connected。 But。

 of course， the way I have it drawn on here is not particularly easy to read。

 So let me sort of rewrite that structure。So say we're talking about L1。

And then it might go one of two different ways。 It might go to L 2。 It might go to L 3。And then。

 at the end。Those are going to rejoin。And they're going to go to L 4。Now。

 this fee thing is a little bit weird， right， So we can， we can lay this out independently like this。

 It's not as useful。 What we really want to do is lay out as a graph。

 outgoing edges to all of the places where you can jump， right。

 We're just looking at those jumps in order to figure out the outgoing edges， right， So L 2， L2， L 3。

 L 3， L 4， L 4， L 4， L4， That's giving us all of those outgoing edges。

 But then what's this fee thing， right， The idea with fee is that we are going to get a different value in T 5。

 depending on which block we are coming from。So if we're jumping from L 2， T 5 is going to be T 3。

 If we're jumping from L 3， T 5 is going to be T 4。 Now， why do we need this。

Anyone remember something that we learned about our basic blocks earlier？

We can only assign to any of our temporary variables once。

 right anywhere across the entirety of the program， those temporary variables have to be unique。

 So we can only have this one assignment to T 5。 It's not okay to have one assignment to it in here and another assignment to it in here。

 And so we have to introduce this fee thing。 There' is basically representing a sort of an approximation and overgeneralization of what could be happening。

 So this is representing the fact that we could be in the state where T 5 is T 3。

 or in the state where T5 is T 4。 We could be in either of those situations。

So we can't just set T 5 differently in L2 E3 because we're only allowed to assign for it once in the entire program。

All right。These graphs are powerful enough to represent all of our control flow patterns。

 except for function calls。 So here is the pattern that we just saw， right， and go ahead and see it。

 If going right there。 I'm going to ask you to go ahead and discuss with someone nearby。

 What does this one represent。 What is a control flow pattern that would be represented by a control flow graph like that。

So what do we think， What is a control flow pattern that might produce this control flow graph。

I love it。 A loop。 absolutely。 That looks like a wild loop to me，100%。 So right， we can go down。

 We can see， okay， is our condition true。 If yes， let's go through the body， Let's loop back around。

 Is the condition true。 Yep， let's go through the body， Let's loop around。 Is our condition true。 Oh。

 no， back to the edge。 Absutely looks like a loop。😊，And now we're gonna get into procedures。

 So here we go， we're gonna notice a couple of things about how we deal with procedures。 So first。

Let's go ahead and highlight oops。 That's the eraser。

 Let's go ahead and highlight that each of them has a unique entry function。 or sorry。

 unique entry block。 Just the one， right， We're only going see what of those。

 What else seems to be unique well。Wexing。Unique exit。Okay， looks good。What else is happening on？

 It seems like the rest of the control flow is going between these。And basically， at this point。

 we have represented all of the components of I our I R。

 This is the representation that we're going use。 So for our next optimization。

You could also imagine doing constant folding here， right。

 so we could keep track of which temporaries are constants。

 and then we could keep track of all the operations that are only using constants。

 that kind of thing。But there are other optimizations that could also make sense to do here。

 So we're not talking about register allocation yet， but we're about to。

 But what if we were going to do something like dead code elimination。

 So dead code elimination is this idea of if something is never going to run， right。

 If we know if we can prove that it's never going to run。

That we could actually go ahead and just remove it from the program。 So for the。

 the programs that I'm showing here， we don't actually have any dead code。

 But I want you to go ahead。And discuss with folks nearby。

 what might we see is true about a control flow graph that would cause us。

To decide to eliminate some good code。Go ahead and discuss nearby。Alright。

 what's a shape that we could have that would make us think。

 Look like this is something we could eliminate。I'll go ahead and draw us something。

 and then we can see if that helps us with our brainstorming。 So stay we have。This situation。

That says entry， despite my bad penmanship。Go ahead and discuss with folks nearby。Allright。

 what do we think。We like it all。 Don't eliminate any of it。So the context here is。

 say we are going ahead and compiling a particular function， right， And we see， O。

 It looks like we've got the entry showing up。O， right here。

 we've got the exit showing up right here。We do have some other basic blocks in between， right。

 in the interim。But then we also end up with this other disconnected thing， right。

 It doesn't seem like we ever jumped to that。 That's a case where weve found some dead code， right。

 So we can go ahead and say， nope， that doesn't seem to ever get jumped to。

 That's an example of dead code。 And we should go ahead and eliminate it。

 So if we were gonna learn more about dead code elimination。

 This is the intermediate representation we would use for that。

 And that is how we would actually do this reasoning。 right， We could do the thing of saying， okay。

 let's traverse starting from the entry point and see what we hit and what we don't hit。

So that's how we do dead code elimination。But there is another optimization that is the one that has actually brought us here today。

 So let's go ahead。And look back once more at our first introduction to basic blocks。

So there's one thing that we've already thought about that seems to really be missing from here。

 right， So this is not much more low level than our A S T。 Well。

 maybe it is much more low level than our A S T。 Certainly。

 it's closer to instructions than it is to our A S Ts。

It's not abstracting away quite as much as when we are actually doing our， our full compilation。

 but it's definitely abstracting away one big thing compared to assembly。 right。

 So we've talked about that in the assembly， we were always went to the stack when we were binding variables。

 what we always sort of knew what we were gonna be doing when we were interacting with particular registers。

 particular elements of the stack。 And here instead。

 we are just acting as though we have this infinite supply of these temporaries。

And so what are we gonna do once we actually hit the point of wanting to produce the instructions。

 Well， it turns out all we're gonna need to do。Or at least close to all we're gonna need to do in order to turn this into actual assembly instructions。

Is figure out， where should I store。These various temporaries， right。

 Which register or which slot on the stack should I use for each of these。

 So we're not actually going have time to dive into it today。

 But what we're gonna to be dealing with on Tuesday is thinking about register allocation。

 which is exactly this process。 say over here， we have our list of registers that it's available。

 right。We have some number of those， and how can I go ahead and make the mapping from these registers to these temporaries in a way that is safe that will prevent us from collaborating things that will also allow us to try to keep as many things in registers and off of memory as we possibly can。

So that's what we're going to be thinking。Questions about optimizations。

 intermediate representations。Anything in that general space before we call it for the day。

It's a quiet day。 That's right。 I'll hang out up here。 If you' all have questions。

 feel free to come up。And I'll see you all on Tuesday。Hello， hello。Situations where。Oh yeah。

 there any examples of where we want to like。Definitely。

 so we would rarely say we have already figured out a particular computation。

 like the output of a particular computation， right， We're not gonna be in a situation where we。

 the compiler， are going to throw away that result and not pop it into the compiler。

 But we are certainly going to choose sometimes to not run particular analyses to not run particular optimization passes to not do sort of the work of figuring out what would be the faster version of this program。

 So we may choose just to not even explore that。 And usually。

 so you if you think about some of the compilers you've used in the past。

 you might have noticed that some of them have different levels of optimization setting。

 So you can set it to not too many optimizations run。 Many optimizations run。

 And usually the reason why you would choose to do that is say you are in the development process。

 right， you are trying to iterate really quickly， get some results really quickly figure out if your program is working。

看。Sorry。Oh par me， when you're in that situation， you're thinking， you know what。

 I don't need this to be the fastest， most performant version of this program。

 I just want the quick compile cycle， right like like development versus a production exactly。

 And then once you're satisfied， you're ready to ship it。

 you are expecting this program to run a million times。

 then you turn it all the way up to the highest level of optimization。 But in the inter。

 you didn't really need that。 you were just trying to get a correctness。

 You were trying to iterate on things until you were satisfied with them。

 And then you were ready to actually do the fast version。 Does that sense。😊，是不是。

What you wrote on one of the slides。 Yeah， which one。About， about the control flow。No。

I think this was a bit after。About this one。 Yeah， oh， this is called the back edge。

 Oh Sorry about my bad handwriting。 It is dreadful。Oh， dear， Yeah， let me。

Let me try to make it a little clearer。And also， just to confirm that when you say class。なん的。

We have class on Tuesday， don't we。Well like it is next week is Thanksgiving。Yeah。

 but we have class on Tuesday。 We just don't have it on Wednesday。Am I making this up？ This is real。

So you know。We never have class。No， but we're a Tuesday Thursday class。哦哦。I'm right， right。 O， Oh。

 you had me panicked for a moment there。 Oh， O。😊，All right， cool。法兰达。Yes， let me pull back up that。

楼续卡。I would call that the input language， or sometimes it's called the source language。

 And then the language that you're actually compiling to is typically called either the target language or the output language。

So let's see。 So let me add a couple more of the labels on here， right。

 because we're kind of mixing together the things that are going between the stages and the things that actually are the stages。

 right， So here we have our code gen and here we have our asmbler linker， right。

And so the things that are actually part of the compiler。R。Theses， right。

 those are the things that together constitute the compiler。

 And then these other things are actually just equivalent representations of a program that we are passing around。

 right， So all of these are just equivalent representations of the same input program。 Now。

 only one of those is expressed in。What we see as sort of the language， right？

 So this would have been represented expressed。In input language。



![](img/61ade704665d282a7d90a2f85fdae687_8.png)

Source。And this is expressed。嗯。In output。Or target。Language。Does that make sense。Yeah。

 different people call it different things。 Some people do also call that codegen。

 So this could be called。So again because basically。

 you just saw that I R that really looks quite a lot like assembled instructions， right。

 like assembly instructions。 And so in order to get from this representation to that representation。

Do something that looks an awful lot like Cogen。 So usually that's what you would call。

 Some people just call it a transformation or a set of rewrite rules。 But I would call it codegen。

Some people will go ahead and treat C as though as an I R， right。

 So usually probably what we would say in that case。

 because we wouldn't be running the assembly link right， All of that would be left to C。

 So that would be a case where we're basically leaving off at C is the instructions and we're going ahead and passing it off to that compiler。

Yeah， in general， if it is a program transforming from a runable sorry if it's a program transforming from one representation of a program to an equivalent program in another language。

 whether that is assembly language， whether that is another like you might have heard of source to source compilers right。

 So you could do a compiler that you know， compiles from C to jascript。 There's nothing stopping you。

 So all of those would still be called compilers， even though you know it it's a little different from what we've been doing。

 So。Did you say that the front。It's reasonable。 Yeah。

 so the line between sort of a program transformation and a compiler is fuzzy。In general。

 we don't have anything that can run an intermediate representation。Again。

 a lot of these lines are fuzzy， but if what you have at the， at sort of the the middle stage here。

Is not runnable without an additional transformation stage。

 We would probably call it a front end rather than calling it a full compiler。But again， it is fuzzy。

 It's totally fuzzy， yeah。当长。

![](img/61ade704665d282a7d90a2f85fdae687_10.png)