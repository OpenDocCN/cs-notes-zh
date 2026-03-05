# 伊利诺伊大学【中英⚡算法｜CS473 Fall 2022 Algorithms】 p18 P18 17maxflow structure -BV1RdBTBrEdx_p18-

Let's go ahead and get started。

![](img/4c05cbcb4b0d86f973ee3ae3f12a2951_1.png)

嗯。Nothing。Significant to announce in terms of administration。One thing that perhaps。

I should suggest with respect to the homework。This is not a good homework to split up amongst your group members。

Solving problem one will help you solve problem two。

 solving problem two will help you solve problem three。

If you try to just start problem three by itself， a couple of people discovered there's a bit of a hill decline because you didn't solve one in two already。

The other piece of advice that I would give。We are no longer in the land of string algorithms。

Some algorithms take longer than linear time。😡，So just because you can't see a way to do it in linear time doesn't mean that you don't already have the fastest algorithm。

😡，UThe other thing about this is we're in the land of graph algorithms。

 we don't know how to prove that anything is optimal。😡，So the idea that you'll be able to like。

 is this the best I can do， I don't know， nobody knows。

And I'll talk about that a little bit in class today with respect to like running times for max flow and cut algorithms。

We don't actually know what an optimal running time is。

Other than you have to read the you have to look at the whole graph。Right。

 so there are a lot of things where。The best algorithm we know。U runs in some large polynomial。

 relatively large polynomial time， like we don't know how to compute。

 how to decide whether a graph an undirected graph contains a triangle。Faster than。

 well we know how to do it faster than V cubed time that would be Floyd Warsholll and you do it by recasting it as a matrix multiplication problem。

But we don't know how to multiply matrices faster than end of the 2。381527， blah， blah， blah， blah。

 something or time and that number keeps changing every few months。Most recently。

By the most recent reduction in that exponent was on the order of 。0002。嗯。It's been 0。

23 something for a while， it's been 0。231 something for a while。

Now it' I don't remember what the actual number is。But u。And this change in 0。

00 is 02 and the exponent is a 30 page paper。😡，So it's a really significant hard work。

If you get down to a running time， that is some nice simple looking polynomial in the number of vertices and edges。

嗯。Play with it again later， but write that down first。

Okay because you might actually have found the best simple algorithm。

 which just really all we're asking for in the homework。看。All right。Good。So。

We have been talking about。Maximum flows and minimum cuts。

So just let me remind you about definitions， what the input is， what the output is。Okay。

 so the input。Is something that I refer to as a flow network。嗯。This is a type of network。

 a network in which we will put flows。This consists of a directed graph。

Which is almost always referred to by the letter G。Um。Two vertices。S and T。

 which are mnemonics for source and target。And we're given。Capacities。So for every edge。

You have some capacity， which well。Without loss of generality， I can assume is positive。

that's what the input is。U。The maximum flow problem。We want to compute。

A function from the edges to the reels。That satisfies。Three conditions one is。

That every flow value that we attach to an edge。😡，Is non negative。

The second is that every flow value that we attach to an edge is less than or equal to the capacity of that edge。

And the last is that we have flow conservation。Flow into V。Is equal to。Flow out of V。

Except where S except at S&T。Okay， so。The third condition is what makes the function of flow。😡。

Having conservation at every vertex except the source and the target。

The first two conditions is what makes that flow feasible。And then what we want to maximize。Is。

The total net flow out of S。So， this is。As to W minus。To flow。Into us。So that absolute value of F。

I'll usually refer to that as the value of the flow。

The language here is a little bit unfortunate because I want on the one hand。U。Some word to describe。

The flow along an edge。😡，And sometimes I will use the word flow value for that number。

 I will try as much as I can to use the word flow amount or something similar。

 the amount of flow along that edge。And reserve value for the value of the whole flow Now notice that the value of the flow here。

 absolute value of F。This is not。The total amount of all flow across all edges。😡。

It's only the net flow out of the source。😡，Or by conservation， the net flow into the target。嗯。嗯。

The other problem， the minimum cut。Is。I want to compute。A partition。Of the vertices into two sets。

 S& T， which are disjoint。So some that square bracket is。Unfortunately。

 there really is no standard notation， but to sometimes use that square u to mean disjoint union。

 that just means it's the union of two sets and oh， by the way。

 the two sets are disjoin from each other。😡，Um。And what I'm trying to minimize。In this case。

 which I'll refer to as the capacity of the cut。Is the sum of the capacities of all edges that start？

😡，In S and end in T。Sorry。OhAnd I guess I do need to make one。And pose one more condition on this。

Which is that little S belongs to set capital S and little T belongs to set capital T。Then。😊。

So the input to the max F in cut problem， there's a flow network。😡，Directed graph。Source in a target。

Capacities attached to every edgech。The maximum flow problem asks to attach a real number。

 a second real number to every edge。😡，such that it's between zero and the capacity at every edge and the net flow in is equal to the net flow out at every vertex except S&T。

 and I want to maximize the net flow out of S。😡，Intuitively。

 I'm pumping water into an assemblage of pipes at S and extracting the same amount of water out at T。

 and I don't want my pipes to blow up。😡，The minimum cut problem， same input。

 now I want to partition the vertices into two subsets， one that contains the source。

 the complement contains the target， and I want all edges crossing from the source side to the target side of that cut。

😡，The total capacity of those edges to be as small as possible。

And the infamous max flow Min cut theorem says that。B。😔，Max。Flow。Value is equal to。The men。

Cut capacity。And along the way， deping the max Fing cut theorem， we saw a condition that tells us。

Whether a given flow is a max flow or not。😡，Namely， you build the residual ground。

And then if in the residual graph there is a path from S to T。

 that means you can make the flow value larger by pushing flow along that path。

 so the flow that you started with is not a maximum flow。😡，On the other hand。

 if there is no path from S to T in the residual graph。

 then capital S you can take to be the set of nodes reachable from the source。😡，Capital T。

 you can assume to be everything else。This defines a cut， and。嗯。

Every edge that crosses the cut forward is saturated。

 every edge that crosses the cut backwards is empty。

 and that implies that this is a minimum cut and a maximum flow。Hey， so。We get an algorithm。

This is the forward focusson algorithm for。It's usually described as a maximum flow algorithm。😡。

But you do also get a minimum cut out as a side effect。

So I start by setting the flow value to be zero everywhere to every edge sorry every edge has zero flow going across it。

 so I assign the amount zero to every edge。😡，No嗯。And。

That means the initial residual graph is just going to be the original network。And then。While。

There is a path。From S to T in this residual network。U。Augment F。Along。That path。And then recompute。

There was a dual graph and then at the end return off。嗯。Okay。

You're going to build a piece of code to。😡，Compute maximum flows。This is what you would implement。可。

嗯。Now。The proof of the maxloin cut theorem implies that if。Yes。This algorithm halts。

It returns a maximum flow。咁。😊，Because the condition of do we have a max flow or not is？😡。

We have a maximum flow if and only if there's no path in the residual graph for et T。

So that's exactly the condition where this algorithm holds。Okay， but now the question is。

 how many iterations do I need？Okay， and this is most of what we're going to talk about today。

So before I go on。They just need to make sure that everybody's on the same page with。

what this algorithm is doing， what we're computing。What these flow things are。Yes。Yeah。

 every step inside the while loop is linear time。So finding。😡，Finding a path from S to T。

 that's whatever for search。Augmenting the flow along that path means for every edge on that path。

 if it's an edge in the original network， I add flow。

 if it's the reverse of an edge in the original network I subtract flow。

 that takes time proportional to the length of the path， which is order V。😡。

tThen I need to recompute the residual graph if I did that from scratch it would take order e time。

 but in fact I can update the residual graph as I'm updating the flow so this part，😡。

Takes order E time， this part takes order v time， which is less than order E。

And so the only thing that we need to figure out is how many iterations the while loop needs before the algorithm halts。

Is there any situation where it doesn't point， yes？

There are situations where this algorithm doesn't hold。That's why that is a big if here。

It doesn't always halt and we'll see a concrete example of this in a second。ok。嗯。So。不这。😡。

I want to first give an example that shows even if it halts， it can take a very long time。😡，Okay， so。

There's another sort of side effect of the way this algorithm works。😡。

Is that if all the input capacities。A integers。Then the maximum flow is that this algorithm computes。

Is also。Interegral。Meaning the amount of flow along every edge is an integer。

 the value of the flow is an integer。U。Everything's an integer。

And the proof of this is by induction on the number of iterations of the algorithm。

 so if I jump into the middle。😡，Let's assume as an inductive hypothesis that all my residual capacities are integers。

😡，Then I find a path per S to T in the residual graph。

 I look at the minimum capacity among all those residual edges well the minimum of a bunch of integers it's an integer。

 so I push that integer amount of flow through the network。

 every flow amount up goes up or down by an integer。

 so now again all of my flow values are still integers and so all my residual capacities are still integers。

😡，Okay， yes。It means that。Once you compute the maximum flow， if you look at any edge。

 an integer amount of flow is going across that edge。😡，As opposed to one half。Or square root of pi。

Right。W whichch now this does not mean that every maximum flow。😡，Is an integer？

So here is a flow network。So when I draw flow networks， I tend to try to remember。

 always put an arrow into the start vertex kind of like this is a DFA and an arrow out of the target vertex。

😡，So let me give these things capacities。Each of these things has capacity one。

And now here is a maximum flow for this network。😡，Well。

 I send one unit of flow through this last edge， but I'm going to send one half unit of flow。

Through each of these other edges。And again， the notation here is when I write two numbers。😡。

With the slash， the first number is the value of the flow。The second number is the capacity。So。

Through these edges each of these edges on the left。

 I'm sending one half unit of flow out of a possible one unit of flow of capacity。😡。

So this is a perfectly valid， perfectly legal flow that Ford Fkerson will never compute。

This is something to keep in mind also for the homework。

A flow does not mean a flow that Ford Fguerson would compute。😡。

You can have all sorts of bizarre looking things that fit the definition of flow。

 even though there's no way to force Vol Tokson to output those things。Okay。

This is also an example where the maximum flow is not unique。😡，I could have sent you know。

 any number， any， any number less than one。😡，Through the edges above the diamond and one minus that number through the edges along the bottom。

Com。But。If I run For Fguson on this same graph。😡，What I will get is。Yeah。

So I erase all the red stuff。T to erase only the red stuff。

What I would get is something that looks maybe like this。The first iteration。

 I would send one unit of flow through that top path。😡，At this point。

 the edge on the right is saturated， so it disappears from the residual graph。

 and that was the only edge into T， so that means there's no more paths from S to T in the residual graph and now I'm done。

😡，And there's my maximum flow。And all of the flow amounts are integers。Okay。😊，Now。

 one of the side effects of this is that if all of the capacities are integers。

 Ford Fkerson is guaranteed to terminate。😡，Because every time I push more flow along an edge。

 I'm pushing at least one unit of flow along the edge。

 which means I'm consuming at least one unit of capacity on some edge。😡。

And there's only a finite amount of capacity lying around。Okay， but。So in this case。Forod Fkson runs。

In big O of e times the value of the maximum flow time。😡，AllThis really crude upper bound。

If in the end， the maximum flow has value 65，000， the most I can say is that this while loop。😡。

Look at most 65，000 iterations。hi is a little unfortunate。And in fact。

It's even more unfortunate because this analysis is tight。😡，So here is。Um。A。Nice looking。呃。

Fone network。X is some really big number， let's just say x is bigger than 10。😡，The precise value。

Doesn't actually matter， okay， in deference to the Romans， x is greater than or equal to 10。嗯。

So I'm going to run Ford Fguson on this network。😡，And I'm going to do it in such a way that amount of flow。

 the flow value increases by exactly one。😡，At every iteration。So。My first iteration。

 I'm going to choose this path to augment along。Perfectly reasonable path from S toT。

The minimum capacity along that path is one， so I can send one unit of flow along that path now that central vertical edge is now saturated。

😡，So in the residual graph， that edge doesn't point up， it points down。😡，So in the next iteration。

 I'm going to send flow along this path。😡，Now the total net flow that I've sent across that vertical edges zero。

 I sent one unit up and then later I sent one unit down， so now that edge is empty。

 so the vertical edge is pointing up in the residual graph the other edges on the outside。😡。

Those all have residual capacity x minus1， and their reverses show up in the residual graph with capacity one。

😡，But I'm just going to keep alternating between the pink and blue pads。😡。

Every time I push along one of those paths， I'm pushing exactly one unit of flow。😡。

And the algorithm doesn't halt until I've used up all of the X's。😡，Okay。

 so if I choose my paths badly。Then the number of iterations。Is。

Equal to the value of the maximum flow， which is equal to 2 x。

Okay the only way that we can make progress here。Is by。嗯。Not choosing those paths。😡。

But making a smarter choice about which pads we augment flow along。Okay。

A in this case is a constant so here we get running time that's proportional to F star the the other thing I want to point out is。

That's exponential time。😡，The number of bits that I need to write down in order to specify this input is a constant times big O log X。

😡，I need log X bits to write down X。😡，But the running time of my algorithm is proportional to X。😡。

The value of x。😡，So I've written down， say， 100 bits。

But then my algorithm needs to run in time two to the 100。So this is。

 I know it's a nice simple looking expression， but anytime you see an actual numerical value in a running time that as opposed to its log。

😡，That's an exponential time algorithm waiting to happen。All right， now。

This is as bad as it gets when things are integers。😡，嗯。But if we。Allow。Non integer capacities。 Well。

 if they're all rational numbers， we can scale them up。

 They're all integers and then scale the flow back down。 that's fine。

 But if we allow irrational capacities。Then here is a lovely little slow network due to Boeseviic。

He's an Israeli。Computer scientist。Who。Does a lot of cool things。One of the the。

Coolest things he's done。Together with Mike Patterson at Warwick。Is he gave a complete。Analysis of。

Game Jennga。So most games。Are interesting only because they're hard。

Most games are fun only because the process of playing them perfectly。

 if you think of it as a computational problem is NP hard or piece based hard or exponential time hard。

 Genenga has a perfect strategy that you can put on a business card。😡。

That basically you just count how many layers there are of each of the possible patterns do one line of math。

 and then that tells you what move to make。So the theorem is Jenga is only fun if you're drunk。Okay。

So here is VI's network so again X is some large number， phi is squared to5 minus1 over two。

 this is the small golden ratio。😡，Okay。Now I'm not going to walk through the details。

 but i'll at least tell you how the augmenting strategy works in the first iteration I'm going to go along this sigzag。

😡，And then in the next iterations。I'm going to augment along paths。That look like the following。Okay。

 in the next iteration。I'll augment along this path。And then I'll augment on this path。

And then I'll augment along this path， so if I call this path A， this path B and this path C。

 then I can actually do the pattern， you know S for the first one， then B CB， B A， B CB， B， A， B， CB。

 BA， etc forever。And what happens is those three horizontal edges。The amount。

 the residual capacity on those edges is always going to be some power of phi。

 so initially that's feet of the zero feet to the zero and feet to the one。😡，Every time I go BCDA。

 those exponents will go up， I think by two okay so the amount of flow that I'm pushing at each of these iterations is one。

 and then B because I'm going through that edge it's phi， then phi， then phi squared。

 then phi squared， then phi cubed， then phi cubed and so on， and so the total amount of flow。

 the total flow value that I'm going to get。😡，Turns out to be one plus the sum over all I greater than equal to one of feet of the eye。

 which is less than seven。That's a geometric series。Remember fee is less than one。

 so this converges to some finite value。The actual value is something like four times the square root to five。

 but whatever， but it's less than seven。So。If I take this network as input and I augment along this pattern of paths。

 the augmenting path algorithm runs forever。😡，And it converges to a value that is not the maximum flow value。

 the maximum flow value in this network is 2 x plus 1， I can send x units to flow down the left。

 X units of flow down the right and one unit along that lightning stroke in the middle。😡，Right。

 so this is。Less than2 x plus 1。Right。嗯。So it runs forever and it doesn't even converge to the right value。

😡，All right。嗯。Now， I am sure at least one of you。Had a question pop into your head。

 the moment I said。This word。系。If we allow irrational capacities， then things go bad。

But computers don't store irrational numbers death。They store numbers that are made out of bits。

There's no such thing as an irrational number in the computer memory， well， okay。😡。

If you insist on using the standard binary representation， in this case， I can represent numbers by。

😡，rationational plus rationalal times square root to five and take that pair of rational numbers as my representation and implement all of the arithmetic and would still work。

 but find point taken under normal circumstances， you can't deal with exact irrational numbers。😡。

So why do I care？First of all。The theoretician's answer， the mathematician's answer。

That's an artifact of the laws of physics， which are utterly irrelevant in this class。

I want to think about the computation at a layer level of abstraction that allows me to ignore。😡。

How numbers are represented when I can most graph algorithms are analyzed under the assumption that you can do arithmetic in constant time Dyketra's algorithm doesn't care whether you're as long as you can add numbers quickly。

 Dyketra's algorithm runs fine， Belllman Ford， same thing yarn minimum van algorithm。

 same thing Gaussian elimination， same thing。😡，Lots and lots of algorithms just say let's assume we can do arithmetic in constant time and just count arimetic operations now we know that's not always physically reasonable。

 but it's a reasonable abstraction to adopt in order to understand the behavior of the algorithm in the abstract。

😡，But the second and more interesting reason is。啱。If you really implemented this。

 you wouldn't be doing it with this abstract model， you'd be using floating point arithmetic。😡。

And the interesting thing about floating point arithmetic is it is utterly broken。😡。

If you multiply small positive numbers， the product might be zero。😡。

If you add a small positive number to something， you might get a result that's equal to the thing that you started with。

😡，So the arithmetic that you're doing here involves smaller and smaller and smaller real numbers at some point those real numbers are going to be so small。

😡，That they still come out to be positive。But then if you try to add that flow to something。😡。

It doesn't actually add。😡，You get underflow。Um，And so you might end up either being stuck in an infinite loop where you literally are making no progress at all on the floating point of arithmetic。

😡，Or worse， because floating point aritic rounds in different ways。

 you might end up with your data structures in a state that is incompatible with the original input。

😡，A flow isn't actually conserved at the vertices？And not here。

 but there are cases where there are algorithms where if you get into into an inconsistent state。

 it screws up the logic of the algorithm and your program just crashes。😡，Right， so。

The practical answer is。I'm not convinced that this would halt even with a standard floating point implementation。

😡，And the only way to figure that out is to actually implement it and that's called admitting failure。

😡，In this class。It's interesting， it's important， but again， in this class。Okay， so。

Eventually we're going to have to deal with this case and we will。😡，All right。Questions about。

Bad behavior for Fage focusinggu。All right。Before I start talking about good behavior。😡。

I need to develop。😡，Some。Structure。And this may be helpful for thinking about flows in the humworks。

嗯。So the way that we've defined flows so far is just there's some numbers attached to every edge。

 it's all kind of wishy washy and floaty and hard to get hard it was certainly hard for me to grasp when I first saw it except that you've got this conservation constrained at the vertices。

 so what I want to give you is another picture， another way of describing what flows are that is better in some ways and worse than others。

😡，Okay， so the standard definition is it's an assignment of numbers。Two edges。m satisfysfying。

Some constraints。ok。But the other way that I want to think of it is that a flow is a sum of paths。

And cycles。嗯。So。I'm really going to be doing linear algebra。But。IfIf those words sound frightening。

We're not going to be doing anything with like。Actual linear algebra but。Um。

What do I mean by when I say this well if I take。啊。You know， if I， if I consider two flows。

F and F prime。Then F plus F prime is also。A flow。For any constant C， C times F is also。A flow。So。

If at any vertex。😡，The total amount of app coming in is equal to the total amount of F coming out。😡。

And the total amount of F prime coming in is equal to this total amount of F prime coming out。😡。

Then the total amount of f plus f prime coming in is equal to the total amount of f plus f prime coming out。

😡，So adding。The edge values for F to the edge values for F prime give you a new set of edge values that satisfies the same conservation constraints。

And therefore， it is also a flow。Likewise。As long as I'm I suppose technically I need to make sure that that constant is actually no。

 sorry。If I don't care about feasibility。😡，Sorry， excuse me。Okay。

I don't want to use C because that's already used for capacity。

So doubling the amount of flow across every edge gives me a new flow whose value is twice as big。😡。

Nigating the value of the flow along every edge gives me a new flow whose values the negation of the one I started with。

😡，Now， negating enough feasible flow gives you an infeasible flow。

 but just let's just focus on conservation for now。😡，Yeah。

 you have the saying two edges that go over your capacity I just said。

 let's not worry about capacities for now。Hey， just。Conservation， what it means to be a flow， yeah。

So。I'm getting there， I'm getting there。All right， so。嗯。Ads are。Flows。So if I have a path。

From S to T。Now let's imagine that I send one unit of flow down that path。I can basically equate。

The path is a subset of veres and edges that connect together the right way。With。

The unit flow along that path。😡，So for every path I have an associated flow。

 now there might be other vertices and edges in the graph。They all have low amount zero。Right。

 but I just mean if I choose a path from S to T and send want you to flow down it。

 that is a flow in my network。😡，But I'm going to identify that flow with the path I'm deliberately going to use。

😡，The same symbols to refer to both the sequence of vertices and edges and the function from edges to the reels。

Likewise。Cyclees are flows。So if I have cycle in my graph。

And I send one unit of flow through that cycle。That is a flow。Now， notice。

This is probably not a flow that Ford Fkerson would compute。I noticed I didn't identify S3 T here。😡。

These could be somewhere else from the graph。😡，I just said。

 here is a directed cycle in my flow network。Push one unit to flow around it。

That assignment of numbers to the edges。😡，One along the cycle zero everywhere else satisfies the conservation constraint。

 in fact at every vertex， not just at every vertex of the Scent T， so it is a flow。Now my claim is。

Every flow can be written as a sum of flows of this form。😡，So given any flow in any flow network。😡。

I can decompose it。Into a linear combination of path flows and cycle flows。😡。

And this decomposition of amorphous blob of numbers into a finite collection of paths and cycles。

imposeosees some very useful structure that can be exploited for thinking about flows and for designing algorithms for flows and for designing algorithms that use flows。

😡，So here is an example。Of this decomposition， Okay， so I've got a flow network from S to T。Just to。

Simplify things a little bit， I've added this extra edge。😡，From T back to S。

And put the right flow value on it， so now this has conservation everywhere。😡，Okay， so。

Now those numbers， if I include that edge underneath。😡，Describe a flow with value zero。😡。

There are 15 units of flow coming out of S and 15 units coming in， so the net flow out of S is zero。

There are 15 units of flow going into T and 15 coming out， so the total net flow out of T is zero。

A flow with value 0。Is called a。Circulation。咁。Yes。All right。😊。

And the flow decomposition theorem says any circulation can be written as a sum of cycles。😡。

So one way that I could imagine。😡，啊。Instructing this decomposition of the circulation into the cycles is to say。

 a， let's just pick。😡，A vertex， let's just start， say here at us。

And I'm just going to start wandering around。Eventually。

 as I wander around following edges in the right direction。😡。

I'm going to run into a vertex that I' visited before。😡，Wait。

 how do I know that I'm going to run into a vertex that I visited before， how come I never get stuck？

How can I ever like hit a dead end when I'm doing this？Conservation， if there's flow into a vertex。

 then there is flow out of a vertex， so if there's an edge carrying flow into a vertex。

 there is an edge carrying flow out of that vertex。😡，So I can just sort of wander around la， la， la。

 la， la， la， la， la la here I have wandered around， Oh， I came back to S， great， I found a cycle。

 What is the minimum amount of。😊，Blow among the edges of that cycle， in this case that's four。

So I say， okay。I'm going to extract。😡，Four units of flow along that cycle。😡。

And now this becomes zero， this becomes zero， this becomes five， and this becomes 11。

And I have another circulation。Where the sum of the amounts of the flows has gone down。

But more importantly。At least one edge that used to carry flow now doesn't。😡。

So I've made progress and I've made progress in a way that won't lead to an infinite loop。Hey。

So I found some cycle， doesn't matter what。I looked for the minimum amount of flow among the edges on that cycle。

 and I reduced all of the flow around that cycle by that amount。Pull that off， that's okay。

 four times the red cycle。Then I would do that again sort of。😡，Again， start wandering around from S。

 Well， I can't go to the right。 So I guess I'll go down。And again， I'll just sort of wander around。

 blah， bh， blah， blah， blah， oh， look， I'm back at us again。Now among the green edges。

 the smallest capacity is five， so I'm going to pull off。😡，Five times that cycle and reduce my。

Flolow values again。And again， two more edges went from having positive flow to having zero flow。

Okay。😊，And and repeat， just keep going okay， so the ideas。😡。

Wonanderder around until you find yourself in a place you've been before。

 you've found a cycle that carries flow。Find the minimum amount of flow along that cycle。

 subtract it off。😡，If there's more flow to be had， keep going， keep doing this。Now you'll notice。

It may be that at some point I've removed all of the flow coming into a route of S。

 but there might still be flow somewhere else， so when I iterate I always look for some vertex that's not done。

😡，And start there， I don't always start a this。Okay， so。嗯。Here's the algorithm for。To decompose。

A circulation。If F is not zero everywhere， if F is zero everywhere。

I claim that F is still a sum awaited sum of cycles。Which cycles？What is zero the sum of？

The elements of the empty set。The zero flow is the sum of no cycles。😡，It's just your additive unit。

Okay， if the flow is not zero， find。Any cycle。C， I can do this in order V time。

And if this is not like Brett for search or anything， this is literally。Watander around， blah， blah。

 blah at random until you see your own footprints。It helps when you're doing this to run like a toddler。

Okay。Then lets。We'll let F min be the minimum over all edges in this cycle of the value to flow along that cycle。

Then I'm going to let。F b F minus。F min times the unit flow let cycle C。Yeah。Yes。嗯。

So there's a question about cycles that only have two vertices。

I've been making an implicit assumption all along that in a flow network。

 if there's an edge from U to V， there's not an edge from VDU。😡。

And you can enforce that assumption by just subdividing every edge with a new vertex。

But even without that assumption， this algorithm works。But some of the cycles you get may be trivial。

Every time I run this algorithm， so here Fmin times C， this C is the unit flow along the cycle C。

 heres where I'm conflating the cycle as a sequence of vertices and edges with the unit flow around that cycle。

😡，I'm multiplying that unit flow by this scalar F min。

 and then I'm subtracting it from the flow that you started with。Um， so。Some edge。

That had positive flow now has zero flow after every iteration。So the total number of iterations。

Is at most he？So the overall running time。To compute this flow decomposition is v times Z。Hey。Now。

At some level， this kind of looks familiar。This is kind of the same logic that we used in Ford Fkerhood。

😡，And Ford Folkson says， look for a way to push more flow through the network。

 if you can find more a way to push more flow through the network。

 push more flow through the network。😡，Keep pushing more flow through the network。😡。

I don't care what path you use， pick any path you want， push more flow through the network。😡。

This algorithm says I'm given a flow and I want to tear it down。😡。

Specifically I'm given a flow with value zero， but you can kind of see if I ignore that edge from T back to s how it might apply to flows with positive value。

😡，It basically says。Find a way to delete some flow。Find a cycle that carries flow。

 delete the flow on that cycle， find a cycle that carries flow， delete flow on say。

 I don't care which cycle you pick， if you find a cycle， delete the flow。😡。

But there's one significant difference。Ford Fkerson， you can make a mistake。

 you can push more flow through an edge than will actually be pushed through that edge by any maximum flow。

😡，You can overestimate how useful a single edge is going to be。😡，so you need a one of backing up。

 this is why we have residual graphs。😡，over， you get over excitedted about using an edge and then later go。

 oh， actually， I need to back up a little okay here。😡，I'm not doing any residual things。

As soon as I find a cycle， I figure out the minimum amount of stuff I can delete from that cycle and I delete that。

😡，Every edge that had positive flow value now still has non negative flow value。😡。

So I can keep going。😡，So not only am I getting a decomposition of this circulation into cycles。

 but the cycles always line up forward in the forward direction of the flow。😡。

And this extends more generally to other kinds of flows。😡，More generally any。Flow。Is a weighted。Some。

Of paths。And cycles。That only use。Forward edges。はい。

The argument is the same if the flow value is not zero， I can find a path from S to T。😡。

That carries flow， delete as much flow as I can from that path。

 eventually the flow has value zero and I start deleting cycles。And。嗯。But every path that I choose。

 every cycle that I choose is only using flow in the proper direction， I never am backing up。😡。

So this is basically saying。If Ford Fguerson could predict the future。😡。

You would never need a residual graph。😡，You can always choose the right paths to augment。😡。

So that you'll never use any residual edges。😡，Unfortunately。

 forward focusing can't predict the future。It'd be really nice if it could。The second thing is that。

If you have a flow that doesn't have any cycles in it。😡。

Then you can decompose this into a sum of pads。No cycles。Just because if there were any cycles。

 it would only use forward edges and that would imply there's a forward cycle in your flow。

 but it started by saying it was acyclic。But。This also means that if I take any maximum flow and just start deleting cycles from it。

 deleting cycles doesn't change the value of the flow so when I delete a cycle from a max flow I get a new max flow。

😡，Hit， hit hint， hint， I just said something important if you delete a cycle from a maximum flow you get a different maximum flow。

😡，Um， that means you can take any maximum flow and just start deleting cycles。😡。

And eventually you'll delete all the cycles there are。

 and you'll be left with a flow that defines a dag inside your network。😡。

And it's still a maximum flow。系。嗯。And so what we did is you know this representation。Of any flow。

That has complexity。Big O of v times V。😡，So this at most order E paths or cycles and each of those paths and cycles has length or at most V。

😡，Now， this is a more verbose representation of flows than just a number on every edge。Right。

But this is the representation that at some level， Ford Folkerson is always computing。😡。

Ford Fkson says augment along this path then augment along this path， then augment along this path。

 then augment along this path， Ford Fkerson is giving you a flow as a sum of paths。

Now the bad news is。That there are flows。Where。Every decomposition。Has complexity。At least v times Z。

Yes。So what does this mean？That if you use Ford Fulerson。Even if you could predict the future。

 even if you chose exactly the right path at every iteration， you were completely omniscient。😡。

That's your running time。B times Z can't be better than that because if it could。

 then you'd be computing a decomposition of your flow into not enough paths。😡，Okay。😊。

So this is in some sense， the best running time that we could possibly hope for by any version of For Fguson。

 in fact， more generally any flow algorithm that computes the flow one step at a time。😡，This is not。

 however。An upper bound， a lower bound on the fastest flow algorithm。

There are flow algorithms that don't use one path at a time。

 They compute a tree of flows at the same time， or they compute。B sort of electrical stuff。嗯。

We're not going to talk about those algorithms in any detail because they're hard and I don't understand them。

😡，They scare me， but for anything that you would actually implement。😡，There's your lower bound。

That's the best you could hope for。Okay。Yes。Instead of like using whatever for service。

 whatever for such too many letters。We don't need to do anything with any structure。

 right you can use whatever for search， that's fine。😡。

But that's already assuming you're like growing a tree and keeping Powerpointers in a bag of stuff and it's like now just just follow edges until you end up somewhere you've been before。

Completely naive， To brutefor。Okay。So this is the best we could hope for。

 let's see how close we can get。Now， as I said， I'm not going to go through the details of the analysis。

 if you are interested in this， I'll give some hint about how the the analysis works。

 but I'm not going to go through the details。😡，U。But。

This all is going to boil down to how do we choose。😡，Are augmenting paths。

So let me throw up our bad example for integer capacities again。Now。I said。

 let's start by choosing this path。And at least a few of you laughed。Which was the right response。

But why was it the right response， why is this not the right path， just total intuition？

What path would you think you'd want to choose？Shortest path， okay， that's one idea， another。😡，But。

Well this the first iteration， so what does that mean？Following paths with similar capacity， okay？

Whatever you choose。Okay， so I think what you're starting to get to is。

You wanted to choose the path with the maximum capacity。That greedy won't quite work there， but。Okay。

His greedy never works。So the the natural choices are for like what path to do that would be smart？

Is one is to choose the。Saddest path。So I want to choose the path。

Whose minimum capacity is as large as possible？So this will allow me to make the fastest progress towards。

My final maximum flow， at least that's the intuition。The second possibility。

Is that we choose the shortest path。Now I need to be careful here。

When we talk about Dyketra's algorithm， the setup is we have a directed graph with numbers attached to the edges。

😡，And what we want to minimize。Among all paths is the sum of the numbers on the edges of that path。😡。

Those numbers are called weights or lengths。 These numbers are capacities they're completely different。

 the right analogy to take is。😡，The numbers that Dkster cares about are the lengths of the roads。

Those numbers， the capacities are the width of the roads。😡，So when I'm computing shortest paths。

 what I really mean is the minimum number of edges。😡。

don't look at the capacities to give you a sense of length。😡，Capacities are width。可以。😊。

These both turn out to be better choices than nothing。😡，Okay。嗯。So let's do number one。A。

This is a heuristic that was first described by Jack Edmonds and Dick Kp， yes。

 that's the same carp from CAp perbe， yes， that's the same carp from NP completeness。Yes。

 look another Turing award， yeah okay。Okay， so I want to minimize the Mac， sorry， sorry， sorry。

I want to maximize。AndChoose a path that maximizes the minimum capacity。Well， okay， first question。😊。

How hard is it to compute？The fattest path from Estity。S。是。U。Okay， we're exercising our paranoia。

 that's good。It turns out that it's not that bad。😡，系。

So we know of a couple of different algorithms that explore graphs in a way that essentially is what I would call best first search。

😡，One of these is Dt algorithm。The next vertex site explore is the one where the distance estimate is smallest。

😡，Another one is Ksll's minimum spanning tree algorithm。

 The next edge I add to my tree is the one with the smallest weight。Okay。So there's a similar。

Best first。Search algorithm。That runs in E log V time。嗯。For undirected graphs。

 it's actually equivalent crossco's algorithm。So you grow a spanning tree like you would with Dyktra。

 you keep edges on the fringe in a priority cube just like you would with Dktra。

 but the priority that you keep on that edge is its capacity。😡。

So you always try to expand the tree by gluing on the edge with the largest capacity。😡。

But eventually that reaches T and that's the fattest path。

The proof of correctness is morally the same as the proof of correctness for Dystra's algorithm or the proof of correctness for Ktzcalll's algorithm。

 it's a greedy algorithm so there's an exchange argument in there。

 but I'm not going to bother showing it to you just it's not hard to implement。

 it really is fast in practice except you've got that log V term。😡，So now the question， of course。

 is the number of iterations。And it turns out。That the number of iterations is big O of e times the natural log of the flow value。

😡，In fact， that's not even a。It's not even a big O。It's an actual upper bound with a constant of one。

Oh my God， where did the natural log come from so the。vaguely， the proof goes as follows。So。

In my original graph， I've got F star flow value left to discover。😡，That maximum flow。

 there is a decomposition of that flow into EPAs from S to T。😡。

One of those pads carries the most flow among all of those paths。😡，Okay， so the key observation is。

Some path。From S to T。Carries。At least flow value over e。Flow。And so in particular， the。'mSorry。

 I was calling it fat not wide。The statusest path。From STT carries at least that much flow。

In other words。Basically， when I push flow across the fattest path。

 I'm reducing the maximum flow value by a multiplicative factor。😡，I'm scaling it down by something。

The right way to say this is。After K iterations。The residual graph。As。At most。

 one minus1 over e to the K times F star。Flow。Left。To find。

One minus something is about e to the minus something， do some math。

So you find the value of pay for which this quantity is less than one。😡。

And if all of your capacities or integers saying there is less than one unit of capacity left defined find is the same as saying there is no more flow left defined find。

😡，Because if you have integer capacities， you have always an integer amount of flow。

So the only integer that's less than one， but greater than or equal to0 is zero。嗯。So。

The E comes from the world's most useful inequality， is1 plus x is less than E to the X。For all X。

This is one of those things that。It's useful。嗯。But it's kind of weird that it shows up in a place that doesn't have anything to do with probability。

There it is。Now， one of the things that this also means is as you run the algorithm。

 the amount of flow that you are pushing through the system is growing。

 but it's always approaching the actual maximum flow。😡。

So even if the algorithm happens to run forever， at least now you know in the limit you're going to get the right answer。

😡，Unfortunately， it's still possible for the algorithm to run forever。😡。

If you have irrational capacities。嗯。The last thing， and then we're out of time。

Shortest augment many pads。Well。Now it's actually easier because I just run Brerent for search and this is probably the algorithm that you implemented anyway。

😡，When you needed to look for a path。Maybe you flipped the coin and got the wrong thing and you implement a depth or search。

 that's not good。Because you can get the bad patterns with depth research search。

 but if you implemented breadth for search， you got the shortest augmenting path every time and it only spent linear time getting it。

And then it turns out that the number of iterations is only v times z。😡。

So you get V squared as the running time。😡，And notice this has no connection whatsoever to the flow value。

 which means among other things， I don't care whether the capacities are irrational。

 the running time is always polynomial in the complexity of the graph。😡。

The values of the numbers simply don't matter。😡，Now this isn't the end of the story。

 I'm just going to show you the most recent running times， yeah quick。First time。就责的对。Yes。

 the shortest path always halts after V squared time。

So Or in 2012 came up with a Max flow algorithm that runs in exactly VE time。😡，It's been 10 years。

 the journal version of this paper has not come out yet。

 so I don't actually know whether it's believable or not。😡，Becauseuse。

Orland is one of these people who's smarter than everybody else。

 which means those papers are hard to read。But people seem to believe him。😡。

This uses a bunch of tricks。😡，Bunch of bunch of tricks。The most recent algorithm。

I have to include the month。Less than six months ago， no。Seven months ago。😡。

The running time is e to the one plus little o of one。Log U where you is an upper bound。

On integer capacities。So if you assume that your capacities are integers， which。Fine。😡，U。

You get there's a logarithmic term there。😡，whichch is kind of inescapable and then the most significant part of the running time here is e to the one plus little o of1。

 which means for large enough graphs， this is faster than e to the 1。1 for large enough graphs。

 this is faster than e to the 1。0000001。😡，There is no constant that you can put in there that's bigger than one that no matter what constant you put in there。

 eventually the algorithm will be faster than that。😡。

No one will ever implement either of those algorithms。😡。

People will implement and have implemented this in variations of this。

 but unless you have something very specialized， the thing you want to implement， well。

 actually the thing you want to implement is that。😡，Because in practice it。It is faster than that。

All right， we are four minutes over， so I apologize for that。Have a good weekend。

 hopefully see some of you on Tuesday。

![](img/4c05cbcb4b0d86f973ee3ae3f12a2951_3.png)

嗯。And it's 122 pages， I'm like， yeah， this is never happening。



![](img/4c05cbcb4b0d86f973ee3ae3f12a2951_5.png)

谢，不拜。不 know。