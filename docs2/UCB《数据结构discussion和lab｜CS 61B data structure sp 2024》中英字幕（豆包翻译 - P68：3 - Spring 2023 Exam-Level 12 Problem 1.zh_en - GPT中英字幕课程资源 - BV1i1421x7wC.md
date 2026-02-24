# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P68：3 - Spring 2023 Exam-Level 12 Problem 1.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/43c32a6431a8b6a645f27a28e0e02b7d_0.png)

Yeah。Hi everyone， this is going to be a video walk through problem two。

 multiple MSTs on the exam worksheet or MSTs Dis and Tris。So let's see what the Chbo has to say。

 we call a graph can have multiple MSTs if there are multiple spanning trees of minimum weight。

So what does this really mean Well， if we have some graph。Let's say we have the following graph。

And let's say that all of the edgeates are one in this triangle graph I created。

 Notice that if we choose any。Two of these three edges， it's a valid MST。

 so what this implies is there is three possible valid MSTs for this given graph。😊，Okay。

 and in general， it's possible for any graph to have multiple valid Mts。

 So this problem we're going to be exploring。😊，What must be the case for a graph to have multiple MSDs okay so let's dive into part A。

 put each sub part below select the correct option and justify your answer if you select never always provide a short explanation if you select sometimes provide two graphs that fulfill the given properties one with multiple MSDs and one without assume G is an undirected connected graph。

😊，Okay， so for part one， it states if none of the edge weights are identical， in other words。

 if all of the edge weights are unique there will。And the answer to this one is going to be。

Never be multiple MSts and G so let me quickly explain why this is the case， so suppose that we have。

Any graph。Where all of these edges are unique。Intuitively。If all the as are unique。

We can't really have multiple MSDs because we can only have multiple MSDs if two of them are the same and one MST chooses this one versus the MST chooses that one that's like really wishy washi so let's dive into a more thorough explanation why it the case。

😊，And to do that， let's first recall the cond property。So， recall。The cut property states that。If。

The。Crossing。Pas。In。A cut。爱。Unique in weight。Then。The minimum。Wt。Crossing。Edge。

Will be in D these important MST。Okay， so what the cut property states。

 and let me just quickly specify that this is the cut property。

Is that if we ever have a cut in the graph where all of the crossing edges on the cut are unique。

Then the minimum weight crossing edge in that cut must be in the MST。

So what we can do for our quick justification is leverage of the cut property。Uing。是 part property。

If。All。啊， the。Edges in a craft。G二， you need。Then we know that for any cut。

All of the edges in that cut right all of the crossing edges in that cut must be unique。

 and we will never have a situation where there's multiple minimum weight crossing edges in a cut okay。

Let me quickly explain like why that implies multiple spending treess so what I'm saying is that if all of the edges in a graph are unique we will never have a situation where there's multiple minimum weight crossing edges in a cut。

😊，So let's explore a situation where there indeed is multiple minimum weight crossing edges in a cut。

😊，So let's say that we have the following cut。Okay， let's say this is our cut。

Notice here that is multiple。Minimum weight crossing edges in this cut， so。If I choose this。

Edge equivalently， we can also choose this one， right。

And that's why when we have multiple minimum weight crossing edges in a cut。

 it kind of leads to the possibility of there being multiple MTs， okay？😊，So， if。

We rule out this possibility because all the edges in a graph G are unique。We know。The minimum。

Waiade。Cl。Adge。我 every。Possible。Cut。妈s。D unique。And。And。The Mt。几。And what this applies is that if。

For any cut in the graph， we know for a fact that that minimum weight crossing edge must be in the MST。

 there's only one possible MST that could exist。There's no ambiguity here for every cut we know for a fact which edge is going to be chosen。

So we're never going to have a situation where there's an ambiguity。

And that ambiguity was kind of what I described in this situation。Okay， so。

I think that answers part one， let's move on to part two。

 Part two states if some of the edge weights are identical， there will。And the answer is here。

Is going to be sometimes be multiple MSTs in G。To arrive to this conclusion。

 let's kind of just play around with some examples and see what will happen。

So let's say that we have a triangle graph。I really enjoy tri's for example。

I want say that we give graduates to。And then we know that some of the graduates have to be identical。

 so I's just arbitrarily say two， two， and one， okay， and let's find the MST for this graph。Well。

 let's run cruise goals。 I like cruise schools。 Well， cruise goals。 what it's going to do。

 It's going to choose this edge first， right。Now， K skills is going to have a choice to make。

It could， either。Let me copy this。It can either choose this upper two edge or the lower two edge。

 And both of them are valid Mts。 So what we can see here is this graph has。Multiple MSTs。

And that's our first counter example。So to produce another counter example。

 we want to show a situation where a graph that has some of the edgeway that identical only has one MST right so that's a situation that we still need to think of for a counter example。

😊，So， let's see。I'll try to think of another triangle graph。And for this triangle graph。

 what I'm going to think of is some graph where the。

Edjects that are the same are smaller in value and the Eds are different， okay？So more precisely。

 this is my idea of becoming。And how I came to this counter of example is that looking at the previous example。

 we noticed that。We always choose the smaller edges first。

And it's the bigger edges that have that ambiguity。 right， So if all the smaller edges in this case。

And two ones are chosen first。Then we're not going to have that ambiguous choice later on when we write cruise skills。

 Okay， so these are the examples and we can move on to part three， okay。So。

Part three states if all of the edge weights are identical， they will。

And the answer here is actually going to be sometimes be multiple MSTs and G。

 So to kind of see why this is the case， I think intuitively always may seem to be the case。

 but there's one edge case that the always neglect okay。😊，So。

Let's start off with the situation where this only one MST。And this is kind of a subtle edge case。

 but if we ever have a graph that is itself a tree。

 then it has only one MST and that is itself right so if we ever have a graph that is a tree。

 we know that the only MST in this graph is itself。😊，So in this case。

 we have to choose all of the edges in that graph， and there's only one MST。

Our situation with multiple MSGs。It's actually rather easy。H。If all of the edges are the same。

 because we can just choose any v minus1 the that is and then we have an MST so long as those edges are a spanning tree。

So what I mean by this is let's say this is our graph。

 I notice I'm neglecting to put an edge weight since all of the edges have the same weight。😊，Now。

 here， if I choose any spanning tree。I's just choose this one arbitrarily。

 we know that this is an MST， right？And。Since we have a lot of edges。

 I can just choose any one of these， I don't know。Spanning trees， and I have a unique MST right。

 so there's multiple MSTs in this case。Perfect。😊，So let's move on to Part B。

 Part B statesS we have a connected undirected graphe with n vertices and n edges where all the edge ratess are identical。

 find the maximum and minimum number of MSTs in G and explain your reasoning。😊。

So this is a fairly challenging problem， and I definitely recommend pausing the video。

 giving him to try yourself if you haven't already before you watch this explanation。

So I'm going to push this problem is。Kind of leveraging what we knew from this past part。

If we ever have a graph that is itself a tree， we know there's only one MST， right？

And for a graph that to be a tree， it means there are n minus one edges。And in this case。

 we have n edges， so all we're really doing is we're taking a graph that has a tree or taking graph that is a tree and we're adding one edge to that graph and we're asking us asking ourselves。

😊，How many MTs can the insertion of that edge create。

So let me just kind of like joy out when I'm explaining。So。Suppose we have any graph that is a tree。

8。This is some tree。Now what we'll notice is that when we。Insert extra edge because we need n edges。

The insertion of that edge will impact how many MSTs can be there。Right。

If I entered the edge like so。Now， what we will notice is not。I could choose any。

Of these edges along this cycle。 and I will have a different MST。Right。Whereas if I could this？

Blue edge， like， so we will notice I can only choose。Different edges along this cycle。

 But all MSTs have to have this edge。Right。😊，And just to generalize this kind of idea that we're playing around with here is that if we。

 for any。Cycle in a graph。 Let's say we have some cycle。ok。

Let's say I don't know those graphs composed of other pieces。

If we ever have this cycle and all of the edge weights are the same， I can choose。Anynie。

N minus-1 edges on the cycle。Great and。Fully connect all of these vertices。ok。

So looking at this example， what we will notice is that for the MST for this graph I've created。

 we always have to choose these edges。But looking at the cycle， we can。Skip。One of these edges。

 right， I don't choose this edge。And I choose all of the others。And we get an MST。

How many edges in the cycle can we skip？We can skip every edge in the cycle and it produces a different MST。

Right， so in this case， what we will notice is that the total number of valid MSTs is going to be。

5 mD。Because one MST is going to neglect this edge， one MST isn going to neglect that edge。

And that and that and that， okay。So。Now， keep， we just keep generalizing this idea。

 let's say we have。Any tree， so。Suppose。We have。Any tree。Okay， and a tree has n minus1 edges。阿姨。诶佢啊。

with。And minus1 edge。Notice。The insertion。好。呃。Next， edge。Must create a cycle。And。

And what we've just figured out is that。If we ever have a cycle in a graph。

I remove any edge from that cycle and include all of the other edges。In MST。

 then we have a unique MST， right？So。Notice。The number。off。M S Ts is equal to a number of edges。

In that cycle。Can。right。And I just want to， I think it's problems with confusing I'm to give one more explanation of why this indicates case。

' say we have some graph。It's a tree。 This is a tree。 And then we add one more edge。

 right Now what we can see is that。If you look at every single possible MST of this graph。

I'm just going to quickly draw every single possible MST in the graph。

What we will notice is that each MST is simply neglecting one edge on this cycle。right。

And accordingly， to figure out the minimum and maximum number of MTs。

 all we need to do is figure out。What is the most edges that can be in the cycle and what is the least number of edges that can be in the cycle？

Okay。😊，so。Let's kind of add that here。We going delete this。🎼，Oh。就好。So。2。😔，Find the。咩得冇。And maximum。

Number of edges。My bad and the minimum and maximum number。Possible。MTs。We simply。你。2。Determine。

Number。Edges。In that cycle。So what is the minimum number of edges that can possibly comprise a cycle？

And we can see the minimum number of edges。In any cycle is three， right。

 we need at least three edges to make a cycle。maximumum number of。

Potenti be all of the ideas in the graph。 I have a graph。

And then the last edge added makes it such that all of the edges in the graph are part of the same cycle。

 So the maximum in this case is going to be。And。Okay， so one can see for any cycle， it could be。

At minimum three edges at maximum and edges， and we've realized from this example that the number of edges in the cycle is the same as the number of MSTs in the graph and accordingly we get the answers3 and n。

😊，So let's move on to party。PartC states that it's possible that Pris and crew schools find different MSTs on the same graph gene。

And as an added， exercise construct。Graph where this is the case。

So we're not going to do that in exercise， but you guys can see in the solutions。

So given any graph G with integer weight， integer edge weights。

 modify G to ensure that Pris and cruise schools will always find the same MST。

You may not modify ps or Crus so this is a good problem because sometimes in your life。

 let's say that your friend runss you run and you want same Well how can we ensure that without changings ands？

😊，系。So what we will leverage is the idea from sub part one of part A that states that if all of the edges in a graph are unique。

 there's only one possible MST， right， leveraging this idea。 What if we can take some graph G。😊，Okay。

 this is my idea。Then， modify it。So say we have a new graph G prime。Where。G prime。Has unique。

Edge weights。Well， a very silly way that we can do this is that。

We can just create a graph G prime where all the edge weights are different。

 but we also need to maintain that the MST。😊，In G prime。Mt。Also， the。MS T， N G。

So this is kind of what our task is as to recap we want。

Given a graph G to create a new graph G prime， G prime has unique edge weights， and in G prime。

 the MST that's found is also an MST in G。Right。So let's kind of like explore some ideas of how we could possibly implement this。

 so let's say that we have some graphji。😊，Sa this是 g。And's just great look at me。Eas意思。The one。第。So。

In order for the MSTs to be the same。We don't want to change each edge rate much。Right。

 one if we just。A really small value to each edge weight。I could say like 01。Well。

 this is kind of silly because if we add the same value to each edge weight。

 if we had two edge weights that were the same， right， Like suppose that these were both one。 Now。

 in the new draft， these will。😊，Also be the same。So what we need to do when we create a graph G prime is we want to add。

Let me just write this down because I think it's really important。小啲。Dear。Is we。Want。To add a unique。

I'm going to call it offset。Betweenen。0 and1。To each edge。Okay。

 so unique is really important because if we ever have two edges that are the same and we add that same offset。

 then they're going to be the same in the new graph， right？

And it's also important to understand here that since that。Eddge weights are all integer。

 It means that no edges or no two edges U and V will differ by more or by less than one。飞。Okay， so。

Let's just kind of like implement this idea。Looking at this graph。Okay， so what if we， I don't know。

 let's just say we decide to do this 1。1，2。2，3。34。4。well， this completely works。So。

I'm going to change this back to2。 The MT found in G prime is going to be the same as the MST found in G after I did this change。

系。Because we can kind of see here that the ordering of all of the edges is the same since this offset that we added to each edge。

Is smaller than one。 There's never going to be a case where if one edge is。

So I'm just going to write this down。By choosing。Offetss。Le。Then one。We will never。Have the case。

Where you is less than me。U and B are both edges。And G。But。U is greater than the energy prime。

Same as。系。So this is a really important conclusion that we've come across to is that by choosing offsets less than one。

 we know that for any pair of verticity earth。Edges U and V。 If the edge U is less than V in G。

We know that by adding something that's less than one。This will never be this case。

 never be the case that you somehow magically is now greater than V， right？So。

Adding one kind of preserves the ordering of these edges。8ight。

And let's imagine that when we run cruise schools， right Cru schools gives us an MST if we have a bunch of address that are ordered。

😊，And now we create a new graph G prime that has different edge weights since this property。Hs。

 we know that the ordering of the edges in G prime is the same exact ordering as the edges in G。

 right because of how we chosen these offsets so。In order to find a unique offset。

 there's many different ways of doing that， we can simply do this 0。1，0。2。3。4。

A clever way that the solution outlines is that what we're going to do。

This is like the solution and I'm kind of write it down here， is that for。😊，Each。Edge in。Zi。Okay。

 we're gonna take。We're going to have some offset value and it's going to start at 0。

And we're going to let E equal the number of edges。

So this is what the solution does and it's going to want to walk through it to show you why。

Each offset chosen this manner is unique and why each offset chosen this manner is also less than one。

 So we're going to do is change the edge weight。By adding offset to it。

 And then we're also going to increment offset each iteration by one over。一。Okay。

So let's see like how this is going to work in the graph from above。So。Looking at the graph above。

 if we run this pseudocode on this graph。And let's say that the graph is ordered by edge weight。

 what's going to happen is that this edge weight1 will stay as one。2 will go to 2。25。 We wrote to 3。

54 will go to 4。75。 and what we can see is if we do this for any。Science graph。

Mimum offset is going to ever be is E -1 over E is maximum。Offet。Will be。2。

And E -1 over E is always going to be less than one。So using this idea。

 just to recap what we're doing here is that。Given some graph G。

 we're going to modify it to create a new graph G prime where G prime has unique and weights。Okay。

 and how we're going to modify it is by running this code right here。

 So what this code does is it ensures that each edge in the new graph G prime。

Has a unique offset added to it such that now all of the edges are unique。

 All of the edge weights are unique okay。

![](img/43c32a6431a8b6a645f27a28e0e02b7d_2.png)

![](img/43c32a6431a8b6a645f27a28e0e02b7d_3.png)

And what we're also ensuring is that in our new graph G prime， if we had。

Any two edge weights such that edge 1 was less than edge 2 in G。

 We know that edge1 will still be less than edge 2 in G prime。

And that's because of how the offset is always going to be between zero。So。

That is all for problem too， I hope you guys enjoyed it and in the comments try to guess where this video walkthrough is being filmed。

 It's somewhere on Berkeley campus。 Al right， that's all Have a good day。😊。



![](img/43c32a6431a8b6a645f27a28e0e02b7d_5.png)