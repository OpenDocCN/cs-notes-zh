# 哈佛大学【中英⚡高级算法｜Fall2014 COMPSCI224 Advanced Algorithms】 p21 P21 -BV1zNSCBkEgW_p21-

![](img/0e4de161d81b6a9975435ee9ff28d93f_0.png)

还认为我都。Maybe that was。ラブたつはこい。Okay， I think on。I's get started because it's already time。🤧嗯。Okay。

 so today or the next couple of topics。We're going to see today link cut trees。

There's a data structure。AndThat can be used to speed up blocking flow。

And we're also going to see like Min cost max flow。I don't know if we're going to get to that today。

 but maybe Tuesday， but we're going to see link countries today。So before I。

Tell you what linknk cut trees are about。呃。Or like you know what operations they support， et cetera。

 let's just revisit the blocking flow algorithm that we looked at Tuesday， okay。

 so we saw on Tuesday。Blocking flow。The algorithm， you know was。Repeat， you know。Find。

A blocking flow。You know， augment。Flow by F。Iterate。

Until we can't find a blocking flow anymore until there's no more SD path in the residual graph。

Okay and。We said at the time。Was。Numb of iterations。Times。The time。To find。A blocking flow。plus。

 let's say to actually perform the augmentation， but this is going to dominate them anyway。

And last time we said， look， they're at most。N -1 iterations because we proved this lemma that said every time you augment by a blocking flow。

 the new residual graph， the S T distance increased by at least one， right。

 So we said that that's almost n -1。 And we showed that basically by modifying depth for search。

This is O of MN。That's what we said last time。So。Link cut trees。This is due to slater and。Yet again。

JCSS。83。Can be used。To。Find a blocking flow。In time。O of M log n。Okay it's a data structure。

And there's a data structure that you can use to find blocking flow faster。

 and there are other applications of linked countries as well。

 which you might see in the final PS Act。So before I describe to you the operations that a link cut treee supports。

 let's just you know look at what happens when you try to find a blocking flow in the level graph。

 right， so remember。Bocking flow。Example。So let's pretend that we have。We have some level graph。

This is ST。 remember all the edges go to subsequent layers， right because we only keep。

Edges that go from one level to the very next level。So。Okay。So pretend that there is some。

There is some level graph that's hidden here where edges go to adjacent levels and we start trying to find a blocking flow。

 How did we find a blocking flow， we basically started at S， we tried to advance to T using DFS。

 and then when we finally were able to get to T， we augmented along that path。

Subtract it off the minimum capacity from everything in that path and then try to DFS again。

 So let's say we do our DFS。We find a path。We find a path that looks like this。对。

And now we're in the general capacity case。嗯。Good， so we're in the general capacity case。

 We already saw that。In the unit capacity case， we could do this step in linear time in O of M。

 so what I'm going to talk about is speeding up the general capacity case。

So now we subtract capacities。 we take the minimum capacity along this path and subtract it from everyone。

Okay。Some of the edges， at least one edge， but maybe more than one edge is going to become saturated now。

 It has no capacity left。And then。We kill that edge， right， so maybe now。Maybe now this edge。

Is out of capacity。And this edge。Is out of capacity。Right。So。

The edges that are still in play are these ones that are not xted。

So it's basically two different paths。This is a length of one path， here's a length two path。Okay。

 so now。We're going to do another first search from S。

 This is the algorithm from Tuesday to try and find T。So。Maybe we'll go this way。嗯。And let's also。

 let me also say， let me kill this one， too。 let's say this one is also out of capacity。

So all that's left on these two edges here。So now we try and DFS out of S。 We'll go this way。 We say。

 oh， there's an edge there。 there's an edge here。And there's also an edge。Let's say here。呃。

How do I want to do this？Let's say there's also。Let's say there's also an edge now here。😡，Okay。

 so normally。Normally now， so we're dfssing we got here， normally we try to advance one more step。

Right and that's what we would do in what I described Tuesday。

 we would just advance one more step and try to continue on critique。

But if we somehow remembered in a data structure that， hey。

 there are these two edges that are still alive here。

We should be able to just kind of skip right to here。To the end of that path。Right？

And then from here we would say， oh， there's no way to get to tea and we'd backtrack and kill that。

And then we'd find some other path。We'd say okay， there's actually a way to get to T this way。

And then now some edges got saturated。 so now when we augment along this path。

 some edges got saturated。Maybe these two。And then the next time we do a DFS from S。

 maybe we'll go here。And then， we'll go。You know， there's an edge that goes up here and then we'll say。

 oh。We remember in our data structure that。These three edges already exist。 There's already。

 we can basically skip ahead。And bypass DFSing all the way through these edges and just skip straight to T and then now augment along this。

Okay， so the point of link countries， I mean， you'll see exactly what they support。 you know。

 and this might sound a little sketchy right now。 but what they do is they remember these fragments。

That still have capacity left。 fragments that you had already explored and are still alive。

You should be able to reuse that knowledge that they're still alive and jump ahead。Okay。

 so that's what link cut trees support Okay。And by the way。

 these aren't necessarily always going to be paths， right？For example， you could have imagined that。

Actually。嗯。I went this way and then I jumped here。And then I skipped head to tea。

And then now maybe some edges get saturated。 So， for example， this edge got saturated。

 So now the fragment that's left is not really a path。 The fragment that that's left is this tree。

 right， Imagine， right， I have this tree。That's left。So in general。

 what's going to be left are trees。The fragments that are left over are trees。So link countries。呃。

It stores。Collection。Of。You， verertex is justjo。Rooted trees。Subject。To the following operations。

