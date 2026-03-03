# 哈佛大学《编译器｜Harvard COMPSCI 153 compilers 2023》中英字幕（claude-3.7-s p20 1699884900-Compliers_on_11_13_2023_(Mon).zh_en -BV14PAUejE98_p20-

A friendly reminder， if you haven't yet to do that， if you look on Ed。

 there'll be a host to that link that'll be clickable。As you know。

 homework 5 is out as of this morning， the files are on the Canvas homework page so you can download directly instead of needing to send an email or private message。

 you have two weeks to work on that。As of today。And homework six。

 the last homework is going to be out。A week from today， and it's going to be due December 5。

 So again， there's a overlap of homeworks。 So you need to think about managing your time there。

Remember， of course you have those up to three days worth of late minutes to use。

 so I encourage you to use that as well in your planning as well。

 feel free to reach out if you feel you're running short on late minutes。Yes。

Any questions on the admin side of things。Great， so today we're actually going to jump back。

 finish up the overview of some optimizations that we didn't get to last lecture。

 and then we're going to be looking at data flow analysis。 So let me without further ado just。😊。

Jump into。More of an overview of optimizations。 so we went through a whole bunch。

Getting an understanding for the different kinds of transformations that were needed。

 this idea that a although of the time it's heuristic。

 we're not exactly sure if it's going to actually improve performance or improve any of the other metrics。

That we want to。That we want to look at。Next optimization in this long list that we've been going through is loop unrolling the basic idea is that if you have a loop that has a loop body what we can do is replace the loop body by several copies of the loop body so that is for example。

 if this is our original loop I from zero to 100， we're doing some array operation here or rather summing up elements of an array。

What you could do is。Instead of having 100 iterations of this loop。

We have a new loop where the body of the loop now has two。Copies of the body of the loop。

And we modified the loop conditions so that we do。Essentially 50 iterations of the loop。Okay。

 so we added the iteration and loop， we're doing。We're doing the work of a couple of iterations。

So you can imagine unrolling the loop， two iterations， the loop， three， four， however many。嗯。

What kind of performance metric？Is it trying to improve。 So remember we had。Space power。Time。

Why do we think this optimization might be a good thing， Jenny。

 usually time it depends on the instruction。给送。Usually time。

 how do we think that this optimization might actually be helping You don't like jump after every iteration。

Right， it's actually reducing the amount of branching that happens。

And checking of the loop guard so for example， in that code it's only got 50 jumps and it's checking the loop condition infrequently。

I'd say modern architectures do a really great job of branch prediction of actually figuring out what the likely branch that's going to be taken。

So yeah， I actually know what the latest results are on。

 this is an optimization for modern architectures。also though that it of course yields larger loops。

 the loop body is longer with a couple of copies， so that might impact the instruction cache。

So when you're doing this， you got the question of which loops to unroll and how many times should you unroll the loop？

Some heuristics that are typically used for this optimization are only unrolling loops with straight line code and only with simple loop control。

 and then it's often useful to use profiled runs to actually check whether or not this is a。

A useful optimization。嗯。And again， one of the additional benefits of loop unrolling is that enables additional optimizations。

 so say by having a couple of loop bodies in there。

 you might have some common sub expressionpressions that can be eliminated and as a result。

 you're reducing the work for， let's say two iterations of the loop into less than twice the amount of work of a single loop iteration by factoruring out common computation over a couple of iterations。

Any questions about loop Unrolling？Okay。Next， optimization。😡，Function inlining。

So this is the idea that if we have a code to a function。

We could actually replace that function call with the function body right so summarywritings required。

 you need to change the body of the function to instead of using the formal parameters。

 use the actual arguments and so on， the local variables and so on。嗯。So， for example。

 if we have here some code， which is calling。Pow X。And here's the code for power X。

What we could do is。Replace that code with。Inlining a copy of the function body。嗯。

And so here you're seeing that we're declaring a local variable in a， which is going to be the。

Sanding in for the formal argument， we've got a copy of the loop body there。

 instead of a return value， we put that in temp and then we use temp instead of the function call。

Now， of course， the benefit of this is that we remove all of the overhead of a function core。 right。

 the stack manipulation jumping to another piece of code and so on。And of course。

 it gives us the benefit of being able to rewrite or specialize the loop the function body for the specific arguments and enable other optimizations。

 such as comments of expression elimination。Constant propagation， constant folding and so on。呃。

Performing this optimization might require some careful code that， for example。

 renames variable names to avoid variable capture。😊，And so on。

This optimization is typically best done。Relatively high in the compiler pipeline。

 so either at the source AST level or at a pretty high intermediate representation。

And it's just because making sure we're doing this when the notion of a function is clear and easy to manipulate。

Right。Okay。Christians。用。Okay， so at a high level。This can be a good idea。But of course。

 we might have recursive functions。So if we have recursive functions。

 let's suppose this function of X and Y， which as part of the implementation calls F again。嗯。

If we end up inlining it。All we're really doing is just unrolling one call。Right。

 so if we had this expression， F of Zcom 8 plus 7， and we inline it。We have this call here。

 but we still have。This recursive function call。Clearly， we can't just keep on inlining。

The recall to F because they don't ever finish every time we replace the core to F with a copy of the body。

 there'll still be a call to F。嗯。But just performing this， you know。

 one unrolling of the loop doesn't really feel like it's of benefit。

RightThe rehecursal call might be invoked。Tens hundreds of times。

 and so the inlining doesn't really seem to be doing much。We can， however。

Get some of the benefits of inlining just by essentially doing a trick。

So what we can do is rewrite the recursive function。Before we unla it。So let's take a look at this。嗯。

Suppose that we。Rewrite the function to use what's called a loop pre header。 So， for example。

 if we have this recursive function。If。We're going to rewrite the body of F to instead use。Instead。

 have this local definition。If prime。And。Essentially。

 the recursive call is going to be referring to F prime。啊。So for example。

 if we had this function F and x and Y。We could rewrite this function。

To have this local function definition， F prime， which is just a copy of F does exactly the thing F does。

嗯。And if is defined in terms of if prime。Right， so this should be a straightforward rewriting。

Doesn't look like it providess any value。from a semantic point of view。

But let's see what happens when we inline it。O。So the key thing that we can do is。We note that。嗯。

Y here is invariant in the calls to F prime because F prime is local。

We're able to do some transformations on F prime。So here we're actually able to pull out。

The fact that F prime had this redundant argument of Y。

 this is kind of like a loop loop invari code motion right we realized that that argument Y was the same to every single invocation。

 so we don't actually need to define it every time we can pull it out。And just let it be captured。

From that enclosing variable。Then when we end up。Inlining。We actually have。

If you will the specialized function。where y got replaced with five with a constant。

And that is kind of the specialization。嗯。The specialization of the recursive function for that particular call that might enable additional optimizations。

 and then our normal compilation process of closure conversion。

 lambmbda lifting and so on will take care of handling this new function， giving us the benefit of。

Essentially， the inlining specializing it to this particular function andvocation。

 while I got replaced with five， we reduce the overhead of calls and so on。

And if we hadn't rewritten F to use this local function F prime。

Then the rewriting would have been less useful。 Okay， we would have gotten this。

Progated this constant。Five， but then for the recursive call， would lose any value of that。

Any questions about this trick。For rewriting recursive functions to enable them to be specialized。

Yeah， so in this particular example， it seems like if we don't do the were writing like the F statement can actually like。

一すも回。You're right， here the if statement we could do constant folding。

Realize four less than one is false and replace it with that。 That's kind of like unrolling， right。

 we kind of。In some ways we've unrolled。The recursive call。

 which you can think of as being like a loop。And and specializing it。

 but we're losing any opportunity to。Factor out common。

Expressions to constant propagation in the callley for the function F。嗯。Yeah。

 thanks for putting that up。It's purely the timetake doesn't come like reducing the number of function calls but。

How many how much repeated color？What going call pass around。Yeah， so with this one。

With this one here。So inlining provides。Some， as we talk about， reduces function overhead。

 like the function call overhead。It might also allow specialization。Of that function call。

 which enables further optimizations。嗯。Theres。With the recursive functions。

 you may not remove all of the。Function overhead。But you're still getting the benefit of specialization here by being able to specialize this recursive call and sort of all iterations of that recursive call。

 in this case， for the constant argument five， for example。

Depending on the smarts of your compiler for a functional language。

 you might be able to convert some recursive functions into loops。

We'll touch a bit on that in just a moment for another optimization， but this one here you can。

In some ways， what you want to do is allow in a functional programming language。

The programmer the ease and the joy of writing recursive programs。Yet get the same behavior。

 sorry performance as writing an imperative program that doesn't have all of that function call overhead。

 and so there are compiler techniques to accomplish that。

 which will typically require local reasoning about functions。

Where you have the entire function body， you have the call to it。

 and you can do the transformation appropriately。So。So that's， again。

 having a copy of the function locally might allow stronger reasoning。

Because you can make this transformation here to convert it into a loop without worry about it being an a。

Let's say separate compilation module where。Where might change and so on。O。Thanks for the question。嗯。

All right， we've talked about that idea。The downside of inlining a function is that it might increase。

The total code size， if you have。A function that's called from four different places。

 And you replace all of those four callss with a function body。 Maybe your code is about， you know。

 now has four copies of the same code。Even with optimizations and maybe being able to reduce it。

 it might be that your total code size is bigger。 and as a result you might have worse code cache performance。

But who knows？嗯。In general， some heuristics for winter inlineer function include only inlaning function calls that are called frequently。

Right， that is。If you if you're inlining a function and that function core site is only actually executed a couple of times。

 reducing the oil overhead of that function call is not going to help much。嗯。That might be done by。

 for example， using an execution profile to see how often are various core sites invoked。

 or there might be static analyses where you can approximate。

The number of times a piece of code will be executed and the kind of heuristic you use there is。

Let's suppose every single loop is executed a constant number of times。 let's say 10。

And so what you're able to do is realize that the innermost loops are the ones that are going to be executed most frequently。

 which is typically true， right Code spends most of its time inside the deeply in loops。

Another heuristic to use is only to un functions that have small function bodies。Right。

 so that you're not getting。呃。So that the copied body wouldn't be much larger than the code to twinvoke。

The flip side of expand only function cores sites that are called frequently。Is actually。

 if you have a function that's called from only one place。In the code。

So I don't necessarily mean called once。Dynaically， only executed once。

 But if there's only one call site， that can also be a good candidate through inlining because then the。

You might have an optimization that removes the function that's no longer invoked。

 so your total code size is not any bigger。Any more questions about function and lining。Okay。

 so that brings us to， I think the last optimization in my list， tail call elimination。

So suppose that we have two recursive functions。 They're both implementing add， add of M and N。

Returning the result of summing up M&N。嗯。They're pretty similar。Except。In this first version。

We have a recursive call to add， they both have a recursive course to add， but in this one。

After a returns。This function still has more work to do。That is a needs to take the result of a。

And then add one to it and return that result。By contrast， the second function。With a recursive call。

After this recursive call， there's nothing else to do。

 The result of this function invocation is simply the result of that recursive call。

And so this is known as a tail call， this is covered in 51， right？

The idea that tail calls can be incredibly efficient。Now， the reason why this can be efficient。

Is that we're often able to eliminate。The tail core。So， let's。

Take a look at this equivalent program in an imperative language。

Of the second version with the tail core。And you could imagine an optimization that in the imperative language。

 eliminates the tailco。And turns it into a loop。RightThat instead of this recursive call， you simply。

Instead of the recursive call， you essentially just jump。To the beginning of the function。

So the cool thing is。We're often able to accomplish that tailco elimination。For a recursive function。

 the idea is that you replace the recursive call。With an update to the parameters and then just jump back to the beginning of the procedure。

And delete the return。嗯。What's going on here is by jumping to the beginning of the function。

What we are doing is reusing the stack frame。Okay we've got the stack layout for the function body。

 there's known to create a new stack frame for the same function instead we've just updated the parameters。

 the arguments jump back to the beginning the layout is still exactly the same。

The other nice thing is that the values of the arguments。

re going to stay in registers right we don't need to put them into if there's a lot of arguments。

 we don't need to put some into the stack， even if there's a few。

 we don't need to worry about the calling conventions。

 they can just stay in whatever registers that register allocation has decided to put them in right as opposed to what's。

Asposed to what registers needed for the。嗯。Calling conventions。So when you end up combining。

Talelco elimination within lining。This is what I was alluding to earlier。

 that we can get a recursive function。There can be as cheap as a wildlife。Right so we get this。

Separation with a programmer can focus on the high level concerns。

Focus what they want to be correct and for the most part， not need to worry about the。

The performance aspects that the compiler can be smart enough。Now， this idea of tcool elimination。

 we can actually do this even。For non recursive functions。

So if the last statement of the function is a function call。Even if it's not to the same function。

You get to reuse the stack frame。Right， so essentially this transformation means that youve will。

You might need some manipulation of the stack to do it。 You might need some。

Coordination with the core Lee， but the basic idea is that you can avoid some of the overheads of the function call or at least of having the intermediate stack frame when you end up returning。

Okay， any questions about Tcool elimination？Yeah， very beyond on the scope。

 but so like the newest version of O capital。They've got cons and independents have call beverage。

They have waters。Like soend by this non tailcursive。

 except in life version 5 point whatever it is now。No。

 I'm not actually keeping up to date on Ocheml things， but there's great post。

 a link to it on Ed and the core staff and others can chairmeman to let's understand。

What it's actually doing。嗯。To make a workout。嗯。The kind of thing that you might imagine it is doing is kind of similar to the transformation we saw there。

 Imagine that you maintain the same interface， but you implement a different version。

 say that use an accumulator。Passing the accumulator down or something。And then you've got。

It's implemented using a recursive function call that is tail recursive。So you get that benefit。

 you might be able to get away within lining and get kind of that localization as well。

 but even if not， you avoid the recursive calls。And reuse this tag frame There might be it。

 it might just be an implementation detail with an append， but yeah。

 post it and we'll dig into the code。Cool， so we actually covered a lot in last lecture in this lecture。

 a whole bunch of optimizations and where they tend to be done。😊，At at the high level。

 middle level or low level。Of code。嗯。Oh， sorry， one。Everything I do just want to say。

Writing fast programs。 So to be honest with you。It doesn't matter how good your compiler is。

 The best thing you can do if you want to。Write a program that goes fast is actually figure out what the right algorithm is。

So no matter how smart we make the compilers， you still probably want to take CS124 or other kind of or just have an idea about what is the algorithm doing and what is the cost of that algorithm？

Similarly， choosing the right data structures is really going to help you。

Those are typically going to have a much bigger impact on performance than the compiler optimizations。

😊，嗯。So it's kind of after you've done this high level work of。For example。

 choosing the right algorithm， minimizing in direction。

 so minimizing the number of hops you need to get to。

 then using compiler optimizations to improve performance is great。😊，And then after you've done that。

 actually using a profiler to run your program， figure out what the hotspots are。嗯。

And this kind of sounds obvious in hindsight， but what you want to do is spend your time working on improving the code that the program actually spends most of its time executing。

Right and in some ways to figure that out， you need to know the workload that it's running under or likely to run under and actually profiling it to see where are the bottlenecks So you know it's very easy to fall into a couple of traps One is what's known as premature optimization thinking through and going like oh wow。

 I could make this faster if I do this and spending a whole lot of time modifying code。

When that might actually not be the bottleneck， it might not be the thing that is actually taking up the bulk of the time and execution。

Related to that is this idea of you know searching for your keys where the lighters as opposed to where you drop the keys。

 same thing if you kind of look at things and think， oh it'll be easy。

 I know how I could optimize that and going and spending time on making something faster。

 but if it's not actually where your program is spending time then no matter how fast you're making it it's still not going to it may not have a significant impact on the performance of your program。

Okay。あ。Optimizations。So。As we've been talking through those optimizations。

 we've been realizing that for many of them， in order to figure out if they're actually。

Where we have opportunity to apply it and how to make sure we apply that optimization or that transformation safely。

We actually needed to know information about the program。We needed to know， for example。

 if an expression is invariant in order to do common subexpression elimination。

 is the same syntactic expression actually going to evaluate to the same value at runtime in those different locations？

Knowing whether or not an expression has side effects， knowing where a variable is defined。

 that is the variable is assigned into， knowing where a variable is used。

 knowing how those things relate， so for a given use of a variable。

 what are the definition sites that might flow to it？

Knowing whether two reference values might be aliases of each other。

So what we're going to do in the rest of the lecture today and yeah we might spill over into Wednesday's class is looking at the algorithms and the data structures that are useful for answering these questions。

😊，嗯。So we're going to look into some particular analyses that。嗯。Let me motivate。

The first analysis we're going to look at， laness analysis。By talking about register allocation。So。

What we're currently doing in our Oat compiler。Is just。

Generating as many temporary variables as we need， UADs。And then we simply map those into the stack。

 we say for this UID， we're going to store it here on the stack。嗯。

So this is nice and easy to compile。But of course， it's inefficient。

 Anytime we want to define a U I D， we compute the value。For that UI， for their temporary。

 we put it into the stack。Anytime we want to use the UID， we load it from the stack。

 put into a register and use it。So ideally， what we'd want to do is for as many of those UADs as possible。

We avoid putting them。In the stack at all right we just map as many of those UidDs as possible into registers。

The problem is that we have only a limited number of registers。 So 16。

Registers available in our 64 bit X86。And it's quite likely that the functions we're writing are going to have more than that number of temporary variables。

And of course， over those 16。You know， some of them have are reserved， so have special semantics。嗯。

So what that。Points us to。Is that we can't just take an I D and assign it into a register for the entire duration of a function。

Instead， what we're going to need to do。Is have a single register represent。More than one temporary。

 more than one UA。That's how we're going to get efficient use of the registers while maintaining the correctness of the program without needing to store things in the stack。

But of course， this gives rise to the question， when is that safe？

When can we say these two temporaries can be assigned to the same register？

And things are going to work out。So the answer to this question。

When is it safe to use a register for more than one local？More than one temporary。

Relies on the idea of liveness。So the key observation is that if I have two temporaries。

 UA1 and UAD2。We can assign them to the same register if the values of those temporaries are never going to be needed at the same time。

Now， by needed what I mean？Is that a temporary is needed if it's contents， if it's value。

Is going to be used as a source opera end sometime in the future， so in a later operation。

So this idea of needed is specific to a program point。Okay。

 so a temporary is needed or is live at a given program point。If the value of that temporary。

Will be used as a source opera end。In a later operation。If I have two variables。Such that。

When I go through every single program point in my function。

There is no program point where both those temporaries， both those variables are alive。

That means the values of those variables are never needed at the same time。

There's no point in the program where both of them alive。And if that's the case。

 then it's all right for us to use the same register to represent。Those two variables。

Does that intuitively make sense， One， this idea of laness。

To this idea of if we have two variables that don't that are never live at the same time at the same program point。

Then we can use the same register for them。Okay。So how do we figure out this liveness information。

So clearly， we can get some coarse grain of information about laveness just by looking at the scope of variables so at the oat level。

If we take a look at this program， we have variable B declared inside this block。

So B is only going to be in scope within this block。 by the time we get down to here。

 B is not in scope， can never be used， and we declare variable C。

So due to the scoping rules variable B and C can never be laid at the same time because their scopes are disjoint。

 there's no program point that could actually refer to B and C。Right。嗯。Or rather。

By the time C is live， B is out of scope， and thus not live。

And so what that means is we could end up assigning B and C to the same slot， storage slot。

 and maybe to the same register。So that's good。But to be honest with you。

 just using scope information about variables is way too coarse。

There's many more opportunities to make efficient use of stack slots and registers。

Beyond variable scoping。So let's take a look at this program。The scope of ABC。To local variables。

 and X， the argument。All of them overlap， right， They're in scope for the。

At the end of the block here。All of the variables are in scope。But。😡，A， B。

 and C are never alive at the same time。😡，All， so let's look at this。A is defined here， x plus 2。

 it gets used in this line。But after it's use， D is defined with the result。

And from that point onwards， A is never used。So once B is defined， A is not life。A similar way。

 B is used right here。But after this use of B， B is not life。

 C is defined and used down here in this return statement。 But at this point here， B is not life。

Same with the variable X。 it's used here， and it's also used here。 But after this use， that is after。

The evaluation of B plus x。X is not life。Anyway， so because A B and C are never live at the same time。

 that means our compiler could end up using the same stacks lot for them。Or more aggressively。

 use the same register。For them without any trouble。There's no program point where they are。

Where A B or C， more than one of them is live。Sorry， just walking through that。

So essentially here at each。Program point or list between these lanes here indicating which variables are life。

Okay。Yeah， question。Doして。嗯。So we could do this with。Two registers， right？

I believe if we had one to hold X and one to hold A B or C。Ignoring， you know。

 we need to look a little and to make sure calling conventions are all okay when we can power down to lower levels。

 but definitely the idea that we only need。We'd only need two spaces to store things。Co。

 thanks for clarifying that。Okay， so we are going to get on to register allocation next lecture for a couple of lectures。

😊，But a key part of this register allocation is the laveness analysis。

knowingnowing which variable is alive at which program points。So we're gonna start digging into。

Lfe variable analysis。The idea of it。How to implement it and then how we generalise it。

So a variable v is live at a program point， if V is defined before the program point。

And is used after it。So that is livenesss defined in terms of where variables are defined and where they are used。

What we're going to do in our laness analysis is compute the set of live variables。

Between each statement。嗯。So this might be conservative in the sense that we might claim that a variable is live when really it isn't。

And that might be because let's say a variable is used。

Only on the thenin branch of an enough statement。Maybe it turns out that the then branch of the Fstatement is never taken。

 the guard turns out to be equivalent to false， but due to a complicated computation。Right。

 that means the variable is never used， but our analysis won't figure that out。

 And our analysis will say conservatively， hey， it looks like。

The variable might be used in the future。And we want the analysis to be useful。

 So we're going to make it more precise than just the scoping rules。

So we're going to present this analysis， and it's an example of a data flow analysis。

There are many other data flow analyses， some of which we'll dig into available expressions。

 reaching definitions， constant propagation， and a whole lot more。Okay。

So we're going to dig into the details of liveness analysis。I said， we're going to compute。

Lveous information kind of between each statement。It's a bit of a hand wave。

 What we're actually going to use to compute the laness information is a control flow graph。

So remember in a control flow graph， this was a graph over basic blocks where basic blocks was where a basic block was a sequence of instructions such that。

嗯。The sequence of instructions was executed in its entirety。

That is program execution always started at the beginning of the basic block。

 There was no jumping into the middle of the basic block。

All of the instructions on the basic block went through in turn。

And then the last instruction of the basic block was some control flow instruction。

 a jump or a conditional jump or a return。So in our control flow graph， the nodes were basic blocks。

 and we had an edge from basic block B1 to B2。 If the exit of B1 might jump to the beginning of B2。嗯。

There were no dangling edges。Even though in L of VMIR， we're using labels。

We check to make sure it's a well form graph right that have， if we're jumping to a label。

 it really is a baseo block that is defined for that label。诶。

In what I'm going to be showing you in the rest of today's slides about data flow analysis。

 I'm being a little vague about what exactly we mean by an instruction。Right。

This idea of control flows and data flow analysis works for assembly code LOVMIR high levelvel source program as well。

 you do need to be careful about the exact details， like what is a statement， what is a basic block。

 what are the suitable terminating instructions and so on。嗯。But the general idea is hold。

 so I'm be I'm going to be a little fast and loose with that。嗯。So an example would be that。

What I'm presenting， we might have the same local variable that is defined multiple times。

That can't happen in LLVM with temporaries because LLVM is in this SSA's form。

Single static assignment。turns out that SSA form makes things like data flow analyses a little easier。

And so when you end up implementing a data flow analysis for L ofVMIR， fantastic。

 your framework gets to be a little simpler than if you're doing it， say for Java source code。Okay。

So we're going to be doing the laness analysis on CFGs。We're also。

Instead of doing it on basic blocks。It's going to be a little easier for us to think about the nodes of the graph being instructions。

So that is instead of a node of the graph being an entire basic block。

We're going to make a node and an instruction and we'll kind of have these full through edges。

 The edge from here to here would be the， you know simply falling through to the next instruction within a basic block。

So in general， in our control flow graph。What we're going to do is a node is going to be an instruction。

We might have multiple incoming edges showing the control flow coming into this instruction。

 We might have multiple outgoing edges， showing the。W control flow goes after the instruction。嗯。

We're going be computing the liveness information。 I said we're going to be doing that between statements。

What we're actually going to be doing is associating it with edges。And that's。So instead of。

It turns out that we don't want to associate it with the node with an instruction itself kind of putting it on the edges allows us to have the same register being used for different temporaries that are used in the same statement。

 So for example， if we had the assignment a equals B plus1 at this instruction here。诶。Sorry， we had。

A equals b plus1。We might have B being live as we。On this edge as we come into this instruction。

 because B is used， A gets defined here。A is live here because A is defined and used later。

But B is no longer live， and let's assume that A is live because it's used somewhere later。

The key point is that by tracking liveness information at the edges rather than the nodes。

 this allows us to say use the same register for both A and B。So even though the same instruction。

Users A and B。The idea that。There's no place we're both A and B alive。

When do we think about laveness being associated with the edges？

Means we could end up using the same register。For this instruction， move A to B。And。

If we use the same register for that move instruction。That becomes a no of。Mo EAX to EAX。

 we can just drop that from our code。So this is the idea that tracking the laness information of the right granularity allows us to get much better use of registers。

 which might allow us to do things like remove entire instructions。Has no os。嗯。O。

I also made a small way here as well。Depending on the analysis you're doing。

 you might actually want to associate facts with edges。For us with this laveness analysis。

 it's going to turn out to be okay for us to associate it with kind of。

I don't need to associate it necessarily with all three of these edges directly。

 I can just end up saying just before the instruction and just after the instruction。

And we're going to use that same laness information for。Kind of all of those。All of those edges。Okay。

 this will hopefully become clearer as we dig into the details of an analysis。All right， next thing。

Next concept， before we get to presenting the analysis。

The idea of uses and definitions of a variable。 Now。

 this is something I've been talking about from last lecture when we talked about optimizations。

The idea being that。For any given instruction or statement。

 it uses some set of variables that as it reads from them。

 it uses the value that's currently in those variables。

And every instruction also has a set possibly empty of instructions that it defines。

variables that it writes to。So we'll use the following notation for a。

A node S will say u of s to be the set of variables used by that statement。

 that node S and de of S to be the set of variables defined by S。Okay。

 so for a plus a equals b plus C， this uses the variables B and C， so use S is Bc。

 and it defines the variable A。For a equals a plus 1。It both uses and defines only A。ok。

So without a moon， we can present a more formal definition of laveness。

So a variable V is live on an edge E F。There is a node in the control flow graph in。

Such that n uses the variable V。And。There is a path。A directed path。From the edge E。To the note end。

Such that， the variable v is not defined on any node on that path。

So what that means is for a given edge E。Cluse one says that。There is a node where。V gets used。

 right there's going to be some path from E。To a node where V is used and moreover。

 Cla two says on that path。V does not get redefined。So that is the current value of V。

At H E is the value of the variable v that's going to be used at the node in the future。Great。

 so this is the definition。Of laveness， phrase pretty concretely， pretty formally。

In terms of the control flow graph。In terms of the set of use and definition sets。Of a given node。

 right？So now we have the problem， given this definition of the liveness。Analysis。

Of how do we actually compute this？Right。How do we compute this laveness information efficiently？

Once we've got that， we're going to have questions about how do we use it for register allocation that's going to be we'll dig into that in much more detail next lecture。

 actually for the next two lectures。😊，And it will turn out that kind of once we understand the analysis。

The choice of the language of the intermediate representation will see that it influences。

How how we're doing the analysis。So let's jump into thinking about how we compute the slaveness information。

And let's first of all， use a very inefficient algorithm。To get the ideas clear。Okay。

 so there's the definition of liveness again。We're paraphrasing of it。Here's a simple algorithm。

For each variable v。Let's。Find a use of V， Well let's go through every single use of that variable V。

And just go backwards through the control flow graph。Go backwards through the control flow graph。

 until either。On that path， we find a definition of V。Or we get back to a node we've already visited。

Okay， so we're kind of doing this for a use of a variable V we're going。Backwards on the edges。

Exploring the graph， terminating our search when we reach a definition of V or when we've already visited node。

Everything that we visited， every age that we traversed in that visit。V is live on。

Because for every edge we traversed， there is a path to a use of V。

 that's where we started from with no intervening redefinition because we truncated our search when we got to a definition。

So this is clearly an algorithm。That we can use。To。Figure out the laveness of variables on edges。

So great， you know， this is definitely a computable problem。

 We can do some pretty simple graph algorithms to figure it out。😊，Nicholas。

 how are we to deal with like redefins， public like， we use gensen to to create a new name for every。

For new variables in the UNI。Right， so。嗯。The analysis we're doing is。嗯。

The program is fixed for the analysis。 right， So what we're doing is。

Let's say we've got a version of the LOVMR。We're not transforming it yet， right。

 What we're doing is we're taking that program and。Understanding for this program。

 which verb was alive on which edges。Yes， we might have used Gensom to come up with new variable names。

But by the time we're analyzingna the program， the variable names make sense for where the programme is in its compilation。

 right？So。You know， the fact that we have the variable V we're talking about。

The name of that variable we might have been generated by a previous compiler pass using Gensom。

 that's all totally fine。it's just the idea that for every use of a variable V。

 we have this inefficient algorithm。The correct algorithm。Then lets go from use of V go。

Backwards through。嗯。The control flow graph， when we reach a definition。We stop our traversal， right。

 And that's kind of how we're dealing with redefinitions， right。

 We're only finding just by the way we're constructing this visit of a graph。

We're only going to be exploring edges that do not encounter a redefinition of V。

Does that help clarify？Ok。Thanks。Any other questions about this simple algorithm？Are we comfortable。

 that's correct？Mtdie， yeah， I don't know if I caught everything from that。

 so it's like what happens if it's redefined？Right。嗯。The reason why this algorithm works。

Let's suppose we have a language where the same local variable could have many definitions。

Right x equals3， x equals x plus 7， x equals 42 right so the same local variable assign three times so not like an LLVM。

Where each temporary can be assigned。Exactly once。Even in that setting。

 where a local variable could be defined multiple times， the algorithm works。

The reason why this algorithm works is。We're starting at the use of a verbal and going backwards。

Until we reach a definition site， which might be a redefinition or the first definition。

 it doesn't matter。As long as once we reach a definition site， we stop our traversal over the graph。

 And what that means is all of the paths that we're exploring are by definition。Pos where。

Going forward it can get to a use of V because that's where we started from。

 and moreover there's no definition of the variable on that path。

Because when we got to a definition of a variable， we truncated our backward search。と。

I appreciate that a diagram or an animation would be useful here， so apologies I don't have one。哦。

Okay。嗯。It's not a proof， but are we comfortable that this algorithm is correct？

Which is in part being comfortable with the notion of Lightness。Yeah， so implicitly like。

This is kind of getting rid of like， like if we have a definition and then immediately like redefinition and then a use。

 like before the definition of the redefinition， wouldn't actually count that as。That's right。

 so if I define a variable。X equals 7。And then in the very next line。I have x equals 42。You're right。

 that x equals 7 nes used right there's no point where。😊，That definition reaches a use。

 and so there's no place where that x equals 7 definition de variable x is live。

And reachable from the x equals 7。So that would be。De code。That could be eliminated。O。Okay。

 correct algorithm， but of course， inefficient， right。

 we're going to be exploring the same paths many times for different uses and different variables。

 right， the simple algorithm went through every single variable and every single use of each variable to do its backward search。

So。The idea of the data flow analysis I'm going to present to you is that we compute that liveness information for all variables at the same time。

RightAnd what we're going to be doing is keeping track of the sets of information about each node or rather about each。

About each edge。The way that we're going to do this is we're going to define equations。

That have to be satisfied。By any correct solution to the liveness analysis program。

 So these equations， when I present them to you should hopefully be quote， obvious。Right。

And the idea is what we're going to do。It start with a really bad approximation。

To the result of a laness analysis， to a really bad approximation to the question of what variables alive at which program points？

Then we're going to use those equations， use those constraints。To improve our solution， right。

 to get a better approximation。And we're going to keep on doing that with this better approximation。

 we're then going to use those constraints to get an even better one。And so on and so forth， until。

No more refinement is possible， right until the equations don't give us any improvement。

In our computation。At that point， we've reached what's known as a fixed point。Okay。

 and so for those who。Took 1，52。 Yes， this is an example of a fixed point computation。

That we're starting off with a bad approximation to the result in getting successfully。

 better and better and better till eventually we stabilize。嗯。

This is an instance of a general framework for computing program properties， of data flow analysis。

Okay， so into this， let's get these， figure out what these equations are。So。嗯。

Our nodes are going to be instructions or statements， so for each node N。

 we're going to be making use of the following sets use of n and de of n we've already talked about the set of variables used by the node n and the set of variables defined by N。

What we want to compute is these two sets in in and out in。

 so in in is the set of variables that live on entry to in。

And out of in is the set of variables that are live on exit。From in。

And so these in and outss are essentially going to be collecting information about the incoming and the outgoing edges。

Okay， so what we're going to have is out of in。Is going to be the Union of Laveness information on all of those。

Outgoing edges。So this is what I was meaning by we're never actually going to be explicitly representing the liveveness on the edges。

 we're instead going to be representing liveness just before and just after。A statement。

 the in and the out。Seets of a statement。Okay。So we've got these four setss， use of N， de of N。

We want to be computing in in and out in。And we're going to be doing that。

 as I mentioned by having constraints， having equations。So。Let's think about this。First of all。

What we want to make sure of is the inset of a node in。

Has to contain all of the variables that N uses。Now， if we think about the definition of liveness。

What's going to be live here at this edge， just on any edge just coming into in？

Remember if there's a path。To a use of a variable V。

 that doesn't have a definition of the V in between。

So anything that's used by N is going to satisfy that。There's a path。

 this really simple one from here to here。Where in is used without a definition。

And that's because conceptually， with a statement。We use the variables to compute the value that we're going to put into the definition。

Into the assign into the new variable。Okay。We also have。An equation， a constraint。That。

The inset of an node N。Is going to contain。Everything that's in the outset。

Minus any variables that are defined by n。All right， so let's think about this。

If the variable is in the outset of n。A variable v is in the set， that means that there is a path。

From here to a use of V。Without a definition， without going through a definition of V。

If V is not defined by N， then V should also be live in the set in of N。

 because there is still a path。There is a path from here to a use of N without going through a definition。

However， if the node to n defines the variable V。😡，Well。

 that's the redefinition of V or the definition of V。And so we so we would not be live。At that point。

Okay， so we have this constraint as well。 in of in includes。Out of n minus f of n。Okay， so this。

 these two constraints kind of talk about。N of N， out of N， use of N and de of N。

RightSo these are kind of relating for a single node in。Those four sets。We also need an equation。

That connects different nodes。So we're also going to have F node in。If N prime is the successor of n。

 meaning there's an edge from n to N prime。What we want is that the out node of n。

Contains the in node of in prime。And that's intuitively because if there is a variable。

In the insideet of n prime， a variable v in the inside of n prime， it means there's a path。

From just before N prime to a use of V without going through an intervening definition。

So there's also a path from just after in。To a use of V without going through a definition。

So this is kind of connecting the in and outs of different nodes。AndThat's it。Right。

 so these three different kinds of constraints。 We need to instantiate each of these constraints for all of the nodes in and n prime as appropriate。

But all of the constraints that we need are going to be of one of these three forms。Okay。

 so let's think about how we could do iterative data flow analysis。嗯。So like I said。

 the idea is that we're going to start from a rough guess。

 a really bad approximation to the result and iterativeably improve it。

 So our really first initial guess is setting everything to the empty set。

N of n and out of n is empty for every single node N。Now。

This solution doesn't satisfy all of the constraints。 might satisfy some。

But there's going to be constraints where it doesn't satisfy the unset containing all the uses of N and so on。

So what we're going to do is iteratively recompute in of in and out of in。

When if we have a constraint that isn't satisfied？So what you can imagine we do is。At each iteration。

 we just go over all of the constraints。If a constraint isn't satisfied。

 we add something to the inset。 If this constraint isn't satisfied， we add use of n and in of n。

This constraint isn'tssfied， we take out of n minus F of n and add all of those to the inset of n。

For this one， if out of N doesn't contain this in of N prime。

We take this set in of N prime and add it to out of N。So that as each pass through。

 we're kind of fixing each broken constraint by increasing the size of the in and outsets。

And we keep on doing this。Each iteration we go through every single constraint。

Find any that uns satisfiedati and increase the size of either in of n or out of N as appropriate。

And if we ever go through all those constraints and find that they're all satisfied。Great。

 that's when we stop。What that means is that we were able to go through all of the constraints they were satisfied。

 they didn't tell us to increase the size of any of the sets。Will turn out。

That when in and out satisfies those equations， they'll in fact be equal。To these things， right。

 n of n will equal use of n union out of n minus Fiv n and out of n will equal the union of all the ins of the success and nodes。

So these inclusion constraints， when we end up finding the least fixed point。

 the least thing that satisfies them。We will， in fact， get this quality condition。Okay。

 so I hand wave my way through that， let me continue to hand waveve and give you some pseudocode。

Right， so here's some pseudocode for the algorithm I just described right for all in。

 we set in of in and out of in to the empty set， and we just go through。

Essentially all the constraints， we're doing that by going through every single node in and making sure that adding things into the outset and the inset。

Until there's no change， okay， that's equivalent to just going through every single constraint。

So this algorithm is guaranteed to terminate。 who wants to give me a quick proof of why。

Or an intuitionful way。Nicholas。Because we want to talk we add variables and whenever there is something that can be fixed。

So it's kind of like the least and kind of like each pass kind of like extends the kind of like well important。

 each path extends the。Pass extends the path by one step。

And since any path has a finite number rope steps doing that， he passes。That's the right idea。

Each time through their algorithm， right， we stop when there's no change。

 So if we went through and there was a change， that meant that。Something got added to a set。Right。

 so we don't need to talk about paths。 Yes， we're effectively computing path for information。

But what we the actual entities we're manipulating are sets of variables right for every node in we have in of n and out of n two sets。

At each iteration where。Increasing。At least one of those sets， by at least one element。

 that's what it means to have a change。A modification。Now， there's only a finite number of variables。

In the program。And a finite number of nodes。 So what that means is that there's only a finite number of times that we can actually increase。

A set。Until。The set is at its maximum possible value。

So that means we are going to terminate at some point。嗯。Okay。

 and why do we start with the empty seat？Hey。I mean。

 if you start with both of them for all nodes being full sets and it satisfies it on the first。

That's very。Right， so let's say we put all the variables。We。

 we set the initial value of the variables to the set of all variables。You know。

 that would actually satisfy the constraints， but as Abe says it'd be a pretty terrible solution。

So it turns out that for us， the smaller the lanness set， the better。Right。

 that's going to be the most。Precise information and the most useful to us in register allocation。

because we want variables to not be live at the same program point。

 it turns out that by starting with the empty set。We're going to find the least。

 the smallest possible sets that satisfy the equations。Austin。Iice a general question， so for a peer。

languageI think this would be sufficient to do like data pro。F go to the very dedicated nation。

But if we had， for example， a variable definition that had side effects， but was otherwise dead。

Would have to we augment this process or would we have some workplace？Right。

 so this analysis is figuring out the laness of variables program points。 And yeah， we。

 I kind of hinted the fact that， hey。A similar analysis。

Is kind of needed for dead code elimination for realizing that this code is。

Is not actually useful in the computation of the program。😊，So you might be able to figure out that。

 hey， I've got a definition of a variable。And that definition never gets used anywhere。

Does that mean that it's。Dead and can be eliminated。 Not quite。 It does exactly like you said。

 depend on side effects。So if the statement has side effects， we might need to keep it there。

And that's totally fine， right， Maybe we called a function and we stored the result into a variable。

 but we never used it。So we don't need to define the variable。

 but we may still need to call the function if their function has side effects。

 such as printing something out or something like that。So this is。So， liveness。

Might be a component of Decode analysis， but isn't the entirety of the analysis。Great。

 thanks for the question。Okay嗯。We got like。Two minutes。I'm going to start walking through。An example。

呃 move。Finish it at on time and we'll continue next class。

 So here is in some sort of unspecified language， a program。

Here is a control flow graph for that program， each node is a statement equals one。

 heres the guard of the whale loop， here's the exit of the whale loop that goes to return of x。

 here is the body of the whale loop。And here is the F statement that's nested inside the wildbo。

And so on okay。So I'm going to be。😊，嗯。Showing you。Here。What we're doing at each iteration。

So the idea is that we initially these sets are empty and we're going to go through and update them according to these。

Equations。At the end of iteration1。They domain mean things like。Down here。

 the inet of node 8 is equal to Z because Z gets used instead of。

9ine is equal to y because y gets used and so on。So it turns out that kind of what's going on here is in this first iteration。

 we've kind of sort of figured out paths of Li。Z ish， right， zero wagedges。The next iteration。

We would be。Proropagating some more of this information through， let's say。

 from in up into some of the outsets。As well as increasing the size of n。

So here I'm just showing the nodes that have changed。Next iteration we'll do the same thing。

 we'll go through each of these， perform the assignments I'm going to highlight in red here the sets that change。

We see。These sets continuing to grow kind of what's happening is each iteration， it's like where。

Exploring a longer path。The information from the use of a variable sort of propagating backwards through the path。

Until it reaches a definition site， so essentially what we're doing is that same simple。

 intuitive algorithm。😊，But we're just kind of doing it for all variables and all users at the same time in each iteration。

In fourth iteration。There was only a couple of changes。And。Same with the fifth Feration。

 and at this point we've actually stabilized。We go through on the sixth Feration。 Nothing changes。

So what that means is what I have up here on the slide is the result of the laness analysis。

 So for each node we have an inset and an outset， and you can go through and you can check that it satisfies these equations。

Okay。We're just over time， so I'll stop it there on Wednesday's lecture。

 we're going to keep on going thinking about liveness analysis。

 thinking about how we can improve this algorithm， and then how we generalize it to other data flow problems beyond just liveness analysis。

Thanks very much。Hope you're enjoying homework five， good luck with it。对。Okay。



![](img/fe17361f66cd4651104582336181c23d_1.png)

![](img/fe17361f66cd4651104582336181c23d_2.png)

![](img/fe17361f66cd4651104582336181c23d_3.png)