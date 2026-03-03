# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p02 -02-(Lecture 2_ Augmenting Path Algorithms for Maximum Flow).zh_en -BV14CAUeUEPj_p2-

Where did we leave off last last time So a few things I want you to remember。

 I want you to remember about flows right so we're talking about directed graphs。 there's a source。

 there's a sink。 every edge has a capacity。 the goal is to push as much stuff as possible from the source S to the sink T subject to capacity constraints you can't overload anyone's capacity and subject to conservation constraints the flow into a vertex should be equal to the flow out except for the source and a sink vertex So those are flows a really important concept is that of a residual graph。

So for the next few lectures， often when we're talking about a graph， it'll be the residual graph。

 it's really important you remember what the residual graph is。So how does that work。

 so if you have a graph G and you have a flow F in the graph G。

 then there's a corresponding residual graph G sub F。

Each edge of G spawns two edges in G sub F1 going forward。

 one going reverse The forward arc is given in the residual network capacity UE minus F。

 so this is just the room left on the edge to push flow forward that's the forward edge and the residual graph。

 the reverse edge corresponds to an undo operation。

 So if you've already pushed F subB units forward across it。

 then you have capacity F subB to undo it to push it backward okay。

So that's the residual graph and we talked about the Ford Forson algorithm， what's the algorithm。

 just whatever the current residual graph is， you try to find an ST path where all the edges have positive capacity if you find one pick an arbitrary such one push as much flow as you can on that path subject to the capacity constraints and then terminate when you don't have any ST path in the current graph G that was the Ford Forson algorithm。

And so we argued last time that it terminated。We haven't yet argued correctness。

 That is the flow that deters with how do we know that it's a maximum flow。 And again。

 there's sort of a broader question here， which we're wondering about in particular for maximum flow。

 but it's going to be a recurring theme through the first half of 261。

Which is how do we know when we're done？Okay， so we have some algorithm。

 We think it's a good algorithm。 And at some point it stops。 How do we it didn't stop too early。

 How do we know it stopped with the optimal solution， In this case， a maximum flow okay。And again。

 this question is sort of interesting， even just without an algorithm。

 so even if someone just handed you on a silver platter， say an alleged maximum flow。

 how could you convince yourself that it really is a maximum flow that there isn't some other flow out there in the world。

 which sends even more stuff？So I left you with this network as an example。

 So the green numbers are the capacities， the red numbers are the flows。

 So this is a flow of value 3。It's sending three units to flow out of S。

And if I tried to claim this was a max flow。Would you believe me and if so， why？Right。

There's all these edges with capacity 100， and somehow could it really be true that the maximum flow you can push from ST T is only three？

All right。So that brings us up to speed。 Any questions about the review？All right， so。

I gave you a claim last time answering this question， how do we know when we're done。

 The claim was that if the residual graph has no ST path， then the flow F has to be maximum。

We didn't prove that。 But if that claim is true， then the fold Ferguson algorithm is indeed correct。

 It Does indeed solve the maximum flow problem。 Why the stopping condition of fold Ferguson is exactly that there's no augmenting path in the residual graph。

 Okay so that's a sufficient condition for optimality。 then we're all good。

So it's going to be convenient to actually prove a stronger statement。

 which is going to be the first thing I do this lecture， and from the stronger statement。

 we'll also be able to derive the famous max Fman cut theorem。So to state this stronger result。

 I need a definition， probably you may have seen this before， for example。

 when you studied minimum spanning trees， that of a cut in a graph。

So you have a graph source S syncnc T， an ST cut， or sometimes they'll just call it a cut。

That's a partition of the vertices into two sets， A and B， the sources in one of the sets。

 the sink is in the other set。So it's a partition。A B， a V。

 So each vertex is't exactly one of A or B。And it should be the case that the source is in A。

And the sink is in B。看。And kind of the generic picture you want to have in your mind for what it cuts look like。

So here's a graph， here's a source， here's a sink。Here's a cut。This is your A。And this is your be。

Okay看。So whenever you have a cut in a directed graph。

 it naturally buckets the edges into four different types。

 you got your edges that are just hanging out inside a。

You got your edges that are just loitering and B。You got edges going across the cut from the source side to the sink side。

And you've got edges going backward。From the sink side to the source side。

So that's an ST cut of a graph。 And as we'll see， it's sort of a duall。

 in a sense we'll make precise later to maximum flows。All right。So that's a cut。

 let me tell you what the capacity of a cut is。So the capacity of a cut。

 what you do is you look at all the edges that stick out of the cut that stick out of a and you add up all of their capacities。

 Importantly， you do not look at the edges that stick into a。 Okay。

 you ignore them for the capacity of computation。So the capacity of a cut AB is by definition。

The sum over the edges sticking out at A of their capacities。And I'm going to be using the notation。

Delta plus of a is the edges sticking out of a。Okay。

 so these are the edges in Dlta plus sticking out。And then delta minus。Is the one sticking in？Okay。

 so these are deelta minus here。All right， so that's a cut and that's the capacity of a cut。

For example。Suppose we take A。To be the vertices S， let's call this W， let's call that V。

So as we take A to B。S and V， and we take B to be V and T。Sorry A is S and W。

So what's the capacity of that cut？Okay， so what's up with a cut。

 So we don't look at edges that are inside A。 So we ignore this 100。

 We don't look at edges that are inside B， so we ignore that 100。

 We don't pay attention to edges that stick in。 So we ignore that 100。

 So we looking only at the ones that stick out of A， we have that one， that one and that。

So the capacity of that code would be three。So example。That has to be of SWVT。Equals 3， okay。

It's not an accident that that's the same value of that flow， more on that in a second。去去去。Alright。

So I should say other cuts in this graph have much larger capacity。

 so another cut would be you just take S the source to be one side。

 you take the other three vertices to be the other side。So the capacity of that cut would be。

Hundred01， right， So much， much bigger。 Okay， so different cuts can have very different capacities。

 What turns out to be of interest to us is the minimum cut， the cut that has the minimum capacity。

 okay。So here's the theorem。Which generalizes the claim from last lecture and improves correctness of Ford Ferguson。

And it's not too hard to prove， we're going to prove it， it'll take us a little bit。

 but it's not too bad。So for a flow F。In a graph G。The following are equivalent Okay， so TFAE。

 that's the following or equivalent。 So I'm going to write down three statements。

 This means either all of them are true or none of them are true。

 Those are the only two possibilities。Okay。So condition one， something we care about。F is a max flow。

But。Property2。There exists an ST cut。A B。Such that the value of f。Equals the capacity of the cut。

And the third statement。Is that the residual graph？Has no ST path。Okay。

So the claim from last lecture was the assertion that three implies one。Okay。

That's what we claimed at the end of the last lecture。

 This is saying any one of these three statements implies the other two。 Ca。

 it's giving us only more information。Question。Yeah。So any questions about the statement。

 Otherwise otherwise we're going to go on the， go on to the proof。Yeah。The following are equivalent。

 either all are true or none are true。So any one of them implies the other two。Other questions。

 you clarify what has no。Sure， so GF is a directed graph as interiorior vertices。

There's either a path from S to two there isn't， the saying there is't one。Other questions。

Stayment Cl。Okay。Alright， so the way you prove these。

 the following are equivalent statements is you just do a cycle of implications。

 Okay that means if any one of them is true， it sort of just percolates through and all of them are true。

 Okay， so we're going show that two implies 1，1 implies 3， and then3 implies2。All right，'s a proof。

So the first step two implies one。Okay。So the claim here is that for this implication。

 it's enough to show。That。For all flows F。And for all cuts AB， S cuts AB。The value of F。

Is it most the capacity of the cut？That is， any S T cut of a graph bounds above the value of any flow in the graph。

So that's the assertion， so I need to just show two things， first you I have to argue this is true。

 but secondly， just take it on faith for a second that this is true。

 let me just point out why that implies the desired implication。So suppose this inequality holds。

 every flow has value at most every cut。And imagine you just sort of plotted on the real line。

 so zero on the left。Plus infinity on the right。 Imagine you just sort of conceptually plotted the value of every possible flow of the graph and every possible cut of the graph。

So you're going to get a bunch of blue X's for the values of flows。

 and you're going to get a bunch of red O's for cuts。Okay。What does this say。

 that says there's never an x to the right of an O。That's what this says， so you have all the x's。

 and you have all the O's。So， imagine。Right， good。 So why is it that if two holds then one holds。

 So suppose you could actually find a cut A B。And a flow F so that the flow's value equals the cut's capacity。

In this picture， that would correspond to an x and an o exactly superimposed。

There'd be an x and O on top of each other。 That's what condition 2 would give us。 If that's true。

 Well， because no x can ever be to the right of an O， no other flow could possibly be bigger。

So put differently， if every cut is an upper bound on every flow。

 if you ever get in a happy case where there's actually a flow， which is as large as the minimum cut。

 you can't possibly be do better。 That's the best case scenario。 if this is true。All right。

 so that's why if this is true， then we're done with this implication。So why is this true。

 Why is it true that the value of any flow is the most the cast of any cut？ Well。

 if this seems sort of like obvious to you， that's great。 I mean。

 your intuition is fine and it's accurate for completeness。

 I'm going to give a short algebraic proof。 But if it seems like it's clear enough。

 that's fine as well。😊，All right， so fix， so I'm going to prove this now。

So fix a flow F and fix a cut A B。So I need to start with the value of F。

 and then I need to have a sequence of equations and inequalities culminating with the capacity of this cut AB。

So we started with value of F。All right， so let's remember what the value of a flow is。

 that's just the amount of stuff going out of the source。So by definition。This is the value of F。Now。

 just for kicks， sort of convenient for me。I'm going to add a second term。

 which refers to the edges coming into S。 Re from Tuesday。

 we're assuming that there are no edges coming into S without less of generality。 So that's vacuous。

 That's just， I just added 0。 Okay， just for fun。All right。

So now what I'm going to do is I'm going to add this same expression。So notice first of all。

 I should say， notice what this is。 This is the net flow out of S。 Okay， flow out minus the flow in。

 I that's what this difference means。 net flow out from a vertex。So I'm going to add to this。

 the net flow out of every other vertex of capital A of the source side of the cut。Okay。

So the claim is that this is exactly the same thing as if I sum over all of the vertices on the source side of the cut。

Of the net flows。Do you see why that's true？Why I can just harmlessly add all these net flows for all these other vertices V and A。

What is it about flows that lets me do this？Yeah。Right， conservation constraints。 Okay。

 So for any vertex other than the source of the sink and notice， you know S was already there。

 And T is not part of a。 So we're only adding vertices that are not the source of the sink。

 They all have flow n equals flow out。 i。e。 This difference is just 0。 Okay， So I added a0 here。

 I just added a whole bunch more zeroes。 You probably wonder， why am I doing all this。

 But give me a second。All right， so now we had to somehow relate this to the capacity of this cut AB。

And the way to do that is to just think about this double summation in a different way。Okay。

 so this is very kind of vertex centric。 the way we've written it right now。

 But imagine we adopt the perspective of an edge instead。So fix an edge E。

 and let's ask the question， how many times does F subB appear in this expression？For a given edgy。

So the answer depends， and it depends on which of the buckets of types of edges you're in。Okay。

So if it's an edge where both endpoints are in capital B。

Then you have nothing to do with this expression at all。 you never show up at all， okay。

Here's a little more interesting。 Consider an edge where both endpoints are in A。

 So the edge goes from V to W。How many times does FE show up in the sum？Well。

 it shows up once with a coefficient of plus 1 corresponding to the vertex V， the tail of the edge。

 And it shows up again with a coefficient of -1。For the vertex W， the head of the edge。

 So those are going to cancel。 So if for any edge inside a。

 it basically contributes 0 to this overall sum。Now。

 if you have an edge which is sticking out of a going from left to right。

 say v is an a and it goes to W and B。 So now W is missing from the sum。

 So that's not going to contribute anything。 but for vertex V。

 this edge sticking out is going to contribute once times F sub B symmetrically。

 for any edge going from B back to a， it's going to show up once with a coefficient of -1。

So the upshot being is another way to write this sum。Is to instead sum over all the edges and ask。

 how much does it contribute？Everything contributes zero to this sum。Except。Edges sticking out of a。

 each contribute F sub B。And edges sticking into a each contribute a minus F subb。Okay。So again。

 that's just writing the exact same number in a different way in an edge centric way rather than a vertex centric way。

All right， so just one more line and then we're done。So notice it， what are' trying to prove。

 We're trying to prove that the value of F is bounded above by the capacity of the cut。 Okay。

 so if it's an inequality， it's going to go in the bigger than direction。So。

What's an upper bound on how big F CV could be。The capacity。

 right used to be right So we use the conservation constraints better use the capacity constraints。

 Here's where we do it。 Okay， so the flow can't be more than the capacity。So if we replace F with UE。

 we only get a bigger number。This stuff we're subtracting。But we know it's not negative。

So if we no longer subtract something which is not negative。

 we again get a number which is only bigger。So。We conclude that this is bounded above。

By so the sum of the capacities of the edges sticking out。Also known as the capacity of A B。Okay。

And that's what we set up to prove。So that concludes the first and arguably the most annoying implication of the three that we're going to do。

 Okay， So if， in fact， you can exhibit a cut and you can exhibit a flow so that they have the same value。

 then the flow has to be a maximum flow。 If you think about it， also。

 that cut has to be a minimum cut for the same reason， okay。All right。

 so that's a sufficient condition for a flow to be maximum。

 You can find a cut with exactly the same value questions。Al right。

So the second implication is almost immediate。So the next implication is going to be that one implies two。

 one implies three， excuse me。And I want you to think about the contrapoitive。 Okay。

 so actually think about why not three implies not one。Well， suppose not three。

 so suppose the residual graph does have an ST path。We need to show that it's not a maximum flow。Why。

 well， if there's an ST path in residual graph， we can just go ahead and run Ford forguson。

Tgue twister。For one more iteration。So what does Ford Forson do。

 It searches for an S path in the residual graph if it finds one that it augments flow along it。

 giving you a flow with strictly larger value。 So as long as there is a path in the residual graph。

 you're not maximum。 You can make more progress and exhibit a higher flow。So contrapoitive。

Is basically immediate。Just by running an iteration of Ford Ferson。Okay。So the last thing I owe you。

Why does 3 imp 2？So why is it that if you don't have a SD path in the residual graph。

 you actually can exhibit a cut whose capacity is equal to the value of the flow that you've got and this is sort of short and sweet proof。

So the trick。Is the following？So assume three。Okay。Soumon this is true。Now， in our minds。

We're going run， say， breath first search。 Okay， again， it's not really an algorithm。

 It's in the proof。 So it's sort of a thought experiment。

 We imagine doing breath first search from S in the residual graph。So， or depth for search， whatever。

 So it's going find everything that's find aable。 Okay。

 that's how these graph search algorithms work。 by assumption。

 it's not going to get to T because there's no path from S to T。 Okay。

 so breath first or depth for search will make some progress。 It'll get to some vertices。

 Call those vertices capital A。So with a equal to V and V， such that there exists a path from S to V。

And Gf。好的。So again， just run your graph search from S， see where you get stuck， you get stuck a day。

O。So I want you to notice that because of assumption3， property 3。A V minus a。Is an ST cut。O。

Certainly， S is an A。 S can get to itself。Certainly， T is not an A。 that's by assumption。

 can't reach T from S and GF。And that's it， and it's a perition， so it's an ST cut。

And so the claim is that this is this cut will actually meet our desired property too。

So let's see why that is。I era the。Nexts this picture。Okay。So。It's an S D cut。

 and it doesn't look like this。 Okay， Why we ran graph search out of S。 and we got stuck at A。

 If you got stuck at A， you're not going to see arcs like this leaving A。 right。

 If there were arcs that went from a to outside of A。

 the graph search would have gone farther and a would be bigger。 Okay。

 So this is a special cut where。😊，There cannot be any arcs going， sticking out of it。

There can be as going backward， that's fine。So this is in Gf here。A residual graph。

RightBecause if it there's anything sticking going the other direction， a would have been bigger。

So what does that mean So that means。That。Thinking about edges back in the original graph G。We have。

Every edge。Whose tail is an A and head is in B that goes from A to B。

 Every edge of the original graph that goes from A to B has to be saturated。

 The current flow has to use its full capacity。Why， well。

 consider an edge which is not totally saturated。 Then in the residual graph。

 there's still a forward version of that edge。But if this edge is sticking out of A from A to B。

And then in the residual graph， there are no edges going from A to B。

 It has to be that this edge is saturated。 It has residual capacity 0。 Okay So again。

 if this was not true， this edge would be in the residual graph， A would have been bigger。

 You wouldn't have gotten stuck at A。Same reasoning。There is no flow。

On any edge of the original graph G。Which sticks into A。Okay， why。 well， if in the original graph。

 you have some flow in an edge sticking in the a in the residual graph。

 you then get a nontrivial reverse version of the edge for the undo operation。

 So sending flow backward into a gives you an edge sticking out in the residual graph。And again。

 if there was an edge sticking on the residual graph， A would be bigger。

 wouldn't have gotten stuck at a。Okay。So when we do this breath first search out of S。

 we get stuck and we get stuck at a very special set。

 we get stuck at a set where all of the edges of the original graph going out are saturated。

 all of the edges coming in in the original graph are zeroed out。What does that mean？That means。

So if we call this inequality here， star。So remember in this derivation here。What was the bounds。

 were the estimates that we used in the inequality， we said， oh， well。

 for all the edges sticking out of A， at worst， it's the capacity。All you just sticking in， well。

 at worst， they're zero， they're at least zero。And for this particular cut here。

All of these inequalities hold with equality。For everything sticking out。

 we actually have F E equals U E。 The flow equals the capacity。 For everything sticking in。

 we actually have that the flow is 0。😊，So for a general flow and a general cut。

 you just have an inequality like that for this particular flow F and this particular choice of a cut。

Everything here is inequality。There's no inequality， it's all equations。

So that means that the value of the flow that we started with equals the capacity of this cut A V minus a。

 which is what we were trying to prove。Right right。So。Star holds。With a quality。Okay。

So that finishes the proof of this theorem。So if there's no SD path residual graph。

 that's how you exhibit a cut with capacity equal to the flow value。Questions。

Certainly you can examine this theorem in action in this particular example。

 so in particular you know this cut A comma B is exactly the same as the value of this red flow 3。

And you will notice that if you look at this cut， it is。

 in fact the case that for all outgoing edges， they're saturated。That's saturated， that's saturated。

 that's saturated。 And for this incoming edge， it is indeed  zero。

 as has to be true for a max flowman cut pair。Yeah part two when we define the parts for G or G。Well。

 so Gf and G have the same vertex set。GF might be different from the， excellent point。

 so I just erased it， no it's here。So Gf。So when you define it in the proof。

You define it in the residual graph。That's important。

 now this is the one part where it's easy to get confused between the original graph and the residual graph。

So the claim is that in the original graph， like in this one。Outgoing edges are saturated。

 and incoming arc are zeroed out。Why， because if any of that was not true in the residual graph。

 you'd have edges sticking out。But there aren't， because you got stuck a day。

So it's sort of like the assumption is in the residual graph， there's no ST path that you get stuck。

 and then the conclusion is back in the original graph about edges out being saturated and edges in being zero。

It's a good clarifying question。Seply one of the things you just sort of get used to with practice And that's one of the benefits of having a few lectures in a row and max flow。

 you know， keeping track， the residual graph， the original graph， that's confusing。

 Everyone finds it confusing when they first learn it。

 Okay so but we have a couple lectures to get used to it。 I think by the end of them。

 you'll get used to it as well。Okay。So。This theorem' is true。 So what。Well， as we pointed out。

 this certainly implies that the full forecast algorithm is correct。

 even just a special case of this if three implies one。

 so we have indeed a correct max flow algorithm at this point。

 We'll talk about running time in a second。Let me deduce a few other things from this theorem。Okay。

Like the max flow Min cut theorem。Which states that for every flow network。The max flow value。

Equals the main cut value。Okay。That's the max flowment cut theorem。 You have a graph。

 two seemingly totally different kinds of objects，Flows from S T conservation capacity constraints。

 yada， yada yada， S T cuts。The exponential number of X T cuts。 And of them all。

 you find the minimum one。 Yet somehow these two objects are just getting at the exact same thing。

One from the left。And one from the right。Yeah。So not only are the xs always to the left of the O's。

 but there's always an x and a O that are superimposed。So why does this follow， Well。

 we know that the max flow value can't be strictly bigger than the min cut because we proved part of our proof showed that all flow values are to the left of all cut dos。

 So there's no way that's strictly bigger。So why can't this be strictly smaller？Well。

 not just because， you know， take a graph， take a max flow。And then invoke this theorem。

If you have what does this say， this says if you have a max flow， then I can find you a cut。

 This is part  two。 I can find you a cut with the same value。

So it's never going to be the case that the max flow is strictly less than the minimum cut。

 This theorem implies you can always get them to be exactly the same。

So that's the max Fing cut theorem。And it's always sort of real pleasure for me to teach it。

 because really， a long time ago， this is the theorem that seduced me into a career and algorithms。

 when I was a student， I just sort of couldn't believe that something that which seemed like such a mess just。

 you know， came together and you had this primal dual in max theorem。 It was just like， dude。

 there's some beauty in the universe。 That's when I thought when I saw this theorem。😊。

Your mile may vary。Okay， so that's just kind of a structural implication。

 Let me just mention a quick algorithmic implication of the proof。Which is cool。

So suppose I gave you a maximum flow in a network for free。Then in linear time。

 you can recover a minimum cut。So in this sense， minimum cut reduces in linear time to maximum flow。

Do you see what that's true， see where the proof implies then？It's the very last step of the proof。

So how do we prove that third implication where we took。As an assumption of a max flow F。

And then we did a search from S in the residual graph to see how far we got。

 And then at the end of the day， it turned out that was a min cut at the time。

 we were just doing that in our minds in the proof。 But that's a perfectly good algorithm。

 So if I give you a max flow in the residual graph， do B FS or DFS from S。 look at how far you get。

 that's the source side of a min cut。 And this proof shows that。😊。

So min cut reduces in linear time to max flow and actually in practice this is typically the method of choice so if you need to solve min cuts in practice and we'll see examples later where you want to do that。

 often the fastest way to do it is just take off the shelf super fast max flow algorithm and do BFS to recover the Min cut。

Okay。So any questions about that。So' let me pass this around。So a little bit， you know。

 before we move on to algorithms， which is the next thing。 a little bit about the backs story。

So how many of you have heard of the Rand corporation， RN D， just curious？Okay。

 so Rand is sort of a famous military think tank that was started after World War I。 Many。

 many famous mathematicians， economists， etc cetera， have passed through Rand。

 And that's where Ford and Fkererson were。In the mid 50s when they were doing this work。

 And so what happened is these two people that got their names here。 So Harris。

 there's an Air Force researcher， Theodore Harris and a retired Army general， Frank Ross。

 and so they came to forward Ford and Forguson for help。 So Harrison Ross， the CIA。

 so keep mind this is in the middle of the Cold War。

 okay mid-50s which happily you know none of you had had the experience。

 So back then know there's the Soviet Union and then there was the West and you know there's this Cold War。

 and so the CIA had given Harris and Ross， the rail system。

Connecting the then Soviet Union to a bunch of Eastern European countries。 So Poland， Czechoslovakia。

 Austria， Eastern Germany， this kind of thing。And so， you know they had。

 they gave them really a network okay with vertices。

 the vertices represented kind of administrative districts and the capacity， there were edges。

 if there were train tracks and the capacity was how much stuff， you know。

 basically how much those train tracks could carry。And so Harrison Ross through trial and error。

 basically through using heuristics， they had actually computed a flow。In the network。

 And by the way， the handout shows you a picture of exactly what they did。

 So they showed they computed a flow of 163000 units through this network。

 And they they found a corresponding minimum cut。 The minimum cut is labeled the bottleneck。

In that diagram。So they knew that Max flow equaled min cut in this particular network。

And then they brought it to Ford and Fson proved that Maxflow equals min cut always。 And also。

 they gave some provably correct algorithms for it。 So Harris and Roz。

 it turns out they're actually more interested in min cut than Maxflow。😊。

They didn't really want to like ship stuff through the Soviet Union's rail network。

 They wanted to blow it up as cheaply as possible and sever the connection between Eastern Europe and Soviet Union。

 So that's where this all comes from。All right。So。How about running time。

 how about computational efficiency？How long does it take。

 say the for focus an algorithm than the computer Max flow， Well。

 I turned that I can take a long time actually。And this is something I'll ask you to think about on exercise set number one。

 I can take a long time in the sense that if the capacities are very large， really big numbers。

 then it can take an enormous number of iterations to terminate。

 So it's what's called a pseudopolynomial time algorithm。

 So something you might have seen when you studied。

 say Napsack in CSs161 in a dynamic programming algorithm for it。 Okay， so that's the bad news。

 When the capacities are big， this algorithm can really take forever。

As you'll see when you come up with this example， the reason Ford Toerson can take forever is because it can basically keep choosing like a really sort of silly path over and over and over again and make very little progress when some other path would have let it make a lot of progress。

So this motivates specializations of Ford Fson， remember in the basic FF algorithm。

 if there's many ST passs in the residual graph， so far we're just choosing arbitrarily。

 but maybe if there's many ST pass in the residual graph， one makes more sense than another。

So that brings us to the Edmd's CAp algorithm。From the early70s。

And this is the very natural specialization of Ford Fson。

 where amongst all of the ST paths in the residual graph， you augment along a shortest path。

Shortest in the sense of it has the fewest number of edges， fewest number of hops。

So that's the Edmons carp maximum flow out。Certainly it's correct just because it's a sort of special case of Ford Fguson。

 which is correct。But the running time。Well， not exactly blazingly fast is still。

Bounded by a polynomial in the input size。So we're going to argue next。

Is that this algorithm always augmented along the shortest path in the residual graph。

Gives you a running time of M squared n， Big O of M squared n。Always in this class。

M we'll denote the number of edges。And N will denote the number of vertices。

 And then the applications that we care about， typically。

 the number of edges is going to be somewhere between like n。

 That's for sparse graphs and like n squared。 That's for a dense graph。

 so that's sort of where N is with respect to N， which means in terms of N。

 this is going to be somewhere between n cubed in the sparse case and N to the fifth in the dense case。

 Okay， so that's kind of。Not very good， frankly， but notice that this bound holds。

 no matter how big the capacities are。 Okay， so this is a really good starting point。

 And then we'll move on to see some optimizations。 Okay， faster algorithms。 You may wonder。

 why do we study the slow algorithm if we're going to study fast ones later。 Well。

 a lot of the important ideas are most gently introduced in the original Edmins carp algorithm。😊。

All right。So how do you get this running time bound， Well this follows from。A key wmer。

Can I fit it in that space？Yeah。So let me talk you about the intuition behind this key lemo。

 So to argue that it runs fast， we need to argue that the algorithm makes， in some sense。

 rapid progress。So what would be a notion of progress in the maximum flow problem？

Actually there's a lot of answers to that question， you'll see some other answers on the homework。

 but for the next couple algorithms we want to think of it as follows， what are we striving for。

 We're striving to get to a point where' in the residual graph there is no path from S to T that's our sufficient condition for optimality so we want to disconnect S& T in the residual graph。

So one notion of progress is if S and T keep getting farther and farther apart from each other in the residual graph。

And again， distance here is number of hops on a shortest path， a minimum hop path。Now， notice。

 the largest possible finite shortest path distance between two vertices would be n minus-1。

 if ends the number of vertices because if you had a path with n edges， it would loop。

 and then if you threw out the cycle， you get a shorter path。Okay。

 so the biggest finite shortest path distance is n -1。 If it ever gets bigger than that。

 it has to mean it's infinite。 It has to mean you're disconnected。So that's the intuition here。

 Our progress measure will be how far S&T are apart from each other in the residual graph if we can argue that that goes up reasonably rapidly。

 then we should be good。Okay， so。So fix a network G， think of that as fixed。

And we're going to be computing a sequence of flows as usual， and given a flow F。

D of F is just going to be the distance between S and T and the current residual graph。

 Fest number of hops。So ST distance。And Gf。Okay，Now again， don't forget。 So G is fixed。

 The original average G is fixed。 F keeps changing Every time F changes。

 the residual network changes。 And so when the residual network changes， this number。

 D of F might change。 Okay， so we want to track this number as Edmd's carp proceeds。All right。

 so what's the assertion？So first of all。D of F never goes down。In the Eddundds Carp algorithm。

So it might stay the same， it doesn't go down。Now， if it stayed the same forever。

 that would bode ill for us。 So we have to say that it goes up at least sometimes。 and indeed。

 well prove that it increases。At least once。Her amiration。对。

So maybe at the beginning of the algorithm， the distance between S and T is two hops。

 we augment along a path， it's still two hops， we augment along another path， it's still two hops。

 but then at some point we augment along a path and it becomes say three hops。

Do you see why this lemma？Okay。Implies our theorem。So first， instead of running time。

 let's just think about the number of iterations。So how many times- so again。

 assuming that this lemma is true。How many iterations could the Edmds carp algorithm possibly execute before terminating？

So how far a park can S&TV before they're disconnected？Right， so as soon as theyre。

 if you know their' distance， at least n hops apart from each other。

 you know they're actually disconnected， okay。So that says。

 and maybe I should say that this value D of F， that's an integer， obviously， it's a number of hops。

So this can only get triggered n times。Yeah，Because after that。

 you're disconnected and we know we stop。And this says that it goes up at least every M iterations。

So Edmunds carpple only ever run n times M iterations in total before finishing。

So that's the iteration bound， Where the running time bound come from。 Well， you have to actually。

 find the shortest path。 Now， maybe when I say shortest path， the first thing you think of is diktra。

But notice that's overkill here， right， because we're just looking at hop counts。

Shortest pass with respect to Hoop count is already solved by breath for a search。

So every iteration of Mmin's carp will be breath for a search， linear time， O of M time。

 O of M times n iterations。 So that's where the M squared n running time bound comes from。好 right。

All right， so let's prove the limit。All right， so proof of key lemma。It's short。

 but it's also a little tricky。So there's two parts， right， we network we've fixed our graph G。

 We're running evidences carp， F keeps changing。 We're tracking the ST distance and the residual graph。

 Part one says it never goes up。 sorry， it never goes down。 it can only go up。All right。

Here's the right way to think about Edmund's Car。 So in terms of what's called a layered graph。

So we obtain Elbeth。From G of F。Okay， so this is the residual graph as usual。

 This is going to be a subgraph。 So basically， we're going to take the residual graph。

 we're going to throw out some of the edges。 We'll be left with Lbe。 L here stands for layered。

So which edges do you keep， Here's what you do， okay。You start from S。

 so you've got the residual graph G of F。 you started the source S。You run BFS spread for search。

 and then you just stop when you get to the sync T。Okay。And you keep。

 you retain all of the forward edges in breath first search。

 meaning edges that go from some layer I to some subsequent layer I plus1。

Any edge in breath for a search which went sideways within a layer， you throw it out。

 any edge which went backward on your layers， you throw it out。

 so you keep an else F only the forward breath first search edges when you run BFS from the source in the residual graph。

So here's the picture。So in the residual graph。You've got some vertices that are a one hop。From S。

Meaning， there's literally an edge from S to these vertices in the residual graph。 So that's layer 1。

Then you've got your vertices， which in the residual graph take two hops to get to from S。

 but that you can indeed get to and two hops。So that's your second layer。And so on。

And then finally you have T， maybe there's some other stuff here， but we don't care。

 and then by definition。This is D ofF hops from S。Remember。

 DFF is defined as the distance between S and T in terms of number of hops in the residual graph。

So layer one， so you can think of it the sources layer0， this layer one， layer  two， layer ， bh。

 bh bh， bh， blah， the way up have to layer D of F。So remember。

 just like a basic property of breath for search， which you learned in。161。

Is when you draw this layered graph， there's no shortcuts。

 There's no way you can get from like layer 3 and traverse a single edge and get to layer 7。

That would violate what breath search does， right， Otherwise。

 that thing in layer 7 would actually be in layer 4。 All， So edges can only either go forward。

 And if they go forward， they go forward one layer at a time or they can go sideways。

 But then we throw them out。 We don't keep them or they can go backward。 Any number of layers。

 We throw those out， too， okay。😊，All right， so's the definition of this subgraph clear？

It's an important。Bor concept。Okay， so why did I do this？

Why should we muck around with this layered graph， Basically。

 it's a really good way to think about the shortest pass in the residual graph。 And remember。

 Edmd's carp augments on shortest paths。 So in other words。

 this is a good way to think about the types of augmentations that Edmd's carp restricts itself to。

So in particular right again， this is really just properties of breath for search。Yeah。

If I think about the paths from S to T in the layered graph。Those are exactly the same。

As the shortest ST paths of the residual graph GSF。So the ST passes in the layered graph。

Are exactly the same。As the shortest。ST paths。Of Gf。Okay。One direction should definitely be clear。

So suppose you actually had a path in the layered graph， what does that path have to look like。

 well it just marches one layer at a time， okay one hop to get here， second hop to get here。

 third hop to get here and so on， it gets to T in exactly D ofF hops and D ofF by definition is the shortest path length。

So it's clear that any path from S T in the layered graph has to net a shortest path in the original graph。

Conversely。Think about any path from S to T in the residual graph G sub F。

 which is not a path in the layered graph。So how would you not be a path in the layered graph。

 Well you' either have to go sideways or you'd have to go backward because all the forward edges are in the layered graph。

So say you go sideways， so you look at a path in the residual graph that goes layer 0， layer 1。

 layer 2， stays in layer 2 again， then goes three， four， five， well it wasted a hop。

It's going to take D of F plus1 hops to get to T。Similarly， if you ever take a backward edge。

 you're going to be stuck with all these D of F plus two hops to get to T。

 so those are not shortest paths。So the upshot is， is that the layered graph just succinctly encodes all of the shortest paths in the residual graph。

 And those are the paths on which Edmund's carp routes flow， okay。All right。

 so I think we should do an example。Make this a little more concrete。

 so let's return to sort of our favorite running example。All right， so the way I'm going to do this。

 so I'm going to draw these networks， the solid edges， those will be the edges that are in。

 so I'm always going to draw the residual graph， but some of the edges will be solid。

 some will be dashed， the solid edges will be in the layered graph。

 the dashed edges will not be in the layer graph， they'll be omitted from it okay。So。

Here's our usual kind of running example。So here the layered graph omits the edge5。

Why does it do that well the S， so the source is basically layer zero。

These two vertices are layer 1 because you can get to each of these in one hop from S。

 so initially there's no flow， right so the residual graph is just the original graph。

So the first layer of these two， that means the five edge is a sideways edge。

 so it gets omitted from the layered graph， and then this is layer2 here。好的。

So is that everything clear so far？What the layers are and like what's in and what's not in the layer graph。

Okay。So what does Edmon's carp do， Edmd carp Edmd's carp augments along some shortest path in the residual graph I。

e。 some path of L of F。 So some path that's all solid edges。 So it has a choice here。

 It can either use the top one or the bottom one。 Those are both shortest augmenting paths。

 It doesn't really matter。 So let's just choose arbitrarily that it picks the top one。

How do things then change？Well， so let's see， so these two arcs are untouched。

So we still have this two。We still have this three。This a got saturated。

 so we just pick up the reverse version。And then this has both a forward and a reverse version。

Epsson the five is still here too。So what is layer 1 now？Has it changed？

Layer one is the same as before。 It's true the capacity here is less， but that edge is still there。

 still has residual capacity one， so you can still get to each of these vertices in one hop。

So this edge is still a sideways edge， it's still going to be out of the layered graph。

And now this is layer2。对。So here， DFF was 2。 and here， DFF is still2。 So this shows that indeed。

 when you do an augmentation in emmon's carp， there's no guarantee that the sour sync distance will strictly increase。

 That may not happen。 Okay， didn't go down， at least。 So that's good。Okay？

And so just to remind you what we're trying to prove。

 we're trying to prove that it never goes down and it goes up at least once every emiterations。Okay。

 so then the last one。Okay， so what does Edmond's carp do here？It routes on a shortest path， I。e。

 on some path of solid edges。 There's only one such path now。

 So Edmonds carp will definitely route two units on that bottom2 hub path。

 That's the only thing it can do。And once it does that。Here's what the new residual graph looks like。

All right， so we still have this one。And it's backward two。The bottom left one we've now saturated。

So this is now backward too。This backward two is still there。

Here we now still have one unit going forward and we have two units going backward。And so this edge。

 which had always been dotted。 the cross edge， it's no longer dotted。 it's now a solid edge。

So that's five。K。What are the layers， well so what vertices can you get to from S in one hop？

Only the top one。Right。Only the top vertex can be reached in one hop from S。So this is layer one。

What's layer2， so which vertices can you get to in two hops from S？Well， only that one。Because again。

 this a is saturated， so it's dropped out of the residual graph。So this is layer two。

And this is layer  three。And we see that in this case。In fact。

 the ST distance in the residual graph has gone up strictly from two till three。From here。

 we do one more augmentation， and we get the max flow and we're done。Allright。

So what this whole lem is about that when taking this detour from。

 it's showing that what we're seeing in this specific example is true in general。 Okay。

 the sourcing distance might stay the same for a while。

 but it's got to go up periodically and it never goes down。So you have some feel for that now？

Any questions about the example？Yeah二。It seems that。R firstt search。能规で。You're right， you're right。

 So really， so I've been a little imprecise about what the residual graph is。 you know。

 the way I defined it， I said， include two edges from every edge of the original graph。

 And now in general， and in all the pictures， I've been noting that some of those are zero either they're saturated。

 so you don't have the forward arc anymore or you haven't routed anything on it so you don't have the reverse arc So I've been omitting those in the picture and you're absolutely right that when I say do breath first search。

 I mean， do breath first search only on edges that have positive residual capacity。😊。

Becauseuse remember at the end of the day， you find a path。 you need dog meant。

 So you better find a path where every single edge has positive residual capacity。

 So that's what you do to search in。 It's a good question。Other questions？2。

So now that we have a little bit of confidence from our examples， let's actually prove it。

Prove the keylemma。So part one just says that when you augment on a shortest path in the residual graph。

 the ST distance can't go down。So why is that true？Well， so Edmund's carp。

Augments on a path of LH sorry， the layer graph， LF。Okay。

So this is using this note up here So Edmond's carp by definition。

 uses some shortest path in the residual graph。 We observed that that's a one to one correspondence with the paths in Elbe。

 That's the whole point of defining ElF so these are the paths that Edmond's carp uses。Now。

What are we worried about， We're worried that somehow some newly shorter path appears after we do this augmentation。

Okay。So currently we have a residual graph where maybe it takes five hops to get from S to T。

 Okay so there's five layers。 We're worried that we do an augmentation。

 suddenly we could get there and only four hops。So how could that possibly happen？Well。

 the only way it could happen is if the augmentation introduced some shortcut edge。

 which catapulted over at least one of these layers right So suddenly there was an edge which went from layer 2 to layer 4。

In this network， then conceivably there'd be a shorter path to T than there was before。

But there's no way this can happen。This augmentation cannot create such shortcut edges， why， well。

 what are the edges which newly appear after an augmentation？

It's the reverse edges of the augmentation you just did。 Okay。

 Those are the only new edges you might have in your graph。You augment meant forward。

 you get a reverse arc with nonze residual capacity。But every edge that we augmented on went forward。

 It went from a layer I to a layer I plus1。 So the new reverse arc goes from layer I plus1。

 the layer I。 It goes backward。Okay， so we certainly don't introduce any new shortcuts by doing that augmentation on a shortest path。

 So that's why that's basically the proof。So newly created edges。Go backward。

Backward in the sense of that picture of those layers up there。

And so that means no new shorter paths are created。Okay。So that's part one of dilemma。

Any questions about that？So that's good。 It can't shrink。 Why does it have to eventually go up。

So part two said that at least once every M iterations。It's going to strictly go up by at least one。

 and that's all we have left to prove。Well。So as long as。D ofF stays constant。Okay。

 so maybe the distance between S and T is like 5。 We do an iteration。 It's still 5。

 We do an iteration。 It's still 5。 And we just watch what happens。y， we say， how long can this go on。

Well， as long as the S T distance stays constant， it's always equal to 5。

The first claim is that every iteration zeroes out。At least one edge。A El Beth。Okay。And this is just。

 by the way， we choose the parameter delta。 this is just because we're greedy。

 but we find a path on which we can augment and we augment as much as we can subject to the residual capacity constraints。

And so then what does that mean， that means whatever edge on this path has the minimum residual capacity。

 it's going to get knocked out of the residual graph。Because we'll just totally saturate it。

 or if it's a reverse arc， we'll totally zero it out and it' will disappear。So at least one edge。

 the bottleneck edge of a path disappears every time we do an augmentation。好看。

So that's the first point。We'd like to say， oh， well， there was only M edges。

 If one of them goes away every time， then we have to something else has to happen after emiterations。

The one tricky point is。We have to argue that it doesn't come back， right， The worry is that sort of。

 you know， we kill an edge over here。 But then we do some other augmentation。 All of a sudden。

 it reappears because we augment it along the reverse arc。 Okay， so that's the one subtle point。

But that can't happen。And the reason it can't happen is really just the same as the proof of part one。

 Okay， so imagine you had an edge in the layer graph， say it went from layer 3 to layer 4， okay。

And so say that was the bottleneck edge。 So that's the one that got saturated in some augmentation。

 So this edge from 3 to 4 dropped down。The only way it could ever reappear。

Is if we augmented flow in the other direction along that edge， O。

 but that would be augmenting from layer 4 to layer 3， which would be a backward path。

Edmd's carp only ever send flow on forward paths， It never routes flow backward。

 So it's never going to reintroduce a forward edge that we had previously zeroed out。

So we drop an edge every time and we have this modestity property that once it drops out。

 it can't reappear at least until the shortest path distance gets bigger。Okay。So that's it。

 that's derivative of the key limit。So one thing I want to point out is that when the shortest path distance does change。

 So remember all of this was just saying consider a sequence of iterations where the ST distance stays the same。

When the SD distance actually goes up， then things can change quite a bit。

 So that's like the difference between this network here。And this network here。And so for example。

 we had something like an edge which had previously not been in the layer graph。

 all of a sudden does become part of the layered graph。

And that's because this edge didn't participate in any two hot paths。

 but it did participate in the three hot paths， so it had to wait till all the two hot paths were sort of severed by augmentations。

 then all of a sudden it would be part of a shortest path again but within while the shortest path distance stays fixed。

 edges only go away and they don't come back。Yep。数额。It looks like we imp assume that layer。

When we remove the short， when we。でば。Yeah so it's a good question， so it's changing。

 but if you like think just think about this partitioning of the vertices。 Okay。

 so at the beginning of this sequence of iterations， you have vertices V1， vertices V2， vertices V3。

 and so on。And it's by definition of BFS， the only way to get from S to T using only。

 say five hops is to use a sequence of four edges and you need at least five hops to do it。

And so with respect to that definition of these vertex groups。

Everything I said is correct right so if an edge goes from V2 to V3， you augment。

 you get a backward edge from V3 to V2。If you try to use an edge from v3 to V2 to get to T。

 it means you have to go backward1。 It's going to take you d of T plus two hops to get to T。

 So I understand， but just freeze this once and for all。 Okay。

 so look at the first iteration where D of T equals 5。Look at this graph。And now just in your head。

 freeze membership of vertices in these groups forevermore。 The residual graph will keep changing。

 but we sort of saved a copy of what this graph looked like the first time D D of F equald 5。

And so then it's still true。 The only way you can get from S T is you have to go layer by layer and none of the augmentations because you only go forward。

 all the new edges go backward。 So at no point where you get a shorter path。

 it's also the reason why at no point will something reappear until D of F changes。 But you're。

 it's a subtle point。 It's a good question。Other questions。Okay。

So I want to wrap up by just giving you a very brief introduction to。

Something quite related to Edmon's carp that you're going to explore mostly on the exercise set and the problem set。

And it's known as using blocking flows to compute maximum flows。

And the idea here is that we're going to augment not just along one path at a time。

 but on a batch of paths all at once。So this is known as Dix algorithm。

So this is roughly the same time an independent of Edmund's carp， and it's pretty similar actually。

 despite being developed independently。So you start with a zero flow。

And as long as there's some ST path in the residual graph。So notice。

 this is a great stopping condition to have because if this algorithm stops。

 it stops with no SD path in digital graphs， is's going to be optimal by our first result from today。

So construct the layered graph L F。From the residual graph Gf via breath first search。Now。

 I sort of going to sled a hand here， actually， because before when we were talking about the layered graph。

 it was all like inside the proof。 It was just a thought experiment。

 Edmond's carp just found a shortest path。In Dixs algorithm。

 we're actually going to explicitly in our algorithm compute this exact same layered graph previously shown in the analysis。

That's just a breath for a search computation， so that's a linear time， no worries。

Then we're going to compute what's known as a blocking flow。

 and I'll tell you what that is in a second。Compe a blocking flow in the residual graph。

 which in general is not one path， but a superposition of a bunch of paths。And then we augment。

F by this entire superposition of paths G。Okay。So that's the high level structure of Dent's algorithm。

 you just keep computing blocking flows in the current residual network。So what's a blocking flow？

A blocking flow。Is just where our very first naive greedy algorithm is exactly where it gets stuck。

So remember， our first greedy algorithm didn't even have a residual graph。

 It just tried to keep pushing flow upward on edges。

If it ever got to the point where there was no path from S to T where every edge was below the capacity。

 that's where that naive Gui algorithm halted。That's called the blocking flow。

 So if you can't find a path where everything is under capacity， that's a blocking flow。

So blocking flow G。Is by definition。So that there is no path。

Such that there's room left on every path。So this is no- I should say there does not exist a path in G。

Okay。So it's not thinking about their residual network， it's talking about just some graph。

And so the example you want to have in mind is the same place where our greedy algorithm got stuck。

Which is this flow here。Yeah， so if you send three units on the zigzag path。

Then this edge is saturated。This edge is saturated， so there is no path from ST T。

 which uses only unsaturated edges in the forward direction。So this is a blocking film。Okay。So。

On the first exercise set， I ask you to prove the following。

The reason it's just an exercise is because the proof is almost exactly the same as the proof of the key lemma we just went through。

 but I want you to think through the details of that。So the claim is that if G。Is a blocking flow？

In the residual network， G of F。Then when you augment the flow F using this blocking flow G。

This ST distance is guaranteed to strictly go up。Okay。So for comparison， remember Edmonund's carp。

 we were augmenting on just one path。And we couldn't say that the S distance went up。

 We could say it went up once every M iterations。 Now we're doing a batch processing。

 we're augmenting not by a path by an entire blocking flow。

 And the benefit is every blocking flow is guaranteed to increase the ST distance。

That means we don't have to do more than n blocking flow computations before we're done。

 because again， remember once S&T are an n hops apart， they're infinite apart and we're done。

 we have a max flow。Okay。Oh whoops。Then。The distance between S and T and the residual graph after the augmentation is strictly bigger than what it was before the augmentation。

Okay， so that's an exercise set， number one。As far as the implications for running time。

So how fast does this algorithm run？Well。Kind of obviously。

 it sort of depends on how fast it takes you to。Computer blocking flow。

 right Comping a shortest path was not hard。 That was linear time。

Right now we're trying to compute a possibly more ambitious object a blocking flow might take more than linear time。

 Okay， but parameterized by whatever your blocking flow subroutine takes。

We can at least say the Dx runtime。The O of n。Times the time needed for a blocking flow。

So you just give me as a black box， a subroutine that will compute a blocking flow in a graph。

Dinix's algorithm just uses that subroutine as a black box。By the claim。

 it only needs to invoke the black box n times。 So the running time is just n times that of the subty n times the blocking flow。

So how fast can you compute a blocking flow。Well， so on the first problem set。

I'll ask you to think about。How you can basically use depth for search。

To get a running time of M times n for a blocking flow。So if you plug that into Den's runtime。

 now you get MN squared。Okay，And that's an improvement over the Edmonund's car running time。 right。

 So M squared n definitely worse than n squared M。 It's always good if you can replace an M by an N。

 which is only going to be smaller。 Okay， so it's going to be N to the fourth at worst， this one。😊。

As far as the state of the art， it's even known how to using sort of fancy data structures。

 you can compute a blocking flow in close to linear time， meaning like an extra log factor。

 So sort of diktra type running time。 So that gives you max flow algorithms with running time pretty close to M times N。

 which is now not so embarrassing anymore。 You've seen some running times like that before in 161。

So that concludes the story with augmenting paths and blocking flows。

 Next up is a different paradigm for Maxflow called push rela。 It's a little less intuitive。

 which is why I do this first。 but push rela has the benefit of being really usually the choice in practice。

 really blazingly fast maximum flow algorithms from push rela。 We'll talk about that Tuesday。

