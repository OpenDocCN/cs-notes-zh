# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p04 -04-(Lecture 4_  Applications of Maximum Flows and Minimum Cuts).zh_en -BV14CAUeUEPj_p4-

Okay， so exercise set number two is going to be posted later today and then the plan for today is I'm talk I'm going to remind you about the S minimum cut problem and the fact that we know how to solve that efficiently and then the bulk of the lecture is going to be about an application to a problem in image segmentation case on computer vision。

And then hopefully we'll have time to talk a little bit about bipartite matching at the end of the lecture as well。

But before I do any of these new topics， I do OU one proof from Tuesday。

 so there's one key lemma which I didn't prove， which was essential for our analysis of the push rela algorithm you'll recall that what we did is we derived a cubic running time bound0 of n cubed where ends the number of vertices for push rela assuming this key lemma。

What is the key MSA， it says， well suppose you have a pre flow in a graph so remember a pre flow that's we've relaxed the conservation constraints and a vertex might have more flow coming in than it has coming out and that's known as its excess。

So suppose you have a preflow F， look at the residual graph G sub F。

If there's a vertex that has excess， positive excess。

 so the flow is strictly bigger than the flow out， then it asserts that there must be a path in the current residual graph from this vertex with excess v back to the source S that's what the di lemma says。

 let me remind you briefly how we used this。 this was really the thin end of the wedge for our analysis。

 we were sort of off to the races once we had this。

 So the first thing we did is we use this to just argue that no ver vertex's height could grow too large。

 The reason for that is well you know the source by our invariant is always anchored at height n。

 we have thisvariant that says that edges in the residual graph can only go downhill at most one at a time。

 So if you have a path from a vertex to the source in the residual graph and the source is stuck at n。

 it means that you started at most o of n so it bounded the height maximum height of any vertex at any time of o of n。

 there's only in vertices， every relabel bumps up a height。

 So that gave us the quadratic running time bound and the number ofs。able。

We then piggybacked on that bound to prove bound on the number of pushes we did that in two cases so first we talked about saturating pushes that's where you have a vertex with excess。

 you push as much flow as you can on an arc and the bottleneck is the edge so saturating push you saturate that outgoing edge that edge drops out of the residual graph and we argued that for any give an edge if you zoom in and look at two consecutive times that you have a saturating push in the same direction on the same edge that can only happen if you have at least a couple relabels of both endpoints in between since any vertex can only be relabeled o of n times and the edge can only have a saturating push o of n times that gives' an O MN bound on the number of saturating pushes。

 even better than the n cube that we were looking for。Finally， we bounded nonsaturating pushes。

 remember what this means， this means that you have a vertex with excess。

 you push as much flow as you can， and the bottleneck is actually the vertex。

 so you have plenty of capacity， but you zero out the excess。

And so this is the part of the proof where we use the fact that we always process the vertex with excess with the highest height。

How do we use it Well we argue， suppose you have a nonaturating push at some vertex。

 It has height like 12。 And so it's the biggest one。

 So anything else with excess has height 12 or less sp your choice of the vertex。

If we have a nonaturating push its excess becomes zero by definition。

 and then the key point is that it will never become positive again until there's a relabel。Why not。

 well where could it get excess from， somebody would have to push to this vertex。

 but we only push downhill， so it wouldd have to be from some vertex with high 13 or higher。

 but none of those vertices have any excess by the choice of the vertex V。

So that's why given the keylemma， oh I should say that then that means that you can only have O ofNs nonsaturating pushes between any pair of relabels。

 there's only n squared relabels so only n cubed nonaturating pushes， so that's the analysis recap。

 so let's prove this， let's prove the limma。So hopefully the limb is pretty intuitive， right。

 So somehow you， you have this pre flow and you have positive excess at some vertex V。

 And so somehow this excess flow had to have gotten there somehow。 And at some point， it came from S。

 So the thinking is， you should just be able to go back。 So that's good intuition。

 That's good motivation for why you might state this as a conjecture。 But it's， it's not a proof。

 And I I do feel like oh you were proof。😊，So fix a pre flow。F。

And the proof it's not too long and it sort of resembles an argument we did back in lecture number two when we were app provinging the max flowman cut theorem。

 one of our steps in that proof said oh， well if we have a maximum flow we can exhibit a cut with exactly the same value that was part of our proof So this will look a little bit like that。

So define a subset of vertices capital A。As if you look at the original graph and you look at the current preflow。

Basically do your favorite graph search， BFS， DFS， whatever from the source S on edges that carry flow。

 positive flow， and see how far you get， call that set A。So be reachable。From S。On edges E。

Of the original graph。With that fee positive。O。So you seef far you can get。

 maybe you can get everybody who knows？All right， so this is this is the second example of sort of the reachability trick in a proof that we saw in lecture number two。

 we did something similar。 We did breath first search or depth first search out of the source for the analysis。

 and we there we were going in the residual network until we got stuck。

 So here we're actually looking at edges that carry positive flow in the original network until we got stuck。

Okay， so it beads and out the other vertices。Let me point out that the source is definitely not in B。

The source can certainly reach itself， so the source is in A， not in B，All right。

 so what's the point of this set where did I pull this out of， Well， suppose there's a ver Tex in a。

Okay so there's a sequence of edges from S to V， all of which carry positive flow。Well。

 then what does the residual graph look like for each of those edges that's carrying positive flow。

 there's a reverse arc with positive residual capacity。

 so if you can get from s to V in the original graph on edges that carry flow。

 you can get from V to S sorry if you can get from S to V in the original graph on edges that carry flow you can get from V to S in the residual graph by following the reverse arcs and that's what we're trying to do。

 we're trying to say that all vertices with excess have to have paths reverse in the residual network back to the source。

So the Lemma is claiming that every single vertex with positive excess is a member of A。

 Nothing with excess should be a member of B。 That's the what we have to prove。Okay。Okay， so。

How do we do this？Well， again， sort of a similar trick to lecture number two， we're going to。

Sum up the difference between the flow in and the flow out， okay。

 this time for all of the vertices B。Okay。What can you tell me about each term of this sum？

It could be zero， what else could it be？Remember， we have a flow and not flow we have a pre flow and not necessarily a flow。

So if it's not zero， it could only be。It should only be negative， right。

 so the flow in is allowed to exceed the flow out。Okay， so it is going to be non positive。

I'm using the fact here that S is not a member of B。Okay， so in a pre flow。

 the source is the one vertex， which is allowed to have more flow going out than comingm in。Okay。

All right， so now like in lecture number two， what we want to do is we want to think about this sum in a different way。

 not as a sum of our vertices， but as a sum over edges。

 So let me draw sort of a picture that you've seen before。So imagine you have G。

And imagine over here you have the set B and over here you have the set A。

 so whenever you part a vertex set into two pieces and a directed graph。

 you get four categories of edges。You get edges that go internally to B。

 edges that go internally to A。Arcs that go from B to A and arcs that go backward from A to B。

 Every edges of one of those four types。 And just like lecture 2， we can ask。

 how much does each of those types of edges contribute to this sum。And the answer is the same。

 so let me just remind you briefly， this is a sum over the vertic season B。

So if the edge doesn't interact with B at all， then it doesn't matter。

 that has nothing to do with this sum。If an edge is entirely inside B， both endpoints are in B。

 then that flow amount will contribute once positively and once negatively。

 so itll contribute positively for the outgoing flow of the tail of the vertex into the incoming flow on the head of the vertex。

 head of the edge， excuse me。Anything that goes from B to A that's going to contribute positively once。

Anything going from A back to B， that's going to contribute negatively once。So when the dust settles。

This is just the sum。Of the flow on edges going out of B。Minus the flow on edge is going back into B。

So let me remind you this notation， I used this last week。

 so delta plus delta minus that means the edges sticking out of and sticking into respectively the set of vertices B so these are the delta plus edges here。

 these are the delta minus edges here so as promised things sticking out contribute once positively。

 things sticking back in， contribute once negatively。All right。

So let me say something pretty uncontroversial about these guys。So these are not negative。

That's a requirement of a preflow， no big deal。His was interesting。

I claim the flow on any edge sticking into B。Has to be zero。

The flow in any edge sticking into B has to be  zero。あ。Why， well， if it sticks into B。

It sticks out of a。How do we define A， he said， well。

 do reachability on edges that carry flow until you get stuck。

So if this edge sticking out of a had positive flow， we wouldn't have gotten stuck。

 A would be bigger Our graph search would to go ahead and traverse this edge。

So by virtue of getting stuck at a， searching along flow carrying edges。

 it must be the case that anything going from right to left has to be flow zero。All right。

So that means of course， that this whole。S is not negative。Okay。

So we've derived two things about exactly the same quantity， okay。

 we've written it two different ways。First of all， we argue that it's non positive， and in fact。

 every single term of this sum has to be non positive。On other hand。

 we argued that the thing has to be non negative。Okay。

So the only way both of those can be true is if this sum is zero。

And given that this is non positive term by term， the only way this can be zero is if every single term is zero。

Okay。So putting all this together， we get that for all vertices of B。Flow n equals flow out。

In other words， every vertex with positive excess has to be in A， cannot be in B。And again， remember。

 if you're an A， that means there's a flow carrying path from S to V。

 so there's a reverse path in the residual network from V to S。

 which is what we were supposed to prove。All right， any questions？All right。

 so that wraps up business from last lecture， push for label。And in fact。

 that's the last maximum flow algorithm we're going to talk about in CS 261。

 I could talk until the cows come home about maximum flow algorithms。

 Okay there are dozens and dozens of different algorithms。

 There's even been a couple big breakthroughs just in the last couple years。

 which is not normal in the 21st century typical year。

 Nobody says anything really new about maximum flow。

 last couple years have actually been sort of different so maybe I'll say a little bit more if there's time in some future lecture。

So you could have a whole class on Max flow algorithms， or for C is 261。

 I think 4 is probably enough。And so I want to move on to applications of maximum flow。

 how do you put these algorithms to use， and then I want to move on to other important problems。

 which we should also know good algorithms for。So the rest of this lecture is about。

Given a fast algorithm for maximum flow as a subroutine， which we now have。

 how can you piggyback on that to solve other problems you might care about？

So this is a good point just to sort of remind you about you why the lecture material is what it is。

 okay， why do we study these algorithms， study these problems？So first of all。

 so the algorithms we've studied， so number one is I think when you want to develop intuition about some nontrivial computational problem like maximum flow。

 for most of us， the easiest way to understand the problem is to actually think about algorithms that solve the problem And so that was the whole point of starting with Ford Fkson the algorithm is easy enough to understand。

 And through it we define residual networks we get to feel for what the maximum flow problem is like。

Another reason I sort of tell you all these specific algorithms is because some of them are just part of the canon。

 know part of the greatest hits of algorithms all time。

 so I'd put Edmond's carp Dick and push relabel in all in that category so it's just kind of cool to know how they work and then the last of those algorithms I mean all of them are reasonably efficient if you implement them well。

 but push rela again is typically blazingly fast in practice So it's actually a great starting point if you really need to solve maximum flow yourself in your future work that's kind I'm not saying you can't do better at all。

 but it does really， really well so it's a great starting point。😊。

All right but okay but why study you know that's great so if you want to understand MaxF。

 you should study these algorithms but why do you want to understand MaxFlow okay and so I said this before I'll say it again。

 like all central algorithmic problems， first of all。

 just in its own right it literally models things that we care about okay you can imagine traffic and transportation networks。

 you know oil going through pipes， you can imagine data packets to communication networks。

 they all sort of obviously map onto a maxflow type setup。😊。

But and this will be more the point of this lecture is lots of problems turn out to just be thinly disguised versions of maximum flow。

 and this takes maybe a little bit of practice to get used to。 And I think， frankly。

 one of the sort of most useful skills I can impart to you in CS 261 is giving you the ability to recognize when the tools from this class are going to be useful。

 so we're sort of moving into a part where that's what we focus on。😊，All right。Oh。

 and I should say there's going to be lots more examples on the exercise sets and the problem sets。

 because I really think this is one of the skills that you're most likely to actually put to use yourself sometime after the class。

Okay， so next up is going to be one of these sort of much less obvious applications of maximum flow actually it's going to be an application of the minimum cut problem。

 which we also know how to solve， it's an application in computer vision。

So we talked about Min cuts made a cameo in lecture number two。

 when we approved the Max F Min cut theem and we saw an algorithm。

 but let me just remind you because it was pretty fast。So what is the problem， first of all。

 the Minka problem， the input。Same kind of input as in max flow。So in network。

 a source is sink edge capacities。What's the goal？I。E， what's the min cut？

So you want to compute the ST cut a comma B。So remember this is just a partitioner of the vertex set S should be an A T should be and B。

That minimizes the capacity of the cut。What's the capacity of a cut？

 What's the sum of the capacities of the edges that stick out。Okay。

 so Dlta plus a edges that stick out of the set a， the source side of the cut。

And you look at their capacity。Okay。So importantly。

 edges that stick back into the source side of the cut do not contribute to the capacity of the cut。

 so it's really capacity outgoing is the definition。So that's the main cut problem。

And let me remind you of something we noted this in passing。

 but actually this is just like a really good thing for you to remember for as long as you can。

This is one of those sort of， if you've taken 261 this is kind of obvious。

 and if you haven't taken 261， you'd have no idea what I was talking about。嗯。So S teamman cut。

Reduces to max flow。In linear time。So given though we know how to solve max flow。

 we actually' know how to solve Min cut we saw this as a byproduct actually of one of our proofs of correctness and it was the same thing I alluded to earlier。

 we had this proof in lecture2 which showed oh well， if you give me a max flow。

 I can show you a cut with exactly the same value is part of the max flow and cut theorem how did the proof work where you say。

 well in our minds， let's do breadth first or depth third search in the residual network。

 see where we get stuck， if there's no ST path and we're going to have an ST cut and then we did a calculation to show that actually that cut has saturated edges only going forward and only zero edges going backward so the max flow value equals the value of that cut。

So at the time we did that in our minds， but you can equally well just actually take a maxflow。

 Comp maxflow and the residual graph there'll be no SD path。

 and now actually literally in your algorithm， run breadth or depth first search to recover the reachable nodes from S in the residual graph。

 Our proof shows that's a min cut。😊，So it's literally just a graph search computation。

 lineartime graph search， piggybacked on top of MaxF， and that gives us ST input。

And in there are algorithms for Min cut， which do not use MaxFlow， especially for undirected graphs。

 but in practice， this is actually usually the way you want to solve the ST cut problem。

 you really just do max flowlow plus this linear time of post processingces。Okay。

 so any questions about that？Okay。So now for stuff we haven't talked about before。Sorry， next。

 image segmentation。This is a basic problem in computer vision。

Let let me tell you about the formalization of the problem。So we're giving as input a graph。

And the way you should think about this graph is you should think of the vertices。

Representing images of a pixel。Okay。The edges is some notion of neighboring pixels。

 so the first graph you might think about is you use a grid， right， So you have a pixel and you say。

 let's call it neighbors， the ones just one pixel north， south，wet and east。

So I' have an example of the neighbors。 You could add in diagonals。 if you felt like it。

 sometimes people do that， the solution I'll show you doesn't really care what the graph is or works for any graph。

 but this is kind of what you should think about as motivation。It's naturally undirected。

And then there's some parameters， which I'll explain the semantics of shortly。

 so let me just get them on the board for now。I guess it's the simplest thing which you're used to。

Is every edge has a number。I'm going to call it a penalty。

 but it's sort of like every edge in a flow network has a capacity， every edge here has a penalty。

But then something which is different than the problems we've been talking about。

 each vertex also comes with a number， actually， with two numbers。 Okay。

 so addition to need each edge having a number。Each vertex has in numbers AV and BV。Okay。

So that's just literally what you're given as input。What are you supposed to do？ Well。

 what you're supposed to do is you're supposed to partition the pixels over the vertices。OK。

X is supposed to be the foreground。Why is supposed to be the background？

You can obviously think of versions where you try to segment into more than two pieces。

 but for today we're going to talk about two pieces， foreground X， background Y。

That's what we're trying to do。So how do we evaluate the quality of a potential partition？

And this is where I explain the semantics of the A's， B's， and P's。

So here's the objective function by a definition。So let me write it down and then I'll explain。Okay。

So。You got to put a vertex in either X or Y。 Okay， you have no choice。 It's going be a partition。

 If you put a vertex V and X， I'll give you a prize worth a sub V。If I give you， if you put it in Y。

 I give you a prize of value B sub V so for each vertex。

 you're going to pick up either the A value or the B value，And。

Depending on if it's in the foreground or the background。And so let's see。Right。

So how should you interpret these numbers？So you should interpret this it as if you have a prior。

 and I'm going to use some language that will be familiar to those of you who know machine learning。

 if you don't know machine learning， it doesn't matter。

 you don't need it to understand anything in this lecture。

 but intuitively you have some domain knowledge which gives you a prior on whether you expect。

 quote unquote each pixel to be part of the foreground or part of the background。Now。

 how do you sort of encode that prior belief into these parameter values， Well。

 if your operator belief is that some pixel is much more likely to be in the foreground than in the background。

 you want to encourage the solution。You want to encourage the solution to put it in the foreground。

 case you're going to have a large A value and a small B value for a pixel you think probably goes to the foreground。

 Similarly for something you think goes to the background。

 you're going to have a small A value and a big B value to make it sort of more likely that the algorithm will put it there。

Now， you could ask so how would you know whether something's likely to be one or the other and you can imagine lots of heuristics right So maybe you know in your sample of images。

 a light blue pixel is very likely to be part of the background because' the color of the sky So maybe just based on color you figure out what the A's and B should be or maybe you have a reference photo So maybe this is an image that came from a camera and you have a different image that came from the same camera in the same position not that long ago。

 and maybe you've even already segmented the previous one。

 then your prior might be that you know every pixel in the new image is likely to be the same the same classification as in the reference image。

To those， again， the solution I'll give you is totally agnostic as to where these A's and B's come from。

 and really， they're just defined using domain knowledge， which is often a sort of you know。

 thinly veiled euphemism for trial and error。 And that's where they come from。 But whatever they are。

 once you've defined them， you can run the algorithm I'm going to tell you about。All right。

 so if that was the whole story， if all you had was A's and B's and no P's。

 this would be a very easy problem to solve。Suppose all the P's were zero。

How would you partition the vertices to make that as big as possible？You would just go。

Pixel by pixel。And for each pixel you do the obvious thing， which you say， well。

 is a bigger or B bigger。 And then you just if it's a bigger， you put next， B is big， you put in Y。

 So that that would literally be what you'd do if all the P's were0。Now， why do these Ps。

 Where did they come from？ Well， you know， your prior is not going to be perfect。

 if you already knew of this segmentation， you wouldn't have to run any algorithm at all， right。

 So you're ready for ready to be wrong some of the time。

 So like maybe even your sensor picked up something that was a corrupted pixel in the middle of an otherwise homogeneous scene。

 Okay， so your data tells you that the boundary is more likely to be in the foreground in the background。

 But the pixel in the middle is more likely to be background than foreground。😊，Now。

 we also have this sort of prior belief that images should be smooth。 You're not going to sort of。

 as you alternate pixels， keep going foreground background， foreground background。 I mean。

 that's just not what images look like， at least ones that humans can interpret。

So there's also some bias so that neighboring pixels and this is where the neighboring relation comes in。

 neighboring pixels are put in the same the same of the two categories。 Okay so in other words。

 you're going to pay a penalty whenever you have two neighboring pixels。

 which are one is a foreground and one is a background。Okay，So that's what these P's are。

 these are the penalties。And every time you oops， this is wrong， right， that's minus。

Every time you have an edge which is cut and a gun cut means one end point in each of x and Y。

 When you have an edge which is cut， then you have to pay for it。Okay， that takes away from。

Your reward。So for example。So what I've meant to do here。

 these are supposed to be labeled with the A values and the B values on each vertex。

 So if the penalties were0， you would just put the whole boundary in the foreground and you'd put the center in the background。

But if the penalties are say one。That would not be an optimal solution。Right。

If every edge penalty was one， then。You wouldn't so let's， let me make sure this is clear。

So with zero edge penalties。All of these would be foreground。And this one would be background。

And you get a total score of nine。Right。But if every edge has penalty1。Then this edge would be cut。

 This edge would be cut。 That edge would be cut。 That edge would be cut。

 and we pay one for each of those edges。 So the solution value would only be 5。

So much smarter would be to actually just make if there are edge penalties of one。

Just make the center vertex also part of the foreground。So now you get eight from the boundary。

 you don't get any prize for the center vertex， but you don't cut any edges。

So you have an objective function value of eight， that'll be optimal here。

 And so this is meant to kind of be a cartoon for recovering a corrupted pixel automatically using these neighboring relationships。

So any questions about that about the definition of the problem？Okay。So what I want to show you。

Is how to very simply solve this problem using ST minimum cuts。Okay， reduces to S team and cut。

Now you may be wondering， how would anyone ever think to try to reduce this problem to ST minimum cut。

 like where does that come from？And， you know， one clue is if you look at the format of the output。

 So the problem by definition， is asking you to partition some set into two groups。

 That's exactly what cut problems do。So if you see these partitioning problems。

 you immediately think， oh， I wonder if a cut problem is going to be useful。Of course。

 it's always good to be optimistic， so you might think maybe it reduces to a cut problem I actually know how to solve。

SomeSome cut problems are empty。 but we notice solve S Min cut。 Maybe this reduces the S Min cut。

 That's basically like the coolest thing that could be true。 We don't know if it's true。

 but that's sort of starting optimistically。So that's fine， super high level， okay， partition cut。

 you know some correspondence， but then you kind of look a little deeper and you're like。

 actually there's a lot of differences it seems between this problem and the minimum cut problem。

Anyone want to offer up some things that don't type check between this problem and ST minimum cuts。

 there's several。Yeah， no clear definition good。It's not clear what's a soer is sink in this problem。

 but definitely one of the differences。Good， the other thing which is I think the least clear is like you have these A's and B's。

 which are on vertices and what do those correspond to a minimum cut problem I think that's the least sort of obvious thing。

And then there's some others which probably scare you a little less， so this is an undirected graph。

 we've been talking about directed graphs and there was one more。Oh yeah。

 This is a maximization problem。 minimumimum cut is a minimization problem。 So all of those are。

 at the very least cosmetic， but you know， possibly more serious issues with having a reduction。

 But as we'll see， all of these can be fixed。None of these problems are fundamental， okay。

 we can still just transform this into a ST minimum cut problem。All right。

 so I'm going to do that in two stages。 first we're going to do some transformations on the objective function。

So again， for those of you who sort of know a little machine learning。

 this is basically a max likelihood objective function。

 case you can take max likelihood and massage it under suitable assumptions into a form like this。

 So this is a natural this is a natural form in which to define the objective function。

 But now that our goal is to reduce it to minimum cut。

 let's think about some further transformations。Okay， so objective， so by this。

 I just mean this objective function， let's rewrite it a couple times。

So first we have this max min sort of type checking issue。

So the obvious way to do that is just sort of multiply by minus1 and then minimize instead。

 so maximizing this is the same as minimizing minus1 times all of this。So I'm in Xy。Of。S over PE。

 E cut。Minus sum over Av v and x。Minus sum over V and y。Okay。So that's pretty trivial。Now。

These minus signs are sort of making me nervous。Because like when we talked about minimum cut。

We only had non negative capacities。 We only had non negative numbers， period。

 So I don't like these negative numbers。So to get rid of the negative numbers。

 what I'm going to do is I'm just going to shift this objective function。To make a non negative。

 make everything non negative。So。Adding。The sum of the A values。And the sum of the B values。

This is the same as minimizing over partitions。Some of the penalties of the cut edges。Okay。

 so for the vertices in x， this minus cancels to this plus for anything which is in y。

 I actually pick up a new a value。So this is now plus sum over V and y of A sub V。 Similarly。

 we now have a plus over V and。X。A B B。这。So quick sanity check， so this number。

 how does this number depend on the particular partition x comma Y？はたぞ。It doesn't。 Okay。

 So I literally just shifted this function by a big constant number。 Okay。

 so certainly our ranking of the solutions is unchanged， right。

 So the optimal solution under this objective function is the same as the optimal optimal solution under this objective function。

Because they just added the same number at every possible feasible solution。All right。

 so we're going to work with this one。 which is totally equivalent to the one we started。

So I also promised you a transformation of the graph。So how does that work？

Well it's actually mostly just sort of tricks that。

We' be familiar for those of you that have spent some time on exercise set number one。

So let me show you the picture first。So we're given an input that looks like this。

 also with some A's， B's， and P's， okay。So we need to translate this into a flow network。Okay。

A directed flow network， because that's what we know how to solve。

So how do you take an undirected network and make it directed was a few ways。

 but the way I asked I encourage you to think about an exercise I set number one is to buy direct each edge。

 so for each undirected edge， you put in a directed edge in either direction。TheAnother thing。

 which is rightfully pointed out is that there was no source in sync in our input。

 but a max flow network is supposed to have one， so the obvious thing to do is just add a new source and add a new sink。

To fix the problem。So。We got this bidirected version of the graph here。

We had a new source and we had a new sink。Okay。So we need to add some edges。

 So those of you that have thought about a size set number one。

 you'll probably immediately think to sort of draw these arcs。 And that's good。

 But it turns out because of the A And B values actually want an arc from S to every vertex of the original vertex set V。

So I'm not going to add that edge。And that edge。And that edge， and similarly edges to T。

That edge and that edge。So a little more formally， what do we do？

We define our vertex set for the flow network to be the vertex， the pixels。

 plus an artificial source and an artificial sink。The edge set of our flow network。We bidirect。

Each edge in the undirected graph that were given。So what I mean is that if you have。

An edge in the undirected graph between U and V with some penalty piece sub B。

This gets mapped to edges going in both directions。With the capacity equal to P of B。

In both directions。That's the obvious first thing to try。 So your input has numbers on edges。

 your flow network' supposed to have numbers on edges。 Let's just use the same numbers。

 it turns out to work。All right， but that's not it。

 so this doesn't talk about the edges from the source and to the sink。So also。

Edges from the source of the sink， as we said， to all of the pixels。So it's the capacity。 Well。

 this is actually where we're going to encode the node numbers， the A's and the B's。

 they're going to correspond to capacities on arcs going out of the source or into the sink。

So if reddge is going out of the source from s to a pixel V， we give it capacity a sub V。

And then we also add edges。From V to T。For all pixels。With capacity， B sub。Good。

So that's the reduction。And the claim。Is that there exists a bijection。Between。Partitions。

Of X comma V。And ST cuts。So let's say partitions。X， Y of G and ST cuts。A B of G prime。That， moreover。

Presures objective function value。Okay right。So there's some way to put partitions of the pixels and SD cuts of G prime into one to one correspondence。

So that whatever the objective function value of that partition is under our transform objective。

 that's going to be exactly the capacity of the corresponding cut。Okay。

So this in particular gives us the desired reduction。

 how are you actually going to segment pixels into a foreground and background？Well。

 you take that input， you just literally constructed this graph G prime， you compute a minimum cut。

And then that cut is just going to correspond directly to the optimal partition x comma y。

That's what buys us in having this objective function preservation。

 says the optimal solution for the problem you're reducing to maximum flow is the minimum cut is the same as the objective function for the original image segmentation problem。

So I'll go through the proof of this， but any questions before we do that？

we said that we need to connect ST to re vertex because of the vertex values。

 A A Vs and B but even if we didn't have them， wouldn we have to connect them to S。Every。ワイテク。やてれ。

It's not necessary that there has to be a path， there has to be some path。Well， I mean。

 like so the only issue， it depends what you mean， but what do you mean even if we didn't have A's right so like if I put all the A's to zero。

You know，Then there is an optimal solution with value zero。Namely。

 I just put or there is a feasible solution with value 0 Okay， so I don't， I mean。

 I'm not quite sure to interpret it。 I mean， if you want。

 you could think of it as like the edges are always there。

 and then it just sort of doesn't count if it's zero capacity， but。I mean。

 sort of the point I want you to take away is that it was unclear how we would encode these labels on vertices in a flow network。

 And so I want to make it transparent how we're encoding them。

 It's exactly the edges going out of the source that encodes the A's and and their capacities and the capacities of the edges going into the sink encode the B sub V's。

That of that's the key point。Other questions？不是。杨员。St to。There is no edge from S T。

 so that may be an artifact of my poor drawing。But if you look at the list of edges。

 there's no direct edge from STT。So you go from S only to the pixels。

 and you go from the pixels to T。 You do not go straight from S to T。Good， other questions？All right。

 frankly， this proof just sort of writes itself， I mean， it's not hard at all。

Let me walk through it anyways。So the bijection， the one to one correspondence。

 I think is sort of the obvious one。Which is if you give me。

A partition of the pixels into a foreground X and a background Y。How do I get N T cut G prime。

 where let me just add S to the foreground and add the sink to the background？

So every ST cut of G prime has to have the form S plus x comma T plus y， x or y could be empty。

 that's no big deal， so every ST cut has this form S plus x T plus y and conversely。Okay。

 so it's a one to one correspondence。So we need to prove then is this part preserves objective function value。

 And this by itself， know， if we screwed up the objective function value。

 we wouldn't have a reduction because maybe we compute the optimal cut。

 and then it wouldn't correspond to the optimal image segmentation。All right。

 so let's pick any old cut and the ST cut and compute its capacity。

 and we're going to observe that the capacity is exactly the same as our transformed objective function in the box。

All right。So again， pick your favorite ST cut。the source side has the form s plus x for some x。

We want to compute its capacity， Remember capacity that refers only to the edges sticking out。

 so you want to sum up the capacities and the edges sticking out of the source side of the cut。

So that is， we're going to look at the edges of delta plus edges sticking out。Of x plus S。

 where x is arbitrary。 X is just some subset of V。All right， good。So。What sticks out of s plus x？

All right。Let's start with the vertices that the edges which go from the source to a pixel。

And which stick out of x。So if you have a pixel， which is an X。

Then the edge from S to that pixel does not stick out， it lies inside。

But if you have a pixel which is not part of x。Then it sticks across this cut。So for a picture。

 you might want to think about。This being our x。And then the corresponding ST cut is you just add S to that。

Okay， so that's going to be。All right。So what sticks out of a。 Well， in particular。

 the two arcs that go from S to the two pixels on the right。 those are both sticking out of the cut。

So in general。You would say that sticking out of x plus S is s comma V。

For all vertices that are part of the background。So what's the capacity of such an edge？

Do you remember。Right here。It'So out of the source， they encode the A's。

So if you cut an arc that goes from the source to a pixel V。

 what you pay for it in your capacity is you pay a sub V。Similarly。Arissymmetrically。

For any edge which enters the sink and where V。Is in x。

 then you're going to pay a capacity of B sub V。Okay。So this， for example。

 corresponds to the two arcs。Yeah。So it corresponds to this arc here。This is cut。

This sticks out of the pink。Region， and so does this a here？Okay。

So those are two types of edges which stick out of the cut。

There's also a third type of edge that sticks out of the cut， right？

They're edges which don't involve the source or the sink。

So that edge right there sticks out of the cut， and so does that edge right there。O。

So whenever you have two pixels， one in the foreground and one in the background。

For the corresponding to bidirect edges in G prime， exactly one of those will stick out of the cut。

 The other one will stick into the cut。Okay。So。For each edge。嗯。Cut by X， Y。Exactly one edge。

Of capacity， PCB。 Remember when we buy directed， both directions get a capacity of PCB。 and again。

 just by our construction， if the two pixels are on different sides， one foreground， one background。

 exactly one of those two arcs will contribute to the cut's capacity。这。

So what is the capacity of this cut？Well， so now we just sum up over all of the outgoing arcs。

Of their capacities。So we have this term。For every vertex in the background。We have these edges。

 so B sub Bs。For all pixels in the foreground。And then for every cut edge， we pick up a piece of B。

And of course， these are the same number。We agreed that that's equivalent to the max likelihood objective function that we started with。

So that shows the correctness of the reduction。There's a one to one correspondence between feasible solutions in both of them。

 the objective function value is preserved， so to compute the optimal and the original problem。

 it suffices to compute the optimal in the flow problem which you've reduced to and then just map the solution back in the obvious way。

Okay。And I want to emphasize this is this is not a made up application。 I mean。

 this really is used in computer vision and this technique。

 this cut based technique is well known in that field。

 So if if you just sort of Google gut cut methods， image segmentation， you'll get。

 you know hundreds of papers about it。So many questions。Makes sense。Yep。That moment。Sure。ではい。

Are there cases like this case？This the actual forecast。So what do you mean？啊。Yeah。好给。

Every pixel in the image。Yeah。Yeahep， yeah， yeahep。Are there any theorem？

We to see that we have a unique solution of。Yeah， that's good， that's a good question。 I mean。

 I think you're really talking about， I mean， there's two different issues。 One is just， you know。

 have you formulated the problem in a way that the solution is going to be meaningful。

And then a second question is about uniqueness。 And I think they're a little bit orthogonal， right。

 I mean， so like。这是这。For guaranteed of me。Yeah， okay， so you know all A's and B's equals zero case。

 it's not clear to me that's meaningful， I guess。Okay， fine。So the short answer is。

It's a little tricky， but at least for a lot of the problems we're talking about in 261。

 there are techniques to check uniqueness。Yeah。So like one thing you can do for， say。

 max flowerer min cut is you can try perturbing edge capacity。It's not trivial。

 it's like it's like a good homework problem to prove that it's polynomial time solvable to figure out if there's a unique STM cut or not。

But it can be done。Maybe I'll it on， maybe I'll it on a problem set。Other questions？Okay。If not。

 I want to talk about another application。So in addition to being another killer app of Max Flow。

 the rest of this lecture will form a convenience seggue。

Between the first two genres of problems we talk about in CS261， namely， first of all。

 flow problems and second of all， graph matching problems。

So I want to talk a little bit about bipartite matching。

My guess is many of you have encountered this at least in passing at some point。

So the input is a bipartite undirected graph。So remember what bipartidite means。

 it means you can partition the vertex set into a V and a W。So that there's no internal edges。

 so no edges inside V， no edges inside W， every arc。

 Every edge of the graph has one end point in each。So that's what a bipartite graph is。

What's a matching？So matching is a subset of the edges of a graph。

So that no two edges in the subset share an end point。So in other words。

 the edges that I'm matching have to be disjoint。And then the goal on the biparttheite matching problem is to compute matching of the largest possible size。

So let's look at some examples， some toy examples。So at a square。Is a square apartid？

So the key is to look at the diagonals。So if we put the untypital points of1 in v and the others is in W。

 then you see that indeed neither set has any edges internal。对。So's a bipartite graph。

What's the size of a maximum matching？Not a trick question。it's two， right？For example。

That's a matching， no shared endpoints。Has size two。

 there's another maximum matching where I take the left edge and the right edge。And you know。

 everybody can only be paired up once。So the best case scenario is you pair up everybody。

And how many edges would that be， that would be half the number of nodes。

 so obviously you can't do better than two， and general you can't do better than half the nodes for a matching size。

Now， in general， the max matching may be much， much， much worse than half the number of vertices。

Think about like a star graph。Is it star apartheid？Sure。

 just put the center on one side and everybody else on the rest。This a apartid graph。

 what's opt here？Does it depend on how many vertices there are？No。It's one， right？So you can do。

Every edge pairs with the center， if you only pair the center once。

 you're only going to get one edge。Okay。How about a triangle？っと。Is that apartheid？

As the simplest non biparttheite graph， it doesn't matter how you put them in two places。

 some edge will be internal。So we're not talking about non bipartite graphs。If we were。

 obviously the optimum here would be one。And it is very interesting， actually。

 to talk about nonbipartite matching， but we're not going to do that today。

 we're going to talk about bipartite matching。So we're thinking about cases like these two and wanted systematic methods of figuring out the max cardinality matching。

And so sort of a side comment right so whenever you have any graph algorithm problem， you can always。

 especially if you're motivated by applications， you can always think about special cases and for graph problems。

 you can always think about the bipartite graph special case depending on the problem。

 it may or may not buy you anything。For matching， bipartite graphs play a particularly fundamental role。

 Okay， for several reasons。 So first of all， the theory around bipartite matching is just much nicer than for non bipartite or much simpler。

 at least， let's say。The algorithms for the biparttheite case are faster。

 quite a bit faster than the non-bipartite case and actually most of the killer applications。

 not all of them， but a majority of the killer applications of matching are already in the case of bipartite graphs so just to give sort of one example right so when you know all the professors submit their preferences about when they want to teach their course like 261 so we Tuesday。

 Thursday 130 so think about CS261 is a node on the left side of this graph and think of the time slot Tuesday。

 Thursday 130 in this room。As one of the nodes on the right hand side。Okay。

So now what is a matching doing， it's pairing up courses with the room slash time slot where they're going to happen。

 Okay and there's just these naturally these two groups。 but you have courses， you have rooms。

 Okay so it's bipartid。 same thing when you're matching medical residents to hospitals after they finish their med degree。

Or assigning you know workers to jobs this kind of thing so in many， many cases。

 bipartite matching is actually all you need for an application and it's much better solved than the nonbipartite case in the sense that nonbipartite matching is still in polynomial time。

 but you have to work quite a bit harder than for bipartite matching。Okay， and in fact。

Bypartite matching just reduces to the maximum flow problem。Again。

 the reduction itself runs in linear time。Okay。And again， in practice。

 while there are algorithms for matching， which you do not go through max flow。

 usually this is the method of choice， so bypart that matching really comes up。

And a lot of applications， and MaxFlow is actually a really good approach for solving it。

So very much like the SDM and cut problem。Okay。So let me do a brief proof sketch。

 this is pretty easy， it's easier than the image segmentation reduction。And again。

 for those of you that have thought about exercise said number one， the ideas will be quite familiar。

So what are the type checking errors， well there's only a couple which we've already dealt with right。

 so we're given a bipartid graph that doesn't have a source of ain。So if you want to reduce it。

 the max flow better add a source in a sink。And we're given an underdirect graph。

 but we're going to run maximum a directed graph。 so we should direct the edges somehow。Okay。

So we're given us input of。Bibparttheite graph VW。Over were these edges？And as usual。

 we're just going to add a source for text。This time we only need to connect S to everybody in capital V。

And then similarly， we're going to connect everybody in W to the sync T。

And then we don't need to bidirect these edges。 It wouldn't hurt to bi direct it。

 but it would be much smart。 actually， we don't want to bi direct it。 Now I think about it。

 We really want to direct the edges from left to right。Okay。

So that's how given an undirected bipartite graph， we can exhibit a flow network。

 I still to tell you the capacities That's an important ingredient of a flow network。

 but this is the graph。All right。And what I want you to have in mind。Is if you have a flow path。

That looks like this。From S to T， and notice the only S pass in the graph have this form。

 It's a layered graph。 so you have to have a hop from S to V。

 a hop from B to W and a hop from W to T。 So every path looks like this。

 This corresponds to picking in your matching this edge from B to W。

Is that sort of what we have in mind when we're doing this reduction？

So how does that motivate setting the edge capacities？Yeah。Well。

 what's the important constraint in the matching， It's that no vertex is paired up more than once。

Okay。So like if this vertex is in this purple path， it'd better not also be in some other flow path。

 which goes over here because then it'll be matched up to two different people in W。

 and that's not allowed。So how do we make sure that this vertex is only going to show up on a single flow path？

We're going to make all of these capacities equal to one。Similarly。

 we don't want anybody in W to be paired up more than months。

So all of the edges from W to T get capacity one。Each。I should say。

So there's still the matter of putting capacities in the middle from V to W。

I'm going to put these capacities to infinity just because I can get away with it， and it's simpler。

 You can set into one that would also be a correct reduction。

 but it's a little simpler to think about them just being infinite。Okay。

So this is a way you take a bipartite graph and construct a flow network。

And the claim is very similar to image segmentation that there's a bijection between on the one hand matchings of the bipartthech graph and on the other hand flows in the flow network。

 Well actually， let me see something a little more precise integral flows in the flow network。

So I hope you find this kind of very believable。 I was planning on not being overly kind of formal about this。

So outside of class， you should think about why the integral flows。In G prime。

Correspond to the matchings。Nng。Okay看。And the correspondence is just the one we mentioned， right。

 So if you have a purple path like that， that's in correspondence with picking this particular purple edge and the bipartite match。

Okay。I should also say preserves objective function value。

So the value of the flow is going to be equal to the cardinality of the corresponding matching。

Just like an image segmentation that says all you need to do to solve bipartite matching is to solve Maxflow in this network。

 And then again， you saw the max flow。 You just look at which edges between V and W carry flow and you output that as your matching。

So one thing you might be sort of slightly worried about。We to say， well。

 actually the correspondence here is only between flows where that are integral so that puts an integer amount of flow on every edge and matchings。

 if you give me a fractional flow that routes half of the flow half a year of flow here。

 half a to flow there， it's not really clear how to interpret that as a matching in the biparttheite graph。

But notice。The flow network that we constructed， all of the capacities are integers。

 We can go ahead and count plus infinity as an integer， make it a sufficiently large number。

And all of the algorithms that we've discussed， if you feed in a network where every edge capacity is integer。

 it's going to terminate with a maximum flow， which is also integral because so every one of our algorithms will give us the desired inity property。

We talked about this a little bit when we talked about why does Ford Fson terminate So remember just inductively everything stays an integer。

 the current flow value， the residual capacities and therefore the amount by which you augment every single iteration so just by induction。

 everything stays integer so you really can just run any of our max flow algorithms in this graph。

 you'll get an integer maximum flow and then there's the natural mapping back to a matching。

So any questions about that？And this is a really good sort of reduction to remember exists。

 it's super simple， but really it's great to know。Yeah。Why you chose capacity？It's not clear yet。

 but it'll be clear in a second。Yeah， I mean， for our purposes up to now， it doesn't matter at all。

Either is equally justified。I mean。Right。I mean， the thing to notice is that even with infinite capacities。

 no edge here is going to carry more than a unit of flow anyways。

 because only one unit of flow can get to its tail。So， yeah。Somehow。

 unit capacities are already implied by the unit capacities incident to the source in the sink。

 but it'll be obvious with the last thing I have to say for this lecture。 Yeah， good question。

Other questions？All right。And we drink track some floor。The research。Say it again。

D that we get if there is an extract from W。Yeah， which brings in a possibility of more flow。

 which you can for a corresponding edge from potentially， but I mean， when we compute the max flow。

 there'll be no SD path in the residual graph。It's all going to work fine。I mean， you're right。

 I can see why maybe it seems like you'd want a tighter reduction of unit capacities， but trust me。

 we want the infinity。But for an implementation， it doesn't matter at all。

 go ahead and use one for an implementation， that's fine。Conceptually。

 I recommend thinking of as plus infinity。 I mean， really。

 where this problem is constrained is at the nodes， not in between V and W。 Okay。

 so it's sort of where the capacities binding are sort of reflecting where the constraints of the problem are right now。

 is which is good。Other questions？All right， so I want to tie a couple different themes that we've discussed so far together in the rest of this lecture。

 and I want to revisit this idea of optimality conditions， so how do we know when we're done。

 and I want to study that briefly in the bipartite matching problem。So in biparttheid matching。

How do we know if we're done？I。e。How do we know if a cs。

 if someone handed you a matching on a silver platter。

 how would you know whether or not it was a maximum matching？Now it was a perfect matching。

You'd be like， okay， good job。Can't do better than that。But what if you。

 there's like 100 vertices and someone gives you a matching with 42 edges？Claims it maximum。

How you after done。So there's a very， very clean answer to this question。

 it's really just one of the most beautiful theorems and sort of elementary combinatorics。

So let me tell you about it。I'm going to assume that the left hand side。Is the smaller side。

 This is without less of generality， I can always exchange V and W beforehand， if I want。

Some notation I'm going to need。Is that of a neighbor set？So for a set on the left hand side。

 like this， S。NFS are going to denote the neighbors of that set。it' a bipartite graph。

 all neighbors will be on the right hand side。O。So similarly， if this was a set T。

Then this would be NFT。Sanitation。NFs is just the union。Overall， the vertices S。Of the neighbors of。

Cisine。And these are all going to be your right hand sidevertices。

 so this law always be a subset of W。Okay。Everyone clear on that notation？

So here's a question for you。Okay， so when you have an unbalanced bipartite graph。

 so by a perfect matching， what I mean is， I mean， a matching that pairs up every single vertex on the left hand side。

So in this graph， we have five on the left， six on the right。 Obviously。

 I can't pair up everybody in the right， that would be silly。

But maybe I can pair up everybody on the left， because the best case scenario was a matching of size5 in this graph。

Does this graph have a perfect matching？Why does this graph not have a perfect match？Right。

 so the comment is that there's a problem with。E and its neighbors set up there， right？

So on the left hand side， we have these three different left hand side nodes。

 we'd like to pair them all up。Unfortunately， between all three of them combined。

 they only have two neighbors。So there's no way we can pair all three of them up。

Each of them has to be paired to one of the two neighbors who can only pair up two of them。

So some vertex of that upper set S will be left unmatched in every single maximum matching。

 every single matching。So this is sort of interesting because now going back to how do we know when we're done。

 well， in this graph， suppose I gave you a matching of size 4。😊，OkayAt first， you might say， well。

 it's not a perfect matching。 Maybe you could do better。 You'd be like， well， but here's my excuse。

 Here's the constricting set， which has fewer neighbors than the number of elements。 You'd be like。

 oh， you're right， No perfect matching。 You have the next best thing I accept maximum matching。好看。

So's thinking about this a little more generally， systematically。For any bipartid graph。

If I can ever find a constricting set， if I can ever show you a subset of vertices S on the left so that the number of neighbors on the right is fewer than the size of S。

 that's a proof that there's no perfect matching。Now。

 if you are responsible for proving the maximality of your matching， maximumness of your matching。

 you might be worried that you wouldn't be able to come up with this succinct excuse for all of the nodes that you've left unmatched。

So maybe there's no perfect matching， but also there's no set like this that proves it。Then again。

 you'd sort of be like unclear howd you convince anybody that you're done？

So what Hall's theorem says is that actually。This problem never arises。

Whenever you have a bipartite graph without a perfect matching。

 there is always an explanation of this form。There is necessarily a constricting set。

 a subset of the left hand side with obviously too few neighbors。

 So whenever there's not a perfect matching， there's always an obvious proof of that fact。

So this is Hall's theorem。From 1935， so it actually predates Max Sloman cut by 20 years。

So there exists a perfect matching。If and only if。For all subsets of the left hand side。

The number of neighbors of S is at least as large as the obvious necessary lower bound。But again。

 these are the only obstructions， the only reason why you're going to fail to have a perfect matching is because there exists one of these constricting sets with the neighbor sets strictly less than the size of the set。

You're always assured of such a certificate of non perfectectness。All right。

 so' talk about the proof a little bit。So isn't even only if one direction should be clear。

So one direction is just what we were talking about in the example。The right hand side is false。

Either some set s that constricts， then the left hand side is also false。

So that's the contrapoitive with the forward direction。

So it was hard is to prove is the reverse direction。If， in fact。

 you don't have any obvious obstructions， why is there a perfect match？And so for this。

 we'll be able to rely on the max flow min cut theorem。So for the reverse direction。

It's going to boil down to the following claim。Yeah。Yeah。In the flow network G prime。

 that's G prime there in the upper left。So in the flow network， G prime。The claim is that every。

ST cut。Has capacity。At least the size of V， size of the left hand side。 Again， remember。

 we're assuming without loss， the left hand side is smaller than the right hand side or at most is large。

So do you see why if this claim is true， then Hall's theorem follows？It's a very nice argument。Well。

 suppose this were true。Suppose every ST cut had capacity， at least the size of V。Well。

 then the min cut。Has value。At least the size of V。By the max flowman cut theorem。

 the max flow value is at least the size of V。What does a flow of value the size of V have to do in G prime？

Well， there's only。Size of V capacity escaping the source S。

So it's clear in G prime that the max flow values at most the size of S because you can only route one unit of flow to vertex each vertex of V。

 excuse me。Okay。So a flow value， a flow with value， at least the size of V has to saturate。

Every single arc out of S。That is， it has to match every vertex of V。Okay。So if this claim is true。

 then we run the previous reduction。 So notice， I mean， again， we've done this slide of hand。

 That was an algorithm。 This is a proof。But whatever， we can run the algorithm in our proof。

 It's fine。So given the bipartide graph， construct G prime， assume that this is true。Then you know。

 there's a max flow that saturates everything out of S that has to yield。

The desired perfect matching that pairs up every vertex of V。Okay。So is the claim true。

 well the claim is really just sort of true by inspection？So pick your favorite ST cut。A， common B。

In G prime。O。So think about A， right。I have to draw this。So A。

 what's going to do is it's going to have the source for sure。

 It's going to have some of the stuff in V。 It's going to have some of the stuff in W。

 and it's definitely not going to have T。Okay。So that's what the source side of some SD code looks like。

Define。S。As the vertices from V on the source side of the cut。So V。Interssect A。All right。

 so like this is our S here。So。I claim that unless something trivial happens。

 all of the neighbors have us。Also belong inside a。So S is over on the left hand side。

 I'm looking at the neighbors on the right hand side， and I'm claiming they also have to be in A。

But that's not quite true。But like imagine all the neighbors of S were not in A。

 There were some neighbor of S outside。Well， then there'd be an edge from the left hand side from V to this neighbor in W that sticks out of this cut。

This is why I defined all the edge capacities to be infinite。

So if any edge from V to W sticks out of a cut， automatically that cut has infinite capacity。

So the neighbor said belongs to A。Unless the capacity is infinite， remember。

 we're just trying to prove that every。Cut capacity sufficiently large。

 but's certainly sufficiently large。 So we're not worried about that case。In that case， we're done。

Alright。So again， we're trying to prove that every cut has large value。

 The observation is that any cut for which there's some。

Edge from a vertex in V to a vertex in W sticking out of the cut has infinite capacity。

So for the rest of the cuts， all of the neighbors。Yeah， that's right。

So all the neighbors also belong to the source side of the cut。So what's the cut value？Well。

 let's stare at this picture。What are the edges that stick out of A？Well。

There's one edge sticking out of a between the source vertex。And every vertex of V。

Which doesn't belong to A i。e。 that is not in S。Okay。So， that's V。Minus S。So these are sticking。

Out of us。Just by definition， everything outside of S is not part of this cut。

 so the edge goes from one side of the cut to the other。On the right hand side。What can we say？

Well on the right hand side， edges stick again， we're looking at things that go from A to T。

We don't really know what A looks like， but we do know that A at the very least contains all of the neighbors of S。

So for each vertex and N of S， there's going to be some edge directly to T sticking out of this cut A。

So this is sticking entity T。And remember， all of these edges have capacity one in G prime。

 I so we just count up the number of edges to lower bound the cut capacity。Here is where we use that。

 as it's called Hull's condition holds。 Every set has at least as many neighbors as its cardinality。

 This is at least as big as this minus term。So， this。

Is at least the number of vertices on the left hand side？Okay。So that's how you drive Hall's theorem。

From the Max F Min cut theorem， next week， more on matching and more on applications。

