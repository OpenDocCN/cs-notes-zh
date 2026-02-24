# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P59：3 - Spring 2023 Exam-Level 10 Problem 3.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

可南家。If one Russia。

![](img/2fc6a6aeef738076e1ad54c109b18f69_1.png)

Everyone， this is Sherry and this is the spring 2023 exam level 10 walkthrough。In this video。

 I'll be going up Pro three and introduction to MSTs。So in this problem。

 we're going to do some basic MST traversals， sorry MST algorithms。

 and then we're going to answer some true or false questions about MSTs conceptually。

So let's just jump right in。As you may remember from class。

 there's two algorithms we can use to find MSTs， Pris， and cross goals。

And I just want to say that crustscos is like a much cooler algorithm than pms。

 but we'll start off with pms。So。😊，For Pris， we visit。

 we basically use the cut property and the cut is between nodes。In and outside of our current tree。

And you'll see what I mean when I start doing this problem。

 but since we form a cut between the nodes that are currently in our tree and currently not in our tree。

 and then we just pick the lightest edge because like the cut property says that the lightest edge between any cut must be in the MST。

And then for crustcos， which is much cooler， we just sort the edges。And then， take。The lightest edge。

If there's no cycle。Because obviously we're forming an MST， which must be a tree。

 so we cannot have cycles。So let's start off with Pris and again。

 we're going to use this idea of the cut property between nodes that are currently in our tree and nodes that are not in our tree。

So。We're given that Pri starts at A because Prim actually needs a starting vertex of crsco does not。

 which is why it's so much cooler。If we start at eight。

The only node currently in our tree is a right so our potential edges between nodes in our tree and not in our tree are this one and this one。

And so since six is lighter than 12， we're going to take six and we're going to incorporate that into our MST。

And now B is also part of our MST， so let's write that down， we took AB。Okay。

 now we look at the edges again， so now we have this edge， this edge。

 this edge and this edge and this edge， all these edges are between nodes currently in ourMST and not in ourMST。

So out these edges， the lightest one is actually going to be this BC edge right here。

 so let's write that down and incorporate C into our MST。Okay。

 and then our potential edges now are CEC， C D， B， E， B F and BG。

 and again the lightest edge is BE or BG， but since we're supposed to break ties alphabetically BE comes first。

 so we're going to incorporate that into our MST。Ohoops。So actually， sorry。

 the order of nodes that we incorporated oops。So we just encoded BE。And now again。

 we're going to examine all the edges between nodes currently in our MST and nodes are outside of our MST。

 so that gives a CD Bf。F E and BG。 And here the lightest is actually this edge right here going out to F。

 So we're going to incorporate F into MST。And we're going to get this edge into MST。

And so we just incorporated EF。And again， let's examine all the possible edges。

 there's only these two， and these two must be in our MST because there's no other way to get to G orT。

 so these are going to be the last two to be incorporated， which are BG and CD。

And so our final MST is going to look like this。And we're going to stop at this point because there's no node that are not incorporated into MST。

Okay， now for crscos， which again is much。A much better algorithm than PRs， in my opinion。

Where we sort the edges and we take the lightest edge。

And just one thing we have to be careful of is we don't want to add any cycles to our graph。

So obviously the lightest edge in this graph is this one right here， EF。It has weight two。

 so we're going to add EF first。And then the next two lightest edges are actually sorry the next lightest edges BCc。

 so we're going to add that。And then the next two lightest edges are actually BE and BG。

 but since we're breaking ties alphabetically， we're going to add VE first and then BG。

And then the next lightest edge is actually this edge C right here。

 but we don't want to take it because I would form a cycles， so we're going to skip over that。

And now we want to add AP P because that has weight6。

And then we're going to look at the next latticeest edge， which is this edge here， but again。

 this will form a cycle， so we skip it。And then the next lattice is edge is CD。And at this point。

 all the nodes are in our MST so we don't add any more edges and we're done。

 and so we actually end up with the same MST， but we added the edges in a different much better order。

嗯。Okay， so now let's answer some true or false questions about these。So。

The first question ask us true or false， adding one to the smallest edge of a graphy with unique edge weights must change the total weight of the MST。

And so this is actually been going to be true， and we can do a short proof by cases to make sure that this is actually true。

So let's call the smallest edge E。And it's called original MSTT。After we add one to this edge。

 we're going to have a new MSTT star。So there's two cases either E is in t star or e is not in t star right if E is in t star we just change E。

By one， right， we increase E by one， so T star is also going to increase by one。

If E is not in T star， then we must。Pick。E prime does not equal e star。

 so that means we must pick some other edge that's not e right because an MST always has exactly a v minus one edges。

So if E is not in this graph， if E is not in the MST。

 then there must be some other edge that replaces it。😡，And since all the graphs weights are unique。

 that means e prime is not equal to E， and so that means t star does not equal T because we changed one of the edge weights in the MST。

So in either case， the total weight of this new MST T star is not equal to T， so this is true。Okay。

 the second question asks us if all the weights in the MST are unique， there's only one possible MST。

And this is true i'm not going to give a full like 10 page proof on this。

 but I just want you to remember the cut property， which states that。The lightest？Crossing edge。

Across any cut must be in the MSC。And。If all the edways are unique。That means that。The crossing。

Edge is unique。As well right so that means this whatever lightest crossing edge it's always guaranteed to be in the MST and there's no other edge that you can swap it with that could also be in the MST because the unique lightest crossing edge is always one single edge and there's nothing lighter than it so that means there's only one possible MST。

Okay， finally， true or false， the shortest path in a graph from u to V is in the。Basically。

 what this is saying is that is the shortest pass tree equal to the MST？And obviously。

 this is not true。And we can see this in the graph above here I've highlighted our MST。

 but if we look at vertex C， the shortest path to get to E。Would be through this edge right here。

 just go there directly， but if we go through the MST， we actually take a much longer path。

 so obviously the MST is not equal to the shortest battery， and so this is false。



![](img/2fc6a6aeef738076e1ad54c109b18f69_3.png)