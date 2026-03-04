# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P25：25_06_03_路径长度.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/d5c768bdcd1c12f80f4c5827196debf4_0.png)

next we're going to talk about the analysis of path length in binary trees。

And this is an important problem to study because that's the quantity that we use to predict performance in the analysis of the binary search algorithm that I talked about before。

So。Here's the definition that I gave before for a binary tree。In the level and the depth。

 when we talk about path length， what we want to compute is the average length of a path to a node that's in the tree。

 say an internal node。So to do that， we compute the total internal path length and then dividing that by n gives you that average cost。

And so to compute the total you just count the number of nodes at each level， so at level1。

 there's two nodes at level2， there's four， level 3， there's three， four， there's one。

 the five there's one， and you add that all up， that's called the internal path length of a binary tree。

It's the sum over all nodes of length of the path from the root to that node or the sum of k times the number at depth K。

For binary trees， we also talk about external path length。

And that's just the same thing for external notess。

So and also that's a quantity of interest in studying the binary search algorithm。So these things。

 there's relationships among these that are easy to prove， it's all recursive。

 so and there's a lot of notation to be able to talk about these things。

 so let's look at some simple relationships among them。So we're talking about binary trees。

 and we have the size function and just a different size function for external nodes。

And then if left and right subtes will indicate with TL and TR IPL stands for the internal path length。

 XPL stands for the external path length， so that's all the notation and again these are simple quantities to define as I did on the previous slide。

So here's some recursive relationships， so one thing is the number of internal nodes in a tree is the number of internal nodes on the left。

 plus the number of internal nodes on the right plus one for the root。So that's fine。External nodes。

 it's just the root is not an external node， so the number of external nodes in the tree is the number of external nodes on the left。

 plus the number of external nodes on the right。Internal path length。 So this is an interesting one。

 If you want the internal path length of the whole tree。

You take the internal path length on the left and the internal path length on the right and add those together。

 and then what you are is you're off by one on every single node except the root。

 so if you add t minus1， then you're adding this link to all the nodes。

And so that's a recursive relationship for the external pathway。

And for internal path length and for external path length， it's similar。

External path length on the left， external path length on the right。

 but you're off by one for every node because you didn't take into account the nodes that connect the external node。

 the subtes to the root。So those are simple but very useful recursive relationships。

So and then from those relationships you can prove easy things like the number of external nodes is equal to the number of internal nodes plus one。

 and that's just by induction。So just plug in。From。This formula here。

 the number of external nodes is the sum of the external nodes in the two parts。

By the inductive hypothesis， that's equal to Tl plus1 plus TR plus1。

 and then using the recursive relationship for internal nodes， we're left with internal nodes plus 1。

There's lots of ways to prove that。Here's another one。

 external path length is equal to internal path length plus two times the number of internal nodes in the tree。

 and again that's inductive right from the simple recursive relationships that we talked about。

So and again， there's a lot of ways to prove those things too。

 just using these as an exercise for getting used to the idea of pathling in its relationship of the path length and the subtes to the path length in the whole tree that is critical to the analysis that we're going to do。

Okay so here's our first problem we have a random binary tree so that's a binary tree where all tree shapes are equally likely with probability one over catalan numbers when a random plus12 and choose in what's the average path length of a random binary tree that's some kind of description of the tree shapes that we saw how far are all the nodes from the root and how far is an average node from the root is sort of what we're saying with that。

So these are the quantities that we're going to work with。

 so QNK is the number of trees with n nodes and internal path length K。

T is the number of trees that's the cattle in numbers。

 and the accumulated cost is the total internal path length on all trees so that we get the average by dividing the accumulated cost by the number of trees。

 that's the way that we compute average values of parameters。So this is for two， so in this case。

 both of the trees with two nodes have internal path length to one。

So the average so the total accumulated interpath length there's one average internal pathway。

 one still not so interesting， now this is a little more interesting。

 so there's five trees with three nodes。Four of them have internal path length three。

 zero to the root， one to the one below and two more to the next one， so it's three。

 four of them have that structure， one of them has internal path length two。

 the nodes are both just one from the root。So Q32 equals1。

 there's one tree of size 2 that has internal path length to 1。

 and there's four trees of size3 that have internal path length 3。

And so in that's a bug as t3 equals 5。So the average internal path length is 14 over5 is 2。8。

So that's the figures for three， and here's the corresponding figures for four。

Total path length in all of these trees is 74， and there's 14 of them。

 so the average expected internal path length is 5。2 in these trees of size 4。

And then you can take that and say the average distance to an internal load divide that by four again to get about how far a node is from their route。

So that's the quantities that we're after now it's always good to do small cases like this to make sure that you have a good fix on the exact quantities that you're analyzing。

Expected path length of a random binary tree。So here's the analytic combinatoric derivation of this。

 and these are all things we've defined so far。So the county Gf is just the Catalans。

 and so that's all the information we know about the Catalan numbers。

The cumulative cost generating function is some over all trees。

 internal path length times Z to the tree size。And that's also equal to the sum sum k number have palling ks and so forth。

 but from now on we're just going to go with cumulative counting and we know that the average is going to be the coefficient of Z to the n in the Q divided by the coefficient of Z to the n in the T。

The coefficient is Z to the n in the Q is the total internal path length of all trees of size N。

 if you divide that by the number of trees of size n， then you get the average internal path length。

So that's the cumulative counting method that we're going to use to analyze this quantity。

 and so now what we have to do is analyze that cumulative cost generating function。

 and that's what we'll do next。So we have the count GF and we have the cumulative GF。

 and we're going to use this recursive relationship slightly different。

 but pretty similar to the one that we just talked about。

The internal path length of a tree is equal to the internal path length of its two subtrees。

 plus the number of nodes in the two subtrees。And so from that definition。

 we can immediately write down this decomposition。This first one is for the empty tree and this other one is for the root。

 but if we have that function， we look at this decomposition。

 IPL of T is exactly equal to that and the size of T is exactly equal to that so we have that double sum for the。

 cumulative cost。In that decomposition or looking other way that construction。

 now we can rearrange terms， and you can see， for example， that IPL Tl Z to TL times Z VR。

 that's Q of Z E T of Z， So that's one of the terms that we find in there。

And the other ones where these TLs come into effect， we get T prime of Z， T of Z。

This formula has those four terms in using these two equations。

 it immediately reduces to that simple equation relating the counting generating function and the cumulative generating function。

 recursive equation that relates those two generating functions， extremely simple argument。

 it's actually possible to develop this symbolically and we'll talk about derivations like that in part two。

 but it's worthwhile having the explicit decomposition in front of us to see how directly we get to the equation that matters。

 which is the generating the equation relating the generating functions that we can then solve and analyze。

Okay， so just to get it all on one slide， I'll put those steps down here。

 So now we know that Q of z equals 2 of z T of z times Q of z plus Z T prime。

We know what T and T primer， the only thing we don't know is Q， so we can solve that for Q。

And then we can just T of Z。 remember， that's the cattle in。 and we know what T sub n is。

And T prime is just the derivative of that， which has two terms in it。

But there is one thing that simplifies calculations a lot1 minus2 z T of z if you multiply this by 2z it's just squared to 1 minus4z。

 so that takes care of the denominator， so there is still a little bit of algebra multiplying these two things together。

 but there's lots of cancellations because squared to 1 minus4 z times squared to1 minus4 z is just 1 minus4z。

 so I'm going to not going to pretend I'm going to admit some of the algebra。

 but the final result is pretty simple， so that's an explicit equation for the cumulative counting generating function。

And what do we need， the coefficient is z to the n and that is the internal path length of all the trees of size N。

And just looking at that， you can see that it's going to be4 to the end。

 next term is lower in magnitude。So take all those binary trees is Catalan number and add up all their internal path lengths and you get four to the n。

 surprisingly simple， it's not exactly four to the n， but asymptically it's  four to the n。

 and that's why we want to do precise asymptototics before。

 because if you take that and divide it by the catalan， all you're left with is n squared to pi n。

We divided two huge quantities， but since we were working with precise asymptotic results。

 we get a precise answer。The average internal path length of a random binary tree n root is asymptotic to n square root of pi N。

 and that's a very accurate estimate。For the average internal pathwayling and we could do it。

 we could get it exactly， but doing it asymptically is very compelling because it's a simple and surprising and unexpected result。

So now let's look at the same thing for random binary search trees。

 so that one kind of explains or starts to explain the shape of a catalan tree。

 the nodes go down square root of n， which in a 10，000 node tree， goes down100。

s pretty good size depth in that's average， so it goes down a few hundred。

What about binary search trees？Well， here's the same calculation for binary search trees。

But now we're counting permutations that result in a binary search tree with n nodes and internal path length decay。

And now it's a little easy because the counting factor is in factorial。 we know that。

 but still the accumulated cost is the same way。 It's just that we have to count the number of permutations。

 so in this case some of the trees have internal path length 4，5 and 6 as before。

 but the weighting is different。 So all of these 12 permutations give four。

There's only four of them that give five that's these four， and the remaining eight give six。

So the total internal path length of the trees that you get from all of the 24 permutations is 74 if you divide that by 24 you get 4。

833 which is less than what you get for cattle entries trees because the balanced ones are weighted are much more likely。

That's the same setup， and now we can use analytic combinatorics in the same way to analyze the path length of binary search trees and get a comparison between showing us the difference between these two models。

So start as usual， but now we have permutations。And so our cost is the length of the permutation。

 but now when we say IPL， we mean we want it's an IPL of a permutation。

 which doesn't make sense except if you say that the permutation is what we want is the internal path length to the BST you get from that permutation by inserting it into an initially empty tree。

And again， the number of permutations as size N is n factorial。

 and that saves us a step in the calculation， as you'll see。

An accumulated cost is the total IPL of binary search trees built from all permutations。

So now our counting EGF is a simple one， that's the basic EGF for permutations。

 it's just one over1 minus E， we have an n factorial involved。

 that's our number of permutations so that cancels out。Our cumulative cost EGF。

 it's the same symbols as before， except now we have permutations， it's not trees。

 and IPL has that different meaning。And so to get the expected internal path length of a binary search tree built from a random permutation。

 we're going to take n factorial coefficients， Z to theN and that divided by n factorial and those n factorials cancel out so it's just almost it's treating it as an ordinary generating function gives us the divide by n factorial for free。

 it's just a little calculation trick because those because we're using exponential generating functions which means that we divide by n factorial but our probability space is permutation so we want to divide by n factorial so it serves both purposes and saves us the step of dividing we just look for the coefficient of Z to theN and c of Z。

So next， we have to look at developing a generating function equation for that C of Z using the recursive definition of the binary tree structure according to the way that we construct trees。

So same basic steps as before， it's just that we're going to come up with a different equation because we have a different structure。

So again， this is just a summary， what we're after is better an equation that C of Z has to satisfy。

And then what we're going to do is use this relationship that we talked about before that gives us all the permutations that lead to the same tree。

And so that decomposition from a permutation P to a permutation that IPLFP is those are all the permutations that give rise to that。

And then IPLFP has got that recursive relationship as before。

 we can express everything there in terms of P of Bell and P of R。

Because of this decomposition that we already talked about。

And this one's even simpler than the other one， there's just one trick that often works with exponential generating functions。

This P plus PR plus1 factorial causes in the denominator。

It causes a little inconvenience in simplifying this formula， but we have Z to that same quantity。

 so what we do is differentiate to cancel out that one factor。

 then you'll see there's a PL plus PRR factorial on the bottom and then we can mix that with the binomial coefficient。

So this is a trick that often works with exponential generating functions， differentiate。

 then cancel the PL plus PR in the binomial coefficient and you left with the P factorial PR factorial and now you've got a very simple。

 double sum that completely decomposes and separates P factorial is just P of z and prime of z is the one that takes care of PL over P factorials。

 P minus1 factorial， so use this equation and then again we get a very simple differential equation now for the。

Cumulative costs exponential generating function for path length and BSDs。

The decomposition is important， it got to be precise， it's got to be correct。

 but once you have that decomposition， you automatically get a relationship that the exponential generating function for the cumulative cost and the count you have have to satisfy。

And again， solving for a C of Z。Gives。嗯呃。It was just simplifying that， substituting in for PZ。

W gives a very simple equation。So recognize that equation， we saw that in the first lecture actually。

 that's the equation that came up with solving the quick sort recurrence。

 I guess it came up in the generating function lecture。Pretty much the same equation。

So just with that observation， we solve that because it's a first。

The first ordered differential equation that has a simple integration factor and was not difficult to solve。

 so now we can fit summarize the analysis of an expected length in a BST bill from aandnda permutation on this slide。

Start with the definitional equation for the cumulative generating function substitute in the construction of the decomposition。

 differentiate to simplify substitute to get further simplification and that is a generating function that has the solution2 over1 minus z squared log of1 over1 minus e minus201 minus z squared and those are elementary series that we can expand to find the coefficients as we did before。

 to show that the average internal path length in a binary search tree is asymptototic to 2 and natural log n。

 so a log n as the factor if you divide by n log n to the average node in a binary search tree square root of n in a binary catalan tree。

And。Since the same equation comes up and people who've had algorithms courses know that there's a bijection between quicks sortt and binary search trees that explains this。

 we could have analyzed binary search trees just by taking advantage of this bijection。So that is。

In QuickSo you have the first entry in the permutation is the partitioning element and the smaller ones and larger ones are mixed and then after the partitioning you do them independently and that's pretty much the same in a binary search tree the first one is the root and then you do the left and right independently so you can show that the average number compares for quickSo is exactly the average external path length of BST built from a random permutation and that's an interesting byjection to know to take advantage of。

Now this same approach works for a lot of other parameters of trees。

 and there's exercises to compute the number of leaves of trees and other things like that in the text。

For finding the height of trees， it's much more intricate。

 it's a different approach because it doesn't break down really as well but that's an interesting problem because it's a natural thing to want to know what's the furthest node from the root in a tree that tells us more information about the shape of the tree。

 so the height derivation is described in the text and actually for for both binary search trees and trees the height was an open problem for quite a while so just to summarize what we know about the shapes of these two different tree structures。

We looked at random binary trees and binary search trees built from ara permutation。

Those are typical shapes of those trees。The average path length that's the average distance to a node in a random tree for minor trees is squared of P He。

 for BSTs from random permutation， it's two natural log n。And again， in the book。

 there's some description， although both of these derivations are quite intricate。

 the height now is known for random binary trees to be twice that average。

 and for random BSTs it's a little more than twice it's a constant times natural again。

 where the constant is about 4。31。呃。And again， there's lots of things that you might want to study about trees and I've only really talked in detail about pathling。

But you can find plenty of examples in the book that show that the same approach works for many other tree parameters as well and certainly don't have time to talk about all of them in this lecture that's a summary of the study of path length in trees。



![](img/d5c768bdcd1c12f80f4c5827196debf4_2.png)

![](img/d5c768bdcd1c12f80f4c5827196debf4_3.png)