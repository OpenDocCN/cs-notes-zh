# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P101：26_02_03_按秩合并分析-进阶选学.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/c2e01d992c835577ca73a86a895428d2_0.png)

In this video we'll provide for the first time， concrete evidence that the lazy union approach to the union find data structure is viable。

 specifically will prove that the worstcase running time of both the fine and the union operation is logarithmic in n the number of objects stored in the data structure。

 we're going to do it even better later once we introduce a second optimization known as path compression。

 but an important stepping stone is to understand just is why just union by rank already gets us to a reasonable logarithmic runtime bound。

So a quick review of the laser union approach to implementing the union fine data structure。

 so with each node we're going to maintain a parent pointer and it's no longer the case that we insist the parent pointer point directly to the leader of a group。

 rather we just insist that the collection of parent pointers induces a collection of directed trees。

 the root of each tree that is the node which it's its own parent we're going to define as the leader of that group so given any old object X。

 how do you implement find how do you figure out what the leader vertex is well you just traverse parent pointers up until you get to the root of that particular group。

So for this implementation of the fine operation， the worst case running time is just going to be the longest path of parent pointers that you ever have to traverse to get from an object to some root。

 So the way we're going to quantify that is using these ranks。

 so this is again a field that we maintain for each object。

 and for now this will break down later but for now before we have path compression we're going to maintain the invariant that the rank of an object X is exactly the largest number of pointers you have to traverse from some leaf to get to X。

As a consequence， the biggest rank of any object is the longest path from any leaf to any route。

 and that's going to be an upper bound on the worst case running time of the find operation。

So let's move on to the union operation So here given two objects X and Y you need to fuse their two trees。

 they're two groups so you find the roots of the two trees so you call a fine on x you call a fine on y that gives you their two respective roots and now you install one as a new child of the other and we saw on a quiz in the last video that if you're not careful about which root you install as a child under the other you can wind up with these long chains and be stuck with a linear worstcase time for both fine and union so instead we have this union by rank optimization which says well we want to keep our tree from getting scraggly and the way we're going to do that is when we have a shallow tree and a deep tree we make the shallow tree a child under the root of the deep one that prevents the tree from getting even deeper Now there is a situation where the two trees have exactly the same depth that is where the two roots have exactly the same rank in that case we just proceed arbitrarily Now when we merge two trees that both had a common rank R it's important that in the new tree the rank has gone up to R plus ones we need to update we need to increment the rank of the new root。

To reflect that increase。So that's where we've already been。 Where are we going to next。

 Well the plan for this video is to show that with the union by rank optimization。

 the maximum rank of any node is always bounded above by log base two of n where n is the number of objects in the data structure。

 Now we just said the worst case running time of find is governed by the maximum rank so logarithmic maximum rank means logarithmic running time of find that also carries over to the union operation。

 remember union is just two fines plus constant work to rewire one pointer so that's going to give us a logarithmic time bound on both operations。

 So let's see why that's true。So let's begin the analysis with a few simple but useful properties that follow immediately from our invariant from the way that we change the ranks of objects as we do funds and as we do union。

So the first simple property is focus on your favorite object X and watch this object's rank change over the course of the data structure as we do fines and unions。

 how can it change well when we do a fine we don't change anything。

 all the ranks stay the same when we do a union， all the ranks stay the same Well。

 except there is one case in the union where the rank of a single node gets bumped up by one gets increased so ranks only go up over time for all of the objects that's property one。

So the second property is again， pretty much trivial， but really， really useful。

 So what is the situation in which somebody's rank gets bumped up by one。

 Well's only take the union of two trees that have a common rank。

 and then whichever the two roots that we pick to be the root of the new bigger tree。

 That's the object whose rank gets bumped up by one。 It's the new root of this fused tree。

 So in particular， the only type of object that can ever get a rank increase is a root。

 if you're not a root， your rank will not go up。 Furthermore。

 once you're not a root in this data structure， you will never be a root again in the future。

 there is no process by which you shed your parent， once you have a parent other than yourself。

 you will always have exactly that parent。Putting those two observations together。

 we find that as soon as an object X becomes a non root。

 as soon as it has apparent other than itself， its rank is frozen for the rest of time， forevermore。

The third and final simple property follows from a formula we mentioned in the last video about computing ranks。

 so remember the rank of a node in general is going to be one more than the maximum rank of any of its children。

 so if you have a child and there's some path from a leaf to that child that takes five hops。

 the path to you from that child is' going to take six hops as a consequence as you go from the leaf up to the root you will see a strictly increasing sequence of ranks。

 the rank of a parent is always strictly more than the rank of all of its children。

So that's it for the immediate properties， let's go to a property which is a little less immediate。

 but still this next lema， which I'm going to call the rank lemma。

 it's the best kind of lemma so on the one hand it's just not that hard to prove I'll give you a full proof in the following two slides on the other hand it's really powerful it's going to play a crucial role in the analysis we're doing right now a logar neck runtime bound with the union by rank optimization and we'll keep using it again as a workhor once we introduce path compression and prove better bounds on the operations。

So what's the rank， let me say， Well， it controls the population size of objects that have a given rank。

 So we wanted to apply at all intermediate stages of our data structures。

 So we're going to consider an arbitrary sequence of unions。 You can throw in some fines as well。

 I don't care。 finds don't change the data structures。 so they're totally irrelevant。

 So think about a sequence of unions， a sequence of mergers。 The claim is for every nonne integer R。

 The number of objects that have rank exactly R at this time is at most n。

 the total number of objects divided by2 to the R。 So for example， if for equals 0。

 it says at most n objects have rank  zero。 That's a trivial statement。 There's only n objects。

 But at any given time， the number of objects that have rank 1 is at most n over 2。

 The number of objects that have rank 2 is at most n over 4 and so on。And if you think about it。

 if we succeed in proving the rank lemma， we're pretty much done showing the efficacy of the union by rank optimization。

 so in particular， once you take R in this keylemma to be log based2 of n。

 it says that there's at most one object that has rank log based 2 of n and there can't be any objects that have rank strictly larger。

 that is this lemma implies that the maximum rank at all times is bounded above by log basedase 2 of n。

And remember， the maximum rank is the longest path of pointers traversals you ever needed to get from a leaf to a root。

 and that means the most amount of work we'll ever do in a find and therefore in a union is big O of login。

Okay， so I've now teased you with the consequences of the rank lemma assuming that it's true。

 but why is it true， Let's turn to the proof。I'm going to break the proof down into two claims。

 claim one and claim two will'll see that the two claims easily imp the rank limit。

So claim1 asks you to consider two objects X and y that have exactly the same rank R。

 and the claim asserts that these subtes of these two objects have to be disjoint。

 they have no objects in common， and hereby the subtree of an object。

 I just mean the other objects that can reach this one by following a sequence of parent pointers。

 so that is a subte at X is the objects from which you can reach X。

 the subt at y is the objects from which you can reach Y。

The second claim is that if you look at any object that has rank R and you look at its subtree。

 that is if you look at the number of objects that can reach this object X by following pointers。

 there have to be a lot of them， there have to be at least two raised to that object's rank R objects in its subt。

Notice that if we prove claim1 and claim 2， then the rank lemma follows easily why well fix a value for R 210。

 I don't care what look at all the nodes that have this rank R by claim2。

 each of them has at least2 to the R objects that can reach them and by claim1。

 these have to be disjoint sets of objects Well there's only n objects to go around。

 and if each of these disjoint sets has at least2 to the R of them。

 there can be at most n over 2 to the R such groups that is at most n over 2 to the R nodes objects with this rank R。

So we've reduced the proof of the rank lemma to proving claims one and two， I will do them in turn。

So if we claim one let me go via the contrapositive that is I will assume that the conclusion is false and I will show that the hypothesis must then also be false。

 so let's assume that we have two objects X and Y and their subtes are not disjoint。

 that is there exists an object Z from which you can reach X and from the same object Z you can also reach y via a sequence of parent pointers。

Well now let's use the fact that we're dealing with a directed tree right so if you start an object Z there's only a unique parent pointer to follow each time so that is all of the objects reachable from Z。

 they form a directed path leading up to the root of Z's group。

 so the only way for both X and Y to be reachable from Z they have to both be on this path if they're both on this path then one has to be an ancestor of the other。

So now we're going to use the third of our symbol properties that we observed that is on every path to the root。

 ranks strictly go up each time， so whichever of x or y's and ancestor or the other that has strictly higher rank。

 therefore x and Y do not have the same rank that completes the proof of claim1。

So let's move on to claim two， remember claim to asserts that an object of rank R necessarily has two to the R objects or more in its subree。

 that's how many objects can actually reach this object X by following parent pointers。

So for this proof we're going to proceed by induction on the number of operations and again。

 remember， fine operations have no effect on the data structure so we can ignore them。

 so it's just by induction on the number of union operations that happen。So for the base case。

 before we've done any unions whatsoever， we're doing just fine。

 every object has a rank of zero and the subt size of every object is equal to one。

 that object itself， also known as two to the zero。

Now for the inductive step there's an easy case and a hard case。

 the easy case is where nobody's rank changes where we do a union and everybody's rank stays exactly the same in this case we're golden why well when you do a union subtree sizes only go up。

 there's only more pointers so there's only more objects that can reach any yet than other objects so subtree sizes go up。

 ranks stay the same if we had this inequality of subte sizes being at least two to the R before。

 we have it equally well now。

![](img/c2e01d992c835577ca73a86a895428d2_2.png)

So the interesting case is when somebody's rank actually changes how can that happen Well it happens in only one particular way that we understand well we're looking at a union operation between objects X and y。

 suppose the roots of these objects are S1 and S2 respectively it's only when these two roots have the same rank let's call that common rank R that somebody's rank gets changed in particular we're going to break ties as we did in the previous video S2 will be the root of the fuseed tree S1 will become a child of it and in that case S2's rank gets bumped up by1 it goes from R to r plus1 Now notice in this case we do have something to prove what are we trying to establish we're trying to establish that every subtree size is big as a function of the rank so S2's rank has gone up and therefore the lower bound the bar that we have to meet for the subtree size has also gone up it's doubled。

So in this case we actually have to scrutinize S2's new subte。

 so what is its new subte while it's really just composed from its old subt and it inherits S1 and all of its subtrees。

Well， in that case， we know that S2's new subte size， the number of objects that can reach it。

 is just its old subte size plus the old subte size of S1。

But then we're in good shape because we have the inductive hypothesis to rescue us。

 So remember before this union by the inductive hypothesis for every object with a given rank， say R。

 it had at least2 to the R objects in its subree， so S1 and S2 both had rank R before this union so before this union both of their subte sizes were at least 2 to the R。

So S2's new subte size is bounded below by2 to the R plus 2 to the R。

 a quantity also known as 2 raised to the r plus 1。

 quite convenient R plus 1 is S2's new rank so even with S2's new bigger rank its subtree size is still meeting the lower bound meeting the target of two raised to that new rank2 raised to the R plus 1 So that completes the inductive step。

 therefore it completes the proof of claim2 that objects of rank R have subre sizes at least 2 to the R therefore it completes the proof of the rank lemma that for every rank R there's the most n over 2 to the R nodes of rank R and remember the rank lemma implies that the maximum rank at all times is bounded by log base2 of n as long as you're using union by rank and that implies that with this first optimization。

 the worst case running time of union and find are both big O of log n or n is the number of objects in the data structure。

