# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P21：-21-Advanced Algorithms (COMPSCI 224), Lecture 22.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

![](img/1de47791f78e65fc62fa5f382eb87df5_0.png)

还认为我。Maybe that was true。名出そこい。Okay， I think all。I's get started because it's already time。🤧嗯。Okay。

 so today or the next couple of topics。We're going to see today link cut trees。

There's a data structure。AndThat can be used to speed up blocking flow。

And we're also going to see like Min cost max flow。I don't know we're going to get to that today。

 but maybe Tuesday， but we're going to see link countries today。So before I。

Tell you what linknk cut trees are about。呃。Or like you know what operations they support， et cetera。

 let's just revisit the blocking flow algorithm that we looked at Tuesday， okay。

 so we saw on Tuesday。Blocking flow。The algorithm， you know was。Repeat， you know。Find。

A blocking flow。You know， augment。Flow by F。Iterate。

Until we can't find a blocking flow anymore until there's no more SD path in the residual graph。

Okay and。We said at the time。Was。Number of iterations。Times。The time。To find。A blocking flow。Plus。

 let's say M to actually perform the augmentation， but this is going to dominate them anyway。

And last time we said， look， they're at most。N -1 iterations because we proved this lemma that said every time you augment by a blocking flow。

 the new residual graph， the S T distance increased by at least one， right。

 So we said that that's at most n -1。 And we showed that basically by modifying depth for search。

This is O of MN。That's what we said last time。So。Link cut trees。This is due to slater in。Yet again。

JCSS。83。Can be used。To。Find a blocking flow。In time。O of M log n。Okay it's a data structure。

And it's a data structure that you can use to find blocking flow faster。

 and there are other applications of linked countries as well， which you might see in the final PSet。

So before I describe to you the operations that a link country supports。

Let's just look at what happens when you try to find a blocking flow in the level graph， right。

 so remember。Locking flow。Example。So let's pretend that we have。We have some level graph。This is ST。

 remember， all the edges go to subsequent layers， right， because we only keep。

Edges that go from one level to the very next level。So。Okay。So pretend that there is some。

There is some level graph that's hidden here where edges go to adjacent levels。

 and we start trying to find a blocking flow。 How did we find a blocking flow。

 We basically started at S。We tried to advance to T using DFS。

 And then when we finally were able to get to T， we augmented along that path。

Subtract it off the minimum capacity from everything in that path and then try to DFS again。

 So let's say we do our DFS。We find a path。We find a path that looks like this。

And now we're in the general capacity case。嗯。Good， so we're in the general capacity case。 We。

 we already， we already saw that。In in the unit capacity case。

 we could do this step in linear time in O of M。 So what I'm going to talk about is speeding up the general capacity case。

So now we subtract capacities。 we take the minimum capacity along this path and subtract it from everyone。

Okay。Some of the edges， at least one edge， but maybe more than one edge is going to become saturated now。

 right， It has no capacity left。And then。We kill that edge， right， so maybe now。Maybe now this edge。

Is out of capacity。And this edge。Is out of capacity。Right。So。

The edges that are still in play are these ones that are not xt。

So it's basically two different paths。This is a length one path， here's a length two path。Okay。

 so now。We're going to do another first search from S。 right。

 This is the algorithm from Tuesday to try and find T。So。Maybe we'll go this way。嗯。And what's also。

 let me also say， let me kill this one， too。 Let's say this one is also out of capacity。

So all that's left are these two edges here。So now we try and DFS out of S。 We'll go this way。

 We say， oh， there's an edge there。 there's an edge here。And there's also an edge。Let's say here。呃。

How do I want to do this？Let's say there's also。Let's say there's also an edge now here。😡，Okay。

 so normally。Normally now， so we're defssing we got here， normally we try to advance one more step。😡。

Right， and that's what we would do in， in what I described Tuesday。

 We would just advance one more step and try to continue on crit。

But if we somehow remembered in a data structure that， hey。

 there are these two edges that are still alive here。😡。

We should be able to just kind of skip right to here。😡，To the end of that path。Right。

And then from here we would say， oh， there's no way to get to tea and we'd backtrack and kill that。

And then we'd find some other path。We'd say okay， there's actually a way to get the T this way。

And then now some edges got saturated。 So now when we augment along this path。

 some edges get saturated。Maybe these two。And then the next time we do a DFS from S。

 maybe we'll go here。And then， we'll go。There's an edge that goes up here and then we'll say， oh。

We remember in our data structure that。These three edges already exist。 There's already。

 we can basically skip ahead and bypass DFsing all the way through these edges and just skip straight to T and then now augment along this。

Okay， so the point of link countries， I mean， you'll see exactly what they support， you know。

 and this might sound a little sketchy right now， but what they do is they remember these fragments。

That still have capacity left fragments that you had already explored and are still alive。

You should be able to， reuse that knowledge that they're still alive and jump ahead。Okay。

 so that's what link link cut trees support。 Okay， so let me。And by the way。

 these aren't necessarily always going to be paths， right？For example， you could have imagined that。

Actually。嗯。I went this way and then I jumped here。And then I skipped head to tea。

And then now maybe some edges get saturated。 So， for example， this edge got saturated。

 So now the fragment that's left is not really a path。 The fragment that that's left is this tree。

 right？ Imagine， right， to have this tree。That's left。So in general。

 what's going to be left are trees。The fragments that are leftover are trees。So link countries。呃。

It stores。Collection。Of。verertex is just joined。Rooted trees。Subject。To the following operations。

 so basically the operations that you need to be able to implement our blocking flow algorithm。

So what are those operations？Make tree。All this does is it makes。A new vertex。And puts。

In a singleton tree。So the very first step of the algorithm to find a blocking flow would be to run make vertex n times to create basically the empty graph。

Okay， Op 2。Is。Find root。That takes as input of vertex。That vertex is in some tree。

 it might be in the singleingleton tree。But it might be part of some bigger fragment。对。

It returns the root。Of tree。Containing V。And in this picture， I'm imagining that。

Roots are things that are further to the right。 So imagine taking this picture and rotating it。

 So T is the root of this tree。Okay， and it has one child， which has another child。

 this thing has two children。I mean， so find root is sort of exactly the kind of thing you would want to skip ahead。

 right you start if you get to a vertex。You want to know， can I jump ahead to the right。

 which is exactly fine root。Yeah。Why。Why is it always a tree？And not a dag。嗯。Hold on， let me see。

 So what would it mean for it to be a dag？呃。So the reason that it's not going to be a dag is。Good。

 so kind of of a path。 So you're gonna to see that you're gonna to see how we're actually going to call these subroutines in our blocking flow algorithm。

 But the basic idea is if there's already a path somewhere。

We're going to just take it using find root。We're never going to ignore a path that already exists and then try to discover things a different way。

Does that make sense？Like。So for example。You can imagine。Let me make this little space。

You can imagine we're in a situation where。We found a path。This is an ST path。

And then we did an augment。And then maybe now this edge got saturated。So now we want to start from。

Now we want to go from S and find another route to T。Yeah。

 so it it is what you're saying is correct in that， you know， if we had gone this way。

 maybe we would end up forming a dag。But。The way that we're going to run our algorithm is going to be such that if there's already a path out of S。

 we're going to use it。 So the very first thing we're going to do is find root on S。

 which is going jump us right back to here。And then we're going to say， okay。

 now can we get from here to T， Oh， we can't， So we're going to do a retreat as in Tuesday。

 and that's going to die here。And then。Maybe we'll find some other path。

And then now maybe both of these。Both of these are now saturated。

And then now we're going to find another path from city， but again。

 we're going to reuse this edge we're not going to as long as there is some path out of S。

We're not going to try and to explore a new path。 We're going to first take that path to its end。

Does that make sense？So yeah， so yeah。外てく。三位。And then we doS and end up somewhere in a different part of it。

That we just came from。 So wait， So first of all， in the level graph， edges only go forward in level。

 The level graph its， the level graph is itself a dag。So we're never。

 I don't know if I understand your question exactly， we're never going to cycle back。

Since the base graph that we're building this on is a Dg itself I'm imagining。Yeah。Like。Okay。

 I guess we always。The node we end up。Thats always the right most。Lo that。

mean we we at the highest level of any vtex。Right， we are， that's right。The furthest to the right。

Right。Very good。Okay， so okay， good。So we are going to maintain the invariant that the underlying graph is always a forest。

 a collection of rooted trees。Another thing we're going to want is cut。What does cut do？It。

Destroys the edge。V parent V。对。Which is what we're going to want to do when we retreat。Right。

So I'm imagining。We get somewhere。I don't know， we get somewhere where we realize， oh。

 there's no path。Okay， so let's say we got here， we realized there's no way to get the T。

 so we retreat now I'm going to cut on this vertex and that's going to remove this edge。Okay。

 another thing we're going to want to do is。Min cost。Or not men cost min capacity， I guess。

 let me call it fine min。What does fineine MinV do？Returns。The lowest。Capacity。Edge。On。The path。

From V to its root。V is in some tree。Look at the vetta root path in that tree。

And then return the lowest capacity edge if there's a tie。呃。Return。Edge。Closeest to the root。

Another operation we're going to want。Is， let's say subtract。Vx。And what does that do？Subtracts。X。

From。Every edge。On the。On the V。To root path。SoFrom capacity。

Aapacity of every edge on the Vta root path。And one more。Or maybe two more depending on。Okay。

 so another one is add flow。嗯。Vx。Which is add。X to。A。The flow。Variable。For every edge。

On Veta roototpath。Okay。And every edge that's going to be alive in our tree is going to remember both its capacity and its flow。

 So if you give me an edge， I， you can just read off。呃。Both of those。Things okay so。うん。

Now let me just write down some pseudocode of how you would actually implement blocking flow using these procedures。

So。Before I do that， are there questions about what any of the operations mean？Wo。

I'll write down the pseudo clip for blocking flow。 and hopefully， yeah。Yeah。

 I guess maybe Op 6 Operation 6 might have been redundant yeah。嗯。Might have been written。

Because another thing you could do is just right， you know all the initial capacities of all the edges。

 and then at the end at the end of running everything。

 you know what the new capacities are so you can infer what all the flows had to a been。Yeah。

 so you actually yeah， you don't need it for 6 separately。Okay， so blocking flow。

 So how are we going to implement this， So initially。Make tree。And times。And then I'll say。You know。

 while。True。嗯。So， V。Is。Find root。On S。Now， if V happens to be T， I'm happy。Okay。

 and then I just augment if v is equal to T。I'll use this notation if V is equal to T。嗯。Then。

Let's say。When me use comments， I'll comment my code， it's good practice。So。

Just to tell you know how。How Find min returns the edge to you， so let's say Zx。Is fine men。And yes。

Okay。Yeah。Trees that have more than one vertex， did I not write link？Oh， well， no。

 there's I meant to write that around link， around cut。 So there's also。An operation link。VW。Okay。

It assumes。That V is the root。Of its tree。Okay。And it makes。

It also assumes that W&V are not in the same tree already。Very different trees。It makes V a child。

And I guess you'll also give it。You'll also give it some number， which is the capacity of that edge。

With capacity。Yeah。So I mean， W will be something on the next level in the level graph。But initially。

 so there are two graphs， right， there's the level graph， which all of this is being built on top of。

But then there's the graph， which is the collection of trees we're maintaining。

 which you can think of as being a subgraph of the level graph。

So initially the graph we're maintaining is empty， there are no edges at all。

And then we're slowly adding edges in the level graph as we go along， building our blocking flow。

Does that make sense？E you still thinking？So the vertices。

 these n vertices that I'm making in this graph。So let's say that the level graph is L。And the graph。

 the graph I'm building， which is this collection of trees。 let's call it。H。So initially。

 so L and H have the same vertex set。Okay， and H is going to be a sub graph of L。Yeah。

 they have the same name。Yeah， just think of them as being the same vertices。 It's a different。

 it's a different。So just think of H as being an actual subgraph。Yeah。

And you know who their neighbors are now。Yeah。Does that answer your question？Any more questions？Okay。

 good。So this is going to be the minimum so the minimum edge。

 minimum capacity edge from S to T is the edge Z parent Z， and it has some capacity X。

And what we're going to do is we're going to， well， as you said。

 we don't really need to add flow because it's all implicit。

 We can know what the flow was at the end anyway。What we can do is we can subtract。Sx。And then cut Z。

And then delete。Z， parent Z。From the level graph。Which we can do because we know the correspondence between vertices。

And then。Continue。I mean， go back to the top of the loop。Okay， so that's one case。

 That's the case where V is equal to T。Otherwise。So what do we do， we want to try to advance， right？

So。We'll try to do that。Else， you know， I'm using my comments。If。Let's say from the level graph L。If。

V。😔，Has outgorowing。Edge。Just some W。In L。Then what do we do。What should we do？啊。Yeah， okay。

 but I mean， there's so what operation do we do in our country？We link， right？

So remember V is the root did find V is the result of find root， it is the root of its tree。

 and now there's some other W which we know we can connect to， so we wanted to link V to W。link。

V V to W with the capacity。With weight， capacity of that edgeVW and L。

so we tried to advance otherwise。Otherwise， we can't advance， so we retreat。So what do we do？嗯。Well。

 first of all， if v is equal to S。Right， that means there's nothing left to do。We break。We're。

 break out of the loop。Otherwise。Otherwise， what we're going to do is retreat。And delete this edge。

For each。Child。Let's call it Y。And we can be aggressive about it， right， I mean， we can basically。

 I mean， if we know that， if we know that there's no， nowhere to go from V。

We don't only have to delete the edge that， that LED us to V。

 We can basically delete anything that's coming into V。Right。

 because we know that V is basically a useless vertex from now on。So for every child。Y a V。We'll cut。

Why。And then we'll delete。Y V。From L。O以。That's walking for。So。I mean like cut， the cut operation。

Remove anything。So what does retreat do， Retat deletes the edge that just led you to be。Right。

 so Rick。When you say remove a descendant， what do you mean remove the descendant？

 So we're not removing vertices here。 I mean， we are removing the vertex V。But there might be， right。

For example。This is now a worthless vertex。But， you before we let's say there was a situation where this thing was not quite saturated yet。

But still， it's a worthless vertex， right if we ever now now this situation would never actually happen。

 but because of this。Right。At some point， we're going to reach here and realize it's worthless and want a retreat。

We shouldn't。 I mean， we should delete this edge， right？We should get rid of this。

But we shouldn't do things to its descendants because， you know， maybe this， this。

 this vertex here might have some other way to get。to get there and also this vertex itself。

 like this edge might still be useful because evidently it was because then we reroouted this way。

 for example。So we're only deleting the edges that come into that vertex。Yeah。さめちだ恥かった。や所まです。八十ろ。

Oh yeah。 but but but yeah， that's a very good point。 So that's， but that's exactly。

 that's exactly why I wanted to return the edge closest to the root because what's going to happen。

 right， So that's a very good point so。Here's S， here's T。We found a path from S T。

Maybe it happens that these two edges。Are now saturated。When we do find men。

 it's going to return us the one that's closest to the root。And then we're going to delete it。😡。

I'm sorry。So actually let me not cross it out yet because we haven't actually deleted it yet。

 let me just draw it in yellow to say that it's saturated， okay。So， so good。

This edge is so the graph that we're maintaining in our link country has all four edges right now。

But then we do find man， we realize that this thing is zero， we delete it。

But S is still in this tree。 So the next time we go to the top of the loop。

 we're going to do find root on S again。Right。And。Oh， I see。 so do I need to？还有。Right。

 so I might need to do this， I might have a little bug here where I need to repeatedly Yeah。

 I need to repeatedly find min on S over and over again and remove everything that has zero capacity。

 Yeah， programming is without bugs is hard。 Oh yeah。How I by there。I'm sorry。不他 to。Or you mean。

 redefine Feynman？Yeah， you could do that。 I mean， but then the。So later。

 I'm going to write the code for Feynman。And then I would have to make that longer。

 So I could just say， I could just say， as you said， so。Of equals T。So do this。

And then now in here somewhere， I guess。So。Finddman。In a loop。To remove。Zero capacity edges。

Does that me？Right。You， you keep finding loop。 you keep fine min until there are no zero。

The zero capacity edge just left， and then each one you find you delete it。So I think now I'm。

Im sorry。Yeah but you're talking about the implementation of cut， right。

 what you're talking about will be handled in the implementation of cut。

You're saying that when I remove edges， I have to change who's the root， right？But， I mean， cut will。

I'm assuming that these operations have been implemented for me， right， And。

 and I just want to use these operations。 These are my abstract operations。Yeah。Oh know。

 that edge is still alive as a fragment。 So at the end of this， these two things will be deleted。

And then what will be left are。Are these two edges。Two separate trees， each is a single edge。Well。

 technically， one， two， three， four， five trees。呃。No， three trees， three trees。

 two of them will have singleleton edges。Two of them will have a single ledge and one will be an isolated vertex。

Yeah。So I said it again。Yeah。I him is quite notifying'm saying。Go back。Yeah。Yeah， I mean。

 yeah you don't have to do it。It'd probably be smarter to just stay where you are because you know that you're gonna just jump right back there at findroot。

 I was just trying to write the shortest correct code I could。 And I still， yeah。

 and I still had a bug anyway。The lowest capacity edge。Yeah。

 but then so you basically you keep running this， you keep running F min over and over again。

 And then once， once it returns an edge， that's not capacity0 anymore。 then you're like， okay。

 I'm done cleaning up all the dead edges。I'm sorry。Yeah， five minutes of us， five minutes of us。

Fman of S。Over and over again。Yeah， you can， I think that's correct。 You can think about it， but。

But why do you care？whyhy do you care about that， I mean。

 you're always removing the one that's closest to the root of S's tree。

So all the ones you need to clean up after that are still a part of Es's tree。Okay， so yeah。嗯。

So what I want to say。TheThe basic idea。Of linked countries。Is。To store。诶。These， potentially。

Unbalanced。Potentially， unbalanced。Trees。Using balanced binary search trees。

You know you'll see what I mean right， so these these trees in our collection。

They're not binary trees， right， They could be really badly imbalanced。 We have no idea。

What they look like other than their trees。And actually， we're going to use s trees to。

Inside of this implementation， you'll see how in a second。Just to tell you what we're shooting for。

You what's the running time now of blocking flow， right？嗯。So。Every time we go through this loop。

We're going to delete。嗯。We're going to delete an edge right， so every time we， how should I say this？

嗯。So okay， good。Whenever you go in this loop。There are three cases of where we could end up。

 If we link， that means we explore an edge for the first time。 that can happen at most M times。嗯。

This case。Can happen also at most M times， right， because we can， you know， the edge gets deleted。

 so we can't delete more edges than exists。 So this happens at most M times。Also， when we augment。嗯。

Notice that。To realize that we had to augment was a single operation。

 we just figured it out from a fine route。So we're doing one operation here。

 and then all the additional operations that happen from fine mins in aggregate that can't happen more than m times because every one of these fine mins。

 except for possibly the last one， results in an edge deletion。Okay。

 so the number of times we perform link cut operations overall is E。Okay。

 so if we can show that we can perform every single one of our link cut operations in login time。

That will give M times log n blocking flow。So really the name of the game is get everything in log in time。

Okay， so today we're going to see how to do。Amortized， we might not see the whole thing for log n。

 maybe we'll see log squared n， but it is possible to get log n。

But it's also possible to get a worst case log n bound。 We're just not gonna do that today in class。

 so you can。You can look at the paper if you want to see how to get a worse case bound。

 the data structure itself has to get a little bit more complicated。Okay， so。

We're going to use something called- so we have this tree， let me draw a tree。

There's going to be a collection of trees， but let me just draw one of them。So。我跟他。嗯。

Maintain something called a preferred。Maintain。For each tree。A。Preferred。Palf。Decomposition。

What do I mean by that？Every vertex。Except for the leaves， we'll have。A。Preferred。Child。

And how is that defined？Preferred child。A V is equal to。Nan。

So vertices can also not have a preferred child at all。It's none。If V was the last。Noode。Accessed。

In its subte， you'll see what I mean by accessed very soon。Otherwise。It's。Child。Containing。The subt。

The child。Containing sub tree， containing。The last access node。And V is sub。Otherwise。Okay， so。

So for example， I mean， I haven't shown you what access means， but access means， but。

Let's say that the last。No that was accessed period in this tree is that one？And let me give it。

Another child， let's say the last node access was that one。

Then the preferred child of this node is which of its children is an ancestor of this。 Well。

 it's the left one。 So that's the preferred child。 So this edge， I'm going to call a preferred edge。

And similarly， for this one。嗯。What's its preferred child， it's that one。And then， you。

 maybe this guy even himself had some children。But what's his preferred child。

 he doesn't have one because he was the last。No access in his suby。

So if he himself has the last node Access in the century， he doesn't have a preferred child。

So then now。Now we can look at preferred children of each one of these guys。

 maybe this guy's preferred child this is the love child。Maybe this one。

 the preferred child is this one。And then this one and then that one。Okay。So。Yeah。The children。

So I say it again。Yeah。Yeah， so then he might， he himself might have a preferred child。

 which might be， I mean， he himself might have been the last node accessed in his own sub。

 in which case he wouldn't have one， but he， he could have one。 This could be his preferred child。

There could be， yeah。What do you mean thatre be multiple those that are hyperfer children？Yeah。

 so look at this node， compare him to everyone in his subre。

 Look at who was the last access node in this subree。 If it was him himself。

 he wouldn't have a preferred child。But it might not be him himself。

 in which case he would have a preferred child。So。An edge。Leading。To a preferred child。Is called。

A preferred edge。And。So what I've done here now is I've drawn a bunch of preferred paths， right？

Just take like the maximal- so a preferred path is a maximal chain of preferred edges。A maximal。

Chain of preferred edges。So。Now， the what is the。What is this preferred？Preferred path decomposition。

 basically now you can imagine collapsing。嗯。Collapsing the preferred paths into like single vertices。

Right。So。Here's one。Here's another one。Here's another one。And here's another one。Okay。

So we have sort of a tree of paths。And then there are these white edges。

That connect these paths to each other。So。The preferred path decomposition。Its a tree。

On the preferred path。So our data structure of the Li country is going to explicitly maintain。

This preferred path decomposition。Okay。So how are we're going to do that？So each one of these paths。

We're going to store。In a balanced binary search tree。

So we're not actually going to store in a balance binary search tree。

 We're going to store it in display tree。But you could store it in a balanced binary search tree and get say log squared endbound。

But I'm just going to skip straight display trees so that we can get the log endbound。little store。

So you should ask me a question right now， right， it's a binary search tree。Right， so what's。

 so what what do I mean storing a balanced binary search tree， What's this， you know。I don't know。

 Does a question come to mind， as I'm writing this。Yeah， exactly。 What are the keys。

 What's the ordering， So we'll store each preferred path。In a s tree。

 which you guys have seen a while ago。Keyed by depth。

So someone higher in the tree is smaller than me。Higher node。In the tree。It's smaller。可以。Yeah。

Is this the。OhSo so let me draw a picture now going back to that。I back here。

So let's see what would happen here。Basically， these three nodes。Would let me call the。

 let me call this。A。B。this is C here。And D。Okay。We'd have some display tree。Sttoring the nodes of A。

Then we'd also have a splay tree。Storing me。But。There would be。A parent pointer。

 a path parent pointer which。Which will store at the root， let's say， of B。

 that'll just tell us where does this hang off of。It'll tell specifically which node does it hang off of。

 so there'll be a pointer。Say like this。Telling us basically this， like remembering this edge。

There will also be a tree for sea。And there'll be a pointer remembering that edge。

There will also be kind of a singleton tree corresponding to that vertex here。

And then we'll remember that edge。Okay。So they'd be like this tree of trees。Does that make sense？

Let's well call。Theplay tree。To store a path。And。Auxiliary tree。And the actual。

The actual tree that we're actually maintaining in the link cut tree， let's call this tree T。

The actual tree T。Is what we call the representativeatory。So。And。The root。Of。Each auxiliary tree。

Has a。Half parent。Pointer。Telling us。The root。tellingling us the。Parent。Of the。Top note of the path。

In the representative。So those are these white sly lines。

 basically telling us how does this path connect up to the rest of the tree？Yeah。

So I can you say that one more time？How are they？So B， B has a child which just a single thing。

 That's right。But I guess。Wait， this is actually， this should have been part of B， right。

 I said that was preferred。But yeah， you're still right in that。This is all part of B。But yeah。

 this is a child of B。So this node。Well remember so this is going to be a singleton tree。

 a singleleton auxiliary tree。 It's going to remember who its parent was in the actual tree。

But B won't remember。The auxiliary tree in bee won't remember who's hanging off of it。Yeah。

 they won't need to remember that。More questions？Okay。So good。

 so now I want to talk about how to actually implement operations。Okay， so。

We'll have a helper operation。Which all the other operations will use。Which I'll call access。

So I remember I said that， you know， the definition of the preferred child is in terms of。

The last access。Right， so。For that to make sense， I need to tell you what access means。

 So there's actually going to be a subroutine that we're going to call a bunch of times called access。

So first of all。What happens when you call access V just by what I've said already？

AccessV is supposed to change。This decomposition， because now the root to V path。

Is now a preferred path。Right。So the root of B path is now going to be preferred。And。That means that。

Some of the paths， which were preferred before are no longer preferred， right， Some of the children。

 some of the preferred children change。 So， for example， a V。

Let's say that I now access this vertex right here。So now this path is a preferred path。

Which means this is no longer， this edge is no longer preferred。 This edge is still preferred， right。

 but this is no longer preferred。 This basically switches over to there。So once we touch V。

 we need to walk up back the tree and make sure we change the preferred children of the roots。

And this might change who needs to be in which ox tree we go up as we go upward。

 but we're going to fix that。Say so。Mix。The root。To V path。In the representative tree。

 let's say in that tree T。RightIn reality， remember。

 the link country maintains a collection of trees， so each tree in our collection will have this kind of decomposition。

And we'll maintain tree of ox trees for each one of them。Okay， got it。呃。

How are we going to do the implementation？So we're going to make sure。So first of all， right。

 first of all， once V is on once the route of V path becomes preferred。

 And remember now none of these children， V might itself have some children and one of them might have been preferred。

 Now， none of them was preferred right， because by the definition of a preferred child and V itself was the last node。

It has no preferred child。So you might have to cut off some of cut off its preferred child。Okay。So。

The way we're going to implement this is so now after V has been accessed。

 it's part of the root auxiliary tree， it's part of A， basically。

And we're going to make sure that not only is it an A， but it's actually the root of A。😡。

Which is spplay， basically， right？So make sure that。Make sure V is the root。Of the root。

Is the root of。The root of the root of the tree of ox trees is that so there's a tree of ox trees。

And its root is a tree。And I want V to be the root of that。

So make sure that V is the root of the root。Of the tree。Of ox trees。Okay， so。

That's how we're going to implement it and how exactly do we do that？So。Let's say。V is in some。

Ox tree。Which is a s tree and one it is a s tree， so it has some。You know， there is。There's V。

 this is an ox tree。Okay。So now。We're going to s。V。So now。This is V。And now it has some children。

 It has a left subt。It has a right sub tree。This is still the ox tree that it's in。Right， this a。

The ox tree itself。呃。This ox tree itself has。Has a path parent planer。Right。Okay， so。

Now V is the rubric。 So what can you tell me about one change that definitely needs to happen now？

V has no preferred child， right？So what does that mean？Both subries。

What's in the left sub and what's in the right sub， How is this tree keyed。By depth。

So who are these guys and who are these guys？Yeah， people above me in the path。

 so I need to cut out the right basically， right？Because now V has no preferred child。This is now。

Removed。对。So let me call this vertex R。So now what I need to do is I need to say。V dot right。Well。

 I didn't even need to name it V dot right。t path parent。Is equal to v。

 and v dot right now is equal to none。Okay。But then now， so that's now fixed。

But now we need to go up the tree and start changing preferred children up the tree。Okay。So。

So now we're in the situation where V is here， it has no right subte， but has a left one。

 and then this is the oxux tree。And then。It has some other tree up here。

let me draw this a little bit lower。So V is here。And it's a tree。It has no right child。

There's a path parent pointer。That points to some W。And some other ox tree。

Now W doesn't have to be the root of its ox tree， right， is's just somewhere in that ox tree。Right。

Who's W， W is the parent of the lowest of the minimum key element in this tree。

Because the minimum key element of this tree is the root of the path。And then his parent is doub。

 that's what this means。So now what we're going to do is we're going to。Basically。

 make room to merge the trees。How are we going to do that？Well。We are going to。Spplaylay。W。Okay。

Now what happens when we split W？😡，Now this。Now this turns into。This is V。

And now W is the root of its tree。And it has some left and some right tree。So now whats。

 what does it mean that So what's the new preferred child of W of W。

 The new preferred child of W is the smallest element in in this tree， right？

 It's no longer who it was here。But who was the preferred what was the preferred kind of descendant path out of W here。

The right subree。So that needs to change。Okay。So we're going to do。W dotright。Dot path parent。

Equals W。 And then。呃。W。right。Dot parent。Is equal to none。Or I should have done that here to V。right。

parent has none as well。In the a tree。So basically we changed the parent pointer into a path parent pointer。

And then now who's going to be the new right child of W？Yeah。Okay呃。I'm now running out of space。

 I should。Soaw this coming and now V dot parent。V dot path parent。I iss none。

 It doesn't have a path parent anymore。 It's an actual parent now。 V dot parent is W now。

And then we display B。Right， so remember what I said。

 the plan was make sure V is the root of the root of tree of ox trees trees。

So we've now spliced V into its parent a tree。But I'm not satisfied with that。

 I wanted to actually be the root of everything。So then finally， when we do that。

 we splitplay it again。And we basically do this in a while loop until we're actually at the root O Street。

Right。W。What do you mean， why already you say that？So just like so W's s tree。

 This ox tree no longer has a right child hanging off W， right， This got kind of branched off。

 This is now its own ox tree。And now we just take this ox tree and make it。

Fit inside this oxygen tree。 You basically make this take the place of that。

I also need to make sure that I change V's pathth parent to be W's old path parent。V is now the root。

 So it's path parent， right， So now V dot path parent。Is w。path parent。

And W no longer has a path parent。Sorry， this is terrible。

You need to make sure you maintain the path parents。Okay， but hopefully the idea makes sense。

Does the idea make sense， Does the idea not yeah？Right， in its path。 So V is somewhere along。

 V is in this path， right。Not the descendants， the people above it in the path。

Everyone here is higher than V in the path， V is the bottom of the path。Right。

And then we know that this path links up to W。So we basically kind of spliced those two paths together。

And cut off everything that was below W before。Baically， W's preferred child just changed。Right。

Because everything here is hanging off of W。 W had some old preferred child。

 but now has now that V has been accessed。This path is now the preferred path leading out of W。

 not the old one。So this lets us cut off the old one and insert the new one。Highest。No。

 because everything everything here， everything here is at a lower depth than W is。😡。

Everything here is at a lower depth than here。Because everything here hangs off W in the represented tree。

Right， so it's， it's valid to put everything here to the right of W。Does that make sense。O wow。

 that was。Painful。I she不存担。Okay， so that's access。That's really all there is to access。 Not that。嗯。

I have。The runtime。Of access。Is。It， depends on。The number of preferred。Child changes。

After accessing me。Yeah。Essentialsically， every time。You know， when do we。

 basically every time there， there's every one of these kind of。

Tree splicing operations that we have to deal with in this loop。

Corresponds to some W having its preferred child change on us。

So the number of times we have to deal with this splicing is the number of preferred child changes。

As you walk up the tree。So。Oh， anyway， this is going to be important when we actually really analyze it。

 but now let me write down operations。So now other ops。

We're always going to do fight like we're always going to start every operation with access。😡。

So the node of interest is always going to be the root。So find root。First， access V。

Now who's the root of these three now？Who's the root of V in the。

W's the root of V in the represented collection of trees？V is in some a tree now。

 it's the root of all the a trees。啊。T， wait what's when you say tea， what do you mean by tea。

So I mean， it's rude as a vertex。Right。So who's its root？The point is after you do an access。

V is now the root to V path is now the preferred path， that entire path is the root a tree。

So who's the root of V of theses tree in the represented tree， it's the lowest depth element。

It's the lowest depth element in VOx tree。😡，So first access V and now return。Lowest。depth。Element。

R in Vs oxox tree。And for good measure， we'll also just now access R。Okay， how do you do？Find men。

You access V。诶。Return。Min value。In Vi O Street。So。I don't want to get too much into this。

 but if you haven't seen this， maybe you should read more about it。

balanced binary with binary searchries in general， you can augment them。

Which lets you do things quickly such as。You know， compute the sum of all elements in an interval in a key interval or find the minimum value in an interval of keys。

 These kinds of things you can do by augmenting a search tree， a binary search tree。 So， you know。

 you can， you can。You can very easily do this。 V is now the root just by looking at some augmented value stored at V。

 You can figure out what the minimum value is， minimum capacity in V's a is。

So I'm not going to get into the detail。cut V。We're going to access。A V。Okay， so now what？Now。

 how do we finish the implementation of cut。We're cutting V from its parent。In the representativeary。

 who's its parent after we've done an access on V。The left subt is the tree that。Contains the parent。

 so now V dot。Left is equal to。Lift up parent。Is none。And V dot left is none as well。

You can also do link。VW。No I'm not going to so you can deal with the weights also。

 but that's going to be a minor thing。So， access V。Remember now？

V andW live in two different represented trees。O。And then access W。And now V dot left。

So W is the parent of Vino。😡，So V dot left is W。And W。呃。Don't need doubt parent。Is V， right？

W is on the left， which means it's higher than us in the tree。Does that make sense。That's right。

 There was nothing at a lower depth than V in it serves energy。So these are all the operations。

 Oh I mean， there's the other one， subtract， et ceter。

 you can do those as well by doing this trick of augmenting your binary search tree。Okay， so。嗯。

You can do this as an exercise。 But now the question is just。对。So all the code is laid out for you。

More or less， so now it's just a matter of proving the runtime bound。

And I think what I'm going to end up doing is Tuesday I'll show you log squared N。

 and then your final PSEC， I will make you prove log N。With hand， maybe。Okay。就在这里。



![](img/1de47791f78e65fc62fa5f382eb87df5_2.png)