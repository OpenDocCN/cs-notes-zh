# 哈佛大学《编译器｜Harvard COMPSCI 153 compilers 2023》中英字幕（claude-3.7-s p22 1700489700-Compliers_on_11_20_2023_(Mon).zh_en -BV14PAUejE98_p22-

Wednesday morning classes occurred and were essentially a non event。Right。Right right。

 thank you for coming to class。So anyway， welcome， those watching it on lecture video。

 just you should be thankful that your classmates are actually here to make sure a lecture actually occurs。

😊，Alright。Just following on from last class is a graph coloring problem Here is another one related to register allocation。

 which is what we're continuing with today。 So here are some fun interference graphs I it possible to write programs that have this interference graph。

😊，So that is， could you write a program that had these variables where a line between two variables means that they're live at the same time So let's take a look at the start configuration first hands up if you think a program is possible with that configuration。

Okay， pretty good， did anyone come up with one？O， okay， a couple of people。

 What about the subtle one， this nice square hands up， if you think it's possible。Well。

 it turns out they are both possible。 Here is。呃。That my clicker starts working。

Here are programs that do it。 So here， for example。

 we have a function where A is essentially live throughout。



![](img/dda0d6744ae5c37c28a7c266a2f25315_1.png)

And then we have variables that are each layer very briefly。I'm managing to get this arrangement。😊。

For this four square one we need a little bit more complicated control flow。

 there's essentially a branch at the beginning if I go to L1 LL2 D is live out。

 D is defined on either branch。B is used on one see on the other， so you can make a workout。呃。

That was more just a fun little。Sideline to。Keep on thinking about these interference graphs。

 liveness properties and register allocation。 Is there something wrong with the solutions。

 he does have some weird scoping， doesn't it。Like， shouldn't he be like declared outside？还有呢。Yeah。

 so this is not L ofVM， is it it's definitely an old single static assignment。But you know？

Were not it's not like this is a formal methods class or anything。

 so we're very hand waving about things。 you're right。

 you can cobble with this and I'm definitely not claiming that any graph is the for any graph there is a program that has that graph as an interference graph。

😊，allThere's a good question， though， could you come up with something？It over like this。

Let's say an LOVM。So that you had static single assignment， I don't actually know。😊，But。

I you to probably make some sort of likecraft rules a lot。If you have cycles that。关上。Yeah。

 you might have。We haven't dug into it， but。With a control flow graph， we often。

Typically want something better in an arbitrary than an arbitrary control flow graph。

 We want something that。Actually nicely structured。That。嗯。什么。

This might be possible but I'm not sure if it's possible with a well structured control flow graph that essentially corresponds to。

Having nice control flow， nesttic control flow without arbitraryu jumps。All right。

Feel free to continue discussing this on on Ed， and we can collectively come to an answer if we want。

Announcements， homework5， due in about a week。Exactly one week， homework  six。

 we released it late last week because we covered all everything for the required parts of homework  five。

 it's due in two weeks so I appreciate that this is tight and particularly there's only one week where you have homework  six without homework  five being due towards that end everyone will be able to use up to three days worth of late minutes。

嗯。Very quickly about what Home6 involves。The key part is on analysis and optimization。

 so you'll actually be implementing a generic data flow analysis。

 so using Fs to kind of parameterize a data flow analysis。

 you'll be instantiating that and using the data flow analysis to implement Els analysis。

Dead code elimination and constant propagation。U。If you have enough time and energy。

 there are some optional components。 You can work on a register allocation algorithm。

And if you complete the register allocation， you can end up digging a little into performance and seeing how much impact that Reg allocation algorithm has on a test case that you're right。

And then finally， there is an optional participation in the leader board and essentially this is。嗯。

If we。If you choose to implement this， you can just implement whatever optimizations you want enabled by minus O2 flag。

 And if you do that and you kind of automatically be。嗯。

Your compiler will be run on a test suite and put up on a leaderboard。

 so it's often essentially if you implement minus O2 and。Right， any questions at the moment。

 I appreciate most people are still working on homework 5 and haven't had a chance to look at homework6 at all。

The wanted to it very brief。Information about it。Time j6 life。Yes， target is to X86 light。

 which is going to limit what you can do。Let me。Yeah， the。

 the comparison is not really against clang。 The comparison is against others in the class。

In terms of how well you can do。Okay， so what we're going to be doing today is continuing to look at register allocation。

 And we'll kind of see how from the basic。Algorithm we had about colouring by simplification。

 we can actually improve that and also handle some of the particulars of。

Of calling conventions within a machine。So just a really brief recap。😊。

What we saw last class was coloring by simplification。

 And if you recall the Reg location algorithm had these four phases。

 remember we had we first of all built an interference graph using the laness information。

We then proceeded to the simplifyimplified phase where if we had a node with degree less than k which the number of available registers we had。

 we could simplify the graph， remove that node， add it to a stack。Keep on going。

It might get to the point where we had。Our graph only had nodes with a degree greater than or equal。

To Ka。In which case we had to select a node to potentially spill。

And the heuristic we used there was we computed the sppo priority。

Which was an attempt to balance how much it'll make the graph better。

 that is its degree with how often their variable is used。Then if we split anything。

 we would go back， continue simplification when we ended up with an empty graph。

 we would start the coloring phase。Essentially selecting the nodes in reverse order。

 so in the popping off the stack， assigning a color if possible， if it wasn't possible。

 then we would in fact need to spill a node that is rewrite the program。Sppell and go back。

All the way to the beginning and build。The graph， again。

But if we were able to successfully select colors， registers for all of the nodes， fantastic。

 we're done。Register allocation is finished。Okay， so thats a very brief recap of。

The algorithm we saw。Last class。Any questions？About this algorithm before we go on into。

Ebellishing it。Okay。So， this is pretty cool。We have this graph coloring algorithm。

 it does pretty nicely。诶。I want to talk about。Some of the optimizations that we've talked about over the last couple of lectures。

Itt actually play nicely with the registrar location。

In the sense that some of the optimizations that we talked about actually increased live ranges。

 So if we think about copy propagation。Right， that was if we had， say。Foo equals bar。

 We might replace uses of fo with bar。Right the thing is that might extend the live range of bar of that variable。

 it's now live out in more places， it's going to interfere with more variables。In a similar way。

 common subexpression elimination， if we have a variable that is storing the result of a subexpression evaluation。

And we realize that there's somewhere else that uses that。

Same sub expression and we used the result that we were already computed。

 that might extend the live range of the variable holding the result。Loop andvariant removal。

 that was where if you had an expression inside the body of a loop。

There was the same every time you evaluated the loop of the body， we could hoist it out of the loop。

And put it before the loop。But that of course， increases the range where the code。

Were those variables alive？And if we have increased wave ranges。

 that means our interference graph is denser。Which means that we might be spilling more frequently。

Okay， so these are bad things。So it turns out that at least copy propagation isn't that useful in the first place。

 So what we're going to do is actually。Develop a version of the register allocation algorithm that。

Is going to figure out if we have a copy， flu equals bar， and then F is lose used later。

What the register allocateator will do is try and allocate those two variables full and bar to the same register。

Where possible。Meaning that the copy， the cost of the copy will go away。

 or go away in the register allocation。Right， and so。

That essentially we might get the benefit of copy propagation。

 not needing to copy a value from one location to another。

 but without this increased register pressure。Okay， so with that。

 we're going to look at a version of this graph coloring register allocation algorithm that's known as coalescing register allocation。

So the key idea is that if we have。An assignment， a copy， X is assigned y。

And X and Y have no edge between them in the interference graph。

Then we might be able to assign them the same color， put them into the same register。Right。

 if we did that， then that assignment x equals Y would be translated to。knowRe I equals register I。

 which could be removed。So the way that we're going to be implementing this in our algorithm in our graph coloring algorithm。

Is we're going to optimistically coalesce nodes。That have this sort of copy relation。

 this move relation between them。And when we do that。

 when we collapse or coalesce those nodes together。

 we're going to take the union of the edges and the interference graph。Okay， so let's see this。

Let's build up some intuition for this。 So here is a program。That we have a couple of moves in here。

 so we have D equals C， so D and C are going to be what's called move related。

 that might be coalesced。As well as J and B。Right， so those are the only two。

Pairs of variables that we might be able to coalesce。So I've indicated on this graph。

 the sn the graph with a dashed line between variables that are move related， J and B， D and C。

And in our graph colouring algorithm， what will。Think about doing is。Coaleescing these nodes。

 combining them together， turning them into one node。Taking the union of their edges。

So that'd be nice， right， It' would mean that those nodes will those variables will get the same register。

But。By coalescing them， we might take a graph that is k colorable。

And by collapsing those nodes together， we'll turn them into a graph that is not k colorable。Right。

Wast question sure。We were talking about topic propagation and register pressure and how that this can cause more spills。

But that campus also calls more spill。So。Could the coalescing cause more spills。

 So what we're actually going to do is we're only going to coalesce。

When doing so will not cause us to do more spills。Right， so in particular。

Because coalescing in general could make a graph， a K colorable graph， not K colorable。

 What we're going to do is use a couple of heuristics。And we're only going to coalesce。

When doing so would not make a key colourable graph。Non K colorable。嗯。

So we'll go through the details of this algorithm。嗯。I think the goal of this heuristic。

Like I say is to the coalitioncing is not going to introduce more spills。

However the algorithm we present we're going to have is a heuristic。

That's trying to solve an N complete problem。So definitely we may not come up with the best possible register allocation。

Through this and we may come up with an approach that spills where it doesn't have to。

 but we're going to make sure that the coalescing doesn't introduce new spills。So towards that end。

 we actually have two heuristics。For when it's O to coalesce。

 So the first is called the Briggs heuristic。This is that it's safe for us to call this。Two nodes。

 x and Y if。After coalescing。So combining x and y into one node。The resulting node will have。

Fewer than K neighbors with degree greater than or equal to K。All right。

 so let's figure out why this is safe。Why this isn't okay heuristic。

So let's think about this combined node。First of all， after we've coalesced them。

 we're going to go back to simplifying and removing。Noodedes with degree less than k。

Right so what this means is if we coalesce the noise。

Any neighbor that it has with a degree less than K is going to end up being simplified away。

so we can kind of ignore them， we know those will be okay。We may be left with。

So if we think about the nodes with a degree greater than are equal to k。

If we have less than k of them。That's fine， that means this coalesce node can itself be simplified away。

It has fewer than Ka neighbours。That are going to be left after simplification。

 so it can be simplified away， meaning that this coalescing is not going。To cause any more spills。

The coalescce node will be able to be simplified a way we're definitely going to be able to color it。

So， that's why this。Huristic is safe， right？If x and Y satisfy this thing。

 we know we're going to be able to simplify it away。

There might also be cases where we can simplify it。A way。Even if this isn't met。

 but this is a nice simple heuristic。That we can check quickly when deciding whether it's okay to coalesce。

Okay， the second heuristic is known as the George heuristic。And this says， for have X and Y。

It's safe for me to coalesce X and Y if。For every neighbor， tea。Of x。Either。

T already interferes with Y。Or T has degree less than k。

Okay so let's think about why this is a safe heuristic。Remember when we coalce x and Y。

 we're going to be merging those nodes together。And kind of unioning the edges。So。If T。

Interferes with X。Right，That is its neighbor of X。 It's going to be a neighbor of this coalesce mode。

If T already interferes with Y？🤢，Then collapsing them together is coing them as completely O， right。

 We're not actually going the。T is not going to be increasing the degree。

Of the coalesce node X and Y。Right。If T has degree less than k。

Then we know that T can be simplified away。So after we have coalesced。

 T will be able to be simplified。And so what this means is that。The coalescing of x and Y。

Is not going to impact。诶。It's not going to cause T complications with T。The neighbor。

So essentially the heuristic is if I merge them together。In this coalesce node， either。嗯。

It had degree lists every neighbor of this coalist node X already had degree less than K。

 so it can be simplified away or really interfered with Y。 So by coalescing them。

This coalescce node is going to have degree。Less than。

It's not going to significantly increase the degree of the coalesce node。Sorry， there was a question。

Would you want to also check the Hifaceic？Like the case with Y for every liberty of y， either T or。

 Yes， if you can swap the roles of x and Y here。 So this coalescing x and Y is a symmetric thing， so。

Yeah， swap the oil of X and Y and if that's satisfied， then it's safe to coalesce them。Okay。

So the point is that。These two heuristics。Are identifying situations where it's going to be safe to coalesce nodes in the sense that as we talked through。

 it's not going to make a graph that is k colorable。And produce a graph that is not kcolable。

And so if either of these heuristics are satisfied。

 then it's going to be okay for us to collapse the notes。Any questions about these heuristics。

 we're about to see them in action soon。O。So。Let's talk about the algorithm of coloring with coalescing。

It's a bit more complicated than the algorithm we saw with simplification。嗯。But not excessively， so。

 So we start off in the same way。 We build our interference graph。Okay。

 so we have the interference edges in this graph if between two variables。

 those variables are both live at any program point。

But we're also going to be categorizing pairs of nodes as move related。If they are。Sorry。

 I note is move related if it is the source or destination of a move。After we've built the graph。

 we move on into the simplifyimplified phase。That is removing。Nodes with the degree less than K。

 Importantly， we're only going to remove。Non move related nodes。Okay。

 so nodes that are not either the source or destination of a move。After we've removed。

 after we've simplified as many nodes as possible。We go from the simplifyplified phase into the coalesce phase。

At that stage， we look at pairs of nodes that are move related。

And we see if it's safe to coalesce them using either the Briggs or the Georges heuristic。

If we coalesce a node。It might still be move related with another node。

 or it might be non move related。Okay。So we just need to mark that coalescce node appropriately。

Then we move back into the simplified phase。Pre， continuing to remove non move related nodes of law enough degree。

We might get to a point。Where we can't make any more progress with simplifying coalesce。

But we don't have。诶。Right。If that's the case， what we're going to do is pick some low degree move related node。

And freeze it。That is make it non move related， give up on coalescing it。Okay。

 so remember the idea with coalescing is that。We coalesce these nodes， meaning that two variables。

 two move related variables are going to be assigned to the same register。

Great if we can make it work。Not terrible if we can't。😡，Okay so if we can't make any progress。

 we're going to choose a node and freeze it， give up on coalating it， continue with simplifyimpl。

Even if we do that， though， we may get to a point where。There's no more known for us to freeze。

There's no more nodes for us to coalesce， no more nodes for us to simplify。

 just like in the previous algorithm， we're going to need to choose a node to potentially spill。

 we remove that potential spill node， put it on the stack， keep on going with Simplify。

When we get down to the empty graph， we've ended up removing all the nodes。

We then move to the select phase。诶。Where just like we did previously。

 we end up restoring the algorithms。In reverse order， stack order， assigning them a register。

 hopefully we'll be lucky when we get up to a spill node。

 hopefully there'll be a colour available if there isn't。We will need to。Sill that node。

 rewrite the program， go all the way back to the build phase， and try again。

Any questions about the algorithm at the ha level， we are going to work through an example As you or is？

It's definitely advantageous to try both。 What you want to do is。

Coaleesce nodes when it's safe to do so when doing so will not cause you to spill more variables。

So any way that you can reason about， okay， it's going to be safe for us to coalesce those nodes is a win。

So， yes。If it's。If you can coalesce nodes using Briggs， do it。

 if you can coalesce nodes using Georges， heuristic， do it。

Was I mean these two hereur and stick together still don't like？

It's figuring out safe cool like N or something。呃。So is figuring out when a safety coalesce nodes NP hard？

嗯。I'm going to say。I don't have a proof that it's NPHt。I don't know whether it is。

 but it's definitely in general。I think something that you'd need to say， hey if I coalesce this。

 how would this play out？Mean that you'd kind of need to do a search for it。

So really what's going on here with these heuristics is you're just figuring out the conditions under which I know for sure it's safe。

😊，There might be additional conditions where you can figure out it safe without needing to kind of go all the way through the algorithm and figure out if we。

If it introduced more。More spills than other ways。Does that help。And also。So we were like deciding。

What to like freeze or spill or whatever？I didn你再 like。

Do we have some heuristics within those as long do I decide which one？嗯。

LikeI think we've talked about so。Yeah， good question。

 so we definitely talked about heuristics for identifying which nodes to potentially spill。

 we talked about the spill priority， which node should we which node should we freeze。

That is a good question， I can't remember off the top of my head。

What good candidates would be for choosing。嗯。Which node to freeze？😔。

There is in general just one copy。🤢，So if it's x equals y， there's only。

That should be the last use of why。Because there's no interference edge between x and y。嗯。

You might want to do it based on an approximation of the number of times that statement will be executed。

 so kind of just figuring out how deeply nested is that statement en loop。嗯。

It's been a while since I looked at the upheld textbook。

 see if it had a suggestion for the heuristic。Yeah， many。那多。

We're making a distinction between these move related nodes and non move related nodes because in the simplifyim phase。

We're only going to be simplifying away non move related nodes。And in the coalescing phase。

 we're going to be coalescing only move related nodes。 in fact， you know。

 a pair of nodes that are the source and destination of a move。And this is because。

We want to coalesce wherever we can。Simplifying the graph。

Kind of is about removing nodes we know can definitely be colorable without changing without adding any more spills。

 simplify the graph as much as possible to figure out if it's going to be safe for us to coalesce a node。

Once we've coalesced and we go back to simplifying and it's only when we've figured out that you know what。

 I don't know for sure that I can coalesce any more notes that we give up on coalescing。

One pair of nodes， that is the nodes that we choose to freeze。Go back to simplifypl。

 So this distinction between move related and non move related means that we are wherever possible coalescing。

And only giving up on that when we。Can't simplify our way to a better situation。

Hey we abouts still priority。我们。The to the degree and how many intended to use。

 is there sort of a difference between？Would you maybe want to count move related versus non would differently in your priority？

I'm just trying to recall in the spill phase if we would only。

If we're restricting to non move related nodes or not。Oh。

 I dont think so like in the scope priority itself， like when calulating computing scope priority。

 like if you've got two， let's say they're both nonm and one is like。

2K neighbors that are all move related and one has like 2K neighbors that are all non move related。

choicehoice between those which you rather still。是。That is a good question。 I don't know the answer。

嗯。Let's see I think。If you had neighbors that were move related。

The is is they might coalesce at some point in the future and。The degree of the node will be reduced。

嗯。So maybe you'd want to count。Move related as， you know， if I have。

Two nodes that are move related with each other。 and they're both neighbors。

 Maybe I want to count that as less than。Dgree 2。Maybe that's the reason because they might be coalesced。

嗯。It's the only reason I could think of wanting to make a distinction。

Tin move related and non move related neighbours。Any additional thoughts？No， well。

 I can almost see an argument of the other direction too it like you choose one of potentially spell that has lots of neighborhoods that are all move related with each other and like when you add it back。

 chances are good you're going to be able to color if you then go less about those。I mean。

 maybe chances arent good。Right， if you're lucky and move related nodes end up with the same register。

 maybe there'll be more available colors。He。That is a good question， I don't know。It's empirically。

One of the things I'll note is that in many ways it's an empirical rather than a theoretical question because this ultimately depends on the interference graphs that you draw from the distribution that is that you actually see in programs So I think this is hard to do in general to say。

For an arbitrary graph， which is better。Yeah， so I don't know that it's a heuristic of what you end up doing。

Okay， oh， sorry， another question。I no cases but the two years ago。I disagree。のつりやす。No。

 other cases with a heuristics disagree。 Yes， they do in the sense that one might say yes and the other might say no。

 But the key point is if either of the， if either of them say yes， then it's safe to coalesce。

In the sense that coll combining those nodeds together will not cause you to have any more spills。

As long as either works。It's okay to coalesce。Okay。So let's walk through an example。

 here is the laveness graph with two pairs of move related nodes， JN B and D andC。

 let's work our way through it。So we've built the graph。

We saw it often in a simplified phase removing。Non move related nodes of low degree。

So let's start off with G。嗯。Put it on the stack。 Removeve it from the graph。Keep on going。

 H is another non move related node with low degree。Fantastic K。If。And at this point， oh wait。

 E as well。Dgree three。Great， and now I has degree three as well so we can remove that。Great。

 at this point all the remaining nodes are move related。So what we're going to do is。

Check the heuristics。And choose a pair that is safe for us to merge， so let's do J and B。

So we coalesce them， move them together， and now this new node has all of the edges to the neighbors that J and B did before the coalescing。

Great， at this point。To coalesce， we go back to simplify。This new node JB is no longer move related。

 so it can be simplified。And it has low degree， so it can be simplified， removed。

 Now we're back to the colores phase。 we can combine D and C to a single node。

 move back to the simplifyimpl phase。Remove this last node。Color it。Now we have an empty graph。😊。

Fantastic， so we're able to go into the select phase。So here is our original graph。

We remove the nodes in reverse order， so we color first of all， DC。

Their coalesced node that corresponded to the original DNC。嗯。So they get the same color。DNC。

 they were coalesccent into one node， meaning they're going to get the same register one here。

 they do indeed get register T3 Now we color JB。In。A。If and so on。

And we know that the coloring is going to be successful because we never reach the spill phase。

Awesome。So this thing is。The register allocation。Here is the program that we had。Originally。

 we're going to we'm going to replace these variable names with the registers。Okay。

 so that is essentially implementing this register allocation。So's when I do that。

Here are the registers and we'll see that。These two statements， T3 equals t3。

 t4 equals t4 that came from that was the result of coalescing right that J and B ended up getting assigned to the same register so did DNC so these two statements are no ops and can be removed。

Great， so we got the benefit of this copy propagation。

But essentially through this coalescent graph algorithm。Any questions of the moment？Okay。

So this is pretty cool。 right， We have the graph coloring algorithm。

 It can do this nice coalescing thing。😊，However， there's a long way from the algorithm we have。

 not a long way， but there's definitely a gap between the algorithm we have versus the realities we need to face when actually performing register allocation。

😊，So when we think about assigning registers， say for X86。

 part of what we'll need to do is we know that there are some special registers that have to be used in particular ways。

So we have to do things like return the result in register RAX。

We have to take certain registers as where the locations or arguments are given to us for a function call。

嗯。So we can。Take account of that by something called pre coloring。Temps。Okay。嗯。Basically。

 you can think about this as。We could include in our program。That uses these virtual registers。

 uses these temp variables。You could also imagine including assignments to actual registers。

And treat those actual registers as temps that have their color already assigned。嗯。So in general。

 this idea of we might have an interference graph where we have precolored some of the variables saying that this variable has to be used in that register okay so that's going to let us get some of the way towards meeting the requirements of a machine。

Soir。For example， one of the ways we can do this is。When we have a function。

We have some arguments that are going to be given to us。We can。At the very beginning of our function。

Put in some explicit assignments， let's say from RDI into argument 1， from RSI into argument2。

AdiI and RSI are going to be precolored。Tempories。We're assigning them into a temporary for the first argument that gets used in the program。

嗯。So that within the procedure body， within the function body。

 we're using the temp that corresponding to AG1， AG2， AG 3。呃。

Register allocation will hopefully coalesce。😡，Og one with。RDI。Meaning that we'll end up using。

They're registered directly。In our register allocation。But we give the Reg allocation algorithm。

Flexibility。Even though it's receiving the argument in RDI， it's got the flexibility to。

Put that into a different register to spill it， whatever it wants to do。O。

We will see an example of this to make sure it's。To clarify what I mean by having these assignments。

 adding these assignments at the beginning and at the end。Okay， so。Precoled temps。

Will help us to handle the calling conventions for where we we have to return results and that we're going to receive arguments in。

A couple of notes on these precoled nodes。嗯。Precoled nodes can't be removed during simplification。

 right， The idea of removing a node in the simplification phase is that， hey， we don't have a。

Color for this node yet， but I know I'm going to be able to provide one in the future。

That's not the case with a precoled node， we have a standard a color we need to keep it there。嗯。

In a similar way， we can't spill a precolored mode。Right。So what's going to end up happening is。嗯。

In our simplified phase， we're never going to remove a pre-colored node and our algorithm is going to stop when all the nodes we have left are pre-colored so instead of when we get to the empty graph。

 it's when we get to a graph containing only precolored nodes。Okay。Like I say。

 we'll see an example of the soon， but any questions at the moment on this idea of。

Using precoled nodes as a way of capturing this part of the calling cange。

Registers where we receive arguments， registers where we should return results。Yeah。

 so right now this doesn't touch like call me， say， Po save that stuff。Great。

 so callly save and call Lea are another important part of calling convention。

About which registers are okay to use。 And ideally， our register allocation algorithm。

 not just ideally， our register allocation does need to take that into account。

 So we're going to take this idea of。Precoled nodes and think about how we extend it for coolly and call low save registers。

I'll get there it's on the next slide， but before I get there any questions about this。

Tweak to the algorithm。Okay。Collly save registers。Here can thinkHere's a way to think about this callly save register。

So remember， Corly sor is one that if we， the coley， the function， wants to use it。

 we need to save it and restore it。One of the ways you can think about this is a quarterly saved register is defined upon entry to the procedure。

That is the value in that callly registerer might be set defined by our caller。

And it's used at the very end。😡，RightAs in we need to。

Make sure that the value in the Qual save register is the same as it was at the beginning。

So it's kind of like that cool saved register is going to be live out at the end of the procedure。

 it's kind of like it's used at the very end。The trick that we're going to do。

Is move a quality save register into a fresh temporary variable。

So if register R is a cool saved register。At the very beginning of the function。

 we're going to say P equals r。So assigning R into a Fer register。At the very end of the procedure。

 we're going to say r equals4。Restoring their value into the Q save register。R。

The Corlyover register is precoled。To be that specific quality save register R。

And then we've got this fresh temp， foo that is livethe throughout the entire function。

B is not actually used except at the very end to restore R。

So this actually gives our register allocation algorithm a lot of freedom。Right。

R and F are move related。So maybe it'll be able to coalesce them。Right， meaning that。Essentially。

 we're not going to use that coolly save register in our function body。Fantastic。

But if that doesn't work out， if it's going to be better for us to be able to use that register R。

Well， it turns out that that fo temporary variable we created is going to be a really good candidate for spilling。

It's live throughout the whole function， so it's got a really high degree。

It interferes with every single other variable， but it's only got one U， one definition and one use。

So that might well get spelled and that's actually a fantastic variable to spill a quarterly saved register。

 that's exactly the kind of thing where you want to take that value from the register。

 put it into the stack， freeing up the register for use in the function body。😊，Restored at the end。

Okay， so this trick。Of。Assigning from a Cor save rerant for a fresh temp at the beginning of the procedure。

Restoring it at the end gives our coalesitioncing register algorithm。

The flexibility to do something good with it。 and in likelihood。

 it's going to do something well right， not touch that register if。It can compile it without it。

Or have be a good candidate for spelling。If it is。Okay。So that's called Lea registeristers。

What about core low save registers？So let's think about a caller save register。

 I suppose we have a caller save register R。Basic idea is。If we had a temporary variable。

 so a local variable that we want to allocate to a register。You don't want to put it into register R。

😡，If that variable has to be live over a function call。Because if you put it into that register。

The coolley is free to change it。So what we're going to do is。When do we have a function call？

We're going to treat that function call as defining all call or save registers。

As an assigning a new value。And to every single call or save register。So what that means， well。

 first of all， that's kind of an appropriate way to think about it because the core Lee might end up overriding that call or save register。

 putting a new value into it。So what that means is that。

If we have any temporary variable that's live across a function call。

It's going to interfere with that call a save register， a precolored node。

For their call a save register， because it interferes with that。Call a saveve register。

 our Reg allocation algorithm will not assign that temporary variable into the call a save registerister。

They interfere with each other， so there's an edge between them and the interference graph。

Their caller save register is precoled。With Reg R， meaning that we can't assign Reg R into that temp variable that's lay over the function core。

Whoops， sorry。Hit the wrong button on my remote。Okay。

 so this is the key idea for this way of using our coalescing register allocation algorithm to take care of core or save registers。

 again， this idea of preed precolored variables representing registers and when we have when we're building up the interference graph。

Few were retreats。A function call as defining all call or save registers。

This will help us put up an interference graph that will prevent any temp that's live across a function call from being allocated into a call save register。

There's a subtlety here， this note here for how you actually need to implement your algorithm for constructing an interference graph to make sure that you get the right interference。

Itges but。So if anyone ends up doing this for homework sex， pay attention to this bullet。Okay。

 let's see this idea of precolored temp in action。This example shows。Mainly the。呃。

The cool Le save functionality。So here's a C like function。

 let's assume that we have three registers， our one our two are three。R1 and R2 are coreera。

 r3 is called Lia。Let's suppose that arguments have passed in R1 and R2。

And our one is where we return results。Okay。So what we're going to do is come up with a version of this function。

In our intermediate language。That is explicitly referring to R1， R2， R3。 so here it is here。

So first of all。C is a new temporary variable that we created。To store the core save register。

 so we have this R3 equals C。C is not used in the body。

Except at the very end here where we assign CNN to R3。So this is us taking the initial value in R3。

 saving it away， restoring it at the end。The arguments are passed in R1 and R2。

And so here are arguments A and B and here we're explicitly assigning。From r1 into A， from R2 and B。

In our interference graph， these variables R1r2r3 are going to be precolored。And so ideally。

 our algorithm will end up doing coalescing and just treating B as using R1 and so on。呃。

Let's suppose our calling convention is that we return the value in R1。

 so here we have that line returning D is assigning D into the register R1。In this simple example。

 I don't have。A call to another function。So we're not going to be demonstrating how we handle。

Implicit assignments to call or save registers。Okay。

So this is what I was mean by transforming the program to explicitly talk about the registers。

Let's think about our phases here， so our first phase is building the interference graph。

In this interference graph。Leave it as an exercise for you to figure out liveness information。

But note that we are using our one， R2 our three as precoled variables。So in our program。

 they were referring to the physical registers so they're colored appropriately。

There are appropriate move related edges， for example， from R1 and A。From this assignment。R1 and D。

From this assignment down here at the end。Com。And interference edges， meaning that。诶。

Because A and R2 are alive at the same program point， we can't use register R2 for A。O。

Any questions at the moment？Okay。So we move from our build phase into our simplified phase。

There are any nodes here of non move related nodes of degree less than three。

Non move related non precolored nodes of degree less than three。I see some shaking heads， no。

 there's actually no node for us to simplify。So let's move on to the coalesce phase。嗯。

I'm not going to get you to check Briggs and George's heuristics right now。

But I will tell you that none of these nodes can be coalesced。Okay。If you remember the freeze phase。

 freezing was where we would take a move related node of degree less than K， less than three。

 and stop it being move related。We don't have any of those。

 all of our move related nodes are of high degree。So what we're actually going to do is move all the way。

😊，Into。The spill phase。So we're going to pick a good candidate to spell。Turs out。That's C。

Is a really good candidate。So we're actually going to Mark C for spilling。And remove it。

Now we'll go back and we'll look at the code later。

But I do want to say that C was the temporary variable we used to save the Co save register。

Which as I mentioned， that's good that we spill that node。Right。

We don't actually do anything with it。 We're just saving the value away to restore at the end。

 So it's a fantastic candidate for spelling。😊，嗯。Alright， we need to。

We move back into the simplified phase。No spl is possible。However。

 when we move into the coalescce phase。😊，We can coalesce some nodes。

 so we're going to coalesce A And D。 Again， you should check to make sure that one of the heuristics is satisfied。

 indicating that A and E， it's safe for us to coalesce them， but we do。 we collapse them together。

And that is the result in graph。呃。After coalescing， we move back to simplify。

No simplification possible， there's no non colored non move related nodes。We go back to coalescing。

Here it turns out we can coalesce B and R2。So we're going to do that。

 we combine BNR2 into a single node。Which of course remains coloured with the Reg R2 Yeah of course。

When you have a moon relatedness like R18？I do just ignore all of these， all of these。

Nos during all us。Do we ignore all of these nodes？Sorry， which nodes are you talking about？

For example， oh no， this is， we could still do this。 We can still。呃。When't we coalesce？

You can implement it how you want， but one of the reasonable things to do is just pick。

 check if there are any nodes that can be coalesced and if there are coalesced those nodes。

 then go back to simplifyplify It doesn't really matter whether they are move related to anything else。

Whatever thing you're coaling with。Oh， you mean， sorry。

 I don't think I'm understanding your question。 For example， like A and R11 A wants to co with R1。

 Does it need to check anything about， for example， whether R1 is。Mo类的9击。Oh呃。I see。

 So when we're considering whether R1 and Ae could be coalesced， No。

 we don't need to consider anything special about D。 This is just to say that。You know。

 there's R1 and this node。This new node AEE are the source and destination of the move。

The fact that R1 is the source or destination of a move with D is not going to affect whether or not we can coalesce。

These two。 So that's why。Yeah， you don't see that appearing in the。

Heuristics for determining when it's safe to coalesce node。Yep。嗯。

And then I think a typical way of implementing coalesce is to simply coalesce one pair。

 go back to simplify because employees。Pretty cheap and easy to do and might enable more coalescing。

As opposed to trying to coalesce all the pairs you can。Which yeah。Okay。Great。

 so we call list an node， we know go back to simplify nothing new that we can simplify。嗯。

We can keep on coalescing our1 and AE。So combine those together。诶。Move back to simplify。

Note that these are not move related anymore because there was an interference edge。Between them。嗯。

So D is now non move related in the simplified phase， we can simplify it away。

This is the graph we're left with， which consists of only precoled nodes。So we're actually done。

We move to the select phase。Okay， so select phase。Here is our original graph。

Where we've already colored the nodes that were coalesced with a precoled node。Right， so A& E。

Are going to be an R1， B is going to be assigned to r2。We go through our stack D。

 we know we can colour。嗯。So we pop it， we color it。Now we need to look at C， can we color C？

We cannot colour see Sea us actually neighbors with。Yellow。

Purple and green are three available registers。So。We're going to actually need to do a spill。

Rewrite the code and try again。But as I mentioned。This is kind of fine。

 right C was the temporary we were using for the cool save register。Okay。So let's go back。

 look at our code。That we had。So here we had our temporary variable C。Started into R3。

 we're going to rewrite the code to explicitly spill C。So splitting C into C1 and C2。

 C1 is stored into the stack。And down here， C2 is read from the stack and then used as previously C2 equals r3 sorry。

 C2 was assigned into R3。Okay， so this was us explicitly rewriting to spill C。To the stack。

 read it in before we use C。So we're able to take this version of the code。😊。

Go all the way back to the build phase， build an interference graph。

 It's very similar to the graph we saw previously， except we now have a node for C1 a node for C2。

All right。So。Let's start， we can't simplify， we're going to coalesce， see1 in R3。

And then later on C2 and R3。Great， so that's exactly what you want。Okay。

We'll keep on going through the algorithm just like before we're going to end up coalescing A& D。

And then B and R2。Like so。诶。Then we're also going to keep going coalesce AE and R1。At this point。

 we can simplify DOA。Okay。Fantastic。Only pre coloured nodes are left at this point。

 So we're ready to move on to the select phase。Okay， so going back to Al。Original graph now。嗯。

Due to coesing。We had C1C2 B， A& D， we were already colored。

So now we get to P D and color it successfully。Fantastic。嗯。And at this point we're done。

 we successfully coloured the graph。 We now have a register allocation。

So let's go and look back at Alcode。That we had here。

We're going to do the same thing where we take our register allocation and I'm going to replace the temporaries with the register that we actually used。

For them。So if I do that。We now have。The following code， which is closer to assembly。

 is now using only physical registers， O tempemp。And you'll see that due to coalescing。

 we ended up with a lot of these essentially Nped， r3 assigned R3。I want to sign out one。

 two assigned our two， I want to sign out one， so on。 So we'll actually remove those statements。

Giving us much more succinct code。And it turns out that we only have one non coalesced move。Here。

 this one from R3 into R1。Which？Three which I believe was this one here。D。Okay。

So this is our coalescent graph coloring algorithm。

Where we're able to express a lot of the machine requirements。Through the use of precoled nodes。

We were able to get calling conventions about what gets passed in as arguments where things get returned。

 we saw call save， I wave my hands about call li save。

 but believe me you can end up doing it by essentially having these explicit pre-colored variables R2 R1R2R3 and treating function calls as implicitly defining or assigning to the call call lia registers。

Any questions about this algorithm？Hands up if you think you're going to implement it。

Maybe a couple of people， it is fun to do。嗯。I will say。

This algorithm that I've kind of presented for register allocation。That is you've got temporaries。

 you want to figure out which of the small number of registers you want to assign them to。U。

Turns out you also want to do a similar thing for stack slots。 right。

 So remember that if you end up spilling。A variable to the stack， you want to kind of say， all right。

 I want a stack slot。To store with that variable in。Right。嗯。

You kind of want to do something similar with these stack slot。

 You want to assigns them to physical spaces in the stack。Such that， if you have。2。s。

Let's call them virtual stack slots that are livethe at the same time。

 they can't be assigned to the same physical stack slot。But on the other hand。

 if you do have two of these virtual stack slots that do not interfere with each other。

 it's great if you can reuse a physical location， you're reducing the amount the size of your stack frame。

😊，So it turns out that this kind of stack slot allocation problem。

Is pretty much exactly the same as the register allocation problem right。

 You've got a number of these virtual stack slots that you want to assign into some number of physical stack slots。

 It's a little different because you get to choose the number of physical stack slots you want。

 but you kind of want to find the minimum number of stack slots that will let you。

That will let you assign your virtual stack slots into the physical stack。

So if you end up implementing an algorithm like this， if you're really， really cool。

 you can actually write it so it's polymorphic and the same piece of code will solve not just your register allocation algorithm。

 but your stack slot allocation。😊，Problem as well。Okay， that's all I have for register allocation。😊。

Hope you all have a wonderful Thanksgiving break， chance to rest and relax a bit as well as of course working on homeworks。

 but make sure you get some time in there to rest and relax。

 and we're going to continue after Thanksgiving with a variety of topics。

 including object orientation and we'll see what else。Thanks very much everyone， see you in a week。

What。Okay。な个？日で。

![](img/dda0d6744ae5c37c28a7c266a2f25315_3.png)

But just in general， is it？Is it possible in general like is the general strategy that most compilers use to just treat them as like？

These are inputs of the register alligator or is like do they usually try to reduce them as much as possible I mean like I don't know what fire reduction really is like。

 but like I can imagine situations where like you only，啊。By e static analysis。

 you can discover that like you only have a write to this location or something。

 and you never read from it like okay， it feels like I don't need it or in the Congress like this situation where you。

Only ever assigned who once， like only in the entry block。

 I don't know how to reason well enough about any other block but like if it's the entry block is the only place like stack slots1 I mean the SSA so we know that about that。

 but like it Macality is yeah yeah。I mean， obviously I can just like Yeah。

 so the finite reduction is。Typically about something else I think so final note it is。

Let me just take my way through this。 We don't with this iPhone， we really have。诶。Maybe justYeah。

 I thought there was a past like that LVM or like a clean pass it like policy。

Phone nodes are when you。One morning， is kind of a essay form。

 but it's normally occurs when you are translating and you have like I cant imagine situations where like you only。

ああ。By static analysis， you can discover that like you only have a write to this location or something。

 you never read from it like， okay， it feels like I don't need it or in the Congress like the situation where you。

Only ever assignment who once， like only in the entry block。

 I don't know how to reason well enough about any other block but like if it's the entry block is the only place like stack slots I mean the SSA so we know that about that but like I mean is yeah。

I mean， obviously I can just like Yeah， so the finite reduction is。Typically about something else。

 I think okay so final note is。Let me just take my way through this。 We don't。 with this a safe。

 we really have。诶。Maybe justYeah， I thought there was a past like that LVM or like a clean pass it like H。

Phonots are when you。One morning， is part of a essay form。

 but it normally occurs when you are translating and you have。



![](img/dda0d6744ae5c37c28a7c266a2f25315_5.png)

Verable X is assigned on。