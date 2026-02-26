# UIUC《高级数据结构｜CS 598 JGE Advanced Data Structures — Spring 2025》中英字幕 p17 -06-Apr 10： Sorting with partial information.zh_en -BV1kWFGzsEmN_p17-

![](img/3bd881a004cbeb4b4d48a1bfa70b8f87_0.png)

All right， so。On Monday， I gave a talk at。To join audience the ACM RSO Sigma group。

 special interest group on mathth and algorithms and to the Siam student chapter。On some。啊。

Cool results about sorting。And one of the things the thing that I want to present today。

Is one of the results that I thought about including。

 but just there wasn't going to be time and it wasn't aimed at the right level。

So I'm going to be talking about a sorting problem。Sorting is as old as dirt。It's， you know。

Predates what most people would consider computer science by decades in terms of building machinery and unarrguably millennia if you really want to think about it。

but the papers， the results I'm going to talk about today。Were published in 2025。

So this is very new stuff。There are。

![](img/3bd881a004cbeb4b4d48a1bfa70b8f87_2.png)

I'm going to talk about two different papers。

![](img/3bd881a004cbeb4b4d48a1bfa70b8f87_4.png)

Whi were published at two different conferences that were held in the same building at the same time。

 so there's the ACM Siam Symposium on discretereet algorithmriths。

 which is like the big International algorithms Conference。嗯。

And then there's a smaller conference called the Symposium on Simpity in algorithmris。

Which is specifically aimed at。Results that are simple and easy to explain to a broad audience。

Considerably simplify earlier results。Because the papers are simpler and it's a smaller conference。

 it tends to go on a shorter review cycle。So the soA paper could be submitted after the soda paper was already kind of submitted in public。

So I think the talks were essentially in light。I think the talks might have even been in the same session。

嗯。So the。The problem that I'm going to talk about。Is。Sorting with。嗯。Partial information。

Sometimes this is also called DAg sorting。Reasons that'll hopefully be clear soon。And the two papers。

 one at Soda， which I'm just going to refer to as paper one， this is by。

 it can never spell his name correctly， Ppller。啊。Loock。Icono。嗯。ち。Rang。Tarin。



![](img/3bd881a004cbeb4b4d48a1bfa70b8f87_6.png)

And。That's it。Bernard Huler is it at。relativelyative young professor at CMU。

 Janacono is somebody whose name has come up before。

 especially when we were talking about the dynamic optimality conjecture for Sp trees。

 Bob Tarjn invented data structures。

![](img/3bd881a004cbeb4b4d48a1bfa70b8f87_8.png)

The second one， which was at Sosa。And claims to be a simplification of the first one。Is by。Fanderho。

U。Gtten bag。And。啊。Richmond。Right， so these are both 2025。Results。

Both both papers solved the same problem， but they solve it in two different ways。

 I'm going to try to explain。You know what the basics of the problem is。

 the two different approaches are at some point it's going to get into the details of the analysis。

And I'm going to stop giving details under the hood， these are data structure results。

 which is why I felt comfortable talking about them in this class， yeah。2025。This year。

Three months ago。对。So what's the problem， okay， so you're given a set of N items。😡。

And you're also given the results of M comparisons between those items。

So somebody started sorting them， did a bunch of comparisons， and then said， I'm tired。

 you finished sorting。嗯。Sort them。m sortrt the items。And。Both of the algorithms。

Solve this problem in n plus M plus T time， or sorry， that's not t。Plus log T time。

Where T is the number of。Total orders。That are consistent。With。The given。I given comparisons。

Another way that you can think about this is your given。Dg。With。And vertices。M edges。

And now this directed acyclic graph defines a partial order。

I'm interested in that is consistent with the underlying total order of the items。

And I want to discover what that total order is。So here T is the number of total orders。

 or another way of saying that is t is the number of topological orders for the DAG。

 the number of ways of saying that is t is the number of linear extensions of this partial order。

 the bunch of equivalent language okay。U so。呃。This is。それ。Clearly optimal。And moreover。

 I should say the actual number of comparisons these algorithms perform。

Is slightly smaller and this end is just there for completeness， but it's actually redundant。

So the N plus M term has to be there because you have to read the input。喺。

The log T term has to be there。Because ultimately you're choosing from a universe of T possibilities。

And you're doing it using pairwise comparisons。You're making binary choices to choose among these T possible total orderings。

 so just like comparison based sorting with no given information requires log of n factorial comparisons here I need to do log of however many permutations might be the right answer comparisons。

Okay， so this is optimal。 I think there's a sense in which these algorithms are。

More optimal than that， but。Cause。啊。This is based on earlier work by Hoitler and Tarjn and some others on。

Algorithms that are the best possible for every input， not merely the best possible for。

Just in the worst case， in particular， they have a version of Dyketra's algorithm where if you use the right kind of priority queue。

 then the running time of their version of the Dyixtra is within a constant factor of any comparison based algorithm for that input graph。

Right， so。But is all this is the version of the result that I want to show you。嗯。And the the。

There's a bunch of reasons why。This problem is interesting。But actually。

 the very first results in the direction of this problem were from in paper by。Fredman in 1976。

The title of his paper isHow Good is the information Theoretic bound for sorting and he basically said。

 hey， if I've got， if I happen to know that，The correct permutation of my input is one of these X permutations and clearly I need log X comparisons。

 but how close to that can I get And so he actually showed you can get by with log base two of n plus2 n。

Comparisons。But he was doing this in a model where you only count comparisons in the time bound。

 so he was only looking at the depth of the comparison tree。

 not in the time that it takes to figure out what to compare and if you read the paper directly。

 this would actually come out to be you know exponential time。

If you really start to turn it into an algorithm。And the specific problem that was motivating Fredman。

Was this problem called sorting x+ Y？So sorting x plus y is one of these very basic problems like3 sum。

Where。We don't really have good lower bounds for the decision version of this， which is。

Are there any repetitions in X plus Y， then there are a bunch of other problems that we don't know how to improve either。

 But if we improve them significantly， we would also improve sorting X plus Y significantly。

 So here the idea is I'm given。Two sets。X and Y。Each。With。And numbers。

Let's say they' were given these as sorted arrays just to get the。Um， just， you know。

 I already know I'm going to be spinning in logll get， so I might as wellum sort it。

I want to sort the set little x plus little y for all little x in x and。Little Y in Y。

So on the one hand。N squared log n time is easy， I literally just use two nested four loops for all items in big X。

 for all items in big Y， write record little x plus little y in an array and then sort the array。

On the other hand。If I really want the sorted order。I have to write down n squared numbers。

And so a quadratic lower bound is trivial。And so Fredman's result actually implies that。

You only need n squared comparisons。Right， so the。There's a there's。

There is a lower bound that says if the only operations you're allowed to perform is x plus y bigger or smaller than x prime plus y prime？

Then you need to ask n squared of those questions。If you allow more general things that lower bound doesn't doesn't hold anymore。

 but Fredmin didn't know that that lower bound at the time， he just said， well。

 I can beat the n squared log n thing， but the。😡，So。It turns out。In this case。嗯。

For the sake of clarity。I need to change this to capital N。Okay， so what's the dag？

Well the dag in this case is just a directed grid。So you have a row for every item。In x。

 and you have a column for every item in y， or if you're bothered by the fact that x is the vertical coordinate and y is the horizontal coordinate。

 you can swap them。So here is your deck。So for any given item in X。I can sort x plus y1， x plus y2。

 x plus y3 in whatever the sorted order y is， and for any given value of y。

 I can sort x1 plus y x2 plus y down to xn plus y。Again， in sorted order。

 so I have a dag that looks like this。I have。啊。N squared vertices。Less than two n squared edges。

Because every node has at most two edges coming out of it。And it turns out。

That the number of total orders。Is。Not that big。You would expect something like。N squared factorial。

 if you didn't have any restrictions on these n squared things。

That would be about two to the n squared log n。😡，But it actually turns out to be only about two to the end logout。

I can， if there's time， I can come back and revisit the at least sketch the argument for why this is true。

And so。Fredman's result。Implies that。We can。Sort x plus y。In well， log of T。That's N login。

Plus two times sorry capital n， which in this case is2 n squared。So order n squared comparisons。Now。

 what I find fascinating about this is that the hard part。

 the part that I would expect to actually be hard is choosing the right comparison。

That's the log of T part， but that's only in log N。And you've got this overhead of2 n squared。

 there's another result。嗯。By K and Kim， I think sometime in the 80s。

That says you only need log T comparisons。啊。Very crudely。

There's always one comparison that divides the number of possible total orders that they're still consistent with the comparisons that you've already done by a constant factor。

I think the constant factor there was like。3，11th or something right there's a conjecture that you can always find a comparison that splits the total orders into a ratio of one third。

 two thirds that's still open。Again， this would run an exponential time。

 you still need n squared time to write down the answer。

So this doesn't give a faster algorithm in the end。

And you still need exponential time to figure out what those comparisons are， yeah。No。

 big n is the number of in this case it's the number of vertices。So sorting， sorry let me。Ah， sorry。

You're right。Um，I've got。Little n equals n squared vertices most to n squared edges。This is N the8N。

So the sorting x plus Y problem。Comes out to N log N plus to in S。Sorry， I got confused， I thought。

I tried to choose the mnemonics right， so big n would be bigger than little n， but I got it back。佢。灯。

So I mean， what the Kan Kim result is actually solving in that number of comparisons is just are all of the pairwise sums distinct？

Are they all different， so that's just outputting a yes or no。And so that can be done in only。

En log N comparisons。Actually。So what the newspapers？Both imply。Is that I can sort x plus y in。

N squared time。This is not this beats for the first time in 50 years。The obvious n squared log n。

Or sorry， I guess that should be capital N again。The sort of obvious end log n algorithm。

So there's an obvious algorithm， and that's been the best algorithm for 50 years。

 and now it's no longer the best algorithm。This also means， for example， that。嗯。

There's an algorithm similar to the sorting x plus y， there's a similar problem for sum。

 here's a set， do any four items add up to zero， the easy algorithm。

 which is all anybody knew was split， you know find all these pair Y sums and then see whether any pair Y sum plus any other pair y sum equals zero。

so that that would take n squared log n。 now it only takes n squared and in general，2 K sum now。

You can get it to run in order end to the K time instead of order to end to the K logette。And again。

 four some， six sum， eight some， these are all problems that have been used as the basis of conditional lower bounds。

And all have not seen any improvement from the more or less obvious algorithm in 50 years。

So that's why I wanted to present this result。Okay。So。Per number one。嗯。We're not hopefulr at all。

Uses an algorithm that they refer to as。Topological。Heap sort。So if you remember。

 topological sort is the problem given a DAG， compute any linear extension of that DG。😡。

Any total order consistent with that deck here， I'm trying to compute a particular。Linear extension。

Consistent with that daAg so the input to this problem is just the DG G so the problem goes as follows so Q is going to be initialized as an emptyQ。

U。And then now。

![](img/3bd881a004cbeb4b4d48a1bfa70b8f87_10.png)

H。Is。A heap of sources。

![](img/3bd881a004cbeb4b4d48a1bfa70b8f87_12.png)

Source vertices。

![](img/3bd881a004cbeb4b4d48a1bfa70b8f87_14.png)

In G， so remember， a source vertex is a vertex that has in degree zero。It only has outgoing edges。



![](img/3bd881a004cbeb4b4d48a1bfa70b8f87_16.png)

Apologise for the。Crappy technology here。All right， now I'm going to do something relatively obvious。

As long as the graph is not empty。The I'm going to pull。A the。Source vertex。😡，That has minimum value。

Out of my heap。Now every item has a value and in particular I can directly compare two items just by comparing their value that's part of the underlying assumption。

 so when I'm building the heap and when I'm doing the delete min。

 I'm doing pairwise comparisons and those pairwise comparisons are actually what I am counting。Then。

4。All edges V to W。S to me。Be more explicit hear。For all edges。V to W in G。If。In degree of W equals1。

 that means when I delete V， W is going to become a source， and so I need to add I need to insert。😡。

W into my heap。Then I。Push。V onto the back of the Q， and then I delete V from G。喂。

So I'm doing comparisons。Here， here， and here。Hope it's clear that this works。

So a standard heap sort is this algorithm。Where your input dag has no edges。

Every vertex is a source because there's no outgoing edges and throw absolutely everything into a heap。

 and then you do extract it over and over again。Okay if if the on the other hand。

 the DAG is just a list， it's already a total order。

All this does is it runs through the sequence of items in total order and pushes it into queue。Yeah。

I。Their numbers。You just compare them。哦。It's just that you've been given the results of some comparisons already。

 So， I mean， think of them as numbers， but the only access you have to them is by comparison。

 but that's given to you as an atomic operation。你肯定要好。

They are items that have a total order that you don't know for any two items。

 you can compare them in Constantine。That's the game that we're playing。

It's just like comparison based sorting。对。Okay， so。All the comparisons happen in here。

 so the running time of the algorithm。😡，嗯。Ultimately is going to depend。On what we use as the heat。

So if I use a standard binary heap， then every delete min takes log n time， every insert。

 takes log n time， every node， every node in the graph is inserted and deleted exactly once。

 so the whole algorithm runs in n log n time。But we already seen。

By the you know through the example of display trees that you have interesting games that you can play with amortized analysis that can beat the naive login time bound for binary search mean we're going to the ultimately the efficiency of this is going to depend on。

The similar kind of thing by choosing the heat data structure correctly。系。嗯。The second。Paper by。

Fanderhook and other Scandinavian people is。Best described as。Tological insertion sort。And again。

 the input to the algorithm is this initial graph。The initial Dg， G。And fundamentally。

 what the algorithm does is it maintains a list。Of items that is already sorted。

And then it considers sources in the DAG one at a time， again in topological order。

 and inserts them into that list。But I need to describe this a little bit carefully for the details to work out。

 so I'm going to let pie be the longest path。In the bag。

This is a standard exercise in depth research to compute in linear time， yeah you have a question。

And then I'm going to let this subgraph H beg minus。All the vertices imp pi in their out edges okay。

And then。While。This remaining subgraph of G is not empty。

I'm going to do the following I'm going to let Xi be any source。In H。

And you'll let PI be the largest。Um。Predecessor in G。Of x sub I。

And I'll assume that there is a sentinel entry which is smaller than in everything that's at the beginning of pies。

 so piece of I is at this point one node that's already been inserted because I'm considering things in topological order。

 I consider predecessors before successors。So this is finding the thing furthest in the list that is still before where XI wants to be。

Then I insert。X I。Into pie after。Pieace a by， and I'll say a little bit more about that in a second。

And then finally， delete xab I from H and then ultimately。I returned pi here ultimately。

I'll return to you。嗯。So。Here。Find the longest path。

 this is relatively easy doesn't require any interesting structure or any interesting data structures。

Sorry about that where the comparisons actually get done is， first of all。

 here and second of all there。I guess， yeah， the longest path， I'm only using existing comparisons。

 so I don't need to do anymore。So in the step where I'm choosing P of I I'm literally just looking at all of the incoming edges coming into node X sub I in the original graph G and for each one I figure out which one is the largest that's just degree in degree minus one comparisons I can charge those comparisons to the edges of the DG and so I'm spending constant time on every edge that's not the interesting part the more interesting part is here when I'm inserting the new key into the sortded list。

😡，Now an easy way to do this is by maintaining that list， that path pie in a binary search tree。😡。

So when I want to do the insertion， I'm literally just doing an insertion into a binary search tree that takes me log in time。

And well， that gives me un log n in the end。On the other hand。

 if I assume that the input graph is just a path。😡，Then I'm done at step one。Find the longest path。

 that's the whole thing。Right and there's nothing else to do。

 so a more interesting special case to think about is what if the DAG just consists of two pads？

OkaySo initially pi is going to be the longer of those two。

 and so the sorting problem here is literally's merging two sorted lists。

 so you would expect it to take linear time。嗯。When I'm doing this insertion。

Because I'm considering if this is my initial pi and this is my initial H。

 I'm considering H in topological order， so I'm considering an increasing order and the predecessor。

 well， it's always just going to be the there's only one predecessor it's going to be the earlier thing in H。

And the insertion is going to just be ahead in the path。

 so I can literally just keep a pointer and just walk forward。

So if these are both paths of length about it and over two。

 that insertion only takes constant amortized time， the whole merge procedure takes linear time。Okay。

 so I don' didn't need to do the binary search because the partial order gives me some additional structure。

So。Ultimately， then。The running time。Depends。On。This insertion structure。Which is called a。

Finger search。Tree。Okay， so the idea is。I need a structure that says， hey。

 find me the predecessor of X sub I。But I'm going to give you a hint。It's after peace it。

So I have a pointer directly into my data structure to one node， and now I want to find another key。

😡，And the idea is if these things are close together in the final ranking。Then the two nodes。

 the one that you started at and the one that you're searching for should be closer together and so the running time for doing that so-called finger search search starting with the finger should be smaller than if I'm starting with no information at all。

😡，And that's ultimately where the efficiency of this algorithm。Comes from。Is doing this kind of well。

If things are close。If I can get a pretty good guess for where something is going。

 insertion should be cheaper than if I'm starting from scratch。嗯。So these are the two algorithms。

I haven't give you enough information to get the time balance。

But at least I want to make sure that the algorithms themselves are reasonably intuitive and clear。

Now， reading these papers to me。嗯。The way this is obed， I actually find the paper one。

To be simpler than the paper too that claims to be simpler and was accepted to the Slic and algorithmrith Conference。

Um。It's very clear reading these two papers that both sets of authors knew about the others's results。

 so the versions that you can find on the archive now。

 each cite each other and each actually refer to technical les in the other paper。

 and then they give self-contained proofs。And in one case， paper1 says， yeah。

 but we solved this other problem like pulling the top K things out of a da faster and we don't know how to use the other structure to do that and then the other paper says oh。

 they said something about top K das here here's half a page， we can do it too。Meanwhile。

 the first paper says， hey， we're going to use alemma from the second paper that takes them two pages to prove。

 here's the six line proof。And this is the simpler paper。So there's a lot of back and forth here。使的。

So。No。The problem is papers exist in multiple versions。

 so the most extreme version of this I know was there's a problem called simplex rain searching。

 I've got a cloud of points。Let's say in the plane。

 and I want to pre processces it that later I can throw up a triangle and it' tell me how many points are in that triangle。

睇。But think of it in higher dimensions。So there are these two papers。

One by Bernard Czeelle and one by Yokobatuk。The journal version of Mattusuchk's paper cites the journal version of Shielle's paper。

 which cites the conference version of Mattusch's paper。

 which cites the conference version of Chizelle's paper。

 which cites the technical report version of Mattusuchch's paper。

 which cites the technical report version of Shizelle's paper and the papers do this in a way that if you actually want to understand the results all the way down to the bare metal。

 you actually have to read all six papers。So yeah， it's sort of a dag。But if you just。

 you know it looks like the two papers just cite each other and then it's not a dag。

You kind of have to untangle it here， these two papers did a much better job of， yes。

 they're each citing each other， really they're citing earlier versions。

But they also include self contained arguments for the things that they pull from the other paper。

So each paper can be read as a standalone thing， which is much， much nicer than that other one。Okay。

 so。This also suggests there may be other。Methods that combine topological sort with other kinds of sorting algorithms。

Fine project。嗯。All right。So。Any questions about the algorithms？

So I want to say a little bit more about exactly what you need for the underlying data structures to be efficient。

I'm only going to。Point in the direction of the actual data structures。

I don't have time today to talk about the specific implementation or why they satisfy the correct time balances。

 but I do want to give you at least the high level intuition。Okay， so。UHeaps。So。In this case。

Lets you know， maintain。A set of items。And subject to two。嗯。

Two operations insert and extract in Now a lot of he。没。Most heat data turn。

Also allow you to delete arbitrary things or do a decreased key or meld。

 there's a bunch of more complicated operations you could perform with priority cues in this case。

 these are the only two that I need。Now the efficiency of the heap。

Is going to depend the way I'm going to formulate this iss going to depend on something called the working set of an item in the heap。

啊。For any。Item X。V。Working set of X。Is all items。That were inserted。After x was inserted。

But before X was deleted。可以。😊，And the idea here is。What you would like？

Is if you pull something out of the heap。After it's only been in the heat for a short time。

Then it should be faster to pull it out than if you're pulling something out of the heap that's been in the heap for a long time。

哎。So the particular。Running times that they need for this algorithm， these are both amortized。

So amort you can insert in amortized constant time again this is kind of what you would expect if I'm going to insert something and immediately delete it。

 it's great if it's just right there at the door， so I shouldn't do very much and I should kind of rely on later insertions to push things deeper into the data structure。

😡，And then the。Acmin that running time depends on how many other things have been inserted since I was inserted。

 that's my working set， so W of x is the size of this working set。Um。

So it's not it's not in any way obvious that a priority queue with these efficiency parameters actually exists。

 but if you have ever heard of，Fbonacci heaps。Fbonacci heaps have the property that the insertion time is constant amortized。

 it's actually constant worst case， and the extractman runs in log n amortized。嗯。

So at least getting the， if you've seen other efficient priority cues。

 the fact that you get constant time insertion is maybe not so weird。

 constant log working size extractments is a bit more difficult。So they're relying on a result。

By Johncono。That。啊。A data structure called a pairing heap， which is not John's invention。

 it was actually Ts。嗯。Its a very easy to implement priority queue whose complexity we don't understand。

But there is an analysis in terms of like worst case performance， we just have no idea。

 but if you want to phrase things in terms of the working set bound and you don't care about things like decrease key。

 and you insist that at the end of time your priority key is empty。

 then pairing heap actually does the job。If you look in the paper itself in the archive version。

They describe another data structure called a double pairing heap。

So they give a self-contained description of the data structure and they give a self-contained analysis of the data structure with these time balance that's simpler than the pairing heap analysis。

 but when they started they said well， we know John said， hey。

 I can do that with pairing heaps and they said great， we'll just plug that in。But。

That makes the paper somewhat less self contained。Okay。I'm still debating。

About what to talk about for the last two weeks of lectures。

One of the things that I'm considering talking about is efficient heaps。

 so I may talk about pairing heaps next week or the week after。系。Okay。So。That gives you。

Some idea of like， oh， okay。I need to do something non trivialvial with my heap。

And this is the nontrivial thing you need to do， but I still haven't connected it to the overall analysis and again I'm going to jump back to paper two because ultimately the analysis is going to use exactly the same tools。

Okay。嗯。Oh okay， so just let me summarize。So there's a alemma。In the paper that says， okay。

 topological heap sort runs in time。Bgo of n plus m plus the sum overall items x of log of the working set size of x。

And this turns out to be。At most， plug T。I guess to be clear， I should say。

That turns out to be big of log C。So that's where the log T comes from， still need to prove it。O。

About the other one。You need a a。Finger search， tree。Here。The idea is。I'm going to insert。Right so。

I'm given an item to insert and I'm given a pointer directly to another item。Given a pointer to X。

Insert why， and it turns out to be equivalent to just say find the predecessor of why。

In this tree that I'm searching。Can。嗯。So one fairly intuitive way that you could imagine doing this。

Um is， okay， I've got， you know， some sort of binary search tree here。And if I want to here is x。

 and then after insertion， there is Y。intuitively you could imagine starting at X and going well I want to find I want to find where y is going to go into this tree。

 what I'd really like to do is kind of walk my way up to the least common ancestor of X and Y and then do a normal binary search to find the predecessor and that's the place where I want to insert the new symbol Y。

😡，And。This idea。Does work out so it is possible。We can insert。In time。Order。Let's say the distance。

From x to LC of x and Y。Plus， the distance from y to LCca of x and Y。嗯。

The problem is that and what we'd really like is for this distance to always be the like something like the log of the difference in ranks。

So if the tree is balanced， it's going to be at most log n。

But if the keys are close together in rank space， we'd like it to be less than log end。

 We don't have to go all the way up to the root and back down。

And it doesn't seem possible to do that because X might be in the left subte down at the leaves and y might be in the right subte down at the leaves。

 and so the LCA you have to go all the way up to the top。So you can speed。

 there's a couple of things you can do。So one。Is if you use a data structure called the tree。

The distance from x to the LC of x and Y。Is a。Loarithmic。 sorryrry。It's logarithmic in the the。

The difference in ranks from x to y， let me just write it as y minus x here。These are ranks。

 not actual keys。And this is an expected value。So if I use a treat。

Then the expected length of this path from x to y is only log of the difference in the rank of x in the rank of y。

 and so summing up over all such operations that means you get the expected bound that you want。

Which is the log of the difference in ranks。On average。And that means in the end。

 you're going to get those are the terms that they're going to add up to log T in the overall time analysis。

 you're going to get log T on average。Okay， if you want a deterministic time bound， though。

 another way you can do this。Is to add。Level pointers。So I might be able to short circuit。



![](img/3bd881a004cbeb4b4d48a1bfa70b8f87_18.png)

If I add pointers。That thread through the tree at each level。



![](img/3bd881a004cbeb4b4d48a1bfa70b8f87_20.png)

And then with slightly more complicated logic， starting at X。

 I don't need to jump all the way up to the LCA， I could just notice the right neighbor of X on that same level is too far。

 and so I know it's going to be like to the left of that neighbor。so in this case， again， I can get。

Order log， let me just。

![](img/3bd881a004cbeb4b4d48a1bfa70b8f87_22.png)

Sorry， the notation demons are beating me up。

![](img/3bd881a004cbeb4b4d48a1bfa70b8f87_24.png)

Now。That's great if what you have is a static tree， but we're building the tree as we go。

Inserting things into the tree we're only inserting we don't need to delete。

And the methods that we've seen for balancing trees when I insert。All involve rotations。

So AVL trees you need to rotate， troops， you need to rotate。

 display trees you need to rotate and maintaining these level pointers when you're using rotations to keep the tree balanced。

Doesn't work out I mean it's just really painful。 so instead you use some variant of beries and so the paper。

嗯。Actually recommends a specific data structure called the 24 tree。

 the thing that bee trees do that balancing binary search trees don't。

Instead of using rotation to keep things balanced， they allowed the node to have somewhere between in this case。

 two and four children， so a single node will have between one and three pivot values。

The way that you build the tree， all leaves are always at the same level。

And so as you insert things into the tree， nodes get bigger。

 so the branching factor gets bigger and the tree gets wider。

Until eventually things get sort of full and you split a node that has four children into two nodes that each have two children and add a new root node above it。

 so you're balancing by widening the nodes and occasionally splitting them。

But this strategy has the property that things that are on the same level。Stay on the same level。

And so maintaining these level pointers。

![](img/3bd881a004cbeb4b4d48a1bfa70b8f87_26.png)

嗯。

![](img/3bd881a004cbeb4b4d48a1bfa70b8f87_28.png)

Deterministically is much more straightforward than trying to do this with the balance。

Bunary research tree based on rotations。系。So the overall running time。Of。ATological insertion sort。

Is on the order of n plus M plus the sum over all nodes I of log of d sub I where D sub I is。

The rank distance。From。The predecessor to the node that I'm inserting。

And this ultimately is going to be。You go of log tea。系。So in both of these cases。

 I'm taking something a sub sub sub sub problem， which using standard data structures would implement in log end time。

And just by being very careful， very precise about how I implement the data structure。

 I can improve that log n to something that essentially depends on how the new item fits into the existing sorted list。

That I'm built it。Right。Or either how it fits into the list or how it pulls out of the heat。嗯。So。

Ultimately， now。All of the analysis。Boils down。To something that they call the intervallemma。

RightBefore I go on first are there questions about。What finger search means？What working sets mean？

Okay， cool。Okay， the interval Emma is this is。Really the technical heart of the paper。

So I want to state thelemma， I want to prove thelemma because it's not going to be that hard。

 then and I'll just briefly point out why thelemma is applicable here。😡，Okay。

 so I'm going to start by just， let's just say I have a bunch。Of intervals。Actually。

 I think it makes sense for them to be open intervalurals。To B2。Up through AN， BN。Be intervals。嗯。嗯。

Integer endpoints。In the range from one to N。Okay。You can think about these in the topological insertion sort。

 these intervals are going to be the rank of each item XI and the rank of the corresponding predecessor PI。

 those will be the rank of PI will be A and the rank of XI will be B in the topological heap sort。😡。

TheThese intervals are going to represent when an item was inserted into the heap and when an item was deleted from the heap。

 so the length of the interval is going to be the size of the working。Now。I'll define。A dag。

Over these intervals or over the indices， one through n of these intervals。

Where an edge from I to J means。That sorry。BI is less than or equal to AJ。

I have one interval that's completely to the left of the other。

It's intervals that are overlap at all are just not comparable in this stag。

 there are no edges that represent them and obviously if the intervals in the other order。

 then the edge points in the other direction。😡，听。😊，And now， let T of I be the number of。

Topological orders。Of this。Of this duck。可以。Let me call this Dg eye for intervals。

So this is the number of topological orders for I。诶。So thelemma says that if I sum over I。

The natural log of the length of these things。This is the number of integers in each of those intervals。

😡，This is at most the natural log of TVI。Plus， little M。诶。嗯。

One technical step is to show that this interval partial order is actually a。Refinment。

Of the partial order that you're given at the beginning of the algorithm and so P of I is actually less than or equal to T。

 the total number of total orders that's consistent with the original Dg。

 so I'm proving a tighter upper bound than I actually need。Okayy。So here's the proof。

I'm going to choose and imagine a random experiment。Hey， I'm going to choose random samples。

 R1 through Rn uniformly and independently at random， sorry， let's say。I just say uniformly。

Independently。From the real interval。Z to n。Okay。😊，嗯。😡，No。If。RI happens to land in the interval AI。

 B。For all I。Then the sorted。The sorting permutation。Of the Rs。Is a total order？

Let's say is a linear extension of I。Of this。Or is a topological order？4 I。1。ok。

So if I just happen to randomly pick。😡，Points where the first random sample lands in the first interval and second random sample lands in the second interval and so on。

 then whatever permutation I apply to those random samples to put them in sorted order。

Is a permutation that's consistent with the interval partial order。Hey， if。

IfIf interval J is to the right of interval I， then this only works if RJ is bigger than RI。系。

So let's。What's。But's use this to count right， so what is the probability that this event happens？😡。

Well。The samples are drawn uniformly， so it is just the product。

Of the probability that AI is less than RI is less than BI。嗯。Sorry， I should say。

mIt's actually if this is。Between AI minus1 and B， there's a little bit of sp because the original intervals have to have integer inputs。

 so there's separated by at least one if they're different。嗯。So。A i minus1。But this is literally。

The length of this interval。Divided by n。I've got a bunch of intervals。

 the probability that the I random sample lands in the I interval is the length of the I interval divided by the total length of the sample space。

诶。嗯。So okay。So how many？Possible orders are there now notice every single possible permutation of the Rs is equally likely because i'm generating the Rs independently at random so this means that the total number of topological orders for I is。

😡，N factorial times this probability， so what you're looking at here is what is the probability that my random sample falls into a permutation that I like？

😡，Well， actually， it's it's。It's potentially more than this。Because。

It's possible that the random samples are in a good order， even if they don't land in the intervals。

So the probability that I have a good order is greater than this probability。😡。

So the number of good orders is greater than that product。Times the number of。For mutationutations。

That can write this as n factorial over end to the N。Times the product of B minus AI plus1。

And now I'm basically done， so if I take the natural log of T of I。

 that's going to be greater than equal to well。This， I think we saw this earlier。

 this is greater than equal to e to the n。So this is going to be log of e to the n。Plus。

The sum of the logs of B minus AI plus one。Overall， I， which is exactly what we needed to prove。

This is the dilemma that the simple paper took two pages to prove is a much more complicated argument。

So the not simple paper did the proof simpler。好公。Oh right， right， right， right， right， you're right。

 sorry， yes。This should be minus n plus。Yeah， I need to do some rearranging。

Just pull add endable sites。Yeah。Okay。Um。So like I said。For topological heap sort。A sub I is the。

This is just equal to I。 This is the time。Where。The ice。呃。Item。Is inserted。And B sub I is the time。

Where。The ice item。Was extracted。And then there's a technical lima that says that。

This partial order you get from the intervals is a refinement of the partial order that you were given at the beginning。

And so。呃。You get the inequality on the number of total orders in the direction you need。

For topological insertion sort， it's slightly more complicated because you've got this initial。

 I't pull out the longest path at the beginning， so there are really two different kinds of items。

 things that are in the initial longest path and stuff that that I need to do finger insertions for later。

U so。So let。R of X I be the final rank。Of X I in the output path pi。A sub I is either。Our X I minus1。

Or are of peace a by， depending on whether。Our subI was in that and let's say this is the final path。

This is the initial path。And B sub I is the final rank of I and again。

There's alemma that requires a little bit of。Case analysis that the intervals。Define this way。

 define a partial order that's a refinement of the partial order that you were given and so the number of total orders consistent with the intervals is less than or equal to the number of total orders consistent with the DAG so again。

 the analysis works out in the end。These。These two proofs that the refinements are there are。啊。

Not particularly long， not particularly complicated， it's just mostly definition chasing。

The proofs are readable in the papers， they're simple。And so that is where I want to stop。

 so if you get anything out of this。The thing that I think is the most important to get out of this is just the existence of this。

 you know， n squared algorithm for sorting x plus y。

 but where it comes from is this weird combination of，Topological sorting and standard sorting。

Both of which are like considering elements one at a time。

either by construction in exactly sorted order or in kind of in an order that's consistent with the topological order and then figure out how it fits in the final output。

And then by plugging the right data structures into critical pieces in this algorithm。

 you actually get the result you want。Happy to answer any questions， but that's all I have for today。

Oh and。If you are interested in hearing about efficient priority cues。

 the other thing that I was considering talking about was fast data structures for integer searching。

So how to sort and integers and log log in time？Vanom deboas trees you might have heard of。

 fusion trees you might have heard of。嗯。I'm not entirely sure that there's enough time left to cover both。

Maybe if I only spend two lectures on each。But I'm happy to listen to， if you have preferences。

 please let me know。All right， thanks。

![](img/3bd881a004cbeb4b4d48a1bfa70b8f87_30.png)