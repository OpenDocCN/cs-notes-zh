# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p24 -P24-Lec 23 - Optimization.zh_en -BV1zQ27BeEfF_p24-

![](img/8ccb05a131cb5ff834169d558701714a_0.png)

Alright， hello， everybody。 Happy Thursday。 Its Thursday， right。😊，Happy Thursday。

 we have an odd dim classroom today who can say why the lighting gods did not bless us， so goess。

A couple of quick logistics things before we dive in exciting logistics things。

 So next Tuesday is still officially a class day， even though it is the week of Thanksgiving。

 And so we do have official class stuff。 there will be sort of the normal lecture which I will post to the B courses as usual。

 but if you are here in person。 we have a special event for you， which is our own David Ka。

 which is to say y'all's GSI is's going to come in and give an in-person lecture that's a bit of a sort of critical history of PL。

 a bit of a sort of brainstorming session on how programming languages might connect to your values and your goals in life。

 and I think it's going to be a really good time。 So I encourage you all to show up。😊。

And then the Tuesday after that， I have a student who is going to be a computer science professor very soon。

 but who is still currently a PhD student and is working on this very cool like teaching certificate for someone who's going really hard on trying to figure out how to teach computer science。

 And so the Tuesday after we all get back from break。

 I'm going also be here because one part of this certificate is I'm also sort of in the audience and being like。

 oh， here's how you could change this to make the teaching even better。 but he's a great speaker。

 he's a great lecture。 He's a great teacher。 And I think y'all will really enjoy。

 he's gonna to teach us type checking。😊，And so that's going to be more sort of back in the usual flow of our content。

 and I think it's going to be a blast， Justin is great。嗯。

Are there questions about these two sort of wacky sessions that we've got coming up？

We feel pretty normal about those。Cool， in that case， we have some exciting。

 exciting content for us today。 you might be thinking to yourself。 okay， last session。

 we finished those first class functions。 We're done with that。

 We clearly have implemented a fully operational， functional programming language。 We're done。

 What are we still doing here。 Why are we still doing 164。 You may， of course。

 have a guess based on what I have put up here on on our little whiteboard。

 but it turns out there are some optional things that we can do to our language implementations that are not just about adding more language features。

 adding more language features， adding more language features。

 And so that's what we are gonna be turning today。 We are going to be starting to talk about optimization which will be our topic for basically two sessions。

 and it will be the topic of y'all's last homework。😊。

So I'm going to start by taking an opportunity to do my brief rant on the term optimization。

 We are going to use the term optimization because we like to fit in。 You know。

 we like to be like the other cool kids in programming languages， however。😊。

If you take a look at sort of what we're doing， this program to program transformation。

 where we are trying to sort of make the program better。

 Do we have any definition in our head of what would make the output program optimal。Yeah。😊。

I like it， so we could certainly have a definition of what would make the program better。

So would it be maybe the fewist instructions would be yeah。 So there is， in fact。

 a part of optimization land that has expressly concerns itself with creating sort of narrow definitions of what is going to be optimal and then searching in a space of possible programs for what is the program that is going to meet that optimal definition and we had to come up with a special term for that。

 And that it's called super optimization。 So we do have a part of optimization land that does actually say。

 okay， I'm going make this particular definition of optimality。

 And then I'm going to do some kind of process that actually guarantees me that definition of optimality。

 And we have to come up with a special term for that because the things that we normally mean when we talked about optimization in programming languages and compilers land is things that are going to preserve meeting make the program better。

 but are not necessarily going to meet any given definition of optimal。

 And so we are going go ahead and adapt that same terminology of calling it an optimizer calling what we are doing optimization。

😊，But I just want to sort of give that little asterisk there that this is not to say that we are actually moving ourselves towards some definition of optimal that we are actually going to achieve here。

Hopefully we're kind of comfy with that general idea。Ku。Okay。

 so now let's do a little bit of a brainstorming activity。

 I think your answer is actually a great start on this。

 So I'd like us to think about what we might mean when we say， make a program better。

 So go ahead and take 40，50 seconds。 chat with someone nearby。

 What could we do to make our programs better。😊，All right， yell him out for me， what are we thinking？

Runs faster。 Well， okay， yeah， let's actually， let's just call it faster because we could mean multiple different things there。

 So let's say faster。 And that might mean like， runs faster。On my computer。

Or maybe I actually mean better worst case。Wors， man am I spelling worst case？Asympttootic。

 did I spell that one， right， Maybe asymptotic execution time。Right。

Those are two very different things。 in fact， And in fact， often。

 if you look at sort of what theorists are， are typically doing when they get things that have better asymptotic worst case execution。

 that is actually something that magnifies the constant hugely。 such that for practical cases。

 we might actually prefer the thing that has worse asymptotic behavior。

 And so usually in optimization setting。 We're not actually going for that second definition。

 We're often going for that first definition。 So okay， faster。 I like it。 what else we got。Yeah。Okay。

 so I'm going to call that more effective。Use of hardware。

So a good example here would be a like better cash utilization， that kind of deal。 Yeah， love it。

What else we got？Yeah。I love it， energy。We're still honestly in man。

 my spelling is even worse today than normal。 We're still in honestly the early days of figuring out how to do low energy consumption。

 basically what we do at this point we say， okay， the CPU is the expensive thing right the processor or whatever that may be is the expensive thing that is happening inside our computation。

 and so we often end up using runtime as the proxy for energy usage， but yes。

 absolutely this is a huge thing that we want to be optimizing for。What else we got。Some other ideas。

That's okay。 I'll pop another couple in there。 So let's say lower memory consumption。

 This might have been what you actually meant。 I'm not sure if this is what you meant， but lower。

Memory footprint。I like that and again， this could mean multiple different things。

 so let's sort of draw some lines back up to here， this could mean like using less on my computer。

 this could mean I'm actually looking to have better worstcase asymptotic memory footprint。

 like either of those is a plausible thing that we might be going for。

I to add another couple of things， so let's add no redundant work。Obviously。

 this is pretty closely related again to faster， and so this is not necessarily something that needs to be called out separately。

 but it's something else that we might want to consider。

I'm going to have one more that we might actually care about so small program size。

This does not actually matter in every situation， but if we find ourselves in right like the program itself also has to live somewhere。

 if we find ourselves in a situation where we just don't have a lot of storage available。

 maybe we're running on a phone or something， maybe we end up caring about the size of the program itself。

 So these are some things that we might want to optimize。

We have questions about any of these or so far， so good。Okay， cool。

 And sometimes we'll actually be finding ourselves in the situation。

 having to trade off between these。 So this is something that we sort of have to keep thinking about what is better。

 according to our definition of better。Okay。I' going to throw out another couple of things that I'm not adding onto that list。

 but that we might actually think about when we think about what makes a program better。

 So I think often one of the things that we as we are sort of humans looking at programs。

 one of the things we might often say makes a program better is if it is more readable that is not the kind of thing that our optimizers are going to be working on for us we are not expecting that for the most part。

 right there are certainly there source to source compilers or transpirs where we might be expecting that a human is going to read the thing that comes out the other side。

 and in that situation， okay， maybe we are actually interested in readability and maybe we do care about making our cogeneration phase actually do something to enforce readability。

 probably would not say that that is the job of the optimizer。

 probably we would just consider that part of the overall structure of the transpir but in general。

 when we are thinking about what counts as an optimizer in programming languages and compilers' land。

 we are normally not thinking about something that is going to improve readability。

Another thing that we're not actually going be taking into account here that we might all think makes a program better is correctness right so if we take a look at item number one right here。

 preserve meaning that means if we get a buggy program in。

 we better put a buggy program out right we are not going to be making our programs more correct during the course of optimization So those are a couple of things that we might think of as things that make a program better that we are actually not going to be tackling an optimization land。

So far so good。Lovely， okay， well。That's our intro to the overall ideas。

 I now want to start thinking about where in the compiler we put this。

RightWe've had this image that we've had in our heads this whole time。 Okay， we're going to go ahead。

 We're going to have the Lexer or tokenizer。 We're going to have the parser。

 We're going to have codegen。We're going to have the asmbler and linker。

Right and we've been able to hook together all those components and that has been sufficient， right。

 we have gone through this process this whole time and been able to get from source code to binary。

 We have done all of those sort of required things in order to get a program at the other end。

 So where exactly does the optimizer fit in this picture。😊。

It turns out that actually we can put it in a bunch of different places depending on what kinds of optimizations that we are doing。

 so we are mostly going to be talking about optimizations that happen once we have converted into an AST representation。

And normally， this will look like， okay， I have a bunch of different optimizations that I can run。

 and they are going to help us convert from one version of the As T to another version of the AS T to another version。

 so this would be opt1。😊，And then we might run Ops  two。And then Op three。And throughout that。

 all that we're actually doing is transforming the AST into a version of the AST that we expect once we run it through cogeneration is going to actually produce a fewer instructions or instructions that are going to run faster or whatever it is that we're thinking about。

Another place where we might choose to introduce an optimization is at the instruction level。

 So if you've ever heard of peoplehole optimization。

This is basically the idea of I'm going to go ahead and look at a particular window of instructions or a particular peoplehole and I'm going to try to find a shorter set of instructions or a set of instructions that has sort of a lower cost estimate some sort of idea I have of what would be a better set of instructions that I can replace that particular people with that is going to make my overall program faster and so for example in X86 land the move instruction is oddly powerful。

 and so I might be able to figure out that a particular move followed by a particular ad I could maybe just replace with just one move that would be an example of peoplehole optimization。

Feeling kind of okay so far about these overall ideas。We are mostly going to be focusing on。

This zone， rather than on people optimization land。Okay， cool。

So this is where optimization is happening。We are going to have to think about some tradeoffs。

 So I think one of the things that I mentioned right up here was this small program size。

 Often we are actually going to have to trade off program size with performance。

 And so if we're in a situation where there's a 10 instruction program versus a 20 instruction program。

 and the performance differences are dramatic。 Okay， great。

 we probably take the 20 instruction program， another 10 instruction， no big deal。

 But if we are going to have to blow up that program size to a million times its' original size。

 and we're only getting a 1% improvement in performance。 Okay。

 we're probably not at that stage willing to make that transformation。

 So this is starting to help us think about the idea that some of these optimizations， right。

 looking here， we might sometimes want to apply them。 and sometimes not。And in fact。

 it's even a little more complicated than that in that it's not necessarily clear what order we should apply these in。

 right， sometimes I might do a process where I apply optimization1 and then suddenly optimization2 is actually able to fire whereas previously what was not。

And so we might ask ourselves， what is the right order in which to run the various rewrite rules of various transformations that we could run in optimization。

 And this turns out to be one of the big， longstanding， extremely open questions in。

Optimization land and in fact in compilers land writ large。

 So this is called the phase ordering problem。 And the truth is we still don't really know what is the right answer here。

 So if you take a gradlevel compilers class， there's a solid chance that you're going to spend that entire compilers class just learning about optimizations because there's still so much work to do here we've actually only just recently started having some really exciting work that's starting to try to tackle this。

 including by new professor here at Berkeley Max Willsey。

 who is working on something that might help us tackle the phase ordering problem。

 which is basically the idea of representing a bunch of equivalent programs all at once in a fairly compact data structure。

 representing a bunch of transformations that we can do and basically in parallel making all of those transformations to all of those equivalent programs at once。

 again， reflecting them all in that exact same compact data structure and then at the end of this process after you've developed the full e graph it's called after you've developed。

EGra， you could then at that point go ahead and extract out whatever you think is the lowest cost version of that program。

 And that's sort of the best break we've had in decades on how we should tackle this phase ordering problem。

 which has just remained open for so long。So this is basically to give you this insight that a lot of what people are doing in optimization land is kind of based on benchmarking。

 We don't necessarily have this beautiful， formal， satisfying solution。

 which is a little weird when we spent this entire programming languages class， okay。

 we have to think about correctness very carefully and we have all of these sort of definitions of what it means to be correct that are very well formalized and now suddenly we're in the situation where we are throwing in some programs and we're seeing if they get better。

And that's kind of realistically what people are actually doing to develop optimizers these days。

 and so in fact， that is also what y'all are going to be doing for your optimization homework is we're going to be asking you to put in a bunch of benchmarks that might show whether our optimizations are actually helping us achieve better performance。

Okay， so that's the phase ordering problem。 is basically just to say。

 optimization is big and messy and complicated， and there are still huge problems to solve here。Okay。

So we are going to go ahead and focus probably around here。

start us off with one of these optimizations so we are actually going to talk about basically three different optimizations。

 although， of course we can apply them repeatedly， but I'm going to start us off with one of them。

 So let's take a look at well， in fact， let's not even take a look at a program。

 let's just think about the fact that sometimes we're going along we're writing a program and we know that we could just sub in a constant we know that we could just put in let's say we've got something we know a process is going run for x minutes and know how many seconds there are in a minute we know how many milliseconds there are in a second and we could just go ahead and do all that multiplication in a calculator and put that number into the program。

 but it is actually a lot clearer a lot more readable if we go ahead and just put that multiplication we give those nice names to those items and then we actually put that multiplication right there in the program that's going to make it a lot clearer to us later when we go back and look what that number actually is。

 And so we do actually want to allow programmers。Do this thing of multiplying constants。

 adding constants， doing various things with constants in their programs。And nevertheless。

 when the programmer has done that， we might prefer if that multiplication of that edition。

 whatever it may be， doesn't have to happen every single time we run the program。

And so we do have an optimization that lets us handle exactly this， which is called constant folding。

 It is basically saying we're doing a fixed computation with some fixed constants。

 let's just do that at compile time so that we don't need to do it at runtime。

 And so let's go ahead and actually start implementing this。

So here we are back in our usual compiler。

![](img/8ccb05a131cb5ff834169d558701714a_2.png)

And we can see that let's actually run one of our programs。What shall we actually run？Let's run。

Print。Add 1，5。So okay， we're getting the correct answer out right。

 our non- optimizeimized compiler gives us six， but if we take a look at our program。

 we're seeing that what's happening here is we're going ahead and putting that representation of 5 into RAX and then down the line we're going ahead and actually adding one to it。

 I would like this program better， I would consider it to have been more optimized if we just went ahead and directly went to putting 24 in there to represent6 right off the back。

So let's go ahead and implement constant folding in order to do that。

 So let's make ourselves a new file。And what shall we call it， Let's actually call it。

 let's just call it constant folding。Great。We'll open our AS T library that lets us play around with the AS Ts and let's make ourselves a new function。

 So this is going to go ahead and take in an expression and put out an expression right。

 remember we talked about the fact that we are often doing AS T to AS T transformations。

 That's exactly what we're going to be doing right here。

What do we actually want to have happen in there。 Well。

 let's say that I'm trying to tackle this program that we just talked about。

 I think probably I'm going to be thinking about that add one primitive that we have。

 So let's go ahead。Tackle Pri1。Add one， numb， and。And if I see that situation， right。

 I can go ahead and just do that edition right now。 So let's do that。So far， so good now。

It is important that we not change the meaning of the program， right， We talked about two things。

 We want to make things faster。 We want to make things more performance。 We want to make them better。

 and we want to make sure we are not changing the meaning of the program。

 So if I encounter anything else， let me just leave it the same。

So let's go ahead and say anything else？Fantastic， leave it the same。Okay。

 I'm going go ahead and add this into it。 No， not you2。 Let's add this into our compiler。

 Let's go ahead and make ourselves a little helper function。

 That's just going to apply this to our program。 And then we'll go ahead and actually call that in here somewhere。

 Y， right around here。 So let's make our little helper function。Let's see what shall we call it。

 let's call it F program。Remember that this optimization is called constant folding。

 so that's why we're calling this fold。 So fold program will apply it to probe。Program。

And what do we need to do in there Well， we just want to apply it to all of our definitions。

 So it's not really anything particularly fancy。 but if we've got the body。

We're going to go ahead and make sure that we can actually do that folding。Fold probegue do body。

 That's the main thing that we're changing。 And then for all of the definitions。

 we want to do the exact same thing。 So defens equals and we'll do list dot map。

So if we get in a definition that has a name， that has arguments， that has the body。

 we have a couple extra things that got added in order to support those extensions to first class functions that I mentioned。

 we've got the top level。Got the offset。 We're going to go ahead and change very， very little here。

 The only thing we really want to change is we want to make sure to call fold on the body。

 So name args body。F。Body。And then。Top level。Offet。And we want to call this on pro defens。Okay。

So far， so good。 Have I mistaken something here。 No， that's mine。 great。 Okay， great。

 So let's go ahead and use this inside compile do M L。Specifically。

 we're just going want to actually call this helper。 So let probegue equals。😊，Constant folding。

 right， that's just the name of our new thing dot fold program。Program， program in。

The following so okay。We have done the thing we want to do， oops。What did I get wrong。

 did I fail to save this， let's make sure that it's saved Sa again。No， we shouldn't need to。

 We should be good to go。 Oh， I misspelled it。 Constant folding。 That'll be it， great。Okay。

 so now I'm about to run it on a program that it is not going to successfully optimize。

 And I want you to think about why is it not going to successfully optimize。

 And I will show us our implementation to help us think about it。So okay。

 let's go ahead and look at programme do S。 I'm still seeing that 20。

 I'm still seeing that we're adding one。That's kind of unsatisfying。 What's going on here。

 Go ahead and discuss with folks nearby for half a minute。 Why didn't it optimize。Alright。

 so I'm hearing it in the audience。 folks are basically saying， hey， if you did this， it would work。

 right， we are just looking for seeing that and that alone and otherwise we just sort of call it。

 so let's see if that doesn't indeed work。Okay， well， it's not going to print out right。

 but that's fine。 We can look at the program。 Hey， we have our first optimized program。

 There's 24 right baked into the assembly。 But okay。

 it's a little unsatisfying that we're not always gonna going get the behavior we want if we've got it sort of somewhere else in the program if it's not right up there at the top。

 So what about if we do something like this。Go ahead and discuss with folks nearby。

 is this going to be optimized？Make your prediction in 20 seconds or less。Alright。

 I'm hearing folks say exactly the problem， which is， hey。

 we're only going go ahead and do this match。 If we're seeing a number right there。 and this addd 1。

5， I mean， that's an expression that we know is eventually going to produce a number。

 but it is not itself just a number literal。 So if we go ahead and we actually run this。

 We can go ahead and see We're right back to where we started。 We're doing the additions。

 We haven't baked in that number at all。 So frustrating。 Let's change it。

 So here we go inside constant folding。The first thing we're going to want to do is let's go ahead and make this recursive。

 not too surprising， probably at this stage in the class。But what we want to do， well。

 we want to go ahead and figure out what to do with E。

 So let's decide based on what we get back when we actually apply fold to E。So here we go。

 we've got E， let's match。Sorry， let's in fact。Call fold on it。 Let E equals fold E in。

 And now let's go ahead and do our match E with。 And if we see that numb， fantastic， great， If not。

 we're going to have to do something else。 So numb N fantastic， let's make numb n plus1。

 If we get anything else。😊，We don't know what to do， right。

 We don't have any idea for how to optimize this because we didn't get back a number from whatever else we did on the subree that is related to E。

 So， okay， that's fine。 We basically just have to recreate that exact same A S T that we had before。

 And so that's exactly what we're gonna do。 Let's do。Prim 1。Add1， E。

And that is going to go ahead and do what we need。 Now。

 we might still have done some constant folding inside this new version of E。 right。

 So maybe there were some children inside that tree where we did actually， you know。

 do that recursive call to fold。 And then maybe we ended up doing that。 But at some point。

 we must have hit something。Where we had to call it and we didn't get a number back。 So okay。

 let's see if this at least fixes the， the most recent case we tried where we had an add one nested inside and add one。

And let's look at our program us。 Hey， we've got it。 Okay， so we're getting， we're getting closer。

 now we're not quite there yet， as you probably guessed， what if I change this to sub1。

 chat with folks nearby 20 seconds。 How should I make this work。

And hopefully we've all come up with the idea that we should do something real similar to that。

 but we should make sure that we're doing our subtraction and that when we recreate it。

 if we don't know what to do to optimize， we're using our sub one。Okay， we've got that handled。Now。

 I would like us to get to the point where we can handle what we actually started with， right。

 We started with this print thing。And basically， it is really gonna be pretty straightforward。

 It's that we do have to actually traverse the whole tree。

 Even if the first thing we see is not actually gonna be something that we can optimize。

 So let's go ahead。 I'm gonna add in a case that might help you think about it。

 And I want you to come up with the change we're gonna have to make in order to specifically handle this program。

Go ahead and discuss with folks nearby for 40 seconds。This one is just to help you think about it。

Alright， so our solution really is gonna be pretty simple。

 It's just that we've got to traverse the whole thing。

 We've got to make sure we're applying fold everywhere。

 Even if the first thing that we're seeing is not actually optimizable。 fantastic， no problem。

 let's do it。 So we've got a primitive， we don't really care what specific primitive we're applying it to。

 we still want to make sure that whatever that operaand is whatever that operaand is that we're still going try to fold So let's go ahead。

 even though we have no idea how to optimize this particular primitive like for these two primitives。

 we do have an exact idea we can just go ahead and do the addition at compile time。

 We can do this traction at compile time for these two primitives。

 we have some ideas for this sort of ambiguous primitive that we're not even specifying which it is。

 we don't have any ideas。 but that's still totally fine。

 we can still totally make sure that at least those operaand that one operaand in this case since it's a unary operator。

 that one opera can still totally get constant fold。 So let's make sure that happens。

 let's recreate prim1 with the exact same thing。 But now with the fold on E。Fantastic。

 so I'm gonna go ahead and actually commit a slightly more complete version of this into the class compiler。

 So you can also see what it looks like for like just straight up edition and that kind of thing。

 But it's still not gonna be quite a complete implementation。 As you might guess。

 based on having read the homework。 But let's go ahead and see this work first。

 This is still the old version。😊，Let's just make sure that we're getting the thing we want when we actually do our print。

 So let's go ahead。And print this out。let's open compile。And then let's do it fabulous。

 We've got seven the output is correct， and we are seeing that value right there where we expect to see it。

okay， we are moving towards optimization。This is looking pretty promising。

 I do want us to zoom out a little bit and think a little more broadly about when it is good to apply constant folding when we're actually going gain from it。

 So let's swap back over to oh well， you know what。

 let's take our five minute break first and then we'll switch over into thinking about our optimizations more abstractly。

 So let's come back together at 421。 I will see you soon。All right。

 let's start with a couple reflection questions。So I have pulled up on our screen。

APart part of Inter。ml。That might look kind of。I mean， you can see that if I， you know。

 I call Inter X。On my you know argument to add one。 and then I find out， okay， I've got a number。

 then it seems like I can do n plus one and make a new number with that and sort of the same deal over here with sub1。

 And if we take a look over a constant folding over here， wow。

 it does kind of look similar to what's happening when we're doing constant folding for add one and sub1 So I want you to discuss for about a minute。

 what is the relationship between constant folding and interpretation。

So here are some things I think about when I think about this question。

One is getting input from the outside world。If I'm running my interpreter。And my program says。

 go check this database for inputs， or it says， go check what time it is right now or go get some input from the user。

 right？The interpreter is running the program。 It can do that If my compiler midway through compiling my program is like。

 give me your user input， what are you talking about， You are compiling this program。

 There's this whole separate phase where we're running the program。

 you can ask me for input then you're not supposed to ask me for input at this right and in particular。

 we might want to then run that program on a bunch of different inputs right So we do actually have this difference where we are only able to do this constant folding when we know at compile time。

 not at runtime， at compile time， What are the values that we're actually operating on。

Right so that's a big thing。 Another big thing for us to think about here is nontermination right We actually write a ton of programs that are not intended to terminate a web server。

 you know any kind of thing where it should keep going until the user says to stop right there are all kinds of things where we're just expecting the program kind of keep going and keep accepting input if my compiler starts running my interpretationer right in order to try to find the output and Ive written a non-terinating program I'm pretty mad when a compiler just hangs there right and I never get a program back So this isn't to say that there's no relationship between these two。

 clearly a lot of the same things that were doing in interpretation land。

 we are also doing in constant folding land but they are actually a little bit different I just wanted to sort of highlight both the similarities and the ways that they might not quite align。

😊，So okay， we're only doing our constant folding on things that we actually know about economic and time。

 relatedly， I want you to go ahead and take a look at。This。

Particular program right here and discuss with someone nearby for half a minute。

 what AST will we produce for this， given our current implementation bless you。

 given our current implementation of constant folding。Okay。

 go ahead and hum if you think we can simplify the A S T for this。Go ahead and hum。

 if you think we cannot。Yeah， I agree， right。 We just don't know what that value is that we're going to get out at runtime。

 And so at least the way our constant folding is implemented right now。

 we don't have any idea what to do here， right we never hit that situation where that argument that opera around is a number right It is just going to be that expression that represents getting a number from the user and so we're not actually going be able to use this implementation of constant folding in order to deal with this in order to optimize this。

 We'll still get a correct answer out。 We'll still be able to run this program right the entire time。

 this entire class， the whole semester that we've been doing this。

 We've been getting out the right answers， right so it's not that we need the optimizer in order to get correct answers。

 This is all fully optional。 we can always fall back on the old thing we've been doing。

So we'll still get the right answer out， but we won't be able to actually simplify this one。

Questions about that， or that feels okay。哎。Yeah。Oh， sure。 In fact， we could even go deeper than that。

 right， We could say， okay， if we have any number of ad ones and any number of sub ones。

 we could collapse all of that into a single addition or subtraction based on doing the analysis。

 Yes， yes， there are all kinds of optimizations that we can choose implement。

 We are only gonna learn just the tiny fraction of optimizations that are out there。 Again。

 It's a whole big wide world。 We're basically gonna be learning patterns like the generalization that you just did right in the same way that constant folding。

 We can imagine generalizing it to that。 right， We're gonna be learning these patterns that we can reuse in all kinds of different ways。

 Yeah， Great question。😊，Okay，One last thing I want to reflect on。

 I won't actually have us discuss it because there there's at least one more optimization I want to get to today。

 One thing that I want us to think about is the fact that we sometimes want our compiler to run a long time and then give us a really fast program。

 and sometimes we want our compiler to run pretty quick and we might not care as much about whether the program that we get out the other end is fast。

 So there are times that we are willing to just poor time and time and time and time into compilation and maybe we want to do all the constant folding that we can possibly come up with to do maybe we choose to just run every single optimization so you've probably worked with production compilers that have different optimization levels and the common pattern is that if you're in the middle of developing right now and you just want to real quick get something compiled so you can keep working on it。

 okay probably you're gonna run with not too many optimizations on you're probably trying to get the compiler to run quickly so you have that fast feedback loop you can then run the thing。

 You don't care if the thing runs super quickly。Whereas if you've been developing this for however long and now you're ready to send general production and it's going to run a million or hundreds of millions of times。

 probably at that stage， you're happy for your compiler to take a ton of time and just pile in every single optimization。

 however expensive however long it's going to take the compiler to do it just go wild and we're going to expect to get out the best possible version that we can get with our compiler。

😊，Basically， there's no one true answer again between when do we want to do that trade off between how long the program is going to take and how long the compiler is going to take。

 but I do want to sort of highlight for us that it is going to vary based on what state of the development process we're at。

Questions about that。Cool in that case， let's go ahead and think about when we want to apply constant folding and when we can safely apply constant folding。

 So this is something I'm gonna to have us actually discuss in our groups And basically。

 there are those two things that I said that optimizations need to do。

 they need to preserve meaning and they make need to make the program better。

 So we are thinking about exactly those two questions here， right。

 So when I say preserve meaning I'm thinking about when it is， is it safe to apply this optimization。

 right， When can we apply this optimization safely。



![](img/8ccb05a131cb5ff834169d558701714a_4.png)

And when I'm talking about making the program better I'm thinking about when should we， right。

 when am I expecting to actually get out a better program if I do this and now that y'all have just seen constant folding actually implemented。

 I think you're in a perfect position to answer these two questions。

 let's go ahead and start by spending a minute discussing the first one。

we're answering it specifically for constant folding， not for optimizationrit large。Alright。

 so hopefully we're feeling pretty comfy about this after our。Chat already， when we can statically。

 meaning at compile time， determine。The value。Of a。Soub。Expresssure。

That's the situation where we can safely。Do this optimization。So our next question for you。

 so are other questions about that？Yeah。ずっとし。User input would be an example of a situation when we will not statically know the value of a particular sub expressionpression。

 right， the subexpression that either is the user input or relies on knowing the user input that would be one way that we might end up getting。

 but it doesn't have to be user input right It can be calling out to a database that can be you know going and finding out what the weather is today right There's any number of things that might be happening that is going to represent getting values that we aren't going to know a compile time。

Make sense。Oh， I love this question。 Hol this question for。

 I don't remember if we going to get this session or next session。 great question。Okay。

 so let's now take， honestly， let's only take like half a minute on this question number two here。

 I think this is going to be a pretty easy answer。Again， this question is about。

You know number two here， right， so this is about when do we think this is going to actually make the program better？

Okay， hum， if you think that every time we can safely apply it。

 this is going to make the program better。H， if you think there are exceptions？Fascinating。

 this is always going to make the program better if we can do this without changing the meaning of the program。

 we always want to do this。RightSo this is one of those early and often things。 Actually。

 every industrial compiler that I'm aware of does this constantly。 It's cheap。

 It just takes one traversal of the ESt。 It can save you a ton of computation。 So you go off。

 you do your other optimizations。 you see if that's unlocked more constant folding that you can do do another optimization。

 You come back， you do constant folding again。 you're just constantly cycling through constant folding。

 you want to be doing constant folding。 This may not always be the case though for other optimizations as we will soon see。

 So for others， we might not want to apply them every time either because it might not actually make the program better or it might just not be worth it。

 but this one is cheap， and it makes the program faster。 We want to apply this one。

So I'm going to have us take a look at this program next and if you take a look at this program。

 I think you'll see that applying constant folding would not make this program any better right there's no way for me to sort of go look at this and say。

 oh yeah there's some constant folding I can do here that will make it faster What I want you to do I've tried to structure this program in a way that is going to suggest a particular optimization to you if you were to manually optimize this program。

What about you do？

![](img/8ccb05a131cb5ff834169d558701714a_6.png)

All right， so here's that same program。Im going to just manually do an optimization you all might have come up with。

 right， So here I am。 I'm looking at this。 I'm thinking， function calls are expensive。

I would prefer if we didn't have to do a function call in order to accomplish this program。

 Let me copy this program and make a variant where I don't have to do a function call。

 So in particular， it looks to me as though I've got this sort of read numb。 that's going to be X。

 So let me do something like let。X， let's make that be readum。

Let me see if I can get my perenssite great and then the body should just be this plus x2 right that's the one I'm actually expecting to have appearing there。

 so let's go ahead and put that inside and now this is basically that replacement for this call to F with one read nu input。

And I can do this exact same thing again to replace this other call。let's get rid of that again。

 and now I don't even need this function definition anymore。

I can go ahead and just do this entire thing with no function calls。

 no extra sort of function definition code ranging around， right。

 I still want the programmer to be able to write in this style。 right。

 my code that I write is littered constantly with these teeny， tiny little functions。

 They have a useful name， it reminds me what I'm doing right。

 It's modeling something about the underlying process that I'm actually trying to accomplish。

 So it's very useful to me to write these teeny tiny little helper functions。

 we still want the programmer to be able to do it。 but we don't want it to be super expensive。

 maybe the compiler can take care of that for us and do exactly the transformation that I just did。

 in fact， the compiler can right So if you've ever heard of inlining or function inlining。

 that is this optimization。 It's just saying， okay。

 let's go ahead and will make these names that reference those arguments， right。

 and then we'll go ahead and use them just as though the body of the function appeared in line。

 Thus the name in liing。😊，Questions about。This optimization。Okay， cool。So in that case。

 I'm going to go ahead and have us think about。😊，This program。

 and what I want you to discuss with folks nearby is can we apply function inlining to this program。

 Itll just be our yes or no question， discuss。All right。

 go ahead and a hum if you think we can apply in line to this program。

Go ahead and hum if you think we cannot。Great， I totally agree。

 So this is totally fine for us to apply in liing to。 Yeah， we'll sort of have to do it， you know。

 with this call。 we'll go into there。 this call will go there right Like we sort of have this two phasese thing going on。

 We could do with the other direction。 Also that's totally fine。 So it's a little bit wacky。

 And it certainly is going to start to blow up the code size a little bit。

 So you will occasionally see production compilers that say， okay， you know what。

 we're only actually going to compile leaf functions right。

 so they don't themselves have function calls within， that is also fine。

 We can make our own decisions about what we want to do here。 But this is totally fine。

 We can absolutely apply inlinning to this program。😊，Questions about that， or we feel good。

Lo it okay， let's consider this program。Can we apply inlining to this program？

ImPart interested in whether we can inline map， just in case you are wondering。All right， Han。

 if you think， yes， let's apply in lining。H if you think no。if you think this is confusing。Yeah。

 so I think all of those answers would have been totally reasonable because， in fact， we sort of can。

 but we also sort of can't。 so we could absolutely inline map two times， three times。

 four times right say we are expecting that in reality these pairs that we're going to be applying to that the lists we're going to be using are going to be short most of the time。

 We might choose to apply inlining some number of times。

 basically unrolling those map calls some number of times and that would be totally fine right we get to avoid some function calls by doing that。

 However， say we tried to be aggressive about this and actually removed our map definition。

 say we unrolled it 100 times and we removed our map definition and then we got a list that was 103 items long。

😊，Suddenly then we're in trouble right so we can actually go ahead and say I'm going to unroll some number of times in order to avoid some number of calls。

 but without actually doing that aggressive thing of removing the function definition， sure， okay。

 no problem， but we cannot actually do the aggressive thing of saying yep。

 I am going to go ahead and remove math entirely。So this has given us a couple of things to think about as we try to answer our questions。

 are two key questions for when can we safely apply inlining and when do we expect inlining is actually going to help us so I want you to go ahead and discuss with folks nearby specifically question one I'm going to write down some of the things we've already talked about and I'm going to ask you to brainstorm some other things that might also actually make it unsafe for us to apply inlining。



![](img/8ccb05a131cb5ff834169d558701714a_8.png)

![](img/8ccb05a131cb5ff834169d558701714a_9.png)

Here's a function that might help us rather a program that might help us think about this。

 here's something we're going ahead and we're defining various names and then we say okay。

 if the user tells us that the readn that they're going give us a zero then we want to go ahead and have this function pointer available and that will get bound to a otherwise we want to have this function pointer available we' nowll bound to a and then later on we're gonna to actually call a and print out what we get back so say I run this and I produce zero I get one say do this and I do okay I'm going to go ahead and provide one is my input we get five this makes sense because either we're doing sort of the thing over here where we're adding2 and3 or we're doing the thing over here where we're doing one。

 but it's weird because there's only one call site。

This is the only place where I'm actually calling a function right here。

So go ahead and discuss with folks nearby what limitation might this suggest。



![](img/8ccb05a131cb5ff834169d558701714a_11.png)

Okay， so let's talk through。So the the first thing was the thing that I think is most straightforward here。

 No-recursive functions。 I think we're all pretty clear on that。 It's gonna be safe， right， go ahead。

 go for it。 recursive functions。 if we know how big those arguments are going be。

 we know exactly what's going to come out。 This is actually this is an extension of constant propagation So a constant function is a function where if it's applied to a given argument。

 it always produces the same output， not all functions are constant functions， but some are。

 So if our function calls read out of luck， don't do that。

 if we have some sort of randomness or whatever going on in there okay， no。

 but if it's a constant function applied to constant arguments， whatever all good。

 we can evaluate the function， we can put the result in right at compile time。But then we had that。

 that sample program that I showed you all a moment ago。

 And I hope one thing you noticed from that example is we don't always know。At compile time。

What function is being called， right？ When I put in 0， we called one function。 When I put in one。

 we called another function。 And that was both at that exact same call site。

So at a given call site where we might be trying to inline the body of a function。

 we're only going to be able to do that if we know what function is actually being called。Right。

 so let's go ahead and insist on statically。Kown。Functions。



![](img/8ccb05a131cb5ff834169d558701714a_13.png)

Right， so if we take a look right here again。We can see this is a situation where we do not have statically known functions。

 This A could be either that lambmbda or that Lambda。

 and we don't know and we won't know until runtime when the user puts in that readno answer。



![](img/8ccb05a131cb5ff834169d558701714a_15.png)

So this a could be either like if we tried to do inlining。

 we might be trying to sub X or we might be trying to sub y plus z。And we're not going to know。

So okay， that's one constraint。 There's actually another constraint also suggested by the same program。

 and that is we only know the closure at runtime right， so no free variables。



![](img/8ccb05a131cb5ff834169d558701714a_17.png)

Right。No free variables。 If we need a closure， the value of free variables is only actually known at runtime。

 Now at compile time。 when we are in liing， right， we're let binding the body。

 We're just going ahead and saying， okay， all of those names associated with the arguments。

 Let's go ahead and put those in there。 What about the things that are appearing in the closure。

 right。So if we have free variables， the body might not even be valid in the place where we are putting it。

 right， So sometimes the place where we would be putting it。



![](img/8ccb05a131cb5ff834169d558701714a_19.png)

might be in the place where those values are available。

 but say that we've got a being returned out of some function that had these let bindings and as popping out somewhere else。

 we don't have any guarantees that X， Y and Z are actually available to us。Right。

 so we have to go ahead and wait until run time when we are relying on closures。

 So free variables are gonna be。

![](img/8ccb05a131cb5ff834169d558701714a_21.png)

A big no for doing inlining。Okay， in the general case， closures might be out。

 There are sometimes we can get away with it。 And it's not to say you can never get away with it。

 but you'd have to do extra analyses to make sure。I want us to turn now， well， okay。

 do we have questions about this topic of when we can safely apply it or we're feeling cofy with that。

Yeah。The whole if statement into the print。Oh， there's no that we could do that。

 It would not be in liing because this is not actually a function。 right。

 You can see that the only functions that appear here are that and that this whole thing is not a function。

 So like definitely like there are other program transformations we can absolutely be doing。

 like there are all kinds of other optimizations。

![](img/8ccb05a131cb5ff834169d558701714a_23.png)

Does that make sense， Yeah， thumbs up。

![](img/8ccb05a131cb5ff834169d558701714a_25.png)

Okay， let's go ahead and start thinking about when we want to do this， Right。

 So when is this a good idea， When do we think this will make the program better。

 Let's turn to topic 2 right here。

![](img/8ccb05a131cb5ff834169d558701714a_27.png)

All right， what's one thing about a given function that I should be thinking about when I'm making the call about whether to inline it？

Feel free to yell it out。I love it。 We're trying to avoid making the program too big。

 And there's a couple of things that are going to go into exactly that decision， right。

 so number one is short functions， right， a short function， even if we repeat it， you know，3。

 four times。 Okay， great。 Like it's probably not making the program itself that much bigger。

 Short functions feels good。😊，Few static call sites， right。

 even if we are going to be hitting this piece of code a million times because it's in the middle of a loop or whatever。

 if we are only actually seeing it in one spot in the code， fantastic。

 that's gonna suggest that we're gonna be able to do this in liing without actually blowing up the program size too much。

 So okay， you。😊，Static。Call sites。 And that's really what it's going to come down to。 right。

 We're just trying to avoid function calls without making the program too big。

What we want to actually sort of target specifically in terms of program size blowup might vary a lot based on what we're trying to do。

 right， Say we are trying to create something that we're going be running on a phone。

We don't have a lot of space， we probably don't want the programs to be too big。

 maybe we're okay with just having a few extra calls in there。On the other hand。

 say we're inside a scientific computing situation。 We're going to run this on a supercomputer。

 and this is going to be running for months。 We really want it to be fast。

 We have a ton of space because it's a supercomputer。😊，Fantastic， let's do all the inlining。

 We can possibly throw out at。 We are probably going to go really hard on this this particular optimization。

 So that's the kind of trade offs that we're thinking about。 But overall。

 the the sort of decisions that we are making are going to be based on pretty much those two constraints。

 right， those two。😊，Things that we talk about right there because it's all about not trying to make the program too big。

This is a great time for questions about inlining， or else I'm going to have us brainstorm one last optimization before we call it for the day。

Alright， let's go ahead and brainstorm one last optimization。 I'm going to show us。 Well。

' show us on the screen here。Again， I think this program is probably going to suggest to you a particular optimization。

Go ahead and see what you can come up with。I don't think this is going give it away。

 but I'm going to write the name of the optimization on the slide。

 I think everyone's probably going to get it。All right。

 does anyone want to yell out what I should do to this program to make it run faster？Yeah。I love it。

And then。I love it。 So let's just pop in a new name that we're gonna to give for this expression that we can see ourselves using repeatedly。

 right， we can look down here and we can see that we've got this repeated repeated repeated。

 It seems like we're using that a bunch of times。 Let's just go ahead and give that a new name。

 Let's calculate it once。 We'll call it Y。 and that can be plus x2。With apologies。

We'll get the little trend down there and now instead of what we have in there right now。

 let's just use why， right？Fantastic now we have only had to calculate it once。

 even though it appeared three times in the original program。

 thus the name common sub expression elimination。So the lecture that I'm going to post for Tuesday。

 not the one that David is going to do live， but the one that I'm going to post for Tuesday is going to go over the rest of Common S expression elimination and answer our sort of two questions for it。

 when can we apply it safely， when do we want to apply it and then we'll also talk a little bit about intermediate representations but if you have any questions about optimizations or about common S expression elimination or whatever。

 I'm all ears。I hope you all have an awesome Thanksgiving break。Eat lots of good food。

There's going to be sort of the standard course content one， which I'm going to post。

 and then there's going to be a live one that is for like special in person experience。

 and that will be David's。That's the one that will happen here， so if you show up here。

 that's what's going to happen。question up。对个。我认该。Where are you。

Inpreting the program and just dumping the result with the compiler versus。

I think we discussed likequiers。A faster alternative to the interpreter。

I wouldn't say that a compiler is necessarily supposed to be a faster alternative to a interpreter。

 it is true that because we have more control over what code we emit。

As opposed to an interpreter where we are creating the interpreter in a language over which we probably don't have control。

 This may not be strictly true right， say I'm writing a rust interpreter in Ru。

 I actually have a lot of control over what the Ru interpreter does right so but yeah， in general。

 you might have more control over where the code that comes out is performant if you're writing a compiler compared to if you're writing an interpreter。

So that sort of gives us a lot of flexibility， but it's not necessarily to say that we always want the compiler to be faster than the interpreter。

 That's not something that we're trying to enforce。



![](img/8ccb05a131cb5ff834169d558701714a_29.png)

I think my。