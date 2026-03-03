# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P56：12_02_04_Dijkstra算法正确性证明.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

In this video， I'll prove to you that Dysster's algorithm does indeed compute correct shortest paths in any directed graph。

 where all edge links are non negative。Let me remind you about what is Dkster's algorithm It's very much in the spirit of our graph search primitives in particular breath first search so there's going to be a subset x of vertices which are the ones that have been processed so far initially x contains only the source vertex of course the distance from the source vertex to itself is zero and the shortest path from S to itself is the empty path so then we'll have a main while loop there's going to be n minus1 iterations and each iteration will bring one vertex which is not currently an x into capital X。

An invariant that we're going to maintain is that all the vertices in X we will have computed estimates of the shortest path distance from S to that vertex and also will have computed the shortest path itself from S to that vertex remember our standing assumptions stated in the previous video we're always going to assume there's at least one path from the source vertex S to every other destination V our job is just to compute the shortest one and also we have to assume that the edge lengths are non negativegative as we've seen otherwise Dx's algorithm might fail Now the key idea in Dx's algorithm is a very careful choice of which vertex to bring from outside of x into capital X So what we do is we scan the edges crossing the frontier。

 meaning given the current edges vertices that we've already processed。

 we look at all of the edges whose tail has been processed and whose head has not been processed so the tail is in capital X the head is outside of X that is they cross the cut from left to right in the diagrams that we usually。

Draw。Now there may be many such edges how do we decide amongst them while we compute the diyxster greedy score for each the diyster greedy score is defined as the shortest path distance we computed for the tail and that's been previously computed because the tails in capital X and then we add to that the length contributed by this edge itself by the edge VW which is crossing the cut from left to right So amongst all edges crossing the cut from left to right。

 we compute all those greedy dister greedy scores， we pick the edge with the smallest greedy score calling that edge just v star W star for the purposes of notation W star is the one that gets added to x so it's the head of the arc with the smallest greedy score and then we compute the shortest path distance of that newu vertex W star to be the shortest path distance to v star plus the length contributed by this edge v star W star and then what is the shortest path it's just the shortest path previously computed to V star plus this extra edge v star W star tacked onto the end Here's the formal statement。

We're going to prove。For this video we're not going to worry at all about running time。

 that'll be the discussion of the next video we'll discuss both the running time of the basic algorithm and a super fast implementation that uses the he data structure for now we're going to just focus on correctness。



![](img/c8b7d2217133f62c42bc006238e70dbe_1.png)

So the claim is that for every directed graph， not just the four node 5 Arc example we studied。

 as long as there's no negative edge links， D's algorithm works perfectly computes all of the correct shortest path distances。

 so just to remind you about the notation， what does it mean to correct all shortest path distances correctly？



![](img/c8b7d2217133f62c42bc006238e70dbe_3.png)

It means that what the algorithm actually computes， which is A of V。

Is exactly the correct shortest path distance， which we were denoting by capital LV in the previous video。

So both the algorithm and the perfect correctness were established by Esker Disra。

 this is back in the late 1950s， so Dyra was a Dutch computer scientist and certainly one of the forefathers of the field really as a science as an intellectual discipline。



![](img/c8b7d2217133f62c42bc006238e70dbe_5.png)

He was awarded the ACM Turing Award， so that is the Nobel Prize in Comp Science effectively。

 I believe it was 1972， and he worked for a long time in the Netherlands。

 but then also spent a lot of his later career at UT Austin。

 So the way this proof is going to go it's going to be by induction。

And basically all we're going to do is we're to say every iteration when we have to commit to shortest path distance to some new vertex。

 we do it correctly and so then the form of the induction will be well given that we made all of our previous decisions correctly。

 we computed all our earlier shortest paths in the correct way that remains true for the current iteration。

 so formally it's induction on the number of iterations of Dexters algorithm。

And as is more often than not the case improved by induction， the base case is completely trivial。

 so that just says before we start the while loop， what do we do where we commit to the shortest path distance from S to itself。

 we set it to zero， we set the shortest path to be the empty path that is of course true Of course even here we're using the fact that there are no edges with negative edge length that makes it obvious that sort of having a non-empty path can't get you negative edge length better than zero。

So the first shortest path computation we do from S to S is trivially correct， the hard part。

 of course is the inductive step justifying all of the future decisions done by the algorithm and of course mindful of that example that non-exle we had at the end of the previous video in the proof by induction we'd better make use of the hypothesis that every edge has non-neegative length。

 otherwise the theorem would be false so we better somewhere in the proof use the fact that edges cannot be negative。



![](img/c8b7d2217133f62c42bc006238e70dbe_7.png)

![](img/c8b7d2217133f62c42bc006238e70dbe_8.png)

![](img/c8b7d2217133f62c42bc006238e70dbe_9.png)

So let's move on to the inductive step。Remember in the inductive step。

 the first thing to do is state the inductive hypothesis。

 you're assuming you haven't made any mistakes up to this point。

Let's be a little bit more formal about that So that is everything we computed in the past okay what have we computed in the past。

 well for each vertex， which is in our set capital x for each vertex that we've already processed。

 we want to claim that our computed shortest path distance matches up exactly with the true correct shortest path distance So in our running notation for every already processed vertex。

 so for all vertices V in our set capital X， what we computed as our estimate of the shortest path distance for V is in fact the real shortest path distance。



![](img/c8b7d2217133f62c42bc006238e70dbe_11.png)

![](img/c8b7d2217133f62c42bc006238e70dbe_12.png)

![](img/c8b7d2217133f62c42bc006238e70dbe_13.png)

And also。The computed shortest path。Is in fact a true， shortest path from SV。So again。

 remember this is approved by induction， we are assuming this is true and we're going to certainly make use of this assumption when we establish the correctness of the new iteration。

 the current iteration， so what happens in iteration where we pick an edge which we've been calling Vstar W star。

And we add the head of this edge W star to the set X。



![](img/c8b7d2217133f62c42bc006238e70dbe_15.png)

So let's get our bearings and remember what Dyketer's algorithm computes as the shortest path and shortest path distance for this new vertex W star。

So by the definition of the algorithm， we assign as a shortest path。

 a purported shortest path from S to W star， the previously computed。

 purportedly shortest path from Esta V star， and then we tack on the end the direct Arc V star W star。



![](img/c8b7d2217133f62c42bc006238e70dbe_17.png)

So pictorially， we already had some path that started at S and ended up at V star。

 And then we tack on the end this arc。Going to W star in one hop。

And this whole sang is what we're going to assign as。B of W star。

So let's use the inductive hypothesis。The indentive hypothesis says that all previous iterations are correct。

 so that is any shortest path we computed in previous iteration is in fact， a bona fide。

 shortest path from the source S to that vertex。 Now V star， remember is in X。

 so that was previously computed。So by the inductive hypothesis， this path。

 B V star from S to V star is， in fact， a true shortest path from S to V star in the graph。

 so therefore。It has length L of V star。 Remember， L of V star is just by definition。

 the true shortest path distance in the graph from S to V star。 And now。

 given that the path that we've exhibited from S to W star is just the same one as that we inherited to V star plus this extra edge tacked on。

 it's pretty obvious what the length of the left hand side is。So it has length。

Just the length of the old path， which we just argued is the shortest path distance from S to V star plus the length of this arc that we tacked on。

 so that's going to be L of V star W star。So by the definition of the algorithm。

 what we compute for W star is just the Dys for greedy score。

 which is just the computed shortest path distance to the tail v star plus the length of the direct edge by the inductive hypothesis we've correctly computed all previous shortest path distances。

 V star is something we computed in the past by the inductive hypothesis it's correct。

 so this is equal to LV star。By the inductive hypothesis。All right。

 so don't worry if you're feeling a little lost at this point。

 We've actually really done no content in this proof yet。

 We haven't done the interesting part of the argument。

 All we've been doing is setting up our dominoes， getting them ready to be knocked down。

 So what have we done in the current iteration。Well， first of all。

 our estimate of the shortest path distance from the source to W star to the new vertex that we're including in the set capital X is the true shortest path distance to V star plus the length of the edge from v star to W star。

 That's the first thing。 Secondly， the path that we have in the B array。



![](img/c8b7d2217133f62c42bc006238e70dbe_19.png)

Is a bona fide path from S to W star with exactly this distance。

And the point is now it's clear what has to be proven for us to complete the inductive step and therefore the proof of correctness of Dysster's algorithm。

So what do we need to prove， we need to prove that this isn't just any old path that we've exhibited from S to this vertex W star that it's the shortest path of them all。

 but differently we need to show that every other SW star path in this graph has length at least this circled value。



![](img/c8b7d2217133f62c42bc006238e70dbe_21.png)

![](img/c8b7d2217133f62c42bc006238e70dbe_22.png)

So let's proceed， let's show that no matter how you get from the source for T S to this destination W star。

 the total length of the path that you travel is going to be at least this circle value。

 at least L ofV star plus LOV star W star。

![](img/c8b7d2217133f62c42bc006238e70dbe_24.png)

Now on the one hand， we don't have a lot going for us because this path P could be almost anything。

 it could be a crazy looking path， so how do we argue that it has to be long Well here's the one thing we've got going for us for any path P that starts in S and goes to W star。

Any such path must cross the frontier。 Remember it starts on the left side of the frontier。

 It starts at the source vert， which is initially and forever in the set capital X。

 And remember that we only choose edges that cross the frontier whose head is outside of X。

 and W star is exactly the head of the edge we chose in this iteration。 So this is not an X。



![](img/c8b7d2217133f62c42bc006238e70dbe_26.png)

So any path that starts in X and goes outside of X at some point crosses from one to the other。

So let's think about the graph and its' two pieces that to the left to the frontier and that to the right。

 the stuff is already processed and the stuff which has not yet been processed。

 as of course is on the left hand side。And at the beginning of this iteration of the Wild loop。

 W star was on the right hand side。Any path， no matter how wacky has to at some point。

 cross this frontier。 maybe it does it a bunch of times。 Who knows， but it's got to do it once。

 Let's focus on the first time that crosses the frontier。And let's say that。

It crosses the frontier with the vertex Y going to the vertex Z。

That is any path P has the form where there's an initial prefix where all the vertices are in X。

 and then there's some first point at which it crosses the frontier and goes to。

A vertex which is not an x， we're calling the first such vertex outside of Xz。

 and then it can skip back and forth who knows， but certainly it ends up in this vertex W star。

 which is not an x。So we're going to make use of just this minimal information about an arbitrary path P。

 and yet this will give us enough of a foothold to lower bound its length。

 and this lower bound will be strong enough we can conclude that our path that we computed is the best。

 smaller than any possible competitor。So let's just summarize where we left on the previous slide。

We established that every directed path from S to W star。P。No matter what it is。

 has to have a prescribed form where it ambs for a while inside X。

And then the portal through which it escapes X for the first time， we're calling Y。

And then the first vertex it sees outside of x is z， and there has to be1。

 and then it perhaps ambs further and eventually reaches W star。

It could well be that Z and W star are exactly the same， that's totally fine for this argument。

So here's one of our competitors， this path P， we have to show is at least as long as our path。

 so we need a lower bound on the length of this arbitrary path from S to W star。

 so let's get that lower bound by arguing about each P separately and then invoking Dyktra's greedy criterion。

So remember we said we better use the hypothesis that edge lengths are non- negativeg。

 otherwise we're toast， otherwise we know the algorithm is not correct。

 so here's where we use it this final part of the path from Z to W star。

 if it's non- emptyty then it's got to have non-ne length right every edge as part of the subpath has edge length so the total length of this part of the path is non-neg。

😡，So y to Z by construction is a direct arc， remember this is the first arc that path P uses to go from X to get outside of X so it's how it escapes the Con territory X。

 and this just has some length L of Yz。So that leaves the first part of this path。

 the prefix of the path that lies entirely in capital X。

 so how do we get a lower bound on the length of this path？Well let's begin with something trivial。

 this is some path from S to y， so certainly it's at least as long as a shortest path from S to Y。

And now we're going to use the inductive hypothesis again， so this vertex Y。

 this is something we treated in a previous iteration right this belongs to the set capital X。

 we've already processed it， we've already computed our estimate of its shortest path length and the inductive hypothesis assures us that we did it correctly。

 so whatever value we have hanging out in our array capital A that is indeed the length of a true shortest path。

So the length of a shortest SY path is L of Y by definition。

 and it's A Y by the inductive hypothesis。And now we're in business right。

 So what does this mean we can say about the total length？Of this arbitrary path P。Well。

 we've broken it into three pieces and we have a lower bound on the length for each of the three pieces。

 our lower bounds are。Our computed shortest path distance to y。

 the length of the direct edge from y to z and0。 So adding those up。

 we get that the length of path P is at least。

![](img/c8b7d2217133f62c42bc006238e70dbe_28.png)

Our computed shortest path distance to y plus the length of the arc from y to Z。

So why is this useful？ Well， we've got one remaining trick up our sleeve is a hypothesis which is presumably very important。

 which they have not yet invoked。And that is the choice of Dyxtra's greedy criterion at no point in the proof yet have we used the facts that we select which vertex to add next according to Dyextra's greedy score。

 So that is going to be the final nail on the coffin that's what's going to complete the proof。

How do we do that Well， we've taken an arbitrary path P。

 we've lower bounded its length in terms of the computed shortest path distance up to the last vertex of this prefix y plus the arc length to get from x to outside of x C Y Z。

 So remember this means y is on the left part of the frontier and Z is not。And therefore。

 in this iteration， the edge Y Z was totally a candidate for us to use to enlarge our frontier。

 Remember， we looked at all of the edges crossing from left to right。Y Z is one such edge。

 and amongst all of them， we chose the one with the smallest Dykstra greedy score。

 that was the diyktra greedy criterion。So what have we shown。

 we've shown that the length of our path。Is no more than what's a lower bound on the length of this arbitrary of the path P。

 So this completes the proof。 So let me just remind you of all of the ingredients in case you got lost along the way。

 So what we started out with is we realized R algorithm or Dtra's algorithm。

 It does compute some path from S to W star It just takes the path that computed previously to v star and it just depends this final hop at the end。

 So that gives us some path from S to W star。 Moreover。

 it was easy to figure out exactly what the length of that path is and the length of the path that we came up with is exactly this circled quantity at the bottom of the slot。

 It's the shortest path distance from S to v star plus the length of the direct arc from v star to W star。

 So that was how well we did but we had to ask the question is it possible to do better right we're trying to argue that our algorithm does the best possible that no competing path could possibly be shorter than ours So how did we do that while we considered an arbitrary competing path。

The only thing we know about it is that it starts at S and it ends up at W star and we observe that any path can be decomposed into three pieces。

 a prefix， a direct edge and a suffix then we gave a lower bound on this path P the direct edge the length is just whatever it is the suffix we just use the trivial lower bound that's at least zero and that's where we use the hypothesis that every edge has non-negative edge length and for the prefix because that's all in the stuff we already computed we can invoke the inductive hypothesis and say。

 well whatever this path is it goes from S to some vertex and y it's at least the shortest path distance from S to Y。

 which is something we computed in a previous iteration we've lower bounded the length of any other path in terms of the dister greedy score for that path since we choose the path with the best greedy score that's why we wind up with the shortest path of them all from S to W star。

 This， of course， is embedded in an outer proof by induction on the number of iterations but this is the inductive step which justifies a single iteration since we can just。

By every iteration giving correctness to the previous ones， that means by induction。

 all of them are correct， so all of the shortest paths are correct。

 and that is why Dexter's algorithm correctly computes shortest paths in any directed graph with non- negative edge lengths。

